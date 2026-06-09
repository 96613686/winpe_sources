# AppReadiness::Tasks::RegisterPackage::OnExecute(void)

- ea: `0x18006a160`
- end: `0x18006add8`
- name: `?OnExecute@RegisterPackage@Tasks@AppReadiness@@MEAAXXZ`
- size: `3192`
- prototype: `void __fastcall(AppReadiness::Tasks::RegisterPackage *__hidden this)`
- caller_count: `0`
- callee_count: `36`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x180001008`
- `0x180002958`
- `0x180002a60`
- `0x180005270`
- `0x180006630`
- `0x1800091a0`
- `0x18000a470`
- `0x18000e1d8`
- `0x18000e4a0`
- `0x1800148b0`
- `0x180017998`
- `0x1800180f8`
- `0x18001870c`
- `0x180019260`
- `0x180019448`
- `0x1800194d4`
- `0x18001d548`
- `0x180020bdc`
- `0x1800211dc`
- `0x180023270`
- `0x18002503c`
- `0x180027a4c`
- `0x180028814`
- `0x18002c38c`
- `0x18002c548`
- `0x180035874`
- `0x180036f90`
- `0x1800399b8`
- `0x180039d8c`
- `0x180039eec`
- `0x18003e210`
- `0x18003ecb4`
- `0x180049310`
- `0x18005f1c0`
- `0x18006a160`
- `0x180079010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18006aaa3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18006aaa3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006a495`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006a580`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006a9ed`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006aae0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006a495`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006a580`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006a9ed`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006aae0`
- `AppXDeploymentClient!__imp_AppxPreRegisterPackage` at `0x18006a6f9`
- `AppXDeploymentClient!__imp_AppxPreRegisterPackage` at `0x18006a6f9`

## string_xrefs

- `0x18006ab3a`: `deploymentOperation->put_Completed(this)`
- `0x18006a400`: `onecoreuap\shell\appreadiness\src\tasks\registerpackage.cpp`
- `0x18006abd3`: `onecoreuap\shell\appreadiness\src\tasks\registerpackage.cpp`
- `0x18006ac11`: `onecoreuap\shell\appreadiness\src\tasks\registerpackage.cpp`
- `0x18006ac24`: `m_uriFactory->CreateUri(packageUriString.Get(), packageUri.GetAddressOf())`
- `0x18006aba8`: `packageManager->RegisterPackageWithAppDataVolumeForUserAsync( packageUri.Get(), nullptr, static_cast<DeploymentOptionsInternal>(deploymentOptions), nullptr, GetUser()->GetUserContext(), &deploymentOperation)`
- `0x18006ab33`: `AppReadiness::Tasks::RegisterPackage::OnExecute`
- `0x18006ab6a`: `AppReadiness::Tasks::RegisterPackage::OnExecute`
- `0x18006aba1`: `AppReadiness::Tasks::RegisterPackage::OnExecute`
- `0x18006abdf`: `AppReadiness::Tasks::RegisterPackage::OnExecute`
- `0x18006ac1d`: `AppReadiness::Tasks::RegisterPackage::OnExecute`
- `0x18006ac9b`: `AppReadiness::Tasks::RegisterPackage::OnExecute`
- `0x18006acd2`: `AppReadiness::Tasks::RegisterPackage::OnExecute`
- `0x18006ad09`: `AppReadiness::Tasks::RegisterPackage::OnExecute`
- `0x18006ad40`: `AppReadiness::Tasks::RegisterPackage::OnExecute`
- `0x18006ad77`: `AppReadiness::Tasks::RegisterPackage::OnExecute`
- `0x18006adae`: `AppReadiness::Tasks::RegisterPackage::OnExecute`
- `0x18006abe6`: `packageUriString.Set(manifestPath.c_str(), static_cast<UINT>(manifestPath.length()))`
- `0x18006ad7e`: `packageManager->RegisterPackageWithAppDataVolumeForUserAsync( packageUri.Get(), nullptr, static_cast<DeploymentOptionsInternal>(deploymentOptions), volume.Get(), GetUser()->GetUserContext(), &deploymentOperation)`

## pseudocode

```c
void __fastcall AppReadiness::Tasks::RegisterPackage::OnExecute(AppReadiness::Tasks::RegisterPackage *this)
{
  __int64 v2; // rax
  char v3; // di
  AppReadiness::PackageInfo *v4; // rsi
  AppReadiness::User *v5; // rax
  unsigned __int8 (__fastcall *v6)(AppReadiness::PackageInfo *, __int64); // rbx
  __int64 v7; // rax
  unsigned __int8 (__fastcall *v8)(AppReadiness::PackageInfo *, __int64); // rbx
  __int64 v9; // rax
  const unsigned __int16 *v10; // rdx
  int v11; // eax
  int v12; // eax
  unsigned __int8 (__fastcall *v13)(AppReadiness::PackageInfo *, __int64); // rbx
  __int64 v14; // rax
  int v15; // edi
  bool v16; // zf
  int v17; // eax
  unsigned int v18; // ebx
  unsigned int v19; // r12d
  __int64 v20; // rbx
  HSTRING v21; // r13
  __int64 v22; // rax
  int PackageTaskResult; // ebx
  AppReadiness::User *v24; // rax
  HSTRING v25; // rdi
  const unsigned __int16 *v26; // rdx
  __int64 v27; // rbx
  __int64 (__fastcall *v28)(__int64, _QWORD, _BYTE *); // r12
  const unsigned __int16 *v29; // rdx
  _QWORD *v30; // rax
  int v31; // eax
  int v32; // eax
  AppReadiness::User *v33; // rax
  struct Windows::Internal::StateRepository::IUser *StateRepositoryUser; // r12
  __int64 v35; // rbx
  const unsigned __int16 *v36; // rdx
  _QWORD *v37; // rax
  int v38; // eax
  __int64 v39; // rax
  int v40; // ebx
  int v41; // r12d
  __int64 v42; // rax
  int v43; // ebx
  __int64 v44; // rcx
  int v45; // eax
  __int64 v46; // rcx
  const unsigned __int16 *v47; // rcx
  int v48; // ebx
  AppReadiness::User *v49; // rax
  const unsigned __int16 *v50; // rdx
  int v51; // ecx
  int v52; // r8d
  int v53; // r9d
  HSTRING v54; // rax
  int v55; // ecx
  int v56; // r8d
  int v57; // r9d
  __int64 v58; // rax
  HSTRING v59; // rdi
  __int64 (__fastcall *v60)(HSTRING, __int64, _QWORD, _QWORD, _QWORD, _QWORD, __int64 *); // rbx
  __int64 v61; // rax
  int v62; // eax
  HSTRING v63; // rbx
  __int64 (__fastcall *v64)(HSTRING, GUID *, __int64 (__fastcall **)(__int64, struct Windows::Internal::StateRepository::IUser *, _QWORD, _BYTE *)); // rdi
  int v65; // eax
  WCHAR *v66; // rdx
  int v67; // eax
  __int64 (__fastcall *v68)(_QWORD, _QWORD, _QWORD, _QWORD); // rsi
  __int64 (__fastcall *v69)(_QWORD, _QWORD, _QWORD); // rdi
  int v70; // eax
  __int64 (__fastcall *v71)(HSTRING, __int64, _QWORD, _QWORD, __int64, _QWORD, __int64 *); // rdi
  __int64 v72; // rax
  int v73; // eax
  char *v74; // rdx
  int v75; // eax
  char *v76; // rdx
  int v77; // eax
  int v78; // [rsp+20h] [rbp-E0h]
  int v79; // [rsp+20h] [rbp-E0h]
  _BYTE v80[8]; // [rsp+40h] [rbp-C0h] BYREF
  HSTRING string; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v82; // [rsp+50h] [rbp-B0h] BYREF
  __int64 (__fastcall *v83)(__int64, struct Windows::Internal::StateRepository::IUser *, _QWORD, _BYTE *); // [rsp+58h] [rbp-A8h] BYREF
  __int64 v84; // [rsp+60h] [rbp-A0h] BYREF
  HSTRING v85; // [rsp+68h] [rbp-98h] BYREF
  PSRWLOCK SRWLock; // [rsp+70h] [rbp-90h] BYREF
  std::_Ref_count_base *v87; // [rsp+78h] [rbp-88h]
  HSTRING v88; // [rsp+80h] [rbp-80h] BYREF
  __int64 v89; // [rsp+88h] [rbp-78h] BYREF
  _BYTE pExceptionObject[40]; // [rsp+90h] [rbp-70h] BYREF
  AppReadiness::PackageInfo *v91; // [rsp+B8h] [rbp-48h] BYREF
  std::_Ref_count_base *v92; // [rsp+C0h] [rbp-40h]
  WCHAR sourceString[8]; // [rsp+C8h] [rbp-38h] BYREF
  unsigned int v94[2]; // [rsp+D8h] [rbp-28h]
  unsigned __int64 v95; // [rsp+E0h] [rbp-20h]
  unsigned __int16 *v96[2]; // [rsp+F0h] [rbp-10h] BYREF
  unsigned int v97; // [rsp+100h] [rbp+0h]
  unsigned __int64 v98; // [rsp+108h] [rbp+8h]
  wil::details::in1diag3 *retaddr; // [rsp+168h] [rbp+68h]

  v2 = (*(__int64 (__fastcall **)(AppReadiness::Tasks::RegisterPackage *, PSRWLOCK *))(*(_QWORD *)this + 80LL))(
         this,
         &SRWLock);
  std::weak_ptr<AppReadiness::PackageInfo>::lock(v2, &v91);
  if ( v87 )
    std::_Ref_count_base::_Decwref(v87);
  v3 = (*(__int64 (__fastcall **)(AppReadiness::Tasks::RegisterPackage *, __int64))(*(_QWORD *)this + 136LL))(
         this,
         0x1000000);
  v4 = v91;
  if ( !v3 && (*((_BYTE *)v91 + 140) & 2) == 0 )
  {
    v5 = (AppReadiness::User *)(*(__int64 (__fastcall **)(AppReadiness::Tasks::RegisterPackage *))(*(_QWORD *)this
                                                                                                 + 112LL))(this);
    if ( !AppReadiness::User::IsSpecialProfile(v5) )
    {
      v6 = *(unsigned __int8 (__fastcall **)(AppReadiness::PackageInfo *, __int64))(*(_QWORD *)v4 + 8LL);
      v7 = (*(__int64 (__fastcall **)(AppReadiness::Tasks::RegisterPackage *))(*(_QWORD *)this + 112LL))(this);
      if ( v6(v4, v7) )
      {
        v8 = *(unsigned __int8 (__fastcall **)(AppReadiness::PackageInfo *, __int64))(*(_QWORD *)v4 + 16LL);
        v9 = (*(__int64 (__fastcall **)(AppReadiness::Tasks::RegisterPackage *))(*(_QWORD *)this + 112LL))(this);
        if ( !v8(v4, v9) )
        {
          AppReadiness::Impl::BaseTask::CompleteTask(this, 0);
          goto LABEL_106;
        }
      }
    }
  }
  v89 = 0;
  v88 = 0;
  AppReadiness::PackageInfo::GetManifestPath(v4, v96);
  v10 = (const unsigned __int16 *)v96;
  if ( v98 > 7 )
    v10 = v96[0];
  v11 = Microsoft::WRL::Wrappers::HString::Set((Microsoft::WRL::Wrappers::HString *)&v88, v10, v97);
  if ( v11 < 0 )
  {
    Windows::HResultException::HResultException(
      (Windows::HResultException *)sourceString,
      v11,
      "packageUriString.Set(manifestPath.c_str(), static_cast<UINT>(manifestPath.length()))",
      "AppReadiness::Tasks::RegisterPackage::OnExecute",
      "onecoreuap\\shell\\appreadiness\\src\\tasks\\registerpackage.cpp",
      188);
    throw (Windows::HResultException *)sourceString;
  }
  v12 = (*(__int64 (__fastcall **)(_QWORD, HSTRING, __int64 *))(**((_QWORD **)this + 32) + 48LL))(
          *((_QWORD *)this + 32),
          v88,
          &v89);
  if ( v12 < 0 )
  {
    Windows::HResultException::HResultException(
      (Windows::HResultException *)sourceString,
      v12,
      "m_uriFactory->CreateUri(packageUriString.Get(), packageUri.GetAddressOf())",
      "AppReadiness::Tasks::RegisterPackage::OnExecute",
      "onecoreuap\\shell\\appreadiness\\src\\tasks\\registerpackage.cpp",
      189);
    throw (Windows::HResultException *)sourceString;
  }
  if ( v3
    || (*(unsigned __int8 (__fastcall **)(AppReadiness::Tasks::RegisterPackage *, __int64))(*(_QWORD *)this + 136LL))(
         this,
         0x400000)
    || (v13 = *(unsigned __int8 (__fastcall **)(AppReadiness::PackageInfo *, __int64))(*(_QWORD *)v4 + 24LL),
        v14 = (*(__int64 (__fastcall **)(AppReadiness::Tasks::RegisterPackage *))(*(_QWORD *)this + 112LL))(this),
        !v13(v4, v14)) )
  {
    v15 = 64;
  }
  else
  {
    v15 = 0;
  }
  v82 = 0;
  if ( !*(_BYTE *)((*(__int64 (__fastcall **)(AppReadiness::Tasks::RegisterPackage *))(*(_QWORD *)this + 112LL))(this)
                 + 177)
    || (v16 = !AppReadiness::PackageInfo::IsBundle(v4), v17 = 544, v16) )
  {
    v17 = 512;
  }
  v18 = v17 | v15 | (*((_DWORD *)v4 + 35) >> 4) & 2;
  if ( (unsigned __int8)LogonOptimizationPermitted() )
  {
    if ( *(_DWORD *)((*(__int64 (__fastcall **)(AppReadiness::Tasks::RegisterPackage *))(*(_QWORD *)this + 112LL))(this)
                   + 380) == 2
      && (*((_BYTE *)v4 + 184) & 0x10) != 0 )
    {
      v18 |= 0x4000000u;
    }
    else
    {
      v18 |= 0x2000000u;
    }
  }
  v19 = AppReadiness::Tasks::RegisterPackage::AdjustDeploymentOptionsForUserLogon((char *)this - 32, v18);
  LODWORD(v84) = v19;
  v20 = (*(__int64 (__fastcall **)(AppReadiness::Tasks::RegisterPackage *))(*(_QWORD *)this + 24LL))(this);
  v21 = (HSTRING)((char *)v4 + 40);
  v22 = (*(__int64 (__fastcall **)(AppReadiness::Tasks::RegisterPackage *))(*(_QWORD *)this + 112LL))(this);
  PackageTaskResult = AppReadiness::Storage::PackageList::GetPackageTaskResult(v22, (char *)v4 + 40, v20);
  v24 = (AppReadiness::User *)(*(__int64 (__fastcall **)(AppReadiness::Tasks::RegisterPackage *))(*(_QWORD *)this + 112LL))(this);
  v25 = (HSTRING)((char *)v4 + 72);
  if ( *((_QWORD *)v4 + 12) <= 7u )
    v26 = (const unsigned __int16 *)((char *)v4 + 72);
  else
    v26 = *(const unsigned __int16 **)v25;
  if ( AppReadiness::User::IsForceInstalledPackage(v24, v26)
    || (*((_BYTE *)v4 + 184) & 0x40) == 0
    || PackageTaskResult == -2147009255 )
  {
    v49 = (AppReadiness::User *)(*(__int64 (__fastcall **)(AppReadiness::Tasks::RegisterPackage *))(*(_QWORD *)this
                                                                                                  + 112LL))(this);
    if ( *((_QWORD *)v4 + 12) <= 7u )
      v50 = (const unsigned __int16 *)((char *)v4 + 72);
    else
      v50 = *(const unsigned __int16 **)v25;
    if ( AppReadiness::User::IsForceInstalledPackage(v49, v50)
      && (unsigned int)dword_1800A2208 > 5
      && (unsigned __int8)tlgKeywordOn(&dword_1800A2208, 0x400000000000LL) )
    {
      SRWLock = (PSRWLOCK)0x1000000;
      if ( *((_QWORD *)v4 + 12) <= 7u )
        v54 = (HSTRING)((char *)v4 + 72);
      else
        v54 = *(HSTRING *)v25;
      string = v54;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>>(
        v51,
        (unsigned int)&byte_1800935F7,
        v52,
        v53,
        (__int64)&string,
        (__int64)&SRWLock);
    }
    if ( PackageTaskResult == -2147009255
      && (unsigned int)dword_1800A2208 > 5
      && (unsigned __int8)tlgKeywordOn(&dword_1800A2208, 0x400000000000LL) )
    {
      SRWLock = (PSRWLOCK)0x1000000;
      if ( *((_QWORD *)v4 + 12) > 7u )
        v25 = *(HSTRING *)v25;
      string = v25;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>>(
        v55,
        (unsigned int)&word_1800935A6,
        v56,
        v57,
        (__int64)&string,
        (__int64)&SRWLock);
    }
  }
  else
  {
    if ( (*((_BYTE *)v4 + 140) & 0x40) == 0 )
      goto LABEL_48;
    v80[0] = 0;
    v27 = *((_QWORD *)this + 34);
    v28 = *(__int64 (__fastcall **)(__int64, _QWORD, _BYTE *))(*(_QWORD *)v27 + 120LL);
    if ( *((_QWORD *)v4 + 12) <= 7u )
      v29 = (const unsigned __int16 *)((char *)v4 + 72);
    else
      v29 = *(const unsigned __int16 **)v25;
    std::wstring::wstring(sourceString, v29);
    v30 = (_QWORD *)to_winstring(&string, sourceString);
    v31 = v28(v27, *v30, v80);
    if ( v31 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0xEC,
        (unsigned int)"onecoreuap\\shell\\appreadiness\\src\\tasks\\registerpackage.cpp",
        (const char *)(unsigned int)v31,
        v78);
    WindowsDeleteString(string);
    string = 0;
    std::pair<std::wstring,enum AppReadiness::Storage::PackageOperation>::~pair<std::wstring,enum AppReadiness::Storage::PackageOperation>(sourceString);
    if ( !v80[0] )
    {
      v32 = AppReadiness::System::PreRegisterInboxPackagesIfNeeded();
      if ( v32 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0xEF,
          (unsigned int)"onecoreuap\\shell\\appreadiness\\src\\tasks\\registerpackage.cpp",
          (const char *)(unsigned int)v32,
          v78);
    }
    if ( !AppReadiness::System::IsSharedAppsEnabled()
      || !*(_BYTE *)((*(__int64 (__fastcall **)(AppReadiness::Tasks::RegisterPackage *))(*(_QWORD *)this + 112LL))(this)
                   + 177) )
    {
      goto LABEL_48;
    }
    v33 = (AppReadiness::User *)(*(__int64 (__fastcall **)(AppReadiness::Tasks::RegisterPackage *))(*(_QWORD *)this
                                                                                                  + 112LL))(this);
    StateRepositoryUser = AppReadiness::User::GetStateRepositoryUser(v33);
    if ( !StateRepositoryUser )
      goto LABEL_80;
    v35 = *((_QWORD *)this + 34);
    v83 = *(__int64 (__fastcall **)(__int64, struct Windows::Internal::StateRepository::IUser *, _QWORD, _BYTE *))(*(_QWORD *)v35 + 352LL);
    if ( *((_QWORD *)v4 + 12) <= 7u )
      v36 = (const unsigned __int16 *)((char *)v4 + 72);
    else
      v36 = *(const unsigned __int16 **)v25;
    std::wstring::wstring(sourceString, v36);
    v37 = (_QWORD *)to_winstring(&string, sourceString);
    v38 = v83(v35, StateRepositoryUser, *v37, v80);
    if ( v38 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0xFA,
        (unsigned int)"onecoreuap\\shell\\appreadiness\\src\\tasks\\registerpackage.cpp",
        (const char *)(unsigned int)v38,
        v78);
    WindowsDeleteString(string);
    string = 0;
    std::pair<std::wstring,enum AppReadiness::Storage::PackageOperation>::~pair<std::wstring,enum AppReadiness::Storage::PackageOperation>(sourceString);
    if ( !v80[0] )
    {
LABEL_80:
      v19 = v84;
    }
    else
    {
LABEL_48:
      v39 = AppReadiness::PackageInfo::GetPackageManager<Windows::Management::Deployment::Internal::IPackageManagerInternal>(&string);
      Microsoft::WRL::ComPtr<AppReadiness::ITask>::ComPtr<AppReadiness::ITask>(&v83, v39);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&string);
      SRWLock = *(PSRWLOCK *)(*(_QWORD *)v83 + 536LL);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v82);
      v40 = ((*(unsigned __int8 (__fastcall **)(AppReadiness::Tasks::RegisterPackage *, __int64))(*(_QWORD *)this + 136LL))(
               this,
               0x400000) != 0)
          + 3;
      v41 = (*(unsigned __int8 (__fastcall **)(AppReadiness::Tasks::RegisterPackage *, __int64))(*(_QWORD *)this + 136LL))(
              this,
              0x200000) != 0
          ? 0x100000
          : 0;
      v85 = *(HSTRING *)((*(__int64 (__fastcall **)(AppReadiness::Tasks::RegisterPackage *))(*(_QWORD *)this + 112LL))(this)
                       + 96);
      if ( *((_QWORD *)v4 + 8) > 7u )
        v21 = *(HSTRING *)v21;
      string = v21;
      v42 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(sourceString, &string);
      v79 = v41;
      v19 = v84;
      v43 = ((__int64 (__fastcall *)(__int64 (__fastcall *)(__int64, struct Windows::Internal::StateRepository::IUser *, _QWORD, _BYTE *), _QWORD, HSTRING, _QWORD, int, int, __int64 *))SRWLock)(
              v83,
              *(_QWORD *)(v42 + 24),
              v85,
              (unsigned int)v84,
              v79,
              v40,
              &v82);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v83);
      if ( v43 != -2147009295 )
      {
        if ( v43 < 0 )
        {
          Windows::HResultException::HResultException(
            (Windows::HResultException *)sourceString,
            v43,
            "result",
            "AppReadiness::Tasks::RegisterPackage::OnExecute",
            "onecoreuap\\shell\\appreadiness\\src\\tasks\\registerpackage.cpp",
            305);
          throw (Windows::HResultException *)sourceString;
        }
        goto LABEL_92;
      }
      if ( (Microsoft_Windows_AppReadinessEnableBits & 0x1000) != 0 )
        McTemplateU0z_EventWriteTransfer(v44, Package_PreRegistration_Start);
      if ( (*((_BYTE *)v4 + 140) & 0x40) != 0 )
      {
        v45 = AppReadiness::System::PreRegisterInboxPackagesIfNeeded();
      }
      else
      {
        if ( *((_QWORD *)v4 + 12) <= 7u )
          v47 = (const unsigned __int16 *)((char *)v4 + 72);
        else
          v47 = *(const unsigned __int16 **)v25;
        v45 = AppxPreRegisterPackage(v47, 0);
      }
      v48 = v45;
      if ( v45 < 0 )
      {
        if ( (Microsoft_Windows_AppReadinessEnableBits & 0x40000) != 0 )
        {
          if ( *((_QWORD *)v4 + 12) > 7u )
            v25 = *(HSTRING *)v25;
          McTemplateU0zd_EventWriteTransfer(v46, Package_PreRegistration_Failure, v25, (unsigned int)v45);
        }
        Windows::HResultException::HResultException(
          (Windows::HResultException *)sourceString,
          v48,
          "result",
          "AppReadiness::Tasks::RegisterPackage::OnExecute",
          "onecoreuap\\shell\\appreadiness\\src\\tasks\\registerpackage.cpp",
          299);
        throw (Windows::HResultException *)sourceString;
      }
      if ( (Microsoft_Windows_AppReadinessEnableBits & 0x1000) != 0 )
        McTemplateU0z_EventWriteTransfer(v46, Package_PreRegistration_Stop);
    }
  }
  v58 = AppReadiness::PackageInfo::GetPackageManager<Windows::Management::Deployment::Internal::IPackageManagerInternal>(&SRWLock);
  Microsoft::WRL::ComPtr<AppReadiness::ITask>::ComPtr<AppReadiness::ITask>(&string, v58);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&SRWLock);
  std::wstring::wstring(sourceString, (char *)v4 + 152);
  if ( *(_QWORD *)v94 )
  {
    v83 = 0;
    v63 = string;
    v64 = **(__int64 (__fastcall ***)(HSTRING, GUID *, __int64 (__fastcall **)(__int64, struct Windows::Internal::StateRepository::IUser *, _QWORD, _BYTE *)))string;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v83);
    v65 = v64(v63, &GUID_daad9948_36f1_41a7_9188_bc263e0dcb72, &v83);
    if ( v65 < 0 )
    {
      Windows::HResultException::HResultException(
        (Windows::HResultException *)pExceptionObject,
        v65,
        "packageManager.As(&packageManager3)",
        "AppReadiness::Tasks::RegisterPackage::OnExecute",
        "onecoreuap\\shell\\appreadiness\\src\\tasks\\registerpackage.cpp",
        354);
      throw (Windows::HResultException *)pExceptionObject;
    }
    v85 = 0;
    v66 = sourceString;
    if ( v95 > 7 )
      v66 = *(WCHAR **)sourceString;
    v67 = Microsoft::WRL::Wrappers::HString::Set((Microsoft::WRL::Wrappers::HString *)&v85, v66, v94[0]);
    if ( v67 < 0 )
    {
      Windows::HResultException::HResultException(
        (Windows::HResultException *)pExceptionObject,
        v67,
        "appDataVolumeNameString.Set(appDataVolumeName.c_str(), static_cast<UINT>(appDataVolumeName.length()))",
        "AppReadiness::Tasks::RegisterPackage::OnExecute",
        "onecoreuap\\shell\\appreadiness\\src\\tasks\\registerpackage.cpp",
        357);
      throw (Windows::HResultException *)pExceptionObject;
    }
    v84 = 0;
    v68 = (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))v83;
    v69 = *(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))(*(_QWORD *)v83 + 80LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v84);
    v70 = v69(v68, v85, &v84);
    if ( v70 < 0 )
    {
      Windows::HResultException::HResultException(
        (Windows::HResultException *)pExceptionObject,
        v70,
        "packageManager3->FindPackageVolumeByName(appDataVolumeNameString.Get(), &volume)",
        "AppReadiness::Tasks::RegisterPackage::OnExecute",
        "onecoreuap\\shell\\appreadiness\\src\\tasks\\registerpackage.cpp",
        360);
      throw (Windows::HResultException *)pExceptionObject;
    }
    v71 = *(__int64 (__fastcall **)(HSTRING, __int64, _QWORD, _QWORD, __int64, _QWORD, __int64 *))(*(_QWORD *)v63 + 560LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v82);
    v72 = (*(__int64 (__fastcall **)(AppReadiness::Tasks::RegisterPackage *))(*(_QWORD *)this + 112LL))(this);
    v73 = v71(v63, v89, 0, v19, v84, *(_QWORD *)(v72 + 96), &v82);
    if ( v73 < 0 )
    {
      Windows::HResultException::HResultException(
        (Windows::HResultException *)pExceptionObject,
        v73,
        "packageManager->RegisterPackageWithAppDataVolumeForUserAsync( packageUri.Get(), nullptr, static_cast<DeploymentO"
        "ptionsInternal>(deploymentOptions), volume.Get(), GetUser()->GetUserContext(), &deploymentOperation)",
        "AppReadiness::Tasks::RegisterPackage::OnExecute",
        "onecoreuap\\shell\\appreadiness\\src\\tasks\\registerpackage.cpp",
        368);
      throw (Windows::HResultException *)pExceptionObject;
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v84);
    WindowsDeleteString(v85);
    v85 = 0;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v83);
  }
  else
  {
    v59 = string;
    v60 = *(__int64 (__fastcall **)(HSTRING, __int64, _QWORD, _QWORD, _QWORD, _QWORD, __int64 *))(*(_QWORD *)string
                                                                                                + 560LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v82);
    v61 = (*(__int64 (__fastcall **)(AppReadiness::Tasks::RegisterPackage *))(*(_QWORD *)this + 112LL))(this);
    v62 = v60(v59, v89, 0, v19, 0, *(_QWORD *)(v61 + 96), &v82);
    if ( v62 < 0 )
    {
      Windows::HResultException::HResultException(
        (Windows::HResultException *)pExceptionObject,
        v62,
        "packageManager->RegisterPackageWithAppDataVolumeForUserAsync( packageUri.Get(), nullptr, static_cast<DeploymentO"
        "ptionsInternal>(deploymentOptions), nullptr, GetUser()->GetUserContext(), &deploymentOperation)",
        "AppReadiness::Tasks::RegisterPackage::OnExecute",
        "onecoreuap\\shell\\appreadiness\\src\\tasks\\registerpackage.cpp",
        349);
      throw (Windows::HResultException *)pExceptionObject;
    }
  }
  std::pair<std::wstring,enum AppReadiness::Storage::PackageOperation>::~pair<std::wstring,enum AppReadiness::Storage::PackageOperation>(sourceString);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&string);
