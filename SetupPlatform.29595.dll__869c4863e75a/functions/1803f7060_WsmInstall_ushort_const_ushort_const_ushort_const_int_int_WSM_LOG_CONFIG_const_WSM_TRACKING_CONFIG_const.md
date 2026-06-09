# WsmInstall(ushort const *,ushort const *,ushort const *,int,int,_WSM_LOG_CONFIG * const,_WSM_TRACKING_CONFIG * const)

- ea: `0x1803f7060`
- end: `0x1803f82ac`
- name: `?WsmInstall@@YAJPEBG00HHQEAU_WSM_LOG_CONFIG@@QEAU_WSM_TRACKING_CONFIG@@@Z`
- size: `4684`
- prototype: `int(const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, int, int, struct _WSM_LOG_CONFIG *const, struct _WSM_TRACKING_CONFIG *const)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1802db97c`

## callees

- `0x180057dec`
- `0x1803ee0cc`
- `0x1803f6308`
- `0x1803f663c`
- `0x1803f67a8`
- `0x1803f6d6c`
- `0x1803f7060`
- `0x180404f78`
- `0x180405298`
- `0x18040d520`
- `0x18040d7a4`
- `0x18040e2b0`
- `0x1804b4278`
- `0x1804b434c`
- `0x180509010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x1803f71ce`
- `msvcrt!_wcsicmp` at `0x1803f71ce`
- `msvcrt!wcsrchr` at `0x1803f712d`
- `msvcrt!wcsrchr` at `0x1803f712d`
- `ntdll!RtlFreeHeap` at `0x1803f738c`
- `ntdll!RtlFreeHeap` at `0x1803f738c`
- `ntdll!RtlAllocateHeap` at `0x1803f72be`
- `ntdll!RtlAllocateHeap` at `0x1803f72be`
- `ADVAPI32!RegDeleteTreeW` at `0x1803f766c`
- `ADVAPI32!RegDeleteTreeW` at `0x1803f7918`
- `ADVAPI32!RegDeleteTreeW` at `0x1803f7f26`
- `ADVAPI32!RegDeleteTreeW` at `0x1803f7feb`
- `ADVAPI32!RegDeleteTreeW` at `0x1803f766c`
- `ADVAPI32!RegDeleteTreeW` at `0x1803f7918`
- `ADVAPI32!RegDeleteTreeW` at `0x1803f7f26`
- `ADVAPI32!RegDeleteTreeW` at `0x1803f7feb`
- `ADVAPI32!RegCloseKey` at `0x1803f7dc0`
- `ADVAPI32!RegCloseKey` at `0x1803f7e3f`
- `ADVAPI32!RegCloseKey` at `0x1803f8157`
- `ADVAPI32!RegCloseKey` at `0x1803f81e5`
- `ADVAPI32!RegCloseKey` at `0x1803f7dc0`
- `ADVAPI32!RegCloseKey` at `0x1803f7e3f`
- `ADVAPI32!RegCloseKey` at `0x1803f8157`
- `ADVAPI32!RegCloseKey` at `0x1803f81e5`
- `ADVAPI32!RegSetValueExW` at `0x1803f7b85`
- `ADVAPI32!RegSetValueExW` at `0x1803f7cd4`
- `ADVAPI32!RegSetValueExW` at `0x1803f7b85`
- `ADVAPI32!RegSetValueExW` at `0x1803f7cd4`
- `ADVAPI32!RegCreateKeyExW` at `0x1803f7745`
- `ADVAPI32!RegCreateKeyExW` at `0x1803f79c8`
- `ADVAPI32!RegCreateKeyExW` at `0x1803f7745`
- `ADVAPI32!RegCreateKeyExW` at `0x1803f79c8`
- `ADVAPI32!RegRestoreKeyW` at `0x1803f77ff`
- `ADVAPI32!RegRestoreKeyW` at `0x1803f77ff`
- `KERNEL32!GetProcessHeap` at `0x1803f819e`
- `KERNEL32!GetProcessHeap` at `0x1803f81f4`
- `KERNEL32!GetProcessHeap` at `0x1803f820d`
- `KERNEL32!GetProcessHeap` at `0x1803f822b`
- `KERNEL32!GetProcessHeap` at `0x1803f819e`
- `KERNEL32!GetProcessHeap` at `0x1803f81f4`
- `KERNEL32!GetProcessHeap` at `0x1803f820d`
- `KERNEL32!GetProcessHeap` at `0x1803f822b`
- `KERNEL32!HeapFree` at `0x1803f81ac`
- `KERNEL32!HeapFree` at `0x1803f8202`
- `KERNEL32!HeapFree` at `0x1803f821b`
- `KERNEL32!HeapFree` at `0x1803f8239`
- `KERNEL32!HeapFree` at `0x1803f81ac`
- `KERNEL32!HeapFree` at `0x1803f8202`
- `KERNEL32!HeapFree` at `0x1803f821b`
- `KERNEL32!HeapFree` at `0x1803f8239`
- `KERNEL32!GetLastError` at `0x1803f7141`
- `KERNEL32!GetLastError` at `0x1803f71e1`
- `KERNEL32!GetLastError` at `0x1803f73cc`
- `KERNEL32!GetLastError` at `0x1803f73e2`
- `KERNEL32!GetLastError` at `0x1803f73fe`
- `KERNEL32!GetLastError` at `0x1803f748c`
- `KERNEL32!GetLastError` at `0x1803f74a6`
- `KERNEL32!GetLastError` at `0x1803f74e8`
- `KERNEL32!GetLastError` at `0x1803f7500`
- `KERNEL32!GetLastError` at `0x1803f7599`
- `KERNEL32!GetLastError` at `0x1803f768e`
- `KERNEL32!GetLastError` at `0x1803f7761`
- `KERNEL32!GetLastError` at `0x1803f781e`
- `KERNEL32!GetLastError` at `0x1803f7938`
- `KERNEL32!GetLastError` at `0x1803f79e1`
- `KERNEL32!GetLastError` at `0x1803f7a59`
- `KERNEL32!GetLastError` at `0x1803f7ad0`
- `KERNEL32!GetLastError` at `0x1803f7ba0`
- `KERNEL32!GetLastError` at `0x1803f7c1e`
- `KERNEL32!GetLastError` at `0x1803f7cf3`
- `KERNEL32!GetLastError` at `0x1803f7d51`
- `KERNEL32!GetLastError` at `0x1803f7dd9`
- `KERNEL32!GetLastError` at `0x1803f7e58`
- `KERNEL32!GetLastError` at `0x1803f7f4f`
- `KERNEL32!GetLastError` at `0x1803f800e`
- `KERNEL32!GetLastError` at `0x1803f80bd`
- `KERNEL32!GetLastError` at `0x1803f80e0`
- `KERNEL32!GetLastError` at `0x1803f7141`
- `KERNEL32!GetLastError` at `0x1803f71e1`
- `KERNEL32!GetLastError` at `0x1803f73cc`
- `KERNEL32!GetLastError` at `0x1803f73e2`
- `KERNEL32!GetLastError` at `0x1803f73fe`
- `KERNEL32!GetLastError` at `0x1803f748c`
- `KERNEL32!GetLastError` at `0x1803f74a6`
- `KERNEL32!GetLastError` at `0x1803f74e8`
- `KERNEL32!GetLastError` at `0x1803f7500`
- `KERNEL32!GetLastError` at `0x1803f7599`
- `KERNEL32!GetLastError` at `0x1803f768e`
- `KERNEL32!GetLastError` at `0x1803f7761`
- `KERNEL32!GetLastError` at `0x1803f781e`
- `KERNEL32!GetLastError` at `0x1803f7938`
- `KERNEL32!GetLastError` at `0x1803f79e1`
- `KERNEL32!GetLastError` at `0x1803f7a59`
- `KERNEL32!GetLastError` at `0x1803f7ad0`
- `KERNEL32!GetLastError` at `0x1803f7ba0`
- `KERNEL32!GetLastError` at `0x1803f7c1e`
- `KERNEL32!GetLastError` at `0x1803f7cf3`
- `KERNEL32!GetLastError` at `0x1803f7d51`
- `KERNEL32!GetLastError` at `0x1803f7dd9`
- `KERNEL32!GetLastError` at `0x1803f7e58`
- `KERNEL32!GetLastError` at `0x1803f7f4f`
- `KERNEL32!GetLastError` at `0x1803f800e`
- `KERNEL32!GetLastError` at `0x1803f80bd`
- `KERNEL32!GetLastError` at `0x1803f80e0`
- `KERNEL32!CopyFileExW` at `0x1803f74da`
- `KERNEL32!CopyFileExW` at `0x1803f74da`
- `WDSCORE!WdsSetupLogMessageW` at `0x1803f71ac`
- `WDSCORE!WdsSetupLogMessageW` at `0x1803f724c`
- `WDSCORE!WdsSetupLogMessageW` at `0x1803f7466`
- `WDSCORE!WdsSetupLogMessageW` at `0x1803f756e`
- `WDSCORE!WdsSetupLogMessageW` at `0x1803f7601`
- `WDSCORE!WdsSetupLogMessageW` at `0x1803f76f9`
- `WDSCORE!WdsSetupLogMessageW` at `0x1803f7889`
- `WDSCORE!WdsSetupLogMessageW` at `0x1803f7b35`
- `WDSCORE!WdsSetupLogMessageW` at `0x1803f7db4`
- `WDSCORE!WdsSetupLogMessageW` at `0x1803f7fbc`
- `WDSCORE!WdsSetupLogMessageW` at `0x1803f8078`
- `WDSCORE!WdsSetupLogMessageW` at `0x1803f813d`
- `WDSCORE!WdsSetupLogMessageW` at `0x1803f71ac`
- `WDSCORE!WdsSetupLogMessageW` at `0x1803f724c`
- `WDSCORE!WdsSetupLogMessageW` at `0x1803f7466`
- `WDSCORE!WdsSetupLogMessageW` at `0x1803f756e`
- `WDSCORE!WdsSetupLogMessageW` at `0x1803f7601`
- `WDSCORE!WdsSetupLogMessageW` at `0x1803f76f9`
- `WDSCORE!WdsSetupLogMessageW` at `0x1803f7889`
- `WDSCORE!WdsSetupLogMessageW` at `0x1803f7b35`
- `WDSCORE!WdsSetupLogMessageW` at `0x1803f7db4`
- `WDSCORE!WdsSetupLogMessageW` at `0x1803f7fbc`
- `WDSCORE!WdsSetupLogMessageW` at `0x1803f8078`
- `WDSCORE!WdsSetupLogMessageW` at `0x1803f813d`
- `WDSCORE!CurrentIP` at `0x1803f7149`
- `WDSCORE!CurrentIP` at `0x1803f71e9`
- `WDSCORE!CurrentIP` at `0x1803f7406`
- `WDSCORE!CurrentIP` at `0x1803f7508`
- `WDSCORE!CurrentIP` at `0x1803f75a1`
- `WDSCORE!CurrentIP` at `0x1803f7696`
- `WDSCORE!CurrentIP` at `0x1803f7769`
- `WDSCORE!CurrentIP` at `0x1803f7826`
- `WDSCORE!CurrentIP` at `0x1803f7940`
- `WDSCORE!CurrentIP` at `0x1803f79e9`
- `WDSCORE!CurrentIP` at `0x1803f7a61`
- `WDSCORE!CurrentIP` at `0x1803f7ad8`
- `WDSCORE!CurrentIP` at `0x1803f7ba8`
- `WDSCORE!CurrentIP` at `0x1803f7c26`
- `WDSCORE!CurrentIP` at `0x1803f7cfb`
- `WDSCORE!CurrentIP` at `0x1803f7d59`
- `WDSCORE!CurrentIP` at `0x1803f7de1`
- `WDSCORE!CurrentIP` at `0x1803f7e60`
- `WDSCORE!CurrentIP` at `0x1803f7f57`
- `WDSCORE!CurrentIP` at `0x1803f8016`
- `WDSCORE!CurrentIP` at `0x1803f80e8`
- `WDSCORE!CurrentIP` at `0x1803f7149`
- `WDSCORE!CurrentIP` at `0x1803f71e9`
- `WDSCORE!CurrentIP` at `0x1803f7406`
- `WDSCORE!CurrentIP` at `0x1803f7508`
- `WDSCORE!CurrentIP` at `0x1803f75a1`
- `WDSCORE!CurrentIP` at `0x1803f7696`
- `WDSCORE!CurrentIP` at `0x1803f7769`
- `WDSCORE!CurrentIP` at `0x1803f7826`
- `WDSCORE!CurrentIP` at `0x1803f7940`
- `WDSCORE!CurrentIP` at `0x1803f79e9`
- `WDSCORE!CurrentIP` at `0x1803f7a61`
- `WDSCORE!CurrentIP` at `0x1803f7ad8`
- `WDSCORE!CurrentIP` at `0x1803f7ba8`
- `WDSCORE!CurrentIP` at `0x1803f7c26`
- `WDSCORE!CurrentIP` at `0x1803f7cfb`
- `WDSCORE!CurrentIP` at `0x1803f7d59`
- `WDSCORE!CurrentIP` at `0x1803f7de1`
- `WDSCORE!CurrentIP` at `0x1803f7e60`
- `WDSCORE!CurrentIP` at `0x1803f7f57`
- `WDSCORE!CurrentIP` at `0x1803f8016`
- `WDSCORE!CurrentIP` at `0x1803f80e8`

