# Appx::Packaging::BundleManifest::BundleManifestXmlWriter::WritePackageElement(Appx::Packaging::BundleManifest::PackageInfo *)

- ea: `0x1800f5190`
- end: `0x1800f57e2`
- name: `?WritePackageElement@BundleManifestXmlWriter@BundleManifest@Packaging@Appx@@AEAAJPEAUPackageInfo@234@@Z`
- size: `1618`
- prototype: `__int64 __fastcall(Appx::Packaging::BundleManifest::BundleManifestXmlWriter *__hidden this, struct Appx::Packaging::BundleManifest::PackageInfo *)`
- caller_count: `2`
- callee_count: `15`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x1800f43c0`
- `0x1800f4f0c`

## callees

- `0x1800133fc`
- `0x180050e7c`
- `0x18006021c`
- `0x18007b024`
- `0x18007d95c`
- `0x18007da44`
- `0x18007df1c`
- `0x18007e4bc`
- `0x1800992a0`
- `0x1800992c4`
- `0x1800f4450`
- `0x1800f4710`
- `0x1800f4a44`
- `0x1800f5190`
- `0x1800f5b38`

## string_xrefs

- `0x1800f557a`: `http://schemas.microsoft.com/appx/2019/bundle`
- `0x1800f51e2`: `onecore\printscan\appxpackaging\production\src\bundlemanifestwriter.cpp`
- `0x1800f5293`: `onecore\printscan\appxpackaging\production\src\bundlemanifestwriter.cpp`
- `0x1800f52da`: `onecore\printscan\appxpackaging\production\src\bundlemanifestwriter.cpp`
- `0x1800f531f`: `onecore\printscan\appxpackaging\production\src\bundlemanifestwriter.cpp`
- `0x1800f535f`: `onecore\printscan\appxpackaging\production\src\bundlemanifestwriter.cpp`
- `0x1800f53ba`: `onecore\printscan\appxpackaging\production\src\bundlemanifestwriter.cpp`
- `0x1800f5402`: `onecore\printscan\appxpackaging\production\src\bundlemanifestwriter.cpp`
- `0x1800f5445`: `onecore\printscan\appxpackaging\production\src\bundlemanifestwriter.cpp`
- `0x1800f5488`: `onecore\printscan\appxpackaging\production\src\bundlemanifestwriter.cpp`
- `0x1800f54d5`: `onecore\printscan\appxpackaging\production\src\bundlemanifestwriter.cpp`
- `0x1800f5518`: `onecore\printscan\appxpackaging\production\src\bundlemanifestwriter.cpp`
- `0x1800f5599`: `onecore\printscan\appxpackaging\production\src\bundlemanifestwriter.cpp`
- `0x1800f55ed`: `onecore\printscan\appxpackaging\production\src\bundlemanifestwriter.cpp`
- `0x1800f564e`: `onecore\printscan\appxpackaging\production\src\bundlemanifestwriter.cpp`
- `0x1800f56aa`: `onecore\printscan\appxpackaging\production\src\bundlemanifestwriter.cpp`
- `0x1800f56ee`: `onecore\printscan\appxpackaging\production\src\bundlemanifestwriter.cpp`
- `0x1800f5734`: `onecore\printscan\appxpackaging\production\src\bundlemanifestwriter.cpp`
- `0x1800f5787`: `onecore\printscan\appxpackaging\production\src\bundlemanifestwriter.cpp`
- `0x1800f57a0`: `onecore\printscan\appxpackaging\production\src\bundlemanifestwriter.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Appx::Packaging::BundleManifest::BundleManifestXmlWriter::WritePackageElement(
        Appx::Packaging::Xml::MXWriter **this,
        struct Appx::Packaging::BundleManifest::PackageInfo *a2)
{
  unsigned int v4; // ebx
  int v5; // eax
  Appx::Packaging::Xml::MXAttributes *v6; // rsi
  __int64 v7; // rdx
  unsigned int i; // eax
  __int64 v9; // r9
  int v10; // eax
  unsigned __int64 v11; // rdx
  Appx::Packaging::Xml::MXAttributes *v12; // rbx
  int v13; // eax
  unsigned int v14; // r8d
  unsigned int v15; // edi
  unsigned __int64 v16; // rdx
  int v17; // eax
  unsigned __int64 v18; // rdx
  int v19; // eax
  unsigned __int64 v20; // rdx
  const unsigned __int16 *v21; // r9
  __int64 v22; // rax
  int v23; // eax
  unsigned __int64 v24; // rdx
  const unsigned __int16 *v25; // r9
  int v26; // eax
  unsigned __int64 v27; // rdx
  unsigned __int64 v28; // rcx
  int v29; // eax
  unsigned __int64 v30; // rdx
  int v31; // eax
  unsigned __int64 v32; // rdx
  unsigned __int64 v33; // rcx
  int v34; // eax
  unsigned __int64 v35; // rdx
  int v36; // eax
  unsigned __int64 v37; // rdx
  const unsigned __int16 *v38; // r12
  unsigned __int16 *v39; // r15
  Appx::Packaging::Xml::MXAttributes *v40; // rdi
  int ElementName; // eax
  unsigned __int64 v42; // rdx
  unsigned __int64 v43; // rdx
  int v44; // eax
  unsigned __int64 v45; // rdx
  unsigned __int64 v46; // rdx
  int started; // eax
  unsigned int v48; // r13d
  unsigned __int64 v49; // rdx
  unsigned __int64 v50; // rdx
  int v51; // eax
  unsigned __int64 v52; // rdx
  unsigned __int64 v53; // rdx
  Appx::Packaging::BundleManifest::BundleManifestXmlWriter *v54; // r13
  int v55; // eax
  unsigned int v56; // r14d
  unsigned __int64 v57; // rdx
  unsigned __int64 v58; // rdx
  int v59; // eax
  unsigned __int64 v60; // rdx
  unsigned __int64 v61; // rdx
  unsigned __int64 v62; // rdx
  unsigned __int64 v63; // rdx
  unsigned __int16 **v65; // [rsp+28h] [rbp-79h]
  int v66; // [rsp+28h] [rbp-79h]
  int v67; // [rsp+28h] [rbp-79h]
  int v68; // [rsp+28h] [rbp-79h]
  int v69; // [rsp+28h] [rbp-79h]
  Appx::Packaging::Xml::MXAttributes *v70; // [rsp+38h] [rbp-69h] BYREF
  unsigned __int16 *v71; // [rsp+40h] [rbp-61h] BYREF
  unsigned __int16 *v72; // [rsp+48h] [rbp-59h]
  Appx::Packaging::BundleManifest::BundleManifestXmlWriter *v73; // [rsp+50h] [rbp-51h]
  __int64 v74; // [rsp+58h] [rbp-49h]
  unsigned __int16 v75[24]; // [rsp+60h] [rbp-41h] BYREF
  unsigned __int16 v76[24]; // [rsp+90h] [rbp-11h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+100h] [rbp+5Fh]

  v74 = -2;
  v73 = (Appx::Packaging::BundleManifest::BundleManifestXmlWriter *)this;
  if ( !*((_QWORD *)a2 + 7) )
  {
    v4 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x147,
      (unsigned int)"onecore\\printscan\\appxpackaging\\production\\src\\bundlemanifestwriter.cpp",
      (const char *)0x80070057LL,
      (int)v65);
    return v4;
  }
  v70 = 0;
  v5 = Appx::Packaging::Xml::MXAttributes::Create(&v70);
  v4 = v5;
  v6 = v70;
  if ( v5 < 0 )
  {
    v7 = 330;
LABEL_11:
    v9 = (unsigned int)v5;
LABEL_61:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"onecore\\printscan\\appxpackaging\\production\\src\\bundlemanifestwriter.cpp",
      (const char *)v9,
      (int)v65);
LABEL_62:
    Common::AutoPtrDeallocate<Appx::Packaging::Xml::MXAttributes>(v6);
    return v4;
  }
  for ( i = 0; ; ++i )
  {
    if ( i >= 2 )
    {
      v4 = -2147024809;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x3E,
        (unsigned int)"onecore\\printscan\\appxpackaging\\production\\src\\bundlemanifestwriter.cpp",
        (const char *)0x80070057LL,
        (int)v65);
      v9 = 2147942487LL;
      v7 = 333;
      goto LABEL_61;
    }
    if ( *((_DWORD *)&Appx::Packaging::BundleManifest::Attribute::PackageTypeValues + 4 * i + 2) == *(_DWORD *)a2 )
      break;
  }
  v5 = Appx::Packaging::Xml::MXAttributes::AddAttribute(
         v70,
         &LocaleName,
         L"Type",
         *((const unsigned __int16 **)&Appx::Packaging::BundleManifest::Attribute::PackageTypeValues + 2 * i));
  v4 = v5;
  if ( v5 < 0 )
  {
    v7 = 337;
    goto LABEL_11;
  }
  v70 = 0;
  v10 = Appx::Packaging::ConvertVersionToString(*((Appx::Packaging **)a2 + 1), 4u, 4u, (unsigned int)&v70, v65);
  v4 = v10;
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x154,
      (unsigned int)"onecore\\printscan\\appxpackaging\\production\\src\\bundlemanifestwriter.cpp",
      (const char *)(unsigned int)v10,
      v66);
    operator delete(v70, v11);
    goto LABEL_62;
  }
  v12 = v70;
  v13 = Appx::Packaging::Xml::MXAttributes::AddAttribute(v6, &LocaleName, L"Version", (const unsigned __int16 *)v70);
  v15 = v13;
  if ( v13 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x158,
      (unsigned int)"onecore\\printscan\\appxpackaging\\production\\src\\bundlemanifestwriter.cpp",
      (const char *)(unsigned int)v13,
      v66);
    operator delete(v12, v16);
LABEL_16:
    v4 = v15;
    goto LABEL_62;
  }
  if ( !*(_DWORD *)a2 )
  {
    v70 = 0;
    v17 = ConvertPackageArchitectureToString(*((unsigned int *)a2 + 4), &v70);
    v15 = v17;
    if ( v17 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x15D,
        (unsigned int)"onecore\\printscan\\appxpackaging\\production\\src\\bundlemanifestwriter.cpp",
        (const char *)(unsigned int)v17,
        v66);
      operator delete(v12, v18);
      goto LABEL_16;
    }
    v19 = Appx::Packaging::Xml::MXAttributes::AddAttribute(
            v6,
            &LocaleName,
            L"Architecture",
            (const unsigned __int16 *)v70);
    v15 = v19;
    if ( v19 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x161,
        (unsigned int)"onecore\\printscan\\appxpackaging\\production\\src\\bundlemanifestwriter.cpp",
        (const char *)(unsigned int)v19,
        v66);
      operator delete(v12, v20);
      goto LABEL_16;
    }
  }
  v21 = (const unsigned __int16 *)*((_QWORD *)a2 + 3);
  if ( v21 )
  {
    v22 = -1;
    do
      ++v22;
    while ( v21[v22] );
    if ( v22 )
    {
      v23 = Appx::Packaging::Xml::MXAttributes::AddAttribute(v6, &LocaleName, L"ResourceId", v21);
      v15 = v23;
      if ( v23 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x169,
          (unsigned int)"onecore\\printscan\\appxpackaging\\production\\src\\bundlemanifestwriter.cpp",
          (const char *)(unsigned int)v23,
          v66);
        operator delete(v12, v24);
        goto LABEL_16;
      }
    }
  }
  v25 = (const unsigned __int16 *)*((_QWORD *)a2 + 4);
  if ( v25 )
  {
    v26 = Appx::Packaging::Xml::MXAttributes::AddAttribute(v6, &LocaleName, L"FileName", v25);
    v15 = v26;
    if ( v26 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x171,
        (unsigned int)"onecore\\printscan\\appxpackaging\\production\\src\\bundlemanifestwriter.cpp",
        (const char *)(unsigned int)v26,
        v66);
      operator delete(v12, v27);
      goto LABEL_16;
    }
  }
  v28 = *((_QWORD *)a2 + 6);
  if ( v28 )
  {
    v29 = Common::UInt64::Encode(v28, v75, v14, (unsigned int *)&v70);
    v15 = v29;
    if ( v29 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x17D,
        (unsigned int)"onecore\\printscan\\appxpackaging\\production\\src\\bundlemanifestwriter.cpp",
        (const char *)(unsigned int)v29,
        v66);
      operator delete(v12, v30);
      goto LABEL_16;
    }
    v31 = Appx::Packaging::Xml::MXAttributes::AddAttribute(v6, &LocaleName, L"Offset", v75);
    v15 = v31;
    if ( v31 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x182,
        (unsigned int)"onecore\\printscan\\appxpackaging\\production\\src\\bundlemanifestwriter.cpp",
        (const char *)(unsigned int)v31,
        v66);
      operator delete(v12, v32);
      goto LABEL_16;
    }
  }
  v33 = *((_QWORD *)a2 + 5);
  if ( v33 && *((_QWORD *)a2 + 6) )
  {
    v34 = Common::UInt64::Encode(v33, v76, v14, (unsigned int *)&v70);
    v15 = v34;
    if ( v34 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x18D,
        (unsigned int)"onecore\\printscan\\appxpackaging\\production\\src\\bundlemanifestwriter.cpp",
        (const char *)(unsigned int)v34,
        v66);
      operator delete(v12, v35);
      goto LABEL_16;
    }
    v36 = Appx::Packaging::Xml::MXAttributes::AddAttribute(v6, &LocaleName, L"Size", v76);
    v15 = v36;
    if ( v36 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x192,
        (unsigned int)"onecore\\printscan\\appxpackaging\\production\\src\\bundlemanifestwriter.cpp",
        (const char *)(unsigned int)v36,
        v66);
      operator delete(v12, v37);
      goto LABEL_16;
    }
  }
  v38 = (const unsigned __int16 *)this[3];
  v39 = L"Package";
  v71 = L"Package";
  v40 = 0;
  v70 = 0;
  if ( *((_DWORD *)a2 + 20) )
  {
    v72 = L"b5";
    v38 = L"http://schemas.microsoft.com/appx/2019/bundle";
    ElementName = Appx::Packaging::BundleManifest::BundleManifestXmlWriter::GetElementName(
                    (Appx::Packaging::BundleManifest::BundleManifestXmlWriter *)this,
                    L"http://schemas.microsoft.com/appx/2019/bundle",
                    L"b5",
                    L"Package",
                    (const unsigned __int16 **)&v71,
                    (unsigned __int16 **)&v70);
    v15 = ElementName;
    if ( ElementName < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x19D,
        (unsigned int)"onecore\\printscan\\appxpackaging\\production\\src\\bundlemanifestwriter.cpp",
        (const char *)(unsigned int)ElementName,
        v67);
      operator delete(v70, v42);
      operator delete(v12, v43);
      goto LABEL_16;
    }
    v44 = Appx::Packaging::Xml::MXAttributes::AddAttribute(v6, &LocaleName, L"IsStub", L"true");
    v15 = v44;
    if ( v44 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x19E,
        (unsigned int)"onecore\\printscan\\appxpackaging\\production\\src\\bundlemanifestwriter.cpp",
        (const char *)(unsigned int)v44,
        v67);
      operator delete(v70, v45);
      operator delete(v12, v46);
      goto LABEL_16;
    }
    v39 = v71;
    v40 = v70;
  }
  else
  {
    v72 = 0;
  }
  started = Appx::Packaging::Xml::MXWriter::StartElement(this[1], v38, v39, v39, v6);
  v48 = started;
  if ( started < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1A1,
      (unsigned int)"onecore\\printscan\\appxpackaging\\production\\src\\bundlemanifestwriter.cpp",
      (const char *)(unsigned int)started,
      v68);
    operator delete(v40, v49);
    operator delete(v12, v50);
LABEL_51:
    v4 = v48;
    goto LABEL_62;
  }
  v51 = Appx::Packaging::BundleManifest::BundleManifestXmlWriter::WriteResourcesElement(
          v73,
          *((struct IAppxManifestQualifiedResourcesEnumerator **)a2 + 7),
          *((_DWORD *)a2 + 16) != 0,
          v38,
          v72);
  v48 = v51;
  if ( v51 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1A3,
      (unsigned int)"onecore\\printscan\\appxpackaging\\production\\src\\bundlemanifestwriter.cpp",
      (const char *)(unsigned int)v51,
      v69);
    operator delete(v40, v52);
    operator delete(v12, v53);
    goto LABEL_51;
  }
  v54 = v73;
  v55 = Appx::Packaging::BundleManifest::BundleManifestXmlWriter::WriteDependenciesElement(
          v73,
          *((struct IAppxManifestTargetDeviceFamiliesEnumerator **)a2 + 9));
  v56 = v55;
  if ( v55 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1A4,
      (unsigned int)"onecore\\printscan\\appxpackaging\\production\\src\\bundlemanifestwriter.cpp",
      (const char *)(unsigned int)v55,
      v69);
    operator delete(v40, v57);
    operator delete(v12, v58);
LABEL_58:
    v4 = v56;
    goto LABEL_62;
  }
  v59 = Appx::Packaging::Xml::MXWriter::EndElement(*((Appx::Packaging::Xml::MXWriter **)v54 + 1), v38, v39, v39);
  v56 = v59;
  if ( v59 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1A6,
      (unsigned int)"onecore\\printscan\\appxpackaging\\production\\src\\bundlemanifestwriter.cpp",
      (const char *)(unsigned int)v59,
      v69);
    operator delete(v40, v61);
    operator delete(v12, v62);
    goto LABEL_58;
  }
  operator delete(v40, v60);
  operator delete(v12, v63);
  Common::AutoPtrDeallocate<Appx::Packaging::Xml::MXAttributes>(v6);
  return 0;
}

```

