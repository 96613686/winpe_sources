# __scrt_dllmain_after_initialize_c

- ea: `0x180001900`
- end: `0x180001934`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: `char()`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x1800014a8`

## callees

- `0x180001900`
- `0x180002180`
- `0x18000240c`
- `0x180002418`
- `0x1800024ba`
- `0x1800024de`

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
0x180001900  sub     rsp, 28h
0x180001904  call    __scrt_is_ucrt_dll_in_use
0x180001909  test    eax, eax
0x18000190b  jz      short loc_180001914
0x18000190d  call    __isa_available_init
0x180001912  jmp     short loc_18000192D
0x180001914  call    _get_startup_argv_mode
0x180001919  mov     ecx, eax; mode
0x18000191b  call    _o__configure_narrow_argv_0
0x180001920  test    eax, eax
0x180001922  jz      short loc_180001928
0x180001924  xor     al, al
0x180001926  jmp     short loc_18000192F
0x180001928  call    _initialize_narrow_environment
0x18000192d  mov     al, 1
0x18000192f  add     rsp, 28h
0x180001933  retn
```
