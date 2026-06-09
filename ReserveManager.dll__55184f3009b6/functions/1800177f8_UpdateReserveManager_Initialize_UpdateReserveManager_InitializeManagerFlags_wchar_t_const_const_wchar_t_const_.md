# UpdateReserveManager::Initialize(UpdateReserveManager::InitializeManagerFlags,wchar_t const * const,wchar_t const * const,char const * const)

- ea: `0x1800177f8`
- end: `0x1800191e6`
- name: `?Initialize@UpdateReserveManager@@QEAAJW4InitializeManagerFlags@1@QEB_W1QEBD@Z`
- size: `6638`
- prototype: `__int64 __fastcall(__int64, unsigned int, WCHAR *, wchar_t *, char *)`
- caller_count: `3`
- callee_count: `29`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180007d08`
- `0x18000c8c0`
- `0x18000c9c0`

## callees

- `0x180003870`
- `0x1800042f4`
- `0x18000555c`
- `0x1800055ac`
- `0x180008140`
- `0x18000f82c`
- `0x18000fae4`
- `0x18000fafc`
- `0x180010794`
- `0x180010ea4`
- `0x180010fe0`
- `0x180011890`
- `0x180011f38`
- `0x180013e84`
- `0x180015b34`
- `0x180016cac`
- `0x1800177f8`
- `0x18001a5b4`
- `0x18001a8f0`
- `0x18001c520`
- `0x18001e068`
- `0x18001effc`
- `0x18001fd60`
- `0x180020158`
- `0x1800203c8`
- `0x180023c40`
- `0x1800243e0`
- `0x1800248e0`
- `0x180033010`

## import_xrefs

- `ntdll!NtClose` at `0x180018935`
- `ntdll!NtClose` at `0x1800189bc`
- `ntdll!NtClose` at `0x180018a5c`
- `ntdll!NtClose` at `0x180018af4`
- `ntdll!NtClose` at `0x180018f2c`
- `ntdll!NtClose` at `0x180019153`
- `ntdll!NtClose` at `0x180018935`
- `ntdll!NtClose` at `0x1800189bc`
- `ntdll!NtClose` at `0x180018a5c`
- `ntdll!NtClose` at `0x180018af4`
- `ntdll!NtClose` at `0x180018f2c`
- `ntdll!NtClose` at `0x180019153`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180018caf`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180018d00`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180018d70`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180018dd0`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180018e1e`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180018ee2`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180018f83`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001902d`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180018caf`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180018d00`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180018d70`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180018dd0`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180018e1e`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180018ee2`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180018f83`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001902d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001796e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001797f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018b46`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018b5c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019056`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019067`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800190e8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019168`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001796e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001797f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018b46`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018b5c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019056`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019067`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800190e8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019168`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180017a65`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180017aef`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180017b75`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180017f87`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800183ba`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180018720`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800188fd`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180018a1a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180017a65`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180017aef`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180017b75`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180017f87`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800183ba`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180018720`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800188fd`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180018a1a`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800184ce`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800184ce`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x180017964`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x180017964`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x180018b32`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x180018b32`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800188b3`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180018c0a`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800188b3`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180018c0a`

## string_xrefs

- `0x1800178fd`: `onecore\base\servicing\updatereservemanager\lib\updatereservemanager.cpp`
- `0x18001798f`: `onecore\base\servicing\updatereservemanager\lib\updatereservemanager.cpp`
- `0x1800179ec`: `onecore\base\servicing\updatereservemanager\lib\updatereservemanager.cpp`
- `0x180017a73`: `onecore\base\servicing\updatereservemanager\lib\updatereservemanager.cpp`
- `0x180017afd`: `onecore\base\servicing\updatereservemanager\lib\updatereservemanager.cpp`
- `0x180017b83`: `onecore\base\servicing\updatereservemanager\lib\updatereservemanager.cpp`
- `0x180017f99`: `onecore\base\servicing\updatereservemanager\lib\updatereservemanager.cpp`
- `0x1800183ca`: `onecore\base\servicing\updatereservemanager\lib\updatereservemanager.cpp`
- `0x1800184de`: `onecore\base\servicing\updatereservemanager\lib\updatereservemanager.cpp`
- `0x180018730`: `onecore\base\servicing\updatereservemanager\lib\updatereservemanager.cpp`
- `0x180018954`: `onecore\base\servicing\updatereservemanager\lib\updatereservemanager.cpp`
- `0x180018a7e`: `onecore\base\servicing\updatereservemanager\lib\updatereservemanager.cpp`
- `0x180018b79`: `onecore\base\servicing\updatereservemanager\lib\updatereservemanager.cpp`
- `0x180019077`: `onecore\base\servicing\updatereservemanager\lib\updatereservemanager.cpp`
- `0x1800190f7`: `onecore\base\servicing\updatereservemanager\lib\updatereservemanager.cpp`
- `0x180017909`: `UpdateReserveManager::Initialize`
- `0x18001799b`: `UpdateReserveManager::Initialize`
- `0x1800179f8`: `UpdateReserveManager::Initialize`
- `0x180017a7f`: `UpdateReserveManager::Initialize`
- `0x180017b09`: `UpdateReserveManager::Initialize`
- `0x180017b8f`: `UpdateReserveManager::Initialize`
- `0x180017fa5`: `UpdateReserveManager::Initialize`
- `0x1800183d6`: `UpdateReserveManager::Initialize`
- `0x1800184ea`: `UpdateReserveManager::Initialize`
- `0x18001873c`: `UpdateReserveManager::Initialize`
- `0x180018960`: `UpdateReserveManager::Initialize`
- `0x180018a8a`: `UpdateReserveManager::Initialize`
- `0x180018b85`: `UpdateReserveManager::Initialize`
- `0x180019083`: `UpdateReserveManager::Initialize`
- `0x180019103`: `UpdateReserveManager::Initialize`
- `0x180017a94`: `::RegOpenKeyExW((( HKEY ) (ULONG_PTR)((LONG)0x80000002) ), L"SOFTWARE", 0, ((((0x00020000L)) | (0x0001) | (0x0008) | (0x0010)) & (~(0x00100000L))) | ((((0x00020000L)) | (0x0002) | (0x0004)) & (~(0x00100000L))) | (0x0100), &m_SoftwareKey)`
- `0x180017b1e`: `::RegOpenKeyExW((( HKEY ) (ULONG_PTR)((LONG)0x80000002) ), L"SYSTEM", 0, ((((0x00020000L)) | (0x0001) | (0x0008) | (0x0010)) & (~(0x00100000L))) | ((((0x00020000L)) | (0x0002) | (0x0004)) & (~(0x00100000L))) | (0x0100), &m_SystemKey)`
- `0x180017ba4`: `::RegOpenKeyExW(m_SystemKey, L"CurrentControlSet", 0, ((((0x00020000L)) | (0x0001) | (0x0008) | (0x0010)) & (~(0x00100000L))) | ((((0x00020000L)) | (0x0002) | (0x0004)) & (~(0x00100000L))) | (0x0100), &m_CurrentControlSetKey)`
- `0x180017c98`: `\System32\Config\SOFTWARE`
- `0x180017fba`: `::RegOpenKeyExW((( HKEY ) (ULONG_PTR)((LONG)0x80000002) ), Key.Buffer, 0, ((((0x00020000L)) | (0x0001) | (0x0008) | (0x0010)) & (~(0x00100000L))) | ((((0x00020000L)) | (0x0002) | (0x0004)) & (~(0x00100000L))) | (0x0100), &m_SoftwareKey)`
- `0x180018074`: `\System32\Config\SYSTEM`
- `0x1800183eb`: `::RegOpenKeyExW((( HKEY ) (ULONG_PTR)((LONG)0x80000002) ), Key.Buffer, 0, ((((0x00020000L)) | (0x0001) | (0x0008) | (0x0010)) & (~(0x00100000L))) | ((((0x00020000L)) | (0x0002) | (0x0004)) & (~(0x00100000L))) | (0x0100), &m_SystemKey)`
- `0x180018751`: `::RegOpenKeyExW(m_SystemKey, ControlSetName.Buffer, 0, ((((0x00020000L)) | (0x0001) | (0x0008) | (0x0010)) & (~(0x00100000L))) | ((((0x00020000L)) | (0x0002) | (0x0004)) & (~(0x00100000L))) | (0x0100), &m_CurrentControlSetKey)`
- `0x180019098`: `m_VolumePathHandle.IsValid()`

## pseudocode

```c
__int64 __fastcall UpdateReserveManager::Initialize(__int64 a1, unsigned int a2, WCHAR *a3, wchar_t *a4, char *a5)
{
  __int64 v8; // rcx
  char *v9; // rsi
  char *v10; // rax
  __int64 v11; // r9
  __int64 v12; // rcx
  __int64 v13; // rdx
  char *v14; // r8
  char v15; // r10
  unsigned int v16; // r14d
  __int64 result; // rax
  char *v18; // rcx
  const WCHAR *v19; // r12
  WCHAR *v20; // rcx
  UINT SystemWindowsDirectoryW; // eax
  unsigned int LastError; // edi
  int v23; // ebx
  unsigned int v24; // r13d
  __int64 v25; // r8
  WCHAR v26; // ax
  WCHAR *v27; // rdx
  __int64 v28; // rsi
  __int64 v29; // rax
  __int64 v30; // rcx
  __m128i v31; // rax
  NTSTATUS v32; // eax
  __int64 v33; // rcx
  unsigned int v34; // ebx
  __int64 v35; // r8
  NTSTATUS v36; // eax
  unsigned int v37; // ebx
  NTSTATUS v38; // eax
  unsigned int v39; // edx
  unsigned int *v40; // r9
  unsigned int v41; // ebx
  NTSTATUS v42; // eax
  unsigned int v43; // ebx
  NTSTATUS v44; // eax
  __int64 v45; // rcx
  unsigned int v46; // ebx
  __int64 v47; // xmm6_8
  NTSTATUS v48; // eax
  unsigned int v49; // ebx
  int v50; // ebx
  __int64 v51; // r9
  __int64 v52; // rcx
  __int64 v53; // rsi
  __int64 v54; // rax
  NTSTATUS v55; // eax
  unsigned int v56; // edx
  __int64 v57; // rcx
  unsigned int *v58; // r9
  unsigned int v59; // ebx
  __int64 v60; // r8
  NTSTATUS v61; // eax
  unsigned int v62; // ebx
  NTSTATUS v63; // eax
  unsigned int v64; // ebx
  NTSTATUS v65; // eax
  __int64 v66; // rcx
  unsigned int v67; // ebx
  __int64 v68; // xmm7_8
  NTSTATUS v69; // eax
  unsigned int v70; // ebx
  HKEY *v71; // r12
  int v72; // ebx
  __int64 v73; // rcx
  int ValueW; // ebx
  NTSTATUS v75; // eax
  unsigned int v76; // ebx
  const WCHAR *v77; // rsi
  int v78; // ebx
  int v79; // ebx
  char *FileW; // rbx
  int v81; // esi
  unsigned int v82; // r15d
  int v83; // esi
  signed int v84; // eax
  bool v85; // sf
  signed int v86; // eax
  char *v87; // rax
  unsigned int v88; // edx
  int PassedPolicyValue; // ebx
  unsigned int v90; // ebx
  int v91; // esi
  char *v92; // rcx
  unsigned int v93; // edi
  DWORD v94; // edi
  PHKEY phkResult; // [rsp+20h] [rbp-288h]
  const wchar_t *phkResulta; // [rsp+20h] [rbp-288h]
  __m128i v97; // [rsp+40h] [rbp-268h] BYREF
  __int64 v98; // [rsp+50h] [rbp-258h]
  const char *v99; // [rsp+58h] [rbp-250h]
  __int64 v100; // [rsp+60h] [rbp-248h]
  const wchar_t *v101; // [rsp+68h] [rbp-240h]
  __int128 v102; // [rsp+70h] [rbp-238h] BYREF
  wchar_t *v103; // [rsp+80h] [rbp-228h]
  char *v104; // [rsp+88h] [rbp-220h] BYREF
  unsigned int v105; // [rsp+90h] [rbp-218h] BYREF
  __int128 v106; // [rsp+98h] [rbp-210h] BYREF
  wchar_t *v107; // [rsp+A8h] [rbp-200h]
  unsigned __int64 v108[2]; // [rsp+B0h] [rbp-1F8h] BYREF
  LPCWSTR lpSubKey; // [rsp+C0h] [rbp-1E8h]
  _QWORD v110[2]; // [rsp+C8h] [rbp-1E0h] BYREF
  wchar_t *v111; // [rsp+D8h] [rbp-1D0h]
  __m128i v112; // [rsp+E0h] [rbp-1C8h] BYREF
  __int64 v113; // [rsp+F0h] [rbp-1B8h]
  __m128i v114; // [rsp+F8h] [rbp-1B0h] BYREF
  __int64 v115; // [rsp+108h] [rbp-1A0h]
  __int64 v116; // [rsp+110h] [rbp-198h]
  _BYTE v117[200]; // [rsp+120h] [rbp-188h] BYREF
  wchar_t *v118; // [rsp+1E8h] [rbp-C0h]
  HANDLE *v119; // [rsp+210h] [rbp-98h] BYREF
  char v120; // [rsp+218h] [rbp-90h]
  HKEY v121; // [rsp+220h] [rbp-88h] BYREF
  DWORD pcbData[2]; // [rsp+228h] [rbp-80h] BYREF
  int pvData; // [rsp+230h] [rbp-78h] BYREF
  _DWORD v124[2]; // [rsp+238h] [rbp-70h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2A8h] [rbp+0h]

  v116 = -2;
  v111 = a4;
  RtlRegisterErrorOriginationCallback();
  v9 = (char *)(v8 + 1200);
  v10 = a5;
  if ( !a5 )
  {
    TraceLoggingCorrelationVector::TraceLoggingCorrelationVector((TraceLoggingCorrelationVector *)v117);
    TraceLoggingCorrelationVector::ToString((TraceLoggingCorrelationVector *)v117, v9);
    v11 = 2147483646;
    v16 = -2147024774;
    goto LABEL_325;
  }
  v11 = 2147483646;
  v12 = 2147483646;
  v13 = 129;
  v14 = v9;
  do
  {
    if ( !v12 )
      break;
    v15 = *v10;
    if ( !*v10 )
      break;
    ++v10;
    *v14++ = v15;
    --v12;
    --v13;
  }
  while ( v13 );
  v16 = -2147024774;
  result = v13 == 0 ? 0x8007007A : 0;
  v18 = v14 - 1;
  if ( v13 )
    v18 = v14;
  *v18 = 0;
  if ( v13 )
  {
LABEL_325:
    try
    {
      v104 = 0;
      v105 = a2 & 2;
      if ( (a2 & 2) != 0 && (a2 & 1) != 0 )
      {
        v97.m128i_i64[0] = (__int64)"onecore\\base\\servicing\\updatereservemanager\\lib\\updatereservemanager.cpp";
        v97.m128i_i64[1] = (__int64)"UpdateReserveManager::Initialize";
        v98 = 79;
        v99 = "((HRESULT)0x80070057L)";
        RtlReportErrorOrigination(&v97, &GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627, 2147942487LL);
        return 2147942487LL;
      }
      v19 = (const WCHAR *)(a1 + 136);
      v20 = (WCHAR *)(a1 + 136);
      if ( !a3 )
      {
        SystemWindowsDirectoryW = GetSystemWindowsDirectoryW(v20, 0x104u);
        if ( !SystemWindowsDirectoryW )
        {
          if ( !GetLastError() )
          {
            LastError = 14077;
LABEL_19:
            v97.m128i_i64[0] = (__int64)"onecore\\base\\servicing\\updatereservemanager\\lib\\updatereservemanager.cpp";
            v97.m128i_i64[1] = (__int64)"UpdateReserveManager::Initialize";
            v98 = 88;
            v99 = "GetLastError";
            if ( (int)LastError > 0 )
              LastError = (unsigned __int16)LastError | 0x80070000;
            RtlReportErrorOrigination(&v97, &GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627, LastError);
            return LastError;
          }
          LastError = GetLastError();
          if ( LastError )
            goto LABEL_19;
LABEL_322:
          INTERNAL_ERROR_ACTION(-1073741595);
        }
        if ( SystemWindowsDirectoryW > 0x104 )
        {
          v97.m128i_i64[0] = (__int64)"onecore\\base\\servicing\\updatereservemanager\\lib\\updatereservemanager.cpp";
          v97.m128i_i64[1] = (__int64)"UpdateReserveManager::Initialize";
          v98 = 92;
          v99 = "static_cast<DWORD>(122L)";
          RtlReportErrorOrigination(&v97, &GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627, 2147942522LL);
          return 2147942522LL;
        }
        if ( *(_QWORD *)(a1 + 104) )
          goto LABEL_322;
        v23 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE", 0, 0x2011Fu, (PHKEY)(a1 + 104));
        if ( v23 )
        {
          v97.m128i_i64[0] = (__int64)"onecore\\base\\servicing\\updatereservemanager\\lib\\updatereservemanager.cpp";
          v97.m128i_i64[1] = (__int64)"UpdateReserveManager::Initialize";
          v98 = 99;
          v99 = "::RegOpenKeyExW((( HKEY ) (ULONG_PTR)((LONG)0x80000002) ), L\"SOFTWARE\", 0, ((((0x00020000L)) | (0x0001"
                ") | (0x0008) | (0x0010)) & (~(0x00100000L))) | ((((0x00020000L)) | (0x0002) | (0x0004)) & (~(0x00100000L"
                "))) | (0x0100), &m_SoftwareKey)";
          if ( v23 > 0 )
            v23 = (unsigned __int16)v23 | 0x80070000;
LABEL_36:
          RtlReportErrorOrigination(&v97, &GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627, (unsigned int)v23);
          return (unsigned int)v23;
        }
        if ( *(_QWORD *)(a1 + 112) )
          goto LABEL_322;
        v23 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SYSTEM", 0, 0x2011Fu, (PHKEY)(a1 + 112));
        if ( v23 )
        {
          v97.m128i_i64[0] = (__int64)"onecore\\base\\servicing\\updatereservemanager\\lib\\updatereservemanager.cpp";
          v97.m128i_i64[1] = (__int64)"UpdateReserveManager::Initialize";
          v98 = 105;
          v99 = "::RegOpenKeyExW((( HKEY ) (ULONG_PTR)((LONG)0x80000002) ), L\"SYSTEM\", 0, ((((0x00020000L)) | (0x0001) "
                "| (0x0008) | (0x0010)) & (~(0x00100000L))) | ((((0x00020000L)) | (0x0002) | (0x0004)) & (~(0x00100000L))"
                ") | (0x0100), &m_SystemKey)";
          if ( v23 > 0 )
            v23 = (unsigned __int16)v23 | 0x80070000;
          goto LABEL_36;
        }
        if ( *(_QWORD *)(a1 + 120) )
          goto LABEL_322;
        v23 = RegOpenKeyExW(*(HKEY *)(a1 + 112), L"CurrentControlSet", 0, 0x2011Fu, (PHKEY)(a1 + 120));
        if ( v23 )
        {
          v97.m128i_i64[0] = (__int64)"onecore\\base\\servicing\\updatereservemanager\\lib\\updatereservemanager.cpp";
          v97.m128i_i64[1] = (__int64)"UpdateReserveManager::Initialize";
          v98 = 111;
          v99 = "::RegOpenKeyExW(m_SystemKey, L\"CurrentControlSet\", 0, ((((0x00020000L)) | (0x0001) | (0x0008) | (0x001"
                "0)) & (~(0x00100000L))) | ((((0x00020000L)) | (0x0002) | (0x0004)) & (~(0x00100000L))) | (0x0100), &m_Cu"
                "rrentControlSetKey)";
          if ( v23 > 0 )
            v23 = (unsigned __int16)v23 | 0x80070000;
          goto LABEL_36;
        }
        *(_BYTE *)(a1 + 1176) = 0;
        v24 = v105;
LABEL_220:
        FileW = (char *)CreateFileW(v19, 0x80000000, 7u, 0, 3u, 0x2000000u, 0);
        v104 = FileW;
        if ( (unsigned __int64)(FileW - 1) > 0xFFFFFFFFFFFFFFFDuLL )
        {
          if ( GetLastError() )
          {
            v94 = GetLastError();
            if ( !v94 )
              goto LABEL_322;
          }
          else
          {
            v94 = 14077;
          }
          v97.m128i_i64[0] = (__int64)"onecore\\base\\servicing\\updatereservemanager\\lib\\updatereservemanager.cpp";
          v97.m128i_i64[1] = (__int64)"UpdateReserveManager::Initialize";
          v98 = 208;
          v99 = "WindowsDirHandle.IsValid()";
          if ( (int)v94 > 0 )
            v94 = (unsigned __int16)v94 | 0x80070000;
          RtlReportErrorOrigination(&v97, &GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627, v94);
          if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL && NtClose(FileW) < 0 )
            __fastfail(7u);
          return v94;
        }
        v121 = 0;
        v81 = RegOpenKeyExW(
                *(HKEY *)(a1 + 104),
                L"Microsoft\\Windows\\CurrentVersion\\ReserveManager",
                0,
                0x20119u,
                &v121);
        if ( v81 == 2 )
        {
          v82 = 8 * !(a2 & 1) - 2146498200;
          Windows::AutoGenericHandle<HKEY__ *,0,&void Windows::Detail::CloseWithRegCloseKey(HKEY__ *)>::~AutoGenericHandle<HKEY__ *,0,&void Windows::Detail::CloseWithRegCloseKey(HKEY__ *)>(&v121);
          if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL && NtClose(FileW) < 0 )
            __fastfail(v81 + 5);
          return v82;
        }
        if ( v81 )
        {
          v97.m128i_i64[0] = (__int64)"onecore\\base\\servicing\\updatereservemanager\\lib\\updatereservemanager.cpp";
          v97.m128i_i64[1] = (__int64)"UpdateReserveManager::Initialize";
          v98 = 227;
          v99 = "RetValue";
          if ( v81 > 0 )
            v81 = (unsigned __int16)v81 | 0x80070000;
          RtlReportErrorOrigination(&v97, &GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627, (unsigned int)v81);
          Windows::AutoGenericHandle<HKEY__ *,0,&void Windows::Detail::CloseWithRegCloseKey(HKEY__ *)>::~AutoGenericHandle<HKEY__ *,0,&void Windows::Detail::CloseWithRegCloseKey(HKEY__ *)>(&v121);
          if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL && NtClose(FileW) < 0 )
            __fastfail(7u);
          return (unsigned int)v81;
        }
        if ( *(_BYTE *)(a1 + 1176) && !*(_BYTE *)(a1 + 1178) )
        {
          *(_QWORD *)pcbData = 0;
          v83 = RegOpenKeyExW(
                  HKEY_LOCAL_MACHINE,
                  L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\ReserveManager",
                  0,
                  0x20119u,
                  (PHKEY)pcbData);
          if ( v83 == 2 )
          {
            Windows::AutoGenericHandle<HKEY__ *,0,&void Windows::Detail::CloseWithRegCloseKey(HKEY__ *)>::~AutoGenericHandle<HKEY__ *,0,&void Windows::Detail::CloseWithRegCloseKey(HKEY__ *)>(pcbData);
            Windows::AutoGenericHandle<HKEY__ *,0,&void Windows::Detail::CloseWithRegCloseKey(HKEY__ *)>::~AutoGenericHandle<HKEY__ *,0,&void Windows::Detail::CloseWithRegCloseKey(HKEY__ *)>(&v121);
            if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL && NtClose(FileW) < 0 )
              __fastfail(v83 + 5);
            return (a2 & 1) != 0 ? -2146498199 : -2146498192;
          }
          if ( v83 )
          {
            v97.m128i_i64[0] = (__int64)"onecore\\base\\servicing\\updatereservemanager\\lib\\updatereservemanager.cpp";
            v97.m128i_i64[1] = (__int64)"UpdateReserveManager::Initialize";
            v98 = 249;
            v99 = "RetValue";
            if ( v83 > 0 )
              v83 = (unsigned __int16)v83 | 0x80070000;
            RtlReportErrorOrigination(&v97, &GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627, (unsigned int)v83);
            Windows::AutoGenericHandle<HKEY__ *,0,&void Windows::Detail::CloseWithRegCloseKey(HKEY__ *)>::~AutoGenericHandle<HKEY__ *,0,&void Windows::Detail::CloseWithRegCloseKey(HKEY__ *)>(pcbData);
            Windows::AutoGenericHandle<HKEY__ *,0,&void Windows::Detail::CloseWithRegCloseKey(HKEY__ *)>::~AutoGenericHandle<HKEY__ *,0,&void Windows::Detail::CloseWithRegCloseKey(HKEY__ *)>(&v121);
            if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL && NtClose(FileW) < 0 )
              __fastfail(7u);
            return (unsigned int)v83;
          }
          Windows::AutoGenericHandle<HKEY__ *,0,&void Windows::Detail::CloseWithRegCloseKey(HKEY__ *)>::~AutoGenericHandle<HKEY__ *,0,&void Windows::Detail::CloseWithRegCloseKey(HKEY__ *)>(pcbData);
        }
        if ( GetFinalPathNameByHandleW(FileW, (LPWSTR)(a1 + 656), 0x104u, 1u) - 48 > 0xD4 )
        {
          v84 = GetLastError();
          v85 = v84 < 0;
          if ( v84 > 0 )
            v85 = 1;
          if ( !v85 )
            goto LABEL_255;
          v86 = GetLastError();
          v16 = v86;
          if ( v86 > 0 )
            v16 = (unsigned __int16)v86 | 0x80070000;
          if ( (v16 & 0x80000000) != 0 )
          {
LABEL_255:
            v97.m128i_i64[0] = (__int64)"onecore\\base\\servicing\\updatereservemanager\\lib\\updatereservemanager.cpp";
            v97.m128i_i64[1] = (__int64)"UpdateReserveManager::Initialize";
            v98 = 268;
            v99 = "hr";
            RtlReportErrorOrigination(&v97, &GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627, v16);
            Windows::AutoGenericHandle<HKEY__ *,0,&void Windows::Detail::CloseWithRegCloseKey(HKEY__ *)>::~AutoGenericHandle<HKEY__ *,0,&void Windows::Detail::CloseWithRegCloseKey(HKEY__ *)>(&v121);
            Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>::~AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>(&v104);
            return v16;
          }
        }
        *(_WORD *)(a1 + 752) = 0;
        v87 = (char *)CreateFileW((LPCWSTR)(a1 + 656), 0xC0000000, 7u, 0, 3u, 0, 0);
        if ( ((*(_QWORD *)(a1 + 128) + 1LL) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
        {
          *(_QWORD *)(a1 + 128) = v87;
          if ( (unsigned __int64)(v87 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
          {
            PassedPolicyValue = UpdateReserveManager::CreateOrOpenMutexInPrivateNamespace((UpdateReserveManager *)a1);
            if ( PassedPolicyValue < 0 )
            {
LABEL_259:
              Windows::AutoGenericHandle<HKEY__ *,0,&void Windows::Detail::CloseWithRegCloseKey(HKEY__ *)>::~AutoGenericHandle<HKEY__ *,0,&void Windows::Detail::CloseWithRegCloseKey(HKEY__ *)>(&v121);
              Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>::~AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>(&v104);
              return (unsigned int)PassedPolicyValue;
            }
            v119 = (HANDLE *)(a1 + 1192);
            v120 = 0;
            PassedPolicyValue = AutoMutexLocker::Lock((AutoMutexLocker *)&v119, v88);
            if ( PassedPolicyValue < 0 )
            {
              if ( !v120 || !*v119 )
                goto LABEL_259;
              goto LABEL_272;
            }
            PassedPolicyValue = UpdateReserveManager::ProcessOneSettings((UpdateReserveManager *)a1);
            if ( PassedPolicyValue < 0 )
            {
              if ( !v120 || !*v119 )
                goto LABEL_259;
              goto LABEL_272;
            }
            v90 = 0;
            v105 = 0;
            if ( *(_BYTE *)(a1 + 1178) )
              goto LABEL_290;
            PassedPolicyValue = UpdateReserveManager::GetPassedPolicyValue((UpdateReserveManager *)a1, &v105);
            if ( PassedPolicyValue < 0 )
            {
              if ( !v120 || !*v119 )
                goto LABEL_259;
LABEL_272:
              ReleaseMutex(*v119);
              goto LABEL_259;
            }
            v90 = v105;
            if ( v105 )
            {
              v91 = UpdateReserveManager::EnsureReservesExist((UpdateReserveManager *)a1);
              if ( v91 < 0 )
              {
                if ( !v120 || !*v119 )
                  goto LABEL_299;
                goto LABEL_298;
              }
            }
            else
            {
              v91 = UpdateReserveManager::SetReservesToZero((UpdateReserveManager *)a1);
              if ( v91 < 0 )
              {
                if ( !v120 || !*v119 )
                  goto LABEL_299;
LABEL_298:
                ReleaseMutex(*v119);
LABEL_299:
                Windows::AutoGenericHandle<HKEY__ *,0,&void Windows::Detail::CloseWithRegCloseKey(HKEY__ *)>::~AutoGenericHandle<HKEY__ *,0,&void Windows::Detail::CloseWithRegCloseKey(HKEY__ *)>(&v121);
                Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>::~AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>(&v104);
                return (unsigned int)v91;
              }
              if ( v24 )
              {
                *(_BYTE *)(a1 + 1178) = 1;
              }
              else if ( (a2 & 1) == 0 )
              {
                memset_0(v117, 0, 0xE8u);
                anonymous_namespace_::RtlGetVersionResource(0x180000000uLL, 0, 2, v117);
                CUpdateReserveManagerDiagnostics::ReportInitializeUpdateReserveManager(
                  v118,
                  v111,
                  (const char *)(a1 + 1200),
                  a2,
                  phkResulta,
                  0,
                  *(_BYTE *)(a1 + 1176),
                  -2146498192);
                if ( v120 && *v119 )
                  ReleaseMutex(*v119);
                Windows::AutoGenericHandle<HKEY__ *,0,&void Windows::Detail::CloseWithRegCloseKey(HKEY__ *)>::~AutoGenericHandle<HKEY__ *,0,&void Windows::Detail::CloseWithRegCloseKey(HKEY__ *)>(&v121);
                Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>::~AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>(&v104);
                return 2148469104LL;
              }
            }
            if ( *(_BYTE *)(a1 + 1178) )
            {
LABEL_290:
              v92 = *(char **)(a1 + 128);
              if ( (unsigned __int64)(v92 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
              {
                if ( NtClose(v92) < 0 )
                  __fastfail(7u);
                *(_QWORD *)(a1 + 128) = 0;
              }
              *(_WORD *)(a1 + 656) = 0;
              if ( *(_BYTE *)(a1 + 1176) )
              {
                v91 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)a1 + 112LL))(a1, 0);
                if ( v91 < 0 )
                {
                  if ( !v120 || !*v119 )
                    goto LABEL_299;
                  goto LABEL_298;
                }
              }
            }
            memset_0(v117, 0, 0xE8u);
            anonymous_namespace_::RtlGetVersionResource(0x180000000uLL, 0, 2, v117);
            CUpdateReserveManagerDiagnostics::ReportInitializeUpdateReserveManager(
              v118,
              v111,
              (const char *)(a1 + 1200),
              a2,
              phkResulta,
              v90 != 0,
              *(_BYTE *)(a1 + 1176),
              0);
            if ( v120 && *v119 )
              ReleaseMutex(*v119);
            Windows::AutoGenericHandle<HKEY__ *,0,&void Windows::Detail::CloseWithRegCloseKey(HKEY__ *)>::~AutoGenericHandle<HKEY__ *,0,&void Windows::Detail::CloseWithRegCloseKey(HKEY__ *)>(&v121);
            Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>::~AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>(&v104);
            return 0;
          }
          if ( !GetLastError() )
          {
            v93 = 14077;
LABEL_307:
            v97.m128i_i64[0] = (__int64)"onecore\\base\\servicing\\updatereservemanager\\lib\\updatereservemanager.cpp";
            v97.m128i_i64[1] = (__int64)"UpdateReserveManager::Initialize";
            v98 = 283;
            v99 = "m_VolumePathHandle.IsValid()";
            if ( (int)v93 > 0 )
              v93 = (unsigned __int16)v93 | 0x80070000;
            RtlReportErrorOrigination(&v97, &GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627, v93);
            Windows::AutoGenericHandle<HKEY__ *,0,&void Windows::Detail::CloseWithRegCloseKey(HKEY__ *)>::~AutoGenericHandle<HKEY__ *,0,&void Windows::Detail::CloseWithRegCloseKey(HKEY__ *)>(&v121);
            Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>::~AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>(&v104);
            return v93;
          }
          v93 = GetLastError();
          if ( v93 )
            goto LABEL_307;
        }
        INTERNAL_ERROR_ACTION(-1073741595);
      }
      v25 = 260;
      do
      {
        if ( !v11 )
          break;
        v26 = *a3;
        if ( !*a3 )
          break;
        ++a3;
        *v20++ = v26;
        --v11;
        --v25;
      }
      while ( v25 );
      result = v25 == 0 ? 0x8007007A : 0;
      v27 = v20 - 1;
      if ( v25 )
        v27 = v20;
      *v27 = 0;
      if ( !v25 )
        return result;
      v106 = 0;
      v107 = 0;
      v28 = -1;
      if ( a1 == -136 )
      {
        v30 = 0;
        v31 = 0u;
      }
      else
      {
        v29 = -1;
        do
          ++v29;
        while ( v19[v29] );
        v31.m128i_i64[0] = 2 * v29;
        v30 = a1 + 136;
        v31.m128i_i64[1] = v31.m128i_i64[0] + 2;
      }
      v97 = v31;
      v98 = v30;
      v99 = (const char *)50;
      v100 = 52;
      v101 = L"\\System32\\Config\\SOFTWARE";
      v32 = RtlCombineNtPathSegments(v30, &v97, &v106, v11);
      if ( v32 < 0 )
      {
        v34 = ConvertNtStatusToHResult(v32);
        if ( v107 )
          anonymous_namespace_::OurRtlFreeStringRoutine(v107);
        return v34;
      }
      v35 = v106;
      if ( *((_QWORD *)&v106 + 1) - (_QWORD)v106 < 2u )
      {
        if ( (__int64)v106 + 2 < (unsigned __int64)v106 )
        {
          v36 = -1073741675;
        }
        else
        {
          v36 = RtlReallocateLUnicodeString(v33, v106 + 2, &v106);
          if ( v36 >= 0 )
          {
            v35 = v106;
            goto LABEL_62;
          }
        }
        v37 = ConvertNtStatusToHResult(v36);
        if ( v107 )
          ((void (*)(void))anonymous_namespace_::OurRtlFreeStringRoutine)();
        return v37;
      }
LABEL_62:
      *(wchar_t *)((char *)v107 + (v35 & 0xFFFFFFFFFFFFFFFEuLL)) = 0;
      v124[0] = 17;
      v124[1] = 18;
      v119 = 0;
      v120 = 0;
      v110[0] = v124;
      v110[1] = 2;
      v38 = RtlSystemUtil::PrivilegeAcquisition::Acquire(&v119, v110);
      if ( v38 < 0 )
      {
        v41 = ConvertNtStatusToHResult(v38);
        RtlSystemUtil::PrivilegeAcquisition::~PrivilegeAcquisition((RtlSystemUtil::PrivilegeAcquisition *)&v119);
        if ( v107 )
          anonymous_namespace_::OurRtlFreeStringRoutine(v107);
        return v41;
      }
      v42 = Windows::Rtl::AutoHive::LoadFromWin32PathForOfflineHive((Windows::Rtl::AutoHive *)(a1 + 8), v39, v107, v40);
      if ( v42 < 0 )
      {
        v43 = ConvertNtStatusToHResult(v42);
        RtlSystemUtil::PrivilegeAcquisition::~PrivilegeAcquisition((RtlSystemUtil::PrivilegeAcquisition *)&v119);
        if ( v107 )
          anonymous_namespace_::OurRtlFreeStringRoutine(v107);
        return v43;
      }
      v114 = 0;
      v115 = 0;
      *(__m128i *)v108 = _mm_unpacklo_epi32(
                           _mm_unpacklo_epi16(_mm_cvtsi32_si128(*(_DWORD *)(a1 + 16)), (__m128i)0LL),
                           (__m128i)0LL);
      lpSubKey = *(LPCWSTR *)(a1 + 24);
      v44 = Windows::StringUtil::Rtl::ConvertNtRegistryPathToNullTerminatedWin32RegistryPath<_LUNICODE_STRING>(
              v108,
              &v114);
      if ( v44 < 0 )
      {
        v46 = ConvertNtStatusToHResult(v44);
        if ( v115 )
          anonymous_namespace_::OurRtlFreeStringRoutine(v115);
        RtlSystemUtil::PrivilegeAcquisition::~PrivilegeAcquisition((RtlSystemUtil::PrivilegeAcquisition *)&v119);
        if ( v107 )
          anonymous_namespace_::OurRtlFreeStringRoutine(v107);
        return v46;
      }
      v110[0] = 0;
      *(_OWORD *)v108 = 0;
      lpSubKey = 0;
      v112 = v114;
      v47 = v115;
      v113 = v115;
      v48 = RtlSplitWin32RegistryPathIntoRootAndLeaves(v45, &v112, v110, v108);
      if ( v48 < 0 )
      {
        v49 = ConvertNtStatusToHResult(v48);
        if ( v47 )
          anonymous_namespace_::OurRtlFreeStringRoutine(v47);
        RtlSystemUtil::PrivilegeAcquisition::~PrivilegeAcquisition((RtlSystemUtil::PrivilegeAcquisition *)&v119);
        if ( v107 )
          anonymous_namespace_::OurRtlFreeStringRoutine(v107);
        return v49;
      }
      if ( *(_QWORD *)(a1 + 104) )
        INTERNAL_ERROR_ACTION(-1073741595);
      v50 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0x2011Fu, (PHKEY)(a1 + 104));
      v52 = 0;
      if ( v50 )
      {
        v97.m128i_i64[0] = (__int64)"onecore\\base\\servicing\\updatereservemanager\\lib\\updatereservemanager.cpp";
        v97.m128i_i64[1] = (__int64)"UpdateReserveManager::Initialize";
        v98 = 143;
        v99 = "::RegOpenKeyExW((( HKEY ) (ULONG_PTR)((LONG)0x80000002) ), Key.Buffer, 0, ((((0x00020000L)) | (0x0001) | ("
              "0x0008) | (0x0010)) & (~(0x00100000L))) | ((((0x00020000L)) | (0x0002) | (0x0004)) & (~(0x00100000L))) | ("
              "0x0100), &m_SoftwareKey)";
        if ( v50 > 0 )
          v50 = (unsigned __int16)v50 | 0x80070000;
        RtlReportErrorOrigination(&v97, &GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627, (unsigned int)v50);
        if ( v47 )
          anonymous_namespace_::OurRtlFreeStringRoutine(v47);
        RtlSystemUtil::PrivilegeAcquisition::~PrivilegeAcquisition((RtlSystemUtil::PrivilegeAcquisition *)&v119);
        if ( v107 )
          anonymous_namespace_::OurRtlFreeStringRoutine(v107);
        return (unsigned int)v50;
      }
      v102 = 0;
      v103 = 0;
      if ( a1 == -136 )
      {
        v54 = 0;
        v53 = 0;
      }
      else
      {
        do
          ++v28;
        while ( v19[v28] );
        v53 = 2 * v28;
        v54 = a1 + 136;
        v52 = v53 + 2;
      }
      v97.m128i_i64[0] = v53;
      v97.m128i_i64[1] = v52;
      v98 = v54;
      v99 = (const char *)46;
      v100 = 48;
      v101 = L"\\System32\\Config\\SYSTEM";
      v55 = RtlCombineNtPathSegments(v52, &v97, &v102, v51);
      if ( v55 < 0 )
      {
        v59 = ConvertNtStatusToHResult(v55);
        if ( v103 )
        {
          anonymous_namespace_::OurRtlFreeStringRoutine(v103);
          v102 = 0;
          v103 = 0;
        }
        if ( v47 )
          anonymous_namespace_::OurRtlFreeStringRoutine(v47);
        RtlSystemUtil::PrivilegeAcquisition::~PrivilegeAcquisition((RtlSystemUtil::PrivilegeAcquisition *)&v119);
        if ( v107 )
          anonymous_namespace_::OurRtlFreeStringRoutine(v107);
        return v59;
      }
      v60 = v102;
      if ( *((_QWORD *)&v102 + 1) - (_QWORD)v102 >= 2u )
        goto LABEL_115;
      if ( (__int64)v102 + 2 < (unsigned __int64)v102 )
      {
        v61 = -1073741675;
      }
      else
      {
        v61 = RtlReallocateLUnicodeString(v57, v102 + 2, &v102);
        if ( v61 >= 0 )
        {
          v60 = v102;
LABEL_115:
          *(wchar_t *)((char *)v103 + (v60 & 0xFFFFFFFFFFFFFFFEuLL)) = 0;
          v63 = Windows::Rtl::AutoHive::LoadFromWin32PathForOfflineHive(
                  (Windows::Rtl::AutoHive *)(a1 + 56),
                  v56,
                  v103,
                  v58);
          if ( v63 < 0 )
          {
            v64 = ConvertNtStatusToHResult(v63);
            if ( v103 )
            {
              anonymous_namespace_::OurRtlFreeStringRoutine(v103);
              v102 = 0;
              v103 = 0;
            }
            if ( v47 )
              anonymous_namespace_::OurRtlFreeStringRoutine(v47);
            RtlSystemUtil::PrivilegeAcquisition::~PrivilegeAcquisition((RtlSystemUtil::PrivilegeAcquisition *)&v119);
            if ( v107 )
              anonymous_namespace_::OurRtlFreeStringRoutine(v107);
            return v64;
          }
          v112 = 0;
          v113 = 0;
          v97 = _mm_unpacklo_epi32(
                  _mm_unpacklo_epi16(_mm_cvtsi32_si128(*(_DWORD *)(a1 + 64)), (__m128i)0LL),
                  (__m128i)0LL);
          v98 = *(_QWORD *)(a1 + 72);
          v65 = Windows::StringUtil::Rtl::ConvertNtRegistryPathToNullTerminatedWin32RegistryPath<_LUNICODE_STRING>(
                  &v97,
                  &v112);
          if ( v65 < 0 )
          {
            v67 = ConvertNtStatusToHResult(v65);
            if ( v113 )
              anonymous_namespace_::OurRtlFreeStringRoutine(v113);
            if ( v103 )
            {
              anonymous_namespace_::OurRtlFreeStringRoutine(v103);
              v102 = 0;
              v103 = 0;
            }
            if ( v47 )
              anonymous_namespace_::OurRtlFreeStringRoutine(v47);
            RtlSystemUtil::PrivilegeAcquisition::~PrivilegeAcquisition((RtlSystemUtil::PrivilegeAcquisition *)&v119);
            if ( v107 )
              anonymous_namespace_::OurRtlFreeStringRoutine(v107);
            return v67;
          }
          v97 = v112;
          v68 = v113;
          v98 = v113;
          v69 = RtlSplitWin32RegistryPathIntoRootAndLeaves(v66, &v97, v110, v108);
          if ( v69 < 0 )
          {
            v70 = ConvertNtStatusToHResult(v69);
            if ( v68 )
              anonymous_namespace_::OurRtlFreeStringRoutine(v68);
            if ( v103 )
            {
              anonymous_namespace_::OurRtlFreeStringRoutine(v103);
              v102 = 0;
              v103 = 0;
            }
            if ( v47 )
              anonymous_namespace_::OurRtlFreeStringRoutine(v47);
            RtlSystemUtil::PrivilegeAcquisition::~PrivilegeAcquisition((RtlSystemUtil::PrivilegeAcquisition *)&v119);
            if ( v107 )
              anonymous_namespace_::OurRtlFreeStringRoutine(v107);
            return v70;
          }
          v71 = (HKEY *)(a1 + 112);
          if ( *(_QWORD *)(a1 + 112) )
            INTERNAL_ERROR_ACTION(-1073741595);
          v72 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0x2011Fu, (PHKEY)(a1 + 112));
          if ( v72 )
          {
            v97.m128i_i64[0] = (__int64)"onecore\\base\\servicing\\updatereservemanager\\lib\\updatereservemanager.cpp";
            v97.m128i_i64[1] = (__int64)"UpdateReserveManager::Initialize";
            v98 = 163;
            v99 = "::RegOpenKeyExW((( HKEY ) (ULONG_PTR)((LONG)0x80000002) ), Key.Buffer, 0, ((((0x00020000L)) | (0x0001)"
                  " | (0x0008) | (0x0010)) & (~(0x00100000L))) | ((((0x00020000L)) | (0x0002) | (0x0004)) & (~(0x00100000"
                  "L))) | (0x0100), &m_SystemKey)";
            if ( v72 > 0 )
              v72 = (unsigned __int16)v72 | 0x80070000;
            RtlReportErrorOrigination(&v97, &GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627, (unsigned int)v72);
            if ( v68 )
              anonymous_namespace_::OurRtlFreeStringRoutine(v68);
            if ( v103 )
            {
              anonymous_namespace_::OurRtlFreeStringRoutine(v103);
              v102 = 0;
              v103 = 0;
            }
            if ( v47 )
              anonymous_namespace_::OurRtlFreeStringRoutine(v47);
            RtlSystemUtil::PrivilegeAcquisition::~PrivilegeAcquisition((RtlSystemUtil::PrivilegeAcquisition *)&v119);
            if ( v107 )
              anonymous_namespace_::OurRtlFreeStringRoutine(v107);
            return (unsigned int)v72;
          }
          pvData = 0;
          pcbData[0] = 4;
          ValueW = RegGetValueW(*v71, L"Select", L"Current", 0x10u, 0, &pvData, pcbData);
          if ( ValueW )
          {
            v97.m128i_i64[0] = (__int64)"onecore\\base\\servicing\\updatereservemanager\\lib\\updatereservemanager.cpp";
            v97.m128i_i64[1] = (__int64)"UpdateReserveManager::Initialize";
            v98 = 173;
            v99 = "::RegGetValueW(m_SystemKey, L\"Select\", L\"Current\", 0x00000010, nullptr, &ControlSetNumber, &DataMax)";
            if ( ValueW > 0 )
              ValueW = (unsigned __int16)ValueW | 0x80070000;
            RtlReportErrorOrigination(&v97, &GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627, (unsigned int)ValueW);
            if ( v68 )
              anonymous_namespace_::OurRtlFreeStringRoutine(v68);
            if ( v103 )
            {
              anonymous_namespace_::OurRtlFreeStringRoutine(v103);
              v102 = 0;
              v103 = 0;
            }
            if ( v47 )
              anonymous_namespace_::OurRtlFreeStringRoutine(v47);
            RtlSystemUtil::PrivilegeAcquisition::~PrivilegeAcquisition((RtlSystemUtil::PrivilegeAcquisition *)&v119);
            if ( v107 )
              anonymous_namespace_::OurRtlFreeStringRoutine(v107);
            return (unsigned int)ValueW;
          }
          *(_OWORD *)v108 = 0;
          lpSubKey = 0;
          v75 = RtlReallocateLUnicodeString(v73, 28, v108);
          if ( v75 < 0 )
          {
            v76 = ConvertNtStatusToHResult(v75);
            if ( lpSubKey )
              anonymous_namespace_::OurRtlFreeStringRoutine(lpSubKey);
            if ( v68 )
              anonymous_namespace_::OurRtlFreeStringRoutine(v68);
            if ( v103 )
            {
              anonymous_namespace_::OurRtlFreeStringRoutine(v103);
              v102 = 0;
              v103 = 0;
            }
            if ( v47 )
              anonymous_namespace_::OurRtlFreeStringRoutine(v47);
            RtlSystemUtil::PrivilegeAcquisition::~PrivilegeAcquisition((RtlSystemUtil::PrivilegeAcquisition *)&v119);
            if ( v107 )
              anonymous_namespace_::OurRtlFreeStringRoutine(v107);
            return v76;
          }
          v77 = lpSubKey;
          LODWORD(phkResult) = pvData;
          v78 = StringCbPrintfW((wchar_t *)lpSubKey, v108[1], L"%ws%03lu", L"ControlSet", phkResult);
          if ( v78 < 0 )
          {
            if ( v77 )
              anonymous_namespace_::OurRtlFreeStringRoutine(v77);
            if ( v68 )
              anonymous_namespace_::OurRtlFreeStringRoutine(v68);
            if ( v103 )
            {
              anonymous_namespace_::OurRtlFreeStringRoutine(v103);
              v102 = 0;
              v103 = 0;
            }
            if ( v47 )
              anonymous_namespace_::OurRtlFreeStringRoutine(v47);
            RtlSystemUtil::PrivilegeAcquisition::~PrivilegeAcquisition((RtlSystemUtil::PrivilegeAcquisition *)&v119);
            if ( v107 )
              anonymous_namespace_::OurRtlFreeStringRoutine(v107);
            return (unsigned int)v78;
          }
          if ( *(_QWORD *)(a1 + 120) )
            INTERNAL_ERROR_ACTION(-1073741595);
          v79 = RegOpenKeyExW(*v71, v77, 0, 0x2011Fu, (PHKEY)(a1 + 120));
          if ( v79 )
          {
            v97.m128i_i64[0] = (__int64)"onecore\\base\\servicing\\updatereservemanager\\lib\\updatereservemanager.cpp";
            v97.m128i_i64[1] = (__int64)"UpdateReserveManager::Initialize";
            v98 = 188;
            v99 = "::RegOpenKeyExW(m_SystemKey, ControlSetName.Buffer, 0, ((((0x00020000L)) | (0x0001) | (0x0008) | (0x00"
                  "10)) & (~(0x00100000L))) | ((((0x00020000L)) | (0x0002) | (0x0004)) & (~(0x00100000L))) | (0x0100), &m"
                  "_CurrentControlSetKey)";
            if ( v79 > 0 )
              v79 = (unsigned __int16)v79 | 0x80070000;
            RtlReportErrorOrigination(&v97, &GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627, (unsigned int)v79);
            if ( v77 )
              anonymous_namespace_::OurRtlFreeStringRoutine(v77);
            if ( v68 )
              anonymous_namespace_::OurRtlFreeStringRoutine(v68);
            if ( v103 )
            {
              anonymous_namespace_::OurRtlFreeStringRoutine(v103);
              v102 = 0;
              v103 = 0;
            }
            if ( v47 )
              anonymous_namespace_::OurRtlFreeStringRoutine(v47);
            RtlSystemUtil::PrivilegeAcquisition::~PrivilegeAcquisition((RtlSystemUtil::PrivilegeAcquisition *)&v119);
            if ( v107 )
              anonymous_namespace_::OurRtlFreeStringRoutine(v107);
            return (unsigned int)v79;
          }
          *(_BYTE *)(a1 + 1176) = 1;
          v24 = v105;
          if ( v105 )
            *(_BYTE *)(a1 + 1178) = 1;
          if ( v77 )
            anonymous_namespace_::OurRtlFreeStringRoutine(v77);
          if ( v68 )
            anonymous_namespace_::OurRtlFreeStringRoutine(v68);
          if ( v103 )
          {
            anonymous_namespace_::OurRtlFreeStringRoutine(v103);
            v102 = 0;
            v103 = 0;
          }
          if ( v47 )
            anonymous_namespace_::OurRtlFreeStringRoutine(v47);
          RtlSystemUtil::PrivilegeAcquisition::~PrivilegeAcquisition((RtlSystemUtil::PrivilegeAcquisition *)&v119);
          if ( v107 )
            anonymous_namespace_::OurRtlFreeStringRoutine(v107);
          v19 = (const WCHAR *)(a1 + 136);
          goto LABEL_220;
        }
      }
      v62 = ConvertNtStatusToHResult(v61);
      if ( v103 )
      {
        ((void (*)(void))anonymous_namespace_::OurRtlFreeStringRoutine)();
        v102 = 0;
        v103 = 0;
      }
      if ( v47 )
        ((void (*)(void))anonymous_namespace_::OurRtlFreeStringRoutine)();
      RtlSystemUtil::PrivilegeAcquisition::~PrivilegeAcquisition((RtlSystemUtil::PrivilegeAcquisition *)&v119);
      if ( v107 )
        ((void (*)(void))anonymous_namespace_::OurRtlFreeStringRoutine)();
      result = v62;
    }
    catch ( ... )
    {
      return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                             retaddr,
                             (void *)0x17B,
                             (unsigned int)"onecore\\base\\servicing\\updatereservemanager\\lib\\updatereservemanager.cpp",
                             (const char *)v11);
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800177f8  mov     rax, rsp
0x1800177fb  push    rbx
0x1800177fc  push    rsi
0x1800177fd  push    rdi
0x1800177fe  push    r12
0x180017800  push    r13
0x180017802  push    r14
0x180017804  push    r15
0x180017806  sub     rsp, 270h
0x18001780d  mov     qword ptr [rax-198h], 0FFFFFFFFFFFFFFFEh
0x180017818  movaps  xmmword ptr [rax-48h], xmm6
0x18001781c  movaps  xmmword ptr [rax-58h], xmm7
0x180017820  mov     rax, cs:__security_cookie
0x180017827  xor     rax, rsp
0x18001782a  mov     [rsp+2A8h+var_68], rax
0x180017832  mov     [rsp+2A8h+var_1D0], r9
0x18001783a  mov     rbx, r8
0x18001783d  mov     r15d, edx
0x180017840  mov     rdi, rcx
0x180017843  call    RtlRegisterErrorOriginationCallback
0x180017848  lea     rsi, [rcx+4B0h]
0x18001784f  mov     rax, [rsp+2A8h+arg_20]
0x180017857  xor     r13d, r13d
0x18001785a  test    rax, rax
0x18001785d  jz      short loc_1800178B7
0x18001785f  mov     r9d, 7FFFFFFEh
0x180017865  mov     ecx, r9d
0x180017868  mov     edx, 81h
0x18001786d  mov     r8, rsi
0x180017870  test    rcx, rcx
0x180017873  jz      short loc_18001788F
0x180017875  mov     r10b, [rax]
0x180017878  test    r10b, r10b
0x18001787b  jz      short loc_18001788F
0x18001787d  inc     rax
0x180017880  mov     [r8], r10b
0x180017883  inc     r8
0x180017886  dec     rcx
0x180017889  sub     rdx, 1
0x18001788d  jnz     short loc_180017870
0x18001788f  mov     rax, rdx
0x180017892  neg     rax
0x180017895  sbb     eax, eax
0x180017897  not     eax
0x180017899  mov     r14d, 8007007Ah
0x18001789f  and     eax, r14d
0x1800178a2  lea     rcx, [r8-1]
0x1800178a6  test    rdx, rdx
0x1800178a9  cmovnz  rcx, r8
0x1800178ad  mov     [rcx], r13b
0x1800178b0  jnz     short loc_1800178E0
0x1800178b2  jmp     loc_18001917D
0x1800178b7  lea     rcx, [rsp+2A8h+var_188]; this
0x1800178bf  call    ??0TraceLoggingCorrelationVector@@QEAA@XZ; TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(void)
0x1800178c4  mov     rdx, rsi; char *
0x1800178c7  lea     rcx, [rsp+2A8h+var_188]; this
0x1800178cf  call    ?ToString@TraceLoggingCorrelationVector@@QEAA_NPEAD@Z; TraceLoggingCorrelationVector::ToString(char *)
0x1800178d4  mov     r9d, 7FFFFFFEh
0x1800178da  mov     r14d, 8007007Ah
0x1800178e0  mov     [rsp+2A8h+var_220], r13
0x1800178e8  mov     eax, r15d
0x1800178eb  and     eax, 2
0x1800178ee  mov     [rsp+2A8h+var_218], eax
0x1800178f5  jz      short loc_18001794C
0x1800178f7  test    r15b, 1
0x1800178fb  jz      short loc_18001794C
0x1800178fd  lea     rax, aOnecoreBaseSer_1; "onecore\\base\\servicing\\updatereserve"...
0x180017904  mov     qword ptr [rsp+2A8h+var_268], rax
0x180017909  lea     rax, aUpdatereservem_5; "UpdateReserveManager::Initialize"
0x180017910  mov     qword ptr [rsp+2A8h+var_268+8], rax
0x180017915  mov     [rsp+2A8h+var_258], 4Fh ; 'O'
0x18001791e  lea     rax, aHresult0x80070; "((HRESULT)0x80070057L)"
0x180017925  mov     [rsp+2A8h+var_250], rax
0x18001792a  mov     r8d, 80070057h
0x180017930  lea     rdx, _GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627
0x180017937  lea     rcx, [rsp+2A8h+var_268]
0x18001793c  call    RtlReportErrorOrigination
0x180017941  nop
0x180017942  mov     eax, 80070057h
0x180017947  jmp     loc_18001917D
0x18001794c  lea     r12, [rdi+88h]
0x180017953  mov     rcx, r12; lpBuffer
0x180017956  test    rbx, rbx
0x180017959  jnz     loc_180017BED
0x18001795f  mov     edx, 104h; uSize
0x180017964  call    cs:__imp_GetSystemWindowsDirectoryW
0x18001796a  test    eax, eax
0x18001796c  jnz     short loc_1800179E5
0x18001796e  call    cs:__imp_GetLastError
0x180017974  test    eax, eax
0x180017976  jnz     short loc_18001797F
0x180017978  mov     edi, 36FDh
0x18001797d  jmp     short loc_18001798F
0x18001797f  call    cs:__imp_GetLastError
0x180017985  mov     edi, eax
0x180017987  test    eax, eax
0x180017989  jz      loc_1800191C4
0x18001798f  lea     rax, aOnecoreBaseSer_1; "onecore\\base\\servicing\\updatereserve"...
0x180017996  mov     qword ptr [rsp+2A8h+var_268], rax
0x18001799b  lea     rax, aUpdatereservem_5; "UpdateReserveManager::Initialize"
0x1800179a2  mov     qword ptr [rsp+2A8h+var_268+8], rax
0x1800179a7  mov     [rsp+2A8h+var_258], 58h ; 'X'
0x1800179b0  lea     rax, aGetlasterror; "GetLastError"
0x1800179b7  mov     [rsp+2A8h+var_250], rax
0x1800179bc  test    edi, edi
0x1800179be  jle     short loc_1800179C9
0x1800179c0  movzx   edi, di
0x1800179c3  or      edi, 80070000h
0x1800179c9  mov     r8d, edi
0x1800179cc  lea     rdx, _GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627
0x1800179d3  lea     rcx, [rsp+2A8h+var_268]
0x1800179d8  call    RtlReportErrorOrigination
0x1800179dd  nop
0x1800179de  mov     eax, edi
0x1800179e0  jmp     loc_18001917D
0x1800179e5  cmp     eax, 104h
0x1800179ea  jbe     short loc_180017A39
0x1800179ec  lea     rax, aOnecoreBaseSer_1; "onecore\\base\\servicing\\updatereserve"...
0x1800179f3  mov     qword ptr [rsp+2A8h+var_268], rax
0x1800179f8  lea     rax, aUpdatereservem_5; "UpdateReserveManager::Initialize"
0x1800179ff  mov     qword ptr [rsp+2A8h+var_268+8], rax
0x180017a04  mov     [rsp+2A8h+var_258], 5Ch ; '\'
0x180017a0d  lea     rax, aStaticCastDwor_0; "static_cast<DWORD>(122L)"
0x180017a14  mov     [rsp+2A8h+var_250], rax
0x180017a19  mov     r8d, 8007007Ah
0x180017a1f  lea     rdx, _GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627
0x180017a26  lea     rcx, [rsp+2A8h+var_268]
0x180017a2b  call    RtlReportErrorOrigination
0x180017a30  nop
0x180017a31  mov     eax, r14d
0x180017a34  jmp     loc_18001917D
0x180017a39  lea     rax, [rdi+68h]
0x180017a3d  cmp     [rax], r13
0x180017a40  jnz     loc_1800191C4
0x180017a46  mov     [rsp+2A8h+phkResult], rax; phkResult
0x180017a4b  mov     r13d, 2011Fh
0x180017a51  mov     r9d, r13d; samDesired
0x180017a54  xor     r8d, r8d; ulOptions
0x180017a57  lea     rdx, aSoftware; "SOFTWARE"
0x180017a5e  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180017a65  call    cs:__imp_RegOpenKeyExW
0x180017a6b  mov     ebx, eax
0x180017a6d  xor     ecx, ecx
0x180017a6f  test    eax, eax
0x180017a71  jz      short loc_180017AC9
0x180017a73  lea     rax, aOnecoreBaseSer_1; "onecore\\base\\servicing\\updatereserve"...
0x180017a7a  mov     qword ptr [rsp+2A8h+var_268], rax
0x180017a7f  lea     rax, aUpdatereservem_5; "UpdateReserveManager::Initialize"
0x180017a86  mov     qword ptr [rsp+2A8h+var_268+8], rax
0x180017a8b  mov     [rsp+2A8h+var_258], 63h ; 'c'
0x180017a94  lea     rax, aRegopenkeyexwH_1; "::RegOpenKeyExW((( HKEY ) (ULONG_PTR)(("...
0x180017a9b  mov     [rsp+2A8h+var_250], rax
0x180017aa0  test    ebx, ebx
0x180017aa2  jle     short loc_180017AAD
0x180017aa4  movzx   ebx, bx
0x180017aa7  or      ebx, 80070000h
0x180017aad  mov     r8d, ebx
0x180017ab0  lea     rdx, _GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627
0x180017ab7  lea     rcx, [rsp+2A8h+var_268]
0x180017abc  call    RtlReportErrorOrigination
0x180017ac1  nop
0x180017ac2  mov     eax, ebx
0x180017ac4  jmp     loc_18001917D
0x180017ac9  lea     rsi, [rdi+70h]
0x180017acd  cmp     [rsi], rcx
0x180017ad0  jnz     loc_1800191C4
0x180017ad6  mov     [rsp+2A8h+phkResult], rsi; phkResult
0x180017adb  mov     r9d, r13d; samDesired
0x180017ade  xor     r8d, r8d; ulOptions
0x180017ae1  lea     rdx, aSystem; "SYSTEM"
0x180017ae8  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180017aef  call    cs:__imp_RegOpenKeyExW
0x180017af5  mov     ebx, eax
0x180017af7  xor     ecx, ecx
0x180017af9  test    eax, eax
0x180017afb  jz      short loc_180017B53
0x180017afd  lea     rax, aOnecoreBaseSer_1; "onecore\\base\\servicing\\updatereserve"...
0x180017b04  mov     qword ptr [rsp+2A8h+var_268], rax
0x180017b09  lea     rax, aUpdatereservem_5; "UpdateReserveManager::Initialize"
0x180017b10  mov     qword ptr [rsp+2A8h+var_268+8], rax
0x180017b15  mov     [rsp+2A8h+var_258], 69h ; 'i'
0x180017b1e  lea     rax, aRegopenkeyexwH_0; "::RegOpenKeyExW((( HKEY ) (ULONG_PTR)(("...
0x180017b25  mov     [rsp+2A8h+var_250], rax
0x180017b2a  test    ebx, ebx
0x180017b2c  jle     short loc_180017B37
0x180017b2e  movzx   ebx, bx
0x180017b31  or      ebx, 80070000h
0x180017b37  mov     r8d, ebx
0x180017b3a  lea     rdx, _GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627
0x180017b41  lea     rcx, [rsp+2A8h+var_268]
0x180017b46  call    RtlReportErrorOrigination
0x180017b4b  nop
0x180017b4c  mov     eax, ebx
0x180017b4e  jmp     loc_18001917D
0x180017b53  lea     rax, [rdi+78h]
0x180017b57  cmp     [rax], rcx
0x180017b5a  jnz     loc_1800191C4
0x180017b60  mov     [rsp+2A8h+phkResult], rax; phkResult
0x180017b65  mov     r9d, r13d; samDesired
0x180017b68  xor     r8d, r8d; ulOptions
0x180017b6b  lea     rdx, aCurrentcontrol; "CurrentControlSet"
0x180017b72  mov     rcx, [rsi]; hKey
0x180017b75  call    cs:__imp_RegOpenKeyExW
0x180017b7b  mov     ebx, eax
0x180017b7d  xor     esi, esi
0x180017b7f  test    eax, eax
0x180017b81  jz      short loc_180017BD9
0x180017b83  lea     rax, aOnecoreBaseSer_1; "onecore\\base\\servicing\\updatereserve"...
0x180017b8a  mov     qword ptr [rsp+2A8h+var_268], rax
0x180017b8f  lea     rax, aUpdatereservem_5; "UpdateReserveManager::Initialize"
0x180017b96  mov     qword ptr [rsp+2A8h+var_268+8], rax
0x180017b9b  mov     [rsp+2A8h+var_258], 6Fh ; 'o'
0x180017ba4  lea     rax, aRegopenkeyexwM_0; "::RegOpenKeyExW(m_SystemKey, L\"Current"...
0x180017bab  mov     [rsp+2A8h+var_250], rax
0x180017bb0  test    ebx, ebx
0x180017bb2  jle     short loc_180017BBD
0x180017bb4  movzx   ebx, bx
0x180017bb7  or      ebx, 80070000h
0x180017bbd  mov     r8d, ebx
0x180017bc0  lea     rdx, _GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627
0x180017bc7  lea     rcx, [rsp+2A8h+var_268]
0x180017bcc  call    RtlReportErrorOrigination
0x180017bd1  nop
0x180017bd2  mov     eax, ebx
0x180017bd4  jmp     loc_18001917D
0x180017bd9  mov     [rdi+498h], sil
0x180017be0  mov     r13d, [rsp+2A8h+var_218]
0x180017be8  jmp     loc_18001888F
0x180017bed  mov     r8d, 104h
0x180017bf3  test    r9, r9
0x180017bf6  jz      short loc_180017C14
0x180017bf8  movzx   eax, word ptr [rbx]
0x180017bfb  test    ax, ax
0x180017bfe  jz      short loc_180017C14
0x180017c00  add     rbx, 2
0x180017c04  mov     [rcx], ax
0x180017c07  add     rcx, 2
0x180017c0b  dec     r9
0x180017c0e  sub     r8, 1
0x180017c12  jnz     short loc_180017BF3
0x180017c14  mov     rax, r8
0x180017c17  neg     rax
0x180017c1a  sbb     eax, eax
0x180017c1c  not     eax
0x180017c1e  and     eax, r14d
0x180017c21  lea     rdx, [rcx-2]
0x180017c25  test    r8, r8
0x180017c28  cmovnz  rdx, rcx
0x180017c2c  mov     [rdx], r13w
0x180017c30  jnz     short loc_180017C37
0x180017c32  jmp     loc_18001917D
0x180017c37  xorps   xmm0, xmm0
0x180017c3a  xor     eax, eax
0x180017c3c  movups  [rsp+2A8h+var_210], xmm0
0x180017c44  mov     [rsp+2A8h+var_200], rax
0x180017c4c  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180017c50  test    r12, r12
0x180017c53  jz      short loc_180017C6E
0x180017c55  mov     rax, rsi
0x180017c58  inc     rax
0x180017c5b  cmp     [r12+rax*2], r13w
0x180017c60  jnz     short loc_180017C58
0x180017c62  add     rax, rax
0x180017c65  mov     rcx, r12
0x180017c68  lea     rdx, [rax+2]
0x180017c6c  jmp     short loc_180017C77
0x180017c6e  mov     rcx, r13
0x180017c71  mov     rax, r13
0x180017c74  mov     rdx, r13
0x180017c77  mov     qword ptr [rsp+2A8h+var_268], rax
0x180017c7c  mov     qword ptr [rsp+2A8h+var_268+8], rdx
0x180017c81  mov     [rsp+2A8h+var_258], rcx
0x180017c86  mov     [rsp+2A8h+var_250], 32h ; '2'
0x180017c8f  mov     [rsp+2A8h+var_248], 34h ; '4'
0x180017c98  lea     rax, aSystem32Config; "\\System32\\Config\\SOFTWARE"
0x180017c9f  mov     [rsp+2A8h+var_240], rax
0x180017ca4  lea     r8, [rsp+2A8h+var_210]
0x180017cac  lea     rdx, [rsp+2A8h+var_268]
0x180017cb1  call    RtlCombineNtPathSegments
0x180017cb6  test    eax, eax
0x180017cb8  jns     short loc_180017CDD
0x180017cba  mov     ecx, eax; Status
0x180017cbc  call    ConvertNtStatusToHResult
0x180017cc1  mov     ebx, eax
0x180017cc3  mov     rcx, [rsp+2A8h+var_200]
0x180017ccb  test    rcx, rcx
0x180017cce  jz      short loc_180017CD6
0x180017cd0  call    _anonymous_namespace___OurRtlFreeStringRoutine
0x180017cd5  nop
0x180017cd6  mov     eax, ebx
0x180017cd8  jmp     loc_18001917D
0x180017cdd  mov     r8, qword ptr [rsp+2A8h+var_210]
0x180017ce5  mov     rax, qword ptr [rsp+2A8h+var_210+8]
0x180017ced  sub     rax, r8
0x180017cf0  cmp     rax, 2
0x180017cf4  jnb     short loc_180017D42
0x180017cf6  lea     rdx, [r8+2]
0x180017cfa  cmp     rdx, r8
0x180017cfd  jb      short loc_180017D1A
0x180017cff  lea     r8, [rsp+2A8h+var_210]
  ... truncated ...
```
