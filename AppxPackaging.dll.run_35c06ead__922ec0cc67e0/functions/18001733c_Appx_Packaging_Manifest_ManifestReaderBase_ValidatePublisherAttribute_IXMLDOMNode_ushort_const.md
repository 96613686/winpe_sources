# Appx::Packaging::Manifest::ManifestReaderBase::ValidatePublisherAttribute(IXMLDOMNode *,ushort const *)

- ea: `0x18001733c`
- end: `0x180017684`
- name: `?ValidatePublisherAttribute@ManifestReaderBase@Manifest@Packaging@Appx@@AEAAJPEAUIXMLDOMNode@@PEBG@Z`
- size: `840`
- prototype: `int(Appx::Packaging::Manifest::ManifestReaderBase *__hidden this, struct IXMLDOMNode *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x1800164a4`

## callees

- `0x1800133fc`
- `0x18001733c`
- `0x18001768c`
- `0x18003a4a0`
- `0x18003c7c8`
- `0x18006bf44`
- `0x180071f50`
- `0x1800992c4`
- `0x18009d3d0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001748c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800175ae`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001748c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800175ae`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18001744c`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18001744c`
- `CRYPT32!CertNameToStrW` at `0x1800173b5`
- `CRYPT32!CertNameToStrW` at `0x180017412`
- `CRYPT32!CertNameToStrW` at `0x1800173b5`
- `CRYPT32!CertNameToStrW` at `0x180017412`

## string_xrefs

- `0x1800174a2`: `onecore\printscan\appxpackaging\manifest\src\manifestreaderbase.cpp`
- `0x1800174d7`: `onecore\printscan\appxpackaging\manifest\src\manifestreaderbase.cpp`
- `0x180017588`: `onecore\printscan\appxpackaging\manifest\src\manifestreaderbase.cpp`
- `0x18001765b`: `onecore\printscan\appxpackaging\manifest\src\manifestreaderbase.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Appx::Packaging::Manifest::ManifestReaderBase::ValidatePublisherAttribute(
        Appx::Packaging::XmlLineInformation **this,
        struct IXMLDOMNode *a2,
        const unsigned __int16 *a3)
{
  int EncodedSubjectName; // eax
  unsigned int v7; // ebx
  void *v8; // rdi
  WCHAR *v9; // rbx
  DWORD v10; // eax
  unsigned __int64 v11; // r15
  unsigned __int64 v12; // rax
  WCHAR *v13; // rax
  WCHAR *v14; // rsi
  unsigned __int64 v15; // rdx
  unsigned int v16; // esi
  unsigned __int64 v17; // rdx
  unsigned __int64 v18; // rdx
  unsigned __int64 v20; // rdx
  unsigned __int64 v21; // rdx
  unsigned __int64 v22; // rdx
  int v23; // ecx
  unsigned __int64 v24; // rdx
  unsigned __int64 v25; // rdx
  int v26; // ecx
  unsigned __int64 v27; // rdx
  unsigned __int64 v28; // rdx
  const unsigned __int16 **csz; // [rsp+20h] [rbp-48h]
  int csza; // [rsp+20h] [rbp-48h]
  int cszb; // [rsp+20h] [rbp-48h]
  int cszc; // [rsp+20h] [rbp-48h]
  int cszd; // [rsp+20h] [rbp-48h]
  unsigned int *v34; // [rsp+30h] [rbp-38h] BYREF
  unsigned __int8 *v35; // [rsp+38h] [rbp-30h] BYREF
  void *v36[2]; // [rsp+40h] [rbp-28h] BYREF
  _CRYPTOAPI_BLOB pName; // [rsp+50h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+40h]
  unsigned int v39; // [rsp+C8h] [rbp+60h] BYREF

  v36[1] = (void *)-2LL;
  HIDWORD(v34) = 0;
  v36[0] = 0;
  v35 = 0;
  EncodedSubjectName = Appx::Packaging::GetEncodedSubjectName(a3, (DWORD *)&v34 + 1, (unsigned int *)v36, &v35, csz);
  v7 = EncodedSubjectName;
  if ( EncodedSubjectName >= 0 )
  {
    pName.cbData = HIDWORD(v34);
    *(&pName.cbData + 1) = 0;
    v8 = v36[0];
    pName.pbData = (BYTE *)v36[0];
    v9 = 0;
    v10 = CertNameToStrW(1u, &pName, 0x22200003u, 0, 0);
    v11 = v10;
    if ( v10 - 1 > 0x7FFFFFFD )
    {
      SetLastError(0xDu);
      v16 = -2147024883;
    }
    else
    {
      v12 = 2LL * v10;
      if ( !is_mul_ok(v11, 2u) )
        v12 = -1;
      v13 = (WCHAR *)operator new[](v12, (const struct std::nothrow_t *)&std::nothrow);
      v14 = v13;
      if ( v13 )
      {
        CertNameToStrW(1u, &pName, 0x22200003u, v13, v11);
        v9 = v14;
        operator delete(0, v15);
        v16 = 0;
      }
      else
      {
        SetLastError(0xEu);
        operator delete(0, v25);
        v16 = -2147024882;
      }
    }
    if ( (v16 & 0x80000000) != 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x109,
        (unsigned int)"onecore\\printscan\\appxpackaging\\manifest\\src\\manifestreaderbase.cpp",
        (const char *)v16,
        cszb);
      operator delete(v9, v20);
      operator delete(v8, v21);
    }
    else
    {
      if ( CompareStringW(0x7Fu, 0, a3, -1, v9, -1) == 2 )
      {
        operator delete(v9, v17);
        operator delete(v8, v18);
        return 0;
      }
      LODWORD(v34) = 0;
      v39 = 0;
      Appx::Packaging::XmlLineInformation::GetXmlLineInformation(
        *this,
        (struct IStream *)a2,
        0,
        L"Publisher",
        (const unsigned __int16 *)&v34,
        &v39,
        v34);
      v16 = -2146958844;
      if ( (Microsoft_Windows_AppxPackagingOMEnableBits & 1) != 0 )
        McTemplateU0dqqz_EventWriteTransfer(
          v26,
          (unsigned int)&EVENT_MANIFEST_INVALID_PUBLISHER_ATTRIBUTE,
          -2146958844,
          (_DWORD)v34,
          v39,
          (__int64)a3);
      AppxPackagingLog(&EVENT_MANIFEST_INVALID_PUBLISHER_ATTRIBUTE, 0xB0000081, -2146958844, (unsigned int)v34, v39, a3);
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x112,
        (unsigned int)"onecore\\printscan\\appxpackaging\\manifest\\src\\manifestreaderbase.cpp",
        (const char *)0x80080204LL,
        cszd);
      operator delete(v9, v27);
      operator delete(v8, v28);
    }
    return v16;
  }
  if ( v35 )
  {
    LODWORD(v34) = 0;
    v39 = 0;
    Appx::Packaging::XmlLineInformation::GetXmlLineInformation(
      *this,
      (struct IStream *)a2,
      0,
      L"Publisher",
      (const unsigned __int16 *)&v34,
      &v39,
      v34);
    v16 = -2146958844;
    if ( (Microsoft_Windows_AppxPackagingOMEnableBits & 1) != 0 )
      McTemplateU0dqqz_EventWriteTransfer(
        v23,
        (unsigned int)&EVENT_MANIFEST_INVALID_PUBLISHER_ATTRIBUTE,
        -2146958844,
        (_DWORD)v34,
        v39,
        (__int64)v35);
    AppxPackagingLog(
      &EVENT_MANIFEST_INVALID_PUBLISHER_ATTRIBUTE,
      0xB0000081,
      -2146958844,
      (unsigned int)v34,
      v39,
      (const unsigned __int16 *)v35);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xFE,
      (unsigned int)"onecore\\printscan\\appxpackaging\\manifest\\src\\manifestreaderbase.cpp",
      (const char *)0x80080204LL,
      cszc);
    operator delete(v36[0], v24);
    return v16;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x102,
    (unsigned int)"onecore\\printscan\\appxpackaging\\manifest\\src\\manifestreaderbase.cpp",
    (const char *)(unsigned int)EncodedSubjectName,
    csza);
  operator delete(v36[0], v22);
  return v7;
}

