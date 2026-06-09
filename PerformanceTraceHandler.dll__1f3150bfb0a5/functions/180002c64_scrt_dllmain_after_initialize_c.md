# __scrt_dllmain_after_initialize_c

- ea: `0x180002c64`
- end: `0x180002c98`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x1800028e8`

## callees

- `0x180002c64`
- `0x180003110`
- `0x180003570`
- `0x18000365a`
- `0x18000367e`
- `0x18000cb40`

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
0x180002c64  sub     rsp, 28h
0x180002c68  call    __scrt_is_ucrt_dll_in_use
0x180002c6d  test    eax, eax
0x180002c6f  jz      short loc_180002C78
0x180002c71  call    __isa_available_init
0x180002c76  jmp     short loc_180002C91
0x180002c78  call    _get_startup_argv_mode
0x180002c7d  mov     ecx, eax; mode
0x180002c7f  call    _o__configure_narrow_argv_0
0x180002c84  test    eax, eax
0x180002c86  jz      short loc_180002C8C
0x180002c88  xor     al, al
0x180002c8a  jmp     short loc_180002C93
0x180002c8c  call    _initialize_narrow_environment
0x180002c91  mov     al, 1
0x180002c93  add     rsp, 28h
0x180002c97  retn
```
