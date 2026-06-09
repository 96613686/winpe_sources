# RAiLaunchAdminProcess

- ea: `0x18003d070`
- end: `0x18003e121`
- name: `RAiLaunchAdminProcess`
- size: `4273`
- prototype: `__int64 __fastcall(struct _RPC_ASYNC_STATE *, void *, unsigned __int16 *, unsigned __int16 *, UINT32, unsigned int, void *, WCHAR *, __int64, void *, int, void **, unsigned int *)`
- caller_count: `0`
- callee_count: `46`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x180009d10`
- `0x180009d50`
- `0x18000caf0`
- `0x18000f210`
- `0x18000f3e0`
- `0x18000f6d0`
- `0x180010430`
- `0x180010878`
- `0x180010dd4`
- `0x180011414`
- `0x18001158c`
- `0x18001aee4`
- `0x18001b25c`
- `0x18001b408`
- `0x18001b6c0`
- `0x18001b7c0`
- `0x18001b9e4`
- `0x18001d494`
- `0x18001e7bc`
- `0x18001e7c8`
- `0x1800201b0`
- `0x180020204`
- `0x180026630`
- `0x180026f40`
- `0x180028eb8`
- `0x18002ad54`
- `0x18002b0c0`
- `0x18002b244`
- `0x18002d8fc`
- `0x18002ebec`
- `0x180037250`
- `0x180037728`
- `0x18003b2ac`
- `0x18003b320`
- `0x18003b3f0`
- `0x18003bb44`
- `0x18003d070`
- `0x18003e5d4`
- `0x18003ef28`
- `0x18003f14c`
- `0x18003f7ac`
- `0x18003fa00`
- `0x180045fa4`
- `0x1800461e8`
- `0x180046e1a`
- `0x180046e50`

## import_xrefs

- `RPCRT4!RpcImpersonateClient` at `0x18003d58f`
- `RPCRT4!RpcImpersonateClient` at `0x18003d58f`
- `RPCRT4!RpcRevertToSelf` at `0x18003d669`
- `RPCRT4!RpcRevertToSelf` at `0x18003d8d0`
- `RPCRT4!RpcRevertToSelf` at `0x18003da00`
- `RPCRT4!RpcRevertToSelf` at `0x18003da92`
- `RPCRT4!RpcRevertToSelf` at `0x18003dae9`
- `RPCRT4!RpcRevertToSelf` at `0x18003d669`
- `RPCRT4!RpcRevertToSelf` at `0x18003d8d0`
- `RPCRT4!RpcRevertToSelf` at `0x18003da00`
- `RPCRT4!RpcRevertToSelf` at `0x18003da92`
- `RPCRT4!RpcRevertToSelf` at `0x18003dae9`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18003e0a8`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18003e0a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d5e1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d5e1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003dfef`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003dfef`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003e001`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003e013`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003e029`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003e033`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003e03d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003e001`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003e013`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003e029`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003e033`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003e03d`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18003d5cd`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18003d5cd`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x18003d1b6`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x18003d1b6`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18003d1a9`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18003d392`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18003d1a9`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18003d392`
- `api-ms-win-core-kernel32-private-l1-1-0!CheckElevationEnabled` at `0x18003d445`
- `api-ms-win-core-kernel32-private-l1-1-0!CheckElevationEnabled` at `0x18003d445`
- `api-ms-win-core-kernel32-private-l1-1-0!CheckElevation` at `0x18003da29`
- `api-ms-win-core-kernel32-private-l1-1-0!CheckElevation` at `0x18003da29`
- `api-ms-win-appmodel-runtime-l1-1-1!GetPackageFullNameFromToken` at `0x18003dbcc`
- `api-ms-win-appmodel-runtime-l1-1-1!GetPackageFullNameFromToken` at `0x18003dbcc`
- `api-ms-win-appmodel-runtime-l1-1-1!ParseApplicationUserModelId` at `0x18003dc5d`
- `api-ms-win-appmodel-runtime-l1-1-1!ParseApplicationUserModelId` at `0x18003dc5d`
- `api-ms-win-appmodel-runtime-l1-1-1!GetApplicationUserModelIdFromToken` at `0x18003dc1f`
- `api-ms-win-appmodel-runtime-l1-1-1!GetApplicationUserModelIdFromToken` at `0x18003dc1f`
- `api-ms-win-appmodel-runtime-l1-1-0!PackageFamilyNameFromFullName` at `0x18003d745`
- `api-ms-win-appmodel-runtime-l1-1-0!PackageFamilyNameFromFullName` at `0x18003d745`
- `ntdll!NtClose` at `0x18003e04e`
- `ntdll!NtClose` at `0x18003e064`
- `ntdll!NtClose` at `0x18003e073`
- `ntdll!NtClose` at `0x18003e04e`
- `ntdll!NtClose` at `0x18003e064`
- `ntdll!NtClose` at `0x18003e073`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18003d492`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18003d492`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18003ddf0`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18003ddf0`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18003de26`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18003de2e`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18003de26`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18003de2e`
- `USERENV!UnloadUserProfile` at `0x18003dde1`
- `USERENV!UnloadUserProfile` at `0x18003de41`
- `USERENV!UnloadUserProfile` at `0x18003dde1`
- `USERENV!UnloadUserProfile` at `0x18003de41`
- `ext-ms-win-desktopappx-l1-1-6!VerifyFileIsTrustedAndInPackage` at `0x18003dbe4`
- `ext-ms-win-desktopappx-l1-1-6!VerifyFileIsTrustedAndInPackage` at `0x18003dbe4`
- `ext-ms-win-appmodel-activation-l1-1-1!RegisterAppXPackageIfNecessary2` at `0x18003de15`
- `ext-ms-win-appmodel-activation-l1-1-1!RegisterAppXPackageIfNecessary2` at `0x18003de15`
- `ext-ms-win-appmodel-appexecutionalias-l1-1-0!GetAppExecutionAliasApplicationUserModelIdEx` at `0x18003d7c3`
- `ext-ms-win-appmodel-appexecutionalias-l1-1-0!GetAppExecutionAliasApplicationUserModelIdEx` at `0x18003d7c3`
- `ext-ms-win-appmodel-appexecutionalias-l1-1-0!LoadAppExecutionAliasInfoEx` at `0x18003d714`
- `ext-ms-win-appmodel-appexecutionalias-l1-1-0!LoadAppExecutionAliasInfoEx` at `0x18003d714`
- `ext-ms-win-appmodel-appexecutionalias-l1-1-0!CloseAppExecutionAliasEx` at `0x18003d8ec`
- `ext-ms-win-appmodel-appexecutionalias-l1-1-0!CloseAppExecutionAliasEx` at `0x18003d9f1`
- `ext-ms-win-appmodel-appexecutionalias-l1-1-0!CloseAppExecutionAliasEx` at `0x18003d8ec`
- `ext-ms-win-appmodel-appexecutionalias-l1-1-0!CloseAppExecutionAliasEx` at `0x18003d9f1`
- `ext-ms-win-appmodel-appexecutionalias-l1-1-0!OpenAppExecutionAliasForUserEx` at `0x18003d798`
- `ext-ms-win-appmodel-appexecutionalias-l1-1-0!OpenAppExecutionAliasForUserEx` at `0x18003d798`
- `ext-ms-win-appmodel-appexecutionalias-l1-1-0!FreeAppExecutionAliasInfoEx` at `0x18003e082`
- `ext-ms-win-appmodel-appexecutionalias-l1-1-0!FreeAppExecutionAliasInfoEx` at `0x18003e082`
- `ext-ms-win-appmodel-appexecutionalias-l1-1-2!GetAppExecutionAliasPath` at `0x18003d6b4`
- `ext-ms-win-appmodel-appexecutionalias-l1-1-2!GetAppExecutionAliasPath` at `0x18003d6fc`
- `ext-ms-win-appmodel-appexecutionalias-l1-1-2!GetAppExecutionAliasPath` at `0x18003d6b4`
- `ext-ms-win-appmodel-appexecutionalias-l1-1-2!GetAppExecutionAliasPath` at `0x18003d6fc`
- `ext-ms-win-appmodel-appexecutionalias-l1-1-5!LoadAppExecutionAliasInfoEx2` at `0x18003d62c`
- `ext-ms-win-appmodel-appexecutionalias-l1-1-5!LoadAppExecutionAliasInfoEx2` at `0x18003d62c`

## string_xrefs

- `0x18003d200`: `++. hwnd = %x dwClientFlags = %x dwCreationFlags = %x dwTimeout = %x\n	lpDesktop = %ws\n	lpApplicationName = %ws\n	lpCommandLine = %ws\n	lpCurrentDirectory = %ws\n	lpCvStr = %s\n`

## pseudocode

```c
__int64 __fastcall RAiLaunchAdminProcess(
        struct _RPC_ASYNC_STATE *a1,
        void *a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4,
        UINT32 a5,
        unsigned int a6,
        void *a7,
        WCHAR *a8,
        __int64 a9,
        void *a10,
        int a11,
        void **a12,
        unsigned int *a13)
{
  unsigned __int16 *v13; // rbx
  unsigned __int16 *v14; // r13
  unsigned __int16 *v15; // r14
  unsigned int v16; // esi
  const wchar_t *v17; // rax
  const wchar_t *v18; // rdi
  const wchar_t *v19; // r12
  const wchar_t *v20; // r15
  char v21; // di
  void *v22; // rax
  volatile signed __int64 *v23; // rdi
  const wchar_t *v24; // rdx
  const wchar_t *v25; // rcx
  const wchar_t *v26; // rax
  unsigned __int16 *v27; // rdx
  unsigned __int8 v28; // cl
  unsigned int v29; // ebx
  unsigned int v30; // r15d
  unsigned int v31; // r12d
  LONGLONG v32; // rdi
  unsigned __int64 v33; // r15
  unsigned __int64 v34; // r12
  wchar_t *v35; // rax
  NTSTATUS v36; // eax
  RPC_STATUS v37; // eax
  HANDLE v38; // rdi
  __int64 v39; // rdx
  __int16 v40; // di
  unsigned int v41; // eax
  unsigned __int16 *v42; // rdx
  const WCHAR *v43; // rdi
  DWORD LastError; // eax
  char AppExecutionAliasInfoEx2Present; // al
  HANDLE v46; // r15
  __int64 v47; // rbx
  int AppExecutionAliasPath; // eax
  int v49; // ebx
  const unsigned __int16 *v50; // rdi
  __int64 v51; // rcx
  unsigned __int16 v52; // ax
  const unsigned __int16 *v53; // rax
  __int64 v54; // rax
  unsigned __int64 v55; // r15
  unsigned __int16 *v56; // rbx
  __int64 v57; // r8
  void *v58; // rdx
  unsigned __int16 *v59; // rcx
  __int64 v60; // rdx
  __int64 v61; // rcx
  HANDLE v62; // rdi
  unsigned int v63; // eax
  __int64 v64; // rcx
  const unsigned __int16 *v65; // rcx
  const unsigned __int16 *v66; // rcx
  const unsigned __int16 *v67; // rcx
  RPC_STATUS v68; // eax
  unsigned int v69; // eax
  const unsigned __int16 *v70; // rcx
  unsigned int v71; // eax
  wchar_t *v72; // rcx
  HLOCAL v73; // rdx
  WCHAR *v74; // rcx
  unsigned int v75; // r15d
  HANDLE v76; // r12
  RPC_STATUS v77; // eax
  __int64 v78; // rcx
  __int64 v79; // rcx
  int v80; // eax
  void **v81; // rcx
  bool v82; // zf
  void *v83; // rdx
  HANDLE v84; // rax
  unsigned int v85; // r9d
  __int64 v86; // rcx
  bool v88[8]; // [rsp+50h] [rbp-100h]
  unsigned int v89; // [rsp+60h] [rbp-F0h]
  __int16 v90; // [rsp+70h] [rbp-E0h]
  void **v91; // [rsp+98h] [rbp-B8h]
  WCHAR *v92; // [rsp+A0h] [rbp-B0h]
  RPC_STATUS Reply; // [rsp+D0h] [rbp-80h] BYREF
  bool v94; // [rsp+D4h] [rbp-7Ch]
  unsigned __int16 *v95; // [rsp+D8h] [rbp-78h] BYREF
  unsigned int v96; // [rsp+E0h] [rbp-70h] BYREF
  __int64 v97; // [rsp+E8h] [rbp-68h] BYREF
  UINT32 v98[2]; // [rsp+F0h] [rbp-60h] BYREF
  unsigned int v99; // [rsp+F8h] [rbp-58h]
  UINT32 packageRelativeApplicationIdLength; // [rsp+FCh] [rbp-54h] BYREF
  HLOCAL hMem; // [rsp+100h] [rbp-50h] BYREF
  unsigned int v102; // [rsp+108h] [rbp-48h] BYREF
  unsigned int v103; // [rsp+10Ch] [rbp-44h]
  int v104; // [rsp+110h] [rbp-40h] BYREF
  HANDLE hToken; // [rsp+118h] [rbp-38h] BYREF
  UINT32 packageFamilyNameLength; // [rsp+120h] [rbp-30h] BYREF
  int v107; // [rsp+124h] [rbp-2Ch]
  HANDLE token; // [rsp+128h] [rbp-28h] BYREF
  HANDLE hProfile; // [rsp+130h] [rbp-20h] BYREF
  HANDLE hObject; // [rsp+138h] [rbp-18h]
  __int64 v111; // [rsp+140h] [rbp-10h] BYREF
  int v112; // [rsp+148h] [rbp-8h] BYREF
  unsigned int v113; // [rsp+14Ch] [rbp-4h] BYREF
  int v114; // [rsp+150h] [rbp+0h] BYREF
  WCHAR *v115; // [rsp+158h] [rbp+8h]
  unsigned __int16 *v116; // [rsp+160h] [rbp+10h] BYREF
  int v117; // [rsp+168h] [rbp+18h] BYREF
  UINT32 packageFullNameLength[2]; // [rsp+170h] [rbp+20h] BYREF
  HANDLE Handle; // [rsp+178h] [rbp+28h] BYREF
  UINT32 applicationUserModelIdLength[2]; // [rsp+180h] [rbp+30h] BYREF
  void **v121; // [rsp+188h] [rbp+38h]
  __int64 v122; // [rsp+190h] [rbp+40h]
  HLOCAL v123; // [rsp+198h] [rbp+48h] BYREF
  unsigned __int16 *v124; // [rsp+1A0h] [rbp+50h] BYREF
  LUATelemetry *v125; // [rsp+1A8h] [rbp+58h]
  HLOCAL v126; // [rsp+1B0h] [rbp+60h] BYREF
  void *v127; // [rsp+1B8h] [rbp+68h]
  LARGE_INTEGER v128; // [rsp+1C0h] [rbp+70h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+1C8h] [rbp+78h] BYREF
  LARGE_INTEGER Frequency; // [rsp+1D0h] [rbp+80h] BYREF
  unsigned int *v131; // [rsp+1D8h] [rbp+88h]
  PRPC_ASYNC_STATE pAsync; // [rsp+1E0h] [rbp+90h]
  unsigned __int16 *v133; // [rsp+1E8h] [rbp+98h]
  unsigned __int16 *v134; // [rsp+1F0h] [rbp+A0h]
  HLOCAL v135; // [rsp+1F8h] [rbp+A8h]
  UINT32 *v136; // [rsp+200h] [rbp+B0h] BYREF
  __int64 v137; // [rsp+208h] [rbp+B8h] BYREF
  char v138; // [rsp+210h] [rbp+C0h]
  char v139[80]; // [rsp+220h] [rbp+D0h] BYREF
  char v140[144]; // [rsp+270h] [rbp+120h] BYREF
  WCHAR packageFamilyName[72]; // [rsp+300h] [rbp+1B0h] BYREF
  WCHAR applicationUserModelId[136]; // [rsp+390h] [rbp+240h] BYREF
  WCHAR packageRelativeApplicationId[136]; // [rsp+4A0h] [rbp+350h] BYREF
  WCHAR packageFullName[128]; // [rsp+5B0h] [rbp+460h] BYREF

  v13 = 0;
  v115 = a8;
  v14 = a4;
  v15 = a3;
  packageRelativeApplicationIdLength = a5;
  v16 = 0;
  v103 = a6;
  v122 = a9;
  hProfile = a10;
  v107 = a11;
  v121 = a12;
  pAsync = a1;
  v131 = a13;
  v127 = a2;
  hMem = a7;
  *(_QWORD *)applicationUserModelIdLength = a3;
  *(_QWORD *)packageFullNameLength = a4;
  *(_QWORD *)v98 = a7;
  Reply = 0;
  v102 = 0;
  v96 = 0;
  LODWORD(v95) = 0;
  v112 = 0;
  v117 = 1;
  v133 = a3;
  v134 = a4;
  v135 = a7;
  v126 = 0;
  hToken = 0;
  Handle = 0;
  token = 0;
  hObject = (HANDLE)-1LL;
  v99 = 6;
  v123 = 0;
  packageFamilyNameLength = 0;
  v94 = 0;
  v111 = 0;
  v114 = 0;
  v113 = 0;
  v104 = 0;
  Frequency.QuadPart = 0;
  PerformanceCount.QuadPart = 0;
  v128.QuadPart = 0;
  v116 = 0;
  v124 = 0;
  QueryPerformanceCounter(&PerformanceCount);
  QueryPerformanceFrequency(&Frequency);
  memset_0(v140, 0, 0x81u);
  v17 = L"NULL";
  v18 = (const wchar_t *)a7;
  v125 = (LUATelemetry *)L"NULL";
  if ( !a7 )
    v18 = L"NULL";
  v19 = v14;
  if ( !v14 )
    v19 = L"NULL";
  if ( v15 )
    v17 = AipJustFileName(v15);
  v20 = v115;
  if ( !v115 )
    v20 = L"NULL";
  *(_QWORD *)v88 = v18;
  v21 = packageRelativeApplicationIdLength;
  LUATelemetry::WatchCurrentThread(
    v139,
    "RAiLaunchAdminProcess",
    "++. hwnd = %x dwClientFlags = %x dwCreationFlags = %x dwTimeout = %x\n"
    "\tlpDesktop = %ws\n"
    "\tlpApplicationName = %ws\n"
    "\tlpCommandLine = %ws\n"
    "\tlpCurrentDirectory = %ws\n"
    "\tlpCvStr = %s\n",
    (unsigned int)hProfile,
    packageRelativeApplicationIdLength,
    v103,
    v107,
    v20,
    v17,
    v19,
    *(_QWORD *)v88,
    v140);
  if ( g_pLaunchAdminProcessActivityTelemetryRateLimiter
    && (unsigned int)RateLimiter::RequestPermission(g_pLaunchAdminProcessActivityTelemetryRateLimiter) )
  {
    v22 = operator new(0x90u);
    if ( v22 )
      v23 = (volatile signed __int64 *)TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(v22);
    else
      v23 = 0;
    TraceLoggingCorrelationVector::ToStringImpl(
      (TraceLoggingCorrelationVector *)v23,
      _InterlockedExchangeAdd64(v23 + 17, 0),
      v140);
    if ( v23 )
      operator delete((void *)v23);
    v21 = packageRelativeApplicationIdLength;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v24 = L"NULL";
    v25 = L"NULL";
    if ( hMem )
      v24 = (const wchar_t *)hMem;
    v26 = L"NULL";
    if ( v14 )
      v25 = v14;
    if ( v15 )
      v26 = v15;
    WPP_SF_DDDDSSSSs(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      (_DWORD)v24,
      (_DWORD)WPP_GLOBAL_Control,
      (_DWORD)hProfile,
      v21,
      v103,
      v107,
      (__int64)v20,
      (__int64)v26,
      (__int64)v25,
      (__int64)v24,
      (__int64)v140);
  }
  v27 = v15;
  if ( !v15 )
    v27 = v14;
  wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
    &v97,
    v27,
    -1);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
    &v116,
    &v97);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v97);
  if ( !v15 && !v14 )
  {
    v125 = 0;
LABEL_31:
    Reply = 87;
    goto LABEL_32;
  }
  v33 = 0;
  v34 = 0;
  if ( v15 )
  {
    v35 = (wchar_t *)AipJustFileName(v15);
    v125 = (LUATelemetry *)v35;
  }
  else
  {
    v35 = L"NULL";
  }
  LODWORD(v97) = AiLogPerfTrackEventEx(&AppInfo_PerfTrack_Elevation_EXE_Start, v35);
  if ( v15 )
  {
    v33 = -1;
    do
      ++v33;
    while ( v15[v33] );
  }
  if ( v14 )
  {
    v34 = -1;
    do
      ++v34;
    while ( v14[v34] );
  }
  if ( v33 > 0x7FFF || v34 > 0x7FFF )
    goto LABEL_31;
  Reply = CheckElevationEnabled(&v117);
  if ( !Reply )
  {
    Reply = AiGetClientInformation(v127, &Handle, &token, &v96, &packageFamilyNameLength);
    if ( !Reply )
    {
      v36 = LUAGetUACPromptPolicy(&v104, &v113);
      if ( v36 < 0
        || (v104 = 0, v38 = token, v36 = AiCheckForElevatedUser(token, &v104), v36 < 0)
        || (v36 = AiCheckForAdminUser(v38, v104, &v114), v40 = 0, v36 < 0) )
      {
        v37 = RtlNtStatusToDosErrorNoTeb(v36);
      }
      else
      {
        if ( (packageRelativeApplicationIdLength & 8) != 0 )
        {
          v41 = AiConvertWow64Paths(
                  v15,
                  (const unsigned __int16 **)applicationUserModelIdLength,
                  v14,
                  (unsigned __int16 **)packageFullNameLength,
                  (const unsigned __int16 *)hMem,
                  (const unsigned __int16 **)v98);
          v15 = *(unsigned __int16 **)applicationUserModelIdLength;
          Reply = v41;
          if ( v41 )
          {
            v14 = *(unsigned __int16 **)packageFullNameLength;
            hMem = *(HLOCAL *)v98;
            goto LABEL_32;
          }
          if ( *(_QWORD *)applicationUserModelIdLength )
          {
            v33 = -1;
            do
              ++v33;
            while ( *(_WORD *)(*(_QWORD *)applicationUserModelIdLength + 2 * v33) );
          }
          v14 = *(unsigned __int16 **)packageFullNameLength;
          if ( *(_QWORD *)packageFullNameLength )
          {
            v34 = -1;
            do
              ++v34;
            while ( *(_WORD *)(*(_QWORD *)packageFullNameLength + 2 * v34) );
          }
          if ( v33 > 0x7FFF || v34 > 0x7FFF )
          {
            hMem = *(HLOCAL *)v98;
            goto LABEL_31;
          }
          if ( *(_QWORD *)applicationUserModelIdLength )
            v42 = *(unsigned __int16 **)applicationUserModelIdLength;
          else
            v42 = *(unsigned __int16 **)packageFullNameLength;
          wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
            &hMem,
            v42,
            -1);
          wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
            &v116,
            &hMem);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&hMem);
          hMem = *(HLOCAL *)v98;
        }
        if ( !v117 )
        {
          v75 = v96;
          v76 = token;
          goto LABEL_192;
        }
        v37 = RpcImpersonateClient(0);
        if ( !v37 )
        {
          v43 = v14;
          if ( v15 )
            v43 = v15;
          hObject = CreateFileW(v43, 0xA0000000, 5u, 0, 3u, 0x80u, 0);
          if ( hObject == (HANDLE)-1LL )
          {
            LastError = GetLastError();
            Reply = LastError;
            if ( LastError != 1920 && LastError != 5 || !(unsigned __int8)IsLoadAppExecutionAliasInfoExPresent() )
              goto LABEL_116;
            v97 = 0;
            AppExecutionAliasInfoEx2Present = IsLoadAppExecutionAliasInfoEx2Present();
            v46 = token;
            if ( AppExecutionAliasInfoEx2Present && (int)LoadAppExecutionAliasInfoEx2(v43, token, 0, &v111) >= 0 )
            {
              wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
                v98,
                v43,
                -1);
              wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
                &v97,
                v98);
              wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(v98);
              v47 = v97;
              if ( !v97 )
              {
LABEL_76:
                RpcRevertToSelf();
LABEL_77:
                wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v97);
                goto LABEL_32;
              }
            }
            else
            {
              v96 = 0;
              AppExecutionAliasPath = GetAppExecutionAliasPath(v43, v46, 0, &v96);
              if ( WIN32_FROM_HRESULT(AppExecutionAliasPath) != 122 )
                goto LABEL_76;
              wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
                v98,
                0,
                v96);
              wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
                &v97,
                v98);
              wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(v98);
              v47 = v97;
              if ( (int)GetAppExecutionAliasPath(v43, v46, v97, &v96) < 0 )
                goto LABEL_76;
              if ( (int)LoadAppExecutionAliasInfoEx(v47, v46, &v111) < 0 )
                goto LABEL_115;
            }
            if ( !*(_DWORD *)(v111 + 32) )
            {
              packageFamilyNameLength = 65;
              if ( !PackageFamilyNameFromFullName(*(PCWSTR *)v111, &packageFamilyNameLength, packageFamilyName) )
              {
                memset_0(packageRelativeApplicationId, 0, 0x106u);
                v96 = 131;
                v136 = v98;
                *(_QWORD *)v98 = 0;
                v137 = 0;
                v138 = 1;
                v49 = OpenAppExecutionAliasForUserEx(v47, v46, &v137);
                wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CloseAppExecutionAliasEx(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CloseAppExecutionAliasEx(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(&v136);
                if ( v49 >= 0
                  && (int)GetAppExecutionAliasApplicationUserModelIdEx(
                            *(_QWORD *)v98,
                            packageRelativeApplicationId,
                            &v96) >= 0 )
                {
                  v50 = v14;
                  LODWORD(v51) = 0;
                  if ( v14 )
                  {
                    v52 = *v14;
                    if ( *v14 == 34 )
                    {
                      do
                        ++v50;
                      while ( *v50 != 34 && *v50 );
                      v53 = v50 + 1;
                      if ( *v50 != 34 )
                        v53 = v50;
                      v50 = v53;
                    }
                    else
                    {
                      while ( v52 != 32 && v52 )
                        v52 = *++v50;
                    }
                    v51 = -1;
                    do
                      ++v51;
                    while ( v50[v51] );
                  }
                  v54 = -1;
                  do
                    ++v54;
                  while ( *(_WORD *)(*(_QWORD *)(v111 + 8) + 2 * v54) );
                  v55 = 2 * ((int)v51 + (int)v54) + 6;
                  wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
                    &v95,
                    0,
                    v55);
                  v56 = v95;
                  if ( v95
                    && StringCbCopyW(v95, v55, L"\"") >= 0
                    && StringCbCatW(v56, v55, *(const unsigned __int16 **)(v111 + 8)) >= 0
                    && StringCbCatW(v56, v55, L"\"") >= 0 )
                  {
                    if ( !v50 || StringCbCatW(v56, v55, v50) >= 0 )
                    {
                      v57 = v111;
                      v58 = v127;
                      *v131 = v99;
                      AipLaunchProcessWithIdentityHelper(
                        pAsync,
                        v58,
                        *(_QWORD *)(v57 + 8),
                        v56,
                        packageRelativeApplicationIdLength | 0x200,
                        v103,
                        hMem,
                        v115,
                        v122);
                      v94 = 1;
                    }
                    RpcRevertToSelf();
                    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v95);
                    if ( *(_QWORD *)v98 )
                      CloseAppExecutionAliasEx();
                    goto LABEL_77;
                  }
                  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v95);
                }
                if ( *(_QWORD *)v98 )
                  CloseAppExecutionAliasEx();
              }
            }
