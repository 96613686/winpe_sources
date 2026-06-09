# RAiLaunchAdminProcess

- ea: `0x18003a8b0`
- end: `0x18003b8f7`
- name: `RAiLaunchAdminProcess`
- size: `4167`
- prototype: `void __fastcall(struct _RPC_ASYNC_STATE *, void *, unsigned __int16 *, unsigned __int16 *, UINT32, unsigned int, unsigned __int16 *, unsigned __int16 *, struct _APPINFO_STARTUPINFO *, void *, unsigned int, struct _PROCESS_INFORMATION *, unsigned int *)`
- caller_count: `0`
- callee_count: `47`
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
- `0x18001fd94`
- `0x180022b74`
- `0x180022bb0`
- `0x1800234a0`
- `0x18002487c`
- `0x180026840`
- `0x180026de4`
- `0x180027224`
- `0x1800273c0`
- `0x18002a1d8`
- `0x180033f00`
- `0x1800343e4`
- `0x18003854c`
- `0x1800385b8`
- `0x180038670`
- `0x1800393e0`
- `0x180039518`
- `0x18003a8b0`
- `0x18003bdd0`
- `0x18003ccb0`
- `0x180041eb4`
- `0x1800437ec`
- `0x180043a2c`
- `0x1800444ba`
- `0x1800444e0`

## import_xrefs

- `RPCRT4!RpcAsyncCompleteCall` at `0x18003b889`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18003b889`
- `RPCRT4!RpcImpersonateClient` at `0x18003ad8a`
- `RPCRT4!RpcImpersonateClient` at `0x18003ad8a`
- `RPCRT4!RpcRevertToSelf` at `0x18003ae84`
- `RPCRT4!RpcRevertToSelf` at `0x18003b105`
- `RPCRT4!RpcRevertToSelf` at `0x18003b22b`
- `RPCRT4!RpcRevertToSelf` at `0x18003b287`
- `RPCRT4!RpcRevertToSelf` at `0x18003b2f5`
- `RPCRT4!RpcRevertToSelf` at `0x18003ae84`
- `RPCRT4!RpcRevertToSelf` at `0x18003b105`
- `RPCRT4!RpcRevertToSelf` at `0x18003b22b`
- `RPCRT4!RpcRevertToSelf` at `0x18003b287`
- `RPCRT4!RpcRevertToSelf` at `0x18003b2f5`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18003b61e`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18003b61e`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18003b65d`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18003b66b`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18003b65d`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18003b66b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ade8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ade8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003b7a0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003b7a0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003b7b5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003b7ca`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003b7e3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003b7f3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003b803`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003b7b5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003b7ca`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003b7e3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003b7f3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003b803`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18003adce`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18003adce`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x18003a9f2`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x18003a9f2`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18003a9df`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18003ad20`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18003a9df`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18003ad20`
- `api-ms-win-core-kernel32-private-l1-1-0!CheckElevation` at `0x18003b25a`
- `api-ms-win-core-kernel32-private-l1-1-0!CheckElevation` at `0x18003b25a`
- `api-ms-win-core-kernel32-private-l1-1-0!CheckElevationEnabled` at `0x18003ac08`
- `api-ms-win-core-kernel32-private-l1-1-0!CheckElevationEnabled` at `0x18003ac08`
- `api-ms-win-appmodel-runtime-l1-1-1!GetApplicationUserModelIdFromToken` at `0x18003b445`
- `api-ms-win-appmodel-runtime-l1-1-1!GetApplicationUserModelIdFromToken` at `0x18003b445`
- `api-ms-win-appmodel-runtime-l1-1-1!ParseApplicationUserModelId` at `0x18003b489`
- `api-ms-win-appmodel-runtime-l1-1-1!ParseApplicationUserModelId` at `0x18003b489`
- `api-ms-win-appmodel-runtime-l1-1-1!GetPackageFullNameFromToken` at `0x18003b3e7`
- `api-ms-win-appmodel-runtime-l1-1-1!GetPackageFullNameFromToken` at `0x18003b3e7`
- `api-ms-win-appmodel-runtime-l1-1-0!PackageFamilyNameFromFullName` at `0x18003af52`
- `api-ms-win-appmodel-runtime-l1-1-0!PackageFamilyNameFromFullName` at `0x18003af52`
- `ntdll!NtClose` at `0x18003b81a`
- `ntdll!NtClose` at `0x18003b833`
- `ntdll!NtClose` at `0x18003b848`
- `ntdll!NtClose` at `0x18003b81a`
- `ntdll!NtClose` at `0x18003b833`
- `ntdll!NtClose` at `0x18003b848`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18003ac5b`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18003ac5b`
- `USERENV!UnloadUserProfile` at `0x18003b609`
- `USERENV!UnloadUserProfile` at `0x18003b684`
- `USERENV!UnloadUserProfile` at `0x18003b609`
- `USERENV!UnloadUserProfile` at `0x18003b684`
- `ext-ms-win-desktopappx-l1-1-6!VerifyFileIsTrustedAndInPackage` at `0x18003b405`
- `ext-ms-win-desktopappx-l1-1-6!VerifyFileIsTrustedAndInPackage` at `0x18003b405`
- `ext-ms-win-appmodel-activation-l1-1-1!RegisterAppXPackageIfNecessary2` at `0x18003b646`
- `ext-ms-win-appmodel-activation-l1-1-1!RegisterAppXPackageIfNecessary2` at `0x18003b646`
- `ext-ms-win-appmodel-appexecutionalias-l1-1-0!GetAppExecutionAliasApplicationUserModelIdEx` at `0x18003afdc`
- `ext-ms-win-appmodel-appexecutionalias-l1-1-0!GetAppExecutionAliasApplicationUserModelIdEx` at `0x18003afdc`
- `ext-ms-win-appmodel-appexecutionalias-l1-1-0!LoadAppExecutionAliasInfoEx` at `0x18003af1b`
- `ext-ms-win-appmodel-appexecutionalias-l1-1-0!LoadAppExecutionAliasInfoEx` at `0x18003af1b`
- `ext-ms-win-appmodel-appexecutionalias-l1-1-0!FreeAppExecutionAliasInfoEx` at `0x18003b85d`
- `ext-ms-win-appmodel-appexecutionalias-l1-1-0!FreeAppExecutionAliasInfoEx` at `0x18003b85d`
- `ext-ms-win-appmodel-appexecutionalias-l1-1-0!OpenAppExecutionAliasForUserEx` at `0x18003afab`
- `ext-ms-win-appmodel-appexecutionalias-l1-1-0!OpenAppExecutionAliasForUserEx` at `0x18003afab`
- `ext-ms-win-appmodel-appexecutionalias-l1-1-2!GetAppExecutionAliasPath` at `0x18003aeaf`
- `ext-ms-win-appmodel-appexecutionalias-l1-1-2!GetAppExecutionAliasPath` at `0x18003aefd`
- `ext-ms-win-appmodel-appexecutionalias-l1-1-2!GetAppExecutionAliasPath` at `0x18003aeaf`
- `ext-ms-win-appmodel-appexecutionalias-l1-1-2!GetAppExecutionAliasPath` at `0x18003aefd`
- `ext-ms-win-appmodel-appexecutionalias-l1-1-5!LoadAppExecutionAliasInfoEx2` at `0x18003ae41`
- `ext-ms-win-appmodel-appexecutionalias-l1-1-5!LoadAppExecutionAliasInfoEx2` at `0x18003ae41`

