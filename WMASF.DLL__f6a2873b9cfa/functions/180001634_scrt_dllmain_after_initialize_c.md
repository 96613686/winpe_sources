# __scrt_dllmain_after_initialize_c

- ea: `0x180001634`
- end: `0x180001668`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x1800012b8`

## callees

- `0x180001634`
- `0x180001b68`
- `0x180001df4`
- `0x180001e4e`
- `0x180001e72`
- `0x180003600`

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
0x180001634  sub     rsp, 28h
0x180001638  call    __scrt_is_ucrt_dll_in_use
0x18000163d  test    eax, eax
0x18000163f  jz      short loc_180001648
0x180001641  call    __isa_available_init
0x180001646  jmp     short loc_180001661
0x180001648  call    _get_startup_argv_mode
0x18000164d  mov     ecx, eax; mode
0x18000164f  call    _o__configure_narrow_argv_0
0x180001654  test    eax, eax
0x180001656  jz      short loc_18000165C
0x180001658  xor     al, al
0x18000165a  jmp     short loc_180001663
0x18000165c  call    _initialize_narrow_environment
0x180001661  mov     al, 1
0x180001663  add     rsp, 28h
0x180001667  retn
```
