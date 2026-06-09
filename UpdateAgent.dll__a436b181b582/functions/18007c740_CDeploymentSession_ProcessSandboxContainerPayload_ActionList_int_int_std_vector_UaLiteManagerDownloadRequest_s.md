# CDeploymentSession::ProcessSandboxContainerPayload(ActionList *,int,int,std::vector<UaLiteManagerDownloadRequest,std::allocator<UaLiteManagerDownloadRequest>> *)

- ea: `0x18007c740`
- end: `0x18007f251`
- name: `?ProcessSandboxContainerPayload@CDeploymentSession@@QEAAJPEAUActionList@@HHPEAV?$vector@UUaLiteManagerDownloadRequest@@V?$allocator@UUaLiteManagerDownloadRequest@@@std@@@std@@@Z`
- size: `11025`
- prototype: `__int64 __usercall@<rax>(CDeploymentSession *this@<rcx>, __int64)`
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
// Hidden C++ exception states: #wind=108
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
  __int64 v20; // rdx
  __int64 v21; // r13
  const wchar_t *v22; // rax
  unsigned int v23; // eax
  int v24; // ecx
  __int64 v25; // rdi
  const wchar_t *v26; // rax
  const WCHAR *v27; // rdx
  int v28; // edx
  __int64 v29; // rax
  __int64 v30; // rcx
  __int64 v31; // rdx
  LPCWSTR v32; // rbx
  HANDLE v33; // rax
  __int64 v34; // rax
  __int64 v35; // rcx
  int v36; // edx
  int v37; // r8d
  int v38; // r9d
  const wchar_t *v39; // r12
  HANDLE ProcessHeap; // rax
  DWORD FileAttributesW; // eax
  BOOL v42; // ebx
  __int64 v43; // rax
  __int64 v44; // rax
  __int64 v45; // rcx
  int v46; // eax
  __int64 v47; // rdx
  union _LARGE_INTEGER v48; // rbx
  HANDLE v49; // rax
  CDeploymentSession *v50; // rcx
  int FileFromWim; // eax
  __int64 v52; // r8
  union _LARGE_INTEGER v53; // rbx
  HANDLE v54; // rax
  const wchar_t **v55; // rsi
  WCHAR *v56; // rbx
  HANDLE v57; // rax
  DWORD v58; // eax
  int v59; // ebx
  __int64 v60; // rbx
  bool v61; // zf
  __int64 v62; // rax
  __int64 v63; // rcx
  int v64; // eax
  __int64 v65; // rdx
  __int64 v66; // rdx
  __int64 v67; // r9
  __int64 v68; // rax
  __int64 v69; // r12
  unsigned __int64 v70; // rax
  __int64 *v71; // rcx
  __int64 v72; // rax
  __int64 v73; // rax
  __int64 v74; // rcx
  int v75; // eax
  __int64 v76; // rdx
  __int64 v77; // rax
  int v78; // eax
  __int64 v79; // rdx
  unsigned int i; // r13d
  wchar_t *v81; // rsi
  __int64 v82; // rax
  __int64 v83; // rax
  __int64 v84; // rcx
  int v85; // eax
  __int64 v86; // rdx
  LPCWSTR v87; // rbx
  HANDLE v88; // rax
  union _LARGE_INTEGER v89; // rdi
  __int64 (__fastcall *v90)(union _LARGE_INTEGER, __int64); // rbx
  __int64 v91; // rdx
  __int64 v92; // rax
  __int64 v93; // rcx
  int v94; // eax
  __int64 v95; // rdx
  union _LARGE_INTEGER v96; // rdi
  __int64 (__fastcall *v97)(union _LARGE_INTEGER, __int64); // rbx
  __int64 v98; // rdx
  int v99; // eax
  union _LARGE_INTEGER v100; // rbx
  __int64 (__fastcall *v101)(union _LARGE_INTEGER, union _LARGE_INTEGER *); // rdi
  _QWORD *v102; // rcx
  int v103; // eax
  int v104; // eax
  __int64 v105; // rax
  int v106; // eax
  DWORD v107; // eax
  BOOL v108; // ebx
  __int64 v109; // rax
  int v110; // eax
  CDeploymentSession *v111; // rcx
  int v112; // eax
  int v113; // eax
  DWORD v114; // eax
  DWORD v115; // ebx
  __int64 v116; // rdi
  __int64 v117; // r8
  __int64 v118; // rcx
  const wchar_t *v119; // rbx
  __int64 v120; // rcx
  int OffsetInOuterContainer; // eax
  unsigned int v122; // eax
  unsigned __int64 v123; // rbx
  unsigned int j; // esi
  __int64 v125; // rax
  int v126; // eax
  int v127; // eax
  __int64 v128; // rdx
  __int64 *v129; // rbx
  unsigned __int64 v130; // rax
  unsigned __int64 v131; // rbx
  unsigned __int64 v132; // rax
  unsigned int v133; // eax
  int v134; // eax
  __int64 v135; // r9
  __int64 v136; // rcx
  _QWORD *v137; // rdi
  const WCHAR *v138; // rdi
  const WCHAR *v139; // r12
  signed int LastError; // eax
  HANDLE FileW; // rax
  __int64 v142; // r13
  unsigned __int64 v143; // rcx
  _QWORD *v144; // r12
  __int64 k; // rax
  WCHAR *v146; // rcx
  signed int v147; // eax
  __int64 v148; // r9
  __int64 v149; // rcx
  union _LARGE_INTEGER v150; // rdx
  union _LARGE_INTEGER v151; // rdi
  _QWORD *v152; // rcx
  _QWORD *v153; // rax
  __int64 v154; // r10
  unsigned __int64 v155; // rdi
  __int64 v156; // rax
  __int64 v157; // rcx
  __int64 v158; // rcx
  void *v159; // rcx
  signed int v160; // eax
  __int64 v161; // rcx
  signed int v162; // eax
  wchar_t *v163; // rdi
  wchar_t *v164; // rax
  void *v165; // rcx
  signed int v166; // eax
  __int64 v167; // r9
  __int64 v168; // rdx
  __int64 v169; // rcx
  __int64 v170; // rcx
  int v171; // eax
  void *v172; // rcx
  signed int v173; // eax
  __int64 v174; // rcx
  __int64 v175; // rcx
  const WCHAR *v176; // rdi
  signed int v177; // eax
  __int64 **v178; // rcx
  __int64 *ii; // rax
  signed int v180; // eax
  int v181; // eax
  LPCWSTR v182; // r9
  HANDLE v183; // rax
  char *v184; // rdi
  LARGE_INTEGER v185; // r14
  signed int v186; // eax
  __int64 v187; // r9
  signed int v188; // eax
  __int64 v189; // rcx
  signed int v190; // eax
  __int64 v191; // r9
  __int64 v192; // rdx
  int v193; // eax
  DWORD LowPart; // r8d
  void *v195; // rcx
  signed int v196; // eax
  void *v197; // rcx
  signed int v198; // eax
  void *v199; // rcx
  signed int v200; // eax
  signed int v201; // eax
  void *v202; // rcx
  BOOL v203; // eax
  void *v204; // rcx
  signed int v205; // eax
  signed int v206; // eax
  signed int v207; // eax
  int v208; // eax
  __int64 v209; // rcx
  __int64 v210; // r9
  __int64 v211; // rdx
  const WCHAR *v212; // rdi
  signed int v213; // eax
  __int64 *jj; // rcx
  signed int v215; // eax
  const char *v216; // r9
  __int64 result; // rax
  DWORD dwCreationDisposition[2]; // [rsp+20h] [rbp-438h]
  DWORD dwFlagsAndAttributes[2]; // [rsp+28h] [rbp-430h]
  LPCWSTR lpFileName; // [rsp+40h] [rbp-418h] BYREF
  LPCWSTR lpExistingFileName; // [rsp+48h] [rbp-410h] BYREF
  unsigned __int64 QuadPart; // [rsp+50h] [rbp-408h] BYREF
  unsigned __int64 v223; // [rsp+58h] [rbp-400h] BYREF
  unsigned __int64 m; // [rsp+60h] [rbp-3F8h] BYREF
  __int128 v225; // [rsp+68h] [rbp-3F0h] BYREF
  unsigned __int64 v226[2]; // [rsp+78h] [rbp-3E0h] BYREF
  __int64 v227; // [rsp+88h] [rbp-3D0h]
  wchar_t *n; // [rsp+90h] [rbp-3C8h] BYREF
  __int64 *v229; // [rsp+98h] [rbp-3C0h] BYREF
  const wchar_t *v230; // [rsp+A0h] [rbp-3B8h] BYREF
  __int128 v231; // [rsp+A8h] [rbp-3B0h] BYREF
  __int64 v232; // [rsp+B8h] [rbp-3A0h]
  __int64 v233; // [rsp+C0h] [rbp-398h]
  DWORD nNumberOfBytesToRead[4]; // [rsp+C8h] [rbp-390h] BYREF
  LPVOID lpBuffer; // [rsp+D8h] [rbp-380h]
  __int64 v236; // [rsp+E0h] [rbp-378h] BYREF
  __int128 v237; // [rsp+E8h] [rbp-370h] BYREF
  __int64 v238; // [rsp+F8h] [rbp-360h]
  _BYTE v239[16]; // [rsp+100h] [rbp-358h] BYREF
  _QWORD v240[4]; // [rsp+110h] [rbp-348h] BYREF
  LPCWSTR v241; // [rsp+130h] [rbp-328h] BYREF
  LPCWSTR v242; // [rsp+138h] [rbp-320h] BYREF
  union _LARGE_INTEGER FileSize; // [rsp+140h] [rbp-318h] BYREF
  int v244; // [rsp+148h] [rbp-310h] BYREF
  union _LARGE_INTEGER NewFilePointer; // [rsp+150h] [rbp-308h] BYREF
  DWORD NumberOfBytesWritten[2]; // [rsp+158h] [rbp-300h] BYREF
  wchar_t *v247; // [rsp+160h] [rbp-2F8h] BYREF
  HANDLE hFile; // [rsp+168h] [rbp-2F0h] BYREF
  DWORD NumberOfBytesRead; // [rsp+170h] [rbp-2E8h] BYREF
  LPVOID pv; // [rsp+178h] [rbp-2E0h] BYREF
  LPVOID v251; // [rsp+180h] [rbp-2D8h] BYREF
  _QWORD v252[2]; // [rsp+188h] [rbp-2D0h] BYREF
  _QWORD v253[2]; // [rsp+198h] [rbp-2C0h] BYREF
  _QWORD v254[2]; // [rsp+1A8h] [rbp-2B0h] BYREF
  __int128 v255; // [rsp+1B8h] [rbp-2A0h] BYREF
  __int64 v256; // [rsp+1C8h] [rbp-290h]
  __int128 v257; // [rsp+1D0h] [rbp-288h] BYREF
  __int64 v258; // [rsp+1E0h] [rbp-278h]
  _QWORD v259[2]; // [rsp+1E8h] [rbp-270h] BYREF
  _QWORD v260[3]; // [rsp+1F8h] [rbp-260h] BYREF
  WCHAR TempFileName[264]; // [rsp+210h] [rbp-248h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+458h] [rbp+0h]

  v240[3] = -2;
  NumberOfBytesRead = a4;
  v5 = a3;
  v244 = a3;
  v8 = a5;
  v229 = a5;
  v9 = 0;
  lpFileName = 0;
  lpExistingFileName = 0;
  *(_OWORD *)nNumberOfBytesToRead = 0;
  lpBuffer = 0;
  v259[0] = 0;
  v259[1] = 0;
  try
  {
    v10 = operator new(0x40u);
    *v10 = v10;
    v10[1] = v10;
    v10[2] = v10;
    *((_WORD *)v10 + 12) = 257;
    v259[0] = v10;
    v257 = 0;
    v258 = 0;
    v255 = 0;
    v256 = 0;
    v251 = 0;
    pv = 0;
    v254[1] = 0;
    v11 = operator new(0x38u);
    *v11 = v11;
    v11[1] = v11;
    v11[2] = v11;
    *((_WORD *)v11 + 12) = 257;
    v254[0] = v11;
    v252[1] = 0;
    v12 = operator new(0x48u);
    *v12 = v12;
    v12[1] = v12;
    v12[2] = v12;
    *((_WORD *)v12 + 12) = 257;
    v252[0] = v12;
    v260[1] = 0;
    v13 = operator new(0x40u);
    *v13 = v13;
    v13[1] = v13;
    v13[2] = v13;
    *((_WORD *)v13 + 12) = 257;
    v260[0] = v13;
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
          CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)updated, v20);
      }
      else
      {
        v18 = 0;
      }
      goto LABEL_11;
    }
    v21 = *(_QWORD *)(a2 + 64);
    v22 = (const wchar_t *)(v21 + 168LL * *(unsigned int *)(a2 + 72));
    v230 = v22;
    while ( (const wchar_t *)v21 != v22 )
    {
      if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PlayB_ModelInstallation>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_PlayB_ModelInstallation>::GetImpl'::`2'::impl)
        || !v8 )
      {
        v242 = 0;
        if ( !v5 )
          goto LABEL_22;
        if ( (v23 = *(_DWORD *)(v21 + 88), v23 <= 0xF) && (v24 = 36992, _bittest(&v24, v23))
          || *(_DWORD *)(v21 + 104) == 2
          || *((_DWORD *)this + 114) == 8 )
        {
          *((_DWORD *)this + 71) = 1;
LABEL_22:
          v25 = *(_QWORD *)(v21 + 112);
          v26 = (const wchar_t *)(v25 + 184LL * *(unsigned int *)(v21 + 120));
          *(_QWORD *)NumberOfBytesWritten = v26;
          while ( 2 )
          {
            if ( (const wchar_t *)v25 == v26 )
            {
              DH_SSTRING::~DH_SSTRING((DH_SSTRING *)&v242);
              v8 = v229;
              break;
            }
            v225 = 0;
            v226[0] = 0;
            v226[1] = 0;
            v227 = 0;
            v241 = 0;
            if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PlayB_ModelInstallation>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_PlayB_ModelInstallation>::GetImpl'::`2'::impl) )
            {
              if ( !*(_QWORD *)(v25 + 48) || *(_DWORD *)(v21 + 88) == 24 )
                goto LABEL_118;
LABEL_29:
              if ( v5 )
              {
                v247 = *(wchar_t **)(v25 + 16);
                v27 = *(const WCHAR **)(v25 + 24);
                v241 = v27;
                goto LABEL_63;
              }
              if ( *(_BYTE *)(v25 + 153) )
              {
                LODWORD(hFile) = 0;
                v28 = (int)v242;
                if ( !v242 )
                {
                  PackageFileListPath = CDeploymentSession::GetPackageFileListPath(
                                          this,
                                          (const struct ActionList::Package *const)v21,
                                          (wchar_t **)&v242);
                  if ( PackageFileListPath < 0 )
                  {
                    v29 = *((_QWORD *)this + 75);
                    v30 = 0;
                    if ( !v29 )
                      goto LABEL_38;
                    dwFlagsAndAttributes[0] = PackageFileListPath;
                    dwCreationDisposition[0] = 4148;
                    v30 = (unsigned int)CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
                                          v29,
                                          4,
                                          L"%s(%d): Result = 0x%X",
                                          L"CDeploymentSession::ProcessSandboxContainerPayload",
                                          *(_QWORD *)dwCreationDisposition,
                                          *(_QWORD *)dwFlagsAndAttributes);
LABEL_36:
                    if ( (int)v30 < 0 )
                      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v30, v31);
                    goto LABEL_38;
                  }
                  v28 = (int)v242;
                }
                PackageFileListPath = CDeploymentSession::ShouldDownloadRangelessFile(
                                        (_DWORD)this,
                                        v28,
                                        v25,
                                        (unsigned int)v260,
                                        (__int64)&hFile,
                                        0);
                if ( PackageFileListPath < 0 )
                {
                  v34 = *((_QWORD *)this + 75);
                  v30 = 0;
                  if ( v34 )
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
              else if ( *(_DWORD *)(v21 + 104) == 2 )
              {
                v35 = *((_QWORD *)this + 75);
                if ( v35 )
                  CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(v35, 2, L"Express payload is found");
              }
              if ( *(_DWORD *)(v21 + 88) == 6
                && CDeploymentSession::IsPackageFileListEmpty(this, (const struct ActionList::Package *const)v21) )
              {
                if ( *(_QWORD *)&LogAdapter::g_Logger )
                  LogAdapter::Logger::LogNumObjects<char [21],wchar_t *>(
                    LogAdapter::g_Logger,
                    v36,
                    v37,
                    v38,
                    dwCreationDisposition[0],
                    v25 + 24);
                goto LABEL_118;
              }
              v27 = *(const WCHAR **)(v25 + 72);
              if ( v27 )
                v247 = *(wchar_t **)(v25 + 72);
              else
                v247 = *(wchar_t **)(v25 + 16);
              if ( NumberOfBytesRead )
                v27 = *(const WCHAR **)(v25 + 80);
              if ( !v27 )
                v27 = *(const WCHAR **)(v25 + 24);
              v241 = v27;
              v39 = *(const wchar_t **)(v25 + 112);
              if ( !v39 )
LABEL_63:
                v39 = *(const wchar_t **)(v25 + 40);
              if ( v9 )
              {
                ProcessHeap = GetProcessHeap();
                HeapFree(ProcessHeap, 0, (LPVOID)(v9 - 2));
                CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
                lpFileName = 0;
                v27 = v241;
              }
              PackageFileListPath = CMiscHelpersT<CEmptyType>::CombinePath(*((_QWORD *)this + 61), v27, 0, &lpFileName);
              if ( PackageFileListPath < 0 )
              {
                v34 = *((_QWORD *)this + 75);
                v30 = 0;
                if ( v34 )
                {
                  dwFlagsAndAttributes[0] = PackageFileListPath;
                  dwCreationDisposition[0] = 4190;
                  goto LABEL_45;
                }
LABEL_38:
                CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v30);
                goto LABEL_39;
              }
              v9 = lpFileName;
              FileAttributesW = GetFileAttributesW(lpFileName);
              v42 = FileAttributesW != -1 && (FileAttributesW & 0x10) == 0;
              CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
              CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
              PackageFileListPath = 0;
              if ( !v42 )
              {
                if ( (!NumberOfBytesRead || *((_BYTE *)this + 329)) && *(_QWORD *)(v25 + 48) )
                {
                  FileSize.QuadPart = 0;
                  v43 = _put___unique_any_t_V__unique_storage_U__resource_policy_PEA_WP6AJPEA_W__E_1_STRAPI_Release__YAJ0_ZU__integral_constant__K_0A__wistd__PEA_WPEA_W_0A___T_details_wil___details_wil___wil__QEAAPEAPEA_WXZ(&FileSize);
                  PackageFileListPath = CMiscHelpersT<CEmptyType>::CombinePath(
                                          *((_QWORD *)this + 61),
                                          *(_QWORD *)(v25 + 48),
                                          0,
                                          v43);
                  if ( PackageFileListPath < 0 )
                  {
                    v44 = *((_QWORD *)this + 75);
                    v45 = 0;
                    if ( v44 )
                    {
                      dwFlagsAndAttributes[0] = PackageFileListPath;
                      dwCreationDisposition[0] = 4205;
                      v46 = CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
                              v44,
                              4,
                              L"%s(%d): Result = 0x%X",
                              L"CDeploymentSession::ProcessSandboxContainerPayload",
                              *(_QWORD *)dwCreationDisposition,
                              *(_QWORD *)dwFlagsAndAttributes);
                      v45 = (unsigned int)v46;
                      if ( v46 < 0 )
                        CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v46, v47);
                    }
                    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v45);
                    v48 = FileSize;
                    if ( FileSize.QuadPart )
                    {
                      v49 = GetProcessHeap();
                      HeapFree(v49, 0, (LPVOID)(v48.QuadPart - 4));
                      v30 = 0;
                      goto LABEL_38;
                    }
LABEL_39:
                    v32 = v242;
                    if ( !v242 )
                      goto LABEL_558;
                    v33 = GetProcessHeap();
                    HeapFree(v33, 0, (LPVOID)(v32 - 2));
                    v18 = 0;
LABEL_11:
                    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v18);