## string_xrefs

- `0x18003aa3f`: `++. hwnd = %x dwClientFlags = %x dwCreationFlags = %x dwTimeout = %x\n	lpDesktop = %ws\n	lpApplicationName = %ws\n	lpCommandLine = %ws\n	lpCurrentDirectory = %ws\n	lpCvStr = %s\n`

## pseudocode

```c
void __fastcall RAiLaunchAdminProcess(
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
        unsigned int *a13)
{
  const unsigned __int16 *v13; // r15
  const unsigned __int16 *v14; // rbx
  unsigned __int16 *v15; // r14
  const unsigned __int16 *v16; // rsi
  unsigned __int16 *v17; // r12
  unsigned int v18; // edi
  unsigned __int64 v19; // r13
  const unsigned __int16 *v20; // rax
  char v21; // bl
  void *v22; // rax
  volatile signed __int64 *v23; // rbx
  const unsigned __int16 *v24; // rdx
  const unsigned __int16 *v25; // rcx
  const unsigned __int16 *v26; // rax
  unsigned __int16 *v27; // rax
  unsigned __int64 v28; // rbx
  NTSTATUS v29; // eax
  signed int v30; // eax
  HANDLE v31; // r15
  unsigned int v32; // eax
  const unsigned __int16 *v33; // rsi
  unsigned int v34; // ebx
  unsigned int v35; // r13d
  LONGLONG v36; // r15
  const WCHAR *v37; // rsi
  DWORD LastError; // eax
  __int64 v39; // rbx
  int AppExecutionAliasPath; // eax
  int v41; // ebx
  const unsigned __int16 *v42; // rsi
  __int64 v43; // rcx
  unsigned __int16 v44; // ax
  const unsigned __int16 *v45; // rcx
  unsigned __int16 v46; // ax
  unsigned __int16 v47; // dx
  __int64 v48; // rax
  unsigned __int64 v49; // r15
  unsigned __int16 *v50; // rbx
  __int64 v51; // r8
  void *v52; // rdx
  unsigned __int16 *v53; // rcx
  const unsigned __int16 *v54; // rcx
  const unsigned __int16 *v55; // rcx
  const unsigned __int16 *v56; // rcx
  RPC_STATUS v57; // eax
  unsigned int v58; // eax
  unsigned int v59; // esi
  unsigned int v60; // eax
  const unsigned __int16 *v61; // rcx
  unsigned int v62; // eax
  wchar_t *v63; // rcx
  HLOCAL v64; // rax
  unsigned __int16 *v65; // rbx
  signed int v66; // eax
  HANDLE v67; // rax
  void *v68; // rdx
  LUATelemetry *v69; // rcx
  unsigned int *dwCreationDisposition; // [rsp+20h] [rbp-120h]
  unsigned __int16 *v71; // [rsp+50h] [rbp-F0h]
  signed int Reply; // [rsp+C0h] [rbp-80h] BYREF
  bool v73; // [rsp+C4h] [rbp-7Ch]
  unsigned int v74; // [rsp+C8h] [rbp-78h] BYREF
  unsigned int v75; // [rsp+D0h] [rbp-70h] BYREF
  UINT32 packageRelativeApplicationIdLength; // [rsp+D4h] [rbp-6Ch] BYREF
  unsigned int v77; // [rsp+D8h] [rbp-68h] BYREF
  unsigned int v78[2]; // [rsp+E0h] [rbp-60h] BYREF
  unsigned int v79; // [rsp+E8h] [rbp-58h] BYREF
  UINT32 packageFamilyNameLength; // [rsp+ECh] [rbp-54h] BYREF
  unsigned int v81; // [rsp+F0h] [rbp-50h]
  unsigned int v82; // [rsp+F8h] [rbp-48h] BYREF
  unsigned int v83; // [rsp+100h] [rbp-40h] BYREF
  HANDLE hToken; // [rsp+108h] [rbp-38h] BYREF
  unsigned __int16 *v85; // [rsp+110h] [rbp-30h] BYREF
  unsigned int v86; // [rsp+118h] [rbp-28h] BYREF
  HANDLE hProfile; // [rsp+120h] [rbp-20h] BYREF
  __int64 v88; // [rsp+128h] [rbp-18h] BYREF
  UINT32 v89[2]; // [rsp+130h] [rbp-10h] BYREF
  int v90; // [rsp+138h] [rbp-8h] BYREF
  unsigned int v91; // [rsp+13Ch] [rbp-4h] BYREF
  int v92; // [rsp+140h] [rbp+0h] BYREF
  int v93; // [rsp+144h] [rbp+4h] BYREF
  int v94; // [rsp+148h] [rbp+8h] BYREF
  HLOCAL hMem; // [rsp+150h] [rbp+10h] BYREF
  unsigned __int16 *v96; // [rsp+158h] [rbp+18h] BYREF
  HANDLE hObject; // [rsp+160h] [rbp+20h]
  unsigned __int16 *v98; // [rsp+168h] [rbp+28h]
  HLOCAL v99; // [rsp+170h] [rbp+30h] BYREF
  UINT32 packageFullNameLength; // [rsp+178h] [rbp+38h] BYREF
  UINT32 applicationUserModelIdLength; // [rsp+17Ch] [rbp+3Ch] BYREF
  unsigned __int16 *v102; // [rsp+180h] [rbp+40h]
  unsigned __int16 *v103; // [rsp+188h] [rbp+48h]
  unsigned __int16 *v104; // [rsp+190h] [rbp+50h]
  unsigned __int16 *v105; // [rsp+198h] [rbp+58h]
  HLOCAL v106; // [rsp+1A0h] [rbp+60h] BYREF
  HANDLE token; // [rsp+1A8h] [rbp+68h] BYREF
  HANDLE Handle; // [rsp+1B0h] [rbp+70h] BYREF
  void *v109; // [rsp+1B8h] [rbp+78h]
  struct _PROCESS_INFORMATION *v110; // [rsp+1C0h] [rbp+80h]
  struct _APPINFO_STARTUPINFO *v111; // [rsp+1C8h] [rbp+88h]
  LARGE_INTEGER v112; // [rsp+1D0h] [rbp+90h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+1D8h] [rbp+98h] BYREF
  LARGE_INTEGER Frequency; // [rsp+1E0h] [rbp+A0h] BYREF
  unsigned int *v115; // [rsp+1E8h] [rbp+A8h]
  PRPC_ASYNC_STATE pAsync; // [rsp+1F0h] [rbp+B0h]
  unsigned __int16 **v117; // [rsp+1F8h] [rbp+B8h] BYREF
  __int64 v118; // [rsp+200h] [rbp+C0h] BYREF
  char v119; // [rsp+208h] [rbp+C8h]
  char v120[80]; // [rsp+210h] [rbp+D0h] BYREF
  char Source[144]; // [rsp+260h] [rbp+120h] BYREF
  WCHAR packageFamilyName[72]; // [rsp+2F0h] [rbp+1B0h] BYREF
  WCHAR applicationUserModelId[136]; // [rsp+380h] [rbp+240h] BYREF
  WCHAR packageRelativeApplicationId[136]; // [rsp+490h] [rbp+350h] BYREF
  WCHAR packageFullName[128]; // [rsp+5A0h] [rbp+460h] BYREF

  v13 = a4;
  v14 = a7;
  v15 = a3;
  v16 = a8;
  v17 = a4;
  hObject = (HANDLE)-1LL;
  packageRelativeApplicationIdLength = a5;
  v81 = a6;
  v111 = a9;
  hProfile = a10;
  v79 = a11;
  v110 = a12;
  v115 = a13;
  pAsync = a1;
  v18 = 0;
  v77 = 0;
  v86 = 0;
  v19 = 0;
  v74 = 0;
  v90 = 0;
  v102 = 0;
  v106 = 0;
  hToken = 0;
  Handle = 0;
  token = 0;
  *(_QWORD *)v89 = 0;
  v99 = 0;
  v83 = 0;
  v82 = 0;
  v73 = 0;
  v88 = 0;
  v92 = 0;
  v91 = 0;
  packageFamilyNameLength = 0;
  Frequency.QuadPart = 0;
  PerformanceCount.QuadPart = 0;
  v112.QuadPart = 0;
  v104 = a4;
  v103 = a3;
  v109 = a2;
  v98 = a8;
  v105 = a7;
  v96 = a3;
  v85 = a4;
  hMem = a7;
  v93 = 1;
  v75 = 6;
  QueryPerformanceCounter(&PerformanceCount);
  QueryPerformanceFrequency(&Frequency);
  memset_0(Source, 0, 0x81u);
  if ( !a7 )
    v14 = L"NULL";
  if ( !v17 )
    v13 = L"NULL";
  if ( v15 )
    v20 = AipJustFileName(v15);
  else
    v20 = L"NULL";
  if ( !a8 )
    v16 = L"NULL";
  v71 = (unsigned __int16 *)v14;
  v21 = packageRelativeApplicationIdLength;
  LUATelemetry::WatchCurrentThread(
    v120,
    "RAiLaunchAdminProcess",
    "++. hwnd = %x dwClientFlags = %x dwCreationFlags = %x dwTimeout = %x\n"
    "\tlpDesktop = %ws\n"
    "\tlpApplicationName = %ws\n"
    "\tlpCommandLine = %ws\n"
    "\tlpCurrentDirectory = %ws\n"
    "\tlpCvStr = %s\n",
    (unsigned int)hProfile,
    packageRelativeApplicationIdLength,
    v81,
    v79,
    v16,
    v20,
    v13,
    v71,
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
    v17 = v85;
    v15 = v96;
    v18 = v74;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v24 = L"NULL";
    if ( hMem )
      v24 = (const unsigned __int16 *)hMem;
    v25 = L"NULL";
    v26 = L"NULL";
    if ( v17 )
      v25 = v17;
    if ( v15 )
      v26 = v15;
    WPP_SF_DDDDSSSSs(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      (_DWORD)v24,
      (_DWORD)WPP_GLOBAL_Control,
      (_DWORD)hProfile,
      v21,
      v81,
      v79,
      (__int64)v16,
      (__int64)v26,
      (__int64)v25,
      (__int64)v24,
      (__int64)Source);
  }
  if ( v15 )
  {
    v27 = (unsigned __int16 *)AipJustFileName(v15);
  }
  else
  {
    if ( !v17 )
    {
LABEL_58:
      Reply = 87;
      goto LABEL_59;
    }
    v27 = L"NULL";
  }
  v102 = v27;
  v78[0] = AiLogPerfTrackEventEx(&AppInfo_PerfTrack_Elevation_EXE_Start, v27);
  if ( v15 )
  {
    v19 = -1;
    do
      ++v19;
    while ( v15[v19] );
  }
  if ( v17 )
  {
    v28 = -1;
    do
      ++v28;
    while ( v17[v28] );
  }
  else
  {
    v28 = *(_QWORD *)v89;
  }
  if ( v19 > 0x7FFF || v28 > 0x7FFF )
    goto LABEL_58;
  Reply = CheckElevationEnabled(&v93);
  if ( !Reply )
  {
    Reply = AiGetClientInformation(v109, &Handle, &token, &v86, &v83);
    if ( !Reply )
    {
      v29 = LUAGetUACPromptPolicy(&packageFamilyNameLength, &v91);
      if ( v29 < 0
        || (v31 = token,
            packageFamilyNameLength = 0,
            v29 = AiCheckForElevatedUser(token, (int *)&packageFamilyNameLength),
            v29 < 0)
        || (v29 = AiCheckForAdminUser(v31, packageFamilyNameLength, &v92), v29 < 0) )
      {
        v30 = RtlNtStatusToDosErrorNoTeb(v29);
      }
      else
      {
        if ( (packageRelativeApplicationIdLength & 8) != 0 )
        {
          v32 = AiConvertWow64Paths(
                  v103,
                  (const unsigned __int16 **)&v96,
                  v104,
                  &v85,
                  v105,
                  (const unsigned __int16 **)&hMem);
          v15 = v96;
          Reply = v32;
          if ( v32 )
          {
            v17 = v85;
            goto LABEL_59;
          }
          if ( v96 )
          {
            v19 = -1;
            do
              ++v19;
            while ( v96[v19] );
          }
          v17 = v85;
          if ( v85 )
          {
            v28 = -1;
            do
              ++v28;
            while ( v85[v28] );
          }
          if ( v19 > 0x7FFF || v28 > 0x7FFF )
            goto LABEL_58;
        }
        if ( !v93 )
        {
          v59 = v86;
          v65 = v98;
          goto LABEL_187;
        }
        v30 = RpcImpersonateClient(0);
        if ( !v30 )
        {
          v37 = v17;
          if ( v15 )
            v37 = v15;
          hObject = CreateFileW(v37, 0xA0000000, 5u, 0, 3u, 0x80u, 0);
          if ( hObject == (HANDLE)-1LL )
          {
            LastError = GetLastError();
            Reply = LastError;
            if ( LastError != 1920 && LastError != 5 || !(unsigned __int8)IsLoadAppExecutionAliasInfoExPresent() )
              goto LABEL_112;
            *(_QWORD *)v78 = 0;
            if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AppExAliasAbsPath2>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_AppExAliasAbsPath2>::GetImpl'::`2'::impl)
              && (unsigned __int8)IsLoadAppExecutionAliasInfoEx2Present()
              && (int)LoadAppExecutionAliasInfoEx2(v37, v31, 0, &v88) >= 0 )
            {
              wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
                &v82,
                v37,
                -1);
              wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
                v78,
                &v82);
              wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v82);
              v39 = *(_QWORD *)v78;
              if ( !*(_QWORD *)v78 )
              {
LABEL_76:
                RpcRevertToSelf();
LABEL_77:
                wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(v78);
                goto LABEL_59;
              }
            }
            else
            {
              v82 = 0;
              AppExecutionAliasPath = GetAppExecutionAliasPath(v37, v31, 0, &v82);
              if ( WIN32_FROM_HRESULT(AppExecutionAliasPath) != 122 )
                goto LABEL_76;
              wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
                &v74,
                0,
                v82);
              wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
                v78,
                &v74);
              wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v74);
              v39 = *(_QWORD *)v78;
              if ( (int)GetAppExecutionAliasPath(v37, v31, *(_QWORD *)v78, &v82) < 0 )
                goto LABEL_76;
              if ( (int)LoadAppExecutionAliasInfoEx(v39, v31, &v88) < 0 )
                goto LABEL_111;
            }
            if ( !*(_DWORD *)(v88 + 32) )
            {
              packageFamilyNameLength = 65;
              if ( !PackageFamilyNameFromFullName(*(PCWSTR *)v88, &packageFamilyNameLength, packageFamilyName) )
              {
                memset_0(packageRelativeApplicationId, 0, 0x106u);
                v83 = 131;
                v117 = &v85;
                v85 = 0;
                v118 = 0;
                v119 = 1;
                v41 = OpenAppExecutionAliasForUserEx(v39, v31, &v118);
                wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CloseAppExecutionAliasEx(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CloseAppExecutionAliasEx(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(&v117);
                if ( v41 >= 0
                  && (int)GetAppExecutionAliasApplicationUserModelIdEx(v85, packageRelativeApplicationId, &v83) >= 0 )
                {
                  v42 = v17;
                  LODWORD(v43) = 0;
                  if ( v17 )
                  {
                    v44 = *v17;
                    if ( *v17 == 34 )
                    {
                      v45 = v17 + 1;
                      v46 = v17[1];
                      if ( v46 != 34 )
                      {
                        v47 = v17[1];
                        do
                        {
                          v46 = v47;
                          if ( !v47 )
                            break;
                          v46 = *++v45;
                          v47 = *v45;
                        }
                        while ( *v45 != 34 );
                      }
                      v42 = v45 + 1;
                      if ( v46 != 34 )
                        v42 = v45;
                    }
                    else
                    {
                      while ( v44 != 32 && v44 )
                        v44 = *++v42;
                    }
                    v43 = -1;
                    do
                      ++v43;
                    while ( v42[v43] );
                  }
                  v48 = -1;
                  do
                    ++v48;
                  while ( *(_WORD *)(*(_QWORD *)(v88 + 8) + 2 * v48) );
                  v49 = 2 * ((int)v43 + (int)v48) + 6;
                  wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
                    v89,
                    0,
                    v49);
                  v50 = *(unsigned __int16 **)v89;
                  if ( *(_QWORD *)v89
                    && StringCbCopyW(*(unsigned __int16 **)v89, v49, L"\"") >= 0
                    && StringCbCatW(v50, v49, *(const unsigned __int16 **)(v88 + 8)) >= 0
                    && StringCbCatW(v50, v49, L"\"") >= 0 )
                  {
                    if ( !v42 || StringCbCatW(v50, v49, v42) >= 0 )
                    {
                      v51 = v88;
                      v52 = v109;
                      *v115 = v75;
                      AipLaunchProcessWithIdentityHelper(
                        pAsync,
                        v52,
                        *(unsigned __int16 **)(v51 + 8),
                        v50,
                        packageRelativeApplicationIdLength | 0x200,
                        v81,
                        (unsigned __int16 *)hMem,
                        v98,
                        v111,
                        packageFamilyName,
                        packageRelativeApplicationId,
                        hProfile,
                        v79,
                        0x11u,
                        0,
                        0,
                        0,
                        0,
                        0,
                        Source,
                        &v92,
                        (enum UACPROMPT_POLICY *)&v91,
                        (struct _APPINFO_PROCESS_INFORMATION *)v110);
                      v73 = 1;
                    }
                    RpcRevertToSelf();
                    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(v89);
                    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CloseAppExecutionAliasEx(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CloseAppExecutionAliasEx(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v85);
                    goto LABEL_77;
                  }
                  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(v89);
                }
                wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CloseAppExecutionAliasEx(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CloseAppExecutionAliasEx(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v85);
              }
            }
LABEL_111:
            wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(v78);
LABEL_112:
            RpcRevertToSelf();
            goto LABEL_59;
          }
          v53 = v17;
          if ( v15 )
            v53 = v15;
          Reply = CheckElevation(v53, &v90, 0, &v77, &v75);
          if ( Reply )
            goto LABEL_112;
          v54 = v17;
          if ( v15 )
            v54 = v15;
          Reply = AiCheckSecureApplicationDirectory(v54, &v74);
          if ( Reply )
          {
            RpcRevertToSelf();
LABEL_120:
            v18 = v74;
            goto LABEL_59;
          }
          if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_2045735225>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_2045735225>::GetImpl'::`2'::impl)
            && v77 - 16 <= 2
            && (unsigned int)LUAIsShadowAdminEnabled() )
          {
            v55 = v17;
            if ( v15 )
              v55 = v15;
            AipCheckAssistiveTechnologyList(v55, &v74);
          }
          v56 = v17;
          if ( v15 )
            v56 = v15;
          AiIsEXESafeToAutoApprove(v56, hObject, v17, &v74, (unsigned __int16 **)&v106);
          v57 = RpcRevertToSelf();
          if ( v57 )
          {
            Reply = v57;
            goto LABEL_120;
          }
          v18 = v74;
          if ( (v90 & 8) != 0 )
          {
            v18 = v74 | 0x1000;
            v74 |= 0x1000u;
          }
          if ( (v90 & 4) != 0 )
          {
            v18 |= 2u;
            v74 = v18;
          }
          v58 = v77;
          if ( v77 - 16 <= 2 )
          {
            if ( v77 >= 3 )
            {
              v58 = v77 - 16;
              v77 -= 16;
            }
            v18 |= 0x8000Cu;
            v74 = v18;
          }
          if ( !v58 && (v18 & 4) != 0 )
          {
            v59 = v86;
          }
          else
          {
            v59 = v86;
            if ( !AiIsElevationAllowedForSession(v86) )
            {
              Reply = 50;
              goto LABEL_59;
            }
            v58 = v77;
          }
          if ( (packageRelativeApplicationIdLength & 1) != 0 )
          {
            if ( v58 <= 1 )
            {
              v18 |= 0x200u;
              v74 = v18;
            }
            v77 = 2;
            v75 = 6;
          }
          if ( (packageRelativeApplicationIdLength & 0x10) != 0 )
          {
            v18 |= 0x800u;
            v74 = v18;
          }
          if ( (packageRelativeApplicationIdLength & 0x80u) != 0 )
          {
            v18 |= 0x100000u;
            v74 = v18;
          }
          if ( (packageRelativeApplicationIdLength & 0x100) != 0 )
          {
            v82 = 8;
          }
          else
          {
            v60 = v82;
            if ( (packageRelativeApplicationIdLength & 0x800) != 0 )
              v60 = 1024;
            v82 = v60;
          }
          v94 = 0;
          packageFullNameLength = 128;
          if ( !GetPackageFullNameFromToken(v31, &packageFullNameLength, packageFullName) )
            VerifyFileIsTrustedAndInPackage(v15, packageFullName, &v94);
          memset_0(applicationUserModelId, 0, 0x106u);
          applicationUserModelIdLength = 131;
          if ( v94 )
          {
            if ( GetApplicationUserModelIdFromToken(v31, &applicationUserModelIdLength, applicationUserModelId) )
              goto LABEL_59;
            v89[0] = 65;
            packageRelativeApplicationIdLength = 65;
            if ( ParseApplicationUserModelId(
                   applicationUserModelId,
                   v89,
                   packageFamilyName,
                   &packageRelativeApplicationIdLength,
                   packageRelativeApplicationId) < 0 )
              goto LABEL_59;
            v75 = 8;
            v61 = v17;
            if ( v15 )
              v61 = v15;
            v62 = AiBuildPackagedAppParams(
                    v61,
                    v19,
                    v17,
                    v28,
                    v83,
                    packageFamilyName,
                    applicationUserModelId,
                    (struct _CONSENTUI_PARAM_HEADER **)&v99);
          }
          else
          {
            v63 = v17;
            if ( v15 )
              v63 = v15;
            v62 = AiBuildEXEParams(
                    v63,
                    hObject,
                    v15,
                    v19,
                    v17,
                    v28,
                    (const unsigned __int16 *)v106,
                    v83,
                    (struct _CONSENTUI_PARAM_HEADER **)&v99);
          }
          Reply = v62;
          if ( v62 )
            goto LABEL_59;
          v64 = v99;
          v65 = v98;
          *((_DWORD *)v99 + 13) = v78[0];
          v66 = AiCheckLUA(v77, &v74, v75, v31, v64, v65, hProfile, v59, v79, Source, &hToken);
          v18 = v74;
          Reply = v66;
          if ( v66 )
            goto LABEL_59;
          v67 = hToken;
          if ( !hToken )
            goto LABEL_188;
          v18 = v74 | 1;
          if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShadowAdmin>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_ShadowAdmin>::GetImpl'::`2'::impl) )
          {
            v81 &= 0xFFFFFFFC;
            if ( v75 == 8 && ((v18 & 0x20) == 0 || (v18 & 0x8000000) != 0 && (unsigned int)LUAIsShadowAdminEnabled()) )
            {
              hProfile = 0;
              Reply = AipLoadUserProfile(hToken, &hProfile);
              if ( Reply )
                goto LABEL_178;
              ImpersonateLoggedOnUser(hToken);
              v79 = 0;
              dwCreationDisposition = &v79;
              if ( (int)RegisterAppXPackageIfNecessary2(0, applicationUserModelId, 0, 0) < 0 )
              {
                Reply = 15669;
                RevertToSelf();
LABEL_178:
                if ( hProfile )
                  UnloadUserProfile(hToken, hProfile);
                goto LABEL_59;
              }
              RevertToSelf();
              if ( hProfile )
                UnloadUserProfile(hToken, hProfile);
            }
          }
          Reply = AipApplyAdminProcessPackageClaimsPolicy(&hToken, v31, v18);
          if ( Reply )
            goto LABEL_59;
