# __scrt_dllmain_after_initialize_c

- ea: `0x18000226c`
- end: `0x1800022a0`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x180001eb8`

## callees

- `0x18000226c`
- `0x1800027fc`
- `0x180002a88`
- `0x180002a94`
- `0x180002b7a`
- `0x180002b9e`

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
0x18000226c  sub     rsp, 28h
0x180002270  call    __scrt_is_ucrt_dll_in_use
0x180002275  test    eax, eax
0x180002277  jz      short loc_180002280
0x180002279  call    __isa_available_init
0x18000227e  jmp     short loc_180002299
0x180002280  call    _get_startup_argv_mode
0x180002285  mov     ecx, eax; mode
0x180002287  call    _o__configure_narrow_argv_0
0x18000228c  test    eax, eax
0x18000228e  jz      short loc_180002294
0x180002290  xor     al, al
0x180002292  jmp     short loc_18000229B
0x180002294  call    _initialize_narrow_environment
0x180002299  mov     al, 1
0x18000229b  add     rsp, 28h
0x18000229f  retn
```
