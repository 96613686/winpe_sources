# __scrt_dllmain_after_initialize_c

- ea: `0x180001704`
- end: `0x180001738`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x180001388`

## callees

- `0x180001704`
- `0x180001ce0`
- `0x180001f6c`
- `0x180001f78`
- `0x18000203e`
- `0x180002062`

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
0x180001704  sub     rsp, 28h
0x180001708  call    __scrt_is_ucrt_dll_in_use
0x18000170d  test    eax, eax
0x18000170f  jz      short loc_180001718
0x180001711  call    __isa_available_init
0x180001716  jmp     short loc_180001731
0x180001718  call    _get_startup_argv_mode
0x18000171d  mov     ecx, eax; mode
0x18000171f  call    _o__configure_narrow_argv_0
0x180001724  test    eax, eax
0x180001726  jz      short loc_18000172C
0x180001728  xor     al, al
0x18000172a  jmp     short loc_180001733
0x18000172c  call    _initialize_narrow_environment
0x180001731  mov     al, 1
0x180001733  add     rsp, 28h
0x180001737  retn
```
