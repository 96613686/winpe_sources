# CLockAction::_SyncBackstopVisualToLogonVisual(void)

- ea: `0x18001def0`
- end: `0x18001ec2c`
- name: `?_SyncBackstopVisualToLogonVisual@CLockAction@@AEAAJXZ`
- size: `3388`
- prototype: `__int64 __fastcall(CLockAction *__hidden this)`
- caller_count: `2`
- callee_count: `15`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180041be0`
- `0x180048140`

## callees

- `0x180017dec`
- `0x18001c56c`
- `0x18001c860`
- `0x18001cc60`
- `0x18001d850`
- `0x18001db70`
- `0x18001def0`
- `0x18001ec34`
- `0x18001ecd8`
- `0x180059a34`
- `0x18005b3e4`
- `0x18005d488`
- `0x18006c000`
- `0x18009b790`
- `0x18009d010`

## import_xrefs

- `KERNEL32!ReleaseSRWLockExclusive` at `0x18001e2e4`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18001e4de`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18001e561`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18001e635`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18001e6d3`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18001e81e`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18001e870`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18001e8c0`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18001e92b`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18001e9aa`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18001ea29`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18001eaa8`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18001eb32`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18001e2e4`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18001e4de`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18001e561`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18001e635`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18001e6d3`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18001e81e`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18001e870`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18001e8c0`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18001e92b`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18001e9aa`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18001ea29`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18001eaa8`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18001eb32`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18001e0d1`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18001e722`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18001e0d1`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18001e722`
- `KERNEL32!CloseHandle` at `0x18001e449`
- `KERNEL32!CloseHandle` at `0x18001eaf2`
- `KERNEL32!CloseHandle` at `0x18001e449`
- `KERNEL32!CloseHandle` at `0x18001eaf2`
- `KERNEL32!SetLastError` at `0x18001eb6f`
- `KERNEL32!SetLastError` at `0x18001eb6f`
- `KERNEL32!GetLastError` at `0x18001eb5c`
- `KERNEL32!GetLastError` at `0x18001eb5c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001e021`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001e021`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001e066`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001e066`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001e334`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001eb67`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001e334`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001eb67`
- `dwmapi!DwmUnregisterThumbnail` at `0x18001e119`
- `dwmapi!DwmUnregisterThumbnail` at `0x18001e119`
- `dwmapi!__imp_DwmpCreateSharedThumbnailVisual` at `0x18001e3e0`
- `dwmapi!__imp_DwmpCreateSharedThumbnailVisual` at `0x18001e3e0`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!PostMessageW` at `0x18001e13c`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!PostMessageW` at `0x18001e13c`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!FindWindowW` at `0x18001e0e0`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!FindWindowW` at `0x18001e0f2`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!FindWindowW` at `0x18001e0e0`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!FindWindowW` at `0x18001e0f2`
- `api-ms-win-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x18001e36e`
- `api-ms-win-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x18001e37c`
- `api-ms-win-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x18001e36e`
- `api-ms-win-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x18001e37c`
- `api-ms-win-ntuser-rectangle-l1-1-0!CopyRect` at `0x18001e38d`
- `api-ms-win-ntuser-rectangle-l1-1-0!CopyRect` at `0x18001e38d`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CLockAction::_SyncBackstopVisualToLogonVisual(RTL_SRWLOCK *this)
{
  __int128 v2; // xmm6
  LSTATUS Value; // eax
  bool v4; // sf
  HWND WindowW; // r15
  HWND v6; // rax
  HWND v7; // r12
  PVOID Ptr; // rcx
  int v9; // eax
  unsigned int v10; // edi
  int v11; // eax
  __int64 v12; // rsi
  __int64 (__fastcall *v13)(__int64, DWORD *); // rdi
  int v14; // eax
  int v15; // eax
  __int64 v16; // rsi
  __int64 (__fastcall *v17)(__int64, void **); // rdi
  int v18; // eax
  HKEY v19; // rcx
  void *v20; // rcx
  __int64 v21; // rcx
  void *v22; // rcx
  __int64 v23; // rcx
  int v24; // eax
  int v25; // eax
  void *v26; // rcx
  void *v27; // rcx
  __int64 v28; // rcx
  void *v29; // rcx
  struct IDCompositionDevice2 *v30; // rcx
  void *v31; // rcx
  __int64 v32; // rcx
  void *v33; // rcx
  void *v34; // rcx
  __int64 v35; // rcx
  void *v36; // rcx
  struct IDCompositionDevice2 *v37; // rcx
  __int64 v38; // rcx
  void *v39; // rcx
  __int64 v40; // rcx
  int v41; // eax
  struct IDCompositionDevice2 *v42; // rcx
  void *v43; // rcx
  void *v44; // rcx
  void *v45; // rcx
  void *v46; // rcx
  CLockAction *v48; // rcx
  int v49; // r8d
  int v50; // r9d
  int GDIRenderedDCompSurface; // eax
  int v52; // eax
  int v53; // eax
  unsigned int phkResult; // [rsp+20h] [rbp-E0h]
  int phkResulta; // [rsp+20h] [rbp-E0h]
  int phkResultb; // [rsp+20h] [rbp-E0h]
  bool lpcbData; // [rsp+28h] [rbp-D8h]
  DWORD Type[2]; // [rsp+40h] [rbp-C0h] BYREF
  DWORD cbData[2]; // [rsp+48h] [rbp-B8h] BYREF
  void *v60; // [rsp+50h] [rbp-B0h] BYREF
  void *v61; // [rsp+58h] [rbp-A8h] BYREF
  HKEY hKey; // [rsp+60h] [rbp-A0h] BYREF
  void *v63; // [rsp+68h] [rbp-98h] BYREF
  HANDLE hObject; // [rsp+70h] [rbp-90h]
  BYTE Data[16]; // [rsp+80h] [rbp-80h] BYREF
  int v66; // [rsp+90h] [rbp-70h] BYREF
  tagRECT rcDst; // [rsp+94h] [rbp-6Ch] BYREF
  __int128 v68; // [rsp+A4h] [rbp-5Ch]
  _BYTE v69[9]; // [rsp+B4h] [rbp-4Ch] BYREF
  void **v70; // [rsp+C0h] [rbp-40h] BYREF
  int v71; // [rsp+C8h] [rbp-38h] BYREF
  char v72; // [rsp+CCh] [rbp-34h]
  int v73; // [rsp+F0h] [rbp-10h] BYREF
  const char *v74; // [rsp+F8h] [rbp-8h]
  __int64 v75; // [rsp+100h] [rbp+0h]
  char v76; // [rsp+108h] [rbp+8h]
  int v77; // [rsp+110h] [rbp+10h]
  __int128 v78; // [rsp+118h] [rbp+18h]
  __int128 v79; // [rsp+128h] [rbp+28h]
  __int128 v80; // [rsp+138h] [rbp+38h]
  __int128 v81; // [rsp+148h] [rbp+48h]
  __int128 v82; // [rsp+158h] [rbp+58h]
  __int128 v83; // [rsp+168h] [rbp+68h]
  __int128 v84; // [rsp+178h] [rbp+78h]
  __int128 v85; // [rsp+188h] [rbp+88h]
  __int128 v86; // [rsp+198h] [rbp+98h]
  __int64 v87; // [rsp+1A8h] [rbp+A8h]
  __int128 v88; // [rsp+1B0h] [rbp+B0h]
  int v89; // [rsp+1C0h] [rbp+C0h]
  __int64 v90; // [rsp+1C8h] [rbp+C8h]
  int *v91; // [rsp+1D0h] [rbp+D0h]
  __int64 v92; // [rsp+1D8h] [rbp+D8h]
  char v93[48]; // [rsp+1E0h] [rbp+E0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  v70 = &wil::ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::`vftable';
  v71 = 0;
  v72 = 0;
  v76 = 0;
  v73 = 0;
  v74 = "CLockAction__SyncBackstopVisualToLogonVisual_Activity";
  v75 = 0;
  v77 = 0;
  v88 = 0;
  v78 = 0;
  v79 = 0;
  v80 = 0;
  v81 = 0;
  v82 = 0;
  v83 = 0;
  v84 = 0;
  v85 = 0;
  v86 = 0;
  v87 = 0;
  v89 = 1;
  v90 = 0;
  v91 = &v71;
  v92 = 0;
  wil::details::ThreadFailureCallbackHolder::ThreadFailureCallbackHolder(
    (wil::details::ThreadFailureCallbackHolder *)v93,
    (struct wil::details::IFailureCallback *)&v70,
    (struct wil::CallContextInfo *)&v73,
    0);
  v70 = &LogonControllerTelemetry::CLockAction__SyncBackstopVisualToLogonVisual_Activity::`vftable';
  v2 = 0;
  *(_OWORD *)Data = 0;
  hKey = 0;
  if ( RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\OOBE\\TelemetryCorrelation",
         0,
         0x20019u,
         &hKey) < 0 )
    goto LABEL_33;
  Type[0] = 3;
  cbData[0] = 16;
  Value = RegQueryValueExW(hKey, L"FirstRunCorrelationID", 0, Type, Data, cbData);
  v4 = Value < 0;
  if ( Value > 0 )
    v4 = 1;
  if ( v4 )
    *(_OWORD *)Data = 0;
  else
LABEL_33:
    v2 = *(_OWORD *)Data;
  if ( hKey )
    RegCloseKey(hKey);
  *(_OWORD *)Data = v2;
  if ( memcmp_0(Data, &GUID_NULL, 0x10u) )
    wil::ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::SetRelatedActivityId(
      &v70,
      Data);
  LogonControllerTelemetry::CLockAction__SyncBackstopVisualToLogonVisual_Activity::StartActivity((LogonControllerTelemetry::CLockAction__SyncBackstopVisualToLogonVisual_Activity *)&v70);
  AcquireSRWLockExclusive(this + 45);
  WindowW = FindWindowW(L"LogonUI Logon Window", 0);
  v6 = FindWindowW(L"LogonUI worker window", 0);
  v7 = v6;
  if ( WindowW && v6 )
  {
    Ptr = this[55].Ptr;
    if ( Ptr )
    {
      DwmUnregisterThumbnail(Ptr);
      this[55].Ptr = 0;
    }
    CLockAction::_CleanupSharedVisual((CLockAction *)this);
    PostMessageW(WindowW, 0x7Eu, 0, 0);
    *(_QWORD *)Type = 0;
    Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(Type);
    v9 = CLockAction::_EnsureDevice((CLockAction *)this, (struct IDCompositionDesktopDevicePartner **)Type);
    v10 = v9;
    if ( v9 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x331,
        (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lockhost\\lockaction.cpp",
        (const char *)(unsigned int)v9,
        phkResult);
      Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(Type);
      if ( this != (RTL_SRWLOCK *)-360LL )
        ReleaseSRWLockExclusive(this + 45);
      goto LABEL_115;
    }
    v60 = 0;
    v11 = (*(__int64 (__fastcall **)(_QWORD, PVOID, GUID *, void **))(**(_QWORD **)Type + 232LL))(
            *(_QWORD *)Type,
            this[47].Ptr,
            &GUID_eacdd04c_117e_4e17_88f4_d1b12b0e3d89,
            &v60);
    v10 = v11;
    if ( v11 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x334,
        (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lockhost\\lockaction.cpp",
        (const char *)(unsigned int)v11,
        phkResult);
      v31 = v60;
      if ( v60 )
      {
        v60 = 0;
        (*(void (__fastcall **)(void *))(*(_QWORD *)v31 + 16LL))(v31);
      }
      v32 = *(_QWORD *)Type;
      if ( *(_QWORD *)Type )
      {
        *(_QWORD *)Type = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
      }
      if ( this != (RTL_SRWLOCK *)-360LL )
        ReleaseSRWLockExclusive(this + 45);
      goto LABEL_115;
    }
    *(_QWORD *)cbData = 0;
    v12 = *(_QWORD *)Type;
    v13 = *(__int64 (__fastcall **)(__int64, DWORD *))(**(_QWORD **)Type + 48LL);
    Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(cbData);
    v14 = v13(v12, cbData);
    v10 = v14;
    if ( v14 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x337,
        (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lockhost\\lockaction.cpp",
        (const char *)(unsigned int)v14,
        phkResult);
      v38 = *(_QWORD *)cbData;
      if ( *(_QWORD *)cbData )
      {
        *(_QWORD *)cbData = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
      }
      v39 = v60;
      if ( v60 )
      {
        v60 = 0;
        (*(void (__fastcall **)(void *))(*(_QWORD *)v39 + 16LL))(v39);
      }
      v40 = *(_QWORD *)Type;
      if ( *(_QWORD *)Type )
      {
        *(_QWORD *)Type = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 16LL))(v40);
      }
      if ( this != (RTL_SRWLOCK *)-360LL )
        ReleaseSRWLockExclusive(this + 45);
      goto LABEL_115;
    }
    v15 = (*(__int64 (__fastcall **)(void *, _QWORD))(*(_QWORD *)v60 + 24LL))(v60, *(_QWORD *)cbData);
    v10 = v15;
    if ( v15 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x338,
        (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lockhost\\lockaction.cpp",
        (const char *)(unsigned int)v15,
        phkResult);
      Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(cbData);
      Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(&v60);
      Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(Type);
      if ( this != (RTL_SRWLOCK *)-360LL )
        ReleaseSRWLockExclusive(this + 45);
      goto LABEL_115;
    }
    v61 = 0;
    if ( dword_1800D354C == 1 )
    {
      hKey = 0;
      v16 = *(_QWORD *)Type;
      v17 = *(__int64 (__fastcall **)(__int64, void **))(**(_QWORD **)Type + 48LL);
      Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(&v61);
      v18 = v17(v16, &v61);
      v10 = v18;
      if ( v18 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x33F,
          (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lockhost\\lockaction.cpp",
          (const char *)(unsigned int)v18,
          phkResult);
        v19 = hKey;
        if ( hKey )
        {
          hKey = 0;
          (*(void (__fastcall **)(HKEY))(*(_QWORD *)v19 + 16LL))(v19);
        }
        v20 = v61;
        if ( v61 )
        {
          v61 = 0;
          (*(void (__fastcall **)(void *))(*(_QWORD *)v20 + 16LL))(v20);
        }
        v21 = *(_QWORD *)cbData;
        if ( *(_QWORD *)cbData )
        {
          *(_QWORD *)cbData = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
        }
        v22 = v60;
        if ( v60 )
        {
          v60 = 0;
          (*(void (__fastcall **)(void *))(*(_QWORD *)v22 + 16LL))(v22);
        }
        v23 = *(_QWORD *)Type;
        if ( *(_QWORD *)Type )
        {
          *(_QWORD *)Type = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
        }
        if ( this != (RTL_SRWLOCK *)-360LL )
          ReleaseSRWLockExclusive(this + 45);
LABEL_115:
        v70 = &LogonControllerTelemetry::CLockAction__SyncBackstopVisualToLogonVisual_Activity::`vftable';
        wil::ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(&v70);
        wil::ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(&v70);
        return v10;
      }
      Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(&hKey);
      GDIRenderedDCompSurface = CLockAction::_CreateGDIRenderedDCompSurface(
                                  v48,
                                  *(struct IDCompositionDevice2 **)Type,
                                  v49,
                                  v50,
                                  phkResult,
                                  lpcbData,
                                  (struct IDCompositionSurface **)&hKey);
      v10 = GDIRenderedDCompSurface;
      if ( GDIRenderedDCompSurface < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x340,
          (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lockhost\\lockaction.cpp",
          (const char *)(unsigned int)GDIRenderedDCompSurface,
          phkResultb);
        Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(&hKey);
        Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(&v61);
        Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(cbData);
        Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(&v60);
        Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(Type);
        if ( this != (RTL_SRWLOCK *)-360LL )
          ReleaseSRWLockExclusive(this + 45);
        goto LABEL_115;
      }
      v52 = (*(__int64 (__fastcall **)(void *, HKEY))(*(_QWORD *)v61 + 120LL))(v61, hKey);
      v10 = v52;
      if ( v52 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x341,
          (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lockhost\\lockaction.cpp",
          (const char *)(unsigned int)v52,
          phkResultb);
        Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(&hKey);
        Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(&v61);
        Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(cbData);
        Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(&v60);
        Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(Type);
        if ( this != (RTL_SRWLOCK *)-360LL )
          ReleaseSRWLockExclusive(this + 45);
        goto LABEL_115;
      }
      v53 = (*(__int64 (__fastcall **)(_QWORD, void *, __int64, _QWORD))(**(_QWORD **)cbData + 128LL))(
              *(_QWORD *)cbData,
              v61,
              1,
              0);
      v10 = v53;
      if ( v53 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x342,
          (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lockhost\\lockaction.cpp",
          (const char *)(unsigned int)v53,
          phkResultb);
        Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(&hKey);
        Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(&v61);
        Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(cbData);
        Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(&v60);
        Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(Type);
        if ( this != (RTL_SRWLOCK *)-360LL )
          ReleaseSRWLockExclusive(this + 45);
        goto LABEL_115;
      }
      Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(&hKey);
    }
    rcDst = 0;
    v68 = 0;
    memset(v69, 0, sizeof(v69));
    v66 = 25;
    *(_QWORD *)Data = 0;
    *(_DWORD *)&Data[8] = GetSystemMetrics(0);
    *(_DWORD *)&Data[12] = GetSystemMetrics(1);
    CopyRect(&rcDst, (const RECT *)Data);
    *(_QWORD *)&v69[1] = 0x100000001LL;
    v63 = 0;
    hObject = 0;
    Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(&v63);
    phkResulta = Type[0];
    v24 = DwmpCreateSharedThumbnailVisual(v7, WindowW, 0, &v66);
    v10 = v24;
    if ( v24 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x34F,
        (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lockhost\\lockaction.cpp",
        (const char *)(unsigned int)v24,
        phkResulta);
      v33 = v63;
      if ( v63 )
      {
        v63 = 0;
        (*(void (__fastcall **)(void *))(*(_QWORD *)v33 + 16LL))(v33);
      }
      v34 = v61;
      if ( v61 )
      {
        v61 = 0;
        (*(void (__fastcall **)(void *))(*(_QWORD *)v34 + 16LL))(v34);
      }
      v35 = *(_QWORD *)cbData;
      if ( *(_QWORD *)cbData )
      {
        *(_QWORD *)cbData = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
      }
      v36 = v60;
      if ( v60 )
      {
        v60 = 0;
        (*(void (__fastcall **)(void *))(*(_QWORD *)v36 + 16LL))(v36);
      }
      v37 = *(struct IDCompositionDevice2 **)Type;
      if ( *(_QWORD *)Type )
      {
        *(_QWORD *)Type = 0;
        (*(void (__fastcall **)(struct IDCompositionDevice2 *))(*(_QWORD *)v37 + 16LL))(v37);
      }
      if ( this != (RTL_SRWLOCK *)-360LL )
        ReleaseSRWLockExclusive(this + 45);
      goto LABEL_115;
    }
    if ( dword_1800D354C != 1 || !v61 )
    {
      v25 = (*(__int64 (__fastcall **)(_QWORD, void *, __int64, _QWORD))(**(_QWORD **)cbData + 128LL))(
              *(_QWORD *)cbData,
              v63,
              1,
              0);
      v10 = v25;
      if ( v25 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x357,
          (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lockhost\\lockaction.cpp",
          (const char *)(unsigned int)v25,
          phkResulta);
        CloseHandle(hObject);
        v26 = v63;
        if ( v63 )
        {
          v63 = 0;
          (*(void (__fastcall **)(void *))(*(_QWORD *)v26 + 16LL))(v26);
        }
        v27 = v61;
        if ( v61 )
        {
          v61 = 0;
          (*(void (__fastcall **)(void *))(*(_QWORD *)v27 + 16LL))(v27);
        }
        v28 = *(_QWORD *)cbData;
        if ( *(_QWORD *)cbData )
        {
          *(_QWORD *)cbData = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
        }
        v29 = v60;
        if ( v60 )
        {
          v60 = 0;
          (*(void (__fastcall **)(void *))(*(_QWORD *)v29 + 16LL))(v29);
        }
        v30 = *(struct IDCompositionDevice2 **)Type;
        if ( *(_QWORD *)Type )
        {
          *(_QWORD *)Type = 0;
          (*(void (__fastcall **)(struct IDCompositionDevice2 *))(*(_QWORD *)v30 + 16LL))(v30);
        }
        if ( this != (RTL_SRWLOCK *)-360LL )
          ReleaseSRWLockExclusive(this + 45);
        goto LABEL_115;
      }
    }
    v41 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)Type + 24LL))(*(_QWORD *)Type);
    v10 = v41;
    if ( v41 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x35A,
        (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lockhost\\lockaction.cpp",
        (const char *)(unsigned int)v41,
        phkResulta);
      CloseHandle(hObject);
      Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(&v63);
      Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(&v61);
      Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(cbData);
      Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(&v60);
      Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(Type);
      if ( this != (RTL_SRWLOCK *)-360LL )
        ReleaseSRWLockExclusive(this + 45);
      goto LABEL_115;
    }
    AcquireSRWLockExclusive(this + 48);
    Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(&this[49]);
    v42 = *(struct IDCompositionDevice2 **)Type;
    if ( *(_QWORD *)Type )
    {
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)Type + 8LL))(*(_QWORD *)Type);
      v42 = *(struct IDCompositionDevice2 **)Type;
    }
    this[49].Ptr = v42;
    Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(&this[50]);
    v43 = v60;
    if ( v60 )
    {
      (*(void (__fastcall **)(void *))(*(_QWORD *)v60 + 8LL))(v60);
      v43 = v60;
    }
    this[50].Ptr = v43;
    Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(&this[51]);
    v44 = *(void **)cbData;
    if ( *(_QWORD *)cbData )
    {
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)cbData + 8LL))(*(_QWORD *)cbData);
      v44 = *(void **)cbData;
    }
    this[51].Ptr = v44;
    if ( dword_1800D354C == 1 )
    {
      Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(&this[53]);
      v45 = v61;
      if ( v61 )
      {
        (*(void (__fastcall **)(void *))(*(_QWORD *)v61 + 8LL))(v61);
        v45 = v61;
      }
      this[53].Ptr = v45;
    }
    Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(&this[52]);
    v46 = v63;
    if ( v63 )
    {
      (*(void (__fastcall **)(void *))(*(_QWORD *)v63 + 8LL))(v63);
      v46 = v63;
    }
    this[52].Ptr = v46;
    this[55].Ptr = hObject;
    if ( this != (RTL_SRWLOCK *)-384LL )
      ReleaseSRWLockExclusive(this + 48);
    Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(&v63);
    Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(&v61);
    Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(cbData);
    Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(&v60);
    Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(Type);
  }
  wil::ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(&v70, 0);
  if ( this != (RTL_SRWLOCK *)-360LL )
    ReleaseSRWLockExclusive(this + 45);
  v70 = &LogonControllerTelemetry::CLockAction__SyncBackstopVisualToLogonVisual_Activity::`vftable';
  wil::ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(&v70);
  wil::ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(&v70);
  return 0;
}

```

