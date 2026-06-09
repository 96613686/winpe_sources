# ATL::CComObjectCached<CRemoteAssistance>::~CComObjectCached<CRemoteAssistance>(void)

- ea: `0x140003558`
- end: `0x140003579`
- name: `??1?$CComObjectCached@VCRemoteAssistance@@@ATL@@QEAA@XZ`
- size: `33`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140003ed8`

## callees

- `0x140003a7c`

## pseudocode

```c
void __fastcall ATL::CComObjectCached<CRemoteAssistance>::~CComObjectCached<CRemoteAssistance>(__int64 a1)
{
  *(_DWORD *)(a1 + 16) = -1073741823;
  *(_QWORD *)a1 = &ATL::CComObjectCached<CRemoteAssistance>::`vftable'{for `ISupportErrorInfo'};
  *(_QWORD *)(a1 + 8) = &ATL::CComObjectCached<CRemoteAssistance>::`vftable'{for `ATL::IDispatchImpl<IRemoteAssistance,&_GUID const IID_IRemoteAssistance,&_GUID const LIBID_RAServerLib,1,0,ATL::CComTypeInfoHolder>'};
  CRemoteAssistance::~CRemoteAssistance((CRemoteAssistance *)a1);
}

```

## disassembly

```asm
0x140003558  lea     rax, ??_7?$CComObjectCached@VCRemoteAssistance@@@ATL@@6BISupportErrorInfo@@@; const ATL::CComObjectCached<CRemoteAssistance>::`vftable'{for `ISupportErrorInfo'}
0x14000355f  mov     dword ptr [rcx+10h], 0C0000001h
0x140003566  mov     [rcx], rax
0x140003569  lea     rax, ??_7?$CComObjectCached@VCRemoteAssistance@@@ATL@@6B?$IDispatchImpl@UIRemoteAssistance@@$1?IID_IRemoteAssistance@@3U_GUID@@B$1?LIBID_RAServerLib@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@1@@; const ATL::CComObjectCached<CRemoteAssistance>::`vftable'{for `ATL::IDispatchImpl<IRemoteAssistance,&_GUID const IID_IRemoteAssistance,&_GUID const LIBID_RAServerLib,1,0,ATL::CComTypeInfoHolder>'}
0x140003570  mov     [rcx+8], rax
0x140003574  jmp     ??1CRemoteAssistance@@QEAA@XZ; CRemoteAssistance::~CRemoteAssistance(void)
```
