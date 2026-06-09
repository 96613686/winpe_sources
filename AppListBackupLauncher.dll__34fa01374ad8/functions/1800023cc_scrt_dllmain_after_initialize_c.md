# __scrt_dllmain_after_initialize_c

- ea: `0x1800023cc`
- end: `0x180002400`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: `char()`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x180001fe8`

## callees

- `0x1800023cc`
- `0x18000280c`
- `0x180002c88`
- `0x180002c94`
- `0x180002d2e`
- `0x180002d52`

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
0x1800023cc  sub     rsp, 28h
0x1800023d0  call    __scrt_is_ucrt_dll_in_use
0x1800023d5  test    eax, eax
0x1800023d7  jz      short loc_1800023E0
0x1800023d9  call    __isa_available_init
0x1800023de  jmp     short loc_1800023F9
0x1800023e0  call    _get_startup_argv_mode
0x1800023e5  mov     ecx, eax; mode
0x1800023e7  call    _o__configure_narrow_argv_0
0x1800023ec  test    eax, eax
0x1800023ee  jz      short loc_1800023F4
0x1800023f0  xor     al, al
0x1800023f2  jmp     short loc_1800023FB
0x1800023f4  call    _initialize_narrow_environment
0x1800023f9  mov     al, 1
0x1800023fb  add     rsp, 28h
0x1800023ff  retn
```
