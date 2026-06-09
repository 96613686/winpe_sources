# __scrt_dllmain_after_initialize_c

- ea: `0x180002a88`
- end: `0x180002abc`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x1800026d8`

## callees

- `0x180002a88`
- `0x180003088`
- `0x180003324`
- `0x180003330`
- `0x180005c67`
- `0x180005c73`

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
0x180002a88  sub     rsp, 28h
0x180002a8c  call    __scrt_is_ucrt_dll_in_use
0x180002a91  test    eax, eax
0x180002a93  jz      short loc_180002A9C
0x180002a95  call    __isa_available_init
0x180002a9a  jmp     short loc_180002AB5
0x180002a9c  call    _get_startup_argv_mode
0x180002aa1  mov     ecx, eax; mode
0x180002aa3  call    _configure_narrow_argv_0
0x180002aa8  test    eax, eax
0x180002aaa  jz      short loc_180002AB0
0x180002aac  xor     al, al
0x180002aae  jmp     short loc_180002AB7
0x180002ab0  call    _initialize_narrow_environment_0
0x180002ab5  mov     al, 1
0x180002ab7  add     rsp, 28h
0x180002abb  retn
```
