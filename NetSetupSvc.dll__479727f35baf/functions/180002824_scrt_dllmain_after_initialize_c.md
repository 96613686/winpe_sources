# __scrt_dllmain_after_initialize_c

- ea: `0x180002824`
- end: `0x180002858`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x1800024a8`

## callees

- `0x180002824`
- `0x180002ca0`
- `0x1800030f0`
- `0x1800030fc`
- `0x180003212`
- `0x180003236`

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
0x180002824  sub     rsp, 28h
0x180002828  call    __scrt_is_ucrt_dll_in_use
0x18000282d  test    eax, eax
0x18000282f  jz      short loc_180002838
0x180002831  call    __isa_available_init
0x180002836  jmp     short loc_180002851
0x180002838  call    _get_startup_argv_mode
0x18000283d  mov     ecx, eax; mode
0x18000283f  call    _o__configure_narrow_argv_0
0x180002844  test    eax, eax
0x180002846  jz      short loc_18000284C
0x180002848  xor     al, al
0x18000284a  jmp     short loc_180002853
0x18000284c  call    _initialize_narrow_environment
0x180002851  mov     al, 1
0x180002853  add     rsp, 28h
0x180002857  retn
```
