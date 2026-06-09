# __scrt_dllmain_after_initialize_c

- ea: `0x180003aa4`
- end: `0x180003ad8`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x1800032e0`

## callees

- `0x180001ee0`
- `0x180003aa4`
- `0x180004140`
- `0x1800042e4`
- `0x180004338`
- `0x18000433e`

## pseudocode

```c
char _scrt_dllmain_after_initialize_c()
{
  DWORD v0; // ecx
  BOOL startup_argv_mode; // eax

  if ( (unsigned int)_scrt_is_ucrt_dll_in_use() )
  {
    _isa_available_init();
  }
  else
  {
    startup_argv_mode = get_startup_argv_mode(v0);
    if ( configure_narrow_argv_0((_crt_argv_mode)startup_argv_mode) )
      return 0;
    initialize_narrow_environment_0();
  }
  return 1;
}

```

## disassembly

```asm
0x180003aa4  sub     rsp, 28h
0x180003aa8  call    __scrt_is_ucrt_dll_in_use
0x180003aad  test    eax, eax
0x180003aaf  jz      short loc_180003AB8
0x180003ab1  call    __isa_available_init
0x180003ab6  jmp     short loc_180003AD1
0x180003ab8  call    _get_startup_argv_mode
0x180003abd  mov     ecx, eax; mode
0x180003abf  call    _configure_narrow_argv_0
0x180003ac4  test    eax, eax
0x180003ac6  jz      short loc_180003ACC
0x180003ac8  xor     al, al
0x180003aca  jmp     short loc_180003AD3
0x180003acc  call    _initialize_narrow_environment_0
0x180003ad1  mov     al, 1
0x180003ad3  add     rsp, 28h
0x180003ad7  retn
```
