# MsixPackage::Provisioning::Library::MsixProvisioningRequest::CreateFromPackageSource(MsixPackage::Provisioning::Library::PackageSource *,MsixPackage::Provisioning::Library::MsixProvisioningContext *,MsixPackage::Provisioning::Library::MsixProvisioningRequest * *)

- ea: `0x180053b30`
- end: `0x180054dba`
- name: `?CreateFromPackageSource@MsixProvisioningRequest@Library@Provisioning@MsixPackage@@SAJPEAVPackageSource@234@PEAVMsixProvisioningContext@234@PEAPEAV1234@@Z`
- size: `4746`
- prototype: `__int64 __fastcall(struct MsixPackage::Provisioning::Library::PackageSource *, struct MsixPackage::Provisioning::Library::MsixProvisioningContext *, struct MsixPackage::Provisioning::Library::MsixProvisioningRequest **)`
- caller_count: `2`
- callee_count: `15`
- tags: `registry_config, installer_update`

## callers

- `0x180035f40`
- `0x18004804c`

## callees

- `0x180002398`
- `0x18000d3dc`
- `0x180034868`
- `0x18003c2c0`
- `0x18003d4ec`
- `0x180045970`
- `0x1800524d0`
- `0x180052828`
- `0x180053b30`
- `0x180054e90`
- `0x180058a30`
- `0x18005a710`
- `0x18005aaac`
- `0x18005b444`
- `0x180070010`

## string_xrefs

- `0x180053c57`: `onecore\admin\appmodel\utilities\provisionhelper\MsixPackageAdapter.h`
- `0x180053b83`: `Failed to create package set.`
- `0x180053c6d`: `Failed to create list of candidate packages.`
- `0x180053b92`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningrequest.cpp`
- `0x180053c7c`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningrequest.cpp`
- `0x180053d0d`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningrequest.cpp`
- `0x180053dd4`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningrequest.cpp`
- `0x180053e5e`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningrequest.cpp`
- `0x180053f02`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningrequest.cpp`
- `0x180053f9b`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningrequest.cpp`
- `0x18005404a`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningrequest.cpp`
- `0x1800540d5`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningrequest.cpp`
- `0x180054164`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningrequest.cpp`
- `0x18005420c`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningrequest.cpp`
- `0x1800542b2`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningrequest.cpp`
- `0x180054365`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningrequest.cpp`
- `0x18005442e`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningrequest.cpp`
- `0x1800544eb`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningrequest.cpp`
- `0x180054668`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningrequest.cpp`
- `0x180054713`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningrequest.cpp`
- `0x1800547cc`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningrequest.cpp`
- `0x18005487f`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningrequest.cpp`
- `0x1800549df`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningrequest.cpp`
- `0x180054a6a`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningrequest.cpp`
- `0x180054b04`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningrequest.cpp`
- `0x180054cb7`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningrequest.cpp`
- `0x180054d42`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningrequest.cpp`
- `0x1800541fd`: `Failed to get bundle manifest reader for bundle.`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
__int64 __fastcall MsixPackage::Provisioning::Library::MsixProvisioningRequest::CreateFromPackageSource(
        struct MsixPackage::Provisioning::Library::PackageSource *a1,
        struct MsixPackage::Provisioning::Library::MsixProvisioningContext *a2,
        struct MsixPackage::Provisioning::Library::MsixProvisioningRequest **a3)
{
  unsigned int v5; // r12d
  struct IAppxBundleManifestReader *v6; // rbx
  int v7; // esi
  struct MsixPackage::Provisioning::Library::CandidatePackages *v9; // rax
  struct MsixPackage::Provisioning::Library::CandidatePackages *v10; // rsi
  unsigned int BundleManifestReader; // ebx
  int PackagesFromPath; // eax
  unsigned int v13; // r14d
  MsixPackage::Provisioning::Library::MsixProvisioningRequest *v14; // r14
  struct MsixPackage::Provisioning::Library::PackageMonikerToPayload *v15; // rcx
  int MainPackage; // eax
  int v17; // r15d
  _QWORD *v18; // rax
  int PackagesFromReader; // eax
  struct MsixPackage::Provisioning::Library::PackageMonikerToPayload *v20; // rcx
  int v21; // eax
  _QWORD *v22; // rax
  int v23; // eax
  const unsigned __int16 *v24; // r15
  int v25; // edi
  MsixPackage::Provisioning::Library::MsixPackageAdapter *v26; // rdi
  _QWORD *v27; // rax
  struct MsixPackage::Provisioning::Library::PackageMonikerToPayload *v28; // rdx
  struct MsixPackage::Provisioning::Library::PackageMonikerToPayload *v29; // rcx
  __int64 v30; // rdx
  __int64 v31; // r8
  const char *v32; // rdx
  int v33; // eax
  struct MsixPackage::Provisioning::Library::PackageMonikerToPayload *v34; // rdx
  struct MsixPackage::Provisioning::Library::PackageMonikerToPayload *v35; // rcx
  int v36; // eax
  const char *v37; // rax
  unsigned int v38; // edi
  struct MsixPackage::Provisioning::Library::PackageMonikerToPayload *v39; // rdx
  struct MsixPackage::Provisioning::Library::PackageMonikerToPayload *v40; // rcx
  const char *v41; // rax
  int v42; // [rsp+20h] [rbp-30h]
  char *v43; // [rsp+28h] [rbp-28h]
  MsixPackage::Provisioning::Library::MsixProvisioningRequest *v44; // [rsp+30h] [rbp-20h] BYREF
  struct IAppxBundleManifestReader *v45; // [rsp+38h] [rbp-18h] BYREF
  MsixPackage::Provisioning::Library::MsixPackageAdapter *v46; // [rsp+40h] [rbp-10h] BYREF
  struct MsixPackage::Provisioning::Library::CandidatePackages *v47; // [rsp+48h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+38h]
  struct MsixPackage::Provisioning::Library::PackageMonikerToPayload *v49; // [rsp+A0h] [rbp+50h] BYREF
  struct MsixPackage::Provisioning::Library::PackageMonikerToPayload *v50; // [rsp+A8h] [rbp+58h] BYREF