## string_xrefs

- `0x1803f77e2`: `SeRestorePrivilege`
- `0x1803f78b2`: `SeRestorePrivilege`
- `0x1803f816f`: `SeRestorePrivilege`
- `0x1803f77cc`: `SeBackupPrivilege`
- `0x1803f78d9`: `SeBackupPrivilege`
- `0x1803f818b`: `SeBackupPrivilege`
- `0x1803f7152`: `WsmInstall: Bad driver file path %s; hr = 0x%x`
- `0x1803f7184`: `WsmInstall`
- `0x1803f7224`: `WsmInstall`
- `0x1803f743e`: `WsmInstall`
- `0x1803f7531`: `WsmInstall`
- `0x1803f75d9`: `WsmInstall`
- `0x1803f76c1`: `WsmInstall`
- `0x1803f778e`: `WsmInstall`
- `0x1803f7861`: `WsmInstall`
- `0x1803f796b`: `WsmInstall`
- `0x1803f7a14`: `WsmInstall`
- `0x1803f7a89`: `WsmInstall`
- `0x1803f7afd`: `WsmInstall`
- `0x1803f7bd0`: `WsmInstall`
- `0x1803f7c4e`: `WsmInstall`
- `0x1803f7d23`: `WsmInstall`
- `0x1803f7d77`: `WsmInstall`
- `0x1803f7e09`: `WsmInstall`
- `0x1803f7e88`: `WsmInstall`
- `0x1803f7f7a`: `WsmInstall`
- `0x1803f8052`: `WsmInstall`
- `0x1803f8094`: `WsmInstall`
- `0x1803f825c`: `WsmInstall`
- `0x1803f740f`: `WsmInstall: Failed to build drivers directory path; hr = 0x%x`
- `0x1803f71f2`: `WsmInstall: Incorrect driver file name %s; hr = 0x%x`
- `0x1803f7518`: `WsmInstall: Failed to copy driver file %s -> %s; hr = 0x%x`
- `0x1803f75aa`: `WsmInstall: Failed to build driver file destination path; hr = 0x%x`
- `0x1803f7349`: `System32\drivers`
- `0x1803f73af`: `%WINDIR%\System32\drivers`
- `0x1803f7c2f`: `WsmInstall: Failed to create driver config; hr = 0x%x`
- `0x1803f7bb1`: `WsmInstall: Failed to set log config value; hr = 0x%x`
- `0x1803f7d5f`: `WsmInstall: Empty driver config provided; will not set`
- `0x1803f7d04`: `WsmInstall: Failed to set tracking config value; hr = 0x%x`
- `0x1803f7e69`: `WsmInstall: Failed to close service key; hr = 0x%x`
- `0x1803f7dea`: `WsmInstall: Failed to close config key; hr = 0x%x`
- `0x1803f801f`: `WsmInstall: Failed to clean up service key %s; hr = 0x%x`
- `0x1803f7f60`: `WsmInstall: Failed to clean up config key %s; hr = 0x%x`
- `0x1803f7772`: `WsmInstall: Failed to create service key %s; hr = 0x%x`
- `0x1803f769f`: `WsmInstall: Failed to delete service key %s; hr = 0x%x`
- `0x1803f782f`: `WsmInstall: Failed to restore service registry hive %s; hr = 0x%x`
- `0x1803f79f2`: `WsmInstall: Failed to create config key %s; hr = 0x%x`
- `0x1803f7949`: `WsmInstall: Failed to delete config key %s; hr = 0x%x`
- `0x1803f7ade`: `WsmInstall: Empty log config provided`
- `0x1803f7a6a`: `WsmInstall: Failed to create log config; hr = 0x%x`
- `0x1803f80f1`: `WsmInstall: Failed to clean up driver file %s; hr = 0x%x`
- `0x1803f7b6c`: `LogConfig`
- `0x1803f7cc8`: `TrackingConfig`