LABEL_558:
                    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)PackageFileListPath);
                    std::_Tree<std::_Tset_traits<std::wstring,WstringCaseInsensitiveCompare,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,WstringCaseInsensitiveCompare,std::allocator<std::wstring>,0>>(v260);
                    __1___Tree_V___Tmap_traits_V__basic_string_view__WU__char_traits__W_std___std__V__vector_UContainerPayload__2__ProcessSandboxContainerPayload_CDeploymentSession__QEAAJPEAUActionList__HHPEAV__vector_UUaLiteManagerDownloadRequest__V__allocator_UUaLiteManagerDownloadRequest___std___std___Z_V__allocator_UContainerPayload__2__ProcessSandboxContainerPayload_CDeploymentSession__QEAAJPEAUActionList__HHPEAV__vector_UUaLiteManagerDownloadRequest__V__allocator_UUaLiteManagerDownloadRequest___std___std___Z__6__2_UWstringCaseInsensitiveCompare__V__allocator_U__pair___CBV__basic_string_view__WU__char_traits__W_std___std__V__vector_UContainerPayload__2__ProcessSandboxContainerPayload_CDeploymentSession__QEAAJPEAUActionList__HHPEAV__vector_UUaLiteManagerDownloadRequest__V__allocator_UUaLiteManagerDownloadRequest___std___std___Z_V__allocator_UContainerPayload__2__ProcessSandboxContainerPayload_CDeploymentSession__QEAAJPEAUActionList__HHPEAV__vector_UUaLiteManagerDownloadRequest__V__allocator_UUaLiteManagerDownloadRequest___std___std___Z__6__2__std___2__0A__std___std__QEAA_XZ(v252);
                    std::map<std::wstring_view,bool,WstringCaseInsensitiveCompare,std::allocator<std::pair<std::wstring_view const,bool>>>::~map<std::wstring_view,bool,WstringCaseInsensitiveCompare,std::allocator<std::pair<std::wstring_view const,bool>>>(v254);
                    if ( pv )
                      CoTaskMemFree(pv);
                    if ( v251 )
                      CoTaskMemFree(v251);
                    std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>::~vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>(&v255);
                    std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>::~vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>(&v257);
                    std::_Tree<std::_Tset_traits<std::wstring,WstringCaseInsensitiveCompare,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,WstringCaseInsensitiveCompare,std::allocator<std::wstring>,0>>(v259);
                    Windows::Auto<_LUTF8_STRING>::~Auto<_LUTF8_STRING>(nNumberOfBytesToRead);
                    DH_SSTRING::~DH_SSTRING((DH_SSTRING *)&lpExistingFileName);
                    DH_SSTRING::~DH_SSTRING((DH_SSTRING *)&lpFileName);
                    return (unsigned int)PackageFileListPath;
                  }
                  if ( (unsigned int)((__int64 (__fastcall *)(_QWORD))FileExists)((union _LARGE_INTEGER)FileSize.QuadPart) )
                  {
                    QuadPart = FileSize.QuadPart;
                    LogAdapter::TraceInfo<wchar_t const *,wchar_t *>("Extracting [{}] from [{}]", &v241, &QuadPart);
                    FileFromWim = CDeploymentSession::ExtractFileFromWim(
                                    v50,
                                    (const wchar_t *const)FileSize.QuadPart,
                                    v241,
                                    v9);
                    if ( FileFromWim < 0 )
                      wil::details::in1diag3::Throw_Hr(
                        retaddr,
                        (void *)0x1072,
                        (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\DeploymentSessionImpl.h",
                        (const char *)(unsigned int)FileFromWim,
                        dwCreationDisposition[0]);
                    v231 = 0;
                    v232 = 0;
                    v233 = 0;
                    v52 = -1;
                    do
                      ++v52;
                    while ( *(_WORD *)(FileSize.QuadPart + 2 * v52) );
                    ((void (__fastcall *)(_QWORD, _QWORD, _QWORD))std::wstring::_Construct<1,wchar_t const *>)(
                      &v231,
                      (union _LARGE_INTEGER)FileSize.QuadPart,
                      v52);
                    std::_Tree<std::_Tset_traits<std::wstring,WstringCaseInsensitiveCompare,std::allocator<std::wstring>,0>>::_Emplace<std::wstring>(
                      v259,
                      v239,
                      &v231);
                    std::wstring::~wstring(&v231);
                  }
                  v53 = FileSize;
                  if ( FileSize.QuadPart )
                  {
                    v54 = GetProcessHeap();
                    HeapFree(v54, 0, (LPVOID)(v53.QuadPart - 4));
                    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
                  }
                }
                else
                {
                  v55 = (const wchar_t **)(v25 + 48);
                  std::_Tree<std::_Tmap_traits<std::wstring_view,std::wstring_view,WstringCaseInsensitiveCompare,std::allocator<std::pair<std::wstring_view const,std::wstring_view>>,0>>::find<wchar_t *,WstringCaseInsensitiveCompare,0>(
                    v254,
                    &v223,
                    v25 + 48);
                  if ( v223 == v254[0] )
                  {
                    if ( lpExistingFileName )
                    {
                      v56 = (WCHAR *)(lpExistingFileName - 2);
                      v57 = GetProcessHeap();
                      HeapFree(v57, 0, v56);
                      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
                      lpExistingFileName = 0;
                    }
                    PackageFileListPath = CMiscHelpersT<CEmptyType>::CombinePath(
                                            *((_QWORD *)this + 61),
                                            *v55,
                                            0,
                                            &lpExistingFileName);
                    if ( PackageFileListPath < 0 )
                    {
                      v34 = *((_QWORD *)this + 75);
                      v30 = 0;
                      if ( !v34 )
                        goto LABEL_38;
                      dwFlagsAndAttributes[0] = PackageFileListPath;
                      dwCreationDisposition[0] = 4225;
LABEL_45:
                      v30 = (unsigned int)CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
                                            v34,
                                            4,
                                            L"%s(%d): Result = 0x%X",
                                            L"CDeploymentSession::ProcessSandboxContainerPayload",
                                            *(_QWORD *)dwCreationDisposition,
                                            *(_QWORD *)dwFlagsAndAttributes);
                      goto LABEL_36;
                    }
                    v58 = GetFileAttributesW(lpExistingFileName);
                    v59 = v58 != -1 && (v58 & 0x10) == 0;
                    LODWORD(hFile) = v59;
                    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
                    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
                    PackageFileListPath = 0;
                    std::_Tree<std::_Tmap_traits<std::wstring_view,bool,WstringCaseInsensitiveCompare,std::allocator<std::pair<std::wstring_view const,bool>>,0>>::emplace<wchar_t * const &,int &>(
                      v254,
                      v240,
                      v25 + 48,
                      &hFile);
                  }
                  else
                  {
                    v59 = *(unsigned __int8 *)(v223 + 48);
                    LODWORD(hFile) = v59;
                  }
                  if ( v59 )
                  {
                    std::_Tree<std::_Tmap_traits<std::wstring_view,std::wstring_view,WstringCaseInsensitiveCompare,std::allocator<std::pair<std::wstring_view const,std::wstring_view>>,0>>::find<wchar_t *,WstringCaseInsensitiveCompare,0>(
                      v252,
                      &NewFilePointer,
                      v25 + 48);
                    if ( NewFilePointer.QuadPart == v252[0] )
                    {
                      v237 = 0;
                      v238 = 0;
                      ___emplace_AEBQEB_WV__vector_UContainerPayload__2__ProcessSandboxContainerPayload_CDeploymentSession__QEAAJPEAUActionList__HHPEAV__vector_UUaLiteManagerDownloadRequest__V__allocator_UUaLiteManagerDownloadRequest___std___std___Z_V__allocator_UContainerPayload__2__ProcessSandboxContainerPayload_CDeploymentSession__QEAAJPEAUActionList__HHPEAV__vector_UUaLiteManagerDownloadRequest__V__allocator_UUaLiteManagerDownloadRequest___std___std___Z__6__std______Tree_V___Tmap_traits_V__basic_string_view__WU__char_traits__W_std___std__V__vector_UContainerPayload__2__ProcessSandboxContainerPayload_CDeploymentSession__QEAAJPEAUActionList__HHPEAV__vector_UUaLiteManagerDownloadRequest__V__allocator_UUaLiteManagerDownloadRequest___std___std___Z_V__allocator_UContainerPayload__2__ProcessSandboxContainerPayload_CDeploymentSession__QEAAJPEAUActionList__HHPEAV__vector_UUaLiteManagerDownloadRequest__V__allocator_UUaLiteManagerDownloadRequest___std___std___Z__6__2_UWstringCaseInsensitiveCompare__V__allocator_U__pair___CBV__basic_string_view__WU__char_traits__W_std___std__V__vector_UContainerPayload__2__ProcessSandboxContainerPayload_CDeploymentSession__QEAAJPEAUActionList__HHPEAV__vector_UUaLiteManagerDownloadRequest__V__allocator_UUaLiteManagerDownloadRequest___std___std___Z_V__allocator_UContainerPayload__2__ProcessSandboxContainerPayload_CDeploymentSession__QEAAJPEAUActionList__HHPEAV__vector_UUaLiteManagerDownloadRequest__V__allocator_UUaLiteManagerDownloadRequest___std___std___Z__6__2__std___2__0A__std___std__QEAA_AU__pair_V___Tree_iterator_V___Tree_val_U___Tree_simple_types_U__pair___CBV__basic_string_view__WU__char_traits__W_std___std__V__vector_UContainerPayload__2__ProcessSandboxContainerPayload_CDeploymentSession__QEAAJPEAUActionList__HHPEAV__vector_UUaLiteManagerDownloadRequest__V__allocator_UUaLiteManagerDownloadRequest___std___std___Z_V__allocator_UContainerPayload__2__ProcessSandboxContainerPayload_CDeploymentSession__QEAAJPEAUActionList__HHPEAV__vector_UUaLiteManagerDownloadRequest__V__allocator_UUaLiteManagerDownloadRequest___std___std___Z__6__2__std___std___std___std___N_1_AEBQEB_W__QEAV__vector_UContainerPayload__2__ProcessSandboxContainerPayload_CDeploymentSession__QEAAJPEAUActionList__HHPEAV__vector_UUaLiteManagerDownloadRequest__V__allocator_UUaLiteManagerDownloadRequest___std___std___Z_V__allocator_UContainerPayload__2__ProcessSandboxContainerPayload_CDeploymentSession__QEAAJPEAUActionList__HHPEAV__vector_UUaLiteManagerDownloadRequest__V__allocator_UUaLiteManagerDownloadRequest___std___std___Z__6__1__Z(
                        v252,
                        v253,
                        v25 + 48,
                        &v237);
                      __1__vector_UContainerPayload__2__ProcessSandboxContainerPayload_CDeploymentSession__QEAAJPEAUActionList__HHPEAV__vector_UUaLiteManagerDownloadRequest__V__allocator_UUaLiteManagerDownloadRequest___std___std___Z_V__allocator_UContainerPayload__2__ProcessSandboxContainerPayload_CDeploymentSession__QEAAJPEAUActionList__HHPEAV__vector_UUaLiteManagerDownloadRequest__V__allocator_UUaLiteManagerDownloadRequest___std___std___Z__6__std__QEAA_XZ(&v237);
                      v60 = v253[0] + 48LL;
                    }
                    else
                    {
                      v60 = NewFilePointer.QuadPart + 48;
                    }
                    *(_QWORD *)&v225 = v241;
                    *((_QWORD *)&v225 + 1) = v39;
                    if ( v244 || *(_DWORD *)(v25 + 8) != 2 || (v61 = *(_BYTE *)(v25 + 153) == 0, LOBYTE(v227) = 1, !v61) )
                      LOBYTE(v227) = 0;
                    PackageFileListPath = CDeploymentSession::GetOffsetInOuterContainer(
                                            this,
                                            *v55,
                                            *(const wchar_t **)(v25 + 56),
                                            v247,
                                            v39,
                                            v226,
                                            &v226[1]);
                    if ( PackageFileListPath < 0 )
                    {
                      v62 = *((_QWORD *)this + 75);
                      v63 = 0;
                      if ( v62 )
                      {
                        dwFlagsAndAttributes[0] = PackageFileListPath;
                        dwCreationDisposition[0] = 4262;
                        v64 = CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
                                v62,
                                4,
                                L"%s(%d): Result = 0x%X",
                                L"CDeploymentSession::ProcessSandboxContainerPayload",
                                *(_QWORD *)dwCreationDisposition,
                                *(_QWORD *)dwFlagsAndAttributes);
                        v63 = (unsigned int)v64;
                        if ( v64 < 0 )
                          CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v64, v65);
                      }
                      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v63);
                      DH_SSTRING::~DH_SSTRING((DH_SSTRING *)&v242);
                      goto LABEL_558;
                    }
                    v66 = *(_QWORD *)(v60 + 8);
                    if ( v66 == *(_QWORD *)(v60 + 16) )
                    {
                      ____Emplace_reallocate_UContainerPayload__2__ProcessSandboxContainerPayload_CDeploymentSession__QEAAJPEAUActionList__HHPEAV__vector_UUaLiteManagerDownloadRequest__V__allocator_UUaLiteManagerDownloadRequest___std___std___Z____vector_UContainerPayload__2__ProcessSandboxContainerPayload_CDeploymentSession__QEAAJPEAUActionList__HHPEAV__vector_UUaLiteManagerDownloadRequest__V__allocator_UUaLiteManagerDownloadRequest___std___std___Z_V__allocator_UContainerPayload__2__ProcessSandboxContainerPayload_CDeploymentSession__QEAAJPEAUActionList__HHPEAV__vector_UUaLiteManagerDownloadRequest__V__allocator_UUaLiteManagerDownloadRequest___std___std___Z__6__std__AEAAPEAUContainerPayload__2__ProcessSandboxContainerPayload_CDeploymentSession__QEAAJPEAUActionList__HHPEAV__vector_UUaLiteManagerDownloadRequest__V__allocator_UUaLiteManagerDownloadRequest___std___1__Z_QEAU2_2__34_QEAAJ0HH1_Z___QEAU2_2__34_QEAAJ0HH1_Z__Z(
                        v60,
                        v66,
                        &v225);
                    }
                    else
                    {
                      *(_OWORD *)v66 = v225;
                      *(_OWORD *)(v66 + 16) = *(_OWORD *)v226;
                      *(_QWORD *)(v66 + 32) = v227;
                      *(_QWORD *)(v60 + 8) += 40LL;
                    }
                  }
                  v9 = lpFileName;
                }
              }
              v5 = v244;
            }
            else if ( *(_QWORD *)(v25 + 48) )
            {
              goto LABEL_29;
            }
