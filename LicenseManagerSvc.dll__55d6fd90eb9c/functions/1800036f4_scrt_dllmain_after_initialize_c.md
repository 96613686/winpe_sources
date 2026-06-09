# __scrt_dllmain_after_initialize_c

- ea: `0x1800036f4`
- end: `0x180003728`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x1800030b8`

## callees

- `0x1800036f4`
- `0x180003cb4`
- `0x180003f40`
- `0x180003f4c`
- `0x1800040de`
- `0x180004102`

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
0x1800036f4  sub     rsp, 28h
0x1800036f8  call    __scrt_is_ucrt_dll_in_use
0x1800036fd  test    eax, eax
0x1800036ff  jz      short loc_180003708
0x180003701  call    __isa_available_init
0x180003706  jmp     short loc_180003721
0x180003708  call    _get_startup_argv_mode
0x18000370d  mov     ecx, eax; mode
0x18000370f  call    _o__configure_narrow_argv_0
0x180003714  test    eax, eax
0x180003716  jz      short loc_18000371C
0x180003718  xor     al, al
0x18000371a  jmp     short loc_180003723
0x18000371c  call    _initialize_narrow_environment
0x180003721  mov     al, 1
0x180003723  add     rsp, 28h
0x180003727  retn
```
