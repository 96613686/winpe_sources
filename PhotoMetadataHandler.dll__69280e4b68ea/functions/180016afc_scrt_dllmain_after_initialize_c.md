# __scrt_dllmain_after_initialize_c

- ea: `0x180016afc`
- end: `0x180016b30`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x180016728`

## callees

- `0x180016afc`
- `0x180017018`
- `0x1800172a4`
- `0x1800172b0`
- `0x18001736a`
- `0x18001738e`

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
0x180016afc  sub     rsp, 28h
0x180016b00  call    __scrt_is_ucrt_dll_in_use
0x180016b05  test    eax, eax
0x180016b07  jz      short loc_180016B10
0x180016b09  call    __isa_available_init
0x180016b0e  jmp     short loc_180016B29
0x180016b10  call    _get_startup_argv_mode
0x180016b15  mov     ecx, eax; mode
0x180016b17  call    _o__configure_narrow_argv_0
0x180016b1c  test    eax, eax
0x180016b1e  jz      short loc_180016B24
0x180016b20  xor     al, al
0x180016b22  jmp     short loc_180016B2B
0x180016b24  call    _initialize_narrow_environment
0x180016b29  mov     al, 1
0x180016b2b  add     rsp, 28h
0x180016b2f  retn
```
