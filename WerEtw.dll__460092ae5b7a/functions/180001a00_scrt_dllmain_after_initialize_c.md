# __scrt_dllmain_after_initialize_c

- ea: `0x180001a00`
- end: `0x180001a34`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x180001548`

## callees

- `0x180001a00`
- `0x180001fc0`
- `0x18000224c`
- `0x180002258`
- `0x180002346`
- `0x18000236a`

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
0x180001a00  sub     rsp, 28h
0x180001a04  call    __scrt_is_ucrt_dll_in_use
0x180001a09  test    eax, eax
0x180001a0b  jz      short loc_180001A14
0x180001a0d  call    __isa_available_init
0x180001a12  jmp     short loc_180001A2D
0x180001a14  call    _get_startup_argv_mode
0x180001a19  mov     ecx, eax; mode
0x180001a1b  call    _o__configure_narrow_argv_0
0x180001a20  test    eax, eax
0x180001a22  jz      short loc_180001A28
0x180001a24  xor     al, al
0x180001a26  jmp     short loc_180001A2F
0x180001a28  call    _initialize_narrow_environment
0x180001a2d  mov     al, 1
0x180001a2f  add     rsp, 28h
0x180001a33  retn
```
