# Common::Deployment::ValidatedManifestReaderHelper::GetManifestReaderFromValidatedManifestImpl(IStream *,ushort const *,ushort const *,Common::Deployment::ValidatedManifestReaderHelper::ReasonNotFound *,IAppxManifestReader * *,IAppxBundleManifestReader * *)

- ea: `0x1801eb3e4`
- end: `0x1801ebbb7`
- name: `?GetManifestReaderFromValidatedManifestImpl@ValidatedManifestReaderHelper@Deployment@Common@@AEAAJPEAUIStream@@PEBG1PEAW4ReasonNotFound@123@PEAPEAUIAppxManifestReader@@PEAPEAUIAppxBundleManifestReader@@@Z`
- size: `2003`
- prototype: `__int64 __usercall@<rax>(Common::Deployment::ValidatedManifestReaderHelper *__hidden this@<rcx>, struct IStream *@<rdx>, const unsigned __int16 *@<r8>, const unsigned __int16 *@<r9>, enum Common::Deployment::ValidatedManifestReaderHelper::ReasonNotFound *, struct IAppxManifestReader **, struct IAppxBundleManifestReader **)`
- caller_count: `2`
- callee_count: `26`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1801eb2f0`
- `0x1801ecb80`

## callees

- `0x18000b3bc`
- `0x18000e6e0`
- `0x180020ae0`
- `0x180026fc4`
- `0x18002aa6c`
- `0x18002ab68`
- `0x18004b72c`
- `0x18006a3f0`
- `0x180098bf4`
- `0x1800a98e0`
- `0x1800ac9a0`
- `0x1800bdadc`
- `0x1800d4f28`
- `0x1800f0260`
- `0x18017f020`
- `0x18018da70`
- `0x1801da21c`
- `0x1801e25b8`
- `0x1801e33a4`
- `0x1801eafbc`
- `0x1801eb3e4`
- `0x1801ebd68`
- `0x1801ec5bc`
- `0x1801ec694`
- `0x1801eff08`
- `0x180211010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1801eb880`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1801eb991`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1801eb880`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1801eb991`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801ebb0e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801ebb3f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801ebb0e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801ebb3f`
- `AppXAllUserStore!IsPackageInUpdatedApplicationsKey` at `0x1801eb741`
- `AppXAllUserStore!IsPackageInUpdatedApplicationsKey` at `0x1801eb741`

## string_xrefs

- `0x1801eb4b1`: `onecore\admin\appmodel\common\manifestreader.cpp`
- `0x1801eb508`: `onecore\admin\appmodel\common\manifestreader.cpp`
- `0x1801eb55a`: `onecore\admin\appmodel\common\manifestreader.cpp`
- `0x1801eb5c8`: `onecore\admin\appmodel\common\manifestreader.cpp`
- `0x1801eb621`: `onecore\admin\appmodel\common\manifestreader.cpp`
- `0x1801eb6f1`: `onecore\admin\appmodel\common\manifestreader.cpp`
- `0x1801eb7e8`: `onecore\admin\appmodel\common\manifestreader.cpp`
- `0x1801eb89b`: `onecore\admin\appmodel\common\manifestreader.cpp`
- `0x1801eb9ac`: `onecore\admin\appmodel\common\manifestreader.cpp`
- `0x1801ebafc`: `onecore\admin\appmodel\common\manifestreader.cpp`
- `0x1801eb43d`: `LoadingManifestFromDisk_GetManifestReaderFromValidatedManifestImpl`

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
  unsigned int v18; // r14d
  int v19; // eax
  struct Common::StringBuffer *v20; // r8
  __int64 v21; // rdx
  char v22; // r14
  int PackageFamilyNameFromFullName; // eax
  __int64 v24; // rdx
  struct StateRepository::Database *v25; // rax
  int v26; // eax
  __int64 v27; // r12
  HRESULT v28; // eax
  __int64 v29; // rdx
  LPVOID v30; // rsi
  __int64 (__fastcall *v31)(LPVOID, struct IStream *, __int64, struct IAppxManifestReader **); // rdi
  struct IAppxManifestReader *v32; // rsi
  HRESULT (__stdcall *v33)(IAppxManifestReader *, IAppxManifestPackageId **); // rdi
  HRESULT v34; // eax
  __int64 v35; // rdx
  LPVOID v36; // rsi
  __int64 (__fastcall *v37)(LPVOID, struct IStream *, __int64, struct IAppxBundleManifestReader **); // rdi
  struct IAppxBundleManifestReader *v38; // rsi
  HRESULT (__stdcall *GetPackageId)(IAppxBundleManifestReader *, IAppxManifestPackageId **); // rdi
  int v40; // eax
  __int64 v41; // rdx
  __int64 v42; // rcx
  __int64 v43; // r9
  __int64 v44; // rdx
  struct IAppxManifestReader *v45; // rax
  struct IAppxBundleManifestReader *v46; // rax
  int ppv; // [rsp+20h] [rbp-E0h]
  int ppva; // [rsp+20h] [rbp-E0h]
  bool v50; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int *v51; // [rsp+38h] [rbp-C8h] BYREF
  struct IAppxBundleManifestReader *v52; // [rsp+40h] [rbp-C0h] BYREF
  struct IAppxManifestReader *v53; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v54; // [rsp+50h] [rbp-B0h] BYREF
  LPVOID v55; // [rsp+58h] [rbp-A8h] BYREF
  LPVOID v56; // [rsp+60h] [rbp-A0h] BYREF
  LPVOID pv; // [rsp+68h] [rbp-98h] BYREF
  int v58; // [rsp+70h] [rbp-90h] BYREF
  struct PackageRepository::IRepositorySession *v59; // [rsp+78h] [rbp-88h] BYREF
  unsigned __int16 *v60[2]; // [rsp+80h] [rbp-80h] BYREF
  int v61; // [rsp+90h] [rbp-70h]
  struct IStream *v62; // [rsp+98h] [rbp-68h]
  _QWORD v63[2]; // [rsp+A0h] [rbp-60h] BYREF
  __int128 v64; // [rsp+B0h] [rbp-50h]
  __int128 v65; // [rsp+C0h] [rbp-40h]
  __int128 v66; // [rsp+D0h] [rbp-30h]
  __int64 v67; // [rsp+E0h] [rbp-20h]
  _QWORD *v68; // [rsp+F0h] [rbp-10h]
  unsigned int **v69; // [rsp+F8h] [rbp-8h]
  char v70; // [rsp+100h] [rbp+0h]
  __int64 v71[8]; // [rsp+110h] [rbp+10h] BYREF
  Common::Deployment *v72; // [rsp+150h] [rbp+50h]
  _QWORD v73[42]; // [rsp+220h] [rbp+120h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+3C8h] [rbp+2C8h]

  v55 = a3;
  v62 = a2;
  v51 = (unsigned int *)a5;
  wil::ActivityBase<AppXDeploymentServerTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<AppXDeploymentServerTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v73);
  v73[0] = &AppXDeploymentServerTelemetry::LoadingManifestFromDisk_GetManifestReaderFromValidatedManifestImpl::`vftable';
  AppXDeploymentServerTelemetry::LoadingManifestFromDisk_GetManifestReaderFromValidatedManifestImpl::StartActivity(
    (AppXDeploymentServerTelemetry::LoadingManifestFromDisk_GetManifestReaderFromValidatedManifestImpl *)v73,
    a4,
    a3);
  v68 = v73;
  v69 = &v51;
  v70 = 1;
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
      (AppXDeploymentServerTelemetry::LoadingManifestFromDisk_GetManifestReaderFromValidatedManifestImpl *)v73,
      *v51);
    goto LABEL_78;
  }
  *v51 = 0;
  if ( a6 )
    *a6 = 0;
  else
    *a7 = 0;
  v11 = 0;
  v59 = 0;
  v12 = (struct PackageRepository::IRepositorySession *)*((_QWORD *)this + 4);
  if ( !v12 )
  {
    ReadOnlySession = PackageRepository::Repository::GetReadOnlySession(&v59);
    v10 = ReadOnlySession;
    if ( ReadOnlySession < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xBB,
        (unsigned int)"onecore\\admin\\appmodel\\common\\manifestreader.cpp",
        (const char *)(unsigned int)ReadOnlySession,
        ppv);
      v14 = v59;
LABEL_32:
      Common::AutoPtrDeallocate<ARI::DependencyMiniRepository::Sections::Globalization>(v14);
      goto LABEL_33;
    }
    v11 = v59;
    *((_QWORD *)this + 4) = v59;
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
  StateRepository::Entity::Package::Package((StateRepository::Entity::Package *)v71);
  v50 = 0;
  if ( a4 )
  {
    *v51 = 2;
    v19 = StateRepository::Entity::Package::TryGetByPackageFullName(
            v15,
            a4,
            (struct StateRepository::Entity::Package *)v71,
            &v50);
    v10 = v19;
    if ( v19 < 0 )
    {
      v21 = 208;
      goto LABEL_18;
    }
  }
  else
  {
    *((_QWORD *)this + 2) = v55;
    *v51 = 1;
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
        StateRepository::Entity::Package::~Package((StateRepository::Entity::Package *)v71);
        Common::AutoPtrDeallocate<ARI::DependencyMiniRepository::Sections::Globalization>(v11);
        v10 = v18;
        goto LABEL_33;
      }
      goto LABEL_30;
    }
    v19 = StateRepository::Entity::Package::TryGetByInstalledLocation(
            v15,
            *((const unsigned __int16 **)this + 3),
            (struct StateRepository::Entity::Package *)v71,
            &v50);
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
      StateRepository::Entity::Package::~Package((StateRepository::Entity::Package *)v71);
      goto LABEL_31;
    }
  }
  if ( !v50 )
  {
LABEL_22:
    StateRepository::Entity::Package::~Package((StateRepository::Entity::Package *)v71);
    Common::AutoPtrDeallocate<ARI::DependencyMiniRepository::Sections::Globalization>(v11);
    v10 = -2147023728;
    goto LABEL_33;
  }
  *v51 = 0;
  if ( !*((_BYTE *)this + 8) )
  {
    *(_OWORD *)v60 = 0;
    v61 = 0;
    PackageFamilyNameFromFullName = Common::Deployment::GetPackageFamilyNameFromFullName(
                                      v72,
                                      (Common::StringBuffer *)v60,
                                      v20);
    v10 = PackageFamilyNameFromFullName;
    if ( PackageFamilyNameFromFullName >= 0 )
    {
      v58 = 0;
      PackageFamilyNameFromFullName = IsPackageInUpdatedApplicationsKey(v60[1], &v58);
      v10 = PackageFamilyNameFromFullName;
      if ( PackageFamilyNameFromFullName >= 0 )
      {
        v22 = 0;
        if ( v58 )
        {
          PackageFamilyNameFromFullName = Common::Deployment::ValidatedManifestReaderHelper::ReloadManifestCacheForPackage(
                                            this,
                                            v71[0],
                                            v60[1],
                                            0);
          v10 = PackageFamilyNameFromFullName;
          if ( PackageFamilyNameFromFullName < 0 )
          {
            v24 = 240;
            goto LABEL_29;
          }
          v22 = 1;
        }
        Common::StringBuffer::~StringBuffer((Common::StringBuffer *)v60);
        goto LABEL_41;
      }
      v24 = 237;
    }
    else
    {
      v24 = 234;
    }
LABEL_29:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v24,
      (unsigned int)"onecore\\admin\\appmodel\\common\\manifestreader.cpp",
      (const char *)(unsigned int)PackageFamilyNameFromFullName,
      ppv);
    Common::StringBuffer::~StringBuffer((Common::StringBuffer *)v60);
    goto LABEL_30;
  }
  v19 = (*(__int64 (__fastcall **)(Common::Deployment::ValidatedManifestReaderHelper *, __int64, _QWORD))(*(_QWORD *)this + 32LL))(
          this,
          v71[0],
          0);
  v10 = v19;
  if ( v19 < 0 )
  {
    v21 = 225;
    goto LABEL_18;
  }
  *((_BYTE *)this + 8) = 0;
  v22 = 1;
