# WAVEWATCH III Build & Code Guidelines

## Build Commands
- CMake (recommended): `cmake /path/to/WW3 -DSWITCH=/path/to/switch_file -DCMAKE_INSTALL_PREFIX=install`
- Build: `make` or single program: `cmake --build . --target ww3_shel`
- Debug build: `cmake .. -DCMAKE_BUILD_TYPE=Debug`
- Legacy build: `w3_setup path_to_source -c compiler_option -s switch_option` then `w3_make [program_name]`

## Test Commands
- Run test: `run_test source_dir test_name [options]`
- Common options: `-n nproc` (parallel processors), `-s switch_file`, `-g grid_file`

## Code Style
- Fortran modules: `w3xxxmd.F90` naming pattern
- Programs: `ww3_xxxx.F90` naming pattern
- Use consistent indentation (2-4 spaces)
- Error handling via function return values and logging
- Follow existing code patterns in neighboring files
- Intel compiler flags: `-no-fma -ip -g -traceback -i4 -real-size 32 -fp-model precise`
- GNU compiler flags: `-g -fno-second-underscore -ffree-line-length-none`