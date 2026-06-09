# MsixPackage::Provisioning::Library::MsixProvisioningRequest::GetMainPackage(MsixPackage::Provisioning::Library::CandidatePackages *,MsixPackage::Provisioning::Library::PackageMonikerToPayload * *)

- ea: `0x180054e90`
- end: `0x180055cf1`
- name: `?GetMainPackage@MsixProvisioningRequest@Library@Provisioning@MsixPackage@@AEAAJPEAVCandidatePackages@234@PEAPEAVPackageMonikerToPayload@234@@Z`
- size: `3681`
- prototype: `__int64 __fastcall(MsixPackage::Provisioning::Library::MsixProvisioningRequest *__hidden this, struct MsixPackage::Provisioning::Library::CandidatePackages *, struct MsixPackage::Provisioning::Library::PackageMonikerToPayload **)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, service_task, installer_update`

## callers

- `0x180053b30`

## callees

- `0x18000d3dc`
- `0x180018c78`
- `0x18003c2c0`
- `0x18003d4ec`
- `0x1800415f8`
- `0x180041900`
- `0x180054e90`
- `0x180070010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180054fa5`
- `msvcrt!??3@YAXPEAX@Z` at `0x180055839`
- `msvcrt!??3@YAXPEAX@Z` at `0x180054fa5`
- `msvcrt!??3@YAXPEAX@Z` at `0x180055839`

## string_xrefs

- `0x18005581e`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningutils.cpp`
- `0x180054f16`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningrequest.cpp`
- `0x1800551f3`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningrequest.cpp`
- `0x1800552ba`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningrequest.cpp`
- `0x180055399`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningrequest.cpp`
- `0x18005545e`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningrequest.cpp`
- `0x180055524`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningrequest.cpp`
- `0x1800555e9`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningrequest.cpp`
- `0x1800556a5`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningrequest.cpp`
- `0x18005576a`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningrequest.cpp`
- `0x180055864`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningrequest.cpp`
- `0x18005592b`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningrequest.cpp`
- `0x180055bbc`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningrequest.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=18
__int64 __fastcall MsixPackage::Provisioning::Library::MsixProvisioningRequest::GetMainPackage(
        MsixPackage::Provisioning::Library::MsixProvisioningRequest *this,
        struct MsixPackage::Provisioning::Library::CandidatePackages *a2,
        struct MsixPackage::Provisioning::Library::PackageMonikerToPayload **a3)
{
  struct MsixPackage::Provisioning::Library::CandidatePackages *v3; // r9
  struct MsixPackage::Provisioning::Library::CandidatePackages *v4; // r14
  struct MsixPackage::Provisioning::Library::CandidatePackages *v5; // r12
  struct MsixPackage::Provisioning::Library::CandidatePackages *v6; // r15
  struct MsixPackage::Provisioning::Library::CandidatePackages *v7; // r13
  struct MsixPackage::Provisioning::Library::CandidatePackages *v8; // rbx
  struct MsixPackage::Provisioning::Library::CandidatePackages *v9; // rsi
  unsigned int v10; // esi
  unsigned int v12; // ecx
  int v13; // eax
  struct MsixPackage::Provisioning::Library::CandidatePackages *v14; // rdi
  char *v15; // rax
  int PackageIdByBasicFullName; // eax
  int v17; // edx
  struct MsixPackage::Provisioning::Library::CandidatePackages *v18; // rcx
  MsixPackage::Provisioning::Library::MsixProvisioningRequest *v19; // rdx
  __int64 v20; // rcx
  _QWORD *v21; // rax
  _QWORD *v22; // rax
  _QWORD *v23; // rax
  _QWORD *v24; // rax
  _QWORD *v25; // rax
  const char *v26; // rax
  _QWORD *v27; // rax
  unsigned int v28; // r8d
  __int64 v29; // rax
  struct MsixPackage::Provisioning::Library::CandidatePackages *v30; // rcx
  struct MsixPackage::Provisioning::Library::CandidatePackages *v31; // rcx
  int v32; // edx
  int v33; // edx
  int v34; // edx
  int v35; // edx
  int v36; // edx
  int v37; // edx
  const wchar_t *v38; // rax
  int v39; // [rsp+28h] [rbp-69h]
  char *v40; // [rsp+30h] [rbp-61h]
  struct MsixPackage::Provisioning::Library::CandidatePackages *v41; // [rsp+48h] [rbp-49h]
  unsigned int v42; // [rsp+50h] [rbp-41h]
  unsigned int v43; // [rsp+50h] [rbp-41h]
  int v44; // [rsp+50h] [rbp-41h]
  char *v45; // [rsp+60h] [rbp-31h]
  void *v46; // [rsp+68h] [rbp-29h] BYREF
  char *v47; // [rsp+70h] [rbp-21h] BYREF
  struct MsixPackage::Provisioning::Library::CandidatePackages *v48; // [rsp+78h] [rbp-19h]
  struct MsixPackage::Provisioning::Library::CandidatePackages *v49; // [rsp+80h] [rbp-11h]
  struct MsixPackage::Provisioning::Library::CandidatePackages *v50; // [rsp+88h] [rbp-9h]
  struct MsixPackage::Provisioning::Library::CandidatePackages *v51; // [rsp+90h] [rbp-1h]
  struct MsixPackage::Provisioning::Library::CandidatePackages *v52; // [rsp+98h] [rbp+7h]
  struct MsixPackage::Provisioning::Library::CandidatePackages *v53; // [rsp+A0h] [rbp+Fh]
  wil::details::in1diag3 *retaddr; // [rsp+F0h] [rbp+5Fh]
  struct MsixPackage::Provisioning::Library::CandidatePackages *v56; // [rsp+100h] [rbp+6Fh] BYREF
  struct MsixPackage::Provisioning::Library::PackageMonikerToPayload **v57; // [rsp+108h] [rbp+77h]
  char *v58; // [rsp+110h] [rbp+7Fh] BYREF

