# __scrt_dllmain_after_initialize_c

- ea: `0x180001d94`
- end: `0x180001dc8`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: `char()`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x180001a18`

## callees

- `0x180001d94`
- `0x180002390`
- `0x18000261c`
- `0x180002628`
- `0x18000272a`
- `0x18000274e`

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
0x180001d94  sub     rsp, 28h
0x180001d98  call    __scrt_is_ucrt_dll_in_use
0x180001d9d  test    eax, eax
0x180001d9f  jz      short loc_180001DA8
0x180001da1  call    __isa_available_init
0x180001da6  jmp     short loc_180001DC1
0x180001da8  call    _get_startup_argv_mode
0x180001dad  mov     ecx, eax; mode
0x180001daf  call    _o__configure_narrow_argv_0
0x180001db4  test    eax, eax
0x180001db6  jz      short loc_180001DBC
0x180001db8  xor     al, al
0x180001dba  jmp     short loc_180001DC3
0x180001dbc  call    _initialize_narrow_environment
0x180001dc1  mov     al, 1
0x180001dc3  add     rsp, 28h
0x180001dc7  retn
```
