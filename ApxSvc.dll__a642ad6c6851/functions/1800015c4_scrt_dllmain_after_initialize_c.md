# __scrt_dllmain_after_initialize_c

- ea: `0x1800015c4`
- end: `0x1800015f8`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: `char()`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x180001238`

## callees

- `0x1800015c4`
- `0x180001b30`
- `0x180001dbc`
- `0x180001dc8`
- `0x180001e6e`
- `0x180001e92`

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
0x1800015c4  sub     rsp, 28h
0x1800015c8  call    __scrt_is_ucrt_dll_in_use
0x1800015cd  test    eax, eax
0x1800015cf  jz      short loc_1800015D8
0x1800015d1  call    __isa_available_init
0x1800015d6  jmp     short loc_1800015F1
0x1800015d8  call    _get_startup_argv_mode
0x1800015dd  mov     ecx, eax; mode
0x1800015df  call    _o__configure_narrow_argv_0
0x1800015e4  test    eax, eax
0x1800015e6  jz      short loc_1800015EC
0x1800015e8  xor     al, al
0x1800015ea  jmp     short loc_1800015F3
0x1800015ec  call    _initialize_narrow_environment
0x1800015f1  mov     al, 1
0x1800015f3  add     rsp, 28h
0x1800015f7  retn
```
