# __scrt_dllmain_after_initialize_c

- ea: `0x180001da4`
- end: `0x180001dd8`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: `char()`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x180001a28`

## callees

- `0x180001da4`
- `0x180002610`
- `0x18000289c`
- `0x1800028a8`
- `0x18000298e`
- `0x1800029b2`

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
0x180001da4  sub     rsp, 28h
0x180001da8  call    __scrt_is_ucrt_dll_in_use
0x180001dad  test    eax, eax
0x180001daf  jz      short loc_180001DB8
0x180001db1  call    __isa_available_init
0x180001db6  jmp     short loc_180001DD1
0x180001db8  call    _get_startup_argv_mode
0x180001dbd  mov     ecx, eax; mode
0x180001dbf  call    _o__configure_narrow_argv_0
0x180001dc4  test    eax, eax
0x180001dc6  jz      short loc_180001DCC
0x180001dc8  xor     al, al
0x180001dca  jmp     short loc_180001DD3
0x180001dcc  call    _initialize_narrow_environment
0x180001dd1  mov     al, 1
0x180001dd3  add     rsp, 28h
0x180001dd7  retn
```