## disassembly

```asm
0x1800f5190  mov     rax, rsp
0x1800f5193  push    rbp
0x1800f5194  push    rsi
0x1800f5195  push    rdi
0x1800f5196  push    r12
0x1800f5198  push    r13
0x1800f519a  push    r14
0x1800f519c  push    r15
0x1800f519e  lea     rbp, [rax-5Fh]
0x1800f51a2  sub     rsp, 0C0h
0x1800f51a9  mov     [rbp+57h+var_A0], 0FFFFFFFFFFFFFFFEh
0x1800f51b1  mov     [rax+18h], rbx
0x1800f51b5  mov     rax, cs:__security_cookie
0x1800f51bc  xor     rax, rsp
0x1800f51bf  mov     [rbp+57h+var_38], rax
0x1800f51c3  mov     r14, rdx
0x1800f51c6  mov     r13, rcx
0x1800f51c9  mov     [rbp+57h+var_A8], rcx
0x1800f51cd  xor     r15d, r15d
0x1800f51d0  cmp     [rdx+38h], r15
0x1800f51d4  jnz     short loc_1800F51F8
0x1800f51d6  mov     rcx, [rbp+5Fh]; this
0x1800f51da  mov     ebx, 80070057h
0x1800f51df  mov     r9d, ebx; char *
0x1800f51e2  lea     r8, aOnecorePrintsc_162; "onecore\\printscan\\appxpackaging\\prod"...
0x1800f51e9  mov     edx, 147h; void *
0x1800f51ee  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f51f3  jmp     loc_1800F57B8
0x1800f51f8  mov     [rbp+57h+var_C0], r15
0x1800f51fc  lea     rcx, [rbp+57h+var_C0]; struct Appx::Packaging::Xml::MXAttributes **
0x1800f5200  call    ?Create@MXAttributes@Xml@Packaging@Appx@@SAJPEAPEAV1234@@Z; Appx::Packaging::Xml::MXAttributes::Create(Appx::Packaging::Xml::MXAttributes * *)
0x1800f5205  mov     ebx, eax
0x1800f5207  mov     rsi, [rbp+57h+var_C0]
0x1800f520b  test    eax, eax
0x1800f520d  jns     short loc_1800F5216
0x1800f520f  mov     edx, 14Ah
0x1800f5214  jmp     short loc_1800F5265
0x1800f5216  mov     ecx, [r14]
0x1800f5219  mov     eax, r15d
0x1800f521c  lea     rdx, ?PackageTypeValues@Attribute@BundleManifest@Packaging@Appx@@3QBUPackageTypeTable@1234@B; Appx::Packaging::BundleManifest::Attribute::PackageTypeTable const near * const Appx::Packaging::BundleManifest::Attribute::PackageTypeValues
0x1800f5223  cmp     eax, 2
0x1800f5226  jnb     loc_1800F577B
0x1800f522c  mov     r9d, eax
0x1800f522f  add     r9, r9
0x1800f5232  cmp     [rdx+r9*8+8], ecx
0x1800f5237  jz      short loc_1800F523D
0x1800f5239  inc     eax
0x1800f523b  jmp     short loc_1800F5223
0x1800f523d  mov     r9, [rdx+r9*8]; unsigned __int16 *
0x1800f5241  lea     r8, ?PackageType@AttributeNameWithoutPrefix@BundleManifest@Packaging@Appx@@3QBGB; "Type"
0x1800f5248  lea     r12, LocaleName
0x1800f524f  mov     rdx, r12; unsigned __int16 *
0x1800f5252  mov     rcx, rsi; this
0x1800f5255  call    ?AddAttribute@MXAttributes@Xml@Packaging@Appx@@QEAAJPEBG00@Z; Appx::Packaging::Xml::MXAttributes::AddAttribute(ushort const *,ushort const *,ushort const *)
0x1800f525a  mov     ebx, eax
0x1800f525c  test    eax, eax
0x1800f525e  jns     short loc_1800F526D
0x1800f5260  mov     edx, 151h
0x1800f5265  mov     r9d, eax
0x1800f5268  jmp     loc_1800F57A0
0x1800f526d  mov     [rbp+57h+var_C0], r15
0x1800f5271  lea     r9, [rbp+57h+var_C0]; unsigned int
0x1800f5275  mov     edx, 4; unsigned __int64
0x1800f527a  mov     r8d, edx; unsigned int
0x1800f527d  mov     rcx, [r14+8]; this
0x1800f5281  call    ?ConvertVersionToString@Packaging@Appx@@YAJ_KKKPEAPEAG@Z; Appx::Packaging::ConvertVersionToString(unsigned __int64,ulong,ulong,ushort * *)
0x1800f5286  mov     ebx, eax
0x1800f5288  test    eax, eax
0x1800f528a  jns     short loc_1800F52B4
0x1800f528c  mov     rcx, [rbp+5Fh]; this
0x1800f5290  mov     r9d, eax; char *
0x1800f5293  lea     r8, aOnecorePrintsc_162; "onecore\\printscan\\appxpackaging\\prod"...
0x1800f529a  mov     edx, 154h; void *
0x1800f529f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f52a4  nop
0x1800f52a5  mov     rcx, [rbp+57h+var_C0]; void *
0x1800f52a9  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800f52ae  nop
0x1800f52af  jmp     loc_1800F57B0
0x1800f52b4  mov     rbx, [rbp+57h+var_C0]
0x1800f52b8  mov     r9, rbx; unsigned __int16 *
0x1800f52bb  lea     r8, ?Version@AttributeNameWithoutPrefix@BundleManifest@Packaging@Appx@@3QBGB; "Version"
0x1800f52c2  mov     rdx, r12; unsigned __int16 *
0x1800f52c5  mov     rcx, rsi; this
0x1800f52c8  call    ?AddAttribute@MXAttributes@Xml@Packaging@Appx@@QEAAJPEBG00@Z; Appx::Packaging::Xml::MXAttributes::AddAttribute(ushort const *,ushort const *,ushort const *)
0x1800f52cd  mov     edi, eax
0x1800f52cf  test    eax, eax
0x1800f52d1  jns     short loc_1800F52FC
0x1800f52d3  mov     rcx, [rbp+5Fh]; this
0x1800f52d7  mov     r9d, eax; char *
0x1800f52da  lea     r8, aOnecorePrintsc_162; "onecore\\printscan\\appxpackaging\\prod"...
0x1800f52e1  mov     edx, 158h; void *
0x1800f52e6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f52eb  nop
0x1800f52ec  mov     rcx, rbx; void *
0x1800f52ef  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800f52f4  nop
0x1800f52f5  mov     ebx, edi
0x1800f52f7  jmp     loc_1800F57B0
0x1800f52fc  cmp     [r14], r15d
0x1800f52ff  jnz     short loc_1800F537F
0x1800f5301  mov     [rbp+57h+var_C0], r15
0x1800f5305  lea     rdx, [rbp+57h+var_C0]
0x1800f5309  mov     ecx, [r14+10h]
0x1800f530d  call    ?ConvertPackageArchitectureToString@@YAJUAppxPackageArchitecture@Types@Manifest@Packaging@Appx@@PEAPEBG@Z; ConvertPackageArchitectureToString(Appx::Packaging::Manifest::Types::AppxPackageArchitecture,ushort const * *)
0x1800f5312  mov     edi, eax
0x1800f5314  test    eax, eax
0x1800f5316  jns     short loc_1800F533C
0x1800f5318  mov     rcx, [rbp+5Fh]; this
0x1800f531c  mov     r9d, eax; char *
0x1800f531f  lea     r8, aOnecorePrintsc_162; "onecore\\printscan\\appxpackaging\\prod"...
0x1800f5326  mov     edx, 15Dh; void *
0x1800f532b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f5330  nop
0x1800f5331  mov     rcx, rbx; void *
0x1800f5334  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800f5339  nop
0x1800f533a  jmp     short loc_1800F52F5
0x1800f533c  mov     r9, [rbp+57h+var_C0]; unsigned __int16 *
0x1800f5340  lea     r8, ?Architecture@AttributeNameWithoutPrefix@BundleManifest@Packaging@Appx@@3QBGB; "Architecture"
0x1800f5347  mov     rdx, r12; unsigned __int16 *
0x1800f534a  mov     rcx, rsi; this
0x1800f534d  call    ?AddAttribute@MXAttributes@Xml@Packaging@Appx@@QEAAJPEBG00@Z; Appx::Packaging::Xml::MXAttributes::AddAttribute(ushort const *,ushort const *,ushort const *)
0x1800f5352  mov     edi, eax
0x1800f5354  test    eax, eax
0x1800f5356  jns     short loc_1800F537F
0x1800f5358  mov     rcx, [rbp+5Fh]; this
0x1800f535c  mov     r9d, eax; char *
0x1800f535f  lea     r8, aOnecorePrintsc_162; "onecore\\printscan\\appxpackaging\\prod"...
0x1800f5366  mov     edx, 161h; void *
0x1800f536b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f5370  nop
0x1800f5371  mov     rcx, rbx; void *
0x1800f5374  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800f5379  nop
0x1800f537a  jmp     loc_1800F52F5
0x1800f537f  mov     r9, [r14+18h]; unsigned __int16 *
0x1800f5383  test    r9, r9
0x1800f5386  jz      short loc_1800F53DA
0x1800f5388  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800f538c  inc     rax
0x1800f538f  cmp     [r9+rax*2], r15w
0x1800f5394  jnz     short loc_1800F538C
0x1800f5396  test    rax, rax
0x1800f5399  jz      short loc_1800F53DA
0x1800f539b  lea     r8, ?ResourceId@AttributeNameWithoutPrefix@BundleManifest@Packaging@Appx@@3QBGB; "ResourceId"
0x1800f53a2  mov     rdx, r12; unsigned __int16 *
0x1800f53a5  mov     rcx, rsi; this
0x1800f53a8  call    ?AddAttribute@MXAttributes@Xml@Packaging@Appx@@QEAAJPEBG00@Z; Appx::Packaging::Xml::MXAttributes::AddAttribute(ushort const *,ushort const *,ushort const *)
0x1800f53ad  mov     edi, eax
0x1800f53af  test    eax, eax
0x1800f53b1  jns     short loc_1800F53DA
0x1800f53b3  mov     rcx, [rbp+5Fh]; this
0x1800f53b7  mov     r9d, eax; char *
0x1800f53ba  lea     r8, aOnecorePrintsc_162; "onecore\\printscan\\appxpackaging\\prod"...
0x1800f53c1  mov     edx, 169h; void *
0x1800f53c6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f53cb  nop
0x1800f53cc  mov     rcx, rbx; void *
0x1800f53cf  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800f53d4  nop
0x1800f53d5  jmp     loc_1800F52F5
0x1800f53da  mov     r9, [r14+20h]; unsigned __int16 *
0x1800f53de  test    r9, r9
0x1800f53e1  jz      short loc_1800F5422
0x1800f53e3  lea     r8, ?FileName@AttributeNameWithoutPrefix@BundleManifest@Packaging@Appx@@3QBGB; "FileName"
0x1800f53ea  mov     rdx, r12; unsigned __int16 *
0x1800f53ed  mov     rcx, rsi; this
0x1800f53f0  call    ?AddAttribute@MXAttributes@Xml@Packaging@Appx@@QEAAJPEBG00@Z; Appx::Packaging::Xml::MXAttributes::AddAttribute(ushort const *,ushort const *,ushort const *)
0x1800f53f5  mov     edi, eax
0x1800f53f7  test    eax, eax
0x1800f53f9  jns     short loc_1800F5422
0x1800f53fb  mov     rcx, [rbp+5Fh]; this
0x1800f53ff  mov     r9d, eax; char *
0x1800f5402  lea     r8, aOnecorePrintsc_162; "onecore\\printscan\\appxpackaging\\prod"...
0x1800f5409  mov     edx, 171h; void *
0x1800f540e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f5413  nop
0x1800f5414  mov     rcx, rbx; void *
0x1800f5417  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800f541c  nop
0x1800f541d  jmp     loc_1800F52F5
0x1800f5422  mov     rcx, [r14+30h]; unsigned __int64
0x1800f5426  test    rcx, rcx
0x1800f5429  jz      short loc_1800F54A8
0x1800f542b  lea     r9, [rbp+57h+var_C0]; unsigned int *
0x1800f542f  lea     rdx, [rbp+57h+var_98]; unsigned __int16 *
0x1800f5433  call    ?Encode@UInt64@Common@@SAJ_KPEAGKPEAK@Z; Common::UInt64::Encode(unsigned __int64,ushort *,ulong,ulong *)
0x1800f5438  mov     edi, eax
0x1800f543a  test    eax, eax
0x1800f543c  jns     short loc_1800F5465
0x1800f543e  mov     rcx, [rbp+5Fh]; this
0x1800f5442  mov     r9d, eax; char *
0x1800f5445  lea     r8, aOnecorePrintsc_162; "onecore\\printscan\\appxpackaging\\prod"...
0x1800f544c  mov     edx, 17Dh; void *
0x1800f5451  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f5456  nop
0x1800f5457  mov     rcx, rbx; void *
0x1800f545a  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800f545f  nop
0x1800f5460  jmp     loc_1800F52F5
0x1800f5465  lea     r9, [rbp+57h+var_98]; unsigned __int16 *
0x1800f5469  lea     r8, ?Offset@AttributeNameWithoutPrefix@BundleManifest@Packaging@Appx@@3QBGB; "Offset"
0x1800f5470  mov     rdx, r12; unsigned __int16 *
0x1800f5473  mov     rcx, rsi; this
0x1800f5476  call    ?AddAttribute@MXAttributes@Xml@Packaging@Appx@@QEAAJPEBG00@Z; Appx::Packaging::Xml::MXAttributes::AddAttribute(ushort const *,ushort const *,ushort const *)
0x1800f547b  mov     edi, eax
0x1800f547d  test    eax, eax
0x1800f547f  jns     short loc_1800F54A8
0x1800f5481  mov     rcx, [rbp+5Fh]; this
0x1800f5485  mov     r9d, eax; char *
0x1800f5488  lea     r8, aOnecorePrintsc_162; "onecore\\printscan\\appxpackaging\\prod"...
0x1800f548f  mov     edx, 182h; void *
0x1800f5494  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f5499  nop
0x1800f549a  mov     rcx, rbx; void *
0x1800f549d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800f54a2  nop
0x1800f54a3  jmp     loc_1800F52F5
0x1800f54a8  mov     rcx, [r14+28h]; unsigned __int64
0x1800f54ac  test    rcx, rcx
0x1800f54af  jz      loc_1800F5538
0x1800f54b5  cmp     [r14+30h], r15
0x1800f54b9  jbe     short loc_1800F5538
0x1800f54bb  lea     r9, [rbp+57h+var_C0]; unsigned int *
0x1800f54bf  lea     rdx, [rbp+57h+var_68]; unsigned __int16 *
0x1800f54c3  call    ?Encode@UInt64@Common@@SAJ_KPEAGKPEAK@Z; Common::UInt64::Encode(unsigned __int64,ushort *,ulong,ulong *)
0x1800f54c8  mov     edi, eax
0x1800f54ca  test    eax, eax
0x1800f54cc  jns     short loc_1800F54F5
0x1800f54ce  mov     rcx, [rbp+5Fh]; this
0x1800f54d2  mov     r9d, eax; char *
0x1800f54d5  lea     r8, aOnecorePrintsc_162; "onecore\\printscan\\appxpackaging\\prod"...
0x1800f54dc  mov     edx, 18Dh; void *
0x1800f54e1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f54e6  nop
0x1800f54e7  mov     rcx, rbx; void *
0x1800f54ea  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800f54ef  nop
0x1800f54f0  jmp     loc_1800F52F5
0x1800f54f5  lea     r9, [rbp+57h+var_68]; unsigned __int16 *
0x1800f54f9  lea     r8, ?Size@AttributeNameWithoutPrefix@BundleManifest@Packaging@Appx@@3QBGB; "Size"
0x1800f5500  mov     rdx, r12; unsigned __int16 *
0x1800f5503  mov     rcx, rsi; this
0x1800f5506  call    ?AddAttribute@MXAttributes@Xml@Packaging@Appx@@QEAAJPEBG00@Z; Appx::Packaging::Xml::MXAttributes::AddAttribute(ushort const *,ushort const *,ushort const *)
0x1800f550b  mov     edi, eax
0x1800f550d  test    eax, eax
0x1800f550f  jns     short loc_1800F5538
0x1800f5511  mov     rcx, [rbp+5Fh]; this
0x1800f5515  mov     r9d, eax; char *
0x1800f5518  lea     r8, aOnecorePrintsc_162; "onecore\\printscan\\appxpackaging\\prod"...
0x1800f551f  mov     edx, 192h; void *
0x1800f5524  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f5529  nop
0x1800f552a  mov     rcx, rbx; void *
0x1800f552d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800f5532  nop
0x1800f5533  jmp     loc_1800F52F5
0x1800f5538  mov     r12, [r13+18h]
0x1800f553c  lea     r15, ?Package@ElementNameWithoutPrefix@BundleManifest@Packaging@Appx@@3QBGB; "Package"
0x1800f5543  mov     [rbp+57h+var_B8], r15
0x1800f5547  xor     edi, edi
0x1800f5549  mov     [rbp+57h+var_C0], rdi
0x1800f554d  cmp     [r14+50h], edi
0x1800f5551  jz      loc_1800F5621
0x1800f5557  lea     rax, [rbp+57h+var_C0]
0x1800f555b  mov     [rsp+28h], rax; unsigned __int16 **
0x1800f5560  lea     rax, [rbp+57h+var_B8]
0x1800f5564  mov     [rsp+0F0h+var_D0], rax; int
0x1800f5569  mov     r9, r15; unsigned __int16 *
0x1800f556c  lea     rax, ?Namespace2019Alias@BundleManifest@Packaging@Appx@@3QBGB; "b5"
0x1800f5573  mov     [rbp+57h+var_B0], rax
0x1800f5577  mov     r8, rax; unsigned __int16 *
0x1800f557a  lea     r12, ?Namespace2019@BundleManifest@Packaging@Appx@@3QBGB; "http://schemas.microsoft.com/appx/2019/"...
0x1800f5581  mov     rdx, r12; unsigned __int16 *
0x1800f5584  mov     rcx, r13; this
0x1800f5587  call    ?GetElementName@BundleManifestXmlWriter@BundleManifest@Packaging@Appx@@AEAAJPEBG00PEAPEBGPEAPEAG@Z; Appx::Packaging::BundleManifest::BundleManifestXmlWriter::GetElementName(ushort const *,ushort const *,ushort const *,ushort const * *,ushort * *)
0x1800f558c  mov     edi, eax
0x1800f558e  test    eax, eax
0x1800f5590  jns     short loc_1800F55C3
0x1800f5592  mov     rcx, [rbp+5Fh]; this
0x1800f5596  mov     r9d, eax; char *
0x1800f5599  lea     r8, aOnecorePrintsc_162; "onecore\\printscan\\appxpackaging\\prod"...
0x1800f55a0  mov     edx, 19Dh; void *
0x1800f55a5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f55aa  nop
0x1800f55ab  mov     rcx, [rbp+57h+var_C0]; void *
0x1800f55af  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800f55b4  nop
0x1800f55b5  mov     rcx, rbx; void *
0x1800f55b8  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800f55bd  nop
0x1800f55be  jmp     loc_1800F52F5
0x1800f55c3  lea     r9, aTrue; "true"
0x1800f55ca  lea     r8, ?IsStub@AttributeNameWithoutPrefix@BundleManifest@Packaging@Appx@@3QBGB; "IsStub"
0x1800f55d1  lea     rdx, LocaleName; unsigned __int16 *
0x1800f55d8  mov     rcx, rsi; this
0x1800f55db  call    ?AddAttribute@MXAttributes@Xml@Packaging@Appx@@QEAAJPEBG00@Z; Appx::Packaging::Xml::MXAttributes::AddAttribute(ushort const *,ushort const *,ushort const *)
0x1800f55e0  mov     edi, eax
0x1800f55e2  test    eax, eax
  ... truncated ...
```
