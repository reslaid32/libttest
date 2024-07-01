# libttest (tinytest)

## How to use

To conduct a test:
- Include the header file tinytest.h

Example of adding tests:
  
  - Also, you can use ttest_t instead of tinytest_t
  
  ```c
  ttest_t testsArr[] = {
      { test_func1, "Test Function 1" },
      { test_func2, "Test Function 2" }
  };
  ```

Running tests:

  ```c
  int nFailed = tt_suit(testsArr, ttnumtests(testsArr));
  ```

  nFailed - number of failed tests

Example code:

  ```c
  #include "tinytest.h"

  int test_func1(void) {
      ttcheck(1 == 1);
      ttcheck(2 > 1);
      ttdone();
  }

  int test_func2(void) {
      ttcheck(1 != 2);
      ttcheck((5 % 10) == (10 / 2));
      ttdone();
  }

  int main() {
      ttest_t testsArr[] = {
          { test_func1, "Test Function 1" },
          { test_func2, "Test Function 2" }
      };

      int nFailed = tt_suit(testsArr, ttnumtests(testsArr));

      return nFailed;
  }
  ```
