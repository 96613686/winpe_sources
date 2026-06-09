# UWAInstallWork::_DoInstallWorkForAllLoggedOnUsers(IUpdateSession *,char *,long &)

- ea: `0x1800f4734`
- end: `0x1800f501a`
- name: `?_DoInstallWorkForAllLoggedOnUsers@UWAInstallWork@@AEAAJPEAUIUpdateSession@@PEADAEAJ@Z`
- size: `2278`
- prototype: `__int64 __fastcall(UWAInstallWork *__hidden this, struct IUpdateSession *, char *, int *)`
- caller_count: `1`
- callee_count: `28`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800f3450`

## callees

- `0x18000ee20`
- `0x1800101f4`
- `0x180011fc4`
- `0x180012368`
- `0x180012394`
- `0x1800123f8`
- `0x180012428`
- `0x18001bf24`
- `0x18001c414`
- `0x18002ec2c`
- `0x180032d10`
- `0x180034bb0`
- `0x180037acc`
- `0x18003f884`
- `0x180044bc0`
- `0x180052008`
- `0x180075608`
- `0x180076e48`
- `0x1800de844`
- `0x1800e9638`
- `0x1800e9b24`
- `0x1800ecb68`
- `0x1800f4734`
- `0x1800f964c`
- `0x1800fb8b8`
- `0x1800fbabc`
- `0x1801dac2c`
- `0x180215010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800f4ae7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800f4ec7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800f4ae7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800f4ec7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f48a7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f48b9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f49af`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f49df`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f4a52`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f4a70`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f4b9f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f4bd0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f4d25`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f4d97`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f4dd2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f4f1d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f48a7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f48b9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f49af`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f49df`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f4a52`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f4a70`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f4b9f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f4bd0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f4d25`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f4d97`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f4dd2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f4f1d`

## string_xrefs

- `0x1800f47a6`: `onecoreuap\enduser\winstore\installservice\lib\uwainstallwork.cpp`
- `0x1800f48ce`: `Attempting to register update for User:%s`
- `0x1800f4a85`: `Nothing to register for User: %s. Skipping Install`
- `0x1800f4daa`: `Failed to Register for UserSid: %ws`
- `0x1800f4de5`: `Failed to Register for UserSid: %ws`
- `0x1800f4f3a`: `Completed Register operation for %d users`
- `0x1800f4cba`: `UserSid: %ws`
- `0x1800f47e8`: `UWAInstallWork::_DoInstallWorkForAllLoggedOnUsers`
- `0x1800f48e2`: `UWAInstallWork::_DoInstallWorkForAllLoggedOnUsers`
- `0x1800f4a99`: `UWAInstallWork::_DoInstallWorkForAllLoggedOnUsers`
- `0x1800f4f4e`: `UWAInstallWork::_DoInstallWorkForAllLoggedOnUsers`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall UWAInstallWork::_DoInstallWorkForAllLoggedOnUsers(
        UWAInstallWork *this,
        struct IUpdateSession *a2,
        OLECHAR *a3,
        unsigned int *a4)
{
  unsigned int v5; // r12d
  int PercentStartForInstallPhase; // esi
  __int64 v7; // rdx
  __int64 v8; // rbx
  __int64 v9; // rcx
  double v10; // xmm0_8
  __int64 v11; // rax
  double v12; // xmm6_8
  int v13; // edi
  __int64 v14; // rax
  __int64 v15; // rcx
  _QWORD *v16; // r13
  PCWSTR StringRawBuffer; // rbx
  const unsigned __int16 *v18; // rax
  unsigned __int16 *v19; // rdi
  struct IUpdateInternalConfiguration *Intent; // rsi
  WCHAR *v21; // rax
  unsigned int updated; // ebx
  const char *v23; // rax
  const char *v24; // rbx
  const unsigned __int16 *v25; // rax
  struct IInstallationProgressChangedCallback *v26; // rcx
  char *v27; // rsi
  const char *v28; // r12
  struct IInstallationProgressChangedCallback *v29; // rdi
  unsigned __int16 *v30; // rbx
  HSTRING v31; // r8
  int v32; // r10d
  int v33; // ecx
  int v34; // eax
  int v35; // r9d
  int v36; // ecx
  unsigned int v37; // eax
  const char *v38; // rdi
  unsigned int v39; // eax
  const char *v40; // rax
  const char *v41; // rax
  struct IInstallationProgressChangedCallback *v42; // rcx
  __int64 v43; // rbx
  const unsigned __int16 *v44; // rax
  const char *v45; // r9
  __int64 v47; // rcx
  unsigned int v48; // eax
  char IsEnabled; // al
  TraceLoggingCorrelationVector *v50; // rcx
  int v51; // [rsp+20h] [rbp-128h]
  HSTRING string; // [rsp+70h] [rbp-D8h] BYREF
  char *v53; // [rsp+78h] [rbp-D0h] BYREF
  struct IInstallationJob *v54; // [rsp+80h] [rbp-C8h] BYREF
  struct IUpdateCollection *v55; // [rsp+88h] [rbp-C0h] BYREF
  struct IInstallationProgressChangedCallback *v56; // [rsp+90h] [rbp-B8h] BYREF
  char *v57; // [rsp+98h] [rbp-B0h] BYREF
  struct IUpdateInstaller *v58; // [rsp+A0h] [rbp-A8h] BYREF
  __int64 v59; // [rsp+A8h] [rbp-A0h]
  _BYTE v60[8]; // [rsp+B0h] [rbp-98h] BYREF
  int v61; // [rsp+B8h] [rbp-90h] BYREF
  int v62; // [rsp+BCh] [rbp-8Ch]
  int v63; // [rsp+C0h] [rbp-88h]
  __int64 v64; // [rsp+C8h] [rbp-80h] BYREF
  __int64 v65; // [rsp+D0h] [rbp-78h] BYREF
  __int64 v66; // [rsp+D8h] [rbp-70h]
  __int64 v67; // [rsp+E0h] [rbp-68h]
  UWAInstallWork *v68; // [rsp+E8h] [rbp-60h] BYREF
  _BYTE v69[8]; // [rsp+F0h] [rbp-58h] BYREF
  _BYTE v70[8]; // [rsp+F8h] [rbp-50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+148h] [rbp+0h]

  try
  {
    v5 = 0;
    LODWORD(v53) = 0;
    TokenHelpers::GetAllLoggedInUserTokens(&v65);
    Microsoft::WRL::Wrappers::SRWLock::LockShared(v60, (char *)this + 1048);
    PercentStartForInstallPhase = GetPercentStartForInstallPhase(
                                    *((unsigned int *)this + 273),
                                    *((unsigned int *)this + 32));
    v63 = PercentStartForInstallPhase;
    if ( (unsigned int)(PercentStartForInstallPhase + 5) > 0x64 )
    {
      LogMessage(
        1u,
        "onecoreuap\\enduser\\winstore\\installservice\\lib\\uwainstallwork.cpp",
        0x18EDu,
        "UWAInstallWork::_DoInstallWorkForAllLoggedOnUsers",
        -1,
        L"Assert (%s): %s",
        0,
        0,
        L"percentMax <= 100",
        L"Failed");
      __int2c();
    }
    Microsoft::WRL::Wrappers::Details::SyncLockShared::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockShared *)v60);
    v7 = v65;
    v8 = v66;
    v9 = (v66 - v65) >> 4;
    if ( v9 )
    {
      if ( v9 < 0 )
      {
        v11 = ((v66 - v65) >> 4) & 1 | ((unsigned __int64)v9 >> 1);
        v10 = (double)(int)v11 + (double)(int)v11;
      }
      else
      {
        v10 = (double)(int)v9;
      }
      v12 = 5.0 / v10;
    }
    else
    {
      v12 = 0.0;
    }
    v13 = 0;
    v14 = v65;
    v15 = v66;
    v64 = v66;
    v16 = (_QWORD *)((char *)this + 304);
    v57 = (char *)this + 304;
    while ( 1 )
    {
      v59 = v14;
      if ( v14 == v15 )
        break;
      TokenHelpers::GetTokenSid(&string, v14);
      StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
      v18 = WindowsGetStringRawBuffer(*((HSTRING *)this + 59), 0);
      LogMessage(
        3u,
        "onecoreuap\\enduser\\winstore\\installservice\\lib\\uwainstallwork.cpp",
        0x18F5u,
        "UWAInstallWork::_DoInstallWorkForAllLoggedOnUsers",
        -1,
        L"Attempting to register update for User:%s",
        (const char *)this + 304,
        v18,
        StringRawBuffer);
      *a4 = -2147023728;
      UWAInstallWork::_SwitchState(this);
      v62 = v13 + 1;
      v61 = (int)((double)(v13 + 1) * v12 + (double)PercentStartForInstallPhase);
      LODWORD(v57) = (int)((double)v13 * v12 + (double)PercentStartForInstallPhase);
      v68 = this;
      wil::MakeOrThrow<InstallationProgress,UWAInstallWork *,unsigned int,unsigned int>(&v56, &v68, &v57, &v61);
      v55 = 0;
      Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v55);
      v19 = (unsigned __int16 *)WindowsGetStringRawBuffer(*((HSTRING *)this + 14), 0);
      LOBYTE(StringRawBuffer) = (*((_DWORD *)this + 32) & 0xFFFFFFFB) == 0;
      v57 = (char *)this + 304;
      Intent = (struct IUpdateInternalConfiguration *)UWAInstallWork::_GetIntent(this);
      v21 = (WCHAR *)WindowsGetStringRawBuffer(*((HSTRING *)this + 15), 0);
      updated = SearchUpdatePackages(
                  *(void **)(v59 + 8),
                  v21,
                  0,
                  Intent,
                  0,
                  0,
                  0,
                  1,
                  1,
                  (char)StringRawBuffer,
                  v19,
                  a2,
                  a3,
                  &v55);
      v23 = (const char *)WindowsGetStringRawBuffer(string, 0);
      if ( updated == -2145124316 )
      {
        v24 = v23;
        v25 = WindowsGetStringRawBuffer(*((HSTRING *)this + 59), 0);
        LogMessage(
          3u,
          "onecoreuap\\enduser\\winstore\\installservice\\lib\\uwainstallwork.cpp",
          0x1915u,
          "UWAInstallWork::_DoInstallWorkForAllLoggedOnUsers",
          -1,
          L"Nothing to register for User: %s. Skipping Install",
          (const char *)this + 304,
          v25,
          v24);
        Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v55);
        v26 = v56;
        if ( v56 )
        {
          v56 = 0;
          ((void (__fastcall *)(struct IInstallationProgressChangedCallback *))v26->lpVtbl->Release)(v26);
        }
      }
      else
      {
        wil::details::in1diag3::Throw_IfFailedMsg(
          retaddr,
          (void *)0x1919,
          (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\uwainstallwork.cpp",
          (const char *)updated,
          (int)"Failed to get packages to register for user: %ws",
          v23);
        v58 = 0;
        v54 = 0;
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AsyncLicensing>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AsyncLicensing>::GetImpl'::`2'::impl) )
        {
          wil::AcquireSRWLockExclusive(v69, (char *)this + 1048);
          TraceLoggingCorrelationVector::Increment(*((TraceLoggingCorrelationVector **)this + 37), (char *)this + 304);
          v27 = (char *)a3;
          *(_QWORD *)a3 = *v16;
          Microsoft::WRL::Wrappers::Details::SyncLockExclusive::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockExclusive *)v69);
        }
        else
        {
          v27 = (char *)a3;
          TraceLoggingCorrelationVector::Increment(*((TraceLoggingCorrelationVector **)this + 37), (char *)a3);
        }
        v28 = (const char *)WindowsGetStringRawBuffer(string, 0);
        Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v54);
        Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v58);
        v29 = v56;
        v30 = (unsigned __int16 *)WindowsGetStringRawBuffer(*((HSTRING *)this + 14), 0);
        v31 = UWAInstallWork::_GetIntent(this);
        v32 = *((_DWORD *)this + 32);
        v33 = 32;
        v34 = 0;
        if ( v32 != 4 )
          v33 = 0;
        v35 = v33
            | (16 * (*((_DWORD *)this + 264) & 1))
            | (*((_DWORD *)this + 264) >> 2) & 0x1000
            | (4 * (*((_DWORD *)this + 264) & 0x2000 | ((*((_DWORD *)this + 264) & 8) << 11)));
        v36 = 8;
        if ( v32 != 3 )
          v36 = 0;
        LOBYTE(v34) = v32 == 1;
        v37 = InstallPackages(
                *(void **)(v59 + 8),
                a2,
                v55,
                v34 | v36 | (unsigned int)v35,
                v31,
                v30,
                v29,
                (struct IInstallationCompletedCallback *)((unsigned __int64)&v29[1] & -(__int64)(v29 != 0)),
                v27,
                &v58,
                &v54);
        wil::details::in1diag3::Throw_IfFailedMsg(
          retaddr,
          (void *)0x1938,
          (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\uwainstallwork.cpp",
          (const char *)v37,
          (int)"UserSid: %ws",
          v28);
        wil::AcquireSRWLockExclusive(v60, (char *)this + 1048);
        if ( *((_DWORD *)this + 265) != 3 )
        {
          Microsoft::WRL::Wrappers::Details::SyncLockExclusive::~SyncLockExclusive((Microsoft::WRL::Wrappers::Details::SyncLockExclusive *)v60);
          v47 = winrt::com_ptr<IUniversalOrchestrator>::operator->(&v54);
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v47 + 96LL))(v47);
          v48 = wil::verify_hresult<long>(2147500036LL);
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x1941,
            (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\uwainstallwork.cpp",
            (const char *)v48,
            v51);
        }
        Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationWithProgress<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress>>::operator=(
          (char *)this + 1152,
          &v54);
        Microsoft::WRL::Wrappers::Details::SyncLockExclusive::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockExclusive *)v60);
        v38 = (const char *)WindowsGetStringRawBuffer(string, 0);
        v39 = ((__int64 (__fastcall *)(struct IInstallationJob *))v54->lpVtbl->CleanUp)(v54);
        wil::details::in1diag3::Throw_IfFailedMsg(
          retaddr,
          (void *)0x1949,
          (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\uwainstallwork.cpp",
          (const char *)v39,
          (int)"UserSid: %ws",
          v38);
        *a4 = GetExtendedHResultForInstallationJob(v58, v54, v55, (int *)&v53);
        v40 = (const char *)WindowsGetStringRawBuffer(string, 0);
        v5 = (unsigned int)v53;
        wil::details::in1diag3::Throw_IfFailedMsg(
          retaddr,
          (void *)0x194D,
          (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\uwainstallwork.cpp",
          (const char *)(unsigned int)v53,
          (int)"Failed to Register for UserSid: %ws",
          v40);
        v41 = (const char *)WindowsGetStringRawBuffer(string, 0);
        wil::details::in1diag3::Throw_IfFailedMsg(
          retaddr,
          (void *)0x194E,
          (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\uwainstallwork.cpp",
          (const char *)*a4,
          (int)"Failed to Register for UserSid: %ws",
          v41);
        if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AsyncLicensing>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AsyncLicensing>::GetImpl'::`2'::impl) )
          TraceLoggingCorrelationVector::Increment(*((TraceLoggingCorrelationVector **)this + 37), v27);
        wil::AcquireSRWLockExclusive(v70, (char *)this + 1048);
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AsyncLicensing>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AsyncLicensing>::GetImpl'::`2'::impl) )
        {
          TraceLoggingCorrelationVector::Increment(*((TraceLoggingCorrelationVector **)this + 37), (char *)this + 304);
          *(_QWORD *)v27 = *v16;
        }
        Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease((char *)this + 1152);
        Microsoft::WRL::Wrappers::Details::SyncLockExclusive::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockExclusive *)v70);
        Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v54);
        Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v58);
        Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v55);
        v42 = v56;
        if ( v56 )
        {
          v56 = 0;
          ((void (__fastcall *)(struct IInstallationProgressChangedCallback *))v42->lpVtbl->Release)(v42);
        }
      }
      WindowsDeleteString(string);
      string = 0;
      v13 = v62;
      v14 = v59 + 16;
      v8 = v66;
      v7 = v65;
      PercentStartForInstallPhase = v63;
      v15 = v64;
    }
    v43 = (v8 - v7) >> 4;
    v44 = WindowsGetStringRawBuffer(*((HSTRING *)this + 59), 0);
    LogMessage(
      3u,
      "onecoreuap\\enduser\\winstore\\installservice\\lib\\uwainstallwork.cpp",
      0x1960u,
      "UWAInstallWork::_DoInstallWorkForAllLoggedOnUsers",
      -1,
      L"Completed Register operation for %d users",
      v57,
      v44,
      v43);
    UWAInstallWork::_SetPostInstallState(this);
    if ( v65 )
    {
      std::_Destroy_range<std::allocator<Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>>>(
        v65,
        v66);
      std::_Deallocate<16>(v65, (v67 - v65) & 0xFFFFFFFFFFFFFFF0uLL);
    }
  }
  catch ( ... )
  {
    LODWORD(v53) = wil::details::in1diag3::Log_CaughtException(
                     retaddr,
                     (void *)0x1965,
                     (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\uwainstallwork.cpp",
                     v45);
    wil::AcquireSRWLockExclusive(&v64, (char *)this + 1048);
    IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_AsyncLicensing>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AsyncLicensing>::GetImpl'::`2'::impl);
    v50 = (TraceLoggingCorrelationVector *)*((_QWORD *)this + 37);
    if ( IsEnabled )
    {
      TraceLoggingCorrelationVector::Increment(v50, (char *)this + 304);
      *(_QWORD *)a3 = *((_QWORD *)this + 38);
    }
    else
    {
      TraceLoggingCorrelationVector::Increment(v50, (char *)a3);
    }
    Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease((char *)this + 1152);
    Microsoft::WRL::Wrappers::Details::SyncLockExclusive::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockExclusive *)&v64);
    return (unsigned int)v53;
  }
  return v5;
}

