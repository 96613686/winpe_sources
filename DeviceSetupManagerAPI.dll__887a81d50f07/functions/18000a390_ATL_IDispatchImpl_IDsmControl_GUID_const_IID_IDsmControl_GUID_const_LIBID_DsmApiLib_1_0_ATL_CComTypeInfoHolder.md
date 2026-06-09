# ATL::IDispatchImpl<IDsmControl,&_GUID const IID_IDsmControl,&_GUID const LIBID_DsmApiLib,1,0,ATL::CComTypeInfoHolder>::GetIDsOfNames(_GUID const &,ushort * *,uint,ulong,long *)

- ea: `0x18000a390`
- end: `0x18000a39c`
- name: `?GetIDsOfNames@?$IDispatchImpl@UIDsmControl@@$1?IID_IDsmControl@@3U_GUID@@B$1?LIBID_DsmApiLib@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@ATL@@UEAAJAEBU_GUID@@PEAPEAGIKPEAJ@Z`
- size: `12`
- prototype: `__int64 __fastcall(__int64, const struct _GUID *, unsigned __int16 **, unsigned int, LCID, int *)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callees

- `0x18000a3a4`

## pseudocode

```c
__int64 __fastcall ATL::IDispatchImpl<IDsmControl,&_GUID const IID_IDsmControl,&_GUID const LIBID_DsmApiLib,1,0,ATL::CComTypeInfoHolder>::GetIDsOfNames(
        __int64 a1,
        const struct _GUID *a2,
        unsigned __int16 **a3,
        unsigned int a4,
        LCID a5,
        int *a6)
{
  return ATL::CComTypeInfoHolder::GetIDsOfNames(
           (ATL::CComTypeInfoHolder *)ATL::IDispatchImpl<IDsmControl,&_GUID const IID_IDsmControl,&_GUID const LIBID_DsmApiLib,1,0,ATL::CComTypeInfoHolder>::_tih,
           a2,
           a3,
           a4,
           a5,
           a6);
}

```

## disassembly

```asm
0x18000a390  lea     rcx, ?_tih@?$IDispatchImpl@UIDsmControl@@$1?IID_IDsmControl@@3U_GUID@@B$1?LIBID_DsmApiLib@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@ATL@@1VCComTypeInfoHolder@2@A; this
0x18000a397  jmp     ?GetIDsOfNames@CComTypeInfoHolder@ATL@@QEAAJAEBU_GUID@@PEAPEAGIKPEAJ@Z; ATL::CComTypeInfoHolder::GetIDsOfNames(_GUID const &,ushort * *,uint,ulong,long *)
```