  v57 = a3;
  v56 = a2;
  v3 = a2;
  v4 = 0;
  v53 = 0;
  v5 = 0;
  v51 = 0;
  v6 = 0;
  v52 = 0;
  v7 = 0;
  v49 = 0;
  v41 = 0;
  v48 = 0;
  v8 = 0;
  v50 = 0;
  v9 = 0;
  *a3 = 0;
  if ( !(unsigned int)((__int64)(*((_QWORD *)a2 + 3) - *((_QWORD *)a2 + 2)) >> 3) )
  {
    v10 = -1051262718;
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0xFE,
      (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningrequest.cpp",
      (const char *)0xC1570102LL,
      (int)"Main package not found.",
      v40);
    return v10;
  }
  v12 = 0;
  LODWORD(v58) = 0;
  do
  {
    v47 = 0;
    v13 = MsixPackage::Provisioning::Library::CContainer<MsixPackage::Provisioning::Library::MsixPackageAdapter,MsixPackage::Provisioning::Library::MsixAdapterCollection>::Item(
            v3,
            v12,
            &v47);
    v42 = v13;
    if ( v13 < 0 )
    {
      LODWORD(v40) = (_DWORD)v58;
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x107,
        (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningrequest.cpp",
        (const char *)(unsigned int)v13,
        (int)"Failed to get item at index %d.",
        v40);
      if ( v47 )
        (*(void (__fastcall **)(char *))(*(_QWORD *)v47 + 16LL))(v47);
      if ( v8 )
        (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::CandidatePackages *))(*(_QWORD *)v8 + 16LL))(v8);
      if ( v41 )
        (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::CandidatePackages *))(*(_QWORD *)v41 + 16LL))(v41);
      if ( v7 )
        (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::CandidatePackages *))(*(_QWORD *)v7 + 16LL))(v7);
      if ( v6 )
        (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::CandidatePackages *))(*(_QWORD *)v6 + 16LL))(v6);
      if ( v5 )
        (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::CandidatePackages *))(*(_QWORD *)v5 + 16LL))(v5);
      if ( v4 )
        (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::CandidatePackages *))(*(_QWORD *)v4 + 16LL))(v4);
      return v42;
    }
    v14 = (struct MsixPackage::Provisioning::Library::CandidatePackages *)v47;
    v15 = v47 + 56;
    v45 = v47 + 56;
    if ( *((_QWORD *)v47 + 10) >= 8u )
    {
      v15 = *(char **)v15;
      v45 = v15;
    }
    v46 = 0;
    PackageIdByBasicFullName = MsixPackage::Provisioning::Library::MsixProvisioningContext::GetPackageIdByBasicFullName(
                                 v15,
                                 &v46);
    v43 = PackageIdByBasicFullName;
    if ( PackageIdByBasicFullName < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x5F,
        (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningutils.cpp",
        (const char *)(unsigned int)PackageIdByBasicFullName,
        v39);
      if ( v46 )
        operator delete(v46);
      v10 = v43;
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x10E,
        (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningrequest.cpp",
        (const char *)v43,
        (int)"Failed while resolving architecture from package moniker %ws",
        v45);
      if ( v14 )
        (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::CandidatePackages *))(*(_QWORD *)v14 + 16LL))(v14);
      if ( v8 )
        (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::CandidatePackages *))(*(_QWORD *)v8 + 16LL))(v8);
      if ( v41 )
        (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::CandidatePackages *))(*(_QWORD *)v41 + 16LL))(v41);
      if ( v7 )
        (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::CandidatePackages *))(*(_QWORD *)v7 + 16LL))(v7);
      if ( v6 )
        (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::CandidatePackages *))(*(_QWORD *)v6 + 16LL))(v6);
      if ( v5 )
        (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::CandidatePackages *))(*(_QWORD *)v5 + 16LL))(v5);
      if ( v4 )
        (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::CandidatePackages *))(*(_QWORD *)v4 + 16LL))(v4);
      return v10;
    }
    v17 = *((_DWORD *)v46 + 1);
    v44 = v17;
    if ( v46 )
    {
      operator delete(v46);
      v17 = v44;
    }
    switch ( v17 )
    {
      case 0:
        if ( !v4 )
        {
          v4 = v14;
          v53 = v14;
          if ( v14 )
            (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::CandidatePackages *))(*(_QWORD *)v14 + 8LL))(v14);
          goto LABEL_40;
        }
        v27 = (_QWORD *)((char *)v4 + 56);
        if ( *((_QWORD *)v4 + 10) >= 8u )
          v27 = (_QWORD *)*v27;
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          (void *)0x126,
          (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningrequest.cpp",
          (const char *)0xC1570109LL,
          (int)"Main packages %ws and %ws have the same architecture",
          v45,
          v27);
        if ( v14 )
          (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::CandidatePackages *))(*(_QWORD *)v14 + 16LL))(v14);
        if ( v8 )
          (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::CandidatePackages *))(*(_QWORD *)v8 + 16LL))(v8);
        if ( v41 )
          (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::CandidatePackages *))(*(_QWORD *)v41 + 16LL))(v41);
        if ( v7 )
          (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::CandidatePackages *))(*(_QWORD *)v7 + 16LL))(v7);
        if ( v6 )
          (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::CandidatePackages *))(*(_QWORD *)v6 + 16LL))(v6);
        if ( v5 )
          (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::CandidatePackages *))(*(_QWORD *)v5 + 16LL))(v5);
        goto LABEL_168;
      case 5:
        if ( v6 )
        {
          v25 = (_QWORD *)((char *)v6 + 56);
          if ( *((_QWORD *)v6 + 10) >= 8u )
            v25 = (_QWORD *)*v25;
          wil::details::in1diag3::Return_HrMsg(
            retaddr,
            (void *)0x13E,
            (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningrequest.cpp",
            (const char *)0xC1570109LL,
            (int)"Main packages %ws and %ws have the same architecture",
            v45,
            v25);
          if ( v14 )
            (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::CandidatePackages *))(*(_QWORD *)v14 + 16LL))(v14);
          if ( v8 )
            (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::CandidatePackages *))(*(_QWORD *)v8 + 16LL))(v8);
          if ( v41 )
            (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::CandidatePackages *))(*(_QWORD *)v41 + 16LL))(v41);
          if ( v7 )
            (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::CandidatePackages *))(*(_QWORD *)v7 + 16LL))(v7);
          (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::CandidatePackages *))(*(_QWORD *)v6 + 16LL))(v6);
          if ( v5 )
            (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::CandidatePackages *))(*(_QWORD *)v5 + 16LL))(v5);
          goto LABEL_72;
        }
        v6 = v14;
        v52 = v14;
        if ( v14 )
          (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::CandidatePackages *))(*(_QWORD *)v14 + 8LL))(v14);
        goto LABEL_40;
      case 9:
        if ( !v5 )
        {
          v5 = v14;
          v51 = v14;
          if ( v14 )
            (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::CandidatePackages *))(*(_QWORD *)v14 + 8LL))(v14);
