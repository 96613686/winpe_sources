# ATL::CComObject<CRASrv>::~CComObject<CRASrv>(void)

- ea: `0x1400034c0`
- end: `0x140003506`
- name: `??1?$CComObject@VCRASrv@@@ATL@@UEAA@XZ`
- size: `70`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140003e60`

## callees

- `0x1400039e0`
- `0x140017010`

## pseudocode

```c
void __fastcall ATL::CComObject<CRASrv>::~CComObject<CRASrv>(__int64 a1)
{
  *(_DWORD *)(a1 + 16) = -1073741823;
  *(_QWORD *)a1 = &ATL::CComObject<CRASrv>::`vftable'{for `ATL::IDispatchImpl<IRASrv,&_GUID const IID_IRASrv,&_GUID const LIBID_RAServerLib,1,0,ATL::CComTypeInfoHolder>'};
  *(_QWORD *)(a1 + 8) = &ATL::CComObject<CRASrv>::`vftable'{for `ISupportErrorInfo'};
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  ATL::CComSafeDeleteCriticalSection::~CComSafeDeleteCriticalSection((ATL::CComSafeDeleteCriticalSection *)(a1 + 24));
}

```

## disassembly

```asm
0x1400034c0  push    rbx
0x1400034c2  sub     rsp, 20h
0x1400034c6  mov     dword ptr [rcx+10h], 0C0000001h
0x1400034cd  lea     rax, ??_7?$CComObject@VCRASrv@@@ATL@@6B?$IDispatchImpl@UIRASrv@@$1?IID_IRASrv@@3U_GUID@@B$1?LIBID_RAServerLib@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@1@@; const ATL::CComObject<CRASrv>::`vftable'{for `ATL::IDispatchImpl<IRASrv,&_GUID const IID_IRASrv,&_GUID const LIBID_RAServerLib,1,0,ATL::CComTypeInfoHolder>'}
0x1400034d4  mov     [rcx], rax
0x1400034d7  mov     rbx, rcx
0x1400034da  lea     rax, ??_7?$CComObject@VCRASrv@@@ATL@@6BISupportErrorInfo@@@; const ATL::CComObject<CRASrv>::`vftable'{for `ISupportErrorInfo'}
0x1400034e1  mov     [rcx+8], rax
0x1400034e5  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1400034ec  mov     rax, [rcx]
0x1400034ef  mov     rax, [rax+10h]
0x1400034f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400034f8  lea     rcx, [rbx+18h]; this
0x1400034fc  add     rsp, 20h
0x140003500  pop     rbx
0x140003501  jmp     ??1CComSafeDeleteCriticalSection@ATL@@QEAA@XZ; ATL::CComSafeDeleteCriticalSection::~CComSafeDeleteCriticalSection(void)
```