## pseudocode

```c
__int64 __fastcall WsmInstall(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        int a4,
        int a5,
        struct _WSM_LOG_CONFIG *const a6,
        struct _WSM_TRACKING_CONFIG *const a7)
{
  const unsigned __int16 *v10; // rbx
  char *v11; // r14
  wchar_t *v12; // rax
  int ServiceKeyName; // esi
  DWORD LastError; // edi
  __int64 v15; // rbx
  struct tagLOG_PARTIAL_MSG *v16; // rax
  const wchar_t *Expand; // rdi
  int v18; // r13d
  char v19; // bl
  const char *v20; // r14
  DWORD v21; // edi
  __int64 v22; // rbx
  struct tagLOG_PARTIAL_MSG *v23; // rax
  int v24; // edi
  __int64 v25; // rbx
  wchar_t *Heap; // rax
  HRESULT v27; // eax
  unsigned __int16 v28; // bx
  HRESULT v29; // eax
  HRESULT v30; // eax
  signed int v31; // eax
  bool v32; // sf
  signed int v33; // eax
  DWORD v34; // edi
  __int64 v35; // rbx
  struct tagLOG_PARTIAL_MSG *v36; // rax
  signed int v37; // eax
  bool v38; // sf
  bool v39; // sf
  signed int v40; // eax
  DWORD v41; // edi
  __int64 v42; // rbx
  struct tagLOG_PARTIAL_MSG *v43; // rax
  WCHAR *v44; // r12
  DWORD v45; // edi
  __int64 v46; // rbx
  struct tagLOG_PARTIAL_MSG *v47; // rax
  unsigned __int16 *v48; // rbx
  const WCHAR *v49; // r15
  int v50; // eax
  DWORD v51; // edi
  __int64 v52; // rbx
  struct tagLOG_PARTIAL_MSG *v53; // rax
  DWORD v54; // edi
  LSTATUS v55; // eax
  DWORD v56; // edi
  __int64 v57; // rbx
  struct tagLOG_PARTIAL_MSG *v58; // rax
  bool v59; // sf
  DWORD v60; // edi
  __int64 v61; // rbx
  struct tagLOG_PARTIAL_MSG *v62; // rax
  int ConfigKeyName; // eax
  int v64; // eax
  DWORD v65; // edi
  __int64 v66; // rbx
  struct tagLOG_PARTIAL_MSG *v67; // rax
  LSTATUS v68; // eax
  DWORD v69; // edi
  __int64 v70; // rbx
  struct tagLOG_PARTIAL_MSG *v71; // rax
  int v72; // eax
  DWORD v73; // edi
  __int64 v74; // rbx
  struct tagLOG_PARTIAL_MSG *v75; // rax
  struct IWsmLogConfig *v76; // rdi
  DWORD v77; // edi
  __int64 v78; // rbx
  struct tagLOG_PARTIAL_MSG *v79; // rax
  DWORD v80; // ebx
  const BYTE *v81; // rax
  LSTATUS v82; // eax
  DWORD v83; // edi
  __int64 v84; // rbx
  struct tagLOG_PARTIAL_MSG *v85; // rax
  int v86; // eax
  DWORD v87; // edi
  __int64 v88; // rbx
  struct tagLOG_PARTIAL_MSG *v89; // rax
  struct IWsmTrackingConfig *v90; // rdi
  DWORD v91; // ebx
  const BYTE *v92; // rax
  LSTATUS v93; // eax
  DWORD v94; // edi
  __int64 v95; // rbx
  struct tagLOG_PARTIAL_MSG *v96; // rax
  DWORD v97; // edi
  __int64 v98; // rbx
  struct tagLOG_PARTIAL_MSG *v99; // rax
  LSTATUS v100; // eax
  DWORD v101; // edi
  __int64 v102; // rbx
  struct tagLOG_PARTIAL_MSG *v103; // rax
  LSTATUS v104; // eax
  DWORD v105; // edi
  __int64 v106; // rbx
  struct tagLOG_PARTIAL_MSG *v107; // rax
  int v108; // ebx
  int v109; // eax
  int v110; // r14d
  DWORD v111; // edi
  __int64 v112; // rbx
  struct tagLOG_PARTIAL_MSG *v113; // rax
  int v114; // eax
  int v115; // r14d
  DWORD v116; // edi
  __int64 v117; // rbx
  struct tagLOG_PARTIAL_MSG *v118; // rax
  char *v119; // r15
  signed int v120; // eax
  int v121; // r14d
  DWORD v122; // edi
  __int64 v123; // rbx
  struct tagLOG_PARTIAL_MSG *v124; // rax
  HANDLE ProcessHeap; // rax
  WCHAR *v126; // rbx
  HANDLE v127; // rax
  HANDLE v128; // rax
  HANDLE v129; // rax
  DWORD lpSecurityAttributes; // [rsp+30h] [rbp-C1h]
  DWORD lpSecurityAttributesa; // [rsp+30h] [rbp-C1h]
  wchar_t *P; // [rsp+60h] [rbp-91h]
  int v134; // [rsp+68h] [rbp-89h]
  LPCWSTR v135; // [rsp+70h] [rbp-81h] BYREF
  LPVOID lpMem; // [rsp+78h] [rbp-79h]
  LPCWSTR lpSubKey; // [rsp+80h] [rbp-71h] BYREF
  __int64 v138; // [rsp+88h] [rbp-69h]
  __int64 v139; // [rsp+90h] [rbp-61h]
  HKEY phkResult; // [rsp+98h] [rbp-59h] BYREF
  HKEY hKey; // [rsp+A0h] [rbp-51h] BYREF
  size_t cchDest; // [rsp+A8h] [rbp-49h] BYREF
  STRSAFE_LPWSTR pszDest; // [rsp+B0h] [rbp-41h] BYREF
  struct IWsmTrackingConfig *v144; // [rsp+B8h] [rbp-39h] BYREF
  struct IWsmLogConfig *v145; // [rsp+C0h] [rbp-31h] BYREF
  unsigned __int16 *v146; // [rsp+C8h] [rbp-29h] BYREF
  __int128 v147; // [rsp+D0h] [rbp-21h] BYREF
  char v148; // [rsp+E0h] [rbp-11h]
  int v149; // [rsp+E1h] [rbp-10h]
  __int16 v150; // [rsp+E5h] [rbp-Ch]
  char v151; // [rsp+E7h] [rbp-Ah]
  __int128 v152; // [rsp+E8h] [rbp-9h]
  int v154; // [rsp+148h] [rbp+57h]
  char v155[8]; // [rsp+160h] [rbp+6Fh]

  v149 = 0;
  v139 = 0;
  v138 = 0;
  v150 = 0;
  v10 = a1;
  v151 = 0;
  v148 = 0;
  v146 = 0;
  lpSubKey = 0;
  hKey = 0;
  v145 = 0;
  v144 = 0;
  v135 = 0;
  phkResult = 0;
  v147 = 0;
  v152 = 0;
  if ( !a2 || !a3 || a1 && a4 || !a6 || !*(_QWORD *)a6 )
  {
    CSystemHive::Unload((CSystemHive *)&v147);
    return 2147942487LL;
  }
  P = 0;
  lpMem = 0;
  v11 = 0;
  v155[0] = 0;
  v134 = 0;
  v154 = 0;
  v12 = wcsrchr(a2, 0x5Cu);
  if ( !v12 )
  {
    ServiceKeyName = -2147024735;
    LastError = GetLastError();
    v15 = CurrentIP();
    v16 = ConstructPartialMsgW(
            0x2000000u,
            "WsmInstall: Bad driver file path %s; hr = 0x%x",
            (const char *)a2,
            -2147024735);
    WdsSetupLogMessageW(
      v16,
      0,
      L"D",
      0,
      833,
      L"base\\ntsetup\\setupplatform\\deployment\\monitor\\api\\winsetupmonapi.cpp",
      L"WsmInstall",
      v15,
      LastError,
      0,
      0);
    Expand = 0;
    v18 = 0;
    v19 = 0;
LABEL_118:
    v44 = (WCHAR *)v135;
    goto LABEL_119;
  }
  v20 = (const char *)(v12 + 1);
  if ( _wcsicmp(v12 + 1, L"WinSetupMon.sys") )
  {
    ServiceKeyName = -2147024809;
    v21 = GetLastError();
    v22 = CurrentIP();
    v23 = ConstructPartialMsgW(0x2000000u, "WsmInstall: Incorrect driver file name %s; hr = 0x%x", v20, -2147024809);
    WdsSetupLogMessageW(
      v23,
      0,
      L"D",
      0,
      841,
      L"base\\ntsetup\\setupplatform\\deployment\\monitor\\api\\winsetupmonapi.cpp",
      L"WsmInstall",
      v22,
      v21,
      0,
      0);
    Expand = 0;
    v11 = 0;
    v18 = 0;
    v19 = 0;
    goto LABEL_118;
  }
  if ( v10 )
  {
    v24 = 0;
    pszDest = 0;
    v25 = -1;
    cchDest = 0;
    do
      ++v25;
    while ( a1[v25] );
    if ( (_DWORD)v25 && a1[(unsigned int)(v25 - 1)] != 92 )
      v24 = 1;
    Heap = (wchar_t *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 2LL * (unsigned int)(v25 + v24 + 17));
    P = Heap;
    if ( Heap )
    {
      v27 = StringCchCopyNExW(
              Heap,
              (unsigned int)(v25 + v24 + 17),
              a1,
              (unsigned int)v25,
              &pszDest,
              &cchDest,
              lpSecurityAttributes);
      v28 = v27;
      if ( v27 >= 0 )
      {
        if ( !v24
          || (v29 = StringCchCopyNExW(pszDest, cchDest, L"\\", 1u, &pszDest, &cchDest, lpSecurityAttributesa),
              v28 = v29,
              v29 >= 0) )
        {
          v30 = StringCchCopyNW(pszDest, cchDest, L"System32\\drivers", 0x10u);
          v28 = v30;
          if ( v30 >= 0 )
          {
            Expand = P;
            NtCurrentTeb()->LastErrorValue = 0;
LABEL_26:
            v10 = a1;
            goto LABEL_28;
          }
        }
      }
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
      NtCurrentTeb()->LastErrorValue = v28;
    }
    else
    {
      NtCurrentTeb()->LastErrorValue = 8;
    }
    P = 0;
    Expand = 0;
    goto LABEL_26;
  }
  Expand = (const wchar_t *)AllocateExpand(L"%WINDIR%\\System32\\drivers");
  P = (wchar_t *)Expand;
LABEL_28:
  if ( Expand )
  {
    lpMem = (LPVOID)BuildPath(Expand, (STRSAFE_PCNZWCH)v20);
    v11 = (char *)lpMem;
    if ( lpMem )
      goto LABEL_43;
    v37 = GetLastError();
    v38 = v37 < 0;
    if ( v37 > 0 )
      v38 = 1;
    if ( v38 )
    {
      ServiceKeyName = GetLastError();
      v39 = ServiceKeyName < 0;
      if ( ServiceKeyName > 0 )
      {
        ServiceKeyName = (unsigned __int16)ServiceKeyName | 0x80070000;
        v39 = ServiceKeyName < 0;
      }
      if ( !v39 )
      {
LABEL_43:
        if ( !CopyFileExW(a2, (LPCWSTR)lpMem, 0, 0, 0, 0) )
        {
          v40 = GetLastError();
          ServiceKeyName = v40;
          if ( v40 > 0 )
            ServiceKeyName = (unsigned __int16)v40 | 0x80070000;
          v41 = GetLastError();
          v42 = CurrentIP();
          v43 = ConstructPartialMsgW(
                  0x2000000u,
                  "WsmInstall: Failed to copy driver file %s -> %s; hr = 0x%x",
                  (const char *)a2,
                  (const char *)lpMem,
                  ServiceKeyName);
          WdsSetupLogMessageW(
            v43,
            0,
            L"D",
            0,
            870,
            L"base\\ntsetup\\setupplatform\\deployment\\monitor\\api\\winsetupmonapi.cpp",
            L"WsmInstall",
            v42,
            v41,
            0,
            0);
          goto LABEL_47;
        }
        if ( v10 )
        {
          ServiceKeyName = CSystemHive::Load((CSystemHive *)&v147, v10, (const unsigned __int16 **)&v146);
          if ( ServiceKeyName < 0 )
            goto LABEL_172;
          v48 = v146;
          v155[0] = 1;
        }
        else
        {
          v48 = L"SYSTEM";
        }
        ServiceKeyName = WsmGetServiceKeyName(v48, &lpSubKey);
        if ( ServiceKeyName < 0 )
        {
          v18 = 0;
          v19 = v155[0];
          goto LABEL_118;
        }
        v49 = lpSubKey;
        v50 = RegDeleteTreeW(HKEY_LOCAL_MACHINE, lpSubKey);
        if ( v50 > 0 )
          v50 = (unsigned __int16)v50 | 0x80070000;
        ServiceKeyName = 0;
        if ( v50 != -2147024894 )
          ServiceKeyName = v50;
        if ( ServiceKeyName >= 0 )
        {
          v54 = a4 != 0;
          v55 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, v49, 0, 0, v54, 0xF003Fu, 0, &hKey, 0);
          ServiceKeyName = v55;
          if ( v55 > 0 )
            ServiceKeyName = (unsigned __int16)v55 | 0x80070000;
          if ( ServiceKeyName >= 0 )
          {
            v134 = EnablePrivilegeEx(L"SeBackupPrivilege");
            v154 = EnablePrivilegeEx(L"SeRestorePrivilege");
            ServiceKeyName = RegRestoreKeyW(hKey, a3, 8u);
            v59 = ServiceKeyName < 0;
            if ( ServiceKeyName > 0 )
            {
              ServiceKeyName = (unsigned __int16)ServiceKeyName | 0x80070000;
              v59 = ServiceKeyName < 0;
            }
            if ( !v59 )
            {
              if ( v154 == 1 && !(_DWORD)v138 )
                EnablePrivilegeEx(L"SeRestorePrivilege");
              v18 = 0;
              v154 = 0;
              LODWORD(v139) = 0;
              if ( v134 == 1 && !HIDWORD(v138) )
                EnablePrivilegeEx(L"SeBackupPrivilege");
              v134 = 0;
              HIDWORD(v139) = 0;
              ConfigKeyName = WsmGetConfigKeyName(v48, &v135);
              v44 = (WCHAR *)v135;
              ServiceKeyName = ConfigKeyName;
              if ( ConfigKeyName < 0 )
                goto LABEL_92;
              v64 = RegDeleteTreeW(HKEY_LOCAL_MACHINE, v135);
              if ( v64 > 0 )
                v64 = (unsigned __int16)v64 | 0x80070000;
              ServiceKeyName = 0;
              if ( v64 != -2147024894 )
                ServiceKeyName = v64;
              if ( ServiceKeyName >= 0 )
              {
                v68 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, v44, 0, 0, v54, 0x20006u, 0, &phkResult, 0);
                ServiceKeyName = v68;
                if ( v68 > 0 )
                  ServiceKeyName = (unsigned __int16)v68 | 0x80070000;
                if ( ServiceKeyName >= 0 )
                {
                  v72 = CreateInstance(a6, &v145);
                  ServiceKeyName = v72 | 0x10000000;
                  if ( v72 >= 0 )
                  {
                    v76 = v145;
                    if ( (**(__int64 (__fastcall ***)(struct IWsmLogConfig *))v145)(v145) )
                    {
                      v80 = (*(__int64 (__fastcall **)(struct IWsmLogConfig *))(*(_QWORD *)v76 + 24LL))(v76);
                      v81 = (const BYTE *)(*(__int64 (__fastcall **)(struct IWsmLogConfig *))(*(_QWORD *)v76 + 16LL))(v76);
                      v82 = RegSetValueExW(phkResult, L"LogConfig", 0, 3u, v81, v80);
                      ServiceKeyName = v82;
                      if ( v82 > 0 )
                        ServiceKeyName = (unsigned __int16)v82 | 0x80070000;
                      if ( ServiceKeyName >= 0 )
                      {
                        if ( a7 )
                        {
                          v86 = CreateInstance(a7, &v144);
                          ServiceKeyName = v86 | 0x10000000;
                          if ( v86 < 0 )
                          {
                            v87 = GetLastError();
                            v88 = CurrentIP();
                            v89 = ConstructPartialMsgW(
                                    0x2000000u,
                                    "WsmInstall: Failed to create driver config; hr = 0x%x",
                                    ServiceKeyName);
                            WdsSetupLogMessageW(
                              v89,
                              0,
                              L"D",
                              0,
                              1045,
                              L"base\\ntsetup\\setupplatform\\deployment\\monitor\\api\\winsetupmonapi.cpp",
                              L"WsmInstall",
                              v88,
                              v87,
                              0,
                              0);
                            goto LABEL_92;
                          }
                          v90 = v144;
                          if ( (**(__int64 (__fastcall ***)(struct IWsmTrackingConfig *))v144)(v144) )
                          {
                            v91 = (*(__int64 (__fastcall **)(struct IWsmTrackingConfig *))(*(_QWORD *)v90 + 24LL))(v90);
                            v92 = (const BYTE *)(*(__int64 (__fastcall **)(struct IWsmTrackingConfig *))(*(_QWORD *)v90 + 16LL))(v90);
                            v93 = RegSetValueExW(phkResult, L"TrackingConfig", 0, 3u, v92, v91);
                            ServiceKeyName = v93;
                            if ( v93 > 0 )
                              ServiceKeyName = (unsigned __int16)v93 | 0x80070000;
                            if ( ServiceKeyName < 0 )
                            {
                              v94 = GetLastError();
                              v95 = CurrentIP();
                              v96 = ConstructPartialMsgW(
                                      0x2000000u,
                                      "WsmInstall: Failed to set tracking config value; hr = 0x%x",
                                      ServiceKeyName);
                              WdsSetupLogMessageW(
                                v96,
                                0,
                                L"D",
                                0,
                                1060,
                                L"base\\ntsetup\\setupplatform\\deployment\\monitor\\api\\winsetupmonapi.cpp",
                                L"WsmInstall",
                                v95,
                                v94,
                                0,
                                0);
                              goto LABEL_92;
                            }
                          }
                          else
                          {
                            v97 = GetLastError();
                            v98 = CurrentIP();
                            v99 = ConstructPartialMsgW(
                                    0x3000000u,
                                    "WsmInstall: Empty driver config provided; will not set");
                            WdsSetupLogMessageW(
                              v99,
                              0,
                              L"D",
                              0,
                              1066,
                              L"base\\ntsetup\\setupplatform\\deployment\\monitor\\api\\winsetupmonapi.cpp",
                              L"WsmInstall",
                              v98,
                              v97,
                              0,
                              0);
                          }
                        }
                        v100 = RegCloseKey(phkResult);
                        ServiceKeyName = v100;
                        if ( v100 > 0 )
                          ServiceKeyName = (unsigned __int16)v100 | 0x80070000;
                        if ( ServiceKeyName >= 0 )
                        {
                          phkResult = 0;
                          v104 = RegCloseKey(hKey);
                          ServiceKeyName = v104;
                          if ( v104 > 0 )
                            ServiceKeyName = (unsigned __int16)v104 | 0x80070000;
                          if ( ServiceKeyName >= 0 )
                          {
                            v19 = v155[0];
                            hKey = 0;
                            if ( v155[0] )
                            {
                              ServiceKeyName = CSystemHive::Unload((CSystemHive *)&v147);
                              if ( ServiceKeyName < 0 )
                              {
                                Expand = P;
                                goto LABEL_120;
                              }
                            }
                            v119 = v11;
                            goto LABEL_148;
                          }
                          v105 = GetLastError();
                          v106 = CurrentIP();
                          v107 = ConstructPartialMsgW(
                                   0x2000000u,
                                   "WsmInstall: Failed to close service key; hr = 0x%x",
                                   ServiceKeyName);
                          WdsSetupLogMessageW(
                            v107,
                            0,
                            L"D",
                            0,
                            1085,
                            L"base\\ntsetup\\setupplatform\\deployment\\monitor\\api\\winsetupmonapi.cpp",
                            L"WsmInstall",
                            v106,
                            v105,
                            0,
                            0);
                        }
                        else
                        {
                          v101 = GetLastError();
                          v102 = CurrentIP();
                          v103 = ConstructPartialMsgW(
                                   0x2000000u,
                                   "WsmInstall: Failed to close config key; hr = 0x%x",
                                   ServiceKeyName);
                          WdsSetupLogMessageW(
                            v103,
                            0,
                            L"D",
                            0,
                            1077,
                            L"base\\ntsetup\\setupplatform\\deployment\\monitor\\api\\winsetupmonapi.cpp",
                            L"WsmInstall",
                            v102,
                            v101,
                            0,
                            0);
                        }
                      }
                      else
                      {
                        v83 = GetLastError();
                        v84 = CurrentIP();
                        v85 = ConstructPartialMsgW(
                                0x2000000u,
                                "WsmInstall: Failed to set log config value; hr = 0x%x",
                                ServiceKeyName);
                        WdsSetupLogMessageW(
                          v85,
                          0,
                          L"D",
                          0,
                          1032,
                          L"base\\ntsetup\\setupplatform\\deployment\\monitor\\api\\winsetupmonapi.cpp",
                          L"WsmInstall",
                          v84,
                          v83,
                          0,
                          0);
                      }
                    }
                    else
                    {
                      ServiceKeyName = -2147024883;
                      v77 = GetLastError();
                      v78 = CurrentIP();
                      v79 = ConstructPartialMsgW(0x2000000u, "WsmInstall: Empty log config provided");
                      WdsSetupLogMessageW(
                        v79,
                        0,
                        L"D",
                        0,
                        1019,
                        L"base\\ntsetup\\setupplatform\\deployment\\monitor\\api\\winsetupmonapi.cpp",
                        L"WsmInstall",
                        v78,
                        v77,
                        0,
                        0);
                    }
                  }
                  else
                  {
                    v73 = GetLastError();
                    v74 = CurrentIP();
                    v75 = ConstructPartialMsgW(
                            0x2000000u,
                            "WsmInstall: Failed to create log config; hr = 0x%x",
                            ServiceKeyName);
                    WdsSetupLogMessageW(
                      v75,
                      0,
                      L"D",
                      0,
                      1012,
                      L"base\\ntsetup\\setupplatform\\deployment\\monitor\\api\\winsetupmonapi.cpp",
                      L"WsmInstall",
                      v74,
                      v73,
                      0,
                      0);
                  }
                }
                else
                {
                  v69 = GetLastError();
                  v70 = CurrentIP();
                  v71 = ConstructPartialMsgW(
                          0x2000000u,
                          "WsmInstall: Failed to create config key %s; hr = 0x%x",
                          (const char *)v44,
                          ServiceKeyName);
                  WdsSetupLogMessageW(
                    v71,
                    0,
                    L"D",
                    0,
                    1001,
                    L"base\\ntsetup\\setupplatform\\deployment\\monitor\\api\\winsetupmonapi.cpp",
                    L"WsmInstall",
                    v70,
                    v69,
                    0,
                    0);
                }
              }
              else
              {
                v65 = GetLastError();
                v66 = CurrentIP();
                v67 = ConstructPartialMsgW(
                        0x2000000u,
                        "WsmInstall: Failed to delete config key %s; hr = 0x%x",
                        (const char *)v44,
                        ServiceKeyName);
                WdsSetupLogMessageW(
                  v67,
                  0,
                  L"D",
                  0,
                  985,
                  L"base\\ntsetup\\setupplatform\\deployment\\monitor\\api\\winsetupmonapi.cpp",
                  L"WsmInstall",
                  v66,
                  v65,
                  0,
                  0);
              }
LABEL_92:
              Expand = P;
              v19 = v155[0];
              goto LABEL_120;
            }
            v60 = GetLastError();
            v61 = CurrentIP();
            v62 = ConstructPartialMsgW(
                    0x2000000u,
                    "WsmInstall: Failed to restore service registry hive %s; hr = 0x%x",
                    (const char *)a3,
                    ServiceKeyName);
            WdsSetupLogMessageW(
              v62,
              0,
              L"D",
              0,
              932,
              L"base\\ntsetup\\setupplatform\\deployment\\monitor\\api\\winsetupmonapi.cpp",
              L"WsmInstall",
              v61,
              v60,
              0,
              0);
            v139 = v138;
          }
          else
          {
            v56 = GetLastError();
            v57 = CurrentIP();
            v58 = ConstructPartialMsgW(
                    0x2000000u,
                    "WsmInstall: Failed to create service key %s; hr = 0x%x",
                    (const char *)v49,
                    ServiceKeyName);
            WdsSetupLogMessageW(
              v58,
              0,
              L"D",
              0,
              922,
              L"base\\ntsetup\\setupplatform\\deployment\\monitor\\api\\winsetupmonapi.cpp",
              L"WsmInstall",
              v57,
              v56,
              0,
              0);
          }
        }
        else
        {
          v51 = GetLastError();
          v52 = CurrentIP();
          v53 = ConstructPartialMsgW(
                  0x2000000u,
                  "WsmInstall: Failed to delete service key %s; hr = 0x%x",
                  (const char *)v49,
                  ServiceKeyName);
          WdsSetupLogMessageW(
            v53,
            0,
            L"D",
            0,
            906,
            L"base\\ntsetup\\setupplatform\\deployment\\monitor\\api\\winsetupmonapi.cpp",
            L"WsmInstall",
            v52,
            v51,
            0,
            0);
        }
        v44 = (WCHAR *)v135;
        v18 = v154;
        goto LABEL_92;
      }
    }
    else
    {
      ServiceKeyName = -2147467259;
    }
    v45 = GetLastError();
    v46 = CurrentIP();
    v47 = ConstructPartialMsgW(
            0x2000000u,
            "WsmInstall: Failed to build driver file destination path; hr = 0x%x",
            ServiceKeyName);
    WdsSetupLogMessageW(
      v47,
      0,
      L"D",
      0,
      863,
      L"base\\ntsetup\\setupplatform\\deployment\\monitor\\api\\winsetupmonapi.cpp",
      L"WsmInstall",
      v46,
      v45,
      0,
      0);
    v18 = 0;
    v19 = 0;
    Expand = P;
    goto LABEL_118;
  }
  v31 = GetLastError();
  v32 = v31 < 0;
  if ( v31 > 0 )
    v32 = 1;
  if ( v32 )
  {
    v33 = GetLastError();
    ServiceKeyName = v33;
    if ( v33 > 0 )
      ServiceKeyName = (unsigned __int16)v33 | 0x80070000;
  }
  else
  {
    ServiceKeyName = -2147467259;
  }
  v34 = GetLastError();
  v35 = CurrentIP();
  v36 = ConstructPartialMsgW(
          0x2000000u,
          "WsmInstall: Failed to build drivers directory path; hr = 0x%x",
          ServiceKeyName);
  WdsSetupLogMessageW(
    v36,
    0,
    L"D",
    0,
    856,
    L"base\\ntsetup\\setupplatform\\deployment\\monitor\\api\\winsetupmonapi.cpp",
    L"WsmInstall",
    v35,
    v34,
    0,
    0);
  v11 = (char *)lpMem;
LABEL_47:
  v44 = (WCHAR *)v135;
  if ( ServiceKeyName < 0 )
  {
    v18 = 0;
    v19 = 0;
    Expand = P;
LABEL_119:
    v49 = lpSubKey;
LABEL_120:
    if ( a1 && !v19 )
    {
LABEL_138:
      v119 = (char *)lpMem;
      goto LABEL_139;
    }
    v108 = v134;
    v154 = v18;
    lpMem = v11;
    P = (wchar_t *)Expand;
    if ( v44 )
    {
      v109 = RegDeleteTreeW(HKEY_LOCAL_MACHINE, v44);
      if ( v109 > 0 )
        v109 = (unsigned __int16)v109 | 0x80070000;
      v110 = 0;
      if ( v109 != -2147024894 )
        v110 = v109;
      if ( v110 >= 0 )
      {
        v11 = (char *)lpMem;
      }
      else
      {
        v111 = GetLastError();
        v112 = CurrentIP();
        v113 = ConstructPartialMsgW(
                 0x2000000u,
                 "WsmInstall: Failed to clean up config key %s; hr = 0x%x",
                 (const char *)v44,
                 v110);
        WdsSetupLogMessageW(
          v113,
          0,
          L"D",
          0,
          1123,
          L"base\\ntsetup\\setupplatform\\deployment\\monitor\\api\\winsetupmonapi.cpp",
          L"WsmInstall",
          v112,
          v111,
          0,
          0);
        Expand = P;
        v11 = (char *)lpMem;
        v108 = v134;
      }
    }
    if ( v49 )
    {
      v114 = RegDeleteTreeW(HKEY_LOCAL_MACHINE, v49);
      if ( v114 > 0 )
        v114 = (unsigned __int16)v114 | 0x80070000;
      v115 = 0;
      if ( v114 != -2147024894 )
        v115 = v114;
      if ( v115 >= 0 )
      {
        P = (wchar_t *)Expand;
        v134 = v108;
        v154 = v18;
      }
      else
      {
        v116 = GetLastError();
        v117 = CurrentIP();
        v118 = ConstructPartialMsgW(
                 0x2000000u,
                 "WsmInstall: Failed to clean up service key %s; hr = 0x%x",
                 (const char *)v49,
                 v115);
        WdsSetupLogMessageW(
          v118,
          0,
          L"D",
          0,
          1137,
          L"base\\ntsetup\\setupplatform\\deployment\\monitor\\api\\winsetupmonapi.cpp",
          L"WsmInstall",
          v117,
          v116,
          0,
          0);
      }
      goto LABEL_138;
    }
    P = (wchar_t *)Expand;
    v134 = v108;
    v154 = v18;
LABEL_172:
    v119 = v11;
LABEL_139:
    if ( v119 && !(unsigned int)DeleteFileEx2(v119, 64) )
    {
      v120 = GetLastError();
      if ( v120 > 0 )
        v120 = (unsigned __int16)v120 | 0x80070000;
      v121 = 0;
      if ( v120 != -2147024894 )
        v121 = v120;
      if ( v121 < 0 )
      {
        v122 = GetLastError();
        v123 = CurrentIP();
        v124 = ConstructPartialMsgW(0x2000000u, "WsmInstall: Failed to clean up driver file %s; hr = 0x%x", v119, v121);
        WdsSetupLogMessageW(
          v124,
          0,
          L"D",
          0,
          1154,
          L"base\\ntsetup\\setupplatform\\deployment\\monitor\\api\\winsetupmonapi.cpp",
          L"WsmInstall",
          v123,
          v122,
          0,
          0);
      }
    }
    v18 = v154;
    v44 = (WCHAR *)v135;
    goto LABEL_148;
  }
  v119 = (char *)lpMem;
  v18 = 0;
LABEL_148:
  if ( phkResult )
    RegCloseKey(phkResult);
  if ( v18 == 1 && !(_DWORD)v139 )
    EnablePrivilegeEx(L"SeRestorePrivilege");
  if ( v134 == 1 && !HIDWORD(v139) )
    EnablePrivilegeEx(L"SeBackupPrivilege");
  if ( v44 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v44);
  }
  if ( v144 )
    (*(void (__fastcall **)(struct IWsmTrackingConfig *))(*(_QWORD *)v144 + 8LL))(v144);
  if ( v145 )
    (*(void (__fastcall **)(struct IWsmLogConfig *))(*(_QWORD *)v145 + 8LL))(v145);
  if ( hKey )
    RegCloseKey(hKey);
  v126 = (WCHAR *)lpSubKey;
  if ( lpSubKey )
  {
    v127 = GetProcessHeap();
    HeapFree(v127, 0, v126);
  }
  if ( v119 )
  {
    v128 = GetProcessHeap();
    HeapFree(v128, 0, v119);
  }
  if ( P )
  {
    v129 = GetProcessHeap();
    HeapFree(v129, 0, P);
  }
  CSystemHive::Unload((CSystemHive *)&v147);
  return (unsigned int)ServiceKeyName;
}

```

