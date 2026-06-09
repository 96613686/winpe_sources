# __scrt_dllmain_after_initialize_c

- ea: `0x1800350e0`
- end: `0x180035114`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x180035550`

## callees

- `0x1800350e0`
- `0x180035968`
- `0x180035e68`
- `0x180035e70`
- `0x180039763`
- `0x180039769`

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
0x1800350e0  sub     rsp, 28h
0x1800350e4  call    __scrt_is_ucrt_dll_in_use
0x1800350e9  test    eax, eax
0x1800350eb  jz      short loc_1800350F4
0x1800350ed  call    __isa_available_init
0x1800350f2  jmp     short loc_18003510D
0x1800350f4  call    _get_startup_argv_mode
0x1800350f9  mov     ecx, eax; mode
0x1800350fb  call    _configure_narrow_argv_0
0x180035100  test    eax, eax
0x180035102  jz      short loc_180035108
0x180035104  xor     al, al
0x180035106  jmp     short loc_18003510F
0x180035108  call    _initialize_narrow_environment_0
0x18003510d  mov     al, 1
0x18003510f  add     rsp, 28h
0x180035113  retn
```
