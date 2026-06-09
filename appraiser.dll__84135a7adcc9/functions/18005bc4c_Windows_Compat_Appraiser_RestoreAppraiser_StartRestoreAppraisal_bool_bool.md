# Windows::Compat::Appraiser::RestoreAppraiser::StartRestoreAppraisal(bool,bool)

- ea: `0x18005bc4c`
- end: `0x18005e0d7`
- name: `?StartRestoreAppraisal@RestoreAppraiser@Appraiser@Compat@Windows@@SAJ_N0@Z`
- size: `9355`
- prototype: `__int64 __fastcall(bool, bool)`
- caller_count: `2`
- callee_count: `54`
- tags: `reparse_path, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180014030`
- `0x180014d70`

## callees

- `0x18000147c`
- `0x180001990`
- `0x1800026e0`
- `0x180008570`
- `0x1800092dc`
- `0x180013318`
- `0x180013c7c`
- `0x1800151f4`
- `0x180029258`
- `0x18002a8b4`
- `0x18002b894`
- `0x18002ebb8`
- `0x1800301d0`
- `0x180059ca8`
- `0x18005a408`
- `0x18005a4c0`
- `0x18005a7e8`
- `0x18005aa34`
- `0x18005ab64`
- `0x18005acb8`
- `0x18005afdc`
- `0x18005b4fc`
- `0x18005bc4c`
- `0x18005e0e0`
- `0x18005e198`
- `0x18005e4f8`
- `0x18005e638`
- `0x18005e6cc`
- `0x18005ef44`
- `0x18005feb8`
- `0x180060a7c`
- `0x180060c4c`
- `0x180081774`
- `0x180084ca8`
- `0x1800858c8`
- `0x180087108`
- `0x180088980`
- `0x180088c0c`
- `0x18008eac8`
- `0x1800952d8`
- `0x180095850`
- `0x180097f20`
- `0x18009b30c`
- `0x18009b550`
- `0x1800a5d88`
- `0x1800b08a4`
- `0x1800b0b3c`
- `0x1801abfd8`
- `0x1801ac054`
- `0x1801b0af0`

## import_xrefs

- `KERNEL32!Sleep` at `0x18005c2f6`
- `KERNEL32!Sleep` at `0x18005c2f6`
- `KERNEL32!GetSystemTime` at `0x18005c182`
- `KERNEL32!GetSystemTime` at `0x18005c410`
- `KERNEL32!GetSystemTime` at `0x18005c74d`
- `KERNEL32!GetSystemTime` at `0x18005cf5f`
- `KERNEL32!GetSystemTime` at `0x18005d232`
- `KERNEL32!GetSystemTime` at `0x18005d43f`
- `KERNEL32!GetSystemTime` at `0x18005d604`
- `KERNEL32!GetSystemTime` at `0x18005d82e`
- `KERNEL32!GetSystemTime` at `0x18005da23`
- `KERNEL32!GetSystemTime` at `0x18005dc18`
- `KERNEL32!GetSystemTime` at `0x18005de05`
- `KERNEL32!GetSystemTime` at `0x18005dfb9`
- `KERNEL32!GetSystemTime` at `0x18005c182`
- `KERNEL32!GetSystemTime` at `0x18005c410`
- `KERNEL32!GetSystemTime` at `0x18005c74d`
- `KERNEL32!GetSystemTime` at `0x18005cf5f`
- `KERNEL32!GetSystemTime` at `0x18005d232`
- `KERNEL32!GetSystemTime` at `0x18005d43f`
- `KERNEL32!GetSystemTime` at `0x18005d604`
- `KERNEL32!GetSystemTime` at `0x18005d82e`
- `KERNEL32!GetSystemTime` at `0x18005da23`
- `KERNEL32!GetSystemTime` at `0x18005dc18`
- `KERNEL32!GetSystemTime` at `0x18005de05`
- `KERNEL32!GetSystemTime` at `0x18005dfb9`
- `KERNEL32!GetProcessHeap` at `0x18005dceb`
- `KERNEL32!GetProcessHeap` at `0x18005dceb`
- `KERNEL32!LeaveCriticalSection` at `0x18005bf2e`
- `KERNEL32!LeaveCriticalSection` at `0x18005ce59`
- `KERNEL32!LeaveCriticalSection` at `0x18005d12a`
- `KERNEL32!LeaveCriticalSection` at `0x18005bf2e`
- `KERNEL32!LeaveCriticalSection` at `0x18005ce59`
- `KERNEL32!LeaveCriticalSection` at `0x18005d12a`
- `KERNEL32!EnterCriticalSection` at `0x18005be56`
- `KERNEL32!EnterCriticalSection` at `0x18005c026`
- `KERNEL32!EnterCriticalSection` at `0x18005c22a`
- `KERNEL32!EnterCriticalSection` at `0x18005ce2e`
- `KERNEL32!EnterCriticalSection` at `0x18005d012`
- `KERNEL32!EnterCriticalSection` at `0x18005d063`
- `KERNEL32!EnterCriticalSection` at `0x18005d0ff`
- `KERNEL32!EnterCriticalSection` at `0x18005be56`
- `KERNEL32!EnterCriticalSection` at `0x18005c026`
- `KERNEL32!EnterCriticalSection` at `0x18005c22a`
- `KERNEL32!EnterCriticalSection` at `0x18005ce2e`
- `KERNEL32!EnterCriticalSection` at `0x18005d012`
- `KERNEL32!EnterCriticalSection` at `0x18005d063`
- `KERNEL32!EnterCriticalSection` at `0x18005d0ff`
- `KERNEL32!HeapFree` at `0x18005dcf9`
- `KERNEL32!HeapFree` at `0x18005dcf9`
- `OLE32!CoTaskMemFree` at `0x18005be36`
- `OLE32!CoTaskMemFree` at `0x18005bf20`
- `OLE32!CoTaskMemFree` at `0x18005e081`
- `OLE32!CoTaskMemFree` at `0x18005e0ac`
- `OLE32!CoTaskMemFree` at `0x18005be36`
- `OLE32!CoTaskMemFree` at `0x18005bf20`
- `OLE32!CoTaskMemFree` at `0x18005e081`
- `OLE32!CoTaskMemFree` at `0x18005e0ac`
- `OLE32!PropVariantClear` at `0x18005c05b`
- `OLE32!PropVariantClear` at `0x18005c05b`
- `acmigration!AcmEngineDelete` at `0x18005d2d5`
- `acmigration!AcmEngineDelete` at `0x18005d2d5`
- `acmigration!AcmEngineCreate` at `0x18005ca0e`
- `acmigration!AcmEngineCreate` at `0x18005ca0e`

## string_xrefs

