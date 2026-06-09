# UWAInstallWork::_DoInstall(IUpdateSession *,IUpdateCollection *)

- ea: `0x1800f1ff0`
- end: `0x1800f29ab`
- name: `?_DoInstall@UWAInstallWork@@AEAAJPEAUIUpdateSession@@PEAUIUpdateCollection@@@Z`
- size: `2491`
- prototype: `__int64 __fastcall(UWAInstallWork *__hidden this, struct IUpdateSession *, struct IUpdateCollection *)`
- caller_count: `1`
- callee_count: `31`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1800f5020`

## callees

- `0x1800101f4`
- `0x180012368`
- `0x180012394`
- `0x1800123f8`
- `0x180012428`
- `0x1800127c8`
- `0x18001c414`
- `0x18001c844`
- `0x18002efc0`
- `0x18003f884`
- `0x180044c3c`
- `0x180044e98`
- `0x180052008`
- `0x1800755d0`
- `0x180075608`
- `0x1800de208`
- `0x1800de680`
- `0x1800e9440`
- `0x1800e9888`
- `0x1800e9b24`
- `0x1800f1ff0`
- `0x1800f964c`
- `0x1800f981c`
- `0x1800fa4c0`
- `0x1800fb8b8`
- `0x1800fb908`
- `0x1800ff460`
- `0x1801131e0`
- `0x180114564`
- `0x180117fc0`
- `0x180215010`

## import_xrefs

- `msvcp_win!_Xtime_get_ticks` at `0x1800f20ed`
- `msvcp_win!_Xtime_get_ticks` at `0x1800f20ed`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f222d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f23cd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f2752`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f2833`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f2929`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f2938`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f294a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f295c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f296b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f222d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f23cd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f2752`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f2833`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f2929`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f2938`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f294a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f295c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f296b`

## string_xrefs

- `0x1800f2175`: `onecoreuap\enduser\winstore\installservice\lib\uwainstallwork.cpp`
- `0x1800f25cd`: `onecoreuap\enduser\winstore\installservice\lib\uwainstallwork.cpp`
- `0x1800f262e`: `onecoreuap\enduser\winstore\installservice\lib\uwainstallwork.cpp`
- `0x1800f267c`: `onecoreuap\enduser\winstore\installservice\lib\uwainstallwork.cpp`
- `0x1800f2708`: `onecoreuap\enduser\winstore\installservice\lib\uwainstallwork.cpp`
- `0x1800f2792`: `onecoreuap\enduser\winstore\installservice\lib\uwainstallwork.cpp`
- `0x1800f2861`: `onecoreuap\enduser\winstore\installservice\lib\uwainstallwork.cpp`
- `0x1800f261b`: `spInstaller->EndInstall(spJob.Get(), &spResult)`
- `0x1800f26f5`: `GetInstallExtendedErrorCode(pPackages, spResult.Get(), &hrExtended)`
- `0x1800f2989`: `StoreAgentInstallFailure1`
- `0x1800f2168`: `UWAInstallWork::_DoInstall`
- `0x1800f25c1`: `UWAInstallWork::_DoInstall`
- `0x1800f2622`: `UWAInstallWork::_DoInstall`
- `0x1800f2670`: `UWAInstallWork::_DoInstall`
- `0x1800f26fc`: `UWAInstallWork::_DoInstall`
- `0x1800f2785`: `UWAInstallWork::_DoInstall`
- `0x1800f2854`: `UWAInstallWork::_DoInstall`
- `0x1800f2843`: `Install failed, triggering fallback to direct download`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall UWAInstallWork::_DoInstall(
        UWAInstallWork *this,
        struct IUpdateSession *a2,
        struct IUpdateCollection *a3)
{
  UWAInstallWork *v3; // r13
  char *v4; // rbx
  _DWORD *v5; // rdi
  int Update; // r15d
  char *v7; // r12
  const char *v8; // r8
  const char *v9; // r9
  int v10; // ecx
  unsigned int v11; // r8d
  int v12; // eax
  int v13; // r9d
  BOOL v14; // r10d
  int v15; // r15d
  int v16; // ecx
  void *v17; // rdx
  const char *v18; // r9
  int v19; // ecx
  unsigned int v20; // r8d
  int v21; // r9d
  int v22; // eax
  BOOL v23; // r10d
  int v24; // r15d
  void *v25; // rcx
  struct IInstallationJobVtbl *lpVtbl; // rax
  int v27; // eax
  struct IUpdateInstaller *v28; // rdi
  HRESULT (__stdcall *EndInstall)(IUpdateInstaller *, IInstallationJob *, IInstallationResult **); // rbx
  int v30; // eax
  int v31; // eax
  int v32; // eax
  int InstallExtendedErrorCode; // eax
  int v34; // eax
  const unsigned __int16 *v35; // rdx
  const unsigned __int16 *v36; // rax
  unsigned __int64 DurationInMilliseconds; // rax
  int v38; // eax
  struct IInstallationProgressChangedCallback *v39; // rcx
  const unsigned __int16 *StringRawBuffer; // r14
  const unsigned __int16 *v41; // rsi
  const unsigned __int16 *v42; // rdi
  PCWSTR v43; // rbx
  const WCHAR *v44; // rax
  HSTRING v46; // [rsp+28h] [rbp-F0h]
  struct IInstallationCompletedCallback *v47; // [rsp+38h] [rbp-E0h]
  struct IInstallationResult *v48; // [rsp+60h] [rbp-B8h] BYREF
  int v49; // [rsp+68h] [rbp-B0h] BYREF
  int PercentStartForInstallPhase; // [rsp+6Ch] [rbp-ACh] BYREF
  struct IUpdateInstaller *v51; // [rsp+70h] [rbp-A8h] BYREF
  struct IInstallationJob *v52; // [rsp+78h] [rbp-A0h] BYREF
  int v53; // [rsp+80h] [rbp-98h]
  int v54; // [rsp+84h] [rbp-94h]
  BOOL v55; // [rsp+88h] [rbp-90h]
  struct IInstallationProgressChangedCallback *v56; // [rsp+90h] [rbp-88h] BYREF
  __int64 ticks; // [rsp+98h] [rbp-80h] BYREF
  HSTRING v58; // [rsp+A0h] [rbp-78h]
  struct IInstallationProgressChangedCallback *v59; // [rsp+A8h] [rbp-70h]
  struct IInstallationProgressChangedCallback *v60; // [rsp+B0h] [rbp-68h]
  HSTRING Intent; // [rsp+B8h] [rbp-60h]
  char *v62; // [rsp+C0h] [rbp-58h]
  _DWORD *v63; // [rsp+C8h] [rbp-50h]
  char *v64; // [rsp+D0h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+0h]
  UWAInstallWork *v66; // [rsp+120h] [rbp+8h] BYREF
  struct IUpdateSession *v67; // [rsp+128h] [rbp+10h]
  struct IUpdateCollection *v68; // [rsp+130h] [rbp+18h]
  int v69; // [rsp+138h] [rbp+20h] BYREF

