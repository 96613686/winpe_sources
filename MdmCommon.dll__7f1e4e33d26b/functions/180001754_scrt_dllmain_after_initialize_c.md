# __scrt_dllmain_after_initialize_c

- ea: `0x180001754`
- end: `0x180001788`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: `char()`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x180001208`

## callees

- `0x180001754`
- `0x180001be8`
- `0x180001e74`
- `0x180001e80`
- `0x180001f2e`
- `0x180001f52`

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
0x180001754  sub     rsp, 28h
0x180001758  call    __scrt_is_ucrt_dll_in_use
0x18000175d  test    eax, eax
0x18000175f  jz      short loc_180001768
0x180001761  call    __isa_available_init
0x180001766  jmp     short loc_180001781
0x180001768  call    _get_startup_argv_mode
0x18000176d  mov     ecx, eax; mode
0x18000176f  call    _o__configure_narrow_argv_0
0x180001774  test    eax, eax
0x180001776  jz      short loc_18000177C
0x180001778  xor     al, al
0x18000177a  jmp     short loc_180001783
0x18000177c  call    _initialize_narrow_environment
0x180001781  mov     al, 1
0x180001783  add     rsp, 28h
0x180001787  retn
```