## disassembly

```asm
0x18001def0  push    rbp
0x18001def2  push    rbx
0x18001def3  push    rsi
0x18001def4  push    rdi
0x18001def5  push    r12
0x18001def7  push    r13
0x18001def9  push    r14
0x18001defb  push    r15
0x18001defd  lea     rbp, [rsp-138h]
0x18001df05  sub     rsp, 238h
0x18001df0c  movaps  [rsp+270h+var_50], xmm6
0x18001df14  mov     rax, cs:__security_cookie
0x18001df1b  xor     rax, rsp
0x18001df1e  mov     [rbp+170h+var_60], rax
0x18001df25  mov     rbx, rcx
0x18001df28  lea     rax, ??_7?$ActivityBase@VLogonControllerLogger@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@6B@; const wil::ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::`vftable'
0x18001df2f  mov     [rbp+170h+var_1B0], rax
0x18001df33  xor     r13d, r13d
0x18001df36  mov     [rbp+170h+var_1A8], r13d
0x18001df3a  mov     [rbp+170h+var_1A4], r13b
0x18001df3e  mov     [rbp+170h+var_168], r13b
0x18001df42  mov     [rbp+170h+var_180], r13d
0x18001df46  lea     rax, aClockactionSyn_0; "CLockAction__SyncBackstopVisualToLogonV"...
0x18001df4d  mov     [rbp+170h+var_178], rax
0x18001df51  mov     [rbp+170h+var_170], r13
0x18001df55  mov     [rbp+170h+var_160], r13d
0x18001df59  xorps   xmm0, xmm0
0x18001df5c  movdqa  [rbp+170h+var_C0], xmm0
0x18001df64  xorps   xmm1, xmm1
0x18001df67  xor     eax, eax
0x18001df69  movups  [rbp+170h+var_158], xmm1
0x18001df6d  movups  [rbp+170h+var_148], xmm1
0x18001df71  movups  [rbp+170h+var_138], xmm1
0x18001df75  movups  [rbp+170h+var_128], xmm1
0x18001df79  movups  [rbp+170h+var_118], xmm1
0x18001df7d  movups  [rbp+170h+var_108], xmm1
0x18001df81  movups  [rbp+170h+var_F8], xmm1
0x18001df85  movups  [rbp+170h+var_E8], xmm1
0x18001df8c  movups  [rbp+170h+var_D8], xmm1
0x18001df93  mov     [rbp+170h+var_C8], rax
0x18001df9a  mov     [rbp+170h+var_B0], 1
0x18001dfa4  mov     [rbp+170h+var_A8], rax
0x18001dfab  lea     rax, [rbp+170h+var_1A8]
0x18001dfaf  mov     [rbp+170h+var_A0], rax
0x18001dfb6  mov     [rbp+170h+var_98], r13
0x18001dfbd  xor     r9d, r9d; bool
0x18001dfc0  lea     r8, [rbp+170h+var_180]; struct wil::CallContextInfo *
0x18001dfc4  lea     rdx, [rbp+170h+var_1B0]; struct wil::details::IFailureCallback *
0x18001dfc8  lea     rcx, [rbp+170h+var_90]; this
0x18001dfcf  call    ??0ThreadFailureCallbackHolder@details@wil@@QEAA@PEAUIFailureCallback@12@PEAUCallContextInfo@2@_N@Z; wil::details::ThreadFailureCallbackHolder::ThreadFailureCallbackHolder(wil::details::IFailureCallback *,wil::CallContextInfo *,bool)
0x18001dfd4  nop
0x18001dfd5  lea     rdi, ??_7CLockAction__SyncBackstopVisualToLogonVisual_Activity@LogonControllerTelemetry@@6B@; const LogonControllerTelemetry::CLockAction__SyncBackstopVisualToLogonVisual_Activity::`vftable'
0x18001dfdc  mov     [rbp+170h+var_1B0], rdi
0x18001dfe0  xorps   xmm6, xmm6
0x18001dfe3  movdqa  xmmword ptr [rbp+170h+Data], xmm6
0x18001dfe8  mov     [rsp+270h+hKey], r13
0x18001dfed  mov     rsi, [rsp+270h+hKey]
0x18001dff2  test    rsi, rsi
0x18001dff5  jnz     loc_18001EB5C
0x18001dffb  mov     [rsp+270h+hKey], r13
0x18001e000  lea     rax, [rsp+270h+hKey]
0x18001e005  mov     [rsp+270h+phkResult], rax; phkResult
0x18001e00a  mov     r9d, 20019h; samDesired
0x18001e010  xor     r8d, r8d; ulOptions
0x18001e013  lea     rdx, aSoftwareMicros_23; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18001e01a  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001e021  call    cs:__imp_RegOpenKeyExW
0x18001e027  test    eax, eax
0x18001e029  js      loc_18001E340
0x18001e02f  mov     [rsp+270h+Type], 3
0x18001e037  mov     [rsp+270h+cbData], 10h
0x18001e03f  lea     rax, [rsp+270h+cbData]
0x18001e044  mov     [rsp+270h+lpcbData], rax; bool
0x18001e049  lea     rax, [rbp+170h+Data]
0x18001e04d  mov     [rsp+270h+phkResult], rax; unsigned int
0x18001e052  lea     r9, [rsp+270h+Type]; lpType
0x18001e057  xor     r8d, r8d; lpReserved
0x18001e05a  lea     rdx, aFirstruncorrel; "FirstRunCorrelationID"
0x18001e061  mov     rcx, [rsp+270h+hKey]; hKey
0x18001e066  call    cs:__imp_RegQueryValueExW
0x18001e06c  test    eax, eax
0x18001e06e  jle     short loc_18001E07A
0x18001e070  movzx   eax, ax
0x18001e073  or      eax, 80070000h
0x18001e078  test    eax, eax
0x18001e07a  jns     loc_18001E340
0x18001e080  movaps  xmmword ptr [rbp+170h+Data], xmm6
0x18001e084  mov     rcx, [rsp+270h+hKey]; hKey
0x18001e089  test    rcx, rcx
0x18001e08c  jnz     loc_18001E334
0x18001e092  movdqa  xmmword ptr [rbp+170h+Data], xmm6
0x18001e097  mov     r8d, 10h; Size
0x18001e09d  lea     rdx, GUID_NULL; Buf2
0x18001e0a4  lea     rcx, [rbp+170h+Data]; Buf1
0x18001e0a8  call    memcmp_0
0x18001e0ad  test    eax, eax
0x18001e0af  jz      short loc_18001E0BE
0x18001e0b1  lea     rdx, [rbp+170h+Data]
0x18001e0b5  lea     rcx, [rbp+170h+var_1B0]
0x18001e0b9  call    ?SetRelatedActivityId@?$ActivityBase@VLogonControllerLogger@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXAEBU_GUID@@@Z; wil::ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::SetRelatedActivityId(_GUID const &)
0x18001e0be  lea     rcx, [rbp+170h+var_1B0]; this
0x18001e0c2  call    ?StartActivity@CLockAction__SyncBackstopVisualToLogonVisual_Activity@LogonControllerTelemetry@@QEAAXXZ; LogonControllerTelemetry::CLockAction__SyncBackstopVisualToLogonVisual_Activity::StartActivity(void)
0x18001e0c7  lea     r14, [rbx+168h]
0x18001e0ce  mov     rcx, r14; SRWLock
0x18001e0d1  call    cs:__imp_AcquireSRWLockExclusive
0x18001e0d7  xor     edx, edx; lpWindowName
0x18001e0d9  lea     rcx, ClassName; "LogonUI Logon Window"
0x18001e0e0  call    cs:__imp_FindWindowW
0x18001e0e6  mov     r15, rax
0x18001e0e9  xor     edx, edx; lpWindowName
0x18001e0eb  lea     rcx, aLogonuiWorkerW; "LogonUI worker window"
0x18001e0f2  call    cs:__imp_FindWindowW
0x18001e0f8  mov     r12, rax
0x18001e0fb  test    r15, r15
0x18001e0fe  jz      loc_18001E85D
0x18001e104  test    rax, rax
0x18001e107  jz      loc_18001E85D
0x18001e10d  mov     rcx, [rbx+1B8h]; hThumbnailId
0x18001e114  test    rcx, rcx
0x18001e117  jz      short loc_18001E126
0x18001e119  call    cs:__imp_DwmUnregisterThumbnail
0x18001e11f  mov     [rbx+1B8h], r13
0x18001e126  mov     rcx, rbx; this
0x18001e129  call    ?_CleanupSharedVisual@CLockAction@@AEAAXXZ; CLockAction::_CleanupSharedVisual(void)
0x18001e12e  xor     r9d, r9d; lParam
0x18001e131  xor     r8d, r8d; wParam
0x18001e134  mov     edx, 7Eh ; '~'; Msg
0x18001e139  mov     rcx, r15; hWnd
0x18001e13c  call    cs:__imp_PostMessageW
0x18001e142  mov     qword ptr [rsp+270h+Type], r13
0x18001e147  lea     rcx, [rsp+270h+Type]
0x18001e14c  call    ?InternalRelease@?$ComPtr@UIDCompositionSurface@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(void)
0x18001e151  lea     rdx, [rsp+270h+Type]; struct IDCompositionDesktopDevicePartner **
0x18001e156  mov     rcx, rbx; this
0x18001e159  call    ?_EnsureDevice@CLockAction@@AEAAJPEAPEAUIDCompositionDesktopDevicePartner@@@Z; CLockAction::_EnsureDevice(IDCompositionDesktopDevicePartner * *)
0x18001e15e  mov     edi, eax
0x18001e160  test    eax, eax
0x18001e162  js      loc_18001E893
0x18001e168  mov     [rsp+270h+var_220], r13
0x18001e16d  mov     rcx, qword ptr [rsp+270h+Type]
0x18001e172  mov     rax, [rcx]
0x18001e175  lea     r9, [rsp+270h+var_220]
0x18001e17a  lea     r8, _GUID_eacdd04c_117e_4e17_88f4_d1b12b0e3d89
0x18001e181  mov     rdx, [rbx+178h]
0x18001e188  mov     rax, [rax+0E8h]
0x18001e18f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e194  mov     edi, eax
0x18001e196  test    eax, eax
0x18001e198  js      loc_18001E508
0x18001e19e  mov     qword ptr [rsp+270h+cbData], r13
0x18001e1a3  mov     rsi, qword ptr [rsp+270h+Type]
0x18001e1a8  mov     rax, [rsi]
0x18001e1ab  mov     rdi, [rax+30h]
0x18001e1af  lea     rcx, [rsp+270h+cbData]
0x18001e1b4  call    ?InternalRelease@?$ComPtr@UIDCompositionSurface@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(void)
0x18001e1b9  lea     rdx, [rsp+270h+cbData]
0x18001e1be  mov     rcx, rsi
0x18001e1c1  mov     rax, rdi
0x18001e1c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e1c9  mov     edi, eax
0x18001e1cb  test    eax, eax
0x18001e1cd  js      loc_18001E65F
0x18001e1d3  mov     rcx, [rsp+270h+var_220]
0x18001e1d8  mov     rax, [rcx]
0x18001e1db  mov     rdx, qword ptr [rsp+270h+cbData]
0x18001e1e0  mov     rax, [rax+18h]
0x18001e1e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e1e9  mov     edi, eax
0x18001e1eb  test    eax, eax
0x18001e1ed  js      loc_18001E8EA
0x18001e1f3  mov     [rsp+270h+var_218], r13
0x18001e1f8  cmp     cs:dword_1800D354C, 1
0x18001e1ff  jnz     loc_18001E349
0x18001e205  mov     [rsp+270h+hKey], r13
0x18001e20a  mov     rsi, qword ptr [rsp+270h+Type]
0x18001e20f  mov     rax, [rsi]
0x18001e212  mov     rdi, [rax+30h]
0x18001e216  lea     rcx, [rsp+270h+var_218]
0x18001e21b  call    ?InternalRelease@?$ComPtr@UIDCompositionSurface@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(void)
0x18001e220  lea     rdx, [rsp+270h+var_218]
0x18001e225  mov     rcx, rsi
0x18001e228  mov     rax, rdi
0x18001e22b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e230  mov     edi, eax
0x18001e232  test    eax, eax
0x18001e234  jns     loc_18001EB82
0x18001e23a  mov     rcx, [rbp+178h]; this
0x18001e241  mov     r9d, eax; char *
0x18001e244  lea     r8, aPcshellShellAu_15; "pcshell\\shell\\auth\\authux\\controlle"...
0x18001e24b  mov     edx, 33Fh; void *
0x18001e250  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001e255  mov     rcx, [rsp+270h+hKey]
0x18001e25a  test    rcx, rcx
0x18001e25d  jz      short loc_18001E270
0x18001e25f  mov     [rsp+270h+hKey], r13
0x18001e264  mov     rax, [rcx]
0x18001e267  mov     rax, [rax+10h]
0x18001e26b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e270  mov     rcx, [rsp+270h+var_218]
0x18001e275  test    rcx, rcx
0x18001e278  jz      short loc_18001E28B
0x18001e27a  mov     [rsp+270h+var_218], r13
0x18001e27f  mov     rax, [rcx]
0x18001e282  mov     rax, [rax+10h]
0x18001e286  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e28b  mov     rcx, qword ptr [rsp+270h+cbData]
0x18001e290  test    rcx, rcx
0x18001e293  jz      short loc_18001E2A6
0x18001e295  mov     qword ptr [rsp+270h+cbData], r13
0x18001e29a  mov     rax, [rcx]
0x18001e29d  mov     rax, [rax+10h]
0x18001e2a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e2a6  mov     rcx, [rsp+270h+var_220]
0x18001e2ab  test    rcx, rcx
0x18001e2ae  jz      short loc_18001E2C1
0x18001e2b0  mov     [rsp+270h+var_220], r13
0x18001e2b5  mov     rax, [rcx]
0x18001e2b8  mov     rax, [rax+10h]
0x18001e2bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e2c1  mov     rcx, qword ptr [rsp+270h+Type]
0x18001e2c6  test    rcx, rcx
0x18001e2c9  jz      short loc_18001E2DC
0x18001e2cb  mov     qword ptr [rsp+270h+Type], r13
0x18001e2d0  mov     rax, [rcx]
0x18001e2d3  mov     rax, [rax+10h]
0x18001e2d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e2dc  test    r14, r14
0x18001e2df  jz      short loc_18001E2EA
0x18001e2e1  mov     rcx, r14; SRWLock
0x18001e2e4  call    cs:__imp_ReleaseSRWLockExclusive
0x18001e2ea  lea     rax, ??_7CLockAction__SyncBackstopVisualToLogonVisual_Activity@LogonControllerTelemetry@@6B@; const LogonControllerTelemetry::CLockAction__SyncBackstopVisualToLogonVisual_Activity::`vftable'
0x18001e2f1  mov     [rbp+170h+var_1B0], rax
0x18001e2f5  lea     rcx, [rbp+170h+var_1B0]
0x18001e2f9  call    ?Destroy@?$ActivityBase@VLogonControllerLogger@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x18001e2fe  lea     rcx, [rbp+170h+var_1B0]
0x18001e302  call    ??1?$ActivityBase@VLogonControllerLogger@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x18001e307  mov     eax, edi
0x18001e309  mov     rcx, [rbp+170h+var_60]
0x18001e310  xor     rcx, rsp; StackCookie
0x18001e313  call    __security_check_cookie
0x18001e318  movaps  xmm6, [rsp+270h+var_50]
0x18001e320  add     rsp, 238h
0x18001e327  pop     r15
0x18001e329  pop     r14
0x18001e32b  pop     r13
0x18001e32d  pop     r12
0x18001e32f  pop     rdi
0x18001e330  pop     rsi
0x18001e331  pop     rbx
0x18001e332  pop     rbp
0x18001e333  retn
0x18001e334  call    cs:__imp_RegCloseKey
0x18001e33a  nop
0x18001e33b  jmp     loc_18001E092
0x18001e340  movaps  xmm6, xmmword ptr [rbp+170h+Data]
0x18001e344  jmp     loc_18001E084
0x18001e349  xorps   xmm0, xmm0
0x18001e34c  movdqu  xmmword ptr [rbp+170h+rcDst.left], xmm0
0x18001e351  xorps   xmm1, xmm1
0x18001e354  movdqu  [rbp+170h+var_1CC], xmm1
0x18001e359  mov     qword ptr [rbp+170h+var_1BC], r13
0x18001e35d  mov     [rbp+170h+var_1BC+8], 0
0x18001e361  mov     [rbp+170h+var_1E0], 19h
0x18001e368  mov     qword ptr [rbp+170h+Data], r13
0x18001e36c  xor     ecx, ecx; nIndex
0x18001e36e  call    cs:__imp_GetSystemMetrics
0x18001e374  mov     dword ptr [rbp+170h+Data+8], eax
0x18001e377  mov     ecx, 1; nIndex
0x18001e37c  call    cs:__imp_GetSystemMetrics
0x18001e382  mov     dword ptr [rbp+170h+Data+0Ch], eax
0x18001e385  lea     rdx, [rbp+170h+Data]; lprcSrc
0x18001e389  lea     rcx, [rbp+170h+rcDst]; lprcDst
0x18001e38d  call    cs:__imp_CopyRect
0x18001e393  mov     dword ptr [rbp+170h+var_1BC+1], 1
0x18001e39a  mov     dword ptr [rbp+170h+var_1BC+5], 1
0x18001e3a1  mov     [rsp+270h+var_208], r13
0x18001e3a6  mov     [rsp+270h+hObject], r13
0x18001e3ab  lea     rcx, [rsp+270h+var_208]
0x18001e3b0  call    ?InternalRelease@?$ComPtr@UIDCompositionSurface@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(void)
0x18001e3b5  mov     rax, qword ptr [rsp+270h+Type]
0x18001e3ba  lea     rcx, [rsp+270h+hObject]
0x18001e3bf  mov     [rsp+270h+var_240], rcx
0x18001e3c4  lea     rcx, [rsp+270h+var_208]
0x18001e3c9  mov     [rsp+270h+lpcbData], rcx
0x18001e3ce  mov     [rsp+270h+phkResult], rax; int
0x18001e3d3  lea     r9, [rbp+170h+var_1E0]
0x18001e3d7  xor     r8d, r8d
0x18001e3da  mov     rdx, r15
0x18001e3dd  mov     rcx, r12
0x18001e3e0  call    cs:__imp_DwmpCreateSharedThumbnailVisual
0x18001e3e6  mov     edi, eax
0x18001e3e8  test    eax, eax
0x18001e3ea  js      loc_18001E58B
0x18001e3f0  cmp     cs:dword_1800D354C, 1
0x18001e3f7  jz      loc_18001EC05
0x18001e3fd  mov     rcx, qword ptr [rsp+270h+cbData]
0x18001e402  mov     rax, [rcx]
0x18001e405  xor     r9d, r9d
0x18001e408  mov     r8d, 1
0x18001e40e  mov     rdx, [rsp+270h+var_208]
  ... truncated ...
```
