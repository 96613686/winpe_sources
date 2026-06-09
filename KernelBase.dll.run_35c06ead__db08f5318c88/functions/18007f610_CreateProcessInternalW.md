# CreateProcessInternalW

- ea: `0x18007f610`
- end: `0x180087e8b`
- name: `CreateProcessInternalW`
- size: `34939`
- prototype: `__int64 __fastcall(void *, const WCHAR *, const wchar_t *, __int64, __int64, int, unsigned int, WCHAR *, WCHAR *, __int64, __int64)`
- caller_count: `5`
- callee_count: `63`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18007de08`
- `0x18007f000`
- `0x18007f510`
- `0x18007f590`
- `0x180111c44`

## callees

- `0x1800134a0`
- `0x180033d70`
- `0x180066d28`
- `0x1800673dc`
- `0x18006cdc0`
- `0x180077680`
- `0x18007f610`
- `0x18009ce5c`
- `0x1800c5490`
- `0x1800c7038`
- `0x1800c8680`
- `0x1800cc8a0`
- `0x1800d9c50`
- `0x1800dfd40`
- `0x1800e19d0`
- `0x1800e3bc0`
- `0x1800e5560`
- `0x1800e7570`
- `0x1800ec878`
- `0x1800f5198`
- `0x1800f56c8`
- `0x1800fed54`
- `0x180100d10`
- `0x1801045b0`
- `0x18010a36c`
- `0x18010cbf0`
- `0x18010eaa0`
- `0x180110728`
- `0x1801120ec`
- `0x180124b90`
- `0x1801256a0`
- `0x180125e80`
- `0x180126ed8`
- `0x1801271e8`
- `0x180127670`
- `0x18012d080`
- `0x18012d119`
- `0x18012fce0`
- `0x180130274`
- `0x1801302c8`
- `0x18013031c`
- `0x180130370`
- `0x180131110`
- `0x18017d5b0`
- `0x18017d680`
- `0x1801800e8`
- `0x180180190`
- `0x1801802c4`
- `0x1801803e4`
- `0x18018059c`

## import_xrefs

- `ntdll!RtlFreeUnicodeString` at `0x180080638`
- `ntdll!RtlFreeUnicodeString` at `0x180086f0b`
- `ntdll!RtlFreeUnicodeString` at `0x18008779d`
- `ntdll!RtlFreeUnicodeString` at `0x180189f89`
- `ntdll!RtlFreeUnicodeString` at `0x18018a7d3`
- `ntdll!RtlFreeUnicodeString` at `0x180080638`
- `ntdll!RtlFreeUnicodeString` at `0x180086f0b`
- `ntdll!RtlFreeUnicodeString` at `0x18008779d`
- `ntdll!RtlFreeUnicodeString` at `0x180189f89`
- `ntdll!RtlFreeUnicodeString` at `0x18018a7d3`
- `ntdll!RtlInitUnicodeString` at `0x18008101a`
- `ntdll!RtlInitUnicodeString` at `0x1800835ca`
- `ntdll!RtlInitUnicodeString` at `0x180083606`
- `ntdll!RtlInitUnicodeString` at `0x180083d36`
- `ntdll!RtlInitUnicodeString` at `0x180083f01`
- `ntdll!RtlInitUnicodeString` at `0x180083f41`
- `ntdll!RtlInitUnicodeString` at `0x1800851db`
- `ntdll!RtlInitUnicodeString` at `0x180085208`
- `ntdll!RtlInitUnicodeString` at `0x180085608`
- `ntdll!RtlInitUnicodeString` at `0x18008101a`
- `ntdll!RtlInitUnicodeString` at `0x1800835ca`
- `ntdll!RtlInitUnicodeString` at `0x180083606`
- `ntdll!RtlInitUnicodeString` at `0x180083d36`
- `ntdll!RtlInitUnicodeString` at `0x180083f01`
- `ntdll!RtlInitUnicodeString` at `0x180083f41`
- `ntdll!RtlInitUnicodeString` at `0x1800851db`
- `ntdll!RtlInitUnicodeString` at `0x180085208`
- `ntdll!RtlInitUnicodeString` at `0x180085608`
- `ntdll!wcslen` at `0x180080b7a`
- `ntdll!wcslen` at `0x180083c1b`
- `ntdll!wcslen` at `0x180083c2c`
- `ntdll!wcslen` at `0x180083ca1`
- `ntdll!wcslen` at `0x180083cb1`
- `ntdll!wcslen` at `0x180083cc1`
- `ntdll!wcslen` at `0x180083d4b`
- `ntdll!wcslen` at `0x180080b7a`
- `ntdll!wcslen` at `0x180083c1b`
- `ntdll!wcslen` at `0x180083c2c`
- `ntdll!wcslen` at `0x180083ca1`
- `ntdll!wcslen` at `0x180083cb1`
- `ntdll!wcslen` at `0x180083cc1`
- `ntdll!wcslen` at `0x180083d4b`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x180080c37`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x180080c37`
- `ntdll!_wcsnicmp` at `0x180083747`
- `ntdll!_wcsnicmp` at `0x180083762`
- `ntdll!_wcsnicmp` at `0x180083747`
- `ntdll!_wcsnicmp` at `0x180083762`
- `ntdll!RtlSetLastWin32Error` at `0x18007fb8f`
- `ntdll!RtlSetLastWin32Error` at `0x180080423`
- `ntdll!RtlSetLastWin32Error` at `0x18007fb8f`
- `ntdll!RtlSetLastWin32Error` at `0x180080423`
- `ntdll!NtWaitForSingleObject` at `0x180080765`
- `ntdll!NtWaitForSingleObject` at `0x180087747`
- `ntdll!NtWaitForSingleObject` at `0x18018a780`
- `ntdll!NtWaitForSingleObject` at `0x180080765`
- `ntdll!NtWaitForSingleObject` at `0x180087747`
- `ntdll!NtWaitForSingleObject` at `0x18018a780`
- `ntdll!RtlIsDosDeviceName_U` at `0x180083f7e`
- `ntdll!RtlIsDosDeviceName_U` at `0x180083f7e`
- `ntdll!RtlDetermineDosPathNameType_U` at `0x180080c7a`
- `ntdll!RtlDetermineDosPathNameType_U` at `0x180080c7a`
- `ntdll!NtTerminateProcess` at `0x180080752`
- `ntdll!NtTerminateProcess` at `0x180087734`
- `ntdll!NtTerminateProcess` at `0x18018a76e`
- `ntdll!NtTerminateProcess` at `0x180080752`
- `ntdll!NtTerminateProcess` at `0x180087734`
- `ntdll!NtTerminateProcess` at `0x18018a76e`
- `ntdll!NtQueryInformationToken` at `0x180084610`
- `ntdll!NtQueryInformationToken` at `0x180084610`
- `ntdll!CsrClientCallServer` at `0x18008470c`
- `ntdll!CsrClientCallServer` at `0x18008470c`
- `ntdll!CsrFreeCaptureBuffer` at `0x18008084f`
- `ntdll!CsrFreeCaptureBuffer` at `0x180087845`
- `ntdll!CsrFreeCaptureBuffer` at `0x18018a872`
- `ntdll!CsrFreeCaptureBuffer` at `0x18008084f`
- `ntdll!CsrFreeCaptureBuffer` at `0x180087845`
- `ntdll!CsrFreeCaptureBuffer` at `0x18018a872`
- `ntdll!RtlInitUnicodeStringEx` at `0x180080c5b`
- `ntdll!RtlInitUnicodeStringEx` at `0x180080c5b`
- `ntdll!NtClose` at `0x180080683`
- `ntdll!NtClose` at `0x18008069e`
- `ntdll!NtClose` at `0x18008070f`
- `ntdll!NtClose` at `0x180080773`
- `ntdll!NtClose` at `0x18008078e`
- `ntdll!NtClose` at `0x180083255`
- `ntdll!NtClose` at `0x1800833a3`
- `ntdll!NtClose` at `0x180083446`
- `ntdll!NtClose` at `0x1800834b2`
- `ntdll!NtClose` at `0x180083627`
- `ntdll!NtClose` at `0x1800855d9`
- `ntdll!NtClose` at `0x180086dc3`
- `ntdll!NtClose` at `0x1800874f1`
- `ntdll!NtClose` at `0x180087507`
- `ntdll!NtClose` at `0x1800876e1`
- `ntdll!NtClose` at `0x1800876f7`
- `ntdll!NtClose` at `0x180087755`
- `ntdll!NtClose` at `0x180087768`
- `ntdll!NtClose` at `0x18008781f`
- `ntdll!NtClose` at `0x180189e8d`
- `ntdll!NtClose` at `0x180189e9a`
- `ntdll!NtClose` at `0x18018a553`
- `ntdll!NtClose` at `0x18018a566`
- `ntdll!NtClose` at `0x18018a723`
- `ntdll!NtClose` at `0x18018a736`
- `ntdll!NtClose` at `0x18018a78d`
- `ntdll!NtClose` at `0x18018a7a0`
- `ntdll!NtClose` at `0x18018a84c`
- `ntdll!NtClose` at `0x180080683`
- `ntdll!NtClose` at `0x18008069e`
- `ntdll!NtClose` at `0x18008070f`
- `ntdll!NtClose` at `0x180080773`
- `ntdll!NtClose` at `0x18008078e`
- `ntdll!NtClose` at `0x180083255`
- `ntdll!NtClose` at `0x1800833a3`
- `ntdll!NtClose` at `0x180083446`
- `ntdll!NtClose` at `0x1800834b2`
- `ntdll!NtClose` at `0x180083627`
- `ntdll!NtClose` at `0x1800855d9`
- `ntdll!NtClose` at `0x180086dc3`
- `ntdll!NtClose` at `0x1800874f1`
- `ntdll!NtClose` at `0x180087507`
- `ntdll!NtClose` at `0x1800876e1`
- `ntdll!NtClose` at `0x1800876f7`
- `ntdll!NtClose` at `0x180087755`
- `ntdll!NtClose` at `0x180087768`
- `ntdll!NtClose` at `0x18008781f`
- `ntdll!NtClose` at `0x180189e8d`
- `ntdll!NtClose` at `0x180189e9a`
- `ntdll!NtClose` at `0x18018a553`
- `ntdll!NtClose` at `0x18018a566`
- `ntdll!NtClose` at `0x18018a723`
- `ntdll!NtClose` at `0x18018a736`
- `ntdll!NtClose` at `0x18018a78d`
- `ntdll!NtClose` at `0x18018a7a0`
- `ntdll!NtClose` at `0x18018a84c`
- `ntdll!NtQueryInformationProcess` at `0x18008427f`
- `ntdll!NtQueryInformationProcess` at `0x18008427f`
- `ntdll!RtlFreeHeap` at `0x1800805ff`
- `ntdll!RtlFreeHeap` at `0x180080622`
- `ntdll!RtlFreeHeap` at `0x180080665`
- `ntdll!RtlFreeHeap` at `0x180081073`
- `ntdll!RtlFreeHeap` at `0x180083511`
- `ntdll!RtlFreeHeap` at `0x180086ec1`
- `ntdll!RtlFreeHeap` at `0x180086efd`
- `ntdll!RtlFreeHeap` at `0x180087673`
- `ntdll!RtlFreeHeap` at `0x18008768e`
- `ntdll!RtlFreeHeap` at `0x1800876b0`
- `ntdll!RtlFreeHeap` at `0x1800876cb`
- `ntdll!RtlFreeHeap` at `0x180087865`
- `ntdll!RtlFreeHeap` at `0x18008787d`
- `ntdll!RtlFreeHeap` at `0x180189f2f`
- `ntdll!RtlFreeHeap` at `0x180189f71`
- `ntdll!RtlFreeHeap` at `0x18018a6be`
- `ntdll!RtlFreeHeap` at `0x18018a6d6`
- `ntdll!RtlFreeHeap` at `0x18018a6f8`
- `ntdll!RtlFreeHeap` at `0x18018a710`
- `ntdll!RtlFreeHeap` at `0x18018a894`
- `ntdll!RtlFreeHeap` at `0x18018a8ac`
- `ntdll!RtlFreeHeap` at `0x1800805ff`
- `ntdll!RtlFreeHeap` at `0x180080622`
- `ntdll!RtlFreeHeap` at `0x180080665`
- `ntdll!RtlFreeHeap` at `0x180081073`
- `ntdll!RtlFreeHeap` at `0x180083511`
- `ntdll!RtlFreeHeap` at `0x180086ec1`
- `ntdll!RtlFreeHeap` at `0x180086efd`
- `ntdll!RtlFreeHeap` at `0x180087673`
- `ntdll!RtlFreeHeap` at `0x18008768e`
- `ntdll!RtlFreeHeap` at `0x1800876b0`
- `ntdll!RtlFreeHeap` at `0x1800876cb`
- `ntdll!RtlFreeHeap` at `0x180087865`
- `ntdll!RtlFreeHeap` at `0x18008787d`
- `ntdll!RtlFreeHeap` at `0x180189f2f`
- `ntdll!RtlFreeHeap` at `0x180189f71`
- `ntdll!RtlFreeHeap` at `0x18018a6be`
- `ntdll!RtlFreeHeap` at `0x18018a6d6`
- `ntdll!RtlFreeHeap` at `0x18018a6f8`
- `ntdll!RtlFreeHeap` at `0x18018a710`
- `ntdll!RtlFreeHeap` at `0x18018a894`
- `ntdll!RtlFreeHeap` at `0x18018a8ac`
- `ntdll!RtlImageNtHeader` at `0x1800845c0`
- `ntdll!RtlImageNtHeader` at `0x1800845c0`
- `ntdll!RtlDestroyProcessParameters` at `0x1800833b3`
- `ntdll!RtlDestroyProcessParameters` at `0x1800833b3`
- `ntdll!NtOpenProcessToken` at `0x18008551e`
- `ntdll!NtOpenProcessToken` at `0x18008551e`
- `ntdll!NtOpenThreadToken` at `0x18008321e`
- `ntdll!NtOpenThreadToken` at `0x1800832ac`
- `ntdll!NtOpenThreadToken` at `0x18008321e`
- `ntdll!NtOpenThreadToken` at `0x1800832ac`
- `ntdll!RtlReleasePath` at `0x1800809dd`
- `ntdll!RtlReleasePath` at `0x180087832`
- `ntdll!RtlReleasePath` at `0x18018a85f`
- `ntdll!RtlReleasePath` at `0x1800809dd`
- `ntdll!RtlReleasePath` at `0x180087832`
- `ntdll!RtlReleasePath` at `0x18018a85f`
- `ntdll!NtWriteVirtualMemory` at `0x1800868fe`
- `ntdll!NtWriteVirtualMemory` at `0x180086935`
- `ntdll!NtWriteVirtualMemory` at `0x18008698c`
- `ntdll!NtWriteVirtualMemory` at `0x1800868fe`

## string_xrefs

- `0x18007f7e9`: `ntdll.dll`
- `0x180083800`: `\system32\cmd.exe`
- `0x1800837bd`: `ComSpec`

## pseudocode

```c
__int64 __fastcall CreateProcessInternalW(
        void *a1,
        const WCHAR *a2,
        const wchar_t *a3,
        __int64 a4,
        __int64 a5,
        int a6,
        unsigned int a7,
        WCHAR *a8,
        WCHAR *a9,
        __int64 a10,
        __int64 a11)
{
  __int64 v14; // r15
  unsigned int v15; // r14d
  __int64 v16; // rcx
  __int64 v17; // rbx
  PVOID ProcessHeap; // r12
  __int64 v19; // rdx
  HANDLE ThreadDebugObject; // rcx
  char v21; // al
  NTSTATUS v22; // eax
  wchar_t *v23; // r14
  __int64 v24; // rax
  __int64 v25; // r15
  int v26; // eax
  __m128i v27; // xmm2
  __int64 v28; // rcx
  unsigned int ProcessInternalW; // ebx
  _DWORD *v30; // rbx
  int ExePath; // eax
  int v32; // edx
  bool v33; // zf
  int v34; // edx
  __int64 v35; // rcx
  WCHAR *v36; // rbx
  PVOID Heap; // r15
  NTSTATUS FullPathName_UEx; // eax
  ULONG v39; // ecx
  unsigned int v40; // eax
  const WCHAR *v41; // r15
  const wchar_t *v42; // rcx
  WCHAR *v43; // rdx
  HANDLE v44; // r13
  void *v45; // rbx
  const wchar_t *v46; // r13
  __int64 v47; // rdx
  __int64 v48; // rax
  HANDLE v49; // rcx
  __int64 v50; // rdx
  __int64 v51; // rcx
  char v52; // r15
  char v53; // r13
  ULONG LastErrorValue; // r14d
  const WCHAR *v55; // rax
  STRSAFE_LPCWSTR v56; // rdx
  STRSAFE_LPCWSTR v57; // rbx
  char v58; // r12
  ULONG v59; // eax
  __int64 v60; // rcx
  DWORD FileAttributesW; // eax
  const wchar_t *v62; // rcx
  SIZE_T v63; // rbx
  wchar_t *v64; // rax
  wchar_t *v65; // r13
  int v66; // ebx
  RTL_PATH_TYPE v67; // eax
  struct _PEB *v68; // r14
  __int64 v69; // rdx
  _WORD *v70; // rcx
  int IsEnabledDeviceUsageNoInline; // eax
  int v72; // ecx
  __int64 v73; // rax
  WCHAR *v74; // r14
  __int64 v75; // rdx
  HANDLE v76; // rbx
  __int64 v77; // rdx
  __int64 v78; // rcx
  WCHAR *v79; // rax
  int v80; // eax
  DWORD v81; // eax
  unsigned int v82; // eax
  int v83; // ecx
  _WORD *v84; // rcx
  int v85; // r12d
  __int64 v86; // rdx
  __int64 v87; // rcx
  char v88; // r11
  char v89; // r9
  char v90; // r14
  __int64 v91; // rbx
  int v92; // eax
  bool v93; // al
  char v94; // r10
  int v95; // eax
  char v96; // al
  char v97; // r10
  int v98; // eax
  char v99; // al
  char v100; // r10
  int v101; // eax
  char v102; // al
  char v103; // r10
  int v104; // eax
  char v105; // al
  char v106; // r10
  int v107; // eax
  char v108; // al
  char v109; // r10
  int v110; // eax
  char v111; // al
  char v112; // r10
  int v113; // eax
  char v114; // al
  int v115; // eax
  bool v116; // al
  char v117; // r10
  int v118; // eax
  char v119; // al
  char v120; // r10
  int v121; // eax
  char v122; // al
  char v123; // r10
  int v124; // eax
  char v125; // al
  char v126; // r10
  int v127; // eax
  char v128; // al
  char v129; // r10
  int v130; // eax
  char v131; // al
  char v132; // r10
  int v133; // eax
  char v134; // al
  char v135; // r10
  int v136; // eax
  char v137; // al
  int v138; // eax
  bool v139; // al
  char v140; // cl
  int v141; // eax
  char v142; // al
  char v143; // r9
  char v144; // r14
  char v145; // r8
  char v146; // r10
  __int64 v147; // rax
  unsigned int v148; // eax
  int v149; // eax
  __int16 v150; // ax
  char v151; // cl
  char v152; // dl
  char v153; // dl
  char v154; // al
  char v155; // dl
  char v156; // dl
  char v157; // cl
  __int64 v158; // r8
  __int64 v159; // rdx
  struct _RTL_USER_PROCESS_PARAMETERS *v160; // r14
  __int64 Length; // rbx
  PVOID v162; // rax
  int v163; // eax
  HANDLE v164; // rcx
  int v165; // eax
  BOOL v166; // eax
  __int64 v167; // rdx
  __int64 v168; // rcx
  __int64 v169; // rcx
  HANDLE v170; // rbx
  _WORD *v171; // r14
  int v172; // eax
  void *v173; // rax
  __int64 v174; // rcx
  WCHAR *v175; // r14
  WCHAR *v176; // rax
  WCHAR *v177; // rbx
  DWORD EnvironmentVariableW; // eax
  char v179; // r14
  char v180; // al
  HANDLE v181; // r14
  __int64 v182; // rdx
  __int64 v183; // rcx
  int v184; // eax
  const wchar_t *v185; // rcx
  int v186; // ebx
  SIZE_T v187; // rbx
  wchar_t *v188; // rax
  wchar_t *v189; // r15
  const wchar_t *v190; // r8
  int v191; // ebx
  int v192; // ebx
  wchar_t *v193; // rax
  SIZE_T v194; // rbx
  wchar_t *v195; // rax
  int AppExecutionAliasInfoForExecutable; // r14d
  int v197; // eax
  void *v198; // rax
  HANDLE v199; // rbx
  int v200; // r12d
  int v201; // eax
  __int64 v202; // rdx
  __int64 v203; // rcx
  int v204; // eax
  __int64 v205; // rdx
  __int64 v206; // rcx
  __int64 v207; // r13
  char v208; // al
  HANDLE v209; // r14
  __int64 v210; // rdx
  __int64 v211; // rcx
  char v212; // al
  __int64 v213; // rdx
  HMODULE ModuleHandleA; // rax
  PIMAGE_NT_HEADERS v215; // rax
  HANDLE v216; // rbx
  unsigned int v217; // eax
  __int64 ConsoleHost; // rcx
  __int64 v219; // rdx
  __int64 v220; // rcx
  __int64 v221; // rdx
  __int64 v222; // rcx
  int v223; // ebx
  int v224; // eax
  __int64 v225; // rcx
  HANDLE v226; // rax
  int EAAumidIfPresent; // ebx
  const WCHAR *v228; // rdx
  __int16 *v229; // rbx
  __int64 v230; // rcx
  LONG PackageActivationTokenForSxS3; // eax
  BOOL v232; // ebx
  LONG PackageFullNameFromToken; // ebx
  WCHAR *v234; // rdx
  char *v235; // rax
  char *v236; // rdx
  WCHAR *v237; // rdx
  char v238; // al
  NTSTATUS v239; // eax
  __int64 v240; // rdx
  unsigned __int64 v241; // rcx
  unsigned __int64 v242; // r14
  HANDLE v243; // r15
  unsigned __int64 i; // rbx
  LONG v245; // ebx
  int v246; // edx
  __int64 v247; // rax
  char *v248; // rdx
  unsigned __int8 v249; // r13
  char v250; // r11
  char v251; // r10
  __int64 v252; // r14
  int v253; // eax
  bool v254; // al
  char v255; // cl
  int v256; // eax
  char v257; // al
  char v258; // cl
  int v259; // eax
  char v260; // al
  char v261; // cl
  int v262; // eax
  char v263; // al
  char v264; // cl
  int v265; // eax
  char v266; // al
  char v267; // cl
  int v268; // eax
  char v269; // al
  char v270; // cl
  int v271; // eax
  char v272; // al
  char v273; // cl
  int v274; // eax
  char v275; // al
  int v276; // eax
  bool v277; // al
  char v278; // r9
  int v279; // eax
  char v280; // al
  char v281; // r9
  int v282; // eax
  char v283; // al
  char v284; // r9
  int v285; // eax
  char v286; // al
  char v287; // r9
  int v288; // eax
  char v289; // al
  char v290; // r9
  int v291; // eax
  char v292; // al
  char v293; // r9
  int v294; // eax
  char v295; // al
  char v296; // r9
  int v297; // eax
  char v298; // al
  int v299; // eax
  bool v300; // al
  char v301; // r9
  int v302; // eax
  char v303; // al
  char v304; // r9
  int v305; // eax
  char v306; // al
  char v307; // r9
  int v308; // eax
  char v309; // al
  char v310; // r9
  int v311; // eax
  char v312; // al
  int v313; // eax
  int v314; // edx
  ULONG v315; // eax
  __int64 v316; // r8
  __int64 v317; // r15
  PVOID v318; // r14
  __int64 v319; // r12
  ULONG v320; // r15d
  __int64 v321; // rdx
  __int64 v322; // rcx
  __int64 v323; // r12
  const WCHAR *v324; // rax
  char *v325; // rax
  __int16 *v326; // rdx
  const WCHAR *v327; // rax
  PVOID v328; // r12
  HANDLE v329; // rcx
  __int64 v330; // rdx
  __int64 v331; // rcx
  __int64 v332; // r12
  const WCHAR *v333; // rax
  char *v334; // rax
  __int16 *v335; // rdx
  const WCHAR *v336; // rax
  __int64 v338; // [rsp+0h] [rbp-2278h] BYREF
  RTL_PATH_TYPE *PathType; // [rsp+30h] [rbp-2248h]
  PSIZE_T LengthNeeded; // [rsp+38h] [rbp-2240h]
  __int64 v341; // [rsp+48h] [rbp-2230h]
  __int64 v342; // [rsp+50h] [rbp-2228h]
  int v343; // [rsp+C0h] [rbp-21B8h]
  int v344; // [rsp+D0h] [rbp-21A8h]
  unsigned int v345; // [rsp+D4h] [rbp-21A4h] BYREF
  PVOID HeapHandle; // [rsp+D8h] [rbp-21A0h]
  NTSTATUS v347; // [rsp+E0h] [rbp-2198h]
  __int64 v348; // [rsp+E8h] [rbp-2190h]
  unsigned int v349; // [rsp+F0h] [rbp-2188h] BYREF
  int v350; // [rsp+F8h] [rbp-2180h] BYREF
  char v351; // [rsp+FCh] [rbp-217Ch]
  char v352; // [rsp+FDh] [rbp-217Bh]
  char v353; // [rsp+FEh] [rbp-217Ah]
  char v354; // [rsp+FFh] [rbp-2179h]
  char v355; // [rsp+100h] [rbp-2178h]
  HANDLE Process; // [rsp+108h] [rbp-2170h] BYREF
  __int64 v357; // [rsp+110h] [rbp-2168h] BYREF
  char v358; // [rsp+118h] [rbp-2160h]
  __int128 v359; // [rsp+120h] [rbp-2158h]
  __int128 v360; // [rsp+130h] [rbp-2148h]
  __int128 v361; // [rsp+140h] [rbp-2138h]
  STRSAFE_LPCWSTR pszSrc; // [rsp+150h] [rbp-2128h] BYREF
  LPCWSTR lpFileName; // [rsp+158h] [rbp-2120h] BYREF
  bool v364; // [rsp+160h] [rbp-2118h] BYREF
  char v365; // [rsp+161h] [rbp-2117h] BYREF
  char v366; // [rsp+162h] [rbp-2116h] BYREF
  bool v367; // [rsp+163h] [rbp-2115h] BYREF
  bool v368; // [rsp+164h] [rbp-2114h] BYREF
  bool v369; // [rsp+165h] [rbp-2113h] BYREF
  bool v370; // [rsp+166h] [rbp-2112h] BYREF
  bool v371; // [rsp+167h] [rbp-2111h] BYREF
  bool v372; // [rsp+168h] [rbp-2110h] BYREF
  bool v373; // [rsp+169h] [rbp-210Fh] BYREF
  bool v374; // [rsp+16Ah] [rbp-210Eh] BYREF
  char v375; // [rsp+16Bh] [rbp-210Dh] BYREF
  char v376; // [rsp+16Ch] [rbp-210Ch] BYREF
  bool v377; // [rsp+16Dh] [rbp-210Bh] BYREF
  bool v378; // [rsp+16Eh] [rbp-210Ah] BYREF
  bool v379; // [rsp+16Fh] [rbp-2109h] BYREF
  bool v380; // [rsp+170h] [rbp-2108h] BYREF
  bool v381; // [rsp+171h] [rbp-2107h] BYREF
  bool v382; // [rsp+172h] [rbp-2106h] BYREF
  bool v383; // [rsp+173h] [rbp-2105h] BYREF
  char v384; // [rsp+174h] [rbp-2104h] BYREF
  char v385; // [rsp+175h] [rbp-2103h] BYREF
  bool v386; // [rsp+176h] [rbp-2102h] BYREF
  bool v387; // [rsp+177h] [rbp-2101h] BYREF
  bool v388; // [rsp+178h] [rbp-2100h] BYREF
  bool v389; // [rsp+179h] [rbp-20FFh] BYREF
  bool v390; // [rsp+17Ah] [rbp-20FEh] BYREF
  bool v391; // [rsp+17Bh] [rbp-20FDh] BYREF
  bool v392; // [rsp+17Ch] [rbp-20FCh] BYREF
  char v393; // [rsp+17Dh] [rbp-20FBh] BYREF
  NTSTATUS ExitStatus; // [rsp+180h] [rbp-20F8h]
  char v395; // [rsp+184h] [rbp-20F4h]
  char v396; // [rsp+185h] [rbp-20F3h] BYREF
  char v397; // [rsp+186h] [rbp-20F2h]
  char v398; // [rsp+187h] [rbp-20F1h] BYREF
  char v399; // [rsp+188h] [rbp-20F0h] BYREF
  bool v400; // [rsp+189h] [rbp-20EFh] BYREF
  bool v401; // [rsp+18Ah] [rbp-20EEh] BYREF
  bool v402; // [rsp+18Bh] [rbp-20EDh] BYREF
  bool v403; // [rsp+18Ch] [rbp-20ECh] BYREF
  bool v404; // [rsp+18Dh] [rbp-20EBh] BYREF
  bool v405; // [rsp+18Eh] [rbp-20EAh] BYREF
  unsigned int v406; // [rsp+190h] [rbp-20E8h] BYREF
  int v407; // [rsp+194h] [rbp-20E4h]
  int v408; // [rsp+198h] [rbp-20E0h]
  __int64 v409; // [rsp+1A0h] [rbp-20D8h] BYREF
  unsigned int v410; // [rsp+1A8h] [rbp-20D0h] BYREF
  PWSTR v411; // [rsp+1B0h] [rbp-20C8h] BYREF
  char ProcessInformation; // [rsp+1B8h] [rbp-20C0h] BYREF
  char v413; // [rsp+1B9h] [rbp-20BFh]
  char v414; // [rsp+1BAh] [rbp-20BEh]
  wchar_t v415; // [rsp+1BCh] [rbp-20BCh]
  char v416[2]; // [rsp+1BEh] [rbp-20BAh] BYREF
  unsigned int v417; // [rsp+1C0h] [rbp-20B8h]
  HANDLE v418; // [rsp+1C8h] [rbp-20B0h]
  HANDLE v419; // [rsp+1D0h] [rbp-20A8h]
  __int64 v420; // [rsp+1D8h] [rbp-20A0h] BYREF
  PWSTR FileName; // [rsp+1E0h] [rbp-2098h]
  STRSAFE_LPCWSTR v422; // [rsp+1E8h] [rbp-2090h]
  __int16 v423[2]; // [rsp+1F0h] [rbp-2088h] BYREF
  _WORD v424[3]; // [rsp+1F4h] [rbp-2084h] BYREF
  char v425; // [rsp+1FAh] [rbp-207Eh]
  __int16 v426; // [rsp+1FBh] [rbp-207Dh]
  char v427; // [rsp+1FDh] [rbp-207Bh]
  __int16 v428; // [rsp+1FEh] [rbp-207Ah]
  char v429; // [rsp+200h] [rbp-2078h]
  int v430; // [rsp+201h] [rbp-2077h]
  __int16 v431; // [rsp+205h] [rbp-2073h]
  char v432; // [rsp+207h] [rbp-2071h]
  __int128 v433; // [rsp+208h] [rbp-2070h]
  __int64 v434; // [rsp+218h] [rbp-2060h]
  __int64 v435; // [rsp+220h] [rbp-2058h]
  __int64 v436; // [rsp+228h] [rbp-2050h]
  HANDLE ThreadHandle[2]; // [rsp+230h] [rbp-2048h] BYREF
  char v438; // [rsp+240h] [rbp-2038h]
  int v439; // [rsp+241h] [rbp-2037h]
  __int16 v440; // [rsp+245h] [rbp-2033h]
  char v441; // [rsp+247h] [rbp-2031h]
  __int128 v442; // [rsp+248h] [rbp-2030h]
  __int128 v443; // [rsp+258h] [rbp-2020h]
  __int64 v444; // [rsp+268h] [rbp-2010h]
  __int64 v445; // [rsp+270h] [rbp-2008h]
  char v446; // [rsp+278h] [rbp-2000h]
  int v447; // [rsp+279h] [rbp-1FFFh]
  __int16 v448; // [rsp+27Dh] [rbp-1FFBh]
  char v449; // [rsp+27Fh] [rbp-1FF9h]
  __int64 v450; // [rsp+280h] [rbp-1FF8h]
  __int64 v451; // [rsp+288h] [rbp-1FF0h]
  __int16 v452; // [rsp+290h] [rbp-1FE8h]
  char v453; // [rsp+292h] [rbp-1FE6h]
  int v454; // [rsp+293h] [rbp-1FE5h]
  char v455; // [rsp+297h] [rbp-1FE1h]
  __int64 v456; // [rsp+298h] [rbp-1FE0h]
  bool v457; // [rsp+2A0h] [rbp-1FD8h] BYREF
  bool v458; // [rsp+2A1h] [rbp-1FD7h] BYREF
  bool v459; // [rsp+2A2h] [rbp-1FD6h] BYREF
  bool v460; // [rsp+2A3h] [rbp-1FD5h] BYREF
  char v461; // [rsp+2A4h] [rbp-1FD4h]
  bool v462; // [rsp+2A5h] [rbp-1FD3h] BYREF
  _BYTE v463[2]; // [rsp+2A6h] [rbp-1FD2h] BYREF
  int v464; // [rsp+2A8h] [rbp-1FD0h] BYREF
  unsigned int v465; // [rsp+2ACh] [rbp-1FCCh] BYREF
  bool v466; // [rsp+2B0h] [rbp-1FC8h] BYREF
  char v467; // [rsp+2B1h] [rbp-1FC7h]
  bool v468; // [rsp+2B2h] [rbp-1FC6h] BYREF
  char v469; // [rsp+2B3h] [rbp-1FC5h]
  char v470; // [rsp+2B4h] [rbp-1FC4h]
  char v471; // [rsp+2B5h] [rbp-1FC3h]
  bool v472; // [rsp+2B6h] [rbp-1FC2h] BYREF
  bool v473; // [rsp+2B7h] [rbp-1FC1h] BYREF
  bool v474; // [rsp+2B8h] [rbp-1FC0h] BYREF
  bool v475; // [rsp+2B9h] [rbp-1FBFh] BYREF
  const wchar_t *v476; // [rsp+2C0h] [rbp-1FB8h]
  int v477; // [rsp+2C8h] [rbp-1FB0h]
  int v478; // [rsp+2CCh] [rbp-1FACh] BYREF
  int v479; // [rsp+2D0h] [rbp-1FA8h] BYREF
  unsigned int NumberOfBytesToWrite; // [rsp+2D4h] [rbp-1FA4h] BYREF
  unsigned int NumberOfBytesToWrite_4; // [rsp+2D8h] [rbp-1FA0h] BYREF
  _DWORD *v482; // [rsp+2E0h] [rbp-1F98h]
  int v483; // [rsp+2E8h] [rbp-1F90h]
  LPCWSTR v484; // [rsp+2F0h] [rbp-1F88h]
  PWSTR v485; // [rsp+2F8h] [rbp-1F80h]
  HANDLE Handle; // [rsp+300h] [rbp-1F78h]
  int v487; // [rsp+308h] [rbp-1F70h]
  int v488; // [rsp+30Ch] [rbp-1F6Ch] BYREF
  __int64 v489; // [rsp+310h] [rbp-1F68h] BYREF
  struct _UNICODE_STRING v490; // [rsp+318h] [rbp-1F60h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+330h] [rbp-1F48h] BYREF
  __int64 v492; // [rsp+340h] [rbp-1F38h]
  int v493; // [rsp+348h] [rbp-1F30h] BYREF
  int v494; // [rsp+34Ch] [rbp-1F2Ch] BYREF
  int v495; // [rsp+350h] [rbp-1F28h] BYREF
  __int64 v496; // [rsp+358h] [rbp-1F20h]
  HANDLE v497; // [rsp+360h] [rbp-1F18h] BYREF
  int v498; // [rsp+368h] [rbp-1F10h]
  int v499; // [rsp+36Ch] [rbp-1F0Ch] BYREF
  __int64 v500; // [rsp+370h] [rbp-1F08h] BYREF
  PWSTR Environment; // [rsp+378h] [rbp-1F00h] BYREF
  int v502; // [rsp+380h] [rbp-1EF8h]
  HANDLE v503; // [rsp+388h] [rbp-1EF0h]
  PVOID v504; // [rsp+390h] [rbp-1EE8h] BYREF
  _QWORD *v505; // [rsp+398h] [rbp-1EE0h] BYREF
  HANDLE token[2]; // [rsp+3A0h] [rbp-1ED8h] BYREF
  __int64 v507; // [rsp+3B0h] [rbp-1EC8h] BYREF
  PVOID P; // [rsp+3B8h] [rbp-1EC0h]
  PVOID v509; // [rsp+3C0h] [rbp-1EB8h]
  PCSR_CAPTURE_BUFFER CaptureBuffer; // [rsp+3C8h] [rbp-1EB0h] BYREF
  ULONG ReturnedLength; // [rsp+3D0h] [rbp-1EA8h] BYREF
  unsigned int v512; // [rsp+3D4h] [rbp-1EA4h]
  int v513; // [rsp+3D8h] [rbp-1EA0h]
  int v514; // [rsp+3DCh] [rbp-1E9Ch]
  int v515; // [rsp+3E0h] [rbp-1E98h]
  int v516; // [rsp+3E4h] [rbp-1E94h]
  int v517; // [rsp+3E8h] [rbp-1E90h] BYREF
  ULONG v518; // [rsp+3ECh] [rbp-1E8Ch] BYREF
  unsigned int v519; // [rsp+3F0h] [rbp-1E88h] BYREF
  unsigned int v520; // [rsp+3F4h] [rbp-1E84h] BYREF
  int v521; // [rsp+3F8h] [rbp-1E80h]
  ULONG v522; // [rsp+3FCh] [rbp-1E7Ch] BYREF
  int v523; // [rsp+400h] [rbp-1E78h] BYREF
  ULONG v524; // [rsp+404h] [rbp-1E74h] BYREF
  unsigned int v525; // [rsp+408h] [rbp-1E70h] BYREF
  ULONG v526; // [rsp+40Ch] [rbp-1E6Ch] BYREF
  unsigned int v527; // [rsp+410h] [rbp-1E68h] BYREF
  ULONG v528; // [rsp+414h] [rbp-1E64h] BYREF
  char v529; // [rsp+418h] [rbp-1E60h]
  char v530; // [rsp+419h] [rbp-1E5Fh]
  HANDLE TokenHandle; // [rsp+420h] [rbp-1E58h] BYREF
  HANDLE v532; // [rsp+428h] [rbp-1E50h]
  __int64 v533; // [rsp+430h] [rbp-1E48h] BYREF
  void *v534; // [rsp+438h] [rbp-1E40h]
  void *Src; // [rsp+440h] [rbp-1E38h]
  PVOID v536; // [rsp+448h] [rbp-1E30h]
  char v537; // [rsp+450h] [rbp-1E28h]
  char v538; // [rsp+451h] [rbp-1E27h]
  char v539; // [rsp+452h] [rbp-1E26h]
  struct _UNICODE_STRING UnicodeString; // [rsp+458h] [rbp-1E20h] BYREF
  wchar_t v541; // [rsp+468h] [rbp-1E10h]
  __int16 v542; // [rsp+46Ch] [rbp-1E0Ch] BYREF
  int v543; // [rsp+470h] [rbp-1E08h] BYREF
  int v544; // [rsp+474h] [rbp-1E04h] BYREF
  HANDLE ProcessHandle; // [rsp+478h] [rbp-1E00h] BYREF
  LPCWSTR lpPath; // [rsp+480h] [rbp-1DF8h] BYREF
  struct _PEB *v547; // [rsp+488h] [rbp-1DF0h]
  HANDLE v548; // [rsp+490h] [rbp-1DE8h]
  PVOID v549; // [rsp+498h] [rbp-1DE0h]
  __int64 v550; // [rsp+4A0h] [rbp-1DD8h]
  int v551; // [rsp+4A8h] [rbp-1DD0h]
  __int64 v552; // [rsp+4B0h] [rbp-1DC8h]
  STRSAFE_LPCWSTR v553; // [rsp+4B8h] [rbp-1DC0h]
  int v554; // [rsp+4C0h] [rbp-1DB8h] BYREF
  int v555; // [rsp+4C4h] [rbp-1DB4h]
  int v556; // [rsp+4C8h] [rbp-1DB0h] BYREF
  int TokenInformation; // [rsp+4CCh] [rbp-1DACh] BYREF
  ULONG ReturnLength; // [rsp+4D0h] [rbp-1DA8h] BYREF
  int v559; // [rsp+4D4h] [rbp-1DA4h] BYREF
  int v560; // [rsp+4D8h] [rbp-1DA0h]
  int v561; // [rsp+4DCh] [rbp-1D9Ch]
  ULONG Response; // [rsp+4E0h] [rbp-1D98h] BYREF
  int v563; // [rsp+4E4h] [rbp-1D94h]
  int v564; // [rsp+4E8h] [rbp-1D90h] BYREF
  int v565; // [rsp+4ECh] [rbp-1D8Ch] BYREF
  int v566; // [rsp+4F0h] [rbp-1D88h] BYREF
  int v567; // [rsp+4F4h] [rbp-1D84h] BYREF
  RTL_PATH_TYPE v568; // [rsp+4F8h] [rbp-1D80h] BYREF
  PVOID BaseAddress; // [rsp+500h] [rbp-1D78h] BYREF
  RTL_PATH_TYPE InputPathType; // [rsp+508h] [rbp-1D70h] BYREF
  BOOL Result; // [rsp+50Ch] [rbp-1D6Ch] BYREF
  int v572; // [rsp+510h] [rbp-1D68h] BYREF
  int v573; // [rsp+514h] [rbp-1D64h] BYREF
  PVOID Buffer; // [rsp+518h] [rbp-1D60h]
  __int64 v575; // [rsp+520h] [rbp-1D58h]
  PVOID v576; // [rsp+528h] [rbp-1D50h]
  HANDLE DebugObject; // [rsp+530h] [rbp-1D48h]
  PVOID v578; // [rsp+538h] [rbp-1D40h]
  PWSTR v579; // [rsp+540h] [rbp-1D38h] BYREF
  STRSAFE_LPCWSTR v580; // [rsp+548h] [rbp-1D30h]
  __int64 v581; // [rsp+550h] [rbp-1D28h] BYREF
  WCHAR *v582; // [rsp+558h] [rbp-1D20h] BYREF
  __int64 v583; // [rsp+560h] [rbp-1D18h] BYREF
  __int64 v584; // [rsp+568h] [rbp-1D10h] BYREF
  struct _UNICODE_STRING v585; // [rsp+570h] [rbp-1D08h] BYREF
  __int128 v586; // [rsp+580h] [rbp-1CF8h]
  __int64 v587; // [rsp+590h] [rbp-1CE8h]
  struct _UNICODE_STRING v588; // [rsp+598h] [rbp-1CE0h] BYREF
  ULONG v589; // [rsp+5A8h] [rbp-1CD0h]
  int v590; // [rsp+5ACh] [rbp-1CCCh] BYREF
  UINT32 packageFullNameLength; // [rsp+5B0h] [rbp-1CC8h] BYREF
  LONG v592; // [rsp+5B4h] [rbp-1CC4h] BYREF
  LONG v593; // [rsp+5B8h] [rbp-1CC0h] BYREF
  UINT32 v594; // [rsp+5BCh] [rbp-1CBCh] BYREF
  LONG v595; // [rsp+5C0h] [rbp-1CB8h] BYREF
  UINT32 v596; // [rsp+5C4h] [rbp-1CB4h] BYREF
  int v597; // [rsp+5C8h] [rbp-1CB0h]
  UINT32 applicationUserModelIdLength; // [rsp+5CCh] [rbp-1CACh] BYREF
  int v599; // [rsp+5D0h] [rbp-1CA8h] BYREF
  unsigned int v600; // [rsp+5D4h] [rbp-1CA4h] BYREF
  int v601; // [rsp+5D8h] [rbp-1CA0h] BYREF
  __int64 v602; // [rsp+5E0h] [rbp-1C98h]
  PVOID v603; // [rsp+5E8h] [rbp-1C90h]
  __int64 v604; // [rsp+5F0h] [rbp-1C88h] BYREF
  __int16 *v605; // [rsp+5F8h] [rbp-1C80h]
  __int64 v606; // [rsp+600h] [rbp-1C78h]
  PVOID v607; // [rsp+608h] [rbp-1C70h]
  __int64 v608; // [rsp+610h] [rbp-1C68h] BYREF
  __int64 v609; // [rsp+618h] [rbp-1C60h] BYREF
  HANDLE v610; // [rsp+620h] [rbp-1C58h] BYREF
  int v611; // [rsp+628h] [rbp-1C50h]
  LONG v612; // [rsp+62Ch] [rbp-1C4Ch] BYREF
  BOOL v613; // [rsp+630h] [rbp-1C48h]
  unsigned int v614; // [rsp+634h] [rbp-1C44h] BYREF
  int v615; // [rsp+638h] [rbp-1C40h] BYREF
  __int64 v616; // [rsp+640h] [rbp-1C38h] BYREF
  int v617; // [rsp+648h] [rbp-1C30h]
  HANDLE KeyHandle; // [rsp+650h] [rbp-1C28h]
  void *v619; // [rsp+658h] [rbp-1C20h]
  void *v620; // [rsp+660h] [rbp-1C18h]
  int v621; // [rsp+674h] [rbp-1C04h]
  __int64 v622; // [rsp+678h] [rbp-1C00h]
  unsigned int v623; // [rsp+680h] [rbp-1BF8h]
  unsigned __int64 v624; // [rsp+688h] [rbp-1BF0h]
  int v625; // [rsp+690h] [rbp-1BE8h]
  __int64 v626; // [rsp+6A0h] [rbp-1BD8h] BYREF
  __int64 v627; // [rsp+6A8h] [rbp-1BD0h]
  struct _UNICODE_STRING DynamicString; // [rsp+6B0h] [rbp-1BC8h] BYREF
  __int64 v629; // [rsp+6C0h] [rbp-1BB8h] BYREF
  __int64 v630; // [rsp+6C8h] [rbp-1BB0h]
  __int64 v631; // [rsp+6D0h] [rbp-1BA8h] BYREF
  __int64 v632; // [rsp+6D8h] [rbp-1BA0h] BYREF
  __int64 v633; // [rsp+6E0h] [rbp-1B98h]
  _QWORD v634[2]; // [rsp+6E8h] [rbp-1B90h] BYREF
  __m128i v635; // [rsp+6F8h] [rbp-1B80h] BYREF
  unsigned __int64 v636; // [rsp+708h] [rbp-1B70h]
  unsigned __int64 v637; // [rsp+710h] [rbp-1B68h] BYREF
  unsigned __int64 v638; // [rsp+718h] [rbp-1B60h]
  __int64 v639; // [rsp+720h] [rbp-1B58h]
  ULONG_PTR RegionSize; // [rsp+728h] [rbp-1B50h] BYREF
  PVOID v641; // [rsp+730h] [rbp-1B48h]
  __int64 v642; // [rsp+738h] [rbp-1B40h] BYREF
  __int64 v643; // [rsp+740h] [rbp-1B38h] BYREF
  int v644; // [rsp+748h] [rbp-1B30h]
  int v645; // [rsp+74Ch] [rbp-1B2Ch]
  int v646; // [rsp+750h] [rbp-1B28h]
  int v647; // [rsp+754h] [rbp-1B24h]
  __int64 v648; // [rsp+758h] [rbp-1B20h] BYREF
  __int64 v649; // [rsp+760h] [rbp-1B18h] BYREF
  PWSTR FilePart; // [rsp+768h] [rbp-1B10h] BYREF
  __int64 v651; // [rsp+770h] [rbp-1B08h] BYREF
  __int64 v652; // [rsp+778h] [rbp-1B00h] BYREF
  __int64 v653; // [rsp+780h] [rbp-1AF8h] BYREF
  __int64 v654; // [rsp+788h] [rbp-1AF0h] BYREF
  __int64 v655; // [rsp+790h] [rbp-1AE8h] BYREF
  __int64 v656; // [rsp+798h] [rbp-1AE0h] BYREF
  __m128i Buf1; // [rsp+7A0h] [rbp-1AD8h] BYREF
  __int128 v658; // [rsp+7B0h] [rbp-1AC8h]
  __int128 v659; // [rsp+7C0h] [rbp-1AB8h]
  __int128 v660; // [rsp+7D0h] [rbp-1AA8h]
  __int128 v661; // [rsp+7E0h] [rbp-1A98h]
  __int128 v662; // [rsp+7F0h] [rbp-1A88h]
  __int64 v663; // [rsp+800h] [rbp-1A78h]
  __int128 v664; // [rsp+810h] [rbp-1A68h] BYREF
  _BYTE v665[32]; // [rsp+820h] [rbp-1A58h] BYREF
  int v666; // [rsp+840h] [rbp-1A38h]
  unsigned __int16 v667; // [rsp+844h] [rbp-1A34h]
  unsigned __int16 v668; // [rsp+846h] [rbp-1A32h]
  unsigned __int16 v669; // [rsp+84Eh] [rbp-1A2Ah]
  unsigned __int16 v670; // [rsp+850h] [rbp-1A28h]
  unsigned __int64 Parameters[4]; // [rsp+860h] [rbp-1A18h] BYREF
  __int64 *v672; // [rsp+880h] [rbp-19F8h]
  __int128 v673; // [rsp+888h] [rbp-19F0h] BYREF
  _OWORD v674[3]; // [rsp+898h] [rbp-19E0h] BYREF
  __int64 v675; // [rsp+8C8h] [rbp-19B0h]
  _OWORD v676[3]; // [rsp+8D0h] [rbp-19A8h] BYREF
  _OWORD v677[3]; // [rsp+900h] [rbp-1978h] BYREF
  int Buf2; // [rsp+930h] [rbp-1948h] BYREF
  char v679[108]; // [rsp+934h] [rbp-1944h] BYREF
  int v680; // [rsp+9A0h] [rbp-18D8h] BYREF
  char v681[108]; // [rsp+9A4h] [rbp-18D4h] BYREF
  _BYTE v682[96]; // [rsp+A10h] [rbp-1868h] BYREF
  __int128 v683; // [rsp+A70h] [rbp-1808h] BYREF
  __int128 v684; // [rsp+A80h] [rbp-17F8h]
  __int128 v685; // [rsp+A90h] [rbp-17E8h] BYREF
  __int128 v686; // [rsp+AA0h] [rbp-17D8h] BYREF
  __int128 v687; // [rsp+AB0h] [rbp-17C8h] BYREF
  __int64 v688; // [rsp+AC0h] [rbp-17B8h]
  __int128 v689; // [rsp+AC8h] [rbp-17B0h] BYREF
  __int128 v690; // [rsp+AD8h] [rbp-17A0h] BYREF
  __int128 v691; // [rsp+AE8h] [rbp-1790h] BYREF
  __int64 v692; // [rsp+AF8h] [rbp-1780h]
  __int128 v693; // [rsp+B00h] [rbp-1778h] BYREF
  __int64 v694; // [rsp+B10h] [rbp-1768h]
  _BYTE ApiMessage[52]; // [rsp+B20h] [rbp-1758h] BYREF
  NTSTATUS v696; // [rsp+B54h] [rbp-1724h]
  unsigned __int64 v697; // [rsp+B60h] [rbp-1718h]
  unsigned __int64 v698; // [rsp+B68h] [rbp-1710h]
  __m128i v699; // [rsp+B70h] [rbp-1708h]
  unsigned int v700; // [rsp+B80h] [rbp-16F8h]
  unsigned int v701; // [rsp+B84h] [rbp-16F4h]
  unsigned int v702; // [rsp+B88h] [rbp-16F0h]
  __int64 v703; // [rsp+B90h] [rbp-16E8h]
  _BYTE v704[4]; // [rsp+B98h] [rbp-16E0h] BYREF
  int v705; // [rsp+B9Ch] [rbp-16DCh]
  _BYTE v706[12]; // [rsp+C30h] [rbp-1648h] BYREF
  _WORD v707[2]; // [rsp+C3Ch] [rbp-163Ch] BYREF
  _BYTE v708[16]; // [rsp+C40h] [rbp-1638h] BYREF
  __int64 v709; // [rsp+C50h] [rbp-1628h] BYREF
  __int16 v710; // [rsp+C58h] [rbp-1620h] BYREF
  __int64 v711; // [rsp+D60h] [rbp-1518h]
  __int64 v712; // [rsp+D68h] [rbp-1510h]
  __int16 v713; // [rsp+D70h] [rbp-1508h]
  __int64 v714; // [rsp+EE0h] [rbp-1398h] BYREF
  __int64 v715; // [rsp+EE8h] [rbp-1390h]
  __int64 v716; // [rsp+EF0h] [rbp-1388h]
  PWSTR v717; // [rsp+EF8h] [rbp-1380h]
  _QWORD v718[138]; // [rsp+F00h] [rbp-1378h]
  char v719[8]; // [rsp+1350h] [rbp-F28h] BYREF
  __int64 v720; // [rsp+1358h] [rbp-F20h]
  __int64 v721; // [rsp+1360h] [rbp-F18h]
  struct _UNICODE_STRING *v722; // [rsp+1368h] [rbp-F10h]
  __int64 v723; // [rsp+1370h] [rbp-F08h]
  __int64 v724; // [rsp+1378h] [rbp-F00h]
  __int64 v725; // [rsp+1380h] [rbp-EF8h]
  __int64 *v726; // [rsp+1388h] [rbp-EF0h]
  __int64 v727; // [rsp+1390h] [rbp-EE8h]
  char v728; // [rsp+17C0h] [rbp-AB8h] BYREF
  __int64 *v729; // [rsp+17E0h] [rbp-A98h]
  __int64 v730; // [rsp+17E8h] [rbp-A90h]
  char *v731; // [rsp+17F0h] [rbp-A88h]
  __int64 v732; // [rsp+17F8h] [rbp-A80h]
  ULONG *v733; // [rsp+1800h] [rbp-A78h]
  __int64 v734; // [rsp+1808h] [rbp-A70h]
  char *v735; // [rsp+1810h] [rbp-A68h]
  __int64 v736; // [rsp+1818h] [rbp-A60h]
  char v737[16]; // [rsp+1820h] [rbp-A58h] BYREF
  char v738[16]; // [rsp+1830h] [rbp-A48h] BYREF
  bool *v739; // [rsp+1840h] [rbp-A38h]
  __int64 v740; // [rsp+1848h] [rbp-A30h]
  bool *v741; // [rsp+1850h] [rbp-A28h]
  __int64 v742; // [rsp+1858h] [rbp-A20h]
  bool *v743; // [rsp+1860h] [rbp-A18h]
  __int64 v744; // [rsp+1868h] [rbp-A10h]
  bool *v745; // [rsp+1870h] [rbp-A08h]
  __int64 v746; // [rsp+1878h] [rbp-A00h]
  unsigned int *v747; // [rsp+1880h] [rbp-9F8h]
  __int64 v748; // [rsp+1888h] [rbp-9F0h]
  bool *v749; // [rsp+1890h] [rbp-9E8h]
  __int64 v750; // [rsp+1898h] [rbp-9E0h]
  bool *v751; // [rsp+18A0h] [rbp-9D8h]
  __int64 v752; // [rsp+18A8h] [rbp-9D0h]
  bool *v753; // [rsp+18B0h] [rbp-9C8h]
  __int64 v754; // [rsp+18B8h] [rbp-9C0h]
  char v755; // [rsp+18C0h] [rbp-9B8h] BYREF
  __int64 *v756; // [rsp+18E0h] [rbp-998h]
  __int64 v757; // [rsp+18E8h] [rbp-990h]
  char *v758; // [rsp+18F0h] [rbp-988h]
  __int64 v759; // [rsp+18F8h] [rbp-980h]
  ULONG *v760; // [rsp+1900h] [rbp-978h]
  __int64 v761; // [rsp+1908h] [rbp-970h]
  char *v762; // [rsp+1910h] [rbp-968h]
  __int64 v763; // [rsp+1918h] [rbp-960h]
  char v764[16]; // [rsp+1920h] [rbp-958h] BYREF
  char v765[16]; // [rsp+1930h] [rbp-948h] BYREF
  bool *v766; // [rsp+1940h] [rbp-938h]
  __int64 v767; // [rsp+1948h] [rbp-930h]
  bool *v768; // [rsp+1950h] [rbp-928h]
  __int64 v769; // [rsp+1958h] [rbp-920h]
  bool *v770; // [rsp+1960h] [rbp-918h]
  __int64 v771; // [rsp+1968h] [rbp-910h]
  bool *v772; // [rsp+1970h] [rbp-908h]
  __int64 v773; // [rsp+1978h] [rbp-900h]
  unsigned int *v774; // [rsp+1980h] [rbp-8F8h]
  __int64 v775; // [rsp+1988h] [rbp-8F0h]
  bool *v776; // [rsp+1990h] [rbp-8E8h]
  __int64 v777; // [rsp+1998h] [rbp-8E0h]
  bool *v778; // [rsp+19A0h] [rbp-8D8h]
  __int64 v779; // [rsp+19A8h] [rbp-8D0h]
  bool *v780; // [rsp+19B0h] [rbp-8C8h]
  __int64 v781; // [rsp+19B8h] [rbp-8C0h]
  char v782; // [rsp+19C0h] [rbp-8B8h] BYREF
  char *v783; // [rsp+19E0h] [rbp-898h]
  __int64 v784; // [rsp+19E8h] [rbp-890h]
  ULONG *v785; // [rsp+19F0h] [rbp-888h]
  __int64 v786; // [rsp+19F8h] [rbp-880h]
  char *v787; // [rsp+1A00h] [rbp-878h]
  __int64 v788; // [rsp+1A08h] [rbp-870h]
  char v789[16]; // [rsp+1A10h] [rbp-868h] BYREF
  char v790[16]; // [rsp+1A20h] [rbp-858h] BYREF
  bool *v791; // [rsp+1A30h] [rbp-848h]
  __int64 v792; // [rsp+1A38h] [rbp-840h]
  bool *v793; // [rsp+1A40h] [rbp-838h]
  __int64 v794; // [rsp+1A48h] [rbp-830h]
  bool *v795; // [rsp+1A50h] [rbp-828h]
  __int64 v796; // [rsp+1A58h] [rbp-820h]
  bool *v797; // [rsp+1A60h] [rbp-818h]
  __int64 v798; // [rsp+1A68h] [rbp-810h]
  unsigned int *v799; // [rsp+1A70h] [rbp-808h]
  __int64 v800; // [rsp+1A78h] [rbp-800h]
  bool *v801; // [rsp+1A80h] [rbp-7F8h]
  __int64 v802; // [rsp+1A88h] [rbp-7F0h]
  bool *v803; // [rsp+1A90h] [rbp-7E8h]
  __int64 v804; // [rsp+1A98h] [rbp-7E0h]
  bool *v805; // [rsp+1AA0h] [rbp-7D8h]
  __int64 v806; // [rsp+1AA8h] [rbp-7D0h]
  char v807; // [rsp+1AB0h] [rbp-7C8h] BYREF
  char *v808; // [rsp+1AD0h] [rbp-7A8h]
  __int64 v809; // [rsp+1AD8h] [rbp-7A0h]
  ULONG *v810; // [rsp+1AE0h] [rbp-798h]
  __int64 v811; // [rsp+1AE8h] [rbp-790h]
  char *v812; // [rsp+1AF0h] [rbp-788h]
  __int64 v813; // [rsp+1AF8h] [rbp-780h]
  char v814[16]; // [rsp+1B00h] [rbp-778h] BYREF
  char v815[16]; // [rsp+1B10h] [rbp-768h] BYREF
  bool *v816; // [rsp+1B20h] [rbp-758h]
  __int64 v817; // [rsp+1B28h] [rbp-750h]
  bool *v818; // [rsp+1B30h] [rbp-748h]
  __int64 v819; // [rsp+1B38h] [rbp-740h]
  bool *v820; // [rsp+1B40h] [rbp-738h]
  __int64 v821; // [rsp+1B48h] [rbp-730h]
  bool *v822; // [rsp+1B50h] [rbp-728h]
  __int64 v823; // [rsp+1B58h] [rbp-720h]
  unsigned int *v824; // [rsp+1B60h] [rbp-718h]
  __int64 v825; // [rsp+1B68h] [rbp-710h]
  bool *v826; // [rsp+1B70h] [rbp-708h]
  __int64 v827; // [rsp+1B78h] [rbp-700h]
  bool *v828; // [rsp+1B80h] [rbp-6F8h]
  __int64 v829; // [rsp+1B88h] [rbp-6F0h]
  bool *v830; // [rsp+1B90h] [rbp-6E8h]
  __int64 v831; // [rsp+1B98h] [rbp-6E0h]
  char v832[32]; // [rsp+1BA0h] [rbp-6D8h] BYREF
  __int64 *v833; // [rsp+1BC0h] [rbp-6B8h]
  __int64 v834; // [rsp+1BC8h] [rbp-6B0h]
  ULONG *v835; // [rsp+1BD0h] [rbp-6A8h]
  __int64 v836; // [rsp+1BD8h] [rbp-6A0h]
  char v837[16]; // [rsp+1BE0h] [rbp-698h] BYREF
  bool *v838; // [rsp+1BF0h] [rbp-688h]
  __int64 v839; // [rsp+1BF8h] [rbp-680h]
  int *v840; // [rsp+1C00h] [rbp-678h]
  __int64 v841; // [rsp+1C08h] [rbp-670h]
  char v842[32]; // [rsp+1C10h] [rbp-668h] BYREF
  __int64 *v843; // [rsp+1C30h] [rbp-648h]
  __int64 v844; // [rsp+1C38h] [rbp-640h]
  char v845[16]; // [rsp+1C40h] [rbp-638h] BYREF
  _BYTE *v846; // [rsp+1C50h] [rbp-628h]
  __int64 v847; // [rsp+1C58h] [rbp-620h]
  bool *v848; // [rsp+1C60h] [rbp-618h]
  __int64 v849; // [rsp+1C68h] [rbp-610h]
  bool *v850; // [rsp+1C70h] [rbp-608h]
  __int64 v851; // [rsp+1C78h] [rbp-600h]
  unsigned int *v852; // [rsp+1C80h] [rbp-5F8h]
  __int64 v853; // [rsp+1C88h] [rbp-5F0h]
  bool *v854; // [rsp+1C90h] [rbp-5E8h]
  __int64 v855; // [rsp+1C98h] [rbp-5E0h]
  bool *v856; // [rsp+1CA0h] [rbp-5D8h]
  __int64 v857; // [rsp+1CA8h] [rbp-5D0h]
  char v858[32]; // [rsp+1CB0h] [rbp-5C8h] BYREF
  __int64 *v859; // [rsp+1CD0h] [rbp-5A8h]
  __int64 v860; // [rsp+1CD8h] [rbp-5A0h]
  char v861[16]; // [rsp+1CE0h] [rbp-598h] BYREF
  bool *v862; // [rsp+1CF0h] [rbp-588h]
  __int64 v863; // [rsp+1CF8h] [rbp-580h]
  bool *v864; // [rsp+1D00h] [rbp-578h]
  __int64 v865; // [rsp+1D08h] [rbp-570h]
  bool *v866; // [rsp+1D10h] [rbp-568h]
  __int64 v867; // [rsp+1D18h] [rbp-560h]
  unsigned int *v868; // [rsp+1D20h] [rbp-558h]
  __int64 v869; // [rsp+1D28h] [rbp-550h]
  bool *v870; // [rsp+1D30h] [rbp-548h]
  __int64 v871; // [rsp+1D38h] [rbp-540h]
  bool *v872; // [rsp+1D40h] [rbp-538h]
  __int64 v873; // [rsp+1D48h] [rbp-530h]
  char v874[32]; // [rsp+1D50h] [rbp-528h] BYREF
  __int64 *v875; // [rsp+1D70h] [rbp-508h]
  __int64 v876; // [rsp+1D78h] [rbp-500h]
  LONG *v877; // [rsp+1D80h] [rbp-4F8h]
  __int64 v878; // [rsp+1D88h] [rbp-4F0h]
  bool *v879; // [rsp+1D90h] [rbp-4E8h]
  __int64 v880; // [rsp+1D98h] [rbp-4E0h]
  char v881[32]; // [rsp+1DA0h] [rbp-4D8h] BYREF
  __int64 *v882; // [rsp+1DC0h] [rbp-4B8h]
  __int64 v883; // [rsp+1DC8h] [rbp-4B0h]
  LONG *v884; // [rsp+1DD0h] [rbp-4A8h]
  __int64 v885; // [rsp+1DD8h] [rbp-4A0h]
  bool *v886; // [rsp+1DE0h] [rbp-498h]
  __int64 v887; // [rsp+1DE8h] [rbp-490h]
  char v888[32]; // [rsp+1DF0h] [rbp-488h] BYREF
  __int64 *v889; // [rsp+1E10h] [rbp-468h]
  __int64 v890; // [rsp+1E18h] [rbp-460h]
  int *v891; // [rsp+1E20h] [rbp-458h]
  __int64 v892; // [rsp+1E28h] [rbp-450h]
  char v893[16]; // [rsp+1E30h] [rbp-448h] BYREF
  int *v894; // [rsp+1E40h] [rbp-438h]
  __int64 v895; // [rsp+1E48h] [rbp-430h]
  char v896; // [rsp+1E50h] [rbp-428h] BYREF
  __int64 *v897; // [rsp+1E70h] [rbp-408h]
  __int64 v898; // [rsp+1E78h] [rbp-400h]
  LONG *v899; // [rsp+1E80h] [rbp-3F8h]
  __int64 v900; // [rsp+1E88h] [rbp-3F0h]
  char v901[16]; // [rsp+1E90h] [rbp-3E8h] BYREF
  char v902[16]; // [rsp+1EA0h] [rbp-3D8h] BYREF
  char v903; // [rsp+1EB0h] [rbp-3C8h] BYREF
  __int64 *v904; // [rsp+1ED0h] [rbp-3A8h]
  __int64 v905; // [rsp+1ED8h] [rbp-3A0h]
  LONG *v906; // [rsp+1EE0h] [rbp-398h]
  __int64 v907; // [rsp+1EE8h] [rbp-390h]
  char v908[16]; // [rsp+1EF0h] [rbp-388h] BYREF
  char v909[16]; // [rsp+1F00h] [rbp-378h] BYREF
  WCHAR packageFullName[128]; // [rsp+1F10h] [rbp-368h] BYREF
  _WORD v911[136]; // [rsp+2010h] [rbp-268h] BYREF
  WCHAR applicationUserModelId[64]; // [rsp+2120h] [rbp-158h] BYREF

  v672 = &v338;
  v496 = a4;
  v534 = a1;
  v14 = a11;
  v348 = a11;
  v15 = a7;
  lpFileName = a2;
  pszSrc = a3;
  v552 = a4;
  v492 = a5;
  v550 = a5;
  v349 = a7;
  v411 = a8;
  FileName = a9;
  v633 = a10;
  v606 = a11;
  ReturnLength = 0;
  NumberOfBytesToWrite_4 = 0;
  v406 = 0;
  v410 = 0;
  v626 = 0;
  v629 = 0;
  v579 = 0;
  Buf1.m128i_i32[1] = 0;
  memset_0(&Buf1, 0, 0x64u);
  lpPath = 0;
  memset_0(ApiMessage, 0, 0x3B8u);
  ReturnedLength = 0;
  memset(v676, 0, 44);
  memset(v677, 0, 44);
  v632 = 0;
  v631 = 0;
  UnicodeString = 0;
  DestinationString = 0;
  v683 = 0;
  v684 = 0;
  v359 = 0;
  v360 = 0;
  v361 = 0;
  v634[0] = 1310738;
  v634[1] = L"ntdll.dll";
  memset_0(&v616, 0, 0x58u);
  Result = 0;
  v573 = 0;
  v568 = RtlPathTypeUnknown;
  memset_0(v665, 0, 0x40u);
  DynamicString = 0;
  *(_QWORD *)&v588.Length = 0;
  v393 = 0;
  Response = 0;
  v495 = 0;
  BaseAddress = 0;
  RegionSize = 0;
  memset_0(&v714, 0, 0x468u);
  v345 = 0;
  memset_0(v719, 0, 0x468u);
  v489 = 0;
  v635 = 0;
  v490 = 0;
  v505 = 0;
  Environment = 0;
  v582 = 0;
  v503 = 0;
  v420 = 0;
  v416[0] = 0;
  v464 = 0;
  v357 = 0;
  v409 = 0;
  TokenHandle = 0;
  ProcessInformation = 0;
  v423[0] = 0;
  v542 = 0;
  v424[0] = 0;
  memset(v674, 0, sizeof(v674));
  v675 = 0;
  v673 = 0;
  v649 = 0;
  v565 = 0;
  v544 = 0;
  v686 = 0;
  v685 = 0;
  v689 = 0;
  v690 = 0;
  v572 = 0;
  v637 = 0;
  v566 = 0;
  if ( !a2 && !a3 )
  {
    v16 = 3221225520LL;
LABEL_1279:
    BaseSetLastNTError(v16);
    return 0;
  }
  if ( !v14 || (v17 = v633) == 0 )
  {
    v16 = 3221225485LL;
    goto LABEL_1279;
  }
  v497 = 0;
  Process = 0;
  ThreadHandle[0] = 0;
  CaptureBuffer = 0;
  v601 = 0;
  FilePart = 0;
  v588.Buffer = 0;
  v396 = 0;
  ProcessHandle = 0;
  v583 = 0;
  v504 = 0;
  NumberOfBytesToWrite = 0;
  v507 = 0;
  v488 = 0;
  v500 = 0;
  v479 = 0;
  v465 = 0;
  v559 = 0;
  v533 = 0;
  v499 = 0;
  v584 = 0;
  v517 = 0;
  v350 = 0;
  v494 = 0;
  v627 = 0;
  v630 = 0;
  v664 = 0;
  v687 = 0;
  v688 = 0;
  v693 = 0;
  v694 = 0;
  v581 = 0;
  v590 = 0;
  v564 = 0;
  v478 = 0;
  v691 = 0;
  v692 = 0;
  memset_0(v682, 0, 0x58u);
  v585 = 0;
  v586 = 0;
  v587 = 0;
  *(_OWORD *)token = 0;
  v547 = NtCurrentPeb();
  ProcessHeap = v547->ProcessHeap;
  HeapHandle = ProcessHeap;
  memset_0(packageFullName, 0, sizeof(packageFullName));
  v544 = 1;
  v911[0] = 0;
  if ( (v15 & 0x18) == 0x18 )
  {
LABEL_9:
    RtlSetLastWin32Error(0x57u);
    return 0;
  }
  if ( (v15 & 0x800) != 0 )
  {
    if ( (v15 & 0x1000) != 0 )
      goto LABEL_9;
  }
  else if ( (v15 & 0x1000) == 0 && *(_BYTE *)(BaseStaticServerData + 2036) )
  {
    v15 |= 0x800u;
    v349 = v15;
  }
  ThreadDebugObject = 0;
  DebugObject = 0;
  if ( (v15 & 0x40) != 0 )
  {
    v21 = 1;
  }
  else if ( (v15 & 0x4000) != 0 )
  {
    v21 = 5;
  }
  else if ( (v15 & 0x20) != 0 )
  {
    v21 = 2;
  }
  else if ( (v15 & 0x8000) != 0 )
  {
    v21 = 6;
  }
  else if ( (v15 & 0x80u) == 0 )
  {
    if ( (v15 & 0x100) != 0 )
    {
      LOBYTE(v19) = a1 != 0;
      v21 = (BasepIsRealtimeAllowed(0, v19) != 0) + 3;
      ThreadDebugObject = DebugObject;
    }
    else
    {
      v21 = 0;
    }
  }
  else
  {
    v21 = 3;
  }
  v393 = v21;
  v349 &= 0xFFFF3E1F;
  if ( (v349 & 0x40000) != 0 )
    v350 |= 0x40u;
  if ( (v349 & 0x1000000) != 0 )
    v350 |= 1u;
  if ( (v349 & 0x10000) != 0 )
    v350 |= 0x100u;
  if ( (v349 & 4) == 0 )
    v350 |= 0x200u;
  if ( (v349 & 3) != 0 )
  {
    v22 = DbgUiConnectToDbg();
    if ( v22 < 0 )
    {
      v16 = (unsigned int)v22;
      goto LABEL_1279;
    }
    ThreadDebugObject = DbgUiGetThreadDebugObject();
    DebugObject = ThreadDebugObject;
    if ( (v349 & 2) != 0 )
      v350 |= 2u;
  }
  v344 = 0;
  v23 = 0;
  v422 = 0;
  v415 = 0;
  v509 = 0;
  v482 = 0;
  v602 = 0;
  Handle = 0;
  v548 = 0;
  P = 0;
  Buffer = 0;
  v536 = 0;
  v607 = 0;
  v397 = 0;
  v358 = 0;
  v395 = 0;
  v576 = 0;
  ExitStatus = 0;
  v636 = 0;
  v560 = 0;
  v502 = 0;
  v487 = 0;
  v351 = 0;
  v603 = ProcessHeap;
  v352 = 0;
  LOBYTE(v515) = 0;
  v413 = 0;
  v418 = 0;
  v575 = 0;
  v498 = 0;
  v355 = 0;
  v354 = 0;
  v578 = 0;
  v549 = 0;
  v561 = 0;
  v516 = 0;
  v521 = 0;
  v477 = 0;
  Src = 0;
  v605 = 0;
  v715 = 131077;
  v718[0] = 0;
  v718[1] = 65539;
  v718[2] = 16;
  v718[4] = 0;
  v718[3] = &v635;
  v718[5] = 6;
  v718[6] = 64;
  v718[8] = 0;
  v718[7] = v665;
  v345 = 3;
  if ( ThreadDebugObject )
  {
    v718[9] = 393217;
    v718[10] = 8;
    v718[12] = 0;
    v718[11] = ThreadDebugObject;
    v345 = 4;
    v24 = 4;
  }
  else
  {
    v24 = 3;
  }
  if ( v393 )
  {
    *(&v715 + 4 * v24) = 131080;
    *(&v716 + 4 * v345) = 1;
    v718[4 * v345] = 0;
    v718[4 * v345 - 1] = &v393;
    v24 = ++v345;
  }
  if ( (v349 & 0x4000000) != 0 )
  {
    v573 = 1;
    *(&v715 + 4 * v24) = 131081;
    *(&v716 + 4 * v345) = 4;
    v718[4 * v345] = 0;
    v718[4 * v345 - 1] = &v573;
    v24 = ++v345;
  }
  if ( (v349 & 0x400000) != 0 )
  {
    *(&v715 + 4 * v24) = 131090;
    *(&v716 + 4 * v345) = 8;
    v718[4 * v345] = 0;
    v718[4 * v345++ - 1] = &v691;
  }
  v25 = v348;
  *(_OWORD *)v348 = 0;
  *(_QWORD *)(v25 + 16) = 0;
  if ( v411 && (v349 & 0x400) == 0 )
  {
    v26 = RtlCreateEnvironmentEx(v411, &v579, 1);
    v347 = v26;
    if ( v26 < 0 )
    {
      BaseSetLastNTError((unsigned int)v26);
      local_unwind_1(v672, &loc_180087E66);
    }
    v411 = v579;
    v349 |= 0x400u;
  }
  v27 = *(__m128i *)v17;
  Buf1 = *(__m128i *)v17;
  v658 = *(_OWORD *)(v17 + 16);
  v659 = *(_OWORD *)(v17 + 32);
  v660 = *(_OWORD *)(v17 + 48);
  v661 = *(_OWORD *)(v17 + 64);
  v662 = *(_OWORD *)(v17 + 80);
  v663 = *(_QWORD *)(v17 + 96);
  if ( (v349 & 0x80000) != 0 )
  {
    if ( _mm_cvtsi128_si32(v27) != 112 )
    {
LABEL_55:
      v28 = 3221225485LL;
LABEL_56:
      BaseSetLastNTError(v28);
      goto LABEL_57;
    }
    v30 = *(_DWORD **)(v17 + 104);
    v482 = v30;
    if ( v30 )
    {
      v343 = 30;
      ExePath = BasepConvertWin32AttributeList(
                  (_DWORD)v30,
                  0,
                  (unsigned int)&v494,
                  (unsigned int)&v490,
                  (__int64)&v505,
                  (__int64)v416,
                  (__int64)&ProcessHandle,
                  (__int64)&v664,
                  (__int64)&v687,
                  (__int64)&v693,
                  (__int64)&v581,
                  (__int64)&v564,
                  (__int64)&v590,
                  (__int64)&v584,
                  (__int64)&v585,
                  (__int64)&v478,
                  (__int64)&v572,
                  (__int64)v674,
                  (__int64)&v673,
                  (__int64)&v649,
                  (__int64)&v691,
                  (__int64)&v350,
                  (__int64)&v714,
                  (__int64)&v345);
      v347 = ExePath;
      if ( ExePath < 0 )
      {
LABEL_60:
        v28 = (unsigned int)ExePath;
        goto LABEL_56;
      }
      if ( (unsigned int)Feature_Win32alacarteSupport_PROC_THREAD_ATTRIBUTE_JOB_LIST__private_IsEnabledDeviceUsageNoInline()
        && v572
        && (unsigned int)ShouldAvoidInlineJobListAssignment(v547) )
      {
        v602 = ExtractJobListAttribute(&v714, &v345, &v637);
        Parameters[3] = v602;
      }
      v32 = *v30;
      if ( (*v30 & 0x100LL) != 0 )
      {
        v352 = 1;
        v529 = 1;
        if ( v505 )
          goto LABEL_55;
      }
      v33 = (*(_QWORD *)&v32 & 0x80000LL) == 0;
      v34 = v502;
      if ( !v33 )
        v34 = 1;
      v502 = v34;
      v611 = v34;
      if ( (v494 & 4) != 0 )
        v350 |= 0x400u;
      if ( (*v30 & 0x20000000) != 0 )
        v349 |= 0x400000u;
    }
  }
  if ( (v349 & 0x800) == 0 )
  {
    v35 = -1;
    if ( ProcessHandle )
      v35 = (__int64)ProcessHandle;
    if ( IsProcessInJob((HANDLE)v35, 0, &Result) && Result )
      v349 = v349 & 0xFFFFE7FF | 0x800;
  }
  if ( (WORD6(v660) & 0x100) != 0 && (WORD6(v660) & 0x600) != 0 )
    HIDWORD(v660) &= ~0x100u;
  v36 = FileName;
  if ( FileName )
  {
    Heap = RtlAllocateHeap(ProcessHeap, 0, 0x206u);
    v536 = Heap;
    if ( !Heap )
    {
LABEL_84:
      v28 = 3221225495LL;
      goto LABEL_56;
    }
    InputPathType = RtlPathTypeUnknown;
    FullPathName_UEx = RtlGetFullPathName_UEx(v36, 0x206u, (PWSTR)Heap, &FilePart, &InputPathType);
    if ( FullPathName_UEx < 0 )
      BaseSetLastNTError((unsigned int)FullPathName_UEx);
    if ( (unsigned int)InputPathType >> 1 >= 0x104 )
    {
LABEL_88:
      v39 = 267;
      goto LABEL_89;
    }
    if ( !((unsigned int)InputPathType >> 1) )
      goto LABEL_57;
    FileName = (PWSTR)Heap;
    v641 = Heap;
  }
  ExePath = BaseFormatObjectAttributes(v676, v496, 0, &v632);
  v347 = ExePath;
  if ( ExePath < 0 )
    goto LABEL_60;
  ExePath = BaseFormatObjectAttributes(v677, v492, 0, &v631);
  v347 = ExePath;
  if ( ExePath < 0 )
    goto LABEL_60;
  v40 = v345;
  v417 = v345;
  v41 = lpFileName;
  v484 = lpFileName;
  v42 = pszSrc;
  v476 = pszSrc;
  v43 = v411;
  v485 = v411;
  v44 = v418;
  while ( 1 )
  {
    v345 = v40;
    if ( !a6 || (v407 = 1, v416[0]) )
      v407 = 0;
    v419 = v534;
    v532 = v534;
    v411 = v43;
    if ( v409 && *(_DWORD *)(v409 + 548) != 1 )
    {
      v45 = *(void **)(v409 + 552);
LABEL_104:
      v419 = v45;
      v532 = v45;
      goto LABEL_107;
    }
    if ( v357 && *(_DWORD *)(v357 + 32) != 1 )
    {
      v45 = *(void **)(v357 + 16);
      goto LABEL_104;
    }
    if ( v44 )
    {
      lpFileName = v41;
      pszSrc = v42;
      v419 = v44;
      v532 = v44;
    }
LABEL_107:
    if ( (unsigned int)Feature_AlwaysUseAppxExtensionForPackagedProcesses__private_IsEnabledDeviceUsageNoInline()
      && v413 )
    {
      lpFileName = v41;
      v46 = v476;
      pszSrc = v476;
    }
    else
    {
      v46 = v476;
    }
    if ( P )
    {
      if ( lpFileName == P )
        lpFileName = v41;
      RtlFreeHeap(ProcessHeap, 0, P);
      P = 0;
    }
    if ( v509 )
    {
      RtlFreeHeap(ProcessHeap, 0, v509);
      v509 = 0;
    }
    RtlFreeUnicodeString(&UnicodeString);
    if ( v576 )
    {
      if ( pszSrc == v576 )
        pszSrc = v46;
      RtlFreeHeap(ProcessHeap, 0, v576);
      v576 = 0;
    }
    if ( Handle )
    {
      NtClose(Handle);
      Handle = 0;
    }
    if ( v503 )
    {
      NtClose(v503);
      v503 = 0;
    }
    if ( Environment )
    {
      RtlDestroyEnvironment(Environment);
      Environment = 0;
    }
    v48 = v420;
    if ( v420 )
    {
      if ( v575 )
      {
        BasepReleaseAppXContext();
        v48 = v420;
      }
      v575 = v48;
      v420 = 0;
    }
    if ( v548 )
    {
      NtClose(v548);
      v548 = 0;
    }
    if ( ThreadHandle[0] )
    {
      if ( DebugObject )
        NtRemoveProcessDebug(Process, DebugObject);
      NtTerminateProcess(Process, -1073741267);
      NtWaitForSingleObject(Process, 0, 0);
      NtClose(ThreadHandle[0]);
      ThreadHandle[0] = 0;
    }
    v49 = Process;
    if ( Process )
    {
      NtClose(Process);
      Process = 0;
    }
    if ( (unsigned __int8)IsBasepProcessInvalidImagePresent(v49, v47) )
    {
      BasepFreeAppCompatData(v504, v507, v500);
      v504 = 0;
      NumberOfBytesToWrite = 0;
      v507 = 0;
      v488 = 0;
      v500 = 0;
      v479 = 0;
    }
    if ( (unsigned __int8)IsBasepFreeAppCompatData2Present() )
    {
      BasepFreeAppCompatData2(v583);
      v583 = 0;
    }
    if ( !v410 && (unsigned __int8)IsBasepProcessInvalidImagePresent(v51, v50) )
    {
      BasepReleaseSxsCreateProcessUtilityStruct(v682);
      memset_0(v682, 0, 0x58u);
    }
    if ( CaptureBuffer )
    {
      CsrFreeCaptureBuffer(CaptureBuffer);
      CaptureBuffer = 0;
    }
    BasepFreeBnoIsolationParameter(&v585);
    v52 = 0;
    v467 = 0;
    v53 = 0;
    v470 = 0;
    v512 = 1;
    if ( !lpFileName )
    {
      P = RtlAllocateHeap(ProcessHeap, 0, 0x208u);
      if ( !P )
        goto LABEL_84;
      LastErrorValue = 0;
      v589 = 0;
      v55 = pszSrc;
      lpFileName = pszSrc;
      v56 = pszSrc;
      v422 = pszSrc;
      v553 = pszSrc;
      v57 = pszSrc;
      v580 = pszSrc;
      if ( *pszSrc == 34 )
      {
        v58 = 0;
        v469 = 0;
        v57 = pszSrc + 1;
        v580 = pszSrc + 1;
        lpFileName = pszSrc + 1;
        while ( 1 )
        {
          if ( !*v57 )
            goto LABEL_164;
          if ( *v57 == 34 )
            break;
          v580 = ++v57;
          v56 = v57;
          v422 = v57;
          v553 = v57;
        }
        v553 = v57;
        v512 = 0;
LABEL_163:
        v422 = v57;
        v56 = v57;
        goto LABEL_164;
      }
      v58 = 1;
      v469 = 1;
      while ( 1 )
      {
        lpFileName = v55;
        while ( *v57 )
        {
          if ( *v57 == 32 || *v57 == 9 )
          {
            v553 = v57;
            goto LABEL_163;
          }
          v580 = ++v57;
          v56 = v57;
          v422 = v57;
          v553 = v57;
        }
LABEL_164:
        v415 = *v56;
        v541 = v415;
        *v56 = 0;
        if ( lpPath )
        {
          RtlReleasePath();
          lpPath = 0;
        }
        ExePath = RtlGetExePath(lpFileName, &lpPath);
        v347 = ExePath;
        if ( ExePath < 0 )
          goto LABEL_60;
        v59 = SearchPathW(lpPath, lpFileName, L".exe", 0x104u, (LPWSTR)P, 0);
        ReturnLength = v59;
        if ( v59 )
        {
          if ( v59 >= 0x104 )
          {
            v60 = 3221225734LL;
LABEL_170:
            BaseSetLastNTError(v60);
            goto LABEL_171;
          }
          FileAttributesW = GetFileAttributesW((LPCWSTR)P);
          if ( FileAttributesW != -1 )
          {
            if ( (FileAttributesW & 0x10) == 0 )
            {
              v23 = (wchar_t *)v422;
              *v422 = v415;
              lpFileName = (LPCWSTR)P;
              v62 = pszSrc;
              ProcessHeap = HeapHandle;
              goto LABEL_184;
            }
            v60 = 3221225658LL;
            goto LABEL_170;
          }
        }
LABEL_171:
        if ( !LastErrorValue )
        {
          LastErrorValue = NtCurrentTeb()->LastErrorValue;
          v589 = LastErrorValue;
        }
        *v422 = v415;
        if ( !*v57 || !v58 )
        {
          v39 = LastErrorValue;
          goto LABEL_89;
        }
        v580 = ++v57;
        v56 = v57;
        v422 = v57;
        v553 = v57;
        v52 = 1;
        v467 = 1;
        v512 = 0;
        v55 = pszSrc;
      }
    }
    v62 = pszSrc;
    if ( !pszSrc || !*pszSrc )
    {
      v53 = 1;
      v470 = 1;
      v62 = lpFileName;
      pszSrc = lpFileName;
    }
LABEL_184:
    if ( v52 || v53 )
    {
      v63 = 2 * wcslen(v62) + 6;
      v64 = (wchar_t *)RtlAllocateHeap(ProcessHeap, 0, v63);
      v65 = v64;
      v576 = v64;
      if ( v64 )
      {
        StringCbCopyW(v64, v63, L"\"");
        if ( v52 )
        {
          v415 = *v23;
          v541 = v415;
          *v23 = 0;
        }
        StringCbCatW(v65, v63, pszSrc);
        StringCbCatW(v65, v63, L"\"");
        if ( v52 )
        {
          *v23 = v415;
          StringCbCatW(v65, v63, v23);
        }
        pszSrc = v65;
      }
    }
    if ( !RtlDosPathNameToNtPathName_U(lpFileName, &UnicodeString, 0, 0) )
    {
      v39 = 3;
      goto LABEL_89;
    }
    ExePath = RtlInitUnicodeStringEx(&DestinationString, lpFileName);
    v66 = ExePath;
    v347 = ExePath;
    if ( ExePath < 0 )
      goto LABEL_60;
    v67 = RtlDetermineDosPathNameType_U(lpFileName);
    v568 = v67;
    if ( (unsigned int)(v67 - 1) > 1 && (unsigned int)(v67 - 6) > 1
      || !(unsigned int)BasepAdjustApplicationPath(&DestinationString) )
    {
      *(_QWORD *)&DynamicString.Length = 0;
      DynamicString.Buffer = 0;
      ExePath = RtlGetFullPathName_UstrEx(&DestinationString, 0, &DynamicString, 0, 0, 0, &v568, 0);
      v66 = ExePath;
      v347 = ExePath;
      if ( ExePath < 0 )
        goto LABEL_60;
      DestinationString = DynamicString;
      v509 = (PVOID)_mm_srli_si128((__m128i)DynamicString, 8).m128i_u64[0];
      DynamicString.Buffer = 0;
    }
    if ( (v478 & 3) == 3 )
      goto LABEL_55;
    v68 = v547;
    if ( (v547->BitField & 0x10) != 0 && !v357 && !v409 )
    {
      v543 = 720897;
      if ( (int)AppModelPolicy_GetProcessPolicy_ImplicitPackageBreakaway(-6, &v543) >= 0
        && (v543 == 720896 && (v478 & 6) == 0 || v543 == 720898 && (v478 & 5) == 1) )
      {
        if ( (unsigned __int8)IsCheckAppXPackageBreakawayPresent() )
        {
          v66 = CheckAppXPackageBreakaway(DestinationString.Buffer, &v464);
          v347 = v66;
          if ( v66 < 0 )
            v464 = 0;
        }
        else
        {
          v66 = -1073741823;
          v347 = -1073741823;
        }
      }
      if ( v66 < 0 )
        goto LABEL_214;
      v567 = 2424832;
      v651 = 0;
      v652 = 0;
      if ( (int)AppModelPolicy_GetPolicy_Internal(-6, 37, (unsigned int)&v567, (unsigned int)&v652, (__int64)&v651) < 0 )
      {
        v66 = -1073741823;
        v347 = -1073741823;
      }
      else if ( v567 == 2424833 )
      {
        v516 = 1;
        v644 = 1;
      }
      if ( v66 < 0 )
        goto LABEL_214;
    }
    if ( (unsigned int)Feature_EnableRunningHostedAppsWithAEA__private_IsEnabledDeviceUsageNoInline() )
    {
      if ( v357 )
      {
        if ( !*(_DWORD *)(v357 + 32) )
        {
          v70 = *(_WORD **)(v357 + 56);
          if ( v70 )
          {
            if ( *v70 )
            {
              v566 = 4;
              v720 = 131097;
              v721 = 4;
              v723 = 0;
              v722 = (struct _UNICODE_STRING *)&v566;
              BasepAddToOrUpdateAttributesList(v719, 1, &v714, &v345, 30);
            }
          }
        }
      }
    }
    if ( v464 || !v490.Length && ((v68->BitField & 0x10) == 0 || v516) )
      goto LABEL_250;
    if ( (unsigned __int8)IsBasepProcessInvalidImagePresent(v70, v69) )
      ExePath = BasepAppXExtension(v419, &v490, v505, v411, &v420, &Environment);
    else
      ExePath = -1073741823;
    v347 = ExePath;
    if ( ExePath < 0 )
    {
      v420 = 0;
      Environment = 0;
      goto LABEL_60;
    }
    IsEnabledDeviceUsageNoInline = Feature_AlwaysUseAppxExtensionForPackagedProcesses__private_IsEnabledDeviceUsageNoInline();
    v72 = (unsigned __int8)v515;
    if ( IsEnabledDeviceUsageNoInline )
      v72 = 1;
    v515 = v72;
    v530 = v72;
    if ( Environment )
      v411 = Environment;
    if ( !v420 )
    {
      *(_QWORD *)&v490.Length = 0;
      v490.Buffer = 0;
LABEL_250:
      v74 = FileName;
      goto LABEL_251;
    }
    RtlInitUnicodeString(&v490, *(PCWSTR *)(v420 + 24));
    v73 = v420;
    if ( *(_QWORD *)v420 )
      v505 = *(_QWORD **)v420;
    if ( !*(_QWORD *)(v420 + 16) || v357 || v409 && *(_BYTE *)(v409 + 544) )
      goto LABEL_250;
    if ( v536 )
    {
      RtlFreeHeap(ProcessHeap, 0, v536);
      v536 = 0;
      v73 = v420;
    }
    v74 = *(WCHAR **)(v73 + 16);
    FileName = v74;
    v641 = v74;
LABEL_251:
    ExePath = GetEmbeddedImageMitigationPolicy(v674, &v687, &v581, &v565);
    v347 = ExePath;
    if ( v565 )
    {
      if ( ExePath < 0 )
        goto LABEL_60;
      v720 = 131088;
      v721 = 24;
      v723 = 0;
      v722 = (struct _UNICODE_STRING *)&v687;
      v75 = 1;
      v483 = 1;
      if ( HIDWORD(v581) )
      {
        v724 = 131094;
        v725 = 8;
        v727 = 0;
        v726 = &v581;
        v75 = 2;
        v483 = 2;
      }
      BasepAddToOrUpdateAttributesList(v719, v75, &v714, &v345, 30);
    }
    if ( v564 )
    {
      v688 &= 0xFFFFFFFFCFFFFFFFuLL;
      v688 |= 0x10000000uLL;
      v483 = 1;
      v720 = 131088;
      v721 = 24;
      v723 = 0;
      v722 = (struct _UNICODE_STRING *)&v687;
      BasepAddToOrUpdateAttributesList(v719, 1, &v714, &v345, 30);
    }
    v76 = v419;
    if ( v505 )
    {
      ExePath = BasepCreateLowBox(v419);
      v347 = ExePath;
      if ( ExePath < 0
        || ((v582 = 0, !(unsigned __int8)IsBasepProcessInvalidImagePresent(v78, v77))
          ? (ExePath = 0)
          : (ExePath = BasepAppContainerEnvironmentExtension(*v505, v411, &v582)),
            v347 = ExePath,
            ExePath < 0) )
      {
        v503 = 0;
        goto LABEL_60;
      }
      if ( v503 )
        v76 = v503;
      v419 = v76;
      v532 = v76;
      v79 = v582;
      if ( v582 )
      {
        if ( Environment )
        {
          RtlDestroyEnvironment(Environment);
          v79 = v582;
        }
        Environment = v79;
        v411 = v79;
      }
    }
    if ( v487 )
    {
      v720 = 131096;
      v721 = 40;
      v723 = 0;
      v722 = &v585;
      BasepAddToOrUpdateAttributesList(v719, 1, &v714, &v345, 30);
      v80 = 1;
      v502 = 1;
      v611 = 1;
    }
    else
    {
      v80 = v502;
    }
    if ( v80 )
    {
      if ( v505 || (NtCurrentPeb()->BitField & 0x20) != 0 )
      {
        v28 = 3221225659LL;
        goto LABEL_56;
      }
      if ( *((_QWORD *)&v586 + 1) )
        goto LABEL_282;
      if ( !(_BYTE)v587 )
      {
        ExePath = 0;
        goto LABEL_283;
      }
      if ( !v585.Buffer )
LABEL_282:
        ExePath = -1073741811;
      else
        ExePath = BasepCreateBnoIsolationObjectDirectories(v76);
LABEL_283:
      v347 = ExePath;
      if ( ExePath < 0 )
        goto LABEL_60;
    }
    if ( v74 )
    {
      v81 = GetFileAttributesW(v74);
      if ( v81 == -1 || (v81 & 0x10) == 0 )
        goto LABEL_88;
    }
    if ( v76 )
    {
      *(&v715 + 4 * v345) = 393218;
      *(&v716 + 4 * v345) = 8;
      v718[4 * v345] = 0;
      v718[4 * v345++ - 1] = v76;
    }
    if ( v420 && (*(_BYTE *)(v420 + 80) & 1) != 0 )
    {
      if ( (unsigned __int8)IsBasepCheckPplSupportPresent() )
      {
        ExePath = BasepCheckPplSupport(DestinationString.Buffer, &v544);
        v347 = ExePath;
        if ( ExePath < 0 )
          goto LABEL_60;
      }
      if ( v544 )
      {
        *(&v715 + 4 * v345) = 393233;
        *(&v716 + 4 * v345) = 1;
        v718[4 * v345] = 0;
        v718[4 * v345++ - 1] = 129;
        v350 |= 0x40u;
      }
    }
    if ( a6 )
      v350 |= 4u;
    else
      v350 &= ~4u;
    memset_0(&v616, 0, 0x58u);
    v616 = 88;
    v82 = v410;
    v83 = v407;
    if ( !v410 )
    {
      if ( !v407 && (WORD6(v660) & 0x100) == 0 && !ProcessHandle && (v349 & 0x8000018) == 0 )
      {
        HIDWORD(v489) = 3;
        LODWORD(v489) = v489 & 0xFFFFFFE0 | 1;
        *(&v715 + 4 * v345) = 131082;
        *(&v716 + 4 * v345) = 8;
        v718[4 * v345] = 0;
        v718[4 * v345++ - 1] = &v489;
        v82 = v410;
      }
      if ( !v82 && !v83 && (WORD6(v660) & 0x100) != 0 && ProcessHandle )
      {
        HIDWORD(v489) = 3;
        LODWORD(v489) = v489 & 0xFFFFFFE0 | 2;
        *(&v715 + 4 * v345) = 131082;
        *(&v716 + 4 * v345) = 8;
        v718[4 * v345] = 0;
        v718[4 * v345++ - 1] = &v489;
      }
    }
    if ( (v349 & 3) == 0 || v547->ReadImageFileExecOptions )
    {
      if ( v395 )
      {
        v395 = 0;
        v471 = 0;
        LOBYTE(KeyHandle) = (unsigned __int8)KeyHandle | 4;
      }
    }
    else
    {
      LOBYTE(KeyHandle) = (unsigned __int8)KeyHandle | 0xC;
    }
    LOBYTE(KeyHandle) = (unsigned __int8)KeyHandle | 1;
    WORD1(KeyHandle) = 0x2000;
    HIDWORD(KeyHandle) = 129;
    if ( !(_QWORD)v658 )
      *(_QWORD *)&v658 = v547->ProcessParameters->DesktopInfo.Buffer;
    if ( !v420 || (v84 = *(_WORD **)(v420 + 24)) == 0 || !*v84 || (*(_BYTE *)(v420 + 80) & 4) != 0 )
      LOBYTE(KeyHandle) = (unsigned __int8)KeyHandle | 2;
    RtlWow64GetProcessMachines(-1, &v542, v424);
    LOWORD(v359) = 48;
    BYTE2(v359) = 18;
    *(_WORD *)((char *)&v359 + 3) = -11264;
    WORD3(v359) = 40;
    BYTE8(v359) = 18;
    *(_DWORD *)((char *)&v359 + 9) = 0;
    *(_WORD *)((char *)&v359 + 13) = 0;
    HIBYTE(v359) = 0;
    *(_QWORD *)&v360 = 0;
    *((_QWORD *)&v360 + 1) = 0x80000000LL;
    LODWORD(v361) = 0x2000000;
    BYTE4(v361) = 108;
    BYTE5(v361) = BYTE5(v361) & 0xF0 | 3;
    *((_QWORD *)&v361 + 1) = 0;
    v85 = 87;
    v408 = 87;
    if ( v424[0] == 0xAA64 )
    {
      if ( !(unsigned __int8)IsBasepFreeAppCompatData2Present()
        || (v85 = BasepQueryModuleChpeSettings2(
                    &v583,
                    DestinationString.Buffer,
                    v634,
                    v411,
                    &v490,
                    &v500,
                    &v479,
                    &v507,
                    &v488,
                    &v533),
            (v408 = v85) != 0) )
      {
LABEL_496:
        if ( (BYTE9(v361) & 0x40) == 0 && (unsigned __int8)IsBasepProcessInvalidImagePresent(v87, v86) )
        {
          v85 = BasepQueryModuleChpeSettings(
                  &v683,
                  32,
                  DestinationString.Buffer,
                  v634,
                  v411,
                  &v490,
                  &v500,
                  &v479,
                  &v507,
                  &v488,
                  &v533);
          v408 = v85;
          if ( v85 )
          {
            *(_QWORD *)&v683 = 0;
            *((_QWORD *)&v683 + 1) = 0x80000000LL;
            LODWORD(v684) = 0x2000000;
            v143 = 108;
            BYTE4(v684) = 108;
            BYTE5(v684) = BYTE5(v684) & 0xF0 | 3;
            *((_QWORD *)&v684 + 1) = 0;
          }
          else
          {
            v143 = BYTE4(v684);
          }
          if ( (BYTE9(v684) & 0x40) != 0 )
          {
            LOWORD(v359) = 48;
            BYTE2(v359) = 18;
            *(_WORD *)((char *)&v359 + 3) = -11264;
            WORD3(v359) = 40;
            BYTE8(v359) = 18;
            *(_DWORD *)((char *)&v359 + 9) = 0;
            *(_WORD *)((char *)&v359 + 13) = 0;
            HIBYTE(v359) = 0;
            *(_QWORD *)&v360 = 0;
            *((_QWORD *)&v360 + 1) = 0x80000000LL;
            LODWORD(v361) = 0x2000000;
            v144 = 2;
            v145 = 108;
            BYTE4(v361) = 108;
            v146 = BYTE5(v361) & 0xF0 | 3;
            BYTE5(v361) = v146;
            *((_QWORD *)&v361 + 1) = 0;
            v147 = 0;
            if ( (BYTE8(v684) & 1) != 0 )
              v147 = v683;
            *(_QWORD *)&v360 = v147;
            BYTE8(v361) = BYTE8(v684) & 1;
            v148 = 0x80000000;
            if ( (BYTE8(v684) & 2) != 0 )
              v148 = DWORD2(v683);
            DWORD2(v360) = v148;
            BYTE8(v361) = BYTE8(v684) & 3;
            v149 = 0;
            if ( (BYTE8(v684) & 4) != 0 )
              v149 = HIDWORD(v683);
            HIDWORD(v360) = v149;
            BYTE8(v361) = BYTE8(v684) & 7;
            v150 = 0;
            if ( (BYTE8(v684) & 8) != 0 )
              v150 = v684;
            LOWORD(v361) = v150;
            BYTE8(v361) = BYTE8(v684) & 0xF;
            v151 = 0;
            if ( (BYTE8(v684) & 0x10) != 0 )
              v151 = BYTE2(v684);
            BYTE2(v361) = v151;
            BYTE8(v361) = BYTE8(v684) & 0x1F;
            if ( (BYTE8(v684) & 0x20) != 0 )
            {
              v144 = BYTE3(v684) & 0xF;
              BYTE3(v361) = BYTE3(v684) & 0xF;
            }
            BYTE8(v361) = BYTE8(v684) & 0x3F;
            if ( (BYTE8(v684) & 0x40) != 0 )
              BYTE3(v361) = v144 & 0xF | BYTE3(v684) & 0xF0;
            BYTE8(v361) = BYTE8(v684) & 0x7F;
            if ( SBYTE8(v684) < 0 )
            {
              v145 = v143 & 3 | 0x6C;
              BYTE4(v361) = v145;
            }
            BYTE8(v361) = BYTE8(v684);
            if ( (BYTE9(v684) & 1) != 0 )
            {
              v145 = v145 & 0xFB | v143 & 4;
              BYTE4(v361) = v145;
            }
            v152 = BYTE9(v684) & 1 | BYTE9(v361) & 0xFE;
            BYTE9(v361) = v152;
            if ( (BYTE9(v684) & 2) != 0 )
            {
              v145 = v145 & 0xF7 | v143 & 8;
              BYTE4(v361) = v145;
            }
            v153 = v152 & 0xFD;
            BYTE9(v361) = v153 | BYTE9(v684) & 2;
            if ( (BYTE9(v684) & 4) != 0 )
            {
              v145 = v145 & 0xEF | v143 & 0x10;
              BYTE4(v361) = v145;
            }
            BYTE9(v361) = v153 & 0xFB | BYTE9(v684) & 2 | BYTE9(v684) & 4;
            if ( (BYTE9(v684) & 8) != 0 )
            {
              v145 = v145 & 0xDF | v143 & 0x20;
              BYTE4(v361) = v145;
            }
            BYTE9(v361) = v153 & 0xF3 | BYTE9(v684) & 2 | BYTE9(v684) & 4 | BYTE9(v684) & 8;
            if ( (BYTE9(v684) & 0x10) != 0 )
            {
              v145 = v145 & 0xBF | v143 & 0x40;
              BYTE4(v361) = v145;
            }
            v154 = v153 & 0xE3 | BYTE9(v684) & 2 | BYTE9(v684) & 4 | BYTE9(v684) & 8 | BYTE9(v684) & 0x10;
            BYTE9(v361) = v154;
            if ( (BYTE9(v684) & 0x20) != 0 )
              BYTE4(v361) = v145 & 0x7F | v143 & 0x80;
            v155 = v153 & 0xC3
                 | BYTE9(v684) & 2
                 | BYTE9(v684) & 4
                 | BYTE9(v684) & 8
                 | BYTE9(v684) & 0x10
                 | BYTE9(v684) & 0x20;
            BYTE9(v361) = v154 & 0xDF | BYTE9(v684) & 0x20;
            if ( (BYTE9(v684) & 0x40) != 0 )
            {
              v146 = v146 & 0xFE | BYTE5(v684) & 1;
              BYTE5(v361) = v146;
            }
            v156 = v155 & 0xBF;
            BYTE9(v361) = v156 | BYTE9(v684) & 0x40;
            if ( SBYTE9(v684) < 0 )
            {
              v146 = v146 & 0xFD | BYTE5(v684) & 2;
              BYTE5(v361) = v146;
            }
            BYTE9(v361) = v156 & 0x7F | BYTE9(v684) & 0x40 | BYTE9(v684) & 0x80;
            if ( (BYTE10(v684) & 1) != 0 )
            {
              v146 = v146 & 0xFB | BYTE5(v684) & 4;
              BYTE5(v361) = v146;
            }
            v157 = BYTE10(v684) & 1 | BYTE10(v361) & 0xFE;
            BYTE10(v361) = v157;
            if ( (BYTE10(v684) & 2) != 0 )
              BYTE5(v361) = v146 & 0xF7 | BYTE5(v684) & 8;
            BYTE10(v361) = v157 & 0xFD | BYTE10(v684) & 2;
          }
        }
        if ( !v85 && (v533 & 0x800000000LL) != 0 )
        {
          *(_QWORD *)&v687 = v687 & 0xFFFFFCFFFFFFFFFFuLL | 0x20000000000LL;
          v720 = 131088;
          v721 = 24;
          v723 = 0;
          v722 = (struct _UNICODE_STRING *)&v687;
          v483 = 1;
          BasepAddToOrUpdateAttributesList(v719, 1, &v714, &v345, 30);
        }
        v74 = FileName;
        goto LABEL_543;
      }
      v86 = v583;
      v455 = 0;
      v445 = 0x2800D400120030LL;
      v446 = 18;
      v447 = 0;
      v448 = 0;
      v449 = 0;
      v450 = 0;
      v451 = 0x80000000LL;
      v452 = 0;
      v453 = 0;
      v454 = 224258;
      v456 = 0;
      LOWORD(v359) = 48;
      BYTE2(v359) = 18;
      *(_WORD *)((char *)&v359 + 3) = -11264;
      WORD3(v359) = 40;
      BYTE8(v359) = 18;
      *(_DWORD *)((char *)&v359 + 9) = 0;
      *(_WORD *)((char *)&v359 + 13) = 0;
      HIBYTE(v359) = 0;
      *(_QWORD *)&v360 = 0;
      *((_QWORD *)&v360 + 1) = 0x80000000LL;
      LODWORD(v361) = 0x2000000;
      v88 = 2;
      v89 = 108;
      BYTE4(v361) = 108;
      v90 = BYTE5(v361) & 0xF0 | 3;
      BYTE5(v361) = v90;
      *((_QWORD *)&v361 + 1) = 0;
      LOBYTE(v87) = 1;
      if ( *(_BYTE *)(v583 + 2) >> 4 == 1 )
      {
        LOBYTE(v87) = -44;
        if ( !*(_BYTE *)(v583 + 3) )
        {
          if ( *(_BYTE *)(v583 + 8) != 18 || *(_WORD *)v583 != 48 || *(_BYTE *)(v583 + 4) != 0xD4 )
            goto LABEL_495;
          if ( !*(_BYTE *)(v583 + 3) )
            goto LABEL_332;
        }
        if ( *(_BYTE *)(v583 + 8) != 18 )
        {
LABEL_332:
          v91 = *(unsigned __int16 *)(v583 + 6) - 40LL;
          if ( !*(_BYTE *)(v583 + 8) || (v92 = 1, (*(_BYTE *)(*(unsigned __int16 *)(v583 + 6) + v583) & 1) == 0) )
            v92 = 0;
          if ( v92 )
            *(_QWORD *)&v360 = *(_QWORD *)(v583 + 16);
          v93 = *(_BYTE *)(v583 + 8) && (*(_BYTE *)(v91 + v583 + 40) & 1) != 0;
          v94 = v93 | BYTE8(v361) & 0xFE;
          BYTE8(v361) = v94;
          if ( *(_BYTE *)(v583 + 8) < 2u || (v95 = 1, (*(_BYTE *)(v91 + v583 + 40) & 2) == 0) )
            v95 = 0;
          v33 = v95 == 0;
          v96 = 2;
          if ( !v33 )
          {
            DWORD2(v360) = *(_DWORD *)(v583 + 24);
            v96 = 2;
          }
          if ( *(_BYTE *)(v583 + 8) < 2u || (*(_BYTE *)(v91 + v583 + 40) & 2) == 0 )
            v96 = 0;
          v97 = v96 | v94 & 0xFD;
          BYTE8(v361) = v97;
          if ( *(_BYTE *)(v583 + 8) < 3u || (v98 = 1, (*(_BYTE *)(v91 + v583 + 40) & 4) == 0) )
            v98 = 0;
          if ( v98 )
            HIDWORD(v360) = *(_DWORD *)(v583 + 28);
          if ( *(_BYTE *)(v583 + 8) >= 3u && (*(_BYTE *)(v91 + v583 + 40) & 4) != 0 )
            v99 = 4;
          else
            v99 = 0;
          v100 = v99 | v97 & 0xFB;
          BYTE8(v361) = v100;
          if ( *(_BYTE *)(v583 + 8) < 4u || (v101 = 1, (*(_BYTE *)(v91 + v583 + 40) & 8) == 0) )
            v101 = 0;
          if ( v101 )
            LOWORD(v361) = *(_WORD *)(v583 + 32);
          if ( *(_BYTE *)(v583 + 8) >= 4u && (*(_BYTE *)(v91 + v583 + 40) & 8) != 0 )
            v102 = 8;
          else
            v102 = 0;
          v103 = v102 | v100 & 0xF7;
          BYTE8(v361) = v103;
          if ( *(_BYTE *)(v583 + 8) < 5u || (v104 = 1, (*(_BYTE *)(v91 + v583 + 40) & 0x10) == 0) )
            v104 = 0;
          if ( v104 )
            BYTE2(v361) = *(_BYTE *)(v583 + 34);
          if ( *(_BYTE *)(v583 + 8) >= 5u && (*(_BYTE *)(v91 + v583 + 40) & 0x10) != 0 )
            v105 = 16;
          else
            v105 = 0;
          v106 = v105 | v103 & 0xEF;
          BYTE8(v361) = v106;
          if ( *(_BYTE *)(v583 + 8) < 6u || (v107 = 1, (*(_BYTE *)(v91 + v583 + 40) & 0x20) == 0) )
            v107 = 0;
          if ( v107 )
          {
            v88 = *(_BYTE *)(v583 + 35) & 0xF;
            BYTE3(v361) = v88;
          }
          if ( *(_BYTE *)(v583 + 8) >= 6u && (*(_BYTE *)(v91 + v583 + 40) & 0x20) != 0 )
            v108 = 32;
          else
            v108 = 0;
          v109 = v108 | v106 & 0xDF;
          BYTE8(v361) = v109;
          if ( *(_BYTE *)(v583 + 8) < 7u || (v110 = 1, (*(_BYTE *)(v91 + v583 + 40) & 0x40) == 0) )
            v110 = 0;
          if ( v110 )
            BYTE3(v361) = v88 & 0xF | (16 * (*(_BYTE *)(v583 + 35) >> 4));
          if ( *(_BYTE *)(v583 + 8) >= 7u && (*(_BYTE *)(v91 + v583 + 40) & 0x40) != 0 )
            v111 = 64;
          else
            v111 = 0;
          v112 = v111 | v109 & 0xBF;
          BYTE8(v361) = v112;
          if ( *(_BYTE *)(v583 + 8) < 8u || (v113 = 1, *(char *)(v91 + v583 + 40) >= 0) )
            v113 = 0;
          if ( v113 )
          {
            v89 = *(_BYTE *)(v583 + 36) & 3 | 0x6C;
            BYTE4(v361) = v89;
          }
          if ( *(_BYTE *)(v583 + 8) < 8u || *(char *)(v91 + v583 + 40) >= 0 )
            v114 = 0;
          else
            v114 = 0x80;
          BYTE8(v361) = v114 | v112 & 0x7F;
          if ( *(_BYTE *)(v583 + 8) < 9u || (v115 = 1, (*(_BYTE *)(v91 + v583 + 41) & 1) == 0) )
            v115 = 0;
          if ( v115 )
          {
            v89 = v89 & 0xFB | (4 * ((*(_BYTE *)(v583 + 36) & 4) != 0));
            BYTE4(v361) = v89;
          }
          v116 = *(_BYTE *)(v583 + 8) >= 9u && (*(_BYTE *)(v91 + v583 + 41) & 1) != 0;
          v117 = v116 | BYTE9(v361) & 0xFE;
          BYTE9(v361) = v117;
          if ( *(_BYTE *)(v583 + 8) < 0xAu || (v118 = 1, (*(_BYTE *)(v91 + v583 + 41) & 2) == 0) )
            v118 = 0;
          if ( v118 )
          {
            v89 = v89 & 0xF7 | (8 * ((*(_BYTE *)(v583 + 36) & 8) != 0));
            BYTE4(v361) = v89;
          }
          if ( *(_BYTE *)(v583 + 8) >= 0xAu && (*(_BYTE *)(v91 + v583 + 41) & 2) != 0 )
            v119 = 2;
          else
            v119 = 0;
          v120 = v119 | v117 & 0xFD;
          BYTE9(v361) = v120;
          if ( *(_BYTE *)(v583 + 8) < 0xBu || (v121 = 1, (*(_BYTE *)(v91 + v583 + 41) & 4) == 0) )
            v121 = 0;
          if ( v121 )
          {
            v89 = v89 & 0xEF | (16 * ((*(_BYTE *)(v583 + 36) & 0x10) != 0));
            BYTE4(v361) = v89;
          }
          if ( *(_BYTE *)(v583 + 8) >= 0xBu && (*(_BYTE *)(v91 + v583 + 41) & 4) != 0 )
            v122 = 4;
          else
            v122 = 0;
          v123 = v122 | v120 & 0xFB;
          BYTE9(v361) = v123;
          if ( *(_BYTE *)(v583 + 8) < 0xCu || (v124 = 1, (*(_BYTE *)(v91 + v583 + 41) & 8) == 0) )
            v124 = 0;
          if ( v124 )
          {
            v89 = v89 & 0xDF | (32 * ((*(_BYTE *)(v583 + 36) & 0x20) != 0));
            BYTE4(v361) = v89;
          }
          if ( *(_BYTE *)(v583 + 8) >= 0xCu && (*(_BYTE *)(v91 + v583 + 41) & 8) != 0 )
            v125 = 8;
          else
            v125 = 0;
          v126 = v125 | v123 & 0xF7;
          BYTE9(v361) = v126;
          if ( *(_BYTE *)(v583 + 8) < 0xDu || (v127 = 1, (*(_BYTE *)(v91 + v583 + 41) & 0x10) == 0) )
            v127 = 0;
          if ( v127 )
          {
            v89 = v89 & 0xBF | (((*(_BYTE *)(v583 + 36) & 0x40) != 0) << 6);
            BYTE4(v361) = v89;
          }
          if ( *(_BYTE *)(v583 + 8) >= 0xDu && (*(_BYTE *)(v91 + v583 + 41) & 0x10) != 0 )
            v128 = 16;
          else
            v128 = 0;
          v129 = v128 | v126 & 0xEF;
          BYTE9(v361) = v129;
          if ( *(_BYTE *)(v583 + 8) < 0xEu || (v130 = 1, (*(_BYTE *)(v91 + v583 + 41) & 0x20) == 0) )
            v130 = 0;
          if ( v130 )
            BYTE4(v361) = v89 & 0x7F | (*(_BYTE *)(v583 + 36) >> 7 << 7);
          if ( *(_BYTE *)(v583 + 8) >= 0xEu && (*(_BYTE *)(v91 + v583 + 41) & 0x20) != 0 )
            v131 = 32;
          else
            v131 = 0;
          v132 = v131 | v129 & 0xDF;
          BYTE9(v361) = v132;
          if ( *(_BYTE *)(v583 + 8) < 0xFu || (v133 = 1, (*(_BYTE *)(v91 + v583 + 41) & 0x40) == 0) )
            v133 = 0;
          if ( v133 )
          {
            v90 = *(_BYTE *)(v583 + 37) & 1 | v90 & 0xFE;
            BYTE5(v361) = v90;
          }
          if ( *(_BYTE *)(v583 + 8) >= 0xFu && (*(_BYTE *)(v91 + v583 + 41) & 0x40) != 0 )
            v134 = 64;
          else
            v134 = 0;
          v135 = v134 | v132 & 0xBF;
          BYTE9(v361) = v135;
          if ( *(_BYTE *)(v583 + 8) < 0x10u || (v136 = 1, *(char *)(v91 + v583 + 41) >= 0) )
            v136 = 0;
          if ( v136 )
          {
            v90 = v90 & 0xFD | (2 * ((*(_BYTE *)(v583 + 37) & 2) != 0));
            BYTE5(v361) = v90;
          }
          if ( *(_BYTE *)(v583 + 8) < 0x10u || *(char *)(v91 + v583 + 41) >= 0 )
            v137 = 0;
          else
            v137 = 0x80;
          BYTE9(v361) = v137 | v135 & 0x7F;
          v87 = 0;
          if ( *(_BYTE *)(v583 + 8) < 0x11u || (v138 = 1, (*(_BYTE *)(v91 + v583 + 42) & 1) == 0) )
            v138 = 0;
          if ( v138 )
          {
            v87 = (*(unsigned __int8 *)(v583 + 37) >> 2) & 1;
            v90 = v90 & 0xFB | (4 * ((*(_BYTE *)(v583 + 37) & 4) != 0));
            BYTE5(v361) = v90;
          }
          v139 = *(_BYTE *)(v583 + 8) >= 0x11u && (*(_BYTE *)(v91 + v583 + 42) & 1) != 0;
          v140 = v139 | BYTE10(v361) & 0xFE;
          BYTE10(v361) = v140;
          if ( *(_BYTE *)(v583 + 8) < 0x12u || (v141 = 1, (*(_BYTE *)(v91 + v583 + 42) & 2) == 0) )
            v141 = 0;
          if ( v141 )
            BYTE5(v361) = v90 & 0xF7 | (8 * ((*(_BYTE *)(v583 + 37) & 8) != 0));
          if ( *(_BYTE *)(v583 + 8) >= 0x12u && (*(_BYTE *)(v91 + v583 + 42) & 2) != 0 )
            v142 = 2;
          else
            v142 = 0;
          LOBYTE(v87) = v142 | v140 & 0xFD;
          BYTE10(v361) = v87;
        }
      }
LABEL_495:
      v85 = v408;
      goto LABEL_496;
    }
LABEL_543:
    if ( v420 )
      v158 = *(_QWORD *)(v420 + 88);
    else
      v158 = 0;
    if ( v420 )
      v159 = *(_QWORD *)(v420 + 8);
    else
      v159 = 0;
    LODWORD(v342) = v407;
    LODWORD(v341) = v349;
    LOBYTE(PathType) = v490.Length != 0;
    v160 = (struct _RTL_USER_PROCESS_PARAMETERS *)BasepCreateProcessParameters(
                                                    lpFileName,
                                                    &DestinationString,
                                                    v74,
                                                    pszSrc,
                                                    v159,
                                                    v158,
                                                    PathType,
                                                    v411,
                                                    &Buf1,
                                                    v341,
                                                    v342,
                                                    v350 | (v464 != 0 ? 0x10000 : 0),
                                                    &v664,
                                                    ProcessHandle);
    if ( !v160 )
      goto LABEL_57;
    if ( v420 && (*(_BYTE *)(v420 + 80) & 2) != 0 )
      v160->Flags |= 0x8000000u;
    if ( v357 || v409 && *(_BYTE *)(v409 + 544) )
    {
      ProcessHeap = HeapHandle;
      if ( !FileName )
      {
        Length = v160->CurrentDirectory.DosPath.Length;
        v162 = RtlAllocateHeap(HeapHandle, 0, Length + 2);
        v536 = v162;
        if ( !v162 )
          goto LABEL_84;
        StringCbCopyW((STRSAFE_LPWSTR)v162, Length + 2, v160->CurrentDirectory.DosPath.Buffer);
        FileName = (PWSTR)v536;
        v641 = v536;
      }
    }
    else
    {
      ProcessHeap = HeapHandle;
    }
    *(&v715 + 4 * v345) = 393242;
    *(&v716 + 4 * v345) = 1;
    v718[4 * v345] = 0;
    v163 = QueryChpeConfiguration(&UnicodeString, BYTE5(v361) & 1);
    v718[4 * v345++ - 1] = v163;
    v717 = UnicodeString.Buffer;
    v716 = UnicodeString.Length;
    v714 = 32LL * v345 + 8;
    if ( !v409 || *(_DWORD *)(v409 + 548) == 1 )
    {
      if ( v357 && *(_DWORD *)(v357 + 32) != 1 )
      {
        if ( NtCurrentTeb()->IsImpersonating )
        {
          ExePath = NtOpenThreadToken((HANDLE)0xFFFFFFFFFFFFFFFELL, 0xCu, 1u, &TokenHandle);
          if ( ExePath < 0 )
            goto LABEL_60;
        }
        if ( !ImpersonateLoggedOnUser(*(HANDLE *)(v357 + 16)) )
        {
LABEL_565:
          v164 = TokenHandle;
          if ( !TokenHandle )
            goto LABEL_57;
          goto LABEL_566;
        }
        v498 = 1;
        v563 = 1;
      }
    }
    else
    {
      if ( NtCurrentTeb()->IsImpersonating )
      {
        ExePath = NtOpenThreadToken((HANDLE)0xFFFFFFFFFFFFFFFELL, 0xCu, 1u, &TokenHandle);
        if ( ExePath < 0 )
          goto LABEL_60;
      }
      if ( !ImpersonateLoggedOnUser(*(HANDLE *)(v409 + 552)) )
        goto LABEL_565;
      v498 = 1;
      v563 = 1;
    }
    v165 = v350;
    if ( (v350 & 0x80000) != 0 )
    {
      v160->Flags |= 0x2000000u;
      v165 = v350;
    }
    v66 = NtCreateUserProcess(&Process, ThreadHandle, 0x2000000, 0x2000000, v632, v631, v165, 1, v160, &v616, &v714);
    v347 = v66;
    if ( v498 == 1 )
    {
      v498 = 0;
      v563 = 0;
      if ( TokenHandle )
      {
        v166 = ImpersonateLoggedOnUser(TokenHandle);
        v164 = TokenHandle;
        if ( !v166 )
          goto LABEL_566;
        NtClose(TokenHandle);
      }
      else
      {
        RevertToSelf();
      }
    }
    RtlDestroyProcessParameters(v160);
    if ( v66 >= 0 )
      goto LABEL_705;
    Process = 0;
    ThreadHandle[0] = 0;
    if ( !v617 )
      goto LABEL_214;
    if ( v617 == 1 )
    {
      if ( !v561 && (unsigned __int8)IsBasepGetPackagedAppInfoForFilePresent() )
      {
        v184 = (unsigned int)Feature_UseAEAForUnsupportedPackagedCreateProcessScenario__private_IsEnabledDeviceUsageNoInline()
            && v66 == -1073741191
             ? -1073283070
             : BasepGetPackagedAppInfoForFile(lpFileName, v419, 1, &v409);
        v561 = 1;
        v645 = 1;
        if ( v184 >= 0 )
        {
          if ( v409 )
          {
            lpFileName = *(LPCWSTR *)(v409 + 520);
            if ( *(_DWORD *)(v409 + 548) == 1 )
            {
              v185 = (const wchar_t *)(v409 + 2);
              if ( *(_BYTE *)(v409 + 544) )
              {
                v186 = wcslen(v185);
                v187 = (int)(2 * (v186 + wcslen(pszSrc)) + 4);
                v188 = (wchar_t *)RtlAllocateHeap(ProcessHeap, 0, v187);
                v189 = v188;
                v549 = v188;
                if ( !v188 )
                  goto LABEL_680;
                StringCbCopyW(v188, v187, (STRSAFE_LPCWSTR)(v409 + 2));
                v190 = L" ";
              }
              else
              {
                v191 = wcslen(v185);
                v192 = wcslen(L" PackagedDataInfo: ") + v191;
                v187 = (int)(2 * (v192 + wcslen(pszSrc)) + 2);
                v193 = (wchar_t *)RtlAllocateHeap(ProcessHeap, 0, v187);
                v189 = v193;
                v549 = v193;
                if ( !v193 )
                  goto LABEL_680;
                StringCbCopyW(v193, v187, (STRSAFE_LPCWSTR)(v409 + 2));
                v190 = L" PackagedDataInfo: ";
              }
              StringCbCatW(v189, v187, v190);
              StringCbCatW(v189, v187, pszSrc);
            }
            else
            {
              v532 = *(HANDLE *)(v409 + 552);
              RtlInitUnicodeString(&v490, (PCWSTR)(v409 + 262));
              v464 = 0;
              v194 = (int)(2 * wcslen(pszSrc) + 2);
              v195 = (wchar_t *)RtlAllocateHeap(ProcessHeap, 0, v194);
              v189 = v195;
              v549 = v195;
              if ( !v195 )
                goto LABEL_680;
              StringCbCopyExW(v195, v194, pszSrc, 0, 0, 0x900u);
            }
            pszSrc = v189;
            goto LABEL_680;
          }
        }
      }
      if ( v357 || v66 != -1073741191 && v66 != -1073741790 )
        goto LABEL_703;
      AppExecutionAliasInfoForExecutable = -1073741822;
      v513 = -1073741822;
      if ( v66 == -1073741790 )
      {
        AppExecutionAliasInfoForExecutable = LoadAppExecutionAliasInfoForExecutable(0, (__int64)&v357);
        v513 = AppExecutionAliasInfoForExecutable;
        if ( AppExecutionAliasInfoForExecutable >= 0 && v357 )
        {
          v197 = ValidateAppXAliasFallback(DestinationString.Buffer);
          goto LABEL_691;
        }
      }
      else if ( (unsigned __int8)IsLoadAppExecutionAliasInfoExPresent() )
      {
        v197 = LoadAppExecutionAliasInfoEx(DestinationString.Buffer, v534, &v357);
LABEL_691:
        v513 = v197;
        AppExecutionAliasInfoForExecutable = v197;
      }
      if ( AppExecutionAliasInfoForExecutable < 0 || !v357 )
      {
        if ( AppExecutionAliasInfoForExecutable == -1073267456 )
          v66 = -1073267456;
        v347 = v66;
LABEL_703:
        if ( !RtlIsDosDeviceName_U(lpFileName) )
        {
LABEL_214:
          v28 = (unsigned int)v66;
          goto LABEL_56;
        }
        v39 = 1200;
LABEL_89:
        RtlSetLastWin32Error(v39);
        goto LABEL_57;
      }
      lpFileName = *(LPCWSTR *)(v357 + 8);
      v532 = *(HANDLE *)(v357 + 16);
      v198 = (void *)BuildAppExecutionAliasCommandLine(pszSrc);
      v578 = v198;
      if ( v198 )
        pszSrc = (STRSAFE_LPCWSTR)v198;
      if ( *(_DWORD *)(v357 + 32) != 1 )
      {
        RtlInitUnicodeString(&v490, *(PCWSTR *)v357);
        v464 = 0;
      }
      if ( *(_QWORD *)(v357 + 48) )
      {
        BasepFreeBnoIsolationParameter(&v585);
        RtlInitUnicodeString(&v585, *(PCWSTR *)(v357 + 48));
        LOBYTE(v587) = 1;
        v487 = 1;
        v514 = 1;
      }
      goto LABEL_680;
    }
    v169 = (unsigned int)(v617 - 2);
    if ( v617 == 2 )
    {
      Handle = KeyHandle;
      if ( v66 == -1073741790 )
      {
        v39 = 5;
        goto LABEL_89;
      }
      if ( v358 )
        goto LABEL_214;
      if ( v66 == -1073741521 && UnicodeString.Length >= 8u )
      {
        v175 = &UnicodeString.Buffer[(unsigned __int64)UnicodeString.Length >> 1];
        if ( !_wcsnicmp(v175 - 4, L".bat", 4u) || !_wcsnicmp(v175 - 4, L".cmd", 4u) )
        {
          v397 = 1;
          v537 = 1;
          v176 = (WCHAR *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, KernelBaseGlobalData, 0x20Eu);
          v177 = v176;
          v607 = v176;
          if ( !v176 )
            goto LABEL_84;
          EnvironmentVariableW = GetEnvironmentVariableW(L"ComSpec", v176, 0x104u);
          if ( EnvironmentVariableW >= 0x104 )
          {
            v28 = 3221225487LL;
            goto LABEL_56;
          }
          if ( !EnvironmentVariableW )
          {
            if ( GetEnvironmentVariableW(L"SystemRoot", v177, 0xF3u) - 1 > 0xF1 )
            {
              v28 = 3221225731LL;
              goto LABEL_56;
            }
            RtlStringCchCatW(v177, 260, L"\\system32\\cmd.exe");
          }
          RtlStringCchCatW(v177, 263, L" /c");
          if ( !(unsigned int)BuildSubSysCommandLine(v512, v177, 0, pszSrc, &v588) )
            goto LABEL_57;
          pszSrc = v588.Buffer;
          lpFileName = 0;
          goto LABEL_630;
        }
      }
      if ( (v349 & 0x2000000) != 0 )
        goto LABEL_647;
      v179 = 1;
      v461 = 1;
      if ( v66 != -1073741541 )
      {
        if ( v66 == -1073741521 )
        {
          if ( !(unsigned __int8)IsBasepProcessInvalidImagePresent(v169, v167)
            || !(unsigned int)BaseIsDosApplication(&UnicodeString, 3221225775LL) )
          {
LABEL_640:
            v179 = 0;
            v461 = 0;
          }
        }
        else if ( (unsigned int)(v66 + 1073741520) > 1 && v66 != -1073741209 )
        {
          goto LABEL_640;
        }
      }
      if ( !v179 )
      {
LABEL_647:
        v181 = v419;
      }
      else
      {
        v180 = IsBasepProcessInvalidImagePresent(v169, v167);
        v181 = v419;
        if ( v180 )
          ExePath = BasepCheckWinSaferRestrictions(v419, lpFileName, Handle, &v490);
        else
          ExePath = 0;
        if ( ExePath < 0 )
          goto LABEL_60;
      }
      if ( v66 == -1073741519 )
      {
        if ( (unsigned __int8)IsBasepProcessInvalidImagePresent(v169, v167) )
        {
          ProcessInternalW = NtVdm64CreateProcessInternalW(
                               v181,
                               lpFileName,
                               pszSrc,
                               v496,
                               v492,
                               a6,
                               v349,
                               v411,
                               FileName,
                               v633,
                               v348,
                               0);
          v344 = ProcessInternalW;
        }
        else
        {
          ProcessInternalW = 0;
          v344 = 0;
        }
        if ( !ProcessInternalW
          && NtCurrentTeb()->LastErrorValue == 216
          && (unsigned __int8)IsBasepProcessInvalidImagePresent(v183, v182) )
        {
          RaiseInvalid16BitExeError(&UnicodeString);
        }
        goto LABEL_1173;
      }
      if ( (unsigned __int8)IsBasepProcessInvalidImagePresent(v169, v167) )
      {
        ProcessInternalW = BasepProcessInvalidImage(
                             (unsigned int)v66,
                             v181,
                             DestinationString.Buffer,
                             &lpFileName,
                             &pszSrc,
                             FileName,
                             &v349,
                             &a6,
                             &UnicodeString,
                             &v396,
                             &v411,
                             &Buf1,
                             ApiMessage,
                             &NumberOfBytesToWrite_4,
                             &v588,
                             &v626,
                             &v629,
                             &v406,
                             &v410,
                             &v601,
                             &v497);
        v344 = ProcessInternalW;
      }
      else
      {
        ProcessInternalW = 0;
        v344 = 0;
      }
      if ( !ProcessInternalW )
        goto LABEL_1173;
      if ( v497 )
        goto LABEL_1160;
LABEL_630:
      v358 = 1;
      v463[1] = 1;
      goto LABEL_680;
    }
    if ( v617 == 3 )
      goto LABEL_614;
    v168 = (unsigned int)(v617 - 4);
    if ( v617 == 4 )
    {
      if ( v424[0] != 0xAA64 )
      {
        Response = 6;
        Parameters[0] = (unsigned __int64)&UnicodeString;
        NtRaiseHardError(1073741859, 1u, 1u, Parameters, 1u, &Response);
      }
      v39 = 193;
      if ( v547->ImageSubsystemMajorVersion > 3 )
        v39 = 216;
      goto LABEL_89;
    }
    if ( v617 == 5 )
    {
      v170 = KeyHandle;
      v171 = Buffer;
      if ( !Buffer )
      {
        v171 = RtlAllocateHeap(ProcessHeap, 0, 0x20Au);
        Buffer = v171;
        if ( !v171 )
        {
          NtClose(v170);
          v39 = 8;
          goto LABEL_89;
        }
      }
      v347 = LdrQueryImageFileKeyOption(v170, L"Debugger", 1u, v171, 0x208u, &ReturnedLength);
      if ( v347 >= 0 )
      {
        if ( v420 )
          ReturnedLength = 0;
        if ( ReturnedLength >= 2 && *v171 )
        {
          NtClose(v170);
          v171[260] = 0;
          if ( !(unsigned int)BuildSubSysCommandLine(3, v171, 0, pszSrc, &v588) )
            goto LABEL_57;
          pszSrc = v588.Buffer;
          lpFileName = 0;
          goto LABEL_680;
        }
      }
      RtlFreeHeap(ProcessHeap, 0, v171);
      Buffer = 0;
      if ( !v357 )
      {
        v172 = LoadAppExecutionAliasInfoForExecutable(v170, (__int64)&v357);
        v347 = v172;
        if ( v172 >= 0 && v357 )
        {
          lpFileName = *(LPCWSTR *)(v357 + 8);
          v532 = *(HANDLE *)(v357 + 16);
          v173 = (void *)BuildAppExecutionAliasCommandLine(pszSrc);
          v578 = v173;
          if ( v173 )
            pszSrc = (STRSAFE_LPCWSTR)v173;
          v174 = v357;
          if ( *(_DWORD *)(v357 + 32) != 1 )
          {
            RtlInitUnicodeString(&v490, *(PCWSTR *)v357);
            v464 = 0;
            v174 = v357;
          }
          if ( *(_QWORD *)(v174 + 48) )
          {
            BasepFreeBnoIsolationParameter(&v585);
            RtlInitUnicodeString(&v585, *(PCWSTR *)(v357 + 48));
            LOBYTE(v587) = 1;
            v487 = 1;
            v514 = 1;
          }
          goto LABEL_607;
        }
        if ( v172 != -1073267456 )
          goto LABEL_607;
        v164 = v170;
LABEL_566:
        NtClose(v164);
        goto LABEL_57;
      }
LABEL_607:
      NtClose(v170);
      v395 = 1;
      v471 = 1;
LABEL_680:
      v44 = v418;
      goto LABEL_681;
    }
LABEL_705:
    v199 = v619;
    Handle = v619;
    v548 = v620;
    if ( (unsigned int)(v666 - 2) > 1 )
    {
      v39 = 129;
      goto LABEL_89;
    }
    v200 = 10;
    if ( v668 < 3u || (v167 = v667, v668 == 3) && v667 < 0xAu )
    {
      v201 = 0;
    }
    else
    {
      v168 = MEMORY[0x7FFE026C];
      if ( (unsigned int)v668 > MEMORY[0x7FFE026C]
        || v668 == MEMORY[0x7FFE026C] && (unsigned int)v667 > MEMORY[0x7FFE0270] )
      {
LABEL_614:
        v39 = 193;
        goto LABEL_89;
      }
      v201 = 1;
    }
    if ( !v201 )
      goto LABEL_614;
    if ( ((unsigned __int8)KeyHandle & 8) != 0 )
    {
      v636 = v624;
      Parameters[2] = v624;
      v560 = v625;
      v646 = v625;
    }
    if ( (unsigned __int8)IsBasepProcessInvalidImagePresent(v168, v167) )
      v204 = BasepCheckWebBladeHashes(v199);
    else
      v204 = 0;
    if ( v204 == -1073741790 )
    {
      v39 = 1277;
      goto LABEL_89;
    }
    if ( v204 < 0 )
    {
      v39 = 1278;
      goto LABEL_89;
    }
    if ( (unsigned __int8)IsBasepProcessInvalidImagePresent(v203, v202) )
      ExePath = BasepIsProcessAllowed(lpFileName);
    else
      ExePath = 0;
    v347 = ExePath;
    if ( ExePath < 0 )
      goto LABEL_60;
    if ( !v396 && (v349 & 0x800) != 0 )
      v349 &= ~0x800u;
    if ( v410 )
    {
      v497 = Process;
      if ( (unsigned __int8)IsBasepProcessInvalidImagePresent(v206, v205) )
      {
        ProcessInternalW = BaseUpdateVDMEntry(1, &v497, NumberOfBytesToWrite_4, v410);
        v344 = ProcessInternalW;
      }
      else
      {
        ProcessInternalW = 0;
        v344 = 0;
      }
      if ( !ProcessInternalW )
      {
        v497 = 0;
        goto LABEL_1173;
      }
      v406 |= 2u;
      v199 = Handle;
    }
    v207 = v622;
    v639 = v622;
    if ( v358 || (v349 & 0x2000000) != 0 )
    {
      v209 = v419;
    }
    else
    {
      v208 = IsBasepProcessInvalidImagePresent(v206, v205);
      v209 = v419;
      if ( v208 )
        ExePath = BasepCheckWinSaferRestrictions(v419, lpFileName, v199, &v490);
      else
        ExePath = 0;
      if ( ExePath < 0 )
        goto LABEL_60;
    }
    memset_0(v704, 0, 0x1C8u);
    v210 = v670;
    v211 = (unsigned int)v670 - 332;
    if ( v670 == 332 )
    {
      if ( ((unsigned __int8)KeyHandle & 2) != 0 )
        LOWORD(v200) = MEMORY[0x7FFE026A];
    }
    else
    {
      v211 = (unsigned int)v670 - 452;
      if ( v670 == 452 )
      {
        v200 = 5;
      }
      else
      {
        v211 = (unsigned int)v670 - 14948;
        if ( v670 != 14948 )
        {
          v211 = (unsigned int)v670 - 34404;
          if ( v670 == 34404 )
          {
            v200 = 9;
          }
          else if ( v670 == 43620 )
          {
            v200 = 12;
          }
          else
          {
            DbgPrint_0("Kernel32: No mapping for ImageInformation.Machine == %04x\n", v670);
            v200 = 0xFFFF;
          }
        }
      }
    }
    v407 = v200;
    if ( (v349 & 0x400000) != 0 )
      goto LABEL_1158;
    if ( ((unsigned __int8)KeyHandle & 0x10) != 0 && v420 )
    {
      v347 = NtQueryInformationProcess(
               Process,
               ProcessAffinityUpdateMode|ProcessUserModeIOPL,
               &ProcessInformation,
               1u,
               0);
      if ( v347 < 0 )
      {
        v347 = 0;
      }
      else if ( ProcessInformation == -127 )
      {
        v212 = 1;
        v351 = 1;
        v538 = 1;
        goto LABEL_766;
      }
    }
    v212 = v351;
LABEL_766:
    v423[0] = 0;
    if ( ((unsigned __int8)KeyHandle & 1) == 0 || v212 )
    {
      if ( (unsigned __int8)IsBasepProcessInvalidImagePresent(v211, v210) )
      {
        BasepQueryAppCompat(
          v665,
          ((unsigned __int8)KeyHandle >> 1) & 1,
          (unsigned __int16)v200,
          v199,
          Process,
          DestinationString.Buffer,
          v411,
          &v490,
          &v500,
          &v479,
          &v507,
          &v488,
          &v559,
          &v533,
          &v499,
          v423,
          &v584,
          &v517);
        if ( (v350 & 0x80000) == 0 && (v533 & 0x1000000000LL) != 0 )
        {
          v350 |= 0x80000u;
LABEL_772:
          ProcessHeap = HeapHandle;
          goto LABEL_680;
        }
      }
    }
    if ( ((unsigned __int8)KeyHandle & 1) == 0 || ((unsigned __int8)KeyHandle & 0x10) != 0 )
    {
      v495 = v621;
      v705 = v621;
      v707[0] = 0;
      v709 = 0;
      if ( (unsigned __int8)IsBasepProcessInvalidImagePresent(v211, v210) )
      {
        v213 = !v420 || (*(_BYTE *)(v420 + 80) & 4) != 0 ? 0LL : *(_QWORD *)(v420 + 16);
        LODWORD(v342) = (v669 >> 9) & 1;
        LODWORD(v341) = v488;
        LODWORD(LengthNeeded) = v559;
        LODWORD(PathType) = ((unsigned __int8)KeyHandle >> 2) & 1;
        ExePath = BasepConstructSxsCreateProcessMessage(
                    &UnicodeString,
                    &DestinationString,
                    v199,
                    Process,
                    v548,
                    v209,
                    PathType,
                    LengthNeeded,
                    v507,
                    v341,
                    v342,
                    v213,
                    v207,
                    v636,
                    v560,
                    &v495,
                    v704,
                    v682);
      }
      else
      {
        ExePath = 0;
      }
      v347 = ExePath;
      if ( ExePath < 0 )
        goto LABEL_60;
    }
    v712 = v623;
    v711 = v622;
    v697 = (unsigned __int64)Process;
    v698 = (unsigned __int64)ThreadHandle[0];
    v699 = _mm_loadu_si128(&v635);
    v713 = v200;
    v700 = v349 & 0xFFFFFFFC;
    if ( v666 == 2 || v396 )
    {
      v697 = (unsigned __int64)Process | 2;
      ModuleHandleA = GetModuleHandleA(0);
      v215 = RtlImageNtHeader(ModuleHandleA);
      if ( v215 )
      {
        if ( v215->OptionalHeader.Subsystem == 2 )
          v697 |= 1u;
      }
    }
    v216 = v419;
    if ( v419 )
    {
      TokenInformation = 0;
      ExePath = NtQueryInformationToken(v419, TokenSessionId, &TokenInformation, 4u, &ReturnLength);
      v347 = ExePath;
      if ( ExePath < 0 )
        goto LABEL_60;
      if ( TokenInformation != NtCurrentPeb()->SessionId )
        v698 |= 1u;
    }
    if ( (BYTE12(v660) & 0x40) != 0 )
      v697 |= 1u;
    if ( SBYTE12(v660) < 0 )
      v697 &= ~1uLL;
    if ( (HIDWORD(v660) & 0x10000) != 0 )
      v697 &= 0xFFFFFFFFFFFFFFFCuLL;
    v701 = v410;
    if ( v410 )
    {
      v217 = NumberOfBytesToWrite_4;
      if ( NumberOfBytesToWrite_4 )
      {
        ConsoleHost = 0;
      }
      else
      {
        ConsoleHost = BasepGetConsoleHost();
        v217 = NumberOfBytesToWrite_4;
      }
      v703 = ConsoleHost;
      v702 = v217;
    }
    if ( ((unsigned __int8)KeyHandle & 1) != 0 && ((unsigned __int8)KeyHandle & 0x10) == 0 )
      v698 |= 2u;
    ExePath = BasepCsrCaptureSxsMessage(v704, &CaptureBuffer);
    v347 = ExePath;
    if ( ExePath < 0 )
      goto LABEL_60;
    CsrClientCallServer(ApiMessage, CaptureBuffer, (CSR_API_NUMBER)0x1001D, 0x218u);
    v220 = (unsigned int)v696;
    if ( v696 < 0 )
    {
      BaseSetLastNTError((unsigned int)v696);
      ExitStatus = v696;
      goto LABEL_57;
    }
    if ( ((unsigned __int8)KeyHandle & 1) == 0 )
    {
      v495 = v705;
      if ( v705 != v621 )
      {
        ExePath = BasepUpdateProcessParametersField(Process, 8, 8, (__int64)&v616);
        v347 = ExePath;
        if ( ExePath < 0 )
          goto LABEL_60;
      }
    }
    if ( !v397 && (v494 & 2) == 0 && !v505 )
    {
      v465 |= 1u;
      if ( (unsigned __int8)IsBasepProcessInvalidImagePresent(v220, v219) )
      {
        if ( (unsigned int)Feature_ShadowAdminAppCompat__private_IsEnabledDeviceUsageNoInline() )
        {
          v556 = 0;
          v223 = BaseCheckElevation(
                   Process,
                   Handle,
                   DestinationString.Buffer,
                   &v465,
                   v533,
                   v706,
                   v708,
                   v499,
                   v216,
                   0,
                   &v556);
          v347 = v223;
          if ( (unsigned int)LUAIsShadowAdminEnabled() )
          {
            if ( v223 < 0 )
              break;
            if ( (unsigned __int8)IsBasepFreeAppCompatData2Present() )
              BaseMarkProcessTokenForInstallers(Process, Handle, lpFileName, v708, v499, v556);
          }
        }
        else
        {
          v223 = BaseCheckElevation(
                   Process,
                   Handle,
                   DestinationString.Buffer,
                   &v465,
                   v533,
                   v706,
                   v708,
                   v499,
                   v216,
                   0,
                   0);
          v347 = v223;
        }
      }
      else
      {
        v223 = 0;
        v347 = 0;
      }
      if ( v223 < 0 )
        break;
    }
    v224 = Feature_AutoGenerateSparsePackages__private_IsEnabledDeviceUsageNoInline();
    LOBYTE(v225) = v352;
    v33 = v224 == 0;
    v226 = v418;
    if ( v33 || v710 || v352 || v357 || v418 )
    {
      EAAumidIfPresent = v477;
    }
    else
    {
      EtwEventActivityIdControl(1, &v689);
      EtwEventActivityIdControl(5, &v690);
      if ( (unsigned int)dword_18039D020 > 5 )
      {
        v642 = 0x1000000;
        v843 = &v642;
        v844 = 8;
        tlgCreate1Sz_wchar_t(v845, lpFileName);
        v463[0] = v496 != 0;
        v846 = v463;
        v847 = 1;
        v462 = v492 != 0;
        v848 = &v462;
        v849 = 1;
        v460 = a6 == 1;
        v850 = &v460;
        v851 = 1;
        v600 = v349;
        v852 = &v600;
        v853 = 4;
        v459 = v411 != 0;
        v854 = &v459;
        v855 = 1;
        v458 = v482 != 0;
        v856 = &v458;
        v857 = 1;
        tlgWriteTransfer_EtwEventWriteTransfer(
          (unsigned int)&dword_18039D020,
          (unsigned int)byte_180359C55,
          (unsigned int)&v689,
          (unsigned int)&v690,
          10,
          (__int64)v842);
      }
      v911[0] = 0;
      EAAumidIfPresent = GetEAAumidIfPresent(lpFileName, v911, 130);
      v477 = EAAumidIfPresent;
      v647 = EAAumidIfPresent;
      v225 = (unsigned int)dword_18039D020;
      if ( (unsigned int)dword_18039D020 > 5 )
      {
        v654 = 0x1000000;
        v889 = &v654;
        v890 = 8;
        v599 = EAAumidIfPresent;
        v891 = &v599;
        v892 = 4;
        v228 = v911;
        if ( !v911[0] )
          v228 = &word_180290A38;
        tlgCreate1Sz_wchar_t(v893, v228);
        v615 = *(_DWORD *)(v348 + 16);
        v894 = &v615;
        v895 = 4;
        tlgWriteTransfer_EtwEventWriteTransfer(
          (unsigned int)&dword_18039D020,
          (unsigned int)&unk_180359C00,
          (unsigned int)&v689,
          (unsigned int)&v690,
          6,
          (__int64)v888);
      }
      v226 = v418;
      LOBYTE(v225) = v352;
    }
    if ( !v710 && (EAAumidIfPresent < 0 || !v911[0]) || (_BYTE)v225 || v357 || v226 )
      goto LABEL_888;
    v229 = &v710;
    if ( !v710 )
      v229 = v911;
    Src = v229;
    v605 = v229;
    EtwEventActivityIdControl(5, &v685);
    EtwEventActivityIdControl(1, &v686);
    v521 = 1;
    if ( (unsigned int)dword_18039D020 > 5 )
    {
      v230 = qword_18039D038;
      if ( (qword_18039D030 & 0x400000000000LL) != 0 && (qword_18039D038 & 0x400000000000LL) == qword_18039D038 )
      {
        v643 = 0x1000000;
        v859 = &v643;
        v860 = 8;
        tlgCreate1Sz_wchar_t(v861, v229);
        v457 = v496 != 0;
        v862 = &v457;
        v863 = 1;
        v472 = v492 != 0;
        v864 = &v472;
        v865 = 1;
        v473 = a6 == 1;
        v866 = &v473;
        v867 = 1;
        v614 = v349;
        v868 = &v614;
        v869 = 4;
        v474 = v411 != 0;
        v870 = &v474;
        v871 = 1;
        v475 = v482 == 0;
        v872 = &v475;
        v873 = 1;
        tlgWriteTransfer_EtwEventWriteTransfer(
          (unsigned int)&dword_18039D020,
          (unsigned int)byte_180359B3D,
          (unsigned int)&v686,
          (unsigned int)&v685,
          10,
          (__int64)v858);
      }
    }
    if ( (unsigned int)Feature_AllowDisableProcessTreeBreakawayFlagForWin32alacarte__private_IsEnabledDeviceUsageNoInline(v230) )
    {
      v232 = 0;
      v613 = 0;
      if ( (v478 & 2) != 0 )
      {
        v555 = 0;
        v347 = CurrentProcessFamilyNameMatches(Src);
        if ( v347 < 0 )
        {
          ExitStatus = -1073741823;
          goto LABEL_57;
        }
        v232 = v555 != 0;
        v613 = v232;
      }
      PackageActivationTokenForSxS3 = BasepGetPackageActivationTokenForSxS3(Src, v534, v232, token);
    }
    else
    {
      PackageActivationTokenForSxS3 = BasepGetPackageActivationTokenForSxS2(v229, v534, token);
    }
    PackageFullNameFromToken = PackageActivationTokenForSxS3;
    if ( (unsigned int)dword_18039D020 > 5 )
    {
      v225 = qword_18039D038;
      if ( (qword_18039D030 & 0x400000000000LL) != 0 && (qword_18039D038 & 0x400000000000LL) == qword_18039D038 )
      {
        v655 = 0x1000000;
        v875 = &v655;
        v876 = 8;
        v612 = PackageActivationTokenForSxS3;
        v877 = &v612;
        v878 = 4;
        v466 = token[0] != 0;
        v879 = &v466;
        v880 = 1;
        tlgWriteTransfer_EtwEventWriteTransfer(
          (unsigned int)&dword_18039D020,
          (unsigned int)byte_180359AE5,
          (unsigned int)&v686,
          (unsigned int)&v685,
          5,
          (__int64)v874);
      }
    }
    if ( PackageFullNameFromToken )
    {
LABEL_866:
      ExitStatus = -1073741823;
      v39 = PackageFullNameFromToken;
      goto LABEL_89;
    }
    if ( !token[0] )
    {
LABEL_888:
      if ( (unsigned int)Feature_AllowDisableProcessTreeBreakawayFlagForWin32alacarte__private_IsEnabledDeviceUsageNoInline(v225) )
      {
        if ( !v418 && (v478 & 2) != 0 )
        {
          applicationUserModelIdLength = 130;
          if ( (unsigned int)ShouldRelaunchWithWin32alacarteIdentity(
                               Process,
                               applicationUserModelId,
                               &applicationUserModelIdLength) )
          {
            PackageFullNameFromToken = BasepGetPackageActivationTokenForSxS3(applicationUserModelId, v534, 1, token);
            if ( (unsigned int)dword_18039D020 > 5
              && (qword_18039D030 & 0x400000000000LL) != 0
              && (qword_18039D038 & 0x400000000000LL) == qword_18039D038 )
            {
              v648 = 0x1000000;
              v882 = &v648;
              v883 = 8;
              v593 = PackageFullNameFromToken;
              v884 = &v593;
              v885 = 4;
              v468 = token[0] != 0;
              v886 = &v468;
              v887 = 1;
              tlgWriteTransfer_EtwEventWriteTransfer(
                (unsigned int)&dword_18039D020,
                (unsigned int)&unk_180359A18,
                (unsigned int)&v686,
                (unsigned int)&v685,
                5,
                (__int64)v881);
            }
            if ( PackageFullNameFromToken )
              goto LABEL_866;
            if ( token[0] )
            {
              v44 = token[0];
              v418 = token[0];
              token[0] = 0;
              v594 = 128;
              PackageFullNameFromToken = GetPackageFullNameFromToken(v418, &v594, packageFullName);
              if ( (unsigned int)dword_18039D020 <= 5
                || (qword_18039D030 & 0x400000000000LL) == 0
                || (qword_18039D038 & 0x400000000000LL) != qword_18039D038 )
              {
                goto LABEL_875;
              }
              v656 = 0x1000000;
              v897 = &v656;
              v898 = 8;
              v595 = PackageFullNameFromToken;
              v899 = &v595;
              v900 = 4;
              tlgCreate1Sz_wchar_t(v901, Src);
              v237 = packageFullName;
              if ( PackageFullNameFromToken )
                v237 = L"NULL";
              tlgCreate1Sz_wchar_t(v902, v237);
              v235 = &v896;
              v236 = byte_1803599A3;
              goto LABEL_874;
            }
          }
        }
      }
      if ( (unsigned int)Feature_AlwaysUseAppxExtensionForPackagedProcesses__private_IsEnabledDeviceUsageNoInline() )
      {
        if ( (v547->BitField & 0x10) != 0 || (v238 = 0, v419) )
          v238 = 1;
        if ( !(_BYTE)v515 && v238 && !v516 )
        {
          v610 = 0;
          v239 = NtOpenProcessToken(Process, 8u, &v610);
          if ( v239 >= 0 )
          {
            v596 = 128;
            v245 = GetPackageFullNameFromToken(v610, &v596, packageFullName);
            NtClose(v610);
            if ( !v245 )
            {
              v413 = 1;
              v539 = 1;
              RtlInitUnicodeString(&v490, packageFullName);
              goto LABEL_772;
            }
          }
          else
          {
            BaseSetLastNTError((unsigned int)v239);
          }
        }
      }
      if ( (unsigned int)Feature_Win32alacarteSupport_PROC_THREAD_ATTRIBUTE_JOB_LIST__private_IsEnabledDeviceUsageNoInline() )
      {
        v241 = v602;
        if ( v602 )
        {
          v242 = v637;
          v243 = Process;
          v638 = 0;
          ExePath = 0;
          v597 = 0;
          for ( i = 0; ; ++i )
          {
            v638 = i;
            if ( i >= v242 )
              break;
            ExePath = NtAssignProcessToJobObject(*(HANDLE *)(v241 + 8 * i), v243);
            v597 = ExePath;
            if ( ExePath < 0 )
              break;
            v241 = v602;
          }
          v347 = ExePath;
          if ( ExePath < 0 )
            goto LABEL_60;
        }
      }
      if ( ((unsigned __int8)KeyHandle & 1) != 0 )
      {
        if ( v351 )
        {
          if ( (unsigned __int8)IsBasepProcessInvalidImagePresent(v241, v240) )
          {
            if ( (unsigned __int8)IsBasepProcessInvalidImagePresent(v241, v240) )
            {
              LODWORD(v341) = v517;
              LOWORD(LengthNeeded) = v423[0];
              BasepGetAppCompatData(
                DestinationString.Buffer,
                v490.Buffer,
                &v465,
                v706,
                v707,
                &v709,
                v665,
                LengthNeeded,
                v584,
                v341,
                &v500,
                &v479,
                &v504,
                &NumberOfBytesToWrite);
              if ( !(unsigned int)BasepInitAppCompatData(Process, v504, NumberOfBytesToWrite) )
              {
                ExePath = -1073741790;
                v347 = -1073741790;
                goto LABEL_60;
              }
            }
          }
        }
      }
      else
      {
        if ( (unsigned __int8)IsBasepProcessInvalidImagePresent(v241, v240) )
        {
          LODWORD(v341) = v517;
          LOWORD(LengthNeeded) = v423[0];
          BasepGetAppCompatData(
            DestinationString.Buffer,
            v490.Buffer,
            &v465,
            v706,
            v707,
            &v709,
            v665,
            LengthNeeded,
            v584,
            v341,
            &v500,
            &v479,
            &v504,
            &NumberOfBytesToWrite);
        }
        v241 = (unsigned __int64)v504;
        if ( !v504 )
          goto LABEL_1131;
        if ( v424[0] == 0xAA64 )
        {
          v246 = v350;
          if ( (v350 & 0x800000) == 0 )
          {
            if ( *((_DWORD *)v504 + 130) < 0x11C0u
              || !*((_DWORD *)v504 + 1136)
              || (v247 = *((unsigned int *)v504 + 1137), !(_DWORD)v247) )
            {
              v313 = *((unsigned __int8 *)v504 + 4520) >> 4;
LABEL_1123:
              if ( (v313 & 8) == 0 )
                goto LABEL_1125;
              v350 = v246 | 0x800000;
              goto LABEL_772;
            }
            v551 = 0;
            v248 = (char *)v504 + v247;
            v427 = 0;
            v443 = 0;
            ThreadHandle[1] = (HANDLE)0x3000AB00110038LL;
            v438 = 21;
            v439 = 0;
            v440 = 0;
            v441 = 0;
            v442 = 0u;
            LODWORD(v443) = -65536;
            *(_QWORD *)((char *)&v443 + 4) = 0x1A010003000000LL;
            v353 = 26;
            v444 = 0;
            v424[2] = 56;
            v425 = 17;
            v426 = -21760;
            v428 = 48;
            v429 = 21;
            v430 = 0;
            v431 = 0;
            v432 = 0;
            v433 = 0u;
            v434 = 0x3000000FFFF0000LL;
            v249 = 0;
            v435 = 1704192;
            v250 = 1;
            v251 = 26;
            v414 = 0;
            v436 = 0;
            if ( *((_BYTE *)v504 + v247 + 2) >> 4 == 1 )
            {
              if ( !v248[3] )
              {
                if ( v248[8] != 21 || *(_WORD *)v248 != 56 || v248[4] != -85 )
                  goto LABEL_1118;
                if ( !v248[3] )
                  goto LABEL_929;
              }
              if ( v248[8] != 21 )
              {
LABEL_929:
                v252 = *((unsigned __int16 *)v248 + 3) - 48LL;
                if ( !v248[8] || (v253 = 1, (v248[*((unsigned __int16 *)v248 + 3)] & 1) == 0) )
                  v253 = 0;
                if ( v253 )
                  *(_QWORD *)&v433 = *((_QWORD *)v248 + 2);
                v254 = v248[8] && (v248[v252 + 48] & 1) != 0;
                v255 = v254 | v436 & 0xFE;
                LOBYTE(v436) = v255;
                if ( (unsigned __int8)v248[8] < 2u || (v256 = 1, (v248[v252 + 48] & 2) == 0) )
                  v256 = 0;
                v33 = v256 == 0;
                v257 = 2;
                if ( !v33 )
                {
                  DWORD2(v433) = *((_DWORD *)v248 + 6);
                  v257 = 2;
                }
                if ( (unsigned __int8)v248[8] < 2u || (v248[v252 + 48] & 2) == 0 )
                  v257 = 0;
                v258 = v257 | v255 & 0xFD;
                LOBYTE(v436) = v258;
                if ( (unsigned __int8)v248[8] < 3u || (v259 = 1, (v248[v252 + 48] & 4) == 0) )
                  v259 = 0;
                if ( v259 )
                  HIDWORD(v433) = *((_DWORD *)v248 + 7);
                if ( (unsigned __int8)v248[8] >= 3u && (v248[v252 + 48] & 4) != 0 )
                  v260 = 4;
                else
                  v260 = 0;
                v261 = v260 | v258 & 0xFB;
                LOBYTE(v436) = v261;
                if ( (unsigned __int8)v248[8] < 4u || (v262 = 1, (v248[v252 + 48] & 8) == 0) )
                  v262 = 0;
                if ( v262 )
                  LOWORD(v434) = *((_WORD *)v248 + 16);
                if ( (unsigned __int8)v248[8] >= 4u && (v248[v252 + 48] & 8) != 0 )
                  v263 = 8;
                else
                  v263 = 0;
                v264 = v263 | v261 & 0xF7;
                LOBYTE(v436) = v264;
                if ( (unsigned __int8)v248[8] < 5u || (v265 = 1, (v248[v252 + 48] & 0x10) == 0) )
                  v265 = 0;
                if ( v265 )
                  WORD1(v434) = *((_WORD *)v248 + 17);
                if ( (unsigned __int8)v248[8] >= 5u && (v248[v252 + 48] & 0x10) != 0 )
                  v266 = 16;
                else
                  v266 = 0;
                v267 = v266 | v264 & 0xEF;
                LOBYTE(v436) = v267;
                if ( (unsigned __int8)v248[8] < 6u || (v268 = 1, (v248[v252 + 48] & 0x20) == 0) )
                  v268 = 0;
                if ( v268 )
                  WORD2(v434) = *((_WORD *)v248 + 18);
                if ( (unsigned __int8)v248[8] >= 6u && (v248[v252 + 48] & 0x20) != 0 )
                  v269 = 32;
                else
                  v269 = 0;
                v270 = v269 | v267 & 0xDF;
                LOBYTE(v436) = v270;
                if ( (unsigned __int8)v248[8] < 7u || (v271 = 1, (v248[v252 + 48] & 0x40) == 0) )
                  v271 = 0;
                if ( v271 )
                  BYTE6(v434) = v248[38];
                if ( (unsigned __int8)v248[8] >= 7u && (v248[v252 + 48] & 0x40) != 0 )
                  v272 = 64;
                else
                  v272 = 0;
                v273 = v272 | v270 & 0xBF;
                LOBYTE(v436) = v273;
                if ( (unsigned __int8)v248[8] < 8u || (v274 = 1, v248[v252 + 48] >= 0) )
                  v274 = 0;
                if ( v274 )
                  HIBYTE(v434) = v248[39] & 0x1F;
                if ( (unsigned __int8)v248[8] < 8u || v248[v252 + 48] >= 0 )
                  v275 = 0;
                else
                  v275 = 0x80;
                LOBYTE(v436) = v275 | v273 & 0x7F;
                if ( (unsigned __int8)v248[8] < 9u || (v276 = 1, (v248[v252 + 49] & 1) == 0) )
                  v276 = 0;
                if ( v276 )
                {
                  v249 = v248[40] & 0xF;
                  LOBYTE(v435) = v249;
                }
                v277 = (unsigned __int8)v248[8] >= 9u && (v248[v252 + 49] & 1) != 0;
                v278 = v277 | BYTE1(v436) & 0xFE;
                BYTE1(v436) = v278;
                if ( (unsigned __int8)v248[8] < 0xAu || (v279 = 1, (v248[v252 + 49] & 2) == 0) )
                  v279 = 0;
                if ( v279 )
                {
                  v249 = v249 & 0xF | (16 * ((unsigned __int8)v248[40] >> 4));
                  LOBYTE(v435) = v249;
                }
                if ( (unsigned __int8)v248[8] >= 0xAu && (v248[v252 + 49] & 2) != 0 )
                  v280 = 2;
                else
                  v280 = 0;
                v281 = v280 | v278 & 0xFD;
                BYTE1(v436) = v281;
                if ( (unsigned __int8)v248[8] < 0xBu || (v282 = 1, (v248[v252 + 49] & 4) == 0) )
                  v282 = 0;
                if ( v282 )
                {
                  v250 = v248[41] & 7;
                  BYTE1(v435) = v250;
                }
                if ( (unsigned __int8)v248[8] >= 0xBu && (v248[v252 + 49] & 4) != 0 )
                  v283 = 4;
                else
                  v283 = 0;
                v284 = v283 | v281 & 0xFB;
                BYTE1(v436) = v284;
                if ( (unsigned __int8)v248[8] < 0xCu || (v285 = 1, (v248[v252 + 49] & 8) == 0) )
                  v285 = 0;
                if ( v285 )
                {
                  v250 = v250 & 0xE7 | (8 * (((unsigned __int8)v248[41] >> 3) & 3));
                  BYTE1(v435) = v250;
                }
                if ( (unsigned __int8)v248[8] >= 0xCu && (v248[v252 + 49] & 8) != 0 )
                  v286 = 8;
                else
                  v286 = 0;
                v287 = v286 | v284 & 0xF7;
                BYTE1(v436) = v287;
                if ( (unsigned __int8)v248[8] < 0xDu || (v288 = 1, (v248[v252 + 49] & 0x10) == 0) )
                  v288 = 0;
                if ( v288 )
                  BYTE1(v435) = v250 & 0x9F | (32 * (((unsigned __int8)v248[41] >> 5) & 3));
                if ( (unsigned __int8)v248[8] >= 0xDu && (v248[v252 + 49] & 0x10) != 0 )
                  v289 = 16;
                else
                  v289 = 0;
                v290 = v289 | v287 & 0xEF;
                BYTE1(v436) = v290;
                if ( (unsigned __int8)v248[8] < 0xEu || (v291 = 1, (v248[v252 + 49] & 0x20) == 0) )
                  v291 = 0;
                if ( v291 )
                {
                  v251 = v248[42] & 3 | 0x18;
                  BYTE2(v435) = v251;
                }
                if ( (unsigned __int8)v248[8] >= 0xEu && (v248[v252 + 49] & 0x20) != 0 )
                  v292 = 32;
                else
                  v292 = 0;
                v293 = v292 | v290 & 0xDF;
                BYTE1(v436) = v293;
                if ( (unsigned __int8)v248[8] < 0xFu || (v294 = 1, (v248[v252 + 49] & 0x40) == 0) )
                  v294 = 0;
                if ( v294 )
                {
                  v251 = v251 & 0xFB | (4 * ((v248[42] & 4) != 0));
                  BYTE2(v435) = v251;
                }
                if ( (unsigned __int8)v248[8] >= 0xFu && (v248[v252 + 49] & 0x40) != 0 )
                  v295 = 64;
                else
                  v295 = 0;
                v296 = v295 | v293 & 0xBF;
                BYTE1(v436) = v296;
                if ( (unsigned __int8)v248[8] < 0x10u || (v297 = 1, v248[v252 + 49] >= 0) )
                  v297 = 0;
                if ( v297 )
                {
                  v251 = v251 & 0xF7 | (8 * ((v248[42] & 8) != 0));
                  BYTE2(v435) = v251;
                }
                if ( (unsigned __int8)v248[8] < 0x10u || v248[v252 + 49] >= 0 )
                  v298 = 0;
                else
                  v298 = 0x80;
                BYTE1(v436) = v298 | v296 & 0x7F;
                if ( (unsigned __int8)v248[8] < 0x11u || (v299 = 1, (v248[v252 + 50] & 1) == 0) )
                  v299 = 0;
                if ( v299 )
                {
                  v251 = v251 & 0xEF | (16 * ((v248[42] & 0x10) != 0));
                  BYTE2(v435) = v251;
                }
                v300 = (unsigned __int8)v248[8] >= 0x11u && (v248[v252 + 50] & 1) != 0;
                v301 = v300 | BYTE2(v436) & 0xFE;
                BYTE2(v436) = v301;
                if ( (unsigned __int8)v248[8] < 0x12u || (v302 = 1, (v248[v252 + 50] & 2) == 0) )
                  v302 = 0;
                if ( v302 )
                {
                  v251 = v251 & 0xDF | (32 * ((v248[42] & 0x20) != 0));
                  BYTE2(v435) = v251;
                }
                if ( (unsigned __int8)v248[8] >= 0x12u && (v248[v252 + 50] & 2) != 0 )
                  v303 = 2;
                else
                  v303 = 0;
                v304 = v303 | v301 & 0xFD;
                BYTE2(v436) = v304;
                if ( (unsigned __int8)v248[8] < 0x13u || (v305 = 1, (v248[v252 + 50] & 4) == 0) )
                  v305 = 0;
                if ( v305 )
                {
                  v251 = v251 & 0xBF | (((v248[42] & 0x40) != 0) << 6);
                  BYTE2(v435) = v251;
                }
                if ( (unsigned __int8)v248[8] >= 0x13u && (v248[v252 + 50] & 4) != 0 )
                  v306 = 4;
                else
                  v306 = 0;
                v307 = v306 | v304 & 0xFB;
                BYTE2(v436) = v307;
                if ( (unsigned __int8)v248[8] < 0x14u || (v308 = 1, (v248[v252 + 50] & 8) == 0) )
                  v308 = 0;
                if ( v308 )
                  BYTE2(v435) = v251 & 0x7F | ((unsigned __int8)v248[42] >> 7 << 7);
                if ( (unsigned __int8)v248[8] >= 0x14u && (v248[v252 + 50] & 8) != 0 )
                  v309 = 8;
                else
                  v309 = 0;
                v310 = v309 | v307 & 0xF7;
                BYTE2(v436) = v310;
                if ( (unsigned __int8)v248[8] < 0x15u || (v311 = 1, (v248[v252 + 50] & 0x10) == 0) )
                  v311 = 0;
                if ( v311 )
                  BYTE3(v435) = v248[43] & 1 | v414 & 0xFE;
                if ( (unsigned __int8)v248[8] >= 0x15u && (v248[v252 + 50] & 0x10) != 0 )
                  v312 = 16;
                else
                  v312 = 0;
                BYTE2(v436) = v312 | v310 & 0xEF;
              }
            }
LABEL_1118:
            v246 = v350;
            LOWORD(v200) = v407;
            if ( (v436 & 0x200) != 0 )
              v313 = v249 >> 4;
            else
              LOBYTE(v313) = v551;
            v207 = v639;
            goto LABEL_1123;
          }
        }
LABEL_1125:
        BaseAddress = 0;
        RegionSize = NumberOfBytesToWrite;
        ExePath = NtAllocateVirtualMemory(Process, &BaseAddress, 0, &RegionSize, 0x1000u, 4u);
        v347 = ExePath;
        if ( ExePath < 0 )
          goto LABEL_60;
        ExePath = NtWriteVirtualMemory(Process, BaseAddress, v504, NumberOfBytesToWrite, 0);
        v347 = ExePath;
        if ( ExePath < 0 )
          goto LABEL_60;
        ExePath = NtWriteVirtualMemory(Process, (PVOID)(v207 + 728), &BaseAddress, 8u, 0);
        v347 = ExePath;
        if ( ExePath < 0 )
          goto LABEL_60;
        v241 = v623;
        if ( v623 )
        {
          v554 = (int)BaseAddress;
          ExePath = NtWriteVirtualMemory(Process, (PVOID)(v623 + 488), &v554, 4u, 0);
          v347 = ExePath;
        }
        if ( ExePath < 0 )
          goto LABEL_60;
      }
LABEL_1131:
      if ( !v397 && ((unsigned __int8)KeyHandle & 1) == 0 )
      {
        ExePath = (unsigned __int8)IsBasepProcessInvalidImagePresent(v241, v240)
                ? BaseElevationPostProcessing(v465, (unsigned __int16)v200, Process)
                : 0;
        v347 = ExePath;
        if ( ExePath < 0 )
        {
LABEL_1142:
          ExitStatus = ExePath;
          goto LABEL_60;
        }
      }
      if ( !v420 )
      {
LABEL_1158:
        if ( (v349 & 4) == 0 )
        {
          v223 = NtResumeThread(ThreadHandle[0], 0);
          v347 = v223;
          if ( v223 < 0 )
            goto LABEL_828;
        }
LABEL_1160:
        ProcessInternalW = 1;
        v344 = 1;
        if ( v406 )
          v406 |= 8u;
        if ( v497 )
        {
          if ( v410 == 32 )
          {
            v317 = v348;
            *(_QWORD *)v348 = (unsigned __int64)v497 | 2;
            if ( (v406 & 4) != 0 )
              v635 = 0;
          }
          else
          {
            v317 = v348;
            *(_QWORD *)v348 = (unsigned __int64)v497 | 1;
          }
          if ( Process )
            NtClose(Process);
        }
        else
        {
          v317 = v348;
          *(_QWORD *)v348 = Process;
        }
        *(HANDLE *)(v317 + 8) = ThreadHandle[0];
        *(_DWORD *)(v317 + 16) = v635.m128i_i32[0];
        *(_DWORD *)(v317 + 20) = v635.m128i_i32[2];
        Process = 0;
        ThreadHandle[0] = 0;
        v318 = HeapHandle;
        v319 = v348;
        goto LABEL_1174;
      }
      ExePath = BasepPostSuccessAppXExtension(Process);
      v347 = ExePath;
      if ( ExePath < 0 )
        goto LABEL_1142;
      if ( *(_QWORD *)(v420 + 72) )
      {
        ExePath = BasepUpdateProcessParametersField(Process, 1024, 664, (__int64)&v616);
        v347 = ExePath;
      }
      if ( ExePath < 0 )
        goto LABEL_1142;
      v493 = 0;
      if ( !v409 || (v314 = *(_DWORD *)(v409 + 548), v314 == 1) )
      {
        if ( v357 )
        {
          v316 = *(unsigned int *)(v357 + 32);
          if ( (_DWORD)v316 != 1 )
          {
            v354 = 1;
            ExePath = CompleteAppExecutionAliasProcessCreationEx(
                        Process,
                        ThreadHandle[0],
                        v316,
                        FileName,
                        pszSrc,
                        v419,
                        &v493);
            v347 = ExePath;
            if ( ExePath < 0 )
              goto LABEL_1142;
            goto LABEL_1156;
          }
        }
        if ( !v418 )
        {
LABEL_1156:
          if ( (v493 & 1) != 0 )
            v349 |= 4u;
          goto LABEL_1158;
        }
        v315 = BasepFinishPackageActivationForSxS(Process, ThreadHandle[0], FileName, pszSrc, v419, &v493);
      }
      else
      {
        v355 = 1;
        v315 = CompletePackagedProcessCreationEx(
                 Process,
                 ThreadHandle[0],
                 v314 == 3,
                 v314 == 2,
                 FileName,
                 pszSrc,
                 *(_BYTE *)(v409 + 544) != 0,
                 v419,
                 &v493);
      }
      if ( v315 )
      {
        ExitStatus = -1073741823;
        v39 = v315;
        goto LABEL_89;
      }
      goto LABEL_1156;
    }
    v44 = token[0];
    v418 = token[0];
    token[0] = 0;
    packageFullNameLength = 128;
    PackageFullNameFromToken = GetPackageFullNameFromToken(v418, &packageFullNameLength, packageFullName);
    if ( (unsigned int)dword_18039D020 <= 5
      || (qword_18039D030 & 0x400000000000LL) == 0
      || (qword_18039D038 & 0x400000000000LL) != qword_18039D038 )
    {
      goto LABEL_875;
    }
    v653 = 0x1000000;
    v904 = &v653;
    v905 = 8;
    v592 = PackageFullNameFromToken;
    v906 = &v592;
    v907 = 4;
    tlgCreate1Sz_wchar_t(v908, Src);
    v234 = packageFullName;
    if ( PackageFullNameFromToken )
      v234 = L"NULL";
    tlgCreate1Sz_wchar_t(v909, v234);
    v235 = &v903;
    v236 = (char *)&unk_180359A70;
LABEL_874:
    tlgWriteTransfer_EtwEventWriteTransfer(
      (unsigned int)&dword_18039D020,
      (_DWORD)v236,
      (unsigned int)&v686,
      (unsigned int)&v685,
      6,
      (__int64)v235);
LABEL_875:
    if ( PackageFullNameFromToken )
      goto LABEL_866;
    RtlInitUnicodeString(&v490, packageFullName);
    if ( token[1] )
    {
      BasepFreeBnoIsolationParameter(&v585);
      RtlInitUnicodeString(&v585, (PCWSTR)token[1]);
      LOBYTE(v587) = 1;
      v487 = 1;
      v514 = 1;
    }
    ProcessHeap = HeapHandle;
LABEL_681:
    v23 = (wchar_t *)v422;
    v41 = v484;
    v42 = v476;
    v40 = v417;
    v43 = v485;
  }
  if ( v223 == -1073740756 && (v494 & 1) == 0 && (unsigned __int8)IsBasepProcessInvalidImagePresent(v222, v221) )
    BaseWriteErrorElevationRequiredEvent();
LABEL_828:
  BaseSetLastNTError((unsigned int)v223);
  ExitStatus = v223;
LABEL_57:
  ProcessInternalW = 0;
  v344 = 0;
LABEL_1173:
  v319 = v348;
  v318 = HeapHandle;
LABEL_1174:
  v320 = NtCurrentTeb()->LastErrorValue;
  if ( Buffer )
    RtlFreeHeap(v318, 0, Buffer);
  if ( v509 )
  {
    if ( ProcessInternalW == 1 && (unsigned int)Feature_PcaProcessTracking__private_IsEnabledDeviceUsageNoInline() )
      BasepSendPcaEvent(*(unsigned int *)(v319 + 16), v509);
    RtlFreeHeap(v318, 0, v509);
  }
  RtlFreeUnicodeString(&UnicodeString);
  if ( !v410 && (unsigned __int8)IsBasepProcessInvalidImagePresent(v322, v321) )
    BasepReleaseSxsCreateProcessUtilityStruct(v682);
  if ( v579 )
    RtlDestroyEnvironment(v579);
  v323 = v357;
  if ( v357 )
  {
    memset_0(v679, 0, 0x64u);
    Buf2 = 104;
    if ( *(_DWORD *)(v323 + 32) )
    {
      if ( (unsigned int)dword_18039D020 > 5
        && (qword_18039D030 & 0x400000000000LL) != 0
        && (qword_18039D038 & 0x400000000000LL) == qword_18039D038 )
      {
        v365 = 1;
        v808 = &v365;
        v809 = 1;
        v528 = v320;
        v810 = &v528;
        v811 = 4;
        v366 = v354;
        v812 = &v366;
        v813 = 1;
        tlgCreate1Sz_wchar_t(v814, *(_QWORD *)v357);
        if ( *(_QWORD *)(v357 + 8) )
          v327 = (const WCHAR *)CentennialActivationRemovePIIfromFilePath_Kernel();
        else
          v327 = &word_180290A38;
        tlgCreate1Sz_wchar_t(v815, v327);
        v367 = ProcessInternalW == 1;
        v816 = &v367;
        v817 = 1;
        v368 = v496 != 0;
        v818 = &v368;
        v819 = 1;
        v369 = v492 != 0;
        v820 = &v369;
        v821 = 1;
        v370 = a6 == 1;
        v822 = &v370;
        v823 = 1;
        v520 = v349;
        v824 = &v520;
        v825 = 4;
        v371 = v411 != 0;
        v826 = &v371;
        v827 = 1;
        v372 = memcmp_0(&Buf1, &Buf2, 0x68u) == 0;
        v828 = &v372;
        v829 = 1;
        v373 = v482 == 0;
        v830 = &v373;
        v831 = 1;
        v325 = &v807;
        v326 = (__int16 *)byte_180359735;
LABEL_1202:
        tlgWriteTransfer_EtwEventWriteTransfer((unsigned int)&dword_18039D020, (_DWORD)v326, 0, 0, 15, (__int64)v325);
      }
    }
    else if ( (unsigned int)dword_18039D020 > 5
           && (qword_18039D030 & 0x400000000000LL) != 0
           && (qword_18039D038 & 0x400000000000LL) == qword_18039D038 )
    {
      v398 = 1;
      v783 = &v398;
      v784 = 1;
      v518 = v320;
      v785 = &v518;
      v786 = 4;
      v399 = v354;
      v787 = &v399;
      v788 = 1;
      tlgCreate1Sz_wchar_t(v789, *(_QWORD *)v357);
      if ( *(_QWORD *)(v357 + 8) )
        v324 = (const WCHAR *)CentennialActivationRemovePIIfromFilePath_Kernel();
      else
        v324 = &word_180290A38;
      tlgCreate1Sz_wchar_t(v790, v324);
      v400 = ProcessInternalW == 1;
      v791 = &v400;
      v792 = 1;
      v401 = v496 != 0;
      v793 = &v401;
      v794 = 1;
      v402 = v492 != 0;
      v795 = &v402;
      v796 = 1;
      v403 = a6 == 1;
      v797 = &v403;
      v798 = 1;
      v519 = v349;
      v799 = &v519;
      v800 = 4;
      v404 = v411 != 0;
      v801 = &v404;
      v802 = 1;
      v405 = memcmp_0(&Buf1, &Buf2, 0x68u) == 0;
      v803 = &v405;
      v804 = 1;
      v364 = v482 == 0;
      v805 = &v364;
      v806 = 1;
      v325 = &v782;
      v326 = word_18035986A;
      goto LABEL_1202;
    }
    if ( !ProcessInternalW )
      PerformAppxLicenseRundownEx(*(_QWORD *)v357, *(_QWORD *)(v357 + 16));
    FreeAppExecutionAliasInfoEx(v357);
    v357 = 0;
  }
  if ( v420 )
  {
    BasepReleaseAppXContext();
    v420 = 0;
  }
  if ( v575 )
    BasepReleaseAppXContext();
  if ( v503 )
    NtClose(v503);
  if ( v418 )
    NtClose(v418);
  if ( v521 == 1 && (unsigned int)dword_18039D020 > 5 )
  {
    v321 = 0x400000000000LL;
    if ( (qword_18039D030 & 0x400000000000LL) != 0 && (qword_18039D038 & 0x400000000000LL) == qword_18039D038 )
    {
      v604 = 0x1000000;
      v833 = &v604;
      v834 = 8;
      v522 = v320;
      v835 = &v522;
      v836 = 4;
      tlgCreate1Sz_wchar_t(v837, Src);
      v374 = ProcessInternalW == 1;
      v838 = &v374;
      v839 = 1;
      v523 = *(_DWORD *)(v348 + 16);
      v840 = &v523;
      v841 = 4;
      tlgWriteTransfer_EtwEventWriteTransfer(
        (unsigned int)&dword_18039D020,
        (unsigned int)&unk_1803596D8,
        (unsigned int)&v686,
        (unsigned int)&v685,
        7,
        (__int64)v832);
    }
  }
  if ( Environment )
    RtlDestroyEnvironment(Environment);
  v328 = HeapHandle;
  if ( v576 )
    RtlFreeHeap(HeapHandle, 0, v576);
  if ( P )
    RtlFreeHeap(v328, 0, P);
  if ( v607 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v607);
  if ( v536 )
    RtlFreeHeap(v328, 0, v536);
  if ( Handle )
    NtClose(Handle);
  if ( v548 )
    NtClose(v548);
  if ( ThreadHandle[0] )
  {
    if ( DebugObject )
      NtRemoveProcessDebug(Process, DebugObject);
    NtTerminateProcess(Process, ExitStatus);
    NtWaitForSingleObject(Process, 0, 0);
    NtClose(ThreadHandle[0]);
  }
  v329 = Process;
  if ( Process )
    NtClose(Process);
  if ( (unsigned __int8)IsBasepProcessInvalidImagePresent(v329, v321) )
    BasepFreeAppCompatData(v504, v507, v500);
  RtlFreeUnicodeString(&v588);
  if ( (v627 || v630) && (unsigned __int8)IsBasepProcessInvalidImagePresent(v331, v330) )
    BaseDestroyVDMEnvironment(&v626, &v629);
  if ( v406 && (v406 & 8) == 0 )
  {
    if ( (unsigned __int8)IsBasepProcessInvalidImagePresent(v331, v330) )
      BaseUpdateVDMEntry(0, &NumberOfBytesToWrite_4, v406, v410);
    if ( v497 )
      NtClose(v497);
  }
  if ( lpPath )
    RtlReleasePath();
  if ( CaptureBuffer )
  {
    CsrFreeCaptureBuffer(CaptureBuffer);
    CaptureBuffer = 0;
  }
  if ( v578 )
    RtlFreeHeap(v328, 0, v578);
  if ( v549 )
    RtlFreeHeap(v328, 0, v549);
  v332 = v409;
  if ( v409 )
  {
    memset_0(v681, 0, 0x64u);
    v680 = 104;
    if ( *(_DWORD *)(v332 + 548) == 4 )
    {
      if ( (unsigned int)dword_18039D020 > 5
        && (qword_18039D030 & 0x400000000000LL) != 0
        && (qword_18039D038 & 0x400000000000LL) == qword_18039D038 )
      {
        v608 = 0x1000000;
        v756 = &v608;
        v757 = 8;
        v375 = 1;
        v758 = &v375;
        v759 = 1;
        v524 = v320;
        v760 = &v524;
        v761 = 4;
        v376 = v355;
        v762 = &v376;
        v763 = 1;
        tlgCreate1Sz_wchar_t(v764, v409 + 262);
        if ( *(_QWORD *)(v409 + 520) )
          v333 = (const WCHAR *)CentennialActivationRemovePIIfromFilePath_Kernel();
        else
          v333 = &word_180290A38;
        tlgCreate1Sz_wchar_t(v765, v333);
        v377 = ProcessInternalW == 1;
        v766 = &v377;
        v767 = 1;
        v378 = v496 != 0;
        v768 = &v378;
        v769 = 1;
        v379 = v492 != 0;
        v770 = &v379;
        v771 = 1;
        v380 = a6 == 1;
        v772 = &v380;
        v773 = 1;
        v525 = v349;
        v774 = &v525;
        v775 = 4;
        v381 = v411 != 0;
        v776 = &v381;
        v777 = 1;
        v382 = memcmp_0(&Buf1, &v680, 0x68u) == 0;
        v778 = &v382;
        v779 = 1;
        v383 = v482 == 0;
        v780 = &v383;
        v781 = 1;
        v334 = &v755;
        v335 = (__int16 *)&byte_18035957F;
        goto LABEL_1275;
      }
    }
    else if ( (unsigned int)dword_18039D020 > 5
           && (qword_18039D030 & 0x400000000000LL) != 0
           && (qword_18039D038 & 0x400000000000LL) == qword_18039D038 )
    {
      v609 = 0x1000000;
      v729 = &v609;
      v730 = 8;
      v384 = 1;
      v731 = &v384;
      v732 = 1;
      v526 = v320;
      v733 = &v526;
      v734 = 4;
      v385 = v355;
      v735 = &v385;
      v736 = 1;
      tlgCreate1Sz_wchar_t(v737, v409 + 262);
      if ( *(_QWORD *)(v409 + 520) )
        v336 = (const WCHAR *)CentennialActivationRemovePIIfromFilePath_Kernel();
      else
        v336 = &word_180290A38;
      tlgCreate1Sz_wchar_t(v738, v336);
      v386 = ProcessInternalW == 1;
      v739 = &v386;
      v740 = 1;
      v387 = v496 != 0;
      v741 = &v387;
      v742 = 1;
      v388 = v492 != 0;
      v743 = &v388;
      v744 = 1;
      v389 = a6 == 1;
      v745 = &v389;
      v746 = 1;
      v527 = v349;
      v747 = &v527;
      v748 = 4;
      v390 = v411 != 0;
      v749 = &v390;
      v750 = 1;
      v391 = memcmp_0(&Buf1, &v680, 0x68u) == 0;
      v751 = &v391;
      v752 = 1;
      v392 = v482 == 0;
      v753 = &v392;
      v754 = 1;
      v334 = &v728;
      v335 = word_18035942A;
LABEL_1275:
      tlgWriteTransfer_EtwEventWriteTransfer((unsigned int)&dword_18039D020, (_DWORD)v335, 0, 0, 16, (__int64)v334);
    }
    BasepReleasePackagedAppInfo(v409);
    v409 = 0;
  }
  BasepFreeBnoIsolationParameter(&v585);
  BasepFreeActivationTokenInfo(token);
  NtCurrentTeb()->LastErrorValue = v320;
  return ProcessInternalW;
}

