# __scrt_dllmain_uninitialize_c

- ea: `0x180002918`
- end: `0x180002948`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: `int()`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800024c8`

## callees

- `0x180002918`
- `0x180003124`
- `0x1800031d2`
- `0x1800031f6`
- `0x18000f0d0`

## pseudocode

```c
int _scrt_dllmain_uninitialize_c()
{
  int result; // eax

  if ( (unsigned int)_scrt_is_ucrt_dll_in_use() )
    return execute_onexit_table(&Table);
  result = ATL::CComCoClass<CMigrationPlugin,&__s_GUID const _GUID_617c0a54_d12e_4340_87e7_01cc31bde762>::GetObjectDescription();
  if ( !result )
    return o__cexit_0();
  return result;
}

```

## disassembly

```asm
0x180002918  sub     rsp, 28h
0x18000291c  call    __scrt_is_ucrt_dll_in_use
0x180002921  test    eax, eax
0x180002923  jz      short loc_180002935
0x180002925  lea     rcx, Table; Table
0x18000292c  add     rsp, 28h
0x180002930  jmp     _execute_onexit_table
0x180002935  call    ?GetObjectDescription@?$CComCoClass@VCMigrationPlugin@@$1?_GUID_617c0a54_d12e_4340_87e7_01cc31bde762@@3U__s_GUID@@B@ATL@@SAPEB_WXZ; ATL::CComCoClass<CMigrationPlugin,&__s_GUID const _GUID_617c0a54_d12e_4340_87e7_01cc31bde762>::GetObjectDescription(void)
0x18000293a  test    eax, eax
0x18000293c  jnz     short loc_180002943
0x18000293e  call    _o__cexit_0
0x180002943  add     rsp, 28h
0x180002947  retn
```
