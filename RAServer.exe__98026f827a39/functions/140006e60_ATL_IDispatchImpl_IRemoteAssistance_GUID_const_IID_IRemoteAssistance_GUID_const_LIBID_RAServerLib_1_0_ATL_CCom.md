# ATL::IDispatchImpl<IRemoteAssistance,&_GUID const IID_IRemoteAssistance,&_GUID const LIBID_RAServerLib,1,0,ATL::CComTypeInfoHolder>::GetTypeInfo(uint,ulong,ITypeInfo * *)

- ea: `0x140006e60`
- end: `0x140006e6c`
- name: `?GetTypeInfo@?$IDispatchImpl@UIRemoteAssistance@@$1?IID_IRemoteAssistance@@3U_GUID@@B$1?LIBID_RAServerLib@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@ATL@@UEAAJIKPEAPEAUITypeInfo@@@Z`
- size: `12`
- prototype: `__int64 __fastcall(__int64, unsigned int, unsigned int, struct ITypeInfo **)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callees

- `0x140006e74`

## pseudocode

```c
__int64 __fastcall ATL::IDispatchImpl<IRemoteAssistance,&_GUID const IID_IRemoteAssistance,&_GUID const LIBID_RAServerLib,1,0,ATL::CComTypeInfoHolder>::GetTypeInfo(
        __int64 a1,
        unsigned int a2,
        unsigned int a3,
        struct ITypeInfo **a4)
{
  return ATL::CComTypeInfoHolder::GetTypeInfo(
           (ATL::CComTypeInfoHolder *)ATL::IDispatchImpl<IRemoteAssistance,&_GUID const IID_IRemoteAssistance,&_GUID const LIBID_RAServerLib,1,0,ATL::CComTypeInfoHolder>::_tih,
           a2,
           a3,
           a4);
}

```

## disassembly

```asm
0x140006e60  lea     rcx, ?_tih@?$IDispatchImpl@UIRemoteAssistance@@$1?IID_IRemoteAssistance@@3U_GUID@@B$1?LIBID_RAServerLib@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@ATL@@1VCComTypeInfoHolder@2@A; this
0x140006e67  jmp     ?GetTypeInfo@CComTypeInfoHolder@ATL@@QEAAJIKPEAPEAUITypeInfo@@@Z; ATL::CComTypeInfoHolder::GetTypeInfo(uint,ulong,ITypeInfo * *)
```
