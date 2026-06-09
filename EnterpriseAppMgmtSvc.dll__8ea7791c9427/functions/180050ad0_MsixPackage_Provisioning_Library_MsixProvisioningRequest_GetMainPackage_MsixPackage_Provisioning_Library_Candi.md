# MsixPackage::Provisioning::Library::MsixProvisioningRequest::GetMainPackage(MsixPackage::Provisioning::Library::CandidatePackages *,MsixPackage::Provisioning::Library::PackageMonikerToPayload * *)

- ea: `0x180050ad0`
- end: `0x180051924`
- name: `?GetMainPackage@MsixProvisioningRequest@Library@Provisioning@MsixPackage@@AEAAJPEAVCandidatePackages@234@PEAPEAVPackageMonikerToPayload@234@@Z`
- size: `3668`
- prototype: `__int64 __fastcall(MsixPackage::Provisioning::Library::MsixProvisioningRequest *__hidden this, struct MsixPackage::Provisioning::Library::CandidatePackages *, struct MsixPackage::Provisioning::Library::PackageMonikerToPayload **)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, service_task, installer_update`

## callers

- `0x18004f76c`

## callees

- `0x18000cfe8`
- `0x180017e70`
- `0x180038d54`
- `0x180039e9c`
- `0x18003dcbc`
- `0x18003dfac`
- `0x180050ad0`
- `0x18006a010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180050be5`
- `msvcrt!??3@YAXPEAX@Z` at `0x180051473`
- `msvcrt!??3@YAXPEAX@Z` at `0x180050be5`
- `msvcrt!??3@YAXPEAX@Z` at `0x180051473`

## string_xrefs

