# Common::Deployment::ValidatedManifestReaderHelper::GetManifestReaderFromValidatedManifestImpl(IStream *,ushort const *,ushort const *,Common::Deployment::ValidatedManifestReaderHelper::ReasonNotFound *,IAppxManifestReader * *,IAppxBundleManifestReader * *)

- ea: `0x180180c64`
- end: `0x18018146a`
- name: `?GetManifestReaderFromValidatedManifestImpl@ValidatedManifestReaderHelper@Deployment@Common@@AEAAJPEAUIStream@@PEBG1PEAW4ReasonNotFound@123@PEAPEAUIAppxManifestReader@@PEAPEAUIAppxBundleManifestReader@@@Z`
- size: `2054`
- prototype: `__int64 __usercall@<rax>(Common::Deployment::ValidatedManifestReaderHelper *__hidden this@<rcx>, struct IStream *@<rdx>, const unsigned __int16 *@<r8>, const unsigned __int16 *@<r9>, enum Common::Deployment::ValidatedManifestReaderHelper::ReasonNotFound *, struct IAppxManifestReader **, struct IAppxBundleManifestReader **)`
- caller_count: `2`
- callee_count: `26`
- tags: `file_ops, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180180b70`
- `0x180182360`

## callees

- `0x180006970`
- `0x18001adb4`
- `0x18003db94`
- `0x180046124`
- `0x180046adc`
- `0x180046c60`
- `0x18005656c`
- `0x18005d490`
- `0x18005df00`
- `0x180078c5c`
- `0x18007ec7c`
- `0x180088514`
- `0x1800923c8`
- `0x1800aed10`
- `0x1800af1bc`
- `0x1800d6fe0`
- `0x18011f65c`
- `0x18017d580`
- `0x18017fb64`
- `0x180180830`
- `0x180180c64`
- `0x180181558`
- `0x180181d98`
- `0x180181e74`
- `0x180183e78`
- `0x1801ac010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801813b4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801813eb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801813b4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801813eb`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180181126`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18018123d`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180181126`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18018123d`
- `AppXAllUserStore!IsPackageInUpdatedApplicationsKey` at `0x180180fc2`
- `AppXAllUserStore!IsPackageInUpdatedApplicationsKey` at `0x180180fc2`

## string_xrefs

- `0x180180d31`: `onecore\admin\appmodel\common\manifestreader.cpp`
- `0x180180d88`: `onecore\admin\appmodel\common\manifestreader.cpp`
- `0x180180dda`: `onecore\admin\appmodel\common\manifestreader.cpp`
- `0x180180e47`: `onecore\admin\appmodel\common\manifestreader.cpp`
- `0x180180e9e`: `onecore\admin\appmodel\common\manifestreader.cpp`
- `0x180180f66`: `onecore\admin\appmodel\common\manifestreader.cpp`
- `0x180180fd9`: `onecore\admin\appmodel\common\manifestreader.cpp`
- `0x180181090`: `onecore\admin\appmodel\common\manifestreader.cpp`
- `0x180181147`: `onecore\admin\appmodel\common\manifestreader.cpp`
- `0x18018125e`: `onecore\admin\appmodel\common\manifestreader.cpp`
- `0x1801813a2`: `onecore\admin\appmodel\common\manifestreader.cpp`
- `0x180180cbd`: `LoadingManifestFromDisk_GetManifestReaderFromValidatedManifestImpl`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
__int64 __fastcall Common::Deployment::ValidatedManifestReaderHelper::GetManifestReaderFromValidatedManifestImpl(
        Common::Deployment::ValidatedManifestReaderHelper *this,
        struct IStream *a2,
        unsigned __int16 *a3,
        const unsigned __int16 *a4,
        enum Common::Deployment::ValidatedManifestReaderHelper::ReasonNotFound *a5,
        struct IAppxManifestReader **a6,
        struct IAppxBundleManifestReader **a7)
{
  unsigned int v10; // edi
  struct PackageRepository::IRepositorySession *v11; // rbx
  struct PackageRepository::IRepositorySession *v12; // rcx
  int ReadOnlySession; // eax
  struct PackageRepository::IRepositorySession *v14; // rcx
  struct StateRepository::Database *v15; // r12
  int v16; // eax
  int PackageInstalledLocationFromManifestPath; // eax
  unsigned int v18; // esi
  int v19; // eax
  struct Common::StringBuffer *v20; // r8
  __int64 v21; // rdx
  char v22; // r12
  int PackageFamilyNameFromFullName; // eax
  const struct std::nothrow_t *v24; // rdx
  unsigned __int16 *v25; // rcx
  unsigned __int16 *v26; // rsi
  int v27; // eax
  const struct std::nothrow_t *v28; // rdx
  __int64 v29; // rdx
  struct StateRepository::Database *v30; // rax
  int v31; // eax
  __int64 v32; // r14
  HRESULT v33; // eax
  __int64 v34; // rdx
  LPVOID v35; // rsi
  __int64 (__fastcall *v36)(LPVOID, struct IStream *, __int64, struct IAppxManifestReader **); // rdi
  struct IAppxManifestReader *v37; // rsi
  HRESULT (__stdcall *v38)(IAppxManifestReader *, IAppxManifestPackageId **); // rdi
  HRESULT v39; // eax
  __int64 v40; // rdx
  LPVOID v41; // rsi
  __int64 (__fastcall *v42)(LPVOID, struct IStream *, __int64, struct IAppxBundleManifestReader **); // rdi
  struct IAppxBundleManifestReader *v43; // rsi
  HRESULT (__stdcall *GetPackageId)(IAppxBundleManifestReader *, IAppxManifestPackageId **); // rdi
  int v45; // eax
  __int64 v46; // rdx
  __int64 v47; // rcx
  __int64 v48; // r8
  __int64 v49; // r9
  __int64 v50; // rdx
  struct IAppxManifestReader *v51; // rax
  struct IAppxBundleManifestReader *v52; // rax
  int ppv; // [rsp+20h] [rbp-E0h]
  int ppva; // [rsp+20h] [rbp-E0h]
  bool v56; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int *v57; // [rsp+38h] [rbp-C8h] BYREF
  struct IAppxBundleManifestReader *v58; // [rsp+40h] [rbp-C0h] BYREF
  struct IAppxManifestReader *v59; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v60; // [rsp+50h] [rbp-B0h] BYREF
  LPVOID v61; // [rsp+58h] [rbp-A8h] BYREF
  LPVOID v62; // [rsp+60h] [rbp-A0h] BYREF
  LPVOID pv; // [rsp+68h] [rbp-98h] BYREF
  int v64; // [rsp+70h] [rbp-90h] BYREF
  struct PackageRepository::IRepositorySession *v65; // [rsp+78h] [rbp-88h] BYREF
  struct IStream *v66; // [rsp+80h] [rbp-80h]
  _QWORD v67[2]; // [rsp+90h] [rbp-70h] BYREF
  __int128 v68; // [rsp+A0h] [rbp-60h]
  __int128 v69; // [rsp+B0h] [rbp-50h]
  __int128 v70; // [rsp+C0h] [rbp-40h]
  __int64 v71; // [rsp+D0h] [rbp-30h]
  unsigned __int16 *v72[2]; // [rsp+E0h] [rbp-20h] BYREF
  int v73; // [rsp+F0h] [rbp-10h]
  _QWORD *v74; // [rsp+F8h] [rbp-8h]
  unsigned int **v75; // [rsp+100h] [rbp+0h]
  char v76; // [rsp+108h] [rbp+8h]
  __int64 v77[8]; // [rsp+110h] [rbp+10h] BYREF
  Common::Deployment *v78; // [rsp+150h] [rbp+50h]
  _QWORD v79[42]; // [rsp+220h] [rbp+120h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+3C8h] [rbp+2C8h]

