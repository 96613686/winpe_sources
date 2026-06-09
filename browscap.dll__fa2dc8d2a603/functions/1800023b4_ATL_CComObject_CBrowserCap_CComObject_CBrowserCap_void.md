# ATL::CComObject<CBrowserCap>::~CComObject<CBrowserCap>(void)

- ea: `0x1800023b4`
- end: `0x180002417`
- name: `??1?$CComObject@VCBrowserCap@@@ATL@@UEAA@XZ`
- size: `99`
- prototype: `__int64 __fastcall(CBrowserCap *this)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180002660`

## callees

- `0x1800023b4`
- `0x180007454`
- `0x18000d010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall ATL::CComObject<CBrowserCap>::~CComObject<CBrowserCap>(CBrowserCap *this)
{
  __int64 v2; // rcx

  *(_QWORD *)this = &ATL::CComObject<CBrowserCap>::`vftable'{for `ISupportErrorInfo'};
  *((_QWORD *)this + 1) = &ATL::CComObject<CBrowserCap>::`vftable'{for `ATL::IDispatchImpl<IBrowserCap,&_GUID const IID_IBrowserCap,&_GUID const LIBID_BrowserType,1,0,ATL::CComTypeInfoHolder>'};
  *((_DWORD *)this + 4) = -1073741823;
  v2 = *((_QWORD *)this + 9);
  if ( v2 )
  {
    *((_QWORD *)this + 9) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
  }
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  CBrowserCap::~CBrowserCap(this);
}

```

## disassembly

```asm
0x1800023b4  push    rbx
0x1800023b6  sub     rsp, 20h
0x1800023ba  mov     rbx, rcx
0x1800023bd  lea     rax, ??_7?$CComObject@VCBrowserCap@@@ATL@@6BISupportErrorInfo@@@; const ATL::CComObject<CBrowserCap>::`vftable'{for `ISupportErrorInfo'}
0x1800023c4  mov     [rcx], rax
0x1800023c7  lea     rax, ??_7?$CComObject@VCBrowserCap@@@ATL@@6B?$IDispatchImpl@UIBrowserCap@@$1?IID_IBrowserCap@@3U_GUID@@B$1?LIBID_BrowserType@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@1@@; const ATL::CComObject<CBrowserCap>::`vftable'{for `ATL::IDispatchImpl<IBrowserCap,&_GUID const IID_IBrowserCap,&_GUID const LIBID_BrowserType,1,0,ATL::CComTypeInfoHolder>'}
0x1800023ce  mov     [rcx+8], rax
0x1800023d2  mov     dword ptr [rcx+10h], 0C0000001h
0x1800023d9  mov     rcx, [rcx+48h]
0x1800023dd  test    rcx, rcx
0x1800023e0  jz      short loc_1800023F7
0x1800023e2  mov     qword ptr [rbx+48h], 0
0x1800023ea  mov     rax, [rcx]
0x1800023ed  mov     rax, [rax+10h]
0x1800023f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800023f6  nop
0x1800023f7  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800023fe  mov     rax, [rcx]
0x180002401  mov     rax, [rax+10h]
0x180002405  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000240a  mov     rcx, rbx; this
0x18000240d  add     rsp, 20h
0x180002411  pop     rbx
0x180002412  jmp     ??1CBrowserCap@@QEAA@XZ; CBrowserCap::~CBrowserCap(void)
```
