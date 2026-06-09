# PrepareRestoreJournal(UnBCL::String *,UnBCL::String *,__int64,int,int,void *,PITR::IPITRRestoreProgress *,ulong *)

- ea: `0x18002a6fc`
- end: `0x18002bf69`
- name: `?PrepareRestoreJournal@@YAJPEAVString@UnBCL@@0_JHHPEAXPEAUIPITRRestoreProgress@PITR@@PEAK@Z`
- size: `6253`
- prototype: `__int64 __fastcall(struct UnBCL::String *, struct UnBCL::String *, VSS_TIMESTAMP, int, int, void *, struct PITR::IPITRRestoreProgress *, unsigned int *)`
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800170f0`

## callees

- `0x18000448c`
- `0x180009e04`
- `0x18000b070`
- `0x18001de74`
- `0x18002523c`
- `0x18002a6fc`
- `0x18002edec`
- `0x18003275c`
- `0x180032ae4`
- `0x180033ba4`
- `0x1800386cc`
- `0x180038df0`
- `0x180039424`
- `0x1800502c2`
- `0x180050300`
- `0x180053010`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetDiskFreeSpaceW` at `0x18002b09a`
- `api-ms-win-core-file-l1-1-0!GetDiskFreeSpaceW` at `0x18002b09a`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002b42f`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002b42f`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18002b20a`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18002b20a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002a906`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002a92e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002a974`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002a997`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002ad64`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002adae`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002bdb7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002bdd5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002bdf8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002be23`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002be4e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002be79`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002bea4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002a906`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002a92e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002a974`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002a997`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002ad64`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002adae`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002bdb7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002bdd5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002bdf8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002be23`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002be4e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002be79`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002bea4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002a919`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002a93c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002a982`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002a9a5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002ad74`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002a919`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002a93c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002a982`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002a9a5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002ad74`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002adbc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002bdc5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002bde8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002be0b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002be36`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002be61`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002be8c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002beb7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002adbc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002bdc5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002bde8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002be0b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002be36`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002be61`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002be8c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002beb7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002aa89`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ac06`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ae00`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002aea7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002af16`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002afdf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b0a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b0be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b0de`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b218`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b22e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b24e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b447`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b45d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b48c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b629`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b6dd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b74f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b7e4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b8d7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b968`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b9c2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002bb1f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002bbc1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002bc5c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002bcb6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002bd0c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002aa89`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ac06`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ae00`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002aea7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002af16`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002afdf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b0a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b0be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b0de`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b218`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b22e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b24e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b447`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b45d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b48c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b629`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b6dd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b74f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b7e4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b8d7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b968`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b9c2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002bb1f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002bbc1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002bc5c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002bcb6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002bd0c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002bb92`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002bd94`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002bb92`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002bd94`
- `WDSCORE!CurrentIP` at `0x18002aa91`
- `WDSCORE!CurrentIP` at `0x18002ac0e`
- `WDSCORE!CurrentIP` at `0x18002ae08`
- `WDSCORE!CurrentIP` at `0x18002aeaf`
- `WDSCORE!CurrentIP` at `0x18002af1e`
- `WDSCORE!CurrentIP` at `0x18002afe7`
- `WDSCORE!CurrentIP` at `0x18002b0e6`
- `WDSCORE!CurrentIP` at `0x18002b256`
- `WDSCORE!CurrentIP` at `0x18002b494`
- `WDSCORE!CurrentIP` at `0x18002b631`
- `WDSCORE!CurrentIP` at `0x18002b6e5`
- `WDSCORE!CurrentIP` at `0x18002b757`
- `WDSCORE!CurrentIP` at `0x18002b7ec`
- `WDSCORE!CurrentIP` at `0x18002b8df`
- `WDSCORE!CurrentIP` at `0x18002b970`
- `WDSCORE!CurrentIP` at `0x18002b9ca`
- `WDSCORE!CurrentIP` at `0x18002bb27`
- `WDSCORE!CurrentIP` at `0x18002bbc9`
- `WDSCORE!CurrentIP` at `0x18002bc64`
- `WDSCORE!CurrentIP` at `0x18002bcbe`
- `WDSCORE!CurrentIP` at `0x18002bd14`
- `WDSCORE!CurrentIP` at `0x18002aa91`
- `WDSCORE!CurrentIP` at `0x18002ac0e`
- `WDSCORE!CurrentIP` at `0x18002ae08`
- `WDSCORE!CurrentIP` at `0x18002aeaf`
- `WDSCORE!CurrentIP` at `0x18002af1e`
- `WDSCORE!CurrentIP` at `0x18002afe7`
- `WDSCORE!CurrentIP` at `0x18002b0e6`
- `WDSCORE!CurrentIP` at `0x18002b256`
- `WDSCORE!CurrentIP` at `0x18002b494`
- `WDSCORE!CurrentIP` at `0x18002b631`
- `WDSCORE!CurrentIP` at `0x18002b6e5`
- `WDSCORE!CurrentIP` at `0x18002b757`
- `WDSCORE!CurrentIP` at `0x18002b7ec`
- `WDSCORE!CurrentIP` at `0x18002b8df`
- `WDSCORE!CurrentIP` at `0x18002b970`
- `WDSCORE!CurrentIP` at `0x18002b9ca`
- `WDSCORE!CurrentIP` at `0x18002bb27`
- `WDSCORE!CurrentIP` at `0x18002bbc9`
- `WDSCORE!CurrentIP` at `0x18002bc64`
- `WDSCORE!CurrentIP` at `0x18002bcbe`
- `WDSCORE!CurrentIP` at `0x18002bd14`
- `WDSCORE!WdsSetupLogMessageW` at `0x18002aaef`
- `WDSCORE!WdsSetupLogMessageW` at `0x18002ac9a`
- `WDSCORE!WdsSetupLogMessageW` at `0x18002ae7f`
- `WDSCORE!WdsSetupLogMessageW` at `0x18002b143`
- `WDSCORE!WdsSetupLogMessageW` at `0x18002b67a`
- `WDSCORE!WdsSetupLogMessageW` at `0x18002b7a5`
- `WDSCORE!WdsSetupLogMessageW` at `0x18002b835`
- `WDSCORE!WdsSetupLogMessageW` at `0x18002b9bc`
- `WDSCORE!WdsSetupLogMessageW` at `0x18002ba13`
- `WDSCORE!WdsSetupLogMessageW` at `0x18002bc1a`
- `WDSCORE!WdsSetupLogMessageW` at `0x18002bd6f`
- `WDSCORE!WdsSetupLogMessageW` at `0x18002aaef`
- `WDSCORE!WdsSetupLogMessageW` at `0x18002ac9a`
- `WDSCORE!WdsSetupLogMessageW` at `0x18002ae7f`
- `WDSCORE!WdsSetupLogMessageW` at `0x18002b143`
- `WDSCORE!WdsSetupLogMessageW` at `0x18002b67a`
- `WDSCORE!WdsSetupLogMessageW` at `0x18002b7a5`
- `WDSCORE!WdsSetupLogMessageW` at `0x18002b835`
- `WDSCORE!WdsSetupLogMessageW` at `0x18002b9bc`
- `WDSCORE!WdsSetupLogMessageW` at `0x18002ba13`
- `WDSCORE!WdsSetupLogMessageW` at `0x18002bc1a`
- `WDSCORE!WdsSetupLogMessageW` at `0x18002bd6f`
- `unbcl!?get_P@?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@2@XZ` at `0x18002aa74`
- `unbcl!?get_P@?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@2@XZ` at `0x18002aa74`
- `unbcl!?GetEnvironmentVar@Environment@UnBCL@@SAPEAVString@2@PEBV32@@Z` at `0x18002b50d`
- `unbcl!?GetEnvironmentVar@Environment@UnBCL@@SAPEAVString@2@PEBV32@@Z` at `0x18002b50d`
- `unbcl!??0?$ArrayList@PEAVString@UnBCL@@@UnBCL@@QEAA@XZ` at `0x18002aa00`
- `unbcl!??0?$ArrayList@PEAVString@UnBCL@@@UnBCL@@QEAA@XZ` at `0x18002aa00`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x18002a9e3`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x18002aba8`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x18002aca5`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x18002a9e3`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x18002aba8`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x18002aca5`
- `unbcl!?AddRef@Object@UnBCL@@QEAAXXZ` at `0x18002a895`
- `unbcl!?AddRef@Object@UnBCL@@QEAAXXZ` at `0x18002a895`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18002abc9`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18002acc6`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18002b176`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18002b2ab`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18002b38c`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18002b503`

## string_xrefs

- `0x18002b262`: `Error creating the store directory: 0x%08X`
- `0x18002aacc`: `base\diagnosis\srt\pitr\dll\src\restore.cpp`
- `0x18002ac7b`: `base\diagnosis\srt\pitr\dll\src\restore.cpp`
- `0x18002ae60`: `base\diagnosis\srt\pitr\dll\src\restore.cpp`
- `0x18002aefd`: `base\diagnosis\srt\pitr\dll\src\restore.cpp`
- `0x18002af8c`: `base\diagnosis\srt\pitr\dll\src\restore.cpp`
- `0x18002b02e`: `base\diagnosis\srt\pitr\dll\src\restore.cpp`
- `0x18002b05a`: `base\diagnosis\srt\pitr\dll\src\restore.cpp`
- `0x18002bc9d`: `base\diagnosis\srt\pitr\dll\src\restore.cpp`
- `0x18002bcf6`: `base\diagnosis\srt\pitr\dll\src\restore.cpp`
- `0x18002bd4c`: `base\diagnosis\srt\pitr\dll\src\restore.cpp`
- `0x18002b4ba`: `Failed to create journal file %s, error: 0x%08X`
- `0x18002b4f4`: `PITR_CONFIG_ENV_PATH_OVERRIDE`
- `0x18002bb33`: `Failed to create restore journal for snapshot restoration. Error: 0x%08X\n`
- `0x18002bbda`: `THOROUGH: Found %d false positive content comparisons`
- `0x18002bc75`: `THOROUGH: Found %d false positive content comparisons`

## pseudocode

```c
// Hidden C++ exception states: #wind=30
__int64 __fastcall PrepareRestoreJournal(
        struct UnBCL::String *a1,
        struct UnBCL::String *a2,
        VSS_TIMESTAMP a3,
        int a4,
        int a5,
        void *a6,
        struct PITR::IPITRRestoreProgress *a7,
        unsigned int *a8)
{
  unsigned __int8 *v10; // r15
  __int64 v11; // rax
  __int64 v12; // rbx
  HANDLE ProcessHeap; // rax
  unsigned int v14; // ebx
  HANDLE v15; // rax
  void *v16; // rax
  HANDLE v17; // rax
  unsigned int v18; // ebx
  HANDLE v19; // rax
  void *v20; // rax
  _QWORD *v21; // rax
  _QWORD *v22; // rbx
  __int64 v23; // rax
  __int64 P; // rax
  int SnapshotProp; // r14d
  DWORD v26; // edi
  __int64 v27; // rbx
  struct tagLOG_PARTIAL_MSG *v28; // rax
  int i; // ebx
  __int64 v30; // rax
  int (__fastcall ***v31)(_QWORD); // rcx
  __int64 v32; // rax
  __int64 v33; // rcx
  struct UnBCL::String **v34; // rax
  UnBCL::String *v35; // rax
  UnBCL::String *v36; // rbx
  DWORD v37; // edi
  __int64 v38; // rbx
  __int64 v39; // rax
  __int64 v40; // rcx
  UnBCL::String **v41; // rax
  const char *v42; // rax
  struct tagLOG_PARTIAL_MSG *v43; // rax
  UnBCL::String *v44; // rax
  UnBCL::String *v45; // rbx
  struct UnBCL::String *v46; // rax
  unsigned int v47; // eax
  unsigned int v48; // r8d
  unsigned int v49; // ebx
  HANDLE v50; // rax
  unsigned int v51; // r9d
  _BYTE *j; // rbx
  HANDLE v53; // rax
  DWORD v54; // edi
  __int64 v55; // rbx
  UnBCL::String *v56; // rax
  const char *v57; // rax
  struct tagLOG_PARTIAL_MSG *v58; // rax
  DWORD v59; // edi
  __int64 v60; // rbx
  UnBCL::String *v61; // rax
  const char *v62; // rax
  DWORD v63; // edi
  __int64 v64; // rbx
  __int64 v65; // rax
  __int64 v66; // r9
  UnBCL::String **v67; // rax
  const char *CString; // rax
  DWORD v69; // edi
  __int64 v70; // rbx
  const char *v71; // rax
  const struct UnBCL::String *v72; // rbx
  const WCHAR *v73; // rax
  signed int v74; // eax
  bool v75; // sf
  signed int v76; // eax
  DWORD v77; // edi
  __int64 v78; // rbx
  const char *v79; // rax
  struct tagLOG_PARTIAL_MSG *v80; // rax
  const struct UnBCL::String *v81; // rax
  struct UnBCL::String *v82; // rax
  const struct UnBCL::String *v83; // rax
  UnBCL::String *v84; // rax
  const WCHAR *v85; // rax
  signed int v86; // eax
  bool v87; // sf
  signed int v88; // eax
  DWORD v89; // edi
  __int64 v90; // rbx
  struct tagLOG_PARTIAL_MSG *v91; // rax
  const struct UnBCL::String *v92; // rbx
  const struct UnBCL::String *v93; // rax
  struct UnBCL::String *v94; // rax
  const struct UnBCL::String *v95; // rax
  const struct UnBCL::String *v96; // rax
  struct UnBCL::FileStream *v97; // rax
  const struct UnBCL::String *v98; // rbx
  const struct UnBCL::String *v99; // rax
  struct UnBCL::String *v100; // rax
  UnBCL::String *v101; // rax
  const WCHAR *v102; // rax
  signed int v103; // eax
  bool v104; // sf
  signed int v105; // eax
  DWORD v106; // edi
  __int64 v107; // rbx
  UnBCL::String *v108; // rax
  const char *v109; // rax
  struct tagLOG_PARTIAL_MSG *v110; // rax
  const struct UnBCL::String *v111; // rax
  struct UnBCL::String *EnvironmentVar; // rax
  const struct UnBCL::String *v113; // rax
  int v114; // r14d
  struct UnBCL::String *v115; // rax
  const struct UnBCL::String *v116; // rax
  struct UnBCL::String *v117; // rax
  DWORD v118; // edi
  __int64 v119; // rbx
  struct tagLOG_PARTIAL_MSG *v120; // rax
  int v121; // eax
  DWORD v122; // edi
  __int64 v123; // rbx
  struct tagLOG_PARTIAL_MSG *v124; // rax
  bool v125; // zf
  int v126; // eax
  DWORD v127; // edi
  __int64 v128; // rbx
  struct tagLOG_PARTIAL_MSG *v129; // rax
  DWORD v130; // edi
  __int64 v131; // rbx
  struct tagLOG_PARTIAL_MSG *v132; // rax
  int v133; // eax
  DWORD v134; // edi
  __int64 v135; // rbx
  struct tagLOG_PARTIAL_MSG *v136; // rax
  char IsEnabled; // al
  unsigned int v138; // r14d
  DWORD v139; // edi
  __int64 v140; // rbx
  struct tagLOG_PARTIAL_MSG *v141; // rax
  DWORD v142; // edi
  __int64 v143; // rbx
  struct tagLOG_PARTIAL_MSG *v144; // rax
  const struct UnBCL::String *v145; // rdi
  UnBCL::String *v146; // rbx
  __int64 v147; // rdx
  struct UnBCL::String *v148; // rax
  DWORD v149; // edi
  __int64 v150; // rbx
  struct tagLOG_PARTIAL_MSG *v151; // rax
  DWORD v152; // edi
  __int64 v153; // rbx
  struct tagLOG_PARTIAL_MSG *v154; // rax
  DWORD v155; // edi
  __int64 v156; // rbx
  struct tagLOG_PARTIAL_MSG *v157; // rax
  DWORD v158; // edi
  __int64 v159; // rbx
  struct tagLOG_PARTIAL_MSG *v160; // rax
  DWORD LastError; // edi
  __int64 v162; // rbx
  HANDLE v163; // rax
  HANDLE v164; // rax
  HANDLE v165; // rax
  HANDLE v166; // rax
  HANDLE v167; // rax
  HANDLE v168; // rax
  HANDLE v169; // rax
  void (__fastcall ***v171)(_QWORD, __int64); // rsi
  __int64 v172; // rax
  DWORD v173; // edi
  __int64 v174; // rbx
  UnBCL::String *v175; // rax
  const char *v176; // rax
  struct tagLOG_PARTIAL_MSG *v177; // rax
  int lpTotalNumberOfClusters; // [rsp+20h] [rbp-2F8h]
  int lpTotalNumberOfClustersa; // [rsp+20h] [rbp-2F8h]
  int lpTotalNumberOfClustersb; // [rsp+20h] [rbp-2F8h]
  __int64 v181; // [rsp+38h] [rbp-2E0h]
  __int64 v182; // [rsp+38h] [rbp-2E0h]
  __int64 v183; // [rsp+38h] [rbp-2E0h]
  DWORD v184; // [rsp+40h] [rbp-2D8h]
  DWORD v185; // [rsp+40h] [rbp-2D8h]
  DWORD v186; // [rsp+40h] [rbp-2D8h]
  int v187; // [rsp+48h] [rbp-2D0h]
  unsigned int v188; // [rsp+60h] [rbp-2B8h] BYREF
  void *v189; // [rsp+68h] [rbp-2B0h]
  unsigned int v190; // [rsp+70h] [rbp-2A8h] BYREF
  unsigned int v191; // [rsp+74h] [rbp-2A4h]
  int v192; // [rsp+78h] [rbp-2A0h] BYREF
  LPVOID lpMem; // [rsp+80h] [rbp-298h] BYREF
  UnBCL::String *v194; // [rsp+88h] [rbp-290h]
  struct UnBCL::String *v195; // [rsp+90h] [rbp-288h]
  __int64 v196; // [rsp+98h] [rbp-280h]
  int v197; // [rsp+A0h] [rbp-278h]
  void **v198; // [rsp+A8h] [rbp-270h] BYREF
  __int64 v199; // [rsp+B0h] [rbp-268h]
  _BYTE v200[24]; // [rsp+B8h] [rbp-260h] BYREF
  void *v201; // [rsp+D0h] [rbp-248h]
  struct PITR::IPITRRestoreProgress *v202; // [rsp+D8h] [rbp-240h]
  unsigned int *v203; // [rsp+E0h] [rbp-238h]
  VSS_TIMESTAMP v204; // [rsp+E8h] [rbp-230h]
  UnBCL::String *v205; // [rsp+F0h] [rbp-228h]
  UnBCL::String *v206; // [rsp+F8h] [rbp-220h]
  void (__fastcall ***v207)(_QWORD, __int64); // [rsp+100h] [rbp-218h] BYREF
  int v208; // [rsp+110h] [rbp-208h] BYREF
  unsigned int v209; // [rsp+114h] [rbp-204h]
  int v210; // [rsp+118h] [rbp-200h]
  LPVOID v211; // [rsp+120h] [rbp-1F8h]
  int v212; // [rsp+128h] [rbp-1F0h]
  LPVOID v213; // [rsp+130h] [rbp-1E8h]
  int v214; // [rsp+138h] [rbp-1E0h]
  LPVOID v215; // [rsp+140h] [rbp-1D8h]
  SIZE_T dwBytes; // [rsp+148h] [rbp-1D0h]
  LPVOID v217; // [rsp+150h] [rbp-1C8h]
  SIZE_T v218; // [rsp+158h] [rbp-1C0h]
  unsigned __int8 *v219; // [rsp+160h] [rbp-1B8h] BYREF
  unsigned int v220[2]; // [rsp+168h] [rbp-1B0h] BYREF
  HANDLE hObject; // [rsp+170h] [rbp-1A8h]
  void *v222; // [rsp+178h] [rbp-1A0h]
  struct PITR::IPITRRestoreProgress *v223; // [rsp+180h] [rbp-198h]
  __int128 v224; // [rsp+190h] [rbp-188h] BYREF
  struct PITR::IPITRRestoreProgress *v225; // [rsp+1A0h] [rbp-178h]
  struct _VSS_SNAPSHOT_PROP v226; // [rsp+1B0h] [rbp-168h] BYREF
  _QWORD v227[2]; // [rsp+230h] [rbp-E8h] BYREF
  void **v228; // [rsp+240h] [rbp-D8h] BYREF
  __int64 v229; // [rsp+248h] [rbp-D0h]
  DWORD BytesPerSector; // [rsp+250h] [rbp-C8h] BYREF
  DWORD SectorsPerCluster; // [rsp+254h] [rbp-C4h] BYREF
  unsigned int v232; // [rsp+258h] [rbp-C0h] BYREF
  _BYTE v233[16]; // [rsp+260h] [rbp-B8h] BYREF
  _BYTE v234[16]; // [rsp+270h] [rbp-A8h] BYREF
  DWORD NumberOfFreeClusters; // [rsp+280h] [rbp-98h] BYREF
  DWORD TotalNumberOfClusters; // [rsp+284h] [rbp-94h] BYREF
  _BYTE v237[16]; // [rsp+288h] [rbp-90h] BYREF
  _BYTE v238[16]; // [rsp+298h] [rbp-80h] BYREF
  _BYTE v239[16]; // [rsp+2A8h] [rbp-70h] BYREF
  _BYTE v240[16]; // [rsp+2B8h] [rbp-60h] BYREF
  _BYTE v241[16]; // [rsp+2C8h] [rbp-50h] BYREF

  v197 = a4;
  v204 = a3;
  v194 = a2;
  v195 = a1;
  v201 = a6;
  v202 = a7;
  v203 = a8;
  v224 = 0;
  v225 = 0;
  memset_0(&v208, 0, 0x78u);
  SectorsPerCluster = 0;
  BytesPerSector = 0;
  NumberOfFreeClusters = 0;
  TotalNumberOfClusters = 0;
  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v238);
  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v241);
  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v240);
  v198 = &UnBCL::SmartPtr<UnBCL::Hashtable<UnBCL::String *,unsigned long>>::`vftable';
  v199 = 0;
  v192 = 0;
  v188 = 0;
  v232 = 0;
  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v237);
  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v234);
  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v239);
  UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>(v233);
  v10 = 0;
  lpMem = 0;
  v190 = 0;
  v11 = pBuildExclusionData();
  UnBCL::SmartPtr<UnBCL::Hashtable<UnBCL::String *,unsigned long>>::SmartPtr<UnBCL::Hashtable<UnBCL::String *,unsigned long>>(
    &v228,
    v11);
  v12 = v229;
  v196 = v229;
  if ( v229 )
    UnBCL::Object::AddRef((UnBCL::Object *)(v229 + *(int *)(*(_QWORD *)(v229 + 8) + 4LL) + 8LL));
  UnBCL::SmartPtr<UnBCL::IEnumerator<unsigned long>>::DeAssign((__int64)&v198);
  v199 = v12;
  v228 = &UnBCL::SmartPtr<UnBCL::Hashtable<UnBCL::String *,unsigned long>>::`vftable';
  UnBCL::SmartPtr<UnBCL::IEnumerator<unsigned long>>::DeAssign((__int64)&v228);
  v208 = a4;
  v210 = a5;
  v222 = a6;
  v223 = a7;
  LODWORD(dwBytes) = 1032224;
  v212 = 1032224;
  ProcessHeap = GetProcessHeap();
  v211 = HeapAlloc(ProcessHeap, 8u, 0xFC020u);
  v14 = dwBytes;
  v15 = GetProcessHeap();
  v16 = HeapAlloc(v15, 8u, v14);
  v215 = v16;
  if ( !v211 || !v16 )
  {
    LastError = GetLastError();
    v162 = CurrentIP();
    v160 = ConstructPartialMsgW(0x2000000, "Out-of-memory (1) while processing the snapshot");
    v186 = LastError;
    v183 = v162;
    lpTotalNumberOfClustersb = 2477;
    goto LABEL_114;
  }
  LODWORD(v218) = 4096;
  v214 = 4096;
  v17 = GetProcessHeap();
  v213 = HeapAlloc(v17, 8u, 0x1000u);
  v18 = v218;
  v19 = GetProcessHeap();
  v20 = HeapAlloc(v19, 8u, v18);
  v217 = v20;
  if ( !v213 || !v20 )
  {
    v158 = GetLastError();
    v159 = CurrentIP();
    v160 = ConstructPartialMsgW(0x2000000, "Out-of-memory (2) while processing the snapshot");
    v186 = v158;
    v183 = v159;
    lpTotalNumberOfClustersb = 2488;
LABEL_114:
    WdsSetupLogMessageW(
      v160,
      0,
      L"D",
      0,
      lpTotalNumberOfClustersb,
      L"base\\diagnosis\\srt\\pitr\\dll\\src\\restore.cpp",
      L"PrepareRestoreJournal",
      v183,
      v186,
      0,
      0);
    SnapshotProp = -2147024888;
    goto LABEL_115;
  }
  if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PITR_FastCompare>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_Servicing_PITR_FastCompare>::GetImpl'::`2'::impl) )
  {
    v21 = UnBCL::Object::operator new(0xB0u);
    v22 = v21;
    v189 = v21;
    if ( v21 )
    {
      UnBCL::ArrayList<UnBCL::String *>::ArrayList<UnBCL::String *>(v21, 1);
      v22[6] = UnBCL::ArrayList<UnBCL::String *>::`local vftable'{for `UnBCL::Object'};
    }
    else
    {
      v22 = 0;
    }
    UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>(&v228, v22);
    UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::operator=(v233, &v228);
    UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::~SmartPtr<UnBCL::ArrayList<UnBCL::String *>>(&v228);
    v23 = UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::operator->(v233);
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v23 + 40LL))(v23, 1);
    P = UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::get_P(v233);
    SnapshotProp = VssEnumSnapshots(P);
    if ( SnapshotProp < 0 )
    {
      v26 = GetLastError();
      v27 = CurrentIP();
      v28 = ConstructPartialMsgW(0x2000000, "Cannot enumerate all VSS snapshots. Error: 0x%08X", SnapshotProp);
      v184 = v26;
      v181 = v27;
      lpTotalNumberOfClusters = 2505;
LABEL_13:
      WdsSetupLogMessageW(
        v28,
        0,
        L"D",
        0,
        lpTotalNumberOfClusters,
        L"base\\diagnosis\\srt\\pitr\\dll\\src\\restore.cpp",
        L"PrepareRestoreJournal",
        v181,
        v184,
        0,
        0);
      goto LABEL_115;
    }
    LODWORD(v189) = 0;
    for ( i = 0; ; i = v191 + 1 )
    {
      v191 = i;
      v30 = UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::operator->(v233);
      v31 = (int (__fastcall ***)(_QWORD))(v30 + 8 + *(int *)(*(_QWORD *)(v30 + 8) + 12LL));
      if ( i >= (**v31)(v31) )
        break;
      memset_0(&v226, 0, sizeof(v226));
      v32 = UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::operator->(v233);
      v33 = v32 + *(int *)(*(_QWORD *)(v32 + 8) + 16LL) + 8LL;
      v34 = (struct UnBCL::String **)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v33 + 24LL))(
                                       v33,
                                       (unsigned int)i);
      SnapshotProp = VssGetSnapshotProp(*v34, &v226);
      if ( SnapshotProp < 0 )
      {
        v63 = GetLastError();
        v64 = CurrentIP();
        v65 = UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::operator->(v233);
        v66 = v65 + *(int *)(*(_QWORD *)(v65 + 8) + 16LL);
        v67 = (UnBCL::String **)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)(v66 + 8) + 24LL))(
                                  v66 + 8,
                                  v191);
        CString = (const char *)UnBCL::String::get_CString(*v67);
        v28 = ConstructPartialMsgW(
                0x2000000,
                "Error getting snapshot properties for %s. Error: 0x%08X",
                CString,
                SnapshotProp);
        v184 = v63;
        v181 = v64;
        lpTotalNumberOfClusters = 2514;
        goto LABEL_13;
      }
      v35 = (UnBCL::String *)UnBCL::Object::operator new(0x18u);
      v36 = v35;
      v205 = v35;
      if ( v35 )
      {
        UnBCL::String::String(v35, v226.m_pwszSnapshotDeviceObject);
        *(_QWORD *)v36 = &UnBCL::String::`local vftable';
      }
      else
      {
        v36 = 0;
      }
      UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(&v228, v36);
      if ( v226.m_tsCreationTimestamp >= v204 )
      {
        v37 = GetLastError();
        v38 = CurrentIP();
        v39 = UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::operator->(v233);
        v40 = v39 + *(int *)(*(_QWORD *)(v39 + 8) + 16LL) + 8LL;
        v41 = (UnBCL::String **)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v40 + 24LL))(v40, v191);
        v42 = (const char *)UnBCL::String::get_CString(*v41);
        v43 = ConstructPartialMsgW(0x4000000, "Including bitmap data from: %s", v42);
        WdsSetupLogMessageW(
          v43,
          0,
          L"D",
          0,
          2522,
          L"base\\diagnosis\\srt\\pitr\\dll\\src\\restore.cpp",
          L"PrepareRestoreJournal",
          v38,
          v37,
          0,
          0);
        v44 = (UnBCL::String *)UnBCL::Object::operator new(0x18u);
        v45 = v44;
        v206 = v44;
        if ( v44 )
        {
          UnBCL::String::String(v44, v226.m_pwszSnapshotDeviceObject);
          *(_QWORD *)v45 = &UnBCL::String::`local vftable';
        }
        else
        {
          v45 = 0;
        }
        UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v227, v45);
        UnBCL::SmartPtr<UnBCL::String>::operator=(&v228, v227);
        UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v227);
        v46 = (struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(&v228);
        SnapshotProp = VssGetCopiedBitmapForVolume(v46, (unsigned __int8 **)&lpMem, &v190);
        if ( SnapshotProp < 0 )
        {
          VssFreeSnapshotPropertiesInternal(&v226);
          v59 = GetLastError();
          v60 = CurrentIP();
          v61 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(&v228);
          v62 = (const char *)UnBCL::String::get_CString(v61);
          v58 = ConstructPartialMsgW(
                  0x2000000,
                  "Failed to get VSS copied bitmap for volume %s. Error: 0x%08X",
                  v62,
                  SnapshotProp);
          v185 = v59;
          v182 = v60;
          lpTotalNumberOfClustersa = 2529;
          goto LABEL_37;
        }
        v47 = (unsigned int)v189;
        v48 = v190;
        if ( !(_DWORD)v189 )
          v47 = v190;
        LODWORD(v189) = v47;
        if ( v190 != v47 )
        {
          VssFreeSnapshotPropertiesInternal(&v226);
          v54 = GetLastError();
          v55 = CurrentIP();
          v56 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(&v228);
          v57 = (const char *)UnBCL::String::get_CString(v56);
          v58 = ConstructPartialMsgW(
                  0x2000000,
                  "VSS copied bitmap has wrong size for volume %s. Expected: %u, found %u",
                  v57,
                  (_DWORD)v189,
                  v190);
          v185 = v54;
          v182 = v55;
          lpTotalNumberOfClustersa = 2545;
LABEL_37:
          WdsSetupLogMessageW(
            v58,
            0,
            L"D",
            0,
            lpTotalNumberOfClustersa,
            L"base\\diagnosis\\srt\\pitr\\dll\\src\\restore.cpp",
            L"PrepareRestoreJournal",
            v182,
            v185,
            0,
            0);
          UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(&v228);
          goto LABEL_115;
        }
        if ( !v10 )
        {
          v49 = v190;
          v50 = GetProcessHeap();
          v10 = (unsigned __int8 *)HeapAlloc(v50, 8u, v49);
          v48 = v190;
        }
        v51 = 0;
        for ( j = lpMem; v51 < v48; ++v51 )
          v10[v51] |= j[v51];
        if ( j )
        {
          v53 = GetProcessHeap();
          HeapFree(v53, 0, j);
        }
        lpMem = 0;
      }
      VssFreeSnapshotPropertiesInternal(&v226);
      UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(&v228);
    }
    v219 = v10;
    v220[0] = (unsigned int)v189;
  }
  else
  {
    SnapshotProp = pGetVolsnapCopiedBitmapForVolume(a1, &v219, v220);
    if ( SnapshotProp < 0 )
    {
      v69 = GetLastError();
      v70 = CurrentIP();
      v71 = (const char *)UnBCL::String::get_CString(a1);
      v28 = ConstructPartialMsgW(
              0x2000000,
              "Failed to get copied bitmap for volume %s. Error: 0x%08X",
              v71,
              SnapshotProp);
      v184 = v69;
      v181 = v70;
      lpTotalNumberOfClusters = 2564;
      goto LABEL_13;
    }
  }
  v72 = v194;
  v73 = UnBCL::String::get_CString(v194);
  if ( !GetDiskFreeSpaceW(v73, &SectorsPerCluster, &BytesPerSector, &NumberOfFreeClusters, &TotalNumberOfClusters) )
  {
    v74 = GetLastError();
    v75 = v74 < 0;
    if ( v74 > 0 )
      v75 = 1;
    if ( v75 )
    {
      v76 = GetLastError();
      SnapshotProp = v76;
      if ( v76 > 0 )
        SnapshotProp = (unsigned __int16)v76 | 0x80070000;
    }
    else
    {
      SnapshotProp = -2147467259;
    }
    v77 = GetLastError();
    v78 = CurrentIP();
    v79 = (const char *)UnBCL::String::get_CString(v194);
    v80 = ConstructPartialMsgW(
            0x2000000,
            "Failed to get the cluster size for volume %s. Error: 0x%08X",
            v79,
            SnapshotProp);
    WdsSetupLogMessageW(
      v80,
      0,
      L"D",
      0,
      2573,
      L"base\\diagnosis\\srt\\pitr\\dll\\src\\restore.cpp",
      L"PrepareRestoreJournal",
      v78,
      v77,
      0,
      0);
    goto LABEL_51;
  }
  v220[1] = SectorsPerCluster * BytesPerSector;
  v81 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v200, L"$WINDOWS.~BK");
  v82 = UnBCL::Path::Combine(v72, v81);
  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v227, v82);
  UnBCL::SmartPtr<UnBCL::String>::operator=(v238, v227);
  UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v227);
  UnBCL::String::~String((UnBCL::String *)v200);
  v83 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v238);
  if ( !UnBCL::Directory::Exists(v83) )
  {
    v84 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v238);
    v85 = UnBCL::String::get_CString(v84);
    if ( !CreateDirectoryW(v85, 0) )
    {
      v86 = GetLastError();
      v87 = v86 < 0;
      if ( v86 > 0 )
        v87 = 1;
      if ( v87 )
      {
        v88 = GetLastError();
        SnapshotProp = v88;
        if ( v88 > 0 )
          SnapshotProp = (unsigned __int16)v88 | 0x80070000;
      }
      else
      {
        SnapshotProp = -2147467259;
      }
      v89 = GetLastError();
      v90 = CurrentIP();
      v91 = ConstructPartialMsgW(0x2000000, "Error creating the store directory: 0x%08X", SnapshotProp);
      WdsSetupLogMessageW(
        v91,
        0,
        L"D",
        0,
        2586,
        L"base\\diagnosis\\srt\\pitr\\dll\\src\\restore.cpp",
        L"PrepareRestoreJournal",
        v90,
        v89,
        0,
        0);
      goto LABEL_51;
    }
  }
  v92 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v200, L"$INPROGRESS.MKR");
  v93 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v238);
  v94 = UnBCL::Path::Combine(v93, v92);
  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v227, v94);
  UnBCL::SmartPtr<UnBCL::String>::operator=(v241, v227);
  UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v227);
  UnBCL::String::~String((UnBCL::String *)v200);
  v95 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v241);
  if ( !UnBCL::File::Exists(v95) )
  {
    try
    {
      v96 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v241);
      v97 = UnBCL::File::Create(v96);
      UnBCL::SmartPtr<UnBCL::FileStream>::SmartPtr<UnBCL::FileStream>(v227, v97);
      v227[0] = &UnBCL::SmartPtr<UnBCL::FileStream>::`vftable';
      UnBCL::SmartPtr<UnBCL::IEnumerator<unsigned long>>::DeAssign((__int64)v227);
    }
    catch ( UnBCL::Exception *v207 )
    {
      v171 = v207;
      v172 = ((__int64 (__fastcall *)(void (__fastcall ***)(_QWORD, __int64)))(*v207)[4])(v207);
      UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v227, v172);
      v173 = GetLastError();
      v174 = CurrentIP();
      v175 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v227);
      v176 = (const char *)UnBCL::String::get_CString(v175);
      v177 = ConstructPartialMsgW(0x2000000, "Exception creating in-progress marker: %s", v176);
      WdsSetupLogMessageW(
        v177,
        0,
        L"D",
        0,
        2602,
        L"base\\diagnosis\\srt\\pitr\\dll\\src\\restore.cpp",
        L"PrepareRestoreJournal",
        v174,
        v173,
        0,
        0);
      (**v171)(v171, 1);
      v188 = -2147467259;
      UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v227);
      v10 = 0;
      SnapshotProp = -2147467259;
      goto LABEL_115;
    }
  }
  v98 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v200, L"Operations.jrn");
  v99 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v238);
  v100 = UnBCL::Path::Combine(v99, v98);
  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v227, v100);
  UnBCL::SmartPtr<UnBCL::String>::operator=(v240, v227);
  UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v227);
  UnBCL::String::~String((UnBCL::String *)v200);
  v101 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v240);
  v102 = UnBCL::String::get_CString(v101);
  hObject = CreateFileW(v102, 0xC0000000, 1u, 0, 2u, 0x2000000u, 0);
  if ( hObject == (HANDLE)-1LL )
  {
    v103 = GetLastError();
    v104 = v103 < 0;
    if ( v103 > 0 )
      v104 = 1;
    if ( v104 )
    {
      v105 = GetLastError();
      SnapshotProp = v105;
      if ( v105 > 0 )
        SnapshotProp = (unsigned __int16)v105 | 0x80070000;
    }
    else
    {
      SnapshotProp = -2147467259;
    }
    v106 = GetLastError();
    v107 = CurrentIP();
    v108 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v240);
    v109 = (const char *)UnBCL::String::get_CString(v108);
    v110 = ConstructPartialMsgW(0x2000000, "Failed to create journal file %s, error: 0x%08X", v109, SnapshotProp);
    WdsSetupLogMessageW(
      v110,
      0,
      L"D",
      0,
      2626,
      L"base\\diagnosis\\srt\\pitr\\dll\\src\\restore.cpp",
      L"PrepareRestoreJournal",
      v107,
      v106,
      0,
      0);
    goto LABEL_51;
  }
  v111 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v200, L"PITR_CONFIG_ENV_PATH_OVERRIDE");
  EnvironmentVar = UnBCL::Environment::GetEnvironmentVar(v111);
  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v227, EnvironmentVar);
  UnBCL::SmartPtr<UnBCL::String>::operator=(v237, v227);
  UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v227);
  UnBCL::String::~String((UnBCL::String *)v200);
  if ( UnBCL::SmartPtr<UnBCL::String>::get_P(v237) )
  {
    v113 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v237);
    v114 = (int)v195;
    v115 = UnBCL::Path::Combine(v195, v113);
    UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v227, v115);
    UnBCL::SmartPtr<UnBCL::String>::operator=(v234, v227);
    UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v227);
    v116 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v237);
    v117 = UnBCL::Path::Combine(v194, v116);
    UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v227, v117);
    UnBCL::SmartPtr<UnBCL::String>::operator=(v239, v227);
    UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v227);
  }
  else
  {
    v114 = (int)v195;
  }
  v118 = GetLastError();
  v119 = CurrentIP();
  v120 = ConstructPartialMsgW(0x4000000, "Estimating restore process (1)...");
  WdsSetupLogMessageW(
    v120,
    0,
    L"D",
    0,
    2638,
    L"base\\diagnosis\\srt\\pitr\\dll\\src\\restore.cpp",
    L"PrepareRestoreJournal",
    v119,
    v118,
    0,
    0);
  if ( UnBCL::SmartPtr<UnBCL::String>::operator UnBCL::SmartPtr<UnBCL::String>::NullTest *(v234) )
    v121 = UnBCL::SmartPtr<UnBCL::String>::get_P(v234);
  else
    v121 = v114;
  SnapshotProp = pEstimateDiff(0, 3u, &v192, v121, 0, v196, 0, 0);
  if ( SnapshotProp < 0 )
  {
    v122 = GetLastError();
    v123 = CurrentIP();
    v124 = ConstructPartialMsgW(0x2000000, "Failed to perform estimation (1), error: 0x%08X", SnapshotProp);
    WdsSetupLogMessageW(
      v124,
      0,
      L"D",
      0,
      2642,
      L"base\\diagnosis\\srt\\pitr\\dll\\src\\restore.cpp",
      L"PrepareRestoreJournal",
      v123,
      v122,
      0,
      0);
LABEL_51:
    v10 = 0;
    goto LABEL_115;
  }
  v125 = wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PITR_FastCompare>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_Servicing_PITR_FastCompare>::GetImpl'::`2'::impl) == 0;
  v126 = v192;
  if ( !v125 && !v192 )
    v126 = 1;
  LODWORD(v189) = v126;
  v127 = GetLastError();
  v128 = CurrentIP();
  v129 = ConstructPartialMsgW(0x4000000, "Number of folders in estimation (1): %d", (_DWORD)v189);
  WdsSetupLogMessageW(
    v129,
    0,
    L"D",
    0,
    2653,
    L"base\\diagnosis\\srt\\pitr\\dll\\src\\restore.cpp",
    L"PrepareRestoreJournal",
    v128,
    v127,
    0,
    0);
  if ( v223 )
  {
    (**(void (__fastcall ***)(struct PITR::IPITRRestoreProgress *, __int64, _QWORD, __int64))v223)(
      v223,
      1,
      (unsigned int)v189,
      1);
    (*(void (__fastcall **)(struct PITR::IPITRRestoreProgress *, _QWORD))(*(_QWORD *)v223 + 8LL))(v223, 0);
  }
  v130 = GetLastError();
  v131 = CurrentIP();
  v132 = ConstructPartialMsgW(0x4000000, "Estimating restore process (2)...");
  WdsSetupLogMessageW(
    v132,
    0,
    L"D",
    0,
    2663,
    L"base\\diagnosis\\srt\\pitr\\dll\\src\\restore.cpp",
    L"PrepareRestoreJournal",
    v131,
    v130,
    0,
    0);
  LODWORD(v224) = 3;
  *((_QWORD *)&v224 + 1) = v201;
  v225 = v202;
  if ( UnBCL::SmartPtr<UnBCL::String>::operator UnBCL::SmartPtr<UnBCL::String>::NullTest *(v234) )
    v133 = UnBCL::SmartPtr<UnBCL::String>::get_P(v234);
  else
    v133 = (int)v195;
  SnapshotProp = pEstimateDiff(
                   0,
                   6u,
                   &v188,
                   v133,
                   0,
                   v196,
                   (__int64 (__fastcall *)(_QWORD, __int64))pEstimateCallback,
                   (__int64)&v224);
  if ( SnapshotProp < 0 )
  {
    v134 = GetLastError();
    v135 = CurrentIP();
    v136 = ConstructPartialMsgW(0x2000000, "Failed to perform estimation (2), error: 0x%08X", SnapshotProp);
    WdsSetupLogMessageW(
      v136,
      0,
      L"D",
      0,
      2670,
      L"base\\diagnosis\\srt\\pitr\\dll\\src\\restore.cpp",
      L"PrepareRestoreJournal",
      v135,
      v134,
      0,
      0);
    goto LABEL_51;
  }
  IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PITR_FastCompare>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_Servicing_PITR_FastCompare>::GetImpl'::`2'::impl);
  v138 = v188;
  if ( IsEnabled && !v188 )
    v138 = 1;
  v188 = v138;
  if ( v223 )
    (*(void (__fastcall **)(struct PITR::IPITRRestoreProgress *, _QWORD))(*(_QWORD *)v223 + 8LL))(
      v223,
      (unsigned int)v189);
  v139 = GetLastError();
  v140 = CurrentIP();
  v141 = ConstructPartialMsgW(0x4000000, "Number of folders in estimation (2): %d", v138);
  WdsSetupLogMessageW(
    v141,
    0,
    L"D",
    0,
    2686,
    L"base\\diagnosis\\srt\\pitr\\dll\\src\\restore.cpp",
    L"PrepareRestoreJournal",
    v140,
    v139,
    0,
    0);
  v142 = GetLastError();
  v143 = CurrentIP();
  v144 = ConstructPartialMsgW(0x4000000, "Generating the restore journal...");
  WdsSetupLogMessageW(
    v144,
    0,
    L"D",
    0,
    2689,
    L"base\\diagnosis\\srt\\pitr\\dll\\src\\restore.cpp",
    L"PrepareRestoreJournal",
    v143,
    v142,
    0,
    0);
  if ( v223 )
  {
    (**(void (__fastcall ***)(struct PITR::IPITRRestoreProgress *, __int64, _QWORD))v223)(v223, 2, v138);
    (*(void (__fastcall **)(struct PITR::IPITRRestoreProgress *, _QWORD))(*(_QWORD *)v223 + 8LL))(v223, v232);
  }
  v145 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v237);
  if ( UnBCL::SmartPtr<UnBCL::String>::operator UnBCL::SmartPtr<UnBCL::String>::NullTest *(v239) )
    v146 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v239);
  else
    v146 = v194;
  if ( UnBCL::SmartPtr<UnBCL::String>::operator UnBCL::SmartPtr<UnBCL::String>::NullTest *(v234) )
    v148 = (struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v234);
  else
    v148 = v195;
  SnapshotProp = pExecuteDiff(0, v147, &v232, v138, v195, v194, (__int64)v148, v146, v145, v187, (__int64)&v208, v196);
  if ( SnapshotProp < 0 )
  {
    v149 = GetLastError();
    v150 = CurrentIP();
    v151 = ConstructPartialMsgW(
             0x2000000,
             "Failed to create restore journal for snapshot restoration. Error: 0x%08X\n",
             SnapshotProp);
    WdsSetupLogMessageW(
      v151,
      0,
      L"D",
      0,
      2712,
      L"base\\diagnosis\\srt\\pitr\\dll\\src\\restore.cpp",
      L"PrepareRestoreJournal",
      v150,
      v149,
      0,
      0);
    goto LABEL_51;
  }
  if ( v223 )
    (*(void (__fastcall **)(struct PITR::IPITRRestoreProgress *, _QWORD))(*(_QWORD *)v223 + 8LL))(v223, v188);
  CloseHandle(hObject);
  hObject = 0;
  if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PITR_FastCompare>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_Servicing_PITR_FastCompare>::GetImpl'::`2'::impl) )
  {
    if ( v209 )
    {
      v152 = GetLastError();
      v153 = CurrentIP();
      v154 = ConstructPartialMsgW(0x2000000, "THOROUGH: Found %d false positive content comparisons", v209);
      WdsSetupLogMessageW(
        v154,
        0,
        L"D",
        0,
        2727,
        L"base\\diagnosis\\srt\\pitr\\dll\\src\\restore.cpp",
        L"PrepareRestoreJournal",
        v153,
        v152,
        0,
        0);
      if ( v203 )
        *v203 = v209;
    }
    goto LABEL_51;
  }
  v10 = 0;
  if ( v197 && v209 )
  {
    v155 = GetLastError();
    v156 = CurrentIP();
    v157 = ConstructPartialMsgW(0x4000000, "THOROUGH: Found %d false positive content comparisons", v209);
    WdsSetupLogMessageW(
      v157,
      0,
      L"D",
      0,
      2738,
      L"base\\diagnosis\\srt\\pitr\\dll\\src\\restore.cpp",
      L"PrepareRestoreJournal",
      v156,
      v155,
      0,
      0);
    goto LABEL_51;
  }