  v61 = a3;
  v66 = a2;
  v57 = (unsigned int *)a5;
  wil::ActivityBase<AppXDeploymentServerTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<AppXDeploymentServerTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
    v79,
    "LoadingManifestFromDisk_GetManifestReaderFromValidatedManifestImpl");
  v79[0] = &AppXDeploymentServerTelemetry::LoadingManifestFromDisk_GetManifestReaderFromValidatedManifestImpl::`vftable';
  AppXDeploymentServerTelemetry::LoadingManifestFromDisk_GetManifestReaderFromValidatedManifestImpl::StartActivity(
    (AppXDeploymentServerTelemetry::LoadingManifestFromDisk_GetManifestReaderFromValidatedManifestImpl *)v79,
    a4,
    a3);
  v74 = v79;
  v75 = &v57;
  v76 = 1;
  if ( (a6 != 0) == (a7 != 0) )
  {
    v10 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xAA,
      (unsigned int)"onecore\\admin\\appmodel\\common\\manifestreader.cpp",
      (const char *)0x80070057LL,
      ppv);
LABEL_33:
    AppXDeploymentServerTelemetry::LoadingManifestFromDisk_GetManifestReaderFromValidatedManifestImpl::Stop(
      (AppXDeploymentServerTelemetry::LoadingManifestFromDisk_GetManifestReaderFromValidatedManifestImpl *)v79,
      *v57);
    goto LABEL_81;
  }
  *v57 = 0;
  if ( a6 )
    *a6 = 0;
  else
    *a7 = 0;
  v11 = 0;
  v65 = 0;
  v12 = (struct PackageRepository::IRepositorySession *)*((_QWORD *)this + 4);
  if ( !v12 )
  {
    ReadOnlySession = PackageRepository::Repository::GetReadOnlySession(&v65);
    v10 = ReadOnlySession;
    if ( ReadOnlySession < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xBB,
        (unsigned int)"onecore\\admin\\appmodel\\common\\manifestreader.cpp",
        (const char *)(unsigned int)ReadOnlySession,
        ppv);
      v14 = v65;
LABEL_32:
      Common::AutoPtrDeallocate<Common::Deployment::IMountedFolderConfiguration>(v14);
      goto LABEL_33;
    }
    v11 = v65;
    *((_QWORD *)this + 4) = v65;
    v12 = v11;
  }
  v15 = (struct StateRepository::Database *)(*(__int64 (__fastcall **)(struct PackageRepository::IRepositorySession *))(*(_QWORD *)v12 + 8LL))(v12);
  v16 = Common::Deployment::ValidatedManifestReaderHelper::ProcessManifestCacheInvalidations(this, v15);
  v10 = v16;
  if ( v16 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC1,
      (unsigned int)"onecore\\admin\\appmodel\\common\\manifestreader.cpp",
      (const char *)(unsigned int)v16,
      ppv);
LABEL_31:
    v14 = v11;
    goto LABEL_32;
  }
  StateRepository::Entity::Package::Package((StateRepository::Entity::Package *)v77);
  v56 = 0;
  if ( a4 )
  {
    *v57 = 2;
    v19 = StateRepository::Entity::Package::TryGetByPackageFullName(
            v15,
            a4,
            (struct StateRepository::Entity::Package *)v77,
            &v56);
    v10 = v19;
    if ( v19 < 0 )
    {
      v21 = 208;
      goto LABEL_18;
    }
  }
  else
  {
    *((_QWORD *)this + 2) = v61;
    *v57 = 1;
    PackageInstalledLocationFromManifestPath = Common::Deployment::ValidatedManifestReaderHelper::GetPackageInstalledLocationFromManifestPath(
                                                 this,
                                                 a7 != 0);
    v18 = PackageInstalledLocationFromManifestPath;
    if ( PackageInstalledLocationFromManifestPath < 0 )
    {
      v10 = -2147023728;
      if ( PackageInstalledLocationFromManifestPath != -2147023728 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xCA,
          (unsigned int)"onecore\\admin\\appmodel\\common\\manifestreader.cpp",
          (const char *)(unsigned int)PackageInstalledLocationFromManifestPath,
          ppv);
        StateRepository::Entity::Package::~Package((StateRepository::Entity::Package *)v77);
        Common::AutoPtrDeallocate<Common::Deployment::IMountedFolderConfiguration>(v11);
        v10 = v18;
        goto LABEL_33;
      }
      goto LABEL_30;
    }
    v19 = StateRepository::Entity::Package::TryGetByInstalledLocation(
            v15,
            *((const unsigned __int16 **)this + 3),
            (struct StateRepository::Entity::Package *)v77,
            &v56);
    v10 = v19;
    if ( v19 < 0 )
    {
      v21 = 203;
LABEL_18:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v21,
        (unsigned int)"onecore\\admin\\appmodel\\common\\manifestreader.cpp",
        (const char *)(unsigned int)v19,
        ppv);
LABEL_30:
      StateRepository::Entity::Package::~Package((StateRepository::Entity::Package *)v77);
      goto LABEL_31;
    }
  }
  if ( !v56 )
  {
LABEL_22:
    StateRepository::Entity::Package::~Package((StateRepository::Entity::Package *)v77);
    Common::AutoPtrDeallocate<Common::Deployment::IMountedFolderConfiguration>(v11);
    v10 = -2147023728;
    goto LABEL_33;
  }
  *v57 = 0;
  if ( !*((_BYTE *)this + 8) )
  {
    *(_OWORD *)v72 = 0;
    v73 = 0;
    PackageFamilyNameFromFullName = Common::Deployment::GetPackageFamilyNameFromFullName(
                                      v78,
                                      (Common::StringBuffer *)v72,
                                      v20);
    v10 = PackageFamilyNameFromFullName;
    if ( PackageFamilyNameFromFullName < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xEA,
        (unsigned int)"onecore\\admin\\appmodel\\common\\manifestreader.cpp",
        (const char *)(unsigned int)PackageFamilyNameFromFullName,
        ppv);
      v25 = v72[1];
      if ( !v72[1] )
        goto LABEL_30;
LABEL_29:
      operator delete(v25, v24);
      goto LABEL_30;
    }
    v64 = 0;
    v26 = v72[1];
    v27 = IsPackageInUpdatedApplicationsKey(v72[1], &v64);
    v10 = v27;
    if ( v27 < 0 )
    {
      v29 = 237;
LABEL_36:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v29,
        (unsigned int)"onecore\\admin\\appmodel\\common\\manifestreader.cpp",
        (const char *)(unsigned int)v27,
        ppv);
      if ( !v26 )
        goto LABEL_30;
      v25 = v26;
      goto LABEL_29;
    }
    v22 = 0;
    if ( v64 )
    {
      v27 = Common::Deployment::ValidatedManifestReaderHelper::ReloadManifestCacheForPackage(this, v77[0], v26, 0);
      v10 = v27;
      if ( v27 < 0 )
      {
        v29 = 240;
        goto LABEL_36;
      }
      v22 = 1;
    }
    if ( v26 )
      operator delete(v26, v28);
    goto LABEL_44;
  }
  v19 = (*(__int64 (__fastcall **)(Common::Deployment::ValidatedManifestReaderHelper *, __int64, _QWORD))(*(_QWORD *)this + 32LL))(
          this,
          v77[0],
          0);
  v10 = v19;
  if ( v19 < 0 )
  {
    v21 = 225;
    goto LABEL_18;
  }
  *((_BYTE *)this + 8) = 0;
  v22 = 1;
LABEL_44:
  v67[0] = 0;
  v67[1] = 0;
  v68 = 0;
  v69 = 0;
  v70 = 0;
  v71 = 0;
  v30 = (struct StateRepository::Database *)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 4) + 16LL))(*((_QWORD *)this + 4));
  v56 = 0;
  v31 = StateRepository::Entity::AppxManifest::TryGetByPackage(
          v30,
          v77[0],
          (struct StateRepository::Entity::AppxManifest *)v67,
          &v56);
  v10 = v31;
  if ( v31 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xFA,
      (unsigned int)"onecore\\admin\\appmodel\\common\\manifestreader.cpp",
      (const char *)(unsigned int)v31,
      ppv);
LABEL_54:
    StateRepository::Entity::PkgExtensionHost::~PkgExtensionHost((StateRepository::Entity::PkgExtensionHost *)v67);
    goto LABEL_30;
  }
  *v57 = 3;
  if ( !v56 || (v32 = v69, *v57 = 4, !v32) )
  {
    StateRepository::Entity::PkgExtensionHost::~PkgExtensionHost((StateRepository::Entity::PkgExtensionHost *)v67);
    goto LABEL_22;
  }
  *v57 = 0;
  v60 = 0;
  v59 = 0;
  v58 = 0;
  if ( !a6 )
  {
    v61 = 0;
    Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(&v61);
    v39 = CoCreateInstance(
            &GUID_2f49412a_3ed3_4da7_b041_f2a55fcc1150,
            0,
            1u,
            &GUID_adfa1cff_cfde_47d4_9d68_11591494e309,
            &v61);
    v10 = v39;
    if ( v39 >= 0 )
    {
      v41 = v61;
      v42 = *(__int64 (__fastcall **)(LPVOID, struct IStream *, __int64, struct IAppxBundleManifestReader **))(*(_QWORD *)v61 + 24LL);
      Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(&v58);
      v39 = v42(v41, v66, v32, &v58);
      v10 = v39;
      if ( v39 >= 0 )
      {
        v43 = v58;
        GetPackageId = v58->lpVtbl->GetPackageId;
        Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(&v60);
        v39 = ((__int64 (__fastcall *)(struct IAppxBundleManifestReader *, __int64 *))GetPackageId)(v43, &v60);
        v10 = v39;
        if ( v39 >= 0 )
        {
          Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(&v61);
          goto LABEL_68;
        }
        v40 = 294;
      }
      else
      {
        v40 = 293;
      }
    }
    else
    {
      v40 = 289;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v40,
      (unsigned int)"onecore\\admin\\appmodel\\common\\manifestreader.cpp",
      (const char *)(unsigned int)v39,
      ppva);
    Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(&v61);
    goto LABEL_53;
  }
  v62 = 0;
  Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(&v62);
  v33 = CoCreateInstance(
          &GUID_fad63700_aafb_463a_8c1f_4c2dbc28ae57,
          0,
          1u,
          &GUID_aabbc97e_7d38_46b2_a27b_e631b519b79b,
          &v62);
  v10 = v33;
  if ( v33 < 0 )
  {
    v34 = 275;
LABEL_52:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v34,
      (unsigned int)"onecore\\admin\\appmodel\\common\\manifestreader.cpp",
      (const char *)(unsigned int)v33,
      ppva);
    Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(&v62);
LABEL_53:
    Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(&v58);
    Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(&v59);
    Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(&v60);
    goto LABEL_54;
  }
  v35 = v62;
  v36 = *(__int64 (__fastcall **)(LPVOID, struct IStream *, __int64, struct IAppxManifestReader **))(*(_QWORD *)v62 + 24LL);
  Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(&v59);
  v33 = v36(v35, v66, v32, &v59);
  v10 = v33;
  if ( v33 < 0 )
  {
    v34 = 279;
    goto LABEL_52;
  }
  v37 = v59;
  v38 = v59->lpVtbl->GetPackageId;
  Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(&v60);
  v33 = ((__int64 (__fastcall *)(struct IAppxManifestReader *, __int64 *))v38)(v37, &v60);
  v10 = v33;
  if ( v33 < 0 )
  {
    v34 = 280;
    goto LABEL_52;
  }
  Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(&v62);
LABEL_68:
  pv = 0;
  v45 = (*(__int64 (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v60 + 72LL))(v60, &pv);
  v10 = v45;
  if ( v45 < 0 )
  {
    v49 = (unsigned int)v45;
    v50 = 300;
LABEL_78:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v50,
      (unsigned int)"onecore\\admin\\appmodel\\common\\manifestreader.cpp",
      (const char *)v49,
      ppva);
    CoTaskMemFree(pv);
    goto LABEL_53;
  }
  *v57 = 5;
  if ( v22 )
  {
    if ( (Microsoft_Windows_AppXDeployment_ServerEnableBits & 0x40) != 0 )
      McTemplateU0zz_EventWriteTransfer(v47, &ManifestCacheEntryReloaded, v78, pv);
    details::appxLog<unsigned short const *,unsigned short *>(v47, v46, v48, v78, pv);
  }
  else if ( !Common::String::CaseInsensitiveEquals((const unsigned __int16 *)pv, (const unsigned __int16 *)v78) )
  {
    v10 = -2147023728;
    v49 = 2147943568LL;
    v50 = 310;
    goto LABEL_78;
  }
  if ( a6 )
  {
    v51 = v59;
    v59 = 0;
    *a6 = v51;
  }
  else
  {
    v52 = v58;
    v58 = 0;
    *a7 = v52;
  }
  wil::ActivityBase<AppXDeploymentServerTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v79, 0);
  CoTaskMemFree(pv);
  Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(&v58);
  Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(&v59);
  Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(&v60);
  StateRepository::Entity::PkgExtensionHost::~PkgExtensionHost((StateRepository::Entity::PkgExtensionHost *)v67);
  StateRepository::Entity::Package::~Package((StateRepository::Entity::Package *)v77);
  Common::AutoPtrDeallocate<Common::Deployment::IMountedFolderConfiguration>(v11);
  v10 = 0;
LABEL_81:
  AppXDeploymentServerTelemetry::LoadingManifestFromDisk_GetManifestReaderFromValidatedManifestImpl::~LoadingManifestFromDisk_GetManifestReaderFromValidatedManifestImpl((AppXDeploymentServerTelemetry::LoadingManifestFromDisk_GetManifestReaderFromValidatedManifestImpl *)v79);
  return v10;
}

```

