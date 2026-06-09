# AppReadiness::User::ProcessTasks(void)

- ea: `0x180010afc`
- end: `0x1800115ad`
- name: `?ProcessTasks@User@AppReadiness@@QEAAXXZ`
- size: `2737`
- prototype: `void __fastcall(HANDLE *this)`
- caller_count: `1`
- callee_count: `55`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1800109f0`

## callees

- `0x180001008`
- `0x180002958`
- `0x180003580`
- `0x180004e00`
- `0x1800091a0`
- `0x180009380`
- `0x180009d00`
- `0x18000b530`
- `0x18000bb90`
- `0x18000c750`
- `0x18000d860`
- `0x18000e4a0`
- `0x18000e5b4`
- `0x18000f3d0`
- `0x180010afc`
- `0x180012784`
- `0x180014220`
- `0x18001488c`
- `0x18001aef0`
- `0x18001c238`
- `0x18001cbdc`
- `0x18001db50`
- `0x18001e268`
- `0x18001ea8c`
- `0x1800203d8`
- `0x180020acc`
- `0x180021184`
- `0x1800211dc`
- `0x180021224`
- `0x180022ae0`
- `0x18002489c`
- `0x18002503c`
- `0x180026954`
- `0x180027340`
- `0x180027a4c`
- `0x18002b63c`
- `0x18002c824`
- `0x18002efa4`
- `0x18002f170`
- `0x180036f90`
- `0x1800397cc`
- `0x180039eec`
- `0x18003b5d8`
- `0x18003bf50`
- `0x18003e210`
- `0x18003eca8`
- `0x18003ecb4`
- `0x180049f8c`
- `0x18004d8b8`
- `0x180059fb4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800113cb`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800113cb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSemaphore` at `0x180011485`
- `api-ms-win-core-synch-l1-1-0!ReleaseSemaphore` at `0x180011485`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800114b7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800114b7`
- `ntdll!RtlIsStateSeparationEnabled` at `0x180010bde`
- `ntdll!RtlIsStateSeparationEnabled` at `0x180010cda`
- `ntdll!RtlIsStateSeparationEnabled` at `0x180010bde`
- `ntdll!RtlIsStateSeparationEnabled` at `0x180010cda`
- `ext-ms-win-kernel32-package-l1-1-0!PackageFamilyNameFromFullName` at `0x180010f03`
- `ext-ms-win-kernel32-package-l1-1-0!PackageFamilyNameFromFullName` at `0x180010f03`
- `AppXDeploymentClient!__imp_AppxPreRegisterPackage` at `0x180010e62`
- `AppXDeploymentClient!__imp_AppxPreRegisterPackage` at `0x180010eb7`
- `AppXDeploymentClient!__imp_AppxPreRegisterPackage` at `0x180010e62`
- `AppXDeploymentClient!__imp_AppxPreRegisterPackage` at `0x180010eb7`
- `AppXDeploymentClient!__imp_ClientGetAllPackagesToBeInstalledForUser` at `0x180010df3`
- `AppXDeploymentClient!__imp_ClientGetAllPackagesToBeInstalledForUser` at `0x180010df3`
- `AppXDeploymentClient!__imp_ClientDeleteAllPackagesFromMainPackageArray` at `0x180010fb4`
- `AppXDeploymentClient!__imp_ClientDeleteAllPackagesFromMainPackageArray` at `0x180010fb4`

## string_xrefs

- `0x180010c1c`: `onecoreuap\shell\appreadiness\src\core\user.cpp`
- `0x1800114de`: `AppReadiness::User::ProcessTasks`
- `0x180011515`: `AppReadiness::User::ProcessTasks`
- `0x18001154c`: `AppReadiness::User::ProcessTasks`
- `0x180011583`: `AppReadiness::User::ProcessTasks`
- `0x1800114e5`: `MakeAndInitialize<Groups::OnDemandSyncGroup>(&task, this)`
- `0x18001151c`: `hrPreinstalled`
- `0x18001158a`: `ClientGetAllPackagesToBeInstalledForUser(nullptr, false, &packages, &packageCount)`

## pseudocode

```c
void __fastcall AppReadiness::User::ProcessTasks(HANDLE *this)
{
  const char *v1; // r13
  int v3; // ebx
  __int64 v4; // rcx
  int UserState; // r14d
  AppReadiness::User *v6; // rcx
  __int64 DefaultAccountSid; // rax
  char v8; // di
  int v9; // eax
  int v10; // eax
  AppReadiness::User *v11; // rcx
  __int64 v12; // rax
  bool v13; // di
  int v14; // eax
  __int64 v15; // rdi
  __int64 (__fastcall *v16)(__int64, __int64, struct ITask **); // rbx
  int v17; // eax
  __int64 v18; // rdx
  int v19; // eax
  int AllPackagesToBeInstalledForUser; // eax
  int v21; // eax
  unsigned int v22; // ebx
  __int64 v23; // rcx
  __int64 v24; // r8
  int v25; // eax
  unsigned int v26; // edi
  __int64 v27; // rbx
  int v28; // eax
  int v29; // eax
  const unsigned __int16 *v30; // rdx
  wil::details::in1diag3 *v31; // rcx
  __int64 v32; // rdx
  int IsStubPreferenceKeyNeededForPackage; // eax
  wil::details::in1diag3 *v34; // rcx
  __int64 v35; // rdx
  int v36; // eax
  struct ITask *v37; // rcx
  int v38; // eax
  bool v39; // bl
  __int64 v40; // r8
  PVOID v41; // rcx
  int v42; // r9d
  _QWORD *v43; // rax
  PVOID v44; // rcx
  char v45; // bl
  struct ITask *v46; // rdx
  _QWORD *v47; // rax
  _QWORD *v48; // r9
  char v49; // di
  _QWORD *v50; // rax
  _QWORD *v51; // r9
  PVOID v52; // rcx
  RTL_SRWLOCK *v53; // rax
  signed int LastError; // eax
  int v55; // edx
  unsigned int v56; // r8d
  int v57; // [rsp+20h] [rbp-E0h]
  bool v58; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v59; // [rsp+34h] [rbp-CCh] BYREF
  struct ITask *v60; // [rsp+38h] [rbp-C8h] BYREF
  struct ITask *v61; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD *v62; // [rsp+48h] [rbp-B8h] BYREF
  UINT32 packageFamilyNameLength; // [rsp+50h] [rbp-B0h] BYREF
  int v64; // [rsp+58h] [rbp-A8h] BYREF
  HANDLE hSemaphore; // [rsp+60h] [rbp-A0h]
  char v66[8]; // [rsp+68h] [rbp-98h] BYREF
  __int64 v67; // [rsp+70h] [rbp-90h]
  __int64 v68; // [rsp+78h] [rbp-88h]
  HSTRING_HEADER pExceptionObject; // [rsp+88h] [rbp-78h] BYREF
  __int64 v70; // [rsp+A0h] [rbp-60h]
  _QWORD v71[2]; // [rsp+B0h] [rbp-50h] BYREF
  WCHAR packageFamilyName[72]; // [rsp+C0h] [rbp-40h] BYREF
  AppReadiness::User *retaddr; // [rsp+188h] [rbp+88h]

  v3 = 0;
  v59 = 0;
  Microsoft::WRL::Wrappers::Semaphore::Lock(this + 18, &v64, 250);
  if ( hSemaphore && (v64 & 0xFFFFFF7F) == 0 )
  {
    if ( (Microsoft_Windows_AppReadinessEnableBits & 0x80u) != 0 )
      McTemplateU0z_EventWriteTransfer(v4, User_ProcessTasks_Start);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, &WPP_2779cad321383337b9ccea6dca676a06_Traceguids);
    AppReadiness::Storage::PackageList::PackageList(
      (AppReadiness::Storage::PackageList *)v66,
      (struct AppReadiness::User *)this);
    UserState = AppReadiness::Storage::PackageList::GetUserState(this);
    if ( !(unsigned __int8)RtlIsStateSeparationEnabled()
      || (DefaultAccountSid = AppReadiness::User::GetDefaultAccountSid(&pExceptionObject),
          v3 = 1,
          v8 = 1,
          !(unsigned __int8)AppReadiness::User::IsUser(this, DefaultAccountSid)) )
    {
      v8 = 0;
    }
    if ( (v3 & 1) != 0 )
    {
      v3 &= ~1u;
      std::pair<std::wstring,enum AppReadiness::Storage::PackageOperation>::~pair<std::wstring,enum AppReadiness::Storage::PackageOperation>(&pExceptionObject);
    }
    v1 = "onecoreuap\\shell\\appreadiness\\src\\core\\user.cpp";
    if ( v8 )
    {
      v9 = AppReadiness::User::CheckForOsUpgrade(v6);
      if ( v9 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x57D,
          (unsigned int)"onecoreuap\\shell\\appreadiness\\src\\core\\user.cpp",
          (const char *)(unsigned int)v9,
          v57);
    }
    if ( AppReadiness::System::IsSharedAppsEnabled() && !*((_BYTE *)this + 177) && !*((_BYTE *)this + 176) )
    {
      AppReadiness::User::CompleteTasks((AppReadiness::User *)this, (struct AppReadiness::Storage::PackageList *)v66);
      if ( *((_BYTE *)this + 217) )
      {
        v61 = 0;
        v71[0] = this;
        v10 = Microsoft::WRL::Details::MakeAndInitialize<AppReadiness::Groups::OnDemandSyncGroup,AppReadiness::ITask,AppReadiness::User *>(
                &v61,
                v71);
        if ( v10 < 0 )
          goto LABEL_142;
        AppReadiness::User::AddTask((AppReadiness::User *)this, v61);
        AppReadiness::User::SetShouldQueryAppx((AppReadiness::User *)this, 0);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v61);
      }
      goto LABEL_70;
    }
    AppReadiness::Storage::PackageList::Read((AppReadiness::Storage::PackageList *)v66);
    AppReadiness::LogUserLoadedPackages(this, v66);
    v13 = 0;
    if ( (unsigned __int8)RtlIsStateSeparationEnabled() && (UserState == 1 || UserState == 4) )
    {
      v12 = AppReadiness::User::GetDefaultAccountSid(&pExceptionObject);
      v3 |= 2u;
      v59 = v3;
      if ( (unsigned __int8)AppReadiness::User::IsUser(this, v12) || AppReadiness::User::IsDefaultAccountDisabled() )
        v13 = 1;
    }
    if ( (v3 & 2) != 0 )
      std::pair<std::wstring,enum AppReadiness::Storage::PackageOperation>::~pair<std::wstring,enum AppReadiness::Storage::PackageOperation>(&pExceptionObject);
    if ( v13 )
    {
      v14 = AppReadiness::User::CleanupPreinstalledVolume(v11);
      if ( v14 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x5A1,
          (unsigned int)"onecoreuap\\shell\\appreadiness\\src\\core\\user.cpp",
          (const char *)(unsigned int)v14,
          v57);
      wil::ActivateInstance<Windows::Management::Deployment::IPackageManager3>(v71);
      v61 = 0;
      v62 = 0;
      v15 = v71[0];
      v16 = *(__int64 (__fastcall **)(__int64, __int64, struct ITask **))(*(_QWORD *)v71[0] + 48LL);
      v70 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(&pExceptionObject, L"P:\\WindowsApps", 0xFu, 0xEu);
      v17 = v16(v15, v70, &v61);
      if ( v17 != -2147024894 )
      {
        if ( v17 < 0 )
        {
          Windows::HResultException::HResultException(
            (Windows::HResultException *)&pExceptionObject,
            v17,
            "hrPreinstalled",
            "AppReadiness::User::ProcessTasks",
            "onecoreuap\\shell\\appreadiness\\src\\core\\user.cpp",
            1454);
          throw (Windows::HResultException *)&pExceptionObject;
        }
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v62);
        v19 = Windows::Management::Deployment::WaitForPackageVolumeOperation(v61, v18, &v62);
        if ( v19 < 0 )
        {
          Windows::HResultException::HResultException(
            (Windows::HResultException *)&pExceptionObject,
            v19,
            "WaitForPackageVolumeOperation(packageVolumeOperation.Get(), nullptr, &packageVolume)",
            "AppReadiness::User::ProcessTasks",
            "onecoreuap\\shell\\appreadiness\\src\\core\\user.cpp",
            1455);
          throw (Windows::HResultException *)&pExceptionObject;
        }
      }
      v59 = 0;
      v60 = 0;
      AllPackagesToBeInstalledForUser = ClientGetAllPackagesToBeInstalledForUser(0, 0, &v60, &v59);
      if ( AllPackagesToBeInstalledForUser < 0 )
      {
        Windows::HResultException::HResultException(
          (Windows::HResultException *)&pExceptionObject,
          AllPackagesToBeInstalledForUser,
          "ClientGetAllPackagesToBeInstalledForUser(nullptr, false, &packages, &packageCount)",
          "AppReadiness::User::ProcessTasks",
          "onecoreuap\\shell\\appreadiness\\src\\core\\user.cpp",
          1461);
        throw (Windows::HResultException *)&pExceptionObject;
      }
      pExceptionObject.Reserved.Reserved1 = &v60;
      *(_QWORD *)&pExceptionObject.Reserved.Reserved2[8] = &v59;
      pExceptionObject.Reserved.Reserved2[16] = 1;
      v21 = AppReadiness::System::PreRegisterInboxPackagesIfNeeded();
      if ( v21 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x5BF,
          (unsigned int)"onecoreuap\\shell\\appreadiness\\src\\core\\user.cpp",
          (const char *)(unsigned int)v21,
          v57);
      v22 = 0;
      v23 = v59;
      if ( v59 )
      {
        do
        {
          v24 = 12LL * v22;
          if ( ((__int64)v60[v24 + 10].lpVtbl & 0x200) != 0 )
          {
            v25 = AppxPreRegisterPackage(v60[v24].lpVtbl, 0);
            if ( v25 < 0 )
              wil::details::in1diag3::_Log_Hr(
                retaddr,
                (void *)0x5C5,
                (unsigned int)"onecoreuap\\shell\\appreadiness\\src\\core\\user.cpp",
                (const char *)(unsigned int)v25,
                v57);
            v23 = v59;
          }
          ++v22;
        }
        while ( v22 < (unsigned int)v23 );
      }
      v26 = 0;
      if ( (_DWORD)v23 )
      {
        do
        {
          v27 = 12LL * v26;
          if ( ((__int64)v60[v27 + 10].lpVtbl & 0x200) == 0 )
          {
            v28 = AppxPreRegisterPackage(v60[v27].lpVtbl, 0);
            if ( v28 < 0 )
              wil::details::in1diag3::_Log_Hr(
                retaddr,
                (void *)0x5CD,
                (unsigned int)"onecoreuap\\shell\\appreadiness\\src\\core\\user.cpp",
                (const char *)(unsigned int)v28,
                v57);
          }
          memset_0(packageFamilyName, 0, 0x82u);
          packageFamilyNameLength = 65;
          v29 = PackageFamilyNameFromFullName((PCWSTR)v60[v27].lpVtbl, &packageFamilyNameLength, packageFamilyName);
          v31 = retaddr;
          if ( v29 >= 0 )
          {
            v29 = AppReadiness::User::InstallAppLicense(packageFamilyName, v30);
            v31 = retaddr;
            if ( v29 >= 0 )
              goto LABEL_55;
            v32 = 1492;
          }
          else
          {
            v32 = 1490;
          }
          wil::details::in1diag3::_Log_Hr(
            v31,
            (void *)v32,
            (unsigned int)"onecoreuap\\shell\\appreadiness\\src\\core\\user.cpp",
            (const char *)(unsigned int)v29,
            v57);
LABEL_55:
          v58 = 0;
          if ( UserState == 1 )
          {
            IsStubPreferenceKeyNeededForPackage = AppReadiness::User::IsStubPreferenceKeyNeededForPackage(
                                                    v31,
                                                    (const unsigned __int16 *)v60[v27].lpVtbl,
                                                    &v58);
            v34 = retaddr;
            if ( IsStubPreferenceKeyNeededForPackage >= 0 )
            {
              if ( !v58 )
                goto LABEL_62;
              IsStubPreferenceKeyNeededForPackage = AppReadiness::User::CreateStubPreferenceRegKey(
                                                      retaddr,
                                                      packageFamilyName);
              v34 = retaddr;
              if ( IsStubPreferenceKeyNeededForPackage >= 0 )
                goto LABEL_62;
              v35 = 1511;
            }
            else
            {
              v35 = 1509;
            }
            wil::details::in1diag3::_Log_Hr(
              v34,
              (void *)v35,
              (unsigned int)"onecoreuap\\shell\\appreadiness\\src\\core\\user.cpp",
              (const char *)(unsigned int)IsStubPreferenceKeyNeededForPackage,
              v57);
          }
LABEL_62:
          ++v26;
          v23 = v59;
        }
        while ( v26 < v59 );
      }
      if ( v60 )
      {
        v36 = ClientDeleteAllPackagesFromMainPackageArray(v23, &v60);
        if ( v36 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x5BB,
            (unsigned int)"onecoreuap\\shell\\appreadiness\\src\\core\\user.cpp",
            (const char *)(unsigned int)v36,
            v57);
      }
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v62);
      v37 = v61;
      if ( v61 )
      {
        v61 = 0;
        ((void (__fastcall *)(struct ITask *))v37->lpVtbl->Release)(v37);
      }
      wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(v71);
    }
    AppReadiness::User::CompleteTasks((AppReadiness::User *)this, (struct AppReadiness::Storage::PackageList *)v66);
