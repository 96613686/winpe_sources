# __scrt_dllmain_after_initialize_c

- ea: `0x180001ea8`
- end: `0x180001edc`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: `char()`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x180001ae8`

## callees

- `0x180001ea8`
- `0x180002488`
- `0x180002714`
- `0x180002720`
- `0x1800027be`
- `0x1800027e2`

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
0x180001ea8  sub     rsp, 28h
0x180001eac  call    __scrt_is_ucrt_dll_in_use
0x180001eb1  test    eax, eax
0x180001eb3  jz      short loc_180001EBC
0x180001eb5  call    __isa_available_init
0x180001eba  jmp     short loc_180001ED5
0x180001ebc  call    _get_startup_argv_mode
0x180001ec1  mov     ecx, eax; mode
0x180001ec3  call    _o__configure_narrow_argv_0
0x180001ec8  test    eax, eax
0x180001eca  jz      short loc_180001ED0
0x180001ecc  xor     al, al
0x180001ece  jmp     short loc_180001ED7
0x180001ed0  call    _initialize_narrow_environment
0x180001ed5  mov     al, 1
0x180001ed7  add     rsp, 28h
0x180001edb  retn
```