- `0x180051458`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningutils.cpp`
- `0x180050b56`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningrequest.cpp`
- `0x180050e2d`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningrequest.cpp`
- `0x180050ef4`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningrequest.cpp`
- `0x180050fd3`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningrequest.cpp`
- `0x180051098`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningrequest.cpp`
- `0x18005115e`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningrequest.cpp`
- `0x180051223`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningrequest.cpp`
- `0x1800512df`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningrequest.cpp`
- `0x1800513a4`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningrequest.cpp`
- `0x180051498`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningrequest.cpp`
- `0x18005155f`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningrequest.cpp`
- `0x1800517f0`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningrequest.cpp`

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
    wil::details::ReportUsageToService(&qword_180090EC0, 24819336, (v28 >> 10) & 1, (v28 >> 11) & 1, &v56, 1, 3);
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
0x180050ad0  mov     rax, rsp
0x180050ad3  mov     [rax+18h], r8
0x180050ad7  mov     [rax+10h], rdx
0x180050adb  mov     [rax+8], rcx
0x180050adf  push    rbp
0x180050ae0  push    rbx
0x180050ae1  push    rsi
0x180050ae2  push    rdi
0x180050ae3  push    r12
0x180050ae5  push    r13
0x180050ae7  push    r14
0x180050ae9  push    r15
0x180050aeb  lea     rbp, [rax-5Fh]
0x180050aef  sub     rsp, 0A8h
0x180050af6  mov     r9, rdx
0x180050af9  xor     r14d, r14d
0x180050afc  mov     [rbp+57h+var_48], r14
0x180050b00  xor     r12d, r12d
0x180050b03  mov     [rbp+57h+var_58], r12
0x180050b07  xor     r15d, r15d
0x180050b0a  mov     [rbp+57h+var_50], r15
0x180050b0e  xor     r13d, r13d
0x180050b11  mov     [rbp+57h+var_68], r13
0x180050b15  xor     edi, edi
0x180050b17  mov     [rbp+57h+var_A0], rdi
0x180050b1b  mov     [rbp+57h+var_70], rdi
0x180050b1f  xor     ebx, ebx
0x180050b21  mov     [rbp+57h+var_60], rbx
0x180050b25  xor     esi, esi
0x180050b27  mov     [rbp+57h+var_90], rsi
0x180050b2b  mov     [r8], rsi
0x180050b2e  mov     rax, [rdx+18h]
0x180050b32  sub     rax, [rdx+10h]
0x180050b36  sar     rax, 3
0x180050b3a  test    eax, eax
0x180050b3c  jnz     short loc_180050B6F
0x180050b3e  mov     rcx, [rbp+5Fh]; this
0x180050b42  lea     rax, aMainPackageNot; "Main package not found."
0x180050b49  mov     qword ptr [rsp+0E0h+var_C0], rax; int
0x180050b4e  mov     esi, 0C1570102h
0x180050b53  mov     r9d, esi; char *
0x180050b56  lea     r8, aOnecoreAdminAp_11; "onecore\\admin\\appmodel\\utilities\\pr"...
0x180050b5d  mov     edx, 0FEh; void *
0x180050b62  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180050b67  nop
0x180050b68  mov     eax, esi
0x180050b6a  jmp     loc_180051910
0x180050b6f  xor     ecx, ecx
0x180050b71  mov     dword ptr [rbp+57h+arg_18], ecx
0x180050b74  test    eax, eax
0x180050b76  jz      loc_180050D94
0x180050b7c  mov     [rbp+57h+var_78], 0
0x180050b84  lea     r8, [rbp+57h+var_78]
0x180050b88  mov     edx, ecx
0x180050b8a  mov     rcx, r9
0x180050b8d  call    ?Item@?$CContainer@VMsixPackageAdapter@Library@Provisioning@MsixPackage@@VMsixAdapterCollection@234@@Library@Provisioning@MsixPackage@@QEAAJKPEAPEAVMsixPackageAdapter@234@@Z; MsixPackage::Provisioning::Library::CContainer<MsixPackage::Provisioning::Library::MsixPackageAdapter,MsixPackage::Provisioning::Library::MsixAdapterCollection>::Item(ulong,MsixPackage::Provisioning::Library::MsixPackageAdapter * *)
0x180050b92  mov     dword ptr [rbp+57h+var_98], eax
0x180050b95  test    eax, eax
0x180050b97  js      loc_180051545
0x180050b9d  mov     rdi, [rbp+57h+var_78]
0x180050ba1  lea     rax, [rdi+38h]
0x180050ba5  mov     [rbp+57h+var_88], rax
0x180050ba9  cmp     qword ptr [rax+18h], 8
0x180050bae  jb      short loc_180050BB7
0x180050bb0  mov     rax, [rax]
0x180050bb3  mov     [rbp+57h+var_88], rax
0x180050bb7  mov     [rbp+57h+var_80], 0
0x180050bbf  lea     rdx, [rbp+57h+var_80]
0x180050bc3  mov     rcx, rax
0x180050bc6  call    ?GetPackageIdByBasicFullName@MsixProvisioningContext@Library@Provisioning@MsixPackage@@SAJPEBGAEAV?$unique_ptr@UPACKAGE_ID@@U?$default_delete@UPACKAGE_ID@@@wistd@@@wistd@@@Z; MsixPackage::Provisioning::Library::MsixProvisioningContext::GetPackageIdByBasicFullName(ushort const *,wistd::unique_ptr<PACKAGE_ID,wistd::default_delete<PACKAGE_ID>> &)
0x180050bcb  mov     dword ptr [rbp+57h+var_98], eax
0x180050bce  test    eax, eax
0x180050bd0  js      loc_180051451
0x180050bd6  mov     rcx, [rbp+57h+var_80]
0x180050bda  mov     edx, [rcx+4]
0x180050bdd  mov     dword ptr [rbp+57h+var_98], edx
0x180050be0  test    rcx, rcx
0x180050be3  jz      short loc_180050BEE
0x180050be5  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180050beb  mov     edx, dword ptr [rbp+57h+var_98]
0x180050bee  mov     eax, edx
0x180050bf0  test    edx, edx
0x180050bf2  jz      loc_180050CEE
0x180050bf8  sub     eax, 5
0x180050bfb  jz      loc_180050CC7
0x180050c01  sub     eax, 4
0x180050c04  jz      loc_180050CA0
0x180050c0a  sub     eax, 2
0x180050c0d  jz      short loc_180050C76
0x180050c0f  sub     eax, 1
0x180050c12  jz      short loc_180050C4C
0x180050c14  cmp     eax, 2
0x180050c17  jnz     loc_180050ECF
0x180050c1d  cmp     [rbp+57h+var_A0], 0
0x180050c22  jnz     loc_180050DF7
0x180050c28  mov     rcx, rdi
0x180050c2b  mov     [rbp+57h+var_A0], rcx
0x180050c2f  mov     [rbp+57h+var_70], rcx
0x180050c33  test    rdi, rdi
0x180050c36  jz      short loc_180050C47
0x180050c38  mov     rax, [rdi]
0x180050c3b  mov     rax, [rax+8]
0x180050c3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050c44  mov     rcx, rdi
0x180050c47  jmp     loc_180050D16
0x180050c4c  test    r13, r13
0x180050c4f  jnz     loc_180050FA1
0x180050c55  mov     r13, rdi
0x180050c58  mov     [rbp+57h+var_68], rdi
0x180050c5c  test    rdi, rdi
0x180050c5f  jz      short loc_180050C71
0x180050c61  mov     rax, [rdi]
0x180050c64  mov     rcx, rdi
0x180050c67  mov     rax, [rax+8]
0x180050c6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050c70  nop
0x180050c71  jmp     loc_180050D13
0x180050c76  test    rbx, rbx
0x180050c79  jnz     loc_180051066
0x180050c7f  mov     rbx, rdi
0x180050c82  mov     [rbp+57h+var_60], rbx
0x180050c86  test    rdi, rdi
0x180050c89  jz      short loc_180050C9B
0x180050c8b  mov     rax, [rdi]
0x180050c8e  mov     rcx, rbx
0x180050c91  mov     rax, [rax+8]
0x180050c95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050c9a  nop
0x180050c9b  mov     rcx, rbx
0x180050c9e  jmp     short loc_180050D16
0x180050ca0  test    r12, r12
0x180050ca3  jnz     loc_18005112B
0x180050ca9  mov     r12, rdi
0x180050cac  mov     [rbp+57h+var_58], rdi
0x180050cb0  test    rdi, rdi
0x180050cb3  jz      short loc_180050CC5
0x180050cb5  mov     rax, [rdi]
0x180050cb8  mov     rcx, rdi
0x180050cbb  mov     rax, [rax+8]
0x180050cbf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050cc4  nop
0x180050cc5  jmp     short loc_180050D13
0x180050cc7  test    r15, r15
0x180050cca  jnz     loc_1800511F1
0x180050cd0  mov     r15, rdi
0x180050cd3  mov     [rbp+57h+var_50], rdi
0x180050cd7  test    rdi, rdi
0x180050cda  jz      short loc_180050CEC
0x180050cdc  mov     rax, [rdi]
0x180050cdf  mov     rcx, rdi
0x180050ce2  mov     rax, [rax+8]
0x180050ce6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050ceb  nop
0x180050cec  jmp     short loc_180050D13
0x180050cee  test    r14, r14
0x180050cf1  jnz     loc_180051372
0x180050cf7  mov     r14, rdi
0x180050cfa  mov     [rbp+57h+var_48], rdi
0x180050cfe  test    rdi, rdi
0x180050d01  jz      short loc_180050D13
0x180050d03  mov     rax, [rdi]
0x180050d06  mov     rcx, rdi
0x180050d09  mov     rax, [rax+8]
0x180050d0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050d12  nop
0x180050d13  mov     rcx, rdi
0x180050d16  test    rcx, rcx
0x180050d19  jz      short loc_180050D2B
0x180050d1b  mov     rax, [rdi]
0x180050d1e  mov     rcx, rdi
0x180050d21  mov     rax, [rax+10h]
0x180050d25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050d2a  nop
0x180050d2b  mov     ecx, dword ptr [rbp+57h+arg_18]
0x180050d2e  inc     ecx
0x180050d30  mov     dword ptr [rbp+57h+arg_18], ecx
0x180050d33  mov     r9, [rbp+57h+arg_8]
0x180050d37  mov     rax, [r9+18h]
0x180050d3b  sub     rax, [r9+10h]
0x180050d3f  sar     rax, 3
0x180050d43  cmp     ecx, eax
0x180050d45  jb      loc_180050B7C
0x180050d4b  test    rbx, rbx
0x180050d4e  jz      short loc_180050D90
0x180050d50  test    r14, r14
0x180050d53  jnz     loc_1800512B6
0x180050d59  test    r12, r12
0x180050d5c  jnz     loc_1800512B6
0x180050d62  test    r15, r15
0x180050d65  jnz     loc_1800512B6
0x180050d6b  test    r13, r13
0x180050d6e  jnz     loc_1800512B6
0x180050d74  mov     rsi, rbx
0x180050d77  mov     [rbp+57h+var_90], rbx
0x180050d7b  test    rbx, rbx
0x180050d7e  jz      short loc_180050D90
0x180050d80  mov     rax, [rbx]
0x180050d83  mov     rcx, rbx
0x180050d86  mov     rax, [rax+8]
0x180050d8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050d8f  nop
0x180050d90  mov     rdi, [rbp+57h+var_A0]
0x180050d94  mov     rdx, [rbp+57h+arg_0]
0x180050d98  mov     rax, [rdx+10h]
0x180050d9c  mov     ecx, [rax+228h]
0x180050da2  test    ecx, ecx
0x180050da4  jz      loc_18005171E
0x180050daa  cmp     ecx, 5
0x180050dad  jz      loc_180051709
0x180050db3  cmp     ecx, 9
0x180050db6  jz      loc_1800516F8
0x180050dbc  cmp     ecx, 0Ch
0x180050dbf  jnz     loc_18005175A
0x180050dc5  test    r13, r13
0x180050dc8  jnz     loc_1800516DC
0x180050dce  test    rdi, rdi
0x180050dd1  jnz     loc_1800516C1
0x180050dd7  test    r15, r15
0x180050dda  jnz     loc_1800516A2
0x180050de0  test    r12, r12
0x180050de3  jnz     loc_180051613
0x180050de9  test    r14, r14
0x180050dec  jz      loc_18005175A
0x180050df2  jmp     loc_180051723
0x180050df7  mov     rsi, [rbp+57h+var_A0]
0x180050dfb  lea     rax, [rsi+38h]
0x180050dff  cmp     qword ptr [rax+18h], 8
0x180050e04  jb      short loc_180050E09
0x180050e06  mov     rax, [rax]
0x180050e09  mov     rcx, [rbp+5Fh]; this
0x180050e0d  mov     [rsp+30h], rax
0x180050e12  mov     rax, [rbp+57h+var_88]
0x180050e16  mov     [rsp+0E0h+var_B8], rax; char *
0x180050e1b  lea     rax, aMainPackagesWs; "Main packages %ws and %ws have the same"...
0x180050e22  mov     qword ptr [rsp+0E0h+var_C0], rax; int
0x180050e27  mov     r9d, 0C1570109h; char *
0x180050e2d  lea     r8, aOnecoreAdminAp_11; "onecore\\admin\\appmodel\\utilities\\pr"...
0x180050e34  mov     edx, 156h; void *
0x180050e39  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180050e3e  nop
0x180050e3f  test    rdi, rdi
0x180050e42  jz      short loc_180050E54
0x180050e44  mov     rax, [rdi]
0x180050e47  mov     rcx, rdi
0x180050e4a  mov     rax, [rax+10h]
0x180050e4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050e53  nop
0x180050e54  test    rbx, rbx
0x180050e57  jz      short loc_180050E69
0x180050e59  mov     rax, [rbx]
0x180050e5c  mov     rcx, rbx
0x180050e5f  mov     rax, [rax+10h]
0x180050e63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050e68  nop
0x180050e69  mov     rax, [rsi]
0x180050e6c  mov     rcx, rsi
0x180050e6f  mov     rax, [rax+10h]
0x180050e73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050e78  nop
0x180050e79  test    r13, r13
0x180050e7c  jz      short loc_180050E8F
0x180050e7e  mov     rax, [r13+0]
0x180050e82  mov     rcx, r13
0x180050e85  mov     rax, [rax+10h]
0x180050e89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050e8e  nop
0x180050e8f  test    r15, r15
0x180050e92  jz      short loc_180050EA4
0x180050e94  mov     rax, [r15]
0x180050e97  mov     rcx, r15
0x180050e9a  mov     rax, [rax+10h]
0x180050e9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050ea3  nop
0x180050ea4  test    r12, r12
0x180050ea7  jz      short loc_180050EBA
0x180050ea9  mov     rax, [r12]
0x180050ead  mov     rcx, r12
0x180050eb0  mov     rax, [rax+10h]
0x180050eb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050eb9  nop
0x180050eba  test    r14, r14
0x180050ebd  jz      loc_18005136D
0x180050ec3  mov     rax, [r14]
0x180050ec6  mov     rax, [rax+10h]
0x180050eca  jmp     loc_180051364
0x180050ecf  mov     rcx, [rbp+5Fh]; this
0x180050ed3  mov     rax, [rbp+57h+var_88]
0x180050ed7  mov     [rsp+30h], rax
0x180050edc  mov     dword ptr [rsp+0E0h+var_B8], edx; char *
0x180050ee0  lea     rax, aUnsupportedPac; "Unsupported package architecture %d in "...
0x180050ee7  mov     qword ptr [rsp+0E0h+var_C0], rax; int
0x180050eec  mov     esi, 80070057h
0x180050ef1  mov     r9d, esi; char *
0x180050ef4  lea     r8, aOnecoreAdminAp_11; "onecore\\admin\\appmodel\\utilities\\pr"...
0x180050efb  mov     edx, 162h; void *
0x180050f00  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180050f05  nop
0x180050f06  test    rdi, rdi
0x180050f09  jz      short loc_180050F1B
0x180050f0b  mov     rax, [rdi]
  ... truncated ...
```
