# __scrt_dllmain_after_initialize_c

- ea: `0x180001ca8`
- end: `0x180001cdc`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: `char()`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x1800018e8`

## callees

- `0x180001ca8`
- `0x180002268`
- `0x1800024f4`
- `0x1800025ae`
- `0x1800025d2`
- `0x180010cb0`

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
0x180001ca8  sub     rsp, 28h
0x180001cac  call    __scrt_is_ucrt_dll_in_use
0x180001cb1  test    eax, eax
0x180001cb3  jz      short loc_180001CBC
0x180001cb5  call    __isa_available_init
0x180001cba  jmp     short loc_180001CD5
0x180001cbc  call    _get_startup_argv_mode
0x180001cc1  mov     ecx, eax; mode
0x180001cc3  call    _o__configure_narrow_argv_0
0x180001cc8  test    eax, eax
0x180001cca  jz      short loc_180001CD0
0x180001ccc  xor     al, al
0x180001cce  jmp     short loc_180001CD7
0x180001cd0  call    _initialize_narrow_environment
0x180001cd5  mov     al, 1
0x180001cd7  add     rsp, 28h
0x180001cdb  retn
```
