# AiLaunchProcess(void *,void *,void *,ulong,ushort const *,ushort *,ulong,ushort const *,ushort const *,_APPINFO_STARTUPINFO *,_STARTUPINFO_STDHANDLES *,_SECURITY_CAPABILITIES *,ulong,ushort *,ulong,AicAgenticFlags,void *,unsigned __int64,ushort const *,_PROCESS_INFORMATION *,ushort *)

- ea: `0x18002d8fc`
- end: `0x18002e7fc`
- name: `?AiLaunchProcess@@YAKPEAX00KPEBGPEAGK11PEAU_APPINFO_STARTUPINFO@@PEAU_STARTUPINFO_STDHANDLES@@PEAU_SECURITY_CAPABILITIES@@K2KW4AicAgenticFlags@@0_K1PEAU_PROCESS_INFORMATION@@2@Z`
- size: `3840`
- prototype: `__int64 __fastcall(void *, void *, void *, unsigned int, wchar_t *lpApplicationName, const WCHAR *, unsigned int, const WCHAR *, WCHAR *, __int64, __int64, __int64, unsigned int, void *, __int16, char, __int64, __int64, unsigned __int16 *, void **, WCHAR *)`
- caller_count: `4`
- callee_count: `30`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1800290b4`
- `0x18002ed98`
- `0x18003d070`
- `0x1800409a0`

## callees

- `0x180009540`
- `0x180009fc0`
- `0x18000c440`
- `0x18000ed20`
- `0x1800105c0`
- `0x1800113a4`
- `0x18001158c`
- `0x1800119b0`
- `0x18001a208`
- `0x18001b0d0`
- `0x18001b7c0`
- `0x18001b800`
- `0x18001b910`
- `0x1800204f0`
- `0x180026630`
- `0x180026f40`
- `0x180028838`
- `0x180029cf4`
- `0x18002a3b4`
- `0x18002bb18`
- `0x18002d8fc`
- `0x18002e804`
- `0x18003c1d4`
- `0x18003c77c`
- `0x18003e9e8`
- `0x18003ea48`
- `0x18003eb5c`
- `0x1800461e8`
- `0x180046e1a`
- `0x180046e50`

## import_xrefs

- `msvcrt!wcsstr` at `0x18002de3d`
- `msvcrt!wcsstr` at `0x18002de3d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002dbda`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002dd96`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002de04`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e49c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e516`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e5c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002dbda`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002dd96`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002de04`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e49c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e516`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e5c0`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x18002e6cf`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x18002e6cf`
- `api-ms-win-core-processthreads-l1-1-0!DeleteProcThreadAttributeList` at `0x18002e717`
- `api-ms-win-core-processthreads-l1-1-0!DeleteProcThreadAttributeList` at `0x18002e717`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002dcb5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002dcc2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002dcb5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002dcc2`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x18002e75f`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x18002e75f`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x18002df99`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x18002dfcd`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x18002e015`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x18002e05c`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x18002e0ba`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x18002e1df`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x18002df99`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x18002dfcd`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x18002e015`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x18002e05c`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x18002e0ba`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x18002e1df`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x18002dbce`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x18002dbce`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x18002e5b6`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x18002e5b6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002e74a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002e769`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002e778`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002e7d1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002e74a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002e769`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002e778`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002e7d1`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18002dce7`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18002dce7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002e799`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002e7c2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002e799`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002e7c2`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002dc83`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002e4dd`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002dc83`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002e4dd`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x18002e4c1`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x18002e50c`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x18002e4c1`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x18002e50c`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002e488`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002e488`
- `api-ms-win-core-appcompat-l1-1-1!BaseReadAppCompatDataForProcess` at `0x18002dd00`
- `api-ms-win-core-appcompat-l1-1-1!BaseReadAppCompatDataForProcess` at `0x18002dd00`
- `api-ms-win-core-appcompat-l1-1-1!BaseFreeAppCompatDataForProcess` at `0x18002e787`
- `api-ms-win-core-appcompat-l1-1-1!BaseFreeAppCompatDataForProcess` at `0x18002e787`
- `api-ms-win-appmodel-runtime-l1-1-1!GetApplicationUserModelIdFromToken` at `0x18002e34f`
- `api-ms-win-appmodel-runtime-l1-1-1!GetApplicationUserModelIdFromToken` at `0x18002e34f`
- `api-ms-win-core-psm-key-l1-1-0!PsmGetKeyFromToken` at `0x18002e325`
- `api-ms-win-core-psm-key-l1-1-0!PsmGetKeyFromToken` at `0x18002e325`
- `ntdll!NtClose` at `0x18002e7af`
- `ntdll!NtClose` at `0x18002e7af`
- `ntdll!NtDuplicateObject` at `0x18002e648`
- `ntdll!NtDuplicateObject` at `0x18002e692`
- `ntdll!NtDuplicateObject` at `0x18002e648`
- `ntdll!NtDuplicateObject` at `0x18002e692`
- `ntdll!RtlSetEnvironmentVar` at `0x18002dec8`
- `ntdll!RtlSetEnvironmentVar` at `0x18002dec8`
- `ntdll!NtDuplicateToken` at `0x18002dab9`
- `ntdll!NtDuplicateToken` at `0x18002dab9`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18002dac7`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18002ded6`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18002e654`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18002dac7`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18002ded6`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18002e654`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18002e29c`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18002e29c`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18002e5c8`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18002e5c8`
- `USERENV!DestroyEnvironmentBlock` at `0x18002dc57`
- `USERENV!DestroyEnvironmentBlock` at `0x18002e726`
- `USERENV!DestroyEnvironmentBlock` at `0x18002dc57`
- `USERENV!DestroyEnvironmentBlock` at `0x18002e726`
- `USERENV!UnloadUserProfile` at `0x18002e739`
- `USERENV!UnloadUserProfile` at `0x18002e739`
- `USERENV!CreateEnvironmentBlock` at `0x18002dc24`
- `USERENV!CreateEnvironmentBlock` at `0x18002dc24`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!MonitorFromPoint` at `0x18002e279`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!MonitorFromPoint` at `0x18002e279`
- `ext-ms-win-appcompat-apphelp-l1-1-1!__imp_SdbGetKnownSafeLayers` at `0x18002dd72`
- `ext-ms-win-appcompat-apphelp-l1-1-1!__imp_SdbGetKnownSafeLayers` at `0x18002dd72`

## string_xrefs

- `0x18002debd`: `__COMPAT_LAYER`

## pseudocode

