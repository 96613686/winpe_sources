# CDeploymentSession::ProcessSandboxContainerPayload(ActionList *,int,int,std::vector<UaLiteManagerDownloadRequest,std::allocator<UaLiteManagerDownloadRequest>> *)

- ea: `0x18007c740`
- end: `0x18007f251`
- name: `?ProcessSandboxContainerPayload@CDeploymentSession@@QEAAJPEAUActionList@@HHPEAV?$vector@UUaLiteManagerDownloadRequest@@V?$allocator@UUaLiteManagerDownloadRequest@@@std@@@std@@@Z`
- size: `11025`
- prototype: `__int64 __fastcall(CDeploymentSession *this, __int64, int, DWORD, __int64 *)`
- caller_count: `4`
- callee_count: `51`
- tags: `file_ops, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18002f468`
- `0x18004478c`
- `0x18004f0b0`
- `0x180073f2c`

## callees

- `0x1800059d0`
- `0x180005cf0`
- `0x1800099ec`
- `0x180012770`
- `0x1800127a4`
- `0x180012878`
- `0x180012a30`
- `0x180012d94`
- `0x180012fe4`
- `0x180014540`
- `0x180015544`
- `0x18001b354`
- `0x18001f4b4`
- `0x18001f5fc`
- `0x18001f95c`
- `0x180022904`
- `0x1800236d8`
- `0x18002374c`
- `0x180023b20`
- `0x1800244c0`
- `0x180024930`
- `0x180024ea8`
- `0x180025190`
- `0x180026af8`
- `0x18002721c`
- `0x1800280d8`
- `0x180028140`
- `0x18002817c`
- `0x1800281d4`
- `0x1800285c4`
- `0x180037234`
- `0x180039f90`
- `0x18003c418`
- `0x18004c794`
- `0x1800613b4`
- `0x180062e60`
- `0x180074968`
- `0x180077664`
- `0x180078b4c`
- `0x180078b9c`
- `0x18007c740`
- `0x18008c3e0`
- `0x18008c6d8`
- `0x1800918a8`
- `0x180094d0c`
- `0x18009d348`
- `0x18009f0b0`
- `0x1801e3fc0`
- `0x1801ec2a4`
- `0x180223ec8`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18007ecbf`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18007ecbf`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18007ec51`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18007ec51`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x18007e438`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x18007e438`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x18007e99d`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x18007e99d`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x18007eb25`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x18007eece`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x18007eb25`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x18007eece`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18007e208`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18007e65b`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18007e208`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18007e65b`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18007e3c1`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18007ea95`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18007e3c1`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18007ea95`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18007ccf1`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18007cfc0`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18007d855`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18007db0d`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18007ccf1`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18007cfc0`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18007d855`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18007db0d`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x18007e5c9`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x18007e750`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x18007e82f`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x18007eadf`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x18007eb76`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x18007ed5d`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x18007ee7d`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x18007e5c9`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x18007e750`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x18007e82f`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x18007eadf`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x18007eb76`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x18007ed5d`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x18007ee7d`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x18007e338`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x18007e90d`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x18007ee0d`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x18007f048`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x18007e338`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x18007e90d`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x18007ee0d`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x18007f048`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18007cb17`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18007cc71`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18007cddb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18007cee2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18007cf49`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18007d498`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18007cb17`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18007cc71`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18007cddb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18007cee2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18007cf49`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18007d498`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18007cb2c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18007cc86`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18007cdf0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18007cef7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18007cf5d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18007d4ad`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18007cb2c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18007cc86`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18007cdf0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18007cef7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18007cf5d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18007d4ad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007e34a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007e448`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007e5dd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007e66d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007e760`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007e83f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007e91f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007e9ad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007eaef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007eb37`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007eb86`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007ec63`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007ecd2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007ed70`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007ee1f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007ee8f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007eede`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007ef4d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007f05e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007f0da`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007e34a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007e448`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007e5dd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007e66d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007e760`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007e83f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007e91f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007e9ad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007eaef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007eb37`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007eb86`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007ec63`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007ecd2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007ed70`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007ee1f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007ee8f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007eede`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007ef4d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007f05e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007f0da`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007f178`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007f192`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007f178`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007f192`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007e611`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007e6b1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007e8bb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007efa3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007f12c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007e611`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007e6b1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007e8bb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007efa3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007f12c`

## string_xrefs

- `0x18007f229`: `onecore\base\ntsetup\conx\mosetup\updateagent\src\DeploymentSessionImpl.h`
- `0x18007f23e`: `onecore\base\ntsetup\conx\mosetup\updateagent\src\DeploymentSessionImpl.h`
- `0x18007ea5c`: `Creating temporary payload file [%ws] for [%ws]`
- `0x18007e216`: `Failed to delete file`

## pseudocode

```c
// Hidden C++ exception states: #wind=16
__int64 __fastcall CDeploymentSession::ProcessSandboxContainerPayload(
        CDeploymentSession *this,
        __int64 a2,
        int a3,
        DWORD a4,
        __int64 *a5)
{
  int v5; // r12d
  __int64 *v8; // rdi
  const wchar_t *v9; // rsi
  _QWORD *v10; // rax
  _QWORD *v11; // rax
  _QWORD *v12; // rax
  _QWORD *v13; // rax
  int PackageFileListPath; // r14d
  __int64 v15; // rcx
  const wchar_t *v16; // r9
  __int64 v17; // rcx
  __int64 v18; // rcx
  int updated; // eax
  __int64 v20; // r13
  const wchar_t *v21; // rax
  unsigned int v22; // eax
  int v23; // ecx
  __int64 v24; // rdi
  const wchar_t *v25; // rax
  const WCHAR *v26; // rdx
  int v27; // edx
  __int64 v28; // rax
  __int64 v29; // rcx
  LPCWSTR v30; // rbx
  HANDLE v31; // rax
  __int64 v32; // rax
  __int64 v33; // rcx
  int v34; // edx
  int v35; // r8d
  int v36; // r9d
  const wchar_t *v37; // r12
  HANDLE ProcessHeap; // rax
  DWORD FileAttributesW; // eax
  BOOL v40; // ebx
  __int64 v41; // rax
  __int64 v42; // rax
  __int64 v43; // rcx
  int v44; // eax
  union _LARGE_INTEGER v45; // rbx
  HANDLE v46; // rax
  CDeploymentSession *v47; // rcx
  int FileFromWim; // eax
  __int64 v49; // r8
  union _LARGE_INTEGER v50; // rbx
  HANDLE v51; // rax
  const wchar_t **v52; // rsi
  WCHAR *v53; // rbx
  HANDLE v54; // rax
  DWORD v55; // eax
  int v56; // ebx
  __int64 v57; // rbx
  bool v58; // zf
  __int64 v59; // rax
  __int64 v60; // rcx
  int v61; // eax
  __int64 v62; // rdx
  __int64 v63; // r9
  __int64 v64; // rax
  __int64 v65; // r12
  unsigned __int64 v66; // rax
  __int64 *v67; // rcx
  __int64 v68; // rax
  __int64 v69; // rax
  __int64 v70; // rcx
  int v71; // eax
  __int64 v72; // rax
  int v73; // eax
  unsigned int i; // r13d
  wchar_t *v75; // rsi
  __int64 v76; // rax
  __int64 v77; // rax
  __int64 v78; // rcx
  int v79; // eax
  LPCWSTR v80; // rbx
  HANDLE v81; // rax
  union _LARGE_INTEGER v82; // rdi
  __int64 (__fastcall *v83)(union _LARGE_INTEGER, __int64); // rbx
  __int64 v84; // rdx
  __int64 v85; // rax
  __int64 v86; // rcx
  int v87; // eax
  union _LARGE_INTEGER v88; // rdi
  __int64 (__fastcall *v89)(union _LARGE_INTEGER, __int64); // rbx
  __int64 v90; // rdx
  int v91; // eax
  union _LARGE_INTEGER v92; // rbx
  __int64 (__fastcall *v93)(union _LARGE_INTEGER, union _LARGE_INTEGER *); // rdi
  _QWORD *v94; // rcx
  int v95; // eax
  int v96; // eax
  __int64 v97; // rax
  int v98; // eax
  DWORD v99; // eax
  BOOL v100; // ebx
  __int64 v101; // rax
  int v102; // eax
  CDeploymentSession *v103; // rcx
  int v104; // eax
  int v105; // eax
  DWORD v106; // eax
  DWORD v107; // ebx
  __int64 v108; // rdi
  __int64 v109; // r8
  __int64 v110; // rcx
  const wchar_t *v111; // rbx
  __int64 v112; // rcx
  int OffsetInOuterContainer; // eax
  unsigned int v114; // eax
  unsigned __int64 v115; // rbx
  unsigned int j; // esi
  __int64 v117; // rax
  int v118; // eax
  int v119; // eax
  __int64 v120; // rdx
  __int64 *v121; // rbx
  unsigned __int64 v122; // rax
  unsigned __int64 v123; // rbx
  unsigned __int64 v124; // rax
  unsigned int v125; // eax
  int v126; // eax
  __int64 v127; // r9
  __int64 v128; // rcx
  _QWORD *v129; // rdi
  const WCHAR *v130; // rdi
  const WCHAR *v131; // r12
  signed int LastError; // eax
  HANDLE FileW; // rax
  __int64 v134; // r13
  unsigned __int64 v135; // rcx
  _QWORD *v136; // r12
  __int64 k; // rax
  WCHAR *v138; // rcx
  signed int v139; // eax
  __int64 v140; // r9
  __int64 v141; // rcx
  union _LARGE_INTEGER v142; // rdx
  union _LARGE_INTEGER v143; // rdi
  _QWORD *v144; // rcx
  _QWORD *v145; // rax
  __int64 v146; // r10
  unsigned __int64 v147; // rdi
  __int64 v148; // rax
  __int64 v149; // rcx
  __int64 v150; // rcx
  void *v151; // rcx
  signed int v152; // eax
  __int64 v153; // rcx
  signed int v154; // eax
  wchar_t *v155; // rdi
  wchar_t *v156; // rax
  void *v157; // rcx
  signed int v158; // eax
  __int64 v159; // r9
  __int64 v160; // rdx
  __int64 v161; // rcx
  __int64 v162; // rcx
  int v163; // eax
  void *v164; // rcx
  signed int v165; // eax
  __int64 v166; // rcx
  __int64 v167; // rcx
  const WCHAR *v168; // rdi
  signed int v169; // eax
  __int64 **v170; // rcx
  __int64 *ii; // rax
  signed int v172; // eax
  int v173; // eax
  LPCWSTR v174; // r9
  HANDLE v175; // rax
  char *v176; // rdi
  LARGE_INTEGER v177; // r14
  signed int v178; // eax
  __int64 v179; // r9
  signed int v180; // eax
  __int64 v181; // rcx
  signed int v182; // eax
  __int64 v183; // r9
  __int64 v184; // rdx
  int v185; // eax
  DWORD LowPart; // r8d
  void *v187; // rcx
  signed int v188; // eax
  void *v189; // rcx
  signed int v190; // eax
  void *v191; // rcx
  signed int v192; // eax
  signed int v193; // eax
  void *v194; // rcx
  BOOL v195; // eax
  void *v196; // rcx
  signed int v197; // eax
  signed int v198; // eax
  signed int v199; // eax
  int v200; // eax
  __int64 v201; // rcx
  __int64 v202; // r9
  __int64 v203; // rdx
  const WCHAR *v204; // rdi
  signed int v205; // eax
  __int64 *jj; // rcx
  signed int v207; // eax
  const char *v208; // r9
  __int64 result; // rax
  DWORD dwCreationDisposition[2]; // [rsp+20h] [rbp-438h]
  DWORD dwFlagsAndAttributes[2]; // [rsp+28h] [rbp-430h]
  LPCWSTR lpFileName; // [rsp+40h] [rbp-418h] BYREF
  LPCWSTR lpExistingFileName; // [rsp+48h] [rbp-410h] BYREF
  unsigned __int64 QuadPart; // [rsp+50h] [rbp-408h] BYREF
  unsigned __int64 v215; // [rsp+58h] [rbp-400h] BYREF
  unsigned __int64 m; // [rsp+60h] [rbp-3F8h] BYREF
  __int128 v217; // [rsp+68h] [rbp-3F0h] BYREF
  unsigned __int64 v218[2]; // [rsp+78h] [rbp-3E0h] BYREF
  __int64 v219; // [rsp+88h] [rbp-3D0h]
  wchar_t *n; // [rsp+90h] [rbp-3C8h] BYREF
  __int64 *v221; // [rsp+98h] [rbp-3C0h] BYREF
  const wchar_t *v222; // [rsp+A0h] [rbp-3B8h] BYREF
  __int128 v223; // [rsp+A8h] [rbp-3B0h] BYREF
  __int64 v224; // [rsp+B8h] [rbp-3A0h]
  __int64 v225; // [rsp+C0h] [rbp-398h]
  DWORD nNumberOfBytesToRead[4]; // [rsp+C8h] [rbp-390h] BYREF
  LPVOID lpBuffer; // [rsp+D8h] [rbp-380h]
  __int64 v228; // [rsp+E0h] [rbp-378h] BYREF
  __int128 v229; // [rsp+E8h] [rbp-370h] BYREF
  __int64 v230; // [rsp+F8h] [rbp-360h]
  _BYTE v231[16]; // [rsp+100h] [rbp-358h] BYREF
  _QWORD v232[4]; // [rsp+110h] [rbp-348h] BYREF
  LPCWSTR v233; // [rsp+130h] [rbp-328h] BYREF
  LPCWSTR v234; // [rsp+138h] [rbp-320h] BYREF
  union _LARGE_INTEGER FileSize; // [rsp+140h] [rbp-318h] BYREF
  int v236; // [rsp+148h] [rbp-310h] BYREF
  union _LARGE_INTEGER NewFilePointer; // [rsp+150h] [rbp-308h] BYREF
  DWORD NumberOfBytesWritten[2]; // [rsp+158h] [rbp-300h] BYREF
  wchar_t *v239; // [rsp+160h] [rbp-2F8h] BYREF
  HANDLE hFile; // [rsp+168h] [rbp-2F0h] BYREF
  DWORD NumberOfBytesRead; // [rsp+170h] [rbp-2E8h] BYREF
  LPVOID pv; // [rsp+178h] [rbp-2E0h] BYREF
  LPVOID v243; // [rsp+180h] [rbp-2D8h] BYREF
  _QWORD v244[2]; // [rsp+188h] [rbp-2D0h] BYREF
  _QWORD v245[2]; // [rsp+198h] [rbp-2C0h] BYREF
  _QWORD v246[2]; // [rsp+1A8h] [rbp-2B0h] BYREF
  __int128 v247; // [rsp+1B8h] [rbp-2A0h] BYREF
  __int64 v248; // [rsp+1C8h] [rbp-290h]
  __int128 v249; // [rsp+1D0h] [rbp-288h] BYREF
  __int64 v250; // [rsp+1E0h] [rbp-278h]
  _QWORD v251[2]; // [rsp+1E8h] [rbp-270h] BYREF
  _QWORD v252[3]; // [rsp+1F8h] [rbp-260h] BYREF
  WCHAR TempFileName[264]; // [rsp+210h] [rbp-248h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+458h] [rbp+0h]

  v232[3] = -2;
  NumberOfBytesRead = a4;
  v5 = a3;
  v236 = a3;
  v8 = a5;
  v221 = a5;
  v9 = 0;
  lpFileName = 0;
  lpExistingFileName = 0;
  *(_OWORD *)nNumberOfBytesToRead = 0;
  lpBuffer = 0;
  v251[0] = 0;
  v251[1] = 0;
  try
  {
    v10 = operator new(0x40u);
    *v10 = v10;
    v10[1] = v10;
    v10[2] = v10;
    *((_WORD *)v10 + 12) = 257;
    v251[0] = v10;
    v249 = 0;
    v250 = 0;
    v247 = 0;
    v248 = 0;
    v243 = 0;
    pv = 0;
    v246[1] = 0;
    v11 = operator new(0x38u);
    *v11 = v11;
    v11[1] = v11;
    v11[2] = v11;
    *((_WORD *)v11 + 12) = 257;
    v246[0] = v11;
    v244[1] = 0;
    v12 = operator new(0x48u);
    *v12 = v12;
    v12[1] = v12;
    v12[2] = v12;
    *((_WORD *)v12 + 12) = 257;
    v244[0] = v12;
    v252[1] = 0;
    v13 = operator new(0x40u);
    *v13 = v13;
    v13[1] = v13;
    v13[2] = v13;
    *((_WORD *)v13 + 12) = 257;
    v252[0] = v13;
    PackageFileListPath = 0;
    v15 = *((_QWORD *)this + 75);
    if ( v15 )
    {
      v16 = L"TRUE";
      if ( !v5 )
        v16 = L"FALSE";
      CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
        v15,
        2,
        L"ProcessSandboxContainerPayload bInitialDownloadOnly: [%ws]",
        v16);
    }
    if ( !a2 )
    {
      PackageFileListPath = -2147024809;
      v17 = *((_QWORD *)this + 75);
      if ( v17 )
      {
        updated = CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
                    v17,
                    4,
                    L"%s(%d): Result = 0x%X",
                    L"CDeploymentSession::ProcessSandboxContainerPayload",
                    4083,
                    -2147024809);
        v18 = (unsigned int)updated;
        if ( updated < 0 )
          CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)updated);
      }
      else
      {
        v18 = 0;
      }
      goto LABEL_11;
    }
    v20 = *(_QWORD *)(a2 + 64);
    v21 = (const wchar_t *)(v20 + 168LL * *(unsigned int *)(a2 + 72));
    v222 = v21;
    while ( (const wchar_t *)v20 != v21 )
    {
      if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PlayB_ModelInstallation>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PlayB_ModelInstallation>::GetImpl'::`2'::impl)
        || !v8 )
      {
        v234 = 0;
        if ( !v5 )
          goto LABEL_22;
        if ( (v22 = *(_DWORD *)(v20 + 88), v22 <= 0xF) && (v23 = 36992, _bittest(&v23, v22))
          || *(_DWORD *)(v20 + 104) == 2
          || *((_DWORD *)this + 114) == 8 )
        {
          *((_DWORD *)this + 71) = 1;
LABEL_22:
          v24 = *(_QWORD *)(v20 + 112);
          v25 = (const wchar_t *)(v24 + 184LL * *(unsigned int *)(v20 + 120));
          *(_QWORD *)NumberOfBytesWritten = v25;
          while ( 2 )
          {
            if ( (const wchar_t *)v24 == v25 )
            {
              DH_SSTRING::~DH_SSTRING((DH_SSTRING *)&v234);
              v8 = v221;
              break;
            }
            v217 = 0;
            v218[0] = 0;
            v218[1] = 0;
            v219 = 0;
            v233 = 0;
            if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PlayB_ModelInstallation>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PlayB_ModelInstallation>::GetImpl'::`2'::impl) )
            {
              if ( !*(_QWORD *)(v24 + 48) || *(_DWORD *)(v20 + 88) == 24 )
                goto LABEL_118;
LABEL_29:
              if ( v5 )
              {
                v239 = *(wchar_t **)(v24 + 16);
                v26 = *(const WCHAR **)(v24 + 24);
                v233 = v26;
                goto LABEL_63;
              }
              if ( *(_BYTE *)(v24 + 153) )
              {
                LODWORD(hFile) = 0;
                v27 = (int)v234;
                if ( !v234 )
                {
                  PackageFileListPath = CDeploymentSession::GetPackageFileListPath(
                                          this,
                                          (const struct ActionList::Package *const)v20,
                                          (wchar_t **)&v234);
                  if ( PackageFileListPath < 0 )
                  {
                    v28 = *((_QWORD *)this + 75);
                    v29 = 0;
                    if ( !v28 )
                      goto LABEL_38;
                    dwFlagsAndAttributes[0] = PackageFileListPath;
                    dwCreationDisposition[0] = 4148;
                    v29 = (unsigned int)CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
                                          v28,
                                          4,
                                          L"%s(%d): Result = 0x%X",
                                          L"CDeploymentSession::ProcessSandboxContainerPayload",
                                          *(_QWORD *)dwCreationDisposition,
                                          *(_QWORD *)dwFlagsAndAttributes);
LABEL_36:
                    if ( (int)v29 < 0 )
                      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v29);
                    goto LABEL_38;
                  }
                  v27 = (int)v234;
                }
                PackageFileListPath = CDeploymentSession::ShouldDownloadRangelessFile(
                                        (_DWORD)this,
                                        v27,
                                        v24,
                                        (unsigned int)v252,
                                        (__int64)&hFile,
                                        0);
                if ( PackageFileListPath < 0 )
                {
                  v32 = *((_QWORD *)this + 75);
                  v29 = 0;
                  if ( v32 )
                  {
                    dwFlagsAndAttributes[0] = PackageFileListPath;
                    dwCreationDisposition[0] = 4151;
                    goto LABEL_45;
                  }
                  goto LABEL_38;
                }
                if ( !(_DWORD)hFile )
                  goto LABEL_118;
              }
              else if ( *(_DWORD *)(v20 + 104) == 2 )
              {
                v33 = *((_QWORD *)this + 75);
                if ( v33 )
                  CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(v33, 2, L"Express payload is found");
              }
              if ( *(_DWORD *)(v20 + 88) == 6
                && CDeploymentSession::IsPackageFileListEmpty(this, (const struct ActionList::Package *const)v20) )
              {
                if ( *(_QWORD *)&LogAdapter::g_Logger )
                  LogAdapter::Logger::LogNumObjects<char [21],wchar_t *>(
                    LogAdapter::g_Logger,
                    v34,
                    v35,
                    v36,
                    dwCreationDisposition[0],
                    v24 + 24);
                goto LABEL_118;
              }
              v26 = *(const WCHAR **)(v24 + 72);
              if ( v26 )
                v239 = *(wchar_t **)(v24 + 72);
              else
                v239 = *(wchar_t **)(v24 + 16);
              if ( NumberOfBytesRead )
                v26 = *(const WCHAR **)(v24 + 80);
              if ( !v26 )
                v26 = *(const WCHAR **)(v24 + 24);
              v233 = v26;
              v37 = *(const wchar_t **)(v24 + 112);
              if ( !v37 )
