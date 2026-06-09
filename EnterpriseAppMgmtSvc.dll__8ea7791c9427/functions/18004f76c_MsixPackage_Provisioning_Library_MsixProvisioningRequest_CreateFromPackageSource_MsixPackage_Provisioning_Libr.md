# MsixPackage::Provisioning::Library::MsixProvisioningRequest::CreateFromPackageSource(MsixPackage::Provisioning::Library::PackageSource *,MsixPackage::Provisioning::Library::MsixProvisioningContext *,MsixPackage::Provisioning::Library::MsixProvisioningRequest * *)

- ea: `0x18004f76c`
- end: `0x1800509f5`
- name: `?CreateFromPackageSource@MsixProvisioningRequest@Library@Provisioning@MsixPackage@@SAJPEAVPackageSource@234@PEAVMsixProvisioningContext@234@PEAPEAV1234@@Z`
- size: `4745`
- prototype: `__int64 __fastcall(struct MsixPackage::Provisioning::Library::PackageSource *, struct MsixPackage::Provisioning::Library::MsixProvisioningContext *, struct MsixPackage::Provisioning::Library::MsixProvisioningRequest **)`
- caller_count: `2`
- callee_count: `15`
- tags: `registry_config, installer_update`

## callers

- `0x180032f28`
- `0x1800441c8`

## callees

- `0x180002368`
- `0x18000cfe8`
- `0x1800319dc`
- `0x180038d54`
- `0x180039e9c`
- `0x180041c60`
- `0x18004e1fc`
- `0x18004e554`
- `0x18004f76c`
- `0x180050ad0`
- `0x1800544e0`
- `0x1800560f8`
- `0x18005647c`
- `0x180056d60`
- `0x18006a010`

## string_xrefs

- `0x18004f893`: `onecore\admin\appmodel\utilities\provisionhelper\MsixPackageAdapter.h`
- `0x18004f8a9`: `Failed to create list of candidate packages.`
- `0x18004f7ce`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningrequest.cpp`
- `0x18004f8b8`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningrequest.cpp`
- `0x18004f949`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningrequest.cpp`
- `0x18004fa10`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningrequest.cpp`
- `0x18004fa9a`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningrequest.cpp`
- `0x18004fb3e`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningrequest.cpp`
- `0x18004fbd7`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningrequest.cpp`
- `0x18004fc86`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningrequest.cpp`
- `0x18004fd11`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningrequest.cpp`
- `0x18004fda0`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningrequest.cpp`
- `0x18004fe48`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningrequest.cpp`
- `0x18004feee`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningrequest.cpp`
- `0x18004ffa1`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningrequest.cpp`
- `0x18005006a`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningrequest.cpp`
- `0x180050127`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningrequest.cpp`
- `0x1800502a4`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningrequest.cpp`
- `0x18005034f`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningrequest.cpp`
- `0x180050408`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningrequest.cpp`
- `0x1800504bb`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningrequest.cpp`
- `0x18005061b`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningrequest.cpp`
- `0x1800506a6`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningrequest.cpp`
- `0x180050740`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningrequest.cpp`
- `0x1800508f2`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningrequest.cpp`
- `0x18005097d`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningrequest.cpp`
- `0x18004f7bf`: `Failed to create package set.`
- `0x18004fe39`: `Failed to get bundle manifest reader for bundle.`

## pseudocode

