# Appx::Packaging::Manifest::AppxManifestReaderImpl::GetWindowsExtensionInUse(ushort const *,int)

- ea: `0x180063050`
- end: `0x180063f30`
- name: `?GetWindowsExtensionInUse@AppxManifestReaderImpl@Manifest@Packaging@Appx@@AEAA?AW4WindowsExtensionInUse@1234@PEBGH@Z`
- size: `3808`
- prototype: `enum Appx::Packaging::Manifest::AppxManifestReaderImpl::WindowsExtensionInUse __high(const unsigned __int16 *, int)`
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18001c8a8`
- `0x1800d757c`

## callees

- `0x18005f7a4`
- `0x180063050`
- `0x180099dd8`
- `0x180099e38`
- `0x1800a8b0c`
- `0x1800c4b50`
- `0x1800c4cd0`
- `0x1800d47a8`
- `0x180106010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800638b7`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800638f3`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800638b7`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800638f3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180063a28`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180063ae6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180063a28`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180063ae6`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180063740`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180063a91`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180063740`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180063a91`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180063858`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180063858`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180063842`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180063842`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800637d0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006392f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006396a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800637d0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006392f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006396a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800637fa`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180063883`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800639b4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800639ca`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800637fa`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180063883`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800639b4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800639ca`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18006394f`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18006394f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800639a6`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800639a6`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180063997`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180063997`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180063983`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800639ff`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180063983`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800639ff`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180063087`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180063087`

## string_xrefs

- `0x180063220`: `windows.classicAppCompatKeys`
- `0x1800632d9`: `windows.customInstall`
- `0x18006329c`: `windows.comServer`
- `0x1800631b0`: `windows.backgroundTasks`
- `0x180063ba9`: `windows.protocol`
- `0x180063259`: `windows.comInterface`
- `0x180063dd9`: `windows.service`
- `0x180063e59`: `windows.startupTask`
- `0x180063c29`: `windows.printSupportExtension`
- `0x1800630fe`: `windows.appService`

## pseudocode

```c
__int64 __fastcall Appx::Packaging::Manifest::AppxManifestReaderImpl::GetWindowsExtensionInUse(
        __int64 a1,
        const WCHAR *a2,
        unsigned int a3)
{
  const WCHAR *v3; // rbx
  __int64 v4; // rcx
  unsigned __int16 *v5; // rcx
  int v6; // edx
  int v7; // r8d
  __int64 result; // rax
  unsigned __int16 *v9; // rax
  int v10; // ecx
  int v11; // edx
  unsigned __int16 *v12; // rax
  int v13; // ecx
  int v14; // edx
  char *v15; // rdx
  int v16; // eax
  int v17; // ecx
  unsigned int v18; // esi
  unsigned __int16 *v19; // rax
  int v20; // ecx
  int v21; // edx
  char *v22; // rdx
  int v23; // eax
  int v24; // ecx
  unsigned int v25; // esi
  unsigned __int16 *v26; // rax
  int v27; // ecx
  int v28; // edx
  unsigned __int16 *v29; // rcx
  int v30; // edx
  int v31; // r8d
  unsigned __int16 *v32; // rax
  int v33; // ecx
  int v34; // edx
  unsigned __int16 *v35; // rax
  int v36; // ecx
  int v37; // edx
  char *v38; // rdx
  int v39; // eax
  int v40; // ecx
  unsigned int v41; // esi
  unsigned __int16 *v42; // rax
  int v43; // ecx
  int v44; // edx
  unsigned __int16 *v45; // rax
  int v46; // ecx
  int v47; // edx
  char *v48; // rdx
  int v49; // eax
  int v50; // ecx
  unsigned int v51; // esi
  unsigned __int16 *v52; // rax
  int v53; // ecx
  int v54; // edx
  unsigned __int16 *v55; // rax
  int v56; // ecx
  int v57; // edx
  unsigned __int16 *v58; // rax
  int v59; // ecx
  int v60; // edx
  unsigned __int16 *v61; // rax
  int v62; // ecx
  int v63; // edx
  char *v64; // rdx
  int v65; // eax
  int v66; // ecx
  unsigned int v67; // esi
  char *v68; // rdx
  int v69; // eax
  int v70; // ecx
  unsigned int v71; // esi
  unsigned __int16 *v72; // rax
  int v73; // ecx
  int v74; // edx
  unsigned __int16 *v75; // rax
  int v76; // ecx
  int v77; // edx
  char *v78; // rdx
  int v79; // eax
  int v80; // ecx
  unsigned int v81; // esi
  int v82; // r12d
  unsigned int v83; // esi
  __int64 v84; // r13
  int *v85; // rax
  __int64 v86; // r8
  unsigned int v87; // ebp
  unsigned int v88; // r14d
  int v89; // r15d
  int v90; // edi
  __int64 v91; // rcx
  _DWORD *v92; // r9
  DWORD dwLowDateTime; // r11d
  unsigned __int64 v94; // r10
  unsigned __int64 v95; // rdx
  unsigned __int64 v96; // rdi
  DWORD LastError; // ebp
  unsigned __int64 v98; // r15
  unsigned __int64 v99; // r8
  char *v100; // rax
  char *v101; // rdi
  signed __int64 v102; // r14
  HANDLE ProcessHeap; // rax
  size_t v104; // r8
  struct _TP_TIMER *v105; // rcx
  DWORD v106; // r14d
  PTP_TIMER ThreadpoolTimer; // rax
  struct _TP_TIMER *v108; // rbp
  struct _TP_TIMER *v109; // r15
  DWORD v110; // edi
  void (__fastcall *v111)(__int64, _QWORD, _QWORD, _QWORD); // rax
  void (__fastcall *v112)(__int64 *, __int64 (__fastcall *)(void *), __int64); // rax
  __int64 v113; // rdx
  void (__fastcall *v114)(__int64, __int64, _QWORD, _QWORD); // rax
  unsigned __int16 *v115; // rax
  int v116; // ecx
  int v117; // edx
  unsigned __int16 *v118; // rax
  int v119; // ecx
  int v120; // edx
  unsigned __int16 *v121; // rax
  int v122; // ecx
  int v123; // edx
  unsigned __int16 *v124; // rax
  int v125; // ecx
  int v126; // edx
  unsigned __int16 *v127; // rax
  int v128; // ecx
  int v129; // edx
  unsigned __int16 *v130; // rax
  int v131; // ecx
  int v132; // edx
  unsigned __int16 *v133; // rax
  int v134; // ecx
  int v135; // edx
  char *v136; // rdx
  int v137; // eax
  int v138; // ecx
  unsigned __int16 *v139; // rax
  int v140; // ecx
  int v141; // edx
  unsigned __int16 *v142; // rax
  int v143; // ecx
  int v144; // edx
  unsigned __int16 *v145; // rax
  int v146; // ecx
  int v147; // edx
  char *v148; // rdx
  int v149; // eax
  int v150; // ecx
  unsigned int v151; // esi
  char *v152; // rdx
  int v153; // eax
  int v154; // ecx
  unsigned int v155; // esi
  int v156; // [rsp+50h] [rbp-78h] BYREF
  int v157; // [rsp+58h] [rbp-70h] BYREF
  __int16 v158; // [rsp+5Ch] [rbp-6Ch]
  LPVOID lpMem; // [rsp+60h] [rbp-68h]
  struct _FILETIME pftDueTime; // [rsp+68h] [rbp-60h] BYREF
  char v161[32]; // [rsp+70h] [rbp-58h] BYREF
  __int64 v162; // [rsp+D0h] [rbp+8h] BYREF
  unsigned int v163; // [rsp+E0h] [rbp+18h]
  unsigned int v164; // [rsp+E8h] [rbp+20h]

  v162 = a1;
  v3 = a2;
  if ( a3 < 8 || CompareStringOrdinal(a2, 8, L"windows.", 8, 1) != 2 )
    return 0;
  switch ( v3[8] )
  {
    case 'a':
      v5 = (unsigned __int16 *)v3;
      do
      {
        v6 = *(unsigned __int16 *)((char *)v5 + (char *)L"windows.activatableClass.outOfProcessServer" - (char *)v3);
        v7 = *v5 - v6;
        if ( v7 )
          break;
        ++v5;
      }
      while ( v6 );
      if ( !v7 )
        return 1;
      v9 = (unsigned __int16 *)v3;
      do
      {
        v10 = *(unsigned __int16 *)((char *)v9 + (char *)L"windows.appService" - (char *)v3);
        v11 = *v9 - v10;
        if ( v11 )
          break;
        ++v9;
      }
      while ( v10 );
      if ( !v11 )
        return 2;
      v12 = (unsigned __int16 *)v3;
      do
      {
        v13 = *(unsigned __int16 *)((char *)v12 + (char *)L"windows.autoPlayHandler" - (char *)v3);
        v14 = *v12 - v13;
        if ( v14 )
          break;
        ++v12;
      }
      while ( v13 );
      if ( !v14 )
        return 4;
      v15 = (char *)((char *)L"windows.appExecutionAlias" - (char *)v3);
      do
      {
        v16 = *(unsigned __int16 *)&v15[(_QWORD)v3];
        v17 = *v3 - v16;
        if ( v17 )
          break;
        ++v3;
      }
      while ( v16 );
      v18 = 0;
      if ( !v17 )
        return 3;
      return v18;
    case 'b':
      v19 = (unsigned __int16 *)v3;
      do
      {
        v20 = *(unsigned __int16 *)((char *)v19 + (char *)L"windows.backgroundTasks" - (char *)v3);
        v21 = *v19 - v20;
        if ( v21 )
          break;
        ++v19;
      }
      while ( v20 );
      if ( !v21 )
        return 5;
      v22 = (char *)((char *)L"windows.barcodeScannerProvider" - (char *)v3);
      do
      {
        v23 = *(unsigned __int16 *)&v22[(_QWORD)v3];
        v24 = *v3 - v23;
        if ( v24 )
          break;
        ++v3;
      }
      while ( v23 );
      v25 = 0;
      if ( !v24 )
        return 6;
      return v25;
    case 'c':
      v26 = (unsigned __int16 *)v3;
      do
      {
        v27 = *(unsigned __int16 *)((char *)v26 + (char *)L"windows.classicAppCompatKeys" - (char *)v3);
        v28 = *v26 - v27;
        if ( v28 )
          break;
        ++v26;
      }
      while ( v27 );
      if ( !v28 )
        return 7;
      v29 = (unsigned __int16 *)v3;
      do
      {
        v30 = *(unsigned __int16 *)((char *)v29 + (char *)L"windows.comInterface" - (char *)v3);
        v31 = *v29 - v30;
        if ( v31 )
          break;
        ++v29;
      }
      while ( v30 );
      if ( !v31 )
        return 8;
      v32 = (unsigned __int16 *)v3;
      do
      {
        v33 = *(unsigned __int16 *)((char *)v32 + (char *)L"windows.comServer" - (char *)v3);
        v34 = *v32 - v33;
        if ( v34 )
          break;
        ++v32;
      }
      while ( v33 );
      if ( !v34 )
        return 9;
      v35 = (unsigned __int16 *)v3;
      do
      {
        v36 = *(unsigned __int16 *)((char *)v35 + (char *)L"windows.customInstall" - (char *)v3);
        v37 = *v35 - v36;
        if ( v37 )
          break;
        ++v35;
      }
      while ( v36 );
      if ( !v37 )
        return 11;
      v38 = (char *)((char *)L"windows.customDesktopEventLog" - (char *)v3);
      do
      {
        v39 = *(unsigned __int16 *)&v38[(_QWORD)v3];
        v40 = *v3 - v39;
        if ( v40 )
          break;
        ++v3;
      }
      while ( v39 );
      v41 = 0;
      if ( !v40 )
        return 10;
      return v41;
    case 'd':
      v42 = (unsigned __int16 *)v3;
      do
      {
        v43 = *(unsigned __int16 *)((char *)v42 + (char *)L"windows.dataShortcuts" - (char *)v3);
        v44 = *v42 - v43;
        if ( v44 )
          break;
        ++v42;
      }
      while ( v43 );
      if ( !v44 )
        return 12;
      v45 = (unsigned __int16 *)v3;
      do
      {
        v46 = *(unsigned __int16 *)((char *)v45 + (char *)L"windows.desktopAppMigration" - (char *)v3);
        v47 = *v45 - v46;
        if ( v47 )
          break;
        ++v45;
      }
      while ( v46 );
      if ( !v47 )
        return 13;
      v48 = (char *)((char *)L"windows.desktopEventLogging" - (char *)v3);
      do
      {
        v49 = *(unsigned __int16 *)&v48[(_QWORD)v3];
        v50 = *v3 - v49;
        if ( v50 )
          break;
        ++v3;
      }
      while ( v49 );
      v51 = 0;
      if ( !v50 )
        return 14;
      return v51;
    case 'f':
      v52 = (unsigned __int16 *)v3;
      do
      {
        v53 = *(unsigned __int16 *)((char *)v52 + (char *)L"windows.fileExplorerClassicContextMenuHandler" - (char *)v3);
        v54 = *v52 - v53;
        if ( v54 )
          break;
        ++v52;
      }
      while ( v53 );
      if ( !v54 )
        return 15;
      v55 = (unsigned __int16 *)v3;
      do
      {
        v56 = *(unsigned __int16 *)((char *)v55
                                  + (char *)L"windows.fileExplorerClassicDragDropContextMenuHandler"
                                  - (char *)v3);
        v57 = *v55 - v56;
        if ( v57 )
          break;
        ++v55;
      }
      while ( v56 );
      if ( !v57 )
        return 16;
      v58 = (unsigned __int16 *)v3;
      do
      {
        v59 = *(unsigned __int16 *)((char *)v58 + (char *)L"windows.fileTypeAssociation" - (char *)v3);
        v60 = *v58 - v59;
        if ( v60 )
          break;
        ++v58;
      }
      while ( v59 );
      if ( !v60 )
        return 17;
      v61 = (unsigned __int16 *)v3;
      do
      {
        v62 = *(unsigned __int16 *)((char *)v61 + (char *)L"windows.firewallRules" - (char *)v3);
        v63 = *v61 - v62;
        if ( v63 )
          break;
        ++v61;
      }
      while ( v62 );
      if ( !v63 )
        return 18;
      v64 = (char *)((char *)L"windows.fullTrustProcess" - (char *)v3);
      do
      {
        v65 = *(unsigned __int16 *)&v64[(_QWORD)v3];
        v66 = *v3 - v65;
        if ( v66 )
          break;
        ++v3;
      }
      while ( v65 );
      v67 = 0;
      if ( !v66 )
        return 19;
      return v67;
    case 'h':
      v68 = (char *)((char *)L"windows.hostRuntime" - (char *)v3);
      do
      {
        v69 = *(unsigned __int16 *)&v68[(_QWORD)v3];
        v70 = *v3 - v69;
        if ( v70 )
          break;
        ++v3;
      }
      while ( v69 );
      v71 = 0;
      if ( !v70 )
        return 20;
      return v71;
    case 'm':
      v72 = (unsigned __int16 *)v3;
      do
      {
        v73 = *(unsigned __int16 *)((char *)v72 + (char *)L"windows.mediaCodec" - (char *)v3);
        v74 = *v72 - v73;
        if ( v74 )
          break;
        ++v72;
      }
      while ( v73 );
      if ( !v74 )
        return 21;
      v75 = (unsigned __int16 *)v3;
      do
      {
        v76 = *(unsigned __int16 *)((char *)v75 + (char *)L"windows.mediaSource" - (char *)v3);
        v77 = *v75 - v76;
        if ( v77 )
          break;
        ++v75;
      }
      while ( v76 );
      if ( !v77 )
        return 22;
      v78 = (char *)((char *)L"windows.mutablePackageDirectories" - (char *)v3);
      do
      {
        v79 = *(unsigned __int16 *)&v78[(_QWORD)v3];
        v80 = *v3 - v79;
        if ( v80 )
          break;
        ++v3;
      }
      while ( v79 );
      v81 = 0;
      if ( !v80 )
        return 23;
      return v81;
    case 'p':
      v82 = *(_DWORD *)Feature_IppPsaEnterprise_Api__descriptor;
      if ( (*(_DWORD *)Feature_IppPsaEnterprise_Api__descriptor & 4) == 0 )
      {
        v162 = *(_QWORD *)wil::details::FeatureImpl<__WilFeatureTraits_Feature_IppPsaEnterprise_Api>::GetCachedFeatureEnabledState(
                            v4,
                            &v162);
        LOWORD(v82) = v162;
      }
      v158 = 3;
      v83 = 0;
      v156 = 3;
      v157 = 0;
      v84 = (unsigned int)wil_details_MapReportingKind(3, 1);
      v85 = (int *)wil_details_FeatureReporting_RecordUsageInCache(v161, &qword_18016A6D8, v84);
      v87 = v85[1];
      v88 = v85[2];
      v89 = v85[4];
      v90 = *v85;
      v163 = v87;
      v164 = v88;
      LODWORD(v162) = v89;
      if ( g_wil_details_RecordSRUMFeatureUsage && (!(_DWORD)v84 || (unsigned int)(v84 - 100) <= 0x31) )
        g_wil_details_RecordSRUMFeatureUsage(56643977, (unsigned int)v84, 1);
      if ( !v90
        || !wil::details::g_enabledStateManager
        || wil::details::g_processShutdownInProgress
        || wil::details::g_pfnDllShutdownInProgress && (unsigned __int8)wil::details::g_pfnDllShutdownInProgress() )
      {
        goto LABEL_167;
      }
      AcquireSRWLockExclusive(&stru_180169F18);
      if ( !wil::details::g_enabledStateManager
        || wil::details::g_processShutdownInProgress
        || wil::details::g_pfnDllShutdownInProgress && (unsigned __int8)wil::details::g_pfnDllShutdownInProgress() )
      {
        goto LABEL_166;
      }
      v92 = qword_180169F38;
      dwLowDateTime = 0;
      v94 = qword_180169F40;
      v95 = qword_180169F40 - (_QWORD)Source;
      pftDueTime = 0;
      if ( (_BYTE *)qword_180169F38 - (_BYTE *)Source + 16 < (unsigned __int64)(qword_180169F40 - (_QWORD)Source) )
        goto LABEL_150;
      v96 = 16;
      if ( 2 * v95 > 0x10 )
        v96 = 2 * v95;
      if ( v95 >= v96 )
        goto LABEL_150;
      LastError = GetLastError();
      v98 = (v96 & 0xFFFFFFFFFFFFFFC0uLL) + 64;
      v100 = (char *)wil::details::ProcessHeapAlloc(0, v98, v99);
      v101 = v100;
      if ( !v100 )
      {
        SetLastError(LastError);
        goto LABEL_159;
      }
      v102 = (_BYTE *)qword_180169F38 - (_BYTE *)Source;
      memcpy_s_1(v100, v98, Source, (_BYTE *)qword_180169F38 - (_BYTE *)Source);
      lpMem = (LPVOID)qword_180169F48;
      qword_180169F48 = (__int64)v101;
      if ( lpMem )
      {
        ProcessHeap = GetProcessHeap();
        HeapFree(ProcessHeap, 0, lpMem);
      }
      Source = v101;
      qword_180169F38 = &v101[v102];
      qword_180169F40 = (__int64)&v101[v98];
      SetLastError(LastError);
      v94 = qword_180169F40;
      v92 = qword_180169F38;
      dwLowDateTime = pftDueTime.dwLowDateTime;
LABEL_150:
      v104 = 0;
      if ( (unsigned __int64)v92 < v94 )
        v104 = v94 - (_QWORD)v92;
      if ( v92 )
      {
        if ( v104 >= 0x10 )
        {
          *v92 = 56643977;
          v92[1] = dwLowDateTime;
          *((_QWORD *)v92 + 1) = &qword_18016A6D8;
          goto LABEL_158;
        }
        memset_0(v92, 0, v104);
        *(_DWORD *)((__int64 (*)(void))_o__errno)() = 34;
      }
      else
      {
        *(_DWORD *)_o__errno(v91, v95, v104) = 22;
      }
      invalid_parameter_noinfo();
LABEL_158:
      qword_180169F38 = (char *)qword_180169F38 + 16;
LABEL_159:
      if ( !byte_180169F28 )
      {
        v105 = pti;
        if ( pti )
          goto LABEL_164;
        v106 = GetLastError();
        ThreadpoolTimer = CreateThreadpoolTimer(
                            _lambda_0374aa0a5d1201b2358c6bce99369c58_::_lambda_invoker_cdecl_,
                            &wil::details::g_enabledStateManager,
                            0);
        v108 = pti;
        v109 = ThreadpoolTimer;
        if ( pti )
        {
          v110 = GetLastError();
          SetThreadpoolTimer(v108, 0, 0, 0);
          WaitForThreadpoolTimerCallbacks(v108, 1);
          CloseThreadpoolTimer(v108);
          SetLastError(v110);
        }
        pti = v109;
        SetLastError(v106);
        v105 = pti;
        if ( pti )
        {
LABEL_164:
          pftDueTime = (struct _FILETIME)-3000000000LL;
          SetThreadpoolTimer(v105, &pftDueTime, 0, 0x124F8u);
          byte_180169F28 = 1;
        }
      }
      v87 = v163;
      v89 = v162;
LABEL_166:
      ReleaseSRWLockExclusive(&stru_180169F18);
      v88 = v164;
LABEL_167:
      if ( v87 )
      {
        v111 = (void (__fastcall *)(__int64, _QWORD, _QWORD, _QWORD))g_wil_details_internalRecordFeatureUsage;
        if ( g_wil_details_internalRecordFeatureUsage
          || (v111 = (void (__fastcall *)(__int64, _QWORD, _QWORD, _QWORD))g_wil_details_apiRecordFeatureUsage) != 0 )
        {
          v111(56643977, v88, v87, 0);
        }
      }
      if ( !v89 && wil::details::g_enabledStateManager )
      {
        AcquireSRWLockExclusive(&stru_180169F18);
        if ( !qword_180169F78 )
        {
          v112 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), __int64))g_wil_details_internalSubscribeFeatureStateChangeNotification;
          qword_180169F78 = 0;
          if ( g_wil_details_internalSubscribeFeatureStateChangeNotification
            || (v112 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), __int64))g_wil_details_apiSubscribeFeatureStateChangeNotification) != 0 )
          {
            v112(&qword_180169F78, _lambda_aa194dc0bf891154933407eb98fb868a_::_lambda_invoker_cdecl_, -1);
          }
        }
        ReleaseSRWLockExclusive(&stru_180169F18);
      }
      if ( (v82 & 0x400) != 0 )
      {
        v113 = (unsigned int)v84;
        if ( (v82 & 0x800) != 0 )
          LODWORD(v113) = v84 | 0x80000000;
        v114 = (void (__fastcall *)(__int64, __int64, _QWORD, _QWORD))g_wil_details_internalRecordFeatureUsage;
        if ( g_wil_details_internalRecordFeatureUsage
          || (v114 = (void (__fastcall *)(__int64, __int64, _QWORD, _QWORD))g_wil_details_apiRecordFeatureUsage) != 0 )
        {
          v114(56643977, v113, 0, 0);
        }
      }
      if ( !v89 )
      {
        if ( g_wil_details_realtimeFeatureUsageHook )
        {
          LOBYTE(v86) = 3;
          g_wil_details_realtimeFeatureUsageHook(56643977, (unsigned int)v84, v86);
        }
        if ( g_wil_details_pfnFeatureLoggingHook )
          g_wil_details_pfnFeatureLoggingHook(56643977, &v157, 0, 1, &v156, 0, 0, 1);
      }
      v115 = (unsigned __int16 *)v3;
      do
      {
        v116 = *(unsigned __int16 *)((char *)v115 + (char *)L"windows.protocol" - (char *)v3);
        v117 = *v115 - v116;
        if ( v117 )
          break;
        ++v115;
      }
      while ( v116 );
      if ( v117 )
      {
        v118 = (unsigned __int16 *)v3;
        do
        {
          v119 = *(unsigned __int16 *)((char *)v118 + (char *)L"windows.primaryInteropAssemblies" - (char *)v3);
          v120 = *v118 - v119;
          if ( v120 )
            break;
          ++v118;
        }
        while ( v119 );
        if ( v120 )
        {
          v121 = (unsigned __int16 *)v3;
          do
          {
            v122 = *(unsigned __int16 *)((char *)v121 + (char *)L"windows.printSupportExtension" - (char *)v3);
            v123 = *v121 - v122;
            if ( v123 )
              break;
            ++v121;
          }
          while ( v122 );
          if ( v123 )
          {
            v124 = (unsigned __int16 *)v3;
            do
            {
              v125 = *(unsigned __int16 *)((char *)v124 + (char *)L"windows.printSupportJobUI" - (char *)v3);
              v126 = *v124 - v125;
              if ( v126 )
                break;
              ++v124;
            }
            while ( v125 );
            if ( v126 )
            {
              v127 = (unsigned __int16 *)v3;
              do
              {
                v128 = *(unsigned __int16 *)((char *)v127 + (char *)L"windows.printSupportSettingsUI" - (char *)v3);
                v129 = *v127 - v128;
                if ( v129 )
                  break;
                ++v127;
              }
              while ( v128 );
              if ( v129 )
              {
                v130 = (unsigned __int16 *)v3;
                do
                {
                  v131 = *(unsigned __int16 *)((char *)v130 + (char *)L"windows.printSupportWorkflow" - (char *)v3);
                  v132 = *v130 - v131;
                  if ( v132 )
                    break;
                  ++v130;
                }
                while ( v131 );
                if ( v132 )
                {
                  v133 = (unsigned __int16 *)v3;
                  do
                  {
                    v134 = *(unsigned __int16 *)((char *)v133
                                               + (char *)L"windows.printSupportVirtualPrinterWorkflow"
                                               - (char *)v3);
                    v135 = *v133 - v134;
                    if ( v135 )
                      break;
                    ++v133;
                  }
                  while ( v134 );
                  if ( v135 )
                  {
                    v136 = (char *)((char *)L"windows.printSupportEnterpriseManagementUI" - (char *)v3);
                    do
                    {
                      v137 = *(unsigned __int16 *)&v136[(_QWORD)v3];
                      v138 = *v3 - v137;
                      if ( v138 )
                        break;
                      ++v3;
                    }
                    while ( v137 );
                    if ( !v138 )
                      v83 = 26;
                    result = v83;
                  }
                  else
                  {
                    result = 30;
                  }
                }
                else
                {
                  result = 31;
                }
              }
              else
              {
                result = 29;
              }
            }
            else
            {
              result = 28;
            }
          }
          else
          {
            result = 27;
          }
        }
        else
        {
          result = 25;
        }
      }
      else
      {
        result = 24;
      }
      break;
    case 's':
      v139 = (unsigned __int16 *)v3;
      do
      {
        v140 = *(unsigned __int16 *)((char *)v139 + (char *)L"windows.searchFilterHandler" - (char *)v3);
        v141 = *v139 - v140;
        if ( v141 )
          break;
        ++v139;
      }
      while ( v140 );
      if ( !v141 )
        return 32;
      v142 = (unsigned __int16 *)v3;
      do
      {
        v143 = *(unsigned __int16 *)((char *)v142 + (char *)L"windows.service" - (char *)v3);
        v144 = *v142 - v143;
        if ( v144 )
          break;
        ++v142;
      }
      while ( v143 );
      if ( !v144 )
        return 33;
      v145 = (unsigned __int16 *)v3;
      do
      {
        v146 = *(unsigned __int16 *)((char *)v145 + (char *)L"windows.shortcut" - (char *)v3);
        v147 = *v145 - v146;
        if ( v147 )
          break;
        ++v145;
      }
      while ( v146 );
      if ( !v147 )
        return 34;
      v148 = (char *)((char *)L"windows.startupTask" - (char *)v3);
      do
      {
        v149 = *(unsigned __int16 *)&v148[(_QWORD)v3];
        v150 = *v3 - v149;
        if ( v150 )
          break;
        ++v3;
      }
      while ( v149 );
      v151 = 0;
      if ( !v150 )
        return 35;
      return v151;
    case 'u':
      v152 = (char *)((char *)L"windows.userDataAccountsProvider" - (char *)v3);
      do
      {
        v153 = *(unsigned __int16 *)&v152[(_QWORD)v3];
        v154 = *v3 - v153;
        if ( v154 )
          break;
        ++v3;
      }
      while ( v153 );
      v155 = 0;
      if ( !v154 )
        return 36;
      return v155;
    default:
      return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180063050  mov     [rsp+arg_0], rcx
