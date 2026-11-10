# Naming Conventions & Architecture Rules — DriveNow

## R1: Test Projects, Test Classes, and Test Files
* Test project name: DriveNow.UnitTests
* Test classes and test files must be named using the class under test followed by Tests (e.g., PricingServiceTests.cs, BookingServiceTests.cs, TaxCalculatorTests.cs).

## R2: Test Methods Naming Style
* Chosen Style: Should_ExpectedResult_When_State
* Justification: This style clearly describes what the test expects to happen and under what condition, making test reports clear and self-documenting.
* Examples from DriveNow:
  1. Should_CalculateCorrectPrice_When_RentalPeriodIsValid (Testing PricingService)
  2. Should_CancelBookingSuccessfully_When_BookingIsActive (Testing CancellationService)
  3. Should_CalculateTaxCorrectly_When_AmountIsPositive (Testing TaxCalculator)

## R3: Test Doubles & Fakers
* Hand-written test doubles must start with Fake or Spy (e.g., FakeBookingRepository, SpySmsSender).
* Bogus data generators must end with Faker or Builder (e.g., CustomerFaker, BookingFaker).
* AutoFixture customizations must be encapsulated in dedicated fixture setup classes.

## R4: Production Code Namespaces
* Interfaces: Located in DriveNow.Application (or sub-folders like Receipts) and prefixed with I (e.g., ITaxCalculator, ICurrencyFormatter).
* Services: Located in DriveNow.Application.Services or specific feature folders (e.g., BookingService, PricingService, ReceiptService).
* Entities: Located in DriveNow.Domain.Entities (e.g., Booking).
* Exceptions: Located in domain/application sub-namespaces ending with Exception.