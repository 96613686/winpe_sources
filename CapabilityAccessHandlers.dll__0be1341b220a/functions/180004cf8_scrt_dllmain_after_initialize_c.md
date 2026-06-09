# __scrt_dllmain_after_initialize_c

- ea: `0x180004cf8`
- end: `0x180004d2c`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: `char()`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x180004958`

## callees

- `0x180004cf8`
- `0x1800052b4`
- `0x180005540`
- `0x18000554c`
- `0x18000562e`
- `0x180005652`

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
0x180004cf8  sub     rsp, 28h
0x180004cfc  call    __scrt_is_ucrt_dll_in_use
0x180004d01  test    eax, eax
0x180004d03  jz      short loc_180004D0C
0x180004d05  call    __isa_available_init
0x180004d0a  jmp     short loc_180004D25
0x180004d0c  call    _get_startup_argv_mode
0x180004d11  mov     ecx, eax; mode
0x180004d13  call    _o__configure_narrow_argv_0
0x180004d18  test    eax, eax
0x180004d1a  jz      short loc_180004D20
0x180004d1c  xor     al, al
0x180004d1e  jmp     short loc_180004D27
0x180004d20  call    _initialize_narrow_environment
0x180004d25  mov     al, 1
0x180004d27  add     rsp, 28h
0x180004d2b  retn
```
