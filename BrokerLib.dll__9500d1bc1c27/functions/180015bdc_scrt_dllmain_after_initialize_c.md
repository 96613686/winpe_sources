# __scrt_dllmain_after_initialize_c

- ea: `0x180015bdc`
- end: `0x180015c10`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x1800157d8`

## callees

- `0x180015bdc`
- `0x180015fe4`
- `0x18001649c`
- `0x1800164a8`
- `0x180016532`
- `0x180016556`

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
0x180015bdc  sub     rsp, 28h
0x180015be0  call    __scrt_is_ucrt_dll_in_use
0x180015be5  test    eax, eax
0x180015be7  jz      short loc_180015BF0
0x180015be9  call    __isa_available_init
0x180015bee  jmp     short loc_180015C09
0x180015bf0  call    _get_startup_argv_mode
0x180015bf5  mov     ecx, eax; mode
0x180015bf7  call    _o__configure_narrow_argv_0
0x180015bfc  test    eax, eax
0x180015bfe  jz      short loc_180015C04
0x180015c00  xor     al, al
0x180015c02  jmp     short loc_180015C0B
0x180015c04  call    _initialize_narrow_environment
0x180015c09  mov     al, 1
0x180015c0b  add     rsp, 28h
0x180015c0f  retn
```
