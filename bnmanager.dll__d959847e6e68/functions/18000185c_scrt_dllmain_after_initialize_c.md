# __scrt_dllmain_after_initialize_c

- ea: `0x18000185c`
- end: `0x180001890`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: `char()`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x1800014a8`

## callees

- `0x18000185c`
- `0x180001ccc`
- `0x180002120`
- `0x18000212c`
- `0x1800021de`
- `0x180002202`

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
0x18000185c  sub     rsp, 28h
0x180001860  call    __scrt_is_ucrt_dll_in_use
0x180001865  test    eax, eax
0x180001867  jz      short loc_180001870
0x180001869  call    __isa_available_init
0x18000186e  jmp     short loc_180001889
0x180001870  call    _get_startup_argv_mode
0x180001875  mov     ecx, eax; mode
0x180001877  call    _o__configure_narrow_argv_0
0x18000187c  test    eax, eax
0x18000187e  jz      short loc_180001884
0x180001880  xor     al, al
0x180001882  jmp     short loc_18000188B
0x180001884  call    _initialize_narrow_environment
0x180001889  mov     al, 1
0x18000188b  add     rsp, 28h
0x18000188f  retn
```
