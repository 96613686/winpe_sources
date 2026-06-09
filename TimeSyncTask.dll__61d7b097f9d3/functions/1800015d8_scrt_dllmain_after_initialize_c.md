# __scrt_dllmain_after_initialize_c

- ea: `0x1800015d8`
- end: `0x18000160c`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: `char()`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x180001148`

## callees

- `0x1800015d8`
- `0x1800019ac`
- `0x180001c38`
- `0x180001c44`
- `0x180001cca`
- `0x180001ce2`

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
0x1800015d8  sub     rsp, 28h
0x1800015dc  call    __scrt_is_ucrt_dll_in_use
0x1800015e1  test    eax, eax
0x1800015e3  jz      short loc_1800015EC
0x1800015e5  call    __isa_available_init
0x1800015ea  jmp     short loc_180001605
0x1800015ec  call    _get_startup_argv_mode
0x1800015f1  mov     ecx, eax; mode
0x1800015f3  call    _o__configure_narrow_argv_0
0x1800015f8  test    eax, eax
0x1800015fa  jz      short loc_180001600
0x1800015fc  xor     al, al
0x1800015fe  jmp     short loc_180001607
0x180001600  call    _initialize_narrow_environment
0x180001605  mov     al, 1
0x180001607  add     rsp, 28h
0x18000160b  retn
```