LABEL_63:
                v37 = *(const wchar_t **)(v24 + 40);
              if ( v9 )
              {
                ProcessHeap = GetProcessHeap();
                HeapFree(ProcessHeap, 0, (LPVOID)(v9 - 2));
                CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
                lpFileName = 0;
                v26 = v233;
              }
              PackageFileListPath = CMiscHelpersT<CEmptyType>::CombinePath(*((_QWORD *)this + 61), v26, 0, &lpFileName);
              if ( PackageFileListPath < 0 )
              {
                v32 = *((_QWORD *)this + 75);
                v29 = 0;
                if ( v32 )
                {
                  dwFlagsAndAttributes[0] = PackageFileListPath;
                  dwCreationDisposition[0] = 4190;
                  goto LABEL_45;
                }
LABEL_38:
                CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v29);
                goto LABEL_39;
              }
              v9 = lpFileName;
              FileAttributesW = GetFileAttributesW(lpFileName);
              v40 = FileAttributesW != -1 && (FileAttributesW & 0x10) == 0;
              CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
              CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
              PackageFileListPath = 0;
              if ( !v40 )
              {
                if ( (!NumberOfBytesRead || *((_BYTE *)this + 329)) && *(_QWORD *)(v24 + 48) )
                {
                  FileSize.QuadPart = 0;
                  v41 = _put___unique_any_t_V__unique_storage_U__resource_policy_PEA_WP6AJPEA_W__E_1_STRAPI_Release__YAJ0_ZU__integral_constant__K_0A__wistd__PEA_WPEA_W_0A___T_details_wil___details_wil___wil__QEAAPEAPEA_WXZ(&FileSize);
                  PackageFileListPath = CMiscHelpersT<CEmptyType>::CombinePath(
                                          *((_QWORD *)this + 61),
                                          *(_QWORD *)(v24 + 48),
                                          0,
                                          v41);
                  if ( PackageFileListPath < 0 )
                  {
                    v42 = *((_QWORD *)this + 75);
                    v43 = 0;
                    if ( v42 )
                    {
                      dwFlagsAndAttributes[0] = PackageFileListPath;
                      dwCreationDisposition[0] = 4205;
                      v44 = CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
                              v42,
                              4,
                              L"%s(%d): Result = 0x%X",
                              L"CDeploymentSession::ProcessSandboxContainerPayload",
                              *(_QWORD *)dwCreationDisposition,
                              *(_QWORD *)dwFlagsAndAttributes);
                      v43 = (unsigned int)v44;
                      if ( v44 < 0 )
                        CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v44);
                    }
                    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v43);
                    v45 = FileSize;
                    if ( FileSize.QuadPart )
                    {
                      v46 = GetProcessHeap();
                      HeapFree(v46, 0, (LPVOID)(v45.QuadPart - 4));
                      v29 = 0;
                      goto LABEL_38;
                    }
LABEL_39:
                    v30 = v234;
                    if ( !v234 )
                      goto LABEL_558;
                    v31 = GetProcessHeap();
                    HeapFree(v31, 0, (LPVOID)(v30 - 2));
                    v18 = 0;
LABEL_11:
                    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v18);
