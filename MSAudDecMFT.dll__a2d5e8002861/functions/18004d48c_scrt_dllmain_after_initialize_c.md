# __scrt_dllmain_after_initialize_c

- ea: `0x18004d48c`
- end: `0x18004d4c0`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x18004d008`

## callees

- `0x18004d48c`
- `0x18004d8c0`
- `0x18004db4c`
- `0x18004db58`
- `0x18004dc16`
- `0x18004dc3a`

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
0x18004d48c  sub     rsp, 28h
0x18004d490  call    __scrt_is_ucrt_dll_in_use
0x18004d495  test    eax, eax
0x18004d497  jz      short loc_18004D4A0
0x18004d499  call    __isa_available_init
0x18004d49e  jmp     short loc_18004D4B9
0x18004d4a0  call    _get_startup_argv_mode
0x18004d4a5  mov     ecx, eax; mode
0x18004d4a7  call    _o__configure_narrow_argv_0
0x18004d4ac  test    eax, eax
0x18004d4ae  jz      short loc_18004D4B4
0x18004d4b0  xor     al, al
0x18004d4b2  jmp     short loc_18004D4BB
0x18004d4b4  call    _initialize_narrow_environment
0x18004d4b9  mov     al, 1
0x18004d4bb  add     rsp, 28h
0x18004d4bf  retn
```
