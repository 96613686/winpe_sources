# __scrt_dllmain_uninitialize_c

- ea: `0x180001f30`
- end: `0x180001f60`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180001ba8`

## callees

- `0x180001f30`
- `0x18000269c`
- `0x18000270a`
- `0x18000272e`
- `0x18000c8f0`

## pseudocode

```c
enum TrustLevel _scrt_dllmain_uninitialize_c()
{
  enum TrustLevel result; // eax

  if ( (unsigned int)_scrt_is_ucrt_dll_in_use() )
    return execute_onexit_table(&Table);
  result = Windows::ApplicationModel::Activation::PhoneCallActivatedEventArgsImpl::InternalGetTrustLevel();
  if ( result == BaseTrust )
    return (unsigned int)o__cexit_0();
  return result;
}

```

## disassembly

```asm
0x180001f30  sub     rsp, 28h
0x180001f34  call    __scrt_is_ucrt_dll_in_use
0x180001f39  test    eax, eax
0x180001f3b  jz      short loc_180001F4D
0x180001f3d  lea     rcx, Table; Table
0x180001f44  add     rsp, 28h
0x180001f48  jmp     _execute_onexit_table
0x180001f4d  call    ?InternalGetTrustLevel@PhoneCallActivatedEventArgsImpl@Activation@ApplicationModel@Windows@@SA?AW4TrustLevel@@XZ; Windows::ApplicationModel::Activation::PhoneCallActivatedEventArgsImpl::InternalGetTrustLevel(void)
0x180001f52  test    eax, eax
0x180001f54  jnz     short loc_180001F5B
0x180001f56  call    _o__cexit_0
0x180001f5b  add     rsp, 28h
0x180001f5f  retn
```