LABEL_70:
    if ( *((_DWORD *)this + 95) != 3 )
    {
      v38 = AppReadiness::User::ImportPackageUserStatusToStateRepository((AppReadiness::User *)this);
      if ( v38 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x5F6,
          (unsigned int)"onecoreuap\\shell\\appreadiness\\src\\core\\user.cpp",
          (const char *)(unsigned int)v38,
          v57);
      if ( !AppReadiness::System::IsSharedAppsEnabled() || *((_BYTE *)this + 177) )
      {
        AppReadiness::User::ClearExpiredPackageErrors((AppReadiness::User *)this);
        AppReadiness::User::PrepareTasks((AppReadiness::User *)this, (struct AppReadiness::Storage::PackageList *)v66);
        AppReadiness::User::CleanupUnusedTasks(
          (AppReadiness::User *)this,
          (const struct AppReadiness::Storage::PackageList *)v66);
        if ( *((_DWORD *)this + 95) != 2
          || v68 != v67
          || (v39 = 1, AppReadiness::User::HasRunningTasks((AppReadiness::User *)this)) )
        {
          v39 = 0;
        }
        AppReadiness::Storage::PackageList::Write((AppReadiness::Storage::PackageList *)v66);
        AppReadiness::Storage::PackageList::SetUserStateDWORD(
          (const struct AppReadiness::User *)this,
          L"UserState",
          v39 + 2);
        if ( v39 )
        {
          if ( UserState != 3 )
          {
            v41 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
              WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, &WPP_2779cad321383337b9ccea6dca676a06_Traceguids);
            if ( (Microsoft_Windows_AppReadinessEnableBits & 0x100) != 0 )
              McTemplateU0z_EventWriteTransfer(v41, User_ReachedSteadyState);
            if ( (unsigned int)dword_1800A2208 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1800A2208, 0x400000000000LL) )
            {
              v71[0] = 0x1000000;
              v43 = this + 8;
              if ( (unsigned __int64)this[11] > 7 )
                v43 = (_QWORD *)*v43;
              v62 = v43;
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>>(
                (_DWORD)v41,
                (unsigned int)byte_1800933B9,
                v40,
                v42,
                (__int64)&v62,
                (__int64)v71);
            }
            if ( (Microsoft_Windows_AppReadinessEnableBits & 0x80u) != 0 )
              McGenEventWrite_EventWriteTransfer(v41, User_ReachedSteadyStateWithoutUserInfo, v40, 1, v71);
          }
        }
        else if ( UserState == 3 )
        {
          v44 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
            WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, &WPP_2779cad321383337b9ccea6dca676a06_Traceguids);
          if ( (Microsoft_Windows_AppReadinessEnableBits & 0x100) != 0 )
            McTemplateU0z_EventWriteTransfer(v44, User_NoLongerInSteadyState);
        }
        AppReadiness::User::CleanupUnusedPackages((AppReadiness::User *)this, v39);
        if ( *((_DWORD *)this + 95) == 2 && !AppReadiness::User::HasRunningTasks((AppReadiness::User *)this) )
          AppReadiness::User::ScorePackages((AppReadiness::User *)this);
      }
      v45 = 0;
      do
      {
        AppReadiness::User::FindNextTask((AppReadiness::User *)this);
        v46 = v60;
        if ( v60 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          {
            v47 = (_QWORD *)((__int64 (__fastcall *)(struct ITask *))v60->lpVtbl->CreateTrigger)(v60);
            if ( v47[3] > 7u )
              v47 = (_QWORD *)*v47;
            v48 = this + 8;
            if ( (unsigned __int64)this[11] > 7 )
              v48 = (_QWORD *)*v48;
            WPP_SF_SS(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              36,
              (unsigned int)&WPP_2779cad321383337b9ccea6dca676a06_Traceguids,
              (_DWORD)v48,
              (__int64)v47);
            v46 = v60;
          }
          if ( !AppReadiness::User::RunTask((AppReadiness::User *)this, v46)
            && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          {
            v49 = ((__int64 (__fastcall *)(struct ITask *))v60->lpVtbl->GetRunTimes)(v60);
            v50 = (_QWORD *)((__int64 (__fastcall *)(struct ITask *))v60->lpVtbl->CreateTrigger)(v60);
            if ( v50[3] > 7u )
              v50 = (_QWORD *)*v50;
            v51 = this + 8;
            if ( (unsigned __int64)this[11] > 7 )
              v51 = (_QWORD *)*v51;
            WPP_SF_SSd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              37,
              (unsigned int)&WPP_2779cad321383337b9ccea6dca676a06_Traceguids,
              (_DWORD)v51,
              (__int64)v50,
              v49);
          }
        }
        else
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
            WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 38, &WPP_2779cad321383337b9ccea6dca676a06_Traceguids);
          v45 = 1;
        }
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v60);
      }
      while ( !v45 );
    }
    if ( !AppReadiness::User::HasRunningTasks((AppReadiness::User *)this) )
    {
      SetEvent(this[30]);
      v52 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 39, &WPP_2779cad321383337b9ccea6dca676a06_Traceguids);
    }
    if ( (Microsoft_Windows_AppReadinessEnableBits & 0x80u) != 0 )
      McTemplateU0z_EventWriteTransfer(v52, User_ProcessTasks_Stop);
    AppReadiness::Storage::PackageList::~PackageList((AppReadiness::Storage::PackageList *)v66);
    goto LABEL_135;
  }
  if ( !AppReadiness::User::HasRunningTasks((AppReadiness::User *)this)
    && AppReadiness::User::HasTasks((AppReadiness::User *)this)
    && *((_DWORD *)this + 95) != 3 )
  {
    v53 = (RTL_SRWLOCK *)AppReadiness::Service::Get();
    AppReadiness::Service::ProcessUserTasks(v53, (struct AppReadiness::User *)this);
  }
