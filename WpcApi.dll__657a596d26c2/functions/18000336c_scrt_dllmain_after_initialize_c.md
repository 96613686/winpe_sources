# __scrt_dllmain_after_initialize_c

- ea: `0x18000336c`
- end: `0x1800033a0`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x180002f88`

## callees

- `0x18000336c`
- `0x180003930`
- `0x180003bbc`
- `0x180003bc8`
- `0x180003c6a`
- `0x180003c8e`

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
0x18000336c  sub     rsp, 28h
0x180003370  call    __scrt_is_ucrt_dll_in_use
0x180003375  test    eax, eax
0x180003377  jz      short loc_180003380
0x180003379  call    __isa_available_init
0x18000337e  jmp     short loc_180003399
0x180003380  call    _get_startup_argv_mode
0x180003385  mov     ecx, eax; mode
0x180003387  call    _o__configure_narrow_argv_0
0x18000338c  test    eax, eax
0x18000338e  jz      short loc_180003394
0x180003390  xor     al, al
0x180003392  jmp     short loc_18000339B
0x180003394  call    _initialize_narrow_environment
0x180003399  mov     al, 1
0x18000339b  add     rsp, 28h
0x18000339f  retn
```