LABEL_558:
                    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)PackageFileListPath);
                    std::_Tree<std::_Tset_traits<std::wstring,WstringCaseInsensitiveCompare,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,WstringCaseInsensitiveCompare,std::allocator<std::wstring>,0>>(v252);
                    __1___Tree_V___Tmap_traits_V__basic_string_view__WU__char_traits__W_std___std__V__vector_UContainerPayload__2__ProcessSandboxContainerPayload_CDeploymentSession__QEAAJPEAUActionList__HHPEAV__vector_UUaLiteManagerDownloadRequest__V__allocator_UUaLiteManagerDownloadRequest___std___std___Z_V__allocator_UContainerPayload__2__ProcessSandboxContainerPayload_CDeploymentSession__QEAAJPEAUActionList__HHPEAV__vector_UUaLiteManagerDownloadRequest__V__allocator_UUaLiteManagerDownloadRequest___std___std___Z__6__2_UWstringCaseInsensitiveCompare__V__allocator_U__pair___CBV__basic_string_view__WU__char_traits__W_std___std__V__vector_UContainerPayload__2__ProcessSandboxContainerPayload_CDeploymentSession__QEAAJPEAUActionList__HHPEAV__vector_UUaLiteManagerDownloadRequest__V__allocator_UUaLiteManagerDownloadRequest___std___std___Z_V__allocator_UContainerPayload__2__ProcessSandboxContainerPayload_CDeploymentSession__QEAAJPEAUActionList__HHPEAV__vector_UUaLiteManagerDownloadRequest__V__allocator_UUaLiteManagerDownloadRequest___std___std___Z__6__2__std___2__0A__std___std__QEAA_XZ(v244);
                    std::map<std::wstring_view,bool,WstringCaseInsensitiveCompare,std::allocator<std::pair<std::wstring_view const,bool>>>::~map<std::wstring_view,bool,WstringCaseInsensitiveCompare,std::allocator<std::pair<std::wstring_view const,bool>>>(v246);
                    if ( pv )
                      CoTaskMemFree(pv);
                    if ( v243 )
                      CoTaskMemFree(v243);
                    std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>::~vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>(&v247);
                    std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>::~vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>(&v249);
                    std::_Tree<std::_Tset_traits<std::wstring,WstringCaseInsensitiveCompare,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,WstringCaseInsensitiveCompare,std::allocator<std::wstring>,0>>(v251);
                    Windows::Auto<_LUTF8_STRING>::~Auto<_LUTF8_STRING>(nNumberOfBytesToRead);
                    DH_SSTRING::~DH_SSTRING((DH_SSTRING *)&lpExistingFileName);
                    DH_SSTRING::~DH_SSTRING((DH_SSTRING *)&lpFileName);
                    return (unsigned int)PackageFileListPath;
                  }
                  if ( (unsigned int)((__int64 (__fastcall *)(_QWORD))FileExists)((union _LARGE_INTEGER)FileSize.QuadPart) )
                  {
                    QuadPart = FileSize.QuadPart;
                    LogAdapter::TraceInfo<wchar_t const *,wchar_t *>("Extracting [{}] from [{}]", &v233, &QuadPart);
                    FileFromWim = CDeploymentSession::ExtractFileFromWim(
                                    v47,
                                    (const wchar_t *const)FileSize.QuadPart,
                                    v233,
                                    v9);
                    if ( FileFromWim < 0 )
                      wil::details::in1diag3::Throw_Hr(
                        retaddr,
                        (void *)0x1072,
                        (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\DeploymentSessionImpl.h",
                        (const char *)(unsigned int)FileFromWim,
                        dwCreationDisposition[0]);
                    v223 = 0;
                    v224 = 0;
                    v225 = 0;
                    v49 = -1;
                    do
                      ++v49;
                    while ( *(_WORD *)(FileSize.QuadPart + 2 * v49) );
                    ((void (__fastcall *)(_QWORD, _QWORD))std::wstring::_Construct<1,wchar_t const *>)(
                      &v223,
                      (union _LARGE_INTEGER)FileSize.QuadPart);
                    std::_Tree<std::_Tset_traits<std::wstring,WstringCaseInsensitiveCompare,std::allocator<std::wstring>,0>>::_Emplace<std::wstring>(
                      v251,
                      v231,
                      &v223);
                    std::wstring::~wstring(&v223);
                  }
                  v50 = FileSize;
                  if ( FileSize.QuadPart )
                  {
                    v51 = GetProcessHeap();
                    HeapFree(v51, 0, (LPVOID)(v50.QuadPart - 4));
                    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
                  }
                }
                else
                {
                  v52 = (const wchar_t **)(v24 + 48);
                  std::_Tree<std::_Tmap_traits<std::wstring_view,std::wstring_view,WstringCaseInsensitiveCompare,std::allocator<std::pair<std::wstring_view const,std::wstring_view>>,0>>::find<wchar_t *,WstringCaseInsensitiveCompare,0>(
                    v246,
                    &v215,
                    v24 + 48);
                  if ( v215 == v246[0] )
                  {
                    if ( lpExistingFileName )
                    {
                      v53 = (WCHAR *)(lpExistingFileName - 2);
                      v54 = GetProcessHeap();
                      HeapFree(v54, 0, v53);
                      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
                      lpExistingFileName = 0;
                    }
                    PackageFileListPath = CMiscHelpersT<CEmptyType>::CombinePath(
                                            *((_QWORD *)this + 61),
                                            *v52,
                                            0,
                                            &lpExistingFileName);
                    if ( PackageFileListPath < 0 )
                    {
                      v32 = *((_QWORD *)this + 75);
                      v29 = 0;
                      if ( !v32 )
                        goto LABEL_38;
                      dwFlagsAndAttributes[0] = PackageFileListPath;
                      dwCreationDisposition[0] = 4225;
LABEL_45:
                      v29 = (unsigned int)CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
                                            v32,
                                            4,
                                            L"%s(%d): Result = 0x%X",
                                            L"CDeploymentSession::ProcessSandboxContainerPayload",
                                            *(_QWORD *)dwCreationDisposition,
                                            *(_QWORD *)dwFlagsAndAttributes);
                      goto LABEL_36;
                    }
                    v55 = GetFileAttributesW(lpExistingFileName);
                    v56 = v55 != -1 && (v55 & 0x10) == 0;
                    LODWORD(hFile) = v56;
                    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
                    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
                    PackageFileListPath = 0;
                    std::_Tree<std::_Tmap_traits<std::wstring_view,bool,WstringCaseInsensitiveCompare,std::allocator<std::pair<std::wstring_view const,bool>>,0>>::emplace<wchar_t * const &,int &>(
                      v246,
                      v232,
                      v24 + 48,
                      &hFile);
                  }
                  else
                  {
                    v56 = *(unsigned __int8 *)(v215 + 48);
                    LODWORD(hFile) = v56;
                  }
                  if ( v56 )
                  {
                    std::_Tree<std::_Tmap_traits<std::wstring_view,std::wstring_view,WstringCaseInsensitiveCompare,std::allocator<std::pair<std::wstring_view const,std::wstring_view>>,0>>::find<wchar_t *,WstringCaseInsensitiveCompare,0>(
                      v244,
                      &NewFilePointer,
                      v24 + 48);
                    if ( NewFilePointer.QuadPart == v244[0] )
                    {
                      v229 = 0;
                      v230 = 0;
                      ___emplace_AEBQEB_WV__vector_UContainerPayload__2__ProcessSandboxContainerPayload_CDeploymentSession__QEAAJPEAUActionList__HHPEAV__vector_UUaLiteManagerDownloadRequest__V__allocator_UUaLiteManagerDownloadRequest___std___std___Z_V__allocator_UContainerPayload__2__ProcessSandboxContainerPayload_CDeploymentSession__QEAAJPEAUActionList__HHPEAV__vector_UUaLiteManagerDownloadRequest__V__allocator_UUaLiteManagerDownloadRequest___std___std___Z__6__std______Tree_V___Tmap_traits_V__basic_string_view__WU__char_traits__W_std___std__V__vector_UContainerPayload__2__ProcessSandboxContainerPayload_CDeploymentSession__QEAAJPEAUActionList__HHPEAV__vector_UUaLiteManagerDownloadRequest__V__allocator_UUaLiteManagerDownloadRequest___std___std___Z_V__allocator_UContainerPayload__2__ProcessSandboxContainerPayload_CDeploymentSession__QEAAJPEAUActionList__HHPEAV__vector_UUaLiteManagerDownloadRequest__V__allocator_UUaLiteManagerDownloadRequest___std___std___Z__6__2_UWstringCaseInsensitiveCompare__V__allocator_U__pair___CBV__basic_string_view__WU__char_traits__W_std___std__V__vector_UContainerPayload__2__ProcessSandboxContainerPayload_CDeploymentSession__QEAAJPEAUActionList__HHPEAV__vector_UUaLiteManagerDownloadRequest__V__allocator_UUaLiteManagerDownloadRequest___std___std___Z_V__allocator_UContainerPayload__2__ProcessSandboxContainerPayload_CDeploymentSession__QEAAJPEAUActionList__HHPEAV__vector_UUaLiteManagerDownloadRequest__V__allocator_UUaLiteManagerDownloadRequest___std___std___Z__6__2__std___2__0A__std___std__QEAA_AU__pair_V___Tree_iterator_V___Tree_val_U___Tree_simple_types_U__pair___CBV__basic_string_view__WU__char_traits__W_std___std__V__vector_UContainerPayload__2__ProcessSandboxContainerPayload_CDeploymentSession__QEAAJPEAUActionList__HHPEAV__vector_UUaLiteManagerDownloadRequest__V__allocator_UUaLiteManagerDownloadRequest___std___std___Z_V__allocator_UContainerPayload__2__ProcessSandboxContainerPayload_CDeploymentSession__QEAAJPEAUActionList__HHPEAV__vector_UUaLiteManagerDownloadRequest__V__allocator_UUaLiteManagerDownloadRequest___std___std___Z__6__2__std___std___std___std___N_1_AEBQEB_W__QEAV__vector_UContainerPayload__2__ProcessSandboxContainerPayload_CDeploymentSession__QEAAJPEAUActionList__HHPEAV__vector_UUaLiteManagerDownloadRequest__V__allocator_UUaLiteManagerDownloadRequest___std___std___Z_V__allocator_UContainerPayload__2__ProcessSandboxContainerPayload_CDeploymentSession__QEAAJPEAUActionList__HHPEAV__vector_UUaLiteManagerDownloadRequest__V__allocator_UUaLiteManagerDownloadRequest___std___std___Z__6__1__Z(
                        v244,
                        v245,
                        v24 + 48,
                        &v229);
                      __1__vector_UContainerPayload__2__ProcessSandboxContainerPayload_CDeploymentSession__QEAAJPEAUActionList__HHPEAV__vector_UUaLiteManagerDownloadRequest__V__allocator_UUaLiteManagerDownloadRequest___std___std___Z_V__allocator_UContainerPayload__2__ProcessSandboxContainerPayload_CDeploymentSession__QEAAJPEAUActionList__HHPEAV__vector_UUaLiteManagerDownloadRequest__V__allocator_UUaLiteManagerDownloadRequest___std___std___Z__6__std__QEAA_XZ(&v229);
                      v57 = v245[0] + 48LL;
                    }
                    else
                    {
                      v57 = NewFilePointer.QuadPart + 48;
                    }
                    *(_QWORD *)&v217 = v233;
                    *((_QWORD *)&v217 + 1) = v37;
                    if ( v236 || *(_DWORD *)(v24 + 8) != 2 || (v58 = *(_BYTE *)(v24 + 153) == 0, LOBYTE(v219) = 1, !v58) )
                      LOBYTE(v219) = 0;
                    PackageFileListPath = CDeploymentSession::GetOffsetInOuterContainer(
                                            this,
                                            *v52,
                                            *(const wchar_t **)(v24 + 56),
                                            v239,
                                            v37,
                                            v218,
                                            &v218[1]);
                    if ( PackageFileListPath < 0 )
                    {
                      v59 = *((_QWORD *)this + 75);
                      v60 = 0;
                      if ( v59 )
                      {
                        dwFlagsAndAttributes[0] = PackageFileListPath;
                        dwCreationDisposition[0] = 4262;
                        v61 = CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
                                v59,
                                4,
                                L"%s(%d): Result = 0x%X",
                                L"CDeploymentSession::ProcessSandboxContainerPayload",
                                *(_QWORD *)dwCreationDisposition,
                                *(_QWORD *)dwFlagsAndAttributes);
                        v60 = (unsigned int)v61;
                        if ( v61 < 0 )
                          CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v61);
                      }
                      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v60);
                      DH_SSTRING::~DH_SSTRING((DH_SSTRING *)&v234);
                      goto LABEL_558;
                    }
                    v62 = *(_QWORD *)(v57 + 8);
                    if ( v62 == *(_QWORD *)(v57 + 16) )
                    {
                      ____Emplace_reallocate_UContainerPayload__2__ProcessSandboxContainerPayload_CDeploymentSession__QEAAJPEAUActionList__HHPEAV__vector_UUaLiteManagerDownloadRequest__V__allocator_UUaLiteManagerDownloadRequest___std___std___Z____vector_UContainerPayload__2__ProcessSandboxContainerPayload_CDeploymentSession__QEAAJPEAUActionList__HHPEAV__vector_UUaLiteManagerDownloadRequest__V__allocator_UUaLiteManagerDownloadRequest___std___std___Z_V__allocator_UContainerPayload__2__ProcessSandboxContainerPayload_CDeploymentSession__QEAAJPEAUActionList__HHPEAV__vector_UUaLiteManagerDownloadRequest__V__allocator_UUaLiteManagerDownloadRequest___std___std___Z__6__std__AEAAPEAUContainerPayload__2__ProcessSandboxContainerPayload_CDeploymentSession__QEAAJPEAUActionList__HHPEAV__vector_UUaLiteManagerDownloadRequest__V__allocator_UUaLiteManagerDownloadRequest___std___1__Z_QEAU2_2__34_QEAAJ0HH1_Z___QEAU2_2__34_QEAAJ0HH1_Z__Z(
                        v57,
                        v62,
                        &v217);
                    }
                    else
                    {
                      *(_OWORD *)v62 = v217;
                      *(_OWORD *)(v62 + 16) = *(_OWORD *)v218;
                      *(_QWORD *)(v62 + 32) = v219;
                      *(_QWORD *)(v57 + 8) += 40LL;
                    }
                  }
                  v9 = lpFileName;
                }
              }
              v5 = v236;
            }
            else if ( *(_QWORD *)(v24 + 48) )
            {
              goto LABEL_29;
            }
LABEL_118:
            v24 += 184;
            v25 = *(const wchar_t **)NumberOfBytesWritten;
            continue;
          }
        }
      }
      v20 += 168;
      v21 = v222;
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PlayB_ModelInstallation>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PlayB_ModelInstallation>::GetImpl'::`2'::impl)
      && v8 )
    {
      v245[0] = 0;
      v245[1] = 0;
      v64 = std::_Allocate<16,std::_Default_allocate_traits>(64);
      *(_QWORD *)v64 = v64;
      *(_QWORD *)(v64 + 8) = v64;
      *(_QWORD *)(v64 + 16) = v64;
      *(_WORD *)(v64 + 24) = 257;
      v245[0] = v64;
      v65 = *v8;
      v66 = v8[1];
      m = v66;
      while ( v65 != v66 )
      {
        v234 = 0;
        LODWORD(hFile) = 0;
        v232[2] = 0;
        v67 = *(__int64 **)(v65 + 96);
        v68 = *v67;
        v234 = 0;
        PackageFileListPath = (*(__int64 (__fastcall **)(__int64 *, LPCWSTR *))(v68 + 40))(v67, &v234);
        if ( PackageFileListPath < 0 )
        {
          v69 = *((_QWORD *)this + 75);
          v70 = 0;
          if ( v69 )
          {
            dwFlagsAndAttributes[0] = PackageFileListPath;
            dwCreationDisposition[0] = 4279;
            v71 = CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
                    v69,
                    4,
                    L"%s(%d): Result = 0x%X",
                    L"CDeploymentSession::ProcessSandboxContainerPayload",
                    *(_QWORD *)dwCreationDisposition,
                    *(_QWORD *)dwFlagsAndAttributes);
            v70 = (unsigned int)v71;
            if ( v71 < 0 )
              CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v71);
          }
LABEL_134:
          CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v70);
          if ( v234 )
            (*(void (__fastcall **)(LPCWSTR))(*(_QWORD *)v234 + 16LL))(v234);
          goto LABEL_136;
        }
        PackageFileListPath = (*(__int64 (__fastcall **)(LPCWSTR, HANDLE *))(*(_QWORD *)v234 + 24LL))(v234, &hFile);
        if ( PackageFileListPath < 0 )
        {
          v72 = *((_QWORD *)this + 75);
          v70 = 0;
          if ( v72 )
          {
            dwFlagsAndAttributes[0] = PackageFileListPath;
            dwCreationDisposition[0] = 4280;
            v73 = CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
                    v72,
                    4,
                    L"%s(%d): Result = 0x%X",
                    L"CDeploymentSession::ProcessSandboxContainerPayload",
                    *(_QWORD *)dwCreationDisposition,
                    *(_QWORD *)dwFlagsAndAttributes);
            v70 = (unsigned int)v73;
            if ( v73 < 0 )
              CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v73);
          }
          goto LABEL_134;
        }
        for ( i = 0; i < (unsigned int)hFile; ++i )
        {
          v217 = 0;
          v218[0] = 0;
          v218[1] = 0;
          v219 = 0;
          FileSize.QuadPart = 0;
          NewFilePointer.QuadPart = 0;
          v215 = 0;
          QuadPart = 0;
          v236 = 0;
          v233 = 0;
          if ( *(_QWORD *)(v65 + 24) <= 7u )
            v75 = (wchar_t *)v65;
          else
            v75 = *(wchar_t **)v65;
          v239 = v75;
          v76 = *(_QWORD *)v234;
          FileSize.QuadPart = 0;
          PackageFileListPath = (*(__int64 (__fastcall **)(LPCWSTR, _QWORD, union _LARGE_INTEGER *))(v76 + 32))(
                                  v234,
                                  i,
                                  &FileSize);
          if ( PackageFileListPath < 0 )
          {
            v77 = *((_QWORD *)this + 75);
            v78 = 0;
            if ( v77 )
            {
              dwFlagsAndAttributes[0] = PackageFileListPath;
              dwCreationDisposition[0] = 4296;
              v79 = CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
                      v77,
                      4,
                      L"%s(%d): Result = 0x%X",
                      L"CDeploymentSession::ProcessSandboxContainerPayload",
                      *(_QWORD *)dwCreationDisposition,
                      *(_QWORD *)dwFlagsAndAttributes);
              v78 = (unsigned int)v79;
              if ( v79 < 0 )
                CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v79);
            }
            CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v78);
            v80 = v233;
            if ( v233 )
            {
              v81 = GetProcessHeap();
              HeapFree(v81, 0, (LPVOID)(v80 - 2));
              CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
            }
            if ( NewFilePointer.QuadPart )
              (*(void (__fastcall **)(union _LARGE_INTEGER))(*(_QWORD *)NewFilePointer.QuadPart + 16LL))(NewFilePointer);
            if ( FileSize.QuadPart )
              (*(void (__fastcall **)(union _LARGE_INTEGER))(*(_QWORD *)FileSize.QuadPart + 16LL))(FileSize);
