# __scrt_dllmain_after_initialize_c

- ea: `0x18000184c`
- end: `0x180001880`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: `char()`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x180001388`

## callees

- `0x18000184c`
- `0x180001cc4`
- `0x180001f50`
- `0x180001f5c`
- `0x180002094`
- `0x1800020b8`

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
0x18000184c  sub     rsp, 28h
0x180001850  call    __scrt_is_ucrt_dll_in_use
0x180001855  test    eax, eax
0x180001857  jz      short loc_180001860
0x180001859  call    __isa_available_init
0x18000185e  jmp     short loc_180001879
0x180001860  call    _get_startup_argv_mode
0x180001865  mov     ecx, eax; mode
0x180001867  call    _o__configure_narrow_argv_0
0x18000186c  test    eax, eax
0x18000186e  jz      short loc_180001874
0x180001870  xor     al, al
0x180001872  jmp     short loc_18000187B
0x180001874  call    _initialize_narrow_environment
0x180001879  mov     al, 1
0x18000187b  add     rsp, 28h
0x18000187f  retn
```
