# __scrt_dllmain_after_initialize_c

- ea: `0x1800015ec`
- end: `0x180001620`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x1800010e8`

## callees

- `0x1800015ec`
- `0x180001a1c`
- `0x180001ca8`
- `0x180001cb4`
- `0x180001f78`
- `0x180001f90`

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
0x1800015ec  sub     rsp, 28h
0x1800015f0  call    __scrt_is_ucrt_dll_in_use
0x1800015f5  test    eax, eax
0x1800015f7  jz      short loc_180001600
0x1800015f9  call    __isa_available_init
0x1800015fe  jmp     short loc_180001619
0x180001600  call    _get_startup_argv_mode
0x180001605  mov     ecx, eax; mode
0x180001607  call    _o__configure_narrow_argv_0
0x18000160c  test    eax, eax
0x18000160e  jz      short loc_180001614
0x180001610  xor     al, al
0x180001612  jmp     short loc_18000161B
0x180001614  call    _initialize_narrow_environment
0x180001619  mov     al, 1
0x18000161b  add     rsp, 28h
0x18000161f  retn
```