```c
__int64 __fastcall AiLaunchProcess(
        void *a1,
        void *a2,
        void *a3,
        unsigned int a4,
        wchar_t *lpApplicationName,
        const WCHAR *a6,
        unsigned int a7,
        const WCHAR *a8,
        WCHAR *a9,
        __int64 a10,
        __int64 a11,
        __int64 a12,
        unsigned int a13,
        void *a14,
        __int16 a15,
        char a16,
        __int64 a17,
        __int64 a18,
        unsigned __int16 *a19,
        void **a20,
        WCHAR *a21)
{
  WCHAR *v21; // rsi
  unsigned int v23; // r12d
  unsigned __int16 *v24; // rdi
  int v25; // eax
  UINT ShouldElevateUIAApplication; // ebx
  unsigned __int16 *v27; // rdi
  char IsEnabled; // al
  unsigned int v29; // ecx
  int v30; // eax
  DWORD v31; // ecx
  ULONG LastError; // eax
  wchar_t *v33; // rdi
  HANDLE CurrentProcess; // rax
  HANDLE v35; // rdi
  void *v36; // rbx
  HANDLE v37; // rax
  int v38; // eax
  int v39; // r8d
  _QWORD *v40; // rcx
  char v41; // al
  int v42; // r8d
  DWORD v43; // eax
  const unsigned __int16 *v44; // r8
  __int64 v45; // rax
  NTSTATUS v46; // eax
  HANDLE *p_hSourceHandle; // r9
  __int64 v48; // rax
  int v49; // eax
  __int64 v50; // rax
  unsigned __int64 v51; // rcx
  struct _PROC_THREAD_ATTRIBUTE_LIST *v52; // rax
  __int64 v53; // rdx
  __int64 v54; // rcx
  const WCHAR *lpCurrentDirectory; // r13
  wil::TraceLoggingProvider *v56; // rax
  unsigned __int8 v57; // dl
  unsigned __int64 v58; // r8
  const WCHAR *v59; // rdi
  LPCWSTR v60; // r14
  WCHAR *v61; // rsi
  __int64 v62; // rax
  WCHAR *v63; // rax
  char v64; // r14
  BOOL v65; // eax
  const WCHAR *v66; // rsi
  HANDLE FileW; // rax
  void *v68; // r14
  DWORD FinalPathNameByHandleW; // eax
  DWORD v70; // r14d
  WCHAR *v71; // rax
  const WCHAR *v72; // r13
  DWORD v73; // r8d
  DWORD v74; // eax
  PHANDLE v75; // r15
  ACCESS_MASK v76; // edi
  int v77; // eax
  ULONG v78; // eax
  unsigned __int16 *hProfile; // [rsp+60h] [rbp-A0h]
  __int64 hFile; // [rsp+68h] [rbp-98h]
  WCHAR *hMem; // [rsp+70h] [rbp-90h]
  HANDLE hToken; // [rsp+78h] [rbp-88h] BYREF
  unsigned int v84; // [rsp+80h] [rbp-80h] BYREF
  ULONG Value; // [rsp+88h] [rbp-78h] BYREF
  LPVOID Environment; // [rsp+90h] [rbp-70h] BYREF
  UINT32 applicationUserModelIdLength; // [rsp+98h] [rbp-68h] BYREF
  int v88; // [rsp+9Ch] [rbp-64h] BYREF
  HANDLE hSourceHandle; // [rsp+A0h] [rbp-60h] BYREF
  wchar_t *Str; // [rsp+A8h] [rbp-58h]
  unsigned __int16 *v91; // [rsp+B0h] [rbp-50h] BYREF
  int v92; // [rsp+B8h] [rbp-48h] BYREF
  LPCWSTR lpFileName; // [rsp+C0h] [rbp-40h]
  WCHAR *v94; // [rsp+C8h] [rbp-38h] BYREF
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+D0h] [rbp-30h] BYREF
  LPCWSTR v96; // [rsp+E8h] [rbp-18h]
  HANDLE TargetHandle; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v98; // [rsp+F8h] [rbp-8h] BYREF
  WCHAR *v99; // [rsp+100h] [rbp+0h] BYREF
  __int64 v100; // [rsp+108h] [rbp+8h] BYREF
  void *v101; // [rsp+110h] [rbp+10h]
  PHANDLE v102; // [rsp+118h] [rbp+18h]
  ULONG_PTR Size; // [rsp+120h] [rbp+20h] BYREF
  PVOID lpValue; // [rsp+128h] [rbp+28h]
  HANDLE v105; // [rsp+130h] [rbp+30h]
  WCHAR *v106; // [rsp+138h] [rbp+38h]
  struct _STARTUPINFOW StartupInfo; // [rsp+140h] [rbp+40h] BYREF
  LPPROC_THREAD_ATTRIBUTE_LIST lpAttributeList; // [rsp+1A8h] [rbp+A8h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+1B0h] [rbp+B0h] BYREF
  _QWORD v110[3]; // [rsp+1E0h] [rbp+E0h] BYREF
  __int128 v111; // [rsp+1F8h] [rbp+F8h] BYREF
  int v112; // [rsp+210h] [rbp+110h] BYREF
  _BYTE v113[524]; // [rsp+214h] [rbp+114h] BYREF
  _BYTE v114[288]; // [rsp+420h] [rbp+320h] BYREF
  int v115; // [rsp+540h] [rbp+440h] BYREF
  char v116[332]; // [rsp+544h] [rbp+444h] BYREF
  WCHAR applicationUserModelId[136]; // [rsp+690h] [rbp+590h] BYREF
  _WORD v118[232]; // [rsp+7A0h] [rbp+6A0h] BYREF

  v21 = 0;
  v23 = a4;
  v24 = a19;
  lpFileName = a6;
  v102 = a20;
  v96 = a8;
  v106 = a9;
  v100 = a17;
  v94 = a21;
  v99 = a21;
  v101 = a3;
  v105 = a2;
  hSourceHandle = a1;
  hProfile = 0;
  v91 = 0;
  v84 = a4;
  lpValue = a14;
  Value = 0;
  Str = 0;
  TargetHandle = 0;
  hToken = 0;
  Environment = 0;
  *(_QWORD *)&StartupInfo.cb = 0;
  memset_0(&StartupInfo.lpReserved, 0, sizeof(struct _STARTUPINFOW));
  v115 = 0;
  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  memset_0(v116, 0, sizeof(v116));
  Size = 336;
  v98 = 0;
  v92 = 4;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  v111 = 0;
  memset_0(&v112, 0, 0x20Cu);
  memset_0(v114, 0, 0x114u);
  hFile = -1;
  hMem = 0;
  if ( (v23 & 0x80u) != 0 )
  {
    hToken = a2;
LABEL_6:
    ShouldElevateUIAApplication = 0;
    if ( (v23 & 4) != 0 )
    {
      ShouldElevateUIAApplication = AipShouldElevateUIAApplication(&v84);
      if ( ShouldElevateUIAApplication )
        goto LABEL_4;
      v23 = v84;
      if ( (v84 & 0x400) != 0 )
      {
        IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShadowAdmin>::__private_IsEnabled(
                      `wil::Feature<__WilFeatureTraits_Feature_ShadowAdmin>::GetImpl'::`2'::impl,
                      0);
        v29 = a7 & 0xFFFFFFFC;
        if ( !IsEnabled )
          v29 = a7;
        v84 = v29;
        ShouldElevateUIAApplication = LUASetUIAToken2(&hToken);
        if ( (unsigned int)LUAIsShadowAdminEnabled() )
          v23 |= 1u;
        if ( ShouldElevateUIAApplication )
          goto LABEL_4;
      }
      else
      {
        Value |= 2u;
        v84 = a7;
      }
    }
    else
    {
      v84 = a7;
    }
    v30 = 0;
    if ( hSourceHandle )
    {
      v30 = (a14 != 0) + 2;
      if ( (a15 & 6) != 0 )
        v30 = (a14 != 0) + 3;
    }
    if ( (v23 & 0x1800000) != 0 || (a16 & 4) != 0 )
      ++v30;
    applicationUserModelIdLength = a15 & 8;
    if ( (a15 & 8) != 0 || (a15 & 0x400) != 0 )
      ++v30;
    v31 = v30 + 1;
    if ( (a15 & 0x2000) == 0 )
      v31 = v30;
    v88 = v31;
    if ( v31 && !InitializeProcThreadAttributeList((LPPROC_THREAD_ATTRIBUTE_LIST)&v115, v31, 0, &Size) )
      goto LABEL_30;
    if ( !hSourceHandle )
    {
LABEL_106:
      v50 = v111;
      if ( (a16 & 4) != 0 )
      {
        v50 = v111 | 0x10000000;
        *(_QWORD *)&v111 = v111 | 0x10000000;
      }
      if ( (v23 & 0x800000) != 0 )
      {
        v50 |= 0x1000000000000000uLL;
        *(_QWORD *)&v111 = v50;
      }
      if ( (v23 & 0x1000000) != 0 )
      {
        if ( (v23 & 0x80u) != 0 )
        {
          v51 = 4144;
          *((_QWORD *)&v111 + 1) = 4144;
        }
        else
        {
          v51 = AipAutoApproveHardeningPolicy();
          *((_QWORD *)&v111 + 1) = v51;
          v50 = v111;
        }
      }
      else
      {
        v51 = *((_QWORD *)&v111 + 1);
      }
      if ( !v50 && !v51
        || UpdateProcThreadAttribute((LPPROC_THREAD_ATTRIBUTE_LIST)&v115, 0, 0x20007u, &v111, 0x10u, 0, 0) )
      {
        v52 = (struct _PROC_THREAD_ATTRIBUTE_LIST *)&v115;
        StartupInfo.cb = 112;
        if ( !v88 )
          v52 = lpAttributeList;
        lpAttributeList = v52;
        StartupInfo.lpDesktop = v106;
        if ( a10 )
        {
          StartupInfo.lpTitle = *(LPWSTR *)a10;
          StartupInfo.dwX = *(_DWORD *)(a10 + 8);
          StartupInfo.dwY = *(_DWORD *)(a10 + 12);
          StartupInfo.dwXSize = *(_DWORD *)(a10 + 16);
          StartupInfo.dwYSize = *(_DWORD *)(a10 + 20);
          StartupInfo.dwXCountChars = *(_DWORD *)(a10 + 24);
          StartupInfo.dwYCountChars = *(_DWORD *)(a10 + 28);
          StartupInfo.dwFillAttribute = *(_DWORD *)(a10 + 32);
          StartupInfo.wShowWindow = *(_WORD *)(a10 + 40);
          StartupInfo.dwFlags = *(_DWORD *)(a10 + 36) & 0xFFFFFCFF;
          if ( (StartupInfo.dwFlags & 0x400) != 0 )
            StartupInfo.hStdOutput = MonitorFromPoint(*(POINT *)(a10 + 44), 2u);
        }
        else
        {
          StartupInfo.dwFlags = 1;
          StartupInfo.wShowWindow = 1;
        }
        if ( ImpersonateLoggedOnUser(hToken) )
        {
          if ( (v23 & 0x4004) == 0x4000 || (lpCurrentDirectory = v96, !AipCanAccessCurrentDirectory(v96)) )
          {
            lpCurrentDirectory = 0;
            v96 = 0;
          }
          if ( a18 )
          {
            v56 = (wil::TraceLoggingProvider *)wil::details::static_lazy<AAMTraceProvider>::get(
                                                 v54,
                                                 _lambda_7e8ef9e9b596109f338594047241dcdf_::_lambda_invoker_cdecl_);
            if ( wil::TraceLoggingProvider::IsEnabled_(v56, v57, v58) )
            {
              memset_0(v118, 0, sizeof(v118));
              v88 = 464;
              if ( (int)PsmGetKeyFromToken(hToken, v118, &v88, 0) < 0 )
                v118[0] = 0;
              applicationUserModelIdLength = 131;
              if ( GetApplicationUserModelIdFromToken(hToken, &applicationUserModelIdLength, applicationUserModelId) )
                applicationUserModelId[0] = 0;
              AAMTraceProvider::AAMActivationCreateProcess<unsigned short (&)[232],unsigned short (&)[131],unsigned __int64 &>(
                v118,
                applicationUserModelId,
                &a18);
            }
          }
          v59 = lpApplicationName;
          if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShadowAdmin>::__private_IsEnabled(
                                  `wil::Feature<__WilFeatureTraits_Feature_ShadowAdmin>::GetImpl'::`2'::impl,
                                  v53) )
          {
            v60 = lpFileName;
            v61 = (WCHAR *)lpFileName;
            if ( (unsigned int)LUAIsShadowAdminEnabled() && v94 )
            {
              v62 = -1;
              do
                ++v62;
              while ( v94[v62] );
              if ( (unsigned __int64)(v62 - 3) > 0x104 )
              {
                if ( lpApplicationName )
                  v59 = v94;
                else
                  v61 = v94;
                v63 = lpApplicationName;
                if ( !lpApplicationName )
                  v63 = (WCHAR *)v60;
                v94 = v63;
                LUATelemetry::LongPathApplicationElevation<unsigned short const *,unsigned short * &>(&v94, &v99);
              }
              else if ( lpApplicationName )
              {
                v59 = v94 + 4;
              }
              else
              {
                v61 = v94 + 4;
              }
            }
            v64 = v84;
            v65 = CreateProcessAsUserW(
                    hToken,
                    v59,
                    v61,
                    0,
                    0,
                    0,
                    v84 | 0x80004,
                    Environment,
                    lpCurrentDirectory,
                    &StartupInfo,
                    &ProcessInformation);
            goto LABEL_172;
          }
          if ( !(unsigned int)LUAIsShadowAdminEnabled() || (v23 & 0x20000000) != 0 )
            goto LABEL_171;
          v66 = lpApplicationName;
          if ( !lpApplicationName )
            v66 = lpFileName;
          FileW = CreateFileW(v66, 0x80000000, 5u, 0, 3u, 0x2000000u, 0);
          hFile = (__int64)FileW;
          v68 = FileW;
          if ( FileW == (HANDLE)-1LL )
          {
            ShouldElevateUIAApplication = GetLastError();
LABEL_157:
            v21 = hMem;
            v27 = hProfile;
            goto LABEL_195;
          }
          FinalPathNameByHandleW = GetFinalPathNameByHandleW(FileW, 0, 0, 8u);
          v70 = FinalPathNameByHandleW;
          if ( FinalPathNameByHandleW )
          {
            v71 = (WCHAR *)LocalAlloc(0x40u, 2LL * (FinalPathNameByHandleW + 1));
            hMem = v71;
            v72 = v71;
            v99 = v71;
            if ( !v71 )
              goto LABEL_42;
            v73 = v70;
            v68 = (void *)hFile;
            v74 = GetFinalPathNameByHandleW((HANDLE)hFile, v71, v73, 8u);
            if ( v74 )
            {
              if ( v74 - 3 > 0x104 )
              {
                if ( lpApplicationName )
                  v59 = v72;
                else
                  lpFileName = v72;
                v94 = (WCHAR *)v66;
                LUATelemetry::LongPathApplicationElevation<unsigned short const *,unsigned short * &>(&v94, &v99);
              }
              else if ( lpApplicationName )
              {
                v59 = v72 + 4;
              }
              else
              {
                lpFileName = v72 + 4;
              }
            }
            else
            {
              ShouldElevateUIAApplication = GetLastError();
              if ( ShouldElevateUIAApplication != 5 )
                goto LABEL_157;
              ShouldElevateUIAApplication = 0;
            }
LABEL_171:
            v64 = v84;
            v61 = (WCHAR *)lpFileName;
            v65 = CreateProcessAsUserW(
                    hToken,
                    v59,
                    (LPWSTR)lpFileName,
                    0,
                    0,
                    0,
                    v84 | 0x80004,
                    Environment,
                    v96,
                    &StartupInfo,
                    &ProcessInformation);
LABEL_172:
            if ( !v65 )
              ShouldElevateUIAApplication = GetLastError();
            RevertToSelf();
            if ( ShouldElevateUIAApplication )
              goto LABEL_192;
            if ( !lpApplicationName )
              v59 = v61;
            ShouldElevateUIAApplication = AipValidateLaunchedProcess(v59, ProcessInformation.hProcess, v101);
            if ( ShouldElevateUIAApplication )
              goto LABEL_192;
            v75 = v102;
            if ( !hSourceHandle )
            {
              *v102 = ProcessInformation.hProcess;
              v75[1] = ProcessInformation.hThread;
              ProcessInformation.hProcess = 0;
              ProcessInformation.hThread = 0;
LABEL_191:
              *((_DWORD *)v75 + 4) = ProcessInformation.dwProcessId;
              *((_DWORD *)v75 + 5) = ProcessInformation.dwThreadId;
              goto LABEL_192;
            }
            v76 = (v23 & 0x401) != 0 ? 0x20000100 : 0;
            Value = (v23 & 0x401) == 0 ? 2 : 0;
            v77 = NtDuplicateObject(
                    (HANDLE)0xFFFFFFFFFFFFFFFFLL,
                    ProcessInformation.hProcess,
                    hSourceHandle,
                    v102,
                    v76,
                    0,
                    Value);
            if ( v77 < 0
              || ((v23 & 0x401) == 0 ? (v78 = Value) : (v76 = 536870914, v78 = 0, Value = 0),
                  v77 = NtDuplicateObject(
                          (HANDLE)0xFFFFFFFFFFFFFFFFLL,
                          ProcessInformation.hThread,
                          hSourceHandle,
                          v75 + 1,
                          v76,
                          0,
                          v78),
                  v77 < 0) )
            {
              LastError = RtlNtStatusToDosErrorNoTeb(v77);
              goto LABEL_31;
            }
            if ( (v23 & 1) == 0 )
            {
LABEL_188:
              if ( (v64 & 4) == 0 )
                ResumeThread(ProcessInformation.hThread);
              goto LABEL_191;
            }
            v27 = hProfile;
            ShouldElevateUIAApplication = AipAddProfileReference(a13, hToken, hProfile);
            if ( !ShouldElevateUIAApplication )
            {
              hProfile = 0;
              goto LABEL_188;
            }
LABEL_193:
            v21 = hMem;
            goto LABEL_194;
          }
        }
      }