  v68 = a3;
  v67 = a2;
  v66 = this;
  v3 = this;
  v4 = (char *)this + 1048;
  v62 = (char *)this + 1048;
  wil::AcquireSRWLockExclusive(&v69, (char *)this + 1048);
  v5 = (_DWORD *)((char *)v3 + 1060);
  v63 = (_DWORD *)((char *)v3 + 1060);
  if ( (unsigned int)(*((_DWORD *)v3 + 265) - 5) <= 1 )
  {
    Update = -2147467260;
  }
  else
  {
    Update = 0;
    *v5 = 3;
  }
  Microsoft::WRL::Wrappers::Details::SyncLockExclusive::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockExclusive *)&v69);
  if ( Update >= 0 )
  {
    UWAInstallWork::_RaiseProgressEvent(v3, 0);
    Microsoft::WRL::Wrappers::SRWLock::LockShared(&v69, v4);
    if ( *v5 != 3 )
      Update = -2147467260;
    Microsoft::WRL::Wrappers::Details::SyncLockShared::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockShared *)&v69);
  }
  wil::AcquireSRWLockExclusive(&v69, v4);
  v7 = (char *)v3 + 304;
  v64 = (char *)v3 + 304;
  TraceLoggingCorrelationVector::Increment(*((TraceLoggingCorrelationVector **)v3 + 37), (char *)v3 + 304);
  Microsoft::WRL::Wrappers::Details::SyncLockExclusive::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockExclusive *)&v69);
  if ( Update < 0 )
  {
    WindowsUpdate::Telemetry::AbortedInstallation(
      v3,
      (struct UWAInstallWork *)(unsigned int)Update,
      (_DWORD)v3 + 304,
      v9);
LABEL_62:
    if ( Update != -2147467260 )
    {
      StringRawBuffer = WindowsGetStringRawBuffer(*((HSTRING *)v3 + 60), 0);
      v41 = WindowsGetStringRawBuffer(*((HSTRING *)v3 + 15), 0);
      v42 = WindowsGetStringRawBuffer(*((HSTRING *)v3 + 57), 0);
      v43 = WindowsGetStringRawBuffer(*((HSTRING *)v3 + 59), 0);
      v44 = WindowsGetStringRawBuffer(*((HSTRING *)v3 + 14), 0);
      WindowsUpdate::InstallAgentWERReporting::ReportAppAcquireUpdateFailure(
        L"StoreAgentInstallFailure1",
        v44,
        (const unsigned __int16 *)(unsigned int)Update,
        (unsigned __int64)v43,
        v42,
        v41,
        StringRawBuffer,
        (const unsigned __int16 *)v47);
    }
    return (unsigned int)Update;
  }
  WindowsUpdate::Telemetry::BeginInstall(v3, (UWAInstallWork *)((char *)v3 + 304), v8);
  ticks = _Xtime_get_ticks();
  Update = -2147024882;
  Microsoft::WRL::Wrappers::SRWLock::LockShared(&v51, v4);
  PercentStartForInstallPhase = GetPercentStartForInstallPhase(*((unsigned int *)v3 + 273), *((unsigned int *)v3 + 32));
  v49 = PercentStartForInstallPhase + 5;
  if ( (unsigned int)(PercentStartForInstallPhase + 5) > 0x64 )
  {
    LogMessage(
      1u,
      "onecoreuap\\enduser\\winstore\\installservice\\lib\\uwainstallwork.cpp",
      0x1602u,
      "UWAInstallWork::_DoInstall",
      -1,
      L"Assert (%s): %s",
      0,
      0);
    __int2c();
  }
  Microsoft::WRL::Wrappers::Details::SyncLockShared::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockShared *)&v51);
  v51 = (struct IUpdateInstaller *)v3;
  Microsoft::WRL::Details::Make<InstallationProgress,UWAInstallWork *,unsigned int,unsigned int>(
    &v56,
    &v51,
    &PercentStartForInstallPhase,
    &v49);
  v69 = -2147023728;
  if ( v56 )
  {
    v51 = 0;
    v52 = 0;
    try
    {
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ImmediateRetryInstall>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ImmediateRetryInstall>::GetImpl'::`2'::impl) )
      {
        Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v52);
        Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v51);
        v59 = v56;
        v58 = (HSTRING)((unsigned __int64)&v56[1] & -(__int64)(v56 != 0));
        v60 = (struct IInstallationProgressChangedCallback *)WindowsGetStringRawBuffer(*((HSTRING *)v3 + 14), 0);
        Intent = UWAInstallWork::_GetIntent(v3);
        v10 = *((_DWORD *)v3 + 32);
        v11 = *((_DWORD *)v3 + 264);
        PercentStartForInstallPhase = v11;
        LODWORD(v48) = (v11 & 0x2000) != 0 ? 0x8000 : 0;
        v12 = 8;
        v13 = (v11 & 8) << 13;
        v53 = v13;
        v14 = v10 == 1;
        v55 = v14;
        if ( v10 != 3 )
          v12 = 0;
        v49 = v12;
        v15 = 32;
        if ( v10 != 4 )
          v15 = 0;
        v16 = (v11 >> 2) & 0x1000;
        v54 = v16;
        if ( (v11 & 0x2000) != 0 )
        {
          v17 = 0;
        }
        else
        {
          v17 = (void *)CallerContext::ContextData::_getToken((_QWORD *)v3 + 19)[1];
          LOBYTE(v11) = PercentStartForInstallPhase;
          v12 = v49;
          v13 = v53;
          v16 = v54;
          v14 = v55;
        }
        Update = UWAInstallWork::_InstallPackagesWithRetry(
                   v3,
                   v17,
                   v67,
                   v68,
                   v16 | (16 * (v11 & 1)) | (unsigned int)v48 | v13 | v14 | v12 | v15,
                   Intent,
                   (const unsigned __int16 *)v60,
                   v59,
                   (struct IInstallationCompletedCallback *)v58,
                   (const char *)v3 + 304,
                   &v51,
                   &v52);
      }
      else
      {
        Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v52);
        Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v51);
        v60 = v56;
        Intent = (HSTRING)((unsigned __int64)&v56[1] & -(__int64)(v56 != 0));
        v59 = (struct IInstallationProgressChangedCallback *)WindowsGetStringRawBuffer(*((HSTRING *)v3 + 14), 0);
        v58 = UWAInstallWork::_GetIntent(v3);
        v19 = *((_DWORD *)v3 + 32);
        v20 = *((_DWORD *)v3 + 264);
        v55 = v20;
        v53 = (v20 & 0x2000) != 0 ? 0x8000 : 0;
        v21 = 8;
        v22 = (v20 & 8) << 13;
        LODWORD(v48) = v22;
        v23 = v19 == 1;
        v54 = v23;
        if ( v19 != 3 )
          v21 = 0;
        v49 = v21;
        v24 = 32;
        if ( v19 != 4 )
          v24 = 0;
        PercentStartForInstallPhase = (v20 >> 2) & 0x1000;
        if ( (v20 & 0x2000) != 0 )
        {
          v25 = 0;
        }
        else
        {
          v25 = (void *)CallerContext::ContextData::_getToken((_QWORD *)v3 + 19)[1];
          v22 = (int)v48;
          LOBYTE(v20) = v55;
          v21 = v49;
          v23 = v54;
        }
        Update = InstallPackages(
                   v25,
                   v67,
                   v68,
                   PercentStartForInstallPhase | (16 * (v20 & 1)) | v53 | v23 | v24 | v22 | v21,
                   v58,
                   (unsigned __int16 *)v59,
                   v60,
                   (struct IInstallationCompletedCallback *)Intent,
                   (const char *)v3 + 304,
                   &v51,
                   &v52);
      }
    }
    catch ( ... )
    {
      LODWORD(v48) = wil::details::in1diag3::Log_CaughtException(
                       retaddr,
                       (void *)0x162E,
                       (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\uwainstallwork.cpp",
                       v18);
      v3 = v66;
      Update = (int)v48;
      v5 = v63;
      v7 = v64;
      v4 = v62;
    }
    if ( Update < 0 )
      goto LABEL_51;
    wil::AcquireSRWLockExclusive(&v66, v4);
    if ( *v5 == 3 )
      Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationWithProgress<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress>>::operator=(
        (char *)v3 + 1152,
        &v52);
    else
      Update = -2147467260;
    Microsoft::WRL::Wrappers::Details::SyncLockExclusive::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockExclusive *)&v66);
    lpVtbl = v52->lpVtbl;
    if ( Update == -2147467260 )
    {
      ((void (*)(void))lpVtbl->RequestAbort)();
LABEL_50:
      wil::AcquireSRWLockExclusive(&v66, v4);
      Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease((char *)v3 + 1152);
      Microsoft::WRL::Wrappers::Details::SyncLockExclusive::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockExclusive *)&v66);