LABEL_40:
          v18 = v14;
          goto LABEL_41;
        }
        v24 = (_QWORD *)((char *)v5 + 56);
        if ( *((_QWORD *)v5 + 10) >= 8u )
          v24 = (_QWORD *)*v24;
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          (void *)0x132,
          (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningrequest.cpp",
          (const char *)0xC1570109LL,
          (int)"Main packages %ws and %ws have the same architecture",
          v45,
          v24);
        if ( v14 )
          (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::CandidatePackages *))(*(_QWORD *)v14 + 16LL))(v14);
        if ( v8 )
          (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::CandidatePackages *))(*(_QWORD *)v8 + 16LL))(v8);
        if ( v41 )
          (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::CandidatePackages *))(*(_QWORD *)v41 + 16LL))(v41);
        if ( v7 )
          (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::CandidatePackages *))(*(_QWORD *)v7 + 16LL))(v7);
        if ( v6 )
          (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::CandidatePackages *))(*(_QWORD *)v6 + 16LL))(v6);
LABEL_71:
        (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::CandidatePackages *))(*(_QWORD *)v5 + 16LL))(v5);
LABEL_72:
        if ( !v4 )
          return 3243704585LL;
LABEL_168:
        (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::CandidatePackages *))(*(_QWORD *)v4 + 16LL))(v4);
        return 3243704585LL;
      case 11:
        if ( v8 )
        {
          v23 = (_QWORD *)((char *)v8 + 56);
          if ( *((_QWORD *)v8 + 10) >= 8u )
            v23 = (_QWORD *)*v23;
          wil::details::in1diag3::Return_HrMsg(
            retaddr,
            (void *)0x11A,
            (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningrequest.cpp",
            (const char *)0xC1570109LL,
            (int)"Main packages %ws and %ws have the same architecture",
            v45,
            v23);
          if ( v14 )
            (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::CandidatePackages *))(*(_QWORD *)v14 + 16LL))(v14);
          (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::CandidatePackages *))(*(_QWORD *)v8 + 16LL))(v8);
          if ( v41 )
            (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::CandidatePackages *))(*(_QWORD *)v41 + 16LL))(v41);
          if ( v7 )
            (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::CandidatePackages *))(*(_QWORD *)v7 + 16LL))(v7);
          if ( v6 )
            (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::CandidatePackages *))(*(_QWORD *)v6 + 16LL))(v6);
          if ( v5 )
            (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::CandidatePackages *))(*(_QWORD *)v5 + 16LL))(v5);
          goto LABEL_72;
        }
        v8 = v14;
        v50 = v14;
        if ( v14 )
          (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::CandidatePackages *))(*(_QWORD *)v14 + 8LL))(v14);
        v18 = v14;
        goto LABEL_41;
      case 12:
        if ( v7 )
        {
          v22 = (_QWORD *)((char *)v7 + 56);
          if ( *((_QWORD *)v7 + 10) >= 8u )
            v22 = (_QWORD *)*v22;
          wil::details::in1diag3::Return_HrMsg(
            retaddr,
            (void *)0x14A,
            (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningrequest.cpp",
            (const char *)0xC1570109LL,
            (int)"Main packages %ws and %ws have the same architecture",
            v45,
            v22);
          if ( v14 )
            (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::CandidatePackages *))(*(_QWORD *)v14 + 16LL))(v14);
          if ( v8 )
            (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::CandidatePackages *))(*(_QWORD *)v8 + 16LL))(v8);
          if ( v41 )
            (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::CandidatePackages *))(*(_QWORD *)v41 + 16LL))(v41);
          (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::CandidatePackages *))(*(_QWORD *)v7 + 16LL))(v7);
          if ( v6 )
            (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::CandidatePackages *))(*(_QWORD *)v6 + 16LL))(v6);
          if ( v5 )
            (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::CandidatePackages *))(*(_QWORD *)v5 + 16LL))(v5);
          goto LABEL_72;
        }
        v7 = v14;
        v49 = v14;
        if ( v14 )
          (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::CandidatePackages *))(*(_QWORD *)v14 + 8LL))(v14);
        goto LABEL_40;
    }
    if ( v17 != 14 )
    {
      LODWORD(v40) = v17;
      v10 = -2147024809;
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x162,
        (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningrequest.cpp",
        (const char *)0x80070057LL,
        (int)"Unsupported package architecture %d in moniker  %ws",
        v40,
        v45);
      if ( v14 )
        (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::CandidatePackages *))(*(_QWORD *)v14 + 16LL))(v14);
      if ( v8 )
        (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::CandidatePackages *))(*(_QWORD *)v8 + 16LL))(v8);
      if ( v41 )
        (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::CandidatePackages *))(*(_QWORD *)v41 + 16LL))(v41);
      if ( v7 )
        (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::CandidatePackages *))(*(_QWORD *)v7 + 16LL))(v7);
      if ( v6 )
        (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::CandidatePackages *))(*(_QWORD *)v6 + 16LL))(v6);
      if ( v5 )
        (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::CandidatePackages *))(*(_QWORD *)v5 + 16LL))(v5);
      if ( v4 )
        (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::CandidatePackages *))(*(_QWORD *)v4 + 16LL))(v4);
      return v10;
    }
    if ( v41 )
    {
      v21 = (_QWORD *)((char *)v41 + 56);
      if ( *((_QWORD *)v41 + 10) >= 8u )
        v21 = (_QWORD *)*v21;
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x156,
        (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningrequest.cpp",
        (const char *)0xC1570109LL,
        (int)"Main packages %ws and %ws have the same architecture",
        v45,
        v21);
      if ( v14 )
        (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::CandidatePackages *))(*(_QWORD *)v14 + 16LL))(v14);
      if ( v8 )
        (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::CandidatePackages *))(*(_QWORD *)v8 + 16LL))(v8);
      (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::CandidatePackages *))(*(_QWORD *)v41 + 16LL))(v41);
      if ( v7 )
        (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::CandidatePackages *))(*(_QWORD *)v7 + 16LL))(v7);
      if ( v6 )
        (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::CandidatePackages *))(*(_QWORD *)v6 + 16LL))(v6);
      if ( v5 )
        goto LABEL_71;
      goto LABEL_72;
    }
    v18 = v14;
    v41 = v14;
    v48 = v14;
    if ( v14 )
    {
      (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::CandidatePackages *))(*(_QWORD *)v14 + 8LL))(v14);
      v18 = v14;
    }
