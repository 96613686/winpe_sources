# __scrt_dllmain_after_initialize_c

- ea: `0x180003480`
- end: `0x1800034b4`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x1800030e8`

## callees

- `0x180003480`
- `0x180003938`
- `0x180003d90`
- `0x180003d9c`
- `0x180003ec6`
- `0x180003eea`

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
0x180003480  sub     rsp, 28h
0x180003484  call    __scrt_is_ucrt_dll_in_use
0x180003489  test    eax, eax
0x18000348b  jz      short loc_180003494
0x18000348d  call    __isa_available_init
0x180003492  jmp     short loc_1800034AD
0x180003494  call    _get_startup_argv_mode
0x180003499  mov     ecx, eax; mode
0x18000349b  call    _o__configure_narrow_argv_0
0x1800034a0  test    eax, eax
0x1800034a2  jz      short loc_1800034A8
0x1800034a4  xor     al, al
0x1800034a6  jmp     short loc_1800034AF
0x1800034a8  call    _initialize_narrow_environment
0x1800034ad  mov     al, 1
0x1800034af  add     rsp, 28h
0x1800034b3  retn
```