LABEL_30:
      LastError = GetLastError();
LABEL_31:
      ShouldElevateUIAApplication = LastError;
LABEL_192:
      v27 = hProfile;
      goto LABEL_193;
    }
    if ( (v23 & 1) != 0 )
    {
      ShouldElevateUIAApplication = AipLoadUserProfile(hToken, (void **)&v91);
      if ( ShouldElevateUIAApplication )
      {
        v27 = v91;
        goto LABEL_193;
      }
      hProfile = v91;
    }
    if ( !CreateEnvironmentBlock(&Environment, hToken, 0) )
      goto LABEL_30;
    if ( v24 )
    {
      v91 = 0;
      ShouldElevateUIAApplication = AipAddDebugEnvironmentBlock((const unsigned __int16 *)Environment, v24, &v91);
      if ( ShouldElevateUIAApplication )
        goto LABEL_192;
      DestroyEnvironmentBlock(Environment);
      Environment = v91;
    }
    ShouldElevateUIAApplication = AipCheckForAppPathsKey(lpApplicationName, &Environment);
    if ( ShouldElevateUIAApplication )
      goto LABEL_192;
    Str = (wchar_t *)LocalAlloc(0x40u, 0x218u);
    v33 = Str;
    if ( !Str )
    {
LABEL_42:
      ShouldElevateUIAApplication = 8;
      goto LABEL_192;
    }
    if ( (unsigned __int8)IsSdbGetKnownSafeLayersPresent() )
    {
      CurrentProcess = GetCurrentProcess();
      v35 = hSourceHandle;
      v36 = CurrentProcess;
      v37 = GetCurrentProcess();
      if ( DuplicateHandle(v37, v35, v36, &TargetHandle, 0x410u, 0, 0) )
      {
        v38 = BaseReadAppCompatDataForProcess(TargetHandle, &v98, 0);
        if ( v38 )
        {
          v40 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
          {
LABEL_54:
            v33 = Str;
            if ( (unsigned int)SdbGetKnownSafeLayers(v98, 256, Str) )
            {
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              {
                WPP_SF_SS(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  16,
                  (unsigned int)WPP_b23fa736e9853481a42645a0499c03f5_Traceguids,
                  (_DWORD)lpApplicationName,
                  (__int64)v33);
              }
            }
            else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                   && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              v41 = GetLastError();
              WPP_SF_SD(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, v42, (_DWORD)lpApplicationName, v41);
            }
            goto LABEL_65;
          }
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          {
LABEL_51:
            if ( v40 != &WPP_GLOBAL_Control && (*((_BYTE *)v40 + 28) & 1) != 0 )
              WPP_SF_S(v40[2], 14, WPP_b23fa736e9853481a42645a0499c03f5_Traceguids, lpApplicationName);
            goto LABEL_54;
          }
          WPP_SF_SD(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, v39, (_DWORD)lpApplicationName, v38);
        }
        v40 = WPP_GLOBAL_Control;
        goto LABEL_51;
      }
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v43 = GetLastError();
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_b23fa736e9853481a42645a0499c03f5_Traceguids, v43);
      }
      v33 = Str;
    }
    else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_b23fa736e9853481a42645a0499c03f5_Traceguids);
    }
