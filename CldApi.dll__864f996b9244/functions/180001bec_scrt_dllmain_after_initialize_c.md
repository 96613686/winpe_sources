# __scrt_dllmain_after_initialize_c

- ea: `0x180001bec`
- end: `0x180001c20`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x180001768`

## callees

- `0x180001bec`
- `0x180001fc0`
- `0x18000224c`
- `0x1800022a6`
- `0x1800022be`
- `0x1800106a0`

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
0x180001bec  sub     rsp, 28h
0x180001bf0  call    __scrt_is_ucrt_dll_in_use
0x180001bf5  test    eax, eax
0x180001bf7  jz      short loc_180001C00
0x180001bf9  call    __isa_available_init
0x180001bfe  jmp     short loc_180001C19
0x180001c00  call    _get_startup_argv_mode
0x180001c05  mov     ecx, eax; mode
0x180001c07  call    _o__configure_narrow_argv_0
0x180001c0c  test    eax, eax
0x180001c0e  jz      short loc_180001C14
0x180001c10  xor     al, al
0x180001c12  jmp     short loc_180001C1B
0x180001c14  call    _initialize_narrow_environment
0x180001c19  mov     al, 1
0x180001c1b  add     rsp, 28h
0x180001c1f  retn
```