LABEL_51:
      Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v52);
      Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v51);
      goto LABEL_52;
    }
    v27 = ((__int64 (*)(void))lpVtbl->CleanUp)();
    Update = TraceHR(
               "onecoreuap\\enduser\\winstore\\installservice\\lib\\uwainstallwork.cpp",
               0x1646u,
               "UWAInstallWork::_DoInstall",
               "spJob->CleanUp()",
               v27,
               (int)v46);
    if ( Update < 0 )
      goto LABEL_50;
    v48 = 0;
    v28 = v51;
    EndInstall = v51->lpVtbl->EndInstall;
    Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v48);
    v30 = ((__int64 (__fastcall *)(struct IUpdateInstaller *, struct IInstallationJob *, struct IInstallationResult **))EndInstall)(
            v28,
            v52,
            &v48);
    Update = TraceHR(
               "onecoreuap\\enduser\\winstore\\installservice\\lib\\uwainstallwork.cpp",
               0x164Bu,
               "UWAInstallWork::_DoInstall",
               "spInstaller->EndInstall(spJob.Get(), &spResult)",
               v30,
               (int)v46);
    if ( Update >= 0 )
    {
      LODWORD(v66) = 0;
      v31 = ((__int64 (__fastcall *)(struct IInstallationResult *, UWAInstallWork **))v48->lpVtbl->get_ResultCode)(
              v48,
              &v66);
      Update = TraceHR(
                 "onecoreuap\\enduser\\winstore\\installservice\\lib\\uwainstallwork.cpp",
                 0x164Fu,
                 "UWAInstallWork::_DoInstall",
                 "spResult->get_ResultCode(&orc)",
                 v31,
                 (int)v46);
      if ( Update >= 0 )
      {
        v32 = HResultFromWUResult((enum tagOperationResultCode)v66);
        Update = v32;
        if ( v32 >= 0 )
        {
          v69 = 0;
          *((_DWORD *)v3 + 268) = 0;
LABEL_48:
          UWAInstallWork::_SetPostInstallState(v3);
          goto LABEL_49;
        }
        if ( v32 != -2147467260 )
        {
          Update = GetUpdateResult<IUpdateInstallationResult,IInstallationResult>(v68, v48);
          InstallExtendedErrorCode = GetInstallExtendedErrorCode(v68, v48, &v69);
          TraceHR(
            "onecoreuap\\enduser\\winstore\\installservice\\lib\\uwainstallwork.cpp",
            0x165Fu,
            "UWAInstallWork::_DoInstall",
            "GetInstallExtendedErrorCode(pPackages, spResult.Get(), &hrExtended)",
            InstallExtendedErrorCode,
            (int)v46);
          *((_DWORD *)v3 + 268) = v69;
          if ( Update == -2147467260 )
          {
            Update = -2147009278;
          }
          else if ( Update == -2147009288 )
          {
            Update = -2147467260;
          }
          else if ( Update >= 0 )
          {
            WindowsGetStringRawBuffer(*((HSTRING *)v3 + 59), 0);
            v34 = HResultFromWUResult((enum tagOperationResultCode)v66);
            LogMessage(
              1u,
              "onecoreuap\\enduser\\winstore\\installservice\\lib\\uwainstallwork.cpp",
              0x166Cu,
              "UWAInstallWork::_DoInstall",
              v34,
              L"Conflicting Operation Result. Something is not quite right. Extended error code returned success for ORC:%d",
              v7,
              v35);
            goto LABEL_48;
          }
        }
      }
    }
