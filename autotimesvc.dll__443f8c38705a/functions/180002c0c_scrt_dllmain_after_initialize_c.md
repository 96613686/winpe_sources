# __scrt_dllmain_after_initialize_c

- ea: `0x180002c0c`
- end: `0x180002c40`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: `char()`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x180002758`

## callees

- `0x180002c0c`
- `0x180003260`
- `0x1800034ec`
- `0x1800034f8`
- `0x18000359a`
- `0x1800035be`

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
0x180002c0c  sub     rsp, 28h
0x180002c10  call    __scrt_is_ucrt_dll_in_use
0x180002c15  test    eax, eax
0x180002c17  jz      short loc_180002C20
0x180002c19  call    __isa_available_init
0x180002c1e  jmp     short loc_180002C39
0x180002c20  call    _get_startup_argv_mode
0x180002c25  mov     ecx, eax; mode
0x180002c27  call    _o__configure_narrow_argv_0
0x180002c2c  test    eax, eax
0x180002c2e  jz      short loc_180002C34
0x180002c30  xor     al, al
0x180002c32  jmp     short loc_180002C3B
0x180002c34  call    _initialize_narrow_environment
0x180002c39  mov     al, 1
0x180002c3b  add     rsp, 28h
0x180002c3f  retn
```
