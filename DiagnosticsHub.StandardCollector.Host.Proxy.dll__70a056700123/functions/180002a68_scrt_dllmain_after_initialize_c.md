# __scrt_dllmain_after_initialize_c

- ea: `0x180002a68`
- end: `0x180002a9c`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x1800024f0`

## callees

- `0x180002a68`
- `0x180003324`
- `0x1800035bc`
- `0x1800035c4`
- `0x1800045a4`
- `0x180005418`

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
    if ( configure_narrow_argv(startup_argv_mode) )
      return 0;
    initialize_narrow_environment();
  }
  return 1;
}

```

## disassembly

```asm
0x180002a68  sub     rsp, 28h
0x180002a6c  call    __scrt_is_ucrt_dll_in_use
0x180002a71  test    eax, eax
0x180002a73  jz      short loc_180002A7C
0x180002a75  call    __isa_available_init
0x180002a7a  jmp     short loc_180002A95
0x180002a7c  call    _get_startup_argv_mode
0x180002a81  mov     ecx, eax; mode
0x180002a83  call    _configure_narrow_argv
0x180002a88  test    eax, eax
0x180002a8a  jz      short loc_180002A90
0x180002a8c  xor     al, al
0x180002a8e  jmp     short loc_180002A97
0x180002a90  call    _initialize_narrow_environment
0x180002a95  mov     al, 1
0x180002a97  add     rsp, 28h
0x180002a9b  retn
```
