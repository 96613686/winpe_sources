# __scrt_dllmain_uninitialize_c

- ea: `0x180001ed0`
- end: `0x180001f00`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: `int()`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180001b48`

## callees

- `0x180001ed0`
- `0x180002630`
- `0x180002842`
- `0x180002866`
- `0x180008160`

## pseudocode

```c
int _scrt_dllmain_uninitialize_c()
{
  Windows::Internal::StateRepository::AppInfoFactoryBrokerServer *v0; // rcx
  int result; // eax

  if ( (unsigned int)_scrt_is_ucrt_dll_in_use() )
    return execute_onexit_table(&Table);
  result = Windows::Internal::StateRepository::AppInfoFactoryBrokerServer::Initialize(v0);
  if ( !result )
    return o__cexit_0();
  return result;
}

```

## disassembly

```asm
0x180001ed0  sub     rsp, 28h
0x180001ed4  call    __scrt_is_ucrt_dll_in_use
0x180001ed9  test    eax, eax
0x180001edb  jz      short loc_180001EED
0x180001edd  lea     rcx, Table; Table
0x180001ee4  add     rsp, 28h
0x180001ee8  jmp     _execute_onexit_table
0x180001eed  call    ?Initialize@AppInfoFactoryBrokerServer@StateRepository@Internal@Windows@@UEAAJXZ; Windows::Internal::StateRepository::AppInfoFactoryBrokerServer::Initialize(void)
0x180001ef2  test    eax, eax
0x180001ef4  jnz     short loc_180001EFB
0x180001ef6  call    _o__cexit_0
0x180001efb  add     rsp, 28h
0x180001eff  retn
```