LABEL_118:
            v25 += 184;
            v26 = *(const wchar_t **)NumberOfBytesWritten;
            continue;
          }
        }
      }
      v21 += 168;
      v22 = v230;
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PlayB_ModelInstallation>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_PlayB_ModelInstallation>::GetImpl'::`2'::impl)
      && v8 )
    {
      v253[0] = 0;
      v253[1] = 0;
      v68 = std::_Allocate<16,std::_Default_allocate_traits>(64);
      *(_QWORD *)v68 = v68;
      *(_QWORD *)(v68 + 8) = v68;
      *(_QWORD *)(v68 + 16) = v68;
      *(_WORD *)(v68 + 24) = 257;
      v253[0] = v68;
      v69 = *v8;
      v70 = v8[1];
      m = v70;
      while ( v69 != v70 )
      {
        v242 = 0;
        LODWORD(hFile) = 0;
        v240[2] = 0;
        v71 = *(__int64 **)(v69 + 96);
        v72 = *v71;
        v242 = 0;
        PackageFileListPath = (*(__int64 (__fastcall **)(__int64 *, LPCWSTR *))(v72 + 40))(v71, &v242);
        if ( PackageFileListPath < 0 )
        {
          v73 = *((_QWORD *)this + 75);
          v74 = 0;
          if ( v73 )
          {
            dwFlagsAndAttributes[0] = PackageFileListPath;
            dwCreationDisposition[0] = 4279;
            v75 = CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
                    v73,
                    4,
                    L"%s(%d): Result = 0x%X",
                    L"CDeploymentSession::ProcessSandboxContainerPayload",
                    *(_QWORD *)dwCreationDisposition,
                    *(_QWORD *)dwFlagsAndAttributes);
            v74 = (unsigned int)v75;
            if ( v75 < 0 )
              CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v75, v76);
          }
LABEL_134:
          CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v74);
          if ( v242 )
            (*(void (__fastcall **)(LPCWSTR))(*(_QWORD *)v242 + 16LL))(v242);
          goto LABEL_136;
        }
        PackageFileListPath = (*(__int64 (__fastcall **)(LPCWSTR, HANDLE *))(*(_QWORD *)v242 + 24LL))(v242, &hFile);
        if ( PackageFileListPath < 0 )
        {
          v77 = *((_QWORD *)this + 75);
          v74 = 0;
          if ( v77 )
          {
            dwFlagsAndAttributes[0] = PackageFileListPath;
            dwCreationDisposition[0] = 4280;
            v78 = CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
                    v77,
                    4,
                    L"%s(%d): Result = 0x%X",
                    L"CDeploymentSession::ProcessSandboxContainerPayload",
                    *(_QWORD *)dwCreationDisposition,
                    *(_QWORD *)dwFlagsAndAttributes);
            v74 = (unsigned int)v78;
            if ( v78 < 0 )
              CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v78, v79);
          }
          goto LABEL_134;
        }
        for ( i = 0; i < (unsigned int)hFile; ++i )
        {
          v225 = 0;
          v226[0] = 0;
          v226[1] = 0;
          v227 = 0;
          FileSize.QuadPart = 0;
          NewFilePointer.QuadPart = 0;
          v223 = 0;
          QuadPart = 0;
          v244 = 0;
          v241 = 0;
          if ( *(_QWORD *)(v69 + 24) <= 7u )
            v81 = (wchar_t *)v69;
          else
            v81 = *(wchar_t **)v69;
          v247 = v81;
          v82 = *(_QWORD *)v242;
          FileSize.QuadPart = 0;
          PackageFileListPath = (*(__int64 (__fastcall **)(LPCWSTR, _QWORD, union _LARGE_INTEGER *))(v82 + 32))(
                                  v242,
                                  i,
                                  &FileSize);
          if ( PackageFileListPath < 0 )
          {
            v83 = *((_QWORD *)this + 75);
            v84 = 0;
            if ( v83 )
            {
              dwFlagsAndAttributes[0] = PackageFileListPath;
              dwCreationDisposition[0] = 4296;
              v85 = CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
                      v83,
                      4,
                      L"%s(%d): Result = 0x%X",
                      L"CDeploymentSession::ProcessSandboxContainerPayload",
                      *(_QWORD *)dwCreationDisposition,
                      *(_QWORD *)dwFlagsAndAttributes);
              v84 = (unsigned int)v85;
              if ( v85 < 0 )
                CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v85, v86);
            }
            CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v84);
            v87 = v241;
            if ( v241 )
            {
              v88 = GetProcessHeap();
              HeapFree(v88, 0, (LPVOID)(v87 - 2));
              CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
            }
            if ( NewFilePointer.QuadPart )
              (*(void (__fastcall **)(union _LARGE_INTEGER))(*(_QWORD *)NewFilePointer.QuadPart + 16LL))(NewFilePointer);
            if ( FileSize.QuadPart )
              (*(void (__fastcall **)(union _LARGE_INTEGER))(*(_QWORD *)FileSize.QuadPart + 16LL))(FileSize);
