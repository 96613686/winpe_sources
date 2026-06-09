# __scrt_dllmain_after_initialize_c

- ea: `0x1800019c4`
- end: `0x1800019f8`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x180001648`

## callees

- `0x1800019c4`
- `0x180001f30`
- `0x1800021bc`
- `0x1800021c8`
- `0x180002272`
- `0x180002296`

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
0x1800019c4  sub     rsp, 28h
0x1800019c8  call    __scrt_is_ucrt_dll_in_use
0x1800019cd  test    eax, eax
0x1800019cf  jz      short loc_1800019D8
0x1800019d1  call    __isa_available_init
0x1800019d6  jmp     short loc_1800019F1
0x1800019d8  call    _get_startup_argv_mode
0x1800019dd  mov     ecx, eax; mode
0x1800019df  call    _o__configure_narrow_argv_0
0x1800019e4  test    eax, eax
0x1800019e6  jz      short loc_1800019EC
0x1800019e8  xor     al, al
0x1800019ea  jmp     short loc_1800019F3
0x1800019ec  call    _initialize_narrow_environment
0x1800019f1  mov     al, 1
0x1800019f3  add     rsp, 28h
0x1800019f7  retn
```
