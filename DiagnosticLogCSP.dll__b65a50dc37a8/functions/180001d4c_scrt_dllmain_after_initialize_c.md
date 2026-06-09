# __scrt_dllmain_after_initialize_c

- ea: `0x180001d4c`
- end: `0x180001d80`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x180001878`

## callees

- `0x180001d4c`
- `0x1800021ec`
- `0x180002478`
- `0x180002484`
- `0x180002576`
- `0x18000259a`

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
0x180001d4c  sub     rsp, 28h
0x180001d50  call    __scrt_is_ucrt_dll_in_use
0x180001d55  test    eax, eax
0x180001d57  jz      short loc_180001D60
0x180001d59  call    __isa_available_init
0x180001d5e  jmp     short loc_180001D79
0x180001d60  call    _get_startup_argv_mode
0x180001d65  mov     ecx, eax; mode
0x180001d67  call    _o__configure_narrow_argv_0
0x180001d6c  test    eax, eax
0x180001d6e  jz      short loc_180001D74
0x180001d70  xor     al, al
0x180001d72  jmp     short loc_180001D7B
0x180001d74  call    _initialize_narrow_environment
0x180001d79  mov     al, 1
0x180001d7b  add     rsp, 28h
0x180001d7f  retn
```
