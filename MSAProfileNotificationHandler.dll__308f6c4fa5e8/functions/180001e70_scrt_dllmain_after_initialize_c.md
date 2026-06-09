# __scrt_dllmain_after_initialize_c

- ea: `0x180001e70`
- end: `0x180001ea4`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: `char()`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x180001998`

## callees

- `0x180001e70`
- `0x1800022fc`
- `0x180002588`
- `0x180002594`
- `0x180002854`
- `0x180002878`

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
0x180001e70  sub     rsp, 28h
0x180001e74  call    __scrt_is_ucrt_dll_in_use
0x180001e79  test    eax, eax
0x180001e7b  jz      short loc_180001E84
0x180001e7d  call    __isa_available_init
0x180001e82  jmp     short loc_180001E9D
0x180001e84  call    _get_startup_argv_mode
0x180001e89  mov     ecx, eax; mode
0x180001e8b  call    _o__configure_narrow_argv_0
0x180001e90  test    eax, eax
0x180001e92  jz      short loc_180001E98
0x180001e94  xor     al, al
0x180001e96  jmp     short loc_180001E9F
0x180001e98  call    _initialize_narrow_environment
0x180001e9d  mov     al, 1
0x180001e9f  add     rsp, 28h
0x180001ea3  retn
```
