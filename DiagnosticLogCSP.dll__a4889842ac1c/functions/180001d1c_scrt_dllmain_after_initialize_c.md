# __scrt_dllmain_after_initialize_c

- ea: `0x180001d1c`
- end: `0x180001d50`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x180001848`

## callees

- `0x180001d1c`
- `0x1800021bc`
- `0x180002448`
- `0x180002454`
- `0x180002546`
- `0x18000256a`

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
0x180001d1c  sub     rsp, 28h
0x180001d20  call    __scrt_is_ucrt_dll_in_use
0x180001d25  test    eax, eax
0x180001d27  jz      short loc_180001D30
0x180001d29  call    __isa_available_init
0x180001d2e  jmp     short loc_180001D49
0x180001d30  call    _get_startup_argv_mode
0x180001d35  mov     ecx, eax; mode
0x180001d37  call    _o__configure_narrow_argv_0
0x180001d3c  test    eax, eax
0x180001d3e  jz      short loc_180001D44
0x180001d40  xor     al, al
0x180001d42  jmp     short loc_180001D4B
0x180001d44  call    _initialize_narrow_environment
0x180001d49  mov     al, 1
0x180001d4b  add     rsp, 28h
0x180001d4f  retn
```