LABEL_255:
            if ( v234 )
              (*(void (__fastcall **)(LPCWSTR))(*(_QWORD *)v234 + 16LL))(v234);
            goto LABEL_136;
          }
          wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>::put(&v243);
          wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>::put(&pv);
          v82 = FileSize;
          v83 = *(__int64 (__fastcall **)(union _LARGE_INTEGER, __int64))(*(_QWORD *)FileSize.QuadPart + 24LL);
          v84 = wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>::put(&v243);
          PackageFileListPath = ((__int64 (__fastcall *)(_QWORD, _QWORD))v83)((union _LARGE_INTEGER)v82.QuadPart, v84);
          if ( PackageFileListPath < 0 )
          {
            v85 = *((_QWORD *)this + 75);
            v86 = 0;
            if ( v85 )
            {
              dwFlagsAndAttributes[0] = PackageFileListPath;
              dwCreationDisposition[0] = 4300;
              v87 = CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
                      v85,
                      4,
                      L"%s(%d): Result = 0x%X",
                      L"CDeploymentSession::ProcessSandboxContainerPayload",
                      *(_QWORD *)dwCreationDisposition,
                      *(_QWORD *)dwFlagsAndAttributes);
              v86 = (unsigned int)v87;
              if ( v87 < 0 )
                CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v87);
            }
            CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v86);
            if ( v233 )
              STRAPI_Release((wchar_t *)v233);
            if ( NewFilePointer.QuadPart )
              (*(void (__fastcall **)(union _LARGE_INTEGER))(*(_QWORD *)NewFilePointer.QuadPart + 16LL))(NewFilePointer);
            if ( FileSize.QuadPart )
              (*(void (__fastcall **)(union _LARGE_INTEGER))(*(_QWORD *)FileSize.QuadPart + 16LL))(FileSize);
            goto LABEL_255;
          }
          v88 = FileSize;
          v89 = *(__int64 (__fastcall **)(union _LARGE_INTEGER, __int64))(*(_QWORD *)FileSize.QuadPart + 40LL);
          v90 = wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>::put(&pv);
          v91 = ((__int64 (__fastcall *)(_QWORD, _QWORD))v89)((union _LARGE_INTEGER)v88.QuadPart, v90);
          PackageFileListPath = v91;
          if ( v91 < 0 )
          {
            CMoUpdateLogT<CEmptyType>::MoUpdateLogError(
              *((_QWORD *)this + 75),
              (unsigned int)v91,
              L"CDeploymentSession::ProcessSandboxContainerPayload",
              4301);
            if ( v233 )
              STRAPI_Release((wchar_t *)v233);
            if ( NewFilePointer.QuadPart )
              (*(void (__fastcall **)(union _LARGE_INTEGER))(*(_QWORD *)NewFilePointer.QuadPart + 16LL))(NewFilePointer);
            if ( FileSize.QuadPart )
              (*(void (__fastcall **)(union _LARGE_INTEGER))(*(_QWORD *)FileSize.QuadPart + 16LL))(FileSize);
            goto LABEL_255;
          }
          v92 = FileSize;
          v93 = *(__int64 (__fastcall **)(union _LARGE_INTEGER, union _LARGE_INTEGER *))(*(_QWORD *)FileSize.QuadPart
                                                                                       + 48LL);
          v94 = (_QWORD *)NewFilePointer.QuadPart;
          NewFilePointer.QuadPart = 0;
          if ( v94 )
            (*(void (__fastcall **)(_QWORD *, _QWORD))(*v94 + 16LL))(v94, *v94);
          v95 = ((__int64 (__fastcall *)(_QWORD, _QWORD))v93)((union _LARGE_INTEGER)v92.QuadPart, &NewFilePointer);
          PackageFileListPath = v95;
          if ( v95 < 0 )
          {
            CMoUpdateLogT<CEmptyType>::MoUpdateLogError(
              *((_QWORD *)this + 75),
              (unsigned int)v95,
              L"CDeploymentSession::ProcessSandboxContainerPayload",
              4302);
            if ( v233 )
              STRAPI_Release((wchar_t *)v233);
            if ( NewFilePointer.QuadPart )
              (*(void (__fastcall **)(union _LARGE_INTEGER))(*(_QWORD *)NewFilePointer.QuadPart + 16LL))(NewFilePointer);
            if ( FileSize.QuadPart )
              (*(void (__fastcall **)(union _LARGE_INTEGER))(*(_QWORD *)FileSize.QuadPart + 16LL))(FileSize);
            goto LABEL_255;
          }
          v96 = (*(__int64 (__fastcall **)(union _LARGE_INTEGER, int *))(*(_QWORD *)NewFilePointer.QuadPart + 24LL))(
                  NewFilePointer,
                  &v236);
          PackageFileListPath = v96;
          if ( v96 < 0 )
          {
            CMoUpdateLogT<CEmptyType>::MoUpdateLogError(
              *((_QWORD *)this + 75),
              (unsigned int)v96,
              L"CDeploymentSession::ProcessSandboxContainerPayload",
              4303);
            if ( v233 )
              STRAPI_Release((wchar_t *)v233);
            if ( NewFilePointer.QuadPart )
              (*(void (__fastcall **)(union _LARGE_INTEGER))(*(_QWORD *)NewFilePointer.QuadPart + 16LL))(NewFilePointer);
            if ( FileSize.QuadPart )
              (*(void (__fastcall **)(union _LARGE_INTEGER))(*(_QWORD *)FileSize.QuadPart + 16LL))(FileSize);
            goto LABEL_255;
          }
          v97 = _put___unique_any_t_V__unique_storage_U__resource_policy_PEA_WP6AJPEA_W__E_1_STRAPI_Release__YAJ0_ZU__integral_constant__K_0A__wistd__PEA_WPEA_W_0A___T_details_wil___details_wil___wil__QEAAPEAPEA_WXZ(&v233);
          v98 = CMiscHelpersT<CEmptyType>::CombinePath(*((_QWORD *)this + 61), pv, 0, v97);
          PackageFileListPath = v98;
          if ( v98 < 0 )
          {
            CMoUpdateLogT<CEmptyType>::MoUpdateLogError(
              *((_QWORD *)this + 75),
              (unsigned int)v98,
              L"CDeploymentSession::ProcessSandboxContainerPayload",
              4305);
            if ( v233 )
              STRAPI_Release((wchar_t *)v233);
            if ( NewFilePointer.QuadPart )
              (*(void (__fastcall **)(union _LARGE_INTEGER))(*(_QWORD *)NewFilePointer.QuadPart + 16LL))(NewFilePointer);
            if ( FileSize.QuadPart )
              (*(void (__fastcall **)(union _LARGE_INTEGER))(*(_QWORD *)FileSize.QuadPart + 16LL))(FileSize);
            goto LABEL_255;
          }
          v99 = GetFileAttributesW(v233);
          v100 = v99 != -1 && (v99 & 0x10) == 0;
          CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
          CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
          PackageFileListPath = 0;
          if ( v100 )
          {
            __1__unique_any_t_V__unique_storage_U__resource_policy_PEA_WP6AJPEA_W__E_1_STRAPI_Release__YAJ0_ZU__integral_constant__K_0A__wistd__PEA_WPEA_W_0A___T_details_wil___details_wil___wil__QEAA_XZ(&v233);
            if ( NewFilePointer.QuadPart )
              (*(void (__fastcall **)(union _LARGE_INTEGER))(*(_QWORD *)NewFilePointer.QuadPart + 16LL))(NewFilePointer);
          }
          else if ( (!NumberOfBytesRead || *((_BYTE *)this + 329)) && v75 )
          {
            *(_QWORD *)NumberOfBytesWritten = 0;
            v101 = _put___unique_any_t_V__unique_storage_U__resource_policy_PEA_WP6AJPEA_W__E_1_STRAPI_Release__YAJ0_ZU__integral_constant__K_0A__wistd__PEA_WPEA_W_0A___T_details_wil___details_wil___wil__QEAAPEAPEA_WXZ(NumberOfBytesWritten);
            v102 = CMiscHelpersT<CEmptyType>::CombinePath(*((_QWORD *)this + 61), v75, 0, v101);
            PackageFileListPath = v102;
            if ( v102 < 0 )
            {
              CMoUpdateLogT<CEmptyType>::MoUpdateLogError(
                *((_QWORD *)this + 75),
                (unsigned int)v102,
                L"CDeploymentSession::ProcessSandboxContainerPayload",
                4320);
              __1__unique_any_t_V__unique_storage_U__resource_policy_PEA_WP6AJPEA_W__E_1_STRAPI_Release__YAJ0_ZU__integral_constant__K_0A__wistd__PEA_WPEA_W_0A___T_details_wil___details_wil___wil__QEAA_XZ(NumberOfBytesWritten);
              __1__unique_any_t_V__unique_storage_U__resource_policy_PEA_WP6AJPEA_W__E_1_STRAPI_Release__YAJ0_ZU__integral_constant__K_0A__wistd__PEA_WPEA_W_0A___T_details_wil___details_wil___wil__QEAA_XZ(&v233);
              if ( NewFilePointer.QuadPart )
                (*(void (__fastcall **)(union _LARGE_INTEGER))(*(_QWORD *)NewFilePointer.QuadPart + 16LL))(NewFilePointer);
              if ( FileSize.QuadPart )
                (*(void (__fastcall **)(union _LARGE_INTEGER))(*(_QWORD *)FileSize.QuadPart + 16LL))(FileSize);
              if ( v234 )
                (*(void (__fastcall **)(LPCWSTR))(*(_QWORD *)v234 + 16LL))(v234);
              goto LABEL_136;
            }
            if ( (unsigned int)FileExists(*(_QWORD *)NumberOfBytesWritten) )
            {
              v222 = *(const wchar_t **)NumberOfBytesWritten;
              v221 = (__int64 *)pv;
              LogAdapter::TraceInfo<wchar_t const *,wchar_t *>("Extracting [{}] from [{}]", &v221, &v222);
              v104 = CDeploymentSession::ExtractFileFromWim(
                       v103,
                       *(const wchar_t *const *)NumberOfBytesWritten,
                       (const wchar_t *const)pv,
                       v233);
              if ( v104 < 0 )
                wil::details::in1diag3::Throw_Hr(
                  retaddr,
                  (void *)0x10E5,
                  (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\DeploymentSessionImpl.h",
                  (const char *)(unsigned int)v104,
                  dwCreationDisposition[0]);
            }
            __1__unique_any_t_V__unique_storage_U__resource_policy_PEA_WP6AJPEA_W__E_1_STRAPI_Release__YAJ0_ZU__integral_constant__K_0A__wistd__PEA_WPEA_W_0A___T_details_wil___details_wil___wil__QEAA_XZ(NumberOfBytesWritten);
            __1__unique_any_t_V__unique_storage_U__resource_policy_PEA_WP6AJPEA_W__E_1_STRAPI_Release__YAJ0_ZU__integral_constant__K_0A__wistd__PEA_WPEA_W_0A___T_details_wil___details_wil___wil__QEAA_XZ(&v233);
            if ( NewFilePointer.QuadPart )
              (*(void (__fastcall **)(union _LARGE_INTEGER))(*(_QWORD *)NewFilePointer.QuadPart + 16LL))(NewFilePointer);
          }
          else
          {
            std::_Tree<std::_Tmap_traits<std::wstring_view,std::wstring_view,WstringCaseInsensitiveCompare,std::allocator<std::pair<std::wstring_view const,std::wstring_view>>,0>>::find<wchar_t *,WstringCaseInsensitiveCompare,0>(
              v246,
              &v228,
              &v239);
            if ( v228 == v246[0] )
            {
              SH_SSTRING::operator=(&lpExistingFileName);
              v105 = CMiscHelpersT<CEmptyType>::CombinePath(*((_QWORD *)this + 61), v75, 0, &lpExistingFileName);
              PackageFileListPath = v105;
              if ( v105 < 0 )
              {
                CMoUpdateLogT<CEmptyType>::MoUpdateLogError(
                  *((_QWORD *)this + 75),
                  (unsigned int)v105,
                  L"CDeploymentSession::ProcessSandboxContainerPayload",
                  4339);
                __1__unique_any_t_V__unique_storage_U__resource_policy_PEA_WP6AJPEA_W__E_1_STRAPI_Release__YAJ0_ZU__integral_constant__K_0A__wistd__PEA_WPEA_W_0A___T_details_wil___details_wil___wil__QEAA_XZ(&v233);
                if ( NewFilePointer.QuadPart )
                  (*(void (__fastcall **)(union _LARGE_INTEGER))(*(_QWORD *)NewFilePointer.QuadPart + 16LL))(NewFilePointer);
                if ( FileSize.QuadPart )
                  (*(void (__fastcall **)(union _LARGE_INTEGER))(*(_QWORD *)FileSize.QuadPart + 16LL))(FileSize);
                goto LABEL_255;
              }
              v106 = GetFileAttributesW(lpExistingFileName);
              v107 = v106 != -1 && (v106 & 0x10) == 0;
              NumberOfBytesWritten[0] = v107;
              CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
              CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
              PackageFileListPath = 0;
              std::_Tree<std::_Tmap_traits<std::wstring_view,bool,WstringCaseInsensitiveCompare,std::allocator<std::pair<std::wstring_view const,bool>>,0>>::emplace<wchar_t * const &,int &>(
                v246,
                &v229,
                &v239,
                NumberOfBytesWritten);
            }
            else
            {
              v107 = *(unsigned __int8 *)(v228 + 48);
              NumberOfBytesWritten[0] = v107;
            }
            if ( v107 )
            {
              std::_Tree<std::_Tmap_traits<std::wstring_view,std::wstring_view,WstringCaseInsensitiveCompare,std::allocator<std::pair<std::wstring_view const,std::wstring_view>>,0>>::find<wchar_t *,WstringCaseInsensitiveCompare,0>(
                v244,
                &n,
                &v239);
              if ( n == (wchar_t *)v244[0] )
              {
                v223 = 0;
                v224 = 0;
                ___emplace_AEBQEB_WV__vector_UContainerPayload__2__ProcessSandboxContainerPayload_CDeploymentSession__QEAAJPEAUActionList__HHPEAV__vector_UUaLiteManagerDownloadRequest__V__allocator_UUaLiteManagerDownloadRequest___std___std___Z_V__allocator_UContainerPayload__2__ProcessSandboxContainerPayload_CDeploymentSession__QEAAJPEAUActionList__HHPEAV__vector_UUaLiteManagerDownloadRequest__V__allocator_UUaLiteManagerDownloadRequest___std___std___Z__6__std______Tree_V___Tmap_traits_V__basic_string_view__WU__char_traits__W_std___std__V__vector_UContainerPayload__2__ProcessSandboxContainerPayload_CDeploymentSession__QEAAJPEAUActionList__HHPEAV__vector_UUaLiteManagerDownloadRequest__V__allocator_UUaLiteManagerDownloadRequest___std___std___Z_V__allocator_UContainerPayload__2__ProcessSandboxContainerPayload_CDeploymentSession__QEAAJPEAUActionList__HHPEAV__vector_UUaLiteManagerDownloadRequest__V__allocator_UUaLiteManagerDownloadRequest___std___std___Z__6__2_UWstringCaseInsensitiveCompare__V__allocator_U__pair___CBV__basic_string_view__WU__char_traits__W_std___std__V__vector_UContainerPayload__2__ProcessSandboxContainerPayload_CDeploymentSession__QEAAJPEAUActionList__HHPEAV__vector_UUaLiteManagerDownloadRequest__V__allocator_UUaLiteManagerDownloadRequest___std___std___Z_V__allocator_UContainerPayload__2__ProcessSandboxContainerPayload_CDeploymentSession__QEAAJPEAUActionList__HHPEAV__vector_UUaLiteManagerDownloadRequest__V__allocator_UUaLiteManagerDownloadRequest___std___std___Z__6__2__std___2__0A__std___std__QEAA_AU__pair_V___Tree_iterator_V___Tree_val_U___Tree_simple_types_U__pair___CBV__basic_string_view__WU__char_traits__W_std___std__V__vector_UContainerPayload__2__ProcessSandboxContainerPayload_CDeploymentSession__QEAAJPEAUActionList__HHPEAV__vector_UUaLiteManagerDownloadRequest__V__allocator_UUaLiteManagerDownloadRequest___std___std___Z_V__allocator_UContainerPayload__2__ProcessSandboxContainerPayload_CDeploymentSession__QEAAJPEAUActionList__HHPEAV__vector_UUaLiteManagerDownloadRequest__V__allocator_UUaLiteManagerDownloadRequest___std___std___Z__6__2__std___std___std___std___N_1_AEBQEB_W__QEAV__vector_UContainerPayload__2__ProcessSandboxContainerPayload_CDeploymentSession__QEAAJPEAUActionList__HHPEAV__vector_UUaLiteManagerDownloadRequest__V__allocator_UUaLiteManagerDownloadRequest___std___std___Z_V__allocator_UContainerPayload__2__ProcessSandboxContainerPayload_CDeploymentSession__QEAAJPEAUActionList__HHPEAV__vector_UUaLiteManagerDownloadRequest__V__allocator_UUaLiteManagerDownloadRequest___std___std___Z__6__1__Z(
                  v244,
                  v232,
                  &v239,
                  &v223);
                __1__vector_UContainerPayload__2__ProcessSandboxContainerPayload_CDeploymentSession__QEAAJPEAUActionList__HHPEAV__vector_UUaLiteManagerDownloadRequest__V__allocator_UUaLiteManagerDownloadRequest___std___std___Z_V__allocator_UContainerPayload__2__ProcessSandboxContainerPayload_CDeploymentSession__QEAAJPEAUActionList__HHPEAV__vector_UUaLiteManagerDownloadRequest__V__allocator_UUaLiteManagerDownloadRequest___std___std___Z__6__std__QEAA_XZ(&v223);
                v108 = v232[0] + 48LL;
              }
              else
              {
                v108 = (__int64)(n + 24);
              }
              v109 = to_wstring(&v223, v243);
              std::_Tree<std::_Tset_traits<std::wstring,WstringCaseInsensitiveCompare,std::allocator<std::wstring>,0>>::_Emplace<std::wstring>(
                v245,
                v231,
                v109);
              std::wstring::~wstring(&v223);
              if ( v231[8] )
              {
                if ( *((_QWORD *)&v249 + 1) == v250 )
                {
                  std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>::_Emplace_reallocate<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>(
                    &v249,
                    *((_QWORD *)&v249 + 1),
                    &pv);
                  v110 = *((_QWORD *)&v249 + 1);
                }
                else
                {
                  **((_QWORD **)&v249 + 1) = pv;
                  pv = 0;
                  v110 = *((_QWORD *)&v249 + 1) + 8LL;
                  *((_QWORD *)&v249 + 1) += 8LL;
                }
                v111 = *(const wchar_t **)(v249 + 8 * ((v110 - (__int64)v249) >> 3) - 8);
                *(_QWORD *)&v217 = v111;
                if ( *((_QWORD *)&v247 + 1) == v248 )
                {
                  std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>::_Emplace_reallocate<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>(
                    &v247,
                    *((_QWORD *)&v247 + 1),
                    &v243);
                  v112 = *((_QWORD *)&v247 + 1);
                }
                else
                {
                  **((_QWORD **)&v247 + 1) = v243;
                  v243 = 0;
                  v112 = *((_QWORD *)&v247 + 1) + 8LL;
                  *((_QWORD *)&v247 + 1) += 8LL;
                }
                *((_QWORD *)&v217 + 1) = *(_QWORD *)(v247 + 8 * ((v112 - (__int64)v247) >> 3) - 8);
                OffsetInOuterContainer = CDeploymentSession::GetOffsetInOuterContainer(
                                           this,
                                           v75,
                                           0,
                                           v111,
                                           *((const wchar_t **)&v217 + 1),
                                           &v215,
                                           &QuadPart);
                PackageFileListPath = OffsetInOuterContainer;
                if ( OffsetInOuterContainer < 0 )
                {
                  CMoUpdateLogT<CEmptyType>::MoUpdateLogError(
                    *((_QWORD *)this + 75),
                    (unsigned int)OffsetInOuterContainer,
                    L"CDeploymentSession::ProcessSandboxContainerPayload",
                    4381);
                  __1__unique_any_t_V__unique_storage_U__resource_policy_PEA_WP6AJPEA_W__E_1_STRAPI_Release__YAJ0_ZU__integral_constant__K_0A__wistd__PEA_WPEA_W_0A___T_details_wil___details_wil___wil__QEAA_XZ(&v233);
                  if ( NewFilePointer.QuadPart )
                    (*(void (__fastcall **)(union _LARGE_INTEGER))(*(_QWORD *)NewFilePointer.QuadPart + 16LL))(NewFilePointer);
                  if ( FileSize.QuadPart )
                    (*(void (__fastcall **)(union _LARGE_INTEGER))(*(_QWORD *)FileSize.QuadPart + 16LL))(FileSize);
                  goto LABEL_255;
                }
                v114 = v236;
                if ( v236 )
                {
                  v115 = 0;
                  for ( j = 0; j < v114; ++j )
                  {
                    v239 = 0;
                    *(_QWORD *)NumberOfBytesWritten = 0;
                    v117 = *(_QWORD *)NewFilePointer.QuadPart;
                    *(_QWORD *)NumberOfBytesWritten = 0;
                    v118 = (*(__int64 (__fastcall **)(union _LARGE_INTEGER, _QWORD, DWORD *))(v117 + 32))(
                             NewFilePointer,
                             j,
                             NumberOfBytesWritten);
                    PackageFileListPath = v118;
                    if ( v118 < 0 )
                    {
                      CMoUpdateLogT<CEmptyType>::MoUpdateLogError(
                        *((_QWORD *)this + 75),
                        (unsigned int)v118,
                        L"CDeploymentSession::ProcessSandboxContainerPayload",
                        4391);
                      if ( *(_QWORD *)NumberOfBytesWritten )
                        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)NumberOfBytesWritten + 16LL))(*(_QWORD *)NumberOfBytesWritten);
                      __1__unique_any_t_V__unique_storage_U__resource_policy_PEA_WP6AJPEA_W__E_1_STRAPI_Release__YAJ0_ZU__integral_constant__K_0A__wistd__PEA_WPEA_W_0A___T_details_wil___details_wil___wil__QEAA_XZ(&v233);
                      if ( NewFilePointer.QuadPart )
                        (*(void (__fastcall **)(union _LARGE_INTEGER))(*(_QWORD *)NewFilePointer.QuadPart + 16LL))(NewFilePointer);
                      if ( FileSize.QuadPart )
                        (*(void (__fastcall **)(union _LARGE_INTEGER))(*(_QWORD *)FileSize.QuadPart + 16LL))(FileSize);
                      goto LABEL_287;
                    }
                    v119 = (*(__int64 (__fastcall **)(_QWORD, wchar_t **))(**(_QWORD **)NumberOfBytesWritten + 32LL))(
                             *(_QWORD *)NumberOfBytesWritten,
                             &v239);
                    PackageFileListPath = v119;
                    if ( v119 < 0 )
                    {
                      CMoUpdateLogT<CEmptyType>::MoUpdateLogError(
                        *((_QWORD *)this + 75),
                        (unsigned int)v119,
                        L"CDeploymentSession::ProcessSandboxContainerPayload",
                        4392);
                      if ( *(_QWORD *)NumberOfBytesWritten )
                        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)NumberOfBytesWritten + 16LL))(*(_QWORD *)NumberOfBytesWritten);
                      __1__unique_any_t_V__unique_storage_U__resource_policy_PEA_WP6AJPEA_W__E_1_STRAPI_Release__YAJ0_ZU__integral_constant__K_0A__wistd__PEA_WPEA_W_0A___T_details_wil___details_wil___wil__QEAA_XZ(&v233);
                      if ( NewFilePointer.QuadPart )
                        (*(void (__fastcall **)(union _LARGE_INTEGER))(*(_QWORD *)NewFilePointer.QuadPart + 16LL))(NewFilePointer);
                      if ( FileSize.QuadPart )
                        (*(void (__fastcall **)(union _LARGE_INTEGER))(*(_QWORD *)FileSize.QuadPart + 16LL))(FileSize);
                      goto LABEL_287;
                    }
                    if ( (unsigned __int64)v239 + v115 < v115 )
                    {
                      PackageFileListPath = -2147024362;
                      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942934LL);
                    }
                    else
                    {
                      v115 += (unsigned __int64)v239;
                      PackageFileListPath = 0;
                    }
                    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)PackageFileListPath);
                    if ( PackageFileListPath < 0 )
                    {
                      CMoUpdateLogT<CEmptyType>::MoUpdateLogError(
                        *((_QWORD *)this + 75),
                        (unsigned int)PackageFileListPath,
                        L"CDeploymentSession::ProcessSandboxContainerPayload",
                        4393);
                      if ( *(_QWORD *)NumberOfBytesWritten )
                        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)NumberOfBytesWritten + 16LL))(*(_QWORD *)NumberOfBytesWritten);
                      __1__unique_any_t_V__unique_storage_U__resource_policy_PEA_WP6AJPEA_W__E_1_STRAPI_Release__YAJ0_ZU__integral_constant__K_0A__wistd__PEA_WPEA_W_0A___T_details_wil___details_wil___wil__QEAA_XZ(&v233);
                      if ( NewFilePointer.QuadPart )
                        (*(void (__fastcall **)(union _LARGE_INTEGER))(*(_QWORD *)NewFilePointer.QuadPart + 16LL))(NewFilePointer);
                      if ( FileSize.QuadPart )
                        (*(void (__fastcall **)(union _LARGE_INTEGER))(*(_QWORD *)FileSize.QuadPart + 16LL))(FileSize);