LABEL_255:
            if ( v242 )
              (*(void (__fastcall **)(LPCWSTR))(*(_QWORD *)v242 + 16LL))(v242);
            goto LABEL_136;
          }
          wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>::put(&v251);
          wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>::put(&pv);
          v89 = FileSize;
          v90 = *(__int64 (__fastcall **)(union _LARGE_INTEGER, __int64))(*(_QWORD *)FileSize.QuadPart + 24LL);
          v91 = wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>::put(&v251);
          PackageFileListPath = ((__int64 (__fastcall *)(_QWORD, _QWORD))v90)((union _LARGE_INTEGER)v89.QuadPart, v91);
          if ( PackageFileListPath < 0 )
          {
            v92 = *((_QWORD *)this + 75);
            v93 = 0;
            if ( v92 )
            {
              dwFlagsAndAttributes[0] = PackageFileListPath;
              dwCreationDisposition[0] = 4300;
              v94 = CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
                      v92,
                      4,
                      L"%s(%d): Result = 0x%X",
                      L"CDeploymentSession::ProcessSandboxContainerPayload",
                      *(_QWORD *)dwCreationDisposition,
                      *(_QWORD *)dwFlagsAndAttributes);
              v93 = (unsigned int)v94;
              if ( v94 < 0 )
                CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v94, v95);
            }
            CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v93);
            if ( v241 )
              STRAPI_Release((wchar_t *)v241);
            if ( NewFilePointer.QuadPart )
              (*(void (__fastcall **)(union _LARGE_INTEGER))(*(_QWORD *)NewFilePointer.QuadPart + 16LL))(NewFilePointer);
            if ( FileSize.QuadPart )
              (*(void (__fastcall **)(union _LARGE_INTEGER))(*(_QWORD *)FileSize.QuadPart + 16LL))(FileSize);
            goto LABEL_255;
          }
          v96 = FileSize;
          v97 = *(__int64 (__fastcall **)(union _LARGE_INTEGER, __int64))(*(_QWORD *)FileSize.QuadPart + 40LL);
          v98 = wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>::put(&pv);
          v99 = ((__int64 (__fastcall *)(_QWORD, _QWORD))v97)((union _LARGE_INTEGER)v96.QuadPart, v98);
          PackageFileListPath = v99;
          if ( v99 < 0 )
          {
            CMoUpdateLogT<CEmptyType>::MoUpdateLogError(
              *((_QWORD *)this + 75),
              (unsigned int)v99,
              L"CDeploymentSession::ProcessSandboxContainerPayload",
              4301);
            if ( v241 )
              STRAPI_Release((wchar_t *)v241);
            if ( NewFilePointer.QuadPart )
              (*(void (__fastcall **)(union _LARGE_INTEGER))(*(_QWORD *)NewFilePointer.QuadPart + 16LL))(NewFilePointer);
            if ( FileSize.QuadPart )
              (*(void (__fastcall **)(union _LARGE_INTEGER))(*(_QWORD *)FileSize.QuadPart + 16LL))(FileSize);
            goto LABEL_255;
          }
          v100 = FileSize;
          v101 = *(__int64 (__fastcall **)(union _LARGE_INTEGER, union _LARGE_INTEGER *))(*(_QWORD *)FileSize.QuadPart
                                                                                        + 48LL);
          v102 = (_QWORD *)NewFilePointer.QuadPart;
          NewFilePointer.QuadPart = 0;
          if ( v102 )
            (*(void (__fastcall **)(_QWORD *, _QWORD))(*v102 + 16LL))(v102, *v102);
          v103 = ((__int64 (__fastcall *)(_QWORD, _QWORD))v101)((union _LARGE_INTEGER)v100.QuadPart, &NewFilePointer);
          PackageFileListPath = v103;
          if ( v103 < 0 )
          {
            CMoUpdateLogT<CEmptyType>::MoUpdateLogError(
              *((_QWORD *)this + 75),
              (unsigned int)v103,
              L"CDeploymentSession::ProcessSandboxContainerPayload",
              4302);
            if ( v241 )
              STRAPI_Release((wchar_t *)v241);
            if ( NewFilePointer.QuadPart )
              (*(void (__fastcall **)(union _LARGE_INTEGER))(*(_QWORD *)NewFilePointer.QuadPart + 16LL))(NewFilePointer);
            if ( FileSize.QuadPart )
              (*(void (__fastcall **)(union _LARGE_INTEGER))(*(_QWORD *)FileSize.QuadPart + 16LL))(FileSize);
            goto LABEL_255;
          }
          v104 = (*(__int64 (__fastcall **)(union _LARGE_INTEGER, int *))(*(_QWORD *)NewFilePointer.QuadPart + 24LL))(
                   NewFilePointer,
                   &v244);
          PackageFileListPath = v104;
          if ( v104 < 0 )
          {
            CMoUpdateLogT<CEmptyType>::MoUpdateLogError(
              *((_QWORD *)this + 75),
              (unsigned int)v104,
              L"CDeploymentSession::ProcessSandboxContainerPayload",
              4303);
            if ( v241 )
              STRAPI_Release((wchar_t *)v241);
            if ( NewFilePointer.QuadPart )
              (*(void (__fastcall **)(union _LARGE_INTEGER))(*(_QWORD *)NewFilePointer.QuadPart + 16LL))(NewFilePointer);
            if ( FileSize.QuadPart )
              (*(void (__fastcall **)(union _LARGE_INTEGER))(*(_QWORD *)FileSize.QuadPart + 16LL))(FileSize);
            goto LABEL_255;
          }
          v105 = _put___unique_any_t_V__unique_storage_U__resource_policy_PEA_WP6AJPEA_W__E_1_STRAPI_Release__YAJ0_ZU__integral_constant__K_0A__wistd__PEA_WPEA_W_0A___T_details_wil___details_wil___wil__QEAAPEAPEA_WXZ(&v241);
          v106 = CMiscHelpersT<CEmptyType>::CombinePath(*((_QWORD *)this + 61), pv, 0, v105);
          PackageFileListPath = v106;
          if ( v106 < 0 )
          {
            CMoUpdateLogT<CEmptyType>::MoUpdateLogError(
              *((_QWORD *)this + 75),
              (unsigned int)v106,
              L"CDeploymentSession::ProcessSandboxContainerPayload",
              4305);
            if ( v241 )
              STRAPI_Release((wchar_t *)v241);
            if ( NewFilePointer.QuadPart )
              (*(void (__fastcall **)(union _LARGE_INTEGER))(*(_QWORD *)NewFilePointer.QuadPart + 16LL))(NewFilePointer);
            if ( FileSize.QuadPart )
              (*(void (__fastcall **)(union _LARGE_INTEGER))(*(_QWORD *)FileSize.QuadPart + 16LL))(FileSize);
            goto LABEL_255;
          }
          v107 = GetFileAttributesW(v241);
          v108 = v107 != -1 && (v107 & 0x10) == 0;
          CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
          CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
          PackageFileListPath = 0;
          if ( v108 )
          {
            __1__unique_any_t_V__unique_storage_U__resource_policy_PEA_WP6AJPEA_W__E_1_STRAPI_Release__YAJ0_ZU__integral_constant__K_0A__wistd__PEA_WPEA_W_0A___T_details_wil___details_wil___wil__QEAA_XZ(&v241);
            if ( NewFilePointer.QuadPart )
              (*(void (__fastcall **)(union _LARGE_INTEGER))(*(_QWORD *)NewFilePointer.QuadPart + 16LL))(NewFilePointer);
          }
          else if ( (!NumberOfBytesRead || *((_BYTE *)this + 329)) && v81 )
          {
            *(_QWORD *)NumberOfBytesWritten = 0;
            v109 = _put___unique_any_t_V__unique_storage_U__resource_policy_PEA_WP6AJPEA_W__E_1_STRAPI_Release__YAJ0_ZU__integral_constant__K_0A__wistd__PEA_WPEA_W_0A___T_details_wil___details_wil___wil__QEAAPEAPEA_WXZ(NumberOfBytesWritten);
            v110 = CMiscHelpersT<CEmptyType>::CombinePath(*((_QWORD *)this + 61), v81, 0, v109);
            PackageFileListPath = v110;
            if ( v110 < 0 )
            {
              CMoUpdateLogT<CEmptyType>::MoUpdateLogError(
                *((_QWORD *)this + 75),
                (unsigned int)v110,
                L"CDeploymentSession::ProcessSandboxContainerPayload",
                4320);
              __1__unique_any_t_V__unique_storage_U__resource_policy_PEA_WP6AJPEA_W__E_1_STRAPI_Release__YAJ0_ZU__integral_constant__K_0A__wistd__PEA_WPEA_W_0A___T_details_wil___details_wil___wil__QEAA_XZ(NumberOfBytesWritten);
              __1__unique_any_t_V__unique_storage_U__resource_policy_PEA_WP6AJPEA_W__E_1_STRAPI_Release__YAJ0_ZU__integral_constant__K_0A__wistd__PEA_WPEA_W_0A___T_details_wil___details_wil___wil__QEAA_XZ(&v241);
              if ( NewFilePointer.QuadPart )
                (*(void (__fastcall **)(union _LARGE_INTEGER))(*(_QWORD *)NewFilePointer.QuadPart + 16LL))(NewFilePointer);
              if ( FileSize.QuadPart )
                (*(void (__fastcall **)(union _LARGE_INTEGER))(*(_QWORD *)FileSize.QuadPart + 16LL))(FileSize);
              if ( v242 )
                (*(void (__fastcall **)(LPCWSTR))(*(_QWORD *)v242 + 16LL))(v242);
              goto LABEL_136;
            }
            if ( (unsigned int)FileExists(*(_QWORD *)NumberOfBytesWritten) )
            {
              v230 = *(const wchar_t **)NumberOfBytesWritten;
              v229 = (__int64 *)pv;
              LogAdapter::TraceInfo<wchar_t const *,wchar_t *>("Extracting [{}] from [{}]", &v229, &v230);
              v112 = CDeploymentSession::ExtractFileFromWim(
                       v111,
                       *(const wchar_t *const *)NumberOfBytesWritten,
                       (const wchar_t *const)pv,
                       v241);
              if ( v112 < 0 )
                wil::details::in1diag3::Throw_Hr(
                  retaddr,
                  (void *)0x10E5,
                  (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\DeploymentSessionImpl.h",
                  (const char *)(unsigned int)v112,
                  dwCreationDisposition[0]);
            }
            __1__unique_any_t_V__unique_storage_U__resource_policy_PEA_WP6AJPEA_W__E_1_STRAPI_Release__YAJ0_ZU__integral_constant__K_0A__wistd__PEA_WPEA_W_0A___T_details_wil___details_wil___wil__QEAA_XZ(NumberOfBytesWritten);
            __1__unique_any_t_V__unique_storage_U__resource_policy_PEA_WP6AJPEA_W__E_1_STRAPI_Release__YAJ0_ZU__integral_constant__K_0A__wistd__PEA_WPEA_W_0A___T_details_wil___details_wil___wil__QEAA_XZ(&v241);
            if ( NewFilePointer.QuadPart )
              (*(void (__fastcall **)(union _LARGE_INTEGER))(*(_QWORD *)NewFilePointer.QuadPart + 16LL))(NewFilePointer);
          }
          else
          {
            std::_Tree<std::_Tmap_traits<std::wstring_view,std::wstring_view,WstringCaseInsensitiveCompare,std::allocator<std::pair<std::wstring_view const,std::wstring_view>>,0>>::find<wchar_t *,WstringCaseInsensitiveCompare,0>(
              v254,
              &v236,
              &v247);
            if ( v236 == v254[0] )
            {
              SH_SSTRING::operator=(&lpExistingFileName);
              v113 = CMiscHelpersT<CEmptyType>::CombinePath(*((_QWORD *)this + 61), v81, 0, &lpExistingFileName);
              PackageFileListPath = v113;
              if ( v113 < 0 )
              {
                CMoUpdateLogT<CEmptyType>::MoUpdateLogError(
                  *((_QWORD *)this + 75),
                  (unsigned int)v113,
                  L"CDeploymentSession::ProcessSandboxContainerPayload",
                  4339);
                __1__unique_any_t_V__unique_storage_U__resource_policy_PEA_WP6AJPEA_W__E_1_STRAPI_Release__YAJ0_ZU__integral_constant__K_0A__wistd__PEA_WPEA_W_0A___T_details_wil___details_wil___wil__QEAA_XZ(&v241);
                if ( NewFilePointer.QuadPart )
                  (*(void (__fastcall **)(union _LARGE_INTEGER))(*(_QWORD *)NewFilePointer.QuadPart + 16LL))(NewFilePointer);
                if ( FileSize.QuadPart )
                  (*(void (__fastcall **)(union _LARGE_INTEGER))(*(_QWORD *)FileSize.QuadPart + 16LL))(FileSize);
                goto LABEL_255;
              }
              v114 = GetFileAttributesW(lpExistingFileName);
              v115 = v114 != -1 && (v114 & 0x10) == 0;
              NumberOfBytesWritten[0] = v115;
              CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
              CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
              PackageFileListPath = 0;
              std::_Tree<std::_Tmap_traits<std::wstring_view,bool,WstringCaseInsensitiveCompare,std::allocator<std::pair<std::wstring_view const,bool>>,0>>::emplace<wchar_t * const &,int &>(
                v254,
                &v237,
                &v247,
                NumberOfBytesWritten);
            }
            else
            {
              v115 = *(unsigned __int8 *)(v236 + 48);
              NumberOfBytesWritten[0] = v115;
            }
            if ( v115 )
            {
              std::_Tree<std::_Tmap_traits<std::wstring_view,std::wstring_view,WstringCaseInsensitiveCompare,std::allocator<std::pair<std::wstring_view const,std::wstring_view>>,0>>::find<wchar_t *,WstringCaseInsensitiveCompare,0>(
                v252,
                &n,
                &v247);
              if ( n == (wchar_t *)v252[0] )
              {
                v231 = 0;
                v232 = 0;
                ___emplace_AEBQEB_WV__vector_UContainerPayload__2__ProcessSandboxContainerPayload_CDeploymentSession__QEAAJPEAUActionList__HHPEAV__vector_UUaLiteManagerDownloadRequest__V__allocator_UUaLiteManagerDownloadRequest___std___std___Z_V__allocator_UContainerPayload__2__ProcessSandboxContainerPayload_CDeploymentSession__QEAAJPEAUActionList__HHPEAV__vector_UUaLiteManagerDownloadRequest__V__allocator_UUaLiteManagerDownloadRequest___std___std___Z__6__std______Tree_V___Tmap_traits_V__basic_string_view__WU__char_traits__W_std___std__V__vector_UContainerPayload__2__ProcessSandboxContainerPayload_CDeploymentSession__QEAAJPEAUActionList__HHPEAV__vector_UUaLiteManagerDownloadRequest__V__allocator_UUaLiteManagerDownloadRequest___std___std___Z_V__allocator_UContainerPayload__2__ProcessSandboxContainerPayload_CDeploymentSession__QEAAJPEAUActionList__HHPEAV__vector_UUaLiteManagerDownloadRequest__V__allocator_UUaLiteManagerDownloadRequest___std___std___Z__6__2_UWstringCaseInsensitiveCompare__V__allocator_U__pair___CBV__basic_string_view__WU__char_traits__W_std___std__V__vector_UContainerPayload__2__ProcessSandboxContainerPayload_CDeploymentSession__QEAAJPEAUActionList__HHPEAV__vector_UUaLiteManagerDownloadRequest__V__allocator_UUaLiteManagerDownloadRequest___std___std___Z_V__allocator_UContainerPayload__2__ProcessSandboxContainerPayload_CDeploymentSession__QEAAJPEAUActionList__HHPEAV__vector_UUaLiteManagerDownloadRequest__V__allocator_UUaLiteManagerDownloadRequest___std___std___Z__6__2__std___2__0A__std___std__QEAA_AU__pair_V___Tree_iterator_V___Tree_val_U___Tree_simple_types_U__pair___CBV__basic_string_view__WU__char_traits__W_std___std__V__vector_UContainerPayload__2__ProcessSandboxContainerPayload_CDeploymentSession__QEAAJPEAUActionList__HHPEAV__vector_UUaLiteManagerDownloadRequest__V__allocator_UUaLiteManagerDownloadRequest___std___std___Z_V__allocator_UContainerPayload__2__ProcessSandboxContainerPayload_CDeploymentSession__QEAAJPEAUActionList__HHPEAV__vector_UUaLiteManagerDownloadRequest__V__allocator_UUaLiteManagerDownloadRequest___std___std___Z__6__2__std___std___std___std___N_1_AEBQEB_W__QEAV__vector_UContainerPayload__2__ProcessSandboxContainerPayload_CDeploymentSession__QEAAJPEAUActionList__HHPEAV__vector_UUaLiteManagerDownloadRequest__V__allocator_UUaLiteManagerDownloadRequest___std___std___Z_V__allocator_UContainerPayload__2__ProcessSandboxContainerPayload_CDeploymentSession__QEAAJPEAUActionList__HHPEAV__vector_UUaLiteManagerDownloadRequest__V__allocator_UUaLiteManagerDownloadRequest___std___std___Z__6__1__Z(
                  v252,
                  v240,
                  &v247,
                  &v231);
                __1__vector_UContainerPayload__2__ProcessSandboxContainerPayload_CDeploymentSession__QEAAJPEAUActionList__HHPEAV__vector_UUaLiteManagerDownloadRequest__V__allocator_UUaLiteManagerDownloadRequest___std___std___Z_V__allocator_UContainerPayload__2__ProcessSandboxContainerPayload_CDeploymentSession__QEAAJPEAUActionList__HHPEAV__vector_UUaLiteManagerDownloadRequest__V__allocator_UUaLiteManagerDownloadRequest___std___std___Z__6__std__QEAA_XZ(&v231);
                v116 = v240[0] + 48LL;
              }
              else
              {
                v116 = (__int64)(n + 24);
              }
              v117 = to_wstring(&v231, v251);
              std::_Tree<std::_Tset_traits<std::wstring,WstringCaseInsensitiveCompare,std::allocator<std::wstring>,0>>::_Emplace<std::wstring>(
                v253,
                v239,
                v117);
              std::wstring::~wstring(&v231);
              if ( v239[8] )
              {
                if ( *((_QWORD *)&v257 + 1) == v258 )
                {
                  std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>::_Emplace_reallocate<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>(
                    &v257,
                    *((_QWORD *)&v257 + 1),
                    &pv);
                  v118 = *((_QWORD *)&v257 + 1);
                }
                else
                {
                  **((_QWORD **)&v257 + 1) = pv;
                  pv = 0;
                  v118 = *((_QWORD *)&v257 + 1) + 8LL;
                  *((_QWORD *)&v257 + 1) += 8LL;
                }
                v119 = *(const wchar_t **)(v257 + 8 * ((v118 - (__int64)v257) >> 3) - 8);
                *(_QWORD *)&v225 = v119;
                if ( *((_QWORD *)&v255 + 1) == v256 )
                {
                  std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>::_Emplace_reallocate<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>(
                    &v255,
                    *((_QWORD *)&v255 + 1),
                    &v251);
                  v120 = *((_QWORD *)&v255 + 1);
                }
                else
                {
                  **((_QWORD **)&v255 + 1) = v251;
                  v251 = 0;
                  v120 = *((_QWORD *)&v255 + 1) + 8LL;
                  *((_QWORD *)&v255 + 1) += 8LL;
                }
                *((_QWORD *)&v225 + 1) = *(_QWORD *)(v255 + 8 * ((v120 - (__int64)v255) >> 3) - 8);
                OffsetInOuterContainer = CDeploymentSession::GetOffsetInOuterContainer(
                                           this,
                                           v81,
                                           0,
                                           v119,
                                           *((const wchar_t **)&v225 + 1),
                                           &v223,
                                           &QuadPart);
                PackageFileListPath = OffsetInOuterContainer;
                if ( OffsetInOuterContainer < 0 )
                {
                  CMoUpdateLogT<CEmptyType>::MoUpdateLogError(
                    *((_QWORD *)this + 75),
                    (unsigned int)OffsetInOuterContainer,
                    L"CDeploymentSession::ProcessSandboxContainerPayload",
                    4381);
                  __1__unique_any_t_V__unique_storage_U__resource_policy_PEA_WP6AJPEA_W__E_1_STRAPI_Release__YAJ0_ZU__integral_constant__K_0A__wistd__PEA_WPEA_W_0A___T_details_wil___details_wil___wil__QEAA_XZ(&v241);
                  if ( NewFilePointer.QuadPart )
                    (*(void (__fastcall **)(union _LARGE_INTEGER))(*(_QWORD *)NewFilePointer.QuadPart + 16LL))(NewFilePointer);
                  if ( FileSize.QuadPart )
                    (*(void (__fastcall **)(union _LARGE_INTEGER))(*(_QWORD *)FileSize.QuadPart + 16LL))(FileSize);
                  goto LABEL_255;
                }
                v122 = v244;
                if ( v244 )
                {
                  v123 = 0;
                  for ( j = 0; j < v122; ++j )
                  {
                    v247 = 0;
                    *(_QWORD *)NumberOfBytesWritten = 0;
                    v125 = *(_QWORD *)NewFilePointer.QuadPart;
                    *(_QWORD *)NumberOfBytesWritten = 0;
                    v126 = (*(__int64 (__fastcall **)(union _LARGE_INTEGER, _QWORD, DWORD *))(v125 + 32))(
                             NewFilePointer,
                             j,
                             NumberOfBytesWritten);
                    PackageFileListPath = v126;
                    if ( v126 < 0 )
                    {
                      CMoUpdateLogT<CEmptyType>::MoUpdateLogError(
                        *((_QWORD *)this + 75),
                        (unsigned int)v126,
                        L"CDeploymentSession::ProcessSandboxContainerPayload",
                        4391);
                      if ( *(_QWORD *)NumberOfBytesWritten )
                        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)NumberOfBytesWritten + 16LL))(*(_QWORD *)NumberOfBytesWritten);
                      __1__unique_any_t_V__unique_storage_U__resource_policy_PEA_WP6AJPEA_W__E_1_STRAPI_Release__YAJ0_ZU__integral_constant__K_0A__wistd__PEA_WPEA_W_0A___T_details_wil___details_wil___wil__QEAA_XZ(&v241);
                      if ( NewFilePointer.QuadPart )
                        (*(void (__fastcall **)(union _LARGE_INTEGER))(*(_QWORD *)NewFilePointer.QuadPart + 16LL))(NewFilePointer);
                      if ( FileSize.QuadPart )
                        (*(void (__fastcall **)(union _LARGE_INTEGER))(*(_QWORD *)FileSize.QuadPart + 16LL))(FileSize);
                      goto LABEL_287;
                    }
                    v127 = (*(__int64 (__fastcall **)(_QWORD, wchar_t **))(**(_QWORD **)NumberOfBytesWritten + 32LL))(
                             *(_QWORD *)NumberOfBytesWritten,
                             &v247);
                    PackageFileListPath = v127;
                    if ( v127 < 0 )
                    {
                      CMoUpdateLogT<CEmptyType>::MoUpdateLogError(
                        *((_QWORD *)this + 75),
                        (unsigned int)v127,
                        L"CDeploymentSession::ProcessSandboxContainerPayload",
                        4392);
                      if ( *(_QWORD *)NumberOfBytesWritten )
                        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)NumberOfBytesWritten + 16LL))(*(_QWORD *)NumberOfBytesWritten);
                      __1__unique_any_t_V__unique_storage_U__resource_policy_PEA_WP6AJPEA_W__E_1_STRAPI_Release__YAJ0_ZU__integral_constant__K_0A__wistd__PEA_WPEA_W_0A___T_details_wil___details_wil___wil__QEAA_XZ(&v241);
                      if ( NewFilePointer.QuadPart )
                        (*(void (__fastcall **)(union _LARGE_INTEGER))(*(_QWORD *)NewFilePointer.QuadPart + 16LL))(NewFilePointer);
                      if ( FileSize.QuadPart )
                        (*(void (__fastcall **)(union _LARGE_INTEGER))(*(_QWORD *)FileSize.QuadPart + 16LL))(FileSize);
                      goto LABEL_287;
                    }
                    if ( (unsigned __int64)v247 + v123 < v123 )
                    {
                      PackageFileListPath = -2147024362;
                      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942934LL, 0);
                    }
                    else
                    {
                      v123 += (unsigned __int64)v247;
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
                      __1__unique_any_t_V__unique_storage_U__resource_policy_PEA_WP6AJPEA_W__E_1_STRAPI_Release__YAJ0_ZU__integral_constant__K_0A__wistd__PEA_WPEA_W_0A___T_details_wil___details_wil___wil__QEAA_XZ(&v241);
                      if ( NewFilePointer.QuadPart )
                        (*(void (__fastcall **)(union _LARGE_INTEGER))(*(_QWORD *)NewFilePointer.QuadPart + 16LL))(NewFilePointer);
                      if ( FileSize.QuadPart )
                        (*(void (__fastcall **)(union _LARGE_INTEGER))(*(_QWORD *)FileSize.QuadPart + 16LL))(FileSize);
LABEL_287:
                      if ( v242 )
                        (*(void (__fastcall **)(LPCWSTR))(*(_QWORD *)v242 + 16LL))(v242);
LABEL_136:
                      std::_Tree<std::_Tset_traits<std::wstring,WstringCaseInsensitiveCompare,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,WstringCaseInsensitiveCompare,std::allocator<std::wstring>,0>>(v253);
                      goto LABEL_558;
                    }
                    if ( *(_QWORD *)NumberOfBytesWritten )
                      (*(void (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)NumberOfBytesWritten + 16LL))(
                        *(_QWORD *)NumberOfBytesWritten,
                        0);
                    v122 = v244;
                  }
                  v226[0] = v223;
                  v226[1] = v123;
                }
                else
                {
                  v226[0] = v223;
                  v226[1] = QuadPart;
                }
                LOBYTE(v227) = 0;
                v128 = *(_QWORD *)(v116 + 8);
                if ( v128 == *(_QWORD *)(v116 + 16) )
                {
                  ____Emplace_reallocate_UContainerPayload__2__ProcessSandboxContainerPayload_CDeploymentSession__QEAAJPEAUActionList__HHPEAV__vector_UUaLiteManagerDownloadRequest__V__allocator_UUaLiteManagerDownloadRequest___std___std___Z____vector_UContainerPayload__2__ProcessSandboxContainerPayload_CDeploymentSession__QEAAJPEAUActionList__HHPEAV__vector_UUaLiteManagerDownloadRequest__V__allocator_UUaLiteManagerDownloadRequest___std___std___Z_V__allocator_UContainerPayload__2__ProcessSandboxContainerPayload_CDeploymentSession__QEAAJPEAUActionList__HHPEAV__vector_UUaLiteManagerDownloadRequest__V__allocator_UUaLiteManagerDownloadRequest___std___std___Z__6__std__AEAAPEAUContainerPayload__2__ProcessSandboxContainerPayload_CDeploymentSession__QEAAJPEAUActionList__HHPEAV__vector_UUaLiteManagerDownloadRequest__V__allocator_UUaLiteManagerDownloadRequest___std___1__Z_QEAU2_2__34_QEAAJ0HH1_Z___QEAU2_2__34_QEAAJ0HH1_Z__Z(
                    v116,
                    v128,
                    &v225);
                }
                else
                {
                  *(_OWORD *)v128 = v225;
                  *(_OWORD *)(v128 + 16) = *(_OWORD *)v226;
                  *(_QWORD *)(v128 + 32) = v227;
                  *(_QWORD *)(v116 + 8) += 40LL;
                }
                __1__unique_any_t_V__unique_storage_U__resource_policy_PEA_WP6AJPEA_W__E_1_STRAPI_Release__YAJ0_ZU__integral_constant__K_0A__wistd__PEA_WPEA_W_0A___T_details_wil___details_wil___wil__QEAA_XZ(&v241);
                if ( NewFilePointer.QuadPart )
                  (*(void (__fastcall **)(union _LARGE_INTEGER))(*(_QWORD *)NewFilePointer.QuadPart + 16LL))(NewFilePointer);
              }
              else
              {
                __1__unique_any_t_V__unique_storage_U__resource_policy_PEA_WP6AJPEA_W__E_1_STRAPI_Release__YAJ0_ZU__integral_constant__K_0A__wistd__PEA_WPEA_W_0A___T_details_wil___details_wil___wil__QEAA_XZ(&v241);
                if ( NewFilePointer.QuadPart )
                  (*(void (__fastcall **)(union _LARGE_INTEGER))(*(_QWORD *)NewFilePointer.QuadPart + 16LL))(NewFilePointer);
              }
            }
            else
            {
              __1__unique_any_t_V__unique_storage_U__resource_policy_PEA_WP6AJPEA_W__E_1_STRAPI_Release__YAJ0_ZU__integral_constant__K_0A__wistd__PEA_WPEA_W_0A___T_details_wil___details_wil___wil__QEAA_XZ(&v241);
              if ( NewFilePointer.QuadPart )
                (*(void (__fastcall **)(union _LARGE_INTEGER))(*(_QWORD *)NewFilePointer.QuadPart + 16LL))(NewFilePointer);
            }
          }
          if ( FileSize.QuadPart )
            (*(void (__fastcall **)(union _LARGE_INTEGER))(*(_QWORD *)FileSize.QuadPart + 16LL))(FileSize);
        }
        if ( v242 )
          (*(void (__fastcall **)(LPCWSTR))(*(_QWORD *)v242 + 16LL))(v242);
        v69 += 104;
        v70 = m;
      }
      std::_Tree<std::_Tset_traits<std::wstring,WstringCaseInsensitiveCompare,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,WstringCaseInsensitiveCompare,std::allocator<std::wstring>,0>>(v253);
    }
    v129 = *(__int64 **)v252[0];
