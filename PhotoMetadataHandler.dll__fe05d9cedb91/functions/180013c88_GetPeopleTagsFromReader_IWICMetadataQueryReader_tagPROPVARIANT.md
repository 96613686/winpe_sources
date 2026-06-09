# GetPeopleTagsFromReader(IWICMetadataQueryReader *,tagPROPVARIANT *)

- ea: `0x180013c88`
- end: `0x180013e2b`
- name: `?GetPeopleTagsFromReader@@YAJPEAUIWICMetadataQueryReader@@PEAUtagPROPVARIANT@@@Z`
- size: `419`
- prototype: `__int64 __fastcall(struct IWICMetadataQueryReader *, PROPVARIANT *ppropvar)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180006860`

## callees

- `0x1800076b0`
- `0x180007804`
- `0x18000bef4`
- `0x18000fc0c`
- `0x180013c88`
- `0x180013e34`
- `0x180016020`
- `0x18002061c`
- `0x180028010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180013dbd`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180013dbd`
- `PROPSYS!InitPropVariantFromStringVector` at `0x180013df1`
- `PROPSYS!InitPropVariantFromStringVector` at `0x180013df1`

## string_xrefs

- `0x180013d49`: `/http\:\/\/ns.microsoft.com\/photo\/1.2\/t\/Region#:PersonDisplayName`

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
0x180013c88  mov     [rsp-8+arg_10], rbx
0x180013c8d  push    rbp
0x180013c8e  push    rsi
0x180013c8f  push    rdi
0x180013c90  push    r12
0x180013c92  push    r13
0x180013c94  push    r14
0x180013c96  push    r15
0x180013c98  lea     rbp, [rsp-27h]
0x180013c9d  sub     rsp, 0A0h
0x180013ca4  mov     rax, cs:__security_cookie
0x180013cab  xor     rax, rsp
0x180013cae  mov     [rbp+57h+var_40], rax
0x180013cb2  mov     r13, rdx
0x180013cb5  mov     rsi, rcx
0x180013cb8  mov     [rbp+57h+var_68], rcx
0x180013cbc  xorps   xmm0, xmm0
0x180013cbf  xor     eax, eax
0x180013cc1  movups  xmmword ptr [rdx], xmm0
0x180013cc4  mov     [rdx+10h], rax
0x180013cc8  movdqu  xmmword ptr [rbp+57h+prgsz], xmm0
0x180013ccd  xor     ecx, ecx
0x180013ccf  mov     r12d, ecx
0x180013cd2  mov     [rbp+57h+var_78], rcx
0x180013cd6  mov     [rbp+57h+var_70], ecx
0x180013cd9  lea     rax, ??_7?$CCoDynamicArray@PEBG@@6B@; const CCoDynamicArray<ushort const *>::`vftable'
0x180013ce0  mov     [rbp+57h+var_90], rax
0x180013ce4  mov     r14d, ecx
0x180013ce7  mov     rbx, [rbp+57h+prgsz+8]
0x180013ceb  mov     r15, [rbp+57h+prgsz]
0x180013cef  mov     r9d, r14d
0x180013cf2  lea     r8, aUlongD; "/{ulong=%d}"
0x180013cf9  mov     edx, 0Fh; unsigned __int64
0x180013cfe  lea     rcx, [rbp+57h+var_60]; unsigned __int16 *
0x180013d02  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180013d07  mov     edi, eax
0x180013d09  xor     eax, eax
0x180013d0b  test    edi, edi
0x180013d0d  js      loc_180013DE4
0x180013d13  mov     [rbp+57h+var_B0], rax
0x180013d17  lea     r9, [rbp+57h+var_B0]; struct IWICMetadataQueryReader **
0x180013d1b  lea     rdx, [rbp+57h+var_60]; unsigned __int16 *
0x180013d1f  mov     rcx, rsi; struct IWICMetadataQueryReader *
0x180013d22  call    ?GetNestedReaderFromQueryReader@@YAJPEAUIWICMetadataQueryReader@@PEBGAEBU_GUID@@PEAPEAU1@@Z; GetNestedReaderFromQueryReader(IWICMetadataQueryReader *,ushort const *,_GUID const &,IWICMetadataQueryReader * *)
0x180013d27  mov     edi, eax
0x180013d29  test    eax, eax
0x180013d2b  js      loc_180013DC4
0x180013d31  xorps   xmm0, xmm0
0x180013d34  xor     eax, eax
0x180013d36  movups  xmmword ptr [rbp+57h+pvar], xmm0
0x180013d3a  mov     qword ptr [rbp+57h+pvar+10h], rax
0x180013d3e  mov     rcx, [rbp+57h+var_B0]
0x180013d42  mov     rax, [rcx]
0x180013d45  lea     r8, [rbp+57h+pvar]
0x180013d49  lea     rdx, aHttpNsMicrosof; "/http\\:\\/\\/ns.microsoft.com\\/photo"...
0x180013d50  mov     rax, [rax+28h]
0x180013d54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013d59  xor     ecx, ecx
0x180013d5b  test    eax, eax
0x180013d5d  js      short loc_180013DB9
0x180013d5f  cmp     word ptr [rbp+57h+pvar], 1Fh
0x180013d64  jnz     short loc_180013DB9
0x180013d66  mov     rax, qword ptr [rbp+57h+pvar+8]
0x180013d6a  test    rax, rax
0x180013d6d  jz      short loc_180013DB9
0x180013d6f  cmp     [rax], cx
0x180013d72  jz      short loc_180013DB9
0x180013d74  mov     rsi, rbx
0x180013d77  cmp     rbx, r12
0x180013d7a  jb      short loc_180013D9D
0x180013d7c  lea     rdx, [rbx+1]
0x180013d80  lea     rcx, [rbp+57h+prgsz]
0x180013d84  call    ?GrowBuffer@?$CAtlArray@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@AEAA_N_K@Z; ATL::CAtlArray<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::GrowBuffer(unsigned __int64)
0x180013d89  test    al, al
0x180013d8b  jz      short loc_180013DD9
0x180013d8d  mov     r12, [rbp+57h+var_78]
0x180013d91  mov     rbx, [rbp+57h+prgsz+8]
0x180013d95  mov     r15, [rbp+57h+prgsz]
0x180013d99  mov     rax, qword ptr [rbp+57h+pvar+8]
0x180013d9d  mov     [r15+rsi*8], rax
0x180013da1  inc     rbx
0x180013da4  mov     [rbp+57h+prgsz+8], rbx
0x180013da8  xorps   xmm0, xmm0
0x180013dab  xor     eax, eax
0x180013dad  movups  xmmword ptr [rbp+57h+pvar], xmm0
0x180013db1  mov     qword ptr [rbp+57h+pvar+10h], rax
0x180013db5  mov     rsi, [rbp+57h+var_68]
0x180013db9  lea     rcx, [rbp+57h+pvar]; pvar
0x180013dbd  call    cs:__imp_PropVariantClear
0x180013dc3  nop
0x180013dc4  lea     rcx, [rbp+57h+var_B0]
0x180013dc8  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180013dcd  test    edi, edi
0x180013dcf  js      short loc_180013DE4
0x180013dd1  inc     r14d
0x180013dd4  jmp     loc_180013CEF
0x180013dd9  mov     ecx, 8007000Eh; int
0x180013dde  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180013de4  test    rbx, rbx
0x180013de7  jz      short loc_180013DF9
0x180013de9  mov     r8, r13; ppropvar
0x180013dec  mov     edx, ebx; cElems
0x180013dee  mov     rcx, r15; prgsz
0x180013df1  call    cs:__imp_InitPropVariantFromStringVector
0x180013df7  mov     edi, eax
0x180013df9  lea     rcx, [rbp+57h+var_90]
0x180013dfd  call    ??1?$CCoDynamicArray@PEBG@@UEAA@XZ; CCoDynamicArray<ushort const *>::~CCoDynamicArray<ushort const *>(void)
0x180013e02  mov     eax, edi
0x180013e04  mov     rcx, [rbp+57h+var_40]
0x180013e08  xor     rcx, rsp; StackCookie
0x180013e0b  call    __security_check_cookie
0x180013e10  mov     rbx, [rsp+0D0h+arg_10]
0x180013e18  add     rsp, 0A0h
0x180013e1f  pop     r15
0x180013e21  pop     r14
0x180013e23  pop     r13
0x180013e25  pop     r12
0x180013e27  pop     rdi
0x180013e28  pop     rsi
0x180013e29  pop     rbp
0x180013e2a  retn
```
