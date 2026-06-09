# __scrt_dllmain_after_initialize_c

- ea: `0x180002c24`
- end: `0x180002c58`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: `char()`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x1800028a8`

## callees

- `0x180002c24`
- `0x180003190`
- `0x18000341c`
- `0x180003428`
- `0x1800034c2`
- `0x1800034e6`

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
0x180002c24  sub     rsp, 28h
0x180002c28  call    __scrt_is_ucrt_dll_in_use
0x180002c2d  test    eax, eax
0x180002c2f  jz      short loc_180002C38
0x180002c31  call    __isa_available_init
0x180002c36  jmp     short loc_180002C51
0x180002c38  call    _get_startup_argv_mode
0x180002c3d  mov     ecx, eax; mode
0x180002c3f  call    _o__configure_narrow_argv_0
0x180002c44  test    eax, eax
0x180002c46  jz      short loc_180002C4C
0x180002c48  xor     al, al
0x180002c4a  jmp     short loc_180002C53
0x180002c4c  call    _initialize_narrow_environment
0x180002c51  mov     al, 1
0x180002c53  add     rsp, 28h
0x180002c57  retn
```