- `0x18005cd24`: `Error listing non fatal components: [0x%x].`
- `0x18005cd48`: `Error listing non fatal components: [0x%x].`
- `0x18005c4d5`: `Error expanding inbox input directory: [0x%x].`
- `0x18005c4f6`: `Error expanding inbox input directory: [0x%x].`
- `0x18005c4b8`: `%WINDIR%\system32\appraiser\`
- `0x18005c809`: `%WINDIR%\system32\appraiser\`
- `0x18005c587`: `Error setting inbox data file path: [0x%x].`
- `0x18005c5a8`: `Error setting inbox data file path: [0x%x].`
- `0x18005c5e0`: `Error expanding cab file path: [0x%x].`
- `0x18005c601`: `Error expanding cab file path: [0x%x].`
- `0x18005bf39`: `Windows::Compat::Appraiser::RestoreAppraiser::StartRestoreAppraisal`
- `0x18005bfe5`: `Windows::Compat::Appraiser::RestoreAppraiser::StartRestoreAppraisal`
- `0x18005c2bc`: `Windows::Compat::Appraiser::RestoreAppraiser::StartRestoreAppraisal`
- `0x18005c49f`: `Windows::Compat::Appraiser::RestoreAppraiser::StartRestoreAppraisal`
- `0x18005c71a`: `Windows::Compat::Appraiser::RestoreAppraiser::StartRestoreAppraisal`
- `0x18005c7be`: `Windows::Compat::Appraiser::RestoreAppraiser::StartRestoreAppraisal`
- `0x18005ca33`: `Windows::Compat::Appraiser::RestoreAppraiser::StartRestoreAppraisal`
- `0x18005ca6b`: `Windows::Compat::Appraiser::RestoreAppraiser::StartRestoreAppraisal`
- `0x18005cab1`: `Windows::Compat::Appraiser::RestoreAppraiser::StartRestoreAppraisal`
- `0x18005cb0b`: `Windows::Compat::Appraiser::RestoreAppraiser::StartRestoreAppraisal`
- `0x18005cb5d`: `Windows::Compat::Appraiser::RestoreAppraiser::StartRestoreAppraisal`
- `0x18005d0c2`: `Windows::Compat::Appraiser::RestoreAppraiser::StartRestoreAppraisal`
- `0x18005d329`: `Windows::Compat::Appraiser::RestoreAppraiser::StartRestoreAppraisal`
- `0x18005d4ee`: `Windows::Compat::Appraiser::RestoreAppraiser::StartRestoreAppraisal`
- `0x18005d710`: `Windows::Compat::Appraiser::RestoreAppraiser::StartRestoreAppraisal`
- `0x18005d905`: `Windows::Compat::Appraiser::RestoreAppraiser::StartRestoreAppraisal`
- `0x18005dafa`: `Windows::Compat::Appraiser::RestoreAppraiser::StartRestoreAppraisal`
- `0x18005dd0a`: `Windows::Compat::Appraiser::RestoreAppraiser::StartRestoreAppraisal`
- `0x18005bf5e`: `onecore\base\appcompat\appraiser\heads\restore\restoreappraiser.cpp`
- `0x18005bfc7`: `onecore\base\appcompat\appraiser\heads\restore\restoreappraiser.cpp`
- `0x18005c27d`: `onecore\base\appcompat\appraiser\heads\restore\restoreappraiser.cpp`
- `0x18005c293`: `onecore\base\appcompat\appraiser\heads\restore\restoreappraiser.cpp`
- `0x18005c500`: `onecore\base\appcompat\appraiser\heads\restore\restoreappraiser.cpp`
- `0x18005c55e`: `onecore\base\appcompat\appraiser\heads\restore\restoreappraiser.cpp`
- `0x18005c5b2`: `onecore\base\appcompat\appraiser\heads\restore\restoreappraiser.cpp`
- `0x18005c60b`: `onecore\base\appcompat\appraiser\heads\restore\restoreappraiser.cpp`
- `0x18005c66d`: `onecore\base\appcompat\appraiser\heads\restore\restoreappraiser.cpp`
- `0x18005c725`: `onecore\base\appcompat\appraiser\heads\restore\restoreappraiser.cpp`
- `0x18005c7df`: `onecore\base\appcompat\appraiser\heads\restore\restoreappraiser.cpp`
- `0x18005c85d`: `onecore\base\appcompat\appraiser\heads\restore\restoreappraiser.cpp`
- `0x18005c8c2`: `onecore\base\appcompat\appraiser\heads\restore\restoreappraiser.cpp`
- `0x18005c913`: `onecore\base\appcompat\appraiser\heads\restore\restoreappraiser.cpp`
- `0x18005c951`: `onecore\base\appcompat\appraiser\heads\restore\restoreappraiser.cpp`
- `0x18005c9b6`: `onecore\base\appcompat\appraiser\heads\restore\restoreappraiser.cpp`
- `0x18005ca3a`: `onecore\base\appcompat\appraiser\heads\restore\restoreappraiser.cpp`
- `0x18005ca72`: `onecore\base\appcompat\appraiser\heads\restore\restoreappraiser.cpp`
- `0x18005cab8`: `onecore\base\appcompat\appraiser\heads\restore\restoreappraiser.cpp`
- `0x18005cb12`: `onecore\base\appcompat\appraiser\heads\restore\restoreappraiser.cpp`
- `0x18005cb76`: `onecore\base\appcompat\appraiser\heads\restore\restoreappraiser.cpp`
- `0x18005cbd3`: `onecore\base\appcompat\appraiser\heads\restore\restoreappraiser.cpp`
- `0x18005cc29`: `onecore\base\appcompat\appraiser\heads\restore\restoreappraiser.cpp`
- `0x18005cc78`: `onecore\base\appcompat\appraiser\heads\restore\restoreappraiser.cpp`
- `0x18005d0cc`: `onecore\base\appcompat\appraiser\heads\restore\restoreappraiser.cpp`
- `0x18005d15d`: `onecore\base\appcompat\appraiser\heads\restore\restoreappraiser.cpp`
- `0x18005d2bb`: `onecore\base\appcompat\appraiser\heads\restore\restoreappraiser.cpp`
- `0x18005d366`: `onecore\base\appcompat\appraiser\heads\restore\restoreappraiser.cpp`
- `0x18005d416`: `onecore\base\appcompat\appraiser\heads\restore\restoreappraiser.cpp`
- `0x18005d52b`: `onecore\base\appcompat\appraiser\heads\restore\restoreappraiser.cpp`
- `0x18005d5db`: `onecore\base\appcompat\appraiser\heads\restore\restoreappraiser.cpp`
- `0x18005d68e`: `onecore\base\appcompat\appraiser\heads\restore\restoreappraiser.cpp`
- `0x18005d6bc`: `onecore\base\appcompat\appraiser\heads\restore\restoreappraiser.cpp`
- `0x18005d755`: `onecore\base\appcompat\appraiser\heads\restore\restoreappraiser.cpp`
- `0x18005d805`: `onecore\base\appcompat\appraiser\heads\restore\restoreappraiser.cpp`
- `0x18005d8b8`: `onecore\base\appcompat\appraiser\heads\restore\restoreappraiser.cpp`
- `0x18005d94a`: `onecore\base\appcompat\appraiser\heads\restore\restoreappraiser.cpp`
- `0x18005d9fa`: `onecore\base\appcompat\appraiser\heads\restore\restoreappraiser.cpp`
- `0x18005daad`: `onecore\base\appcompat\appraiser\heads\restore\restoreappraiser.cpp`
- `0x18005db3f`: `onecore\base\appcompat\appraiser\heads\restore\restoreappraiser.cpp`
- `0x18005dbef`: `onecore\base\appcompat\appraiser\heads\restore\restoreappraiser.cpp`
- `0x18005dca2`: `onecore\base\appcompat\appraiser\heads\restore\restoreappraiser.cpp`
- `0x18005dd11`: `onecore\base\appcompat\appraiser\heads\restore\restoreappraiser.cpp`
- `0x18005bf4b`: `Unable to determine output path for restore: [0x%x].`
- `0x18005bfbb`: `Error creating event log path: [0x%x].`
- `0x18005c273`: `Error creating event log path: [0x%x].`
- `0x18005c62d`: `%TEMP%\Appraiser_AlternateDataRestore_Temp.cab`
- `0x18005c5c3`: `%TEMP%\Appraiser_AlternateDataRestore.cab`
- `0x18005c621`: `%TEMP%\AltData\`
- `0x18005c900`: `Failed to initialize datafile from filepath %ls: [0x%x].`
- `0x18005c947`: `Failed to initialize datafile from filepath %ls: [0x%x].`
- `0x18005c98b`: `Error combinining: [0x%x].`
- `0x18005c9ac`: `Error combinining: [0x%x].`
- `0x18005c832`: `Error expanding input directory: [0x%x].`
- `0x18005c853`: `Error expanding input directory: [0x%x].`
- `0x18005c897`: `Error combining: [0x%x].`
- `0x18005c8b8`: `Error combining: [0x%x].`
- `0x18005cb44`: `AddDatasourceComponentsForRun failed: [0x%x].`
- `0x18005cb6c`: `AddDatasourceComponentsForRun failed: [0x%x].`
- `0x18005cba8`: `AddDecisionmakerComponentsForRun failed: [0x%x].`
- `0x18005cbc9`: `AddDecisionmakerComponentsForRun failed: [0x%x].`
- `0x18005cae3`: `AddInventoryComponentsForRun failed: [0x%x].`
- `0x18005cb04`: `AddInventoryComponentsForRun failed: [0x%x].`
- `0x18005cbfe`: `AddDecisionAggregatorComponentsForRun failed: [0x%x].`
- `0x18005cc1f`: `AddDecisionAggregatorComponentsForRun failed: [0x%x].`
- `0x18005cc5f`: `AddOutputterComponentsForRun failed: [0x%x].`
- `0x18005cc87`: `AddOutputterComponentsForRun failed: [0x%x].`
- `0x18005d02e`: `TipReasonV2::SecurityMode`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Windows::Compat::Appraiser::RestoreAppraiser::StartRestoreAppraisal(bool a1)
{
  __int64 v2; // rsi
  __int64 v3; // rbx
  struct _RTL_CRITICAL_SECTION *v4; // r14
  int v5; // edx
  int v6; // r8d
  _DWORD *v7; // rdi
  __int64 v8; // rax
  __int64 v9; // rsi
  __int64 v10; // rax
  unsigned __int64 v11; // rdx
  unsigned __int16 *v12; // rcx
  int v13; // eax
  HRESULT v14; // edi
  char v15; // r13
  const char *v16; // r15
  const char *v17; // r9
  char v18; // dl
  const char *v19; // rax
  const char *v20; // rbx
  char v21; // cl
  __int64 v22; // rsi
  __int64 v23; // rax
  __int64 v24; // r14
  __int64 v25; // rbx
  volatile signed __int64 *v26; // rcx
  void **v27; // rdx
  int v28; // ebx
  unsigned __int16 *v29; // rcx
  int v30; // r8d
  int v31; // r9d
  const char *v32; // rsi
  __int64 v33; // rbx
  int v34; // ebx
  __int64 v35; // rcx
  volatile signed __int64 *v36; // rcx
  void **v37; // rdx
  int v38; // ebx
  unsigned __int16 *v39; // rcx
  unsigned __int64 v40; // rdx
  int v41; // r8d
  int v42; // r9d
  unsigned int v43; // edx
  unsigned int v44; // edx
  const unsigned __int16 *v45; // rsi
  int v46; // eax
  int v47; // edi
  volatile signed __int64 *v48; // rcx
  void **v49; // rdx
  int v50; // ebx
  int v51; // r8d
  int v52; // r9d
  unsigned int v53; // edx
  int v54; // eax
  void *inited; // rbx
  const char *v56; // rax
  const char *v57; // rbx
  char v58; // cl
  _QWORD *v59; // rax
  char *v60; // rbx
  struct _RTL_CRITICAL_SECTION *v61; // rsi
  volatile signed __int64 *v62; // rcx
  void **v63; // rdx
  int v64; // ebx
  unsigned __int16 *v65; // rcx
  int v66; // r8d
  int v67; // r9d
  const char *v68; // rax
  const char *v69; // rsi
  char v70; // cl
  struct _RTL_CRITICAL_SECTION **v71; // rax
  __int64 p_LockCount; // rbx
  __int64 v73; // rdx
  const char *v74; // rax
  char v75; // cl
  struct _RTL_CRITICAL_SECTION **v76; // rax
  char *v77; // rbx
  struct _RTL_CRITICAL_SECTION *v78; // rsi
  int v79; // eax
  int v80; // ebx
  volatile signed __int64 *v81; // rcx
  void **v82; // rdx
  int v83; // esi
  int v84; // r8d
  int v85; // r9d
  unsigned int i; // ebx
  __int64 v87; // r14
  void (__fastcall ***v88)(_QWORD); // rcx
  unsigned int v89; // ebx
  __int64 v90; // r12
  __int64 v91; // rcx
  int v92; // eax
  int v93; // r14d
  volatile signed __int64 *v94; // rcx
  void **v95; // rdx
  int v96; // esi
  int v97; // r8d
  int v98; // r9d
  __int64 v99; // rcx
  unsigned int v100; // ebx
  __int64 v101; // r12
  __int64 v102; // rcx
  int v103; // eax
  int v104; // r14d
  volatile signed __int64 *v105; // rcx
  void **v106; // rdx
  int v107; // esi
  int v108; // r8d
  int v109; // r9d
  __int64 v110; // rcx
  unsigned int v111; // ebx
  __int64 v112; // r12
  __int64 v113; // rcx
  int v114; // eax
  int v115; // r14d
  volatile signed __int64 *v116; // rcx
  void **v117; // rdx
  int v118; // esi
  int v119; // r8d
  int v120; // r9d
  __int64 v121; // rcx
  unsigned int v122; // ebx
  __int64 v123; // r12
  __int64 v124; // rcx
  int v125; // eax
  int v126; // r14d
  volatile signed __int64 *v127; // rcx
  void **v128; // rdx
  int v129; // esi
  int v130; // r8d
  int v131; // r9d
  __int64 v132; // rcx
  unsigned int v133; // ebx
  __int64 v134; // r12
  __int64 v135; // rcx
  int v136; // eax
  int v137; // r14d
  volatile signed __int64 *v138; // rcx
  void **v139; // rdx
  int v140; // esi
  int v141; // r8d
  int v142; // r9d
  __int64 v143; // rcx
  void *v144; // rbx
  HANDLE ProcessHeap; // rax
  int v146; // eax
  int v147; // ebx
  volatile signed __int64 *v148; // rcx
  void **v149; // rdx
  int v150; // esi
  int v151; // r8d
  int v152; // r9d
  int v153; // eax
  int v154; // esi
  volatile signed __int64 *v155; // rcx
  void **v156; // rdx
  int v157; // ebx
  int v158; // r8d
  int v159; // r9d
  void *v160; // rbx
  void *v161; // rbx
  const char *dwFlags; // [rsp+20h] [rbp-E0h]
  const char *dwFlagsa; // [rsp+20h] [rbp-E0h]
  const char *dwFlagsb; // [rsp+20h] [rbp-E0h]
  char *v166; // [rsp+30h] [rbp-D0h]
  char *v167; // [rsp+30h] [rbp-D0h]
  __int64 v168; // [rsp+38h] [rbp-C8h]
  char v169[4]; // [rsp+70h] [rbp-90h] BYREF
  bool v170; // [rsp+74h] [rbp-8Ch] BYREF
  __int64 v171; // [rsp+78h] [rbp-88h] BYREF
  char *v172; // [rsp+80h] [rbp-80h] BYREF
  char v173; // [rsp+88h] [rbp-78h]
  char *v174; // [rsp+90h] [rbp-70h] BYREF
  struct _SYSTEMTIME *v175; // [rsp+98h] [rbp-68h] BYREF
  unsigned __int16 *v176; // [rsp+A0h] [rbp-60h] BYREF
  char v177[8]; // [rsp+A8h] [rbp-58h] BYREF
  _QWORD v178[2]; // [rsp+B0h] [rbp-50h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+C0h] [rbp-40h] BYREF
  LPVOID pv; // [rsp+D0h] [rbp-30h] BYREF
  __int128 v181; // [rsp+D8h] [rbp-28h] BYREF
  unsigned int v182; // [rsp+E8h] [rbp-18h] BYREF
  struct _SYSTEMTIME *v183; // [rsp+F0h] [rbp-10h] BYREF
  const wchar_t *v184; // [rsp+F8h] [rbp-8h] BYREF
  void *v185; // [rsp+100h] [rbp+0h] BYREF
  LPVOID v186; // [rsp+108h] [rbp+8h] BYREF
  __int128 v187; // [rsp+110h] [rbp+10h] BYREF
  __int128 v188; // [rsp+120h] [rbp+20h]
  __int128 v189; // [rsp+130h] [rbp+30h]
  LPVOID lpMem[2]; // [rsp+140h] [rbp+40h] BYREF
  __int128 v191; // [rsp+150h] [rbp+50h]
  __int128 v192; // [rsp+160h] [rbp+60h]
  void *v193[2]; // [rsp+170h] [rbp+70h] BYREF
  _BYTE v194[480]; // [rsp+180h] [rbp+80h] BYREF
  struct RtlStringArray *v195; // [rsp+360h] [rbp+260h]
  unsigned int v196; // [rsp+400h] [rbp+300h]
  struct _SYSTEMTIME v197; // [rsp+410h] [rbp+310h] BYREF
  LPVOID v198; // [rsp+420h] [rbp+320h] BYREF
  char v199; // [rsp+428h] [rbp+328h]
  int v200; // [rsp+429h] [rbp+329h] BYREF
  char v201; // [rsp+42Dh] [rbp+32Dh]
  char v202; // [rsp+42Eh] [rbp+32Eh] BYREF
  char v203; // [rsp+C29h] [rbp+B29h] BYREF
  int *v204; // [rsp+C30h] [rbp+B30h]
  char *v205; // [rsp+C38h] [rbp+B38h]
  char *v206; // [rsp+C40h] [rbp+B40h]
  __int64 v207; // [rsp+C50h] [rbp+B50h] BYREF
  char v208; // [rsp+C58h] [rbp+B58h]
  __int64 v209; // [rsp+C60h] [rbp+B60h]
  __int64 v210; // [rsp+C68h] [rbp+B68h]
  __int16 v211; // [rsp+C70h] [rbp+B70h]
  char v212; // [rsp+E78h] [rbp+D78h]
  struct Windows::Compat::Appraiser::IInventory *v213[32]; // [rsp+E80h] [rbp+D80h] BYREF
  struct IDataSource *v214[32]; // [rsp+F80h] [rbp+E80h] BYREF
  struct Windows::Compat::Appraiser::IDecisionMaker *v215[32]; // [rsp+1080h] [rbp+F80h] BYREF
  struct Windows::Compat::Appraiser::IDecisionAggregator *v216[32]; // [rsp+1180h] [rbp+1080h] BYREF
  struct Windows::Compat::Appraiser::IOutputter *v217[32]; // [rsp+1280h] [rbp+1180h] BYREF
  struct Windows::Compat::Appraiser::IProperty *v218[128]; // [rsp+1380h] [rbp+1280h] BYREF
  char v219[16]; // [rsp+1780h] [rbp+1680h] BYREF
  __int128 v220; // [rsp+1790h] [rbp+1690h]
  __int128 v221; // [rsp+17A0h] [rbp+16A0h]
  __int128 v222; // [rsp+17B0h] [rbp+16B0h]
  __int128 v223; // [rsp+17C0h] [rbp+16C0h]
  __int128 v224; // [rsp+17D0h] [rbp+16D0h]
  WCHAR pszPath[264]; // [rsp+1810h] [rbp+1710h] BYREF
  WCHAR pszPathIn[264]; // [rsp+1A20h] [rbp+1920h] BYREF
  WCHAR v227[264]; // [rsp+1C30h] [rbp+1B30h] BYREF
  WCHAR pszPathOut[264]; // [rsp+1E40h] [rbp+1D40h] BYREF
  WCHAR Dst[264]; // [rsp+2050h] [rbp+1F50h] BYREF

  v193[1] = (void *)-2LL;
  v170 = 0;
  v186 = 0;
  pv = 0;
  v209 = 0;
  v210 = 0;
  v211 = 0;
  v207 = 0;
  v208 = 0;
  v212 = 0;
  Windows::Compat::Appraiser::DataFile::DataFile((Windows::Compat::Appraiser::DataFile *)v194);
  memset_0(v218, 0, sizeof(v218));
  memset_0(v213, 0, sizeof(v213));
  memset_0(v214, 0, sizeof(v214));
  memset_0(v217, 0, sizeof(v217));
  memset_0(v215, 0, sizeof(v215));
  memset_0(v216, 0, sizeof(v216));
  Windows::Compat::Appraiser::RestoreAppraiser::Placeholder_Decision_BackupDevice = 0;
  memset_0(&Windows::Compat::Appraiser::RestoreAppraiser::OutputDirPath, 0, 0x208u);
  memset_0(&v187, 0, 0x60u);
  memset_0(pszPathIn, 0, 0x208u);
  memset_0(pszPathOut, 0, 0x208u);
  memset_0(Dst, 0, 0x208u);
  memset_0(pszPath, 0, 0x208u);
  memset_0(v227, 0, 0x208u);
  v181 = 0u;
  *(_DWORD *)v169 = 0;
  v182 = 0;
  v193[0] = 0;
  v185 = 0;
  Windows::Compat::Appraiser::AppraiserSettings::FeatureType = 3;
  Windows::Compat::Appraiser::AppraiserSettings::OnesettingsQueryTries = 1;
  v173 = 0;
  v2 = *(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_MercuryExtendedAppsRestoreV2Success_attributes,tip2::test_data_basic>>::ensure_data(&pv);
  v3 = v2 + 8;
  v4 = (struct _RTL_CRITICAL_SECTION *)(v2 + 200);
  EnterCriticalSection((LPCRITICAL_SECTION)(v2 + 200));
  v198 = 0;
  v199 = 0;
  v204 = &v200;
  v206 = &v203;
  v200 = -2143256512;
  v201 = 0;
  v205 = &v202;
  if ( (*(_DWORD *)(v2 + 72) & 0x800) != 0 )
  {
    v7 = (_DWORD *)(v2 + 28);
    if ( (*(_DWORD *)(v2 + 28) & 0x8000) == 0 )
    {
      v8 = tip2::details::shared_data<0,0,1>::serialize_data(v3, &v198, 1);
      v9 = v2 + 152;
      goto LABEL_6;
    }
  }
  else
  {
    v7 = (_DWORD *)(v2 + 28);
  }
  v8 = 0;
  v9 = v2 + 152;
LABEL_6:
  LOBYTE(v6) = *(_BYTE *)(v3 + 32);
  v10 = TestCreate(*(_DWORD *)(v3 + 16), v5, v6, *v7, v8, v9);
  wil::details::unique_storage<wil::details::resource_policy<HTIPTEST__ *,void (*)(HTIPTEST__ *),&void TestClose(HTIPTEST__ *),wistd::integral_constant<unsigned __int64,0>,HTIPTEST__ *,HTIPTEST__ *,0,std::nullptr_t>>::reset(
    v3 + 240,
    v10);
  *(_DWORD *)(v3 + 184) = 1;
  v12 = (unsigned __int16 *)v198;
  if ( v198 )
    CoTaskMemFree(v198);
  if ( v4 )
    LeaveCriticalSection(v4);
  v13 = Windows::Compat::Appraiser::Utilities::DetermineRestoreOutputPath(v12, v11);
  if ( v13 < 0 )
  {
    LODWORD(v166) = v13;
    LODWORD(dwFlags) = v13;
    Windows::Compat::Appraiser::WriteLog(
      (Windows::Compat::Appraiser *)1,
      74,
      (unsigned int)"onecore\\base\\appcompat\\appraiser\\heads\\restore\\restoreappraiser.cpp",
      "Windows::Compat::Appraiser::RestoreAppraiser::StartRestoreAppraisal",
      dwFlags,
      (int)"Unable to determine output path for restore: [0x%x].",
      v166);
    memset_0(&Windows::Compat::Appraiser::RestoreAppraiser::OutputDirPath, 0, 0x208u);
  }
  v14 = PathCchCombineEx(
          pszPathOut,
          0x104u,
          &Windows::Compat::Appraiser::RestoreAppraiser::OutputDirPath,
          L"APPRAISER_Restore_EventLog.etl",
          (ULONG)dwFlags);
  LODWORD(v171) = v14;
  v15 = 84;
  v16 = "TipReasonV2::RestoreEventSent";
  if ( v14 < 0 )
  {
    v17 = "Error creating event log path: [0x%x].";
    v18 = 83;
LABEL_14:
    LODWORD(v166) = v14;
    LODWORD(dwFlagsa) = v14;
    Windows::Compat::Appraiser::WriteLog(
      (Windows::Compat::Appraiser *)1,
      v18,
      (unsigned int)"onecore\\base\\appcompat\\appraiser\\heads\\restore\\restoreappraiser.cpp",
      "Windows::Compat::Appraiser::RestoreAppraiser::StartRestoreAppraisal",
      dwFlagsa,
      (int)v17,
      v166);
    goto LABEL_15;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x53u,
      "onecore\\base\\appcompat\\appraiser\\heads\\restore\\restoreappraiser.cpp",
      "Windows::Compat::Appraiser::RestoreAppraiser::StartRestoreAppraisal",
      "Error creating event log path: [0x%x].",
      v14);
  v34 = Windows::Compat::Appraiser::LogToFile::Start((Windows::Compat::Appraiser::LogToFile *)&v207, pszPathOut);
  if ( v34 >= 0 )
  {
    Sleep(0x3E8u);
  }
  else
  {
    LODWORD(v166) = v34;
    if ( Windows::Compat::Appraiser::AppraiserTestHooks::TreatWarningsAsErrors() )
    {
      LODWORD(dwFlagsa) = v34;
      v35 = 1;
    }
    else
    {
      dwFlagsa = 0;
      v35 = 0;
    }
    Windows::Compat::Appraiser::WriteLog(
      (Windows::Compat::Appraiser *)v35,
      88,
      (unsigned int)"onecore\\base\\appcompat\\appraiser\\heads\\restore\\restoreappraiser.cpp",
      "Windows::Compat::Appraiser::RestoreAppraiser::StartRestoreAppraisal",
      dwFlagsa,
      (int)"Error starting logger: [0x%x].",
      v166);
  }
  if ( !Windows::Compat::Appraiser::Utilities::IsMachineInSecurityMode() )
  {
    TraceLoggingCorrelationVector::TraceLoggingCorrelationVector((TraceLoggingCorrelationVector *)&v198);
    v36 = (volatile signed __int64 *)&v198;
    if ( Windows::Compat::Appraiser::WicaFactory::CorrelationVector )
      v36 = (volatile signed __int64 *)Windows::Compat::Appraiser::WicaFactory::CorrelationVector;
    TraceLoggingCorrelationVector::ToStringImpl(
      (TraceLoggingCorrelationVector *)v36,
      _InterlockedExchangeAdd64(v36 + 17, 0),
      v219);
    if ( Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive )
      UtcThrottle::Throttle((UtcThrottle *)&Windows::Compat::Appraiser::WicaFactory::UtcEventThrottler, v37);
    v38 = qword_1802C9560;
    if ( *(_DWORD *)qword_1802C9560 > 5u )
    {
      v39 = *(unsigned __int16 **)(qword_1802C9560 + 24);
      v40 = 0x800000000000LL;
      if ( (*(_QWORD *)(qword_1802C9560 + 16) & 0x800000000000LL) != 0
        && (unsigned __int16 *)((unsigned __int64)v39 & 0x800000000000LL) == v39 )
      {
        v172 = v219;
        v171 = 0x1000000;
        v183 = (struct _SYSTEMTIME *)&szValueBuf;
        v184 = L"RestoreAppraiser";
        if ( !Windows::Compat::Appraiser::WicaFactory::AppraiserProcessExeBuffer )
          Windows::Compat::Appraiser::Utilities::GetAppraiserProcessExe(v39, 0x800000000000uLL);
        v175 = (struct _SYSTEMTIME *)&Windows::Compat::Appraiser::WicaFactory::AppraiserProcessExeBuffer;
        if ( !Windows::Compat::Appraiser::WicaFactory::AppraiserBranchBuffer )
          Windows::Compat::Appraiser::Utilities::GetAppraiserBranch(v39, v40);
        v176 = &Windows::Compat::Appraiser::WicaFactory::AppraiserBranchBuffer;
        *(_QWORD *)v177 = Windows::Compat::Appraiser::WicaFactory::AppraiserVersion();
        v178[0] = &szValueBuf;
        SystemTime = 0;
        GetSystemTime(&SystemTime);
        v197 = SystemTime;
        v174 = (char *)&v197;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>,_tlgWrapSz<char>>(
          v38,
          (unsigned int)&unk_1802A0FC7,
          v41,
          v42,
          (__int64)&v174,
          (__int64)v178,
          (__int64)v177,
          (__int64)&v176,
          (__int64)&v175,
          (__int64)&v184,
          (__int64)&v183,
          (__int64)&v171,
          (__int64)&v172);
      }
    }
  }
  Windows::Compat::Appraiser::WriteLog(
    0,
    100,
    (unsigned int)"onecore\\base\\appcompat\\appraiser\\heads\\restore\\restoreappraiser.cpp",
    "Windows::Compat::Appraiser::RestoreAppraiser::StartRestoreAppraisal",
    0,
    (int)"StartRestoreAppraisal called.",
    v166);
  v14 = Windows::Compat::Appraiser::Utilities::ExpandDirectory(pszPath, v43, L"%WINDIR%\\system32\\appraiser\\");
  LODWORD(v171) = v14;
  if ( v14 < 0 )
  {
    v17 = "Error expanding inbox input directory: [0x%x].";
    v18 = 107;
    goto LABEL_14;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x6Bu,
      "onecore\\base\\appcompat\\appraiser\\heads\\restore\\restoreappraiser.cpp",
      "Windows::Compat::Appraiser::RestoreAppraiser::StartRestoreAppraisal",
      "Error expanding inbox input directory: [0x%x].",
      v14);
  v14 = PathCchAppend(pszPath, 0x104u, L"Appraiser_Data.ini");
  LODWORD(v171) = v14;
  if ( v14 < 0 )
  {
    v17 = "Error appending: [0x%x].";
    v18 = 110;
    goto LABEL_14;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x6Eu,
      "onecore\\base\\appcompat\\appraiser\\heads\\restore\\restoreappraiser.cpp",
      "Windows::Compat::Appraiser::RestoreAppraiser::StartRestoreAppraisal",
      "Error appending: [0x%x].",
      v14);
  v14 = Windows::Compat::Appraiser::DataFile::UseAlternateInboxDataPath(pszPath, 0);
  LODWORD(v171) = v14;
  if ( v14 < 0 )
  {
    v17 = "Error setting inbox data file path: [0x%x].";
    v18 = 113;
    goto LABEL_14;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x71u,
      "onecore\\base\\appcompat\\appraiser\\heads\\restore\\restoreappraiser.cpp",
      "Windows::Compat::Appraiser::RestoreAppraiser::StartRestoreAppraisal",
      "Error setting inbox data file path: [0x%x].",
      v14);
  v14 = Windows::Compat::Appraiser::Utilities::ExpandDirectory(Dst, v44, L"%TEMP%\\Appraiser_AlternateDataRestore.cab");
  LODWORD(v171) = v14;
  if ( v14 < 0 )
  {
    v17 = "Error expanding cab file path: [0x%x].";
    v18 = 120;
    goto LABEL_14;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x78u,
      "onecore\\base\\appcompat\\appraiser\\heads\\restore\\restoreappraiser.cpp",
      "Windows::Compat::Appraiser::RestoreAppraiser::StartRestoreAppraisal",
      "Error expanding cab file path: [0x%x].",
      v14);
  v45 = L"%TEMP%\\AltData\\";
  v46 = Windows::Compat::Appraiser::Utilities::EnsureAlternateCabUpToDateAndExtractIfNeeded(
          &v170,
          Dst,
          L"AlternateDownloadRestoreVersion",
          L"%TEMP%\\Appraiser_AlternateDataRestore_Temp.cab",
          L"%TEMP%\\AltData\\",
          0);
  v47 = v46;
  if ( v46 >= 0 )
  {
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0x7Fu,
        "onecore\\base\\appcompat\\appraiser\\heads\\restore\\restoreappraiser.cpp",
        "Windows::Compat::Appraiser::RestoreAppraiser::StartRestoreAppraisal",
        "Error getting alternate data files, swallowing: [0x%x].",
        v46);
  }
  else
  {
    LODWORD(v166) = v46;
    LODWORD(dwFlagsa) = v46;
    Windows::Compat::Appraiser::WriteLog(
      (Windows::Compat::Appraiser *)1,
      127,
      (unsigned int)"onecore\\base\\appcompat\\appraiser\\heads\\restore\\restoreappraiser.cpp",
      "Windows::Compat::Appraiser::RestoreAppraiser::StartRestoreAppraisal",
      dwFlagsa,
      (int)"Error getting alternate data files, swallowing: [0x%x].",
      v166);
    TraceLoggingCorrelationVector::TraceLoggingCorrelationVector((TraceLoggingCorrelationVector *)&v198);
    v48 = (volatile signed __int64 *)&v198;
    if ( Windows::Compat::Appraiser::WicaFactory::CorrelationVector )
      v48 = (volatile signed __int64 *)Windows::Compat::Appraiser::WicaFactory::CorrelationVector;
    TraceLoggingCorrelationVector::ToStringImpl(
      (TraceLoggingCorrelationVector *)v48,
      _InterlockedExchangeAdd64(v48 + 17, 0),
      v219);
    if ( Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive )
      UtcThrottle::Throttle((UtcThrottle *)&Windows::Compat::Appraiser::WicaFactory::UtcEventThrottler, v49);
    v50 = qword_1802C9628;
    if ( *(_DWORD *)qword_1802C9628 > 5u
      && (*(_QWORD *)(qword_1802C9628 + 16) & 0x200000000000LL) != 0
      && (*(_QWORD *)(qword_1802C9628 + 24) & 0x200000000000LL) == *(_QWORD *)(qword_1802C9628 + 24) )
    {
      v174 = v219;
      LODWORD(v171) = v47;
      v178[0] = "Windows::Compat::Appraiser::RestoreAppraiser::StartRestoreAppraisal";
      *(_QWORD *)v177 = "onecore\\base\\appcompat\\appraiser\\heads\\restore\\restoreappraiser.cpp";
      LODWORD(v172) = 127;
      v176 = (unsigned __int16 *)&szValueBuf;
      SystemTime = 0;
      GetSystemTime(&SystemTime);
      v197 = SystemTime;
      v175 = &v197;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v50,
        (unsigned int)&unk_1802A0F64,
        v51,
        v52,
        (__int64)&v175,
        (__int64)&v176,
        (__int64)&v172,
        (__int64)v177,
        (__int64)v178,
        (__int64)&v171,
        (__int64)&v174);
    }
    v170 = 0;
  }
  memset_0(pszPath, 0, 0x208u);
  if ( !v170 )
    v45 = L"%WINDIR%\\system32\\appraiser\\";
  v14 = Windows::Compat::Appraiser::Utilities::ExpandDirectory(pszPathIn, v53, v45);
  LODWORD(v171) = v14;
  if ( v14 < 0 )
  {
    v17 = "Error expanding input directory: [0x%x].";
    v18 = -116;
    goto LABEL_14;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x8Cu,
      "onecore\\base\\appcompat\\appraiser\\heads\\restore\\restoreappraiser.cpp",
      "Windows::Compat::Appraiser::RestoreAppraiser::StartRestoreAppraisal",
      "Error expanding input directory: [0x%x].",
      v14);
  v14 = PathCchCombineEx(pszPath, 0x104u, pszPathIn, L"Appraiser_Data.ini", (ULONG)dwFlagsa);
  LODWORD(v171) = v14;
  if ( v14 < 0 )
  {
    v17 = "Error combining: [0x%x].";
    v18 = -109;
    goto LABEL_14;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x93u,
      "onecore\\base\\appcompat\\appraiser\\heads\\restore\\restoreappraiser.cpp",
      "Windows::Compat::Appraiser::RestoreAppraiser::StartRestoreAppraisal",
      "Error combining: [0x%x].",
      v14);
  v54 = Windows::Compat::Appraiser::DataFile::Initialize((Windows::Compat::Appraiser::DataFile *)v194, pszPath);
  v14 = v54;
  LODWORD(v171) = v54;
  if ( v54 < 0 )
  {
    LODWORD(v168) = v54;
    LODWORD(dwFlagsa) = v54;
    Windows::Compat::Appraiser::WriteLog(
      (Windows::Compat::Appraiser *)1,
      150,
      (unsigned int)"onecore\\base\\appcompat\\appraiser\\heads\\restore\\restoreappraiser.cpp",
      "Windows::Compat::Appraiser::RestoreAppraiser::StartRestoreAppraisal",
      dwFlagsa,
      (int)"Failed to initialize datafile from filepath %ls: [0x%x].",
      (const char *)pszPath,
      v168);
    goto LABEL_15;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x96u,
      "onecore\\base\\appcompat\\appraiser\\heads\\restore\\restoreappraiser.cpp",
      "Windows::Compat::Appraiser::RestoreAppraiser::StartRestoreAppraisal",
      "Failed to initialize datafile from filepath %ls: [0x%x].",
      pszPath,
      v54);
  v14 = PathCchCombineEx(v227, 0x104u, pszPathIn, L"restore.sdb", (ULONG)dwFlagsa);
  LODWORD(v171) = v14;
  if ( v14 < 0 )
  {
    v17 = "Error combinining: [0x%x].";
    v18 = -99;
    goto LABEL_14;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x9Du,
      "onecore\\base\\appcompat\\appraiser\\heads\\restore\\restoreappraiser.cpp",
      "Windows::Compat::Appraiser::RestoreAppraiser::StartRestoreAppraisal",
      "Error combinining: [0x%x].",
      v14);
  inited = (void *)SdbInitDatabase(3, v227);
  v193[0] = inited;
  if ( !inited )
  {
    v14 = -2147024882;
    LODWORD(v171) = -2147024882;
    goto LABEL_15;
  }
  if ( !Windows::Compat::Appraiser::Utilities::IsMachineInSecurityMode() )
    Windows::Compat::Appraiser::SdbUtils::SendSdbInfoTelemetry(inited, v227);
  v14 = AcmEngineCreate(&v185);
  LODWORD(v171) = v14;
  if ( v14 < 0 )
  {
    v17 = "Error creating mig shim engine: [0x%x].";
    v18 = -88;
    goto LABEL_14;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0xA8u,
      "onecore\\base\\appcompat\\appraiser\\heads\\restore\\restoreappraiser.cpp",
      "Windows::Compat::Appraiser::RestoreAppraiser::StartRestoreAppraisal",
      "Error creating mig shim engine: [0x%x].",
      v14);
  Windows::Compat::Appraiser::RestoreAppraiser::AddMetadataPropertiesForRun(v218, (unsigned int *)&v181, v196);
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0xB3u,
      "onecore\\base\\appcompat\\appraiser\\heads\\restore\\restoreappraiser.cpp",
      "Windows::Compat::Appraiser::RestoreAppraiser::StartRestoreAppraisal",
      "AddMetadataPropertiesForRun failed: [0x%x].",
      v14);
  v14 = Windows::Compat::Appraiser::RestoreAppraiser::AddInventoryComponentsForRun(v213, (unsigned int *)&v181 + 1);
  LODWORD(v171) = v14;
  if ( v14 < 0 )
  {
    v17 = "AddInventoryComponentsForRun failed: [0x%x].";
    v18 = -70;
    goto LABEL_14;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0xBAu,
      "onecore\\base\\appcompat\\appraiser\\heads\\restore\\restoreappraiser.cpp",
      "Windows::Compat::Appraiser::RestoreAppraiser::StartRestoreAppraisal",
      "AddInventoryComponentsForRun failed: [0x%x].",
      v14);
  v14 = Windows::Compat::Appraiser::RestoreAppraiser::AddDatasourceComponentsForRun(
          v214,
          (unsigned int *)&v181 + 2,
          inited,
          v185);
  LODWORD(v171) = v14;
  if ( v14 < 0 )
  {
    v17 = "AddDatasourceComponentsForRun failed: [0x%x].";
    v18 = -63;
    goto LABEL_14;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0xC1u,
      "onecore\\base\\appcompat\\appraiser\\heads\\restore\\restoreappraiser.cpp",
      "Windows::Compat::Appraiser::RestoreAppraiser::StartRestoreAppraisal",
      "AddDatasourceComponentsForRun failed: [0x%x].",
      v14);
  v14 = Windows::Compat::Appraiser::RestoreAppraiser::AddDecisionmakerComponentsForRun(
          v215,
          (unsigned int *)&v181 + 3,
          (struct Windows::Compat::Appraiser::DataFile *)v194);
  LODWORD(v171) = v14;
  if ( v14 < 0 )
  {
    v17 = "AddDecisionmakerComponentsForRun failed: [0x%x].";
    v18 = -56;
    goto LABEL_14;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0xC8u,
      "onecore\\base\\appcompat\\appraiser\\heads\\restore\\restoreappraiser.cpp",
      "Windows::Compat::Appraiser::RestoreAppraiser::StartRestoreAppraisal",
      "AddDecisionmakerComponentsForRun failed: [0x%x].",
      v14);
  v14 = Windows::Compat::Appraiser::RestoreAppraiser::AddDecisionAggregatorComponentsForRun(v216, &v182);
  LODWORD(v171) = v14;
  if ( v14 < 0 )
  {
    v17 = "AddDecisionAggregatorComponentsForRun failed: [0x%x].";
    v18 = -48;
    goto LABEL_14;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0xD0u,
      "onecore\\base\\appcompat\\appraiser\\heads\\restore\\restoreappraiser.cpp",
      "Windows::Compat::Appraiser::RestoreAppraiser::StartRestoreAppraisal",
      "AddDecisionAggregatorComponentsForRun failed: [0x%x].",
      v14);
  v14 = Windows::Compat::Appraiser::RestoreAppraiser::AddOutputterComponentsForRun(
          v217,
          (unsigned int *)v169,
          (struct Windows::Compat::Appraiser::DataFile *)v194,
          a1);
  LODWORD(v171) = v14;
  if ( v14 < 0 )
  {
    v17 = "AddOutputterComponentsForRun failed: [0x%x].";
    v18 = -41;
    goto LABEL_14;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0xD7u,
      "onecore\\base\\appcompat\\appraiser\\heads\\restore\\restoreappraiser.cpp",
      "Windows::Compat::Appraiser::RestoreAppraiser::StartRestoreAppraisal",
      "AddOutputterComponentsForRun failed: [0x%x].",
      v14);
  *(_QWORD *)&v187 = v218;
  v191 = v181;
  *((_QWORD *)&v187 + 1) = v213;
  *(_QWORD *)&v188 = v214;
  *((_QWORD *)&v188 + 1) = v215;
  *(_QWORD *)&v189 = v216;
  *(_QWORD *)&v192 = __PAIR64__(*(unsigned int *)v169, v182);
  *((_QWORD *)&v189 + 1) = v217;
  if ( v195 )
  {
    v14 = Windows::Compat::Appraiser::Utilities::ArrayToListAlloc((const unsigned __int16 ***)lpMem, v195);
    LODWORD(v171) = v14;
    if ( v14 < 0 )
    {
      v17 = "Error listing non fatal components: [0x%x].";
      v18 = -9;
      goto LABEL_14;
    }
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0xF7u,
        "onecore\\base\\appcompat\\appraiser\\heads\\restore\\restoreappraiser.cpp",
        "Windows::Compat::Appraiser::RestoreAppraiser::StartRestoreAppraisal",
        "Error listing non fatal components: [0x%x].",
        v14);
    DWORD2(v192) = *((_DWORD *)v195 + 4);
  }
  tip2::tip_test<tip2::details::merged_data<_tip_MercuryRestoreExtendedAppsSuccess_attributes,tip2::test_data_basic>>::start(
    &v186,
    &v197);
  *(_OWORD *)v219 = v187;
  v220 = v188;
  v221 = v189;
  v222 = *(_OWORD *)lpMem;
  v223 = v191;
  v224 = v192;
  v14 = Windows::Compat::Appraiser::WicaFactory::DoWicaRun(v219);
  LODWORD(v171) = v14;
  v56 = "TipReason::FailedRestore";
  v57 = "TipReason::FailedRestore";
  v58 = 84;
  do
  {
    ++v56;
    if ( v58 == 58 )
      v57 = v56;
    v58 = *v56;
  }
  while ( *v56 );
  if ( v14 < 0 )
  {
    v59 = (_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_MercuryRestoreExtendedAppsSuccess_attributes,tip2::test_data_basic>>::ensure_data(&v186);
    tip2::details::shared_data<1,0,1>::set_flag_value_without_lock<long>(*v59 + 8LL, 0, v57, (unsigned int)v14);
  }
  if ( v186 )
  {
    v60 = (char *)v186 + 8;
    v61 = (struct _RTL_CRITICAL_SECTION *)((char *)v186 + 200);
    EnterCriticalSection((LPCRITICAL_SECTION)v186 + 5);
    *((_DWORD *)v60 + 16) |= 0x300u;
    if ( *((_QWORD *)v60 + 30) )
      tip2::details::shared_data<1,0,1>::complete_helper(v60, 2);
    if ( v61 )
      LeaveCriticalSection(v61);
  }
  if ( Windows::Compat::Appraiser::Utilities::IsMachineInSecurityMode() )
  {
    v74 = "TipReasonV2::SecurityMode";
    v69 = "TipReasonV2::SecurityMode";
    v75 = 84;
    do
    {
      ++v74;
      if ( v75 == 58 )
        v69 = v74;
      v75 = *v74;
    }
    while ( *v74 );
    v76 = (struct _RTL_CRITICAL_SECTION **)tip2::tip_test<tip2::details::merged_data<_tip_MercuryExtendedAppsRestoreV2Success_attributes,tip2::test_data_basic>>::ensure_data(&pv);
    p_LockCount = (__int64)&(*v76)->LockCount;
    EnterCriticalSection(*v76 + 5);
    ++*(_DWORD *)(p_LockCount + 232);
    if ( (*(_DWORD *)(p_LockCount + 64) & 0x100) == 0 )
    {
      v73 = 0;
      goto LABEL_180;
    }
  }
  else
  {
    TraceLoggingCorrelationVector::TraceLoggingCorrelationVector((TraceLoggingCorrelationVector *)&v198);
    v62 = (volatile signed __int64 *)&v198;
    if ( Windows::Compat::Appraiser::WicaFactory::CorrelationVector )
      v62 = (volatile signed __int64 *)Windows::Compat::Appraiser::WicaFactory::CorrelationVector;
    TraceLoggingCorrelationVector::ToStringImpl(
      (TraceLoggingCorrelationVector *)v62,
      _InterlockedExchangeAdd64(v62 + 17, 0),
      v219);
    if ( Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive )
      UtcThrottle::Throttle((UtcThrottle *)&Windows::Compat::Appraiser::WicaFactory::UtcEventThrottler, v63);
    v64 = qword_1802C9560;
    if ( *(_DWORD *)qword_1802C9560 > 5u )
    {
      v65 = *(unsigned __int16 **)(qword_1802C9560 + 24);
      if ( (*(_QWORD *)(qword_1802C9560 + 16) & 0x800000000000LL) != 0
        && (unsigned __int16 *)((unsigned __int64)v65 & 0x800000000000LL) == v65 )
      {
        v174 = v219;
        v178[0] = 0x1000000;
        LODWORD(v172) = v196;
        *(_DWORD *)v169 = v14;
        *(_QWORD *)v177 = L"DoWicaRun";
        if ( !Windows::Compat::Appraiser::WicaFactory::AppraiserBranchBuffer )
          Windows::Compat::Appraiser::Utilities::GetAppraiserBranch(v65, 0x800000000000uLL);
        v176 = &Windows::Compat::Appraiser::WicaFactory::AppraiserBranchBuffer;
        v175 = (struct _SYSTEMTIME *)Windows::Compat::Appraiser::WicaFactory::AppraiserVersion();
        v184 = (const wchar_t *)&szValueBuf;
        SystemTime = 0;
        GetSystemTime(&SystemTime);
        v197 = SystemTime;
        v183 = &v197;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<char>>(
          v64,
          (unsigned int)&unk_1802A0ED9,
          v66,
          v67,
          (__int64)&v183,
          (__int64)&v184,
          (__int64)&v175,
          (__int64)&v176,
          (__int64)v177,
          (__int64)v169,
          (__int64)&v172,
          (__int64)v178,
          (__int64)&v174);
      }
    }
    v173 = 1;
    v68 = "TipReasonV2::RestoreEventSent";
    v69 = "TipReasonV2::RestoreEventSent";
    v70 = 84;
    do
    {
      ++v68;
      if ( v70 == 58 )
        v69 = v68;
      v70 = *v68;
    }
    while ( *v68 );
    v71 = (struct _RTL_CRITICAL_SECTION **)tip2::tip_test<tip2::details::merged_data<_tip_MercuryExtendedAppsRestoreV2Success_attributes,tip2::test_data_basic>>::ensure_data(&pv);
    p_LockCount = (__int64)&(*v71)->LockCount;
    EnterCriticalSection(*v71 + 5);
    ++*(_DWORD *)(p_LockCount + 232);
    if ( (*(_DWORD *)(p_LockCount + 64) & 0x100) == 0 )
    {
      v73 = 1;
LABEL_180:
      tip2::details::shared_data<0,0,1>::get_or_add_flag_under_lock(p_LockCount, v73, v69);
    }
  }
  tip2::details::shared_data<0,0,1>::end_update(p_LockCount);
  if ( v14 < 0 )
  {
    v17 = "Error running restore appraisal: [0x%x].";
    v18 = 16;
    goto LABEL_14;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x110u,
      "onecore\\base\\appcompat\\appraiser\\heads\\restore\\restoreappraiser.cpp",
      "Windows::Compat::Appraiser::RestoreAppraiser::StartRestoreAppraisal",
      "Error running restore appraisal: [0x%x].",
      v14);
LABEL_15:
  v19 = "TipReasonV2::FunctionFailure";
  v20 = "TipReasonV2::FunctionFailure";
  v21 = 84;
  do
  {
    ++v19;
    if ( v21 == 58 )
      v20 = v19;
    v21 = *v19;
  }
  while ( *v19 );
  if ( v14 < 0 )
  {
    v22 = *(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_MercuryExtendedAppsRestoreV2Success_attributes,tip2::test_data_basic>>::ensure_data(&pv);
    EnterCriticalSection((LPCRITICAL_SECTION)(v22 + 200));
    ++*(_DWORD *)(v22 + 240);
    if ( (*(_DWORD *)(v22 + 72) & 0x100) == 0 )
    {
      v23 = tip2::details::shared_data<0,0,1>::get_or_add_flag_under_lock(v22 + 8, 2, v20);
      v24 = v23;
      if ( v23 )
      {
        v25 = v23 + 16;
        PropVariantClear((PROPVARIANT *)(v23 + 16));
        *(_OWORD *)v25 = 0;
        *(_QWORD *)(v25 + 16) = 0;
        *(_WORD *)v25 = 3;
        *(_DWORD *)(v24 + 24) = v14;
      }
    }
    tip2::details::shared_data<0,0,1>::end_update(v22 + 8);
  }
  if ( !Windows::Compat::Appraiser::Utilities::IsMachineInSecurityMode() && !v173 )
  {
    TraceLoggingCorrelationVector::TraceLoggingCorrelationVector((TraceLoggingCorrelationVector *)&v198);
    v26 = (volatile signed __int64 *)&v198;
    if ( Windows::Compat::Appraiser::WicaFactory::CorrelationVector )
      v26 = (volatile signed __int64 *)Windows::Compat::Appraiser::WicaFactory::CorrelationVector;
    TraceLoggingCorrelationVector::ToStringImpl(
      (TraceLoggingCorrelationVector *)v26,
      _InterlockedExchangeAdd64(v26 + 17, 0),
      v219);
    if ( Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive )
      UtcThrottle::Throttle((UtcThrottle *)&Windows::Compat::Appraiser::WicaFactory::UtcEventThrottler, v27);
    v28 = qword_1802C9560;
    if ( *(_DWORD *)qword_1802C9560 > 5u )
    {
      v29 = *(unsigned __int16 **)(qword_1802C9560 + 24);
      if ( (*(_QWORD *)(qword_1802C9560 + 16) & 0x800000000000LL) != 0
        && (unsigned __int16 *)((unsigned __int64)v29 & 0x800000000000LL) == v29 )
      {
        v174 = v219;
        v178[0] = 0x1000000;
        LODWORD(v172) = 0;
        *(_DWORD *)v169 = v14;
        *(_QWORD *)v177 = L"StartRestoreAppraisal";
        if ( !Windows::Compat::Appraiser::WicaFactory::AppraiserBranchBuffer )
          Windows::Compat::Appraiser::Utilities::GetAppraiserBranch(v29, 0x800000000000uLL);
        v176 = &Windows::Compat::Appraiser::WicaFactory::AppraiserBranchBuffer;
        v175 = (struct _SYSTEMTIME *)Windows::Compat::Appraiser::WicaFactory::AppraiserVersion();
        v184 = (const wchar_t *)&szValueBuf;
        SystemTime = 0;
        GetSystemTime(&SystemTime);
        v197 = SystemTime;
        v183 = &v197;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<char>>(
          v28,
          (unsigned int)&unk_1802A0DEB,
          v30,
          v31,
          (__int64)&v183,
          (__int64)&v184,
          (__int64)&v175,
          (__int64)&v176,
          (__int64)v177,
          (__int64)v169,
          (__int64)&v172,
          (__int64)v178,
          (__int64)&v174);
      }
    }
    v32 = "TipReasonV2::RestoreEventSent";
    do
    {
      ++v16;
      if ( v15 == 58 )
        v32 = v16;
      v15 = *v16;
    }
    while ( *v16 );
    v33 = *(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_MercuryExtendedAppsRestoreV2Success_attributes,tip2::test_data_basic>>::ensure_data(&pv);
    EnterCriticalSection((LPCRITICAL_SECTION)(v33 + 200));
    ++*(_DWORD *)(v33 + 240);
    if ( (*(_DWORD *)(v33 + 72) & 0x100) == 0 )
      tip2::details::shared_data<0,0,1>::get_or_add_flag_under_lock(v33 + 8, 1, v32);
    tip2::details::shared_data<0,0,1>::end_update(v33 + 8);
  }
  if ( pv )
  {
    v77 = (char *)pv + 8;
    v78 = (struct _RTL_CRITICAL_SECTION *)((char *)pv + 200);
    EnterCriticalSection((LPCRITICAL_SECTION)pv + 5);
    *((_DWORD *)v77 + 16) |= 0x300u;
    if ( *((_QWORD *)v77 + 30) )
      tip2::details::shared_data<0,0,1>::complete_helper(v77, 2);
    if ( v78 )
      LeaveCriticalSection(v78);
  }
  v79 = Windows::Compat::Appraiser::DataFile::UnInitialize((Windows::Compat::Appraiser::DataFile *)v194);
  v80 = v79;
  if ( v79 >= 0 )
  {
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0x11Fu,
        "onecore\\base\\appcompat\\appraiser\\heads\\restore\\restoreappraiser.cpp",
        "Windows::Compat::Appraiser::RestoreAppraiser::StartRestoreAppraisal",
        "Error uninitializing data file: [0x%x].",
        v79);
  }
  else
  {
    LODWORD(v166) = v79;
    LODWORD(dwFlagsa) = v79;
    Windows::Compat::Appraiser::WriteLog(
      (Windows::Compat::Appraiser *)1,
      31,
      (unsigned int)"onecore\\base\\appcompat\\appraiser\\heads\\restore\\restoreappraiser.cpp",
      "Windows::Compat::Appraiser::RestoreAppraiser::StartRestoreAppraisal",
      dwFlagsa,
      (int)"Error uninitializing data file: [0x%x].",
      v166);
    TraceLoggingCorrelationVector::TraceLoggingCorrelationVector((TraceLoggingCorrelationVector *)&v198);
    v81 = (volatile signed __int64 *)&v198;
    if ( Windows::Compat::Appraiser::WicaFactory::CorrelationVector )
      v81 = (volatile signed __int64 *)Windows::Compat::Appraiser::WicaFactory::CorrelationVector;
    TraceLoggingCorrelationVector::ToStringImpl(
      (TraceLoggingCorrelationVector *)v81,
      _InterlockedExchangeAdd64(v81 + 17, 0),
      v219);
    if ( Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive )
      UtcThrottle::Throttle((UtcThrottle *)&Windows::Compat::Appraiser::WicaFactory::UtcEventThrottler, v82);
    v83 = qword_1802C9628;
    if ( *(_DWORD *)qword_1802C9628 > 5u
      && (*(_QWORD *)(qword_1802C9628 + 16) & 0x200000000000LL) != 0
      && (*(_QWORD *)(qword_1802C9628 + 24) & 0x200000000000LL) == *(_QWORD *)(qword_1802C9628 + 24) )
    {
      v174 = v219;
      LODWORD(v172) = v80;
      v178[0] = "Windows::Compat::Appraiser::RestoreAppraiser::StartRestoreAppraisal";
      *(_QWORD *)v177 = "onecore\\base\\appcompat\\appraiser\\heads\\restore\\restoreappraiser.cpp";
      *(_DWORD *)v169 = 287;
      v176 = (unsigned __int16 *)&szValueBuf;
      SystemTime = 0;
      GetSystemTime(&SystemTime);
      v197 = SystemTime;
      v175 = &v197;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v83,
        (unsigned int)&unk_1802A0D88,
        v84,
        v85,
        (__int64)&v175,
        (__int64)&v176,
        (__int64)v169,
        (__int64)v177,
        (__int64)v178,
        (__int64)&v172,
        (__int64)&v174);
    }
  }
  if ( v185 )
  {
    AcmEngineDelete(v185);
    v185 = 0;
  }
  for ( i = 0; i < (unsigned int)v191; ++i )
  {
    v87 = v187;
    v88 = *(void (__fastcall ****)(_QWORD))(v187 + 8LL * i);
    if ( v88 )
    {
      (**v88)(v88);
      *(_QWORD *)(v87 + 8LL * i) = 0;
    }
  }
  v89 = 0;
  if ( DWORD1(v192) )
  {
    do
    {
      v90 = *((_QWORD *)&v189 + 1);
      v91 = *(_QWORD *)(*((_QWORD *)&v189 + 1) + 8LL * v89) + 8LL;
      v92 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v91 + 8LL))(v91);
      v93 = v92;
      if ( v92 >= 0 )
      {
        if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
          Windows::Compat::Appraiser::WicaFactory::RunPrintf(
            0x12Fu,
            "onecore\\base\\appcompat\\appraiser\\heads\\restore\\restoreappraiser.cpp",
            "Windows::Compat::Appraiser::RestoreAppraiser::StartRestoreAppraisal",
            "Error uninitializing: [0x%x].",
            v92);
      }
      else
      {
        LODWORD(v166) = v92;
        LODWORD(dwFlagsa) = v92;
        Windows::Compat::Appraiser::WriteLog(
          (Windows::Compat::Appraiser *)1,
          47,
          (unsigned int)"onecore\\base\\appcompat\\appraiser\\heads\\restore\\restoreappraiser.cpp",
          "Windows::Compat::Appraiser::RestoreAppraiser::StartRestoreAppraisal",
          dwFlagsa,
          (int)"Error uninitializing: [0x%x].",
          v166);
        TraceLoggingCorrelationVector::TraceLoggingCorrelationVector((TraceLoggingCorrelationVector *)&v198);
        v94 = (volatile signed __int64 *)&v198;
        if ( Windows::Compat::Appraiser::WicaFactory::CorrelationVector )
          v94 = (volatile signed __int64 *)Windows::Compat::Appraiser::WicaFactory::CorrelationVector;
        TraceLoggingCorrelationVector::ToStringImpl(
          (TraceLoggingCorrelationVector *)v94,
          _InterlockedExchangeAdd64(v94 + 17, 0),
          v219);
        if ( Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive )
          UtcThrottle::Throttle((UtcThrottle *)&Windows::Compat::Appraiser::WicaFactory::UtcEventThrottler, v95);
        v96 = qword_1802C9628;
        if ( *(_DWORD *)qword_1802C9628 > 5u
          && (*(_QWORD *)(qword_1802C9628 + 16) & 0x200000000000LL) != 0
          && (*(_QWORD *)(qword_1802C9628 + 24) & 0x200000000000LL) == *(_QWORD *)(qword_1802C9628 + 24) )
        {
          v174 = v219;
          LODWORD(v172) = v93;
          v178[0] = "Windows::Compat::Appraiser::RestoreAppraiser::StartRestoreAppraisal";
          *(_QWORD *)v177 = "onecore\\base\\appcompat\\appraiser\\heads\\restore\\restoreappraiser.cpp";
          *(_DWORD *)v169 = 303;
          v176 = (unsigned __int16 *)&szValueBuf;
          SystemTime = 0;
          GetSystemTime(&SystemTime);
          v197 = SystemTime;
          v175 = &v197;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
            v96,
            (unsigned int)&unk_1802A0E76,
            v97,
            v98,
            (__int64)&v175,
            (__int64)&v176,
            (__int64)v169,
            (__int64)v177,
            (__int64)v178,
            (__int64)&v172,
            (__int64)&v174);
        }
      }
      v99 = *(_QWORD *)(v90 + 8LL * v89);
      if ( v99 )
      {
        (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v99 + 8LL))(v99, 1);
        *(_QWORD *)(v90 + 8LL * v89) = 0;
      }
      ++v89;
    }
    while ( v89 < DWORD1(v192) );
    v14 = v171;
  }
  v100 = 0;
  if ( (_DWORD)v192 )
  {
    do
    {
      v101 = v189;
      v102 = *(_QWORD *)(v189 + 8LL * v100) + 8LL;
      v103 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v102 + 8LL))(v102);
      v104 = v103;
      if ( v103 >= 0 )
      {
        if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
          Windows::Compat::Appraiser::WicaFactory::RunPrintf(
            0x136u,
            "onecore\\base\\appcompat\\appraiser\\heads\\restore\\restoreappraiser.cpp",
            "Windows::Compat::Appraiser::RestoreAppraiser::StartRestoreAppraisal",
            "Error uninitializing: [0x%x].",
            v103);
      }
      else
      {
        LODWORD(v166) = v103;
        LODWORD(dwFlagsa) = v103;
        Windows::Compat::Appraiser::WriteLog(
          (Windows::Compat::Appraiser *)1,
          54,
          (unsigned int)"onecore\\base\\appcompat\\appraiser\\heads\\restore\\restoreappraiser.cpp",
          "Windows::Compat::Appraiser::RestoreAppraiser::StartRestoreAppraisal",
          dwFlagsa,
          (int)"Error uninitializing: [0x%x].",
          v166);
        TraceLoggingCorrelationVector::TraceLoggingCorrelationVector((TraceLoggingCorrelationVector *)&v198);
        v105 = (volatile signed __int64 *)&v198;
        if ( Windows::Compat::Appraiser::WicaFactory::CorrelationVector )
          v105 = (volatile signed __int64 *)Windows::Compat::Appraiser::WicaFactory::CorrelationVector;
        TraceLoggingCorrelationVector::ToStringImpl(
          (TraceLoggingCorrelationVector *)v105,
          _InterlockedExchangeAdd64(v105 + 17, 0),
          v219);
        if ( Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive )
          UtcThrottle::Throttle((UtcThrottle *)&Windows::Compat::Appraiser::WicaFactory::UtcEventThrottler, v106);
        v107 = qword_1802C9628;
        if ( *(_DWORD *)qword_1802C9628 > 5u
          && (*(_QWORD *)(qword_1802C9628 + 16) & 0x200000000000LL) != 0
          && (*(_QWORD *)(qword_1802C9628 + 24) & 0x200000000000LL) == *(_QWORD *)(qword_1802C9628 + 24) )
        {
          v174 = v219;
          LODWORD(v172) = v104;
          v178[0] = "Windows::Compat::Appraiser::RestoreAppraiser::StartRestoreAppraisal";
          *(_QWORD *)v177 = "onecore\\base\\appcompat\\appraiser\\heads\\restore\\restoreappraiser.cpp";
          *(_DWORD *)v169 = 310;
          v176 = (unsigned __int16 *)&szValueBuf;
          SystemTime = 0;
          GetSystemTime(&SystemTime);
          v197 = SystemTime;
          v175 = &v197;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
            v107,
            (unsigned int)&unk_1802A0D25,
            v108,
            v109,
            (__int64)&v175,
            (__int64)&v176,
            (__int64)v169,
            (__int64)v177,
            (__int64)v178,
            (__int64)&v172,
            (__int64)&v174);
        }
      }
      v110 = *(_QWORD *)(v101 + 8LL * v100);
      if ( v110 )
      {
        (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v110 + 8LL))(v110, 1);
        *(_QWORD *)(v101 + 8LL * v100) = 0;
      }
      ++v100;
    }
    while ( v100 < (unsigned int)v192 );
    v14 = v171;
  }
  v111 = 0;
  if ( HIDWORD(v191) )
  {
    do
    {
      v112 = *((_QWORD *)&v188 + 1);
      v113 = *(_QWORD *)(*((_QWORD *)&v188 + 1) + 8LL * v111) + 8LL;
      v114 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v113 + 8LL))(v113);
      v115 = v114;
      if ( v114 >= 0 )
      {
        if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
          Windows::Compat::Appraiser::WicaFactory::RunPrintf(
            0x13Du,
            "onecore\\base\\appcompat\\appraiser\\heads\\restore\\restoreappraiser.cpp",
            "Windows::Compat::Appraiser::RestoreAppraiser::StartRestoreAppraisal",
            "Error uninitializing: [0x%x].",
            v114);
      }
      else
      {
        LODWORD(v166) = v114;
        LODWORD(dwFlagsa) = v114;
        Windows::Compat::Appraiser::WriteLog(
          (Windows::Compat::Appraiser *)1,
          61,
          (unsigned int)"onecore\\base\\appcompat\\appraiser\\heads\\restore\\restoreappraiser.cpp",
          "Windows::Compat::Appraiser::RestoreAppraiser::StartRestoreAppraisal",
          dwFlagsa,
          (int)"Error uninitializing: [0x%x].",
          v166);
        TraceLoggingCorrelationVector::TraceLoggingCorrelationVector((TraceLoggingCorrelationVector *)&v198);
        v116 = (volatile signed __int64 *)&v198;
        if ( Windows::Compat::Appraiser::WicaFactory::CorrelationVector )
          v116 = (volatile signed __int64 *)Windows::Compat::Appraiser::WicaFactory::CorrelationVector;
        TraceLoggingCorrelationVector::ToStringImpl(
          (TraceLoggingCorrelationVector *)v116,
          _InterlockedExchangeAdd64(v116 + 17, 0),
          v219);
        if ( Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive )
          UtcThrottle::Throttle((UtcThrottle *)&Windows::Compat::Appraiser::WicaFactory::UtcEventThrottler, v117);
        v118 = qword_1802C9628;
        if ( *(_DWORD *)qword_1802C9628 > 5u
          && (*(_QWORD *)(qword_1802C9628 + 16) & 0x200000000000LL) != 0
          && (*(_QWORD *)(qword_1802C9628 + 24) & 0x200000000000LL) == *(_QWORD *)(qword_1802C9628 + 24) )
        {
          v174 = v219;
          LODWORD(v172) = v115;
          v178[0] = "Windows::Compat::Appraiser::RestoreAppraiser::StartRestoreAppraisal";
          *(_QWORD *)v177 = "onecore\\base\\appcompat\\appraiser\\heads\\restore\\restoreappraiser.cpp";
          *(_DWORD *)v169 = 317;
          v176 = (unsigned __int16 *)&szValueBuf;
          SystemTime = 0;
          GetSystemTime(&SystemTime);
          v197 = SystemTime;
          v175 = &v197;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
            v118,
            (unsigned int)&unk_1802A0CC2,
            v119,
            v120,
            (__int64)&v175,
            (__int64)&v176,
            (__int64)v169,
            (__int64)v177,
            (__int64)v178,
            (__int64)&v172,
            (__int64)&v174);
        }
      }
      v121 = *(_QWORD *)(v112 + 8LL * v111);
      if ( v121 )
      {
        (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v121 + 8LL))(v121, 1);
        *(_QWORD *)(v112 + 8LL * v111) = 0;
      }
      ++v111;
    }
    while ( v111 < HIDWORD(v191) );
    v14 = v171;
  }
  v122 = 0;
  if ( DWORD2(v191) )
  {
    do
    {
      v123 = v188;
      v124 = *(_QWORD *)(v188 + 8LL * v122) + 8LL;
      v125 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v124 + 8LL))(v124);
      v126 = v125;
      if ( v125 >= 0 )
      {
        if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
          Windows::Compat::Appraiser::WicaFactory::RunPrintf(
            0x144u,
            "onecore\\base\\appcompat\\appraiser\\heads\\restore\\restoreappraiser.cpp",
            "Windows::Compat::Appraiser::RestoreAppraiser::StartRestoreAppraisal",
            "Error uninitializing: [0x%x].",
            v125);
      }
      else
      {
        LODWORD(v166) = v125;
        LODWORD(dwFlagsa) = v125;
        Windows::Compat::Appraiser::WriteLog(
          (Windows::Compat::Appraiser *)1,
          68,
          (unsigned int)"onecore\\base\\appcompat\\appraiser\\heads\\restore\\restoreappraiser.cpp",
          "Windows::Compat::Appraiser::RestoreAppraiser::StartRestoreAppraisal",
          dwFlagsa,
          (int)"Error uninitializing: [0x%x].",
          v166);
        TraceLoggingCorrelationVector::TraceLoggingCorrelationVector((TraceLoggingCorrelationVector *)&v198);
        v127 = (volatile signed __int64 *)&v198;
        if ( Windows::Compat::Appraiser::WicaFactory::CorrelationVector )
          v127 = (volatile signed __int64 *)Windows::Compat::Appraiser::WicaFactory::CorrelationVector;
        TraceLoggingCorrelationVector::ToStringImpl(
          (TraceLoggingCorrelationVector *)v127,
          _InterlockedExchangeAdd64(v127 + 17, 0),
          v219);
        if ( Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive )
          UtcThrottle::Throttle((UtcThrottle *)&Windows::Compat::Appraiser::WicaFactory::UtcEventThrottler, v128);
        v129 = qword_1802C9628;
        if ( *(_DWORD *)qword_1802C9628 > 5u
          && (*(_QWORD *)(qword_1802C9628 + 16) & 0x200000000000LL) != 0
          && (*(_QWORD *)(qword_1802C9628 + 24) & 0x200000000000LL) == *(_QWORD *)(qword_1802C9628 + 24) )
        {
          v174 = v219;
          LODWORD(v172) = v126;
          v178[0] = "Windows::Compat::Appraiser::RestoreAppraiser::StartRestoreAppraisal";
          *(_QWORD *)v177 = "onecore\\base\\appcompat\\appraiser\\heads\\restore\\restoreappraiser.cpp";
          *(_DWORD *)v169 = 324;
          v176 = (unsigned __int16 *)&szValueBuf;
          SystemTime = 0;
          GetSystemTime(&SystemTime);
          v197 = SystemTime;
          v175 = &v197;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
            v129,
            (unsigned int)&unk_1802A0C5F,
            v130,
            v131,
            (__int64)&v175,
            (__int64)&v176,
            (__int64)v169,
            (__int64)v177,
            (__int64)v178,
            (__int64)&v172,
            (__int64)&v174);
        }
      }
      v132 = *(_QWORD *)(v123 + 8LL * v122);
      if ( v132 )
      {
        (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v132 + 8LL))(v132, 1);
        *(_QWORD *)(v123 + 8LL * v122) = 0;
      }
      ++v122;
    }
    while ( v122 < DWORD2(v191) );
    v14 = v171;
  }
  v133 = 0;
  if ( DWORD1(v191) )
  {
    do
    {
      v134 = *((_QWORD *)&v187 + 1);
      v135 = *(_QWORD *)(*((_QWORD *)&v187 + 1) + 8LL * v133) + 8LL;
      v136 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v135 + 8LL))(v135);
      v137 = v136;
      if ( v136 >= 0 )
      {
        if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
          Windows::Compat::Appraiser::WicaFactory::RunPrintf(
            0x14Bu,
            "onecore\\base\\appcompat\\appraiser\\heads\\restore\\restoreappraiser.cpp",
            "Windows::Compat::Appraiser::RestoreAppraiser::StartRestoreAppraisal",
            "Error uninitializing: [0x%x].",
            v136);
      }
      else
      {
        LODWORD(v166) = v136;
        LODWORD(dwFlagsa) = v136;
        Windows::Compat::Appraiser::WriteLog(
          (Windows::Compat::Appraiser *)1,
          75,
          (unsigned int)"onecore\\base\\appcompat\\appraiser\\heads\\restore\\restoreappraiser.cpp",
          "Windows::Compat::Appraiser::RestoreAppraiser::StartRestoreAppraisal",
          dwFlagsa,
          (int)"Error uninitializing: [0x%x].",
          v166);
        TraceLoggingCorrelationVector::TraceLoggingCorrelationVector((TraceLoggingCorrelationVector *)&v198);
        v138 = (volatile signed __int64 *)&v198;
        if ( Windows::Compat::Appraiser::WicaFactory::CorrelationVector )
          v138 = (volatile signed __int64 *)Windows::Compat::Appraiser::WicaFactory::CorrelationVector;
        TraceLoggingCorrelationVector::ToStringImpl(
          (TraceLoggingCorrelationVector *)v138,
          _InterlockedExchangeAdd64(v138 + 17, 0),
          v219);
        if ( Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive )
          UtcThrottle::Throttle((UtcThrottle *)&Windows::Compat::Appraiser::WicaFactory::UtcEventThrottler, v139);
        v140 = qword_1802C9628;
        if ( *(_DWORD *)qword_1802C9628 > 5u
          && (*(_QWORD *)(qword_1802C9628 + 16) & 0x200000000000LL) != 0
          && (*(_QWORD *)(qword_1802C9628 + 24) & 0x200000000000LL) == *(_QWORD *)(qword_1802C9628 + 24) )
        {
          v174 = v219;
          LODWORD(v172) = v137;
          v178[0] = "Windows::Compat::Appraiser::RestoreAppraiser::StartRestoreAppraisal";
          *(_QWORD *)v177 = "onecore\\base\\appcompat\\appraiser\\heads\\restore\\restoreappraiser.cpp";
          *(_DWORD *)v169 = 331;
          v176 = (unsigned __int16 *)&szValueBuf;
          SystemTime = 0;
          GetSystemTime(&SystemTime);
          v197 = SystemTime;
          v175 = &v197;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
            v140,
            (unsigned int)&unk_1802A0BFC,
            v141,
            v142,
            (__int64)&v175,
            (__int64)&v176,
            (__int64)v169,
            (__int64)v177,
            (__int64)v178,
            (__int64)&v172,
            (__int64)&v174);
        }
      }
      v143 = *(_QWORD *)(v134 + 8LL * v133);
      if ( v143 )
      {
        (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v143 + 8LL))(v143, 1);
        *(_QWORD *)(v134 + 8LL * v133) = 0;
      }
      ++v133;
    }
    while ( v133 < DWORD1(v191) );
    v14 = v171;
  }
  v144 = lpMem[0];
  if ( lpMem[0] )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v144);
  }
  v146 = Windows::Compat::Appraiser::SdbUtils::SafeReleaseDatabase(v193);
  v147 = v146;
  if ( v146 >= 0 )
  {
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0x152u,
        "onecore\\base\\appcompat\\appraiser\\heads\\restore\\restoreappraiser.cpp",
        "Windows::Compat::Appraiser::RestoreAppraiser::StartRestoreAppraisal",
        "RestoreAppraiser leaked one or more duplicate sdb handles [0x%x].",
        v146);
  }
  else
  {
    LODWORD(v166) = v146;
    LODWORD(dwFlagsa) = v146;
    Windows::Compat::Appraiser::WriteLog(
      (Windows::Compat::Appraiser *)1,
      82,
      (unsigned int)"onecore\\base\\appcompat\\appraiser\\heads\\restore\\restoreappraiser.cpp",
      "Windows::Compat::Appraiser::RestoreAppraiser::StartRestoreAppraisal",
      dwFlagsa,
      (int)"RestoreAppraiser leaked one or more duplicate sdb handles [0x%x].",
      v166);
    TraceLoggingCorrelationVector::TraceLoggingCorrelationVector((TraceLoggingCorrelationVector *)&v198);
    v148 = (volatile signed __int64 *)&v198;
    if ( Windows::Compat::Appraiser::WicaFactory::CorrelationVector )
      v148 = (volatile signed __int64 *)Windows::Compat::Appraiser::WicaFactory::CorrelationVector;
    TraceLoggingCorrelationVector::ToStringImpl(
      (TraceLoggingCorrelationVector *)v148,
      _InterlockedExchangeAdd64(v148 + 17, 0),
      v219);
    if ( Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive )
      UtcThrottle::Throttle((UtcThrottle *)&Windows::Compat::Appraiser::WicaFactory::UtcEventThrottler, v149);
    v150 = qword_1802C9628;
    if ( *(_DWORD *)qword_1802C9628 > 5u
      && (*(_QWORD *)(qword_1802C9628 + 16) & 0x200000000000LL) != 0
      && (*(_QWORD *)(qword_1802C9628 + 24) & 0x200000000000LL) == *(_QWORD *)(qword_1802C9628 + 24) )
    {
      v174 = v219;
      LODWORD(v172) = v147;
      v178[0] = "Windows::Compat::Appraiser::RestoreAppraiser::StartRestoreAppraisal";
      *(_QWORD *)v177 = "onecore\\base\\appcompat\\appraiser\\heads\\restore\\restoreappraiser.cpp";
      *(_DWORD *)v169 = 338;
      v176 = (unsigned __int16 *)&szValueBuf;
      SystemTime = 0;
      GetSystemTime(&SystemTime);
      v197 = SystemTime;
      v175 = &v197;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v150,
        (unsigned int)&unk_1802A0B99,
        v151,
        v152,
        (__int64)&v175,
        (__int64)&v176,
        (__int64)v169,
        (__int64)v177,
        (__int64)v178,
        (__int64)&v172,
        (__int64)&v174);
    }
  }
  Windows::Compat::Appraiser::WriteLog(
    0,
    84,
    (unsigned int)"onecore\\base\\appcompat\\appraiser\\heads\\restore\\restoreappraiser.cpp",
    "Windows::Compat::Appraiser::RestoreAppraiser::StartRestoreAppraisal",
    0,
    (int)"StartRestoreAppraisal end.",
    v166);
  v153 = Windows::Compat::Appraiser::LogToFile::Stop((Windows::Compat::Appraiser::LogToFile *)&v207);
  v154 = v153;
  if ( v153 >= 0 )
  {
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0x157u,
        "onecore\\base\\appcompat\\appraiser\\heads\\restore\\restoreappraiser.cpp",
        "Windows::Compat::Appraiser::RestoreAppraiser::StartRestoreAppraisal",
        "Error stopping file logger: [0x%x].",
        v153);
  }
  else
  {
    LODWORD(v167) = v153;
    LODWORD(dwFlagsb) = v153;
    Windows::Compat::Appraiser::WriteLog(
      (Windows::Compat::Appraiser *)1,
      87,
      (unsigned int)"onecore\\base\\appcompat\\appraiser\\heads\\restore\\restoreappraiser.cpp",
      "Windows::Compat::Appraiser::RestoreAppraiser::StartRestoreAppraisal",
      dwFlagsb,
      (int)"Error stopping file logger: [0x%x].",
      v167);
    TraceLoggingCorrelationVector::TraceLoggingCorrelationVector((TraceLoggingCorrelationVector *)&v198);
    v155 = (volatile signed __int64 *)&v198;
    if ( Windows::Compat::Appraiser::WicaFactory::CorrelationVector )
      v155 = (volatile signed __int64 *)Windows::Compat::Appraiser::WicaFactory::CorrelationVector;
    TraceLoggingCorrelationVector::ToStringImpl(
      (TraceLoggingCorrelationVector *)v155,
      _InterlockedExchangeAdd64(v155 + 17, 0),
      v219);
    if ( Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive )
      UtcThrottle::Throttle((UtcThrottle *)&Windows::Compat::Appraiser::WicaFactory::UtcEventThrottler, v156);
    v157 = qword_1802C9628;
    if ( *(_DWORD *)qword_1802C9628 > 5u
      && (*(_QWORD *)(qword_1802C9628 + 16) & 0x200000000000LL) != 0
      && (*(_QWORD *)(qword_1802C9628 + 24) & 0x200000000000LL) == *(_QWORD *)(qword_1802C9628 + 24) )
    {
      v174 = v219;
      LODWORD(v172) = v154;
      v178[0] = "Windows::Compat::Appraiser::RestoreAppraiser::StartRestoreAppraisal";
      *(_QWORD *)v177 = "onecore\\base\\appcompat\\appraiser\\heads\\restore\\restoreappraiser.cpp";
      *(_DWORD *)v169 = 343;
      v176 = (unsigned __int16 *)&szValueBuf;
      SystemTime = 0;
      GetSystemTime(&SystemTime);
      v197 = SystemTime;
      v175 = &v197;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v157,
        (unsigned int)&unk_1802A0B36,
        v158,
        v159,
        (__int64)&v175,
        (__int64)&v176,
        (__int64)v169,
        (__int64)v177,
        (__int64)v178,
        (__int64)&v172,
        (__int64)&v174);
    }
  }
  Windows::Compat::Appraiser::DataFile::~DataFile((Windows::Compat::Appraiser::DataFile *)v194);
  v160 = pv;
  if ( pv && _InterlockedExchangeAdd((volatile signed __int32 *)pv + 84, 0xFFFFFFFF) == 1 )
  {
    tip2::details::merged_data<_tip_MercuryExtendedAppsRestoreV2Success_attributes,tip2::test_data_basic>::~merged_data<_tip_MercuryExtendedAppsRestoreV2Success_attributes,tip2::test_data_basic>(v160);
    CoTaskMemFree(v160);
  }
  v161 = v186;
  if ( v186 && _InterlockedExchangeAdd((volatile signed __int32 *)v186 + 84, 0xFFFFFFFF) == 1 )
  {
    tip2::details::merged_data<_tip_MercuryRestoreExtendedAppsSuccess_attributes,tip2::test_data_basic>::~merged_data<_tip_MercuryRestoreExtendedAppsSuccess_attributes,tip2::test_data_basic>(v161);
    CoTaskMemFree(v161);
  }
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x18005bc4c  push    rbp
0x18005bc4e  push    rbx
0x18005bc4f  push    rsi
0x18005bc50  push    rdi
0x18005bc51  push    r12
0x18005bc53  push    r13
0x18005bc55  push    r14
0x18005bc57  push    r15
0x18005bc59  lea     rbp, [rsp-2178h]
0x18005bc61  mov     eax, 2278h
0x18005bc66  call    _alloca_probe
0x18005bc6b  sub     rsp, rax
0x18005bc6e  mov     [rbp+21B0h+var_2138], 0FFFFFFFFFFFFFFFEh
0x18005bc76  mov     rax, cs:__security_cookie
0x18005bc7d  xor     rax, rsp
0x18005bc80  mov     [rbp+21B0h+var_50], rax
0x18005bc87  mov     r12b, cl
0x18005bc8a  xor     r15d, r15d
0x18005bc8d  mov     [rsp+22B0h+var_223C], r15b
0x18005bc92  mov     [rbp+21B0h+var_21A8], r15
0x18005bc96  mov     [rbp+21B0h+pv], r15
0x18005bc9a  mov     [rbp+21B0h+var_1650], r15
0x18005bca1  mov     [rbp+21B0h+var_1648], r15
0x18005bca8  mov     [rbp+21B0h+var_1640], r15w
0x18005bcb0  mov     [rbp+21B0h+var_1660], r15
0x18005bcb7  mov     [rbp+21B0h+var_1658], r15b
0x18005bcbe  mov     [rbp+21B0h+var_1438], r15b
0x18005bcc5  lea     rcx, [rbp+21B0h+var_2130]; this
0x18005bccc  call    ??0DataFile@Appraiser@Compat@Windows@@QEAA@XZ; Windows::Compat::Appraiser::DataFile::DataFile(void)
0x18005bcd1  nop
0x18005bcd2  xor     edx, edx; Val
0x18005bcd4  mov     r8d, 400h; Size
0x18005bcda  lea     rcx, [rbp+21B0h+var_F30]; void *
0x18005bce1  call    memset_0
0x18005bce6  mov     edi, 100h
0x18005bceb  mov     r8d, edi; Size
0x18005bcee  xor     edx, edx; Val
0x18005bcf0  lea     rcx, [rbp+21B0h+var_1430]; void *
0x18005bcf7  call    memset_0
0x18005bcfc  mov     r8d, edi; Size
0x18005bcff  xor     edx, edx; Val
0x18005bd01  lea     rcx, [rbp+21B0h+var_1330]; void *
0x18005bd08  call    memset_0
0x18005bd0d  mov     r8d, edi; Size
0x18005bd10  xor     edx, edx; Val
0x18005bd12  lea     rcx, [rbp+21B0h+var_1030]; void *
0x18005bd19  call    memset_0
0x18005bd1e  mov     r8d, edi; Size
0x18005bd21  xor     edx, edx; Val
0x18005bd23  lea     rcx, [rbp+21B0h+var_1230]; void *
0x18005bd2a  call    memset_0
0x18005bd2f  mov     r8d, edi; Size
0x18005bd32  xor     edx, edx; Val
0x18005bd34  lea     rcx, [rbp+21B0h+var_1130]; void *
0x18005bd3b  call    memset_0
0x18005bd40  mov     cs:?Placeholder_Decision_BackupDevice@RestoreAppraiser@Appraiser@Compat@Windows@@0_NA, r15b; bool Windows::Compat::Appraiser::RestoreAppraiser::Placeholder_Decision_BackupDevice
0x18005bd47  mov     ebx, 208h
0x18005bd4c  mov     r8d, ebx; Size
0x18005bd4f  xor     edx, edx; Val
0x18005bd51  lea     rcx, ?OutputDirPath@RestoreAppraiser@Appraiser@Compat@Windows@@0PAGA; void *
0x18005bd58  call    memset_0
0x18005bd5d  xor     edx, edx; Val
0x18005bd5f  lea     r8d, [r15+60h]; Size
0x18005bd63  lea     rcx, [rbp+21B0h+var_21A0]; void *
0x18005bd67  call    memset_0
0x18005bd6c  mov     r8d, ebx; Size
0x18005bd6f  xor     edx, edx; Val
0x18005bd71  lea     rcx, [rbp+21B0h+pszPathIn]; void *
0x18005bd78  call    memset_0
0x18005bd7d  mov     r8d, ebx; Size
0x18005bd80  xor     edx, edx; Val
0x18005bd82  lea     rcx, [rbp+21B0h+pszPathOut]; void *
0x18005bd89  call    memset_0
0x18005bd8e  mov     r8d, ebx; Size
0x18005bd91  xor     edx, edx; Val
0x18005bd93  lea     rcx, [rbp+21B0h+Dst]; void *
0x18005bd9a  call    memset_0
0x18005bd9f  mov     r8d, ebx; Size
0x18005bda2  xor     edx, edx; Val
0x18005bda4  lea     rcx, [rbp+21B0h+pszPath]; void *
0x18005bdab  call    memset_0
0x18005bdb0  mov     r8d, ebx; Size
0x18005bdb3  xor     edx, edx; Val
0x18005bdb5  lea     rcx, [rbp+21B0h+var_680]; void *
0x18005bdbc  call    memset_0
0x18005bdc1  mov     dword ptr [rbp+21B0h+var_21D8], r15d
0x18005bdc5  mov     dword ptr [rsp+22B0h+var_2240], r15d
0x18005bdca  mov     [rbp+21B0h+var_21C8], r15d
0x18005bdce  mov     dword ptr [rbp+21B0h+var_21D8+0Ch], r15d
0x18005bdd2  mov     dword ptr [rbp+21B0h+var_21D8+8], r15d
0x18005bdd6  mov     dword ptr [rbp+21B0h+var_21D8+4], r15d
0x18005bdda  mov     [rbp+21B0h+var_2140], r15
0x18005bdde  mov     [rbp+21B0h+var_21B0], r15
0x18005bde2  mov     cs:?FeatureType@AppraiserSettings@Appraiser@Compat@Windows@@0W4OnesettingsFeatureType@1234@A, 3; Windows::Compat::Appraiser::AppraiserSettings::OnesettingsFeatureType Windows::Compat::Appraiser::AppraiserSettings::FeatureType
0x18005bdec  lea     r13d, [r15+1]
0x18005bdf0  mov     cs:?OnesettingsQueryTries@AppraiserSettings@Appraiser@Compat@Windows@@0_KA, r13; unsigned __int64 Windows::Compat::Appraiser::AppraiserSettings::OnesettingsQueryTries
0x18005bdf7  mov     [rbp+21B0h+var_2228], r15b
0x18005bdfb  mov     rbx, [rbp+21B0h+pv]
0x18005bdff  test    rbx, rbx
0x18005be02  jz      short loc_18005BE3C
0x18005be04  cmp     [rbx+0F8h], r15
0x18005be0b  jnz     short loc_18005BE12
0x18005be0d  test    [rbx+48h], edi
0x18005be10  jz      short loc_18005BE3C
0x18005be12  mov     [rbp+21B0h+pv], r15
0x18005be16  test    rbx, rbx
0x18005be19  jz      short loc_18005BE3C
0x18005be1b  or      eax, 0FFFFFFFFh
0x18005be1e  lock xadd [rbx+150h], eax
0x18005be26  cmp     eax, r13d
0x18005be29  jnz     short loc_18005BE3C
0x18005be2b  mov     rcx, rbx
0x18005be2e  call    ??1?$merged_data@U_tip_MercuryExtendedAppsRestoreV2Success_attributes@@Vtest_data_basic@tip2@@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_MercuryExtendedAppsRestoreV2Success_attributes,tip2::test_data_basic>::~merged_data<_tip_MercuryExtendedAppsRestoreV2Success_attributes,tip2::test_data_basic>(void)
0x18005be33  mov     rcx, rbx; pv
0x18005be36  call    cs:__imp_CoTaskMemFree
0x18005be3c  lea     rcx, [rbp+21B0h+pv]
0x18005be40  call    ?ensure_data@?$tip_test@V?$merged_data@U_tip_MercuryExtendedAppsRestoreV2Success_attributes@@Vtest_data_basic@tip2@@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_MercuryExtendedAppsRestoreV2Success_attributes@@Vtest_data_basic@tip2@@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::tip_test<tip2::details::merged_data<_tip_MercuryExtendedAppsRestoreV2Success_attributes,tip2::test_data_basic>>::ensure_data(void)
0x18005be45  mov     rsi, [rax]
0x18005be48  lea     rbx, [rsi+8]
0x18005be4c  lea     r14, [rbx+0C0h]
0x18005be53  mov     rcx, r14; lpCriticalSection
0x18005be56  call    cs:__imp_EnterCriticalSection
0x18005be5c  mov     [rbp+21B0h+var_1E90], r15
0x18005be63  mov     [rbp+21B0h+var_1E88], r15b
0x18005be6a  lea     rax, [rbp+21B0h+var_1E87]
0x18005be71  mov     [rbp+21B0h+var_1680], rax
0x18005be78  lea     rax, [rbp+21B0h+var_1687]
0x18005be7f  mov     [rbp+21B0h+var_1670], rax
0x18005be86  mov     [rbp+21B0h+var_1E87], 80408040h
0x18005be90  mov     [rbp+21B0h+var_1E83], r15b
0x18005be97  lea     rax, [rbp+21B0h+var_1E82]
0x18005be9e  mov     [rbp+21B0h+var_1678], rax
0x18005bea5  test    dword ptr [rbx+40h], 800h
0x18005beac  jz      short loc_18005BED5
0x18005beae  lea     rdi, [rbx+14h]
0x18005beb2  test    dword ptr [rdi], 8000h
0x18005beb8  jnz     short loc_18005BED9
0x18005beba  mov     r8d, r13d
0x18005bebd  lea     rdx, [rbp+21B0h+var_1E90]
0x18005bec4  mov     rcx, rbx
0x18005bec7  call    ?serialize_data@?$shared_data@$0A@$0A@$00@details@tip2@@AEAAPEBDAEAVwrite_buffer@tson@@W4serialize_options@23@@Z; tip2::details::shared_data<0,0,1>::serialize_data(tson::write_buffer &,tip2::details::serialize_options)
0x18005becc  lea     rsi, [rbx+90h]
0x18005bed3  jmp     short loc_18005BEE3
0x18005bed5  lea     rdi, [rsi+1Ch]
0x18005bed9  mov     rax, r15
0x18005bedc  add     rsi, 98h
0x18005bee3  mov     [rsp+22B0h+var_2288], rsi
0x18005bee8  mov     qword ptr [rsp+22B0h+dwFlags], rax
0x18005beed  mov     r9d, [rdi]
0x18005bef0  mov     r8b, [rbx+20h]
0x18005bef4  mov     ecx, [rbx+10h]
0x18005bef7  call    TestCreate
0x18005befc  mov     rdx, rax
0x18005beff  lea     rcx, [rbx+0F0h]
0x18005bf06  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHTIPTEST__@@P6AXPEAU1@@Z$1?TestClose@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHTIPTEST__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HTIPTEST__ *,void (*)(HTIPTEST__ *),&TestClose(HTIPTEST__ *),wistd::integral_constant<unsigned __int64,0>,HTIPTEST__ *,HTIPTEST__ *,0,std::nullptr_t>>::reset(HTIPTEST__ *)
0x18005bf0b  mov     rsi, r13
0x18005bf0e  mov     [rbx+0B8h], esi
0x18005bf14  mov     rcx, [rbp+21B0h+var_1E90]; pv
0x18005bf1b  test    rcx, rcx
0x18005bf1e  jz      short loc_18005BF26
0x18005bf20  call    cs:__imp_CoTaskMemFree
0x18005bf26  test    r14, r14
0x18005bf29  jz      short loc_18005BF34
0x18005bf2b  mov     rcx, r14; lpCriticalSection
0x18005bf2e  call    cs:__imp_LeaveCriticalSection
0x18005bf34  call    ?DetermineRestoreOutputPath@Utilities@Appraiser@Compat@Windows@@SAJPEAG_K@Z; Windows::Compat::Appraiser::Utilities::DetermineRestoreOutputPath(ushort *,unsigned __int64)
0x18005bf39  lea     rbx, aWindowsCompatA_823; "Windows::Compat::Appraiser::RestoreAppr"...
0x18005bf40  xor     r14d, r14d
0x18005bf43  test    eax, eax
0x18005bf45  jns     short loc_18005BF84
0x18005bf47  mov     dword ptr [rsp+22B0h+var_2280], eax; char *
0x18005bf4b  lea     rcx, aUnableToDeterm; "Unable to determine output path for res"...
0x18005bf52  mov     [rsp+22B0h+var_2288], rcx; int
0x18005bf57  mov     [rsp+22B0h+dwFlags], eax; char *
0x18005bf5b  mov     r9, rbx; char *
0x18005bf5e  lea     r8, aOnecoreBaseApp_68; "onecore\\base\\appcompat\\appraiser\\he"...
0x18005bf65  lea     edx, [r14+4Ah]; bool
0x18005bf69  mov     ecx, esi; this
0x18005bf6b  call    ?WriteLog@Appraiser@Compat@Windows@@YAX_NKPEBD1J1ZZ; Windows::Compat::Appraiser::WriteLog(bool,ulong,char const *,char const *,long,char const *,...)
0x18005bf70  xor     edx, edx; Val
0x18005bf72  mov     r8d, 208h; Size
0x18005bf78  lea     rcx, ?OutputDirPath@RestoreAppraiser@Appraiser@Compat@Windows@@0PAGA; void *
0x18005bf7f  call    memset_0
0x18005bf84  lea     r9, aAppraiserResto_0; "APPRAISER_Restore_EventLog.etl"
0x18005bf8b  lea     r8, ?OutputDirPath@RestoreAppraiser@Appraiser@Compat@Windows@@0PAGA; pszPathIn
0x18005bf92  mov     edx, 104h; cchPathOut
0x18005bf97  lea     rcx, [rbp+21B0h+pszPathOut]; pszPathOut
0x18005bf9e  call    PathCchCombineEx
0x18005bfa3  mov     edi, eax
0x18005bfa5  mov     dword ptr [rsp+22B0h+var_2238], eax
0x18005bfa9  mov     r13b, 54h ; 'T'
0x18005bfac  lea     r15, aTipreasonv2Res; "TipReasonV2::RestoreEventSent"
0x18005bfb3  test    eax, eax
0x18005bfb5  jns     loc_18005C263
0x18005bfbb  lea     r9, aErrorCreatingE_0; "Error creating event log path: [0x%x]."
0x18005bfc2  mov     edx, 53h ; 'S'; bool
0x18005bfc7  lea     r8, aOnecoreBaseApp_68; "onecore\\base\\appcompat\\appraiser\\he"...
0x18005bfce  mov     dword ptr [rsp+22B0h+var_2280], edi; char *
0x18005bfd2  mov     [rsp+22B0h+var_2288], r9; int
0x18005bfd7  mov     r9, rbx; char *
0x18005bfda  mov     [rsp+22B0h+dwFlags], edi; char *
0x18005bfde  mov     ecx, esi; this
0x18005bfe0  call    ?WriteLog@Appraiser@Compat@Windows@@YAX_NKPEBD1J1ZZ; Windows::Compat::Appraiser::WriteLog(bool,ulong,char const *,char const *,long,char const *,...)
0x18005bfe5  lea     r12, aWindowsCompatA_823; "Windows::Compat::Appraiser::RestoreAppr"...
0x18005bfec  mov     edx, edi
0x18005bfee  shr     edx, 1Fh
0x18005bff1  lea     rax, aTipreasonv2Fun; "TipReasonV2::FunctionFailure"
0x18005bff8  mov     rbx, rax
0x18005bffb  mov     cl, r13b
0x18005bffe  add     rax, rsi
0x18005c001  cmp     cl, 3Ah ; ':'
0x18005c004  jnz     short loc_18005C009
0x18005c006  mov     rbx, rax
0x18005c009  mov     cl, [rax]
0x18005c00b  test    cl, cl
0x18005c00d  jnz     short loc_18005BFFE
0x18005c00f  test    dl, dl
0x18005c011  jz      short loc_18005C082
0x18005c013  lea     rcx, [rbp+21B0h+pv]
0x18005c017  call    ?ensure_data@?$tip_test@V?$merged_data@U_tip_MercuryExtendedAppsRestoreV2Success_attributes@@Vtest_data_basic@tip2@@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_MercuryExtendedAppsRestoreV2Success_attributes@@Vtest_data_basic@tip2@@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::tip_test<tip2::details::merged_data<_tip_MercuryExtendedAppsRestoreV2Success_attributes,tip2::test_data_basic>>::ensure_data(void)
0x18005c01c  mov     rsi, [rax]
0x18005c01f  lea     rcx, [rsi+0C8h]; lpCriticalSection
0x18005c026  call    cs:__imp_EnterCriticalSection
0x18005c02c  inc     dword ptr [rsi+0F0h]
0x18005c032  test    dword ptr [rsi+48h], 100h
0x18005c039  jnz     short loc_18005C079
0x18005c03b  mov     edx, 2
0x18005c040  mov     r8, rbx
0x18005c043  lea     rcx, [rsi+8]
0x18005c047  call    ?get_or_add_flag_under_lock@?$shared_data@$0A@$0A@$00@details@tip2@@AEAAPEAUtest_flag@3@GPEBD@Z; tip2::details::shared_data<0,0,1>::get_or_add_flag_under_lock(ushort,char const *)
0x18005c04c  mov     r14, rax
0x18005c04f  test    rax, rax
0x18005c052  jz      short loc_18005C076
0x18005c054  lea     rbx, [rax+10h]
0x18005c058  mov     rcx, rbx; pvar
0x18005c05b  call    cs:__imp_PropVariantClear
0x18005c061  xorps   xmm0, xmm0
0x18005c064  xor     eax, eax
0x18005c066  movups  xmmword ptr [rbx], xmm0
0x18005c069  mov     [rbx+10h], rax
0x18005c06d  mov     word ptr [rbx], 3
0x18005c072  mov     [r14+18h], edi
0x18005c076  xor     r14d, r14d
0x18005c079  lea     rcx, [rsi+8]
0x18005c07d  call    ?end_update@?$shared_data@$0A@$0A@$00@details@tip2@@AEAAXXZ; tip2::details::shared_data<0,0,1>::end_update(void)
0x18005c082  call    ?IsMachineInSecurityMode@Utilities@Appraiser@Compat@Windows@@SA_NXZ; Windows::Compat::Appraiser::Utilities::IsMachineInSecurityMode(void)
0x18005c087  test    al, al
0x18005c089  jnz     loc_18005D0E2
0x18005c08f  cmp     [rbp+21B0h+var_2228], r14b
0x18005c093  jnz     loc_18005D0E2
0x18005c099  lea     rcx, [rbp+21B0h+var_1E90]; this
0x18005c0a0  call    ??0TraceLoggingCorrelationVector@@QEAA@XZ; TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(void)
0x18005c0a5  lea     rcx, [rbp+21B0h+var_1E90]
0x18005c0ac  mov     rax, cs:?CorrelationVector@WicaFactory@Appraiser@Compat@Windows@@2PEAVTraceLoggingCorrelationVector@@EA; TraceLoggingCorrelationVector * Windows::Compat::Appraiser::WicaFactory::CorrelationVector
0x18005c0b3  test    rax, rax
0x18005c0b6  cmovnz  rcx, rax; this
0x18005c0ba  mov     rdx, r14
0x18005c0bd  lock xadd [rcx+88h], rdx; unsigned __int64
0x18005c0c6  lea     r8, [rbp+21B0h+var_B30]; char *
0x18005c0cd  call    ?ToStringImpl@TraceLoggingCorrelationVector@@AEAA_N_KPEAD@Z; TraceLoggingCorrelationVector::ToStringImpl(unsigned __int64,char *)
0x18005c0d2  cmp     cs:?UtcEventThrottlerActive@WicaFactory@Appraiser@Compat@Windows@@2_NA, r14b; bool Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive
0x18005c0d9  jz      short loc_18005C0E7
0x18005c0db  lea     rcx, ?UtcEventThrottler@WicaFactory@Appraiser@Compat@Windows@@2VUtcThrottle@@A; this
0x18005c0e2  call    ?Throttle@UtcThrottle@@QEAA_NPEAPEAX@Z; UtcThrottle::Throttle(void * *)
0x18005c0e7  mov     rbx, cs:qword_1802C9560
0x18005c0ee  mov     eax, [rbx]
0x18005c0f0  cmp     eax, 5
0x18005c0f3  jbe     loc_18005C200
0x18005c0f9  mov     rcx, [rbx+18h]; unsigned __int16 *
0x18005c0fd  mov     rax, [rbx+10h]
0x18005c101  mov     rdx, 800000000000h; unsigned __int64
0x18005c10b  test    rdx, rax
0x18005c10e  jz      loc_18005C200
0x18005c114  mov     rax, rcx
0x18005c117  and     rax, rdx
0x18005c11a  cmp     rax, rcx
0x18005c11d  jnz     loc_18005C200
0x18005c123  lea     rax, [rbp+21B0h+var_B30]
0x18005c12a  mov     [rbp+21B0h+var_2220], rax
0x18005c12e  mov     [rbp+21B0h+var_2200], 1000000h
0x18005c136  mov     dword ptr [rbp+21B0h+var_2230], r14d
0x18005c13a  mov     dword ptr [rsp+22B0h+var_2240], edi
0x18005c13e  lea     rax, aStartrestoreap_1; "StartRestoreAppraisal"
0x18005c145  mov     qword ptr [rbp+21B0h+var_2208], rax
0x18005c149  cmp     r14w, word ptr cs:?AppraiserBranchBuffer@WicaFactory@Appraiser@Compat@Windows@@0PAGA; ushort near * Windows::Compat::Appraiser::WicaFactory::AppraiserBranchBuffer
0x18005c151  jnz     short loc_18005C158
0x18005c153  call    ?GetAppraiserBranch@Utilities@Appraiser@Compat@Windows@@SAXPEAG_K@Z; Windows::Compat::Appraiser::Utilities::GetAppraiserBranch(ushort *,unsigned __int64)
0x18005c158  lea     rax, ?AppraiserBranchBuffer@WicaFactory@Appraiser@Compat@Windows@@0PAGA; ushort near * Windows::Compat::Appraiser::WicaFactory::AppraiserBranchBuffer
0x18005c15f  mov     [rbp+21B0h+var_2210], rax
0x18005c163  call    ?AppraiserVersion@WicaFactory@Appraiser@Compat@Windows@@SAPEBGXZ; Windows::Compat::Appraiser::WicaFactory::AppraiserVersion(void)
0x18005c168  mov     [rbp+21B0h+var_2218], rax
0x18005c16c  lea     rax, szValueBuf
0x18005c173  mov     [rbp+21B0h+var_21B8], rax
0x18005c177  xorps   xmm0, xmm0
0x18005c17a  movups  xmmword ptr [rbp+21B0h+SystemTime.wYear], xmm0
0x18005c17e  lea     rcx, [rbp+21B0h+SystemTime]; lpSystemTime
0x18005c182  call    cs:__imp_GetSystemTime
0x18005c188  movaps  xmm0, xmmword ptr [rbp+21B0h+SystemTime.wYear]
0x18005c18c  movdqa  [rbp+21B0h+var_1EA0], xmm0
0x18005c194  lea     rax, [rbp+21B0h+var_1EA0]
  ... truncated ...
```
