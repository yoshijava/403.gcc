# Patch for SPEC CPU2006 403.gcc
This bug is due to wrong usage of function pointer, and happened to work on most architecture; however, it fails on iPhone and some other architectures with different calling conventions, as the discussion in the mailing list of GNU GCC. More details can be found at: https://gcc.gnu.org/bugzilla/show_bug.cgi?id=12081



# Mail to SPEC.org
```
SPEC CPU version info:
Version summary:
    CPU2006 version: 1.2
 Benchmarks version: 118
      Tools version: 118
    runspec version: 6674 ($Id: runspec 6674 2011-07-21 16:47:54Z CloyceS $)


I would like to propose a change to benchmark 403.gcc

According to the gnu gcc mailing list, this is a known bug solved in gcc version >= 4.8.
https://gcc.gnu.org/bugzilla/show_bug.cgi?id=12081

This problem occurs to me when porting this benchmark to iPhone using xcode toolchain:
Apple clang version 12.0.0 (clang-1200.0.32.27)
Target: x86_64-apple-darwin19.6.0
Thread model: posix


The solution posted in gnu's mailing list is based on c++ technique, so not applicable for 403.gcc which is based on gcc 3.2
Attached please find my own handcrafted patch.
```
