# CBrowserCap::Clone(CBrowserCap * *)

- ea: `0x180007968`
- end: `0x180007a67`
- name: `?Clone@CBrowserCap@@QEAAJPEAPEAV1@@Z`
- size: `255`
- prototype: `__int64 __fastcall(CBrowserCap *__hidden this, struct CBrowserCap **)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180007a70`

## callees

- `0x1800037f4`
- `0x180007358`
- `0x180007570`
- `0x180007968`
- `0x1800099f8`
- `0x18000d010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x180007a42`
- `KERNEL32!LeaveCriticalSection` at `0x180007a42`
- `KERNEL32!EnterCriticalSection` at `0x1800079fd`
- `KERNEL32!EnterCriticalSection` at `0x1800079fd`
- `ole32!CoCreateFreeThreadedMarshaler` at `0x1800079eb`
- `ole32!CoCreateFreeThreadedMarshaler` at `0x1800079eb`
- `OLEAUT32!__imp_VariantCopy` at `0x180007a2b`
- `OLEAUT32!__imp_VariantCopy` at `0x180007a2b`

## pseudocode

```c
__int64 __fastcall CBrowserCap::Clone(CBrowserCap *this, struct CBrowserCap **a2)
{
  CBrowserCap *v4; // rax
  CBrowserCap *v5; // rdi
  IUnknown *v7; // rax
  unsigned __int64 i; // rdi
  VARIANTARG *v9; // rax
  VARIANTARG *v10; // rsi
  HRESULT v11; // eax

  v4 = (CBrowserCap *)operator new(0x90u);
  v5 = v4;
  if ( v4 )
  {
    CBrowserCap::CBrowserCap(v4);
    *(_QWORD *)v5 = &ATL::CComObject<CBrowserCap>::`vftable'{for `ISupportErrorInfo'};
    *((_QWORD *)v5 + 1) = &ATL::CComObject<CBrowserCap>::`vftable'{for `ATL::IDispatchImpl<IBrowserCap,&_GUID const IID_IBrowserCap,&_GUID const LIBID_BrowserType,1,0,ATL::CComTypeInfoHolder>'};
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
  }
  else
  {
    v5 = 0;
  }
  *a2 = v5;
  if ( !v5 )
    return 2147942414LL;
  v7 = (IUnknown *)(*(__int64 (__fastcall **)(CBrowserCap *))(*(_QWORD *)v5 + 32LL))(v5);
  CoCreateFreeThreadedMarshaler(v7, (LPUNKNOWN *)v5 + 9);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 104));
  for ( i = *((_QWORD *)this + 11); i < *((_QWORD *)this + 12); i += 40LL )
  {
    v9 = (VARIANTARG *)TStringMap<ATL::CComVariant>::operator[]((char *)*a2 + 80, i);
    v10 = v9;
    if ( v9 != (VARIANTARG *)(i + 16) )
    {
      v11 = VariantCopy(v9, (const VARIANTARG *)(i + 16));
      if ( v11 < 0 )
      {
        v10->vt = 10;
        v10->lVal = v11;
        ATL::AtlThrowImpl(v11);
      }
    }
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 104));
  return 0;
}

```

## disassembly

```asm
0x180007968  push    rbx
0x18000796a  push    rbp
0x18000796b  push    rsi
0x18000796c  push    rdi
0x18000796d  push    r14
0x18000796f  push    r15
0x180007971  sub     rsp, 28h
0x180007975  mov     r14, rdx
0x180007978  mov     rbp, rcx
0x18000797b  mov     ecx, 90h; unsigned __int64
0x180007980  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180007985  mov     rdi, rax
0x180007988  mov     [rsp+58h+arg_8], rax
0x18000798d  test    rax, rax
0x180007990  jz      short loc_1800079C4
0x180007992  mov     rcx, rax; this
0x180007995  call    ??0CBrowserCap@@QEAA@XZ; CBrowserCap::CBrowserCap(void)
0x18000799a  lea     rax, ??_7?$CComObject@VCBrowserCap@@@ATL@@6BISupportErrorInfo@@@; const ATL::CComObject<CBrowserCap>::`vftable'{for `ISupportErrorInfo'}
0x1800079a1  mov     [rdi], rax
0x1800079a4  lea     rax, ??_7?$CComObject@VCBrowserCap@@@ATL@@6B?$IDispatchImpl@UIBrowserCap@@$1?IID_IBrowserCap@@3U_GUID@@B$1?LIBID_BrowserType@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@1@@; const ATL::CComObject<CBrowserCap>::`vftable'{for `ATL::IDispatchImpl<IBrowserCap,&_GUID const IID_IBrowserCap,&_GUID const LIBID_BrowserType,1,0,ATL::CComTypeInfoHolder>'}
0x1800079ab  mov     [rdi+8], rax
0x1800079af  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800079b6  mov     rax, [rcx]
0x1800079b9  mov     rax, [rax+8]
0x1800079bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800079c2  jmp     short loc_1800079C6
0x1800079c4  xor     edi, edi
0x1800079c6  mov     [r14], rdi
0x1800079c9  test    rdi, rdi
0x1800079cc  jnz     short loc_1800079D5
0x1800079ce  mov     eax, 8007000Eh
0x1800079d3  jmp     short loc_180007A4A
0x1800079d5  mov     rax, [rdi]
0x1800079d8  mov     rcx, rdi
0x1800079db  mov     rax, [rax+20h]
0x1800079df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800079e4  mov     rcx, rax; punkOuter
0x1800079e7  lea     rdx, [rdi+48h]; ppunkMarshal
0x1800079eb  call    cs:__imp_CoCreateFreeThreadedMarshaler
0x1800079f1  lea     rbx, [rbp+68h]
0x1800079f5  mov     [rsp+58h+arg_8], rbx
0x1800079fa  mov     rcx, rbx; lpCriticalSection
0x1800079fd  call    cs:__imp_EnterCriticalSection
0x180007a03  nop
0x180007a04  mov     rdi, [rbp+58h]
0x180007a08  jmp     short loc_180007A39
0x180007a0a  lea     r15, [rdi+10h]
0x180007a0e  mov     rcx, [r14]
0x180007a11  add     rcx, 50h ; 'P'
0x180007a15  mov     rdx, rdi
0x180007a18  call    ??A?$TStringMap@VCComVariant@ATL@@@@QEAAAEAVCComVariant@ATL@@AEBVString@@@Z; TStringMap<ATL::CComVariant>::operator[](String const &)
0x180007a1d  mov     rsi, rax
0x180007a20  cmp     rax, r15
0x180007a23  jz      short loc_180007A35
0x180007a25  mov     rdx, r15; pvargSrc
0x180007a28  mov     rcx, rax; pvargDest
0x180007a2b  call    cs:__imp_VariantCopy
0x180007a31  test    eax, eax
0x180007a33  js      short loc_180007A57
0x180007a35  add     rdi, 28h ; '('
0x180007a39  cmp     rdi, [rbp+60h]
0x180007a3d  jb      short loc_180007A0A
0x180007a3f  mov     rcx, rbx; lpCriticalSection
0x180007a42  call    cs:__imp_LeaveCriticalSection
0x180007a48  xor     eax, eax
0x180007a4a  add     rsp, 28h
0x180007a4e  pop     r15
0x180007a50  pop     r14
0x180007a52  pop     rdi
0x180007a53  pop     rsi
0x180007a54  pop     rbp
0x180007a55  pop     rbx
0x180007a56  retn
0x180007a57  mov     word ptr [rsi], 0Ah
0x180007a5c  mov     [rsi+8], eax
0x180007a5f  mov     ecx, eax; int
0x180007a61  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