LABEL_115:
  if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
  {
    CloseHandle(hObject);
    hObject = 0;
  }
  if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PITR_FastCompare>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_Servicing_PITR_FastCompare>::GetImpl'::`2'::impl) )
  {
    if ( v10 )
    {
      v163 = GetProcessHeap();
      HeapFree(v163, 0, v10);
    }
    if ( lpMem )
    {
      v164 = GetProcessHeap();
      HeapFree(v164, 0, lpMem);
    }
  }
  if ( v211 )
  {
    v165 = GetProcessHeap();
    HeapFree(v165, 0, v211);
    v211 = 0;
  }
  if ( v215 )
  {
    v166 = GetProcessHeap();
    HeapFree(v166, 0, v215);
    v215 = 0;
  }
  if ( v213 )
  {
    v167 = GetProcessHeap();
    HeapFree(v167, 0, v213);
    v213 = 0;
  }
  if ( v217 )
  {
    v168 = GetProcessHeap();
    HeapFree(v168, 0, v217);
    v217 = 0;
  }
  if ( v219 )
  {
    v169 = GetProcessHeap();
    HeapFree(v169, 0, v219);
    v219 = 0;
  }
  UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::~SmartPtr<UnBCL::ArrayList<UnBCL::String *>>(v233);
  UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v239);
  UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v234);
  UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v237);
  v198 = &UnBCL::SmartPtr<UnBCL::Hashtable<UnBCL::String *,unsigned long>>::`vftable';
  UnBCL::SmartPtr<UnBCL::IEnumerator<unsigned long>>::DeAssign((__int64)&v198);
  UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v240);
  UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v241);
  UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v238);
  return (unsigned int)SnapshotProp;
}

```

