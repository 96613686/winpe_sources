# RAiLaunchAdminProcess

- ea: `0x18003ac30`
- end: `0x18003be34`
- name: `RAiLaunchAdminProcess`
- size: `4612`
- prototype: `__int64 __fastcall(struct _RPC_ASYNC_STATE *, void *, unsigned __int16 *, unsigned __int16 *, UINT32, unsigned int, unsigned __int16 *, unsigned __int16 *, struct _APPINFO_STARTUPINFO *, void *, unsigned int, struct _PROCESS_INFORMATION *, UINT32 *)`
- caller_count: `0`
- callee_count: `46`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x18000a1f0`
- `0x18000a230`
- `0x18000cdd0`
- `0x18000f190`
- `0x18000f24c`
- `0x18000fac0`
- `0x180010f44`
- `0x18001166c`
- `0x180011ff8`
- `0x180012634`
- `0x180012a14`
- `0x180014da0`
- `0x180016a40`
- `0x180016da4`
- `0x1800192e8`
- `0x180019704`
- `0x18001980c`
- `0x180019b18`
- `0x18001b494`
- `0x18001b4a0`
- `0x18001ccf8`
- `0x18001cd4c`
- `0x180022b74`
- `0x180022bb0`
- `0x1800234a0`
- `0x18002487c`
- `0x18002628c`
- `0x180026910`
- `0x180026eb4`
- `0x1800272f4`
- `0x180027490`
- `0x18002a2a8`
- `0x18003888c`
- `0x1800388f8`
- `0x1800389b0`
- `0x180039720`
- `0x18003981c`
- `0x180039894`
- `0x18003ac30`
- `0x18003c310`
- `0x18003d1f0`
- `0x1800423f4`
- `0x180043d2c`
- `0x180043f6c`
- `0x1800449fa`
- `0x180044a20`

## import_xrefs

- `RPCRT4!RpcAsyncCompleteCall` at `0x18003bdbd`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18003bdbd`
- `RPCRT4!RpcImpersonateClient` at `0x18003b1e0`
- `RPCRT4!RpcImpersonateClient` at `0x18003b1e0`
- `RPCRT4!RpcRevertToSelf` at `0x18003b2de`
- `RPCRT4!RpcRevertToSelf` at `0x18003b321`
- `RPCRT4!RpcRevertToSelf` at `0x18003b579`
- `RPCRT4!RpcRevertToSelf` at `0x18003b67a`
- `RPCRT4!RpcRevertToSelf` at `0x18003b6c5`
- `RPCRT4!RpcRevertToSelf` at `0x18003b707`
- `RPCRT4!RpcRevertToSelf` at `0x18003b78e`
- `RPCRT4!RpcRevertToSelf` at `0x18003b2de`
- `RPCRT4!RpcRevertToSelf` at `0x18003b321`
- `RPCRT4!RpcRevertToSelf` at `0x18003b579`
- `RPCRT4!RpcRevertToSelf` at `0x18003b67a`
- `RPCRT4!RpcRevertToSelf` at `0x18003b6c5`
- `RPCRT4!RpcRevertToSelf` at `0x18003b707`
- `RPCRT4!RpcRevertToSelf` at `0x18003b78e`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18003babe`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18003babe`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18003bafc`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18003bb0a`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18003bafc`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18003bb0a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b23f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b23f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003bcd4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003bcd4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003bcec`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003bd04`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003bd1d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003bd2d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003bd40`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003bcec`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003bd04`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003bd1d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003bd2d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003bd40`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18003b222`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18003b222`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x18003ad7a`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x18003ad7a`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18003ad67`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18003af77`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18003ad67`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18003af77`
- `api-ms-win-core-kernel32-private-l1-1-0!CheckElevation` at `0x18003b6f4`
- `api-ms-win-core-kernel32-private-l1-1-0!CheckElevation` at `0x18003b6f4`
- `api-ms-win-core-kernel32-private-l1-1-0!CheckElevationEnabled` at `0x18003b04a`
- `api-ms-win-core-kernel32-private-l1-1-0!CheckElevationEnabled` at `0x18003b04a`
- `api-ms-win-appmodel-runtime-l1-1-1!GetApplicationUserModelIdFromToken` at `0x18003b8dc`
- `api-ms-win-appmodel-runtime-l1-1-1!GetApplicationUserModelIdFromToken` at `0x18003b8dc`
- `api-ms-win-appmodel-runtime-l1-1-1!ParseApplicationUserModelId` at `0x18003b920`
- `api-ms-win-appmodel-runtime-l1-1-1!ParseApplicationUserModelId` at `0x18003b920`
- `api-ms-win-appmodel-runtime-l1-1-1!GetPackageFullNameFromToken` at `0x18003b880`
- `api-ms-win-appmodel-runtime-l1-1-1!GetPackageFullNameFromToken` at `0x18003b880`
- `api-ms-win-appmodel-runtime-l1-1-0!PackageFamilyNameFromFullName` at `0x18003b3ca`
- `api-ms-win-appmodel-runtime-l1-1-0!PackageFamilyNameFromFullName` at `0x18003b3ca`
- `ntdll!NtClose` at `0x18003bd55`
- `ntdll!NtClose` at `0x18003bd6d`
- `ntdll!NtClose` at `0x18003bd85`
- `ntdll!NtClose` at `0x18003bd55`
- `ntdll!NtClose` at `0x18003bd6d`
- `ntdll!NtClose` at `0x18003bd85`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18003b0a3`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18003b0d1`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18003b0a3`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18003b0d1`
- `USERENV!UnloadUserProfile` at `0x18003baa9`
- `USERENV!UnloadUserProfile` at `0x18003bb23`
- `USERENV!UnloadUserProfile` at `0x18003baa9`
- `USERENV!UnloadUserProfile` at `0x18003bb23`
- `ext-ms-win-desktopappx-l1-1-6!VerifyFileIsTrustedAndInPackage` at `0x18003b89e`
- `ext-ms-win-desktopappx-l1-1-6!VerifyFileIsTrustedAndInPackage` at `0x18003b89e`
- `ext-ms-win-appmodel-activation-l1-1-1!RegisterAppXPackageIfNecessary2` at `0x18003bae5`
- `ext-ms-win-appmodel-activation-l1-1-1!RegisterAppXPackageIfNecessary2` at `0x18003bae5`
- `ext-ms-win-appmodel-appexecutionalias-l1-1-0!GetAppExecutionAliasApplicationUserModelIdEx` at `0x18003b454`
- `ext-ms-win-appmodel-appexecutionalias-l1-1-0!GetAppExecutionAliasApplicationUserModelIdEx` at `0x18003b454`
- `ext-ms-win-appmodel-appexecutionalias-l1-1-0!LoadAppExecutionAliasInfoEx` at `0x18003b38f`
- `ext-ms-win-appmodel-appexecutionalias-l1-1-0!LoadAppExecutionAliasInfoEx` at `0x18003b38f`
- `ext-ms-win-appmodel-appexecutionalias-l1-1-0!FreeAppExecutionAliasInfoEx` at `0x18003bd9a`
- `ext-ms-win-appmodel-appexecutionalias-l1-1-0!FreeAppExecutionAliasInfoEx` at `0x18003bd9a`
- `ext-ms-win-appmodel-appexecutionalias-l1-1-0!OpenAppExecutionAliasForUserEx` at `0x18003b423`
- `ext-ms-win-appmodel-appexecutionalias-l1-1-0!OpenAppExecutionAliasForUserEx` at `0x18003b423`
- `ext-ms-win-appmodel-appexecutionalias-l1-1-2!GetAppExecutionAliasPath` at `0x18003b309`
- `ext-ms-win-appmodel-appexecutionalias-l1-1-2!GetAppExecutionAliasPath` at `0x18003b371`
- `ext-ms-win-appmodel-appexecutionalias-l1-1-2!GetAppExecutionAliasPath` at `0x18003b309`
- `ext-ms-win-appmodel-appexecutionalias-l1-1-2!GetAppExecutionAliasPath` at `0x18003b371`
- `ext-ms-win-appmodel-appexecutionalias-l1-1-5!LoadAppExecutionAliasInfoEx2` at `0x18003b298`
- `ext-ms-win-appmodel-appexecutionalias-l1-1-5!LoadAppExecutionAliasInfoEx2` at `0x18003b298`

## string_xrefs

- `0x18003adc7`: `++. hwnd = %x dwClientFlags = %x dwCreationFlags = %x dwTimeout = %x\n	lpDesktop = %ws\n	lpApplicationName = %ws\n	lpCommandLine = %ws\n	lpCurrentDirectory = %ws\n	lpCvStr = %s\n`

## pseudocode

```c
__int64 __fastcall RAiLaunchAdminProcess(
        struct _RPC_ASYNC_STATE *a1,
        void *a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4,
        UINT32 a5,
        unsigned int a6,
        unsigned __int16 *a7,
        unsigned __int16 *a8,
        struct _APPINFO_STARTUPINFO *a9,
        void *a10,
        unsigned int a11,
        struct _PROCESS_INFORMATION *a12,
        UINT32 *a13)
{
  const unsigned __int16 *v13; // r12
  const unsigned __int16 *v14; // rbx
  unsigned __int16 *v15; // rdi
  const unsigned __int16 *v16; // r14
  unsigned __int16 *v17; // r15
  unsigned __int64 v18; // r13
  const unsigned __int16 *v19; // rsi
  const unsigned __int16 *v20; // rax
  char v21; // bl
  void *v22; // rax
  volatile signed __int64 *v23; // rbx
  const unsigned __int16 *v24; // rdx
  const unsigned __int16 *v25; // rax
  const unsigned __int16 *v26; // rcx
  unsigned __int64 v27; // r14
  unsigned __int16 *v28; // rdx
  HANDLE v29; // r12
  HANDLE v30; // rbx
  struct _RPC_ASYNC_STATE *v31; // rsi
  UINT32 *v32; // r14
  char IsEnabled; // al
  unsigned int v34; // eax
  NTSTATUS v35; // eax
  NTSTATUS v36; // eax
  int v37; // eax
  unsigned int v38; // eax
  unsigned __int16 *v39; // rdx
  const WCHAR *v40; // rsi
  DWORD LastError; // eax
  __int64 v42; // rbx
  int AppExecutionAliasPath; // eax
  int v44; // ebx
  const unsigned __int16 *v45; // rsi
  __int64 v46; // rcx
  unsigned __int16 v47; // ax
  const unsigned __int16 *v48; // rcx
  unsigned __int16 v49; // ax
  unsigned __int16 v50; // dx
  __int64 v51; // rax
  unsigned __int64 v52; // r14
  unsigned __int16 *v53; // rbx
  __int64 v54; // r8
  UINT32 v55; // ecx
  void *v56; // rdx
  unsigned __int16 *v57; // rcx
  const unsigned __int16 *v58; // rcx
  const unsigned __int16 *v59; // rcx
  const unsigned __int16 *v60; // rcx
  RPC_STATUS v61; // eax
  unsigned int v62; // ebx
  unsigned int v63; // eax
  unsigned int v64; // esi
  unsigned int v65; // ebx
  const unsigned __int16 *v66; // rcx
  unsigned int v67; // eax
  wchar_t *v68; // rcx
  HLOCAL v69; // rax
  unsigned __int16 *v70; // r14
  HANDLE v71; // rax
  unsigned int v72; // ebx
  void *v73; // rdx
  struct _PROCESS_INFORMATION *v74; // rax
  unsigned int v75; // eax
  unsigned __int16 *v77; // [rsp+50h] [rbp-F0h]
  int Reply; // [rsp+C0h] [rbp-80h] BYREF
  char v79; // [rsp+C4h] [rbp-7Ch] BYREF
  unsigned int v80; // [rsp+C8h] [rbp-78h] BYREF
  HANDLE hObject; // [rsp+D0h] [rbp-70h]
  unsigned int v82; // [rsp+D8h] [rbp-68h] BYREF
  PRPC_ASYNC_STATE pAsync; // [rsp+E0h] [rbp-60h]
  UINT32 *v84; // [rsp+E8h] [rbp-58h]
  __int64 v85; // [rsp+F0h] [rbp-50h] BYREF
  UINT32 v86; // [rsp+F8h] [rbp-48h] BYREF
  unsigned int v87; // [rsp+FCh] [rbp-44h] BYREF
  UINT32 packageRelativeApplicationIdLength; // [rsp+100h] [rbp-40h] BYREF
  unsigned int v89; // [rsp+104h] [rbp-3Ch]
  UINT32 packageFamilyNameLength; // [rsp+108h] [rbp-38h] BYREF
  unsigned int v91; // [rsp+10Ch] [rbp-34h]
  unsigned int v92; // [rsp+110h] [rbp-30h] BYREF
  unsigned __int16 *v93; // [rsp+118h] [rbp-28h] BYREF
  HANDLE hToken; // [rsp+120h] [rbp-20h] BYREF
  UINT32 v95[2]; // [rsp+128h] [rbp-18h] BYREF
  unsigned int v96; // [rsp+130h] [rbp-10h] BYREF
  int v97; // [rsp+134h] [rbp-Ch] BYREF
  int v98; // [rsp+138h] [rbp-8h] BYREF
  HANDLE hProfile; // [rsp+140h] [rbp+0h] BYREF
  __int64 v100; // [rsp+148h] [rbp+8h] BYREF
  int v101; // [rsp+150h] [rbp+10h] BYREF
  HANDLE token; // [rsp+158h] [rbp+18h] BYREF
  struct _PROCESS_INFORMATION *v103; // [rsp+160h] [rbp+20h] BYREF
  struct _PROCESS_INFORMATION *v104; // [rsp+168h] [rbp+28h] BYREF
  int v105; // [rsp+170h] [rbp+30h] BYREF
  int v106; // [rsp+174h] [rbp+34h] BYREF
  HLOCAL hMem; // [rsp+178h] [rbp+38h] BYREF
  char v108[8]; // [rsp+180h] [rbp+40h] BYREF
  LPCWSTR lpFileName; // [rsp+188h] [rbp+48h] BYREF
  struct _APPINFO_STARTUPINFO *v110; // [rsp+190h] [rbp+50h] BYREF
  unsigned __int16 *v111; // [rsp+198h] [rbp+58h]
  HLOCAL v112; // [rsp+1A0h] [rbp+60h] BYREF
  unsigned __int64 v113; // [rsp+1A8h] [rbp+68h] BYREF
  UINT32 applicationUserModelIdLength; // [rsp+1B0h] [rbp+70h] BYREF
  UINT32 packageFullNameLength; // [rsp+1B4h] [rbp+74h] BYREF
  LUATelemetry *v116; // [rsp+1B8h] [rbp+78h] BYREF
  unsigned __int16 *v117; // [rsp+1C0h] [rbp+80h]
  unsigned __int16 *v118; // [rsp+1C8h] [rbp+88h]
  unsigned __int16 *v119; // [rsp+1D0h] [rbp+90h]
  HLOCAL v120; // [rsp+1D8h] [rbp+98h] BYREF
  HANDLE Handle; // [rsp+1E0h] [rbp+A0h] BYREF
  void *v122; // [rsp+1E8h] [rbp+A8h]
  LARGE_INTEGER v123; // [rsp+1F0h] [rbp+B0h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+1F8h] [rbp+B8h] BYREF
  LARGE_INTEGER Frequency; // [rsp+200h] [rbp+C0h] BYREF
  unsigned __int16 **v126; // [rsp+208h] [rbp+C8h] BYREF
  __int64 v127; // [rsp+210h] [rbp+D0h] BYREF
  char v128; // [rsp+218h] [rbp+D8h]
  char v129[80]; // [rsp+220h] [rbp+E0h] BYREF
  char Source[144]; // [rsp+270h] [rbp+130h] BYREF
  WCHAR packageFamilyName[72]; // [rsp+300h] [rbp+1C0h] BYREF
  WCHAR applicationUserModelId[136]; // [rsp+390h] [rbp+250h] BYREF
  WCHAR packageRelativeApplicationId[136]; // [rsp+4A0h] [rbp+360h] BYREF
  WCHAR packageFullName[128]; // [rsp+5B0h] [rbp+470h] BYREF

  v13 = a4;
  v14 = a7;
  v15 = a3;
  v16 = a8;
  v17 = a4;
  hObject = (HANDLE)-1LL;
  packageRelativeApplicationIdLength = a5;
  v91 = a6;
  v110 = a9;
  hProfile = a10;
  v89 = a11;
  v104 = a12;
  v84 = a13;
  pAsync = a1;
  v18 = 0;
  v87 = 0;
  v96 = 0;
  v80 = 0;
  v101 = 0;
  v116 = 0;
  v120 = 0;
  hToken = 0;
  Handle = 0;
  token = 0;
  v113 = 0;
  v112 = 0;
  v82 = 0;
  v92 = 0;
  v79 = 0;
  v100 = 0;
  v98 = 0;
  v97 = 0;
  packageFamilyNameLength = 0;
  Frequency.QuadPart = 0;
  PerformanceCount.QuadPart = 0;
  v123.QuadPart = 0;
  v103 = 0;
  v118 = a4;
  v117 = a3;
  v122 = a2;
  v111 = a8;
  v119 = a7;
  lpFileName = a3;
  v93 = a4;
  hMem = a7;
  v105 = 1;
  v86 = 6;
  QueryPerformanceCounter(&PerformanceCount);
  QueryPerformanceFrequency(&Frequency);
  memset_0(Source, 0, 0x81u);
  v19 = L"NULL";
  if ( !a7 )
    v14 = L"NULL";
  if ( !v17 )
    v13 = L"NULL";
  if ( v15 )
    v20 = AipJustFileName(v15);
  else
    v20 = L"NULL";
  v77 = (unsigned __int16 *)v14;
  if ( !a8 )
    v16 = L"NULL";
  v21 = packageRelativeApplicationIdLength;
  LUATelemetry::WatchCurrentThread(
    v129,
    "RAiLaunchAdminProcess",
    "++. hwnd = %x dwClientFlags = %x dwCreationFlags = %x dwTimeout = %x\n"
    "\tlpDesktop = %ws\n"
    "\tlpApplicationName = %ws\n"
    "\tlpCommandLine = %ws\n"
    "\tlpCurrentDirectory = %ws\n"
    "\tlpCvStr = %s\n",
    (unsigned int)hProfile,
    packageRelativeApplicationIdLength,
    v91,
    v89,
    v16,
    v20,
    v13,
    v77,
    Source);
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
      Source);
    if ( v23 )
      operator delete((void *)v23);
    v21 = packageRelativeApplicationIdLength;
    v17 = v93;
    v15 = (unsigned __int16 *)lpFileName;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v24 = L"NULL";
    if ( hMem )
      v24 = (const unsigned __int16 *)hMem;
    v25 = L"NULL";
    v26 = L"NULL";
    if ( v17 )
      v26 = v17;
    if ( v15 )
      v25 = v15;
    WPP_SF_DDDDSSSSs(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      (_DWORD)v24,
      (_DWORD)WPP_GLOBAL_Control,
      (_DWORD)hProfile,
      v21,
      v91,
      v89,
      (__int64)v16,
      (__int64)v25,
      (__int64)v26,
      (__int64)v24,
      (__int64)Source);
  }
  v27 = -1;
  if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_4155280696>::__private_IsEnabled((__int64)&`wil::Feature<__WilFeatureTraits_Feature_4155280696>::GetImpl'::`2'::impl) )
  {
    v28 = v15;
    if ( !v15 )
      v28 = v17;
    wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
      &v85,
      v28,
      -1);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
      &v103,
      &v85);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v85);
  }
  if ( v15 )
  {
    v19 = AipJustFileName(v15);
  }
  else if ( !v17 )
  {
LABEL_33:
    Reply = 87;
LABEL_34:
    v29 = token;
    goto LABEL_35;
  }
  v116 = (LUATelemetry *)v19;
  LODWORD(v85) = AiLogPerfTrackEventEx(&AppInfo_PerfTrack_Elevation_EXE_Start, v19);
  if ( v15 )
  {
    v18 = -1;
    do
      ++v18;
    while ( v15[v18] );
  }
  if ( v17 )
  {
    do
      ++v27;
    while ( v17[v27] );
  }
  else
  {
    v27 = v113;
  }
  if ( v18 > 0x7FFF || v27 > 0x7FFF )
    goto LABEL_33;
  Reply = CheckElevationEnabled(&v105);
  if ( Reply )
    goto LABEL_34;
  Reply = AiGetClientInformation(v122, &Handle, &token, &v96, &v82);
  if ( Reply )
    goto LABEL_34;
  v35 = LUAGetUACPromptPolicy(&packageFamilyNameLength, &v97);
  if ( v35 < 0 )
  {
    Reply = RtlNtStatusToDosErrorNoTeb(v35);
    goto LABEL_34;
  }
  packageFamilyNameLength = 0;
  v29 = token;
  v36 = AiCheckForElevatedUser(token, (int *)&packageFamilyNameLength);
  if ( v36 < 0 || (v36 = AiCheckForAdminUser(v29, packageFamilyNameLength, &v98), v36 < 0) )
  {
    v37 = RtlNtStatusToDosErrorNoTeb(v36);
    goto LABEL_56;
  }
  if ( (v21 & 8) != 0 )
  {
    v38 = AiConvertWow64Paths(v117, &lpFileName, v118, &v93, v119, (const unsigned __int16 **)&hMem);
    v15 = (unsigned __int16 *)lpFileName;
    Reply = v38;
    if ( v38 )
    {
      v17 = v93;
      goto LABEL_35;
    }
    if ( lpFileName )
    {
      v18 = -1;
      do
        ++v18;
      while ( lpFileName[v18] );
    }
    v17 = v93;
    if ( v93 )
    {
      v27 = -1;
      do
        ++v27;
      while ( v93[v27] );
    }
    if ( v18 > 0x7FFF || v27 > 0x7FFF )
    {
      Reply = 87;
      goto LABEL_35;
    }
    if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_4155280696>::__private_IsEnabled((__int64)&`wil::Feature<__WilFeatureTraits_Feature_4155280696>::GetImpl'::`2'::impl) )
    {
      if ( v15 )
        v39 = v15;
      else
        v39 = v17;
      wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
        v108,
        v39,
        -1);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
        &v103,
        v108);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(v108);
    }
  }
  if ( !v105 )
  {
    v64 = v96;
    v70 = v111;
    goto LABEL_198;
  }
  v37 = RpcImpersonateClient(0);
  if ( v37 )
  {
LABEL_56:
    Reply = v37;
    goto LABEL_35;
  }
  v40 = v17;
  if ( v15 )
    v40 = v15;
  hObject = CreateFileW(v40, 0xA0000000, 5u, 0, 3u, 0x80u, 0);
  v30 = hObject;
  if ( hObject != (HANDLE)-1LL )
  {
    v57 = v17;
    if ( v15 )
      v57 = v15;
    Reply = CheckElevation(v57, &v101, 0, &v87, &v86);
    if ( Reply )
      goto LABEL_128;
    v58 = v17;
    if ( v15 )
      v58 = v15;
    Reply = AiCheckSecureApplicationDirectory(v58, &v80);
    if ( Reply )
    {
LABEL_128:
      RpcRevertToSelf();
      goto LABEL_36;
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_2045735225>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_2045735225>::GetImpl'::`2'::impl)
      && v87 - 16 <= 2
      && (unsigned int)LUAIsShadowAdminEnabled() )
    {
      v59 = v17;
      if ( v15 )
        v59 = v15;
      AipCheckAssistiveTechnologyList(v59, &v80);
    }
    v60 = v17;
    if ( v15 )
      v60 = v15;
    AiIsEXESafeToAutoApprove(v60, v30, v17, (const unsigned __int16 *)&v80, (unsigned __int16 **)&v120);
    v61 = RpcRevertToSelf();
    if ( v61 )
    {
      Reply = v61;
      goto LABEL_36;
    }
    v62 = v80;
    if ( (v101 & 8) != 0 )
    {
      v62 = v80 | 0x1000;
      v80 |= 0x1000u;
    }
    if ( (v101 & 4) != 0 )
    {
      v62 |= 2u;
      v80 = v62;
    }
    v63 = v87;
    if ( v87 - 16 <= 2 )
    {
      if ( v87 >= 3 )
      {
        v63 = v87 - 16;
        v87 -= 16;
      }
      v62 |= 0x8000Cu;
      v80 = v62;
    }
    if ( !v63 && (v62 & 4) != 0 )
    {
      v64 = v96;
    }
    else
    {
      v64 = v96;
      if ( !AiIsElevationAllowedForSession(v96) )
      {
        Reply = 50;
        goto LABEL_35;
      }
      v63 = v87;
    }
    if ( (packageRelativeApplicationIdLength & 1) != 0 )
    {
      if ( v63 <= 1 )
      {
        v62 |= 0x200u;
        v80 = v62;
      }
      v87 = 2;
      v86 = 6;
    }
    if ( (packageRelativeApplicationIdLength & 0x10) != 0 )
    {
      v62 |= 0x800u;
      v80 = v62;
    }
    if ( (packageRelativeApplicationIdLength & 0x80u) != 0 )
      v80 = v62 | 0x100000;
    if ( (packageRelativeApplicationIdLength & 0x100) != 0 )
    {
      v92 = 8;
    }
    else
    {
      v65 = v92;
      if ( (packageRelativeApplicationIdLength & 0x800) != 0 )
        v65 = 1024;
      v92 = v65;
    }
    packageFullNameLength = 128;
    v106 = 0;
    if ( !GetPackageFullNameFromToken(v29, &packageFullNameLength, packageFullName) )
      VerifyFileIsTrustedAndInPackage(v15, packageFullName, &v106);
    memset_0(applicationUserModelId, 0, 0x106u);
    applicationUserModelIdLength = 131;
    if ( v106 )
    {
      if ( GetApplicationUserModelIdFromToken(v29, &applicationUserModelIdLength, applicationUserModelId) )
        goto LABEL_35;
      v95[0] = 65;
      packageRelativeApplicationIdLength = 65;
      if ( ParseApplicationUserModelId(
             applicationUserModelId,
             v95,
             packageFamilyName,
             &packageRelativeApplicationIdLength,
             packageRelativeApplicationId) < 0 )
        goto LABEL_35;
      v86 = 8;
      v66 = v17;
      if ( v15 )
        v66 = v15;
      v67 = AiBuildPackagedAppParams(
              v66,
              v18,
              v17,
              v27,
              v82,
              packageFamilyName,
              applicationUserModelId,
              (struct _CONSENTUI_PARAM_HEADER **)&v112);
    }
    else
    {
      v68 = v17;
      if ( v15 )
        v68 = v15;
      v67 = AiBuildEXEParams(
              v68,
              hObject,
              v15,
              v18,
              v17,
              v27,
              (const unsigned __int16 *)v120,
              v82,
              (struct _CONSENTUI_PARAM_HEADER **)&v112);
    }
    Reply = v67;
    if ( v67
      || (v69 = v112,
          v70 = v111,
          *((_DWORD *)v112 + 13) = v85,
          (Reply = AiCheckLUA(v87, &v80, v86, v29, v69, v70, hProfile, v64, v89, Source, &hToken)) != 0) )
    {
LABEL_35:
      v30 = hObject;
LABEL_36:
      v31 = pAsync;
      v32 = v84;
      goto LABEL_37;
    }
    v71 = hToken;
    if ( !hToken )
    {
LABEL_199:
      v73 = v29;
      if ( v71 )
        v73 = v71;
      v30 = hObject;
      Reply = AiLaunchProcess(
                Handle,
                v73,
                hObject,
                v80,
                v15,
                v17,
                v91,
                (const unsigned __int16 *)hMem,
                v70,
                v110,
                v64,
                0,
                v92,
                0,
                0,
                0,
                v104);
      goto LABEL_36;
    }
    v72 = v80 | 1;
    v80 |= 1u;
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShadowAdmin>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_ShadowAdmin>::GetImpl'::`2'::impl) )
    {
      v91 &= 0xFFFFFFFC;
      if ( v86 == 8 && ((v72 & 0x20) == 0 || (v72 & 0x8000000) != 0 && (unsigned int)LUAIsShadowAdminEnabled()) )
      {
        hProfile = 0;
        Reply = AipLoadUserProfile(hToken, &hProfile);
        if ( Reply )
          goto LABEL_189;
        ImpersonateLoggedOnUser(hToken);
        v89 = 0;
        if ( (int)RegisterAppXPackageIfNecessary2(0, applicationUserModelId, 0, 0) < 0 )
        {
          Reply = 15669;
          RevertToSelf();
LABEL_189:
          if ( hProfile )
            UnloadUserProfile(hToken, hProfile);
          goto LABEL_35;
        }
        RevertToSelf();
        if ( hProfile )
          UnloadUserProfile(hToken, hProfile);
      }
    }
    Reply = AipApplyAdminProcessPackageClaimsPolicy(&hToken, v29, v80);
    if ( Reply )
      goto LABEL_35;
