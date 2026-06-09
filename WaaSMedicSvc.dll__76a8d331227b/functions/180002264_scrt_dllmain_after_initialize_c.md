# __scrt_dllmain_after_initialize_c

- ea: `0x180002264`
- end: `0x180002298`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: `char()`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x180001ee8`

## callees

- `0x180002264`
- `0x180002b70`
- `0x180002dfc`
- `0x180002e08`
- `0x180002eee`
- `0x180002f12`

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
0x180002264  sub     rsp, 28h
0x180002268  call    __scrt_is_ucrt_dll_in_use
0x18000226d  test    eax, eax
0x18000226f  jz      short loc_180002278
0x180002271  call    __isa_available_init
0x180002276  jmp     short loc_180002291
0x180002278  call    _get_startup_argv_mode
0x18000227d  mov     ecx, eax; mode
0x18000227f  call    _o__configure_narrow_argv_0
0x180002284  test    eax, eax
0x180002286  jz      short loc_18000228C
0x180002288  xor     al, al
0x18000228a  jmp     short loc_180002293
0x18000228c  call    _initialize_narrow_environment
0x180002291  mov     al, 1
0x180002293  add     rsp, 28h
0x180002297  retn
```
