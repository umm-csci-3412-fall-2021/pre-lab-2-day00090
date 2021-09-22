# Leak report

_In this project, there is one C file to be considered for leaks: 'clean_whitespace.c'. Through memory analysis with the command valgrind, we can see that there is indeed a memory leak in the code. 46 bytes of data in 6 blocks is being used upon exit, with a total heap usage of 7 allocations, 1 frees, at a limit of 1,070 bytes. These 46 bytes of data are shown to be lost at line 41, where a slot is allocated for all the saved characters with calloc. Three functions use the allocated slot at different times, producing the problem: strip, is_clean, and main._