LABEL_115:
            wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v97);
LABEL_116:
            RpcRevertToSelf();
            goto LABEL_32;
          }
          v59 = v14;
          if ( v15 )
            v59 = v15;
          Reply = CheckElevation(v59, &v112, 0, &v102);
          if ( Reply )
            goto LABEL_116;
          if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShadowAdmin>::__private_IsEnabled(
                                  `wil::Feature<__WilFeatureTraits_Feature_ShadowAdmin>::GetImpl'::`2'::impl,
                                  v60)
            && (unsigned int)LUAIsShadowAdminEnabled(v61) )
          {
            wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
              &v124,
              0);
            v62 = hObject;
            v63 = AiCheckSecureApplicationDirectoryEx(hObject, (unsigned int *)&v95, &v124);
            v13 = v124;
          }
          else
          {
            v65 = v14;
            if ( v15 )
              v65 = v15;
            v63 = AiCheckSecureApplicationDirectory(v65, (unsigned int *)&v95);
            v62 = hObject;
          }
          Reply = v63;
          if ( v63 )
          {
            RpcRevertToSelf();
LABEL_128:
            v16 = (unsigned int)v95;
            goto LABEL_32;
          }
          if ( v102 - 16 <= 2 && (unsigned int)LUAIsShadowAdminEnabled(v64) )
          {
            v66 = v14;
            if ( v15 )
              v66 = v15;
            AipCheckAssistiveTechnologyList(v66, (unsigned int *)&v95);
          }
          v67 = v14;
          if ( v15 )
            v67 = v15;
          AiIsEXESafeToAutoApprove(v67, v62, v14, (unsigned int *)&v95, (unsigned __int16 **)&v126);
          v68 = RpcRevertToSelf();
          if ( v68 )
          {
            Reply = v68;
            goto LABEL_128;
          }
          v16 = (unsigned int)v95;
          if ( (v112 & 8) != 0 )
          {
            v16 = (unsigned int)v95 | 0x1000;
            LODWORD(v95) = (unsigned int)v95 | 0x1000;
          }
          if ( (v112 & 4) != 0 )
          {
            v16 |= 2u;
            LODWORD(v95) = v16;
          }
          v69 = v102;
          if ( v102 - 16 <= 2 )
          {
            if ( v102 >= 3 )
            {
              v69 = v102 - 16;
              v102 -= 16;
            }
            v16 |= 0x8000Cu;
            LODWORD(v95) = v16;
          }
          if ( v69 || (v16 & 4) == 0 )
          {
            if ( !(unsigned int)AiIsElevationAllowedForSession(v96) )
            {
              Reply = 50;
              goto LABEL_32;
            }
            v69 = v102;
          }
          if ( (packageRelativeApplicationIdLength & 1) != 0 )
          {
            if ( v69 <= 1 )
            {
              v16 |= 0x200u;
              LODWORD(v95) = v16;
            }
            v102 = 2;
            v99 = 6;
          }
          if ( (packageRelativeApplicationIdLength & 0x10) != 0 )
          {
            v16 |= 0x800u;
            LODWORD(v95) = v16;
          }
          if ( (packageRelativeApplicationIdLength & 0x80u) != 0 )
          {
            v16 |= 0x100000u;
            LODWORD(v95) = v16;
          }
          if ( (packageRelativeApplicationIdLength & 0x100) != 0 )
          {
            v40 = 8;
          }
          else
          {
            v40 = 0;
            if ( (packageRelativeApplicationIdLength & 0x800) != 0 )
              v40 = 1024;
          }
          v104 = 0;
          packageFullNameLength[0] = 128;
          if ( !GetPackageFullNameFromToken(token, packageFullNameLength, packageFullName) )
            VerifyFileIsTrustedAndInPackage(v15, packageFullName, &v104);
          memset_0(applicationUserModelId, 0, 0x106u);
          applicationUserModelIdLength[0] = 131;
          if ( v104 )
          {
            if ( GetApplicationUserModelIdFromToken(token, applicationUserModelIdLength, applicationUserModelId) )
              goto LABEL_32;
            v98[0] = 65;
            packageRelativeApplicationIdLength = 65;
            if ( ParseApplicationUserModelId(
                   applicationUserModelId,
                   v98,
                   packageFamilyName,
                   &packageRelativeApplicationIdLength,
                   packageRelativeApplicationId) < 0 )
              goto LABEL_32;
            v99 = 8;
            v70 = v14;
            if ( v15 )
              v70 = v15;
            v71 = AiBuildPackagedAppParams(
                    v70,
                    v33,
                    v14,
                    v34,
                    packageFamilyNameLength,
                    packageFamilyName,
                    applicationUserModelId,
                    (struct _CONSENTUI_PARAM_HEADER **)&v123);
          }
          else
          {
            v72 = v14;
            if ( v15 )
              v72 = v15;
            v71 = AiBuildEXEParams(
                    v72,
                    hObject,
                    v15,
                    v33,
                    v14,
                    v34,
                    (const unsigned __int16 *)v126,
                    packageFamilyNameLength,
                    (struct _CONSENTUI_PARAM_HEADER **)&v123);
          }
          Reply = v71;
          if ( v71 )
            goto LABEL_32;
          v73 = v123;
          v74 = v115;
          v75 = v96;
          v76 = token;
          *((_DWORD *)v123 + 13) = v97;
          v77 = AiCheckLUA(v102, &v95, v99, v76, v73, v74, hProfile, v75, v107, v140, &hToken);
          v16 = (unsigned int)v95;
          Reply = v77;
          if ( v77 )
            goto LABEL_32;
          if ( hToken )
          {
            v16 = (unsigned int)v95 | 1;
            if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShadowAdmin>::__private_IsEnabled(
                                    `wil::Feature<__WilFeatureTraits_Feature_ShadowAdmin>::GetImpl'::`2'::impl,
                                    v39) )
            {
              v103 &= 0xFFFFFFFC;
              if ( v99 == 8
                && ((v16 & 0x20) == 0 || (v16 & 0x8000000) != 0 && (unsigned int)LUAIsShadowAdminEnabled(v78)) )
              {
                hProfile = 0;
                Reply = AipLoadUserProfile(hToken, &hProfile);
                if ( Reply )
                  goto LABEL_183;
                ImpersonateLoggedOnUser(hToken);
                LODWORD(v97) = 0;
                if ( (int)RegisterAppXPackageIfNecessary2(0, applicationUserModelId, 0, 0) < 0 )
                {
                  Reply = 15669;
                  RevertToSelf();
LABEL_183:
                  if ( hProfile )
                    UnloadUserProfile(hToken, hProfile);
                  goto LABEL_32;
                }
                RevertToSelf();
                if ( hProfile )
                  UnloadUserProfile(hToken, hProfile);
              }
            }
            Reply = AipApplyAdminProcessPackageClaimsPolicy(&hToken, v76, v16);
            if ( Reply )
              goto LABEL_32;
          }
