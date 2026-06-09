# __scrt_dllmain_after_initialize_c

- ea: `0x180024a8c`
- end: `0x180024ac0`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x1800246d8`

## callees

- `0x180024a8c`
- `0x180025100`
- `0x18002538c`
- `0x180025398`
- `0x180025416`
- `0x18002543a`

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
0x180024a8c  sub     rsp, 28h
0x180024a90  call    __scrt_is_ucrt_dll_in_use
0x180024a95  test    eax, eax
0x180024a97  jz      short loc_180024AA0
0x180024a99  call    __isa_available_init
0x180024a9e  jmp     short loc_180024AB9
0x180024aa0  call    _get_startup_argv_mode
0x180024aa5  mov     ecx, eax; mode
0x180024aa7  call    _o__configure_narrow_argv_0
0x180024aac  test    eax, eax
0x180024aae  jz      short loc_180024AB4
0x180024ab0  xor     al, al
0x180024ab2  jmp     short loc_180024ABB
0x180024ab4  call    _initialize_narrow_environment
0x180024ab9  mov     al, 1
0x180024abb  add     rsp, 28h
0x180024abf  retn
```