LABEL_287:
                      if ( v234 )
                        (*(void (__fastcall **)(LPCWSTR))(*(_QWORD *)v234 + 16LL))(v234);
LABEL_136:
                      std::_Tree<std::_Tset_traits<std::wstring,WstringCaseInsensitiveCompare,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,WstringCaseInsensitiveCompare,std::allocator<std::wstring>,0>>(v245);
                      goto LABEL_558;
                    }
                    if ( *(_QWORD *)NumberOfBytesWritten )
                      (*(void (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)NumberOfBytesWritten + 16LL))(
                        *(_QWORD *)NumberOfBytesWritten,
                        0);
                    v114 = v236;
                  }
                  v218[0] = v215;
                  v218[1] = v115;
                }
                else
                {
                  v218[0] = v215;
                  v218[1] = QuadPart;
                }
                LOBYTE(v219) = 0;
                v120 = *(_QWORD *)(v108 + 8);
                if ( v120 == *(_QWORD *)(v108 + 16) )
                {
                  ____Emplace_reallocate_UContainerPayload__2__ProcessSandboxContainerPayload_CDeploymentSession__QEAAJPEAUActionList__HHPEAV__vector_UUaLiteManagerDownloadRequest__V__allocator_UUaLiteManagerDownloadRequest___std___std___Z____vector_UContainerPayload__2__ProcessSandboxContainerPayload_CDeploymentSession__QEAAJPEAUActionList__HHPEAV__vector_UUaLiteManagerDownloadRequest__V__allocator_UUaLiteManagerDownloadRequest___std___std___Z_V__allocator_UContainerPayload__2__ProcessSandboxContainerPayload_CDeploymentSession__QEAAJPEAUActionList__HHPEAV__vector_UUaLiteManagerDownloadRequest__V__allocator_UUaLiteManagerDownloadRequest___std___std___Z__6__std__AEAAPEAUContainerPayload__2__ProcessSandboxContainerPayload_CDeploymentSession__QEAAJPEAUActionList__HHPEAV__vector_UUaLiteManagerDownloadRequest__V__allocator_UUaLiteManagerDownloadRequest___std___1__Z_QEAU2_2__34_QEAAJ0HH1_Z___QEAU2_2__34_QEAAJ0HH1_Z__Z(
                    v108,
                    v120,
                    &v217);
                }
                else
                {
                  *(_OWORD *)v120 = v217;
                  *(_OWORD *)(v120 + 16) = *(_OWORD *)v218;
                  *(_QWORD *)(v120 + 32) = v219;
                  *(_QWORD *)(v108 + 8) += 40LL;
                }
                __1__unique_any_t_V__unique_storage_U__resource_policy_PEA_WP6AJPEA_W__E_1_STRAPI_Release__YAJ0_ZU__integral_constant__K_0A__wistd__PEA_WPEA_W_0A___T_details_wil___details_wil___wil__QEAA_XZ(&v233);
                if ( NewFilePointer.QuadPart )
                  (*(void (__fastcall **)(union _LARGE_INTEGER))(*(_QWORD *)NewFilePointer.QuadPart + 16LL))(NewFilePointer);
              }
              else
              {
                __1__unique_any_t_V__unique_storage_U__resource_policy_PEA_WP6AJPEA_W__E_1_STRAPI_Release__YAJ0_ZU__integral_constant__K_0A__wistd__PEA_WPEA_W_0A___T_details_wil___details_wil___wil__QEAA_XZ(&v233);
                if ( NewFilePointer.QuadPart )
                  (*(void (__fastcall **)(union _LARGE_INTEGER))(*(_QWORD *)NewFilePointer.QuadPart + 16LL))(NewFilePointer);
              }
            }
            else
            {
              __1__unique_any_t_V__unique_storage_U__resource_policy_PEA_WP6AJPEA_W__E_1_STRAPI_Release__YAJ0_ZU__integral_constant__K_0A__wistd__PEA_WPEA_W_0A___T_details_wil___details_wil___wil__QEAA_XZ(&v233);
              if ( NewFilePointer.QuadPart )
                (*(void (__fastcall **)(union _LARGE_INTEGER))(*(_QWORD *)NewFilePointer.QuadPart + 16LL))(NewFilePointer);
            }
          }
          if ( FileSize.QuadPart )
            (*(void (__fastcall **)(union _LARGE_INTEGER))(*(_QWORD *)FileSize.QuadPart + 16LL))(FileSize);
        }
        if ( v234 )
          (*(void (__fastcall **)(LPCWSTR))(*(_QWORD *)v234 + 16LL))(v234);
        v65 += 104;
        v66 = m;
      }
      std::_Tree<std::_Tset_traits<std::wstring,WstringCaseInsensitiveCompare,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,WstringCaseInsensitiveCompare,std::allocator<std::wstring>,0>>(v245);
    }
    v121 = *(__int64 **)v244[0];
