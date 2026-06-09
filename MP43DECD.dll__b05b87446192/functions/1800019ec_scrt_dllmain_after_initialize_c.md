# __scrt_dllmain_after_initialize_c

- ea: `0x1800019ec`
- end: `0x180001a20`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x180001568`

## callees

- `0x1800019ec`
- `0x180001dc0`
- `0x18000204c`
- `0x180002058`
- `0x1800020be`
- `0x1800020d6`

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
0x1800019ec  sub     rsp, 28h
0x1800019f0  call    __scrt_is_ucrt_dll_in_use
0x1800019f5  test    eax, eax
0x1800019f7  jz      short loc_180001A00
0x1800019f9  call    __isa_available_init
0x1800019fe  jmp     short loc_180001A19
0x180001a00  call    _get_startup_argv_mode
0x180001a05  mov     ecx, eax; mode
0x180001a07  call    _o__configure_narrow_argv_0
0x180001a0c  test    eax, eax
0x180001a0e  jz      short loc_180001A14
0x180001a10  xor     al, al
0x180001a12  jmp     short loc_180001A1B
0x180001a14  call    _initialize_narrow_environment
0x180001a19  mov     al, 1
0x180001a1b  add     rsp, 28h
0x180001a1f  retn
```
