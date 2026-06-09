# __scrt_dllmain_after_initialize_c

- ea: `0x1800015bc`
- end: `0x1800015f0`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: `char()`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x1800010e8`

## callees

- `0x1800015bc`
- `0x180001b88`
- `0x180001e14`
- `0x180001e20`
- `0x180001efe`
- `0x180001f16`

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
0x1800015bc  sub     rsp, 28h
0x1800015c0  call    __scrt_is_ucrt_dll_in_use
0x1800015c5  test    eax, eax
0x1800015c7  jz      short loc_1800015D0
0x1800015c9  call    __isa_available_init
0x1800015ce  jmp     short loc_1800015E9
0x1800015d0  call    _get_startup_argv_mode
0x1800015d5  mov     ecx, eax; mode
0x1800015d7  call    _o__configure_narrow_argv_0
0x1800015dc  test    eax, eax
0x1800015de  jz      short loc_1800015E4
0x1800015e0  xor     al, al
0x1800015e2  jmp     short loc_1800015EB
0x1800015e4  call    _initialize_narrow_environment
0x1800015e9  mov     al, 1
0x1800015eb  add     rsp, 28h
0x1800015ef  retn
```