LABEL_41:
    if ( v18 )
      (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::CandidatePackages *))(*(_QWORD *)v14 + 16LL))(v14);
    v12 = (_DWORD)v58 + 1;
    LODWORD(v58) = v12;
    v3 = v56;
  }
  while ( v12 < (unsigned int)((__int64)(*((_QWORD *)v56 + 3) - *((_QWORD *)v56 + 2)) >> 3) );
  if ( !v8 )
    goto LABEL_50;
  if ( v4 || v5 || v6 || v7 )
  {
    v26 = (char *)v8 + 56;
    if ( *((_QWORD *)v8 + 10) >= 8u )
      v26 = *(const char **)v26;
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x16F,
      (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningrequest.cpp",
      (const char *)0xC1570109LL,
      (int)"Neutral main packages %ws cannot co-exist with a non-neutral main package",
      v26);
    (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::CandidatePackages *))(*(_QWORD *)v8 + 16LL))(v8);
    if ( v41 )
      (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::CandidatePackages *))(*(_QWORD *)v41 + 16LL))(v41);
    if ( v7 )
      (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::CandidatePackages *))(*(_QWORD *)v7 + 16LL))(v7);
    if ( v6 )
      (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::CandidatePackages *))(*(_QWORD *)v6 + 16LL))(v6);
    if ( v5 )
      (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::CandidatePackages *))(*(_QWORD *)v5 + 16LL))(v5);
    if ( v4 )
      (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::CandidatePackages *))(*(_QWORD *)v4 + 16LL))(v4);
    return 3243704585LL;
  }
  v9 = v8;
  (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::CandidatePackages *))(*(_QWORD *)v8 + 8LL))(v8);