LABEL_41:
  v63[0] = 0;
  v63[1] = 0;
  v64 = 0;
  v65 = 0;
  v66 = 0;
  v67 = 0;
  v25 = (struct StateRepository::Database *)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 4) + 16LL))(*((_QWORD *)this + 4));
  v50 = 0;
  v26 = StateRepository::Entity::AppxManifest::TryGetByPackage(
          v25,
          v71[0],
          (struct StateRepository::Entity::AppxManifest *)v63,
          &v50);
  v10 = v26;
  if ( v26 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xFA,
      (unsigned int)"onecore\\admin\\appmodel\\common\\manifestreader.cpp",
      (const char *)(unsigned int)v26,
      ppv);
LABEL_51:
    StateRepository::Entity::PkgExtensionHost::~PkgExtensionHost((StateRepository::Entity::PkgExtensionHost *)v63);
    goto LABEL_30;
  }
  *v51 = 3;
  if ( !v50 || (v27 = v65, *v51 = 4, !v27) )
  {
    StateRepository::Entity::PkgExtensionHost::~PkgExtensionHost((StateRepository::Entity::PkgExtensionHost *)v63);
    goto LABEL_22;
  }
  *v51 = 0;
  v54 = 0;
  v53 = 0;
  v52 = 0;
  if ( !a6 )
  {
    v55 = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v55);
    v34 = CoCreateInstance(
            &GUID_2f49412a_3ed3_4da7_b041_f2a55fcc1150,
            0,
            1u,
            &GUID_adfa1cff_cfde_47d4_9d68_11591494e309,
            &v55);
    v10 = v34;
    if ( v34 >= 0 )
    {
      v36 = v55;
      v37 = *(__int64 (__fastcall **)(LPVOID, struct IStream *, __int64, struct IAppxBundleManifestReader **))(*(_QWORD *)v55 + 24LL);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v52);
      v34 = v37(v36, v62, v27, &v52);
      v10 = v34;
      if ( v34 >= 0 )
      {
        v38 = v52;
        GetPackageId = v52->lpVtbl->GetPackageId;
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v54);
        v34 = ((__int64 (__fastcall *)(struct IAppxBundleManifestReader *, __int64 *))GetPackageId)(v38, &v54);
        v10 = v34;
        if ( v34 >= 0 )
        {
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v55);
          goto LABEL_65;
        }
        v35 = 294;
      }
      else
      {
        v35 = 293;
      }
    }
    else
    {
      v35 = 289;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v35,
      (unsigned int)"onecore\\admin\\appmodel\\common\\manifestreader.cpp",
      (const char *)(unsigned int)v34,
      ppva);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v55);
    goto LABEL_50;
  }
  v56 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v56);
  v28 = CoCreateInstance(
          &GUID_fad63700_aafb_463a_8c1f_4c2dbc28ae57,
          0,
          1u,
          &GUID_aabbc97e_7d38_46b2_a27b_e631b519b79b,
          &v56);
  v10 = v28;
  if ( v28 < 0 )
  {
    v29 = 275;
LABEL_49:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v29,
      (unsigned int)"onecore\\admin\\appmodel\\common\\manifestreader.cpp",
      (const char *)(unsigned int)v28,
      ppva);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v56);