0x180063055  push    rbx
0x180063056  push    rsi
0x180063057  push    rdi
0x180063058  sub     rsp, 0B0h
0x18006305f  mov     rbx, rdx
0x180063062  cmp     r8d, 8
0x180063066  jb      def_1800630BF; jumptable 00000001800630BF default case, cases 101,103,105-108,110,111,113,114,116
0x18006306c  mov     r9d, 8; cchCount2
0x180063072  mov     [rsp+0C8h+bIgnoreCase], 1; bIgnoreCase
0x18006307a  mov     edx, r9d; cchCount1
0x18006307d  lea     r8, ?WindowsExtensionPrefix@Manifest@Packaging@Appx@@3QBGB; "windows."
0x180063084  mov     rcx, rbx; lpString1
0x180063087  call    cs:__imp_CompareStringOrdinal
0x18006308e  nop     dword ptr [rax+rax+00h]
0x180063093  cmp     eax, 2
0x180063096  jnz     def_1800630BF; jumptable 00000001800630BF default case, cases 101,103,105-108,110,111,113,114,116
0x18006309c  movzx   eax, word ptr [rbx+10h]
0x1800630a0  add     eax, 0FFFFFF9Fh; switch 21 cases
0x1800630a3  cmp     eax, 14h
0x1800630a6  ja      def_1800630BF; jumptable 00000001800630BF default case, cases 101,103,105-108,110,111,113,114,116
0x1800630ac  lea     rdx, __ImageBase
0x1800630b3  cdqe
0x1800630b5  mov     ecx, ds:(jpt_1800630BF - 180000000h)[rdx+rax*4]
0x1800630bc  add     rcx, rdx
0x1800630bf  jmp     rcx; switch jump
0x1800630c5  lea     r9, ?ExtensionCategoryOutOfProcessServer@Attribute@Manifest@Packaging@Appx@@3QBGB; jumptable 00000001800630BF case 97
0x1800630cc  mov     rcx, rbx
0x1800630cf  sub     r9, rbx
0x1800630d2  movzx   r8d, word ptr [rcx]
0x1800630d6  movzx   edx, word ptr [rcx+r9]
0x1800630db  sub     r8d, edx
0x1800630de  jnz     short loc_1800630E8
0x1800630e0  add     rcx, 2
0x1800630e4  test    edx, edx
0x1800630e6  jnz     short loc_1800630D2
0x1800630e8  test    r8d, r8d
0x1800630eb  jnz     short loc_1800630FE
0x1800630ed  mov     eax, 1
0x1800630f2  add     rsp, 0B0h
0x1800630f9  pop     rdi
0x1800630fa  pop     rsi
0x1800630fb  pop     rbx
0x1800630fc  retn
0x1800630fe  lea     r8, ?ExtensionCategoryAppService@Attribute@Manifest@Packaging@Appx@@3QBGB; "windows.appService"
0x180063105  mov     rax, rbx
0x180063108  sub     r8, rbx
0x18006310b  nop     dword ptr [rax+rax+00h]
0x180063110  movzx   edx, word ptr [rax]
0x180063113  movzx   ecx, word ptr [rax+r8]
0x180063118  sub     edx, ecx
0x18006311a  jnz     short loc_180063124
0x18006311c  add     rax, 2
0x180063120  test    ecx, ecx
0x180063122  jnz     short loc_180063110
0x180063124  test    edx, edx
0x180063126  jnz     short loc_180063139
0x180063128  mov     eax, 2
0x18006312d  add     rsp, 0B0h
0x180063134  pop     rdi
0x180063135  pop     rsi
0x180063136  pop     rbx
0x180063137  retn
0x180063139  lea     r8, ?ExtensionCategoryAutoPlayHandler@Attribute@Manifest@Packaging@Appx@@3QBGB; "windows.autoPlayHandler"
0x180063140  mov     rax, rbx
0x180063143  sub     r8, rbx
0x180063146  nop     word ptr [rax+rax+00000000h]
0x180063150  movzx   edx, word ptr [rax]
0x180063153  movzx   ecx, word ptr [rax+r8]
0x180063158  sub     edx, ecx
0x18006315a  jnz     short loc_180063164
0x18006315c  add     rax, 2
0x180063160  test    ecx, ecx
0x180063162  jnz     short loc_180063150
0x180063164  test    edx, edx
0x180063166  jnz     short loc_180063179
0x180063168  mov     eax, 4
0x18006316d  add     rsp, 0B0h
0x180063174  pop     rdi
0x180063175  pop     rsi
0x180063176  pop     rbx
0x180063177  retn
0x180063179  lea     rdx, ?ExtensionCategoryAppExecutionAlias@Attribute@Manifest@Packaging@Appx@@3QBGB; "windows.appExecutionAlias"
0x180063180  sub     rdx, rbx
0x180063183  movzx   ecx, word ptr [rbx]
0x180063186  movzx   eax, word ptr [rbx+rdx]
0x18006318a  sub     ecx, eax
0x18006318c  jnz     short loc_180063196
0x18006318e  add     rbx, 2
0x180063192  test    eax, eax
0x180063194  jnz     short loc_180063183
0x180063196  xor     esi, esi
0x180063198  mov     eax, 3
0x18006319d  test    ecx, ecx
0x18006319f  cmovz   esi, eax
0x1800631a2  mov     eax, esi
0x1800631a4  add     rsp, 0B0h
0x1800631ab  pop     rdi
0x1800631ac  pop     rsi
0x1800631ad  pop     rbx
0x1800631ae  retn
0x1800631b0  lea     r8, ?ExtensionCategoryBackgroundTasks@Attribute@Manifest@Packaging@Appx@@3QBGB; jumptable 00000001800630BF case 98
0x1800631b7  mov     rax, rbx
0x1800631ba  sub     r8, rbx
0x1800631bd  nop     dword ptr [rax]
0x1800631c0  movzx   edx, word ptr [rax]
0x1800631c3  movzx   ecx, word ptr [rax+r8]
0x1800631c8  sub     edx, ecx
0x1800631ca  jnz     short loc_1800631D4
0x1800631cc  add     rax, 2
0x1800631d0  test    ecx, ecx
0x1800631d2  jnz     short loc_1800631C0
0x1800631d4  test    edx, edx
0x1800631d6  jnz     short loc_1800631E9
0x1800631d8  mov     eax, 5
0x1800631dd  add     rsp, 0B0h
0x1800631e4  pop     rdi
0x1800631e5  pop     rsi
0x1800631e6  pop     rbx
0x1800631e7  retn
0x1800631e9  lea     rdx, ?ExtensionCategoryBarcodeScannerProvider@Attribute@Manifest@Packaging@Appx@@3QBGB; "windows.barcodeScannerProvider"
0x1800631f0  sub     rdx, rbx
0x1800631f3  movzx   ecx, word ptr [rbx]
0x1800631f6  movzx   eax, word ptr [rbx+rdx]
0x1800631fa  sub     ecx, eax
0x1800631fc  jnz     short loc_180063206
0x1800631fe  add     rbx, 2
0x180063202  test    eax, eax
0x180063204  jnz     short loc_1800631F3
0x180063206  xor     esi, esi
0x180063208  mov     eax, 6
0x18006320d  test    ecx, ecx
0x18006320f  cmovz   esi, eax
0x180063212  mov     eax, esi
0x180063214  add     rsp, 0B0h
0x18006321b  pop     rdi
0x18006321c  pop     rsi
0x18006321d  pop     rbx
0x18006321e  retn
0x180063220  lea     r8, ?ExtensionCategoryClassicAppCompatKeys@Attribute@Manifest@Packaging@Appx@@3QBGB; jumptable 00000001800630BF case 99
0x180063227  mov     rax, rbx
0x18006322a  sub     r8, rbx
0x18006322d  nop     dword ptr [rax]
0x180063230  movzx   edx, word ptr [rax]
0x180063233  movzx   ecx, word ptr [rax+r8]
0x180063238  sub     edx, ecx
0x18006323a  jnz     short loc_180063244
0x18006323c  add     rax, 2
0x180063240  test    ecx, ecx
0x180063242  jnz     short loc_180063230
0x180063244  test    edx, edx
0x180063246  jnz     short loc_180063259
0x180063248  mov     eax, 7
0x18006324d  add     rsp, 0B0h
0x180063254  pop     rdi
0x180063255  pop     rsi
0x180063256  pop     rbx
0x180063257  retn
0x180063259  lea     r9, ?ExtensionCategoryComInterface@Attribute@Manifest@Packaging@Appx@@3QBGB; "windows.comInterface"
0x180063260  mov     rcx, rbx
0x180063263  sub     r9, rbx
0x180063266  nop     word ptr [rax+rax+00000000h]
0x180063270  movzx   r8d, word ptr [rcx]
0x180063274  movzx   edx, word ptr [rcx+r9]
0x180063279  sub     r8d, edx
0x18006327c  jnz     short loc_180063286
0x18006327e  add     rcx, 2
0x180063282  test    edx, edx
0x180063284  jnz     short loc_180063270
0x180063286  test    r8d, r8d
0x180063289  jnz     short loc_18006329C
0x18006328b  mov     eax, 8
0x180063290  add     rsp, 0B0h
0x180063297  pop     rdi
0x180063298  pop     rsi
0x180063299  pop     rbx
0x18006329a  retn
0x18006329c  lea     r8, ?ExtensionCategoryComServer@Attribute@Manifest@Packaging@Appx@@3QBGB; "windows.comServer"
0x1800632a3  mov     rax, rbx
0x1800632a6  sub     r8, rbx
0x1800632a9  nop     dword ptr [rax+00000000h]
0x1800632b0  movzx   edx, word ptr [rax]
0x1800632b3  movzx   ecx, word ptr [rax+r8]
0x1800632b8  sub     edx, ecx
0x1800632ba  jnz     short loc_1800632C4
0x1800632bc  add     rax, 2
0x1800632c0  test    ecx, ecx
0x1800632c2  jnz     short loc_1800632B0
0x1800632c4  test    edx, edx
0x1800632c6  jnz     short loc_1800632D9
0x1800632c8  mov     eax, 9
0x1800632cd  add     rsp, 0B0h
0x1800632d4  pop     rdi
0x1800632d5  pop     rsi
0x1800632d6  pop     rbx
0x1800632d7  retn
0x1800632d9  lea     r8, ?ExtensionCategoryCustomInstall@Attribute@Manifest@Packaging@Appx@@3QBGB; "windows.customInstall"
0x1800632e0  mov     rax, rbx
0x1800632e3  sub     r8, rbx
0x1800632e6  nop     word ptr [rax+rax+00000000h]
0x1800632f0  movzx   edx, word ptr [rax]
0x1800632f3  movzx   ecx, word ptr [rax+r8]
0x1800632f8  sub     edx, ecx
0x1800632fa  jnz     short loc_180063304
0x1800632fc  add     rax, 2
0x180063300  test    ecx, ecx
0x180063302  jnz     short loc_1800632F0
0x180063304  test    edx, edx
0x180063306  jnz     short loc_180063319
0x180063308  mov     eax, 0Bh
0x18006330d  add     rsp, 0B0h
0x180063314  pop     rdi
0x180063315  pop     rsi
0x180063316  pop     rbx
0x180063317  retn
0x180063319  lea     rdx, ?ExtensionCategoryCustomDesktopEventLog@Attribute@Manifest@Packaging@Appx@@3QBGB; "windows.customDesktopEventLog"
0x180063320  sub     rdx, rbx
0x180063323  movzx   ecx, word ptr [rbx]
0x180063326  movzx   eax, word ptr [rbx+rdx]
0x18006332a  sub     ecx, eax
0x18006332c  jnz     short loc_180063336
0x18006332e  add     rbx, 2
0x180063332  test    eax, eax
0x180063334  jnz     short loc_180063323
0x180063336  xor     esi, esi
0x180063338  mov     eax, 0Ah
0x18006333d  test    ecx, ecx
0x18006333f  cmovz   esi, eax
0x180063342  mov     eax, esi
0x180063344  add     rsp, 0B0h
0x18006334b  pop     rdi
0x18006334c  pop     rsi
0x18006334d  pop     rbx
0x18006334e  retn
0x180063350  lea     r8, ?ExtensionCategoryDataShortcuts@Attribute@Manifest@Packaging@Appx@@3QBGB; jumptable 00000001800630BF case 100
0x180063357  mov     rax, rbx
0x18006335a  sub     r8, rbx
0x18006335d  nop     dword ptr [rax]
0x180063360  movzx   edx, word ptr [rax]
0x180063363  movzx   ecx, word ptr [rax+r8]
0x180063368  sub     edx, ecx
0x18006336a  jnz     short loc_180063374
0x18006336c  add     rax, 2
0x180063370  test    ecx, ecx
0x180063372  jnz     short loc_180063360
0x180063374  test    edx, edx
0x180063376  jnz     short loc_180063389
0x180063378  mov     eax, 0Ch
0x18006337d  add     rsp, 0B0h
0x180063384  pop     rdi
0x180063385  pop     rsi
0x180063386  pop     rbx
0x180063387  retn
0x180063389  lea     r8, ?ExtensionCategoryDesktopAppMigration@Attribute@Manifest@Packaging@Appx@@3QBGB; "windows.desktopAppMigration"
0x180063390  mov     rax, rbx
0x180063393  sub     r8, rbx
0x180063396  nop     word ptr [rax+rax+00000000h]
0x1800633a0  movzx   edx, word ptr [rax]
0x1800633a3  movzx   ecx, word ptr [rax+r8]
0x1800633a8  sub     edx, ecx
0x1800633aa  jnz     short loc_1800633B4
0x1800633ac  add     rax, 2
0x1800633b0  test    ecx, ecx
0x1800633b2  jnz     short loc_1800633A0
0x1800633b4  test    edx, edx
0x1800633b6  jnz     short loc_1800633C9
0x1800633b8  mov     eax, 0Dh
0x1800633bd  add     rsp, 0B0h
0x1800633c4  pop     rdi
0x1800633c5  pop     rsi
0x1800633c6  pop     rbx
0x1800633c7  retn
0x1800633c9  lea     rdx, ?ExtensionCategoryDesktopEventLogging@Attribute@Manifest@Packaging@Appx@@3QBGB; "windows.desktopEventLogging"
0x1800633d0  sub     rdx, rbx
0x1800633d3  movzx   ecx, word ptr [rbx]
0x1800633d6  movzx   eax, word ptr [rbx+rdx]
0x1800633da  sub     ecx, eax
0x1800633dc  jnz     short loc_1800633E6
0x1800633de  add     rbx, 2
0x1800633e2  test    eax, eax
0x1800633e4  jnz     short loc_1800633D3
0x1800633e6  xor     esi, esi
0x1800633e8  mov     eax, 0Eh
0x1800633ed  test    ecx, ecx
0x1800633ef  cmovz   esi, eax
0x1800633f2  mov     eax, esi
0x1800633f4  add     rsp, 0B0h
0x1800633fb  pop     rdi
0x1800633fc  pop     rsi
0x1800633fd  pop     rbx
0x1800633fe  retn
0x180063400  lea     r8, ?ExtensionCategoryFileExplorerClassicContextMenuHandler@Attribute@Manifest@Packaging@Appx@@3QBGB; jumptable 00000001800630BF case 102
0x180063407  mov     rax, rbx
0x18006340a  sub     r8, rbx
0x18006340d  nop     dword ptr [rax]
0x180063410  movzx   edx, word ptr [rax]
0x180063413  movzx   ecx, word ptr [rax+r8]
0x180063418  sub     edx, ecx
0x18006341a  jnz     short loc_180063424
0x18006341c  add     rax, 2
  ... truncated ...
```
