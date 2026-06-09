# __scrt_dllmain_after_initialize_c

- ea: `0x180002140`
- end: `0x180002174`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: `char()`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x180001d18`

## callees

- `0x180002140`
- `0x1800027d0`
- `0x180002c70`
- `0x180002c7c`
- `0x180002d1a`
- `0x180002d3e`

## pseudocode

```c
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
    if ( o__configure_narrow_argv_0(startup_argv_mode) )
      return 0;
    initialize_narrow_environment();
  }
  return 1;
}

```

## disassembly

```asm
0x180002140  sub     rsp, 28h
0x180002144  call    __scrt_is_ucrt_dll_in_use
0x180002149  test    eax, eax
0x18000214b  jz      short loc_180002154
0x18000214d  call    __isa_available_init
0x180002152  jmp     short loc_18000216D
0x180002154  call    _get_startup_argv_mode
0x180002159  mov     ecx, eax; mode
0x18000215b  call    _o__configure_narrow_argv_0
0x180002160  test    eax, eax
0x180002162  jz      short loc_180002168
0x180002164  xor     al, al
0x180002166  jmp     short loc_18000216F
0x180002168  call    _initialize_narrow_environment
0x18000216d  mov     al, 1
0x18000216f  add     rsp, 28h
0x180002173  retn
```
