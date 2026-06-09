# __scrt_dllmain_after_initialize_c

- ea: `0x1800028e4`
- end: `0x180002918`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x180002558`

## callees

- `0x1800028e4`
- `0x180003294`
- `0x180003448`
- `0x180003454`
- `0x180003546`
- `0x18000356a`

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
0x1800028e4  sub     rsp, 28h
0x1800028e8  call    __scrt_is_ucrt_dll_in_use
0x1800028ed  test    eax, eax
0x1800028ef  jz      short loc_1800028F8
0x1800028f1  call    __isa_available_init
0x1800028f6  jmp     short loc_180002911
0x1800028f8  call    _get_startup_argv_mode
0x1800028fd  mov     ecx, eax; mode
0x1800028ff  call    _o__configure_narrow_argv_0
0x180002904  test    eax, eax
0x180002906  jz      short loc_18000290C
0x180002908  xor     al, al
0x18000290a  jmp     short loc_180002913
0x18000290c  call    _initialize_narrow_environment
0x180002911  mov     al, 1
0x180002913  add     rsp, 28h
0x180002917  retn
```
