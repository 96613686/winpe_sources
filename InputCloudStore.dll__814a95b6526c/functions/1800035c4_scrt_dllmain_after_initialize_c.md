# __scrt_dllmain_after_initialize_c

- ea: `0x1800035c4`
- end: `0x1800035f8`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x180003248`

## callees

- `0x1800035c4`
- `0x180003b60`
- `0x180003dec`
- `0x180003df8`
- `0x180003f36`
- `0x180003f5a`

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
0x1800035c4  sub     rsp, 28h
0x1800035c8  call    __scrt_is_ucrt_dll_in_use
0x1800035cd  test    eax, eax
0x1800035cf  jz      short loc_1800035D8
0x1800035d1  call    __isa_available_init
0x1800035d6  jmp     short loc_1800035F1
0x1800035d8  call    _get_startup_argv_mode
0x1800035dd  mov     ecx, eax; mode
0x1800035df  call    _o__configure_narrow_argv_0
0x1800035e4  test    eax, eax
0x1800035e6  jz      short loc_1800035EC
0x1800035e8  xor     al, al
0x1800035ea  jmp     short loc_1800035F3
0x1800035ec  call    _initialize_narrow_environment
0x1800035f1  mov     al, 1
0x1800035f3  add     rsp, 28h
0x1800035f7  retn
```
