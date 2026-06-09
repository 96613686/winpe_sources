# __scrt_dllmain_after_initialize_c

- ea: `0x180001e48`
- end: `0x180001e7c`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x180001aa8`

## callees

- `0x180001e48`
- `0x180002410`
- `0x18000269c`
- `0x180002716`
- `0x18000273a`
- `0x180003df0`

## pseudocode

```c
char _scrt_dllmain_after_initialize_c()
{
  enum TrustLevel TrustLevelStatic; // eax

  if ( (unsigned int)_scrt_is_ucrt_dll_in_use() )
  {
    _isa_available_init();
  }
  else
  {
    TrustLevelStatic = WindowsInternal::ApplicationModel::Calls::ServiceUiToastStatics::InternalGetTrustLevelStatic();
    if ( o__configure_narrow_argv_0((_crt_argv_mode)TrustLevelStatic) )
      return 0;
    initialize_narrow_environment();
  }
  return 1;
}

```

## disassembly

```asm
0x180001e48  sub     rsp, 28h
0x180001e4c  call    __scrt_is_ucrt_dll_in_use
0x180001e51  test    eax, eax
0x180001e53  jz      short loc_180001E5C
0x180001e55  call    __isa_available_init
0x180001e5a  jmp     short loc_180001E75
0x180001e5c  call    ?InternalGetTrustLevelStatic@ServiceUiToastStatics@Calls@ApplicationModel@WindowsInternal@@SA?AW4TrustLevel@@XZ; WindowsInternal::ApplicationModel::Calls::ServiceUiToastStatics::InternalGetTrustLevelStatic(void)
0x180001e61  mov     ecx, eax; mode
0x180001e63  call    _o__configure_narrow_argv_0
0x180001e68  test    eax, eax
0x180001e6a  jz      short loc_180001E70
0x180001e6c  xor     al, al
0x180001e6e  jmp     short loc_180001E77
0x180001e70  call    _initialize_narrow_environment
0x180001e75  mov     al, 1
0x180001e77  add     rsp, 28h
0x180001e7b  retn
```
