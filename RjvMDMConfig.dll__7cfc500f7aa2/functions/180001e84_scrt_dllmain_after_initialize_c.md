# __scrt_dllmain_after_initialize_c

- ea: `0x180001e84`
- end: `0x180001eb8`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x180001948`

## callees

- `0x180001e84`
- `0x1800022e8`
- `0x180002574`
- `0x180002580`
- `0x180002646`
- `0x18000266a`

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
0x180001e84  sub     rsp, 28h
0x180001e88  call    __scrt_is_ucrt_dll_in_use
0x180001e8d  test    eax, eax
0x180001e8f  jz      short loc_180001E98
0x180001e91  call    __isa_available_init
0x180001e96  jmp     short loc_180001EB1
0x180001e98  call    _get_startup_argv_mode
0x180001e9d  mov     ecx, eax; mode
0x180001e9f  call    _o__configure_narrow_argv_0
0x180001ea4  test    eax, eax
0x180001ea6  jz      short loc_180001EAC
0x180001ea8  xor     al, al
0x180001eaa  jmp     short loc_180001EB3
0x180001eac  call    _initialize_narrow_environment
0x180001eb1  mov     al, 1
0x180001eb3  add     rsp, 28h
0x180001eb7  retn
```
