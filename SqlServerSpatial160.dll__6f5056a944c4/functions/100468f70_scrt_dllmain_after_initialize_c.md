# __scrt_dllmain_after_initialize_c

- ea: `0x100468f70`
- end: `0x100468fa4`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x100468c0c`

## callees

- `0x10046887c`
- `0x100468f70`
- `0x1004697ec`
- `0x1004697f8`
- `0x10046989a`
- `0x1004698a6`

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
0x100468f70  sub     rsp, 28h
0x100468f74  call    __scrt_is_ucrt_dll_in_use
0x100468f79  test    eax, eax
0x100468f7b  jz      short loc_100468F84
0x100468f7d  call    __isa_available_init
0x100468f82  jmp     short loc_100468F9D
0x100468f84  call    _get_startup_argv_mode
0x100468f89  mov     ecx, eax; mode
0x100468f8b  call    _configure_narrow_argv_0
0x100468f90  test    eax, eax
0x100468f92  jz      short loc_100468F98
0x100468f94  xor     al, al
0x100468f96  jmp     short loc_100468F9F
0x100468f98  call    _initialize_narrow_environment_0
0x100468f9d  mov     al, 1
0x100468f9f  add     rsp, 28h
0x100468fa3  retn
```