LABEL_65:
    if ( (v23 & 2) != 0 && !wcsstr(v33, L"VistaSetUp") )
    {
      v44 = L" VistaSetUp";
      if ( !*v33 )
        v44 = L"VistaSetUp";
      if ( StringCchCatW(v33, 0x10Cu, v44) < 0
        && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_b23fa736e9853481a42645a0499c03f5_Traceguids);
      }
    }
    if ( *v33 )
    {
      v45 = -1;
      do
        ++v45;
      while ( v33[v45] );
      v46 = RtlSetEnvironmentVar(&Environment, L"__COMPAT_LAYER", 14, v33, v45);
      if ( v46 < 0 )
      {
        ShouldElevateUIAApplication = RtlNtStatusToDosErrorNoTeb(v46);
        if ( ShouldElevateUIAApplication )
          goto LABEL_192;
      }
    }
    ShouldElevateUIAApplication = AipHardenEnvironment(&Environment);
    if ( ShouldElevateUIAApplication )
      goto LABEL_192;
    ShouldElevateUIAApplication = AipExpandEnvironment(&Environment);
    if ( ShouldElevateUIAApplication )
      goto LABEL_192;
    if ( (v23 & 0x401) != 0 )
    {
      ShouldElevateUIAApplication = AiSetMandatoryPolicy(hToken);
      if ( ShouldElevateUIAApplication )
        goto LABEL_192;
    }
    p_hSourceHandle = (HANDLE *)&v100;
    if ( !v100 )
      p_hSourceHandle = &hSourceHandle;
    if ( !UpdateProcThreadAttribute((LPPROC_THREAD_ATTRIBUTE_LIST)&v115, 0, 0x20000u, p_hSourceHandle, 8u, 0, 0) )
      goto LABEL_30;
    if ( !UpdateProcThreadAttribute((LPPROC_THREAD_ATTRIBUTE_LIST)&v115, 0, 0x60001u, &Value, 4u, 0, 0) )
      goto LABEL_30;
    if ( lpValue )
    {
      v48 = -1;
      do
        ++v48;
      while ( *((_WORD *)lpValue + v48) );
      if ( !UpdateProcThreadAttribute((LPPROC_THREAD_ATTRIBUTE_LIST)&v115, 0, 0x20008u, lpValue, 2 * v48, 0, 0) )
        goto LABEL_30;
    }
    if ( (a15 & 6) != 0 )
    {
      if ( (a15 & 4) != 0 )
        v92 = 2;
      if ( !UpdateProcThreadAttribute((LPPROC_THREAD_ATTRIBUTE_LIST)&v115, 0, 0x20012u, &v92, 4u, 0, 0) )
        goto LABEL_30;
    }
    if ( applicationUserModelIdLength )
    {
      memset_0(v113, 0, 0x208u);
      v112 = 8;
    }
    else
    {
      if ( (a15 & 0x400) == 0 )
      {
LABEL_101:
        if ( (a15 & 0x2000) != 0 )
        {
          v110[0] = &hToken;
          v110[1] = v114;
          v110[2] = &v115;
          v49 = lambda_cb53673acf3e3e27f7e291508307a564_::operator()(v110);
          if ( v49 < 0 )
          {
            LastError = WIN32_FROM_HRESULT(v49);
            goto LABEL_31;
          }
        }
        goto LABEL_106;
      }
      memset_0(v113, 0, 0x208u);
      v112 = 256;
    }
    if ( !UpdateProcThreadAttribute((LPPROC_THREAD_ATTRIBUTE_LIST)&v115, 0, 0x20011u, &v112, 0x20Cu, 0, 0) )
      goto LABEL_30;
    goto LABEL_101;
  }
  ObjectAttributes.Length = 48;
  memset(&ObjectAttributes.RootDirectory, 0, 20);
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v25 = NtDuplicateToken(a2, 0, &ObjectAttributes, 0, TokenPrimary, &hToken);
  if ( v25 >= 0 )
    goto LABEL_6;
  ShouldElevateUIAApplication = RtlNtStatusToDosErrorNoTeb(v25);