```

## disassembly

```asm
0x18001733c  push    rbp
0x18001733e  push    rbx
0x18001733f  push    rsi
0x180017340  push    rdi
0x180017341  push    r12
0x180017343  push    r13
0x180017345  push    r14
0x180017347  push    r15
0x180017349  mov     rbp, rsp
0x18001734c  sub     rsp, 68h
0x180017350  mov     [rbp+var_20], 0FFFFFFFFFFFFFFFEh
0x180017358  mov     r14, r8
0x18001735b  mov     r12, rdx
0x18001735e  mov     r13, rcx
0x180017361  xor     esi, esi
0x180017363  mov     [rbp+pcbEncoded], esi
0x180017366  mov     [rbp+var_28], rsi
0x18001736a  mov     [rbp+var_30], rsi
0x18001736e  lea     r9, [rbp+var_30]; unsigned __int8 **
0x180017372  lea     r8, [rbp+var_28]; unsigned int *
0x180017376  lea     rdx, [rbp+pcbEncoded]; pcbEncoded
0x18001737a  mov     rcx, r14; pszX500
0x18001737d  call    ?GetEncodedSubjectName@Packaging@Appx@@YAJPEBGPEAKPEAPEAEPEAPEBG@Z; Appx::Packaging::GetEncodedSubjectName(ushort const *,ulong *,uchar * *,ushort const * *)
0x180017382  mov     ebx, eax
0x180017384  test    eax, eax
0x180017386  js      loc_1800174CA
0x18001738c  mov     eax, [rbp+pcbEncoded]
0x18001738f  mov     [rbp+pName.cbData], eax
0x180017392  xor     eax, eax
0x180017394  mov     dword ptr [rbp+pName+4], eax
0x180017397  mov     rdi, [rbp+var_28]
0x18001739b  mov     [rbp+pName.pbData], rdi
0x18001739f  mov     ebx, esi
0x1800173a1  mov     [rsp+68h+csz], esi; csz
0x1800173a5  xor     r9d, r9d; psz
0x1800173a8  mov     r8d, 22200003h; dwStrType
0x1800173ae  lea     rdx, [rbp+pName]; pName
0x1800173b2  lea     ecx, [rsi+1]; dwCertEncodingType
0x1800173b5  call    cs:__imp_CertNameToStrW
0x1800173bc  nop     dword ptr [rax+rax+00h]
0x1800173c1  mov     r15d, eax
0x1800173c4  lea     ecx, [r15-1]
0x1800173c8  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800173cc  cmp     ecx, 7FFFFFFDh
0x1800173d2  ja      loc_180017487
0x1800173d8  lea     eax, [rsi+2]
0x1800173db  mul     r15
0x1800173de  cmovb   rax, r8
0x1800173e2  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800173e9  mov     rcx, rax; unsigned __int64
0x1800173ec  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800173f1  mov     rsi, rax
0x1800173f4  test    rax, rax
0x1800173f7  jz      loc_1800175A9
0x1800173fd  mov     [rsp+68h+csz], r15d; int
0x180017402  mov     r9, rax; psz
0x180017405  mov     r8d, 22200003h; dwStrType
0x18001740b  lea     rdx, [rbp+pName]; pName
0x18001740f  lea     ecx, [rbx+1]; dwCertEncodingType
0x180017412  call    cs:__imp_CertNameToStrW
0x180017419  nop     dword ptr [rax+rax+00h]
0x18001741e  mov     rbx, rsi
0x180017421  xor     ecx, ecx; void *
0x180017423  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180017428  nop
0x180017429  xor     esi, esi
0x18001742b  mov     rcx, [rbp+40h]; this
0x18001742f  test    esi, esi
0x180017431  js      short loc_18001749F
0x180017433  mov     [rsp+68h+cchCount2], 0FFFFFFFFh; cchCount2
0x18001743b  mov     qword ptr [rsp+68h+csz], rbx; lpString2
0x180017440  or      r9d, 0FFFFFFFFh; cchCount1
0x180017444  mov     r8, r14; lpString1
0x180017447  xor     edx, edx; dwCmpFlags
0x180017449  lea     ecx, [rdx+7Fh]; Locale
0x18001744c  call    cs:__imp_CompareStringW
0x180017453  nop     dword ptr [rax+rax+00h]
0x180017458  cmp     eax, 2
0x18001745b  jnz     loc_1800175CD
0x180017461  mov     rcx, rbx; void *
0x180017464  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180017469  nop
0x18001746a  mov     rcx, rdi; void *
0x18001746d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180017472  nop
0x180017473  xor     eax, eax
0x180017475  add     rsp, 68h
0x180017479  pop     r15
0x18001747b  pop     r14
0x18001747d  pop     r13
0x18001747f  pop     r12
0x180017481  pop     rdi
0x180017482  pop     rsi
0x180017483  pop     rbx
0x180017484  pop     rbp
0x180017485  retn
0x180017487  mov     ecx, 0Dh; dwErrCode
0x18001748c  call    cs:__imp_SetLastError
0x180017493  nop     dword ptr [rax+rax+00h]
0x180017498  mov     esi, 8007000Dh
0x18001749d  jmp     short loc_18001742B
0x18001749f  mov     r9d, esi; char *
0x1800174a2  lea     r8, aOnecorePrintsc_124; "onecore\\printscan\\appxpackaging\\mani"...
0x1800174a9  mov     edx, 109h; void *
0x1800174ae  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800174b3  nop
0x1800174b4  mov     rcx, rbx; void *
0x1800174b7  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800174bc  nop
0x1800174bd  mov     rcx, rdi; void *
0x1800174c0  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800174c5  nop
0x1800174c6  mov     eax, esi
0x1800174c8  jmp     short loc_180017475
0x1800174ca  cmp     [rbp+var_30], rsi
0x1800174ce  jnz     short loc_1800174FA
0x1800174d0  mov     rcx, [rbp+40h]; this
0x1800174d4  mov     r9d, ebx; char *
0x1800174d7  lea     r8, aOnecorePrintsc_124; "onecore\\printscan\\appxpackaging\\mani"...
0x1800174de  mov     edx, 102h; void *
0x1800174e3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800174e8  nop
0x1800174e9  mov     rcx, [rbp+var_28]; void *
0x1800174ed  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800174f2  nop
0x1800174f3  mov     eax, ebx
0x1800174f5  jmp     loc_180017475
0x1800174fa  mov     [rbp+var_38], esi
0x1800174fd  mov     [rbp+arg_18], esi
0x180017500  lea     rax, [rbp+arg_18]
0x180017504  mov     qword ptr [rsp+68h+cchCount2], rax; unsigned int *
0x180017509  lea     rax, [rbp+var_38]
0x18001750d  mov     qword ptr [rsp+68h+csz], rax; unsigned __int16 *
0x180017512  lea     r9, ?Publisher@AttributeNameWithoutPrefix@Manifest@Packaging@Appx@@3QBGB; "Publisher"
0x180017519  xor     r8d, r8d; struct IXMLDOMNode *
0x18001751c  mov     rdx, r12; struct IStream *
0x18001751f  mov     rcx, [r13+0]; this
0x180017523  call    ?GetXmlLineInformation@XmlLineInformation@Packaging@Appx@@YAJPEAUIStream@@PEAUIXMLDOMNode@@PEBG2PEAI3@Z; Appx::Packaging::XmlLineInformation::GetXmlLineInformation(IStream *,IXMLDOMNode *,ushort const *,ushort const *,uint *,uint *)
0x180017528  mov     esi, 80080204h
0x18001752d  test    byte ptr cs:Microsoft_Windows_AppxPackagingOMEnableBits, 1
0x180017534  jz      short loc_180017559
0x180017536  mov     rax, [rbp+var_30]
0x18001753a  mov     qword ptr [rsp+68h+cchCount2], rax
0x18001753f  mov     eax, [rbp+arg_18]
0x180017542  mov     [rsp+68h+csz], eax
0x180017546  mov     r9d, [rbp+var_38]
0x18001754a  mov     r8d, esi
0x18001754d  lea     rdx, EVENT_MANIFEST_INVALID_PUBLISHER_ATTRIBUTE
0x180017554  call    McTemplateU0dqqz_EventWriteTransfer
0x180017559  mov     rax, [rbp+var_30]
0x18001755d  mov     qword ptr [rsp+68h+cchCount2], rax; unsigned __int16 *
0x180017562  mov     eax, [rbp+arg_18]
0x180017565  mov     [rsp+68h+csz], eax; int
0x180017569  mov     r9d, [rbp+var_38]; unsigned int
0x18001756d  mov     r8d, esi; int
0x180017570  mov     edx, 0B0000081h; unsigned int
0x180017575  lea     rcx, EVENT_MANIFEST_INVALID_PUBLISHER_ATTRIBUTE; struct _EVENT_DESCRIPTOR *
0x18001757c  call    ?AppxPackagingLog@@YAJAEBU_EVENT_DESCRIPTOR@@KJIIPEBG@Z; AppxPackagingLog(_EVENT_DESCRIPTOR const &,ulong,long,uint,uint,ushort const *)
0x180017581  mov     rcx, [rbp+40h]; this
0x180017585  mov     r9d, esi; char *
0x180017588  lea     r8, aOnecorePrintsc_124; "onecore\\printscan\\appxpackaging\\mani"...
0x18001758f  mov     edx, 0FEh; void *
0x180017594  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017599  nop
0x18001759a  mov     rcx, [rbp+var_28]; void *
0x18001759e  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800175a3  nop
0x1800175a4  jmp     loc_1800174C6
0x1800175a9  mov     ecx, 0Eh; dwErrCode
0x1800175ae  call    cs:__imp_SetLastError
0x1800175b5  nop     dword ptr [rax+rax+00h]
0x1800175ba  nop
0x1800175bb  xor     ecx, ecx; void *
0x1800175bd  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800175c2  nop
0x1800175c3  mov     esi, 8007000Eh
0x1800175c8  jmp     loc_18001742B
0x1800175cd  mov     [rbp+var_38], 0
0x1800175d4  mov     [rbp+arg_18], 0
0x1800175db  lea     rax, [rbp+arg_18]
0x1800175df  mov     qword ptr [rsp+68h+cchCount2], rax; unsigned int *
0x1800175e4  lea     rax, [rbp+var_38]
0x1800175e8  mov     qword ptr [rsp+68h+csz], rax; unsigned __int16 *
0x1800175ed  lea     r9, ?Publisher@AttributeNameWithoutPrefix@Manifest@Packaging@Appx@@3QBGB; "Publisher"
0x1800175f4  xor     r8d, r8d; struct IXMLDOMNode *
0x1800175f7  mov     rdx, r12; struct IStream *
0x1800175fa  mov     rcx, [r13+0]; this
0x1800175fe  call    ?GetXmlLineInformation@XmlLineInformation@Packaging@Appx@@YAJPEAUIStream@@PEAUIXMLDOMNode@@PEBG2PEAI3@Z; Appx::Packaging::XmlLineInformation::GetXmlLineInformation(IStream *,IXMLDOMNode *,ushort const *,ushort const *,uint *,uint *)
0x180017603  mov     esi, 80080204h
0x180017608  test    byte ptr cs:Microsoft_Windows_AppxPackagingOMEnableBits, 1
0x18001760f  jz      short loc_180017630
0x180017611  mov     qword ptr [rsp+68h+cchCount2], r14
0x180017616  mov     eax, [rbp+arg_18]
0x180017619  mov     [rsp+68h+csz], eax
0x18001761d  mov     r9d, [rbp+var_38]
0x180017621  mov     r8d, esi
0x180017624  lea     rdx, EVENT_MANIFEST_INVALID_PUBLISHER_ATTRIBUTE
0x18001762b  call    McTemplateU0dqqz_EventWriteTransfer
0x180017630  mov     qword ptr [rsp+68h+cchCount2], r14; unsigned __int16 *
0x180017635  mov     eax, [rbp+arg_18]
0x180017638  mov     [rsp+68h+csz], eax; int
0x18001763c  mov     r9d, [rbp+var_38]; unsigned int
0x180017640  mov     r8d, esi; int
0x180017643  mov     edx, 0B0000081h; unsigned int
0x180017648  lea     rcx, EVENT_MANIFEST_INVALID_PUBLISHER_ATTRIBUTE; struct _EVENT_DESCRIPTOR *
0x18001764f  call    ?AppxPackagingLog@@YAJAEBU_EVENT_DESCRIPTOR@@KJIIPEBG@Z; AppxPackagingLog(_EVENT_DESCRIPTOR const &,ulong,long,uint,uint,ushort const *)
0x180017654  mov     rcx, [rbp+40h]; this
0x180017658  mov     r9d, esi; char *
0x18001765b  lea     r8, aOnecorePrintsc_124; "onecore\\printscan\\appxpackaging\\mani"...
0x180017662  mov     edx, 112h; void *
0x180017667  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001766c  nop
0x18001766d  mov     rcx, rbx; void *
0x180017670  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180017675  nop
0x180017676  mov     rcx, rdi; void *
0x180017679  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001767e  nop
0x18001767f  jmp     loc_1800174C6
```
