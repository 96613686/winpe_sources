# __scrt_dllmain_after_initialize_c

- ea: `0x180015678`
- end: `0x1800156ac`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x180015218`

## callees

- `0x180015678`
- `0x180015a88`
- `0x180015d14`
- `0x180015d20`
- `0x180015d8a`
- `0x180015dae`

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
0x180015678  sub     rsp, 28h
0x18001567c  call    __scrt_is_ucrt_dll_in_use
0x180015681  test    eax, eax
0x180015683  jz      short loc_18001568C
0x180015685  call    __isa_available_init
0x18001568a  jmp     short loc_1800156A5
0x18001568c  call    _get_startup_argv_mode
0x180015691  mov     ecx, eax; mode
0x180015693  call    _o__configure_narrow_argv_0
0x180015698  test    eax, eax
0x18001569a  jz      short loc_1800156A0
0x18001569c  xor     al, al
0x18001569e  jmp     short loc_1800156A7
0x1800156a0  call    _initialize_narrow_environment
0x1800156a5  mov     al, 1
0x1800156a7  add     rsp, 28h
0x1800156ab  retn
```