LABEL_49:
    Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v48);
    v4 = v62;
    goto LABEL_50;
  }
LABEL_52:
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_BackupScan>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_BackupScan>::GetImpl'::`2'::impl) )
  {
    if ( (unsigned __int8)UWAInstallWork::_ShouldFallbackToHarbor(v3, (unsigned int)Update, 3) )
    {
      v36 = WindowsGetStringRawBuffer(*((HSTRING *)v3 + 59), 0);
      LogSimpleMessage(
        3u,
        "onecoreuap\\enduser\\winstore\\installservice\\lib\\uwainstallwork.cpp",
        0x1682u,
        "UWAInstallWork::_DoInstall",
        Update,
        L"Install failed, triggering fallback to direct download",
        v7,
        v36);
      DurationInMilliseconds = UWAInstallWork::StageTimer::GetDurationInMilliseconds((UWAInstallWork::StageTimer *)&ticks);
      *((_BYTE *)v3 + 985) = 1;
      *((_DWORD *)v3 + 248) = Update;
      *((_DWORD *)v3 + 249) = v69;
      *((_DWORD *)v3 + 247) = 3;
      *((_QWORD *)v3 + 125) = DurationInMilliseconds;
      goto LABEL_57;
    }
    *((_BYTE *)v3 + 985) = 0;
  }
  v38 = UWAInstallWork::StageTimer::GetDurationInMilliseconds((UWAInstallWork::StageTimer *)&ticks);
  WindowsUpdate::Telemetry::EndInstall(
    v3,
    (struct UWAInstallWork *)v7,
    (const char *)(unsigned int)Update,
    v69,
    v38,
    (unsigned __int64)v46);
LABEL_57:
  v39 = v56;
  if ( v56 )
  {
    v56 = 0;
    ((void (__fastcall *)(struct IInstallationProgressChangedCallback *))v39->lpVtbl->Release)(v39);
  }
  if ( Update < 0 )
    goto LABEL_62;
  return (unsigned int)Update;
}

