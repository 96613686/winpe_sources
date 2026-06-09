# __scrt_dllmain_after_initialize_c

- ea: `0x180002974`
- end: `0x1800029a8`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x1800025f8`

## callees

- `0x180002974`
- `0x180002eb0`
- `0x18000313c`
- `0x180003148`
- `0x1800031e6`
- `0x18000320a`

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
0x180002974  sub     rsp, 28h
0x180002978  call    __scrt_is_ucrt_dll_in_use
0x18000297d  test    eax, eax
0x18000297f  jz      short loc_180002988
0x180002981  call    __isa_available_init
0x180002986  jmp     short loc_1800029A1
0x180002988  call    _get_startup_argv_mode
0x18000298d  mov     ecx, eax; mode
0x18000298f  call    _o__configure_narrow_argv_0
0x180002994  test    eax, eax
0x180002996  jz      short loc_18000299C
0x180002998  xor     al, al
0x18000299a  jmp     short loc_1800029A3
0x18000299c  call    _initialize_narrow_environment
0x1800029a1  mov     al, 1
0x1800029a3  add     rsp, 28h
0x1800029a7  retn
```