```c
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
  char *v24; // r15
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
         (__int64)a2,
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
    PackagesFromPath = MsixPackage::Provisioning::Library::PackageSource::GetPackagesFromReader(a1, 0, v10);
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
      v17 = MsixPackage::Provisioning::Library::MsixProvisioningRequest::AddPackage(
              (struct MsixPackage::Provisioning::Library::MsixProvisioningContext **)v14,
              0,
              (__int64)v49,
              0);
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
      PackagesFromReader = MsixPackage::Provisioning::Library::PackageSource::GetPackagesFromReader(a1, 2, v10);
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
              v23 = MsixPackage::Provisioning::Library::PackageSource::GetPackagesFromReader(a1, 3, v10);
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
            v24 = (char *)a1 + 56;
            if ( *((_QWORD *)a1 + 10) >= 8u )
              v24 = *(char **)v24;
            if ( v24 && *(_WORD *)v24 )
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
            v17 = MsixPackage::Provisioning::Library::MsixProvisioningRequest::AddPackage(
                    (struct MsixPackage::Provisioning::Library::MsixProvisioningContext **)v14,
                    1u,
                    (__int64)v50,
                    (__int64)v49);
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
            v17 = MsixPackage::Provisioning::Library::MsixProvisioningRequest::AddPackageToList(
                    (__int64)v14,
                    v30,
                    v31,
                    (__int64)v49);
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
              v33 = MsixPackage::Provisioning::Library::PackageSource::GetPackagesFromReader(a1, 4, v10);
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
                v17 = MsixPackage::Provisioning::Library::MsixProvisioningRequest::AddPackage(
                        (struct MsixPackage::Provisioning::Library::MsixProvisioningContext **)v14,
                        2u,
                        (__int64)v49,
                        0);
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
              v36 = MsixPackage::Provisioning::Library::PackageSource::GetPackagesFromReader(a1, 1, v10);
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
                v17 = MsixPackage::Provisioning::Library::MsixProvisioningRequest::AddPackage(
                        (struct MsixPackage::Provisioning::Library::MsixProvisioningContext **)v14,
                        3u,
                        (__int64)v49,
                        0);
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
0x18004f76c  mov     [rsp-38h+arg_0], rbx
0x18004f771  push    rbp
0x18004f772  push    rsi
0x18004f773  push    rdi
0x18004f774  push    r12
0x18004f776  push    r13
0x18004f778  push    r14
0x18004f77a  push    r15
0x18004f77c  mov     rbp, rsp
0x18004f77f  sub     rsp, 50h
0x18004f783  mov     r13, r8
0x18004f786  mov     rax, rdx
0x18004f789  mov     rdi, rcx
0x18004f78c  xor     r12d, r12d
0x18004f78f  mov     [rbp+var_8], r12
0x18004f793  mov     [rbp+arg_10], r12
0x18004f797  mov     ebx, r12d
0x18004f79a  mov     [rbp+var_18], rbx
0x18004f79e  mov     [rbp+arg_18], r12
0x18004f7a2  mov     [r8], r12
0x18004f7a5  mov     [rbp+var_20], r12
0x18004f7a9  lea     rdx, [rbp+var_20]
0x18004f7ad  mov     rcx, rax
0x18004f7b0  call    ??$Make@VMsixProvisioningRequest@Library@Provisioning@MsixPackage@@@MsixAdapterBase@Library@Provisioning@MsixPackage@@SAJPEAVMsixProvisioningContext@123@PEAPEAVMsixProvisioningRequest@123@@Z; MsixPackage::Provisioning::Library::MsixAdapterBase::Make<MsixPackage::Provisioning::Library::MsixProvisioningRequest>(MsixPackage::Provisioning::Library::MsixProvisioningContext *,MsixPackage::Provisioning::Library::MsixProvisioningRequest * *)
0x18004f7b5  mov     esi, eax
0x18004f7b7  test    eax, eax
0x18004f7b9  jns     short loc_18004F829
0x18004f7bb  mov     rcx, [rbp+38h]; this
0x18004f7bf  lea     rax, aFailedToCreate_24; "Failed to create package set."
0x18004f7c6  mov     qword ptr [rsp+50h+var_30], rax; int
0x18004f7cb  mov     r9d, esi; char *
0x18004f7ce  lea     r8, aOnecoreAdminAp_11; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18004f7d5  lea     edx, [r12+24h]; void *
0x18004f7da  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18004f7df  nop
0x18004f7e0  mov     rcx, [rbp+arg_18]
0x18004f7e4  test    rcx, rcx
0x18004f7e7  jz      short loc_18004F7F6
0x18004f7e9  mov     rax, [rcx]
0x18004f7ec  mov     rax, [rax+10h]
0x18004f7f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f7f5  nop
0x18004f7f6  mov     rcx, [rbp+arg_10]
0x18004f7fa  test    rcx, rcx
0x18004f7fd  jz      short loc_18004F80C
0x18004f7ff  mov     rax, [rcx]
0x18004f802  mov     rax, [rax+10h]
0x18004f806  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f80b  nop
0x18004f80c  mov     rcx, [rbp+var_20]
0x18004f810  test    rcx, rcx
0x18004f813  jz      short loc_18004F822
0x18004f815  mov     rax, [rcx]
0x18004f818  mov     rax, [rax+10h]
0x18004f81c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f821  nop
0x18004f822  mov     eax, esi
0x18004f824  jmp     loc_1800508B0
0x18004f829  mov     [rbp+var_8], r12
0x18004f82d  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18004f834  mov     ecx, 30h ; '0'; unsigned __int64
0x18004f839  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18004f83e  mov     rsi, rax
0x18004f841  test    rax, rax
0x18004f844  jz      short loc_18004F866
0x18004f846  mov     [rax+8], r12
0x18004f84a  mov     [rax+10h], r12
0x18004f84e  mov     [rax+18h], r12
0x18004f852  mov     [rax+20h], r12
0x18004f856  mov     [rax+28h], r12
0x18004f85a  lea     rax, ??_7CandidatePackages@Library@Provisioning@MsixPackage@@6B@; const MsixPackage::Provisioning::Library::CandidatePackages::`vftable'
0x18004f861  mov     [rsi], rax
0x18004f864  jmp     short loc_18004F869
0x18004f866  mov     rsi, r12
0x18004f869  test    rsi, rsi
0x18004f86c  jz      short loc_18004F87E
0x18004f86e  mov     rax, [rsi]
0x18004f871  mov     rcx, rsi
0x18004f874  mov     rax, [rax+8]
0x18004f878  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f87d  nop
0x18004f87e  test    rsi, rsi
0x18004f881  jnz     loc_18004F911
0x18004f887  mov     rcx, [rbp+38h]; this
0x18004f88b  mov     ebx, 8007000Eh
0x18004f890  mov     r9d, ebx; char *
0x18004f893  lea     r8, aOnecoreAdminAp_7; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18004f89a  mov     edx, 1B3h; void *
0x18004f89f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004f8a4  nop
0x18004f8a5  mov     rcx, [rbp+38h]; this
0x18004f8a9  lea     rax, aFailedToCreate_21; "Failed to create list of candidate pack"...
0x18004f8b0  mov     qword ptr [rsp+50h+var_30], rax; int
0x18004f8b5  mov     r9d, ebx; char *
0x18004f8b8  lea     r8, aOnecoreAdminAp_11; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18004f8bf  lea     edx, [rsi+26h]; void *
0x18004f8c2  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18004f8c7  nop
0x18004f8c8  mov     rcx, [rbp+arg_18]
0x18004f8cc  test    rcx, rcx
0x18004f8cf  jz      short loc_18004F8DE
0x18004f8d1  mov     rax, [rcx]
0x18004f8d4  mov     rax, [rax+10h]
0x18004f8d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f8dd  nop
0x18004f8de  mov     rcx, [rbp+arg_10]
0x18004f8e2  test    rcx, rcx
0x18004f8e5  jz      short loc_18004F8F4
0x18004f8e7  mov     rax, [rcx]
0x18004f8ea  mov     rax, [rax+10h]
0x18004f8ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f8f3  nop
0x18004f8f4  mov     rcx, [rbp+var_20]
0x18004f8f8  test    rcx, rcx
0x18004f8fb  jz      short loc_18004F90A
0x18004f8fd  mov     rdx, [rcx]
0x18004f900  mov     rax, [rdx+10h]
0x18004f904  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f909  nop
0x18004f90a  mov     eax, ebx
0x18004f90c  jmp     loc_1800508B0
0x18004f911  mov     [rbp+var_8], rsi
0x18004f915  mov     r8, rsi
0x18004f918  xor     edx, edx
0x18004f91a  mov     rcx, rdi
0x18004f91d  cmp     [rdi+8], r12
0x18004f921  jz      short loc_18004F92A
0x18004f923  call    ?GetPackagesFromPath@PackageSource@Library@Provisioning@MsixPackage@@AEAAJW4PackageType@234@PEAVCandidatePackages@234@@Z; MsixPackage::Provisioning::Library::PackageSource::GetPackagesFromPath(MsixPackage::Provisioning::Library::PackageType,MsixPackage::Provisioning::Library::CandidatePackages *)
0x18004f928  jmp     short loc_18004F92F
0x18004f92a  call    ?GetPackagesFromReader@PackageSource@Library@Provisioning@MsixPackage@@AEAAJW4PackageType@234@PEAVCandidatePackages@234@@Z; MsixPackage::Provisioning::Library::PackageSource::GetPackagesFromReader(MsixPackage::Provisioning::Library::PackageType,MsixPackage::Provisioning::Library::CandidatePackages *)
0x18004f92f  mov     r14d, eax
0x18004f932  test    eax, eax
0x18004f934  jns     short loc_18004F9B5
0x18004f936  mov     rcx, [rbp+38h]; this
0x18004f93a  lea     rax, aFailedToGetLis_2; "Failed to get list of main packages."
0x18004f941  mov     qword ptr [rsp+50h+var_30], rax; int
0x18004f946  mov     r9d, r14d; char *
0x18004f949  lea     r8, aOnecoreAdminAp_11; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18004f950  mov     edx, 29h ; ')'; void *
0x18004f955  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18004f95a  nop
0x18004f95b  mov     rcx, [rbp+arg_18]
0x18004f95f  test    rcx, rcx
0x18004f962  jz      short loc_18004F971
0x18004f964  mov     rax, [rcx]
0x18004f967  mov     rax, [rax+10h]
0x18004f96b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f970  nop
0x18004f971  mov     rcx, [rbp+arg_10]
0x18004f975  test    rcx, rcx
0x18004f978  jz      short loc_18004F987
0x18004f97a  mov     rax, [rcx]
0x18004f97d  mov     rax, [rax+10h]
0x18004f981  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f986  nop
0x18004f987  mov     rax, [rsi]
0x18004f98a  mov     rcx, rsi
0x18004f98d  mov     rax, [rax+10h]
0x18004f991  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f996  nop
0x18004f997  mov     rcx, [rbp+var_20]
0x18004f99b  test    rcx, rcx
0x18004f99e  jz      short loc_18004F9AD
0x18004f9a0  mov     rax, [rcx]
0x18004f9a3  mov     rax, [rax+10h]
0x18004f9a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f9ac  nop
0x18004f9ad  mov     eax, r14d
0x18004f9b0  jmp     loc_1800508B0
0x18004f9b5  mov     rax, [rsi+18h]
0x18004f9b9  sub     rax, [rsi+10h]
0x18004f9bd  sar     rax, 3
0x18004f9c1  test    eax, eax
0x18004f9c3  jz      loc_18004FBA1
0x18004f9c9  mov     r14, [rbp+var_20]
0x18004f9cd  mov     rcx, [rbp+arg_10]
0x18004f9d1  mov     [rbp+arg_10], r12
0x18004f9d5  test    rcx, rcx
0x18004f9d8  jz      short loc_18004F9E7
0x18004f9da  mov     rax, [rcx]
0x18004f9dd  mov     rax, [rax+10h]
0x18004f9e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f9e6  nop
0x18004f9e7  lea     r8, [rbp+arg_10]; struct MsixPackage::Provisioning::Library::PackageMonikerToPayload **
0x18004f9eb  mov     rdx, rsi; struct MsixPackage::Provisioning::Library::CandidatePackages *
0x18004f9ee  mov     rcx, r14; this
0x18004f9f1  call    ?GetMainPackage@MsixProvisioningRequest@Library@Provisioning@MsixPackage@@AEAAJPEAVCandidatePackages@234@PEAPEAVPackageMonikerToPayload@234@@Z; MsixPackage::Provisioning::Library::MsixProvisioningRequest::GetMainPackage(MsixPackage::Provisioning::Library::CandidatePackages *,MsixPackage::Provisioning::Library::PackageMonikerToPayload * *)
0x18004f9f6  mov     r15d, eax
0x18004f9f9  test    eax, eax
0x18004f9fb  jns     short loc_18004FA7B
0x18004f9fd  mov     rcx, [rbp+38h]; this
0x18004fa01  lea     rdx, aFailedToGetMai_1; "Failed to get main package."
0x18004fa08  mov     qword ptr [rsp+50h+var_30], rdx; int
0x18004fa0d  mov     r9d, eax; char *
0x18004fa10  lea     r8, aOnecoreAdminAp_11; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18004fa17  mov     edx, 2Dh ; '-'; void *
0x18004fa1c  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18004fa21  nop
0x18004fa22  mov     rcx, [rbp+arg_18]
0x18004fa26  test    rcx, rcx
0x18004fa29  jz      short loc_18004FA38
0x18004fa2b  mov     rax, [rcx]
0x18004fa2e  mov     rax, [rax+10h]
0x18004fa32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004fa37  nop
0x18004fa38  mov     rcx, [rbp+arg_10]
0x18004fa3c  test    rcx, rcx
0x18004fa3f  jz      short loc_18004FA4E
0x18004fa41  mov     rax, [rcx]
0x18004fa44  mov     rax, [rax+10h]
0x18004fa48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004fa4d  nop
0x18004fa4e  mov     rax, [rsi]
0x18004fa51  mov     rcx, rsi
0x18004fa54  mov     rax, [rax+10h]
0x18004fa58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004fa5d  nop
0x18004fa5e  test    r14, r14
0x18004fa61  jz      short loc_18004FA73
0x18004fa63  mov     rax, [r14]
0x18004fa66  mov     rcx, r14
0x18004fa69  mov     rax, [rax+10h]
0x18004fa6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004fa72  nop
0x18004fa73  mov     eax, r15d
0x18004fa76  jmp     loc_1800508B0
0x18004fa7b  mov     rax, [rbp+arg_10]
0x18004fa7f  test    rax, rax
0x18004fa82  jnz     short loc_18004FAFD
0x18004fa84  mov     rcx, [rbp+38h]; this
0x18004fa88  lea     rax, aFailedToPickMa; "Failed to pick main package."
0x18004fa8f  mov     qword ptr [rsp+50h+var_30], rax; int
0x18004fa94  mov     r9d, 0C1570102h; char *
0x18004fa9a  lea     r8, aOnecoreAdminAp_11; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18004faa1  mov     edx, 30h ; '0'; void *
0x18004faa6  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18004faab  nop
0x18004faac  mov     rcx, [rbp+arg_18]
0x18004fab0  test    rcx, rcx
0x18004fab3  jz      short loc_18004FAC2
0x18004fab5  mov     rax, [rcx]
0x18004fab8  mov     rax, [rax+10h]
0x18004fabc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004fac1  nop
0x18004fac2  mov     rcx, [rbp+arg_10]
0x18004fac6  test    rcx, rcx
0x18004fac9  jz      short loc_18004FAD8
0x18004facb  mov     rax, [rcx]
0x18004face  mov     rax, [rax+10h]
0x18004fad2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004fad7  nop
0x18004fad8  mov     rax, [rsi]
0x18004fadb  mov     rcx, rsi
0x18004fade  mov     rax, [rax+10h]
0x18004fae2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004fae7  nop
0x18004fae8  test    r14, r14
0x18004faeb  jz      loc_18004FD74
0x18004faf1  mov     rax, [r14]
0x18004faf4  mov     rax, [rax+10h]
0x18004faf8  jmp     loc_18004FD6B
0x18004fafd  add     rax, 38h ; '8'
0x18004fb01  cmp     qword ptr [rax+18h], 8
0x18004fb06  jb      short loc_18004FB0B
0x18004fb08  mov     rax, [rax]
0x18004fb0b  mov     [r14+40h], rax
0x18004fb0f  xor     r9d, r9d
0x18004fb12  mov     r8, [rbp+arg_10]
0x18004fb16  xor     edx, edx
0x18004fb18  mov     rcx, r14
0x18004fb1b  call    ?AddPackage@MsixProvisioningRequest@Library@Provisioning@MsixPackage@@AEAAJW4APPX_PACKAGE_TARGET_TYPE@234@PEAVPackageMonikerToPayload@234@1@Z; MsixPackage::Provisioning::Library::MsixProvisioningRequest::AddPackage(MsixPackage::Provisioning::Library::APPX_PACKAGE_TARGET_TYPE,MsixPackage::Provisioning::Library::PackageMonikerToPayload *,MsixPackage::Provisioning::Library::PackageMonikerToPayload *)
0x18004fb20  mov     r15d, eax
0x18004fb23  test    eax, eax
0x18004fb25  jns     loc_1800505D2
0x18004fb2b  mov     rcx, [rbp+38h]; this
0x18004fb2f  lea     rax, aFailedToAddMai_1; "Failed to add main package for provisio"...
0x18004fb36  mov     qword ptr [rsp+50h+var_30], rax; int
0x18004fb3b  mov     r9d, r15d; char *
0x18004fb3e  lea     r8, aOnecoreAdminAp_11; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18004fb45  mov     edx, 35h ; '5'; void *
0x18004fb4a  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18004fb4f  nop
0x18004fb50  mov     rcx, [rbp+arg_18]
0x18004fb54  test    rcx, rcx
0x18004fb57  jz      short loc_18004FB66
0x18004fb59  mov     rax, [rcx]
0x18004fb5c  mov     rax, [rax+10h]
0x18004fb60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004fb65  nop
0x18004fb66  mov     rcx, [rbp+arg_10]
0x18004fb6a  test    rcx, rcx
0x18004fb6d  jz      short loc_18004FB7C
0x18004fb6f  mov     rax, [rcx]
0x18004fb72  mov     rax, [rax+10h]
0x18004fb76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004fb7b  nop
0x18004fb7c  mov     rax, [rsi]
0x18004fb7f  mov     rcx, rsi
0x18004fb82  mov     rax, [rax+10h]
0x18004fb86  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