## disassembly

```asm
0x180180c64  push    rbp
0x180180c66  push    rbx
0x180180c67  push    rsi
0x180180c68  push    rdi
0x180180c69  push    r12
0x180180c6b  push    r13
0x180180c6d  push    r14
0x180180c6f  push    r15
0x180180c71  lea     rbp, [rsp-288h]
0x180180c79  sub     rsp, 388h
0x180180c80  mov     rax, cs:__security_cookie
0x180180c87  xor     rax, rsp
0x180180c8a  mov     [rbp+2C0h+var_50], rax
0x180180c91  mov     rsi, r9
0x180180c94  mov     rbx, r8
0x180180c97  mov     [rsp+3C0h+var_368], rbx
0x180180c9c  mov     [rbp+2C0h+var_340], rdx
0x180180ca0  mov     r14, rcx
0x180180ca3  mov     rax, [rbp+2C0h+arg_20]
0x180180caa  mov     [rsp+3C0h+var_388], rax
0x180180caf  mov     r15, [rbp+2C0h+arg_28]
0x180180cb6  mov     r13, [rbp+2C0h+arg_30]
0x180180cbd  lea     rdx, aLoadingmanifes_0; "LoadingManifestFromDisk_GetManifestRead"...
0x180180cc4  lea     rcx, [rbp+2C0h+var_1A0]
0x180180ccb  call    ??0?$ActivityBase@VAppXDeploymentServerTelemetry@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<AppXDeploymentServerTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<AppXDeploymentServerTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180180cd0  lea     rax, ??_7LoadingManifestFromDisk_GetManifestReaderFromValidatedManifestImpl@AppXDeploymentServerTelemetry@@6B@; const AppXDeploymentServerTelemetry::LoadingManifestFromDisk_GetManifestReaderFromValidatedManifestImpl::`vftable'
0x180180cd7  mov     [rbp+2C0h+var_1A0], rax
0x180180cde  mov     r8, rbx; unsigned __int16 *
0x180180ce1  mov     rdx, rsi; unsigned __int16 *
0x180180ce4  lea     rcx, [rbp+2C0h+var_1A0]; this
0x180180ceb  call    ?StartActivity@LoadingManifestFromDisk_GetManifestReaderFromValidatedManifestImpl@AppXDeploymentServerTelemetry@@QEAAXPEBG0@Z; AppXDeploymentServerTelemetry::LoadingManifestFromDisk_GetManifestReaderFromValidatedManifestImpl::StartActivity(ushort const *,ushort const *)
0x180180cf0  nop
0x180180cf1  lea     rax, [rbp+2C0h+var_1A0]
0x180180cf8  mov     [rbp+2C0h+var_2C8], rax
0x180180cfc  lea     rax, [rsp+3C0h+var_388]
0x180180d01  mov     [rbp+2C0h+var_2C0], rax
0x180180d05  mov     [rbp+2C0h+var_2B8], 1
0x180180d09  xor     r12d, r12d
0x180180d0c  mov     ecx, r12d
0x180180d0f  test    r13, r13
0x180180d12  setnz   cl
0x180180d15  mov     eax, r12d
0x180180d18  test    r15, r15
0x180180d1b  setnz   al
0x180180d1e  cmp     eax, ecx
0x180180d20  jnz     short loc_180180D47
0x180180d22  mov     rcx, [rbp+2C8h]; this
0x180180d29  mov     edi, 80070057h
0x180180d2e  mov     r9d, edi; char *
0x180180d31  lea     r8, aOnecoreAdminAp_118; "onecore\\admin\\appmodel\\common\\manif"...
0x180180d38  mov     edx, 0AAh; void *
0x180180d3d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180180d42  jmp     loc_180180F9A
0x180180d47  mov     rax, [rsp+3C0h+var_388]
0x180180d4c  mov     [rax], r12d
0x180180d4f  test    r15, r15
0x180180d52  jz      short loc_180180D59
0x180180d54  mov     [r15], r12
0x180180d57  jmp     short loc_180180D5D
0x180180d59  mov     [r13+0], r12
0x180180d5d  mov     rbx, r12
0x180180d60  mov     [rsp+3C0h+var_348], rbx
0x180180d65  mov     rcx, [r14+20h]
0x180180d69  test    rcx, rcx
0x180180d6c  jnz     short loc_180180DB0
0x180180d6e  lea     rcx, [rsp+3C0h+var_348]; struct PackageRepository::IRepositorySession **
0x180180d73  call    ?GetReadOnlySession@Repository@PackageRepository@@SAJPEAPEAVIRepositorySession@2@@Z; PackageRepository::Repository::GetReadOnlySession(PackageRepository::IRepositorySession * *)
0x180180d78  mov     edi, eax
0x180180d7a  test    eax, eax
0x180180d7c  jns     short loc_180180DA4
0x180180d7e  mov     rcx, [rbp+2C8h]; this
0x180180d85  mov     r9d, eax; char *
0x180180d88  lea     r8, aOnecoreAdminAp_118; "onecore\\admin\\appmodel\\common\\manif"...
0x180180d8f  mov     edx, 0BBh; void *
0x180180d94  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180180d99  nop
0x180180d9a  mov     rcx, [rsp+3C0h+var_348]
0x180180d9f  jmp     loc_180180F94
0x180180da4  mov     rbx, [rsp+3C0h+var_348]
0x180180da9  mov     [r14+20h], rbx
0x180180dad  mov     rcx, rbx
0x180180db0  mov     rax, [rcx]
0x180180db3  mov     rax, [rax+8]
0x180180db7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180180dbc  mov     r12, rax
0x180180dbf  mov     rdx, rax; struct StateRepository::Database *
0x180180dc2  mov     rcx, r14; this
0x180180dc5  call    ?ProcessManifestCacheInvalidations@ValidatedManifestReaderHelper@Deployment@Common@@QEAAJAEAVDatabase@StateRepository@@@Z; Common::Deployment::ValidatedManifestReaderHelper::ProcessManifestCacheInvalidations(StateRepository::Database &)
0x180180dca  mov     edi, eax
0x180180dcc  test    eax, eax
0x180180dce  jns     short loc_180180DF0
0x180180dd0  mov     rcx, [rbp+2C8h]; this
0x180180dd7  mov     r9d, eax; char *
0x180180dda  lea     r8, aOnecoreAdminAp_118; "onecore\\admin\\appmodel\\common\\manif"...
0x180180de1  mov     edx, 0C1h; void *
0x180180de6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180180deb  jmp     loc_180180F91
0x180180df0  lea     rcx, [rbp+2C0h+var_2B0]; this
0x180180df4  call    ??0Package@Entity@StateRepository@@QEAA@XZ; StateRepository::Entity::Package::Package(void)
0x180180df9  nop
0x180180dfa  mov     [rsp+3C0h+var_390], 0
0x180180dff  test    rsi, rsi
0x180180e02  jnz     loc_180180EAF
0x180180e08  mov     rax, [rsp+3C0h+var_368]
0x180180e0d  mov     [r14+10h], rax
0x180180e11  mov     rax, [rsp+3C0h+var_388]
0x180180e16  mov     dword ptr [rax], 1
0x180180e1c  test    r13, r13
0x180180e1f  setnz   dl; bool
0x180180e22  mov     rcx, r14; this
0x180180e25  call    ?GetPackageInstalledLocationFromManifestPath@ValidatedManifestReaderHelper@Deployment@Common@@AEAAJ_N@Z; Common::Deployment::ValidatedManifestReaderHelper::GetPackageInstalledLocationFromManifestPath(bool)
0x180180e2a  mov     esi, eax
0x180180e2c  test    eax, eax
0x180180e2e  jns     short loc_180180E72
0x180180e30  mov     edi, 80070490h
0x180180e35  cmp     eax, edi
0x180180e37  jz      loc_180180F87
0x180180e3d  mov     rcx, [rbp+2C8h]; this
0x180180e44  mov     r9d, eax; char *
0x180180e47  lea     r8, aOnecoreAdminAp_118; "onecore\\admin\\appmodel\\common\\manif"...
0x180180e4e  mov     edx, 0CAh; void *
0x180180e53  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180180e58  nop
0x180180e59  lea     rcx, [rbp+2C0h+var_2B0]; this
0x180180e5d  call    ??1Package@Entity@StateRepository@@QEAA@XZ; StateRepository::Entity::Package::~Package(void)
0x180180e62  nop
0x180180e63  mov     rcx, rbx
0x180180e66  call    ??$AutoPtrDeallocate@VIMountedFolderConfiguration@Deployment@Common@@@Common@@YAXPEAVIMountedFolderConfiguration@Deployment@0@@Z; Common::AutoPtrDeallocate<Common::Deployment::IMountedFolderConfiguration>(Common::Deployment::IMountedFolderConfiguration *)
0x180180e6b  mov     edi, esi
0x180180e6d  jmp     loc_180180F9A
0x180180e72  lea     r9, [rsp+3C0h+var_390]; bool *
0x180180e77  lea     r8, [rbp+2C0h+var_2B0]; struct StateRepository::Entity::Package *
0x180180e7b  mov     rdx, [r14+18h]; unsigned __int16 *
0x180180e7f  mov     rcx, r12; this
0x180180e82  call    ?TryGetByInstalledLocation@Package@Entity@StateRepository@@SAJAEAVDatabase@3@PEBGAEAV123@AEA_N@Z; StateRepository::Entity::Package::TryGetByInstalledLocation(StateRepository::Database &,ushort const *,StateRepository::Entity::Package &,bool &)
0x180180e87  mov     edi, eax
0x180180e89  xor     esi, esi
0x180180e8b  test    eax, eax
0x180180e8d  jns     short loc_180180EDD
0x180180e8f  mov     edx, 0CBh; void *
0x180180e94  mov     rcx, [rbp+2C8h]; this
0x180180e9b  mov     r9d, eax; char *
0x180180e9e  lea     r8, aOnecoreAdminAp_118; "onecore\\admin\\appmodel\\common\\manif"...
0x180180ea5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180180eaa  jmp     loc_180180F87
0x180180eaf  mov     rax, [rsp+3C0h+var_388]
0x180180eb4  mov     dword ptr [rax], 2
0x180180eba  lea     r9, [rsp+3C0h+var_390]; bool *
0x180180ebf  lea     r8, [rbp+2C0h+var_2B0]; struct StateRepository::Entity::Package *
0x180180ec3  mov     rdx, rsi; unsigned __int16 *
0x180180ec6  mov     rcx, r12; struct StateRepository::Database *
0x180180ec9  call    ?TryGetByPackageFullName@Package@Entity@StateRepository@@SAJAEAVDatabase@3@PEBGAEAV123@AEA_N@Z; StateRepository::Entity::Package::TryGetByPackageFullName(StateRepository::Database &,ushort const *,StateRepository::Entity::Package &,bool &)
0x180180ece  mov     edi, eax
0x180180ed0  xor     esi, esi
0x180180ed2  test    eax, eax
0x180180ed4  jns     short loc_180180EDD
0x180180ed6  mov     edx, 0D0h
0x180180edb  jmp     short loc_180180E94
0x180180edd  cmp     [rsp+3C0h+var_390], sil
0x180180ee2  jnz     short loc_180180F00
0x180180ee4  lea     rcx, [rbp+2C0h+var_2B0]; this
0x180180ee8  call    ??1Package@Entity@StateRepository@@QEAA@XZ; StateRepository::Entity::Package::~Package(void)
0x180180eed  nop
0x180180eee  mov     rcx, rbx
0x180180ef1  call    ??$AutoPtrDeallocate@VIMountedFolderConfiguration@Deployment@Common@@@Common@@YAXPEAVIMountedFolderConfiguration@Deployment@0@@Z; Common::AutoPtrDeallocate<Common::Deployment::IMountedFolderConfiguration>(Common::Deployment::IMountedFolderConfiguration *)
0x180180ef6  mov     edi, 80070490h
0x180180efb  jmp     loc_180180F9A
0x180180f00  mov     rax, [rsp+3C0h+var_388]
0x180180f05  mov     [rax], esi
0x180180f07  cmp     [r14+8], sil
0x180180f0b  jz      short loc_180180F3F
0x180180f0d  mov     rax, [r14]
0x180180f10  xor     r8d, r8d
0x180180f13  mov     rdx, [rbp+2C0h+var_2B0]
0x180180f17  mov     rcx, r14
0x180180f1a  mov     rax, [rax+20h]
0x180180f1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180180f23  mov     edi, eax
0x180180f25  test    eax, eax
0x180180f27  jns     short loc_180180F33
0x180180f29  mov     edx, 0E1h
0x180180f2e  jmp     loc_180180E94
0x180180f33  mov     [r14+8], sil
0x180180f37  mov     r12b, 1
0x180180f3a  jmp     loc_180181035
0x180180f3f  xorps   xmm0, xmm0
0x180180f42  movups  xmmword ptr [rbp+2C0h+var_2E0], xmm0
0x180180f46  mov     [rbp+2C0h+var_2D0], esi
0x180180f49  lea     rdx, [rbp+2C0h+var_2E0]; Common::StringBuffer *
0x180180f4d  mov     rcx, [rbp+2C0h+var_270]; this
0x180180f51  call    ?GetPackageFamilyNameFromFullName@Deployment@Common@@YAJPEBGPEAVStringBuffer@2@@Z; Common::Deployment::GetPackageFamilyNameFromFullName(ushort const *,Common::StringBuffer *)
0x180180f56  mov     edi, eax
0x180180f58  test    eax, eax
0x180180f5a  jns     short loc_180180FB2
0x180180f5c  mov     rcx, [rbp+2C8h]; this
0x180180f63  mov     r9d, eax; char *
0x180180f66  lea     r8, aOnecoreAdminAp_118; "onecore\\admin\\appmodel\\common\\manif"...
0x180180f6d  mov     edx, 0EAh; void *
0x180180f72  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180180f77  nop
0x180180f78  mov     rcx, [rbp+2C0h+var_2E0+8]; void *
0x180180f7c  test    rcx, rcx
0x180180f7f  jz      short loc_180180F87
0x180180f81  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180180f86  nop
0x180180f87  lea     rcx, [rbp+2C0h+var_2B0]; this
0x180180f8b  call    ??1Package@Entity@StateRepository@@QEAA@XZ; StateRepository::Entity::Package::~Package(void)
0x180180f90  nop
0x180180f91  mov     rcx, rbx
0x180180f94  call    ??$AutoPtrDeallocate@VIMountedFolderConfiguration@Deployment@Common@@@Common@@YAXPEAVIMountedFolderConfiguration@Deployment@0@@Z; Common::AutoPtrDeallocate<Common::Deployment::IMountedFolderConfiguration>(Common::Deployment::IMountedFolderConfiguration *)
0x180180f99  nop
0x180180f9a  mov     rdx, [rsp+3C0h+var_388]
0x180180f9f  mov     edx, [rdx]; unsigned int
0x180180fa1  lea     rcx, [rbp+2C0h+var_1A0]; this
0x180180fa8  call    ?Stop@LoadingManifestFromDisk_GetManifestReaderFromValidatedManifestImpl@AppXDeploymentServerTelemetry@@QEAAXI@Z; AppXDeploymentServerTelemetry::LoadingManifestFromDisk_GetManifestReaderFromValidatedManifestImpl::Stop(uint)
0x180180fad  jmp     loc_180181438
0x180180fb2  mov     [rsp+3C0h+var_350], esi
0x180180fb6  mov     rsi, [rbp+2C0h+var_2E0+8]
0x180180fba  lea     rdx, [rsp+3C0h+var_350]
0x180180fbf  mov     rcx, rsi
0x180180fc2  call    cs:__imp_IsPackageInUpdatedApplicationsKey
0x180180fc9  nop     dword ptr [rax+rax+00h]
0x180180fce  mov     edi, eax
0x180180fd0  test    eax, eax
0x180180fd2  jns     short loc_180180FFA
0x180180fd4  mov     edx, 0EDh; void *
0x180180fd9  lea     r8, aOnecoreAdminAp_118; "onecore\\admin\\appmodel\\common\\manif"...
0x180180fe0  mov     r9d, eax; char *
0x180180fe3  mov     rcx, [rbp+2C8h]; this
0x180180fea  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180180fef  nop
0x180180ff0  test    rsi, rsi
0x180180ff3  jz      short loc_180180F87
0x180180ff5  mov     rcx, rsi
0x180180ff8  jmp     short loc_180180F81
0x180180ffa  xor     r12b, r12b
0x180180ffd  cmp     [rsp+3C0h+var_350], 0
0x180181002  jz      short loc_180181026
0x180181004  xor     r9d, r9d; int
0x180181007  mov     r8, rsi; unsigned __int16 *
0x18018100a  mov     rdx, [rbp+2C0h+var_2B0]; __int64
0x18018100e  mov     rcx, r14; this
0x180181011  call    ?ReloadManifestCacheForPackage@ValidatedManifestReaderHelper@Deployment@Common@@QEAAJ_JPEBGH@Z; Common::Deployment::ValidatedManifestReaderHelper::ReloadManifestCacheForPackage(__int64,ushort const *,int)
0x180181016  mov     edi, eax
0x180181018  test    eax, eax
0x18018101a  jns     short loc_180181023
0x18018101c  mov     edx, 0F0h
0x180181021  jmp     short loc_180180FD9
0x180181023  mov     r12b, 1
0x180181026  test    rsi, rsi
0x180181029  jz      short loc_180181033
0x18018102b  mov     rcx, rsi; void *
0x18018102e  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180181033  xor     esi, esi
0x180181035  mov     [rbp+2C0h+var_330], rsi
0x180181039  mov     [rbp+2C0h+var_328], rsi
0x18018103d  xorps   xmm0, xmm0
0x180181040  movdqa  [rbp+2C0h+var_320], xmm0
0x180181045  xorps   xmm1, xmm1
0x180181048  movdqa  [rbp+2C0h+var_310], xmm1
0x18018104d  movdqa  [rbp+2C0h+var_300], xmm0
0x180181052  mov     [rbp+2C0h+var_2F0], rsi
0x180181056  mov     rcx, [r14+20h]
0x18018105a  mov     rax, [rcx]
0x18018105d  mov     rax, [rax+10h]
0x180181061  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180181066  mov     [rsp+3C0h+var_390], sil
0x18018106b  lea     r9, [rsp+3C0h+var_390]; bool *
0x180181070  lea     r8, [rbp+2C0h+var_330]; struct StateRepository::Entity::AppxManifest *
0x180181074  mov     rdx, [rbp+2C0h+var_2B0]; __int64
0x180181078  mov     rcx, rax; struct StateRepository::Database *
0x18018107b  call    ?TryGetByPackage@AppxManifest@Entity@StateRepository@@SAJAEAVDatabase@3@_JAEAV123@AEA_N@Z; StateRepository::Entity::AppxManifest::TryGetByPackage(StateRepository::Database &,__int64,StateRepository::Entity::AppxManifest &,bool &)
0x180181080  mov     edi, eax
0x180181082  test    eax, eax
0x180181084  jns     short loc_1801810A6
0x180181086  mov     rcx, [rbp+2C8h]; this
0x18018108d  mov     r9d, eax; char *
0x180181090  lea     r8, aOnecoreAdminAp_118; "onecore\\admin\\appmodel\\common\\manif"...
0x180181097  mov     edx, 0FAh; void *
0x18018109c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801810a1  jmp     loc_180181180
0x1801810a6  mov     rax, [rsp+3C0h+var_388]
0x1801810ab  mov     dword ptr [rax], 3
0x1801810b1  cmp     [rsp+3C0h+var_390], sil
0x1801810b6  jnz     short loc_1801810C6
0x1801810b8  lea     rcx, [rbp+2C0h+var_330]; this
0x1801810bc  call    ??1PkgExtensionHost@Entity@StateRepository@@QEAA@XZ; StateRepository::Entity::PkgExtensionHost::~PkgExtensionHost(void)
0x1801810c1  jmp     loc_180180EE4
0x1801810c6  mov     r14, qword ptr [rbp+2C0h+var_310]
0x1801810ca  mov     rax, [rsp+3C0h+var_388]
0x1801810cf  mov     dword ptr [rax], 4
0x1801810d5  test    r14, r14
0x1801810d8  jz      short loc_1801810B8
0x1801810da  mov     rax, [rsp+3C0h+var_388]
0x1801810df  mov     [rax], esi
0x1801810e1  mov     [rsp+3C0h+var_370], rsi
0x1801810e6  mov     [rsp+3C0h+var_378], rsi
0x1801810eb  mov     [rsp+3C0h+var_380], rsi
0x1801810f0  test    r15, r15
0x1801810f3  jz      loc_180181210
  ... truncated ...
```
