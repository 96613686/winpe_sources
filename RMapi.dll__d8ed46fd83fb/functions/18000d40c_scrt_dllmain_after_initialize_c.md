# __scrt_dllmain_after_initialize_c

- ea: `0x18000d40c`
- end: `0x18000d440`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x18000cf88`

## callees

- `0x18000d40c`
- `0x18000d914`
- `0x18000dd70`
- `0x18000dd7c`
- `0x18000de8e`
- `0x18000deb2`

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
0x18000d40c  sub     rsp, 28h
0x18000d410  call    __scrt_is_ucrt_dll_in_use
0x18000d415  test    eax, eax
0x18000d417  jz      short loc_18000D420
0x18000d419  call    __isa_available_init
0x18000d41e  jmp     short loc_18000D439
0x18000d420  call    _get_startup_argv_mode
0x18000d425  mov     ecx, eax; mode
0x18000d427  call    _o__configure_narrow_argv_0
0x18000d42c  test    eax, eax
0x18000d42e  jz      short loc_18000D434
0x18000d430  xor     al, al
0x18000d432  jmp     short loc_18000D43B
0x18000d434  call    _initialize_narrow_environment
0x18000d439  mov     al, 1
0x18000d43b  add     rsp, 28h
0x18000d43f  retn
```
