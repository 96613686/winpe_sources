# __scrt_dllmain_after_initialize_c

- ea: `0x180001814`
- end: `0x180001848`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x180001498`

## callees

- `0x180001814`
- `0x180001d90`
- `0x18000201c`
- `0x180002028`
- `0x1800020e6`
- `0x18000210a`

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
0x180001814  sub     rsp, 28h
0x180001818  call    __scrt_is_ucrt_dll_in_use
0x18000181d  test    eax, eax
0x18000181f  jz      short loc_180001828
0x180001821  call    __isa_available_init
0x180001826  jmp     short loc_180001841
0x180001828  call    _get_startup_argv_mode
0x18000182d  mov     ecx, eax; mode
0x18000182f  call    _o__configure_narrow_argv_0
0x180001834  test    eax, eax
0x180001836  jz      short loc_18000183C
0x180001838  xor     al, al
0x18000183a  jmp     short loc_180001843
0x18000183c  call    _initialize_narrow_environment
0x180001841  mov     al, 1
0x180001843  add     rsp, 28h
0x180001847  retn
```
