# __scrt_dllmain_after_initialize_c

- ea: `0x180001fbc`
- end: `0x180001ff0`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: `char()`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x180001c08`

## callees

- `0x180001fbc`
- `0x1800024e4`
- `0x180002770`
- `0x18000277c`
- `0x1800027fa`
- `0x18000281e`

## pseudocode

```c
char _scrt_dllmain_after_initialize_c()
{
  _crt_argv_mode startup_argv_mode; // eax

  if ( _scrt_is_ucrt_dll_in_use() )
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
0x180001fbc  sub     rsp, 28h
0x180001fc0  call    __scrt_is_ucrt_dll_in_use
0x180001fc5  test    eax, eax
0x180001fc7  jz      short loc_180001FD0
0x180001fc9  call    __isa_available_init
0x180001fce  jmp     short loc_180001FE9
0x180001fd0  call    _get_startup_argv_mode
0x180001fd5  mov     ecx, eax; mode
0x180001fd7  call    _o__configure_narrow_argv_0
0x180001fdc  test    eax, eax
0x180001fde  jz      short loc_180001FE4
0x180001fe0  xor     al, al
0x180001fe2  jmp     short loc_180001FEB
0x180001fe4  call    _initialize_narrow_environment
0x180001fe9  mov     al, 1
0x180001feb  add     rsp, 28h
0x180001fef  retn
```
