# __scrt_dllmain_after_initialize_c

- ea: `0x1800020c8`
- end: `0x1800020fc`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: `char()`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x180001d08`

## callees

- `0x1800020c8`
- `0x180002780`
- `0x180002a0c`
- `0x180002a18`
- `0x180002aae`
- `0x180002ad2`

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
0x1800020c8  sub     rsp, 28h
0x1800020cc  call    __scrt_is_ucrt_dll_in_use
0x1800020d1  test    eax, eax
0x1800020d3  jz      short loc_1800020DC
0x1800020d5  call    __isa_available_init
0x1800020da  jmp     short loc_1800020F5
0x1800020dc  call    _get_startup_argv_mode
0x1800020e1  mov     ecx, eax; mode
0x1800020e3  call    _o__configure_narrow_argv_0
0x1800020e8  test    eax, eax
0x1800020ea  jz      short loc_1800020F0
0x1800020ec  xor     al, al
0x1800020ee  jmp     short loc_1800020F7
0x1800020f0  call    _initialize_narrow_environment
0x1800020f5  mov     al, 1
0x1800020f7  add     rsp, 28h
0x1800020fb  retn
```
