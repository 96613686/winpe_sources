# SetupRecoveryTaskHandler::InternalCallPluginWorker(HKEY__ *,ushort *)

- ea: `0x180005f60`
- end: `0x1800068db`
- name: `?InternalCallPluginWorker@SetupRecoveryTaskHandler@@AEAAJPEAUHKEY__@@PEAG@Z`
- size: `2427`
- prototype: `__int64 __fastcall(SetupRecoveryTaskHandler *this, HKEY, char *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, service_task, installer_update`

## callers

- `0x18000a210`

## callees

- `0x1800040f4`
- `0x180005f60`
- `0x18000c610`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180006897`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180006897`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180006395`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180006395`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180006615`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180006615`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180005feb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180005feb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180006866`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180006866`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180006107`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800062b1`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180006107`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800062b1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006884`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006884`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800064fe`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006876`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800064fe`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006876`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000650f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000650f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006000`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000611c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800061c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800062ca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800063ad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800063c2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006411`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000649a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800064af`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006552`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006567`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800065b6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006628`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000663d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000668c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800066f5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800067fc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006000`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000611c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800061c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800062ca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800063ad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800063c2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006411`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000649a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800064af`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006552`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006567`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800065b6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006628`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000663d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000668c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800066f5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800067fc`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18000648d`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180006548`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18000648d`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180006548`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000606e`
- `WDSCORE!WdsSetupLogMessageW` at `0x1800060d2`
- `WDSCORE!WdsSetupLogMessageW` at `0x1800061c1`
- `WDSCORE!WdsSetupLogMessageW` at `0x180006216`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000636f`
- `WDSCORE!WdsSetupLogMessageW` at `0x180006460`
- `WDSCORE!WdsSetupLogMessageW` at `0x180006605`
- `WDSCORE!WdsSetupLogMessageW` at `0x1800066db`
- `WDSCORE!WdsSetupLogMessageW` at `0x180006763`
- `WDSCORE!WdsSetupLogMessageW` at `0x1800067b0`
- `WDSCORE!WdsSetupLogMessageW` at `0x180006853`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000606e`
- `WDSCORE!WdsSetupLogMessageW` at `0x1800060d2`
- `WDSCORE!WdsSetupLogMessageW` at `0x1800061c1`
- `WDSCORE!WdsSetupLogMessageW` at `0x180006216`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000636f`
- `WDSCORE!WdsSetupLogMessageW` at `0x180006460`
- `WDSCORE!WdsSetupLogMessageW` at `0x180006605`
- `WDSCORE!WdsSetupLogMessageW` at `0x1800066db`
- `WDSCORE!WdsSetupLogMessageW` at `0x180006763`
- `WDSCORE!WdsSetupLogMessageW` at `0x1800067b0`
- `WDSCORE!WdsSetupLogMessageW` at `0x180006853`
- `WDSCORE!CurrentIP` at `0x180006008`
- `WDSCORE!CurrentIP` at `0x180006124`
- `WDSCORE!CurrentIP` at `0x1800061cf`
- `WDSCORE!CurrentIP` at `0x1800062d2`
- `WDSCORE!CurrentIP` at `0x1800063ca`
- `WDSCORE!CurrentIP` at `0x180006419`
- `WDSCORE!CurrentIP` at `0x1800064b7`
- `WDSCORE!CurrentIP` at `0x18000656f`
- `WDSCORE!CurrentIP` at `0x1800065be`
- `WDSCORE!CurrentIP` at `0x180006645`
- `WDSCORE!CurrentIP` at `0x180006694`
- `WDSCORE!CurrentIP` at `0x1800066fd`
- `WDSCORE!CurrentIP` at `0x180006804`
- `WDSCORE!CurrentIP` at `0x180006008`
- `WDSCORE!CurrentIP` at `0x180006124`
- `WDSCORE!CurrentIP` at `0x1800061cf`
- `WDSCORE!CurrentIP` at `0x1800062d2`
- `WDSCORE!CurrentIP` at `0x1800063ca`
- `WDSCORE!CurrentIP` at `0x180006419`
- `WDSCORE!CurrentIP` at `0x1800064b7`
- `WDSCORE!CurrentIP` at `0x18000656f`
- `WDSCORE!CurrentIP` at `0x1800065be`
- `WDSCORE!CurrentIP` at `0x180006645`
- `WDSCORE!CurrentIP` at `0x180006694`
- `WDSCORE!CurrentIP` at `0x1800066fd`
- `WDSCORE!CurrentIP` at `0x180006804`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18000637d`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18000637d`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x18000625e`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x18000625e`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18000626d`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1800068a6`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18000626d`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1800068a6`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x180005fc3`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x180006247`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x180005fc3`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x180006247`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180006386`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180006386`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18000627c`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18000627c`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18000622c`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18000622c`
- `unbcl!?ExpandEnvironmentVariables@Environment@UnBCL@@SAPEAVString@2@PEBV32@@Z` at `0x180006236`
- `unbcl!?ExpandEnvironmentVariables@Environment@UnBCL@@SAPEAVString@2@PEBV32@@Z` at `0x180006236`

## string_xrefs

