# __scrt_dllmain_after_initialize_c

- ea: `0x1800017c4`
- end: `0x1800017f8`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x180001448`

## callees

- `0x1800017c4`
- `0x180001d60`
- `0x180001fec`
- `0x180001ff8`
- `0x1800020ee`
- `0x180002112`

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
0x1800017c4  sub     rsp, 28h
0x1800017c8  call    __scrt_is_ucrt_dll_in_use
0x1800017cd  test    eax, eax
0x1800017cf  jz      short loc_1800017D8
0x1800017d1  call    __isa_available_init
0x1800017d6  jmp     short loc_1800017F1
0x1800017d8  call    _get_startup_argv_mode
0x1800017dd  mov     ecx, eax; mode
0x1800017df  call    _o__configure_narrow_argv_0
0x1800017e4  test    eax, eax
0x1800017e6  jz      short loc_1800017EC
0x1800017e8  xor     al, al
0x1800017ea  jmp     short loc_1800017F3
0x1800017ec  call    _initialize_narrow_environment
0x1800017f1  mov     al, 1
0x1800017f3  add     rsp, 28h
0x1800017f7  retn
```
