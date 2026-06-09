# __scrt_dllmain_after_initialize_c

- ea: `0x1800036bc`
- end: `0x1800036f0`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: `char()`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x180003208`

## callees

- `0x1800036bc`
- `0x180003b08`
- `0x180003fa0`
- `0x180003fac`
- `0x18000404a`
- `0x18000406e`

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
0x1800036bc  sub     rsp, 28h
0x1800036c0  call    __scrt_is_ucrt_dll_in_use
0x1800036c5  test    eax, eax
0x1800036c7  jz      short loc_1800036D0
0x1800036c9  call    __isa_available_init
0x1800036ce  jmp     short loc_1800036E9
0x1800036d0  call    _get_startup_argv_mode
0x1800036d5  mov     ecx, eax; mode
0x1800036d7  call    _o__configure_narrow_argv_0
0x1800036dc  test    eax, eax
0x1800036de  jz      short loc_1800036E4
0x1800036e0  xor     al, al
0x1800036e2  jmp     short loc_1800036EB
0x1800036e4  call    _initialize_narrow_environment
0x1800036e9  mov     al, 1
0x1800036eb  add     rsp, 28h
0x1800036ef  retn
```