## disassembly

```asm
0x18002a6fc  push    rbx
0x18002a6fe  push    rsi
0x18002a6ff  push    rdi
0x18002a700  push    r12
0x18002a702  push    r13
0x18002a704  push    r14
0x18002a706  push    r15
0x18002a708  sub     rsp, 2E0h
0x18002a70f  mov     rax, cs:__security_cookie
0x18002a716  xor     rax, rsp
0x18002a719  mov     [rsp+318h+var_40], rax
0x18002a721  mov     r13d, r9d
0x18002a724  mov     [rsp+318h+var_278], r9d
0x18002a72c  mov     [rsp+318h+var_230], r8
0x18002a734  mov     [rsp+318h+var_290], rdx
0x18002a73c  mov     r12, rcx
0x18002a73f  mov     [rsp+318h+var_288], rcx
0x18002a747  mov     rdi, [rsp+318h+arg_28]
0x18002a74f  mov     [rsp+318h+var_248], rdi
0x18002a757  mov     r14, [rsp+318h+arg_30]
0x18002a75f  mov     [rsp+318h+var_240], r14
0x18002a767  mov     rax, [rsp+318h+arg_38]
0x18002a76f  mov     [rsp+318h+var_238], rax
0x18002a777  xorps   xmm0, xmm0
0x18002a77a  xor     eax, eax
0x18002a77c  movups  [rsp+318h+var_188], xmm0
0x18002a784  mov     [rsp+318h+var_178], rax
0x18002a78c  xor     edx, edx; Val
0x18002a78e  lea     r8d, [rax+78h]; Size
0x18002a792  lea     rcx, [rsp+318h+var_208]; void *
0x18002a79a  call    memset_0
0x18002a79f  xor     esi, esi
0x18002a7a1  mov     [rsp+318h+SectorsPerCluster], esi
0x18002a7a8  mov     [rsp+318h+BytesPerSector], esi
0x18002a7af  mov     [rsp+318h+NumberOfFreeClusters], esi
0x18002a7b6  mov     [rsp+318h+TotalNumberOfClusters], esi
0x18002a7bd  lea     rcx, [rsp+318h+var_80]
0x18002a7c5  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(void)
0x18002a7cb  nop
0x18002a7cc  lea     rcx, [rsp+318h+var_50]
0x18002a7d4  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(void)
0x18002a7da  nop
0x18002a7db  lea     rcx, [rsp+318h+var_60]
0x18002a7e3  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(void)
0x18002a7e9  nop
0x18002a7ea  lea     rax, ??_7?$SmartPtr@V?$Hashtable@PEAVString@UnBCL@@K@UnBCL@@@UnBCL@@6B@; const UnBCL::SmartPtr<UnBCL::Hashtable<UnBCL::String *,ulong>>::`vftable'
0x18002a7f1  mov     [rsp+318h+var_270], rax
0x18002a7f9  mov     [rsp+318h+var_268], rsi
0x18002a801  mov     [rsp+318h+var_2A0], esi
0x18002a805  mov     [rsp+318h+var_2B8], esi
0x18002a809  mov     [rsp+318h+var_C0], esi
0x18002a810  lea     rcx, [rsp+318h+var_90]
0x18002a818  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(void)
0x18002a81e  nop
0x18002a81f  lea     rcx, [rsp+318h+var_A8]
0x18002a827  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(void)
0x18002a82d  nop
0x18002a82e  lea     rcx, [rsp+318h+var_70]
0x18002a836  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(void)
0x18002a83c  nop
0x18002a83d  lea     rcx, [rsp+318h+var_B8]
0x18002a845  call    cs:__imp_??0?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEAA@XZ; UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>(void)
0x18002a84b  nop
0x18002a84c  mov     r15d, esi
0x18002a84f  mov     [rsp+318h+lpMem], rsi
0x18002a857  mov     dword ptr [rsp+318h+var_2A8], esi
0x18002a85b  call    ?pBuildExclusionData@@YAPEAV?$Hashtable@PEAVString@UnBCL@@K@UnBCL@@XZ; pBuildExclusionData(void)
0x18002a860  mov     rdx, rax
0x18002a863  lea     rcx, [rsp+318h+var_D8]
0x18002a86b  call    ??0?$SmartPtr@V?$Hashtable@PEAVString@UnBCL@@K@UnBCL@@@UnBCL@@QEAA@PEAV?$Hashtable@PEAVString@UnBCL@@K@1@@Z; UnBCL::SmartPtr<UnBCL::Hashtable<UnBCL::String *,ulong>>::SmartPtr<UnBCL::Hashtable<UnBCL::String *,ulong>>(UnBCL::Hashtable<UnBCL::String *,ulong> *)
0x18002a870  nop
0x18002a871  mov     rbx, [rsp+318h+var_D0]
0x18002a879  mov     [rsp+318h+var_280], rbx
0x18002a881  test    rbx, rbx
0x18002a884  jz      short loc_18002A89B
0x18002a886  mov     rax, [rbx+8]
0x18002a88a  movsxd  rcx, dword ptr [rax+4]
0x18002a88e  add     rcx, 8
0x18002a892  add     rcx, rbx
0x18002a895  call    cs:__imp_?AddRef@Object@UnBCL@@QEAAXXZ; UnBCL::Object::AddRef(void)
0x18002a89b  lea     rcx, [rsp+318h+var_270]
0x18002a8a3  call    ?DeAssign@?$SmartPtr@U?$IEnumerator@K@UnBCL@@@UnBCL@@AEAAXXZ; UnBCL::SmartPtr<UnBCL::IEnumerator<ulong>>::DeAssign(void)
0x18002a8a8  mov     [rsp+318h+var_268], rbx
0x18002a8b0  lea     rax, ??_7?$SmartPtr@V?$Hashtable@PEAVString@UnBCL@@K@UnBCL@@@UnBCL@@6B@; const UnBCL::SmartPtr<UnBCL::Hashtable<UnBCL::String *,ulong>>::`vftable'
0x18002a8b7  mov     [rsp+318h+var_D8], rax
0x18002a8bf  lea     rcx, [rsp+318h+var_D8]
0x18002a8c7  call    ?DeAssign@?$SmartPtr@U?$IEnumerator@K@UnBCL@@@UnBCL@@AEAAXXZ; UnBCL::SmartPtr<UnBCL::IEnumerator<ulong>>::DeAssign(void)
0x18002a8cc  nop
0x18002a8cd  mov     [rsp+318h+var_208], r13d
0x18002a8d5  mov     eax, [rsp+318h+arg_20]
0x18002a8dc  mov     [rsp+318h+var_200], eax
0x18002a8e3  mov     [rsp+318h+var_1A0], rdi
0x18002a8eb  mov     [rsp+318h+var_198], r14
0x18002a8f3  mov     ebx, 0FC020h
0x18002a8f8  mov     dword ptr [rsp+318h+dwBytes], ebx
0x18002a8ff  mov     [rsp+318h+var_1F0], ebx
0x18002a906  call    cs:__imp_GetProcessHeap
0x18002a90c  mov     rcx, rax; hHeap
0x18002a90f  mov     r8d, ebx; dwBytes
0x18002a912  mov     edi, 8
0x18002a917  mov     edx, edi; dwFlags
0x18002a919  call    cs:__imp_HeapAlloc
0x18002a91f  mov     [rsp+318h+var_1F8], rax
0x18002a927  mov     ebx, dword ptr [rsp+318h+dwBytes]
0x18002a92e  call    cs:__imp_GetProcessHeap
0x18002a934  mov     rcx, rax; hHeap
0x18002a937  mov     r8d, ebx; dwBytes
0x18002a93a  mov     edx, edi; dwFlags
0x18002a93c  call    cs:__imp_HeapAlloc
0x18002a942  mov     [rsp+318h+var_1D8], rax
0x18002a94a  cmp     [rsp+318h+var_1F8], rsi
0x18002a952  jz      loc_18002BD0C
0x18002a958  test    rax, rax
0x18002a95b  jz      loc_18002BD0C
0x18002a961  mov     ebx, 1000h
0x18002a966  mov     dword ptr [rsp+318h+var_1C0], ebx
0x18002a96d  mov     [rsp+318h+var_1E0], ebx
0x18002a974  call    cs:__imp_GetProcessHeap
0x18002a97a  mov     rcx, rax; hHeap
0x18002a97d  mov     r8d, ebx; dwBytes
0x18002a980  mov     edx, edi; dwFlags
0x18002a982  call    cs:__imp_HeapAlloc
0x18002a988  mov     [rsp+318h+var_1E8], rax
0x18002a990  mov     ebx, dword ptr [rsp+318h+var_1C0]
0x18002a997  call    cs:__imp_GetProcessHeap
0x18002a99d  mov     rcx, rax; hHeap
0x18002a9a0  mov     r8d, ebx; dwBytes
0x18002a9a3  mov     edx, edi; dwFlags
0x18002a9a5  call    cs:__imp_HeapAlloc
0x18002a9ab  mov     [rsp+318h+var_1C8], rax
0x18002a9b3  cmp     [rsp+318h+var_1E8], rsi
0x18002a9bb  jz      loc_18002BCB6
0x18002a9c1  test    rax, rax
0x18002a9c4  jz      loc_18002BCB6
0x18002a9ca  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_PITR_FastCompare@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_PITR_FastCompare@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PITR_FastCompare> `wil::Feature<__WilFeatureTraits_Feature_Servicing_PITR_FastCompare>::GetImpl(void)'::`2'::impl
0x18002a9d1  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_PITR_FastCompare@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PITR_FastCompare>::__private_IsEnabled(void)
0x18002a9d6  test    al, al
0x18002a9d8  jz      loc_18002AFC0
0x18002a9de  mov     ecx, 0B0h
0x18002a9e3  call    cs:__imp_??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18002a9e9  mov     rbx, rax
0x18002a9ec  mov     [rsp+318h+var_2B0], rax
0x18002a9f1  mov     edi, 1
0x18002a9f6  test    rax, rax
0x18002a9f9  jz      short loc_18002AA13
0x18002a9fb  mov     edx, edi
0x18002a9fd  mov     rcx, rax
0x18002aa00  call    cs:__imp_??0?$ArrayList@PEAVString@UnBCL@@@UnBCL@@QEAA@XZ; UnBCL::ArrayList<UnBCL::String *>::ArrayList<UnBCL::String *>(void)
0x18002aa06  lea     rax, ??_S?$ArrayList@PEAVString@UnBCL@@@UnBCL@@6BObject@1@@; const UnBCL::ArrayList<UnBCL::String *>::`local vftable'{for `UnBCL::Object'}
0x18002aa0d  mov     [rbx+30h], rax
0x18002aa11  jmp     short loc_18002AA16
0x18002aa13  mov     rbx, rsi
0x18002aa16  mov     rdx, rbx
0x18002aa19  lea     rcx, [rsp+318h+var_D8]
0x18002aa21  call    cs:__imp_??0?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEAA@PEAV?$ArrayList@PEAVString@UnBCL@@@1@@Z; UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>(UnBCL::ArrayList<UnBCL::String *> *)
0x18002aa27  nop
0x18002aa28  lea     rdx, [rsp+318h+var_D8]
0x18002aa30  lea     rcx, [rsp+318h+var_B8]
0x18002aa38  call    cs:__imp_??4?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z; UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::operator=(UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>> const &)
0x18002aa3e  nop
0x18002aa3f  lea     rcx, [rsp+318h+var_D8]
0x18002aa47  call    cs:__imp_??1?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::~SmartPtr<UnBCL::ArrayList<UnBCL::String *>>(void)
0x18002aa4d  lea     rcx, [rsp+318h+var_B8]
0x18002aa55  call    cs:__imp_??C?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@1@XZ; UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::operator->(void)
0x18002aa5b  mov     rcx, rax
0x18002aa5e  mov     rax, [rax]
0x18002aa61  mov     edx, edi
0x18002aa63  mov     rax, [rax+28h]
0x18002aa67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002aa6c  lea     rcx, [rsp+318h+var_B8]
0x18002aa74  call    cs:__imp_?get_P@?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@2@XZ; UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::get_P(void)
0x18002aa7a  mov     rcx, rax
0x18002aa7d  call    ?VssEnumSnapshots@@YAJPEAV?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@Z; VssEnumSnapshots(UnBCL::ArrayList<UnBCL::String *> *)
0x18002aa82  mov     r14d, eax
0x18002aa85  test    eax, eax
0x18002aa87  jns     short loc_18002AAFA
0x18002aa89  call    cs:__imp_GetLastError
0x18002aa8f  mov     edi, eax
0x18002aa91  call    cs:__imp_CurrentIP
0x18002aa97  mov     rbx, rax
0x18002aa9a  mov     r8d, r14d
0x18002aa9d  lea     rdx, aCannotEnumerat; "Cannot enumerate all VSS snapshots. Err"...
0x18002aaa4  mov     ecx, 2000000h; unsigned int
0x18002aaa9  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18002aaae  mov     dword ptr [rsp+318h+var_2C8], esi
0x18002aab2  mov     [rsp+318h+var_2D0], rsi
0x18002aab7  mov     dword ptr [rsp+318h+var_2D8], edi
0x18002aabb  mov     [rsp+318h+var_2E0], rbx
0x18002aac0  lea     r13, aPreparerestore; "PrepareRestoreJournal"
0x18002aac7  mov     [rsp+318h+hTemplateFile], r13
0x18002aacc  lea     rcx, aBaseDiagnosisS_3; "base\\diagnosis\\srt\\pitr\\dll\\src\\r"...
0x18002aad3  mov     qword ptr [rsp+318h+dwFlagsAndAttributes], rcx
0x18002aad8  mov     dword ptr [rsp+318h+lpTotalNumberOfClusters], 9C9h
0x18002aae0  lea     r8, aD; "D"
0x18002aae7  xor     r9d, r9d
0x18002aaea  xor     edx, edx
0x18002aaec  mov     rcx, rax
0x18002aaef  call    cs:__imp_WdsSetupLogMessageW
0x18002aaf5  jmp     loc_18002BD7B
0x18002aafa  mov     dword ptr [rsp+318h+var_2B0], esi
0x18002aafe  mov     ebx, esi
0x18002ab00  lea     r13, aPreparerestore; "PrepareRestoreJournal"
0x18002ab07  lea     r12, aD; "D"
0x18002ab0e  mov     dword ptr [rsp+318h+var_2A8+4], ebx
0x18002ab12  lea     rcx, [rsp+318h+var_B8]
0x18002ab1a  call    cs:__imp_??C?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@1@XZ; UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::operator->(void)
0x18002ab20  mov     rdx, rax
0x18002ab23  mov     rax, [rax+8]
0x18002ab27  movsxd  rcx, dword ptr [rax+0Ch]
0x18002ab2b  add     rdx, 8
0x18002ab2f  add     rcx, rdx
0x18002ab32  mov     rax, [rcx]
0x18002ab35  mov     rax, [rax]
0x18002ab38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ab3d  cmp     ebx, eax
0x18002ab3f  jge     loc_18002AFA8
0x18002ab45  xor     edx, edx; Val
0x18002ab47  mov     r8d, 80h; Size
0x18002ab4d  lea     rcx, [rsp+318h+var_168]; void *
0x18002ab55  call    memset_0
0x18002ab5a  lea     rcx, [rsp+318h+var_B8]
0x18002ab62  call    cs:__imp_??C?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@1@XZ; UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::operator->(void)
0x18002ab68  mov     rdx, rax
0x18002ab6b  mov     rax, [rax+8]
0x18002ab6f  movsxd  rcx, dword ptr [rax+10h]
0x18002ab73  add     rcx, 8
0x18002ab77  add     rcx, rdx
0x18002ab7a  mov     rax, [rcx]
0x18002ab7d  mov     edx, ebx
0x18002ab7f  mov     rax, [rax+18h]
0x18002ab83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ab88  lea     rdx, [rsp+318h+var_168]; struct _VSS_SNAPSHOT_PROP *
0x18002ab90  mov     rcx, [rax]; struct UnBCL::String *
0x18002ab93  call    ?VssGetSnapshotProp@@YAJPEAVString@UnBCL@@PEAU_VSS_SNAPSHOT_PROP@@@Z; VssGetSnapshotProp(UnBCL::String *,_VSS_SNAPSHOT_PROP *)
0x18002ab98  mov     r14d, eax
0x18002ab9b  test    eax, eax
0x18002ab9d  js      loc_18002AF16
0x18002aba3  mov     ecx, 18h
0x18002aba8  call    cs:__imp_??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18002abae  mov     rbx, rax
0x18002abb1  mov     [rsp+318h+var_228], rax
0x18002abb9  test    rax, rax
0x18002abbc  jz      short loc_18002ABDB
0x18002abbe  mov     rdx, [rsp+318h+var_168.m_pwszSnapshotDeviceObject]
0x18002abc6  mov     rcx, rax
0x18002abc9  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x18002abcf  lea     rax, ??_SString@UnBCL@@6B@; const UnBCL::String::`local vftable'
0x18002abd6  mov     [rbx], rax
0x18002abd9  jmp     short loc_18002ABDE
0x18002abdb  mov     rbx, rsi
0x18002abde  mov     rdx, rbx
0x18002abe1  lea     rcx, [rsp+318h+var_D8]
0x18002abe9  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x18002abef  nop
0x18002abf0  mov     rax, [rsp+318h+var_230]
0x18002abf8  cmp     [rsp+318h+var_168.m_tsCreationTimestamp], rax
0x18002ac00  jl      loc_18002ADCA
0x18002ac06  call    cs:__imp_GetLastError
0x18002ac0c  mov     edi, eax
0x18002ac0e  call    cs:__imp_CurrentIP
0x18002ac14  mov     rbx, rax
0x18002ac17  lea     rcx, [rsp+318h+var_B8]
0x18002ac1f  call    cs:__imp_??C?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@1@XZ; UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::operator->(void)
0x18002ac25  mov     rdx, rax
0x18002ac28  mov     rax, [rax+8]
0x18002ac2c  movsxd  rcx, dword ptr [rax+10h]
0x18002ac30  add     rcx, 8
0x18002ac34  add     rcx, rdx
0x18002ac37  mov     rax, [rcx]
0x18002ac3a  mov     edx, dword ptr [rsp+318h+var_2A8+4]
0x18002ac3e  mov     rax, [rax+18h]
0x18002ac42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ac47  mov     rcx, [rax]
0x18002ac4a  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x18002ac50  mov     r8, rax
0x18002ac53  lea     rdx, aIncludingBitma; "Including bitmap data from: %s"
0x18002ac5a  mov     ecx, 4000000h; unsigned int
0x18002ac5f  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18002ac64  mov     dword ptr [rsp+318h+var_2C8], esi
0x18002ac68  mov     [rsp+318h+var_2D0], rsi
0x18002ac6d  mov     dword ptr [rsp+318h+var_2D8], edi
0x18002ac71  mov     [rsp+318h+var_2E0], rbx
0x18002ac76  mov     [rsp+318h+hTemplateFile], r13
0x18002ac7b  lea     rcx, aBaseDiagnosisS_3; "base\\diagnosis\\srt\\pitr\\dll\\src\\r"...
0x18002ac82  mov     qword ptr [rsp+318h+dwFlagsAndAttributes], rcx
0x18002ac87  mov     dword ptr [rsp+318h+lpTotalNumberOfClusters], 9DAh
0x18002ac8f  xor     r9d, r9d
0x18002ac92  mov     r8, r12
0x18002ac95  xor     edx, edx
0x18002ac97  mov     rcx, rax
0x18002ac9a  call    cs:__imp_WdsSetupLogMessageW
0x18002aca0  mov     ecx, 18h
0x18002aca5  call    cs:__imp_??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18002acab  mov     rbx, rax
0x18002acae  mov     [rsp+318h+var_220], rax
0x18002acb6  test    rax, rax
0x18002acb9  jz      short loc_18002ACD8
0x18002acbb  mov     rdx, [rsp+318h+var_168.m_pwszSnapshotDeviceObject]
0x18002acc3  mov     rcx, rax
0x18002acc6  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
  ... truncated ...
```
