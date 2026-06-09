# __scrt_dllmain_after_initialize_c

- ea: `0x180001ce4`
- end: `0x180001d18`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: `char()`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x180001958`

## callees

- `0x180001ce4`
- `0x1800023d8`
- `0x180002664`
- `0x180002670`
- `0x180002766`
- `0x18000278a`

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
0x180001ce4  sub     rsp, 28h
0x180001ce8  call    __scrt_is_ucrt_dll_in_use
0x180001ced  test    eax, eax
0x180001cef  jz      short loc_180001CF8
0x180001cf1  call    __isa_available_init
0x180001cf6  jmp     short loc_180001D11
0x180001cf8  call    _get_startup_argv_mode
0x180001cfd  mov     ecx, eax; mode
0x180001cff  call    _o__configure_narrow_argv_0
0x180001d04  test    eax, eax
0x180001d06  jz      short loc_180001D0C
0x180001d08  xor     al, al
0x180001d0a  jmp     short loc_180001D13
0x180001d0c  call    _initialize_narrow_environment
0x180001d11  mov     al, 1
0x180001d13  add     rsp, 28h
0x180001d17  retn
```