- `0x180006048`: `base\diagnosis\srt\setuprecoverydatatask\dll\src\setuprecoverydatatask.cpp`
- `0x1800060ac`: `base\diagnosis\srt\setuprecoverydatatask\dll\src\setuprecoverydatatask.cpp`
- `0x1800067c3`: `base\diagnosis\srt\setuprecoverydatatask\dll\src\setuprecoverydatatask.cpp`
- `0x18000603c`: `SetupRecoveryTaskHandler::InternalCallPluginWorker`
- `0x1800060a0`: `SetupRecoveryTaskHandler::InternalCallPluginWorker`
- `0x1800067bc`: `SetupRecoveryTaskHandler::InternalCallPluginWorker`
- `0x180006018`: `SetupRecoveryTaskHandler::InternalCallPluginWorker: RegOpenKeyExW failed to open registered plugin key. Error: 0x%08X`
- `0x18000607c`: `SetupRecoveryTaskHandler::InternalCallPluginWorker: Successfully opened [%s] key`
- `0x180006134`: `SetupRecoveryTaskHandler::InternalCallPluginWorker: RegQueryValueExW failed to query the binary location. Error: 0x%08X`
- `0x18000617e`: `SetupRecoveryTaskHandler::InternalCallPluginWorker: Successfully queried the %s: [%s]`
- `0x18000632c`: `SetupRecoveryTaskHandler::InternalCallPluginWorker: Successfully queried the %s: [%s]`
- `0x1800061d8`: `SetupRecoveryTaskHandler::InternalCallPluginWorker: Expanding the binary location file path in case of environment variable usage`
- `0x1800062e2`: `SetupRecoveryTaskHandler::InternalCallPluginWorker: RegQueryValueExW failed to query the entry point name. Error: 0x%08X`
- `0x1800063d6`: `SetupRecoveryTaskHandler::InternalCallPluginWorker: LoadLibraryEx failed to load the plugin dll. Error: 0x%08X`
- `0x180006422`: `SetupRecoveryTaskHandler::InternalCallPluginWorker: Successfully loaded the binary path`
- `0x1800064c3`: `SetupRecoveryTaskHandler::InternalCallPluginWorker: Failed to get UTF-8 length for registered plugin. Error: 0x%08X`
- `0x18000657b`: `SetupRecoveryTaskHandler::InternalCallPluginWorker: Failed to get UTF-8 value for registered plugin. Error: 0x%08X`
- `0x1800065c7`: `SetupRecoveryTaskHandler::InternalCallPluginWorker: Successfully converted entrypoint into UTF-8 for GetProcAddress`
- `0x180006651`: `SetupRecoveryTaskHandler::InternalCallPluginWorker: GetProcAddress failed to find plugin entry point. Error: 0x%08X`
- `0x18000669d`: `SetupRecoveryTaskHandler::InternalCallPluginWorker: Successfully got handle to the entry point`
- `0x180006722`: `SetupRecoveryTaskHandler::InternalCallPluginWorker: Failure occurred while executing the plugin. Error: 0x%08X, Plugin: [%s], Entry Point: [%s]`
- `0x18000676f`: `SetupRecoveryTaskHandler::InternalCallPluginWorker: Successfully called the entry point`
- `0x180006812`: `SetupRecoveryTaskHandler::InternalCallPluginWorker: Cleaning up variables for [%s]`

## pseudocode