LABEL_135:
  if ( hSemaphore && (v64 & 0xFFFFFF7F) == 0 && !ReleaseSemaphore(hSemaphore, 1, 0) )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)LastError, v55, v56);
LABEL_142:
    Windows::HResultException::HResultException(
      (Windows::HResultException *)&pExceptionObject,
      v10,
      "MakeAndInitialize<Groups::OnDemandSyncGroup>(&task, this)",
      "AppReadiness::User::ProcessTasks",
      v1,
      1420);
    throw (Windows::HResultException *)&pExceptionObject;
  }
}

```

## disassembly

```asm
0x180010afc  mov     [rsp-8+arg_8], rbx
0x180010b01  mov     [rsp-8+arg_10], rsi
0x180010b06  push    rbp
0x180010b07  push    rdi
0x180010b08  push    r12
0x180010b0a  push    r13
0x180010b0c  push    r14
0x180010b0e  lea     rbp, [rsp-60h]
0x180010b13  sub     rsp, 160h
0x180010b1a  mov     rax, cs:__security_cookie
0x180010b21  xor     rax, rsp
0x180010b24  mov     [rbp+80h+var_30], rax
0x180010b28  mov     rsi, rcx
0x180010b2b  xor     r12d, r12d
0x180010b2e  mov     ebx, r12d
0x180010b31  mov     [rsp+180h+var_14C], ebx
0x180010b35  add     rcx, 90h
0x180010b3c  mov     r8d, 0FAh
0x180010b42  lea     rdx, [rsp+180h+var_128]
0x180010b47  call    ?Lock@Semaphore@Wrappers@WRL@Microsoft@@QEAA?AV?$SyncLockWithStatusT@USemaphoreTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Details@234@K@Z; Microsoft::WRL::Wrappers::Semaphore::Lock(ulong)
0x180010b4c  nop
0x180010b4d  cmp     [rsp+180h+hSemaphore], r12
0x180010b52  jz      loc_180011436
0x180010b58  test    [rsp+180h+var_128], 0FFFFFF7Fh
0x180010b60  jnz     loc_180011436
0x180010b66  cmp     byte ptr cs:Microsoft_Windows_AppReadinessEnableBits, r12b
0x180010b6d  jge     short loc_180010B89
0x180010b6f  lea     r8, [rsi+40h]
0x180010b73  cmp     qword ptr [r8+18h], 7
0x180010b78  jbe     short loc_180010B7D
0x180010b7a  mov     r8, [r8]
0x180010b7d  lea     rdx, User_ProcessTasks_Start
0x180010b84  call    McTemplateU0z_EventWriteTransfer
0x180010b89  lea     rax, WPP_GLOBAL_Control
0x180010b90  mov     rcx, cs:WPP_GLOBAL_Control
0x180010b97  cmp     rcx, rax
0x180010b9a  jz      short loc_180010BC5
0x180010b9c  test    byte ptr [rcx+1Ch], 4
0x180010ba0  jz      short loc_180010BC5
0x180010ba2  lea     r9, [rsi+40h]
0x180010ba6  cmp     qword ptr [r9+18h], 7
0x180010bab  jbe     short loc_180010BB0
0x180010bad  mov     r9, [r9]
0x180010bb0  mov     edx, 21h ; '!'
0x180010bb5  lea     r8, WPP_2779cad321383337b9ccea6dca676a06_Traceguids
0x180010bbc  mov     rcx, [rcx+10h]
0x180010bc0  call    WPP_SF_S
0x180010bc5  mov     rdx, rsi; struct AppReadiness::User *
0x180010bc8  lea     rcx, [rsp+180h+var_118]; this
0x180010bcd  call    ??0PackageList@Storage@AppReadiness@@QEAA@PEAVUser@2@@Z; AppReadiness::Storage::PackageList::PackageList(AppReadiness::User *)
0x180010bd2  nop
0x180010bd3  mov     rcx, rsi
0x180010bd6  call    ?GetUserState@PackageList@Storage@AppReadiness@@SA?AW4UserState@23@PEBVUser@3@@Z; AppReadiness::Storage::PackageList::GetUserState(AppReadiness::User const *)
0x180010bdb  mov     r14d, eax
0x180010bde  call    cs:__imp_RtlIsStateSeparationEnabled
0x180010be4  test    al, al
0x180010be6  jz      short loc_180010C08
0x180010be8  lea     rcx, [rbp+80h+pExceptionObject]
0x180010bec  call    ?GetDefaultAccountSid@User@AppReadiness@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; AppReadiness::User::GetDefaultAccountSid(void)
0x180010bf1  mov     ebx, 1
0x180010bf6  mov     rdx, rax
0x180010bf9  mov     rcx, rsi
0x180010bfc  call    ?IsUser@User@AppReadiness@@QEBA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; AppReadiness::User::IsUser(std::wstring const &)
0x180010c01  test    al, al
0x180010c03  mov     dil, bl
0x180010c06  jnz     short loc_180010C0B
0x180010c08  mov     dil, r12b
0x180010c0b  test    bl, 1
0x180010c0e  jz      short loc_180010C1C
0x180010c10  and     ebx, 0FFFFFFFEh
0x180010c13  lea     rcx, [rbp+80h+pExceptionObject]
0x180010c17  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4PackageOperation@Storage@AppReadiness@@@std@@QEAA@XZ; std::pair<std::wstring,AppReadiness::Storage::PackageOperation>::~pair<std::wstring,AppReadiness::Storage::PackageOperation>(void)
0x180010c1c  lea     r13, aOnecoreuapShel_34; "onecoreuap\\shell\\appreadiness\\src\\c"...
0x180010c23  test    dil, dil
0x180010c26  jz      short loc_180010C48
0x180010c28  call    ?CheckForOsUpgrade@User@AppReadiness@@IEAAJXZ; AppReadiness::User::CheckForOsUpgrade(void)
0x180010c2d  mov     rcx, [rbp+88h]; this
0x180010c34  test    eax, eax
0x180010c36  jns     short loc_180010C48
0x180010c38  mov     r9d, eax; char *
0x180010c3b  mov     r8, r13; unsigned int
0x180010c3e  mov     edx, 57Dh; void *
0x180010c43  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180010c48  call    ?IsSharedAppsEnabled@System@AppReadiness@@SA_NXZ; AppReadiness::System::IsSharedAppsEnabled(void)
0x180010c4d  test    al, al
0x180010c4f  jz      short loc_180010CC3
0x180010c51  cmp     [rsi+0B1h], r12b
0x180010c58  jnz     short loc_180010CC3
0x180010c5a  cmp     [rsi+0B0h], r12b
0x180010c61  jnz     short loc_180010CC3
0x180010c63  lea     rdx, [rsp+180h+var_118]; struct AppReadiness::Storage::PackageList *
0x180010c68  mov     rcx, rsi; this
0x180010c6b  call    ?CompleteTasks@User@AppReadiness@@IEAA_NAEAVPackageList@Storage@2@@Z; AppReadiness::User::CompleteTasks(AppReadiness::Storage::PackageList &)
0x180010c70  cmp     [rsi+0D9h], r12b
0x180010c77  jz      loc_180011013
0x180010c7d  mov     [rsp+180h+var_140], r12
0x180010c82  mov     [rbp+80h+var_D0], rsi
0x180010c86  lea     rdx, [rbp+80h+var_D0]
0x180010c8a  lea     rcx, [rsp+180h+var_140]
0x180010c8f  call    ??$MakeAndInitialize@VOnDemandSyncGroup@Groups@AppReadiness@@UITask@3@PEAVUser@3@@Details@WRL@Microsoft@@YAJV?$ComPtrRef@V?$ComPtr@UITask@AppReadiness@@@WRL@Microsoft@@@012@$$QEAPEAVUser@AppReadiness@@@Z; Microsoft::WRL::Details::MakeAndInitialize<AppReadiness::Groups::OnDemandSyncGroup,AppReadiness::ITask,AppReadiness::User *>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<AppReadiness::ITask>>,AppReadiness::User * &&)
0x180010c94  test    eax, eax
0x180010c96  js      loc_1800114D1
0x180010c9c  mov     rdx, [rsp+180h+var_140]; struct ITask *
0x180010ca1  mov     rcx, rsi; this
0x180010ca4  call    ?AddTask@User@AppReadiness@@QEAAXPEAUITask@2@@Z; AppReadiness::User::AddTask(AppReadiness::ITask *)
0x180010ca9  xor     edx, edx; bool
0x180010cab  mov     rcx, rsi; this
0x180010cae  call    ?SetShouldQueryAppx@User@AppReadiness@@QEAAX_N@Z; AppReadiness::User::SetShouldQueryAppx(bool)
0x180010cb3  nop
0x180010cb4  lea     rcx, [rsp+180h+var_140]
0x180010cb9  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180010cbe  jmp     loc_180011013
0x180010cc3  lea     rcx, [rsp+180h+var_118]; this
0x180010cc8  call    ?Read@PackageList@Storage@AppReadiness@@QEAAXXZ; AppReadiness::Storage::PackageList::Read(void)
0x180010ccd  lea     rdx, [rsp+180h+var_118]
0x180010cd2  mov     rcx, rsi
0x180010cd5  call    AppReadiness__LogUserLoadedPackages
0x180010cda  call    cs:__imp_RtlIsStateSeparationEnabled
0x180010ce0  test    al, al
0x180010ce2  jz      short loc_180010D1E
0x180010ce4  cmp     r14d, 1
0x180010ce8  jz      short loc_180010CF0
0x180010cea  cmp     r14d, 4
0x180010cee  jnz     short loc_180010D1E
0x180010cf0  lea     rcx, [rbp+80h+pExceptionObject]
0x180010cf4  call    ?GetDefaultAccountSid@User@AppReadiness@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; AppReadiness::User::GetDefaultAccountSid(void)
0x180010cf9  nop
0x180010cfa  or      ebx, 2
0x180010cfd  mov     [rsp+180h+var_14C], ebx
0x180010d01  mov     rdx, rax
0x180010d04  mov     rcx, rsi
0x180010d07  call    ?IsUser@User@AppReadiness@@QEBA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; AppReadiness::User::IsUser(std::wstring const &)
0x180010d0c  test    al, al
0x180010d0e  jnz     short loc_180010D19
0x180010d10  call    ?IsDefaultAccountDisabled@User@AppReadiness@@SA_NXZ; AppReadiness::User::IsDefaultAccountDisabled(void)
0x180010d15  test    al, al
0x180010d17  jz      short loc_180010D1E
0x180010d19  mov     dil, 1
0x180010d1c  jmp     short loc_180010D21
0x180010d1e  mov     dil, r12b
0x180010d21  test    bl, 2
0x180010d24  jz      short loc_180010D2F
0x180010d26  lea     rcx, [rbp+80h+pExceptionObject]
0x180010d2a  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4PackageOperation@Storage@AppReadiness@@@std@@QEAA@XZ; std::pair<std::wstring,AppReadiness::Storage::PackageOperation>::~pair<std::wstring,AppReadiness::Storage::PackageOperation>(void)
0x180010d2f  test    dil, dil
0x180010d32  jz      loc_180011006
0x180010d38  call    ?CleanupPreinstalledVolume@User@AppReadiness@@IEAAJXZ; AppReadiness::User::CleanupPreinstalledVolume(void)
0x180010d3d  mov     rcx, [rbp+88h]; this
0x180010d44  test    eax, eax
0x180010d46  jns     short loc_180010D58
0x180010d48  mov     r9d, eax; char *
0x180010d4b  mov     r8, r13; unsigned int
0x180010d4e  mov     edx, 5A1h; void *
0x180010d53  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180010d58  lea     rcx, [rbp+80h+var_D0]
0x180010d5c  call    ??$ActivateInstance@UIPackageManager3@Deployment@Management@Windows@@@wil@@YA?AV?$com_ptr_t@UIPackageManager3@Deployment@Management@Windows@@Uerr_exception_policy@wil@@@0@PEBG@Z; wil::ActivateInstance<Windows::Management::Deployment::IPackageManager3>(ushort const *)
0x180010d61  nop
0x180010d62  mov     [rsp+180h+var_140], r12
0x180010d67  mov     [rsp+180h+var_138], r12
0x180010d6c  mov     rdi, [rbp+80h+var_D0]
0x180010d70  mov     rax, [rdi]
0x180010d73  mov     rbx, [rax+30h]
0x180010d77  mov     [rbp+80h+var_E0], r12
0x180010d7b  mov     r9d, 0Eh; unsigned int
0x180010d81  lea     r8d, [r9+1]; unsigned int
0x180010d85  lea     rdx, sourceString; "P:\\WindowsApps"
0x180010d8c  lea     rcx, [rbp+80h+pExceptionObject]; hstringHeader
0x180010d90  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180010d95  nop
0x180010d96  lea     r8, [rsp+180h+var_140]
0x180010d9b  mov     rdx, [rbp+80h+var_E0]
0x180010d9f  mov     rcx, rdi
0x180010da2  mov     rax, rbx
0x180010da5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010daa  nop
0x180010dab  cmp     eax, 80070002h
0x180010db0  jz      short loc_180010DDB
0x180010db2  test    eax, eax
0x180010db4  js      loc_180011508
0x180010dba  lea     rcx, [rsp+180h+var_138]
0x180010dbf  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180010dc4  lea     r8, [rsp+180h+var_138]
0x180010dc9  mov     rcx, [rsp+180h+var_140]
0x180010dce  call    ?WaitForPackageVolumeOperation@Deployment@Management@Windows@@YAJPEAU?$IAsyncOperation@PEAVPackageVolume@Deployment@Management@Windows@@@Foundation@3@PEAU?$IAsyncOperationCompletedHandler@PEAVPackageVolume@Deployment@Management@Windows@@@53@PEAPEAUIPackageVolume@123@@Z; Windows::Management::Deployment::WaitForPackageVolumeOperation(Windows::Foundation::IAsyncOperation<Windows::Management::Deployment::PackageVolume *> *,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Management::Deployment::PackageVolume *> *,Windows::Management::Deployment::IPackageVolume * *)
0x180010dd3  test    eax, eax
0x180010dd5  js      loc_18001153F
0x180010ddb  mov     [rsp+180h+var_14C], r12d
0x180010de0  mov     [rsp+180h+var_148], r12
0x180010de5  lea     r9, [rsp+180h+var_14C]
0x180010dea  lea     r8, [rsp+180h+var_148]
0x180010def  xor     edx, edx
0x180010df1  xor     ecx, ecx
0x180010df3  call    cs:__imp_ClientGetAllPackagesToBeInstalledForUser
0x180010df9  test    eax, eax
0x180010dfb  js      loc_180011576
0x180010e01  lea     rax, [rsp+180h+var_148]
0x180010e06  mov     [rbp+80h+pExceptionObject], rax
0x180010e0a  lea     rax, [rsp+180h+var_14C]
0x180010e0f  mov     [rbp+80h+var_F0], rax
0x180010e13  mov     [rbp+80h+var_E8], 1
0x180010e17  call    ?PreRegisterInboxPackagesIfNeeded@System@AppReadiness@@SAJXZ; AppReadiness::System::PreRegisterInboxPackagesIfNeeded(void)
0x180010e1c  mov     rcx, [rbp+88h]; this
0x180010e23  test    eax, eax
0x180010e25  jns     short loc_180010E37
0x180010e27  mov     r9d, eax; char *
0x180010e2a  mov     r8, r13; unsigned int
0x180010e2d  mov     edx, 5BFh; void *
0x180010e32  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180010e37  mov     ebx, r12d
0x180010e3a  mov     ecx, [rsp+180h+var_14C]
0x180010e3e  test    ecx, ecx
0x180010e40  jz      short loc_180010E8D
0x180010e42  mov     eax, ebx
0x180010e44  lea     r8, [rax+rax*2]
0x180010e48  shl     r8, 5
0x180010e4c  mov     rax, [rsp+180h+var_148]
0x180010e51  test    dword ptr [r8+rax+50h], 200h
0x180010e5a  jz      short loc_180010E87
0x180010e5c  xor     edx, edx
0x180010e5e  mov     rcx, [r8+rax]
0x180010e62  call    cs:__imp_AppxPreRegisterPackage
0x180010e68  mov     rcx, [rbp+88h]; this
0x180010e6f  test    eax, eax
0x180010e71  jns     short loc_180010E83
0x180010e73  mov     r9d, eax; char *
0x180010e76  mov     r8, r13; unsigned int
0x180010e79  mov     edx, 5C5h; void *
0x180010e7e  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180010e83  mov     ecx, [rsp+180h+var_14C]
0x180010e87  inc     ebx
0x180010e89  cmp     ebx, ecx
0x180010e8b  jb      short loc_180010E42
0x180010e8d  mov     edi, r12d
0x180010e90  test    ecx, ecx
0x180010e92  jz      loc_180010FA8
0x180010e98  mov     eax, edi
0x180010e9a  lea     rbx, [rax+rax*2]
0x180010e9e  shl     rbx, 5
0x180010ea2  mov     rcx, [rsp+180h+var_148]
0x180010ea7  test    dword ptr [rbx+rcx+50h], 200h
0x180010eaf  jnz     short loc_180010ED8
0x180010eb1  xor     edx, edx
0x180010eb3  mov     rcx, [rbx+rcx]
0x180010eb7  call    cs:__imp_AppxPreRegisterPackage
0x180010ebd  mov     rcx, [rbp+88h]; this
0x180010ec4  test    eax, eax
0x180010ec6  jns     short loc_180010ED8
0x180010ec8  mov     r9d, eax; char *
0x180010ecb  mov     r8, r13; unsigned int
0x180010ece  mov     edx, 5CDh; void *
0x180010ed3  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180010ed8  xor     edx, edx; Val
0x180010eda  mov     r8d, 82h; Size
0x180010ee0  lea     rcx, [rbp+80h+packageFamilyName]; void *
0x180010ee4  call    memset_0
0x180010ee9  mov     [rsp+180h+packageFamilyNameLength], 41h ; 'A'
0x180010ef1  lea     r8, [rbp+80h+packageFamilyName]; packageFamilyName
0x180010ef5  lea     rdx, [rsp+180h+packageFamilyNameLength]; packageFamilyNameLength
0x180010efa  mov     rcx, [rsp+180h+var_148]
0x180010eff  mov     rcx, [rbx+rcx]; packageFullName
0x180010f03  call    cs:__imp_PackageFamilyNameFromFullName
0x180010f09  mov     rcx, [rbp+88h]
0x180010f10  test    eax, eax
0x180010f12  jns     short loc_180010F1B
0x180010f14  mov     edx, 5D2h
0x180010f19  jmp     short loc_180010F34
0x180010f1b  lea     rcx, [rbp+80h+packageFamilyName]; unsigned __int16 *
0x180010f1f  call    ?InstallAppLicense@User@AppReadiness@@SAJPEBG0_N@Z; AppReadiness::User::InstallAppLicense(ushort const *,ushort const *,bool)
0x180010f24  mov     rcx, [rbp+88h]; this
0x180010f2b  test    eax, eax
0x180010f2d  jns     short loc_180010F3F
0x180010f2f  mov     edx, 5D4h; void *
0x180010f34  mov     r9d, eax; char *
0x180010f37  mov     r8, r13; unsigned int
0x180010f3a  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180010f3f  mov     [rsp+180h+var_150], r12b
0x180010f44  cmp     r14d, 1
0x180010f48  jnz     short loc_180010F9A
0x180010f4a  lea     r8, [rsp+180h+var_150]; bool *
0x180010f4f  mov     rdx, [rsp+180h+var_148]
0x180010f54  mov     rdx, [rbx+rdx]; unsigned __int16 *
0x180010f58  call    ?IsStubPreferenceKeyNeededForPackage@User@AppReadiness@@AEAAJPEBGPEA_N@Z; AppReadiness::User::IsStubPreferenceKeyNeededForPackage(ushort const *,bool *)
0x180010f5d  mov     rcx, [rbp+88h]; this
0x180010f64  test    eax, eax
0x180010f66  jns     short loc_180010F6F
0x180010f68  mov     edx, 5E5h
0x180010f6d  jmp     short loc_180010F8F
0x180010f6f  cmp     [rsp+180h+var_150], r12b
0x180010f74  jz      short loc_180010F9A
0x180010f76  lea     rdx, [rbp+80h+packageFamilyName]; unsigned __int16 *
0x180010f7a  call    ?CreateStubPreferenceRegKey@User@AppReadiness@@AEAAJPEBG@Z; AppReadiness::User::CreateStubPreferenceRegKey(ushort const *)
0x180010f7f  mov     rcx, [rbp+88h]; this
0x180010f86  test    eax, eax
0x180010f88  jns     short loc_180010F9A
0x180010f8a  mov     edx, 5E7h; void *
0x180010f8f  mov     r9d, eax; char *
0x180010f92  mov     r8, r13; unsigned int
0x180010f95  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180010f9a  inc     edi
0x180010f9c  mov     ecx, [rsp+180h+var_14C]
  ... truncated ...
```
