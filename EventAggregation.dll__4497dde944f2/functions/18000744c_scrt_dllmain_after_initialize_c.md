# __scrt_dllmain_after_initialize_c

- ea: `0x18000744c`
- end: `0x180007480`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x180006fc8`

## callees

- `0x18000744c`
- `0x180007820`
- `0x180007aac`
- `0x180007ab8`
- `0x180007b16`
- `0x180007b2e`

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
0x18000744c  sub     rsp, 28h
0x180007450  call    __scrt_is_ucrt_dll_in_use
0x180007455  test    eax, eax
0x180007457  jz      short loc_180007460
0x180007459  call    __isa_available_init
0x18000745e  jmp     short loc_180007479
0x180007460  call    _get_startup_argv_mode
0x180007465  mov     ecx, eax; mode
0x180007467  call    _o__configure_narrow_argv_0
0x18000746c  test    eax, eax
0x18000746e  jz      short loc_180007474
0x180007470  xor     al, al
0x180007472  jmp     short loc_18000747B
0x180007474  call    _initialize_narrow_environment
0x180007479  mov     al, 1
0x18000747b  add     rsp, 28h
0x18000747f  retn
```
