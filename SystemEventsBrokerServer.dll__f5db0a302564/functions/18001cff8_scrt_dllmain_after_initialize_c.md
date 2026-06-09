# __scrt_dllmain_after_initialize_c

- ea: `0x18001cff8`
- end: `0x18001d02c`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x18001cc38`

## callees

- `0x18001cff8`
- `0x18001d5c0`
- `0x18001d84c`
- `0x18001d858`
- `0x18001d8f6`
- `0x18001d91a`

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
0x18001cff8  sub     rsp, 28h
0x18001cffc  call    __scrt_is_ucrt_dll_in_use
0x18001d001  test    eax, eax
0x18001d003  jz      short loc_18001D00C
0x18001d005  call    __isa_available_init
0x18001d00a  jmp     short loc_18001D025
0x18001d00c  call    _get_startup_argv_mode
0x18001d011  mov     ecx, eax; mode
0x18001d013  call    _o__configure_narrow_argv_0
0x18001d018  test    eax, eax
0x18001d01a  jz      short loc_18001D020
0x18001d01c  xor     al, al
0x18001d01e  jmp     short loc_18001D027
0x18001d020  call    _initialize_narrow_environment
0x18001d025  mov     al, 1
0x18001d027  add     rsp, 28h
0x18001d02b  retn
```
