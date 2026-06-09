# __scrt_dllmain_after_initialize_c

- ea: `0x180003b48`
- end: `0x180003b7c`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x180003748`

## callees

- `0x180003b48`
- `0x180003fac`
- `0x180004460`
- `0x180004516`
- `0x18000453a`
- `0x18000ed18`

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
0x180003b48  sub     rsp, 28h
0x180003b4c  call    __scrt_is_ucrt_dll_in_use
0x180003b51  test    eax, eax
0x180003b53  jz      short loc_180003B5C
0x180003b55  call    __isa_available_init
0x180003b5a  jmp     short loc_180003B75
0x180003b5c  call    _get_startup_argv_mode
0x180003b61  mov     ecx, eax; mode
0x180003b63  call    _o__configure_narrow_argv_0
0x180003b68  test    eax, eax
0x180003b6a  jz      short loc_180003B70
0x180003b6c  xor     al, al
0x180003b6e  jmp     short loc_180003B77
0x180003b70  call    _initialize_narrow_environment
0x180003b75  mov     al, 1
0x180003b77  add     rsp, 28h
0x180003b7b  retn
```
