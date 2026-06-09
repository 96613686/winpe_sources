# __scrt_dllmain_after_initialize_c

- ea: `0x18000179c`
- end: `0x1800017d0`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x180001318`

## callees

- `0x18000179c`
- `0x180001bd0`
- `0x180001e5c`
- `0x180001e68`
- `0x180001ece`
- `0x180001ef2`

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
0x18000179c  sub     rsp, 28h
0x1800017a0  call    __scrt_is_ucrt_dll_in_use
0x1800017a5  test    eax, eax
0x1800017a7  jz      short loc_1800017B0
0x1800017a9  call    __isa_available_init
0x1800017ae  jmp     short loc_1800017C9
0x1800017b0  call    _get_startup_argv_mode
0x1800017b5  mov     ecx, eax; mode
0x1800017b7  call    _o__configure_narrow_argv_0
0x1800017bc  test    eax, eax
0x1800017be  jz      short loc_1800017C4
0x1800017c0  xor     al, al
0x1800017c2  jmp     short loc_1800017CB
0x1800017c4  call    _initialize_narrow_environment
0x1800017c9  mov     al, 1
0x1800017cb  add     rsp, 28h
0x1800017cf  retn
```