LABEL_50:
  v19 = this;
  v20 = *(unsigned int *)(*((_QWORD *)this + 2) + 552LL);
  switch ( (_DWORD)v20 )
  {
    case 0:
      if ( v4 )
        goto LABEL_217;
      goto LABEL_221;
    case 5:
      if ( !v6 )
        goto LABEL_221;
      v56 = v9;
      v9 = v6;
      goto LABEL_207;
    case 9:
      if ( !v5 )
      {
        if ( !v4 )
          goto LABEL_221;
LABEL_217:
        v31 = v9;
        v9 = v4;
        v56 = v31;
        v30 = v4;
        v29 = *(_QWORD *)v4;
        goto LABEL_218;
      }
      goto LABEL_205;
  }
  if ( (_DWORD)v20 != 12 )
    goto LABEL_221;
  if ( v7 )
  {
    v56 = v9;
    v9 = v7;
    v29 = *(_QWORD *)v7;
    v30 = v7;
    goto LABEL_218;
  }
  if ( v41 )
  {
    v56 = v9;
    v9 = v41;
    v29 = *(_QWORD *)v41;
    v30 = v41;
    goto LABEL_218;
  }
  if ( v6 )
  {
    v56 = v9;
    v9 = v6;
LABEL_207:
    v29 = *(_QWORD *)v6;
    v30 = v6;
    goto LABEL_218;
  }
  if ( v5 )
  {
    v28 = *(_DWORD *)Feature_x64StoreAppsOnArm64__descriptor;
    if ( (*(_DWORD *)Feature_x64StoreAppsOnArm64__descriptor & 4) == 0 )
    {
      v58 = *(char **)wil::details::FeatureImpl<__WilFeatureTraits_Feature_x64StoreAppsOnArm64>::GetCachedFeatureEnabledState(
                        v20,
                        &v58);
      v28 = (unsigned int)v58;
    }
    LODWORD(v56) = 0;
    WORD2(v56) = 3;
    wil::details::ReportUsageToService(&qword_180096EC0, 24819336, (v28 >> 10) & 1, (v28 >> 11) & 1, &v56, 1, 3);
LABEL_205:
    v56 = v9;
    v9 = v5;
    v29 = *(_QWORD *)v5;
    v30 = v5;
LABEL_218:
    (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::CandidatePackages *))(v29 + 8))(v30);
    if ( v56 )
      (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::CandidatePackages *))(*(_QWORD *)v56 + 16LL))(v56);
    v19 = this;
    goto LABEL_221;
  }
  if ( v4 )
    goto LABEL_217;
LABEL_221:
  if ( !v9 )
  {
    v32 = *(_DWORD *)(*((_QWORD *)v19 + 2) + 552LL);
    if ( v32 )
    {
      v33 = v32 - 5;
      if ( v33 )
      {
        v34 = v33 - 4;
        if ( v34 )
        {
          v35 = v34 - 2;
          if ( v35 )
          {
            v36 = v35 - 1;
            if ( v36 )
            {
              v37 = v36 - 2;
              if ( v37 )
              {
                if ( v37 == 65521 )
                  v38 = L"unknown";
                else
                  v38 = 0;
              }
              else
              {
                v38 = L"x86a64";
              }
            }
            else
            {
              v38 = L"arm64";
            }
          }
          else
          {
            v38 = L"neutral";
          }
        }
        else
        {
          v38 = L"x64";
        }
      }
      else
      {
        v38 = L"arm";
      }
    }
    else
    {
      v38 = L"x86";
    }
    v10 = -1051262718;
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x1B2,
      (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningrequest.cpp",
      (const char *)0xC1570102LL,
      (int)"No applicable main package was found for %ws OS architecture",
      (const char *)v38);
    if ( v8 )
      (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::CandidatePackages *))(*(_QWORD *)v8 + 16LL))(v8);
    if ( v41 )
      (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::CandidatePackages *))(*(_QWORD *)v41 + 16LL))(v41);
    if ( v7 )
      (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::CandidatePackages *))(*(_QWORD *)v7 + 16LL))(v7);
    if ( v6 )
      (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::CandidatePackages *))(*(_QWORD *)v6 + 16LL))(v6);
    if ( v5 )
      (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::CandidatePackages *))(*(_QWORD *)v5 + 16LL))(v5);
    if ( v4 )
      (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::CandidatePackages *))(*(_QWORD *)v4 + 16LL))(v4);
    return v10;
  }
  *v57 = v9;
  if ( v8 )
    (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::CandidatePackages *))(*(_QWORD *)v8 + 16LL))(v8);
  if ( v41 )
    (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::CandidatePackages *))(*(_QWORD *)v41 + 16LL))(v41);
  if ( v7 )
    (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::CandidatePackages *))(*(_QWORD *)v7 + 16LL))(v7);
  if ( v6 )
    (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::CandidatePackages *))(*(_QWORD *)v6 + 16LL))(v6);
  if ( v5 )
    (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::CandidatePackages *))(*(_QWORD *)v5 + 16LL))(v5);
  if ( v4 )
    (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::CandidatePackages *))(*(_QWORD *)v4 + 16LL))(v4);
  return 0;
}

