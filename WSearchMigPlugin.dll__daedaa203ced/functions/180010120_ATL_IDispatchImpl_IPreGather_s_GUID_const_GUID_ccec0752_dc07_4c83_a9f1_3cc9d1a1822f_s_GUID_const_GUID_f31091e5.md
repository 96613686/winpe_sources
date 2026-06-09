# ATL::IDispatchImpl<IPreGather,&__s_GUID const _GUID_ccec0752_dc07_4c83_a9f1_3cc9d1a1822f,&__s_GUID const _GUID_f31091e5_b0a8_11d6_b6fc_005056c00008,2,0,ATL::CComTypeInfoHolder>::GetTypeInfoCount(uint *)

- ea: `0x180010120`
- end: `0x180010134`
- name: `?GetTypeInfoCount@?$IDispatchImpl@UIPreGather@@$1?_GUID_ccec0752_dc07_4c83_a9f1_3cc9d1a1822f@@3U__s_GUID@@B$1?_GUID_f31091e5_b0a8_11d6_b6fc_005056c00008@@3U3@B$01$0A@VCComTypeInfoHolder@ATL@@@ATL@@UEAAJPEAI@Z`
- size: `20`
- prototype: `__int64 __fastcall(__int64, _DWORD *)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180010120`

## pseudocode

```c
__int64 __fastcall ATL::IDispatchImpl<IPreGather,&__s_GUID const _GUID_ccec0752_dc07_4c83_a9f1_3cc9d1a1822f,&__s_GUID const _GUID_f31091e5_b0a8_11d6_b6fc_005056c00008,2,0,ATL::CComTypeInfoHolder>::GetTypeInfoCount(
        __int64 a1,
        _DWORD *a2)
{
  if ( !a2 )
    return 2147500035LL;
  *a2 = 1;
  return 0;
}

```

## disassembly

```asm
0x180010120  test    rdx, rdx
0x180010123  jnz     short loc_18001012B
0x180010125  mov     eax, 80004003h
0x18001012a  retn
0x18001012b  mov     dword ptr [rdx], 1
0x180010131  xor     eax, eax
0x180010133  retn
```
