# __scrt_dllmain_after_initialize_c

- ea: `0x180003dec`
- end: `0x180003e20`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x180003968`

## callees

- `0x180003dec`
- `0x180004220`
- `0x1800044ac`
- `0x1800044b8`
- `0x180004536`
- `0x18000455a`

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
0x180003dec  sub     rsp, 28h
0x180003df0  call    __scrt_is_ucrt_dll_in_use
0x180003df5  test    eax, eax
0x180003df7  jz      short loc_180003E00
0x180003df9  call    __isa_available_init
0x180003dfe  jmp     short loc_180003E19
0x180003e00  call    _get_startup_argv_mode
0x180003e05  mov     ecx, eax; mode
0x180003e07  call    _o__configure_narrow_argv_0
0x180003e0c  test    eax, eax
0x180003e0e  jz      short loc_180003E14
0x180003e10  xor     al, al
0x180003e12  jmp     short loc_180003E1B
0x180003e14  call    _initialize_narrow_environment
0x180003e19  mov     al, 1
0x180003e1b  add     rsp, 28h
0x180003e1f  retn
```
