# ATL::CComObject<CRemoteAssistance>::~CComObject<CRemoteAssistance>(void)

- ea: `0x14000350c`
- end: `0x140003551`
- name: `??1?$CComObject@VCRemoteAssistance@@@ATL@@UEAA@XZ`
- size: `69`
- prototype: `void __fastcall(CRemoteAssistance *this)`
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140003ea0`

## callees

- `0x140003a7c`
- `0x140017010`

## pseudocode

```c
void __fastcall ATL::CComObject<CRemoteAssistance>::~CComObject<CRemoteAssistance>(CRemoteAssistance *this)
{
  *((_DWORD *)this + 4) = -1073741823;
  *(_QWORD *)this = &ATL::CComObject<CRemoteAssistance>::`vftable'{for `ISupportErrorInfo'};
  *((_QWORD *)this + 1) = &ATL::CComObject<CRemoteAssistance>::`vftable'{for `ATL::IDispatchImpl<IRemoteAssistance,&_GUID const IID_IRemoteAssistance,&_GUID const LIBID_RAServerLib,1,0,ATL::CComTypeInfoHolder>'};
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  CRemoteAssistance::~CRemoteAssistance(this);
}

```

## disassembly

```asm
0x14000350c  push    rbx
0x14000350e  sub     rsp, 20h
0x140003512  mov     dword ptr [rcx+10h], 0C0000001h
0x140003519  lea     rax, ??_7?$CComObject@VCRemoteAssistance@@@ATL@@6BISupportErrorInfo@@@; const ATL::CComObject<CRemoteAssistance>::`vftable'{for `ISupportErrorInfo'}
0x140003520  mov     [rcx], rax
0x140003523  mov     rbx, rcx
0x140003526  lea     rax, ??_7?$CComObject@VCRemoteAssistance@@@ATL@@6B?$IDispatchImpl@UIRemoteAssistance@@$1?IID_IRemoteAssistance@@3U_GUID@@B$1?LIBID_RAServerLib@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@1@@; const ATL::CComObject<CRemoteAssistance>::`vftable'{for `ATL::IDispatchImpl<IRemoteAssistance,&_GUID const IID_IRemoteAssistance,&_GUID const LIBID_RAServerLib,1,0,ATL::CComTypeInfoHolder>'}
0x14000352d  mov     [rcx+8], rax
0x140003531  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x140003538  mov     rax, [rcx]
0x14000353b  mov     rax, [rax+10h]
0x14000353f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003544  mov     rcx, rbx; this
0x140003547  add     rsp, 20h
0x14000354b  pop     rbx
0x14000354c  jmp     ??1CRemoteAssistance@@QEAA@XZ; CRemoteAssistance::~CRemoteAssistance(void)
```