```

## disassembly

```asm
0x1800f1ff0  mov     rax, rsp
0x1800f1ff3  mov     [rax+18h], r8
0x1800f1ff7  mov     [rax+10h], rdx
0x1800f1ffb  mov     [rax+8], rcx
0x1800f1fff  push    rbx
0x1800f2000  push    rsi
0x1800f2001  push    rdi
0x1800f2002  push    r12
0x1800f2004  push    r13
0x1800f2006  push    r14
0x1800f2008  push    r15
0x1800f200a  sub     rsp, 0E0h
0x1800f2011  mov     r13, rcx
0x1800f2014  lea     rbx, [rcx+418h]
0x1800f201b  mov     [rsp+118h+var_58], rbx
0x1800f2023  mov     rdx, rbx
0x1800f2026  lea     rcx, [rax+20h]
0x1800f202a  call    ?AcquireSRWLockExclusive@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_SRWLOCK@@@Z; wil::AcquireSRWLockExclusive(_RTL_SRWLOCK *)
0x1800f202f  lea     rdi, [r13+424h]
0x1800f2036  mov     [rsp+118h+var_50], rdi
0x1800f203e  mov     eax, [rdi]
0x1800f2040  sub     eax, 5
0x1800f2043  xor     esi, esi
0x1800f2045  mov     r14d, 80004004h
0x1800f204b  cmp     eax, 1
0x1800f204e  jbe     short loc_1800F205B
0x1800f2050  mov     r15d, esi
0x1800f2053  mov     dword ptr [rdi], 3
0x1800f2059  jmp     short loc_1800F205E
0x1800f205b  mov     r15d, r14d
0x1800f205e  lea     rcx, [rsp+118h+arg_18]; this
0x1800f2066  call    ?InternalUnlock@SyncLockExclusive@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockExclusive::InternalUnlock(void)
0x1800f206b  test    r15d, r15d
0x1800f206e  js      short loc_1800F209E
0x1800f2070  xor     edx, edx; bool
0x1800f2072  mov     rcx, r13; this
0x1800f2075  call    ?_RaiseProgressEvent@UWAInstallWork@@AEAAX_N@Z; UWAInstallWork::_RaiseProgressEvent(bool)
0x1800f207a  mov     rdx, rbx
0x1800f207d  lea     rcx, [rsp+118h+arg_18]
0x1800f2085  call    ?LockShared@SRWLock@Wrappers@WRL@Microsoft@@SA?AVSyncLockShared@Details@234@PEAU_RTL_SRWLOCK@@@Z; Microsoft::WRL::Wrappers::SRWLock::LockShared(_RTL_SRWLOCK *)
0x1800f208a  cmp     dword ptr [rdi], 3
0x1800f208d  cmovnz  r15d, r14d
0x1800f2091  lea     rcx, [rsp+118h+arg_18]; this
0x1800f2099  call    ?InternalUnlock@SyncLockShared@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockShared::InternalUnlock(void)
0x1800f209e  mov     rdx, rbx
0x1800f20a1  lea     rcx, [rsp+118h+arg_18]
0x1800f20a9  call    ?AcquireSRWLockExclusive@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_SRWLOCK@@@Z; wil::AcquireSRWLockExclusive(_RTL_SRWLOCK *)
0x1800f20ae  lea     r12, [r13+130h]
0x1800f20b5  mov     [rsp+118h+var_48], r12
0x1800f20bd  mov     rdx, r12; char *
0x1800f20c0  mov     rcx, [r13+128h]; this
0x1800f20c7  call    ?Increment@TraceLoggingCorrelationVector@@QEAA_NPEAD@Z; TraceLoggingCorrelationVector::Increment(char *)
0x1800f20cc  lea     rcx, [rsp+118h+arg_18]; this
0x1800f20d4  call    ?InternalUnlock@SyncLockExclusive@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockExclusive::InternalUnlock(void)
0x1800f20d9  mov     rcx, r13; this
0x1800f20dc  test    r15d, r15d
0x1800f20df  js      loc_1800F2910
0x1800f20e5  mov     rdx, r12; struct UWAInstallWork *
0x1800f20e8  call    ?BeginInstall@Telemetry@WindowsUpdate@@YAXPEAVUWAInstallWork@@PEBD@Z; WindowsUpdate::Telemetry::BeginInstall(UWAInstallWork *,char const *)
0x1800f20ed  call    cs:__imp__Xtime_get_ticks
0x1800f20f3  mov     [rsp+118h+var_80], rax
0x1800f20fb  mov     r15d, 8007000Eh
0x1800f2101  mov     rdx, rbx
0x1800f2104  lea     rcx, [rsp+118h+var_A8]
0x1800f2109  call    ?LockShared@SRWLock@Wrappers@WRL@Microsoft@@SA?AVSyncLockShared@Details@234@PEAU_RTL_SRWLOCK@@@Z; Microsoft::WRL::Wrappers::SRWLock::LockShared(_RTL_SRWLOCK *)
0x1800f210e  nop
0x1800f210f  mov     edx, [r13+80h]
0x1800f2116  mov     ecx, [r13+444h]
0x1800f211d  call    ?GetPercentStartForInstallPhase@@YAIIW4InstallType@Internal@WindowsUpdate@@@Z; GetPercentStartForInstallPhase(uint,WindowsUpdate::Internal::InstallType)
0x1800f2122  mov     [rsp+118h+var_AC], eax
0x1800f2126  add     eax, 5
0x1800f2129  mov     [rsp+118h+var_B0], eax
0x1800f212d  cmp     eax, 64h ; 'd'
0x1800f2130  jbe     short loc_1800F2188
0x1800f2132  lea     rax, aFailed_1; "Failed"
0x1800f2139  mov     [rsp+118h+var_D0], rax
0x1800f213e  lea     rax, aPercentmax100; "percentMax <= 100"
0x1800f2145  mov     [rsp+118h+var_D8], rax
0x1800f214a  mov     [rsp+118h+var_E0], rsi; unsigned __int16 *
0x1800f214f  mov     [rsp+118h+var_E8], rsi; char *
0x1800f2154  lea     rax, aAssertSS; "Assert (%s): %s"
0x1800f215b  mov     [rsp+118h+var_F0], rax; unsigned __int16 *
0x1800f2160  mov     dword ptr [rsp+118h+var_F8], 0FFFFFFFFh; int
0x1800f2168  lea     r9, aUwainstallwork_7; "UWAInstallWork::_DoInstall"
0x1800f216f  mov     r8d, 1602h; unsigned int
0x1800f2175  lea     rdx, aOnecoreuapEndu_12; "onecoreuap\\enduser\\winstore\\installs"...
0x1800f217c  mov     ecx, 1; unsigned int
0x1800f2181  call    ?LogMessage@@YAXIPEBDI0JPEBG01ZZ; LogMessage(uint,char const *,uint,char const *,long,ushort const *,char const *,ushort const *,...)
0x1800f2186  int     2Ch; Windows NT - assertion failure
0x1800f2188  lea     rcx, [rsp+118h+var_A8]; this
0x1800f218d  call    ?InternalUnlock@SyncLockShared@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockShared::InternalUnlock(void)
0x1800f2192  mov     [rsp+118h+var_A8], r13
0x1800f2197  lea     r9, [rsp+118h+var_B0]
0x1800f219c  lea     r8, [rsp+118h+var_AC]
0x1800f21a1  lea     rdx, [rsp+118h+var_A8]
0x1800f21a6  lea     rcx, [rsp+118h+var_88]
0x1800f21ae  call    ??$Make@VInstallationProgress@@PEAVUWAInstallWork@@II@Details@WRL@Microsoft@@YA?AV?$ComPtr@VInstallationProgress@@@12@$$QEAPEAVUWAInstallWork@@$$QEAI1@Z; Microsoft::WRL::Details::Make<InstallationProgress,UWAInstallWork *,uint,uint>(UWAInstallWork * &&,uint &&,uint &&)
0x1800f21b3  nop
0x1800f21b4  mov     [rsp+118h+arg_18], 80070490h
0x1800f21bf  cmp     [rsp+118h+var_88], rsi
0x1800f21c7  jz      loc_1800F27FD
0x1800f21cd  mov     [rsp+118h+var_A8], rsi
0x1800f21d2  mov     [rsp+118h+var_A0], rsi
0x1800f21d7  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ImmediateRetryInstall@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ImmediateRetryInstall@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ImmediateRetryInstall> `wil::Feature<__WilFeatureTraits_Feature_ImmediateRetryInstall>::GetImpl(void)'::`2'::impl
0x1800f21de  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ImmediateRetryInstall@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ImmediateRetryInstall>::__private_IsEnabled(void)
0x1800f21e3  lea     rcx, [rsp+118h+var_A0]
0x1800f21e8  test    al, al
0x1800f21ea  jz      loc_1800F2390
0x1800f21f0  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1800f21f5  lea     rcx, [rsp+118h+var_A8]
0x1800f21fa  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1800f21ff  mov     rcx, [rsp+118h+var_88]
0x1800f2207  mov     [rsp+118h+var_70], rcx
0x1800f220f  mov     rax, rcx
0x1800f2212  add     rcx, 8
0x1800f2216  neg     rax
0x1800f2219  sbb     rax, rax
0x1800f221c  and     rax, rcx
0x1800f221f  mov     [rsp+118h+var_78], rax
0x1800f2227  xor     edx, edx; length
0x1800f2229  mov     rcx, [r13+70h]; string
0x1800f222d  call    cs:__imp_WindowsGetStringRawBuffer
0x1800f2233  mov     [rsp+118h+var_68], rax
0x1800f223b  mov     rcx, r13; this
0x1800f223e  call    ?_GetIntent@UWAInstallWork@@AEBAPEAUHSTRING__@@XZ; UWAInstallWork::_GetIntent(void)
0x1800f2243  mov     [rsp+118h+var_60], rax
0x1800f224b  mov     ecx, [r13+80h]
0x1800f2252  mov     r8d, [r13+420h]
0x1800f2259  mov     [rsp+118h+var_AC], r8d
0x1800f225e  mov     edx, r8d
0x1800f2261  and     edx, 2000h
0x1800f2267  mov     eax, edx
0x1800f2269  neg     eax
0x1800f226b  sbb     eax, eax
0x1800f226d  and     eax, 8000h
0x1800f2272  mov     dword ptr [rsp+118h+var_B8], eax
0x1800f2276  mov     r9d, r8d
0x1800f2279  mov     eax, 8
0x1800f227e  and     r9d, eax
0x1800f2281  shl     r9d, 0Dh
0x1800f2285  mov     [rsp+118h+var_98], r9d
0x1800f228d  mov     r10d, esi
0x1800f2290  cmp     ecx, 1
0x1800f2293  setz    r10b
0x1800f2297  mov     [rsp+118h+var_90], r10d
0x1800f229f  cmp     ecx, 3
0x1800f22a2  cmovnz  eax, esi
0x1800f22a5  mov     [rsp+118h+var_B0], eax
0x1800f22a9  mov     r15d, 20h ; ' '
0x1800f22af  cmp     ecx, 4
0x1800f22b2  cmovnz  r15d, esi
0x1800f22b6  mov     ecx, r8d
0x1800f22b9  shr     ecx, 2
0x1800f22bc  and     ecx, 1000h
0x1800f22c2  mov     [rsp+118h+var_94], ecx
0x1800f22c9  test    edx, edx
0x1800f22cb  jz      short loc_1800F22D2
0x1800f22cd  mov     rdx, rsi
0x1800f22d0  jmp     short loc_1800F2302
0x1800f22d2  lea     rcx, [r13+98h]
0x1800f22d9  call    ?_getToken@ContextData@CallerContext@@AEAAAEBV?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@XZ; CallerContext::ContextData::_getToken(void)
0x1800f22de  mov     rdx, [rax+8]; void *
0x1800f22e2  mov     r8d, [rsp+118h+var_AC]
0x1800f22e7  mov     eax, [rsp+118h+var_B0]
0x1800f22eb  mov     r9d, [rsp+118h+var_98]
0x1800f22f3  mov     ecx, [rsp+118h+var_94]
0x1800f22fa  mov     r10d, [rsp+118h+var_90]
0x1800f2302  or      r15d, eax
0x1800f2305  or      r15d, r10d
0x1800f2308  or      r15d, r9d
0x1800f230b  or      r15d, dword ptr [rsp+118h+var_B8]
0x1800f2310  and     r8d, 1
0x1800f2314  shl     r8d, 4
0x1800f2318  or      r15d, r8d
0x1800f231b  or      r15d, ecx
0x1800f231e  lea     rax, [rsp+118h+var_A0]
0x1800f2323  mov     [rsp+118h+var_C0], rax; struct IInstallationJob **
0x1800f2328  lea     rax, [rsp+118h+var_A8]
0x1800f232d  mov     [rsp+118h+var_C8], rax; struct IUpdateInstaller **
0x1800f2332  mov     [rsp+118h+var_D0], r12; char *
0x1800f2337  mov     rax, [rsp+118h+var_78]
0x1800f233f  mov     [rsp+118h+var_D8], rax; struct IInstallationCompletedCallback *
0x1800f2344  mov     rax, [rsp+118h+var_70]
0x1800f234c  mov     [rsp+118h+var_E0], rax; struct IInstallationProgressChangedCallback *
0x1800f2351  mov     rax, [rsp+118h+var_68]
0x1800f2359  mov     [rsp+118h+var_E8], rax; unsigned __int16 *
0x1800f235e  mov     rax, [rsp+118h+var_60]
0x1800f2366  mov     [rsp+118h+var_F0], rax; HSTRING
0x1800f236b  mov     dword ptr [rsp+118h+var_F8], r15d; unsigned int
0x1800f2370  mov     r9, [rsp+118h+arg_10]; struct IUpdateCollection *
0x1800f2378  mov     r8, [rsp+118h+arg_8]; struct IUpdateSession *
0x1800f2380  mov     rcx, r13; this
0x1800f2383  call    ?_InstallPackagesWithRetry@UWAInstallWork@@AEAAJPEAXPEAUIUpdateSession@@PEAUIUpdateCollection@@KPEAUHSTRING__@@PEBGPEAUIInstallationProgressChangedCallback@@PEAUIInstallationCompletedCallback@@PEBDPEAPEAUIUpdateInstaller@@PEAPEAUIInstallationJob@@@Z; UWAInstallWork::_InstallPackagesWithRetry(void *,IUpdateSession *,IUpdateCollection *,ulong,HSTRING__ *,ushort const *,IInstallationProgressChangedCallback *,IInstallationCompletedCallback *,char const *,IUpdateInstaller * *,IInstallationJob * *)
0x1800f2388  mov     r15d, eax
0x1800f238b  jmp     loc_1800F2522
0x1800f2390  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1800f2395  lea     rcx, [rsp+118h+var_A8]
0x1800f239a  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1800f239f  mov     rcx, [rsp+118h+var_88]
0x1800f23a7  mov     [rsp+118h+var_68], rcx
0x1800f23af  mov     rax, rcx
0x1800f23b2  add     rcx, 8
0x1800f23b6  neg     rax
0x1800f23b9  sbb     rax, rax
0x1800f23bc  and     rax, rcx
0x1800f23bf  mov     [rsp+118h+var_60], rax
0x1800f23c7  xor     edx, edx; length
0x1800f23c9  mov     rcx, [r13+70h]; string
0x1800f23cd  call    cs:__imp_WindowsGetStringRawBuffer
0x1800f23d3  mov     [rsp+118h+var_70], rax
0x1800f23db  mov     rcx, r13; this
0x1800f23de  call    ?_GetIntent@UWAInstallWork@@AEBAPEAUHSTRING__@@XZ; UWAInstallWork::_GetIntent(void)
0x1800f23e3  mov     [rsp+118h+var_78], rax
0x1800f23eb  mov     ecx, [r13+80h]
0x1800f23f2  mov     r8d, [r13+420h]
0x1800f23f9  mov     [rsp+118h+var_90], r8d
0x1800f2401  mov     edx, r8d
0x1800f2404  and     edx, 2000h
0x1800f240a  mov     eax, edx
0x1800f240c  neg     eax
0x1800f240e  sbb     eax, eax
0x1800f2410  and     eax, 8000h
0x1800f2415  mov     [rsp+118h+var_98], eax
0x1800f241c  mov     eax, r8d
0x1800f241f  mov     r9d, 8
0x1800f2425  and     eax, r9d
0x1800f2428  shl     eax, 0Dh
0x1800f242b  mov     dword ptr [rsp+118h+var_B8], eax
0x1800f242f  mov     r10d, esi
0x1800f2432  cmp     ecx, 1
0x1800f2435  setz    r10b
0x1800f2439  mov     [rsp+118h+var_94], r10d
0x1800f2441  cmp     ecx, 3
0x1800f2444  cmovnz  r9d, esi
0x1800f2448  mov     [rsp+118h+var_B0], r9d
0x1800f244d  mov     r15d, 20h ; ' '
0x1800f2453  cmp     ecx, 4
0x1800f2456  cmovnz  r15d, esi
0x1800f245a  mov     ecx, r8d
0x1800f245d  shr     ecx, 2
0x1800f2460  and     ecx, 1000h
0x1800f2466  mov     [rsp+118h+var_AC], ecx
0x1800f246a  test    edx, edx
0x1800f246c  jz      short loc_1800F2473
0x1800f246e  mov     rcx, rsi
0x1800f2471  jmp     short loc_1800F249C
0x1800f2473  lea     rcx, [r13+98h]
0x1800f247a  call    ?_getToken@ContextData@CallerContext@@AEAAAEBV?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@XZ; CallerContext::ContextData::_getToken(void)
0x1800f247f  mov     rcx, [rax+8]; void *
0x1800f2483  mov     eax, dword ptr [rsp+118h+var_B8]
0x1800f2487  mov     r8d, [rsp+118h+var_90]
0x1800f248f  mov     r9d, [rsp+118h+var_B0]
0x1800f2494  mov     r10d, [rsp+118h+var_94]
0x1800f249c  or      eax, r15d
0x1800f249f  or      r9d, eax
0x1800f24a2  or      r9d, r10d
0x1800f24a5  or      r9d, [rsp+118h+var_98]
0x1800f24ad  and     r8d, 1
0x1800f24b1  shl     r8d, 4
0x1800f24b5  or      r9d, r8d
0x1800f24b8  or      r9d, [rsp+118h+var_AC]; unsigned int
0x1800f24bd  lea     rdx, [rsp+118h+var_A0]
0x1800f24c2  mov     [rsp+118h+var_C8], rdx; struct IInstallationJob **
0x1800f24c7  lea     rdx, [rsp+118h+var_A8]
0x1800f24cc  mov     [rsp+118h+var_D0], rdx; struct IUpdateInstaller **
0x1800f24d1  mov     [rsp+118h+var_D8], r12; char *
0x1800f24d6  mov     rdx, [rsp+118h+var_60]
0x1800f24de  mov     [rsp+118h+var_E0], rdx; struct IInstallationCompletedCallback *
0x1800f24e3  mov     rdx, [rsp+118h+var_68]
0x1800f24eb  mov     [rsp+118h+var_E8], rdx; struct IInstallationProgressChangedCallback *
0x1800f24f0  mov     rdx, [rsp+118h+var_70]
0x1800f24f8  mov     [rsp+118h+var_F0], rdx; unsigned __int16 *
0x1800f24fd  mov     rdx, [rsp+118h+var_78]
0x1800f2505  mov     [rsp+118h+var_F8], rdx; HSTRING
0x1800f250a  mov     r8, [rsp+118h+arg_10]; struct IUpdateCollection *
0x1800f2512  mov     rdx, [rsp+118h+arg_8]; struct IUpdateSession *
0x1800f251a  call    ?InstallPackages@@YAJPEAXPEAUIUpdateSession@@PEAUIUpdateCollection@@KPEAUHSTRING__@@PEBGPEAUIInstallationProgressChangedCallback@@PEAUIInstallationCompletedCallback@@PEBDPEAPEAUIUpdateInstaller@@PEAPEAUIInstallationJob@@@Z; InstallPackages(void *,IUpdateSession *,IUpdateCollection *,ulong,HSTRING__ *,ushort const *,IInstallationProgressChangedCallback *,IInstallationCompletedCallback *,char const *,IUpdateInstaller * *,IInstallationJob * *)
0x1800f251f  mov     r15d, eax
0x1800f2522  jmp     short loc_1800F2551
0x1800f2524  xor     esi, esi
0x1800f2526  mov     r14d, 80004004h
0x1800f252c  mov     r13, [rsp+118h+arg_0]
0x1800f2534  mov     r15d, dword ptr [rsp+118h+var_B8]
0x1800f2539  mov     rdi, [rsp+118h+var_50]
0x1800f2541  mov     r12, [rsp+118h+var_48]
0x1800f2549  mov     rbx, [rsp+118h+var_58]
0x1800f2551  test    r15d, r15d
0x1800f2554  js      loc_1800F27E8
0x1800f255a  mov     rdx, rbx
0x1800f255d  lea     rcx, [rsp+118h+arg_0]
0x1800f2565  call    ?AcquireSRWLockExclusive@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_SRWLOCK@@@Z; wil::AcquireSRWLockExclusive(_RTL_SRWLOCK *)
0x1800f256a  cmp     dword ptr [rdi], 3
0x1800f256d  jz      short loc_1800F2574
0x1800f256f  mov     r15d, r14d
0x1800f2572  jmp     short loc_1800F2585
0x1800f2574  lea     rdx, [rsp+118h+var_A0]
0x1800f2579  lea     rcx, [r13+480h]
0x1800f2580  call    ??4?$ComPtr@U?$IAsyncOperationWithProgress@PEAVDeploymentResult@Deployment@Management@Windows@@UDeploymentProgress@234@@Foundation@Windows@@@WRL@Microsoft@@QEAAAEAV012@AEBV012@@Z; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationWithProgress<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress>>::operator=(Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationWithProgress<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress>> const &)
0x1800f2585  lea     rcx, [rsp+118h+arg_0]; this
0x1800f258d  call    ?InternalUnlock@SyncLockExclusive@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockExclusive::InternalUnlock(void)
  ... truncated ...
```