```

## disassembly

```asm
0x1800f4734  mov     rax, rsp
0x1800f4737  mov     [rax+20h], r9
0x1800f473b  mov     [rax+18h], r8
0x1800f473f  mov     [rax+10h], rdx
0x1800f4743  mov     [rax+8], rcx
0x1800f4747  push    rbx
0x1800f4748  push    rsi
0x1800f4749  push    rdi
0x1800f474a  push    r12
0x1800f474c  push    r13
0x1800f474e  push    r14
0x1800f4750  push    r15
0x1800f4752  sub     rsp, 110h
0x1800f4759  movaps  xmmword ptr [rax-48h], xmm6
0x1800f475d  mov     r14, rcx
0x1800f4760  xor     r12d, r12d
0x1800f4763  mov     dword ptr [rsp+148h+var_D0], r12d
0x1800f4768  lea     rcx, [rax-78h]
0x1800f476c  call    ?GetAllLoggedInUserTokens@TokenHelpers@@YA?AV?$vector@V?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@V?$allocator@V?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@@std@@@std@@XZ; TokenHelpers::GetAllLoggedInUserTokens(void)
0x1800f4771  nop
0x1800f4772  lea     rdx, [r14+418h]
0x1800f4779  lea     rcx, [rsp+148h+var_98]
0x1800f4781  call    ?LockShared@SRWLock@Wrappers@WRL@Microsoft@@SA?AVSyncLockShared@Details@234@PEAU_RTL_SRWLOCK@@@Z; Microsoft::WRL::Wrappers::SRWLock::LockShared(_RTL_SRWLOCK *)
0x1800f4786  nop
0x1800f4787  mov     edx, [r14+80h]
0x1800f478e  mov     ecx, [r14+444h]
0x1800f4795  call    ?GetPercentStartForInstallPhase@@YAIIW4InstallType@Internal@WindowsUpdate@@@Z; GetPercentStartForInstallPhase(uint,WindowsUpdate::Internal::InstallType)
0x1800f479a  mov     esi, eax
0x1800f479c  mov     [rsp+148h+var_88], eax
0x1800f47a3  add     eax, 5
0x1800f47a6  lea     r15, aOnecoreuapEndu_12; "onecoreuap\\enduser\\winstore\\installs"...
0x1800f47ad  cmp     eax, 64h ; 'd'
0x1800f47b0  jbe     short loc_1800F4804
0x1800f47b2  lea     rax, aFailed_1; "Failed"
0x1800f47b9  mov     [rsp+148h+var_100], rax
0x1800f47be  lea     rax, aPercentmax100; "percentMax <= 100"
0x1800f47c5  mov     [rsp+148h+var_108], rax
0x1800f47ca  mov     [rsp+148h+var_110], r12; unsigned __int16 *
0x1800f47cf  mov     [rsp+148h+var_118], r12; char *
0x1800f47d4  lea     rax, aAssertSS; "Assert (%s): %s"
0x1800f47db  mov     [rsp+148h+var_120], rax; unsigned __int16 *
0x1800f47e0  mov     dword ptr [rsp+148h+var_128], 0FFFFFFFFh; int
0x1800f47e8  lea     r9, aUwainstallwork_60; "UWAInstallWork::_DoInstallWorkForAllLog"...
0x1800f47ef  mov     r8d, 18EDh; unsigned int
0x1800f47f5  mov     rdx, r15; char *
0x1800f47f8  lea     ecx, [r12+1]; unsigned int
0x1800f47fd  call    ?LogMessage@@YAXIPEBDI0JPEBG01ZZ; LogMessage(uint,char const *,uint,char const *,long,ushort const *,char const *,ushort const *,...)
0x1800f4802  int     2Ch; Windows NT - assertion failure
0x1800f4804  lea     rcx, [rsp+148h+var_98]; this
0x1800f480c  call    ?InternalUnlock@SyncLockShared@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockShared::InternalUnlock(void)
0x1800f4811  mov     rdx, [rsp+148h+var_78]
0x1800f4819  mov     rbx, [rsp+148h+var_70]
0x1800f4821  mov     rcx, rbx
0x1800f4824  sub     rcx, rdx
0x1800f4827  sar     rcx, 4
0x1800f482b  test    rcx, rcx
0x1800f482e  jz      short loc_1800F485F
0x1800f4830  xorps   xmm0, xmm0
0x1800f4833  js      short loc_1800F483C
0x1800f4835  cvtsi2sd xmm0, rcx
0x1800f483a  jmp     short loc_1800F4851
0x1800f483c  mov     rax, rcx
0x1800f483f  shr     rax, 1
0x1800f4842  and     ecx, 1
0x1800f4845  or      rax, rcx
0x1800f4848  cvtsi2sd xmm0, rax
0x1800f484d  addsd   xmm0, xmm0
0x1800f4851  movsd   xmm6, cs:__real@4014000000000000
0x1800f4859  divsd   xmm6, xmm0
0x1800f485d  jmp     short loc_1800F4862
0x1800f485f  xorps   xmm6, xmm6
0x1800f4862  xor     edi, edi
0x1800f4864  mov     rax, rdx
0x1800f4867  mov     rcx, rbx
0x1800f486a  mov     [rsp+148h+var_80], rbx
0x1800f4872  lea     r13, [r14+130h]
0x1800f4879  mov     [rsp+148h+var_B0], r13
0x1800f4881  mov     [rsp+148h+var_A0], rax
0x1800f4889  cmp     rax, rcx
0x1800f488c  jz      loc_1800F4F0D
0x1800f4892  mov     rdx, rax
0x1800f4895  lea     rcx, [rsp+148h+string]
0x1800f489a  call    ?GetTokenSid@TokenHelpers@@YA?AVHString@Wrappers@WRL@Microsoft@@AEBV?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@345@@Z; TokenHelpers::GetTokenSid(Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits> const &)
0x1800f489f  nop
0x1800f48a0  xor     edx, edx; length
0x1800f48a2  mov     rcx, [rsp+148h+string]; string
0x1800f48a7  call    cs:__imp_WindowsGetStringRawBuffer
0x1800f48ad  mov     rbx, rax
0x1800f48b0  xor     edx, edx; length
0x1800f48b2  mov     rcx, [r14+1D8h]; string
0x1800f48b9  call    cs:__imp_WindowsGetStringRawBuffer
0x1800f48bf  mov     [rsp+148h+var_108], rbx
0x1800f48c4  mov     [rsp+148h+var_110], rax; unsigned __int16 *
0x1800f48c9  mov     [rsp+148h+var_118], r13; char *
0x1800f48ce  lea     rax, aAttemptingToRe; "Attempting to register update for User:"...
0x1800f48d5  mov     [rsp+148h+var_120], rax; unsigned __int16 *
0x1800f48da  mov     dword ptr [rsp+148h+var_128], 0FFFFFFFFh; int
0x1800f48e2  lea     r9, aUwainstallwork_60; "UWAInstallWork::_DoInstallWorkForAllLog"...
0x1800f48e9  mov     r8d, 18F5h; unsigned int
0x1800f48ef  mov     rdx, r15; char *
0x1800f48f2  mov     ecx, 3; unsigned int
0x1800f48f7  call    ?LogMessage@@YAXIPEBDI0JPEBG01ZZ; LogMessage(uint,char const *,uint,char const *,long,ushort const *,char const *,ushort const *,...)
0x1800f48fc  mov     rax, [rsp+148h+arg_18]
0x1800f4904  mov     dword ptr [rax], 80070490h
0x1800f490a  mov     rcx, r14
0x1800f490d  call    ?_SwitchState@UWAInstallWork@@AEAAXW4InstallState@Internal@WindowsUpdate@@@Z; UWAInstallWork::_SwitchState(WindowsUpdate::Internal::InstallState)
0x1800f4912  lea     ecx, [rdi+1]
0x1800f4915  mov     [rsp+148h+var_8C], ecx
0x1800f491c  mov     eax, esi
0x1800f491e  xorps   xmm1, xmm1
0x1800f4921  cvtsi2sd xmm1, rax
0x1800f4926  mov     eax, ecx
0x1800f4928  xorps   xmm0, xmm0
0x1800f492b  cvtsi2sd xmm0, rax
0x1800f4930  mulsd   xmm0, xmm6
0x1800f4934  addsd   xmm0, xmm1
0x1800f4938  cvttsd2si rax, xmm0
0x1800f493d  mov     [rsp+148h+var_90], eax
0x1800f4944  mov     eax, edi
0x1800f4946  xorps   xmm0, xmm0
0x1800f4949  cvtsi2sd xmm0, rax
0x1800f494e  mulsd   xmm0, xmm6
0x1800f4952  addsd   xmm0, xmm1
0x1800f4956  cvttsd2si rax, xmm0
0x1800f495b  mov     dword ptr [rsp+148h+var_B0], eax
0x1800f4962  mov     [rsp+148h+var_60], r14
0x1800f496a  lea     r9, [rsp+148h+var_90]
0x1800f4972  lea     r8, [rsp+148h+var_B0]
0x1800f497a  lea     rdx, [rsp+148h+var_60]
0x1800f4982  lea     rcx, [rsp+148h+var_B8]
0x1800f498a  call    ??$MakeOrThrow@VInstallationProgress@@PEAVUWAInstallWork@@II@wil@@YA?AV?$ComPtr@VInstallationProgress@@@WRL@Microsoft@@$$QEAPEAVUWAInstallWork@@$$QEAI1@Z; wil::MakeOrThrow<InstallationProgress,UWAInstallWork *,uint,uint>(UWAInstallWork * &&,uint &&,uint &&)
0x1800f498f  nop
0x1800f4990  mov     [rsp+148h+var_C0], 0
0x1800f499c  lea     rcx, [rsp+148h+var_C0]
0x1800f49a4  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1800f49a9  xor     edx, edx; length
0x1800f49ab  mov     rcx, [r14+70h]; string
0x1800f49af  call    cs:__imp_WindowsGetStringRawBuffer
0x1800f49b5  mov     rdi, rax
0x1800f49b8  test    dword ptr [r14+80h], 0FFFFFFFBh
0x1800f49c3  setz    bl
0x1800f49c6  mov     [rsp+148h+var_B0], r13
0x1800f49ce  mov     rcx, r14; this
0x1800f49d1  call    ?_GetIntent@UWAInstallWork@@AEBAPEAUHSTRING__@@XZ; UWAInstallWork::_GetIntent(void)
0x1800f49d6  mov     rsi, rax
0x1800f49d9  xor     edx, edx; length
0x1800f49db  mov     rcx, [r14+78h]; string
0x1800f49df  call    cs:__imp_WindowsGetStringRawBuffer
0x1800f49e5  lea     rcx, [rsp+148h+var_C0]
0x1800f49ed  mov     [rsp+148h+var_E0], rcx
0x1800f49f2  mov     rcx, [rsp+148h+arg_10]
0x1800f49fa  mov     [rsp+148h+var_E8], rcx
0x1800f49ff  mov     rcx, [rsp+148h+arg_8]
0x1800f4a07  mov     [rsp+148h+var_F0], rcx
0x1800f4a0c  mov     [rsp+148h+var_F8], rdi
0x1800f4a11  mov     byte ptr [rsp+148h+var_100], bl
0x1800f4a15  mov     byte ptr [rsp+148h+var_108], 1
0x1800f4a1a  mov     byte ptr [rsp+148h+var_110], 1
0x1800f4a1f  xor     edi, edi
0x1800f4a21  mov     byte ptr [rsp+148h+var_118], dil
0x1800f4a26  mov     byte ptr [rsp+148h+var_120], dil
0x1800f4a2b  mov     dword ptr [rsp+148h+var_128], edi
0x1800f4a2f  mov     r9, rsi
0x1800f4a32  xor     r8d, r8d
0x1800f4a35  mov     rdx, rax
0x1800f4a38  mov     rcx, [rsp+148h+var_A0]
0x1800f4a40  mov     rcx, [rcx+8]
0x1800f4a44  call    ?SearchUpdatePackages@@YAJPEAXPEBG1PEAUHSTRING__@@W4WU_INSTALLED_FLAG@@_N44441PEAUIUpdateSession@@PEBDPEAPEAUIUpdateCollection@@@Z; SearchUpdatePackages(void *,ushort const *,ushort const *,HSTRING__ *,WU_INSTALLED_FLAG,bool,bool,bool,bool,bool,ushort const *,IUpdateSession *,char const *,IUpdateCollection * *)
0x1800f4a49  mov     ebx, eax
0x1800f4a4b  xor     edx, edx; length
0x1800f4a4d  mov     rcx, [rsp+148h+string]; string
0x1800f4a52  call    cs:__imp_WindowsGetStringRawBuffer
0x1800f4a58  cmp     ebx, 80240024h
0x1800f4a5e  jnz     loc_1800F4AF7
0x1800f4a64  mov     rbx, rax
0x1800f4a67  xor     edx, edx; length
0x1800f4a69  mov     rcx, [r14+1D8h]; string
0x1800f4a70  call    cs:__imp_WindowsGetStringRawBuffer
0x1800f4a76  mov     [rsp+148h+var_108], rbx
0x1800f4a7b  mov     [rsp+148h+var_110], rax; unsigned __int16 *
0x1800f4a80  mov     [rsp+148h+var_118], r13; char *
0x1800f4a85  lea     rax, aNothingToRegis; "Nothing to register for User: %s. Skipp"...
0x1800f4a8c  mov     [rsp+148h+var_120], rax; unsigned __int16 *
0x1800f4a91  mov     dword ptr [rsp+148h+var_128], 0FFFFFFFFh; int
0x1800f4a99  lea     r9, aUwainstallwork_60; "UWAInstallWork::_DoInstallWorkForAllLog"...
0x1800f4aa0  mov     r8d, 1915h; unsigned int
0x1800f4aa6  mov     rdx, r15; char *
0x1800f4aa9  lea     ecx, [rdi+3]; unsigned int
0x1800f4aac  call    ?LogMessage@@YAXIPEBDI0JPEBG01ZZ; LogMessage(uint,char const *,uint,char const *,long,ushort const *,char const *,ushort const *,...)
0x1800f4ab1  nop
0x1800f4ab2  lea     rcx, [rsp+148h+var_C0]
0x1800f4aba  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1800f4abf  nop
0x1800f4ac0  mov     rcx, [rsp+148h+var_B8]
0x1800f4ac8  test    rcx, rcx
0x1800f4acb  jz      short loc_1800F4AE2
0x1800f4acd  mov     [rsp+148h+var_B8], rdi
0x1800f4ad5  mov     rax, [rcx]
0x1800f4ad8  mov     rax, [rax+10h]
0x1800f4adc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f4ae1  nop
0x1800f4ae2  mov     rcx, [rsp+148h+string]; string
0x1800f4ae7  call    cs:__imp_WindowsDeleteString
0x1800f4aed  mov     [rsp+148h+string], rdi
0x1800f4af2  jmp     loc_1800F4ED6
0x1800f4af7  mov     rcx, [rsp+148h]; this
0x1800f4aff  mov     [rsp+148h+var_120], rax; char *
0x1800f4b04  lea     rax, aFailedToGetPac; "Failed to get packages to register for "...
0x1800f4b0b  mov     [rsp+148h+var_128], rax; int
0x1800f4b10  mov     r9d, ebx; char *
0x1800f4b13  mov     r8, r15; unsigned int
0x1800f4b16  mov     edx, 1919h; void *
0x1800f4b1b  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x1800f4b20  mov     [rsp+148h+var_A8], rdi
0x1800f4b28  mov     [rsp+148h+var_C8], rdi
0x1800f4b30  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AsyncLicensing@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AsyncLicensing@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AsyncLicensing> `wil::Feature<__WilFeatureTraits_Feature_AsyncLicensing>::GetImpl(void)'::`2'::impl
0x1800f4b37  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AsyncLicensing@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AsyncLicensing>::__private_IsEnabled(void)
0x1800f4b3c  test    al, al
0x1800f4b3e  jz      short loc_1800F4B81
0x1800f4b40  lea     rdx, [r14+418h]
0x1800f4b47  lea     rcx, [rsp+148h+var_58]
0x1800f4b4f  call    ?AcquireSRWLockExclusive@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_SRWLOCK@@@Z; wil::AcquireSRWLockExclusive(_RTL_SRWLOCK *)
0x1800f4b54  mov     rdx, r13; char *
0x1800f4b57  mov     rcx, [r14+128h]; this
0x1800f4b5e  call    ?Increment@TraceLoggingCorrelationVector@@QEAA_NPEAD@Z; TraceLoggingCorrelationVector::Increment(char *)
0x1800f4b63  mov     rax, [r13+0]
0x1800f4b67  mov     rsi, [rsp+148h+arg_10]
0x1800f4b6f  mov     [rsi], rax
0x1800f4b72  lea     rcx, [rsp+148h+var_58]; this
0x1800f4b7a  call    ?InternalUnlock@SyncLockExclusive@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockExclusive::InternalUnlock(void)
0x1800f4b7f  jmp     short loc_1800F4B98
0x1800f4b81  mov     rsi, [rsp+148h+arg_10]
0x1800f4b89  mov     rdx, rsi; char *
0x1800f4b8c  mov     rcx, [r14+128h]; this
0x1800f4b93  call    ?Increment@TraceLoggingCorrelationVector@@QEAA_NPEAD@Z; TraceLoggingCorrelationVector::Increment(char *)
0x1800f4b98  xor     edx, edx; length
0x1800f4b9a  mov     rcx, [rsp+148h+string]; string
0x1800f4b9f  call    cs:__imp_WindowsGetStringRawBuffer
0x1800f4ba5  mov     r12, rax
0x1800f4ba8  lea     rcx, [rsp+148h+var_C8]
0x1800f4bb0  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1800f4bb5  lea     rcx, [rsp+148h+var_A8]
0x1800f4bbd  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1800f4bc2  mov     rdi, [rsp+148h+var_B8]
0x1800f4bca  xor     edx, edx; length
0x1800f4bcc  mov     rcx, [r14+70h]; string
0x1800f4bd0  call    cs:__imp_WindowsGetStringRawBuffer
0x1800f4bd6  mov     rbx, rax
0x1800f4bd9  mov     rcx, r14; this
0x1800f4bdc  call    ?_GetIntent@UWAInstallWork@@AEBAPEAUHSTRING__@@XZ; UWAInstallWork::_GetIntent(void)
0x1800f4be1  mov     r8, rax
0x1800f4be4  mov     r10d, [r14+80h]
0x1800f4beb  mov     edx, [r14+420h]
0x1800f4bf2  mov     rax, rdi
0x1800f4bf5  lea     rcx, [rdi+8]
0x1800f4bf9  neg     rax
0x1800f4bfc  sbb     r11, r11
0x1800f4bff  and     r11, rcx
0x1800f4c02  mov     r9d, edx
0x1800f4c05  and     r9d, 8
0x1800f4c09  shl     r9d, 0Bh
0x1800f4c0d  mov     eax, edx
0x1800f4c0f  and     eax, 2000h
0x1800f4c14  or      r9d, eax
0x1800f4c17  shl     r9d, 2
0x1800f4c1b  mov     eax, edx
0x1800f4c1d  shr     eax, 2
0x1800f4c20  and     eax, 1000h
0x1800f4c25  or      r9d, eax
0x1800f4c28  and     edx, 1
0x1800f4c2b  shl     edx, 4
0x1800f4c2e  or      r9d, edx
0x1800f4c31  mov     ecx, 20h ; ' '
0x1800f4c36  xor     eax, eax
0x1800f4c38  cmp     r10d, 4
0x1800f4c3c  cmovnz  ecx, eax
0x1800f4c3f  or      r9d, ecx
0x1800f4c42  lea     ecx, [rax+8]
0x1800f4c45  cmp     r10d, 3
0x1800f4c49  cmovnz  ecx, eax
0x1800f4c4c  or      r9d, ecx
0x1800f4c4f  cmp     r10d, 1
0x1800f4c53  setz    al
0x1800f4c56  or      r9d, eax; unsigned int
0x1800f4c59  lea     rax, [rsp+148h+var_C8]
0x1800f4c61  mov     [rsp+148h+var_F8], rax; struct IInstallationJob **
0x1800f4c66  lea     rax, [rsp+148h+var_A8]
0x1800f4c6e  mov     [rsp+148h+var_100], rax; struct IUpdateInstaller **
0x1800f4c73  mov     [rsp+148h+var_108], rsi; char *
0x1800f4c78  mov     [rsp+148h+var_110], r11; struct IInstallationCompletedCallback *
0x1800f4c7d  mov     [rsp+148h+var_118], rdi; struct IInstallationProgressChangedCallback *
0x1800f4c82  mov     [rsp+148h+var_120], rbx; unsigned __int16 *
0x1800f4c87  mov     [rsp+148h+var_128], r8; HSTRING
0x1800f4c8c  mov     r8, [rsp+148h+var_C0]; struct IUpdateCollection *
0x1800f4c94  mov     rdx, [rsp+148h+arg_8]; struct IUpdateSession *
0x1800f4c9c  mov     rax, [rsp+148h+var_A0]
0x1800f4ca4  mov     rcx, [rax+8]; void *
0x1800f4ca8  call    ?InstallPackages@@YAJPEAXPEAUIUpdateSession@@PEAUIUpdateCollection@@KPEAUHSTRING__@@PEBGPEAUIInstallationProgressChangedCallback@@PEAUIInstallationCompletedCallback@@PEBDPEAPEAUIUpdateInstaller@@PEAPEAUIInstallationJob@@@Z; InstallPackages(void *,IUpdateSession *,IUpdateCollection *,ulong,HSTRING__ *,ushort const *,IInstallationProgressChangedCallback *,IInstallationCompletedCallback *,char const *,IUpdateInstaller * *,IInstallationJob * *)
0x1800f4cad  mov     rcx, [rsp+148h]; this
0x1800f4cb5  mov     [rsp+148h+var_120], r12; char *
  ... truncated ...
```