LABEL_187:
          v67 = hToken;
LABEL_188:
          v68 = v31;
          if ( v67 )
            v68 = v67;
          v30 = AiLaunchProcess(
                  Handle,
                  v68,
                  hObject,
                  v18,
                  v15,
                  v17,
                  v81,
                  (const unsigned __int16 *)hMem,
                  v65,
                  v111,
                  v59,
                  0,
                  v82,
                  0,
                  0,
                  0,
                  v110);
        }
      }
      Reply = v30;
    }
  }
LABEL_59:
  QueryPerformanceCounter(&v112);
  v33 = v17;
  v34 = Reply;
  v35 = v91;
  v36 = 1000 * (v112.QuadPart - PerformanceCount.QuadPart) / Frequency.QuadPart;
  if ( v15 )
    v33 = v15;
  v78[0] = v75;
  if ( Reply == 1223 )
  {
    v34 = 0;
  }
  else if ( Reply > 0 )
  {
    v34 = (unsigned __int16)Reply | 0x80070000;
  }
  if ( LUATelemetry::IsEnabled(0, 1000 * (v112.QuadPart - PerformanceCount.QuadPart) % Frequency.QuadPart) )
  {
    LUATelemetry::Instance();
    LUATelemetry::LaunchAdminProcess_(v69, v34, v18, v78[0], Reply, v102, v33, v92, v35, v36, v73, Source);
  }
  if ( hObject != (HANDLE)-1LL )
    CloseHandle(hObject);
  if ( v15 != v103 )
    LocalFree(v15);
  if ( v17 != v104 )
    LocalFree(v17);
  if ( hMem != v105 )
    LocalFree(hMem);
  LocalFree(v99);
  LocalFree(v106);
  if ( hToken )
  {
    NtClose(hToken);
    hToken = 0;
  }
  if ( token )
    NtClose(token);
  if ( Handle )
    NtClose(Handle);
  if ( v88 )
  {
    FreeAppExecutionAliasInfoEx(v88);
    v88 = 0;
  }
  if ( !v73 )
  {
    *v115 = v75;
    RpcAsyncCompleteCall(pAsync, &Reply);
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_D(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      12,
      &WPP_063934a2c6ca383cf9bd298d4f16efdb_Traceguids,
      (unsigned int)Reply,
      dwCreationDisposition);
  wil::ActivityThreadWatcher::~ActivityThreadWatcher((wil::ActivityThreadWatcher *)v120);
}

