# __scrt_dllmain_after_initialize_c

- ea: `0x180001724`
- end: `0x180001758`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x1800012d8`

## callees

- `0x180001724`
- `0x180001cc0`
- `0x180001f4c`
- `0x180001f58`
- `0x18000207e`
- `0x1800020a2`

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
0x180001724  sub     rsp, 28h
0x180001728  call    __scrt_is_ucrt_dll_in_use
0x18000172d  test    eax, eax
0x18000172f  jz      short loc_180001738
0x180001731  call    __isa_available_init
0x180001736  jmp     short loc_180001751
0x180001738  call    _get_startup_argv_mode
0x18000173d  mov     ecx, eax; mode
0x18000173f  call    _o__configure_narrow_argv_0
0x180001744  test    eax, eax
0x180001746  jz      short loc_18000174C
0x180001748  xor     al, al
0x18000174a  jmp     short loc_180001753
0x18000174c  call    _initialize_narrow_environment
0x180001751  mov     al, 1
0x180001753  add     rsp, 28h
0x180001757  retn
```
