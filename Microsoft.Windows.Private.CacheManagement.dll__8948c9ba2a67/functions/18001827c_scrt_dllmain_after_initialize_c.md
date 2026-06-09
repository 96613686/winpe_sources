# __scrt_dllmain_after_initialize_c

- ea: `0x18001827c`
- end: `0x1800182b0`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: `char()`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x180018620`

## callees

- `0x18001827c`
- `0x1800189b0`
- `0x180018ee0`
- `0x180018ee8`
- `0x18001c59d`
- `0x18001c5a3`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char _scrt_dllmain_after_initialize_c()
{
  _crt_argv_mode startup_argv_mode; // eax

  if ( (unsigned int)_scrt_is_ucrt_dll_in_use() )
  {
    _isa_available_init();
  }
  else
  {
    startup_argv_mode = get_startup_argv_mode();
    if ( configure_narrow_argv_0(startup_argv_mode) )
      return 0;
    initialize_narrow_environment_0();
  }
  return 1;
}

```

## disassembly

```asm
0x18001827c  sub     rsp, 28h
0x180018280  call    __scrt_is_ucrt_dll_in_use
0x180018285  test    eax, eax
0x180018287  jz      short loc_180018290
0x180018289  call    __isa_available_init
0x18001828e  jmp     short loc_1800182A9
0x180018290  call    _get_startup_argv_mode
0x180018295  mov     ecx, eax; mode
0x180018297  call    _configure_narrow_argv_0
0x18001829c  test    eax, eax
0x18001829e  jz      short loc_1800182A4
0x1800182a0  xor     al, al
0x1800182a2  jmp     short loc_1800182AB
0x1800182a4  call    _initialize_narrow_environment_0
0x1800182a9  mov     al, 1
0x1800182ab  add     rsp, 28h
0x1800182af  retn
```