```

## disassembly

```asm
0x180054e90  mov     rax, rsp
0x180054e93  mov     [rax+18h], r8
0x180054e97  mov     [rax+10h], rdx
0x180054e9b  mov     [rax+8], rcx
0x180054e9f  push    rbp
0x180054ea0  push    rbx
0x180054ea1  push    rsi
0x180054ea2  push    rdi
0x180054ea3  push    r12
0x180054ea5  push    r13
0x180054ea7  push    r14
0x180054ea9  push    r15
0x180054eab  lea     rbp, [rax-5Fh]
0x180054eaf  sub     rsp, 0A8h
0x180054eb6  mov     r9, rdx
0x180054eb9  xor     r14d, r14d
0x180054ebc  mov     [rbp+57h+var_48], r14
0x180054ec0  xor     r12d, r12d
0x180054ec3  mov     [rbp+57h+var_58], r12
0x180054ec7  xor     r15d, r15d
0x180054eca  mov     [rbp+57h+var_50], r15
0x180054ece  xor     r13d, r13d
0x180054ed1  mov     [rbp+57h+var_68], r13
0x180054ed5  xor     edi, edi
0x180054ed7  mov     [rbp+57h+var_A0], rdi
0x180054edb  mov     [rbp+57h+var_70], rdi
0x180054edf  xor     ebx, ebx
0x180054ee1  mov     [rbp+57h+var_60], rbx
0x180054ee5  xor     esi, esi
0x180054ee7  mov     [rbp+57h+var_90], rsi
0x180054eeb  mov     [r8], rsi
0x180054eee  mov     rax, [rdx+18h]
0x180054ef2  sub     rax, [rdx+10h]
0x180054ef6  sar     rax, 3
0x180054efa  test    eax, eax
0x180054efc  jnz     short loc_180054F2F
0x180054efe  mov     rcx, [rbp+5Fh]; this
0x180054f02  lea     rax, aMainPackageNot; "Main package not found."
0x180054f09  mov     qword ptr [rsp+0E0h+var_C0], rax; int
0x180054f0e  mov     esi, 0C1570102h
0x180054f13  mov     r9d, esi; char *
0x180054f16  lea     r8, aOnecoreAdminAp_11; "onecore\\admin\\appmodel\\utilities\\pr"...
0x180054f1d  mov     edx, 0FEh; void *
0x180054f22  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180054f27  nop
0x180054f28  mov     eax, esi
0x180054f2a  jmp     loc_180055CDC
0x180054f2f  xor     ecx, ecx
0x180054f31  mov     dword ptr [rbp+57h+arg_18], ecx
0x180054f34  test    eax, eax
0x180054f36  jz      loc_18005515A
0x180054f3c  mov     [rbp+57h+var_78], 0
0x180054f44  lea     r8, [rbp+57h+var_78]
0x180054f48  mov     edx, ecx
0x180054f4a  mov     rcx, r9
0x180054f4d  call    ?Item@?$CContainer@VMsixPackageAdapter@Library@Provisioning@MsixPackage@@VMsixAdapterCollection@234@@Library@Provisioning@MsixPackage@@QEAAJKPEAPEAVMsixPackageAdapter@234@@Z; MsixPackage::Provisioning::Library::CContainer<MsixPackage::Provisioning::Library::MsixPackageAdapter,MsixPackage::Provisioning::Library::MsixAdapterCollection>::Item(ulong,MsixPackage::Provisioning::Library::MsixPackageAdapter * *)
0x180054f52  mov     dword ptr [rbp+57h+var_98], eax
0x180054f55  test    eax, eax
0x180054f57  js      loc_180055911
0x180054f5d  mov     rdi, [rbp+57h+var_78]
0x180054f61  lea     rax, [rdi+38h]
0x180054f65  mov     [rbp+57h+var_88], rax
0x180054f69  cmp     qword ptr [rax+18h], 8
0x180054f6e  jb      short loc_180054F77
0x180054f70  mov     rax, [rax]
0x180054f73  mov     [rbp+57h+var_88], rax
0x180054f77  mov     [rbp+57h+var_80], 0
0x180054f7f  lea     rdx, [rbp+57h+var_80]
0x180054f83  mov     rcx, rax
0x180054f86  call    ?GetPackageIdByBasicFullName@MsixProvisioningContext@Library@Provisioning@MsixPackage@@SAJPEBGAEAV?$unique_ptr@UPACKAGE_ID@@U?$default_delete@UPACKAGE_ID@@@wistd@@@wistd@@@Z; MsixPackage::Provisioning::Library::MsixProvisioningContext::GetPackageIdByBasicFullName(ushort const *,wistd::unique_ptr<PACKAGE_ID,wistd::default_delete<PACKAGE_ID>> &)
0x180054f8b  mov     dword ptr [rbp+57h+var_98], eax
0x180054f8e  test    eax, eax
0x180054f90  js      loc_180055817
0x180054f96  mov     rcx, [rbp+57h+var_80]
0x180054f9a  mov     edx, [rcx+4]
0x180054f9d  mov     dword ptr [rbp+57h+var_98], edx
0x180054fa0  test    rcx, rcx
0x180054fa3  jz      short loc_180054FB4
0x180054fa5  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180054fac  nop     dword ptr [rax+rax+00h]
0x180054fb1  mov     edx, dword ptr [rbp+57h+var_98]
0x180054fb4  mov     eax, edx
0x180054fb6  test    edx, edx
0x180054fb8  jz      loc_1800550B4
0x180054fbe  sub     eax, 5
0x180054fc1  jz      loc_18005508D
0x180054fc7  sub     eax, 4
0x180054fca  jz      loc_180055066
0x180054fd0  sub     eax, 2
0x180054fd3  jz      short loc_18005503C
0x180054fd5  sub     eax, 1
0x180054fd8  jz      short loc_180055012
0x180054fda  cmp     eax, 2
0x180054fdd  jnz     loc_180055295
0x180054fe3  cmp     [rbp+57h+var_A0], 0
0x180054fe8  jnz     loc_1800551BD
0x180054fee  mov     rcx, rdi
0x180054ff1  mov     [rbp+57h+var_A0], rcx
0x180054ff5  mov     [rbp+57h+var_70], rcx
0x180054ff9  test    rdi, rdi
0x180054ffc  jz      short loc_18005500D
0x180054ffe  mov     rax, [rdi]
0x180055001  mov     rax, [rax+8]
0x180055005  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005500a  mov     rcx, rdi
0x18005500d  jmp     loc_1800550DC
0x180055012  test    r13, r13
0x180055015  jnz     loc_180055367
0x18005501b  mov     r13, rdi
0x18005501e  mov     [rbp+57h+var_68], rdi
0x180055022  test    rdi, rdi
0x180055025  jz      short loc_180055037
0x180055027  mov     rax, [rdi]
0x18005502a  mov     rcx, rdi
0x18005502d  mov     rax, [rax+8]
0x180055031  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055036  nop
0x180055037  jmp     loc_1800550D9
0x18005503c  test    rbx, rbx
0x18005503f  jnz     loc_18005542C
0x180055045  mov     rbx, rdi
0x180055048  mov     [rbp+57h+var_60], rbx
0x18005504c  test    rdi, rdi
0x18005504f  jz      short loc_180055061
0x180055051  mov     rax, [rdi]
0x180055054  mov     rcx, rbx
0x180055057  mov     rax, [rax+8]
0x18005505b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055060  nop
0x180055061  mov     rcx, rbx
0x180055064  jmp     short loc_1800550DC
0x180055066  test    r12, r12
0x180055069  jnz     loc_1800554F1
0x18005506f  mov     r12, rdi
0x180055072  mov     [rbp+57h+var_58], rdi
0x180055076  test    rdi, rdi
0x180055079  jz      short loc_18005508B
0x18005507b  mov     rax, [rdi]
0x18005507e  mov     rcx, rdi
0x180055081  mov     rax, [rax+8]
0x180055085  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005508a  nop
0x18005508b  jmp     short loc_1800550D9
0x18005508d  test    r15, r15
0x180055090  jnz     loc_1800555B7
0x180055096  mov     r15, rdi
0x180055099  mov     [rbp+57h+var_50], rdi
0x18005509d  test    rdi, rdi
0x1800550a0  jz      short loc_1800550B2
0x1800550a2  mov     rax, [rdi]
0x1800550a5  mov     rcx, rdi
0x1800550a8  mov     rax, [rax+8]
0x1800550ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800550b1  nop
0x1800550b2  jmp     short loc_1800550D9
0x1800550b4  test    r14, r14
0x1800550b7  jnz     loc_180055738
0x1800550bd  mov     r14, rdi
0x1800550c0  mov     [rbp+57h+var_48], rdi
0x1800550c4  test    rdi, rdi
0x1800550c7  jz      short loc_1800550D9
0x1800550c9  mov     rax, [rdi]
0x1800550cc  mov     rcx, rdi
0x1800550cf  mov     rax, [rax+8]
0x1800550d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800550d8  nop
0x1800550d9  mov     rcx, rdi
0x1800550dc  test    rcx, rcx
0x1800550df  jz      short loc_1800550F1
0x1800550e1  mov     rax, [rdi]
0x1800550e4  mov     rcx, rdi
0x1800550e7  mov     rax, [rax+10h]
0x1800550eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800550f0  nop
0x1800550f1  mov     ecx, dword ptr [rbp+57h+arg_18]
0x1800550f4  inc     ecx
0x1800550f6  mov     dword ptr [rbp+57h+arg_18], ecx
0x1800550f9  mov     r9, [rbp+57h+arg_8]
0x1800550fd  mov     rax, [r9+18h]
0x180055101  sub     rax, [r9+10h]
0x180055105  sar     rax, 3
0x180055109  cmp     ecx, eax
0x18005510b  jb      loc_180054F3C
0x180055111  test    rbx, rbx
0x180055114  jz      short loc_180055156
0x180055116  test    r14, r14
0x180055119  jnz     loc_18005567C
0x18005511f  test    r12, r12
0x180055122  jnz     loc_18005567C
0x180055128  test    r15, r15
0x18005512b  jnz     loc_18005567C
0x180055131  test    r13, r13
0x180055134  jnz     loc_18005567C
0x18005513a  mov     rsi, rbx
0x18005513d  mov     [rbp+57h+var_90], rbx
0x180055141  test    rbx, rbx
0x180055144  jz      short loc_180055156
0x180055146  mov     rax, [rbx]
0x180055149  mov     rcx, rbx
0x18005514c  mov     rax, [rax+8]
0x180055150  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055155  nop
0x180055156  mov     rdi, [rbp+57h+var_A0]
0x18005515a  mov     rdx, [rbp+57h+arg_0]
0x18005515e  mov     rax, [rdx+10h]
0x180055162  mov     ecx, [rax+228h]
0x180055168  test    ecx, ecx
0x18005516a  jz      loc_180055AEA
0x180055170  cmp     ecx, 5
0x180055173  jz      loc_180055AD5
0x180055179  cmp     ecx, 9
0x18005517c  jz      loc_180055AC4
0x180055182  cmp     ecx, 0Ch
0x180055185  jnz     loc_180055B26
0x18005518b  test    r13, r13
0x18005518e  jnz     loc_180055AA8
0x180055194  test    rdi, rdi
0x180055197  jnz     loc_180055A8D
0x18005519d  test    r15, r15
0x1800551a0  jnz     loc_180055A6E
0x1800551a6  test    r12, r12
0x1800551a9  jnz     loc_1800559DF
0x1800551af  test    r14, r14
0x1800551b2  jz      loc_180055B26
0x1800551b8  jmp     loc_180055AEF
0x1800551bd  mov     rsi, [rbp+57h+var_A0]
0x1800551c1  lea     rax, [rsi+38h]
0x1800551c5  cmp     qword ptr [rax+18h], 8
0x1800551ca  jb      short loc_1800551CF
0x1800551cc  mov     rax, [rax]
0x1800551cf  mov     rcx, [rbp+5Fh]; this
0x1800551d3  mov     [rsp+30h], rax
0x1800551d8  mov     rax, [rbp+57h+var_88]
0x1800551dc  mov     [rsp+0E0h+var_B8], rax; char *
0x1800551e1  lea     rax, aMainPackagesWs; "Main packages %ws and %ws have the same"...
0x1800551e8  mov     qword ptr [rsp+0E0h+var_C0], rax; int
0x1800551ed  mov     r9d, 0C1570109h; char *
0x1800551f3  lea     r8, aOnecoreAdminAp_11; "onecore\\admin\\appmodel\\utilities\\pr"...
0x1800551fa  mov     edx, 156h; void *
0x1800551ff  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180055204  nop
0x180055205  test    rdi, rdi
0x180055208  jz      short loc_18005521A
0x18005520a  mov     rax, [rdi]
0x18005520d  mov     rcx, rdi
0x180055210  mov     rax, [rax+10h]
0x180055214  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055219  nop
0x18005521a  test    rbx, rbx
0x18005521d  jz      short loc_18005522F
0x18005521f  mov     rax, [rbx]
0x180055222  mov     rcx, rbx
0x180055225  mov     rax, [rax+10h]
0x180055229  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005522e  nop
0x18005522f  mov     rax, [rsi]
0x180055232  mov     rcx, rsi
0x180055235  mov     rax, [rax+10h]
0x180055239  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005523e  nop
0x18005523f  test    r13, r13
0x180055242  jz      short loc_180055255
0x180055244  mov     rax, [r13+0]
0x180055248  mov     rcx, r13
0x18005524b  mov     rax, [rax+10h]
0x18005524f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055254  nop
0x180055255  test    r15, r15
0x180055258  jz      short loc_18005526A
0x18005525a  mov     rax, [r15]
0x18005525d  mov     rcx, r15
0x180055260  mov     rax, [rax+10h]
0x180055264  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055269  nop
0x18005526a  test    r12, r12
0x18005526d  jz      short loc_180055280
0x18005526f  mov     rax, [r12]
0x180055273  mov     rcx, r12
0x180055276  mov     rax, [rax+10h]
0x18005527a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005527f  nop
0x180055280  test    r14, r14
0x180055283  jz      loc_180055733
0x180055289  mov     rax, [r14]
0x18005528c  mov     rax, [rax+10h]
0x180055290  jmp     loc_18005572A
0x180055295  mov     rcx, [rbp+5Fh]; this
0x180055299  mov     rax, [rbp+57h+var_88]
0x18005529d  mov     [rsp+30h], rax
0x1800552a2  mov     dword ptr [rsp+0E0h+var_B8], edx; char *
0x1800552a6  lea     rax, aUnsupportedPac; "Unsupported package architecture %d in "...
0x1800552ad  mov     qword ptr [rsp+0E0h+var_C0], rax; int
0x1800552b2  mov     esi, 80070057h
0x1800552b7  mov     r9d, esi; char *
0x1800552ba  lea     r8, aOnecoreAdminAp_11; "onecore\\admin\\appmodel\\utilities\\pr"...
0x1800552c1  mov     edx, 162h; void *
0x1800552c6  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800552cb  nop
0x1800552cc  test    rdi, rdi
0x1800552cf  jz      short loc_1800552E1
  ... truncated ...
```