LABEL_50:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v52);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v53);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v54);
    goto LABEL_51;
  }
  v30 = v56;
  v31 = *(__int64 (__fastcall **)(LPVOID, struct IStream *, __int64, struct IAppxManifestReader **))(*(_QWORD *)v56 + 24LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v53);
  v28 = v31(v30, v62, v27, &v53);
  v10 = v28;
  if ( v28 < 0 )
  {
    v29 = 279;
    goto LABEL_49;
  }
  v32 = v53;
  v33 = v53->lpVtbl->GetPackageId;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v54);
  v28 = ((__int64 (__fastcall *)(struct IAppxManifestReader *, __int64 *))v33)(v32, &v54);
  v10 = v28;
  if ( v28 < 0 )
  {
    v29 = 280;
    goto LABEL_49;
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v56);
LABEL_65:
  pv = 0;
  v40 = (*(__int64 (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v54 + 72LL))(v54, &pv);
  v10 = v40;
  if ( v40 < 0 )
  {
    v43 = (unsigned int)v40;
    v44 = 300;
LABEL_75:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v44,
      (unsigned int)"onecore\\admin\\appmodel\\common\\manifestreader.cpp",
      (const char *)v43,
      ppva);
    CoTaskMemFree(pv);
    goto LABEL_50;
  }
  *v51 = 5;
  if ( v22 )
  {
    if ( (Microsoft_Windows_AppXDeployment_ServerEnableBits & 0x40) != 0 )
      McTemplateU0zz_EventWriteTransfer(v42, ManifestCacheEntryReloaded, v72, pv);
    details::appxLog<unsigned short const *,unsigned short *>(0, v41, ManifestCacheEntryReloaded, v72);
  }
  else if ( !Common::String::CaseInsensitiveEquals((const unsigned __int16 *)pv, (const unsigned __int16 *)v72) )
  {
    v10 = -2147023728;
    v43 = 2147943568LL;
    v44 = 310;
    goto LABEL_75;
  }
  if ( a6 )
  {
    v45 = v53;
    v53 = 0;
    *a6 = v45;
  }
  else
  {
    v46 = v52;
    v52 = 0;
    *a7 = v46;
  }
  wil::ActivityBase<AppXDeploymentServerTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v73, 0);
  CoTaskMemFree(pv);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v52);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v53);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v54);
  StateRepository::Entity::PkgExtensionHost::~PkgExtensionHost((StateRepository::Entity::PkgExtensionHost *)v63);
  StateRepository::Entity::Package::~Package((StateRepository::Entity::Package *)v71);
  Common::AutoPtrDeallocate<ARI::DependencyMiniRepository::Sections::Globalization>(v11);
  v10 = 0;
