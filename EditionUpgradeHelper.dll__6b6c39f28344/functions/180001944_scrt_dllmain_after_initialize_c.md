# __scrt_dllmain_after_initialize_c

- ea: `0x180001944`
- end: `0x180001978`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: `char()`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x1800015c8`

## callees

- `0x180001944`
- `0x180001f00`
- `0x18000218c`
- `0x180002198`
- `0x180002436`
- `0x18000245a`

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
0x180001944  sub     rsp, 28h
0x180001948  call    __scrt_is_ucrt_dll_in_use
0x18000194d  test    eax, eax
0x18000194f  jz      short loc_180001958
0x180001951  call    __isa_available_init
0x180001956  jmp     short loc_180001971
0x180001958  call    _get_startup_argv_mode
0x18000195d  mov     ecx, eax; mode
0x18000195f  call    _o__configure_narrow_argv_0
0x180001964  test    eax, eax
0x180001966  jz      short loc_18000196C
0x180001968  xor     al, al
0x18000196a  jmp     short loc_180001973
0x18000196c  call    _initialize_narrow_environment
0x180001971  mov     al, 1
0x180001973  add     rsp, 28h
0x180001977  retn
```
