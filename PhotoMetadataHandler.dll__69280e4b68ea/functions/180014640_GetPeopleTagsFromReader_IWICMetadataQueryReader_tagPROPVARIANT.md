# GetPeopleTagsFromReader(IWICMetadataQueryReader *,tagPROPVARIANT *)

- ea: `0x180014640`
- end: `0x1800147f0`
- name: `?GetPeopleTagsFromReader@@YAJPEAUIWICMetadataQueryReader@@PEAUtagPROPVARIANT@@@Z`
- size: `432`
- prototype: `__int64 __fastcall(struct IWICMetadataQueryReader *, PROPVARIANT *ppropvar)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180007af0`

## callees

- `0x1800089f0`
- `0x180008b54`
- `0x18000c49c`
- `0x1800103a0`
- `0x180014640`
- `0x1800147f8`
- `0x180016a40`
- `0x18002166c`
- `0x180029010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180014775`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180014775`
- `PROPSYS!InitPropVariantFromStringVector` at `0x1800147af`
- `PROPSYS!InitPropVariantFromStringVector` at `0x1800147af`

## string_xrefs

- `0x180014701`: `/http\:\/\/ns.microsoft.com\/photo\/1.2\/t\/Region#:PersonDisplayName`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall GetPeopleTagsFromReader(struct IWICMetadataQueryReader *a1, PROPVARIANT *ppropvar)
{
  struct IWICMetadataQueryReader *v3; // rsi
  __int128 v4; // rcx
  unsigned __int64 v5; // r12
  unsigned int v6; // r14d
  PCWSTR *v7; // r15
  HRESULT NestedReaderFromQueryReader; // edi
  const struct _GUID *v9; // r8
  LARGE_INTEGER hVal; // rax
  __int64 v11; // rsi
  struct IWICMetadataQueryReader *v13; // [rsp+20h] [rbp-59h] BYREF
  PROPVARIANT pvar; // [rsp+28h] [rbp-51h] BYREF
  void **v15; // [rsp+40h] [rbp-39h] BYREF
  PCWSTR *prgsz[2]; // [rsp+48h] [rbp-31h] BYREF
  unsigned __int64 v17; // [rsp+58h] [rbp-21h]
  int v18; // [rsp+60h] [rbp-19h]
  struct IWICMetadataQueryReader *v19; // [rsp+68h] [rbp-11h]
  unsigned __int16 v20[16]; // [rsp+70h] [rbp-9h] BYREF

  v3 = a1;
  v19 = a1;
  *(_OWORD *)&ppropvar->vt = 0;
  ppropvar->bstrblobVal.pData = 0;
  *(_OWORD *)prgsz = 0;
  v4 = 0;
  v5 = 0;
  v17 = 0;
  v18 = 0;
  v15 = &CCoDynamicArray<unsigned short const *>::`vftable';
  v6 = 0;
  v7 = 0;
  while ( 1 )
  {
    NestedReaderFromQueryReader = StringCchPrintfW(v20, 0xFu, L"/{ulong=%d}", v6);
    if ( NestedReaderFromQueryReader < 0 )
      break;
    v13 = 0;
    NestedReaderFromQueryReader = GetNestedReaderFromQueryReader(v3, v20, v9, &v13);
    if ( NestedReaderFromQueryReader >= 0 )
    {
      memset(&pvar, 0, sizeof(pvar));
      if ( ((int (__fastcall *)(struct IWICMetadataQueryReader *, const wchar_t *, PROPVARIANT *))v13->lpVtbl->GetMetadataByName)(
             v13,
             L"/http\\:\\/\\/ns.microsoft.com\\/photo\\/1.2\\/t\\/Region#:PersonDisplayName",
             &pvar) >= 0
        && pvar.vt == 31 )
      {
        hVal = pvar.hVal;
        if ( pvar.hVal.QuadPart )
        {
          if ( *pvar.bstrVal )
          {
            v11 = *((_QWORD *)&v4 + 1);
            if ( *((_QWORD *)&v4 + 1) >= v5 )
            {
              if ( !(unsigned __int8)ATL::CAtlArray<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::GrowBuffer(
                                       prgsz,
                                       *((_QWORD *)&v4 + 1) + 1LL) )
                ATL::AtlThrowImpl(-2147024882);
              v5 = v17;
              *((PCWSTR **)&v4 + 1) = prgsz[1];
              v7 = prgsz[0];
              hVal = pvar.hVal;
            }
            v7[v11] = (PCWSTR)hVal.QuadPart;
            ++*((_QWORD *)&v4 + 1);
            prgsz[1] = *((PCWSTR **)&v4 + 1);
            memset(&pvar, 0, sizeof(pvar));
            v3 = v19;
          }
        }
      }
      PropVariantClear(&pvar);
    }
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v13);
    if ( NestedReaderFromQueryReader < 0 )
      break;
    ++v6;
  }
  if ( *((_QWORD *)&v4 + 1) )
    NestedReaderFromQueryReader = InitPropVariantFromStringVector(v7, DWORD2(v4), ppropvar);
  CCoDynamicArray<unsigned short const *>::~CCoDynamicArray<unsigned short const *>(&v15);
  return (unsigned int)NestedReaderFromQueryReader;
}

```

## disassembly

```asm
0x180014640  mov     [rsp-8+arg_10], rbx
0x180014645  push    rbp
0x180014646  push    rsi
0x180014647  push    rdi
0x180014648  push    r12
0x18001464a  push    r13
0x18001464c  push    r14
0x18001464e  push    r15
0x180014650  lea     rbp, [rsp-27h]
0x180014655  sub     rsp, 0A0h
0x18001465c  mov     rax, cs:__security_cookie
0x180014663  xor     rax, rsp
0x180014666  mov     [rbp+57h+var_40], rax
0x18001466a  mov     r13, rdx
0x18001466d  mov     rsi, rcx
0x180014670  mov     [rbp+57h+var_68], rcx
0x180014674  xorps   xmm0, xmm0
0x180014677  xor     eax, eax
0x180014679  movups  xmmword ptr [rdx], xmm0
0x18001467c  mov     [rdx+10h], rax
0x180014680  movdqu  xmmword ptr [rbp+57h+prgsz], xmm0
0x180014685  xor     ecx, ecx
0x180014687  mov     r12d, ecx
0x18001468a  mov     [rbp+57h+var_78], rcx
0x18001468e  mov     [rbp+57h+var_70], ecx
0x180014691  lea     rax, ??_7?$CCoDynamicArray@PEBG@@6B@; const CCoDynamicArray<ushort const *>::`vftable'
0x180014698  mov     [rbp+57h+var_90], rax
0x18001469c  mov     r14d, ecx
0x18001469f  mov     rbx, [rbp+57h+prgsz+8]
0x1800146a3  mov     r15, [rbp+57h+prgsz]
0x1800146a7  mov     r9d, r14d
0x1800146aa  lea     r8, aUlongD; "/{ulong=%d}"
0x1800146b1  mov     edx, 0Fh; unsigned __int64
0x1800146b6  lea     rcx, [rbp+57h+var_60]; unsigned __int16 *
0x1800146ba  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800146bf  mov     edi, eax
0x1800146c1  xor     eax, eax
0x1800146c3  test    edi, edi
0x1800146c5  js      loc_1800147A2
0x1800146cb  mov     [rbp+57h+var_B0], rax
0x1800146cf  lea     r9, [rbp+57h+var_B0]; struct IWICMetadataQueryReader **
0x1800146d3  lea     rdx, [rbp+57h+var_60]; unsigned __int16 *
0x1800146d7  mov     rcx, rsi; struct IWICMetadataQueryReader *
0x1800146da  call    ?GetNestedReaderFromQueryReader@@YAJPEAUIWICMetadataQueryReader@@PEBGAEBU_GUID@@PEAPEAU1@@Z; GetNestedReaderFromQueryReader(IWICMetadataQueryReader *,ushort const *,_GUID const &,IWICMetadataQueryReader * *)
0x1800146df  mov     edi, eax
0x1800146e1  test    eax, eax
0x1800146e3  js      loc_180014782
0x1800146e9  xorps   xmm0, xmm0
0x1800146ec  xor     eax, eax
0x1800146ee  movups  xmmword ptr [rbp+57h+pvar], xmm0
0x1800146f2  mov     qword ptr [rbp+57h+pvar+10h], rax
0x1800146f6  mov     rcx, [rbp+57h+var_B0]
0x1800146fa  mov     rax, [rcx]
0x1800146fd  lea     r8, [rbp+57h+pvar]
0x180014701  lea     rdx, aHttpNsMicrosof; "/http\\:\\/\\/ns.microsoft.com\\/photo"...
0x180014708  mov     rax, [rax+28h]
0x18001470c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014711  xor     ecx, ecx
0x180014713  test    eax, eax
0x180014715  js      short loc_180014771
0x180014717  cmp     word ptr [rbp+57h+pvar], 1Fh
0x18001471c  jnz     short loc_180014771
0x18001471e  mov     rax, qword ptr [rbp+57h+pvar+8]
0x180014722  test    rax, rax
0x180014725  jz      short loc_180014771
0x180014727  cmp     [rax], cx
0x18001472a  jz      short loc_180014771
0x18001472c  mov     rsi, rbx
0x18001472f  cmp     rbx, r12
0x180014732  jb      short loc_180014755
0x180014734  lea     rdx, [rbx+1]
0x180014738  lea     rcx, [rbp+57h+prgsz]
0x18001473c  call    ?GrowBuffer@?$CAtlArray@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@AEAA_N_K@Z; ATL::CAtlArray<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::GrowBuffer(unsigned __int64)
0x180014741  test    al, al
0x180014743  jz      short loc_180014797
0x180014745  mov     r12, [rbp+57h+var_78]
0x180014749  mov     rbx, [rbp+57h+prgsz+8]
0x18001474d  mov     r15, [rbp+57h+prgsz]
0x180014751  mov     rax, qword ptr [rbp+57h+pvar+8]
0x180014755  mov     [r15+rsi*8], rax
0x180014759  inc     rbx
0x18001475c  mov     [rbp+57h+prgsz+8], rbx
0x180014760  xorps   xmm0, xmm0
0x180014763  xor     eax, eax
0x180014765  movups  xmmword ptr [rbp+57h+pvar], xmm0
0x180014769  mov     qword ptr [rbp+57h+pvar+10h], rax
0x18001476d  mov     rsi, [rbp+57h+var_68]
0x180014771  lea     rcx, [rbp+57h+pvar]; pvar
0x180014775  call    cs:__imp_PropVariantClear
0x18001477c  nop     dword ptr [rax+rax+00h]
0x180014781  nop
0x180014782  lea     rcx, [rbp+57h+var_B0]
0x180014786  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18001478b  test    edi, edi
0x18001478d  js      short loc_1800147A2
0x18001478f  inc     r14d
0x180014792  jmp     loc_1800146A7
0x180014797  mov     ecx, 8007000Eh; int
0x18001479c  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x1800147a2  test    rbx, rbx
0x1800147a5  jz      short loc_1800147BD
0x1800147a7  mov     r8, r13; ppropvar
0x1800147aa  mov     edx, ebx; cElems
0x1800147ac  mov     rcx, r15; prgsz
0x1800147af  call    cs:__imp_InitPropVariantFromStringVector
0x1800147b6  nop     dword ptr [rax+rax+00h]
0x1800147bb  mov     edi, eax
0x1800147bd  lea     rcx, [rbp+57h+var_90]
0x1800147c1  call    ??1?$CCoDynamicArray@PEBG@@UEAA@XZ; CCoDynamicArray<ushort const *>::~CCoDynamicArray<ushort const *>(void)
0x1800147c6  mov     eax, edi
0x1800147c8  mov     rcx, [rbp+57h+var_40]
0x1800147cc  xor     rcx, rsp; StackCookie
0x1800147cf  call    __security_check_cookie
0x1800147d4  mov     rbx, [rsp+0D0h+arg_10]
0x1800147dc  add     rsp, 0A0h
0x1800147e3  pop     r15
0x1800147e5  pop     r14
0x1800147e7  pop     r13
0x1800147e9  pop     r12
0x1800147eb  pop     rdi
0x1800147ec  pop     rsi
0x1800147ed  pop     rbp
0x1800147ee  retn
```