LABEL_4:
  v27 = 0;
LABEL_194:
  v68 = (void *)hFile;
LABEL_195:
  if ( lpAttributeList )
    DeleteProcThreadAttributeList(lpAttributeList);
  if ( Environment )
    DestroyEnvironmentBlock(Environment);
  if ( v27 )
    UnloadUserProfile(hToken, v27);
  if ( ProcessInformation.hThread )
    CloseHandle(ProcessInformation.hThread);
  if ( ProcessInformation.hProcess )
  {
    if ( ShouldElevateUIAApplication )
      TerminateProcess(ProcessInformation.hProcess, ShouldElevateUIAApplication);
    CloseHandle(ProcessInformation.hProcess);
  }
  if ( TargetHandle )
    CloseHandle(TargetHandle);
  if ( v98 )
    BaseFreeAppCompatDataForProcess();
  if ( Str )
    LocalFree(Str);
  if ( hToken && hToken != v105 )
  {
    NtClose(hToken);
    hToken = 0;
  }
  if ( v21 )
    LocalFree(v21);
  if ( v68 != (void *)-1LL )
    CloseHandle(v68);
  return ShouldElevateUIAApplication;
}

```

## disassembly

```asm
0x18002d8fc  push    rbp
0x18002d8fe  push    rbx
0x18002d8ff  push    rsi
0x18002d900  push    rdi
0x18002d901  push    r12
0x18002d903  push    r13
0x18002d905  push    r14
0x18002d907  push    r15
0x18002d909  lea     rbp, [rsp-888h]
0x18002d911  sub     rsp, 988h
0x18002d918  mov     rax, cs:__security_cookie
0x18002d91f  xor     rax, rsp
0x18002d922  mov     [rbp+8C0h+var_50], rax
0x18002d929  mov     rax, [rbp+8C0h+arg_28]
0x18002d930  xor     esi, esi
0x18002d932  mov     r13, [rbp+8C0h+arg_68]
0x18002d939  mov     rbx, rdx
0x18002d93c  mov     r15, [rbp+8C0h+lpApplicationName]
0x18002d943  mov     r12d, r9d
0x18002d946  mov     r14, [rbp+8C0h+arg_48]
0x18002d94d  mov     rdi, [rbp+8C0h+arg_90]
0x18002d954  mov     [rbp+8C0h+lpFileName], rax
0x18002d958  mov     rax, [rbp+8C0h+arg_98]
0x18002d95f  mov     [rbp+8C0h+var_8A8], rax
0x18002d963  mov     rax, [rbp+8C0h+arg_38]
0x18002d96a  mov     [rbp+8C0h+var_8D8], rax
0x18002d96e  mov     rax, [rbp+8C0h+arg_40]
0x18002d975  mov     [rbp+8C0h+var_888], rax
0x18002d979  mov     rax, [rbp+8C0h+arg_80]
0x18002d980  mov     [rbp+8C0h+var_8B8], rax
0x18002d984  mov     rax, [rbp+8C0h+arg_A0]
0x18002d98b  mov     [rbp+8C0h+var_8F8], rax
0x18002d98f  mov     [rbp+8C0h+var_8C0], rax
0x18002d993  mov     eax, esi
0x18002d995  mov     [rbp+8C0h+var_8B0], r8
0x18002d999  lea     r8d, [rsi+68h]; Size
0x18002d99d  mov     [rbp+8C0h+var_890], rdx
0x18002d9a1  xor     edx, edx; Val
0x18002d9a3  mov     [rbp+8C0h+hSourceHandle], rcx
0x18002d9a7  lea     rcx, [rbp+8C0h+StartupInfo.lpReserved]; void *
0x18002d9ab  mov     [rsp+9C0h+hProfile], rax
0x18002d9b0  mov     [rbp+8C0h+var_910], rax
0x18002d9b4  mov     [rbp+8C0h+var_940], r9d
0x18002d9b8  mov     [rbp+8C0h+lpValue], r13
0x18002d9bc  mov     [rbp+8C0h+Value], esi
0x18002d9bf  mov     [rbp+8C0h+Str], rsi
0x18002d9c3  mov     [rbp+8C0h+TargetHandle], rsi
0x18002d9c7  mov     [rsp+9C0h+hToken], rsi
0x18002d9cc  mov     [rbp+8C0h+Environment], rsi
0x18002d9d0  mov     qword ptr [rbp+8C0h+StartupInfo.cb], rsi
0x18002d9d4  call    memset_0
0x18002d9d9  xorps   xmm0, xmm0
0x18002d9dc  mov     [rbp+8C0h+var_480], esi
0x18002d9e2  xor     eax, eax
0x18002d9e4  lea     rcx, [rbp+8C0h+var_47C]; void *
0x18002d9eb  xor     edx, edx; Val
0x18002d9ed  mov     qword ptr [rbp+8C0h+ProcessInformation.dwProcessId], rax
0x18002d9f1  mov     r8d, 14Ch; Size
0x18002d9f7  movups  xmmword ptr [rbp+8C0h+ProcessInformation.hProcess], xmm0
0x18002d9fb  call    memset_0
0x18002da00  xorps   xmm0, xmm0
0x18002da03  mov     [rbp+8C0h+Size], 150h
0x18002da0b  xor     edx, edx; Val
0x18002da0d  mov     [rbp+8C0h+var_8C8], rsi
0x18002da11  mov     r8d, 20Ch; Size
0x18002da17  mov     [rbp+8C0h+var_908], 4
0x18002da1e  lea     rcx, [rbp+8C0h+var_7B0]; void *
0x18002da25  movups  xmmword ptr [rbp+8C0h+ObjectAttributes.Length], xmm0
0x18002da2c  movups  xmmword ptr [rbp+8C0h+ObjectAttributes.ObjectName], xmm0
0x18002da33  movups  xmmword ptr [rbp+8C0h+ObjectAttributes.SecurityDescriptor], xmm0
0x18002da3a  movups  [rbp+8C0h+var_7C8], xmm0
0x18002da41  call    memset_0
0x18002da46  xor     edx, edx; Val
0x18002da48  lea     rcx, [rbp+8C0h+var_5A0]; void *
0x18002da4f  mov     r8d, 114h; Size
0x18002da55  call    memset_0
0x18002da5a  mov     [rsp+9C0h+hFile], 0FFFFFFFFFFFFFFFFh
0x18002da63  mov     [rsp+9C0h+hMem], rsi
0x18002da68  test    r12b, r12b
0x18002da6b  js      short loc_18002DAD9
0x18002da6d  xor     eax, eax
0x18002da6f  mov     [rbp+8C0h+ObjectAttributes.Length], 30h ; '0'
0x18002da79  mov     [rbp+8C0h+ObjectAttributes.RootDirectory], rax
0x18002da80  lea     r8, [rbp+8C0h+ObjectAttributes]; ObjectAttributes
0x18002da87  mov     [rbp+8C0h+ObjectAttributes.Attributes], eax
0x18002da8d  xorps   xmm0, xmm0
0x18002da90  mov     [rbp+8C0h+ObjectAttributes.ObjectName], rax
0x18002da97  xor     r9d, r9d; EffectiveOnly
0x18002da9a  lea     rax, [rsp+9C0h+hToken]
0x18002da9f  xor     edx, edx; DesiredAccess
0x18002daa1  mov     [rsp+9C0h+NewTokenHandle], rax; NewTokenHandle
0x18002daa6  mov     rcx, rbx; ExistingTokenHandle
0x18002daa9  mov     [rsp+9C0h+TokenType], 1; TokenType
0x18002dab1  movdqu  xmmword ptr [rbp+8C0h+ObjectAttributes.SecurityDescriptor], xmm0
0x18002dab9  call    cs:__imp_NtDuplicateToken
0x18002dabf  xor     edx, edx
0x18002dac1  test    eax, eax
0x18002dac3  jns     short loc_18002DAE0
0x18002dac5  mov     ecx, eax; Status
0x18002dac7  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x18002dacd  mov     ebx, eax
0x18002dacf  mov     rdi, [rsp+9C0h+hProfile]
0x18002dad4  jmp     loc_18002E706
0x18002dad9  mov     [rsp+9C0h+hToken], rbx
0x18002dade  xor     edx, edx
0x18002dae0  mov     ebx, edx
0x18002dae2  test    r12b, 4
0x18002dae6  jz      short loc_18002DB55
0x18002dae8  lea     rcx, [rbp+8C0h+var_940]; unsigned int *
0x18002daec  call    ?AipShouldElevateUIAApplication@@YAKPEAK@Z; AipShouldElevateUIAApplication(ulong *)
0x18002daf1  xor     edx, edx
0x18002daf3  mov     ebx, eax
0x18002daf5  test    eax, eax
0x18002daf7  jnz     short loc_18002DACF
0x18002daf9  mov     r12d, [rbp+8C0h+var_940]
0x18002dafd  bt      r12d, 0Ah
0x18002db02  jnb     short loc_18002DB46
0x18002db04  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ShadowAdmin@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ShadowAdmin@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShadowAdmin> `wil::Feature<__WilFeatureTraits_Feature_ShadowAdmin>::GetImpl(void)'::`2'::impl
0x18002db0b  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ShadowAdmin@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShadowAdmin>::__private_IsEnabled(void)
0x18002db10  mov     ecx, [rbp+8C0h+arg_30]
0x18002db16  and     ecx, 0FFFFFFFCh
0x18002db19  test    al, al
0x18002db1b  cmovz   ecx, [rbp+8C0h+arg_30]
0x18002db22  mov     [rbp+8C0h+var_940], ecx
0x18002db25  lea     rcx, [rsp+9C0h+hToken]
0x18002db2a  call    LUASetUIAToken2
0x18002db2f  mov     ebx, eax
0x18002db31  call    LUAIsShadowAdminEnabled
0x18002db36  xor     edx, edx
0x18002db38  test    eax, eax
0x18002db3a  jz      short loc_18002DB40
0x18002db3c  or      r12d, 1
0x18002db40  test    ebx, ebx
0x18002db42  jnz     short loc_18002DACF
0x18002db44  jmp     short loc_18002DB5E
0x18002db46  mov     ecx, [rbp+8C0h+arg_30]
0x18002db4c  or      [rbp+8C0h+Value], 2
0x18002db50  mov     [rbp+8C0h+var_940], ecx
0x18002db53  jmp     short loc_18002DB5E
0x18002db55  mov     eax, [rbp+8C0h+arg_30]
0x18002db5b  mov     [rbp+8C0h+var_940], eax
0x18002db5e  mov     eax, edx
0x18002db60  mov     esi, dword ptr [rbp+8C0h+arg_70]
0x18002db66  cmp     [rbp+8C0h+hSourceHandle], rdx
0x18002db6a  jz      short loc_18002DB81
0x18002db6c  mov     rax, r13
0x18002db6f  neg     rax
0x18002db72  sbb     eax, eax
0x18002db74  neg     eax
0x18002db76  add     eax, 2
0x18002db79  test    sil, 6
0x18002db7d  jz      short loc_18002DB81
0x18002db7f  inc     eax
0x18002db81  test    r12d, 1800000h
0x18002db88  jnz     short loc_18002DB93
0x18002db8a  test    [rbp+8C0h+arg_78], 4
0x18002db91  jz      short loc_18002DB95
0x18002db93  inc     eax
0x18002db95  mov     ecx, esi
0x18002db97  and     ecx, 8
0x18002db9a  mov     [rbp+8C0h+applicationUserModelIdLength], ecx
0x18002db9d  jnz     short loc_18002DBA5
0x18002db9f  bt      esi, 0Ah
0x18002dba3  jnb     short loc_18002DBA7
0x18002dba5  inc     eax
0x18002dba7  mov     r13d, esi
0x18002dbaa  lea     ecx, [rax+1]
0x18002dbad  and     r13d, 2000h
0x18002dbb4  cmovz   ecx, eax
0x18002dbb7  mov     [rbp+8C0h+var_924], ecx
0x18002dbba  test    ecx, ecx
0x18002dbbc  jz      short loc_18002DBE7
0x18002dbbe  mov     edx, ecx; dwAttributeCount
0x18002dbc0  lea     r9, [rbp+8C0h+Size]; lpSize
0x18002dbc4  lea     rcx, [rbp+8C0h+var_480]; lpAttributeList
0x18002dbcb  xor     r8d, r8d; dwFlags
0x18002dbce  call    cs:__imp_InitializeProcThreadAttributeList
0x18002dbd4  xor     edx, edx
0x18002dbd6  test    eax, eax
0x18002dbd8  jnz     short loc_18002DBE7
0x18002dbda  call    cs:__imp_GetLastError
0x18002dbe0  mov     ebx, eax
0x18002dbe2  jmp     loc_18002E6FC
0x18002dbe7  cmp     [rbp+8C0h+hSourceHandle], rdx
0x18002dbeb  jz      loc_18002E13A
0x18002dbf1  test    r12b, 1
0x18002dbf5  jz      short loc_18002DC18
0x18002dbf7  mov     rcx, [rsp+9C0h+hToken]; hToken
0x18002dbfc  lea     rdx, [rbp+8C0h+var_910]; void **
0x18002dc00  call    ?AipLoadUserProfile@@YAKPEAXPEAPEAX@Z; AipLoadUserProfile(void *,void * *)
0x18002dc05  mov     ebx, eax
0x18002dc07  test    eax, eax
0x18002dc09  jnz     loc_18002DC9F
0x18002dc0f  mov     rax, [rbp+8C0h+var_910]
0x18002dc13  mov     [rsp+9C0h+hProfile], rax
0x18002dc18  mov     rdx, [rsp+9C0h+hToken]; hToken
0x18002dc1d  lea     rcx, [rbp+8C0h+Environment]; lpEnvironment
0x18002dc21  xor     r8d, r8d; bInherit
0x18002dc24  call    cs:__imp_CreateEnvironmentBlock
0x18002dc2a  xor     ecx, ecx
0x18002dc2c  test    eax, eax
0x18002dc2e  jz      short loc_18002DBDA
0x18002dc30  test    rdi, rdi
0x18002dc33  jz      short loc_18002DC65
0x18002dc35  mov     [rbp+8C0h+var_910], rcx
0x18002dc39  lea     r8, [rbp+8C0h+var_910]; unsigned __int16 **
0x18002dc3d  mov     rcx, [rbp+8C0h+Environment]; Src
0x18002dc41  mov     rdx, rdi; unsigned __int16 *
0x18002dc44  call    ?AipAddDebugEnvironmentBlock@@YAKPEBG0PEAPEAG@Z; AipAddDebugEnvironmentBlock(ushort const *,ushort const *,ushort * *)
0x18002dc49  mov     ebx, eax
0x18002dc4b  test    eax, eax
0x18002dc4d  jnz     loc_18002E6FC
0x18002dc53  mov     rcx, [rbp+8C0h+Environment]; lpEnvironment
0x18002dc57  call    cs:__imp_DestroyEnvironmentBlock
0x18002dc5d  mov     rax, [rbp+8C0h+var_910]
0x18002dc61  mov     [rbp+8C0h+Environment], rax
0x18002dc65  lea     rdx, [rbp+8C0h+Environment]; void **
0x18002dc69  mov     rcx, r15; Str
0x18002dc6c  call    ?AipCheckForAppPathsKey@@YAKPEBGPEAPEAX@Z; AipCheckForAppPathsKey(ushort const *,void * *)
0x18002dc71  mov     ebx, eax
0x18002dc73  test    eax, eax
0x18002dc75  jnz     loc_18002E6FC
0x18002dc7b  mov     edx, 218h; uBytes
0x18002dc80  lea     ecx, [rax+40h]; uFlags
0x18002dc83  call    cs:__imp_LocalAlloc
0x18002dc89  mov     [rbp+8C0h+Str], rax
0x18002dc8d  mov     rdi, rax
0x18002dc90  test    rax, rax
0x18002dc93  jnz     short loc_18002DCA8
0x18002dc95  mov     ebx, 8
0x18002dc9a  jmp     loc_18002E6FC
0x18002dc9f  mov     rdi, [rbp+8C0h+var_910]
0x18002dca3  jmp     loc_18002E701
0x18002dca8  call    IsSdbGetKnownSafeLayersPresent
0x18002dcad  test    al, al
0x18002dcaf  jz      loc_18002DEE7
0x18002dcb5  call    cs:__imp_GetCurrentProcess
0x18002dcbb  mov     rdi, [rbp+8C0h+hSourceHandle]
0x18002dcbf  mov     rbx, rax
0x18002dcc2  call    cs:__imp_GetCurrentProcess
0x18002dcc8  xor     ecx, ecx
0x18002dcca  lea     r9, [rbp+8C0h+TargetHandle]; lpTargetHandle
0x18002dcce  mov     [rsp+9C0h+dwOptions], ecx; dwOptions
0x18002dcd2  mov     r8, rbx; hTargetProcessHandle
0x18002dcd5  mov     dword ptr [rsp+9C0h+NewTokenHandle], ecx; bInheritHandle
0x18002dcd9  mov     rdx, rdi; hSourceHandle
0x18002dcdc  mov     rcx, rax; hSourceProcessHandle
0x18002dcdf  mov     [rsp+9C0h+TokenType], 410h; dwDesiredAccess
0x18002dce7  call    cs:__imp_DuplicateHandle
0x18002dced  test    eax, eax
0x18002dcef  jz      loc_18002DDEB
0x18002dcf5  mov     rcx, [rbp+8C0h+TargetHandle]
0x18002dcf9  lea     rdx, [rbp+8C0h+var_8C8]
0x18002dcfd  xor     r8d, r8d
0x18002dd00  call    cs:__imp_BaseReadAppCompatDataForProcess
0x18002dd06  lea     rbx, WPP_GLOBAL_Control
0x18002dd0d  test    eax, eax
0x18002dd0f  jz      short loc_18002DD38
0x18002dd11  mov     rcx, cs:WPP_GLOBAL_Control
0x18002dd18  cmp     rcx, rbx
0x18002dd1b  jz      short loc_18002DD62
0x18002dd1d  test    byte ptr [rcx+1Ch], 1
0x18002dd21  jz      short loc_18002DD3F
0x18002dd23  mov     rcx, [rcx+10h]
0x18002dd27  mov     edx, 0Dh
0x18002dd2c  mov     r9, r15
0x18002dd2f  mov     [rsp+9C0h+TokenType], eax
0x18002dd33  call    WPP_SF_SD
0x18002dd38  mov     rcx, cs:WPP_GLOBAL_Control
0x18002dd3f  cmp     rcx, rbx
0x18002dd42  jz      short loc_18002DD62
0x18002dd44  test    byte ptr [rcx+1Ch], 1
0x18002dd48  jz      short loc_18002DD62
0x18002dd4a  mov     rcx, [rcx+10h]
0x18002dd4e  lea     r8, WPP_b23fa736e9853481a42645a0499c03f5_Traceguids
0x18002dd55  mov     edx, 0Eh
0x18002dd5a  mov     r9, r15
0x18002dd5d  call    WPP_SF_S
0x18002dd62  mov     rdi, [rbp+8C0h+Str]
0x18002dd66  mov     edx, 100h
0x18002dd6b  mov     rcx, [rbp+8C0h+var_8C8]
0x18002dd6f  mov     r8, rdi
0x18002dd72  call    cs:__imp_SdbGetKnownSafeLayers
0x18002dd78  test    eax, eax
0x18002dd7a  jnz     short loc_18002DDBA
0x18002dd7c  mov     rax, cs:WPP_GLOBAL_Control
0x18002dd83  cmp     rax, rbx
0x18002dd86  jz      loc_18002DE2D
0x18002dd8c  test    byte ptr [rax+1Ch], 1
0x18002dd90  jz      loc_18002DE2D
0x18002dd96  call    cs:__imp_GetLastError
0x18002dd9c  mov     rcx, cs:WPP_GLOBAL_Control
0x18002dda3  mov     edx, 0Fh
0x18002dda8  mov     r9, r15
0x18002ddab  mov     [rsp+9C0h+TokenType], eax
0x18002ddaf  mov     rcx, [rcx+10h]
0x18002ddb3  call    WPP_SF_SD
0x18002ddb8  jmp     short loc_18002DE2D
0x18002ddba  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ddc1  cmp     rcx, rbx
  ... truncated ...
```