LABEL_78:
  AppXDeploymentServerTelemetry::LoadingManifestFromDisk_GetManifestReaderFromValidatedManifestImpl::~LoadingManifestFromDisk_GetManifestReaderFromValidatedManifestImpl((AppXDeploymentServerTelemetry::LoadingManifestFromDisk_GetManifestReaderFromValidatedManifestImpl *)v73);
  return v10;
}

```

## disassembly

```asm
0x1801eb3e4  push    rbp
0x1801eb3e6  push    rbx
0x1801eb3e7  push    rsi
0x1801eb3e8  push    rdi
0x1801eb3e9  push    r12
0x1801eb3eb  push    r13
0x1801eb3ed  push    r14
0x1801eb3ef  push    r15
0x1801eb3f1  lea     rbp, [rsp-288h]
0x1801eb3f9  sub     rsp, 388h
0x1801eb400  mov     rax, cs:__security_cookie
0x1801eb407  xor     rax, rsp
0x1801eb40a  mov     [rbp+2C0h+var_50], rax
0x1801eb411  mov     r14, r9
0x1801eb414  mov     rbx, r8
0x1801eb417  mov     [rsp+3C0h+var_368], rbx
0x1801eb41c  mov     [rbp+2C0h+var_328], rdx
0x1801eb420  mov     rsi, rcx
0x1801eb423  mov     rax, [rbp+2C0h+arg_20]
0x1801eb42a  mov     [rsp+3C0h+var_388], rax
0x1801eb42f  mov     r15, [rbp+2C0h+arg_28]
0x1801eb436  mov     r13, [rbp+2C0h+arg_30]
0x1801eb43d  lea     rdx, aLoadingmanifes_0; "LoadingManifestFromDisk_GetManifestRead"...
0x1801eb444  lea     rcx, [rbp+2C0h+var_1A0]; struct wil::details::IFailureCallback *
0x1801eb44b  call    ??0?$ActivityBase@VAppXDeploymentServerTelemetry@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<AppXDeploymentServerTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<AppXDeploymentServerTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x1801eb450  lea     rax, ??_7LoadingManifestFromDisk_GetManifestReaderFromValidatedManifestImpl@AppXDeploymentServerTelemetry@@6B@; const AppXDeploymentServerTelemetry::LoadingManifestFromDisk_GetManifestReaderFromValidatedManifestImpl::`vftable'
0x1801eb457  mov     [rbp+2C0h+var_1A0], rax
0x1801eb45e  mov     r8, rbx; unsigned __int16 *
0x1801eb461  mov     rdx, r14; unsigned __int16 *
0x1801eb464  lea     rcx, [rbp+2C0h+var_1A0]; this
0x1801eb46b  call    ?StartActivity@LoadingManifestFromDisk_GetManifestReaderFromValidatedManifestImpl@AppXDeploymentServerTelemetry@@QEAAXPEBG0@Z; AppXDeploymentServerTelemetry::LoadingManifestFromDisk_GetManifestReaderFromValidatedManifestImpl::StartActivity(ushort const *,ushort const *)
0x1801eb470  nop
0x1801eb471  lea     rax, [rbp+2C0h+var_1A0]
0x1801eb478  mov     [rbp+2C0h+var_2D0], rax
0x1801eb47c  lea     rax, [rsp+3C0h+var_388]
0x1801eb481  mov     [rbp+2C0h+var_2C8], rax
0x1801eb485  mov     [rbp+2C0h+var_2C0], 1
0x1801eb489  xor     r12d, r12d
0x1801eb48c  mov     ecx, r12d
0x1801eb48f  test    r13, r13
0x1801eb492  setnz   cl
0x1801eb495  mov     eax, r12d
0x1801eb498  test    r15, r15
0x1801eb49b  setnz   al
0x1801eb49e  cmp     eax, ecx
0x1801eb4a0  jnz     short loc_1801EB4C7
0x1801eb4a2  mov     rcx, [rbp+2C8h]; this
0x1801eb4a9  mov     edi, 80070057h
0x1801eb4ae  mov     r9d, edi; char *
0x1801eb4b1  lea     r8, aOnecoreAdminAp_138; "onecore\\admin\\appmodel\\common\\manif"...
0x1801eb4b8  mov     edx, 0AAh; void *
0x1801eb4bd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801eb4c2  jmp     loc_1801EB71B
0x1801eb4c7  mov     rax, [rsp+3C0h+var_388]
0x1801eb4cc  mov     [rax], r12d
0x1801eb4cf  test    r15, r15
0x1801eb4d2  jz      short loc_1801EB4D9
0x1801eb4d4  mov     [r15], r12
0x1801eb4d7  jmp     short loc_1801EB4DD
0x1801eb4d9  mov     [r13+0], r12
0x1801eb4dd  mov     rbx, r12
0x1801eb4e0  mov     [rsp+3C0h+var_348], rbx
0x1801eb4e5  mov     rcx, [rsi+20h]
0x1801eb4e9  test    rcx, rcx
0x1801eb4ec  jnz     short loc_1801EB530
0x1801eb4ee  lea     rcx, [rsp+3C0h+var_348]; struct PackageRepository::IRepositorySession **
0x1801eb4f3  call    ?GetReadOnlySession@Repository@PackageRepository@@SAJPEAPEAVIRepositorySession@2@@Z; PackageRepository::Repository::GetReadOnlySession(PackageRepository::IRepositorySession * *)
0x1801eb4f8  mov     edi, eax
0x1801eb4fa  test    eax, eax
0x1801eb4fc  jns     short loc_1801EB524
0x1801eb4fe  mov     rcx, [rbp+2C8h]; this
0x1801eb505  mov     r9d, eax; char *
0x1801eb508  lea     r8, aOnecoreAdminAp_138; "onecore\\admin\\appmodel\\common\\manif"...
0x1801eb50f  mov     edx, 0BBh; void *
0x1801eb514  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801eb519  nop
0x1801eb51a  mov     rcx, [rsp+3C0h+var_348]
0x1801eb51f  jmp     loc_1801EB715
0x1801eb524  mov     rbx, [rsp+3C0h+var_348]
0x1801eb529  mov     [rsi+20h], rbx
0x1801eb52d  mov     rcx, rbx
0x1801eb530  mov     rax, [rcx]
0x1801eb533  mov     rax, [rax+8]
0x1801eb537  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801eb53c  mov     r12, rax
0x1801eb53f  mov     rdx, rax; struct StateRepository::Database *
0x1801eb542  mov     rcx, rsi; this
0x1801eb545  call    ?ProcessManifestCacheInvalidations@ValidatedManifestReaderHelper@Deployment@Common@@QEAAJAEAVDatabase@StateRepository@@@Z; Common::Deployment::ValidatedManifestReaderHelper::ProcessManifestCacheInvalidations(StateRepository::Database &)
0x1801eb54a  mov     edi, eax
0x1801eb54c  test    eax, eax
0x1801eb54e  jns     short loc_1801EB570
0x1801eb550  mov     rcx, [rbp+2C8h]; this
0x1801eb557  mov     r9d, eax; char *
0x1801eb55a  lea     r8, aOnecoreAdminAp_138; "onecore\\admin\\appmodel\\common\\manif"...
0x1801eb561  mov     edx, 0C1h; void *
0x1801eb566  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801eb56b  jmp     loc_1801EB712
0x1801eb570  lea     rcx, [rbp+2C0h+var_2B0]; this
0x1801eb574  call    ??0Package@Entity@StateRepository@@QEAA@XZ; StateRepository::Entity::Package::Package(void)
0x1801eb579  nop
0x1801eb57a  mov     [rsp+3C0h+var_390], 0
0x1801eb57f  test    r14, r14
0x1801eb582  jnz     loc_1801EB632
0x1801eb588  mov     rax, [rsp+3C0h+var_368]
0x1801eb58d  mov     [rsi+10h], rax
0x1801eb591  mov     rax, [rsp+3C0h+var_388]
0x1801eb596  mov     dword ptr [rax], 1
0x1801eb59c  test    r13, r13
0x1801eb59f  setnz   dl; bool
0x1801eb5a2  mov     rcx, rsi; this
0x1801eb5a5  call    ?GetPackageInstalledLocationFromManifestPath@ValidatedManifestReaderHelper@Deployment@Common@@AEAAJ_N@Z; Common::Deployment::ValidatedManifestReaderHelper::GetPackageInstalledLocationFromManifestPath(bool)
0x1801eb5aa  mov     r14d, eax
0x1801eb5ad  test    eax, eax
0x1801eb5af  jns     short loc_1801EB5F4
0x1801eb5b1  mov     edi, 80070490h
0x1801eb5b6  cmp     eax, edi
0x1801eb5b8  jz      loc_1801EB708
0x1801eb5be  mov     rcx, [rbp+2C8h]; this
0x1801eb5c5  mov     r9d, eax; char *
0x1801eb5c8  lea     r8, aOnecoreAdminAp_138; "onecore\\admin\\appmodel\\common\\manif"...
0x1801eb5cf  mov     edx, 0CAh; void *
0x1801eb5d4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801eb5d9  nop
0x1801eb5da  lea     rcx, [rbp+2C0h+var_2B0]; this
0x1801eb5de  call    ??1Package@Entity@StateRepository@@QEAA@XZ; StateRepository::Entity::Package::~Package(void)
0x1801eb5e3  nop
0x1801eb5e4  mov     rcx, rbx
0x1801eb5e7  call    ??$AutoPtrDeallocate@VGlobalization@Sections@DependencyMiniRepository@ARI@@@Common@@YAXPEAVGlobalization@Sections@DependencyMiniRepository@ARI@@@Z; Common::AutoPtrDeallocate<ARI::DependencyMiniRepository::Sections::Globalization>(ARI::DependencyMiniRepository::Sections::Globalization *)
0x1801eb5ec  mov     edi, r14d
0x1801eb5ef  jmp     loc_1801EB71B
0x1801eb5f4  lea     r9, [rsp+3C0h+var_390]; bool *
0x1801eb5f9  lea     r8, [rbp+2C0h+var_2B0]; struct StateRepository::Entity::Package *
0x1801eb5fd  mov     rdx, [rsi+18h]; unsigned __int16 *
0x1801eb601  mov     rcx, r12; this
0x1801eb604  call    ?TryGetByInstalledLocation@Package@Entity@StateRepository@@SAJAEAVDatabase@3@PEBGAEAV123@AEA_N@Z; StateRepository::Entity::Package::TryGetByInstalledLocation(StateRepository::Database &,ushort const *,StateRepository::Entity::Package &,bool &)
0x1801eb609  mov     edi, eax
0x1801eb60b  xor     r12d, r12d
0x1801eb60e  test    eax, eax
0x1801eb610  jns     short loc_1801EB661
0x1801eb612  mov     edx, 0CBh; void *
0x1801eb617  mov     rcx, [rbp+2C8h]; this
0x1801eb61e  mov     r9d, eax; char *
0x1801eb621  lea     r8, aOnecoreAdminAp_138; "onecore\\admin\\appmodel\\common\\manif"...
0x1801eb628  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801eb62d  jmp     loc_1801EB708
0x1801eb632  mov     rax, [rsp+3C0h+var_388]
0x1801eb637  mov     dword ptr [rax], 2
0x1801eb63d  lea     r9, [rsp+3C0h+var_390]; bool *
0x1801eb642  lea     r8, [rbp+2C0h+var_2B0]; struct StateRepository::Entity::Package *
0x1801eb646  mov     rdx, r14; unsigned __int16 *
0x1801eb649  mov     rcx, r12; struct StateRepository::Database *
0x1801eb64c  call    ?TryGetByPackageFullName@Package@Entity@StateRepository@@SAJAEAVDatabase@3@PEBGAEAV123@AEA_N@Z; StateRepository::Entity::Package::TryGetByPackageFullName(StateRepository::Database &,ushort const *,StateRepository::Entity::Package &,bool &)
0x1801eb651  mov     edi, eax
0x1801eb653  xor     r12d, r12d
0x1801eb656  test    eax, eax
0x1801eb658  jns     short loc_1801EB661
0x1801eb65a  mov     edx, 0D0h
0x1801eb65f  jmp     short loc_1801EB617
0x1801eb661  cmp     [rsp+3C0h+var_390], r12b
0x1801eb666  jnz     short loc_1801EB684
0x1801eb668  lea     rcx, [rbp+2C0h+var_2B0]; this
0x1801eb66c  call    ??1Package@Entity@StateRepository@@QEAA@XZ; StateRepository::Entity::Package::~Package(void)
0x1801eb671  nop
0x1801eb672  mov     rcx, rbx
0x1801eb675  call    ??$AutoPtrDeallocate@VGlobalization@Sections@DependencyMiniRepository@ARI@@@Common@@YAXPEAVGlobalization@Sections@DependencyMiniRepository@ARI@@@Z; Common::AutoPtrDeallocate<ARI::DependencyMiniRepository::Sections::Globalization>(ARI::DependencyMiniRepository::Sections::Globalization *)
0x1801eb67a  mov     edi, 80070490h
0x1801eb67f  jmp     loc_1801EB71B
0x1801eb684  mov     rax, [rsp+3C0h+var_388]
0x1801eb689  mov     [rax], r12d
0x1801eb68c  cmp     [rsi+8], r12b
0x1801eb690  jz      short loc_1801EB6C4
0x1801eb692  mov     rax, [rsi]
0x1801eb695  xor     r8d, r8d
0x1801eb698  mov     rdx, [rbp+2C0h+var_2B0]
0x1801eb69c  mov     rcx, rsi
0x1801eb69f  mov     rax, [rax+20h]
0x1801eb6a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801eb6a8  mov     edi, eax
0x1801eb6aa  test    eax, eax
0x1801eb6ac  jns     short loc_1801EB6B8
0x1801eb6ae  mov     edx, 0E1h
0x1801eb6b3  jmp     loc_1801EB617
0x1801eb6b8  mov     [rsi+8], r12b
0x1801eb6bc  mov     r14b, 1
0x1801eb6bf  jmp     loc_1801EB78D
0x1801eb6c4  xorps   xmm0, xmm0
0x1801eb6c7  movups  xmmword ptr [rbp+2C0h+var_340], xmm0
0x1801eb6cb  mov     [rbp+2C0h+var_330], r12d
0x1801eb6cf  lea     rdx, [rbp+2C0h+var_340]; Common::StringBuffer *
0x1801eb6d3  mov     rcx, [rbp+2C0h+var_270]; this
0x1801eb6d7  call    ?GetPackageFamilyNameFromFullName@Deployment@Common@@YAJPEBGPEAVStringBuffer@2@@Z; Common::Deployment::GetPackageFamilyNameFromFullName(ushort const *,Common::StringBuffer *)
0x1801eb6dc  mov     edi, eax
0x1801eb6de  test    eax, eax
0x1801eb6e0  jns     short loc_1801EB733
0x1801eb6e2  mov     edx, 0EAh; void *
0x1801eb6e7  mov     rcx, [rbp+2C8h]; this
0x1801eb6ee  mov     r9d, eax; char *
0x1801eb6f1  lea     r8, aOnecoreAdminAp_138; "onecore\\admin\\appmodel\\common\\manif"...
0x1801eb6f8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801eb6fd  nop
0x1801eb6fe  lea     rcx, [rbp+2C0h+var_340]; this
0x1801eb702  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x1801eb707  nop
0x1801eb708  lea     rcx, [rbp+2C0h+var_2B0]; this
0x1801eb70c  call    ??1Package@Entity@StateRepository@@QEAA@XZ; StateRepository::Entity::Package::~Package(void)
0x1801eb711  nop
0x1801eb712  mov     rcx, rbx
0x1801eb715  call    ??$AutoPtrDeallocate@VGlobalization@Sections@DependencyMiniRepository@ARI@@@Common@@YAXPEAVGlobalization@Sections@DependencyMiniRepository@ARI@@@Z; Common::AutoPtrDeallocate<ARI::DependencyMiniRepository::Sections::Globalization>(ARI::DependencyMiniRepository::Sections::Globalization *)
0x1801eb71a  nop
0x1801eb71b  mov     rdx, [rsp+3C0h+var_388]
0x1801eb720  mov     edx, [rdx]; unsigned int
0x1801eb722  lea     rcx, [rbp+2C0h+var_1A0]; this
0x1801eb729  call    ?Stop@LoadingManifestFromDisk_GetManifestReaderFromValidatedManifestImpl@AppXDeploymentServerTelemetry@@QEAAXI@Z; AppXDeploymentServerTelemetry::LoadingManifestFromDisk_GetManifestReaderFromValidatedManifestImpl::Stop(uint)
0x1801eb72e  jmp     loc_1801EBB86
0x1801eb733  mov     [rsp+3C0h+var_350], r12d
0x1801eb738  lea     rdx, [rsp+3C0h+var_350]
0x1801eb73d  mov     rcx, [rbp+2C0h+var_340+8]
0x1801eb741  call    cs:__imp_IsPackageInUpdatedApplicationsKey
0x1801eb747  mov     edi, eax
0x1801eb749  test    eax, eax
0x1801eb74b  jns     short loc_1801EB754
0x1801eb74d  mov     edx, 0EDh
0x1801eb752  jmp     short loc_1801EB6E7
0x1801eb754  mov     r14b, r12b
0x1801eb757  cmp     [rsp+3C0h+var_350], r12d
0x1801eb75c  jz      short loc_1801EB784
0x1801eb75e  xor     r9d, r9d; int
0x1801eb761  mov     r8, [rbp+2C0h+var_340+8]; unsigned __int16 *
0x1801eb765  mov     rdx, [rbp+2C0h+var_2B0]; __int64
0x1801eb769  mov     rcx, rsi; this
0x1801eb76c  call    ?ReloadManifestCacheForPackage@ValidatedManifestReaderHelper@Deployment@Common@@QEAAJ_JPEBGH@Z; Common::Deployment::ValidatedManifestReaderHelper::ReloadManifestCacheForPackage(__int64,ushort const *,int)
0x1801eb771  mov     edi, eax
0x1801eb773  test    eax, eax
0x1801eb775  jns     short loc_1801EB781
0x1801eb777  mov     edx, 0F0h
0x1801eb77c  jmp     loc_1801EB6E7
0x1801eb781  mov     r14b, 1
0x1801eb784  lea     rcx, [rbp+2C0h+var_340]; this
0x1801eb788  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x1801eb78d  mov     [rbp+2C0h+var_320], r12
0x1801eb791  mov     [rbp+2C0h+var_318], r12
0x1801eb795  xorps   xmm0, xmm0
0x1801eb798  movdqa  [rbp+2C0h+var_310], xmm0
0x1801eb79d  xorps   xmm1, xmm1
0x1801eb7a0  movdqa  [rbp+2C0h+var_300], xmm1
0x1801eb7a5  movdqa  [rbp+2C0h+var_2F0], xmm0
0x1801eb7aa  mov     [rbp+2C0h+var_2E0], r12
0x1801eb7ae  mov     rcx, [rsi+20h]
0x1801eb7b2  mov     rax, [rcx]
0x1801eb7b5  mov     rax, [rax+10h]
0x1801eb7b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801eb7be  mov     [rsp+3C0h+var_390], r12b
0x1801eb7c3  lea     r9, [rsp+3C0h+var_390]; bool *
0x1801eb7c8  lea     r8, [rbp+2C0h+var_320]; struct StateRepository::Entity::AppxManifest *
0x1801eb7cc  mov     rdx, [rbp+2C0h+var_2B0]; __int64
0x1801eb7d0  mov     rcx, rax; this
0x1801eb7d3  call    ?TryGetByPackage@AppxManifest@Entity@StateRepository@@SAJAEAVDatabase@3@_JAEAV123@AEA_N@Z; StateRepository::Entity::AppxManifest::TryGetByPackage(StateRepository::Database &,__int64,StateRepository::Entity::AppxManifest &,bool &)
0x1801eb7d8  mov     edi, eax
0x1801eb7da  test    eax, eax
0x1801eb7dc  jns     short loc_1801EB7FE
0x1801eb7de  mov     rcx, [rbp+2C8h]; this
0x1801eb7e5  mov     r9d, eax; char *
0x1801eb7e8  lea     r8, aOnecoreAdminAp_138; "onecore\\admin\\appmodel\\common\\manif"...
0x1801eb7ef  mov     edx, 0FAh; void *
0x1801eb7f4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801eb7f9  jmp     loc_1801EB8D4
0x1801eb7fe  mov     rax, [rsp+3C0h+var_388]
0x1801eb803  mov     dword ptr [rax], 3
0x1801eb809  cmp     [rsp+3C0h+var_390], r12b
0x1801eb80e  jnz     short loc_1801EB81E
0x1801eb810  lea     rcx, [rbp+2C0h+var_320]; this
0x1801eb814  call    ??1PkgExtensionHost@Entity@StateRepository@@QEAA@XZ; StateRepository::Entity::PkgExtensionHost::~PkgExtensionHost(void)
0x1801eb819  jmp     loc_1801EB668
0x1801eb81e  mov     r12, qword ptr [rbp+2C0h+var_300]
0x1801eb822  mov     rax, [rsp+3C0h+var_388]
0x1801eb827  mov     dword ptr [rax], 4
0x1801eb82d  xor     esi, esi
0x1801eb82f  test    r12, r12
0x1801eb832  jz      short loc_1801EB810
0x1801eb834  mov     rax, [rsp+3C0h+var_388]
0x1801eb839  mov     [rax], esi
0x1801eb83b  mov     [rsp+3C0h+var_370], rsi
0x1801eb840  mov     [rsp+3C0h+var_378], rsi
0x1801eb845  mov     [rsp+3C0h+var_380], rsi
0x1801eb84a  test    r15, r15
0x1801eb84d  jz      loc_1801EB964
0x1801eb853  mov     [rsp+3C0h+var_360], rsi
0x1801eb858  lea     rcx, [rsp+3C0h+var_360]
0x1801eb85d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801eb862  lea     rax, [rsp+3C0h+var_360]
0x1801eb867  mov     qword ptr [rsp+3C0h+ppv], rax; int
0x1801eb86c  lea     r9, _GUID_aabbc97e_7d38_46b2_a27b_e631b519b79b; riid
0x1801eb873  xor     edx, edx; pUnkOuter
0x1801eb875  lea     r8d, [rsi+1]; dwClsContext
0x1801eb879  lea     rcx, _GUID_fad63700_aafb_463a_8c1f_4c2dbc28ae57; rclsid
0x1801eb880  call    cs:__imp_CoCreateInstance
0x1801eb886  mov     edi, eax
0x1801eb888  test    eax, eax
0x1801eb88a  jns     short loc_1801EB8E2
0x1801eb88c  mov     edx, 113h; void *
  ... truncated ...
```