LABEL_198:
    v71 = hToken;
    goto LABEL_199;
  }
  LastError = GetLastError();
  Reply = LastError;
  if ( LastError != 1920 && LastError != 5 || !(unsigned __int8)IsLoadAppExecutionAliasInfoExPresent() )
    goto LABEL_124;
  v85 = 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AppExAliasAbsPath2>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_AppExAliasAbsPath2>::GetImpl'::`2'::impl)
    && (unsigned __int8)IsLoadAppExecutionAliasInfoEx2Present()
    && (int)LoadAppExecutionAliasInfoEx2(v40, v29, 0, &v100) >= 0 )
  {
    wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
      &v92,
      v40,
      -1);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
      &v85,
      &v92);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v92);
    v42 = v85;
    if ( !v85 )
    {
LABEL_87:
      RpcRevertToSelf();
LABEL_88:
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v85);
      goto LABEL_35;
    }
  }
  else
  {
    v92 = 0;
    AppExecutionAliasPath = GetAppExecutionAliasPath(v40, v29, 0, &v92);
    if ( WIN32_FROM_HRESULT(AppExecutionAliasPath) != 122 )
    {
      RpcRevertToSelf();
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v85);
      goto LABEL_36;
    }
    wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
      &v113,
      0,
      v92);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
      &v85,
      &v113);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v113);
    v42 = v85;
    if ( (int)GetAppExecutionAliasPath(v40, v29, v85, &v92) < 0 )
      goto LABEL_87;
    if ( (int)LoadAppExecutionAliasInfoEx(v42, v29, &v100) < 0 )
      goto LABEL_123;
  }
  if ( *(_DWORD *)(v100 + 32)
    || (packageFamilyNameLength = 65,
        PackageFamilyNameFromFullName(*(PCWSTR *)v100, &packageFamilyNameLength, packageFamilyName)) )
  {
LABEL_123:
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v85);
LABEL_124:
    RpcRevertToSelf();
    goto LABEL_35;
  }
  memset_0(packageRelativeApplicationId, 0, 0x106u);
  v82 = 131;
  v126 = &v93;
  v93 = 0;
  v127 = 0;
  v128 = 1;
  v44 = OpenAppExecutionAliasForUserEx(v42, v29, &v127);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CloseAppExecutionAliasEx(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CloseAppExecutionAliasEx(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(&v126);
  if ( v44 < 0 || (int)GetAppExecutionAliasApplicationUserModelIdEx(v93, packageRelativeApplicationId, &v82) < 0 )
  {
LABEL_122:
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CloseAppExecutionAliasEx(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CloseAppExecutionAliasEx(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v93);
    goto LABEL_123;
  }
  v45 = v17;
  LODWORD(v46) = 0;
  if ( v17 )
  {
    v47 = *v17;
    if ( *v17 == 34 )
    {
      v48 = v17 + 1;
      v49 = v17[1];
      if ( v49 != 34 )
      {
        v50 = v17[1];
        do
        {
          v49 = v50;
          if ( !v50 )
            break;
          v49 = *++v48;
          v50 = *v48;
        }
        while ( *v48 != 34 );
      }
      v45 = v48 + 1;
      if ( v49 != 34 )
        v45 = v48;
    }
    else
    {
      while ( v47 != 32 && v47 )
        v47 = *++v45;
    }
    v46 = -1;
    do
      ++v46;
    while ( v45[v46] );
  }
  v51 = -1;
  do
    ++v51;
  while ( *(_WORD *)(*(_QWORD *)(v100 + 8) + 2 * v51) );
  v52 = 2 * ((int)v46 + (int)v51) + 6;
  wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
    v95,
    0,
    v52);
  v53 = *(unsigned __int16 **)v95;
  if ( !*(_QWORD *)v95
    || StringCbCopyW(*(unsigned __int16 **)v95, v52, L"\"") < 0
    || StringCbCatW(v53, v52, *(const unsigned __int16 **)(v100 + 8)) < 0
    || StringCbCatW(v53, v52, L"\"") < 0 )
  {
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(v95);
    goto LABEL_122;
  }
  if ( v45 && StringCbCatW(v53, v52, v45) < 0 )
  {
    RpcRevertToSelf();
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(v95);
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CloseAppExecutionAliasEx(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CloseAppExecutionAliasEx(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v93);
    goto LABEL_88;
  }
  v32 = v84;
  v54 = v100;
  v55 = packageRelativeApplicationIdLength | 0x200;
  v31 = pAsync;
  v56 = v122;
  *v84 = v86;
  AipLaunchProcessWithIdentityHelper(
    v31,
    v56,
    *(unsigned __int16 **)(v54 + 8),
    v53,
    v55,
    v91,
    (unsigned __int16 *)hMem,
    v111,
    v110,
    packageFamilyName,
    packageRelativeApplicationId,
    hProfile,
    v89,
    0x11u,
    0,
    0,
    0,
    0,
    0,
    Source,
    &v98,
    (enum UACPROMPT_POLICY *)&v97,
    (struct _APPINFO_PROCESS_INFORMATION *)v104);
  v79 = 1;
  RpcRevertToSelf();
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(v95);
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CloseAppExecutionAliasEx(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CloseAppExecutionAliasEx(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v93);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v85);
  v30 = hObject;
LABEL_37:
  QueryPerformanceCounter(&v123);
  v110 = (struct _APPINFO_STARTUPINFO *)(1000 * (v123.QuadPart - PerformanceCount.QuadPart) / Frequency.QuadPart);
  IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_4155280696>::__private_IsEnabled((__int64)&`wil::Feature<__WilFeatureTraits_Feature_4155280696>::GetImpl'::`2'::impl);
  LODWORD(v85) = v97;
  if ( IsEnabled )
  {
    v104 = v103;
    v95[0] = v86;
    v34 = Reply;
    if ( Reply == 1223 )
    {
      v82 = 0;
    }
    else
    {
      if ( Reply > 0 )
        v34 = (unsigned __int16)Reply | 0x80070000;
      v82 = v34;
    }
  }
  else
  {
    v74 = (struct _PROCESS_INFORMATION *)v17;
    if ( v15 )
      v74 = (struct _PROCESS_INFORMATION *)v15;
    v104 = v74;
    v95[0] = v86;
    v75 = Reply;
    if ( Reply == 1223 )
    {
      v82 = 0;
    }
    else
    {
      if ( Reply > 0 )
        v75 = (unsigned __int16)Reply | 0x80070000;
      v82 = v75;
    }
  }
  LUATelemetry::LaunchAdminProcess<long,unsigned long &,unsigned long,unsigned long &,unsigned short const * &,unsigned short *,int &,unsigned long,__int64 &,bool &,char (&)[129]>(
    (int *)&v82,
    &v80,
    v95,
    (unsigned int *)&Reply,
    &v116,
    (const unsigned __int16 **)&v104,
    &v98,
    (unsigned int *)&v85,
    (__int64 *)&v110,
    (bool *)&v79,
    Source);
  if ( v30 != (HANDLE)-1LL )
    CloseHandle(v30);
  if ( v15 != v117 )
    LocalFree(v15);
  if ( v17 != v118 )
    LocalFree(v17);
  if ( hMem != v119 )
    LocalFree(hMem);
  LocalFree(v112);
  LocalFree(v120);
  if ( hToken )
  {
    NtClose(hToken);
    hToken = 0;
  }
  if ( v29 )
    NtClose(v29);
  if ( Handle )
    NtClose(Handle);
  if ( v100 )
  {
    FreeAppExecutionAliasInfoEx();
    v100 = 0;
  }
  if ( !v79 )
  {
    *v32 = v86;
    RpcAsyncCompleteCall(v31, &Reply);
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_D(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      12,
      &WPP_5a99e4d32d543c5ccd81a78831f70868_Traceguids,
      (unsigned int)Reply);
  wil::ActivityThreadWatcher::~ActivityThreadWatcher((wil::ActivityThreadWatcher *)v129);
  return wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v103);
}

```

## disassembly

```asm
0x18003ac30  push    rbp
0x18003ac32  push    rbx
0x18003ac33  push    rsi
0x18003ac34  push    rdi
0x18003ac35  push    r12
0x18003ac37  push    r13
0x18003ac39  push    r14
0x18003ac3b  push    r15
0x18003ac3d  lea     rbp, [rsp-588h]
0x18003ac45  sub     rsp, 6C8h
0x18003ac4c  mov     rax, cs:__security_cookie
0x18003ac53  xor     rax, rsp
0x18003ac56  mov     [rbp+5C0h+var_50], rax
0x18003ac5d  mov     eax, [rbp+5C0h+arg_20]
0x18003ac63  mov     r12, r9
0x18003ac66  mov     rbx, [rbp+5C0h+arg_30]
0x18003ac6d  mov     rdi, r8
0x18003ac70  mov     r14, [rbp+5C0h+arg_38]
0x18003ac77  mov     r15, r9
0x18003ac7a  or      [rbp+5C0h+hObject], 0FFFFFFFFFFFFFFFFh
0x18003ac7f  mov     [rbp+5C0h+packageRelativeApplicationIdLength], eax
0x18003ac82  mov     eax, [rbp+5C0h+arg_28]
0x18003ac88  mov     [rbp+5C0h+var_5F4], eax
0x18003ac8b  mov     rax, [rbp+5C0h+arg_40]
0x18003ac92  mov     [rbp+5C0h+var_570], rax
0x18003ac96  mov     rax, [rbp+5C0h+arg_48]
0x18003ac9d  mov     [rbp+5C0h+hProfile], rax
0x18003aca1  mov     eax, [rbp+5C0h+arg_50]
0x18003aca7  mov     [rbp+5C0h+var_5FC], eax
0x18003acaa  mov     rax, [rbp+5C0h+arg_58]
0x18003acb1  mov     [rbp+5C0h+var_598], rax
0x18003acb5  mov     rax, [rbp+5C0h+arg_60]
0x18003acbc  mov     [rbp+5C0h+var_618], rax
0x18003acc0  xor     eax, eax
0x18003acc2  mov     [rbp+5C0h+pAsync], rcx
0x18003acc6  mov     r13d, eax
0x18003acc9  lea     rcx, [rbp+5C0h+PerformanceCount]; lpPerformanceCount
0x18003acd0  mov     [rbp+5C0h+var_604], eax
0x18003acd3  mov     [rbp+5C0h+var_5D0], eax
0x18003acd6  mov     [rbp+5C0h+var_638], eax
0x18003acd9  mov     [rbp+5C0h+var_5B0], eax
0x18003acdc  mov     [rbp+5C0h+var_548], rax
0x18003ace0  mov     [rbp+5C0h+var_528], rax
0x18003ace7  mov     [rbp+5C0h+hToken], rax
0x18003aceb  mov     [rbp+5C0h+Handle], rax
0x18003acf2  mov     [rbp+5C0h+token], rax
0x18003acf6  mov     [rbp+5C0h+var_558], rax
0x18003acfa  mov     [rbp+5C0h+var_560], rax
0x18003acfe  mov     [rbp+5C0h+var_628], eax
0x18003ad01  mov     [rbp+5C0h+var_5F0], eax
0x18003ad04  mov     [rbp+5C0h+var_63C], al
0x18003ad07  mov     [rbp+5C0h+var_5B8], rax
0x18003ad0b  mov     [rbp+5C0h+var_5C8], eax
0x18003ad0e  mov     [rbp+5C0h+var_5CC], eax
0x18003ad11  mov     [rbp+5C0h+packageFamilyNameLength], eax
0x18003ad14  mov     qword ptr [rbp+5C0h+Frequency], rax
0x18003ad1b  mov     qword ptr [rbp+5C0h+PerformanceCount], rax
0x18003ad22  mov     qword ptr [rbp+5C0h+var_510], rax
0x18003ad29  mov     [rbp+5C0h+var_5A0], rax
0x18003ad2d  mov     [rbp+5C0h+var_538], r9
0x18003ad34  mov     [rbp+5C0h+var_540], r8
0x18003ad3b  mov     [rbp+5C0h+var_518], rdx
0x18003ad42  mov     [rbp+5C0h+var_568], r14
0x18003ad46  mov     [rbp+5C0h+var_530], rbx
0x18003ad4d  mov     [rbp+5C0h+lpFileName], r8
0x18003ad51  mov     [rbp+5C0h+var_5E8], r9
0x18003ad55  mov     [rbp+5C0h+hMem], rbx
0x18003ad59  mov     [rbp+5C0h+var_590], 1
0x18003ad60  mov     [rbp+5C0h+var_608], 6
0x18003ad67  call    cs:__imp_QueryPerformanceCounter
0x18003ad6e  nop     dword ptr [rax+rax+00h]
0x18003ad73  lea     rcx, [rbp+5C0h+Frequency]; lpFrequency
0x18003ad7a  call    cs:__imp_QueryPerformanceFrequency
0x18003ad81  nop     dword ptr [rax+rax+00h]
0x18003ad86  xor     edx, edx; Val
0x18003ad88  lea     rcx, [rbp+5C0h+var_490]; void *
0x18003ad8f  mov     r8d, 81h; Size
0x18003ad95  call    memset_0
0x18003ad9a  xor     eax, eax
0x18003ad9c  lea     rsi, aNull_0; "NULL"
0x18003ada3  cmp     rbx, rax
0x18003ada6  cmovz   rbx, rsi
0x18003adaa  cmp     r15, rax
0x18003adad  cmovz   r12, rsi
0x18003adb1  cmp     rdi, rax
0x18003adb4  jz      short loc_18003ADC0
0x18003adb6  mov     rcx, rdi; unsigned __int16 *
0x18003adb9  call    ?AipJustFileName@@YAPEBGPEBG@Z; AipJustFileName(ushort const *)
0x18003adbe  jmp     short loc_18003ADC3
0x18003adc0  mov     rax, rsi
0x18003adc3  mov     r9d, dword ptr [rbp+5C0h+hProfile]
0x18003adc7  lea     r8, aHwndXDwclientf; "++. hwnd = %x dwClientFlags = %x dwCrea"...
0x18003adce  xor     ecx, ecx
0x18003add0  lea     rdx, aRailaunchadmin; "RAiLaunchAdminProcess"
0x18003add7  cmp     r14, rcx
0x18003adda  lea     rcx, [rbp+5C0h+var_490]
0x18003ade1  mov     [rsp+700h+lpValue], rcx
0x18003ade6  lea     rcx, [rbp+5C0h+var_4E0]
0x18003aded  mov     [rsp+700h+var_6B0], rbx
0x18003adf2  cmovz   r14, rsi
0x18003adf6  mov     ebx, [rbp+5C0h+packageRelativeApplicationIdLength]
0x18003adf9  mov     [rsp+700h+var_6B8], r12
0x18003adfe  mov     r12d, [rbp+5C0h+var_5F4]
0x18003ae02  mov     [rsp+700h+var_6C0], rax
0x18003ae07  mov     eax, [rbp+5C0h+var_5FC]
0x18003ae0a  mov     [rsp+700h+var_6C8], r14
0x18003ae0f  mov     dword ptr [rsp+700h+hTemplateFile], eax
0x18003ae13  mov     [rsp+700h+dwFlagsAndAttributes], r12d
0x18003ae18  mov     [rsp+700h+dwCreationDisposition], ebx
0x18003ae1c  call    ?WatchCurrentThread@LUATelemetry@@SA?AVActivityThreadWatcher@wil@@PEBD0ZZ; LUATelemetry::WatchCurrentThread(char const *,char const *,...)
0x18003ae21  mov     rcx, cs:?g_pLaunchAdminProcessActivityTelemetryRateLimiter@@3V?$unique_ptr@VRateLimiter@@U?$default_delete@VRateLimiter@@@wistd@@@wistd@@A; this
0x18003ae28  test    rcx, rcx
0x18003ae2b  jz      short loc_18003AE8A
0x18003ae2d  call    ?RequestPermission@RateLimiter@@QEAAHXZ; RateLimiter::RequestPermission(void)
0x18003ae32  test    eax, eax
0x18003ae34  jz      short loc_18003AE8A
0x18003ae36  mov     ecx, 90h; Size
0x18003ae3b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003ae40  xor     edi, edi
0x18003ae42  test    rax, rax
0x18003ae45  jz      short loc_18003AE54
0x18003ae47  mov     rcx, rax
0x18003ae4a  call    ??0TraceLoggingCorrelationVector@@QEAA@UTraceLoggingCorrelationVectorV2_t@@@Z; TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(TraceLoggingCorrelationVectorV2_t)
0x18003ae4f  mov     rbx, rax
0x18003ae52  jmp     short loc_18003AE57
0x18003ae54  mov     rbx, rdi
0x18003ae57  mov     rdx, rdi
0x18003ae5a  lock xadd [rbx+88h], rdx; unsigned __int64
0x18003ae63  lea     r8, [rbp+5C0h+var_490]; char *
0x18003ae6a  mov     rcx, rbx; this
0x18003ae6d  call    ?ToStringImpl@TraceLoggingCorrelationVector@@AEAA_N_KPEAD@Z; TraceLoggingCorrelationVector::ToStringImpl(unsigned __int64,char *)
0x18003ae72  test    rbx, rbx
0x18003ae75  jz      short loc_18003AE7F
0x18003ae77  mov     rcx, rbx; Block
0x18003ae7a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18003ae7f  mov     ebx, [rbp+5C0h+packageRelativeApplicationIdLength]
0x18003ae82  mov     r15, [rbp+5C0h+var_5E8]
0x18003ae86  mov     rdi, [rbp+5C0h+lpFileName]
0x18003ae8a  mov     r8, cs:WPP_GLOBAL_Control
0x18003ae91  lea     rax, WPP_GLOBAL_Control
0x18003ae98  cmp     r8, rax
0x18003ae9b  jz      short loc_18003AF03
0x18003ae9d  test    byte ptr [r8+1Ch], 1
0x18003aea2  jz      short loc_18003AF03
0x18003aea4  mov     rcx, [rbp+5C0h+hMem]
0x18003aea8  lea     r9, [rbp+5C0h+var_490]
0x18003aeaf  mov     [rsp+700h+lpValue], r9
0x18003aeb4  test    rcx, rcx
0x18003aeb7  mov     r9d, dword ptr [rbp+5C0h+hProfile]
0x18003aebb  mov     rdx, rsi
0x18003aebe  cmovnz  rdx, rcx
0x18003aec2  mov     rax, rsi
0x18003aec5  mov     [rsp+700h+var_6B0], rdx
0x18003aeca  test    r15, r15
0x18003aecd  mov     rcx, rsi
0x18003aed0  cmovnz  rcx, r15
0x18003aed4  test    rdi, rdi
0x18003aed7  mov     [rsp+700h+var_6B8], rcx
0x18003aedc  mov     rcx, [r8+10h]
0x18003aee0  cmovnz  rax, rdi
0x18003aee4  mov     [rsp+700h+var_6C0], rax
0x18003aee9  mov     eax, [rbp+5C0h+var_5FC]
0x18003aeec  mov     [rsp+700h+var_6C8], r14
0x18003aef1  mov     dword ptr [rsp+700h+hTemplateFile], eax
0x18003aef5  mov     [rsp+700h+dwFlagsAndAttributes], r12d
0x18003aefa  mov     [rsp+700h+dwCreationDisposition], ebx
0x18003aefe  call    WPP_SF_DDDDSSSSs
0x18003af03  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_4155280696@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_4155280696@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_4155280696> `wil::Feature<__WilFeatureTraits_Feature_4155280696>::GetImpl(void)'::`2'::impl
0x18003af0a  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_4155280696@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_4155280696>::__private_IsEnabled(void)
0x18003af0f  xor     r12d, r12d
0x18003af12  or      r14, 0FFFFFFFFFFFFFFFFh
0x18003af16  test    al, al
0x18003af18  jz      short loc_18003AF47
0x18003af1a  lea     rcx, [rbp+5C0h+var_610]
0x18003af1e  mov     r8, r14
0x18003af21  mov     rdx, rdi
0x18003af24  test    rdi, rdi
0x18003af27  jnz     short loc_18003AF2C
0x18003af29  mov     rdx, r15
0x18003af2c  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x18003af31  lea     rdx, [rbp+5C0h+var_610]
0x18003af35  lea     rcx, [rbp+5C0h+var_5A0]
0x18003af39  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x18003af3e  lea     rcx, [rbp+5C0h+var_610]
0x18003af42  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18003af47  test    rdi, rdi
0x18003af4a  jnz     loc_18003AFE7
0x18003af50  test    r15, r15
0x18003af53  jnz     loc_18003AFF2
0x18003af59  mov     [rbp+5C0h+Reply], 57h ; 'W'
0x18003af60  mov     r12, [rbp+5C0h+token]
0x18003af64  mov     rbx, [rbp+5C0h+hObject]
0x18003af68  mov     rsi, [rbp+5C0h+pAsync]
0x18003af6c  mov     r14, [rbp+5C0h+var_618]
0x18003af70  lea     rcx, [rbp+5C0h+var_510]; lpPerformanceCount
0x18003af77  call    cs:__imp_QueryPerformanceCounter
0x18003af7e  nop     dword ptr [rax+rax+00h]
0x18003af83  mov     rax, qword ptr [rbp+5C0h+var_510]
0x18003af8a  sub     rax, qword ptr [rbp+5C0h+PerformanceCount]
0x18003af91  imul    rax, 3E8h
0x18003af98  cqo
0x18003af9a  idiv    qword ptr [rbp+5C0h+Frequency]
0x18003afa1  mov     [rbp+5C0h+var_570], rax
0x18003afa5  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_4155280696@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_4155280696@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_4155280696> `wil::Feature<__WilFeatureTraits_Feature_4155280696>::GetImpl(void)'::`2'::impl
0x18003afac  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_4155280696@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_4155280696>::__private_IsEnabled(void)
0x18003afb1  xor     r13d, r13d
0x18003afb4  test    al, al
0x18003afb6  mov     eax, [rbp+5C0h+var_5CC]
0x18003afb9  mov     dword ptr [rbp+5C0h+var_610], eax
0x18003afbc  jz      loc_18003BC41
0x18003afc2  mov     rax, [rbp+5C0h+var_5A0]
0x18003afc6  mov     [rbp+5C0h+var_598], rax
0x18003afca  mov     eax, [rbp+5C0h+var_608]
0x18003afcd  mov     [rbp+5C0h+var_5D8], eax
0x18003afd0  mov     eax, [rbp+5C0h+Reply]
0x18003afd3  cmp     eax, 4C7h
0x18003afd8  jnz     loc_18003BBD6
0x18003afde  mov     [rbp+5C0h+var_628], r13d
0x18003afe2  jmp     loc_18003BBE5
0x18003afe7  mov     rcx, rdi; unsigned __int16 *
0x18003afea  call    ?AipJustFileName@@YAPEBGPEBG@Z; AipJustFileName(ushort const *)
0x18003afef  mov     rsi, rax
0x18003aff2  mov     rdx, rsi; unsigned __int16 *
0x18003aff5  mov     [rbp+5C0h+var_548], rsi
0x18003aff9  lea     rcx, AppInfo_PerfTrack_Elevation_EXE_Start; struct _EVENT_DESCRIPTOR *
0x18003b000  call    ?AiLogPerfTrackEventEx@@YAKPEBU_EVENT_DESCRIPTOR@@PEBG@Z; AiLogPerfTrackEventEx(_EVENT_DESCRIPTOR const *,ushort const *)
0x18003b005  mov     dword ptr [rbp+5C0h+var_610], eax
0x18003b008  test    rdi, rdi
0x18003b00b  jz      short loc_18003B01A
0x18003b00d  mov     r13, r14
0x18003b010  inc     r13
0x18003b013  cmp     [rdi+r13*2], r12w
0x18003b018  jnz     short loc_18003B010
0x18003b01a  test    r15, r15
0x18003b01d  jz      short loc_18003B02B
0x18003b01f  inc     r14
0x18003b022  cmp     [r15+r14*2], r12w
0x18003b027  jnz     short loc_18003B01F
0x18003b029  jmp     short loc_18003B02F
0x18003b02b  mov     r14, [rbp+5C0h+var_558]
0x18003b02f  mov     eax, 7FFFh
0x18003b034  cmp     r13, rax
0x18003b037  ja      loc_18003AF59
0x18003b03d  cmp     r14, rax
0x18003b040  ja      loc_18003AF59
0x18003b046  lea     rcx, [rbp+5C0h+var_590]
0x18003b04a  call    cs:__imp_CheckElevationEnabled
0x18003b051  nop     dword ptr [rax+rax+00h]
0x18003b056  mov     [rbp+5C0h+Reply], eax
0x18003b059  test    eax, eax
0x18003b05b  jnz     loc_18003AF60
0x18003b061  mov     rcx, [rbp+5C0h+var_518]; void *
0x18003b068  lea     rax, [rbp+5C0h+var_628]
0x18003b06c  lea     r9, [rbp+5C0h+var_5D0]; unsigned int *
0x18003b070  mov     qword ptr [rsp+700h+dwCreationDisposition], rax; unsigned int *
0x18003b075  lea     r8, [rbp+5C0h+token]; void **
0x18003b079  lea     rdx, [rbp+5C0h+Handle]; void **
0x18003b080  call    ?AiGetClientInformation@@YAKPEAXPEAPEAX1PEAK2@Z; AiGetClientInformation(void *,void * *,void * *,ulong *,ulong *)
0x18003b085  mov     [rbp+5C0h+Reply], eax
0x18003b088  test    eax, eax
0x18003b08a  jnz     loc_18003AF60
0x18003b090  lea     rdx, [rbp+5C0h+var_5CC]
0x18003b094  lea     rcx, [rbp+5C0h+packageFamilyNameLength]
0x18003b098  call    LUAGetUACPromptPolicy
0x18003b09d  test    eax, eax
0x18003b09f  jns     short loc_18003B0B7
0x18003b0a1  mov     ecx, eax; Status
0x18003b0a3  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x18003b0aa  nop     dword ptr [rax+rax+00h]
0x18003b0af  mov     [rbp+5C0h+Reply], eax
0x18003b0b2  jmp     loc_18003AF60
0x18003b0b7  mov     [rbp+5C0h+packageFamilyNameLength], r12d
0x18003b0bb  lea     rdx, [rbp+5C0h+packageFamilyNameLength]; int *
0x18003b0bf  mov     r12, [rbp+5C0h+token]
0x18003b0c3  mov     rcx, r12; void *
0x18003b0c6  call    ?AiCheckForElevatedUser@@YAJPEAXPEAH@Z; AiCheckForElevatedUser(void *,int *)
0x18003b0cb  test    eax, eax
0x18003b0cd  jns     short loc_18003B0E5
0x18003b0cf  mov     ecx, eax; Status
0x18003b0d1  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x18003b0d8  nop     dword ptr [rax+rax+00h]
0x18003b0dd  mov     [rbp+5C0h+Reply], eax
0x18003b0e0  jmp     loc_18003AF64
0x18003b0e5  mov     edx, [rbp+5C0h+packageFamilyNameLength]; int
0x18003b0e8  lea     r8, [rbp+5C0h+var_5C8]; int *
0x18003b0ec  mov     rcx, r12; Handle
0x18003b0ef  call    ?AiCheckForAdminUser@@YAJPEAXHPEAH@Z; AiCheckForAdminUser(void *,int,int *)
0x18003b0f4  test    eax, eax
0x18003b0f6  js      short loc_18003B0CF
0x18003b0f8  test    bl, 8
0x18003b0fb  jz      loc_18003B1D3
0x18003b101  mov     r8, [rbp+5C0h+var_538]; unsigned __int16 *
0x18003b108  lea     rax, [rbp+5C0h+hMem]
0x18003b10c  mov     rcx, [rbp+5C0h+var_540]; unsigned __int16 *
0x18003b113  lea     r9, [rbp+5C0h+var_5E8]; unsigned __int16 **
0x18003b117  mov     qword ptr [rsp+700h+dwFlagsAndAttributes], rax; unsigned __int16 **
0x18003b11c  lea     rdx, [rbp+5C0h+lpFileName]; unsigned __int16 **
0x18003b120  mov     rax, [rbp+5C0h+var_530]
0x18003b127  mov     qword ptr [rsp+700h+dwCreationDisposition], rax; unsigned __int16 *
0x18003b12c  call    ?AiConvertWow64Paths@@YAKPEBGPEAPEBGPEAGPEAPEAG01@Z; AiConvertWow64Paths(ushort const *,ushort const * *,ushort *,ushort * *,ushort const *,ushort const * *)
  ... truncated ...
```