LABEL_92:
  if ( v82 )
  {
    if ( this == (AppReadiness::Tasks::RegisterPackage *)32 )
      v74 = 0;
    else
      v74 = (char *)this + 240;
    v75 = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v82 + 48LL))(v82, v74);
    if ( v75 < 0 )
    {
      Windows::HResultException::HResultException(
        (Windows::HResultException *)pExceptionObject,
        v75,
        "deploymentOperation->put_Progress(this)",
        "AppReadiness::Tasks::RegisterPackage::OnExecute",
        "onecoreuap\\shell\\appreadiness\\src\\tasks\\registerpackage.cpp",
        376);
      throw (Windows::HResultException *)pExceptionObject;
    }
    if ( this == (AppReadiness::Tasks::RegisterPackage *)32 )
      v76 = 0;
    else
      v76 = (char *)this + 232;
    v77 = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v82 + 64LL))(v82, v76);
    if ( v77 < 0 )
    {
      Windows::HResultException::HResultException(
        (Windows::HResultException *)pExceptionObject,
        v77,
        "deploymentOperation->put_Completed(this)",
        "AppReadiness::Tasks::RegisterPackage::OnExecute",
        "onecoreuap\\shell\\appreadiness\\src\\tasks\\registerpackage.cpp",
        377);
      throw (Windows::HResultException *)pExceptionObject;
    }
    Microsoft::WRL::Wrappers::SRWLock::LockExclusive(&SRWLock, (char *)this + 56);
    Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationWithProgress<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress>>::operator=(
      (char *)this + 264,
      &v82);
    if ( SRWLock )
      ReleaseSRWLockExclusive(SRWLock);
    if ( *((_BYTE *)this + 196) )
      (*(void (__fastcall **)(AppReadiness::Tasks::RegisterPackage *))(*(_QWORD *)this + 208LL))(this);
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v82);
  std::pair<std::wstring,enum AppReadiness::Storage::PackageOperation>::~pair<std::wstring,enum AppReadiness::Storage::PackageOperation>(v96);
  WindowsDeleteString(v88);
  v88 = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v89);
