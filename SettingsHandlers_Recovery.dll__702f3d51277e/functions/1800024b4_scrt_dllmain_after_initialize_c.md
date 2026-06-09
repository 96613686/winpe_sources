# __scrt_dllmain_after_initialize_c

- ea: `0x1800024b4`
- end: `0x1800024e8`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x180002038`

## callees

- `0x1800024b4`
- `0x180002a88`
- `0x180002d14`
- `0x180002d20`
- `0x180002dfe`
- `0x180002e22`

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
0x1800024b4  sub     rsp, 28h
0x1800024b8  call    __scrt_is_ucrt_dll_in_use
0x1800024bd  test    eax, eax
0x1800024bf  jz      short loc_1800024C8
0x1800024c1  call    __isa_available_init
0x1800024c6  jmp     short loc_1800024E1
0x1800024c8  call    _get_startup_argv_mode
0x1800024cd  mov     ecx, eax; mode
0x1800024cf  call    _o__configure_narrow_argv_0
0x1800024d4  test    eax, eax
0x1800024d6  jz      short loc_1800024DC
0x1800024d8  xor     al, al
0x1800024da  jmp     short loc_1800024E3
0x1800024dc  call    _initialize_narrow_environment
0x1800024e1  mov     al, 1
0x1800024e3  add     rsp, 28h
0x1800024e7  retn
```
