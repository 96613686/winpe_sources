# __scrt_dllmain_after_initialize_c

- ea: `0x180002b38`
- end: `0x180002b6c`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x180002778`

## callees

- `0x180002b38`
- `0x180003258`
- `0x180003718`
- `0x180003724`
- `0x1800037be`
- `0x1800037e2`

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
0x180002b38  sub     rsp, 28h
0x180002b3c  call    __scrt_is_ucrt_dll_in_use
0x180002b41  test    eax, eax
0x180002b43  jz      short loc_180002B4C
0x180002b45  call    __isa_available_init
0x180002b4a  jmp     short loc_180002B65
0x180002b4c  call    _get_startup_argv_mode
0x180002b51  mov     ecx, eax; mode
0x180002b53  call    _o__configure_narrow_argv_0
0x180002b58  test    eax, eax
0x180002b5a  jz      short loc_180002B60
0x180002b5c  xor     al, al
0x180002b5e  jmp     short loc_180002B67
0x180002b60  call    _initialize_narrow_environment
0x180002b65  mov     al, 1
0x180002b67  add     rsp, 28h
0x180002b6b  retn
```
