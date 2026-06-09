# __scrt_dllmain_after_initialize_c

- ea: `0x1800099bc`
- end: `0x1800099f0`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: `char()`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x180009538`

## callees

- `0x1800099bc`
- `0x180009df0`
- `0x18000a07c`
- `0x18000a088`
- `0x18000a116`
- `0x18000a13a`

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
0x1800099bc  sub     rsp, 28h
0x1800099c0  call    __scrt_is_ucrt_dll_in_use
0x1800099c5  test    eax, eax
0x1800099c7  jz      short loc_1800099D0
0x1800099c9  call    __isa_available_init
0x1800099ce  jmp     short loc_1800099E9
0x1800099d0  call    _get_startup_argv_mode
0x1800099d5  mov     ecx, eax; mode
0x1800099d7  call    _o__configure_narrow_argv_0
0x1800099dc  test    eax, eax
0x1800099de  jz      short loc_1800099E4
0x1800099e0  xor     al, al
0x1800099e2  jmp     short loc_1800099EB
0x1800099e4  call    _initialize_narrow_environment
0x1800099e9  mov     al, 1
0x1800099eb  add     rsp, 28h
0x1800099ef  retn
```
