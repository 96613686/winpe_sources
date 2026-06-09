# ATL::IDispatchImpl<IPreGather,&__s_GUID const _GUID_ccec0752_dc07_4c83_a9f1_3cc9d1a1822f,&__s_GUID const _GUID_f31091e5_b0a8_11d6_b6fc_005056c00008,2,0,ATL::CComTypeInfoHolder>::GetIDsOfNames(_GUID const &,wchar_t * *,uint,ulong,long *)

- ea: `0x18000f930`
- end: `0x18000f93c`
- name: `?GetIDsOfNames@?$IDispatchImpl@UIPreGather@@$1?_GUID_ccec0752_dc07_4c83_a9f1_3cc9d1a1822f@@3U__s_GUID@@B$1?_GUID_f31091e5_b0a8_11d6_b6fc_005056c00008@@3U3@B$01$0A@VCComTypeInfoHolder@ATL@@@ATL@@UEAAJAEBU_GUID@@PEAPEA_WIKPEAJ@Z`
- size: `12`
- prototype: `__int64 __fastcall(__int64, const struct _GUID *, wchar_t **, unsigned int, LCID, int *)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callees

- `0x18000f944`

## pseudocode

```c
__int64 __fastcall ATL::IDispatchImpl<IPreGather,&__s_GUID const _GUID_ccec0752_dc07_4c83_a9f1_3cc9d1a1822f,&__s_GUID const _GUID_f31091e5_b0a8_11d6_b6fc_005056c00008,2,0,ATL::CComTypeInfoHolder>::GetIDsOfNames(
        __int64 a1,
        const struct _GUID *a2,
        wchar_t **a3,
        unsigned int a4,
        LCID a5,
        int *a6)
{
  return ATL::CComTypeInfoHolder::GetIDsOfNames(
           (ATL::CComTypeInfoHolder *)ATL::IDispatchImpl<IPreGather,&__s_GUID const _GUID_ccec0752_dc07_4c83_a9f1_3cc9d1a1822f,&__s_GUID const _GUID_f31091e5_b0a8_11d6_b6fc_005056c00008,2,0,ATL::CComTypeInfoHolder>::_tih,
           a2,
           a3,
           a4,
           a5,
           a6);
}

```

## disassembly

```asm
0x18000f930  lea     rcx, ?_tih@?$IDispatchImpl@UIPreGather@@$1?_GUID_ccec0752_dc07_4c83_a9f1_3cc9d1a1822f@@3U__s_GUID@@B$1?_GUID_f31091e5_b0a8_11d6_b6fc_005056c00008@@3U3@B$01$0A@VCComTypeInfoHolder@ATL@@@ATL@@1VCComTypeInfoHolder@2@A; this
0x18000f937  jmp     ?GetIDsOfNames@CComTypeInfoHolder@ATL@@QEAAJAEBU_GUID@@PEAPEA_WIKPEAJ@Z; ATL::CComTypeInfoHolder::GetIDsOfNames(_GUID const &,wchar_t * *,uint,ulong,long *)
```
