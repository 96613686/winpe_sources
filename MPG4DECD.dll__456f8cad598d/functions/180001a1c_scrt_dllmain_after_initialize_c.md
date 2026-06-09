# __scrt_dllmain_after_initialize_c

- ea: `0x180001a1c`
- end: `0x180001a50`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x180001598`

## callees

- `0x180001a1c`
- `0x180001df0`
- `0x18000207c`
- `0x180002088`
- `0x1800020ee`
- `0x180002106`

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
0x180001a1c  sub     rsp, 28h
0x180001a20  call    __scrt_is_ucrt_dll_in_use
0x180001a25  test    eax, eax
0x180001a27  jz      short loc_180001A30
0x180001a29  call    __isa_available_init
0x180001a2e  jmp     short loc_180001A49
0x180001a30  call    _get_startup_argv_mode
0x180001a35  mov     ecx, eax; mode
0x180001a37  call    _o__configure_narrow_argv_0
0x180001a3c  test    eax, eax
0x180001a3e  jz      short loc_180001A44
0x180001a40  xor     al, al
0x180001a42  jmp     short loc_180001A4B
0x180001a44  call    _initialize_narrow_environment
0x180001a49  mov     al, 1
0x180001a4b  add     rsp, 28h
0x180001a4f  retn
```
