# __scrt_dllmain_after_initialize_c

- ea: `0x18000732c`
- end: `0x180007360`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: `char()`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x1800076f0`

## callees

- `0x18000732c`
- `0x180007c28`
- `0x180007ec0`
- `0x180007ec8`
- `0x18000b5c8`
- `0x18000b5ce`

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
0x18000732c  sub     rsp, 28h
0x180007330  call    __scrt_is_ucrt_dll_in_use
0x180007335  test    eax, eax
0x180007337  jz      short loc_180007340
0x180007339  call    __isa_available_init
0x18000733e  jmp     short loc_180007359
0x180007340  call    _get_startup_argv_mode
0x180007345  mov     ecx, eax; mode
0x180007347  call    _configure_narrow_argv_0
0x18000734c  test    eax, eax
0x18000734e  jz      short loc_180007354
0x180007350  xor     al, al
0x180007352  jmp     short loc_18000735B
0x180007354  call    _initialize_narrow_environment_0
0x180007359  mov     al, 1
0x18000735b  add     rsp, 28h
0x18000735f  retn
```
