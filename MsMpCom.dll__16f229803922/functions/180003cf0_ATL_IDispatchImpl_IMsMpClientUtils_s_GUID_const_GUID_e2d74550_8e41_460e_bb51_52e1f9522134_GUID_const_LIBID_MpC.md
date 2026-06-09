# ATL::IDispatchImpl<IMsMpClientUtils,&__s_GUID const _GUID_e2d74550_8e41_460e_bb51_52e1f9522134,&_GUID const LIBID_MpComExportsLib,1,0,ATL::CComTypeInfoHolder>::GetIDsOfNames(_GUID const &,ushort * *,uint,ulong,long *)

- ea: `0x180003cf0`
- end: `0x180003cfc`
- name: `?GetIDsOfNames@?$IDispatchImpl@UIMsMpClientUtils@@$1?_GUID_e2d74550_8e41_460e_bb51_52e1f9522134@@3U__s_GUID@@B$1?LIBID_MpComExportsLib@@3U_GUID@@B$00$0A@VCComTypeInfoHolder@ATL@@@ATL@@UEAAJAEBU_GUID@@PEAPEAGIKPEAJ@Z`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180003d44`

## pseudocode

```c
__int64 __fastcall ATL::IDispatchImpl<IMsMpClientUtils,&__s_GUID const _GUID_e2d74550_8e41_460e_bb51_52e1f9522134,&_GUID const LIBID_MpComExportsLib,1,0,ATL::CComTypeInfoHolder>::GetIDsOfNames(
        __int64 a1,
        const struct _GUID *a2,
        unsigned __int16 **a3,
        unsigned int a4,
        LCID a5,
        int *a6)
{
  return ATL::CComTypeInfoHolder::GetIDsOfNames(
           (ATL::CComTypeInfoHolder *)ATL::IDispatchImpl<IMsMpClientUtils,&__s_GUID const _GUID_e2d74550_8e41_460e_bb51_52e1f9522134,&_GUID const LIBID_MpComExportsLib,1,0,ATL::CComTypeInfoHolder>::_tih,
           a2,
           a3,
           a4,
           a5,
           a6);
}

```

## disassembly

```asm
0x180003cf0  lea     rcx, ?_tih@?$IDispatchImpl@UIMsMpClientUtils@@$1?_GUID_e2d74550_8e41_460e_bb51_52e1f9522134@@3U__s_GUID@@B$1?LIBID_MpComExportsLib@@3U_GUID@@B$00$0A@VCComTypeInfoHolder@ATL@@@ATL@@1VCComTypeInfoHolder@2@A; this
0x180003cf7  jmp     ?GetIDsOfNames@CComTypeInfoHolder@ATL@@QEAAJAEBU_GUID@@PEAPEAGIKPEAJ@Z; ATL::CComTypeInfoHolder::GetIDsOfNames(_GUID const &,ushort * *,uint,ulong,long *)
```
