# Appx::Packaging::BundleManifest::BundleManifestXmlWriter::WriteResourceElement(IAppxManifestQualifiedResource *,ushort const *,ushort const *)

- ea: `0x1800f57e8`
- end: `0x1800f5b31`
- name: `?WriteResourceElement@BundleManifestXmlWriter@BundleManifest@Packaging@Appx@@AEAAJPEAUIAppxManifestQualifiedResource@@PEBG1@Z`
- size: `841`
- prototype: `__int64 __fastcall(Appx::Packaging::BundleManifest::BundleManifestXmlWriter *__hidden this, struct IAppxManifestQualifiedResource *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x1800f5b38`

## callees

- `0x1800133fc`
- `0x18003a284`
- `0x180050e7c`
- `0x18006021c`
- `0x18007d95c`
- `0x18007da44`
- `0x18007df1c`
- `0x1800992a0`
- `0x1800992c4`
- `0x1800f4710`
- `0x1800f57e8`
- `0x180106010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f5a87`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f5ad6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f5afc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f5a87`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f5ad6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f5afc`

## string_xrefs

- `0x1800f5841`: `onecore\printscan\appxpackaging\production\src\bundlemanifestwriter.cpp`
- `0x1800f5880`: `onecore\printscan\appxpackaging\production\src\bundlemanifestwriter.cpp`
- `0x1800f59c0`: `onecore\printscan\appxpackaging\production\src\bundlemanifestwriter.cpp`
- `0x1800f5a1e`: `onecore\printscan\appxpackaging\production\src\bundlemanifestwriter.cpp`
- `0x1800f5a67`: `onecore\printscan\appxpackaging\production\src\bundlemanifestwriter.cpp`
- `0x1800f5ab6`: `onecore\printscan\appxpackaging\production\src\bundlemanifestwriter.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Appx::Packaging::BundleManifest::BundleManifestXmlWriter::WriteResourceElement(
        Appx::Packaging::Xml::MXWriter **this,
        struct IAppxManifestQualifiedResource *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4)
{
  int v8; // eax
  unsigned int v9; // edi
  Appx::Packaging::Xml::MXAttributes *v10; // rbx
  int v11; // eax
  __int64 v12; // rdx
  __int64 v13; // r9
  unsigned int v14; // r8d
  unsigned int i; // eax
  const unsigned __int16 *v16; // r9
  int ElementName; // eax
  unsigned __int64 v18; // rdx
  const unsigned __int16 *v19; // rdi
  int started; // eax
  unsigned int v21; // esi
  unsigned __int64 v22; // rdx
  int v23; // eax
  unsigned __int64 v24; // rdx
  unsigned __int64 v25; // rdx
  int v27; // [rsp+20h] [rbp-60h]
  int v28; // [rsp+20h] [rbp-60h]
  int v29; // [rsp+20h] [rbp-60h]
  LPVOID pv; // [rsp+30h] [rbp-50h] BYREF
  Appx::Packaging::Xml::MXAttributes *v31; // [rsp+38h] [rbp-48h] BYREF
  unsigned int v32; // [rsp+40h] [rbp-40h] BYREF
  int v33; // [rsp+44h] [rbp-3Ch] BYREF
  unsigned __int16 *v34[2]; // [rsp+48h] [rbp-38h] BYREF
  unsigned __int16 v35[12]; // [rsp+58h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+38h]

  v34[1] = (unsigned __int16 *)-2LL;
  v31 = 0;
  v8 = Appx::Packaging::Xml::MXAttributes::Create(&v31);
  v9 = v8;
  v10 = v31;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1E2,
      (unsigned int)"onecore\\printscan\\appxpackaging\\production\\src\\bundlemanifestwriter.cpp",
      (const char *)(unsigned int)v8,
      v27);
LABEL_35:
    Common::AutoPtrDeallocate<Appx::Packaging::Xml::MXAttributes>(v10);
    return v9;
  }
  pv = 0;
  v11 = ((__int64 (__fastcall *)(struct IAppxManifestQualifiedResource *, LPVOID *))a2->lpVtbl->GetLanguage)(a2, &pv);
  v9 = v11;
  if ( v11 < 0 )
  {
    v12 = 485;
    goto LABEL_5;
  }
  if ( pv )
  {
    v11 = Appx::Packaging::Xml::MXAttributes::AddAttribute(v10, &LocaleName, L"Language", (const unsigned __int16 *)pv);
    v9 = v11;
    if ( v11 < 0 )
    {
      v12 = 491;
      goto LABEL_5;
    }
  }
  v32 = 0;
  v11 = ((__int64 (__fastcall *)(struct IAppxManifestQualifiedResource *, unsigned int *))a2->lpVtbl->GetScale)(
          a2,
          &v32);
  v9 = v11;
  if ( v11 < 0 )
  {
    v12 = 495;
    goto LABEL_5;
  }
  if ( v32 )
  {
    v11 = Common::UInt32::Encode(v32, v35, v14, (unsigned int *)&v31);
    v9 = v11;
    if ( v11 < 0 )
    {
      v12 = 500;
      goto LABEL_5;
    }
    v11 = Appx::Packaging::Xml::MXAttributes::AddAttribute(v10, &LocaleName, L"Scale", v35);
    v9 = v11;
    if ( v11 < 0 )
    {
      v12 = 504;
      goto LABEL_5;
    }
  }
  v33 = 0;
  v11 = ((__int64 (__fastcall *)(struct IAppxManifestQualifiedResource *, int *))a2->lpVtbl->GetDXFeatureLevel)(
          a2,
          &v33);
  v9 = v11;
  if ( v11 < 0 )
  {
    v12 = 508;
LABEL_5:
    v13 = (unsigned int)v11;
LABEL_6:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"onecore\\printscan\\appxpackaging\\production\\src\\bundlemanifestwriter.cpp",
      (const char *)v13,
      v27);
    goto LABEL_34;
  }
  if ( v33 )
  {
    for ( i = 0; ; ++i )
    {
      if ( i >= 3 )
      {
        v9 = -2147024809;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x52,
          (unsigned int)"onecore\\printscan\\appxpackaging\\production\\src\\bundlemanifestwriter.cpp",
          (const char *)0x80070057LL,
          v27);
        v13 = 2147942487LL;
        v12 = 510;
        goto LABEL_6;
      }
      if ( *((_DWORD *)&Appx::Packaging::Manifest::Attribute::DXFeatureLevelValues + 4 * i + 2) == v33 )
        break;
    }
    v16 = (const unsigned __int16 *)*((_QWORD *)&Appx::Packaging::Manifest::Attribute::DXFeatureLevelValues + 2 * i);
    if ( v16 )
    {
      v11 = Appx::Packaging::Xml::MXAttributes::AddAttribute(v10, &LocaleName, L"DXFeatureLevel", v16);
      v9 = v11;
      if ( v11 < 0 )
      {
        v12 = 516;
        goto LABEL_5;
      }
    }
  }
  v34[0] = L"Resource";
  v31 = 0;
  ElementName = Appx::Packaging::BundleManifest::BundleManifestXmlWriter::GetElementName(
                  (Appx::Packaging::BundleManifest::BundleManifestXmlWriter *)this,
                  a3,
                  a4,
                  L"Resource",
                  (const unsigned __int16 **)v34,
                  (unsigned __int16 **)&v31);
  v9 = ElementName;
  if ( ElementName < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x209,
      (unsigned int)"onecore\\printscan\\appxpackaging\\production\\src\\bundlemanifestwriter.cpp",
      (const char *)(unsigned int)ElementName,
      v28);
    operator delete(v31, v18);
LABEL_34:
    CoTaskMemFree(pv);
    goto LABEL_35;
  }
  v19 = v34[0];
  started = Appx::Packaging::Xml::MXWriter::StartElement(this[1], a3, v34[0], v34[0], v10);
  v21 = started;
  if ( started < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x20B,
      (unsigned int)"onecore\\printscan\\appxpackaging\\production\\src\\bundlemanifestwriter.cpp",
      (const char *)(unsigned int)started,
      v29);
    operator delete(v31, v22);
    CoTaskMemFree(pv);
    v9 = v21;
    goto LABEL_35;
  }
  v23 = Appx::Packaging::Xml::MXWriter::EndElement(this[1], a3, v19, v19);
  v9 = v23;
  if ( v23 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x20C,
      (unsigned int)"onecore\\printscan\\appxpackaging\\production\\src\\bundlemanifestwriter.cpp",
      (const char *)(unsigned int)v23,
      v29);
    operator delete(v31, v25);
    goto LABEL_34;
  }
  operator delete(v31, v24);
  CoTaskMemFree(pv);
  Common::AutoPtrDeallocate<Appx::Packaging::Xml::MXAttributes>(v10);
  return 0;
}

```

