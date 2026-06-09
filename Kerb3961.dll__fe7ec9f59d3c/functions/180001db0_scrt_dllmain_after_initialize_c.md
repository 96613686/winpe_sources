# __scrt_dllmain_after_initialize_c

- ea: `0x180001db0`
- end: `0x180001de4`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x180001a28`

## callees

- `0x180001db0`
- `0x180002310`
- `0x18000259c`
- `0x18000288c`
- `0x1800028b0`
- `0x1800082e0`

## pseudocode

```c
char _scrt_dllmain_after_initialize_c()
{
  _crt_argv_mode InterfaceVersion; // eax

  if ( (unsigned int)_scrt_is_ucrt_dll_in_use() )
  {
    _isa_available_init();
  }
  else
  {
    InterfaceVersion = (unsigned int)Kerb3961::VersionedEncryptionAlgorithm<1>::GetInterfaceVersion();
    if ( o__configure_narrow_argv_0(InterfaceVersion) )
      return 0;
    initialize_narrow_environment();
  }
  return 1;
}

```

## disassembly

```asm
0x180001db0  sub     rsp, 28h
0x180001db4  call    __scrt_is_ucrt_dll_in_use
0x180001db9  test    eax, eax
0x180001dbb  jz      short loc_180001DC4
0x180001dbd  call    __isa_available_init
0x180001dc2  jmp     short loc_180001DDD
0x180001dc4  call    ?GetInterfaceVersion@?$VersionedEncryptionAlgorithm@$00@Kerb3961@@EEAA?AW4EncryptionInterfaceVersion@2@XZ; Kerb3961::VersionedEncryptionAlgorithm<1>::GetInterfaceVersion(void)
0x180001dc9  mov     ecx, eax; mode
0x180001dcb  call    _o__configure_narrow_argv_0
0x180001dd0  test    eax, eax
0x180001dd2  jz      short loc_180001DD8
0x180001dd4  xor     al, al
0x180001dd6  jmp     short loc_180001DDF
0x180001dd8  call    _initialize_narrow_environment
0x180001ddd  mov     al, 1
0x180001ddf  add     rsp, 28h
0x180001de3  retn
```
