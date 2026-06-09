# __scrt_dllmain_after_initialize_c

- ea: `0x180001de8`
- end: `0x180001e1c`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: `char()`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180001a48`

## callees

- `0x180001de8`
- `0x1800023a4`
- `0x180002630`
- `0x18000284e`
- `0x180002872`
- `0x180005390`

## pseudocode

```c
char _scrt_dllmain_after_initialize_c()
{
  _crt_argv_mode TrustLevel; // eax

  if ( (unsigned int)_scrt_is_ucrt_dll_in_use() )
  {
    _isa_available_init();
  }
  else
  {
    TrustLevel = (unsigned int)Windows::Internal::StateRepository::AppInfoFactoryBrokerServer::InternalGetTrustLevel();
    if ( o__configure_narrow_argv_0(TrustLevel) )
      return 0;
    initialize_narrow_environment();
  }
  return 1;
}

```

## disassembly

```asm
0x180001de8  sub     rsp, 28h
0x180001dec  call    __scrt_is_ucrt_dll_in_use
0x180001df1  test    eax, eax
0x180001df3  jz      short loc_180001DFC
0x180001df5  call    __isa_available_init
0x180001dfa  jmp     short loc_180001E15
0x180001dfc  call    ?InternalGetTrustLevel@AppInfoFactoryBrokerServer@StateRepository@Internal@Windows@@SA?AW4TrustLevel@@XZ; Windows::Internal::StateRepository::AppInfoFactoryBrokerServer::InternalGetTrustLevel(void)
0x180001e01  mov     ecx, eax; mode
0x180001e03  call    _o__configure_narrow_argv_0
0x180001e08  test    eax, eax
0x180001e0a  jz      short loc_180001E10
0x180001e0c  xor     al, al
0x180001e0e  jmp     short loc_180001E17
0x180001e10  call    _initialize_narrow_environment
0x180001e15  mov     al, 1
0x180001e17  add     rsp, 28h
0x180001e1b  retn
```