## disassembly

```asm
0x1800f57e8  push    rbp
0x1800f57ea  push    rbx
0x1800f57eb  push    rsi
0x1800f57ec  push    rdi
0x1800f57ed  push    r12
0x1800f57ef  push    r14
0x1800f57f1  push    r15
0x1800f57f3  mov     rbp, rsp
0x1800f57f6  sub     rsp, 80h
0x1800f57fd  mov     [rbp+var_30], 0FFFFFFFFFFFFFFFEh
0x1800f5805  mov     rax, cs:__security_cookie
0x1800f580c  xor     rax, rsp
0x1800f580f  mov     [rbp+var_10], rax
0x1800f5813  mov     r12, r9
0x1800f5816  mov     r15, r8
0x1800f5819  mov     rsi, rdx
0x1800f581c  mov     r14, rcx
0x1800f581f  mov     [rbp+var_48], 0
0x1800f5827  lea     rcx, [rbp+var_48]; struct Appx::Packaging::Xml::MXAttributes **
0x1800f582b  call    ?Create@MXAttributes@Xml@Packaging@Appx@@SAJPEAPEAV1234@@Z; Appx::Packaging::Xml::MXAttributes::Create(Appx::Packaging::Xml::MXAttributes * *)
0x1800f5830  mov     edi, eax
0x1800f5832  mov     rbx, [rbp+var_48]
0x1800f5836  test    eax, eax
0x1800f5838  jns     short loc_1800F5857
0x1800f583a  mov     rcx, [rbp+38h]; this
0x1800f583e  mov     r9d, eax; char *
0x1800f5841  lea     r8, aOnecorePrintsc_162; "onecore\\printscan\\appxpackaging\\prod"...
0x1800f5848  mov     edx, 1E2h; void *
0x1800f584d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f5852  jmp     loc_1800F5AE2
0x1800f5857  mov     [rbp+pv], 0
0x1800f585f  mov     rax, [rsi]
0x1800f5862  lea     rdx, [rbp+pv]
0x1800f5866  mov     rcx, rsi
0x1800f5869  mov     rax, [rax+18h]
0x1800f586d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f5872  mov     edi, eax
0x1800f5874  test    eax, eax
0x1800f5876  jns     short loc_1800F5895
0x1800f5878  mov     edx, 1E5h; void *
0x1800f587d  mov     r9d, eax; char *
0x1800f5880  lea     r8, aOnecorePrintsc_162; "onecore\\printscan\\appxpackaging\\prod"...
0x1800f5887  mov     rcx, [rbp+38h]; this
0x1800f588b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f5890  jmp     loc_1800F5AD2
0x1800f5895  mov     r9, [rbp+pv]; unsigned __int16 *
0x1800f5899  test    r9, r9
0x1800f589c  jz      short loc_1800F58C1
0x1800f589e  lea     r8, ?Language@AttributeNameWithoutPrefix@BundleManifest@Packaging@Appx@@3QBGB; "Language"
0x1800f58a5  lea     rdx, LocaleName; unsigned __int16 *
0x1800f58ac  mov     rcx, rbx; this
0x1800f58af  call    ?AddAttribute@MXAttributes@Xml@Packaging@Appx@@QEAAJPEBG00@Z; Appx::Packaging::Xml::MXAttributes::AddAttribute(ushort const *,ushort const *,ushort const *)
0x1800f58b4  mov     edi, eax
0x1800f58b6  test    eax, eax
0x1800f58b8  jns     short loc_1800F58C1
0x1800f58ba  mov     edx, 1EBh
0x1800f58bf  jmp     short loc_1800F587D
0x1800f58c1  mov     [rbp+var_40], 0
0x1800f58c8  mov     rax, [rsi]
0x1800f58cb  lea     rdx, [rbp+var_40]
0x1800f58cf  mov     rcx, rsi
0x1800f58d2  mov     rax, [rax+20h]
0x1800f58d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f58db  mov     edi, eax
0x1800f58dd  test    eax, eax
0x1800f58df  jns     short loc_1800F58E8
0x1800f58e1  mov     edx, 1EFh
0x1800f58e6  jmp     short loc_1800F587D
0x1800f58e8  mov     ecx, [rbp+var_40]; unsigned int
0x1800f58eb  test    ecx, ecx
0x1800f58ed  jz      short loc_1800F5936
0x1800f58ef  lea     r9, [rbp+var_48]; unsigned int *
0x1800f58f3  lea     rdx, [rbp+var_28]; unsigned __int16 *
0x1800f58f7  call    ?Encode@UInt32@Common@@SAJKPEAGKPEAK@Z; Common::UInt32::Encode(ulong,ushort *,ulong,ulong *)
0x1800f58fc  mov     edi, eax
0x1800f58fe  test    eax, eax
0x1800f5900  jns     short loc_1800F590C
0x1800f5902  mov     edx, 1F4h
0x1800f5907  jmp     loc_1800F587D
0x1800f590c  lea     r9, [rbp+var_28]; unsigned __int16 *
0x1800f5910  lea     r8, ?Scale@AttributeNameWithoutPrefix@BundleManifest@Packaging@Appx@@3QBGB; "Scale"
0x1800f5917  lea     rdx, LocaleName; unsigned __int16 *
0x1800f591e  mov     rcx, rbx; this
0x1800f5921  call    ?AddAttribute@MXAttributes@Xml@Packaging@Appx@@QEAAJPEBG00@Z; Appx::Packaging::Xml::MXAttributes::AddAttribute(ushort const *,ushort const *,ushort const *)
0x1800f5926  mov     edi, eax
0x1800f5928  test    eax, eax
0x1800f592a  jns     short loc_1800F5936
0x1800f592c  mov     edx, 1F8h
0x1800f5931  jmp     loc_1800F587D
0x1800f5936  mov     [rbp+var_3C], 0
0x1800f593d  mov     rax, [rsi]
0x1800f5940  lea     rdx, [rbp+var_3C]
0x1800f5944  mov     rcx, rsi
0x1800f5947  mov     rax, [rax+28h]
0x1800f594b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f5950  mov     edi, eax
0x1800f5952  test    eax, eax
0x1800f5954  jns     short loc_1800F5960
0x1800f5956  mov     edx, 1FCh
0x1800f595b  jmp     loc_1800F587D
0x1800f5960  mov     edx, [rbp+var_3C]
0x1800f5963  test    edx, edx
0x1800f5965  jz      short loc_1800F59DE
0x1800f5967  xor     eax, eax
0x1800f5969  lea     r9, ?DXFeatureLevelValues@Attribute@Manifest@Packaging@Appx@@3QBUDXFeatureLevelTable@1234@B; Appx::Packaging::Manifest::Attribute::DXFeatureLevelTable const near * const Appx::Packaging::Manifest::Attribute::DXFeatureLevelValues
0x1800f5970  cmp     eax, 3
0x1800f5973  jnb     short loc_1800F59B4
0x1800f5975  mov     ecx, eax
0x1800f5977  add     rcx, rcx
0x1800f597a  cmp     [r9+rcx*8+8], edx
0x1800f597f  jz      short loc_1800F5985
0x1800f5981  inc     eax
0x1800f5983  jmp     short loc_1800F5970
0x1800f5985  mov     r9, [r9+rcx*8]; unsigned __int16 *
0x1800f5989  test    r9, r9
0x1800f598c  jz      short loc_1800F59DE
0x1800f598e  lea     r8, ?DXFeatureLevel@AttributeNameWithoutPrefix@BundleManifest@Packaging@Appx@@3QBGB; "DXFeatureLevel"
0x1800f5995  lea     rdx, LocaleName; unsigned __int16 *
0x1800f599c  mov     rcx, rbx; this
0x1800f599f  call    ?AddAttribute@MXAttributes@Xml@Packaging@Appx@@QEAAJPEBG00@Z; Appx::Packaging::Xml::MXAttributes::AddAttribute(ushort const *,ushort const *,ushort const *)
0x1800f59a4  mov     edi, eax
0x1800f59a6  test    eax, eax
0x1800f59a8  jns     short loc_1800F59DE
0x1800f59aa  mov     edx, 204h
0x1800f59af  jmp     loc_1800F587D
0x1800f59b4  mov     rcx, [rbp+38h]; this
0x1800f59b8  mov     edi, 80070057h
0x1800f59bd  mov     r9d, edi; char *
0x1800f59c0  lea     r8, aOnecorePrintsc_162; "onecore\\printscan\\appxpackaging\\prod"...
0x1800f59c7  mov     edx, 52h ; 'R'; void *
0x1800f59cc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f59d1  mov     r9d, edi
0x1800f59d4  mov     edx, 1FEh
0x1800f59d9  jmp     loc_1800F5880
0x1800f59de  lea     r9, ?Resource@ElementNameWithoutPrefix@BundleManifest@Packaging@Appx@@3QBGB; "Resource"
0x1800f59e5  mov     [rbp+var_38], r9
0x1800f59e9  mov     [rbp+var_48], 0
0x1800f59f1  lea     rax, [rbp+var_48]
0x1800f59f5  mov     [rsp+80h+var_58], rax; unsigned __int16 **
0x1800f59fa  lea     rax, [rbp+var_38]
0x1800f59fe  mov     [rsp+80h+var_60], rax; int
0x1800f5a03  mov     r8, r12; unsigned __int16 *
0x1800f5a06  mov     rdx, r15; unsigned __int16 *
0x1800f5a09  mov     rcx, r14; this
0x1800f5a0c  call    ?GetElementName@BundleManifestXmlWriter@BundleManifest@Packaging@Appx@@AEAAJPEBG00PEAPEBGPEAPEAG@Z; Appx::Packaging::BundleManifest::BundleManifestXmlWriter::GetElementName(ushort const *,ushort const *,ushort const *,ushort const * *,ushort * *)
0x1800f5a11  mov     edi, eax
0x1800f5a13  test    eax, eax
0x1800f5a15  jns     short loc_1800F5A3F
0x1800f5a17  mov     rcx, [rbp+38h]; this
0x1800f5a1b  mov     r9d, eax; char *
0x1800f5a1e  lea     r8, aOnecorePrintsc_162; "onecore\\printscan\\appxpackaging\\prod"...
0x1800f5a25  mov     edx, 209h; void *
0x1800f5a2a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f5a2f  nop
0x1800f5a30  mov     rcx, [rbp+var_48]; void *
0x1800f5a34  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800f5a39  nop
0x1800f5a3a  jmp     loc_1800F5AD2
0x1800f5a3f  mov     rdi, [rbp+var_38]
0x1800f5a43  mov     [rsp+80h+var_60], rbx; int
0x1800f5a48  mov     r9, rdi; unsigned __int16 *
0x1800f5a4b  mov     r8, rdi; unsigned __int16 *
0x1800f5a4e  mov     rdx, r15; unsigned __int16 *
0x1800f5a51  mov     rcx, [r14+8]; this
0x1800f5a55  call    ?StartElement@MXWriter@Xml@Packaging@Appx@@QEAAJPEBG00AEBVMXAttributes@234@@Z; Appx::Packaging::Xml::MXWriter::StartElement(ushort const *,ushort const *,ushort const *,Appx::Packaging::Xml::MXAttributes const &)
0x1800f5a5a  mov     esi, eax
0x1800f5a5c  test    eax, eax
0x1800f5a5e  jns     short loc_1800F5A97
0x1800f5a60  mov     rcx, [rbp+38h]; this
0x1800f5a64  mov     r9d, eax; char *
0x1800f5a67  lea     r8, aOnecorePrintsc_162; "onecore\\printscan\\appxpackaging\\prod"...
0x1800f5a6e  mov     edx, 20Bh; void *
0x1800f5a73  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f5a78  nop
0x1800f5a79  mov     rcx, [rbp+var_48]; void *
0x1800f5a7d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800f5a82  nop
0x1800f5a83  mov     rcx, [rbp+pv]; pv
0x1800f5a87  call    cs:__imp_CoTaskMemFree
0x1800f5a8e  nop     dword ptr [rax+rax+00h]
0x1800f5a93  mov     edi, esi
0x1800f5a95  jmp     short loc_1800F5AE2
0x1800f5a97  mov     r9, rdi; unsigned __int16 *
0x1800f5a9a  mov     r8, rdi; unsigned __int16 *
0x1800f5a9d  mov     rdx, r15; unsigned __int16 *
0x1800f5aa0  mov     rcx, [r14+8]; this
0x1800f5aa4  call    ?EndElement@MXWriter@Xml@Packaging@Appx@@QEAAJPEBG00@Z; Appx::Packaging::Xml::MXWriter::EndElement(ushort const *,ushort const *,ushort const *)
0x1800f5aa9  mov     edi, eax
0x1800f5aab  test    eax, eax
0x1800f5aad  jns     short loc_1800F5AEE
0x1800f5aaf  mov     rcx, [rbp+38h]; this
0x1800f5ab3  mov     r9d, eax; char *
0x1800f5ab6  lea     r8, aOnecorePrintsc_162; "onecore\\printscan\\appxpackaging\\prod"...
0x1800f5abd  mov     edx, 20Ch; void *
0x1800f5ac2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f5ac7  nop
0x1800f5ac8  mov     rcx, [rbp+var_48]; void *
0x1800f5acc  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800f5ad1  nop
0x1800f5ad2  mov     rcx, [rbp+pv]; pv
0x1800f5ad6  call    cs:__imp_CoTaskMemFree
0x1800f5add  nop     dword ptr [rax+rax+00h]
0x1800f5ae2  mov     rcx, rbx; void *
0x1800f5ae5  call    ??$AutoPtrDeallocate@VMXAttributes@Xml@Packaging@Appx@@@Common@@YAXPEAVMXAttributes@Xml@Packaging@Appx@@@Z; Common::AutoPtrDeallocate<Appx::Packaging::Xml::MXAttributes>(Appx::Packaging::Xml::MXAttributes *)
0x1800f5aea  mov     eax, edi
0x1800f5aec  jmp     short loc_1800F5B12
0x1800f5aee  mov     rcx, [rbp+var_48]; void *
0x1800f5af2  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800f5af7  nop
0x1800f5af8  mov     rcx, [rbp+pv]; pv
0x1800f5afc  call    cs:__imp_CoTaskMemFree
0x1800f5b03  nop     dword ptr [rax+rax+00h]
0x1800f5b08  mov     rcx, rbx; void *
0x1800f5b0b  call    ??$AutoPtrDeallocate@VMXAttributes@Xml@Packaging@Appx@@@Common@@YAXPEAVMXAttributes@Xml@Packaging@Appx@@@Z; Common::AutoPtrDeallocate<Appx::Packaging::Xml::MXAttributes>(Appx::Packaging::Xml::MXAttributes *)
0x1800f5b10  xor     eax, eax
0x1800f5b12  mov     rcx, [rbp+var_10]
0x1800f5b16  xor     rcx, rsp; StackCookie
0x1800f5b19  call    __security_check_cookie
0x1800f5b1e  add     rsp, 80h
0x1800f5b25  pop     r15
0x1800f5b27  pop     r14
0x1800f5b29  pop     r12
0x1800f5b2b  pop     rdi
0x1800f5b2c  pop     rsi
0x1800f5b2d  pop     rbx
0x1800f5b2e  pop     rbp
0x1800f5b2f  retn
```