LABEL_308:
    if ( *((_BYTE *)v129 + 25) )
    {
      v130 = *(_QWORD *)v259[0];
      QuadPart = *(_QWORD *)v259[0];
      while ( !*(_BYTE *)(v130 + 25) )
      {
        v131 = v130 + 32;
        if ( *(_QWORD *)(v130 + 56) <= 7u )
          v132 = v130 + 32;
        else
          v132 = *(_QWORD *)v131;
        m = v132;
        LogAdapter::TraceInfo<wchar_t const *>("Deleting file [{}]", &m);
        if ( *(_QWORD *)(v131 + 24) > 7u )
          v131 = *(_QWORD *)v131;
        v133 = DeleteFileW((LPCWSTR)v131);
        LogAdapter::TraceWarningIfWin32BoolFalse<>(v133, "Failed to delete file");
        std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::wstring>>,std::_Iterator_base0>::operator++(&QuadPart);
        v130 = QuadPart;
      }
      goto LABEL_558;
    }
    v241 = (LPCWSTR)-1LL;
    FileSize.QuadPart = 0;
    LOBYTE(v67) = 0;
    ____Sort_unchecked_PEAUContainerPayload__2__ProcessSandboxContainerPayload_CDeploymentSession__QEAAJPEAUActionList__HHPEAV__vector_UUaLiteManagerDownloadRequest__V__allocator_UUaLiteManagerDownloadRequest___std___std___Z_U_unnamed_type_containerPayloadCompare___2__23_QEAAJ0HH1_Z__std__YAXPEAUContainerPayload__2__ProcessSandboxContainerPayload_CDeploymentSession__QEAAJPEAUActionList__HHPEAV__vector_UUaLiteManagerDownloadRequest__V__allocator_UUaLiteManagerDownloadRequest___std___0__Z_2_JU_unnamed_type_containerPayloadCompare___2__23_QEAAJ0HH1_Z__Z(
      v129[6],
      v129[7],
      0xCCCCCCCCCCCCCCCDuLL * ((v129[7] - v129[6]) >> 3),
      v67);
    SH_SSTRING::operator=(&lpExistingFileName);
    v134 = CMiscHelpersT<CEmptyType>::CombinePath(*((_QWORD *)this + 61), v129[4], 0, &lpExistingFileName);
    PackageFileListPath = v134;
    if ( v134 < 0 )
    {
      v135 = 4424;
      v136 = *((_QWORD *)this + 75);
      goto LABEL_322;
    }
    v137 = (_QWORD *)v129[6];
    if ( v129[7] - (_QWORD)v137 == 40 )
    {
      SH_SSTRING::operator=(&lpFileName);
      v134 = CMiscHelpersT<CEmptyType>::CombinePath(*((_QWORD *)this + 61), *v137, 0, &lpFileName);
      PackageFileListPath = v134;
      v136 = *((_QWORD *)this + 75);
      if ( v134 >= 0 )
      {
        v138 = lpFileName;
        v139 = lpExistingFileName;
        if ( v136 )
          CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
            v136,
            1,
            L"Single payload chunk; renaming [%ws] to [%ws]",
            lpExistingFileName,
            lpFileName);
        if ( !MoveFileExW(v139, v138, 9u) )
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
      v135 = 4430;
LABEL_322:
      CMoUpdateLogT<CEmptyType>::MoUpdateLogError(
        v136,
        (unsigned int)v134,
        L"CDeploymentSession::ProcessSandboxContainerPayload",
        v135);
      goto LABEL_558;
    }
    FileW = CreateFileW(lpExistingFileName, 0xC0000000, 1u, 0, 3u, 0x10000000u, 0);
    SH_FILENT::operator=(&v241, FileW);
    v142 = (__int64)v241;
    if ( (unsigned __int64)v241 - 1 > 0xFFFFFFFFFFFFFFFDuLL )
    {
      v215 = GetLastError();
      PackageFileListPath = v215;
      if ( v215 )
      {
        if ( v215 > 0 )
          PackageFileListPath = (unsigned __int16)v215 | 0x80070000;
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
    v143 = 0;
    v223 = 0;
    v144 = 0;
    for ( k = v129[6]; k != v129[7]; k += 40 )
    {
      if ( *(_BYTE *)(k + 32) )
      {
        v144 = (_QWORD *)k;
      }
      else
      {
        v143 += *(_QWORD *)(k + 24);
        v223 = v143;
      }
    }
    v146 = 0;
    if ( (unsigned __int64)v241 - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
      v146 = (WCHAR *)v241;
    if ( !GetFileSizeEx(v146, &FileSize) )
    {
      v147 = GetLastError();
      PackageFileListPath = v147;
      if ( v147 )
      {
        if ( v147 > 0 )
          PackageFileListPath = (unsigned __int16)v147 | 0x80070000;
      }
      else
      {
        PackageFileListPath = -2147467259;
      }
      v148 = 4464;
      goto LABEL_346;
    }
    v149 = *((_QWORD *)this + 75);
    if ( v149 )
      CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(v149, 2, L"Validating container file [%ws]", v129[4]);
    v150 = FileSize;
    v151 = FileSize;
    v152 = (_QWORD *)v129[6];
    v153 = (_QWORD *)v129[7];
    for ( m = (unsigned __int64)v153; ; v153 = (_QWORD *)m )
    {
      QuadPart = (unsigned __int64)v152;
      if ( v152 == v153 )
        break;
      v151.QuadPart -= v152[3];
      v154 = *((_QWORD *)this + 75);
      if ( v154 )
      {
        CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
          v154,
          1,
          L"  Expecting container payload: %ws, original offset: %llu, new offset: %llu, length: %llu",
          *v152,
          v152[2],
          v151.QuadPart,
          v152[3]);
        v150 = FileSize;
        v152 = (_QWORD *)QuadPart;
      }
      v152 += 5;
    }
    v155 = v223;
    if ( v144 )
      v156 = v150.QuadPart - v223;
    else
      v156 = 0;
    if ( *((_DWORD *)this + 64) && v156 <= 0 )
    {
      v157 = *((_QWORD *)this + 75);
      if ( v157 )
      {
        CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
          v157,
          2,
          L"Container file does not contain variable payload, but the LCU is being reoffered.");
        v150 = FileSize;
      }
      v144 = 0;
    }
    else if ( v144 )
    {
      if ( v156 <= 0 )
      {
LABEL_372:
        if ( (unsigned __int64)(v142 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
        {
          CloseHandle((HANDLE)v142);
          v142 = -1;
          v241 = (LPCWSTR)-1LL;
          v150 = FileSize;
        }
        v161 = *((_QWORD *)this + 75);
        if ( v161 )
          CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
            v161,
            2,
            L"Deleting corrupt container file. Actual size: [%llu], Minimum expected size: [%llu]",
            v150.QuadPart,
            v155);
        if ( DeleteFileW(lpExistingFileName) )
        {
          if ( (unsigned __int64)(v142 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
            CloseHandle((HANDLE)v142);
          goto LABEL_431;
        }
        v162 = GetLastError();
        PackageFileListPath = v162;
        if ( v162 )
        {
          if ( v162 > 0 )
            PackageFileListPath = (unsigned __int16)v162 | 0x80070000;
        }
        else
        {
          PackageFileListPath = -2147467259;
        }
        v148 = 4498;
LABEL_346:
        CMoUpdateLogT<CEmptyType>::MoUpdateLogError(
          *((_QWORD *)this + 75),
          (unsigned int)PackageFileListPath,
          L"CDeploymentSession::ProcessSandboxContainerPayload",
          v148);
        goto LABEL_556;
      }
      goto LABEL_364;
    }
    if ( v150.QuadPart != v155 )
      goto LABEL_372;
LABEL_364:
    v158 = *((_QWORD *)this + 75);
    if ( v158 )
    {
      CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
        v158,
        1,
        L"Found valid container file. Actual size: [%llu], Minimum expected size: [%llu]",
        v150.QuadPart,
        v155);
      v150 = FileSize;
    }
    v159 = 0;
    if ( (unsigned __int64)(v142 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      v159 = (void *)v142;
    if ( !SetFilePointerEx(v159, v150, 0, 0) )
    {
      v160 = GetLastError();
      PackageFileListPath = v160;
      if ( v160 )
      {
        if ( v160 > 0 )
          PackageFileListPath = (unsigned __int16)v160 | 0x80070000;
      }
      else
      {
        PackageFileListPath = -2147467259;
      }
      v148 = 4512;
      goto LABEL_346;
    }
    v163 = (wchar_t *)v129[6];
    v164 = (wchar_t *)v129[7];
    for ( n = v164; ; v164 = n )
    {
      v247 = v163;
      if ( v163 == v164 )
      {
        if ( !v144 )
          goto LABEL_430;
        SH_SSTRING::operator=(&lpFileName);
        SH_FILENT::operator=(&v241);
        v208 = CMiscHelpersT<CEmptyType>::CombinePath(*((_QWORD *)this + 61), *v144, 0, &lpFileName);
        PackageFileListPath = v208;
        v209 = *((_QWORD *)this + 75);
        if ( v208 >= 0 )
        {
          v212 = lpFileName;
          if ( v209 )
            CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
              v209,
              1,
              L"Final payload chunk; renaming [%ws] to [%ws]",
              lpExistingFileName,
              lpFileName);
          if ( MoveFileExW(lpExistingFileName, v212, 9u) )
            goto LABEL_430;
          v213 = GetLastError();
          PackageFileListPath = v213;
          if ( v213 )
          {
            if ( v213 > 0 )
              PackageFileListPath = (unsigned __int16)v213 | 0x80070000;
          }
          else
          {
            PackageFileListPath = -2147467259;
          }
          v210 = 4644;
          v211 = (unsigned int)PackageFileListPath;
          v209 = *((_QWORD *)this + 75);
        }
        else
        {
          v210 = 4639;
          v211 = (unsigned int)v208;
        }
        CMoUpdateLogT<CEmptyType>::MoUpdateLogError(
          v209,
          v211,
          L"CDeploymentSession::ProcessSandboxContainerPayload",
          v210);
        goto LABEL_499;
      }
      v165 = 0;
      v242 = 0;
      hFile = (HANDLE)-1LL;
      NewFilePointer.QuadPart = 0;
      if ( *((_BYTE *)v163 + 32) )
      {
        DH_SSTRING::~DH_SSTRING((DH_SSTRING *)&v242);
      }
      else
      {
        if ( (unsigned __int64)(v142 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
          v165 = (void *)v142;
        if ( !SetFilePointerEx(v165, 0, &NewFilePointer, 1u) )
        {
          v166 = GetLastError();
          PackageFileListPath = v166;
          if ( v166 )
          {
            if ( v166 > 0 )
              PackageFileListPath = (unsigned __int16)v166 | 0x80070000;
          }
          else
          {
            PackageFileListPath = -2147467259;
          }
          v167 = 4530;
          goto LABEL_399;
        }
        v170 = *((_QWORD *)this + 75);
        if ( v170 )
          CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
            v170,
            1,
            L"Starting container position [%llu]",
            NewFilePointer.QuadPart);
        SH_SSTRING::operator=(&lpFileName);
        v171 = CMiscHelpersT<CEmptyType>::CombinePath(*((_QWORD *)this + 61), *(_QWORD *)v163, 0, &lpFileName);
        PackageFileListPath = v171;
        if ( v171 < 0 )
        {
          v167 = 4537;
          v168 = (unsigned int)v171;
          goto LABEL_400;
        }
        v172 = 0;
        if ( (unsigned __int64)(v142 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
          v172 = (void *)v142;
        if ( !SetFilePointerEx(v172, (LARGE_INTEGER)-*((_QWORD *)v163 + 3), &NewFilePointer, 2u) )
        {
          v173 = GetLastError();
          PackageFileListPath = v173;
          if ( v173 )
          {
            if ( v173 > 0 )
              PackageFileListPath = (unsigned __int16)v173 | 0x80070000;
          }
          else
          {
            PackageFileListPath = -2147467259;
          }
          v167 = 4545;
LABEL_399:
          v168 = (unsigned int)PackageFileListPath;
LABEL_400:
          v169 = *((_QWORD *)this + 75);
          goto LABEL_401;
        }
        v174 = *((_QWORD *)this + 75);
        if ( v174 )
          CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
            v174,
            1,
            L"Next container position [%llu]",
            NewFilePointer.QuadPart);
        if ( !NewFilePointer.QuadPart && !v144 )
        {
          if ( (unsigned __int64)(v142 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
          {
            CloseHandle((HANDLE)v142);
            v142 = -1;
            v241 = (LPCWSTR)-1LL;
          }
          v175 = *((_QWORD *)this + 75);
          v176 = lpFileName;
          if ( v175 )
            CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
              v175,
              1,
              L"Final payload chunk; renaming [%ws] to [%ws]",
              lpExistingFileName,
              lpFileName);
          if ( !MoveFileExW(lpExistingFileName, v176, 9u) )
          {
            v177 = GetLastError();
            PackageFileListPath = v177;
            if ( v177 )
            {
              if ( v177 > 0 )
                PackageFileListPath = (unsigned __int16)v177 | 0x80070000;
            }
            else
            {
              PackageFileListPath = -2147467259;
            }
            v167 = 4559;
            goto LABEL_399;
          }
          DH_SSTRING::~DH_SSTRING((DH_SSTRING *)&v242);
LABEL_430:
          SH_FILENT::~SH_FILENT((SH_FILENT *)&v241);
LABEL_431:
          v178 = (__int64 **)v129[2];
          if ( *((_BYTE *)v178 + 25) )
          {
            for ( ii = (__int64 *)v129[1]; !*((_BYTE *)ii + 25) && v129 == (__int64 *)ii[2]; ii = (__int64 *)ii[1] )
              v129 = ii;
            v129 = ii;
          }
          else
          {
            v129 = (__int64 *)v129[2];
            for ( jj = *v178; !*((_BYTE *)jj + 25); jj = (__int64 *)*jj )
              v129 = jj;
          }
          goto LABEL_308;
        }
        if ( !GetTempFileNameW(*((LPCWSTR *)this + 61), L"tmp", 0, TempFileName) )
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
          v167 = 4566;
          goto LABEL_399;
        }
        TempFileName[259] = 0;
        if ( !TempFileName[0] )
        {
          PackageFileListPath = -2147418113;
          v167 = 4568;
          goto LABEL_399;
        }
        v181 = STRAPI_Create(TempFileName, (wchar_t **)&v242);
        PackageFileListPath = v181;
        v244 = v181;
        v169 = *((_QWORD *)this + 75);
        if ( v181 < 0 )
        {
          v167 = 4570;
          v168 = (unsigned int)v181;
LABEL_401:
          CMoUpdateLogT<CEmptyType>::MoUpdateLogError(
            v169,
            v168,
            L"CDeploymentSession::ProcessSandboxContainerPayload",
            v167);
LABEL_402:
          DH_SSTRING::~DH_SSTRING((DH_SSTRING *)&v242);
LABEL_556:
          if ( (unsigned __int64)(v142 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
            CloseHandle((HANDLE)v142);
          goto LABEL_558;
        }
        if ( v169 )
        {
          v182 = 0;
          if ( v242 )
            v182 = v242;
          CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
            v169,
            1,
            L"Creating temporary payload file [%ws] for [%ws]",
            v182,
            lpFileName);
        }
        v183 = CreateFileW(v242, 0xC0000000, 0, 0, 5u, 0x8000000u, 0);
        SH_FILENT::operator=(&hFile, v183);
        v184 = (char *)hFile;
        if ( (char *)hFile - 1 > (char *)0xFFFFFFFFFFFFFFFDLL )
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
          v187 = 4582;
          goto LABEL_530;
        }
        v185 = *(LARGE_INTEGER *)(v247 + 12);
        if ( !SetFilePointerEx(hFile, v185, 0, 0) )
        {
          v186 = GetLastError();
          PackageFileListPath = v186;
          if ( v186 )
          {
            if ( v186 > 0 )
              PackageFileListPath = (unsigned __int16)v186 | 0x80070000;
          }
          else
          {
            PackageFileListPath = -2147467259;
          }
          v187 = 4588;
LABEL_530:
          CMoUpdateLogT<CEmptyType>::MoUpdateLogError(
            *((_QWORD *)this + 75),
            (unsigned int)PackageFileListPath,
            L"CDeploymentSession::ProcessSandboxContainerPayload",
            v187);
          if ( (unsigned __int64)(v184 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
            CloseHandle(v184);
          goto LABEL_402;
        }
        if ( !SetEndOfFile(v184) )
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
          v187 = 4589;
          goto LABEL_530;
        }
        if ( !SetFilePointerEx(v184, 0, 0, 0) )
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
          v191 = 4590;
          goto LABEL_498;
        }
        v192 = v185.QuadPart;
        if ( v185.QuadPart > 0x400000uLL )
          v192 = 0x400000;
        v193 = RtlReallocateLBlob(v189, v192, nNumberOfBytesToRead);
        if ( !(unsigned int)SErrorConverter::C_NtStatus2HR(v193, &v244) )
        {
          PackageFileListPath = v244;
          v191 = 4597;
          goto LABEL_498;
        }
        while ( v185.QuadPart )
        {
          LowPart = v185.LowPart;
          if ( v185.QuadPart >= *(_QWORD *)&nNumberOfBytesToRead[2] )
            LowPart = nNumberOfBytesToRead[2];
          NumberOfBytesRead = 0;
          NumberOfBytesWritten[0] = 0;
          v195 = (void *)v142;
          if ( (unsigned __int64)(v142 - 1) > 0xFFFFFFFFFFFFFFFDuLL )
            v195 = 0;
          if ( !ReadFile(v195, lpBuffer, LowPart, &NumberOfBytesRead, 0) )
          {
            v196 = GetLastError();
            PackageFileListPath = v196;
            if ( v196 )
            {
              if ( v196 > 0 )
                PackageFileListPath = (unsigned __int16)v196 | 0x80070000;
            }
            else
            {
              PackageFileListPath = -2147467259;
            }
            v191 = 4605;
            goto LABEL_498;
          }
          v197 = 0;
          if ( (unsigned __int64)(v184 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
            v197 = v184;
          if ( !WriteFile(v197, lpBuffer, NumberOfBytesRead, NumberOfBytesWritten, 0) )
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
            v191 = 4606;
            goto LABEL_498;
          }
          m = NumberOfBytesWritten[0];
          if ( NumberOfBytesWritten[0] < NumberOfBytesRead )
          {
            NewFilePointer.QuadPart = -(__int64)(NumberOfBytesRead - NumberOfBytesWritten[0]);
            v199 = 0;
            if ( (unsigned __int64)(v142 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
              v199 = (void *)v142;
            if ( !SetFilePointerEx(v199, (LARGE_INTEGER)-(__int64)(NumberOfBytesRead - NumberOfBytesWritten[0]), 0, 1u) )
            {
              v200 = GetLastError();
              PackageFileListPath = v200;
              if ( v200 )
              {
                if ( v200 > 0 )
                  PackageFileListPath = (unsigned __int16)v200 | 0x80070000;
              }
              else
              {
                PackageFileListPath = -2147467259;
              }
              v191 = 4614;
              goto LABEL_498;
            }
          }
          v185.QuadPart -= m;
        }
        SH_FILENT::operator=(&hFile);
        if ( !MoveFileExW(v242, lpFileName, 9u) )
        {
          v201 = GetLastError();
          PackageFileListPath = v201;
          if ( v201 )
          {
            if ( v201 > 0 )
              PackageFileListPath = (unsigned __int16)v201 | 0x80070000;
          }
          else
          {
            PackageFileListPath = -2147467259;
          }
          v191 = 4622;
          goto LABEL_498;
        }
        v202 = (void *)v142;
        if ( (unsigned __int64)(v142 - 1) > 0xFFFFFFFFFFFFFFFDuLL )
          v202 = 0;
        v203 = SetFilePointerEx(v202, (LARGE_INTEGER)-*((_QWORD *)v247 + 3), 0, 2u);
        v204 = 0;
        if ( !v203 )
        {
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
          v191 = 4628;
          goto LABEL_498;
        }
        if ( (unsigned __int64)(v142 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
          v204 = (void *)v142;
        if ( !SetEndOfFile(v204) )
        {
          v206 = GetLastError();
          PackageFileListPath = v206;
          if ( v206 )
          {
            if ( v206 > 0 )
              PackageFileListPath = (unsigned __int16)v206 | 0x80070000;
          }
          else
          {
            PackageFileListPath = -2147467259;
          }
          v191 = 4629;
LABEL_498:
          CMoUpdateLogT<CEmptyType>::MoUpdateLogError(
            *((_QWORD *)this + 75),
            (unsigned int)PackageFileListPath,
            L"CDeploymentSession::ProcessSandboxContainerPayload",
            v191);
          SH_FILENT::~SH_FILENT((SH_FILENT *)&hFile);
          DH_SSTRING::~DH_SSTRING((DH_SSTRING *)&v242);
LABEL_499:
          SH_FILENT::~SH_FILENT((SH_FILENT *)&v241);
          goto LABEL_558;
        }
        SH_FILENT::~SH_FILENT((SH_FILENT *)&hFile);
        DH_SSTRING::~DH_SSTRING((DH_SSTRING *)&v242);
        PackageFileListPath = v244;
        v163 = v247;
      }
      v163 += 20;
    }
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x1235,
                           (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\DeploymentSessionImpl.h",
                           v216);
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