LABEL_106:
  if ( v92 )
    std::_Ref_count_base::_Decref(v92);
}

```

## disassembly

```asm
0x18006a160  push    rbp
0x18006a162  push    rbx
0x18006a163  push    rsi
0x18006a164  push    rdi
0x18006a165  push    r12
0x18006a167  push    r13
0x18006a169  push    r14
0x18006a16b  push    r15
0x18006a16d  lea     rbp, [rsp-28h]
0x18006a172  sub     rsp, 128h
0x18006a179  mov     rax, cs:__security_cookie
0x18006a180  xor     rax, rsp
0x18006a183  mov     [rbp+60h+var_50], rax
0x18006a187  mov     r14, rcx
0x18006a18a  mov     rax, [rcx]
0x18006a18d  lea     rdx, [rsp+160h+SRWLock]
0x18006a192  mov     rax, [rax+50h]
0x18006a196  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a19b  lea     rdx, [rbp+60h+var_A8]
0x18006a19f  mov     rcx, rax
0x18006a1a2  call    ?lock@?$weak_ptr@VPackageInfo@AppReadiness@@@std@@QEBA?AV?$shared_ptr@VPackageInfo@AppReadiness@@@2@XZ; std::weak_ptr<AppReadiness::PackageInfo>::lock(void)
0x18006a1a7  nop
0x18006a1a8  mov     rcx, [rsp+160h+var_E8]; this
0x18006a1ad  test    rcx, rcx
0x18006a1b0  jz      short loc_18006A1B7
0x18006a1b2  call    ?_Decwref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decwref(void)
0x18006a1b7  mov     rax, [r14]
0x18006a1ba  mov     edx, 1000000h
0x18006a1bf  mov     rcx, r14
0x18006a1c2  mov     rax, [rax+88h]
0x18006a1c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a1ce  mov     dil, al
0x18006a1d1  mov     rsi, [rbp+60h+var_A8]
0x18006a1d5  test    al, al
0x18006a1d7  jnz     loc_18006A260
0x18006a1dd  test    byte ptr [rsi+8Ch], 2
0x18006a1e4  jnz     short loc_18006A260
0x18006a1e6  mov     rcx, [r14]
0x18006a1e9  mov     rax, [rcx+70h]
0x18006a1ed  mov     rcx, r14
0x18006a1f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a1f5  mov     rcx, rax; this
0x18006a1f8  call    ?IsSpecialProfile@User@AppReadiness@@QEAA_NXZ; AppReadiness::User::IsSpecialProfile(void)
0x18006a1fd  test    al, al
0x18006a1ff  jnz     short loc_18006A260
0x18006a201  mov     rax, [rsi]
0x18006a204  mov     rbx, [rax+8]
0x18006a208  mov     rcx, [r14]
0x18006a20b  mov     rax, [rcx+70h]
0x18006a20f  mov     rcx, r14
0x18006a212  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a217  mov     rdx, rax
0x18006a21a  mov     rcx, rsi
0x18006a21d  mov     rax, rbx
0x18006a220  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a225  test    al, al
0x18006a227  jz      short loc_18006A260
0x18006a229  mov     rax, [rsi]
0x18006a22c  mov     rbx, [rax+10h]
0x18006a230  mov     rcx, [r14]
0x18006a233  mov     rax, [rcx+70h]
0x18006a237  mov     rcx, r14
0x18006a23a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a23f  mov     rdx, rax
0x18006a242  mov     rcx, rsi
0x18006a245  mov     rax, rbx
0x18006a248  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a24d  test    al, al
0x18006a24f  jnz     short loc_18006A260
0x18006a251  xor     edx, edx; int
0x18006a253  mov     rcx, r14; this
0x18006a256  call    ?CompleteTask@BaseTask@Impl@AppReadiness@@IEAA_NJ@Z; AppReadiness::Impl::BaseTask::CompleteTask(long)
0x18006a25b  jmp     loc_18006AAF8
0x18006a260  mov     [rbp+60h+var_D8], 0
0x18006a268  mov     [rbp+60h+var_E0], 0
0x18006a270  lea     rdx, [rbp+60h+var_70]
0x18006a274  mov     rcx, rsi
0x18006a277  call    ?GetManifestPath@PackageInfo@AppReadiness@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; AppReadiness::PackageInfo::GetManifestPath(void)
0x18006a27c  nop
0x18006a27d  lea     rdx, [rbp+60h+var_70]
0x18006a281  cmp     [rbp+60h+var_58], 7
0x18006a286  cmova   rdx, [rbp+60h+var_70]; unsigned __int16 *
0x18006a28b  mov     r8d, [rbp+60h+var_60]; unsigned int
0x18006a28f  lea     rcx, [rbp+60h+var_E0]; this
0x18006a293  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJPEBGI@Z; Microsoft::WRL::Wrappers::HString::Set(ushort const *,uint)
0x18006a298  test    eax, eax
0x18006a29a  js      loc_18006ABCB
0x18006a2a0  mov     rcx, [r14+100h]
0x18006a2a7  mov     rax, [rcx]
0x18006a2aa  lea     r8, [rbp+60h+var_D8]
0x18006a2ae  mov     rdx, [rbp+60h+var_E0]
0x18006a2b2  mov     rax, [rax+30h]
0x18006a2b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a2bb  test    eax, eax
0x18006a2bd  js      loc_18006AC09
0x18006a2c3  test    dil, dil
0x18006a2c6  jnz     short loc_18006A30F
0x18006a2c8  mov     rax, [r14]
0x18006a2cb  mov     edx, 400000h
0x18006a2d0  mov     rcx, r14
0x18006a2d3  mov     rax, [rax+88h]
0x18006a2da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a2df  test    al, al
0x18006a2e1  jnz     short loc_18006A30F
0x18006a2e3  mov     rax, [rsi]
0x18006a2e6  mov     rbx, [rax+18h]
0x18006a2ea  mov     rcx, [r14]
0x18006a2ed  mov     rax, [rcx+70h]
0x18006a2f1  mov     rcx, r14
0x18006a2f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a2f9  mov     rdx, rax
0x18006a2fc  mov     rcx, rsi
0x18006a2ff  mov     rax, rbx
0x18006a302  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a307  test    al, al
0x18006a309  jz      short loc_18006A30F
0x18006a30b  xor     edi, edi
0x18006a30d  jmp     short loc_18006A314
0x18006a30f  mov     edi, 40h ; '@'
0x18006a314  mov     [rsp+160h+var_110], 0
0x18006a31d  mov     rax, [r14]
0x18006a320  mov     rcx, r14
0x18006a323  mov     rax, [rax+70h]
0x18006a327  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a32c  cmp     byte ptr [rax+0B1h], 0
0x18006a333  jz      short loc_18006A346
0x18006a335  mov     rcx, rsi; this
0x18006a338  call    ?IsBundle@PackageInfo@AppReadiness@@QEAA_NXZ; AppReadiness::PackageInfo::IsBundle(void)
0x18006a33d  test    al, al
0x18006a33f  mov     eax, 220h
0x18006a344  jnz     short loc_18006A34B
0x18006a346  mov     eax, 200h
0x18006a34b  mov     ebx, [rsi+8Ch]
0x18006a351  shr     ebx, 4
0x18006a354  and     ebx, 2
0x18006a357  or      ebx, edi
0x18006a359  or      ebx, eax
0x18006a35b  call    ?LogonOptimizationPermitted@@YA_NW4LogonOptimizationFlags@@_N@Z; LogonOptimizationPermitted(LogonOptimizationFlags,bool)
0x18006a360  test    al, al
0x18006a362  jz      short loc_18006A38F
0x18006a364  mov     rax, [r14]
0x18006a367  mov     rcx, r14
0x18006a36a  mov     rax, [rax+70h]
0x18006a36e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a373  cmp     dword ptr [rax+17Ch], 2
0x18006a37a  jnz     short loc_18006A38B
0x18006a37c  test    byte ptr [rsi+0B8h], 10h
0x18006a383  jz      short loc_18006A38B
0x18006a385  bts     ebx, 1Ah
0x18006a389  jmp     short loc_18006A38F
0x18006a38b  bts     ebx, 19h
0x18006a38f  mov     edx, ebx
0x18006a391  lea     rcx, [r14-20h]
0x18006a395  call    ?AdjustDeploymentOptionsForUserLogon@RegisterPackage@Tasks@AppReadiness@@AEAA?AW4DeploymentOptions@Deployment@Management@Windows@@W44567@@Z; AppReadiness::Tasks::RegisterPackage::AdjustDeploymentOptionsForUserLogon(Windows::Management::Deployment::DeploymentOptions)
0x18006a39a  mov     r12d, eax
0x18006a39d  mov     dword ptr [rsp+160h+var_100], eax
0x18006a3a1  mov     rcx, [r14]
0x18006a3a4  mov     rax, [rcx+18h]
0x18006a3a8  mov     rcx, r14
0x18006a3ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a3b0  mov     rbx, rax
0x18006a3b3  lea     r13, [rsi+28h]
0x18006a3b7  mov     rcx, [r14]
0x18006a3ba  mov     rax, [rcx+70h]
0x18006a3be  mov     rcx, r14
0x18006a3c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a3c6  mov     r8, rbx
0x18006a3c9  mov     rdx, r13
0x18006a3cc  mov     rcx, rax
0x18006a3cf  call    ?GetPackageTaskResult@PackageList@Storage@AppReadiness@@SAJPEAVUser@3@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@1@Z; AppReadiness::Storage::PackageList::GetPackageTaskResult(AppReadiness::User *,std::wstring const &,std::wstring const &)
0x18006a3d4  mov     ebx, eax
0x18006a3d6  mov     rcx, [r14]
0x18006a3d9  mov     rax, [rcx+70h]
0x18006a3dd  mov     rcx, r14
0x18006a3e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a3e5  lea     rdi, [rsi+48h]
0x18006a3e9  cmp     qword ptr [rdi+18h], 7
0x18006a3ee  jbe     short loc_18006A3F5
0x18006a3f0  mov     rdx, [rdi]
0x18006a3f3  jmp     short loc_18006A3F8
0x18006a3f5  mov     rdx, rdi; unsigned __int16 *
0x18006a3f8  mov     rcx, rax; this
0x18006a3fb  call    ?IsForceInstalledPackage@User@AppReadiness@@QEAA_NPEBG@Z; AppReadiness::User::IsForceInstalledPackage(ushort const *)
0x18006a400  lea     r15, aOnecoreuapShel_9; "onecoreuap\\shell\\appreadiness\\src\\t"...
0x18006a407  test    al, al
0x18006a409  jnz     loc_18006A741
0x18006a40f  test    byte ptr [rsi+0B8h], 40h
0x18006a416  jz      loc_18006A741
0x18006a41c  cmp     ebx, 80073D19h
0x18006a422  jz      loc_18006A741
0x18006a428  test    byte ptr [rsi+8Ch], 40h
0x18006a42f  jz      loc_18006A5AF
0x18006a435  mov     [rsp+160h+var_120], al
0x18006a439  mov     rbx, [r14+110h]
0x18006a440  mov     rax, [rbx]
0x18006a443  mov     r12, [rax+78h]
0x18006a447  cmp     qword ptr [rdi+18h], 7
0x18006a44c  jbe     short loc_18006A453
0x18006a44e  mov     rdx, [rdi]
0x18006a451  jmp     short loc_18006A456
0x18006a453  mov     rdx, rdi
0x18006a456  lea     rcx, [rbp+60h+sourceString]
0x18006a45a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18006a45f  nop
0x18006a460  lea     rdx, [rbp+60h+sourceString]; sourceString
0x18006a464  lea     rcx, [rsp+160h+string]; string
0x18006a469  call    ?to_winstring@@YA?AVHString@Wrappers@WRL@Microsoft@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; to_winstring(std::wstring const &)
0x18006a46e  nop
0x18006a46f  lea     r8, [rsp+160h+var_120]
0x18006a474  mov     rdx, [rax]
0x18006a477  mov     rcx, rbx
0x18006a47a  mov     rax, r12
0x18006a47d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a482  mov     rcx, [rbp+68h]; this
0x18006a486  xor     ebx, ebx
0x18006a488  test    eax, eax
0x18006a48a  js      loc_18006AC47
0x18006a490  mov     rcx, [rsp+160h+string]; string
0x18006a495  call    cs:__imp_WindowsDeleteString
0x18006a49b  mov     [rsp+160h+string], rbx
0x18006a4a0  lea     rcx, [rbp+60h+sourceString]
0x18006a4a4  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4PackageOperation@Storage@AppReadiness@@@std@@QEAA@XZ; std::pair<std::wstring,AppReadiness::Storage::PackageOperation>::~pair<std::wstring,AppReadiness::Storage::PackageOperation>(void)
0x18006a4a9  cmp     [rsp+160h+var_120], bl
0x18006a4ad  jnz     short loc_18006A4CC
0x18006a4af  call    ?PreRegisterInboxPackagesIfNeeded@System@AppReadiness@@SAJXZ; AppReadiness::System::PreRegisterInboxPackagesIfNeeded(void)
0x18006a4b4  mov     rcx, [rbp+68h]; this
0x18006a4b8  test    eax, eax
0x18006a4ba  jns     short loc_18006A4CC
0x18006a4bc  mov     r9d, eax; char *
0x18006a4bf  mov     r8, r15; unsigned int
0x18006a4c2  mov     edx, 0EFh; void *
0x18006a4c7  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18006a4cc  call    ?IsSharedAppsEnabled@System@AppReadiness@@SA_NXZ; AppReadiness::System::IsSharedAppsEnabled(void)
0x18006a4d1  test    al, al
0x18006a4d3  jz      loc_18006A5AF
0x18006a4d9  mov     rax, [r14]
0x18006a4dc  mov     rcx, r14
0x18006a4df  mov     rax, [rax+70h]
0x18006a4e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a4e8  cmp     [rax+0B1h], bl
0x18006a4ee  jz      loc_18006A5AF
0x18006a4f4  mov     rax, [r14]
0x18006a4f7  mov     rcx, r14
0x18006a4fa  mov     rax, [rax+70h]
0x18006a4fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a503  mov     rcx, rax; this
0x18006a506  call    ?GetStateRepositoryUser@User@AppReadiness@@QEAAPEAUIUser@StateRepository@Internal@Windows@@XZ; AppReadiness::User::GetStateRepositoryUser(void)
0x18006a50b  mov     r12, rax
0x18006a50e  test    rax, rax
0x18006a511  jz      loc_18006A834
0x18006a517  mov     rbx, [r14+110h]
0x18006a51e  mov     rcx, [rbx]
0x18006a521  mov     rax, [rcx+160h]
0x18006a528  mov     [rsp+160h+var_108], rax
0x18006a52d  cmp     qword ptr [rdi+18h], 7
0x18006a532  jbe     short loc_18006A539
0x18006a534  mov     rdx, [rdi]
0x18006a537  jmp     short loc_18006A53C
0x18006a539  mov     rdx, rdi
0x18006a53c  lea     rcx, [rbp+60h+sourceString]
0x18006a540  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18006a545  nop
0x18006a546  lea     rdx, [rbp+60h+sourceString]; sourceString
0x18006a54a  lea     rcx, [rsp+160h+string]; string
0x18006a54f  call    ?to_winstring@@YA?AVHString@Wrappers@WRL@Microsoft@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; to_winstring(std::wstring const &)
0x18006a554  nop
0x18006a555  lea     r9, [rsp+160h+var_120]
0x18006a55a  mov     r8, [rax]
0x18006a55d  mov     rdx, r12
0x18006a560  mov     rcx, rbx
0x18006a563  mov     rax, [rsp+160h+var_108]
0x18006a568  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a56d  mov     rcx, [rbp+68h]; this
0x18006a571  test    eax, eax
0x18006a573  js      loc_18006AC58
0x18006a579  xor     bl, bl
0x18006a57b  mov     rcx, [rsp+160h+string]; string
0x18006a580  call    cs:__imp_WindowsDeleteString
0x18006a586  mov     [rsp+160h+string], 0
0x18006a58f  lea     rcx, [rbp+60h+sourceString]
0x18006a593  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4PackageOperation@Storage@AppReadiness@@@std@@QEAA@XZ; std::pair<std::wstring,AppReadiness::Storage::PackageOperation>::~pair<std::wstring,AppReadiness::Storage::PackageOperation>(void)
0x18006a598  movzx   eax, bl
0x18006a59b  mov     ecx, 1
0x18006a5a0  cmp     [rsp+160h+var_120], bl
0x18006a5a4  cmovz   eax, ecx
0x18006a5a7  test    al, al
0x18006a5a9  jnz     loc_18006A834
0x18006a5af  lea     rcx, [rsp+160h+string]
0x18006a5b4  call    ??$GetPackageManager@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@@PackageInfo@AppReadiness@@SA?AV?$ComPtr@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@@WRL@Microsoft@@XZ; AppReadiness::PackageInfo::GetPackageManager<Windows::Management::Deployment::Internal::IPackageManagerInternal>(void)
0x18006a5b9  mov     rdx, rax
0x18006a5bc  lea     rcx, [rsp+160h+var_108]
0x18006a5c1  call    ??0?$ComPtr@UITask@AppReadiness@@@WRL@Microsoft@@QEAA@$$QEAV012@@Z; Microsoft::WRL::ComPtr<AppReadiness::ITask>::ComPtr<AppReadiness::ITask>(Microsoft::WRL::ComPtr<AppReadiness::ITask> &&)
0x18006a5c6  nop
0x18006a5c7  lea     rcx, [rsp+160h+string]
0x18006a5cc  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18006a5d1  mov     rax, [rsp+160h+var_108]
0x18006a5d6  mov     rax, [rax]
0x18006a5d9  mov     rax, [rax+218h]
0x18006a5e0  mov     [rsp+160h+SRWLock], rax
0x18006a5e5  lea     rcx, [rsp+160h+var_110]
  ... truncated ...
```
