# __scrt_dllmain_after_initialize_c

- ea: `0x180001f54`
- end: `0x180001f88`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: `char()`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x180001b08`

## callees

- `0x180001f54`
- `0x1800024f0`
- `0x18000277c`
- `0x180002a06`
- `0x180002a2a`
- `0x180006c70`

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
0x180001f54  sub     rsp, 28h
0x180001f58  call    __scrt_is_ucrt_dll_in_use
0x180001f5d  test    eax, eax
0x180001f5f  jz      short loc_180001F68
0x180001f61  call    __isa_available_init
0x180001f66  jmp     short loc_180001F81
0x180001f68  call    _get_startup_argv_mode
0x180001f6d  mov     ecx, eax; mode
0x180001f6f  call    _o__configure_narrow_argv_0
0x180001f74  test    eax, eax
0x180001f76  jz      short loc_180001F7C
0x180001f78  xor     al, al
0x180001f7a  jmp     short loc_180001F83
0x180001f7c  call    _initialize_narrow_environment
0x180001f81  mov     al, 1
0x180001f83  add     rsp, 28h
0x180001f87  retn
```