```

## disassembly

```asm
0x18003a8b0  push    rbp
0x18003a8b2  push    rbx
0x18003a8b3  push    rsi
0x18003a8b4  push    rdi
0x18003a8b5  push    r12
0x18003a8b7  push    r13
0x18003a8b9  push    r14
0x18003a8bb  push    r15
0x18003a8bd  lea     rbp, [rsp-578h]
0x18003a8c5  sub     rsp, 6B8h
0x18003a8cc  mov     rax, cs:__security_cookie
0x18003a8d3  xor     rax, rsp
0x18003a8d6  mov     [rbp+5B0h+var_50], rax
0x18003a8dd  mov     eax, [rbp+5B0h+arg_20]
0x18003a8e3  mov     r15, r9
0x18003a8e6  mov     rbx, [rbp+5B0h+arg_30]
0x18003a8ed  mov     r14, r8
0x18003a8f0  mov     rsi, [rbp+5B0h+arg_38]
0x18003a8f7  mov     r12, r9
0x18003a8fa  or      [rbp+5B0h+hObject], 0FFFFFFFFFFFFFFFFh
0x18003a8ff  mov     [rbp+5B0h+packageRelativeApplicationIdLength], eax
0x18003a902  mov     eax, [rbp+5B0h+arg_28]
0x18003a908  mov     [rbp+5B0h+var_600], eax
0x18003a90b  mov     rax, [rbp+5B0h+arg_40]
0x18003a912  mov     [rbp+5B0h+var_528], rax
0x18003a919  mov     rax, [rbp+5B0h+arg_48]
0x18003a920  mov     [rbp+5B0h+hProfile], rax
0x18003a924  mov     eax, [rbp+5B0h+arg_50]
0x18003a92a  mov     [rbp+5B0h+var_608], eax
0x18003a92d  mov     rax, [rbp+5B0h+arg_58]
0x18003a934  mov     [rbp+5B0h+var_530], rax
0x18003a93b  mov     rax, [rbp+5B0h+arg_60]
0x18003a942  mov     [rbp+5B0h+var_508], rax
0x18003a949  xor     eax, eax
0x18003a94b  mov     [rbp+5B0h+pAsync], rcx
0x18003a952  mov     edi, eax
0x18003a954  lea     rcx, [rbp+5B0h+PerformanceCount]; lpPerformanceCount
0x18003a95b  mov     [rbp+5B0h+var_618], eax
0x18003a95e  mov     [rbp+5B0h+var_5D8], eax
0x18003a961  mov     r13d, eax
0x18003a964  mov     [rbp+5B0h+var_628], eax
0x18003a967  mov     [rbp+5B0h+var_5B8], eax
0x18003a96a  mov     [rbp+5B0h+var_570], rax
0x18003a96e  mov     [rbp+5B0h+var_550], rax
0x18003a972  mov     [rbp+5B0h+hToken], rax
0x18003a976  mov     [rbp+5B0h+Handle], rax
0x18003a97a  mov     [rbp+5B0h+token], rax
0x18003a97e  mov     qword ptr [rbp+5B0h+var_5C0], rax
0x18003a982  mov     [rbp+5B0h+var_580], rax
0x18003a986  mov     [rbp+5B0h+var_5F0], eax
0x18003a989  mov     [rbp+5B0h+var_5F8], eax
0x18003a98c  mov     [rbp+5B0h+var_62C], al
0x18003a98f  mov     [rbp+5B0h+var_5C8], rax
0x18003a993  mov     [rbp+5B0h+var_5B0], eax
0x18003a996  mov     [rbp+5B0h+var_5B4], eax
0x18003a999  mov     [rbp+5B0h+packageFamilyNameLength], eax
0x18003a99c  mov     qword ptr [rbp+5B0h+Frequency], rax
0x18003a9a3  mov     qword ptr [rbp+5B0h+PerformanceCount], rax
0x18003a9aa  mov     qword ptr [rbp+5B0h+var_520], rax
0x18003a9b1  mov     [rbp+5B0h+var_560], r9
0x18003a9b5  mov     [rbp+5B0h+var_568], r8
0x18003a9b9  mov     [rbp+5B0h+var_538], rdx
0x18003a9bd  mov     [rbp+5B0h+var_588], rsi
0x18003a9c1  mov     [rbp+5B0h+var_558], rbx
0x18003a9c5  mov     [rbp+5B0h+var_598], r8
0x18003a9c9  mov     [rbp+5B0h+var_5E0], r9
0x18003a9cd  mov     [rbp+5B0h+hMem], rbx
0x18003a9d1  mov     [rbp+5B0h+var_5AC], 1
0x18003a9d8  mov     [rbp+5B0h+var_620], 6
0x18003a9df  call    cs:__imp_QueryPerformanceCounter
0x18003a9e6  nop     dword ptr [rax+rax+00h]
0x18003a9eb  lea     rcx, [rbp+5B0h+Frequency]; lpFrequency
0x18003a9f2  call    cs:__imp_QueryPerformanceFrequency
0x18003a9f9  nop     dword ptr [rax+rax+00h]
0x18003a9fe  xor     edx, edx; Val
0x18003aa00  lea     rcx, [rbp+5B0h+var_490]; void *
0x18003aa07  mov     r8d, 81h; Size
0x18003aa0d  call    memset_0
0x18003aa12  xor     eax, eax
0x18003aa14  lea     rcx, aNull_0; "NULL"
0x18003aa1b  cmp     rbx, rax
0x18003aa1e  cmovz   rbx, rcx
0x18003aa22  cmp     r12, rax
0x18003aa25  cmovz   r15, rcx
0x18003aa29  cmp     r14, rax
0x18003aa2c  jz      short loc_18003AA38
0x18003aa2e  mov     rcx, r14; unsigned __int16 *
0x18003aa31  call    ?AipJustFileName@@YAPEBGPEBG@Z; AipJustFileName(ushort const *)
0x18003aa36  jmp     short loc_18003AA3B
0x18003aa38  mov     rax, rcx
0x18003aa3b  mov     r9d, dword ptr [rbp+5B0h+hProfile]
0x18003aa3f  lea     r8, aHwndXDwclientf; "++. hwnd = %x dwClientFlags = %x dwCrea"...
0x18003aa46  xor     ecx, ecx
0x18003aa48  lea     rdx, aRailaunchadmin; "RAiLaunchAdminProcess"
0x18003aa4f  cmp     rsi, rcx
0x18003aa52  lea     rcx, aNull_0; "NULL"
0x18003aa59  cmovz   rsi, rcx
0x18003aa5d  lea     rcx, [rbp+5B0h+var_490]
0x18003aa64  mov     [rsp+6F0h+lpValue], rcx
0x18003aa69  lea     rcx, [rbp+5B0h+var_4E0]
0x18003aa70  mov     [rsp+6F0h+var_6A0], rbx
0x18003aa75  mov     ebx, [rbp+5B0h+packageRelativeApplicationIdLength]
0x18003aa78  mov     [rsp+6F0h+var_6A8], r15
0x18003aa7d  mov     r15d, [rbp+5B0h+var_600]
0x18003aa81  mov     [rsp+6F0h+var_6B0], rax
0x18003aa86  mov     eax, [rbp+5B0h+var_608]
0x18003aa89  mov     [rsp+6F0h+var_6B8], rsi
0x18003aa8e  mov     dword ptr [rsp+6F0h+hTemplateFile], eax
0x18003aa92  mov     [rsp+6F0h+dwFlagsAndAttributes], r15d
0x18003aa97  mov     [rsp+6F0h+dwCreationDisposition], ebx
0x18003aa9b  call    ?WatchCurrentThread@LUATelemetry@@SA?AVActivityThreadWatcher@wil@@PEBD0ZZ; LUATelemetry::WatchCurrentThread(char const *,char const *,...)
0x18003aaa0  mov     rcx, cs:?g_pLaunchAdminProcessActivityTelemetryRateLimiter@@3V?$unique_ptr@VRateLimiter@@U?$default_delete@VRateLimiter@@@wistd@@@wistd@@A; this
0x18003aaa7  test    rcx, rcx
0x18003aaaa  jz      short loc_18003AB0A
0x18003aaac  call    ?RequestPermission@RateLimiter@@QEAAHXZ; RateLimiter::RequestPermission(void)
0x18003aab1  test    eax, eax
0x18003aab3  jz      short loc_18003AB0A
0x18003aab5  mov     ecx, 90h; Size
0x18003aaba  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003aabf  test    rax, rax
0x18003aac2  jz      short loc_18003AAD1
0x18003aac4  mov     rcx, rax
0x18003aac7  call    ??0TraceLoggingCorrelationVector@@QEAA@UTraceLoggingCorrelationVectorV2_t@@@Z; TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(TraceLoggingCorrelationVectorV2_t)
0x18003aacc  mov     rbx, rax
0x18003aacf  jmp     short loc_18003AAD4
0x18003aad1  mov     rbx, rdi
0x18003aad4  mov     rdx, rdi
0x18003aad7  lock xadd [rbx+88h], rdx; unsigned __int64
0x18003aae0  lea     r8, [rbp+5B0h+var_490]; char *
0x18003aae7  mov     rcx, rbx; this
0x18003aaea  call    ?ToStringImpl@TraceLoggingCorrelationVector@@AEAA_N_KPEAD@Z; TraceLoggingCorrelationVector::ToStringImpl(unsigned __int64,char *)
0x18003aaef  test    rbx, rbx
0x18003aaf2  jz      short loc_18003AAFC
0x18003aaf4  mov     rcx, rbx; Block
0x18003aaf7  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18003aafc  mov     ebx, [rbp+5B0h+packageRelativeApplicationIdLength]
0x18003aaff  mov     r12, [rbp+5B0h+var_5E0]
0x18003ab03  mov     r14, [rbp+5B0h+var_598]
0x18003ab07  mov     edi, [rbp+5B0h+var_628]
0x18003ab0a  mov     r8, cs:WPP_GLOBAL_Control
0x18003ab11  lea     rax, WPP_GLOBAL_Control
0x18003ab18  cmp     r8, rax
0x18003ab1b  jz      short loc_18003AB8A
0x18003ab1d  test    byte ptr [r8+1Ch], 1
0x18003ab22  jz      short loc_18003AB8A
0x18003ab24  mov     rax, [rbp+5B0h+hMem]
0x18003ab28  lea     r10, aNull_0; "NULL"
0x18003ab2f  test    rax, rax
0x18003ab32  lea     r9, [rbp+5B0h+var_490]
0x18003ab39  mov     [rsp+6F0h+lpValue], r9
0x18003ab3e  mov     rdx, r10
0x18003ab41  mov     r9d, dword ptr [rbp+5B0h+hProfile]
0x18003ab45  cmovnz  rdx, rax
0x18003ab49  mov     [rsp+6F0h+var_6A0], rdx
0x18003ab4e  test    r12, r12
0x18003ab51  mov     rcx, r10
0x18003ab54  mov     rax, r10
0x18003ab57  cmovnz  rcx, r12
0x18003ab5b  test    r14, r14
0x18003ab5e  mov     [rsp+6F0h+var_6A8], rcx
0x18003ab63  mov     rcx, [r8+10h]
0x18003ab67  cmovnz  rax, r14
0x18003ab6b  mov     [rsp+6F0h+var_6B0], rax
0x18003ab70  mov     eax, [rbp+5B0h+var_608]
0x18003ab73  mov     [rsp+6F0h+var_6B8], rsi
0x18003ab78  mov     dword ptr [rsp+6F0h+hTemplateFile], eax
0x18003ab7c  mov     [rsp+6F0h+dwFlagsAndAttributes], r15d
0x18003ab81  mov     [rsp+6F0h+dwCreationDisposition], ebx
0x18003ab85  call    WPP_SF_DDDDSSSSs
0x18003ab8a  xor     esi, esi
0x18003ab8c  test    r14, r14
0x18003ab8f  jnz     short loc_18003ABA3
0x18003ab91  test    r12, r12
0x18003ab94  jz      loc_18003AD12
0x18003ab9a  lea     rax, aNull_0; "NULL"
0x18003aba1  jmp     short loc_18003ABAB
0x18003aba3  mov     rcx, r14; unsigned __int16 *
0x18003aba6  call    ?AipJustFileName@@YAPEBGPEBG@Z; AipJustFileName(ushort const *)
0x18003abab  mov     rdx, rax; unsigned __int16 *
0x18003abae  mov     [rbp+5B0h+var_570], rax
0x18003abb2  lea     rcx, AppInfo_PerfTrack_Elevation_EXE_Start; struct _EVENT_DESCRIPTOR *
0x18003abb9  call    ?AiLogPerfTrackEventEx@@YAKPEBU_EVENT_DESCRIPTOR@@PEBG@Z; AiLogPerfTrackEventEx(_EVENT_DESCRIPTOR const *,ushort const *)
0x18003abbe  mov     [rbp+5B0h+var_610], eax
0x18003abc1  test    r14, r14
0x18003abc4  jz      short loc_18003ABD4
0x18003abc6  or      r13, 0FFFFFFFFFFFFFFFFh
0x18003abca  inc     r13
0x18003abcd  cmp     [r14+r13*2], si
0x18003abd2  jnz     short loc_18003ABCA
0x18003abd4  test    r12, r12
0x18003abd7  jz      short loc_18003ABE9
0x18003abd9  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18003abdd  inc     rbx
0x18003abe0  cmp     [r12+rbx*2], si
0x18003abe5  jnz     short loc_18003ABDD
0x18003abe7  jmp     short loc_18003ABED
0x18003abe9  mov     rbx, qword ptr [rbp+5B0h+var_5C0]
0x18003abed  mov     eax, 7FFFh
0x18003abf2  cmp     r13, rax
0x18003abf5  ja      loc_18003AD12
0x18003abfb  cmp     rbx, rax
0x18003abfe  ja      loc_18003AD12
0x18003ac04  lea     rcx, [rbp+5B0h+var_5AC]
0x18003ac08  call    cs:__imp_CheckElevationEnabled
0x18003ac0f  nop     dword ptr [rax+rax+00h]
0x18003ac14  mov     [rbp+5B0h+Reply], eax
0x18003ac17  test    eax, eax
0x18003ac19  jnz     loc_18003AD19
0x18003ac1f  mov     rcx, [rbp+5B0h+var_538]; void *
0x18003ac23  lea     rax, [rbp+5B0h+var_5F0]
0x18003ac27  lea     r9, [rbp+5B0h+var_5D8]; unsigned int *
0x18003ac2b  mov     qword ptr [rsp+6F0h+dwCreationDisposition], rax; unsigned int *
0x18003ac30  lea     r8, [rbp+5B0h+token]; void **
0x18003ac34  lea     rdx, [rbp+5B0h+Handle]; void **
0x18003ac38  call    ?AiGetClientInformation@@YAKPEAXPEAPEAX1PEAK2@Z; AiGetClientInformation(void *,void * *,void * *,ulong *,ulong *)
0x18003ac3d  mov     [rbp+5B0h+Reply], eax
0x18003ac40  test    eax, eax
0x18003ac42  jnz     loc_18003AD19
0x18003ac48  lea     rdx, [rbp+5B0h+var_5B4]
0x18003ac4c  lea     rcx, [rbp+5B0h+packageFamilyNameLength]
0x18003ac50  call    LUAGetUACPromptPolicy
0x18003ac55  test    eax, eax
0x18003ac57  jns     short loc_18003AC6F
0x18003ac59  mov     ecx, eax; Status
0x18003ac5b  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x18003ac62  nop     dword ptr [rax+rax+00h]
0x18003ac67  mov     [rbp+5B0h+Reply], eax
0x18003ac6a  jmp     loc_18003AD19
0x18003ac6f  mov     r15, [rbp+5B0h+token]
0x18003ac73  lea     rdx, [rbp+5B0h+packageFamilyNameLength]; int *
0x18003ac77  mov     rcx, r15; void *
0x18003ac7a  mov     [rbp+5B0h+packageFamilyNameLength], esi
0x18003ac7d  call    ?AiCheckForElevatedUser@@YAJPEAXPEAH@Z; AiCheckForElevatedUser(void *,int *)
0x18003ac82  test    eax, eax
0x18003ac84  js      short loc_18003AC59
0x18003ac86  mov     edx, [rbp+5B0h+packageFamilyNameLength]; int
0x18003ac89  lea     r8, [rbp+5B0h+var_5B0]; int *
0x18003ac8d  mov     rcx, r15; Handle
0x18003ac90  call    ?AiCheckForAdminUser@@YAJPEAXHPEAH@Z; AiCheckForAdminUser(void *,int,int *)
0x18003ac95  test    eax, eax
0x18003ac97  js      short loc_18003AC59
0x18003ac99  test    byte ptr [rbp+5B0h+packageRelativeApplicationIdLength], 8
0x18003ac9d  jz      loc_18003AD7F
0x18003aca3  mov     r8, [rbp+5B0h+var_560]; unsigned __int16 *
0x18003aca7  lea     rax, [rbp+5B0h+hMem]
0x18003acab  mov     rcx, [rbp+5B0h+var_568]; unsigned __int16 *
0x18003acaf  lea     r9, [rbp+5B0h+var_5E0]; unsigned __int16 **
0x18003acb3  mov     qword ptr [rsp+6F0h+dwFlagsAndAttributes], rax; unsigned __int16 **
0x18003acb8  lea     rdx, [rbp+5B0h+var_598]; unsigned __int16 **
0x18003acbc  mov     rax, [rbp+5B0h+var_558]
0x18003acc0  mov     qword ptr [rsp+6F0h+dwCreationDisposition], rax; unsigned __int16 *
0x18003acc5  call    ?AiConvertWow64Paths@@YAKPEBGPEAPEBGPEAGPEAPEAG01@Z; AiConvertWow64Paths(ushort const *,ushort const * *,ushort *,ushort * *,ushort const *,ushort const * *)
0x18003acca  mov     r14, [rbp+5B0h+var_598]
0x18003acce  mov     [rbp+5B0h+Reply], eax
0x18003acd1  test    eax, eax
0x18003acd3  jnz     loc_18003AD79
0x18003acd9  test    r14, r14
0x18003acdc  jz      short loc_18003ACEC
0x18003acde  or      r13, 0FFFFFFFFFFFFFFFFh
0x18003ace2  inc     r13
0x18003ace5  cmp     [r14+r13*2], si
0x18003acea  jnz     short loc_18003ACE2
0x18003acec  mov     r12, [rbp+5B0h+var_5E0]
0x18003acf0  test    r12, r12
0x18003acf3  jz      short loc_18003AD03
0x18003acf5  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18003acf9  inc     rbx
0x18003acfc  cmp     [r12+rbx*2], si
0x18003ad01  jnz     short loc_18003ACF9
0x18003ad03  mov     eax, 7FFFh
0x18003ad08  cmp     r13, rax
0x18003ad0b  ja      short loc_18003AD12
0x18003ad0d  cmp     rbx, rax
0x18003ad10  jbe     short loc_18003AD7F
0x18003ad12  mov     [rbp+5B0h+Reply], 57h ; 'W'
0x18003ad19  lea     rcx, [rbp+5B0h+var_520]; lpPerformanceCount
0x18003ad20  call    cs:__imp_QueryPerformanceCounter
0x18003ad27  nop     dword ptr [rax+rax+00h]
0x18003ad2c  mov     rax, qword ptr [rbp+5B0h+var_520]
0x18003ad33  xor     ecx, ecx; unsigned __int8
0x18003ad35  sub     rax, qword ptr [rbp+5B0h+PerformanceCount]
0x18003ad3c  mov     rsi, r12
0x18003ad3f  mov     ebx, [rbp+5B0h+Reply]
0x18003ad42  mov     r13d, [rbp+5B0h+var_5B4]
0x18003ad46  imul    rax, 3E8h
0x18003ad4d  cqo; unsigned __int64
0x18003ad4f  idiv    qword ptr [rbp+5B0h+Frequency]
0x18003ad56  test    r14, r14
0x18003ad59  mov     r15, rax
0x18003ad5c  mov     eax, [rbp+5B0h+var_620]
0x18003ad5f  cmovnz  rsi, r14
0x18003ad63  mov     [rbp+5B0h+var_610], eax
0x18003ad66  cmp     ebx, 4C7h
0x18003ad6c  jnz     loc_18003B731
0x18003ad72  mov     ebx, ecx
0x18003ad74  jmp     loc_18003B73E
0x18003ad79  mov     r12, [rbp+5B0h+var_5E0]
0x18003ad7d  jmp     short loc_18003AD19
0x18003ad7f  cmp     [rbp+5B0h+var_5AC], esi
0x18003ad82  jz      loc_18003B6AB
  ... truncated ...
```