```

## disassembly

```asm
0x18007f610  push    rbx
0x18007f612  push    rsi
0x18007f613  push    rdi
0x18007f614  push    r12
0x18007f616  push    r13
0x18007f618  push    r14
0x18007f61a  push    r15
0x18007f61c  mov     eax, 2240h
0x18007f621  call    __chkstk_1
0x18007f626  sub     rsp, rax
0x18007f629  mov     rax, cs:__security_cookie
0x18007f630  xor     rax, rsp
0x18007f633  mov     [rsp+2278h+var_48], rax
0x18007f63b  mov     [rsp+2278h+var_19F8], rsp
0x18007f643  mov     rax, r9
0x18007f646  mov     [rsp+2278h+var_1F20], rax
0x18007f64e  mov     rsi, r8
0x18007f651  mov     rbx, rdx
0x18007f654  mov     r13, rcx
0x18007f657  mov     [rsp+2278h+var_1E40], rcx
0x18007f65f  mov     r15, [rsp+2278h+arg_50]
0x18007f667  mov     [rsp+2278h+var_2190], r15
0x18007f66f  mov     r14d, [rsp+2278h+arg_30]
0x18007f677  mov     [rsp+2278h+lpFileName], rdx
0x18007f67f  mov     [rsp+2278h+pszSrc], r8
0x18007f687  mov     [rsp+2278h+var_1DC8], rax
0x18007f68f  mov     rax, [rsp+2278h+arg_20]
0x18007f697  mov     [rsp+2278h+var_1F38], rax
0x18007f69f  mov     [rsp+2278h+var_1DD8], rax
0x18007f6a7  mov     [rsp+2278h+var_2188], r14d
0x18007f6af  mov     rax, [rsp+2278h+arg_38]
0x18007f6b7  mov     [rsp+2278h+var_20C8], rax
0x18007f6bf  mov     rax, [rsp+2278h+arg_40]
0x18007f6c7  mov     [rsp+2278h+FileName], rax
0x18007f6cf  mov     rax, [rsp+2278h+arg_48]
0x18007f6d7  mov     [rsp+2278h+var_1B98], rax
0x18007f6df  mov     [rsp+2278h+var_1C78], r15
0x18007f6e7  xor     edi, edi
0x18007f6e9  mov     [rsp+2278h+ReturnLength], edi
0x18007f6f0  mov     dword ptr [rsp+2278h+NumberOfBytesToWrite+4], edi
0x18007f6f7  mov     [rsp+2278h+var_20E8], edi
0x18007f6fe  mov     [rsp+2278h+var_20D0], edi
0x18007f705  mov     [rsp+2278h+var_1BD8], rdi
0x18007f70d  mov     [rsp+2278h+var_1BB8], rdi
0x18007f715  mov     [rsp+2278h+var_1D38], rdi
0x18007f71d  xor     eax, eax
0x18007f71f  mov     dword ptr [rsp+2278h+Buf1+4], eax
0x18007f726  xor     edx, edx; Val
0x18007f728  lea     r8d, [rdi+64h]; Size
0x18007f72c  lea     rcx, [rsp+2278h+Buf1]; void *
0x18007f734  call    memset_0
0x18007f739  mov     [rsp+2278h+lpPath], rdi
0x18007f741  xor     edx, edx; Val
0x18007f743  mov     r8d, 3B8h; Size
0x18007f749  lea     rcx, [rsp+2278h+ApiMessage]; void *
0x18007f751  call    memset_0
0x18007f756  mov     [rsp+2278h+ReturnedLength], edi
0x18007f75d  xor     eax, eax
0x18007f75f  xorps   xmm0, xmm0
0x18007f762  movups  [rsp+2278h+var_19A8], xmm0
0x18007f76a  movups  xmmword ptr [rsp+2278h+var_1998], xmm0
0x18007f772  movups  xmmword ptr [rsp+2278h+var_1998+0Ch], xmm0
0x18007f77a  movups  [rsp+2278h+var_1978], xmm0
0x18007f782  movups  xmmword ptr [rsp+2278h+var_1968], xmm0
0x18007f78a  movups  xmmword ptr [rsp+2278h+var_1968+0Ch], xmm0
0x18007f792  mov     [rsp+2278h+var_1BA0], rdi
0x18007f79a  mov     [rsp+2278h+var_1BA8], rdi
0x18007f7a2  movups  xmmword ptr [rsp+2278h+UnicodeString.Length], xmm0
0x18007f7aa  xorps   xmm1, xmm1
0x18007f7ad  movups  xmmword ptr [rsp+2278h+DestinationString.Length], xmm1
0x18007f7b5  movups  [rsp+2278h+var_1808], xmm0
0x18007f7bd  movups  [rsp+2278h+var_17F8], xmm0
0x18007f7c5  movups  [rsp+2278h+var_2158], xmm1
0x18007f7cd  movups  [rsp+2278h+var_2148], xmm1
0x18007f7d5  movups  [rsp+2278h+var_2138], xmm1
0x18007f7dd  mov     [rsp+2278h+var_1B90], 140012h
0x18007f7e9  lea     rax, ModuleName; "ntdll.dll"
0x18007f7f0  mov     [rsp+2278h+var_1B88], rax
0x18007f7f8  xor     edx, edx; Val
0x18007f7fa  lea     r8d, [rdi+58h]; Size
0x18007f7fe  lea     rcx, [rsp+2278h+var_1C38]; void *
0x18007f806  call    memset_0
0x18007f80b  mov     [rsp+2278h+Result], edi
0x18007f812  mov     [rsp+2278h+var_1D64], edi
0x18007f819  mov     [rsp+2278h+var_1D80], edi
0x18007f820  xor     edx, edx; Val
0x18007f822  lea     r8d, [rdi+40h]; Size
0x18007f826  lea     rcx, [rsp+2278h+var_1A58]; void *
0x18007f82e  call    memset_0
0x18007f833  xorps   xmm0, xmm0
0x18007f836  movups  xmmword ptr [rsp+2278h+DynamicString.Length], xmm0
0x18007f83e  mov     qword ptr [rsp+2278h+var_1CE0.Length], rdi
0x18007f846  mov     [rsp+2278h+var_20FB], dil
0x18007f84e  mov     [rsp+2278h+Response], edi
0x18007f855  mov     [rsp+2278h+var_1F28], edi
0x18007f85c  mov     [rsp+2278h+BaseAddress], rdi
0x18007f864  mov     [rsp+2278h+RegionSize], rdi
0x18007f86c  mov     r12d, 468h
0x18007f872  mov     r8d, r12d; Size
0x18007f875  xor     edx, edx; Val
0x18007f877  lea     rcx, [rsp+2278h+var_1398]; void *
0x18007f87f  call    memset_0
0x18007f884  mov     [rsp+2278h+var_21A4], edi
0x18007f88b  mov     r8d, r12d; Size
0x18007f88e  xor     edx, edx; Val
0x18007f890  lea     rcx, [rsp+2278h+var_F28]; void *
0x18007f898  call    memset_0
0x18007f89d  mov     [rsp+2278h+var_1F68], rdi
0x18007f8a5  xorps   xmm0, xmm0
0x18007f8a8  movups  [rsp+2278h+var_1B80], xmm0
0x18007f8b0  xorps   xmm1, xmm1
0x18007f8b3  movups  xmmword ptr [rsp+2278h+var_1F60.Length], xmm1
0x18007f8bb  mov     [rsp+2278h+var_1EE0], rdi
0x18007f8c3  mov     [rsp+2278h+Environment], rdi
0x18007f8cb  mov     [rsp+2278h+var_1D20], rdi
0x18007f8d3  mov     [rsp+2278h+var_1EF0], rdi
0x18007f8db  mov     [rsp+2278h+var_20A0], rdi
0x18007f8e3  mov     [rsp+2278h+var_20BA], dil
0x18007f8eb  mov     [rsp+2278h+var_1FD0], edi
0x18007f8f2  mov     [rsp+2278h+var_2168], rdi
0x18007f8fa  mov     [rsp+2278h+var_20D8], rdi
0x18007f902  mov     [rsp+2278h+TokenHandle], rdi
0x18007f90a  mov     [rsp+2278h+ProcessInformation], dil
0x18007f912  mov     [rsp+2278h+var_2088], di
0x18007f91a  mov     [rsp+2278h+var_1E0C], di
0x18007f922  mov     [rsp+2278h+var_2084], di
0x18007f92a  xor     eax, eax
0x18007f92c  movups  [rsp+2278h+var_19E0], xmm0
0x18007f934  movups  [rsp+2278h+var_19D0], xmm0
0x18007f93c  movups  [rsp+2278h+var_19C0], xmm0
0x18007f944  mov     [rsp+2278h+var_19B0], rax
0x18007f94c  movups  [rsp+2278h+var_19F0], xmm0
0x18007f954  mov     [rsp+2278h+var_1B18], rdi
0x18007f95c  mov     [rsp+2278h+var_1D8C], edi
0x18007f963  mov     [rsp+2278h+var_1E04], edi
0x18007f96a  movups  [rsp+2278h+var_17D8], xmm0
0x18007f972  movups  [rsp+2278h+var_17E8], xmm1
0x18007f97a  movups  [rsp+2278h+var_17B0], xmm0
0x18007f982  movups  [rsp+2278h+var_17A0], xmm1
0x18007f98a  mov     [rsp+2278h+var_1D68], edi
0x18007f991  mov     [rsp+2278h+var_1B68], rdi
0x18007f999  mov     [rsp+2278h+var_1D88], edi
0x18007f9a0  test    rbx, rbx
0x18007f9a3  jnz     short loc_18007F9B4
0x18007f9a5  test    rsi, rsi
0x18007f9a8  jnz     short loc_18007F9B4
0x18007f9aa  mov     ecx, 0C0000030h
0x18007f9af  jmp     loc_180087E61
0x18007f9b4  test    r15, r15
0x18007f9b7  jz      loc_180087E5C
0x18007f9bd  mov     rbx, [rsp+2278h+var_1B98]
0x18007f9c5  test    rbx, rbx
0x18007f9c8  jz      loc_180087E5C
0x18007f9ce  mov     [rsp+2278h+var_1F18], rdi
0x18007f9d6  mov     [rsp+2278h+Process], rdi
0x18007f9de  mov     [rsp+2278h+ThreadHandle], rdi
0x18007f9e6  mov     [rsp+2278h+CaptureBuffer], rdi
0x18007f9ee  mov     [rsp+2278h+var_1CA0], edi
0x18007f9f5  mov     [rsp+2278h+FilePart], rdi
0x18007f9fd  mov     [rsp+2278h+var_1CE0.Buffer], rdi
0x18007fa05  mov     [rsp+2278h+var_20F3], dil
0x18007fa0d  mov     [rsp+2278h+ProcessHandle], rdi
0x18007fa15  mov     [rsp+2278h+var_1D18], rdi
0x18007fa1d  mov     [rsp+2278h+var_1EE8], rdi
0x18007fa25  mov     dword ptr [rsp+2278h+NumberOfBytesToWrite], edi
0x18007fa2c  mov     [rsp+2278h+var_1EC8], rdi
0x18007fa34  mov     [rsp+2278h+var_1F6C], edi
0x18007fa3b  mov     [rsp+2278h+var_1F08], rdi
0x18007fa43  mov     [rsp+2278h+var_1FA8], edi
0x18007fa4a  mov     [rsp+2278h+var_1FCC], edi
0x18007fa51  mov     [rsp+2278h+var_1DA4], edi
0x18007fa58  mov     [rsp+2278h+var_1E48], rdi
0x18007fa60  mov     [rsp+2278h+var_1F0C], edi
0x18007fa67  mov     [rsp+2278h+var_1D10], rdi
0x18007fa6f  mov     [rsp+2278h+var_1E90], edi
0x18007fa76  mov     [rsp+2278h+var_2180], edi
0x18007fa7d  mov     [rsp+2278h+var_1F2C], edi
0x18007fa84  mov     [rsp+2278h+var_1BD0], rdi
0x18007fa8c  mov     [rsp+2278h+var_1BB0], rdi
0x18007fa94  movups  [rsp+2278h+var_1A68], xmm0
0x18007fa9c  movups  [rsp+2278h+var_17C8], xmm1
0x18007faa4  mov     [rsp+2278h+var_17B8], rax
0x18007faac  movups  [rsp+2278h+var_1778], xmm0
0x18007fab4  mov     [rsp+2278h+var_1768], rax
0x18007fabc  mov     [rsp+2278h+var_1D28], rdi
0x18007fac4  mov     [rsp+2278h+var_1CCC], edi
0x18007facb  mov     [rsp+2278h+var_1D90], edi
0x18007fad2  mov     [rsp+2278h+var_1FAC], edi
0x18007fad9  movups  [rsp+2278h+var_1790], xmm0
0x18007fae1  mov     [rsp+2278h+var_1780], rax
0x18007fae9  xor     edx, edx; Val
0x18007faeb  lea     r8d, [rdx+58h]; Size
0x18007faef  lea     rcx, [rsp+2278h+var_1868]; void *
0x18007faf7  call    memset_0
0x18007fafc  xorps   xmm0, xmm0
0x18007faff  xor     eax, eax
0x18007fb01  movups  xmmword ptr [rsp+2278h+var_1D08.Length], xmm0
0x18007fb09  movups  [rsp+2278h+var_1CF8], xmm0
0x18007fb11  mov     [rsp+2278h+var_1CE8], rax
0x18007fb19  movups  xmmword ptr [rsp+2278h+token], xmm0
0x18007fb21  mov     rax, gs:60h
0x18007fb2a  mov     [rsp+2278h+var_1DF0], rax
0x18007fb32  mov     r12, [rax+30h]
0x18007fb36  mov     [rsp+2278h+HeapHandle], r12
0x18007fb3e  mov     r15d, 100h
0x18007fb44  mov     r8d, r15d; Size
0x18007fb47  xor     edx, edx; Val
0x18007fb49  lea     rcx, [rsp+2278h+packageFullName]; void *
0x18007fb51  call    memset_0
0x18007fb56  mov     esi, 1
0x18007fb5b  mov     [rsp+2278h+var_1E04], esi
0x18007fb62  mov     [rsp+2278h+var_268], di
0x18007fb6a  mov     eax, r14d
0x18007fb6d  and     eax, 18h
0x18007fb70  cmp     al, 18h
0x18007fb72  jz      short loc_18007FB8A
0x18007fb74  mov     eax, r14d
0x18007fb77  and     eax, 1000h
0x18007fb7c  mov     ecx, 800h
0x18007fb81  test    ecx, r14d
0x18007fb84  jz      short loc_18007FB9A
0x18007fb86  test    eax, eax
0x18007fb88  jz      short loc_18007FBB9
0x18007fb8a  mov     ecx, 57h ; 'W'; LastError
0x18007fb8f  call    cs:__imp_RtlSetLastWin32Error
0x18007fb95  jmp     loc_180087E66
0x18007fb9a  test    eax, eax
0x18007fb9c  jnz     short loc_18007FBB9
0x18007fb9e  mov     rax, cs:BaseStaticServerData
0x18007fba5  cmp     [rax+7F4h], dil
0x18007fbac  jz      short loc_18007FBB9
0x18007fbae  or      r14d, ecx
0x18007fbb1  mov     [rsp+2278h+var_2188], r14d
0x18007fbb9  mov     rcx, rdi
0x18007fbbc  mov     [rsp+2278h+DebugObject], rcx
0x18007fbc4  test    r14b, 40h
0x18007fbc8  jz      short loc_18007FBCF
0x18007fbca  mov     al, sil
0x18007fbcd  jmp     short loc_18007FC24
0x18007fbcf  bt      r14d, 0Eh
0x18007fbd4  jnb     short loc_18007FBDA
0x18007fbd6  mov     al, 5
0x18007fbd8  jmp     short loc_18007FC24
0x18007fbda  test    r14b, 20h
0x18007fbde  jz      short loc_18007FBEB
0x18007fbe0  mov     r15d, 2
0x18007fbe6  mov     al, r15b
0x18007fbe9  jmp     short loc_18007FC2A
0x18007fbeb  bt      r14d, 0Fh
0x18007fbf0  jnb     short loc_18007FBF6
0x18007fbf2  mov     al, 6
0x18007fbf4  jmp     short loc_18007FC24
0x18007fbf6  test    r14b, r14b
0x18007fbf9  jns     short loc_18007FBFF
0x18007fbfb  mov     al, 3
0x18007fbfd  jmp     short loc_18007FC24
0x18007fbff  test    r15d, r14d
0x18007fc02  jz      short loc_18007FC21
0x18007fc04  test    r13, r13
0x18007fc07  setnz   dl
0x18007fc0a  call    BasepIsRealtimeAllowed
0x18007fc0f  test    rax, rax
0x18007fc12  setnz   al
0x18007fc15  add     al, 3
0x18007fc17  mov     rcx, [rsp+2278h+DebugObject]
0x18007fc1f  jmp     short loc_18007FC24
0x18007fc21  mov     al, dil
0x18007fc24  mov     r15d, 2
0x18007fc2a  mov     [rsp+2278h+var_20FB], al
0x18007fc31  mov     eax, [rsp+2278h+var_2188]
0x18007fc38  and     eax, 0FFFF3E1Fh
0x18007fc3d  mov     [rsp+2278h+var_2188], eax
0x18007fc44  bt      eax, 12h
0x18007fc48  jnb     short loc_18007FC52
0x18007fc4a  or      [rsp+2278h+var_2180], 40h
0x18007fc52  bt      eax, 18h
0x18007fc56  jnb     short loc_18007FC5F
0x18007fc58  or      [rsp+2278h+var_2180], esi
0x18007fc5f  bt      eax, 10h
0x18007fc63  jnb     short loc_18007FC6E
0x18007fc65  bts     [rsp+2278h+var_2180], 8
0x18007fc6e  test    al, 4
0x18007fc70  jnz     short loc_18007FC7B
0x18007fc72  bts     [rsp+2278h+var_2180], 9
0x18007fc7b  test    al, 3
0x18007fc7d  jz      short loc_18007FCB3
0x18007fc7f  call    cs:__imp_DbgUiConnectToDbg
0x18007fc85  test    eax, eax
0x18007fc87  jns     short loc_18007FC90
0x18007fc89  mov     ecx, eax
0x18007fc8b  jmp     loc_180087E61
0x18007fc90  call    cs:__imp_DbgUiGetThreadDebugObject
0x18007fc96  mov     rcx, rax
0x18007fc99  mov     [rsp+2278h+DebugObject], rax
0x18007fca1  test    byte ptr [rsp+2278h+var_2188], r15b
0x18007fca9  jz      short loc_18007FCB3
0x18007fcab  or      [rsp+2278h+var_2180], r15d
0x18007fcb3  mov     [rsp+2278h+var_21A8], edi
0x18007fcba  mov     r14, rdi
0x18007fcbd  mov     [rsp+2278h+var_2090], rdi
  ... truncated ...
```