LABEL_308:
    if ( *((_BYTE *)v121 + 25) )
    {
      v122 = *(_QWORD *)v251[0];
      QuadPart = *(_QWORD *)v251[0];
      while ( !*(_BYTE *)(v122 + 25) )
      {
        v123 = v122 + 32;
        if ( *(_QWORD *)(v122 + 56) <= 7u )
          v124 = v122 + 32;
        else
          v124 = *(_QWORD *)v123;
        m = v124;
        LogAdapter::TraceInfo<wchar_t const *>("Deleting file [{}]", &m);
        if ( *(_QWORD *)(v123 + 24) > 7u )
          v123 = *(_QWORD *)v123;
        v125 = DeleteFileW((LPCWSTR)v123);
        LogAdapter::TraceWarningIfWin32BoolFalse<>(v125, "Failed to delete file");
        std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::wstring>>,std::_Iterator_base0>::operator++(&QuadPart);
        v122 = QuadPart;
      }
      goto LABEL_558;
    }
    v233 = (LPCWSTR)-1LL;
    FileSize.QuadPart = 0;
    LOBYTE(v63) = 0;
    ____Sort_unchecked_PEAUContainerPayload__2__ProcessSandboxContainerPayload_CDeploymentSession__QEAAJPEAUActionList__HHPEAV__vector_UUaLiteManagerDownloadRequest__V__allocator_UUaLiteManagerDownloadRequest___std___std___Z_U_unnamed_type_containerPayloadCompare___2__23_QEAAJ0HH1_Z__std__YAXPEAUContainerPayload__2__ProcessSandboxContainerPayload_CDeploymentSession__QEAAJPEAUActionList__HHPEAV__vector_UUaLiteManagerDownloadRequest__V__allocator_UUaLiteManagerDownloadRequest___std___0__Z_2_JU_unnamed_type_containerPayloadCompare___2__23_QEAAJ0HH1_Z__Z(
      v121[6],
      v121[7],
      0xCCCCCCCCCCCCCCCDuLL * ((v121[7] - v121[6]) >> 3),
      v63);
    SH_SSTRING::operator=(&lpExistingFileName);
    v126 = CMiscHelpersT<CEmptyType>::CombinePath(*((_QWORD *)this + 61), v121[4], 0, &lpExistingFileName);
    PackageFileListPath = v126;
    if ( v126 < 0 )
    {
      v127 = 4424;
      v128 = *((_QWORD *)this + 75);
      goto LABEL_322;
    }
    v129 = (_QWORD *)v121[6];
    if ( v121[7] - (_QWORD)v129 == 40 )
    {
      SH_SSTRING::operator=(&lpFileName);
      v126 = CMiscHelpersT<CEmptyType>::CombinePath(*((_QWORD *)this + 61), *v129, 0, &lpFileName);
      PackageFileListPath = v126;
      v128 = *((_QWORD *)this + 75);
      if ( v126 >= 0 )
      {
        v130 = lpFileName;
        v131 = lpExistingFileName;
        if ( v128 )
          CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
            v128,
            1,
            L"Single payload chunk; renaming [%ws] to [%ws]",
            lpExistingFileName,
            lpFileName);
        if ( !MoveFileExW(v131, v130, 9u) )
        {
          LastError = GetLastError();
          PackageFileListPath = LastError;
          if ( LastError )
          {
            if ( LastError > 0 )
              PackageFileListPath = (unsigned __int16)LastError | 0x80070000;
          }
          else
          {
            PackageFileListPath = -2147467259;
          }
          CMoUpdateLogT<CEmptyType>::MoUpdateLogError(
            *((_QWORD *)this + 75),
            (unsigned int)PackageFileListPath,
            L"CDeploymentSession::ProcessSandboxContainerPayload",
            4435);
          goto LABEL_558;
        }
        goto LABEL_431;
      }
      v127 = 4430;
