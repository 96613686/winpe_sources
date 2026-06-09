# __scrt_dllmain_after_initialize_c

- ea: `0x180001568`
- end: `0x18000159c`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: `char()`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x1800010e8`

## callees

- `0x180001568`
- `0x180001918`
- `0x180001ba4`
- `0x180001bb0`
- `0x180001c16`
- `0x180001c2e`

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
0x180001568  sub     rsp, 28h
0x18000156c  call    __scrt_is_ucrt_dll_in_use
0x180001571  test    eax, eax
0x180001573  jz      short loc_18000157C
0x180001575  call    __isa_available_init
0x18000157a  jmp     short loc_180001595
0x18000157c  call    _get_startup_argv_mode
0x180001581  mov     ecx, eax; mode
0x180001583  call    _o__configure_narrow_argv_0
0x180001588  test    eax, eax
0x18000158a  jz      short loc_180001590
0x18000158c  xor     al, al
0x18000158e  jmp     short loc_180001597
0x180001590  call    _initialize_narrow_environment
0x180001595  mov     al, 1
0x180001597  add     rsp, 28h
0x18000159b  retn
```