  v5 = 0;
  v47 = 0;
  v49 = 0;
  v6 = 0;
  v45 = 0;
  v50 = 0;
  *a3 = 0;
  v44 = 0;
  v7 = MsixPackage::Provisioning::Library::MsixAdapterBase::Make<MsixPackage::Provisioning::Library::MsixProvisioningRequest>(
         a2,
         &v44);
  if ( v7 < 0 )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x24,
      (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningrequest.cpp",
      (const char *)(unsigned int)v7,
      (int)"Failed to create package set.",
      v43);
    if ( v50 )
      (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::PackageMonikerToPayload *))(*(_QWORD *)v50 + 16LL))(v50);
    if ( v49 )
      (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::PackageMonikerToPayload *))(*(_QWORD *)v49 + 16LL))(v49);
    if ( v44 )
      (*(void (__fastcall **)(MsixPackage::Provisioning::Library::MsixProvisioningRequest *))(*(_QWORD *)v44 + 16LL))(v44);
    return (unsigned int)v7;
  }
  v47 = 0;
  v9 = (struct MsixPackage::Provisioning::Library::CandidatePackages *)operator new(
                                                                         0x30u,
                                                                         (const struct std::nothrow_t *)&std::nothrow);
  v10 = v9;
  if ( v9 )
  {
    *((_QWORD *)v9 + 1) = 0;
    *((_QWORD *)v9 + 2) = 0;
    *((_QWORD *)v9 + 3) = 0;
    *((_QWORD *)v9 + 4) = 0;
    *((_QWORD *)v9 + 5) = 0;
    *(_QWORD *)v9 = &MsixPackage::Provisioning::Library::CandidatePackages::`vftable';
  }
  else
  {
    v10 = 0;
  }
  if ( !v10 )
  {
    BundleManifestReader = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B3,
      (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\MsixPackageAdapter.h",
      (const char *)0x8007000ELL,
      v42);
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x26,
      (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningrequest.cpp",
      (const char *)0x8007000ELL,
      (int)"Failed to create list of candidate packages.",
      v43);
    if ( v50 )
      (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::PackageMonikerToPayload *))(*(_QWORD *)v50 + 16LL))(v50);
    if ( v49 )
      (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::PackageMonikerToPayload *))(*(_QWORD *)v49 + 16LL))(v49);
    if ( v44 )
      (*(void (__fastcall **)(MsixPackage::Provisioning::Library::MsixProvisioningRequest *))(*(_QWORD *)v44 + 16LL))(v44);
    return BundleManifestReader;
  }
  (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::CandidatePackages *))(*(_QWORD *)v10 + 8LL))(v10);
  v47 = v10;
  if ( *((_QWORD *)a1 + 1) )
    PackagesFromPath = MsixPackage::Provisioning::Library::PackageSource::GetPackagesFromPath(a1, 0, v10);
  else
    PackagesFromPath = MsixPackage::Provisioning::Library::PackageSource::GetPackagesFromReader((__int64)a1, 0, v10);
  v13 = PackagesFromPath;
  if ( PackagesFromPath >= 0 )
  {
    if ( (unsigned int)((__int64)(*((_QWORD *)v10 + 3) - *((_QWORD *)v10 + 2)) >> 3) )
    {
      v14 = v44;
      v15 = v49;
      v49 = 0;
      if ( v15 )
        (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::PackageMonikerToPayload *))(*(_QWORD *)v15 + 16LL))(v15);
      MainPackage = MsixPackage::Provisioning::Library::MsixProvisioningRequest::GetMainPackage(v14, v10, &v49);
      v17 = MainPackage;
      if ( MainPackage < 0 )
      {
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          (void *)0x2D,
          (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningrequest.cpp",
          (const char *)(unsigned int)MainPackage,
          (int)"Failed to get main package.",
          v43);
        if ( v50 )
          (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::PackageMonikerToPayload *))(*(_QWORD *)v50 + 16LL))(v50);
        if ( v49 )
          (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::PackageMonikerToPayload *))(*(_QWORD *)v49 + 16LL))(v49);
        (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::CandidatePackages *))(*(_QWORD *)v10 + 16LL))(v10);
        if ( v14 )
          (*(void (__fastcall **)(MsixPackage::Provisioning::Library::MsixProvisioningRequest *))(*(_QWORD *)v14 + 16LL))(v14);
        return (unsigned int)v17;
      }
      if ( !v49 )
      {
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          (void *)0x30,
          (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningrequest.cpp",
          (const char *)0xC1570102LL,
          (int)"Failed to pick main package.",
          v43);
        if ( v50 )
          (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::PackageMonikerToPayload *))(*(_QWORD *)v50 + 16LL))(v50);
        if ( v49 )
          (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::PackageMonikerToPayload *))(*(_QWORD *)v49 + 16LL))(v49);
        (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::CandidatePackages *))(*(_QWORD *)v10 + 16LL))(v10);
        if ( !v14 )
          return 3243704578LL;
        goto LABEL_85;
      }
      v18 = (_QWORD *)((char *)v49 + 56);
      if ( *((_QWORD *)v49 + 10) >= 8u )
        v18 = (_QWORD *)*v18;
      *((_QWORD *)v14 + 8) = v18;
      v17 = MsixPackage::Provisioning::Library::MsixProvisioningRequest::AddPackage(v14, 0, v49, 0);
      if ( v17 < 0 )
      {
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          (void *)0x35,
          (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningrequest.cpp",
          (const char *)(unsigned int)v17,
          (int)"Failed to add main package for provisioning.",
          v43);
        if ( v50 )
          (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::PackageMonikerToPayload *))(*(_QWORD *)v50 + 16LL))(v50);
        if ( v49 )
          (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::PackageMonikerToPayload *))(*(_QWORD *)v49 + 16LL))(v49);
LABEL_265:
        (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::CandidatePackages *))(*(_QWORD *)v10 + 16LL))(v10);
        (*(void (__fastcall **)(MsixPackage::Provisioning::Library::MsixProvisioningRequest *))(*(_QWORD *)v14 + 16LL))(v14);
        return (unsigned int)v17;
      }
      goto LABEL_208;
    }
    if ( *((_QWORD *)a1 + 1) )
      PackagesFromReader = MsixPackage::Provisioning::Library::PackageSource::GetPackagesFromPath(a1, 2, v10);
    else
      PackagesFromReader = MsixPackage::Provisioning::Library::PackageSource::GetPackagesFromReader(
                             (__int64)a1,
                             2u,
                             v10);
    BundleManifestReader = PackagesFromReader;
    if ( PackagesFromReader >= 0 )
    {
      v14 = v44;
      v20 = v50;
      v50 = 0;
      if ( v20 )
        (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::PackageMonikerToPayload *))(*(_QWORD *)v20 + 16LL))(v20);
      v21 = MsixPackage::Provisioning::Library::MsixProvisioningRequest::GetMainPackage(v14, v10, &v50);
      BundleManifestReader = v21;
      if ( v21 >= 0 )
      {
        if ( !v50 )
        {
          wil::details::in1diag3::Return_HrMsg(
            retaddr,
            (void *)0x3E,
            (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningrequest.cpp",
            (const char *)0xC1570102LL,
            (int)"Failed to pick main package.",
            v43);
          if ( v50 )
            (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::PackageMonikerToPayload *))(*(_QWORD *)v50 + 16LL))(v50);
          if ( v49 )
            (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::PackageMonikerToPayload *))(*(_QWORD *)v49 + 16LL))(v49);
          (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::CandidatePackages *))(*(_QWORD *)v10 + 16LL))(v10);
          if ( !v14 )
            return 3243704578LL;
LABEL_85:
          (*(void (__fastcall **)(MsixPackage::Provisioning::Library::MsixProvisioningRequest *))(*(_QWORD *)v14 + 16LL))(v14);
          return 3243704578LL;
        }
        if ( *((_DWORD *)v50 + 30) )
        {
          v22 = (_QWORD *)((char *)v50 + 56);
          if ( *((_QWORD *)v50 + 10) >= 8u )
            v22 = (_QWORD *)*v22;
          *((_QWORD *)v14 + 8) = v22;
          v45 = 0;
          BundleManifestReader = MsixPackage::Provisioning::Library::PackageMonikerToPayload::GetBundleManifestReader(
                                   v50,
                                   &v45);
          if ( (BundleManifestReader & 0x80000000) == 0 )
          {
            v6 = v45;
            v17 = MsixPackage::Provisioning::Library::PackageSource::CalculateApplicablePackagesForBundle(a1, v45);
            if ( v17 < 0 )
            {
              wil::details::in1diag3::Return_HrMsg(
                retaddr,
                (void *)0x4A,
                (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningrequest.cpp",
                (const char *)(unsigned int)v17,
                (int)"Failed to calculate applicable packages for bundle.",
                v43);
              if ( v50 )
                (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::PackageMonikerToPayload *))(*(_QWORD *)v50 + 16LL))(v50);
              if ( v6 )
                ((void (__fastcall *)(struct IAppxBundleManifestReader *))v6->lpVtbl->Release)(v6);
              if ( v49 )
                (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::PackageMonikerToPayload *))(*(_QWORD *)v49 + 16LL))(v49);
              goto LABEL_265;
            }
            if ( *((_QWORD *)a1 + 1) )
              v23 = MsixPackage::Provisioning::Library::PackageSource::GetPackagesFromPath(a1, 3, v10);
            else
              v23 = MsixPackage::Provisioning::Library::PackageSource::GetPackagesFromReader((__int64)a1, 3u, v10);
            v17 = v23;
            if ( v23 < 0 )
            {
              wil::details::in1diag3::Return_HrMsg(
                retaddr,
                (void *)0x4D,
                (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningrequest.cpp",
                (const char *)(unsigned int)v23,
                (int)"Failed to get list of application packages.",
                v43);
              if ( v50 )
                (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::PackageMonikerToPayload *))(*(_QWORD *)v50 + 16LL))(v50);
              if ( v6 )
                ((void (__fastcall *)(struct IAppxBundleManifestReader *))v6->lpVtbl->Release)(v6);
              if ( v49 )
                (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::PackageMonikerToPayload *))(*(_QWORD *)v49 + 16LL))(v49);
              goto LABEL_265;
            }
            v24 = (const unsigned __int16 *)((char *)a1 + 56);
            if ( *((_QWORD *)a1 + 10) >= 8u )
              v24 = *(const unsigned __int16 **)v24;
            if ( v24 && *v24 )
            {
              v46 = 0;
              v25 = MsixPackage::Provisioning::Library::CContainer<MsixPackage::Provisioning::Library::MsixPackageAdapter,MsixPackage::Provisioning::Library::MsixAdapterCollection>::Item(
                      *((_QWORD *)v14 + 4),
                      0,
                      &v46);
              if ( v25 < 0 )
              {
                wil::details::in1diag3::Return_HrMsg(
                  retaddr,
                  (void *)0x56,
                  (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningrequest.cpp",
                  (const char *)(unsigned int)v25,
                  (int)"Failed to get package we just added",
                  v43);
                if ( v46 )
                  (*(void (__fastcall **)(MsixPackage::Provisioning::Library::MsixPackageAdapter *))(*(_QWORD *)v46 + 16LL))(v46);
                if ( v50 )
                  (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::PackageMonikerToPayload *))(*(_QWORD *)v50 + 16LL))(v50);
                if ( v6 )
                  ((void (__fastcall *)(struct IAppxBundleManifestReader *))v6->lpVtbl->Release)(v6);
                if ( v49 )
                  (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::PackageMonikerToPayload *))(*(_QWORD *)v49 + 16LL))(v49);
                goto LABEL_137;
              }
              v26 = v46;
              v17 = MsixPackage::Provisioning::Library::MsixPackageAdapter::ConvertToProvisionExistingFullBundle(
                      v46,
                      v24);
              if ( v17 < 0 )
              {
                wil::details::in1diag3::Return_HrMsg(
                  retaddr,
                  (void *)0x58,
                  (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningrequest.cpp",
                  (const char *)(unsigned int)v17,
                  (int)"Failed to convert to using existing full bundle",
                  v43);
                if ( v26 )
                  (*(void (__fastcall **)(MsixPackage::Provisioning::Library::MsixPackageAdapter *))(*(_QWORD *)v26 + 16LL))(v26);
                if ( v50 )
                  (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::PackageMonikerToPayload *))(*(_QWORD *)v50 + 16LL))(v50);
                if ( v6 )
                  ((void (__fastcall *)(struct IAppxBundleManifestReader *))v6->lpVtbl->Release)(v6);
                if ( v49 )
                  (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::PackageMonikerToPayload *))(*(_QWORD *)v49 + 16LL))(v49);
                goto LABEL_265;
              }
              v27 = (_QWORD *)((char *)v26 + 48);
              if ( *((_QWORD *)v26 + 9) >= 8u )
                v27 = (_QWORD *)*v27;
              *((_QWORD *)v14 + 8) = v27;
              *((_BYTE *)v14 + 72) = 1;
              v44 = 0;
              *a3 = v14;
              if ( v26 )
                (*(void (__fastcall **)(MsixPackage::Provisioning::Library::MsixPackageAdapter *))(*(_QWORD *)v26 + 16LL))(v26);
              if ( v50 )
                (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::PackageMonikerToPayload *))(*(_QWORD *)v50 + 16LL))(v50);
              if ( v6 )
                ((void (__fastcall *)(struct IAppxBundleManifestReader *))v6->lpVtbl->Release)(v6);
              if ( v49 )
                (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::PackageMonikerToPayload *))(*(_QWORD *)v49 + 16LL))(v49);
LABEL_249:
              (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::CandidatePackages *))(*(_QWORD *)v10 + 16LL))(v10);
              return 0;
            }
            v28 = v49;
            v29 = 0;
            v49 = 0;
            if ( v28 )
            {
              (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::PackageMonikerToPayload *))(*(_QWORD *)v28 + 16LL))(v28);
              v29 = v49;
            }
            v49 = 0;
            if ( v29 )
              (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::PackageMonikerToPayload *))(*(_QWORD *)v29 + 16LL))(v29);
            v17 = MsixPackage::Provisioning::Library::MsixProvisioningRequest::GetMainPackage(v14, v10, &v49);
            if ( v17 < 0 )
            {
              wil::details::in1diag3::Return_HrMsg(
                retaddr,
                (void *)0x64,
                (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningrequest.cpp",
                (const char *)(unsigned int)v17,
                (int)"Failed to get main application from bundle.",
                v43);
              if ( v50 )
                (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::PackageMonikerToPayload *))(*(_QWORD *)v50 + 16LL))(v50);
              if ( v6 )
                ((void (__fastcall *)(struct IAppxBundleManifestReader *))v6->lpVtbl->Release)(v6);
              if ( v49 )
                (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::PackageMonikerToPayload *))(*(_QWORD *)v49 + 16LL))(v49);
              goto LABEL_265;
            }
            v17 = MsixPackage::Provisioning::Library::MsixProvisioningRequest::AddPackage(v14, 1, v50, v49);
            if ( v17 < 0 )
            {
              wil::details::in1diag3::Return_HrMsg(
                retaddr,
                (void *)0x67,
                (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningrequest.cpp",
                (const char *)(unsigned int)v17,
                (int)"Failed to add main bundle package for provisioning.",
                v43);
              if ( v50 )
                (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::PackageMonikerToPayload *))(*(_QWORD *)v50 + 16LL))(v50);
              if ( v6 )
                ((void (__fastcall *)(struct IAppxBundleManifestReader *))v6->lpVtbl->Release)(v6);
              if ( v49 )
                (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::PackageMonikerToPayload *))(*(_QWORD *)v49 + 16LL))(v49);
              goto LABEL_265;
            }
            v17 = MsixPackage::Provisioning::Library::MsixProvisioningRequest::AddPackageToList(v14, v30, v31, v49);
            if ( v17 < 0 )
            {
              v32 = (char *)v49 + 56;
              if ( *((_QWORD *)v49 + 10) >= 8u )
                v32 = *(const char **)v32;
              wil::details::in1diag3::Return_HrMsg(
                retaddr,
                (void *)0x6D,
                (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningrequest.cpp",
                (const char *)(unsigned int)v17,
                (int)"Failed to add main application package %ws for provisioning.",
                v32);
              if ( v50 )
                (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::PackageMonikerToPayload *))(*(_QWORD *)v50 + 16LL))(v50);
              if ( v6 )
                ((void (__fastcall *)(struct IAppxBundleManifestReader *))v6->lpVtbl->Release)(v6);
              if ( v49 )
                (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::PackageMonikerToPayload *))(*(_QWORD *)v49 + 16LL))(v49);
              goto LABEL_265;
            }
            if ( *((_QWORD *)a1 + 1) )
              v33 = MsixPackage::Provisioning::Library::PackageSource::GetPackagesFromPath(a1, 4, v10);
            else
              v33 = MsixPackage::Provisioning::Library::PackageSource::GetPackagesFromReader((__int64)a1, 4u, v10);
            v17 = v33;
            if ( v33 < 0 )
            {
              wil::details::in1diag3::Return_HrMsg(
                retaddr,
                (void *)0x72,
                (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningrequest.cpp",
                (const char *)(unsigned int)v33,
                (int)"Failed to get resource packages.",
                v43);
              if ( v50 )
                (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::PackageMonikerToPayload *))(*(_QWORD *)v50 + 16LL))(v50);
              if ( v6 )
                ((void (__fastcall *)(struct IAppxBundleManifestReader *))v6->lpVtbl->Release)(v6);
              if ( v49 )
                (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::PackageMonikerToPayload *))(*(_QWORD *)v49 + 16LL))(v49);
              goto LABEL_265;
            }
            if ( (unsigned int)((__int64)(*((_QWORD *)v10 + 3) - *((_QWORD *)v10 + 2)) >> 3) )
            {
              while ( 1 )
              {
                v34 = v49;
                v35 = 0;
                v49 = 0;
                if ( v34 )
                {
                  (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::PackageMonikerToPayload *))(*(_QWORD *)v34 + 16LL))(v34);
                  v35 = v49;
                }
                v49 = 0;
                if ( v35 )
                  (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::PackageMonikerToPayload *))(*(_QWORD *)v35 + 16LL))(v35);
                v17 = MsixPackage::Provisioning::Library::CContainer<MsixPackage::Provisioning::Library::MsixPackageAdapter,MsixPackage::Provisioning::Library::MsixAdapterCollection>::Item(
                        v10,
                        v5,
                        &v49);
                if ( v17 < 0 )
                  break;
                v17 = MsixPackage::Provisioning::Library::MsixProvisioningRequest::AddPackage(v14, 2, v49, 0);
                if ( v17 < 0 )
                {
                  v37 = (char *)v49 + 56;
                  if ( *((_QWORD *)v49 + 10) >= 8u )
                    v37 = *(const char **)v37;
                  wil::details::in1diag3::Return_HrMsg(
                    retaddr,
                    (void *)0x7C,
                    (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningrequest.cpp",
                    (const char *)(unsigned int)v17,
                    (int)"Failed to add resource package %ws for provisioning.",
                    v37);
                  if ( v50 )
                    (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::PackageMonikerToPayload *))(*(_QWORD *)v50 + 16LL))(v50);
                  if ( v6 )
                    ((void (__fastcall *)(struct IAppxBundleManifestReader *))v6->lpVtbl->Release)(v6);
                  if ( v49 )
                    (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::PackageMonikerToPayload *))(*(_QWORD *)v49 + 16LL))(v49);
                  goto LABEL_265;
                }
                if ( ++v5 >= (unsigned int)((__int64)(*((_QWORD *)v10 + 3) - *((_QWORD *)v10 + 2)) >> 3) )
                  goto LABEL_208;
              }
              wil::details::in1diag3::Return_HrMsg(
                retaddr,
                (void *)0x77,
                (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningrequest.cpp",
                (const char *)(unsigned int)v17,
                (int)"Failed to get resource package from collection for provisioning.",
                v43);
              if ( v50 )
                (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::PackageMonikerToPayload *))(*(_QWORD *)v50 + 16LL))(v50);
              if ( v6 )
                ((void (__fastcall *)(struct IAppxBundleManifestReader *))v6->lpVtbl->Release)(v6);
              if ( v49 )
                (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::PackageMonikerToPayload *))(*(_QWORD *)v49 + 16LL))(v49);
              goto LABEL_265;
            }
LABEL_208:
            if ( *((_QWORD *)a1 + 1) )
              v36 = MsixPackage::Provisioning::Library::PackageSource::GetPackagesFromPath(a1, 1, v10);
            else
              v36 = MsixPackage::Provisioning::Library::PackageSource::GetPackagesFromReader((__int64)a1, 1u, v10);
            v25 = v36;
            if ( v36 < 0 )
            {
              wil::details::in1diag3::Return_HrMsg(
                retaddr,
                (void *)0x83,
                (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningrequest.cpp",
                (const char *)(unsigned int)v36,
                (int)"Failed to get dependency packages.",
                v43);
              if ( v50 )
                (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::PackageMonikerToPayload *))(*(_QWORD *)v50 + 16LL))(v50);
              if ( v6 )
                ((void (__fastcall *)(struct IAppxBundleManifestReader *))v6->lpVtbl->Release)(v6);
              if ( v49 )
                (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::PackageMonikerToPayload *))(*(_QWORD *)v49 + 16LL))(v49);
LABEL_137:
              (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::CandidatePackages *))(*(_QWORD *)v10 + 16LL))(v10);
              (*(void (__fastcall **)(MsixPackage::Provisioning::Library::MsixProvisioningRequest *))(*(_QWORD *)v14 + 16LL))(v14);
              return (unsigned int)v25;
            }
            v38 = 0;
            if ( (unsigned int)((__int64)(*((_QWORD *)v10 + 3) - *((_QWORD *)v10 + 2)) >> 3) )
            {
              while ( 1 )
              {
                v39 = v49;
                v40 = 0;
                v49 = 0;
                if ( v39 )
                {
                  (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::PackageMonikerToPayload *))(*(_QWORD *)v39 + 16LL))(v39);
                  v40 = v49;
                }
                v49 = 0;
                if ( v40 )
                  (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::PackageMonikerToPayload *))(*(_QWORD *)v40 + 16LL))(v40);
                v17 = MsixPackage::Provisioning::Library::CContainer<MsixPackage::Provisioning::Library::MsixPackageAdapter,MsixPackage::Provisioning::Library::MsixAdapterCollection>::Item(
                        v10,
                        v38,
                        &v49);
                if ( v17 < 0 )
                  break;
                v17 = MsixPackage::Provisioning::Library::MsixProvisioningRequest::AddPackage(v14, 3, v49, 0);
                if ( v17 < 0 )
                {
                  v41 = (char *)v49 + 56;
                  if ( *((_QWORD *)v49 + 10) >= 8u )
                    v41 = *(const char **)v41;
                  wil::details::in1diag3::Return_HrMsg(
                    retaddr,
                    (void *)0x8D,
                    (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningrequest.cpp",
                    (const char *)(unsigned int)v17,
                    (int)"Failed to add dependency package %ws for provisioning.",
                    v41);
                  if ( v50 )
                    (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::PackageMonikerToPayload *))(*(_QWORD *)v50 + 16LL))(v50);
                  if ( v6 )
                    ((void (__fastcall *)(struct IAppxBundleManifestReader *))v6->lpVtbl->Release)(v6);
                  if ( v49 )
                    (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::PackageMonikerToPayload *))(*(_QWORD *)v49 + 16LL))(v49);
                  goto LABEL_265;
                }
                if ( ++v38 >= (unsigned int)((__int64)(*((_QWORD *)v10 + 3) - *((_QWORD *)v10 + 2)) >> 3) )
                  goto LABEL_243;
              }
              wil::details::in1diag3::Return_HrMsg(
                retaddr,
                (void *)0x88,
                (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningrequest.cpp",
                (const char *)(unsigned int)v17,
                (int)"Failed to get dependency package from collection for provisioning.",
                v43);
              if ( v50 )
                (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::PackageMonikerToPayload *))(*(_QWORD *)v50 + 16LL))(v50);
              if ( v6 )
                ((void (__fastcall *)(struct IAppxBundleManifestReader *))v6->lpVtbl->Release)(v6);
              if ( v49 )
                (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::PackageMonikerToPayload *))(*(_QWORD *)v49 + 16LL))(v49);
              goto LABEL_265;
            }
LABEL_243:
            v44 = 0;
            *a3 = v14;
            if ( v50 )
              (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::PackageMonikerToPayload *))(*(_QWORD *)v50 + 16LL))(v50);
            if ( v6 )
              ((void (__fastcall *)(struct IAppxBundleManifestReader *))v6->lpVtbl->Release)(v6);
            if ( v49 )
              (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::PackageMonikerToPayload *))(*(_QWORD *)v49 + 16LL))(v49);
            goto LABEL_249;
          }
          wil::details::in1diag3::Return_HrMsg(
            retaddr,
            (void *)0x47,
            (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningrequest.cpp",
            (const char *)BundleManifestReader,
            (int)"Failed to get bundle manifest reader for bundle.",
            v43);
          if ( v50 )
            (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::PackageMonikerToPayload *))(*(_QWORD *)v50 + 16LL))(v50);
          if ( v45 )
            ((void (__fastcall *)(struct IAppxBundleManifestReader *))v45->lpVtbl->Release)(v45);
          if ( v49 )
            (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::PackageMonikerToPayload *))(*(_QWORD *)v49 + 16LL))(v49);
          (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::CandidatePackages *))(*(_QWORD *)v10 + 16LL))(v10);
          (*(void (__fastcall **)(MsixPackage::Provisioning::Library::MsixProvisioningRequest *))(*(_QWORD *)v14 + 16LL))(v14);
        }
        else
        {
          BundleManifestReader = -2147024846;
          wil::details::in1diag3::Return_HrMsg(
            retaddr,
            (void *)0x42,
            (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningrequest.cpp",
            (const char *)0x80070032LL,
            (int)"Loose files not supported for bundle packages.",
            v43);
          if ( v50 )
            (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::PackageMonikerToPayload *))(*(_QWORD *)v50 + 16LL))(v50);
          if ( v49 )
            (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::PackageMonikerToPayload *))(*(_QWORD *)v49 + 16LL))(v49);
          (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::CandidatePackages *))(*(_QWORD *)v10 + 16LL))(v10);
          if ( v14 )
            (*(void (__fastcall **)(MsixPackage::Provisioning::Library::MsixProvisioningRequest *))(*(_QWORD *)v14 + 16LL))(v14);
        }
      }
      else
      {
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          (void *)0x3A,
          (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningrequest.cpp",
          (const char *)(unsigned int)v21,
          (int)"Failed to get main package.",
          v43);
        if ( v50 )
          (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::PackageMonikerToPayload *))(*(_QWORD *)v50 + 16LL))(v50);
        if ( v49 )
          (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::PackageMonikerToPayload *))(*(_QWORD *)v49 + 16LL))(v49);
        (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::CandidatePackages *))(*(_QWORD *)v10 + 16LL))(v10);
        if ( v14 )
          (*(void (__fastcall **)(MsixPackage::Provisioning::Library::MsixProvisioningRequest *))(*(_QWORD *)v14 + 16LL))(v14);
      }
    }
    else
    {
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x39,
        (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningrequest.cpp",
        (const char *)(unsigned int)PackagesFromReader,
        (int)"Failed to get list of main bundle packages.",
        v43);
      if ( v50 )
        (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::PackageMonikerToPayload *))(*(_QWORD *)v50 + 16LL))(v50);
      if ( v49 )
        (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::PackageMonikerToPayload *))(*(_QWORD *)v49 + 16LL))(v49);
      (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::CandidatePackages *))(*(_QWORD *)v10 + 16LL))(v10);
      if ( v44 )
        (*(void (__fastcall **)(MsixPackage::Provisioning::Library::MsixProvisioningRequest *))(*(_QWORD *)v44 + 16LL))(v44);
    }
    return BundleManifestReader;
  }
  wil::details::in1diag3::Return_HrMsg(
    retaddr,
    (void *)0x29,
    (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningrequest.cpp",
    (const char *)(unsigned int)PackagesFromPath,
    (int)"Failed to get list of main packages.",
    v43);
  if ( v50 )
    (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::PackageMonikerToPayload *))(*(_QWORD *)v50 + 16LL))(v50);
  if ( v49 )
    (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::PackageMonikerToPayload *))(*(_QWORD *)v49 + 16LL))(v49);
  (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::CandidatePackages *))(*(_QWORD *)v10 + 16LL))(v10);
  if ( v44 )
    (*(void (__fastcall **)(MsixPackage::Provisioning::Library::MsixProvisioningRequest *))(*(_QWORD *)v44 + 16LL))(v44);
  return v13;
}

```

## disassembly

```asm
0x180053b30  mov     [rsp-38h+arg_0], rbx
0x180053b35  push    rbp
0x180053b36  push    rsi
0x180053b37  push    rdi
0x180053b38  push    r12
0x180053b3a  push    r13
0x180053b3c  push    r14
0x180053b3e  push    r15
0x180053b40  mov     rbp, rsp
0x180053b43  sub     rsp, 50h
0x180053b47  mov     r13, r8
0x180053b4a  mov     rax, rdx
0x180053b4d  mov     rdi, rcx
0x180053b50  xor     r12d, r12d
0x180053b53  mov     [rbp+var_8], r12
0x180053b57  mov     [rbp+arg_10], r12
0x180053b5b  mov     ebx, r12d
0x180053b5e  mov     [rbp+var_18], rbx
0x180053b62  mov     [rbp+arg_18], r12
0x180053b66  mov     [r8], r12
0x180053b69  mov     [rbp+var_20], r12
0x180053b6d  lea     rdx, [rbp+var_20]
0x180053b71  mov     rcx, rax
0x180053b74  call    ??$Make@VMsixProvisioningRequest@Library@Provisioning@MsixPackage@@@MsixAdapterBase@Library@Provisioning@MsixPackage@@SAJPEAVMsixProvisioningContext@123@PEAPEAVMsixProvisioningRequest@123@@Z; MsixPackage::Provisioning::Library::MsixAdapterBase::Make<MsixPackage::Provisioning::Library::MsixProvisioningRequest>(MsixPackage::Provisioning::Library::MsixProvisioningContext *,MsixPackage::Provisioning::Library::MsixProvisioningRequest * *)
0x180053b79  mov     esi, eax
0x180053b7b  test    eax, eax
0x180053b7d  jns     short loc_180053BED
0x180053b7f  mov     rcx, [rbp+38h]; this
0x180053b83  lea     rax, aFailedToCreate_24; "Failed to create package set."
0x180053b8a  mov     qword ptr [rsp+50h+var_30], rax; int
0x180053b8f  mov     r9d, esi; char *
0x180053b92  lea     r8, aOnecoreAdminAp_11; "onecore\\admin\\appmodel\\utilities\\pr"...
0x180053b99  lea     edx, [r12+24h]; void *
0x180053b9e  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180053ba3  nop
0x180053ba4  mov     rcx, [rbp+arg_18]
0x180053ba8  test    rcx, rcx
0x180053bab  jz      short loc_180053BBA
0x180053bad  mov     rax, [rcx]
0x180053bb0  mov     rax, [rax+10h]
0x180053bb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053bb9  nop
0x180053bba  mov     rcx, [rbp+arg_10]
0x180053bbe  test    rcx, rcx
0x180053bc1  jz      short loc_180053BD0
0x180053bc3  mov     rax, [rcx]
0x180053bc6  mov     rax, [rax+10h]
0x180053bca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053bcf  nop
0x180053bd0  mov     rcx, [rbp+var_20]
0x180053bd4  test    rcx, rcx
0x180053bd7  jz      short loc_180053BE6
0x180053bd9  mov     rax, [rcx]
0x180053bdc  mov     rax, [rax+10h]
0x180053be0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053be5  nop
0x180053be6  mov     eax, esi
0x180053be8  jmp     loc_180054C74
0x180053bed  mov     [rbp+var_8], r12
0x180053bf1  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180053bf8  mov     ecx, 30h ; '0'; unsigned __int64
0x180053bfd  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180053c02  mov     rsi, rax
0x180053c05  test    rax, rax
0x180053c08  jz      short loc_180053C2A
0x180053c0a  mov     [rax+8], r12
0x180053c0e  mov     [rax+10h], r12
0x180053c12  mov     [rax+18h], r12
0x180053c16  mov     [rax+20h], r12
0x180053c1a  mov     [rax+28h], r12
0x180053c1e  lea     rax, ??_7CandidatePackages@Library@Provisioning@MsixPackage@@6B@; const MsixPackage::Provisioning::Library::CandidatePackages::`vftable'
0x180053c25  mov     [rsi], rax
0x180053c28  jmp     short loc_180053C2D
0x180053c2a  mov     rsi, r12
0x180053c2d  test    rsi, rsi
0x180053c30  jz      short loc_180053C42
0x180053c32  mov     rax, [rsi]
0x180053c35  mov     rcx, rsi
0x180053c38  mov     rax, [rax+8]
0x180053c3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053c41  nop
0x180053c42  test    rsi, rsi
0x180053c45  jnz     loc_180053CD5
0x180053c4b  mov     rcx, [rbp+38h]; this
0x180053c4f  mov     ebx, 8007000Eh
0x180053c54  mov     r9d, ebx; char *
0x180053c57  lea     r8, aOnecoreAdminAp_7; "onecore\\admin\\appmodel\\utilities\\pr"...
0x180053c5e  mov     edx, 1B3h; void *
0x180053c63  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180053c68  nop
0x180053c69  mov     rcx, [rbp+38h]; this
0x180053c6d  lea     rax, aFailedToCreate_21; "Failed to create list of candidate pack"...
0x180053c74  mov     qword ptr [rsp+50h+var_30], rax; int
0x180053c79  mov     r9d, ebx; char *
0x180053c7c  lea     r8, aOnecoreAdminAp_11; "onecore\\admin\\appmodel\\utilities\\pr"...
0x180053c83  lea     edx, [rsi+26h]; void *
0x180053c86  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180053c8b  nop
0x180053c8c  mov     rcx, [rbp+arg_18]
0x180053c90  test    rcx, rcx
0x180053c93  jz      short loc_180053CA2
0x180053c95  mov     rax, [rcx]
0x180053c98  mov     rax, [rax+10h]
0x180053c9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053ca1  nop
0x180053ca2  mov     rcx, [rbp+arg_10]
0x180053ca6  test    rcx, rcx
0x180053ca9  jz      short loc_180053CB8
0x180053cab  mov     rax, [rcx]
0x180053cae  mov     rax, [rax+10h]
0x180053cb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053cb7  nop
0x180053cb8  mov     rcx, [rbp+var_20]
0x180053cbc  test    rcx, rcx
0x180053cbf  jz      short loc_180053CCE
0x180053cc1  mov     rdx, [rcx]
0x180053cc4  mov     rax, [rdx+10h]
0x180053cc8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053ccd  nop
0x180053cce  mov     eax, ebx
0x180053cd0  jmp     loc_180054C74
0x180053cd5  mov     [rbp+var_8], rsi
0x180053cd9  mov     r8, rsi
0x180053cdc  xor     edx, edx
0x180053cde  mov     rcx, rdi
0x180053ce1  cmp     [rdi+8], r12
0x180053ce5  jz      short loc_180053CEE
0x180053ce7  call    ?GetPackagesFromPath@PackageSource@Library@Provisioning@MsixPackage@@AEAAJW4PackageType@234@PEAVCandidatePackages@234@@Z; MsixPackage::Provisioning::Library::PackageSource::GetPackagesFromPath(MsixPackage::Provisioning::Library::PackageType,MsixPackage::Provisioning::Library::CandidatePackages *)
0x180053cec  jmp     short loc_180053CF3
0x180053cee  call    ?GetPackagesFromReader@PackageSource@Library@Provisioning@MsixPackage@@AEAAJW4PackageType@234@PEAVCandidatePackages@234@@Z; MsixPackage::Provisioning::Library::PackageSource::GetPackagesFromReader(MsixPackage::Provisioning::Library::PackageType,MsixPackage::Provisioning::Library::CandidatePackages *)
0x180053cf3  mov     r14d, eax
0x180053cf6  test    eax, eax
0x180053cf8  jns     short loc_180053D79
0x180053cfa  mov     rcx, [rbp+38h]; this
0x180053cfe  lea     rax, aFailedToGetLis_2; "Failed to get list of main packages."
0x180053d05  mov     qword ptr [rsp+50h+var_30], rax; int
0x180053d0a  mov     r9d, r14d; char *
0x180053d0d  lea     r8, aOnecoreAdminAp_11; "onecore\\admin\\appmodel\\utilities\\pr"...
0x180053d14  mov     edx, 29h ; ')'; void *
0x180053d19  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180053d1e  nop
0x180053d1f  mov     rcx, [rbp+arg_18]
0x180053d23  test    rcx, rcx
0x180053d26  jz      short loc_180053D35
0x180053d28  mov     rax, [rcx]
0x180053d2b  mov     rax, [rax+10h]
0x180053d2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053d34  nop
0x180053d35  mov     rcx, [rbp+arg_10]
0x180053d39  test    rcx, rcx
0x180053d3c  jz      short loc_180053D4B
0x180053d3e  mov     rax, [rcx]
0x180053d41  mov     rax, [rax+10h]
0x180053d45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053d4a  nop
0x180053d4b  mov     rax, [rsi]
0x180053d4e  mov     rcx, rsi
0x180053d51  mov     rax, [rax+10h]
0x180053d55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053d5a  nop
0x180053d5b  mov     rcx, [rbp+var_20]
0x180053d5f  test    rcx, rcx
0x180053d62  jz      short loc_180053D71
0x180053d64  mov     rax, [rcx]
0x180053d67  mov     rax, [rax+10h]
0x180053d6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053d70  nop
0x180053d71  mov     eax, r14d
0x180053d74  jmp     loc_180054C74
0x180053d79  mov     rax, [rsi+18h]
0x180053d7d  sub     rax, [rsi+10h]
0x180053d81  sar     rax, 3
0x180053d85  test    eax, eax
0x180053d87  jz      loc_180053F65
0x180053d8d  mov     r14, [rbp+var_20]
0x180053d91  mov     rcx, [rbp+arg_10]
0x180053d95  mov     [rbp+arg_10], r12
0x180053d99  test    rcx, rcx
0x180053d9c  jz      short loc_180053DAB
0x180053d9e  mov     rax, [rcx]
0x180053da1  mov     rax, [rax+10h]
0x180053da5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053daa  nop
0x180053dab  lea     r8, [rbp+arg_10]; struct MsixPackage::Provisioning::Library::PackageMonikerToPayload **
0x180053daf  mov     rdx, rsi; struct MsixPackage::Provisioning::Library::CandidatePackages *
0x180053db2  mov     rcx, r14; this
0x180053db5  call    ?GetMainPackage@MsixProvisioningRequest@Library@Provisioning@MsixPackage@@AEAAJPEAVCandidatePackages@234@PEAPEAVPackageMonikerToPayload@234@@Z; MsixPackage::Provisioning::Library::MsixProvisioningRequest::GetMainPackage(MsixPackage::Provisioning::Library::CandidatePackages *,MsixPackage::Provisioning::Library::PackageMonikerToPayload * *)
0x180053dba  mov     r15d, eax
0x180053dbd  test    eax, eax
0x180053dbf  jns     short loc_180053E3F
0x180053dc1  mov     rcx, [rbp+38h]; this
0x180053dc5  lea     rdx, aFailedToGetMai_1; "Failed to get main package."
0x180053dcc  mov     qword ptr [rsp+50h+var_30], rdx; int
0x180053dd1  mov     r9d, eax; char *
0x180053dd4  lea     r8, aOnecoreAdminAp_11; "onecore\\admin\\appmodel\\utilities\\pr"...
0x180053ddb  mov     edx, 2Dh ; '-'; void *
0x180053de0  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180053de5  nop
0x180053de6  mov     rcx, [rbp+arg_18]
0x180053dea  test    rcx, rcx
0x180053ded  jz      short loc_180053DFC
0x180053def  mov     rax, [rcx]
0x180053df2  mov     rax, [rax+10h]
0x180053df6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053dfb  nop
0x180053dfc  mov     rcx, [rbp+arg_10]
0x180053e00  test    rcx, rcx
0x180053e03  jz      short loc_180053E12
0x180053e05  mov     rax, [rcx]
0x180053e08  mov     rax, [rax+10h]
0x180053e0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053e11  nop
0x180053e12  mov     rax, [rsi]
0x180053e15  mov     rcx, rsi
0x180053e18  mov     rax, [rax+10h]
0x180053e1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053e21  nop
0x180053e22  test    r14, r14
0x180053e25  jz      short loc_180053E37
0x180053e27  mov     rax, [r14]
0x180053e2a  mov     rcx, r14
0x180053e2d  mov     rax, [rax+10h]
0x180053e31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053e36  nop
0x180053e37  mov     eax, r15d
0x180053e3a  jmp     loc_180054C74
0x180053e3f  mov     rax, [rbp+arg_10]
0x180053e43  test    rax, rax
0x180053e46  jnz     short loc_180053EC1
0x180053e48  mov     rcx, [rbp+38h]; this
0x180053e4c  lea     rax, aFailedToPickMa; "Failed to pick main package."
0x180053e53  mov     qword ptr [rsp+50h+var_30], rax; int
0x180053e58  mov     r9d, 0C1570102h; char *
0x180053e5e  lea     r8, aOnecoreAdminAp_11; "onecore\\admin\\appmodel\\utilities\\pr"...
0x180053e65  mov     edx, 30h ; '0'; void *
0x180053e6a  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180053e6f  nop
0x180053e70  mov     rcx, [rbp+arg_18]
0x180053e74  test    rcx, rcx
0x180053e77  jz      short loc_180053E86
0x180053e79  mov     rax, [rcx]
0x180053e7c  mov     rax, [rax+10h]
0x180053e80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053e85  nop
0x180053e86  mov     rcx, [rbp+arg_10]
0x180053e8a  test    rcx, rcx
0x180053e8d  jz      short loc_180053E9C
0x180053e8f  mov     rax, [rcx]
0x180053e92  mov     rax, [rax+10h]
0x180053e96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053e9b  nop
0x180053e9c  mov     rax, [rsi]
0x180053e9f  mov     rcx, rsi
0x180053ea2  mov     rax, [rax+10h]
0x180053ea6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053eab  nop
0x180053eac  test    r14, r14
0x180053eaf  jz      loc_180054138
0x180053eb5  mov     rax, [r14]
0x180053eb8  mov     rax, [rax+10h]
0x180053ebc  jmp     loc_18005412F
0x180053ec1  add     rax, 38h ; '8'
0x180053ec5  cmp     qword ptr [rax+18h], 8
0x180053eca  jb      short loc_180053ECF
0x180053ecc  mov     rax, [rax]
0x180053ecf  mov     [r14+40h], rax
0x180053ed3  xor     r9d, r9d
0x180053ed6  mov     r8, [rbp+arg_10]
0x180053eda  xor     edx, edx
0x180053edc  mov     rcx, r14
0x180053edf  call    ?AddPackage@MsixProvisioningRequest@Library@Provisioning@MsixPackage@@AEAAJW4APPX_PACKAGE_TARGET_TYPE@234@PEAVPackageMonikerToPayload@234@1@Z; MsixPackage::Provisioning::Library::MsixProvisioningRequest::AddPackage(MsixPackage::Provisioning::Library::APPX_PACKAGE_TARGET_TYPE,MsixPackage::Provisioning::Library::PackageMonikerToPayload *,MsixPackage::Provisioning::Library::PackageMonikerToPayload *)
0x180053ee4  mov     r15d, eax
0x180053ee7  test    eax, eax
0x180053ee9  jns     loc_180054996
0x180053eef  mov     rcx, [rbp+38h]; this
0x180053ef3  lea     rax, aFailedToAddMai_1; "Failed to add main package for provisio"...
0x180053efa  mov     qword ptr [rsp+50h+var_30], rax; int
0x180053eff  mov     r9d, r15d; char *
0x180053f02  lea     r8, aOnecoreAdminAp_11; "onecore\\admin\\appmodel\\utilities\\pr"...
0x180053f09  mov     edx, 35h ; '5'; void *
0x180053f0e  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180053f13  nop
0x180053f14  mov     rcx, [rbp+arg_18]
0x180053f18  test    rcx, rcx
0x180053f1b  jz      short loc_180053F2A
0x180053f1d  mov     rax, [rcx]
0x180053f20  mov     rax, [rax+10h]
0x180053f24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053f29  nop
0x180053f2a  mov     rcx, [rbp+arg_10]
0x180053f2e  test    rcx, rcx
0x180053f31  jz      short loc_180053F40
0x180053f33  mov     rax, [rcx]
0x180053f36  mov     rax, [rax+10h]
0x180053f3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053f3f  nop
0x180053f40  mov     rax, [rsi]
0x180053f43  mov     rcx, rsi
0x180053f46  mov     rax, [rax+10h]
0x180053f4a  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
