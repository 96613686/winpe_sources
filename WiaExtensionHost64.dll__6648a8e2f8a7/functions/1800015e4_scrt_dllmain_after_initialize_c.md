# __scrt_dllmain_after_initialize_c

- ea: `0x1800015e4`
- end: `0x180001618`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: `char()`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x180001128`

## callees

- `0x1800015e4`
- `0x1800019bc`
- `0x180001c48`
- `0x180001c54`
- `0x180001cc2`
- `0x180001cda`

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
0x1800015e4  sub     rsp, 28h
0x1800015e8  call    __scrt_is_ucrt_dll_in_use
0x1800015ed  test    eax, eax
0x1800015ef  jz      short loc_1800015F8
0x1800015f1  call    __isa_available_init
0x1800015f6  jmp     short loc_180001611
0x1800015f8  call    _get_startup_argv_mode
0x1800015fd  mov     ecx, eax; mode
0x1800015ff  call    _o__configure_narrow_argv_0
0x180001604  test    eax, eax
0x180001606  jz      short loc_18000160C
0x180001608  xor     al, al
0x18000160a  jmp     short loc_180001613
0x18000160c  call    _initialize_narrow_environment
0x180001611  mov     al, 1
0x180001613  add     rsp, 28h
0x180001617  retn
```
