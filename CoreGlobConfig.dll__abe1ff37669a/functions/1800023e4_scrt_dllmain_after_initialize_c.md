# __scrt_dllmain_after_initialize_c

- ea: `0x1800023e4`
- end: `0x180002418`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x180002068`

## callees

- `0x1800023e4`
- `0x180002cc8`
- `0x180003120`
- `0x18000312c`
- `0x18000321a`
- `0x18000323e`

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
0x1800023e4  sub     rsp, 28h
0x1800023e8  call    __scrt_is_ucrt_dll_in_use
0x1800023ed  test    eax, eax
0x1800023ef  jz      short loc_1800023F8
0x1800023f1  call    __isa_available_init
0x1800023f6  jmp     short loc_180002411
0x1800023f8  call    _get_startup_argv_mode
0x1800023fd  mov     ecx, eax; mode
0x1800023ff  call    _o__configure_narrow_argv_0
0x180002404  test    eax, eax
0x180002406  jz      short loc_18000240C
0x180002408  xor     al, al
0x18000240a  jmp     short loc_180002413
0x18000240c  call    _initialize_narrow_environment
0x180002411  mov     al, 1
0x180002413  add     rsp, 28h
0x180002417  retn
```