LABEL_192:
          if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShadowAdmin>::__private_IsEnabled(
                                  `wil::Feature<__WilFeatureTraits_Feature_ShadowAdmin>::GetImpl'::`2'::impl,
                                  v39) )
          {
            v80 = LUAIsShadowAdminEnabled(v79);
            v81 = v121;
            v82 = v80 == 0;
            v83 = v76;
            v84 = hToken;
            v85 = v16;
            if ( !v82 )
            {
              v92 = v13;
              v91 = v121;
              v90 = v40;
              v89 = v75;
LABEL_197:
              if ( v84 )
                v83 = v84;
              v37 = AiLaunchProcess(
                      Handle,
                      v83,
                      hObject,
                      v85,
                      v15,
                      v14,
                      v103,
                      (const WCHAR *)hMem,
                      v115,
                      v122,
                      0,
                      0,
                      v89,
                      0,
                      v90,
                      0,
                      0,
                      0,
                      0,
                      v91,
                      v92);
              goto LABEL_49;
            }
          }
          else
          {
            v84 = hToken;
            v83 = v76;
            v81 = v121;
            v85 = v16;
          }
          v92 = 0;
          v91 = v81;
          v90 = v40;
          v89 = v75;
          goto LABEL_197;
        }
      }
LABEL_49:
      Reply = v37;
    }
  }