LABEL_322:
      CMoUpdateLogT<CEmptyType>::MoUpdateLogError(
        v128,
        (unsigned int)v126,
        L"CDeploymentSession::ProcessSandboxContainerPayload",
        v127);
      goto LABEL_558;
    }
    FileW = CreateFileW(lpExistingFileName, 0xC0000000, 1u, 0, 3u, 0x10000000u, 0);
    SH_FILENT::operator=(&v233, FileW);
    v134 = (__int64)v233;
    if ( (unsigned __int64)v233 - 1 > 0xFFFFFFFFFFFFFFFDuLL )
    {
      v207 = GetLastError();
      PackageFileListPath = v207;
      if ( v207 )
      {
        if ( v207 > 0 )
          PackageFileListPath = (unsigned __int16)v207 | 0x80070000;
      }
      else
      {
        PackageFileListPath = -2147467259;
      }
      CMoUpdateLogT<CEmptyType>::MoUpdateLogError(
        *((_QWORD *)this + 75),
        (unsigned int)PackageFileListPath,
        L"CDeploymentSession::ProcessSandboxContainerPayload",
        4446);
      goto LABEL_556;
    }
    v135 = 0;
    v215 = 0;
    v136 = 0;
    for ( k = v121[6]; k != v121[7]; k += 40 )
    {
      if ( *(_BYTE *)(k + 32) )
      {
        v136 = (_QWORD *)k;
      }
      else
      {
        v135 += *(_QWORD *)(k + 24);
        v215 = v135;
      }
    }
    v138 = 0;
    if ( (unsigned __int64)v233 - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
      v138 = (WCHAR *)v233;
    if ( !GetFileSizeEx(v138, &FileSize) )
    {
      v139 = GetLastError();
      PackageFileListPath = v139;
      if ( v139 )
      {
        if ( v139 > 0 )
          PackageFileListPath = (unsigned __int16)v139 | 0x80070000;
      }
      else
      {
        PackageFileListPath = -2147467259;
      }
      v140 = 4464;
      goto LABEL_346;
    }
    v141 = *((_QWORD *)this + 75);
    if ( v141 )
      CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(v141, 2, L"Validating container file [%ws]", v121[4]);
    v142 = FileSize;
    v143 = FileSize;
    v144 = (_QWORD *)v121[6];
    v145 = (_QWORD *)v121[7];
    for ( m = (unsigned __int64)v145; ; v145 = (_QWORD *)m )
    {
      QuadPart = (unsigned __int64)v144;
      if ( v144 == v145 )
        break;
      v143.QuadPart -= v144[3];
      v146 = *((_QWORD *)this + 75);
      if ( v146 )
      {
        CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
          v146,
          1,
          L"  Expecting container payload: %ws, original offset: %llu, new offset: %llu, length: %llu",
          *v144,
          v144[2],
          v143.QuadPart,
          v144[3]);
        v142 = FileSize;
        v144 = (_QWORD *)QuadPart;
      }
      v144 += 5;
    }
    v147 = v215;
    if ( v136 )
      v148 = v142.QuadPart - v215;
    else
      v148 = 0;
    if ( *((_DWORD *)this + 64) && v148 <= 0 )
    {
      v149 = *((_QWORD *)this + 75);
      if ( v149 )
      {
        CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
          v149,
          2,
          L"Container file does not contain variable payload, but the LCU is being reoffered.");
        v142 = FileSize;
      }
      v136 = 0;
    }
    else if ( v136 )
    {
      if ( v148 <= 0 )
      {
LABEL_372:
        if ( (unsigned __int64)(v134 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
        {
          CloseHandle((HANDLE)v134);
          v134 = -1;
          v233 = (LPCWSTR)-1LL;
          v142 = FileSize;
        }
        v153 = *((_QWORD *)this + 75);
        if ( v153 )
          CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
            v153,
            2,
            L"Deleting corrupt container file. Actual size: [%llu], Minimum expected size: [%llu]",
            v142.QuadPart,
            v147);
        if ( DeleteFileW(lpExistingFileName) )
        {
          if ( (unsigned __int64)(v134 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
            CloseHandle((HANDLE)v134);
          goto LABEL_431;
        }
        v154 = GetLastError();
        PackageFileListPath = v154;
        if ( v154 )
        {
          if ( v154 > 0 )
            PackageFileListPath = (unsigned __int16)v154 | 0x80070000;
        }
        else
        {
          PackageFileListPath = -2147467259;
        }
        v140 = 4498;
LABEL_346:
        CMoUpdateLogT<CEmptyType>::MoUpdateLogError(
          *((_QWORD *)this + 75),
          (unsigned int)PackageFileListPath,
          L"CDeploymentSession::ProcessSandboxContainerPayload",
          v140);
        goto LABEL_556;
      }
      goto LABEL_364;
    }
    if ( v142.QuadPart != v147 )
      goto LABEL_372;
LABEL_364:
    v150 = *((_QWORD *)this + 75);
    if ( v150 )
    {
      CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
        v150,
        1,
        L"Found valid container file. Actual size: [%llu], Minimum expected size: [%llu]",
        v142.QuadPart,
        v147);
      v142 = FileSize;
    }
    v151 = 0;
    if ( (unsigned __int64)(v134 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      v151 = (void *)v134;
    if ( !SetFilePointerEx(v151, v142, 0, 0) )
    {
      v152 = GetLastError();
      PackageFileListPath = v152;
      if ( v152 )
      {
        if ( v152 > 0 )
          PackageFileListPath = (unsigned __int16)v152 | 0x80070000;
      }
      else
      {
        PackageFileListPath = -2147467259;
      }
      v140 = 4512;
      goto LABEL_346;
    }
    v155 = (wchar_t *)v121[6];
    v156 = (wchar_t *)v121[7];
    for ( n = v156; ; v156 = n )
    {
      v239 = v155;
      if ( v155 == v156 )
      {
        if ( !v136 )
          goto LABEL_430;
        SH_SSTRING::operator=(&lpFileName);
        SH_FILENT::operator=(&v233);
        v200 = CMiscHelpersT<CEmptyType>::CombinePath(*((_QWORD *)this + 61), *v136, 0, &lpFileName);
        PackageFileListPath = v200;
        v201 = *((_QWORD *)this + 75);
        if ( v200 >= 0 )
        {
          v204 = lpFileName;
          if ( v201 )
            CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
              v201,
              1,
              L"Final payload chunk; renaming [%ws] to [%ws]",
              lpExistingFileName,
              lpFileName);
          if ( MoveFileExW(lpExistingFileName, v204, 9u) )
            goto LABEL_430;
          v205 = GetLastError();
          PackageFileListPath = v205;
          if ( v205 )
          {
            if ( v205 > 0 )
              PackageFileListPath = (unsigned __int16)v205 | 0x80070000;
          }
          else
          {
            PackageFileListPath = -2147467259;
          }
          v202 = 4644;
          v203 = (unsigned int)PackageFileListPath;
          v201 = *((_QWORD *)this + 75);
        }
        else
        {
          v202 = 4639;
          v203 = (unsigned int)v200;
        }
        CMoUpdateLogT<CEmptyType>::MoUpdateLogError(
          v201,
          v203,
          L"CDeploymentSession::ProcessSandboxContainerPayload",
          v202);
        goto LABEL_499;
      }
      v157 = 0;
      v234 = 0;
      hFile = (HANDLE)-1LL;
      NewFilePointer.QuadPart = 0;
      if ( *((_BYTE *)v155 + 32) )
      {
        DH_SSTRING::~DH_SSTRING((DH_SSTRING *)&v234);
      }
      else
      {
        if ( (unsigned __int64)(v134 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
          v157 = (void *)v134;
        if ( !SetFilePointerEx(v157, 0, &NewFilePointer, 1u) )
        {
          v158 = GetLastError();
          PackageFileListPath = v158;
          if ( v158 )
          {
            if ( v158 > 0 )
              PackageFileListPath = (unsigned __int16)v158 | 0x80070000;
          }
          else
          {
            PackageFileListPath = -2147467259;
          }
          v159 = 4530;
          goto LABEL_399;
        }
        v162 = *((_QWORD *)this + 75);
        if ( v162 )
          CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
            v162,
            1,
            L"Starting container position [%llu]",
            NewFilePointer.QuadPart);
        SH_SSTRING::operator=(&lpFileName);
        v163 = CMiscHelpersT<CEmptyType>::CombinePath(*((_QWORD *)this + 61), *(_QWORD *)v155, 0, &lpFileName);
        PackageFileListPath = v163;
        if ( v163 < 0 )
        {
          v159 = 4537;
          v160 = (unsigned int)v163;
          goto LABEL_400;
        }
        v164 = 0;
        if ( (unsigned __int64)(v134 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
          v164 = (void *)v134;
        if ( !SetFilePointerEx(v164, (LARGE_INTEGER)-*((_QWORD *)v155 + 3), &NewFilePointer, 2u) )
        {
          v165 = GetLastError();
          PackageFileListPath = v165;
          if ( v165 )
          {
            if ( v165 > 0 )
              PackageFileListPath = (unsigned __int16)v165 | 0x80070000;
          }
          else
          {
            PackageFileListPath = -2147467259;
          }
          v159 = 4545;
LABEL_399:
          v160 = (unsigned int)PackageFileListPath;
LABEL_400:
          v161 = *((_QWORD *)this + 75);
          goto LABEL_401;
        }
        v166 = *((_QWORD *)this + 75);
        if ( v166 )
          CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
            v166,
            1,
            L"Next container position [%llu]",
            NewFilePointer.QuadPart);
        if ( !NewFilePointer.QuadPart && !v136 )
        {
          if ( (unsigned __int64)(v134 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
          {
            CloseHandle((HANDLE)v134);
            v134 = -1;
            v233 = (LPCWSTR)-1LL;
          }
          v167 = *((_QWORD *)this + 75);
          v168 = lpFileName;
          if ( v167 )
            CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
              v167,
              1,
              L"Final payload chunk; renaming [%ws] to [%ws]",
              lpExistingFileName,
              lpFileName);
          if ( !MoveFileExW(lpExistingFileName, v168, 9u) )
          {
            v169 = GetLastError();
            PackageFileListPath = v169;
            if ( v169 )
            {
              if ( v169 > 0 )
                PackageFileListPath = (unsigned __int16)v169 | 0x80070000;
            }
            else
            {
              PackageFileListPath = -2147467259;
            }
            v159 = 4559;
            goto LABEL_399;
          }
          DH_SSTRING::~DH_SSTRING((DH_SSTRING *)&v234);
LABEL_430:
          SH_FILENT::~SH_FILENT((SH_FILENT *)&v233);
LABEL_431:
          v170 = (__int64 **)v121[2];
          if ( *((_BYTE *)v170 + 25) )
          {
            for ( ii = (__int64 *)v121[1]; !*((_BYTE *)ii + 25) && v121 == (__int64 *)ii[2]; ii = (__int64 *)ii[1] )
              v121 = ii;
            v121 = ii;
          }
          else
          {
            v121 = (__int64 *)v121[2];
            for ( jj = *v170; !*((_BYTE *)jj + 25); jj = (__int64 *)*jj )
              v121 = jj;
          }
          goto LABEL_308;
        }
        if ( !GetTempFileNameW(*((LPCWSTR *)this + 61), L"tmp", 0, TempFileName) )
        {
          v172 = GetLastError();
          PackageFileListPath = v172;
          if ( v172 )
          {
            if ( v172 > 0 )
              PackageFileListPath = (unsigned __int16)v172 | 0x80070000;
          }
          else
          {
            PackageFileListPath = -2147467259;
          }
          v159 = 4566;
          goto LABEL_399;
        }
        TempFileName[259] = 0;
        if ( !TempFileName[0] )
        {
          PackageFileListPath = -2147418113;
          v159 = 4568;
          goto LABEL_399;
        }
        v173 = STRAPI_Create(TempFileName, (wchar_t **)&v234);
        PackageFileListPath = v173;
        v236 = v173;
        v161 = *((_QWORD *)this + 75);
        if ( v173 < 0 )
        {
          v159 = 4570;
          v160 = (unsigned int)v173;
LABEL_401:
          CMoUpdateLogT<CEmptyType>::MoUpdateLogError(
            v161,
            v160,
            L"CDeploymentSession::ProcessSandboxContainerPayload",
            v159);
LABEL_402:
          DH_SSTRING::~DH_SSTRING((DH_SSTRING *)&v234);
LABEL_556:
          if ( (unsigned __int64)(v134 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
            CloseHandle((HANDLE)v134);
          goto LABEL_558;
        }
        if ( v161 )
        {
          v174 = 0;
          if ( v234 )
            v174 = v234;
          CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
            v161,
            1,
            L"Creating temporary payload file [%ws] for [%ws]",
            v174,
            lpFileName);
        }
        v175 = CreateFileW(v234, 0xC0000000, 0, 0, 5u, 0x8000000u, 0);
        SH_FILENT::operator=(&hFile, v175);
        v176 = (char *)hFile;
        if ( (char *)hFile - 1 > (char *)0xFFFFFFFFFFFFFFFDLL )
        {
          v199 = GetLastError();
          PackageFileListPath = v199;
          if ( v199 )
          {
            if ( v199 > 0 )
              PackageFileListPath = (unsigned __int16)v199 | 0x80070000;
          }
          else
          {
            PackageFileListPath = -2147467259;
          }
          v179 = 4582;
          goto LABEL_530;
        }
        v177 = *(LARGE_INTEGER *)(v239 + 12);
        if ( !SetFilePointerEx(hFile, v177, 0, 0) )
        {
          v178 = GetLastError();
          PackageFileListPath = v178;
          if ( v178 )
          {
            if ( v178 > 0 )
              PackageFileListPath = (unsigned __int16)v178 | 0x80070000;
          }
          else
          {
            PackageFileListPath = -2147467259;
          }
          v179 = 4588;
LABEL_530:
          CMoUpdateLogT<CEmptyType>::MoUpdateLogError(
            *((_QWORD *)this + 75),
            (unsigned int)PackageFileListPath,
            L"CDeploymentSession::ProcessSandboxContainerPayload",
            v179);
          if ( (unsigned __int64)(v176 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
            CloseHandle(v176);
          goto LABEL_402;
        }
        if ( !SetEndOfFile(v176) )
        {
          v180 = GetLastError();
          PackageFileListPath = v180;
          if ( v180 )
          {
            if ( v180 > 0 )
              PackageFileListPath = (unsigned __int16)v180 | 0x80070000;
          }
          else
          {
            PackageFileListPath = -2147467259;
          }
          v179 = 4589;
          goto LABEL_530;
        }
        if ( !SetFilePointerEx(v176, 0, 0, 0) )
        {
          v182 = GetLastError();
          PackageFileListPath = v182;
          if ( v182 )
          {
            if ( v182 > 0 )
              PackageFileListPath = (unsigned __int16)v182 | 0x80070000;
          }
          else
          {
            PackageFileListPath = -2147467259;
          }
          v183 = 4590;
          goto LABEL_498;
        }
        v184 = v177.QuadPart;
        if ( v177.QuadPart > 0x400000uLL )
          v184 = 0x400000;
        v185 = RtlReallocateLBlob(v181, v184, nNumberOfBytesToRead);
        if ( !(unsigned int)SErrorConverter::C_NtStatus2HR(v185, &v236) )
        {
          PackageFileListPath = v236;
          v183 = 4597;
          goto LABEL_498;
        }
        while ( v177.QuadPart )
        {
          LowPart = v177.LowPart;
          if ( v177.QuadPart >= *(_QWORD *)&nNumberOfBytesToRead[2] )
            LowPart = nNumberOfBytesToRead[2];
          NumberOfBytesRead = 0;
          NumberOfBytesWritten[0] = 0;
          v187 = (void *)v134;
          if ( (unsigned __int64)(v134 - 1) > 0xFFFFFFFFFFFFFFFDuLL )
            v187 = 0;
          if ( !ReadFile(v187, lpBuffer, LowPart, &NumberOfBytesRead, 0) )
          {
            v188 = GetLastError();
            PackageFileListPath = v188;
            if ( v188 )
            {
              if ( v188 > 0 )
                PackageFileListPath = (unsigned __int16)v188 | 0x80070000;
            }
            else
            {
              PackageFileListPath = -2147467259;
            }
            v183 = 4605;
            goto LABEL_498;
          }
          v189 = 0;
          if ( (unsigned __int64)(v176 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
            v189 = v176;
          if ( !WriteFile(v189, lpBuffer, NumberOfBytesRead, NumberOfBytesWritten, 0) )
          {
            v190 = GetLastError();
            PackageFileListPath = v190;
            if ( v190 )
            {
              if ( v190 > 0 )
                PackageFileListPath = (unsigned __int16)v190 | 0x80070000;
            }
            else
            {
              PackageFileListPath = -2147467259;
            }
            v183 = 4606;
            goto LABEL_498;
          }
          m = NumberOfBytesWritten[0];
          if ( NumberOfBytesWritten[0] < NumberOfBytesRead )
          {
            NewFilePointer.QuadPart = -(__int64)(NumberOfBytesRead - NumberOfBytesWritten[0]);
            v191 = 0;
            if ( (unsigned __int64)(v134 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
              v191 = (void *)v134;
            if ( !SetFilePointerEx(v191, (LARGE_INTEGER)-(__int64)(NumberOfBytesRead - NumberOfBytesWritten[0]), 0, 1u) )
            {
              v192 = GetLastError();
              PackageFileListPath = v192;
              if ( v192 )
              {
                if ( v192 > 0 )
                  PackageFileListPath = (unsigned __int16)v192 | 0x80070000;
              }
              else
              {
                PackageFileListPath = -2147467259;
              }
              v183 = 4614;
              goto LABEL_498;
            }
          }
          v177.QuadPart -= m;
        }
        SH_FILENT::operator=(&hFile);
        if ( !MoveFileExW(v234, lpFileName, 9u) )
        {
          v193 = GetLastError();
          PackageFileListPath = v193;
          if ( v193 )
          {
            if ( v193 > 0 )
              PackageFileListPath = (unsigned __int16)v193 | 0x80070000;
          }
          else
          {
            PackageFileListPath = -2147467259;
          }
          v183 = 4622;
          goto LABEL_498;
        }
        v194 = (void *)v134;
        if ( (unsigned __int64)(v134 - 1) > 0xFFFFFFFFFFFFFFFDuLL )
          v194 = 0;
        v195 = SetFilePointerEx(v194, (LARGE_INTEGER)-*((_QWORD *)v239 + 3), 0, 2u);
        v196 = 0;
        if ( !v195 )
        {
          v197 = GetLastError();
          PackageFileListPath = v197;
          if ( v197 )
          {
            if ( v197 > 0 )
              PackageFileListPath = (unsigned __int16)v197 | 0x80070000;
          }
          else
          {
            PackageFileListPath = -2147467259;
          }
          v183 = 4628;
          goto LABEL_498;
        }
        if ( (unsigned __int64)(v134 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
          v196 = (void *)v134;
        if ( !SetEndOfFile(v196) )
        {
          v198 = GetLastError();
          PackageFileListPath = v198;
          if ( v198 )
          {
            if ( v198 > 0 )
              PackageFileListPath = (unsigned __int16)v198 | 0x80070000;
          }
          else
          {
            PackageFileListPath = -2147467259;
          }
          v183 = 4629;
LABEL_498:
          CMoUpdateLogT<CEmptyType>::MoUpdateLogError(
            *((_QWORD *)this + 75),
            (unsigned int)PackageFileListPath,
            L"CDeploymentSession::ProcessSandboxContainerPayload",
            v183);
          SH_FILENT::~SH_FILENT((SH_FILENT *)&hFile);
          DH_SSTRING::~DH_SSTRING((DH_SSTRING *)&v234);
LABEL_499:
          SH_FILENT::~SH_FILENT((SH_FILENT *)&v233);
          goto LABEL_558;
        }
        SH_FILENT::~SH_FILENT((SH_FILENT *)&hFile);
        DH_SSTRING::~DH_SSTRING((DH_SSTRING *)&v234);
        PackageFileListPath = v236;
        v155 = v239;
      }
      v155 += 20;
    }
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x1235,
                           (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\DeploymentSessionImpl.h",
                           v208);
  }
  return result;
}

```

## disassembly

```asm
0x18007c740  mov     r11, rsp
0x18007c743  push    rdi
0x18007c744  push    r12
0x18007c746  push    r13
0x18007c748  push    r14
0x18007c74a  push    r15
0x18007c74c  sub     rsp, 430h
0x18007c753  mov     qword ptr [r11-330h], 0FFFFFFFFFFFFFFFEh
0x18007c75e  mov     [r11+10h], rbx
0x18007c762  mov     [r11+18h], rsi
0x18007c766  mov     rax, cs:__security_cookie
0x18007c76d  xor     rax, rsp
0x18007c770  mov     [rsp+458h+var_38], rax
0x18007c778  mov     [rsp+458h+NumberOfBytesRead], r9d
0x18007c780  mov     r12d, r8d
0x18007c783  mov     [rsp+458h+var_310], r8d
0x18007c78b  mov     rbx, rdx
0x18007c78e  mov     r15, rcx
0x18007c791  mov     rdi, [rsp+458h+arg_20]
0x18007c799  mov     [rsp+458h+var_3C0], rdi
0x18007c7a1  xor     r13d, r13d
0x18007c7a4  mov     esi, r13d
0x18007c7a7  mov     [rsp+458h+lpFileName], r13
0x18007c7ac  mov     [rsp+458h+lpExistingFileName], r13
0x18007c7b1  xorps   xmm0, xmm0
0x18007c7b4  xor     eax, eax
0x18007c7b6  movups  xmmword ptr [rsp+458h+nNumberOfBytesToRead], xmm0
0x18007c7be  mov     [r11-380h], rax
0x18007c7c5  mov     [r11-270h], r13
0x18007c7cc  mov     [r11-268h], r13
0x18007c7d3  lea     r14d, [r13+40h]
0x18007c7d7  mov     ecx, r14d; Size
0x18007c7da  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18007c7df  mov     [rax], rax
0x18007c7e2  mov     [rax+8], rax
0x18007c7e6  mov     [rax+10h], rax
0x18007c7ea  mov     word ptr [rax+18h], 101h
0x18007c7f0  mov     [rsp+458h+var_270], rax
0x18007c7f8  xorps   xmm0, xmm0
0x18007c7fb  movdqu  [rsp+458h+var_288], xmm0
0x18007c804  mov     [rsp+458h+var_278], r13
0x18007c80c  movdqu  [rsp+458h+var_2A0], xmm0
0x18007c815  mov     [rsp+458h+var_290], r13
0x18007c81d  mov     [rsp+458h+var_2D8], r13
0x18007c825  mov     [rsp+458h+pv], r13
0x18007c82d  mov     [rsp+458h+var_2B0], r13
0x18007c835  mov     [rsp+458h+var_2A8], r13
0x18007c83d  lea     ecx, [r13+38h]; Size
0x18007c841  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18007c846  mov     [rax], rax
0x18007c849  mov     [rax+8], rax
0x18007c84d  mov     [rax+10h], rax
0x18007c851  mov     word ptr [rax+18h], 101h
0x18007c857  mov     [rsp+458h+var_2B0], rax
0x18007c85f  mov     [rsp+458h+var_2D0], r13
0x18007c867  mov     [rsp+458h+var_2C8], r13
0x18007c86f  lea     ecx, [r13+48h]; Size
0x18007c873  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18007c878  mov     [rax], rax
0x18007c87b  mov     [rax+8], rax
0x18007c87f  mov     [rax+10h], rax
0x18007c883  mov     word ptr [rax+18h], 101h
0x18007c889  mov     [rsp+458h+var_2D0], rax
0x18007c891  mov     [rsp+458h+var_260], r13
0x18007c899  mov     [rsp+458h+var_258], r13
0x18007c8a1  mov     ecx, r14d; Size
0x18007c8a4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18007c8a9  mov     [rax], rax
0x18007c8ac  mov     [rax+8], rax
0x18007c8b0  mov     [rax+10h], rax
0x18007c8b4  mov     word ptr [rax+18h], 101h
0x18007c8ba  mov     [rsp+458h+var_260], rax
0x18007c8c2  mov     r14d, r13d
0x18007c8c5  mov     rcx, [r15+258h]
0x18007c8cc  test    rcx, rcx
0x18007c8cf  jz      short loc_18007C8F6
0x18007c8d1  lea     r9, aTrue_3; "TRUE"
0x18007c8d8  lea     rax, aFalse_2; "FALSE"
0x18007c8df  test    r12d, r12d
0x18007c8e2  cmovz   r9, rax
0x18007c8e6  lea     r8, aProcesssandbox_0; "ProcessSandboxContainerPayload bInitial"...
0x18007c8ed  lea     edx, [r13+2]
0x18007c8f1  call    ?MoUpdateLogFormat@?$CMoUpdateLogT@VCEmptyType@@@@SAJPEAVIUpdateDiagnostics@@W4MOUPDATE_LOGLEVEL@@PEB_WZZ; CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(IUpdateDiagnostics *,MOUPDATE_LOGLEVEL,wchar_t const *,...)
0x18007c8f6  test    rbx, rbx
0x18007c8f9  jnz     short loc_18007C94D
0x18007c8fb  mov     r14d, 80070057h
0x18007c901  mov     rcx, [r15+258h]
0x18007c908  xor     edi, edi
0x18007c90a  test    rcx, rcx
0x18007c90d  jnz     short loc_18007C913
0x18007c90f  mov     ecx, edi
0x18007c911  jmp     short loc_18007C943
0x18007c913  mov     [rsp+458h+dwFlagsAndAttributes], r14d
0x18007c918  mov     [rsp+458h+dwCreationDisposition], 0FF3h
0x18007c920  lea     r9, aCdeploymentses_61; "CDeploymentSession::ProcessSandboxConta"...
0x18007c927  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x18007c92e  mov     edx, 4
0x18007c933  call    ?MoUpdateLogFormat@?$CMoUpdateLogT@VCEmptyType@@@@SAJPEAVIUpdateDiagnostics@@W4MOUPDATE_LOGLEVEL@@PEB_WZZ; CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(IUpdateDiagnostics *,MOUPDATE_LOGLEVEL,wchar_t const *,...)
0x18007c938  mov     ecx, eax
0x18007c93a  test    eax, eax
0x18007c93c  jns     short loc_18007C943
0x18007c93e  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18007c943  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18007c948  jmp     loc_18007F138
0x18007c94d  mov     r13, [rbx+40h]
0x18007c951  mov     eax, [rbx+48h]
0x18007c954  imul    rax, 0A8h
0x18007c95b  add     rax, r13
0x18007c95e  mov     [rsp+458h+var_3B8], rax
0x18007c966  xor     ebx, ebx
0x18007c968  cmp     r13, rax
0x18007c96b  jz      loc_18007D204
0x18007c971  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PlayB_ModelInstallation@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PlayB_ModelInstallation@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PlayB_ModelInstallation> `wil::Feature<__WilFeatureTraits_Feature_PlayB_ModelInstallation>::GetImpl(void)'::`2'::impl
0x18007c978  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PlayB_ModelInstallation@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PlayB_ModelInstallation>::__private_IsEnabled(void)
0x18007c97d  test    al, al
0x18007c97f  jz      short loc_18007C98A
0x18007c981  test    rdi, rdi
0x18007c984  jnz     loc_18007D1F0
0x18007c98a  mov     [rsp+458h+var_320], rbx
0x18007c992  test    r12d, r12d
0x18007c995  jz      short loc_18007C9CB
0x18007c997  mov     eax, [r13+58h]
0x18007c99b  cmp     eax, 0Fh
0x18007c99e  ja      short loc_18007C9AA
0x18007c9a0  mov     ecx, 9080h
0x18007c9a5  bt      ecx, eax
0x18007c9a8  jb      short loc_18007C9C0
0x18007c9aa  cmp     dword ptr [r13+68h], 2
0x18007c9af  jz      short loc_18007C9C0
0x18007c9b1  cmp     dword ptr [r15+1C8h], 8
0x18007c9b9  jz      short loc_18007C9C0
0x18007c9bb  jmp     loc_18007D1F0
0x18007c9c0  mov     dword ptr [r15+11Ch], 1
0x18007c9cb  mov     rdi, [r13+70h]
0x18007c9cf  mov     eax, [r13+78h]
0x18007c9d3  imul    rax, 0B8h
0x18007c9da  add     rax, rdi
0x18007c9dd  mov     qword ptr [rsp+458h+NumberOfBytesWritten], rax
0x18007c9e5  cmp     rdi, rax
0x18007c9e8  jz      loc_18007D1DB
0x18007c9ee  xorps   xmm0, xmm0
0x18007c9f1  movdqu  [rsp+458h+var_3F0], xmm0
0x18007c9f7  mov     [rsp+458h+var_3E0], rbx
0x18007c9fc  mov     [rsp+458h+var_3E0+8], rbx
0x18007ca04  mov     byte ptr [rsp+458h+var_3D0], bl
0x18007ca0b  xor     eax, eax
0x18007ca0d  mov     dword ptr [rsp+458h+var_3D0+1], eax
0x18007ca14  mov     word ptr [rsp+458h+var_3D0+5], ax
0x18007ca1c  mov     byte ptr [rsp+458h+var_3D0+7], al
0x18007ca23  mov     [rsp+458h+var_328], rbx
0x18007ca2b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PlayB_ModelInstallation@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PlayB_ModelInstallation@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PlayB_ModelInstallation> `wil::Feature<__WilFeatureTraits_Feature_PlayB_ModelInstallation>::GetImpl(void)'::`2'::impl
0x18007ca32  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PlayB_ModelInstallation@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PlayB_ModelInstallation>::__private_IsEnabled(void)
0x18007ca37  test    al, al
0x18007ca39  jz      short loc_18007CA51
0x18007ca3b  cmp     [rdi+30h], rbx
0x18007ca3f  jz      loc_18007D1C7
0x18007ca45  cmp     dword ptr [r13+58h], 18h
0x18007ca4a  jnz     short loc_18007CA5B
0x18007ca4c  jmp     loc_18007D1C7
0x18007ca51  cmp     [rdi+30h], rbx
0x18007ca55  jz      loc_18007D1C7
0x18007ca5b  test    r12d, r12d
0x18007ca5e  jz      short loc_18007CA7D
0x18007ca60  mov     rax, [rdi+10h]
0x18007ca64  mov     [rsp+458h+var_2F8], rax
0x18007ca6c  mov     rdx, [rdi+18h]
0x18007ca70  mov     [rsp+458h+var_328], rdx
0x18007ca78  jmp     loc_18007CC68
0x18007ca7d  cmp     [rdi+99h], bl
0x18007ca83  jz      loc_18007CBC5
0x18007ca89  mov     dword ptr [rsp+458h+hFile], ebx
0x18007ca90  mov     rdx, [rsp+458h+var_320]
0x18007ca98  test    rdx, rdx
0x18007ca9b  jnz     loc_18007CB47
0x18007caa1  lea     r8, [rsp+458h+var_320]; wchar_t **
0x18007caa9  mov     rdx, r13; struct ActionList::Package *
0x18007caac  mov     rcx, r15; this
0x18007caaf  call    ?GetPackageFileListPath@CDeploymentSession@@QEAAJQEBUPackage@ActionList@@PEAPEA_W@Z; CDeploymentSession::GetPackageFileListPath(ActionList::Package const * const,wchar_t * *)
0x18007cab4  mov     r14d, eax
0x18007cab7  test    eax, eax
0x18007cab9  jns     loc_18007CB3F
0x18007cabf  mov     rax, [r15+258h]
0x18007cac6  xor     edi, edi
0x18007cac8  mov     ecx, edi
0x18007caca  test    rax, rax
0x18007cacd  jz      short loc_18007CB00
0x18007cacf  mov     [rsp+458h+dwFlagsAndAttributes], r14d
0x18007cad4  mov     [rsp+458h+dwCreationDisposition], 1034h
0x18007cadc  lea     r9, aCdeploymentses_61; "CDeploymentSession::ProcessSandboxConta"...
0x18007cae3  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x18007caea  lea     edx, [rdi+4]
0x18007caed  mov     rcx, rax
0x18007caf0  call    ?MoUpdateLogFormat@?$CMoUpdateLogT@VCEmptyType@@@@SAJPEAVIUpdateDiagnostics@@W4MOUPDATE_LOGLEVEL@@PEB_WZZ; CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(IUpdateDiagnostics *,MOUPDATE_LOGLEVEL,wchar_t const *,...)
0x18007caf5  mov     ecx, eax
0x18007caf7  test    ecx, ecx
0x18007caf9  jns     short loc_18007CB00
0x18007cafb  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18007cb00  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18007cb05  nop
0x18007cb06  mov     rbx, [rsp+458h+var_320]
0x18007cb0e  test    rbx, rbx
0x18007cb11  jz      loc_18007F138
0x18007cb17  call    cs:__imp_GetProcessHeap
0x18007cb1e  nop     dword ptr [rax+rax+00h]
0x18007cb23  mov     rcx, rax; hHeap
0x18007cb26  lea     r8, [rbx-4]; lpMem
0x18007cb2a  xor     edx, edx; dwFlags
0x18007cb2c  call    cs:__imp_HeapFree
0x18007cb33  nop     dword ptr [rax+rax+00h]
0x18007cb38  xor     ecx, ecx
0x18007cb3a  jmp     loc_18007C943
0x18007cb3f  mov     rdx, [rsp+458h+var_320]
0x18007cb47  mov     qword ptr [rsp+458h+dwFlagsAndAttributes], rbx
0x18007cb4c  lea     rax, [rsp+458h+hFile]
0x18007cb54  mov     qword ptr [rsp+458h+dwCreationDisposition], rax
0x18007cb59  lea     r9, [rsp+458h+var_260]
0x18007cb61  mov     r8, rdi
0x18007cb64  mov     rcx, r15
0x18007cb67  call    ?ShouldDownloadRangelessFile@CDeploymentSession@@QEAAJPEB_WQEBUPayload@ActionList@@PEAV?$set@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UWstringCaseInsensitiveCompare@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@PEAHPEA_K@Z; CDeploymentSession::ShouldDownloadRangelessFile(wchar_t const *,ActionList::Payload const * const,std::set<std::wstring,WstringCaseInsensitiveCompare,std::allocator<std::wstring>> *,int *,unsigned __int64 *)
0x18007cb6c  mov     r14d, eax
0x18007cb6f  test    eax, eax
0x18007cb71  jns     short loc_18007CBB6
0x18007cb73  mov     rax, [r15+258h]
0x18007cb7a  xor     edi, edi
0x18007cb7c  mov     ecx, edi
0x18007cb7e  test    rax, rax
0x18007cb81  jz      loc_18007CB00
0x18007cb87  mov     [rsp+458h+dwFlagsAndAttributes], r14d
0x18007cb8c  mov     [rsp+458h+dwCreationDisposition], 1037h
0x18007cb94  lea     r9, aCdeploymentses_61; "CDeploymentSession::ProcessSandboxConta"...
0x18007cb9b  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x18007cba2  mov     edx, 4
0x18007cba7  mov     rcx, rax
0x18007cbaa  call    ?MoUpdateLogFormat@?$CMoUpdateLogT@VCEmptyType@@@@SAJPEAVIUpdateDiagnostics@@W4MOUPDATE_LOGLEVEL@@PEB_WZZ; CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(IUpdateDiagnostics *,MOUPDATE_LOGLEVEL,wchar_t const *,...)
0x18007cbaf  mov     ecx, eax
0x18007cbb1  jmp     loc_18007CAF7
0x18007cbb6  cmp     dword ptr [rsp+458h+hFile], ebx
0x18007cbbd  jz      loc_18007D1C7
0x18007cbc3  jmp     short loc_18007CBE9
0x18007cbc5  cmp     dword ptr [r13+68h], 2
0x18007cbca  jnz     short loc_18007CBE9
0x18007cbcc  mov     rcx, [r15+258h]
0x18007cbd3  test    rcx, rcx
0x18007cbd6  jz      short loc_18007CBE9
0x18007cbd8  lea     r8, aExpressPayload; "Express payload is found"
0x18007cbdf  mov     edx, 2
0x18007cbe4  call    ?MoUpdateLogFormat@?$CMoUpdateLogT@VCEmptyType@@@@SAJPEAVIUpdateDiagnostics@@W4MOUPDATE_LOGLEVEL@@PEB_WZZ; CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(IUpdateDiagnostics *,MOUPDATE_LOGLEVEL,wchar_t const *,...)
0x18007cbe9  cmp     dword ptr [r13+58h], 6
0x18007cbee  jnz     short loc_18007CC22
0x18007cbf0  mov     rdx, r13; struct ActionList::Package *
0x18007cbf3  mov     rcx, r15; this
0x18007cbf6  call    ?IsPackageFileListEmpty@CDeploymentSession@@QEAA_NQEBUPackage@ActionList@@@Z; CDeploymentSession::IsPackageFileListEmpty(ActionList::Package const * const)
0x18007cbfb  test    al, al
0x18007cbfd  jz      short loc_18007CC22
0x18007cbff  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18007cc06  test    rcx, rcx
0x18007cc09  jz      loc_18007D1C7
0x18007cc0f  lea     rax, [rdi+18h]
0x18007cc13  mov     qword ptr [rsp+458h+dwFlagsAndAttributes], rax
0x18007cc18  call    ??$LogNumObjects@$$BY0BF@DPEA_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEAY0BF@$$CBDAEBQEA_W@Z; LogAdapter::Logger::LogNumObjects<char [21],wchar_t *>(bool,LogAdapter::LogLevel,char const * const,char const (&)[21],wchar_t * const &)
0x18007cc1d  jmp     loc_18007D1C7
0x18007cc22  mov     rdx, [rdi+48h]
0x18007cc26  test    rdx, rdx
0x18007cc29  jz      short loc_18007CC35
0x18007cc2b  mov     [rsp+458h+var_2F8], rdx
0x18007cc33  jmp     short loc_18007CC41
0x18007cc35  mov     rax, [rdi+10h]
0x18007cc39  mov     [rsp+458h+var_2F8], rax
0x18007cc41  cmp     [rsp+458h+NumberOfBytesRead], ebx
0x18007cc48  jz      short loc_18007CC4E
0x18007cc4a  mov     rdx, [rdi+50h]
0x18007cc4e  test    rdx, rdx
0x18007cc51  jnz     short loc_18007CC57
0x18007cc53  mov     rdx, [rdi+18h]
0x18007cc57  mov     [rsp+458h+var_328], rdx
0x18007cc5f  mov     r12, [rdi+70h]
0x18007cc63  test    r12, r12
0x18007cc66  jnz     short loc_18007CC6C
0x18007cc68  mov     r12, [rdi+28h]
0x18007cc6c  test    rsi, rsi
0x18007cc6f  jz      short loc_18007CCA8
0x18007cc71  call    cs:__imp_GetProcessHeap
0x18007cc78  nop     dword ptr [rax+rax+00h]
0x18007cc7d  mov     rcx, rax; hHeap
0x18007cc80  lea     r8, [rsi-4]; lpMem
0x18007cc84  xor     edx, edx; dwFlags
0x18007cc86  call    cs:__imp_HeapFree
0x18007cc8d  nop     dword ptr [rax+rax+00h]
0x18007cc92  xor     ebx, ebx
0x18007cc94  xor     ecx, ecx
0x18007cc96  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18007cc9b  mov     [rsp+458h+lpFileName], rbx
0x18007cca0  mov     rdx, [rsp+458h+var_328]
0x18007cca8  lea     r9, [rsp+458h+lpFileName]
0x18007ccad  xor     r8d, r8d
0x18007ccb0  mov     rcx, [r15+1E8h]
0x18007ccb7  call    ?CombinePath@?$CMiscHelpersT@VCEmptyType@@@@SAJPEB_W00PEAPEA_W@Z; CMiscHelpersT<CEmptyType>::CombinePath(wchar_t const *,wchar_t const *,wchar_t const *,wchar_t * *)
0x18007ccbc  mov     r14d, eax
0x18007ccbf  test    eax, eax
0x18007ccc1  jns     short loc_18007CCE9
  ... truncated ...
```
