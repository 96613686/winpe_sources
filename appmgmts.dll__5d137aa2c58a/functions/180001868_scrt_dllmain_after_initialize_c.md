# __scrt_dllmain_after_initialize_c

- ea: `0x180001868`
- end: `0x18000189c`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: `char()`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x1800013b8`

## callees

- `0x180001868`
- `0x180001c78`
- `0x180001f04`
- `0x180001f10`
- `0x180001faa`
- `0x180001fce`

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
0x180001868  sub     rsp, 28h
0x18000186c  call    __scrt_is_ucrt_dll_in_use
0x180001871  test    eax, eax
0x180001873  jz      short loc_18000187C
0x180001875  call    __isa_available_init
0x18000187a  jmp     short loc_180001895
0x18000187c  call    _get_startup_argv_mode
0x180001881  mov     ecx, eax; mode
0x180001883  call    _o__configure_narrow_argv_0
0x180001888  test    eax, eax
0x18000188a  jz      short loc_180001890
0x18000188c  xor     al, al
0x18000188e  jmp     short loc_180001897
0x180001890  call    _initialize_narrow_environment
0x180001895  mov     al, 1
0x180001897  add     rsp, 28h
0x18000189b  retn
```
