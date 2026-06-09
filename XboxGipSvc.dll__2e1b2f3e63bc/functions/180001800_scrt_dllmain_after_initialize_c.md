# __scrt_dllmain_after_initialize_c

- ea: `0x180001800`
- end: `0x180001834`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: `char()`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x1800013a8`

## callees

- `0x180001800`
- `0x180001d50`
- `0x180001fdc`
- `0x180001fe8`
- `0x18000208e`
- `0x1800020b2`

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
0x180001800  sub     rsp, 28h
0x180001804  call    __scrt_is_ucrt_dll_in_use
0x180001809  test    eax, eax
0x18000180b  jz      short loc_180001814
0x18000180d  call    __isa_available_init
0x180001812  jmp     short loc_18000182D
0x180001814  call    _get_startup_argv_mode
0x180001819  mov     ecx, eax; mode
0x18000181b  call    _o__configure_narrow_argv_0
0x180001820  test    eax, eax
0x180001822  jz      short loc_180001828
0x180001824  xor     al, al
0x180001826  jmp     short loc_18000182F
0x180001828  call    _initialize_narrow_environment
0x18000182d  mov     al, 1
0x18000182f  add     rsp, 28h
0x180001833  retn
```