LABEL_32:
  QueryPerformanceCounter(&v128);
  v29 = Reply;
  v30 = v113;
  v31 = v99;
  v32 = 1000 * (v128.QuadPart - PerformanceCount.QuadPart) / Frequency.QuadPart;
  if ( Reply == 1223 )
  {
    v29 = 0;
  }
  else if ( Reply > 0 )
  {
    v29 = (unsigned __int16)Reply | 0x80070000;
  }
  if ( LUATelemetry::IsEnabled(v28, 1000 * (v128.QuadPart - PerformanceCount.QuadPart) % Frequency.QuadPart) )
  {
    wil::details::static_lazy<LUATelemetry>::get(v86, _lambda_8fd1dd6eff698f29c42c633fb94303b5_::_lambda_invoker_cdecl_);
    LUATelemetry::LaunchAdminProcess_(
      v125,
      v29,
      v16,
      v31,
      Reply,
      (const unsigned __int16 *)v125,
      v116,
      v114,
      v30,
      v32,
      v94,
      v140);
  }
  if ( hObject != (HANDLE)-1LL )
    CloseHandle(hObject);
  if ( v15 != v133 )
    LocalFree(v15);
  if ( v14 != v134 )
    LocalFree(v14);
  if ( hMem != v135 )
    LocalFree(hMem);
  LocalFree(v123);
  LocalFree(v126);
  if ( hToken )
  {
    NtClose(hToken);
    hToken = 0;
  }
  if ( token )
    NtClose(token);
  if ( Handle )
    NtClose(Handle);
  if ( v111 )
  {
    FreeAppExecutionAliasInfoEx(v111);
    v111 = 0;
  }
  if ( !v94 )
  {
    *v131 = v99;
    RpcAsyncCompleteCall(pAsync, &Reply);
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_D(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      12,
      WPP_b23fa736e9853481a42645a0499c03f5_Traceguids,
      (unsigned int)Reply);
  wil::ActivityThreadWatcher::~ActivityThreadWatcher((wil::ActivityThreadWatcher *)v139);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v124);
  return wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v116);
}

