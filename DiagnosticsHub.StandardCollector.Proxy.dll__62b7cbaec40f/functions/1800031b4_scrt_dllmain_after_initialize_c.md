# __scrt_dllmain_after_initialize_c

- ea: `0x1800031b4`
- end: `0x1800031e8`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x180002880`

## callees

- `0x1800031b4`
- `0x180003a74`
- `0x180003d0c`
- `0x180003d14`
- `0x180004d00`
- `0x180005b74`

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
    if ( configure_narrow_argv(startup_argv_mode) )
      return 0;
    initialize_narrow_environment();
  }
  return 1;
}

```

## disassembly

```asm
0x1800031b4  sub     rsp, 28h
0x1800031b8  call    __scrt_is_ucrt_dll_in_use
0x1800031bd  test    eax, eax
0x1800031bf  jz      short loc_1800031C8
0x1800031c1  call    __isa_available_init
0x1800031c6  jmp     short loc_1800031E1
0x1800031c8  call    _get_startup_argv_mode
0x1800031cd  mov     ecx, eax; mode
0x1800031cf  call    _configure_narrow_argv
0x1800031d4  test    eax, eax
0x1800031d6  jz      short loc_1800031DC
0x1800031d8  xor     al, al
0x1800031da  jmp     short loc_1800031E3
0x1800031dc  call    _initialize_narrow_environment
0x1800031e1  mov     al, 1
0x1800031e3  add     rsp, 28h
0x1800031e7  retn
```