## disassembly

```asm
0x1803f7060  mov     [rsp-8+arg_10], rbx
0x1803f7065  mov     [rsp-8+pszSrc], rcx
0x1803f706a  push    rbp
0x1803f706b  push    rsi
0x1803f706c  push    rdi
0x1803f706d  push    r12
0x1803f706f  push    r13
0x1803f7071  push    r14
0x1803f7073  push    r15
0x1803f7075  lea     rbp, [rsp-0Fh]
0x1803f707a  sub     rsp, 100h
0x1803f7081  xor     esi, esi
0x1803f7083  xorps   xmm0, xmm0
0x1803f7086  mov     [rbp+3Fh+var_4F], esi
0x1803f7089  mov     eax, esi
0x1803f708b  mov     dword ptr [rbp+3Fh+var_A0+4], eax
0x1803f708e  xorps   xmm1, xmm1
0x1803f7091  mov     dword ptr [rbp+3Fh+var_A8+4], eax
0x1803f7094  mov     r12d, r9d
0x1803f7097  mov     dword ptr [rbp+3Fh+var_A0], eax
0x1803f709a  mov     r13, r8
0x1803f709d  mov     dword ptr [rbp+3Fh+var_A8], eax
0x1803f70a0  mov     r15, rdx
0x1803f70a3  mov     [rbp+3Fh+var_4B], si
0x1803f70a7  mov     rbx, rcx
0x1803f70aa  mov     [rbp+3Fh+var_49], sil
0x1803f70ae  mov     [rbp+3Fh+var_50], sil
0x1803f70b2  mov     [rbp+3Fh+var_68], rsi
0x1803f70b6  mov     [rbp+3Fh+lpSubKey], rsi
0x1803f70ba  mov     [rbp+3Fh+hKey], rsi
0x1803f70be  mov     [rbp+3Fh+var_70], rsi
0x1803f70c2  mov     [rbp+3Fh+var_78], rsi
0x1803f70c6  mov     [rsp+130h+var_C0], rsi
0x1803f70cb  mov     [rbp+3Fh+var_98], rsi
0x1803f70cf  movups  [rbp+3Fh+var_60], xmm0
0x1803f70d3  movdqu  [rbp+3Fh+var_48], xmm1
0x1803f70d8  test    rdx, rdx
0x1803f70db  jz      loc_1803F8283
0x1803f70e1  test    r8, r8
0x1803f70e4  jz      loc_1803F8283
0x1803f70ea  test    rcx, rcx
0x1803f70ed  jz      short loc_1803F70F8
0x1803f70ef  test    r9d, r9d
0x1803f70f2  jnz     loc_1803F8283
0x1803f70f8  mov     rax, [rbp+3Fh+arg_28]
0x1803f70fc  test    rax, rax
0x1803f70ff  jz      loc_1803F8283
0x1803f7105  cmp     [rax], rsi
0x1803f7108  jz      loc_1803F8283
0x1803f710e  mov     edx, 5Ch ; '\'; Ch
0x1803f7113  mov     [rsp+130h+P], rsi
0x1803f7118  mov     rcx, r15; Str
0x1803f711b  mov     [rbp+3Fh+lpMem], rsi
0x1803f711f  mov     r14, rsi
0x1803f7122  mov     [rbp+3Fh+arg_20], sil
0x1803f7126  mov     [rsp+130h+var_C8], esi
0x1803f712a  mov     [rbp+3Fh+arg_8], esi
0x1803f712d  call    cs:__imp_wcsrchr
0x1803f7133  test    rax, rax
0x1803f7136  jnz     loc_1803F71C0
0x1803f713c  mov     esi, 800700A1h
0x1803f7141  call    cs:__imp_GetLastError
0x1803f7147  mov     edi, eax
0x1803f7149  call    cs:__imp_CurrentIP
0x1803f714f  mov     r9d, esi
0x1803f7152  lea     rdx, aWsminstallBadD; "WsmInstall: Bad driver file path %s; hr"...
0x1803f7159  mov     r8, r15
0x1803f715c  mov     ecx, 2000000h; unsigned int
0x1803f7161  mov     rbx, rax
0x1803f7164  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x1803f7169  xor     ecx, ecx
0x1803f716b  lea     r8, aD_0; "D"
0x1803f7172  mov     [rsp+130h+var_E0], ecx
0x1803f7176  xor     r9d, r9d
0x1803f7179  mov     [rsp+130h+var_E8], rcx
0x1803f717e  xor     edx, edx
0x1803f7180  mov     dword ptr [rsp+130h+lpdwDisposition], edi
0x1803f7184  lea     rcx, aWsminstall; "WsmInstall"
0x1803f718b  mov     [rsp+130h+phkResult], rbx
0x1803f7190  mov     [rsp+130h+lpSecurityAttributes], rcx
0x1803f7195  lea     rcx, aBaseNtsetupSet_11; "base\\ntsetup\\setupplatform\\deploymen"...
0x1803f719c  mov     [rsp+130h+pcchRemaining], rcx
0x1803f71a1  mov     rcx, rax
0x1803f71a4  mov     dword ptr [rsp+130h+ppszDestEnd], 341h
0x1803f71ac  call    cs:__imp_WdsSetupLogMessageW
0x1803f71b2  mov     rdi, r14
0x1803f71b5  mov     r13d, r14d
0x1803f71b8  mov     bl, r14b
0x1803f71bb  jmp     loc_1803F7EE6
0x1803f71c0  lea     r14, [rax+2]
0x1803f71c4  mov     rcx, r14; String1
0x1803f71c7  lea     rdx, aWinsetupmonSys; "WinSetupMon.sys"
0x1803f71ce  call    cs:__imp__wcsicmp
0x1803f71d4  test    eax, eax
0x1803f71d6  jz      loc_1803F7265
0x1803f71dc  mov     esi, 80070057h
0x1803f71e1  call    cs:__imp_GetLastError
0x1803f71e7  mov     edi, eax
0x1803f71e9  call    cs:__imp_CurrentIP
0x1803f71ef  mov     r9d, esi
0x1803f71f2  lea     rdx, aWsminstallInco; "WsmInstall: Incorrect driver file name "...
0x1803f71f9  mov     r8, r14
0x1803f71fc  mov     ecx, 2000000h; unsigned int
0x1803f7201  mov     rbx, rax
0x1803f7204  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x1803f7209  xor     ecx, ecx
0x1803f720b  lea     r8, aD_0; "D"
0x1803f7212  mov     [rsp+130h+var_E0], ecx
0x1803f7216  xor     r9d, r9d
0x1803f7219  mov     [rsp+130h+var_E8], rcx
0x1803f721e  xor     edx, edx
0x1803f7220  mov     dword ptr [rsp+130h+lpdwDisposition], edi
0x1803f7224  lea     rcx, aWsminstall; "WsmInstall"
0x1803f722b  mov     [rsp+130h+phkResult], rbx
0x1803f7230  mov     [rsp+130h+lpSecurityAttributes], rcx
0x1803f7235  lea     rcx, aBaseNtsetupSet_11; "base\\ntsetup\\setupplatform\\deploymen"...
0x1803f723c  mov     [rsp+130h+pcchRemaining], rcx
0x1803f7241  mov     rcx, rax
0x1803f7244  mov     dword ptr [rsp+130h+ppszDestEnd], 349h
0x1803f724c  call    cs:__imp_WdsSetupLogMessageW
0x1803f7252  mov     rdi, [rsp+130h+P]
0x1803f7257  mov     r14, rdi
0x1803f725a  mov     r13d, edi
0x1803f725d  mov     bl, dil
0x1803f7260  jmp     loc_1803F7EE6
0x1803f7265  test    rbx, rbx
0x1803f7268  jz      loc_1803F73AF
0x1803f726e  mov     rdx, [rbp+3Fh+pszSrc]
0x1803f7272  mov     edi, esi
0x1803f7274  mov     [rbp+3Fh+pszDest], rsi
0x1803f7278  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1803f727c  mov     [rbp+3Fh+cchDest], rsi
0x1803f7280  inc     rbx
0x1803f7283  cmp     [rdx+rbx*2], si
0x1803f7287  jnz     short loc_1803F7280
0x1803f7289  test    ebx, ebx
0x1803f728b  jz      short loc_1803F72A1
0x1803f728d  mov     eax, 5Ch ; '\'
0x1803f7292  lea     ecx, [rbx-1]
0x1803f7295  cmp     ax, [rdx+rcx*2]
0x1803f7299  mov     eax, 1
0x1803f729e  cmovnz  edi, eax
0x1803f72a1  mov     rcx, gs:60h
0x1803f72aa  lea     eax, [rdi+11h]
0x1803f72ad  add     eax, ebx
0x1803f72af  mov     edx, 8; Flags
0x1803f72b4  mov     esi, eax
0x1803f72b6  mov     rcx, [rcx+30h]; HeapHandle
0x1803f72ba  lea     r8, [rax+rax]; Size
0x1803f72be  call    cs:__imp_RtlAllocateHeap
0x1803f72c4  mov     [rsp+130h+P], rax
0x1803f72c9  test    rax, rax
0x1803f72cc  jnz     short loc_1803F72E5
0x1803f72ce  mov     rax, gs:30h
0x1803f72d7  xor     esi, esi
0x1803f72d9  mov     dword ptr [rax+68h], 8
0x1803f72e0  jmp     loc_1803F73A1
0x1803f72e5  mov     r8, [rbp+3Fh+pszSrc]; pszSrc
0x1803f72e9  lea     rcx, [rbp+3Fh+cchDest]
0x1803f72ed  mov     [rsp+130h+pcchRemaining], rcx; pcchRemaining
0x1803f72f2  mov     rdx, rsi; cchDest
0x1803f72f5  lea     rcx, [rbp+3Fh+pszDest]
0x1803f72f9  mov     r9d, ebx; cchToCopy
0x1803f72fc  mov     [rsp+130h+ppszDestEnd], rcx; ppszDestEnd
0x1803f7301  mov     rcx, rax; pszDest
0x1803f7304  call    StringCchCopyNExW
0x1803f7309  xor     esi, esi
0x1803f730b  mov     ebx, eax
0x1803f730d  test    eax, eax
0x1803f730f  js      short loc_1803F7378
0x1803f7311  test    edi, edi
0x1803f7313  jz      short loc_1803F7345
0x1803f7315  mov     rdx, [rbp+3Fh+cchDest]; cchDest
0x1803f7319  lea     rax, [rbp+3Fh+cchDest]
0x1803f731d  mov     rcx, [rbp+3Fh+pszDest]; pszDest
0x1803f7321  lea     r9d, [rsi+1]; cchToCopy
0x1803f7325  mov     [rsp+130h+pcchRemaining], rax; pcchRemaining
0x1803f732a  lea     r8, pszSrc; "\\"
0x1803f7331  lea     rax, [rbp+3Fh+pszDest]
0x1803f7335  mov     [rsp+130h+ppszDestEnd], rax; ppszDestEnd
0x1803f733a  call    StringCchCopyNExW
0x1803f733f  mov     ebx, eax
0x1803f7341  test    eax, eax
0x1803f7343  js      short loc_1803F7378
0x1803f7345  mov     rdx, [rbp+3Fh+cchDest]; cchDest
0x1803f7349  lea     r8, aSystem32Driver; "System32\\drivers"
0x1803f7350  mov     rcx, [rbp+3Fh+pszDest]; pszDest
0x1803f7354  mov     r9d, 10h; cchToCopy
0x1803f735a  call    StringCchCopyNW
0x1803f735f  mov     ebx, eax
0x1803f7361  test    eax, eax
0x1803f7363  js      short loc_1803F7378
0x1803f7365  mov     rax, gs:30h
0x1803f736e  mov     rdi, [rsp+130h+P]
0x1803f7373  mov     [rax+68h], esi
0x1803f7376  jmp     short loc_1803F73A9
0x1803f7378  mov     rcx, gs:60h
0x1803f7381  xor     edx, edx; Flags
0x1803f7383  mov     r8, [rsp+130h+P]; P
0x1803f7388  mov     rcx, [rcx+30h]; HeapHandle
0x1803f738c  call    cs:__imp_RtlFreeHeap
0x1803f7392  mov     rax, gs:30h
0x1803f739b  movzx   ecx, bx
0x1803f739e  mov     [rax+68h], ecx
0x1803f73a1  mov     [rsp+130h+P], rsi
0x1803f73a6  mov     rdi, rsi
0x1803f73a9  mov     rbx, [rbp+3Fh+pszSrc]
0x1803f73ad  jmp     short loc_1803F73C3
0x1803f73af  lea     rcx, aWindirSystem32_0; "%WINDIR%\\System32\\drivers"
0x1803f73b6  call    AllocateExpand
0x1803f73bb  mov     rdi, rax
0x1803f73be  mov     [rsp+130h+P], rax
0x1803f73c3  test    rdi, rdi
0x1803f73c6  jnz     loc_1803F7475
0x1803f73cc  call    cs:__imp_GetLastError
0x1803f73d2  test    eax, eax
0x1803f73d4  jle     short loc_1803F73E0
0x1803f73d6  movzx   eax, ax
0x1803f73d9  or      eax, 80070000h
0x1803f73de  test    eax, eax
0x1803f73e0  jns     short loc_1803F73F9
0x1803f73e2  call    cs:__imp_GetLastError
0x1803f73e8  mov     esi, eax
0x1803f73ea  test    eax, eax
0x1803f73ec  jle     short loc_1803F73FE
0x1803f73ee  movzx   esi, ax
0x1803f73f1  or      esi, 80070000h
0x1803f73f7  jmp     short loc_1803F73FE
0x1803f73f9  mov     esi, 80004005h
0x1803f73fe  call    cs:__imp_GetLastError
0x1803f7404  mov     edi, eax
0x1803f7406  call    cs:__imp_CurrentIP
0x1803f740c  mov     r8d, esi
0x1803f740f  lea     rdx, aWsminstallFail_2; "WsmInstall: Failed to build drivers dir"...
0x1803f7416  mov     ecx, 2000000h; unsigned int
0x1803f741b  mov     rbx, rax
0x1803f741e  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x1803f7423  xor     ecx, ecx
0x1803f7425  lea     r8, aD_0; "D"
0x1803f742c  mov     [rsp+130h+var_E0], ecx
0x1803f7430  xor     r9d, r9d
0x1803f7433  mov     [rsp+130h+var_E8], rcx
0x1803f7438  xor     edx, edx
0x1803f743a  mov     dword ptr [rsp+130h+lpdwDisposition], edi
0x1803f743e  lea     rcx, aWsminstall; "WsmInstall"
0x1803f7445  mov     [rsp+130h+phkResult], rbx
0x1803f744a  mov     [rsp+130h+lpSecurityAttributes], rcx
0x1803f744f  lea     rcx, aBaseNtsetupSet_11; "base\\ntsetup\\setupplatform\\deploymen"...
0x1803f7456  mov     [rsp+130h+pcchRemaining], rcx
0x1803f745b  mov     rcx, rax
0x1803f745e  mov     dword ptr [rsp+130h+ppszDestEnd], 358h
0x1803f7466  call    cs:__imp_WdsSetupLogMessageW
0x1803f746c  mov     r14, [rbp+3Fh+lpMem]
0x1803f7470  jmp     loc_1803F7574
0x1803f7475  mov     rdx, r14; STRSAFE_PCNZWCH
0x1803f7478  mov     rcx, rdi; pszSrc
0x1803f747b  call    BuildPath
0x1803f7480  mov     [rbp+3Fh+lpMem], rax
0x1803f7484  mov     r14, rax
0x1803f7487  test    rax, rax
0x1803f748a  jnz     short loc_1803F74C5
0x1803f748c  call    cs:__imp_GetLastError
0x1803f7492  test    eax, eax
0x1803f7494  jle     short loc_1803F74A0
0x1803f7496  movzx   eax, ax
0x1803f7499  or      eax, 80070000h
0x1803f749e  test    eax, eax
0x1803f74a0  jns     loc_1803F7594
0x1803f74a6  call    cs:__imp_GetLastError
0x1803f74ac  mov     esi, eax
0x1803f74ae  test    eax, eax
0x1803f74b0  jle     short loc_1803F74BD
0x1803f74b2  movzx   esi, si
0x1803f74b5  or      esi, 80070000h
0x1803f74bb  test    esi, esi
0x1803f74bd  js      loc_1803F7599
0x1803f74c3  xor     esi, esi
0x1803f74c5  mov     dword ptr [rsp+130h+pcchRemaining], esi; dwCopyFlags
0x1803f74c9  xor     r9d, r9d; lpData
0x1803f74cc  xor     r8d, r8d; lpProgressRoutine
0x1803f74cf  mov     [rsp+130h+ppszDestEnd], rsi; pbCancel
0x1803f74d4  mov     rdx, r14; lpNewFileName
0x1803f74d7  mov     rcx, r15; lpExistingFileName
0x1803f74da  call    cs:__imp_CopyFileExW
0x1803f74e0  test    eax, eax
0x1803f74e2  jnz     loc_1803F7618
0x1803f74e8  call    cs:__imp_GetLastError
0x1803f74ee  xor     r12d, r12d
0x1803f74f1  mov     esi, eax
0x1803f74f3  test    eax, eax
0x1803f74f5  jle     short loc_1803F7500
0x1803f74f7  movzx   esi, ax
0x1803f74fa  or      esi, 80070000h
0x1803f7500  call    cs:__imp_GetLastError
0x1803f7506  mov     edi, eax
0x1803f7508  call    cs:__imp_CurrentIP
0x1803f750e  mov     r9, r14
0x1803f7511  mov     dword ptr [rsp+130h+ppszDestEnd], esi
0x1803f7515  mov     r8, r15
0x1803f7518  lea     rdx, aWsminstallFail_6; "WsmInstall: Failed to copy driver file "...
  ... truncated ...
```