```

## disassembly

```asm
0x18003d070  push    rbp
0x18003d072  push    rbx
0x18003d073  push    rsi
0x18003d074  push    rdi
0x18003d075  push    r12
0x18003d077  push    r13
0x18003d079  push    r14
0x18003d07b  push    r15
0x18003d07d  lea     rbp, [rsp-578h]
0x18003d085  sub     rsp, 6C8h
0x18003d08c  mov     rax, cs:__security_cookie
0x18003d093  xor     rax, rsp
0x18003d096  mov     [rbp+5B0h+var_50], rax
0x18003d09d  mov     rax, [rbp+5B0h+arg_38]
0x18003d0a4  xor     r12d, r12d
0x18003d0a7  mov     r15, [rbp+5B0h+arg_30]
0x18003d0ae  mov     ebx, r12d
0x18003d0b1  mov     [rbp+5B0h+var_5A8], rax
0x18003d0b5  mov     r13, r9
0x18003d0b8  mov     eax, [rbp+5B0h+arg_20]
0x18003d0be  mov     r14, r8
0x18003d0c1  mov     [rbp+5B0h+packageRelativeApplicationIdLength], eax
0x18003d0c4  mov     esi, r12d
0x18003d0c7  mov     eax, [rbp+5B0h+arg_28]
0x18003d0cd  mov     [rbp+5B0h+var_5F4], eax
0x18003d0d0  mov     rax, [rbp+5B0h+arg_40]
0x18003d0d7  mov     [rbp+5B0h+var_570], rax
0x18003d0db  mov     rax, [rbp+5B0h+arg_48]
0x18003d0e2  mov     [rbp+5B0h+hProfile], rax
0x18003d0e6  mov     eax, [rbp+5B0h+arg_50]
0x18003d0ec  mov     [rbp+5B0h+var_5DC], eax
0x18003d0ef  mov     rax, [rbp+5B0h+arg_58]
0x18003d0f6  mov     [rbp+5B0h+var_578], rax
0x18003d0fa  mov     rax, [rbp+5B0h+arg_60]
0x18003d101  mov     [rbp+5B0h+pAsync], rcx
0x18003d108  lea     rcx, [rbp+5B0h+PerformanceCount]; lpPerformanceCount
0x18003d10c  mov     [rbp+5B0h+var_528], rax
0x18003d113  mov     [rbp+5B0h+var_548], rdx
0x18003d117  mov     [rbp+5B0h+hMem], r15
0x18003d11b  mov     qword ptr [rbp+5B0h+applicationUserModelIdLength], r8
0x18003d11f  mov     qword ptr [rbp+5B0h+packageFullNameLength], r9
0x18003d123  mov     qword ptr [rbp+5B0h+var_610], r15
0x18003d127  mov     [rbp+5B0h+Reply], r12d
0x18003d12b  mov     [rbp+5B0h+var_5F8], r12d
0x18003d12f  mov     [rbp+5B0h+var_620], r12d
0x18003d133  mov     dword ptr [rbp+5B0h+var_628], r12d
0x18003d137  mov     [rbp+5B0h+var_5B8], r12d
0x18003d13b  mov     [rbp+5B0h+var_598], 1
0x18003d142  mov     [rbp+5B0h+var_518], r8
0x18003d149  mov     [rbp+5B0h+var_510], r9
0x18003d150  mov     [rbp+5B0h+var_508], r15
0x18003d157  mov     [rbp+5B0h+var_550], r12
0x18003d15b  mov     [rbp+5B0h+hToken], r12
0x18003d15f  mov     [rbp+5B0h+Handle], r12
0x18003d163  mov     [rbp+5B0h+token], r12
0x18003d167  mov     [rbp+5B0h+hObject], 0FFFFFFFFFFFFFFFFh
0x18003d16f  mov     [rbp+5B0h+var_608], 6
0x18003d176  mov     [rbp+5B0h+var_568], r12
0x18003d17a  mov     [rbp+5B0h+packageFamilyNameLength], r12d
0x18003d17e  mov     [rbp+5B0h+var_62C], r12b
0x18003d182  mov     [rbp+5B0h+var_5C0], r12
0x18003d186  mov     [rbp+5B0h+var_5B0], r12d
0x18003d18a  mov     [rbp+5B0h+var_5B4], r12d
0x18003d18e  mov     [rbp+5B0h+var_5F0], r12d
0x18003d192  mov     qword ptr [rbp+5B0h+Frequency], r12
0x18003d199  mov     qword ptr [rbp+5B0h+PerformanceCount], r12
0x18003d19d  mov     qword ptr [rbp+5B0h+var_540], r12
0x18003d1a1  mov     [rbp+5B0h+var_5A0], r12
0x18003d1a5  mov     [rbp+5B0h+var_560], rbx
0x18003d1a9  call    cs:__imp_QueryPerformanceCounter
0x18003d1af  lea     rcx, [rbp+5B0h+Frequency]; lpFrequency
0x18003d1b6  call    cs:__imp_QueryPerformanceFrequency
0x18003d1bc  xor     edx, edx; Val
0x18003d1be  lea     rcx, [rbp+5B0h+var_490]; void *
0x18003d1c5  mov     r8d, 81h; Size
0x18003d1cb  call    memset_0
0x18003d1d0  test    r15, r15
0x18003d1d3  lea     rax, aNull_0; "NULL"
0x18003d1da  mov     rdi, r15
0x18003d1dd  mov     [rbp+5B0h+var_558], rax
0x18003d1e1  cmovz   rdi, rax
0x18003d1e5  mov     r12, r13
0x18003d1e8  test    r13, r13
0x18003d1eb  cmovz   r12, rax
0x18003d1ef  test    r14, r14
0x18003d1f2  jz      short loc_18003D1FC
0x18003d1f4  mov     rcx, r14; unsigned __int16 *
0x18003d1f7  call    ?AipJustFileName@@YAPEBGPEBG@Z; AipJustFileName(ushort const *)
0x18003d1fc  mov     rcx, [rbp+5B0h+var_5A8]
0x18003d200  lea     r8, aHwndXDwclientf; "++. hwnd = %x dwClientFlags = %x dwCrea"...
0x18003d207  mov     r9d, dword ptr [rbp+5B0h+hProfile]
0x18003d20b  lea     rdx, aRailaunchadmin; "RAiLaunchAdminProcess"
0x18003d212  mov     r15, rcx
0x18003d215  test    rcx, rcx
0x18003d218  lea     rcx, aNull_0; "NULL"
0x18003d21f  cmovz   r15, rcx
0x18003d223  lea     rcx, [rbp+5B0h+var_490]
0x18003d22a  mov     [rsp+700h+var_6A8], rcx
0x18003d22f  lea     rcx, [rbp+5B0h+var_4E0]
0x18003d236  mov     qword ptr [rsp+700h+var_6B0], rdi
0x18003d23b  mov     edi, [rbp+5B0h+packageRelativeApplicationIdLength]
0x18003d23e  mov     [rsp+700h+var_6B8], r12
0x18003d243  mov     r12d, [rbp+5B0h+var_5F4]
0x18003d247  mov     [rsp+700h+var_6C0], rax
0x18003d24c  mov     eax, [rbp+5B0h+var_5DC]
0x18003d24f  mov     [rsp+700h+var_6C8], r15
0x18003d254  mov     dword ptr [rsp+700h+hTemplateFile], eax
0x18003d258  mov     [rsp+700h+dwFlagsAndAttributes], r12d
0x18003d25d  mov     [rsp+700h+dwCreationDisposition], edi
0x18003d261  call    ?WatchCurrentThread@LUATelemetry@@SA?AVActivityThreadWatcher@wil@@PEBD0ZZ; LUATelemetry::WatchCurrentThread(char const *,char const *,...)
0x18003d266  mov     rcx, cs:?g_pLaunchAdminProcessActivityTelemetryRateLimiter@@3V?$unique_ptr@VRateLimiter@@U?$default_delete@VRateLimiter@@@wistd@@@wistd@@A; this
0x18003d26d  test    rcx, rcx
0x18003d270  jz      short loc_18003D2C9
0x18003d272  call    ?RequestPermission@RateLimiter@@QEAAHXZ; RateLimiter::RequestPermission(void)
0x18003d277  test    eax, eax
0x18003d279  jz      short loc_18003D2C9
0x18003d27b  mov     ecx, 90h; Size
0x18003d280  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003d285  xor     ecx, ecx
0x18003d287  test    rax, rax
0x18003d28a  jz      short loc_18003D29B
0x18003d28c  mov     rcx, rax
0x18003d28f  call    ??0TraceLoggingCorrelationVector@@QEAA@UTraceLoggingCorrelationVectorV2_t@@@Z; TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(TraceLoggingCorrelationVectorV2_t)
0x18003d294  mov     rdi, rax
0x18003d297  xor     ecx, ecx
0x18003d299  jmp     short loc_18003D29E
0x18003d29b  mov     rdi, rcx
0x18003d29e  mov     rdx, rcx
0x18003d2a1  lock xadd [rdi+88h], rdx; unsigned __int64
0x18003d2aa  lea     r8, [rbp+5B0h+var_490]; char *
0x18003d2b1  mov     rcx, rdi; this
0x18003d2b4  call    ?ToStringImpl@TraceLoggingCorrelationVector@@AEAA_N_KPEAD@Z; TraceLoggingCorrelationVector::ToStringImpl(unsigned __int64,char *)
0x18003d2b9  test    rdi, rdi
0x18003d2bc  jz      short loc_18003D2C6
0x18003d2be  mov     rcx, rdi; Block
0x18003d2c1  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18003d2c6  mov     edi, [rbp+5B0h+packageRelativeApplicationIdLength]
0x18003d2c9  mov     r8, cs:WPP_GLOBAL_Control
0x18003d2d0  lea     rax, WPP_GLOBAL_Control
0x18003d2d7  cmp     r8, rax
0x18003d2da  jz      short loc_18003D349
0x18003d2dc  test    byte ptr [r8+1Ch], 1
0x18003d2e1  jz      short loc_18003D349
0x18003d2e3  mov     rax, [rbp+5B0h+hMem]
0x18003d2e7  lea     r9, aNull_0; "NULL"
0x18003d2ee  test    rax, rax
0x18003d2f1  mov     rdx, r9
0x18003d2f4  mov     rcx, r9
0x18003d2f7  cmovnz  rdx, rax
0x18003d2fb  mov     rax, r9
0x18003d2fe  test    r13, r13
0x18003d301  lea     r9, [rbp+5B0h+var_490]
0x18003d308  mov     [rsp+700h+var_6A8], r9
0x18003d30d  mov     r9d, dword ptr [rbp+5B0h+hProfile]
0x18003d311  cmovnz  rcx, r13
0x18003d315  mov     qword ptr [rsp+700h+var_6B0], rdx
0x18003d31a  test    r14, r14
0x18003d31d  mov     [rsp+700h+var_6B8], rcx
0x18003d322  mov     rcx, [r8+10h]
0x18003d326  cmovnz  rax, r14
0x18003d32a  mov     [rsp+700h+var_6C0], rax
0x18003d32f  mov     eax, [rbp+5B0h+var_5DC]
0x18003d332  mov     [rsp+700h+var_6C8], r15
0x18003d337  mov     dword ptr [rsp+700h+hTemplateFile], eax
0x18003d33b  mov     [rsp+700h+dwFlagsAndAttributes], r12d
0x18003d340  mov     [rsp+700h+dwCreationDisposition], edi
0x18003d344  call    WPP_SF_DDDDSSSSs
0x18003d349  xor     edi, edi
0x18003d34b  lea     rcx, [rbp+5B0h+var_618]
0x18003d34f  or      r8, 0FFFFFFFFFFFFFFFFh
0x18003d353  mov     rdx, r14
0x18003d356  test    r14, r14
0x18003d359  jnz     short loc_18003D35E
0x18003d35b  mov     rdx, r13
0x18003d35e  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x18003d363  lea     rdx, [rbp+5B0h+var_618]
0x18003d367  lea     rcx, [rbp+5B0h+var_5A0]
0x18003d36b  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x18003d370  lea     rcx, [rbp+5B0h+var_618]
0x18003d374  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18003d379  test    r14, r14
0x18003d37c  jnz     short loc_18003D3D1
0x18003d37e  test    r13, r13
0x18003d381  jnz     short loc_18003D3D1
0x18003d383  mov     [rbp+5B0h+var_558], rdi
0x18003d387  mov     [rbp+5B0h+Reply], 57h ; 'W'
0x18003d38e  lea     rcx, [rbp+5B0h+var_540]; lpPerformanceCount
0x18003d392  call    cs:__imp_QueryPerformanceCounter
0x18003d398  mov     rax, qword ptr [rbp+5B0h+var_540]
0x18003d39c  sub     rax, qword ptr [rbp+5B0h+PerformanceCount]
0x18003d3a0  mov     ebx, [rbp+5B0h+Reply]
0x18003d3a3  mov     r15d, [rbp+5B0h+var_5B4]
0x18003d3a7  mov     r12d, [rbp+5B0h+var_608]
0x18003d3ab  imul    rax, 3E8h
0x18003d3b2  cqo; unsigned __int64
0x18003d3b4  idiv    qword ptr [rbp+5B0h+Frequency]
0x18003d3bb  mov     rdi, rax
0x18003d3be  cmp     ebx, 4C7h
0x18003d3c4  jnz     loc_18003DF76
0x18003d3ca  xor     ebx, ebx
0x18003d3cc  jmp     loc_18003DF83
0x18003d3d1  mov     r15, rdi
0x18003d3d4  mov     r12, rdi
0x18003d3d7  test    r14, r14
0x18003d3da  jz      short loc_18003D3EA
0x18003d3dc  mov     rcx, r14; unsigned __int16 *
0x18003d3df  call    ?AipJustFileName@@YAPEBGPEBG@Z; AipJustFileName(ushort const *)
0x18003d3e4  mov     [rbp+5B0h+var_558], rax
0x18003d3e8  jmp     short loc_18003D3F1
0x18003d3ea  lea     rax, aNull_0; "NULL"
0x18003d3f1  mov     rdx, rax; unsigned __int16 *
0x18003d3f4  lea     rcx, AppInfo_PerfTrack_Elevation_EXE_Start; struct _EVENT_DESCRIPTOR *
0x18003d3fb  call    ?AiLogPerfTrackEventEx@@YAKPEBU_EVENT_DESCRIPTOR@@PEBG@Z; AiLogPerfTrackEventEx(_EVENT_DESCRIPTOR const *,ushort const *)
0x18003d400  mov     dword ptr [rbp+5B0h+var_618], eax
0x18003d403  test    r14, r14
0x18003d406  jz      short loc_18003D416
0x18003d408  or      r15, 0FFFFFFFFFFFFFFFFh
0x18003d40c  inc     r15
0x18003d40f  cmp     [r14+r15*2], di
0x18003d414  jnz     short loc_18003D40C
0x18003d416  test    r13, r13
0x18003d419  jz      short loc_18003D42A
0x18003d41b  or      r12, 0FFFFFFFFFFFFFFFFh
0x18003d41f  inc     r12
0x18003d422  cmp     [r13+r12*2+0], di
0x18003d428  jnz     short loc_18003D41F
0x18003d42a  mov     eax, 7FFFh
0x18003d42f  cmp     r15, rax
0x18003d432  ja      loc_18003D387
0x18003d438  cmp     r12, rax
0x18003d43b  ja      loc_18003D387
0x18003d441  lea     rcx, [rbp+5B0h+var_598]
0x18003d445  call    cs:__imp_CheckElevationEnabled
0x18003d44b  mov     [rbp+5B0h+Reply], eax
0x18003d44e  test    eax, eax
0x18003d450  jnz     loc_18003D38E
0x18003d456  mov     rcx, [rbp+5B0h+var_548]; void *
0x18003d45a  lea     rax, [rbp+5B0h+packageFamilyNameLength]
0x18003d45e  lea     r9, [rbp+5B0h+var_620]; unsigned int *
0x18003d462  mov     qword ptr [rsp+700h+dwCreationDisposition], rax; unsigned int *
0x18003d467  lea     r8, [rbp+5B0h+token]; void **
0x18003d46b  lea     rdx, [rbp+5B0h+Handle]; void **
0x18003d46f  call    ?AiGetClientInformation@@YAKPEAXPEAPEAX1PEAK2@Z; AiGetClientInformation(void *,void * *,void * *,ulong *,ulong *)
0x18003d474  mov     [rbp+5B0h+Reply], eax
0x18003d477  test    eax, eax
0x18003d479  jnz     loc_18003D38E
0x18003d47f  lea     rdx, [rbp+5B0h+var_5B4]
0x18003d483  lea     rcx, [rbp+5B0h+var_5F0]
0x18003d487  call    LUAGetUACPromptPolicy
0x18003d48c  test    eax, eax
0x18003d48e  jns     short loc_18003D4A0
0x18003d490  mov     ecx, eax; Status
0x18003d492  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x18003d498  mov     [rbp+5B0h+Reply], eax
0x18003d49b  jmp     loc_18003D38E
0x18003d4a0  mov     [rbp+5B0h+var_5F0], edi
0x18003d4a3  lea     rdx, [rbp+5B0h+var_5F0]; int *
0x18003d4a7  mov     rdi, [rbp+5B0h+token]
0x18003d4ab  mov     rcx, rdi; void *
0x18003d4ae  call    ?AiCheckForElevatedUser@@YAJPEAXPEAH@Z; AiCheckForElevatedUser(void *,int *)
0x18003d4b3  test    eax, eax
0x18003d4b5  js      short loc_18003D490
0x18003d4b7  mov     edx, [rbp+5B0h+var_5F0]; int
0x18003d4ba  lea     r8, [rbp+5B0h+var_5B0]; int *
0x18003d4be  mov     rcx, rdi; Handle
0x18003d4c1  call    ?AiCheckForAdminUser@@YAJPEAXHPEAH@Z; AiCheckForAdminUser(void *,int,int *)
0x18003d4c6  xor     edi, edi
0x18003d4c8  test    eax, eax
0x18003d4ca  js      short loc_18003D490
0x18003d4cc  test    byte ptr [rbp+5B0h+packageRelativeApplicationIdLength], 8
0x18003d4d0  jz      loc_18003D584
0x18003d4d6  mov     rcx, [rbp+5B0h+hMem]
0x18003d4da  lea     rax, [rbp+5B0h+var_610]
0x18003d4de  mov     qword ptr [rsp+700h+dwFlagsAndAttributes], rax; unsigned __int16 **
0x18003d4e3  lea     r9, [rbp+5B0h+packageFullNameLength]; unsigned __int16 **
0x18003d4e7  mov     qword ptr [rsp+700h+dwCreationDisposition], rcx; unsigned __int16 *
0x18003d4ec  lea     rdx, [rbp+5B0h+applicationUserModelIdLength]; unsigned __int16 **
0x18003d4f0  mov     rcx, r14; unsigned __int16 *
0x18003d4f3  mov     r8, r13; unsigned __int16 *
0x18003d4f6  call    ?AiConvertWow64Paths@@YAKPEBGPEAPEBGPEAGPEAPEAG01@Z; AiConvertWow64Paths(ushort const *,ushort const * *,ushort *,ushort * *,ushort const *,ushort const * *)
0x18003d4fb  mov     r14, qword ptr [rbp+5B0h+applicationUserModelIdLength]
0x18003d4ff  mov     [rbp+5B0h+Reply], eax
0x18003d502  test    eax, eax
0x18003d504  jnz     loc_18003D692
0x18003d50a  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18003d50e  test    r14, r14
0x18003d511  jz      short loc_18003D520
0x18003d513  mov     r15, rcx
0x18003d516  inc     r15
0x18003d519  cmp     [r14+r15*2], di
0x18003d51e  jnz     short loc_18003D516
0x18003d520  mov     r13, qword ptr [rbp+5B0h+packageFullNameLength]
0x18003d524  test    r13, r13
0x18003d527  jz      short loc_18003D537
0x18003d529  mov     r12, rcx
0x18003d52c  inc     r12
0x18003d52f  cmp     [r13+r12*2+0], di
0x18003d535  jnz     short loc_18003D52C
0x18003d537  mov     eax, 7FFFh
0x18003d53c  cmp     r15, rax
  ... truncated ...
```
