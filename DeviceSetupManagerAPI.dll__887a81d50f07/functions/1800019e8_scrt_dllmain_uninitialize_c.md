# __scrt_dllmain_uninitialize_c

- ea: `0x1800019e8`
- end: `0x180001a18`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: `int()`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800015a8`

## callees

- `0x1800019e8`
- `0x180002418`
- `0x1800024ae`
- `0x1800024d2`
- `0x180009790`

## pseudocode

```c
int _scrt_dllmain_uninitialize_c()
{
  int result; // eax

  if ( (unsigned int)_scrt_is_ucrt_dll_in_use() )
    return execute_onexit_table(&Table);
  result = ATL::CComCoClass<CDsmRefreshTask,&_GUID const CLSID_DsmRefreshTask>::GetObjectDescription();
  if ( !result )
    return o__cexit_0();
  return result;
}

```

## disassembly

```asm
0x1800019e8  sub     rsp, 28h
0x1800019ec  call    __scrt_is_ucrt_dll_in_use
0x1800019f1  test    eax, eax
0x1800019f3  jz      short loc_180001A05
0x1800019f5  lea     rcx, Table; Table
0x1800019fc  add     rsp, 28h
0x180001a00  jmp     _execute_onexit_table
0x180001a05  call    ?GetObjectDescription@?$CComCoClass@VCDsmRefreshTask@@$1?CLSID_DsmRefreshTask@@3U_GUID@@B@ATL@@SAPEBGXZ; ATL::CComCoClass<CDsmRefreshTask,&_GUID const CLSID_DsmRefreshTask>::GetObjectDescription(void)
0x180001a0a  test    eax, eax
0x180001a0c  jnz     short loc_180001A13
0x180001a0e  call    _o__cexit_0
0x180001a13  add     rsp, 28h
0x180001a17  retn
```