```c
__int64 __fastcall SetupRecoveryTaskHandler::InternalCallPluginWorker(
        SetupRecoveryTaskHandler *this,
        HKEY a2,
        char *a3)
{
  LSTATUS v5; // eax
  signed int v6; // esi
  DWORD LastError; // edi
  __int64 v8; // rbx
  struct tagLOG_PARTIAL_MSG *v9; // rax
  struct tagLOG_PARTIAL_MSG *v10; // rax
  LSTATUS v11; // eax
  DWORD v12; // edi
  __int64 v13; // rbx
  struct tagLOG_PARTIAL_MSG *v14; // rax
  DWORD v15; // edi
  __int64 v16; // rbx
  struct tagLOG_PARTIAL_MSG *v17; // rax
  const struct UnBCL::String *v18; // rcx
  struct UnBCL::String *v19; // rax
  LSTATUS v20; // eax
  DWORD v21; // edi
  __int64 v22; // rbx
  struct tagLOG_PARTIAL_MSG *v23; // rax
  UnBCL::String *v24; // rax
  const WCHAR *CString; // rax
  signed int v26; // eax
  DWORD v27; // edi
  __int64 v28; // rbx
  DWORD v29; // edi
  __int64 v30; // rbx
  struct tagLOG_PARTIAL_MSG *v31; // rax
  int v32; // eax
  SIZE_T v33; // rdi
  signed int v34; // eax
  DWORD v35; // edi
  __int64 v36; // rbx
  HANDLE ProcessHeap; // rax
  signed int v38; // eax
  DWORD v39; // edi
  __int64 v40; // rbx
  DWORD v41; // edi
  __int64 v42; // rbx
  struct tagLOG_PARTIAL_MSG *v43; // rax
  signed int v44; // eax
  DWORD v45; // edi
  __int64 v46; // rbx
  DWORD v47; // edi
  __int64 v48; // rbx
  struct tagLOG_PARTIAL_MSG *v49; // rax
  DWORD v50; // edi
  __int64 v51; // rax
  __int64 v52; // rbx
  struct tagLOG_PARTIAL_MSG *v53; // rax
  struct tagLOG_PARTIAL_MSG *v54; // rax
  DWORD v55; // edi
  __int64 v56; // rbx
  struct tagLOG_PARTIAL_MSG *v57; // rax
  HANDLE v58; // rax
  DWORD v60; // edi
  __int64 v61; // rbx
  struct tagLOG_PARTIAL_MSG *v62; // rax
  int phkResult; // [rsp+20h] [rbp-528h]
  LPBOOL lpUsedDefaultChar; // [rsp+38h] [rbp-510h]
  DWORD v65; // [rsp+40h] [rbp-508h]
  signed int v66; // [rsp+60h] [rbp-4E8h]
  CHAR *lpProcName; // [rsp+68h] [rbp-4E0h]
  HMODULE hModule; // [rsp+70h] [rbp-4D8h]
  const char *v69; // [rsp+78h] [rbp-4D0h]
  _QWORD v70[2]; // [rsp+80h] [rbp-4C8h] BYREF
  __int64 (*ProcAddress)(void); // [rsp+90h] [rbp-4B8h]
  HMODULE v72; // [rsp+98h] [rbp-4B0h]
  unsigned __int16 *v73; // [rsp+A0h] [rbp-4A8h]
  _BYTE v74[24]; // [rsp+B0h] [rbp-498h] BYREF
  HKEY hKey; // [rsp+C8h] [rbp-480h] BYREF
  DWORD cbData; // [rsp+D0h] [rbp-478h] BYREF
  BYTE v77[24]; // [rsp+D8h] [rbp-470h] BYREF
  WCHAR v78[264]; // [rsp+F0h] [rbp-458h] BYREF
  unsigned __int16 Data[264]; // [rsp+300h] [rbp-248h] BYREF

  v69 = a3;
  v73 = (unsigned __int16 *)a3;
  hKey = 0;
  cbData = 260;
  hModule = 0;
  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v77, 0);
  lpProcName = 0;
  v5 = RegOpenKeyExW(a2, (LPCWSTR)a3, 0, 0x20019u, &hKey);
  v6 = v5;
  if ( v5 > 0 )
    v6 = (unsigned __int16)v5 | 0x80070000;
  LastError = GetLastError();
  v8 = CurrentIP();
  if ( v6 < 0 )
  {
    v9 = ConstructPartialMsgW(
           0x2000000u,
           "SetupRecoveryTaskHandler::InternalCallPluginWorker: RegOpenKeyExW failed to open registered plugin key. Error: 0x%08X",
           v6);
    v65 = LastError;
    lpUsedDefaultChar = (LPBOOL)v8;
    phkResult = 189;
LABEL_5:
    WdsSetupLogMessageW(
      v9,
      0,
      L"D",
      0,
      phkResult,
      L"base\\diagnosis\\srt\\setuprecoverydatatask\\dll\\src\\setuprecoverydatatask.cpp",
      L"SetupRecoveryTaskHandler::InternalCallPluginWorker",
      lpUsedDefaultChar,
      v65,
      0,
      0);
    goto LABEL_34;
  }
  v10 = ConstructPartialMsgW(
          0x4000000u,
          "SetupRecoveryTaskHandler::InternalCallPluginWorker: Successfully opened [%s] key",
          a3);
  WdsSetupLogMessageW(
    v10,
    0,
    L"D",
    0,
    194,
    L"base\\diagnosis\\srt\\setuprecoverydatatask\\dll\\src\\setuprecoverydatatask.cpp",
    L"SetupRecoveryTaskHandler::InternalCallPluginWorker",
    v8,
    LastError,
    0,
    0);
  v11 = RegQueryValueExW(hKey, L"BinaryLocation", 0, 0, (LPBYTE)Data, &cbData);
  v6 = v11;
  if ( v11 > 0 )
    v6 = (unsigned __int16)v11 | 0x80070000;
  v12 = GetLastError();
  v13 = CurrentIP();
  if ( v6 < 0 )
  {
    v9 = ConstructPartialMsgW(
           0x2000000u,
           "SetupRecoveryTaskHandler::InternalCallPluginWorker: RegQueryValueExW failed to query the binary location. Error: 0x%08X",
           v6);
    v65 = v12;
    lpUsedDefaultChar = (LPBOOL)v13;
    phkResult = 201;
    goto LABEL_5;
  }
  v14 = ConstructPartialMsgW(
          0x4000000u,
          "SetupRecoveryTaskHandler::InternalCallPluginWorker: Successfully queried the %s: [%s]",
          (const char *)L"BinaryLocation",
          (const char *)Data);
  WdsSetupLogMessageW(
    v14,
    0,
    L"D",
    0,
    206,
    L"base\\diagnosis\\srt\\setuprecoverydatatask\\dll\\src\\setuprecoverydatatask.cpp",
    L"SetupRecoveryTaskHandler::InternalCallPluginWorker",
    v13,
    v12,
    0,
    0);
  v15 = GetLastError();
  v16 = CurrentIP();
  v17 = ConstructPartialMsgW(
          0x4000000u,
          "SetupRecoveryTaskHandler::InternalCallPluginWorker: Expanding the binary location file path in case of environ"
          "ment variable usage");
  WdsSetupLogMessageW(
    v17,
    0,
    L"D",
    0,
    210,
    L"base\\diagnosis\\srt\\setuprecoverydatatask\\dll\\src\\setuprecoverydatatask.cpp",
    L"SetupRecoveryTaskHandler::InternalCallPluginWorker",
    v16,
    v15,
    0,
    0);
  v18 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v74, Data);
  v19 = UnBCL::Environment::ExpandEnvironmentVariables(v18);
  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v70, v19);
  UnBCL::SmartPtr<UnBCL::String>::operator=(v77, v70);
  UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v70);
  UnBCL::String::~String((UnBCL::String *)v74);
  v20 = RegQueryValueExW(hKey, L"EntryPoint", 0, 0, (LPBYTE)v78, &cbData);
  v6 = v20;
  if ( v20 > 0 )
    v6 = (unsigned __int16)v20 | 0x80070000;
  v21 = GetLastError();
  v22 = CurrentIP();
  if ( v6 < 0 )
  {
    v9 = ConstructPartialMsgW(
           0x2000000u,
           "SetupRecoveryTaskHandler::InternalCallPluginWorker: RegQueryValueExW failed to query the entry point name. Error: 0x%08X",
           v6);
    v65 = v21;
    lpUsedDefaultChar = (LPBOOL)v22;
    phkResult = 217;
    goto LABEL_5;
  }
  v23 = ConstructPartialMsgW(
          0x4000000u,
          "SetupRecoveryTaskHandler::InternalCallPluginWorker: Successfully queried the %s: [%s]",
          (const char *)L"EntryPoint",
          (const char *)v78);
  WdsSetupLogMessageW(
    v23,
    0,
    L"D",
    0,
    222,
    L"base\\diagnosis\\srt\\setuprecoverydatatask\\dll\\src\\setuprecoverydatatask.cpp",
    L"SetupRecoveryTaskHandler::InternalCallPluginWorker",
    v22,
    v21,
    0,
    0);
  v24 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v77);
  CString = UnBCL::String::get_CString(v24);
  hModule = LoadLibraryExW(CString, 0, 8u);
  v72 = hModule;
  if ( !hModule )
  {
    v26 = GetLastError();
    v6 = v26;
    if ( v26 > 0 )
      v6 = (unsigned __int16)v26 | 0x80070000;
    v27 = GetLastError();
    v28 = CurrentIP();
    v9 = ConstructPartialMsgW(
           0x2000000u,
           "SetupRecoveryTaskHandler::InternalCallPluginWorker: LoadLibraryEx failed to load the plugin dll. Error: 0x%08X",
           v6);
    v65 = v27;
    lpUsedDefaultChar = (LPBOOL)v28;
    phkResult = 230;
    goto LABEL_5;
  }
  v29 = GetLastError();
  v30 = CurrentIP();
  v31 = ConstructPartialMsgW(
          0x4000000u,
          "SetupRecoveryTaskHandler::InternalCallPluginWorker: Successfully loaded the binary path");
  WdsSetupLogMessageW(
    v31,
    0,
    L"D",
    0,
    235,
    L"base\\diagnosis\\srt\\setuprecoverydatatask\\dll\\src\\setuprecoverydatatask.cpp",
    L"SetupRecoveryTaskHandler::InternalCallPluginWorker",
    v30,
    v29,
    0,
    0);
  v32 = WideCharToMultiByte(0xFDE9u, 0, v78, -1, 0, 0, 0, 0);
  v33 = v32;
  if ( !v32 )
  {
    v34 = GetLastError();
    v6 = v34;
    if ( v34 > 0 )
      v6 = (unsigned __int16)v34 | 0x80070000;
    v35 = GetLastError();
    v36 = CurrentIP();
    v9 = ConstructPartialMsgW(
           0x2000000u,
           "SetupRecoveryTaskHandler::InternalCallPluginWorker: Failed to get UTF-8 length for registered plugin. Error: 0x%08X",
           v6);
    v65 = v35;
    lpUsedDefaultChar = (LPBOOL)v36;
    phkResult = 245;
    goto LABEL_5;
  }
  ProcessHeap = GetProcessHeap();
  lpProcName = (CHAR *)HeapAlloc(ProcessHeap, 8u, v33);
  v70[0] = lpProcName;
  if ( !WideCharToMultiByte(0xFDE9u, 0, v78, -1, lpProcName, v33, 0, 0) )
  {
    v38 = GetLastError();
    v6 = v38;
    if ( v38 > 0 )
      v6 = (unsigned __int16)v38 | 0x80070000;
    v39 = GetLastError();
    v40 = CurrentIP();
    v9 = ConstructPartialMsgW(
           0x2000000u,
           "SetupRecoveryTaskHandler::InternalCallPluginWorker: Failed to get UTF-8 value for registered plugin. Error: 0x%08X",
           v6);
    v65 = v39;
    lpUsedDefaultChar = (LPBOOL)v40;
    phkResult = 254;
    goto LABEL_5;
  }
  v41 = GetLastError();
  v42 = CurrentIP();
  v43 = ConstructPartialMsgW(
          0x4000000u,
          "SetupRecoveryTaskHandler::InternalCallPluginWorker: Successfully converted entrypoint into UTF-8 for GetProcAddress");
  WdsSetupLogMessageW(
    v43,
    0,
    L"D",
    0,
    258,
    L"base\\diagnosis\\srt\\setuprecoverydatatask\\dll\\src\\setuprecoverydatatask.cpp",
    L"SetupRecoveryTaskHandler::InternalCallPluginWorker",
    v42,
    v41,
    0,
    0);
  ProcAddress = GetProcAddress(hModule, lpProcName);
  if ( !ProcAddress )
  {
    v44 = GetLastError();
    v6 = v44;
    if ( v44 > 0 )
      v6 = (unsigned __int16)v44 | 0x80070000;
    v45 = GetLastError();
    v46 = CurrentIP();
    v9 = ConstructPartialMsgW(
           0x2000000u,
           "SetupRecoveryTaskHandler::InternalCallPluginWorker: GetProcAddress failed to find plugin entry point. Error: 0x%08X",
           v6);
    v65 = v45;
    lpUsedDefaultChar = (LPBOOL)v46;
    phkResult = 264;
    goto LABEL_5;
  }
  v47 = GetLastError();
  v48 = CurrentIP();
  v49 = ConstructPartialMsgW(
          0x4000000u,
          "SetupRecoveryTaskHandler::InternalCallPluginWorker: Successfully got handle to the entry point");
  WdsSetupLogMessageW(
    v49,
    0,
    L"D",
    0,
    269,
    L"base\\diagnosis\\srt\\setuprecoverydatatask\\dll\\src\\setuprecoverydatatask.cpp",
    L"SetupRecoveryTaskHandler::InternalCallPluginWorker",
    v48,
    v47,
    0,
    0);
  if ( __eh34_try(-1, 0) )
  {
    __eh34_scope_strut(0);
    v6 = ProcAddress();
    v66 = v6;
    v50 = GetLastError();
    v51 = CurrentIP();
  }
  if ( __eh34_catch(0) )
  {
    if ( __eh34_catch_type(0, &exception `RTTI Type Descriptor', 0) )
    {
      v60 = GetLastError();
      v61 = CurrentIP();
      v62 = ConstructPartialMsgW(
              0x2000000u,
              "SetupRecoveryTaskHandler::InternalCallPluginWorker: Unhandled exception while executing the plugin. Plugin"
              ": [%s], Entry Point: [%s]",
              (const char *)Data,
              (const char *)v78);
      WdsSetupLogMessageW(
        v62,
        0,
        L"D",
        0,
        292,
        L"base\\diagnosis\\srt\\setuprecoverydatatask\\dll\\src\\setuprecoverydatatask.cpp",
        L"SetupRecoveryTaskHandler::InternalCallPluginWorker",
        v61,
        v60,
        0,
        0);
      v6 = v66;
      hModule = v72;
      lpProcName = (CHAR *)v70[0];
      v69 = (const char *)v73;
      __eh34_try_continuation(0, &exception `RTTI Type Descriptor', &loc_1800067B9);
      goto LABEL_34;
    }
  }
  v52 = v51;
  if ( v6 >= 0 )
  {
    v54 = ConstructPartialMsgW(
            0x4000000u,
            "SetupRecoveryTaskHandler::InternalCallPluginWorker: Successfully called the entry point");
    WdsSetupLogMessageW(
      v54,
      0,
      L"D",
      0,
      287,
      L"base\\diagnosis\\srt\\setuprecoverydatatask\\dll\\src\\setuprecoverydatatask.cpp",
      L"SetupRecoveryTaskHandler::InternalCallPluginWorker",
      v52,
      v50,
      0,
      0);
  }
  else
  {
    v53 = ConstructPartialMsgW(
            0x2000000u,
            "SetupRecoveryTaskHandler::InternalCallPluginWorker: Failure occurred while executing the plugin. Error: 0x%0"
            "8X, Plugin: [%s], Entry Point: [%s]",
            v6,
            (const char *)Data,
            (const char *)v78);
    WdsSetupLogMessageW(
      v53,
      0,
      L"D",
      0,
      282,
      L"base\\diagnosis\\srt\\setuprecoverydatatask\\dll\\src\\setuprecoverydatatask.cpp",
      L"SetupRecoveryTaskHandler::InternalCallPluginWorker",
      v52,
      v50,
      0,
      0);
  }
LABEL_34:
  v55 = GetLastError();
  v56 = CurrentIP();
  v57 = ConstructPartialMsgW(
          0x4000000u,
          "SetupRecoveryTaskHandler::InternalCallPluginWorker: Cleaning up variables for [%s]",
          v69);
  WdsSetupLogMessageW(
    v57,
    0,
    L"D",
    0,
    298,
    L"base\\diagnosis\\srt\\setuprecoverydatatask\\dll\\src\\setuprecoverydatatask.cpp",
    L"SetupRecoveryTaskHandler::InternalCallPluginWorker",
    v56,
    v55,
    0,
    0);
  if ( hKey )
    RegCloseKey(hKey);
  if ( lpProcName )
  {
    v58 = GetProcessHeap();
    HeapFree(v58, 0, lpProcName);
  }
  if ( hModule )
    FreeLibrary(hModule);
  UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v77);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180005f60  mov     r11, rsp
0x180005f63  mov     [r11+8], rbx
0x180005f67  mov     [r11+20h], rsi
0x180005f6b  push    rdi
0x180005f6c  push    r12
0x180005f6e  push    r13
0x180005f70  push    r14
0x180005f72  push    r15
0x180005f74  sub     rsp, 520h
0x180005f7b  mov     rax, cs:__security_cookie
0x180005f82  xor     rax, rsp
0x180005f85  mov     [rsp+548h+var_38], rax
0x180005f8d  mov     r15, r8
0x180005f90  mov     [rsp+548h+var_4D0], r8
0x180005f95  mov     rbx, rdx
0x180005f98  mov     [rsp+548h+var_4A8], r8
0x180005fa0  xor     r14d, r14d
0x180005fa3  mov     [r11-480h], r14
0x180005faa  mov     [rsp+548h+cbData], 104h
0x180005fb5  mov     [rsp+548h+hModule], r14
0x180005fba  xor     edx, edx
0x180005fbc  lea     rcx, [r11-470h]
0x180005fc3  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x180005fc9  nop
0x180005fca  mov     [rsp+548h+lpProcName], r14
0x180005fcf  lea     rax, [rsp+548h+hKey]
0x180005fd7  mov     [rsp+548h+phkResult], rax; phkResult
0x180005fdc  mov     r9d, 20019h; samDesired
0x180005fe2  xor     r8d, r8d; ulOptions
0x180005fe5  mov     rdx, r15; lpSubKey
0x180005fe8  mov     rcx, rbx; hKey
0x180005feb  call    cs:__imp_RegOpenKeyExW
0x180005ff1  mov     esi, eax
0x180005ff3  test    eax, eax
0x180005ff5  jle     short loc_180006000
0x180005ff7  movzx   esi, ax
0x180005ffa  or      esi, 80070000h
0x180006000  call    cs:__imp_GetLastError
0x180006006  mov     edi, eax
0x180006008  call    cs:__imp_CurrentIP
0x18000600e  mov     rbx, rax
0x180006011  test    esi, esi
0x180006013  jns     short loc_180006079
0x180006015  mov     r8d, esi
0x180006018  lea     rdx, aSetuprecoveryt_7; "SetupRecoveryTaskHandler::InternalCallP"...
0x18000601f  mov     ecx, 2000000h; unsigned int
0x180006024  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180006029  mov     [rsp+548h+var_4F8], r14d
0x18000602e  mov     [rsp+548h+var_500], r14
0x180006033  mov     [rsp+548h+var_508], edi
0x180006037  mov     [rsp+548h+lpUsedDefaultChar], rbx
0x18000603c  lea     r12, aSetuprecoveryt_21; "SetupRecoveryTaskHandler::InternalCallP"...
0x180006043  mov     [rsp+548h+lpDefaultChar], r12
0x180006048  lea     r13, aBaseDiagnosisS; "base\\diagnosis\\srt\\setuprecoverydata"...
0x18000604f  mov     [rsp+548h+lpcbData], r13
0x180006054  mov     dword ptr [rsp+548h+phkResult], 0BDh
0x18000605c  lea     r15, aD; "D"
0x180006063  xor     r9d, r9d
0x180006066  mov     r8, r15
0x180006069  xor     edx, edx
0x18000606b  mov     rcx, rax
0x18000606e  call    cs:__imp_WdsSetupLogMessageW
0x180006074  jmp     loc_1800067FC
0x180006079  mov     r8, r15
0x18000607c  lea     rdx, aSetuprecoveryt_15; "SetupRecoveryTaskHandler::InternalCallP"...
0x180006083  mov     ecx, 4000000h; unsigned int
0x180006088  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18000608d  mov     [rsp+548h+var_4F8], r14d
0x180006092  mov     [rsp+548h+var_500], r14
0x180006097  mov     [rsp+548h+var_508], edi
0x18000609b  mov     [rsp+548h+lpUsedDefaultChar], rbx
0x1800060a0  lea     r12, aSetuprecoveryt_21; "SetupRecoveryTaskHandler::InternalCallP"...
0x1800060a7  mov     [rsp+548h+lpDefaultChar], r12
0x1800060ac  lea     r13, aBaseDiagnosisS; "base\\diagnosis\\srt\\setuprecoverydata"...
0x1800060b3  mov     [rsp+548h+lpcbData], r13
0x1800060b8  mov     dword ptr [rsp+548h+phkResult], 0C2h
0x1800060c0  xor     r9d, r9d
0x1800060c3  lea     r15, aD; "D"
0x1800060ca  mov     r8, r15
0x1800060cd  xor     edx, edx
0x1800060cf  mov     rcx, rax
0x1800060d2  call    cs:__imp_WdsSetupLogMessageW
0x1800060d8  lea     rax, [rsp+548h+cbData]
0x1800060e0  mov     [rsp+548h+lpcbData], rax; lpcbData
0x1800060e5  lea     rax, [rsp+548h+Data]
0x1800060ed  mov     [rsp+548h+phkResult], rax; lpData
0x1800060f2  xor     r9d, r9d; lpType
0x1800060f5  xor     r8d, r8d; lpReserved
0x1800060f8  lea     rdx, aBinarylocation; "BinaryLocation"
0x1800060ff  mov     rcx, [rsp+548h+hKey]; hKey
0x180006107  call    cs:__imp_RegQueryValueExW
0x18000610d  mov     esi, eax
0x18000610f  test    eax, eax
0x180006111  jle     short loc_18000611C
0x180006113  movzx   esi, ax
0x180006116  or      esi, 80070000h
0x18000611c  call    cs:__imp_GetLastError
0x180006122  mov     edi, eax
0x180006124  call    cs:__imp_CurrentIP
0x18000612a  mov     rbx, rax
0x18000612d  test    esi, esi
0x18000612f  jns     short loc_18000616F
0x180006131  mov     r8d, esi
0x180006134  lea     rdx, aSetuprecoveryt_23; "SetupRecoveryTaskHandler::InternalCallP"...
0x18000613b  mov     ecx, 2000000h; unsigned int
0x180006140  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180006145  mov     [rsp+548h+var_4F8], r14d
0x18000614a  mov     [rsp+548h+var_500], r14
0x18000614f  mov     [rsp+548h+var_508], edi
0x180006153  mov     [rsp+548h+lpUsedDefaultChar], rbx
0x180006158  mov     [rsp+548h+lpDefaultChar], r12
0x18000615d  mov     [rsp+548h+lpcbData], r13
0x180006162  mov     dword ptr [rsp+548h+phkResult], 0C9h
0x18000616a  jmp     loc_180006063
0x18000616f  lea     r9, [rsp+548h+Data]
0x180006177  lea     r8, aBinarylocation; "BinaryLocation"
0x18000617e  lea     rdx, aSetuprecoveryt_10; "SetupRecoveryTaskHandler::InternalCallP"...
0x180006185  mov     esi, 4000000h
0x18000618a  mov     ecx, esi; unsigned int
0x18000618c  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180006191  mov     [rsp+548h+var_4F8], r14d
0x180006196  mov     [rsp+548h+var_500], r14
0x18000619b  mov     [rsp+548h+var_508], edi
0x18000619f  mov     [rsp+548h+lpUsedDefaultChar], rbx
0x1800061a4  mov     [rsp+548h+lpDefaultChar], r12
0x1800061a9  mov     [rsp+548h+lpcbData], r13
0x1800061ae  mov     dword ptr [rsp+548h+phkResult], 0CEh
0x1800061b6  xor     r9d, r9d
0x1800061b9  mov     r8, r15
0x1800061bc  xor     edx, edx
0x1800061be  mov     rcx, rax
0x1800061c1  call    cs:__imp_WdsSetupLogMessageW
0x1800061c7  call    cs:__imp_GetLastError
0x1800061cd  mov     edi, eax
0x1800061cf  call    cs:__imp_CurrentIP
0x1800061d5  mov     rbx, rax
0x1800061d8  lea     rdx, aSetuprecoveryt_24; "SetupRecoveryTaskHandler::InternalCallP"...
0x1800061df  mov     ecx, esi; unsigned int
0x1800061e1  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x1800061e6  mov     [rsp+548h+var_4F8], r14d
0x1800061eb  mov     [rsp+548h+var_500], r14
0x1800061f0  mov     [rsp+548h+var_508], edi
0x1800061f4  mov     [rsp+548h+lpUsedDefaultChar], rbx
0x1800061f9  mov     [rsp+548h+lpDefaultChar], r12
0x1800061fe  mov     [rsp+548h+lpcbData], r13
0x180006203  mov     dword ptr [rsp+548h+phkResult], 0D2h
0x18000620b  xor     r9d, r9d
0x18000620e  mov     r8, r15
0x180006211  xor     edx, edx
0x180006213  mov     rcx, rax
0x180006216  call    cs:__imp_WdsSetupLogMessageW
0x18000621c  lea     rdx, [rsp+548h+Data]
0x180006224  lea     rcx, [rsp+548h+var_498]
0x18000622c  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x180006232  nop
0x180006233  mov     rcx, rax
0x180006236  call    cs:__imp_?ExpandEnvironmentVariables@Environment@UnBCL@@SAPEAVString@2@PEBV32@@Z; UnBCL::Environment::ExpandEnvironmentVariables(UnBCL::String const *)
0x18000623c  mov     rdx, rax
0x18000623f  lea     rcx, [rsp+548h+var_4C8]
0x180006247  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x18000624d  nop
0x18000624e  lea     rdx, [rsp+548h+var_4C8]
0x180006256  lea     rcx, [rsp+548h+var_470]
0x18000625e  call    cs:__imp_??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z; UnBCL::SmartPtr<UnBCL::String>::operator=(UnBCL::SmartPtr<UnBCL::String> const &)
0x180006264  nop
0x180006265  lea     rcx, [rsp+548h+var_4C8]
0x18000626d  call    cs:__imp_??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(void)
0x180006273  nop
0x180006274  lea     rcx, [rsp+548h+var_498]
0x18000627c  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x180006282  lea     rax, [rsp+548h+cbData]
0x18000628a  mov     [rsp+548h+lpcbData], rax; lpcbData
0x18000628f  lea     rax, [rsp+548h+var_458]
0x180006297  mov     [rsp+548h+phkResult], rax; lpData
0x18000629c  xor     r9d, r9d; lpType
0x18000629f  xor     r8d, r8d; lpReserved
0x1800062a2  lea     rdx, aEntrypoint; "EntryPoint"
0x1800062a9  mov     rcx, [rsp+548h+hKey]; hKey
0x1800062b1  call    cs:__imp_RegQueryValueExW
0x1800062b7  mov     esi, eax
0x1800062b9  test    eax, eax
0x1800062bb  jle     short loc_1800062C6
0x1800062bd  movzx   esi, ax
0x1800062c0  or      esi, 80070000h
0x1800062c6  mov     [rsp+548h+var_4E8], esi
0x1800062ca  call    cs:__imp_GetLastError
0x1800062d0  mov     edi, eax
0x1800062d2  call    cs:__imp_CurrentIP
0x1800062d8  mov     rbx, rax
0x1800062db  test    esi, esi
0x1800062dd  jns     short loc_18000631D
0x1800062df  mov     r8d, esi
0x1800062e2  lea     rdx, aSetuprecoveryt_0; "SetupRecoveryTaskHandler::InternalCallP"...
0x1800062e9  mov     ecx, 2000000h; unsigned int
0x1800062ee  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x1800062f3  mov     [rsp+548h+var_4F8], r14d
0x1800062f8  mov     [rsp+548h+var_500], r14
0x1800062fd  mov     [rsp+548h+var_508], edi
0x180006301  mov     [rsp+548h+lpUsedDefaultChar], rbx
0x180006306  mov     [rsp+548h+lpDefaultChar], r12
0x18000630b  mov     [rsp+548h+lpcbData], r13
0x180006310  mov     dword ptr [rsp+548h+phkResult], 0D9h
0x180006318  jmp     loc_180006063
0x18000631d  lea     r9, [rsp+548h+var_458]
0x180006325  lea     r8, aEntrypoint; "EntryPoint"
0x18000632c  lea     rdx, aSetuprecoveryt_10; "SetupRecoveryTaskHandler::InternalCallP"...
0x180006333  mov     esi, 4000000h
0x180006338  mov     ecx, esi; unsigned int
0x18000633a  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18000633f  mov     [rsp+548h+var_4F8], r14d
0x180006344  mov     [rsp+548h+var_500], r14
0x180006349  mov     [rsp+548h+var_508], edi
0x18000634d  mov     [rsp+548h+lpUsedDefaultChar], rbx
0x180006352  mov     [rsp+548h+lpDefaultChar], r12
0x180006357  mov     [rsp+548h+lpcbData], r13
0x18000635c  mov     dword ptr [rsp+548h+phkResult], 0DEh
0x180006364  xor     r9d, r9d
0x180006367  mov     r8, r15
0x18000636a  xor     edx, edx
0x18000636c  mov     rcx, rax
0x18000636f  call    cs:__imp_WdsSetupLogMessageW
0x180006375  lea     rcx, [rsp+548h+var_470]
0x18000637d  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x180006383  mov     rcx, rax
0x180006386  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x18000638c  mov     rcx, rax; lpLibFileName
0x18000638f  xor     edx, edx; hFile
0x180006391  lea     r8d, [rdx+8]; dwFlags
0x180006395  call    cs:__imp_LoadLibraryExW
0x18000639b  mov     [rsp+548h+hModule], rax
0x1800063a0  mov     [rsp+548h+var_4B0], rax
0x1800063a8  test    rax, rax
0x1800063ab  jnz     short loc_180006411
0x1800063ad  call    cs:__imp_GetLastError
0x1800063b3  mov     esi, eax
0x1800063b5  test    eax, eax
0x1800063b7  jle     short loc_1800063C2
0x1800063b9  movzx   esi, ax
0x1800063bc  or      esi, 80070000h
0x1800063c2  call    cs:__imp_GetLastError
0x1800063c8  mov     edi, eax
0x1800063ca  call    cs:__imp_CurrentIP
0x1800063d0  mov     rbx, rax
0x1800063d3  mov     r8d, esi
0x1800063d6  lea     rdx, aSetuprecoveryt_14; "SetupRecoveryTaskHandler::InternalCallP"...
0x1800063dd  mov     ecx, 2000000h; unsigned int
0x1800063e2  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x1800063e7  mov     [rsp+548h+var_4F8], r14d
0x1800063ec  mov     [rsp+548h+var_500], r14
0x1800063f1  mov     [rsp+548h+var_508], edi
0x1800063f5  mov     [rsp+548h+lpUsedDefaultChar], rbx
0x1800063fa  mov     [rsp+548h+lpDefaultChar], r12
0x1800063ff  mov     [rsp+548h+lpcbData], r13
0x180006404  mov     dword ptr [rsp+548h+phkResult], 0E6h
0x18000640c  jmp     loc_180006063
0x180006411  call    cs:__imp_GetLastError
0x180006417  mov     edi, eax
0x180006419  call    cs:__imp_CurrentIP
0x18000641f  mov     rbx, rax
0x180006422  lea     rdx, aSetuprecoveryt_17; "SetupRecoveryTaskHandler::InternalCallP"...
0x180006429  mov     ecx, esi; unsigned int
0x18000642b  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180006430  mov     [rsp+548h+var_4F8], r14d
0x180006435  mov     [rsp+548h+var_500], r14
0x18000643a  mov     [rsp+548h+var_508], edi
0x18000643e  mov     [rsp+548h+lpUsedDefaultChar], rbx
0x180006443  mov     [rsp+548h+lpDefaultChar], r12
0x180006448  mov     [rsp+548h+lpcbData], r13
0x18000644d  mov     dword ptr [rsp+548h+phkResult], 0EBh
0x180006455  xor     r9d, r9d
0x180006458  mov     r8, r15
0x18000645b  xor     edx, edx
0x18000645d  mov     rcx, rax
0x180006460  call    cs:__imp_WdsSetupLogMessageW
0x180006466  mov     [rsp+548h+lpUsedDefaultChar], r14; lpUsedDefaultChar
0x18000646b  mov     [rsp+548h+lpDefaultChar], r14; lpDefaultChar
0x180006470  mov     dword ptr [rsp+548h+lpcbData], r14d; cbMultiByte
0x180006475  mov     [rsp+548h+phkResult], r14; lpMultiByteStr
0x18000647a  or      r9d, 0FFFFFFFFh; cchWideChar
0x18000647e  lea     r8, [rsp+548h+var_458]; lpWideCharStr
0x180006486  xor     edx, edx; dwFlags
0x180006488  mov     ecx, 0FDE9h; CodePage
0x18000648d  call    cs:__imp_WideCharToMultiByte
0x180006493  movsxd  rdi, eax
0x180006496  test    eax, eax
0x180006498  jnz     short loc_1800064FE
0x18000649a  call    cs:__imp_GetLastError
0x1800064a0  mov     esi, eax
0x1800064a2  test    eax, eax
0x1800064a4  jle     short loc_1800064AF
0x1800064a6  movzx   esi, ax
0x1800064a9  or      esi, 80070000h
0x1800064af  call    cs:__imp_GetLastError
0x1800064b5  mov     edi, eax
0x1800064b7  call    cs:__imp_CurrentIP
0x1800064bd  mov     rbx, rax
0x1800064c0  mov     r8d, esi
0x1800064c3  lea     rdx, aSetuprecoveryt_12; "SetupRecoveryTaskHandler::InternalCallP"...
0x1800064ca  mov     ecx, 2000000h; unsigned int
0x1800064cf  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
  ... truncated ...
```
