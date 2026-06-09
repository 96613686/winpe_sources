# __scrt_dllmain_after_initialize_c

- ea: `0x180003ba0`
- end: `0x180003bd4`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x180003fd0`

## callees

- `0x180003ba0`
- `0x1800044a0`
- `0x180004668`
- `0x180004670`
- `0x18000497e`
- `0x180004984`

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
    if ( configure_narrow_argv_0(startup_argv_mode) )
      return 0;
    initialize_narrow_environment_0();
  }
  return 1;
}

```

## disassembly

```asm
0x180003ba0  sub     rsp, 28h
0x180003ba4  call    __scrt_is_ucrt_dll_in_use
0x180003ba9  test    eax, eax
0x180003bab  jz      short loc_180003BB4
0x180003bad  call    __isa_available_init
0x180003bb2  jmp     short loc_180003BCD
0x180003bb4  call    _get_startup_argv_mode
0x180003bb9  mov     ecx, eax; mode
0x180003bbb  call    _configure_narrow_argv_0
0x180003bc0  test    eax, eax
0x180003bc2  jz      short loc_180003BC8
0x180003bc4  xor     al, al
0x180003bc6  jmp     short loc_180003BCF
0x180003bc8  call    _initialize_narrow_environment_0
0x180003bcd  mov     al, 1
0x180003bcf  add     rsp, 28h
0x180003bd3  retn
```
