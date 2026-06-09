# BaseCopyStream

- ea: `0x1800d061c`
- end: `0x1800d7542`
- name: `BaseCopyStream`
- size: `28454`
- prototype: `__int64 __fastcall(int, int, int, int, __int64, int, __int64, __int64, __int64, __int64, __int64, __int64, __int64, int, int, SECURITY_INFORMATION SecurityInfo, __int64, char, int, int, int, __int64)`
- caller_count: `3`
- callee_count: `52`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800ceb58`
- `0x1800f0120`
- `0x180105a40`

## callees

- `0x180012dc0`
- `0x180012f90`
- `0x1800134a0`
- `0x1800134d0`
- `0x180013ec0`
- `0x180048f30`
- `0x18006d010`
- `0x18007d8e4`
- `0x18009b6a4`
- `0x18009b730`
- `0x1800a5940`
- `0x1800ae290`
- `0x1800b68a0`
- `0x1800cf0f4`
- `0x1800cf810`
- `0x1800cf8c0`
- `0x1800cfa00`
- `0x1800cfa60`
- `0x1800cfb40`
- `0x1800d023c`
- `0x1800d061c`
- `0x1800e2fd4`
- `0x1800eca6c`
- `0x1800eccb4`
- `0x1800f2b84`
- `0x1800f8790`
- `0x1800f884c`
- `0x1800f89bc`
- `0x1800f8fe0`
- `0x1801045b0`
- `0x1801057f4`
- `0x180107988`
- `0x180108d00`
- `0x18010b1f8`
- `0x18010e01c`
- `0x18010fce8`
- `0x1801103d4`
- `0x1801109b8`
- `0x180110c48`
- `0x180110f5c`
- `0x18011128c`
- `0x1801125f4`
- `0x180112bcc`
- `0x1801242c8`
- `0x180125028`
- `0x18012d119`
- `0x18012e894`
- `0x18012e9d0`
- `0x180132718`
- `0x18013299c`

## import_xrefs

- `ntdll!NtQueryInformationFile` at `0x1800d0a4c`
- `ntdll!NtQueryInformationFile` at `0x1800d10e5`
- `ntdll!NtQueryInformationFile` at `0x1800d1e85`
- `ntdll!NtQueryInformationFile` at `0x1800d2055`
- `ntdll!NtQueryInformationFile` at `0x1800d21db`
- `ntdll!NtQueryInformationFile` at `0x1800d2416`
- `ntdll!NtQueryInformationFile` at `0x1800d28c3`
- `ntdll!NtQueryInformationFile` at `0x1800d2bd1`
- `ntdll!NtQueryInformationFile` at `0x1800d30ad`
- `ntdll!NtQueryInformationFile` at `0x1800d725a`
- `ntdll!NtQueryInformationFile` at `0x1800d0a4c`
- `ntdll!NtQueryInformationFile` at `0x1800d10e5`
- `ntdll!NtQueryInformationFile` at `0x1800d1e85`
- `ntdll!NtQueryInformationFile` at `0x1800d2055`
- `ntdll!NtQueryInformationFile` at `0x1800d21db`
- `ntdll!NtQueryInformationFile` at `0x1800d2416`
- `ntdll!NtQueryInformationFile` at `0x1800d28c3`
- `ntdll!NtQueryInformationFile` at `0x1800d2bd1`
- `ntdll!NtQueryInformationFile` at `0x1800d30ad`
- `ntdll!NtQueryInformationFile` at `0x1800d725a`
- `ntdll!_wcsicmp` at `0x1800d3e11`
- `ntdll!_wcsicmp` at `0x1800d3e11`
- `ntdll!RtlDeleteCriticalSection` at `0x1800d7124`
- `ntdll!RtlDeleteCriticalSection` at `0x18018bf1e`
- `ntdll!RtlDeleteCriticalSection` at `0x1800d7124`
- `ntdll!RtlDeleteCriticalSection` at `0x18018bf1e`
- `ntdll!RtlEnterCriticalSection` at `0x1800d5580`
- `ntdll!RtlEnterCriticalSection` at `0x1800d5b81`
- `ntdll!RtlEnterCriticalSection` at `0x1800d5ec8`
- `ntdll!RtlEnterCriticalSection` at `0x1800d62bf`
- `ntdll!RtlEnterCriticalSection` at `0x1800d651a`
- `ntdll!RtlEnterCriticalSection` at `0x1800d6aaa`
- `ntdll!RtlEnterCriticalSection` at `0x1800d5580`
- `ntdll!RtlEnterCriticalSection` at `0x1800d5b81`
- `ntdll!RtlEnterCriticalSection` at `0x1800d5ec8`
- `ntdll!RtlEnterCriticalSection` at `0x1800d62bf`
- `ntdll!RtlEnterCriticalSection` at `0x1800d651a`
- `ntdll!RtlEnterCriticalSection` at `0x1800d6aaa`
- `ntdll!RtlInitializeCriticalSection` at `0x1800d0c07`
- `ntdll!RtlInitializeCriticalSection` at `0x1800d0c07`
- `ntdll!RtlLeaveCriticalSection` at `0x1800d56de`
- `ntdll!RtlLeaveCriticalSection` at `0x1800d56fc`
- `ntdll!RtlLeaveCriticalSection` at `0x1800d5cb1`
- `ntdll!RtlLeaveCriticalSection` at `0x1800d5cd7`
- `ntdll!RtlLeaveCriticalSection` at `0x1800d600d`
- `ntdll!RtlLeaveCriticalSection` at `0x1800d63ea`
- `ntdll!RtlLeaveCriticalSection` at `0x1800d6791`
- `ntdll!RtlLeaveCriticalSection` at `0x1800d67b7`
- `ntdll!RtlLeaveCriticalSection` at `0x1800d6bc0`
- `ntdll!RtlLeaveCriticalSection` at `0x18018bae6`
- `ntdll!RtlLeaveCriticalSection` at `0x1800d56de`
- `ntdll!RtlLeaveCriticalSection` at `0x1800d56fc`
- `ntdll!RtlLeaveCriticalSection` at `0x1800d5cb1`
- `ntdll!RtlLeaveCriticalSection` at `0x1800d5cd7`
- `ntdll!RtlLeaveCriticalSection` at `0x1800d600d`
- `ntdll!RtlLeaveCriticalSection` at `0x1800d63ea`
- `ntdll!RtlLeaveCriticalSection` at `0x1800d6791`
- `ntdll!RtlLeaveCriticalSection` at `0x1800d67b7`
- `ntdll!RtlLeaveCriticalSection` at `0x1800d6bc0`
- `ntdll!RtlLeaveCriticalSection` at `0x18018bae6`
- `ntdll!NtSetInformationFile` at `0x1800d2099`
- `ntdll!NtSetInformationFile` at `0x1800d2234`
- `ntdll!NtSetInformationFile` at `0x1800d2366`
- `ntdll!NtSetInformationFile` at `0x1800d2b65`
- `ntdll!NtSetInformationFile` at `0x1800d311f`
- `ntdll!NtSetInformationFile` at `0x1800d324b`
- `ntdll!NtSetInformationFile` at `0x1800d39d7`
- `ntdll!NtSetInformationFile` at `0x1800d47fa`
- `ntdll!NtSetInformationFile` at `0x1800d4e8c`
- `ntdll!NtSetInformationFile` at `0x1800d5b60`
- `ntdll!NtSetInformationFile` at `0x1800d626f`
- `ntdll!NtSetInformationFile` at `0x1800d6e84`
- `ntdll!NtSetInformationFile` at `0x1800d6f10`
- `ntdll!NtSetInformationFile` at `0x18018bc7d`
- `ntdll!NtSetInformationFile` at `0x18018bd1c`
- `ntdll!NtSetInformationFile` at `0x1800d2099`
- `ntdll!NtSetInformationFile` at `0x1800d2234`
- `ntdll!NtSetInformationFile` at `0x1800d2366`
- `ntdll!NtSetInformationFile` at `0x1800d2b65`
- `ntdll!NtSetInformationFile` at `0x1800d311f`
- `ntdll!NtSetInformationFile` at `0x1800d324b`
- `ntdll!NtSetInformationFile` at `0x1800d39d7`
- `ntdll!NtSetInformationFile` at `0x1800d47fa`
- `ntdll!NtSetInformationFile` at `0x1800d4e8c`
- `ntdll!NtSetInformationFile` at `0x1800d5b60`
- `ntdll!NtSetInformationFile` at `0x1800d626f`
- `ntdll!NtSetInformationFile` at `0x1800d6e84`
- `ntdll!NtSetInformationFile` at `0x1800d6f10`
- `ntdll!NtSetInformationFile` at `0x18018bc7d`
- `ntdll!NtSetInformationFile` at `0x18018bd1c`
- `ntdll!NtFsControlFile` at `0x1800d410a`
- `ntdll!NtFsControlFile` at `0x1800d43df`
- `ntdll!NtFsControlFile` at `0x1800d410a`
- `ntdll!NtFsControlFile` at `0x1800d43df`
- `ntdll!NtQueryVolumeInformationFile` at `0x1800d23c5`
- `ntdll!NtQueryVolumeInformationFile` at `0x1800d245a`
- `ntdll!NtQueryVolumeInformationFile` at `0x1800d3031`
- `ntdll!NtQueryVolumeInformationFile` at `0x1800d32f6`
- `ntdll!NtQueryVolumeInformationFile` at `0x1800d343e`
- `ntdll!NtQueryVolumeInformationFile` at `0x1800d346a`
- `ntdll!NtQueryVolumeInformationFile` at `0x1800d350f`
- `ntdll!NtQueryVolumeInformationFile` at `0x1800d35cf`
- `ntdll!NtQueryVolumeInformationFile` at `0x1800d71dc`
- `ntdll!NtQueryVolumeInformationFile` at `0x1800d7231`
- `ntdll!NtQueryVolumeInformationFile` at `0x1800d23c5`
- `ntdll!NtQueryVolumeInformationFile` at `0x1800d245a`
- `ntdll!NtQueryVolumeInformationFile` at `0x1800d3031`
- `ntdll!NtQueryVolumeInformationFile` at `0x1800d32f6`
- `ntdll!NtQueryVolumeInformationFile` at `0x1800d343e`
- `ntdll!NtQueryVolumeInformationFile` at `0x1800d346a`
- `ntdll!NtQueryVolumeInformationFile` at `0x1800d350f`
- `ntdll!NtQueryVolumeInformationFile` at `0x1800d35cf`
- `ntdll!NtQueryVolumeInformationFile` at `0x1800d71dc`
- `ntdll!NtQueryVolumeInformationFile` at `0x1800d7231`
- `ntdll!NtCreateFile` at `0x1800d15dc`
- `ntdll!NtCreateFile` at `0x1800d16c7`
- `ntdll!NtCreateFile` at `0x1800d175d`
- `ntdll!NtCreateFile` at `0x1800d18ad`
- `ntdll!NtCreateFile` at `0x1800d196a`
- `ntdll!NtCreateFile` at `0x1800d1a32`
- `ntdll!NtCreateFile` at `0x1800d1d93`
- `ntdll!NtCreateFile` at `0x1800d1e09`
- `ntdll!NtCreateFile` at `0x1800d2a38`
- `ntdll!NtCreateFile` at `0x1800d2f23`
- `ntdll!NtCreateFile` at `0x1800d2fac`
- `ntdll!NtCreateFile` at `0x1800d2fbd`
- `ntdll!NtCreateFile` at `0x1800d3184`
- `ntdll!NtCreateFile` at `0x1800d3204`
- `ntdll!NtCreateFile` at `0x1800d15dc`
- `ntdll!NtCreateFile` at `0x1800d16c7`
- `ntdll!NtCreateFile` at `0x1800d175d`
- `ntdll!NtCreateFile` at `0x1800d18ad`
- `ntdll!NtCreateFile` at `0x1800d196a`
- `ntdll!NtCreateFile` at `0x1800d1a32`
- `ntdll!NtCreateFile` at `0x1800d1d93`
- `ntdll!NtCreateFile` at `0x1800d1e09`
- `ntdll!NtCreateFile` at `0x1800d2a38`
- `ntdll!NtCreateFile` at `0x1800d2f23`
- `ntdll!NtCreateFile` at `0x1800d2fac`
- `ntdll!NtCreateFile` at `0x1800d2fbd`
- `ntdll!NtCreateFile` at `0x1800d3184`
- `ntdll!NtCreateFile` at `0x1800d3204`
- `ntdll!RtlSetLastWin32Error` at `0x1800d0ffc`
- `ntdll!RtlSetLastWin32Error` at `0x1800d13d1`
- `ntdll!RtlSetLastWin32Error` at `0x1800d144d`
- `ntdll!RtlSetLastWin32Error` at `0x1800d7530`
- `ntdll!RtlSetLastWin32Error` at `0x1800d0ffc`
- `ntdll!RtlSetLastWin32Error` at `0x1800d13d1`
- `ntdll!RtlSetLastWin32Error` at `0x1800d144d`
- `ntdll!RtlSetLastWin32Error` at `0x1800d7530`
- `ntdll!NtWaitForSingleObject` at `0x1800d594f`
- `ntdll!NtWaitForSingleObject` at `0x1800d6122`
- `ntdll!NtWaitForSingleObject` at `0x1800d594f`
- `ntdll!NtWaitForSingleObject` at `0x1800d6122`
- `ntdll!NtCopyFileChunk` at `0x1800d575f`
- `ntdll!NtCopyFileChunk` at `0x1800d6075`
- `ntdll!NtCopyFileChunk` at `0x1800d6818`
- `ntdll!NtCopyFileChunk` at `0x1800d575f`
- `ntdll!NtCopyFileChunk` at `0x1800d6075`
- `ntdll!NtCopyFileChunk` at `0x1800d6818`
- `ntdll!TpSetWait` at `0x1800d52a0`
- `ntdll!TpSetWait` at `0x1800d52a0`
- `ntdll!TpReleaseWait` at `0x1800d6d3c`
- `ntdll!TpReleaseWait` at `0x18018bb0a`
- `ntdll!TpReleaseWait` at `0x1800d6d3c`
- `ntdll!TpReleaseWait` at `0x18018bb0a`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x1800d0fdf`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x1800d0fdf`
- `ntdll!NtQueryEaFile` at `0x1800d117a`
- `ntdll!NtQueryEaFile` at `0x1800d117a`
- `ntdll!NtFlushBuffersFile` at `0x1800d453b`
- `ntdll!NtFlushBuffersFile` at `0x1800d4646`
- `ntdll!NtFlushBuffersFile` at `0x1800d4f35`
- `ntdll!NtFlushBuffersFile` at `0x1800d501c`
- `ntdll!NtFlushBuffersFile` at `0x1800d6984`
- `ntdll!NtFlushBuffersFile` at `0x1800d6a6b`
- `ntdll!NtFlushBuffersFile` at `0x1800d453b`
- `ntdll!NtFlushBuffersFile` at `0x1800d4646`
- `ntdll!NtFlushBuffersFile` at `0x1800d4f35`
- `ntdll!NtFlushBuffersFile` at `0x1800d501c`
- `ntdll!NtFlushBuffersFile` at `0x1800d6984`
- `ntdll!NtFlushBuffersFile` at `0x1800d6a6b`
- `ntdll!RtlGetLastNtStatus` at `0x1800d716a`
- `ntdll!RtlGetLastNtStatus` at `0x1800d716a`
- `ntdll!RtlGetLastWin32Error` at `0x1800d7162`
- `ntdll!RtlGetLastWin32Error` at `0x1800d7162`
- `ntdll!RtlNtStatusToDosError` at `0x1800d2c54`
- `ntdll!RtlNtStatusToDosError` at `0x1800d3a98`
- `ntdll!RtlNtStatusToDosError` at `0x1800d3ff2`
- `ntdll!RtlNtStatusToDosError` at `0x1800d6c5b`
- `ntdll!RtlNtStatusToDosError` at `0x1800d2c54`
- `ntdll!RtlNtStatusToDosError` at `0x1800d3a98`
- `ntdll!RtlNtStatusToDosError` at `0x1800d3ff2`
- `ntdll!RtlNtStatusToDosError` at `0x1800d6c5b`
- `ntdll!TpWaitForWait` at `0x1800d6d2e`
- `ntdll!TpWaitForWait` at `0x18018bb01`
- `ntdll!TpWaitForWait` at `0x1800d6d2e`
- `ntdll!TpWaitForWait` at `0x18018bb01`
- `ntdll!wcsrchr` at `0x1800d7180`
- `ntdll!wcsrchr` at `0x1800d7180`

## pseudocode

```c
__int64 __fastcall BaseCopyStream(
        wchar_t *a1,
        HANDLE *a2,
        DWORD a3,
        const WCHAR *a4,
        void *a5,
        int a6,
        __int64 *a7,
        int *a8,
        HANDLE *a9,
        int *a10,
        _DWORD *a11,
        __int64 *a12,
        const void *a13,
        int a14,
        int a15,
        SECURITY_INFORMATION SecurityInfo,
        __int64 a17,
        char a18,
        int a19,
        unsigned int a20,
        int a21,
        _DWORD *a22)
{
  __int64 *v23; // r13
  __int64 v24; // rbx
  __int64 v25; // rdi
  BOOL v26; // ecx
  WCHAR *StaticUnicodeBuffer; // rax
  _OWORD *v28; // rcx
  __int64 v29; // rdx
  NTSTATUS v30; // ebx
  int v31; // eax
  int v32; // r14d
  bool v33; // cf
  HANDLE v34; // rax
  int v36; // ebx
  int v37; // eax
  int v38; // r8d
  int *v39; // rdx
  int v40; // eax
  int v41; // ebx
  int v42; // r12d
  int v43; // ecx
  unsigned int v44; // eax
  ULONG v45; // r13d
  int v46; // r12d
  ACCESS_MASK v47; // r15d
  int v48; // eax
  PCWSTR v49; // rbx
  NTSTATUS v50; // eax
  __int64 v51; // rcx
  NTSTATUS v52; // eax
  ULONG v53; // ecx
  int Information; // ebx
  HANDLE *v55; // r14
  ULONG v56; // ebx
  PVOID Heap; // rax
  NTSTATUS v58; // r14d
  ACCESS_MASK v59; // r14d
  ULONG v60; // r15d
  unsigned int v61; // r8d
  int v62; // edx
  unsigned int v63; // ebx
  int v64; // eax
  int v65; // ebx
  ULONG v66; // ecx
  int v67; // ebx
  BOOL v68; // ecx
  ULONG v69; // ecx
  int EncryptedFileVersion; // eax
  unsigned int v71; // ebx
  __int16 v72; // r13
  ULONG v73; // r15d
  NTSTATUS v74; // eax
  NTSTATUS v75; // ebx
  int v76; // eax
  ACCESS_MASK v77; // r15d
  ULONG v78; // r12d
  HANDLE v79; // rcx
  int v80; // ecx
  int v81; // eax
  BOOL v82; // ebx
  int v83; // r14d
  __int64 *v84; // r15
  int IsCopyOverSMBCAWithLargeMTU; // eax
  int *v86; // r12
  HANDLE Event; // rax
  void *v88; // r14
  int v89; // ebx
  int *v90; // r14
  HANDLE *v91; // rbx
  ACCESS_MASK v92; // r12d
  _DWORD *v93; // rax
  unsigned int v94; // ebx
  HANDLE v95; // r15
  int i; // r14d
  int v97; // edx
  int v98; // r8d
  int v99; // eax
  HANDLE v100; // rbx
  int v101; // r12d
  int v102; // r9d
  ULONG v103; // r14d
  unsigned int *v104; // rax
  unsigned int *v105; // rbx
  NTSTATUS v106; // r15d
  unsigned int *v107; // r14
  NTSTATUS v108; // r15d
  unsigned int v109; // ecx
  int v110; // r13d
  int *v111; // r14
  __int64 v112; // rbx
  NTSTATUS inited; // eax
  int v114; // ecx
  ULONG v115; // ebx
  _QWORD *v116; // r9
  ULONG v117; // r14d
  signed int v118; // r15d
  int v119; // eax
  int v120; // r13d
  NTSTATUS v121; // r12d
  HANDLE v122; // r12
  NTSTATUS v123; // r12d
  HANDLE v124; // r15
  __int64 v125; // rcx
  int v126; // ebx
  HANDLE *v127; // rbx
  int v128; // r8d
  int v129; // ecx
  NTSTATUS v130; // ebx
  bool v131; // zf
  __int64 v132; // r9
  __int64 v133; // r14
  int v134; // ebx
  int v135; // r15d
  __int64 v136; // rax
  int v137; // r15d
  HANDLE *v138; // r14
  int v139; // eax
  int *v140; // rcx
  BOOL v141; // eax
  int v142; // r14d
  __int64 *v143; // r15
  BOOL OverlappedResult; // eax
  DWORD v145; // r14d
  __int64 v146; // rcx
  int *v147; // rax
  __int64 v148; // r8
  __int64 v149; // rbx
  int IsCopyCancelled; // eax
  HANDLE v151; // rcx
  int v152; // ecx
  int v154; // r14d
  unsigned __int64 v155; // rbx
  int IsServerSku; // eax
  int v157; // ecx
  _DWORD *v158; // r14
  int v159; // eax
  __int64 *v160; // r9
  __int64 v161; // rcx
  __int64 v162; // rcx
  unsigned __int64 v163; // r14
  __int64 v164; // rbx
  HANDLE *v165; // r10
  __int64 v166; // rbx
  NTSTATUS Status; // ebx
  int v168; // r15d
  __int64 v169; // r13
  unsigned __int64 v170; // rcx
  unsigned __int64 v171; // rax
  char *v172; // rax
  char *v173; // rcx
  __int64 v174; // rdx
  __int64 v175; // rax
  BOOL v176; // ecx
  NTSTATUS v177; // ebx
  int v178; // r13d
  int v179; // eax
  __int64 v180; // rcx
  DWORD v181; // eax
  __int64 *v182; // rbx
  HANDLE v183; // rbx
  NTSTATUS v184; // eax
  __int64 v185; // rcx
  unsigned __int16 *v186; // rcx
  int v187; // r8d
  unsigned __int16 *v188; // r9
  int m; // edx
  int v190; // eax
  unsigned int v191; // ecx
  LPCVOID v192; // rcx
  __int64 v193; // rax
  NTSTATUS v194; // eax
  int v195; // eax
  int v196; // r15d
  PVOID v197; // rax
  _QWORD *v198; // r8
  DWORD v199; // r13d
  BOOL v200; // r14d
  __int64 *v201; // rcx
  __int64 v202; // rcx
  unsigned int v203; // ebx
  int v204; // eax
  unsigned int v205; // r14d
  __int64 v206; // rax
  unsigned int v207; // edx
  bool v208; // zf
  int v209; // eax
  HANDLE *v210; // r14
  int v211; // ecx
  __int64 v212; // rax
  int v213; // ecx
  __int64 v214; // r14
  NTSTATUS v215; // eax
  HANDLE v216; // r14
  unsigned __int16 *v217; // rcx
  int v218; // r8d
  unsigned __int16 *v219; // r9
  int n; // edx
  int v221; // eax
  unsigned int v222; // ecx
  LPCVOID v223; // rcx
  int v224; // eax
  bool v225; // zf
  HANDLE *v226; // r15
  NTSTATUS v227; // eax
  __int64 v228; // rax
  int *v229; // r14
  PVOID v230; // r15
  unsigned int jj; // ebx
  HANDLE v232; // rax
  int v233; // r8d
  __int64 v234; // r13
  unsigned int v235; // r14d
  char *v236; // rbx
  unsigned int v237; // r15d
  int v238; // edx
  int v239; // r14d
  int v240; // eax
  int v241; // eax
  __int64 v242; // r8
  unsigned int v243; // r13d
  char *v244; // rbx
  unsigned int v245; // edx
  int v246; // edx
  NTSTATUS v247; // eax
  __int64 v248; // rbx
  int v249; // r13d
  unsigned int kk; // r15d
  unsigned __int64 v251; // r14
  char *v252; // r9
  int v253; // ecx
  __int64 v254; // rax
  __int64 v255; // rcx
  unsigned int v256; // r14d
  unsigned int v257; // r15d
  __int64 v258; // rcx
  __int64 *v259; // r14
  int v260; // r15d
  __int64 v261; // rdx
  unsigned int v262; // r14d
  int v263; // edx
  int v264; // eax
  int v265; // eax
  NTSTATUS v266; // ecx
  int v267; // r8d
  NTSTATUS v268; // eax
  unsigned int v269; // ebx
  int v270; // eax
  int *v271; // r14
  __int64 v272; // r15
  _DWORD *v273; // r10
  __int64 v274; // r13
  __int64 *v275; // rbx
  unsigned int v276; // edx
  __int64 v277; // rax
  unsigned int v278; // eax
  HANDLE *v279; // rbx
  NTSTATUS v280; // ebx
  int v281; // eax
  unsigned int v282; // ecx
  __int64 v283; // rdx
  unsigned int v284; // ebx
  __int64 v285; // rdx
  HANDLE v286; // r14
  unsigned __int16 *v287; // rcx
  int v288; // r8d
  unsigned __int16 *v289; // r9
  int ii; // edx
  int v291; // eax
  unsigned int v292; // ecx
  LPCVOID v293; // rcx
  __int64 v294; // rcx
  __int64 *v295; // rbx
  __int64 v296; // rdx
  __int64 v297; // r8
  __int64 v298; // rcx
  int v299; // eax
  NTSTATUS v300; // eax
  __int64 v301; // rcx
  unsigned __int16 *v302; // rbx
  unsigned __int16 *v303; // r8
  int v304; // edx
  unsigned int v305; // ecx
  HANDLE v306; // rcx
  char *v307; // rdi
  unsigned int v308; // ebx
  unsigned int mm; // ecx
  unsigned __int64 v310; // rax
  wchar_t *v311; // rbx
  wchar_t *v312; // r12
  WCHAR *v313; // rax
  _OWORD *v314; // rcx
  __int64 v315; // rdx
  ULONG LastWin32Error; // edi
  unsigned int LastNtStatus; // r14d
  DWORD v318; // ecx
  int *v319; // rax
  const wchar_t *v320; // rdx
  FILE_INFORMATION_CLASS FileInformationClass[2]; // [rsp+A8h] [rbp-20E8h]
  unsigned int EaListLength; // [rsp+B8h] [rbp-20D8h]
  unsigned int EaListLengtha; // [rsp+B8h] [rbp-20D8h]
  ULONG EaIndex; // [rsp+C0h] [rbp-20D0h]
  ULONG RestartScan; // [rsp+C8h] [rbp-20C8h]
  unsigned int v326; // [rsp+118h] [rbp-2078h]
  int v327; // [rsp+11Ch] [rbp-2074h]
  __int64 v328; // [rsp+120h] [rbp-2070h] BYREF
  HANDLE FileHandle; // [rsp+128h] [rbp-2068h] BYREF
  HANDLE *v330; // [rsp+130h] [rbp-2060h]
  __int64 *v331; // [rsp+138h] [rbp-2058h]
  HANDLE hFile; // [rsp+140h] [rbp-2050h]
  int v333; // [rsp+148h] [rbp-2048h]
  ACCESS_MASK DesiredAccess; // [rsp+14Ch] [rbp-2044h] BYREF
  int NextSparseRange; // [rsp+150h] [rbp-2040h]
  ULONG CreateOptions; // [rsp+154h] [rbp-203Ch]
  int v337; // [rsp+158h] [rbp-2038h]
  int v338; // [rsp+15Ch] [rbp-2034h]
  unsigned int v339; // [rsp+160h] [rbp-2030h] BYREF
  unsigned int v340; // [rsp+164h] [rbp-202Ch] BYREF
  ULONG ShareAccess; // [rsp+168h] [rbp-2028h]
  int v342; // [rsp+16Ch] [rbp-2024h]
  int v343; // [rsp+170h] [rbp-2020h]
  int v344; // [rsp+174h] [rbp-201Ch]
  _BYTE InBuffer[4]; // [rsp+178h] [rbp-2018h] BYREF
  int v346; // [rsp+17Ch] [rbp-2014h]
  int v347; // [rsp+180h] [rbp-2010h]
  int k; // [rsp+184h] [rbp-200Ch] BYREF
  DWORD v349; // [rsp+188h] [rbp-2008h]
  LONG v350; // [rsp+18Ch] [rbp-2004h]
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+190h] [rbp-2000h] BYREF
  int v352; // [rsp+1A0h] [rbp-1FF0h]
  int v353; // [rsp+1A4h] [rbp-1FECh] BYREF
  ACCESS_MASK v354; // [rsp+1A8h] [rbp-1FE8h]
  ULONG v355; // [rsp+1ACh] [rbp-1FE4h]
  int *v356; // [rsp+1B0h] [rbp-1FE0h]
  unsigned int v357; // [rsp+1B8h] [rbp-1FD8h]
  int v358; // [rsp+1BCh] [rbp-1FD4h] BYREF
  _WORD v359[2]; // [rsp+1C0h] [rbp-1FD0h] BYREF
  ACCESS_MASK v360; // [rsp+1C4h] [rbp-1FCCh]
  unsigned int v361; // [rsp+1C8h] [rbp-1FC8h]
  int v362; // [rsp+1CCh] [rbp-1FC4h]
  __int64 v363; // [rsp+1D0h] [rbp-1FC0h] BYREF
  __int64 v364; // [rsp+1D8h] [rbp-1FB8h]
  _DWORD *v365; // [rsp+1E0h] [rbp-1FB0h]
  unsigned int v366; // [rsp+1E8h] [rbp-1FA8h]
  DWORD BytesReturned; // [rsp+1ECh] [rbp-1FA4h] BYREF
  __int64 v368; // [rsp+1F0h] [rbp-1FA0h] BYREF
  int v369; // [rsp+1F8h] [rbp-1F98h] BYREF
  DWORD v370; // [rsp+1FCh] [rbp-1F94h] BYREF
  __int64 v371; // [rsp+200h] [rbp-1F90h]
  LPCVOID lpBuffer; // [rsp+208h] [rbp-1F88h]
  LONG DistanceToMoveHigh[2]; // [rsp+210h] [rbp-1F80h] BYREF
  unsigned int v374; // [rsp+218h] [rbp-1F78h]
  int v375; // [rsp+21Ch] [rbp-1F74h]
  int v376; // [rsp+220h] [rbp-1F70h]
  int v377; // [rsp+224h] [rbp-1F6Ch] BYREF
  DWORD NumberOfBytesTransferred[2]; // [rsp+228h] [rbp-1F68h] BYREF
  __int64 v379; // [rsp+230h] [rbp-1F60h] BYREF
  __int64 v380; // [rsp+238h] [rbp-1F58h] BYREF
  int v381; // [rsp+240h] [rbp-1F50h]
  int v382; // [rsp+244h] [rbp-1F4Ch]
  int v383; // [rsp+248h] [rbp-1F48h]
  DWORD v384; // [rsp+24Ch] [rbp-1F44h] BYREF
  __int64 v385; // [rsp+250h] [rbp-1F40h] BYREF
  PVOID v386; // [rsp+258h] [rbp-1F38h]
  DWORD v387; // [rsp+260h] [rbp-1F30h] BYREF
  int v388; // [rsp+264h] [rbp-1F2Ch]
  HANDLE Handle; // [rsp+268h] [rbp-1F28h] BYREF
  LONG v390[2]; // [rsp+270h] [rbp-1F20h] BYREF
  __int64 v391; // [rsp+278h] [rbp-1F18h]
  LONG lDistanceToMove[2]; // [rsp+280h] [rbp-1F10h] BYREF
  __int64 v393; // [rsp+288h] [rbp-1F08h] BYREF
  LPVOID lpInBuffer; // [rsp+290h] [rbp-1F00h]
  DWORD v395[2]; // [rsp+298h] [rbp-1EF8h] BYREF
  ULONG v396; // [rsp+2A0h] [rbp-1EF0h]
  int v397; // [rsp+2A4h] [rbp-1EECh]
  int v398; // [rsp+2A8h] [rbp-1EE8h]
  int v399; // [rsp+2ACh] [rbp-1EE4h]
  int v400; // [rsp+2B0h] [rbp-1EE0h]
  BOOL v401; // [rsp+2B4h] [rbp-1EDCh]
  int v402; // [rsp+2B8h] [rbp-1ED8h]
  DWORD v403; // [rsp+2BCh] [rbp-1ED4h] BYREF
  PCWSTR SourceString; // [rsp+2C0h] [rbp-1ED0h]
  PVOID v405; // [rsp+2C8h] [rbp-1EC8h] BYREF
  wchar_t *Str; // [rsp+2D0h] [rbp-1EC0h]
  _DWORD *v407; // [rsp+2D8h] [rbp-1EB8h]
  int v408; // [rsp+2E0h] [rbp-1EB0h]
  ULONG CreateDisposition; // [rsp+2E4h] [rbp-1EACh]
  int v410; // [rsp+2E8h] [rbp-1EA8h] BYREF
  int v411; // [rsp+2ECh] [rbp-1EA4h]
  int v412; // [rsp+2F0h] [rbp-1EA0h]
  DWORD v413; // [rsp+2F4h] [rbp-1E9Ch]
  int v414; // [rsp+2F8h] [rbp-1E98h]
  __int64 v415; // [rsp+300h] [rbp-1E90h] BYREF
  PVOID P; // [rsp+308h] [rbp-1E88h]
  __int64 v417; // [rsp+310h] [rbp-1E80h] BYREF
  __int128 EaBuffer; // [rsp+318h] [rbp-1E78h] BYREF
  __int128 v419; // [rsp+328h] [rbp-1E68h]
  int v420; // [rsp+338h] [rbp-1E58h]
  BOOL v421; // [rsp+33Ch] [rbp-1E54h]
  int v422; // [rsp+340h] [rbp-1E50h]
  int v423; // [rsp+344h] [rbp-1E4Ch]
  int v424; // [rsp+348h] [rbp-1E48h]
  int v425; // [rsp+34Ch] [rbp-1E44h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+350h] [rbp-1E40h] BYREF
  __int64 v427; // [rsp+380h] [rbp-1E10h] BYREF
  PVOID v428; // [rsp+388h] [rbp-1E08h]
  PVOID v429; // [rsp+390h] [rbp-1E00h]
  struct _OVERLAPPED Overlapped; // [rsp+398h] [rbp-1DF8h] BYREF
  int v431; // [rsp+3B8h] [rbp-1DD8h]
  int v432; // [rsp+3BCh] [rbp-1DD4h]
  int v433; // [rsp+3C0h] [rbp-1DD0h]
  unsigned int v434; // [rsp+3C8h] [rbp-1DC8h]
  int v435; // [rsp+3CCh] [rbp-1DC4h]
  int v436; // [rsp+3D0h] [rbp-1DC0h]
  int v437; // [rsp+3D8h] [rbp-1DB8h]
  int v438; // [rsp+3E0h] [rbp-1DB0h]
  int v439; // [rsp+3E8h] [rbp-1DA8h]
  int *v440; // [rsp+3F0h] [rbp-1DA0h] BYREF
  int v441; // [rsp+3F8h] [rbp-1D98h]
  BOOL v442; // [rsp+3FCh] [rbp-1D94h]
  BOOL v443; // [rsp+400h] [rbp-1D90h]
  __int64 v444; // [rsp+408h] [rbp-1D88h]
  __int64 v445; // [rsp+410h] [rbp-1D80h]
  __int64 v446; // [rsp+418h] [rbp-1D78h]
  int v447; // [rsp+420h] [rbp-1D70h]
  struct _RTL_CRITICAL_SECTION CriticalSection; // [rsp+428h] [rbp-1D68h] BYREF
  HANDLE *v449; // [rsp+450h] [rbp-1D40h]
  __int64 v450; // [rsp+458h] [rbp-1D38h]
  HANDLE v451; // [rsp+460h] [rbp-1D30h]
  HANDLE *v452; // [rsp+468h] [rbp-1D28h]
  void *v453; // [rsp+470h] [rbp-1D20h]
  wchar_t *v454; // [rsp+478h] [rbp-1D18h]
  unsigned int *j; // [rsp+480h] [rbp-1D10h]
  __int128 v456; // [rsp+488h] [rbp-1D08h] BYREF
  unsigned int v457; // [rsp+498h] [rbp-1CF8h]
  int v458; // [rsp+49Ch] [rbp-1CF4h]
  int v459; // [rsp+4A0h] [rbp-1CF0h]
  unsigned __int16 *v460; // [rsp+4A8h] [rbp-1CE8h]
  HANDLE *v461; // [rsp+4B0h] [rbp-1CE0h]
  const void *v462; // [rsp+4B8h] [rbp-1CD8h]
  __int64 v463; // [rsp+4C0h] [rbp-1CD0h]
  __int64 v464; // [rsp+4C8h] [rbp-1CC8h]
  unsigned __int16 *v465; // [rsp+4D0h] [rbp-1CC0h]
  __int64 v466; // [rsp+4D8h] [rbp-1CB8h]
  __int64 *v467; // [rsp+4E0h] [rbp-1CB0h]
  __int64 v468; // [rsp+4E8h] [rbp-1CA8h]
  __int128 v469; // [rsp+4F0h] [rbp-1CA0h] BYREF
  struct _UNICODE_STRING v470; // [rsp+500h] [rbp-1C90h] BYREF
  unsigned __int16 *v471; // [rsp+510h] [rbp-1C80h]
  struct _OBJECT_ATTRIBUTES v472; // [rsp+518h] [rbp-1C78h] BYREF
  int v473; // [rsp+548h] [rbp-1C48h] BYREF
  HANDLE v474; // [rsp+550h] [rbp-1C40h]
  int v475; // [rsp+558h] [rbp-1C38h]
  __int128 FileInformation; // [rsp+1568h] [rbp-C28h] BYREF
  __int128 v477; // [rsp+1578h] [rbp-C18h]
  int v478[2]; // [rsp+1588h] [rbp-C08h]
  int v479; // [rsp+1590h] [rbp-C00h] BYREF
  __int64 v480; // [rsp+1594h] [rbp-BFCh]
  struct _UNICODE_STRING DestinationString; // [rsp+15A0h] [rbp-BF0h] BYREF
  __int64 v482; // [rsp+15B0h] [rbp-BE0h]
  __int128 v483; // [rsp+15B8h] [rbp-BD8h] BYREF
  __int128 v484; // [rsp+15C8h] [rbp-BC8h]
  __int64 v485; // [rsp+15D8h] [rbp-BB8h]
  __int128 v486; // [rsp+15E0h] [rbp-BB0h] BYREF
  __int64 OutBuffer; // [rsp+15F0h] [rbp-BA0h] BYREF
  int v488; // [rsp+15F8h] [rbp-B98h]
  __int128 InputBuffer; // [rsp+1600h] [rbp-B90h] BYREF
  __int128 v490; // [rsp+1610h] [rbp-B80h]
  GUID ActivityId; // [rsp+1620h] [rbp-B70h] BYREF
  __int128 v492; // [rsp+1630h] [rbp-B60h] BYREF
  int v493; // [rsp+1640h] [rbp-B50h]
  __int128 v494; // [rsp+1648h] [rbp-B48h] BYREF
  __int128 v495; // [rsp+1658h] [rbp-B38h]
  __int64 v496; // [rsp+1668h] [rbp-B28h]
  _OWORD v497[2]; // [rsp+1670h] [rbp-B20h] BYREF
  __int64 v498; // [rsp+1690h] [rbp-B00h]
  __int128 v499; // [rsp+1698h] [rbp-AF8h] BYREF
  __int128 v500; // [rsp+16A8h] [rbp-AE8h]
  int OutputBuffer; // [rsp+16B8h] [rbp-AD8h] BYREF
  unsigned __int64 v502; // [rsp+16C0h] [rbp-AD0h]
  char v503; // [rsp+16C8h] [rbp-AC8h] BYREF
  DWORD *v504; // [rsp+16D8h] [rbp-AB8h]
  __int64 v505; // [rsp+16E0h] [rbp-AB0h]
  int **v506; // [rsp+16E8h] [rbp-AA8h]
  __int64 v507; // [rsp+16F0h] [rbp-AA0h]
  _WORD *v508; // [rsp+16F8h] [rbp-A98h]
  __int64 v509; // [rsp+1700h] [rbp-A90h]
  _BYTE *v510; // [rsp+1708h] [rbp-A88h]
  __int64 v511; // [rsp+1710h] [rbp-A80h]
  DWORD *v512; // [rsp+1718h] [rbp-A78h]
  __int64 v513; // [rsp+1720h] [rbp-A70h]
  DWORD *v514; // [rsp+1728h] [rbp-A68h]
  __int64 v515; // [rsp+1730h] [rbp-A60h]
  char v516[16]; // [rsp+1738h] [rbp-A58h] BYREF
  char v517[16]; // [rsp+1748h] [rbp-A48h] BYREF
  int *v518; // [rsp+1758h] [rbp-A38h]
  __int64 v519; // [rsp+1760h] [rbp-A30h]
  __int64 *v520; // [rsp+1768h] [rbp-A28h]
  __int64 v521; // [rsp+1770h] [rbp-A20h]
  char v522[352]; // [rsp+1778h] [rbp-A18h] BYREF
  ULONG InputBufferLength[2]; // [rsp+18D8h] [rbp-8B8h] BYREF
  int v524; // [rsp+18E0h] [rbp-8B0h]
  int v525; // [rsp+18E4h] [rbp-8ACh]
  unsigned __int64 v526; // [rsp+18E8h] [rbp-8A8h]
  __int64 v527; // [rsp+18F0h] [rbp-8A0h]
  char v528; // [rsp+18F8h] [rbp-898h] BYREF
  _DWORD FsInformation[3]; // [rsp+1AF8h] [rbp-698h] BYREF
  wchar_t String1[266]; // [rsp+1B04h] [rbp-68Ch] BYREF
  _DWORD v531[3]; // [rsp+1D18h] [rbp-478h] BYREF
  char v532[532]; // [rsp+1D24h] [rbp-46Ch] BYREF
  _BYTE v533[464]; // [rsp+1F38h] [rbp-258h] BYREF

  SourceString = a4;
  v395[0] = a3;
  v330 = a2;
  Str = a1;
  lpBuffer = a13;
  v23 = a7;
  v331 = a7;
  v454 = a1;
  v461 = a2;
  hFile = a5;
  v453 = a5;
  v467 = a7;
  v356 = a8;
  v452 = a9;
  v463 = (__int64)a9;
  v440 = a10;
  v464 = (__int64)a10;
  v365 = a11;
  v462 = a13;
  *(_QWORD *)DistanceToMoveHigh = a17;
  v407 = a22;
  IoStatusBlock = 0;
  memset(&Overlapped, 0, sizeof(Overlapped));
  v499 = 0;
  v500 = 0;
  v393 = 0;
  v369 = 0;
  v24 = *a12;
  v328 = *a12;
  memset_0(&CriticalSection, 0, 0x40u);
  FileHandle = (HANDLE)-1LL;
  FileInformation = 0;
  v477 = 0;
  *(_QWORD *)v478 = 0;
  v363 = 0;
  k = 0;
  v358 = 0;
  v353 = 0;
  v383 = *a8;
  v343 = v383 & 0x11000;
  memset_0(v531, 0, 0x218u);
  memset_0(FsInformation, 0, 0x218u);
  EaBuffer = 0;
  v419 = 0;
  memset(&ObjectAttributes, 0, 44);
  v405 = 0;
  v25 = 0;
  v371 = 0;
  v340 = 0;
  v339 = 0;
  memset_0(&v473, 0, 0x1020u);
  v474 = *a2;
  ActivityId = 0;
  v492 = 0;
  v493 = 0;
  memset_0(v533, 0, 0x20Au);
  v26 = (v383 & 0x40000) == 0 && *a7 >= 0x40000;
  v349 = v26;
  *a11 = 0x100000;
  if ( Str == NtCurrentTeb()->StaticUnicodeBuffer )
  {
    StaticUnicodeBuffer = NtCurrentTeb()->StaticUnicodeBuffer;
    v28 = v533;
    v29 = 4;
    do
    {
      *v28 = *(_OWORD *)StaticUnicodeBuffer;
      v28[1] = *((_OWORD *)StaticUnicodeBuffer + 1);
      v28[2] = *((_OWORD *)StaticUnicodeBuffer + 2);
      v28[3] = *((_OWORD *)StaticUnicodeBuffer + 3);
      v28[4] = *((_OWORD *)StaticUnicodeBuffer + 4);
      v28[5] = *((_OWORD *)StaticUnicodeBuffer + 5);
      v28[6] = *((_OWORD *)StaticUnicodeBuffer + 6);
      v28[7] = *((_OWORD *)StaticUnicodeBuffer + 7);
      v28 += 8;
      StaticUnicodeBuffer += 64;
      --v29;
    }
    while ( v29 );
    *(_OWORD *)((char *)v28 - 6) = *(_OWORD *)(StaticUnicodeBuffer - 3);
    Str = (wchar_t *)v533;
    v454 = (wchar_t *)v533;
  }
  if ( v24 )
  {
    *(_DWORD *)(v24 + 48) = 2;
    *(_QWORD *)(v328 + 56) = *a7;
    *(_QWORD *)(v328 + 64) = 0;
    ++*(_DWORD *)(v328 + 16);
    *(_DWORD *)(v328 + 20) = 1;
    *(_DWORD *)(v328 + 24) = 1235;
    *(_QWORD *)(v328 + 32) = *a2;
    *(_QWORD *)(v328 + 40) = FileHandle;
    *(_QWORD *)(v328 + 80) = 0;
    *(_QWORD *)(v328 + 96) = 0;
  }
  BasepQueryDeviceCharacteristics(*a2, &v358);
  v30 = NtQueryInformationFile(*a2, &IoStatusBlock, &FileInformation, 0x28u, FileBasicInformation);
  v31 = 0;
  if ( v30 >= 0 )
    v31 = v478[0];
  v344 = v31;
  v32 = v31 & 0x10;
  if ( (v31 & 0x10) == 0 )
  {
    v33 = (v31 & 0x4000) != 0;
    v34 = hFile;
    if ( !v33 )
      goto LABEL_17;
    if ( hFile )
    {
LABEL_20:
      v478[0] = 0;
      goto LABEL_21;
    }
    BasepBaseCopyStreamStartActivity(&ActivityId);
  }
  v34 = hFile;
LABEL_17:
  if ( v34 )
    goto LABEL_20;
  if ( v30 < 0 )
  {
    BaseSetLastNTError((unsigned int)v30);
    return 0;
  }
LABEL_21:
  NextSparseRange = 0;
  v326 = 0;
  v352 = 0;
  v376 = 1;
  v36 = 0;
  v362 = 0;
  LODWORD(v380) = 0;
  lpInBuffer = 0;
  v386 = 0;
  v342 = 0;
  v338 = 0;
  v387 = 0;
  v346 = 0;
  v415 = 0;
  v446 = 0;
  v402 = 0;
  v370 = 0;
  v428 = 0;
  v403 = 0;
  v401 = 0;
  P = 0;
  LODWORD(v364) = 0;
  v366 = 0;
  v414 = 0;
  BytesReturned = 0;
  v384 = v383 & 0x4000000;
  v383 &= 0x8000000u;
  v390[0] = 1;
  v37 = *v356;
  if ( (*v356 & 2) != 0 )
  {
    v347 = 1;
    if ( !v32 )
      goto LABEL_25;
    *v356 = v37 & 0xFFFFFFFD;
    *(_WORD *)lpBuffer = 19139;
  }
  v347 = 0;
LABEL_25:
  LODWORD(v419) = 0;
  EaBuffer = 2u;
  RtlInitializeCriticalSection(&CriticalSection);
  if ( hFile )
  {
    v470 = 0;
    if ( v328 )
      *(_DWORD *)(v328 + 48) = 2;
    inited = RtlInitUnicodeStringEx(&v470, SourceString);
    if ( inited < 0 )
    {
      BaseSetLastNTError((unsigned int)inited);
      goto LABEL_327;
    }
    ObjectAttributes.Length = 48;
    ObjectAttributes.RootDirectory = hFile;
    ObjectAttributes.Attributes = 0;
    ObjectAttributes.ObjectName = &v470;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    *((_QWORD *)&EaBuffer + 1) = 0;
    LODWORD(v419) = 0;
    v114 = *v356 & 1;
    v115 = v114 != 0 ? 2 : 5;
    v355 = v115;
    if ( v347 || (*v356 & 0x4000) != 0 )
    {
      v116 = lpBuffer;
      v115 = *((_QWORD *)lpBuffer + 5) != 0 ? 1 : 5;
      v355 = v115;
    }
    else
    {
      v116 = lpBuffer;
    }
    v117 = 268435460;
    v350 = 268435460;
    if ( v347 )
      v117 = 268435492;
    v350 = v117;
    if ( (*v356 & 0x180) != 0 )
    {
      v117 |= 0x4000u;
      v350 = v117;
    }
    v118 = 1074790400;
    v361 = 1074790400;
    if ( a14 )
    {
      if ( (v117 |= 0x200000u, v350 = v117, v118 = -1072693248, v361 = -1072693248, !v114)
        || !v347 && (*v356 & 0x4000) == 0
        || !v116[5] )
      {
        v115 = 3;
        v355 = 3;
      }
    }
    if ( v118 >= 0 )
    {
      v119 = v362;
    }
    else
    {
      v119 = 1;
      v362 = 1;
      v381 = 1;
    }
    if ( v119
      || (v120 = v118 | 1,
          v121 = NtCreateFile(
                   &FileHandle,
                   v118 | 1,
                   &ObjectAttributes,
                   &IoStatusBlock,
                   0,
                   0,
                   7u,
                   v115,
                   v117,
                   &EaBuffer,
                   0x20u),
          v121 < 0) )
    {
      v121 = NtCreateFile(&FileHandle, v118, &ObjectAttributes, &IoStatusBlock, 0, 0, 7u, v115, v117, &EaBuffer, 0x20u);
    }
    else
    {
      v362 = 1;
      v381 = 1;
      v118 |= 1u;
      v361 = v120;
    }
    if ( v121 >= 0 )
    {
LABEL_374:
      v343 = 0;
      v110 = 0x2000000;
      v111 = v356;
      goto LABEL_375;
    }
    BaseSetLastNTError((unsigned int)v121);
    if ( v121 == -1073741773 && (unsigned __int16)(v470.Buffer[1] - 1) <= 0x1Eu )
    {
      DestinationString = 0;
      v50 = NtQueryVolumeInformationFile(hFile, &IoStatusBlock, &DestinationString, 0x10u, FileFsAttributeInformation);
      if ( ((v50 + 0x80000000) & 0x80000000) == 0 && v50 != -2147483643 )
        goto LABEL_64;
      if ( (*(_DWORD *)&DestinationString.Length & 0x10000) == 0 )
        goto LABEL_323;
    }
    if ( v121 != -1073741790 )
    {
      v51 = (unsigned int)v121;
LABEL_65:
      BaseSetLastNTError(v51);
      goto LABEL_66;
    }
    v122 = hFile;
    v50 = NtQueryInformationFile(hFile, &IoStatusBlock, &FileInformation, 0x28u, FileBasicInformation);
    if ( v50 < 0 )
    {
LABEL_64:
      v51 = (unsigned int)v50;
      goto LABEL_65;
    }
    NumberOfBytesTransferred[0] = v478[0];
    if ( (v478[0] & 1) == 0 )
      goto LABEL_66;
    FileInformation = 0;
    v477 = 0;
    v478[1] = 0;
    v478[0] = 128;
    NtSetInformationFile(v122, &IoStatusBlock, &FileInformation, 0x28u, FileBasicInformation);
    RestartScan = v117;
    EaIndex = v115;
    if ( !v362 )
    {
      v123 = NtCreateFile(
               &FileHandle,
               v118 | 1,
               &ObjectAttributes,
               &IoStatusBlock,
               0,
               0,
               7u,
               v115,
               v117,
               &EaBuffer,
               0x20u);
      if ( v123 >= 0 )
      {
        v362 = 1;
        v381 = 1;
        v361 = v118 | 1;
        goto LABEL_369;
      }
      RestartScan = v117;
      EaIndex = v115;
    }
    v123 = NtCreateFile(
             &FileHandle,
             v118,
             &ObjectAttributes,
             &IoStatusBlock,
             0,
             0,
             7u,
             EaIndex,
             RestartScan,
             &EaBuffer,
             0x20u);
LABEL_369:
    v478[0] = NumberOfBytesTransferred[0];
    v124 = hFile;
    NtSetInformationFile(hFile, &IoStatusBlock, &FileInformation, 0x28u, FileBasicInformation);
    if ( v123 < 0 )
    {
      v125 = (unsigned int)v123;
      goto LABEL_371;
    }
    goto LABEL_374;
  }
  LODWORD(v427) = 0;
  v396 = 0;
  v423 = 0;
  v429 = 0;
  v425 = 0;
  v38 = v347;
  v39 = v356;
  if ( v347 || (*v356 & 0x4000) != 0 )
  {
    v40 = BasepOpenRestartableFile(
            *v330,
            SourceString,
            *v356,
            (__int64)lpBuffer,
            (__int64)a7,
            (__int64)a12,
            v478[0],
            a14,
            (__int64)&v369);
    NextSparseRange = v40;
    v337 = v40;
    if ( v40 == 2 )
    {
      if ( (v358 & 0x10) != 0 )
        *a11 = 61440;
      v41 = 2;
      goto LABEL_32;
    }
    if ( v40 )
    {
      v39 = v356;
      v38 = v347;
      goto LABEL_35;
    }
LABEL_327:
    v42 = 26;
LABEL_328:
    v41 = 0;
    goto LABEL_1035;
  }
LABEL_35:
  if ( FileHandle != (HANDLE)-1LL )
  {
    LOBYTE(v101) = v344;
    goto LABEL_317;
  }
  LODWORD(Handle) = v32 != 0;
  v374 = -1;
  DestinationString = 0;
  v494 = 0;
  v495 = 0;
  v496 = 0;
  v469 = 0;
  LODWORD(v368) = 0;
  v442 = 0;
  v43 = *v39;
  v44 = *v39 & 0xFFFFBFFF;
  *v39 = v44;
  if ( v32 )
  {
    v45 = 268451873;
LABEL_42:
    v350 = v45;
    CreateOptions = v45;
    goto LABEL_43;
  }
  v45 = 268435524;
  v350 = 268435524;
  if ( v38 )
    v45 = 268435556;
  CreateOptions = v45;
  v350 = v45;
  if ( (v44 & 0x11000) != 0 )
  {
    v45 |= 8u;
    goto LABEL_42;
  }
LABEL_43:
  if ( (v43 & 0x140) != 0 )
  {
    v45 |= 0x4000u;
    CreateOptions = v45;
    v350 = v45;
  }
  if ( v32 )
    v46 = !(v43 & 1) + 2;
  else
    v46 = (v43 & 1) != 0 ? 2 : 5;
  v355 = v46;
  v47 = -1072627584;
  v361 = -1072627584;
  if ( (v43 & 0x2000000) == 0 )
    v47 = -1072365440;
  v360 = v47;
  v361 = v47;
  if ( v32 )
  {
    v47 = v47 & 0xBFFFFEEC | 0x113;
    v360 = v47;
    v361 = v47;
  }
  if ( (v43 & 0x2010) != 0 )
    v36 = 1;
  v362 = v36;
  v381 = v36;
  if ( (v43 & 0x2040) != 0 )
  {
    v47 |= 0x80000u;
    v360 = v47;
    v361 = v47;
  }
  if ( (v43 & 0x2020) != 0 && (v395[0] & 0x1000000) != 0 )
  {
    v47 |= 0x1000000u;
    v360 = v47;
    v361 = v47;
  }
  v48 = -1;
  if ( (v43 & 0x800000) != 0 )
    v48 = -16385;
  v333 = v48;
  v374 = v48;
  if ( a14 )
  {
    v45 |= 0x200000u;
    CreateOptions = v45;
    v350 = v45;
    v47 = v47 & 0x7FFEFFFF | 0x80000000;
    v360 = v47;
    v361 = v47;
    v46 = !(v43 & 1) + 2;
    v355 = v46;
    v362 = 1;
    v381 = 1;
  }
  lDistanceToMove[0] = v45;
  NumberOfBytesTransferred[0] = v46;
  v49 = SourceString;
  v50 = RtlInitUnicodeStringEx(&DestinationString, SourceString);
  if ( v50 < 0 )
    goto LABEL_64;
  v359[0] = v49[((unsigned __int64)DestinationString.Length >> 1) - 1];
  v52 = RtlDosPathNameToNtPathName_U_WithStatus(v49, &v469, 0, 0);
  if ( v52 < 0 )
  {
    if ( v52 == -1073741801 || v52 == -1073741670 )
    {
LABEL_73:
      BaseSetLastNTError((unsigned int)v52);
      goto LABEL_74;
    }
    v53 = 3;
LABEL_72:
    RtlSetLastWin32Error(v53);
    goto LABEL_74;
  }
  v428 = (PVOID)*((_QWORD *)&v469 + 1);
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  ObjectAttributes.ObjectName = (PUNICODE_STRING)&v469;
  ObjectAttributes.SecurityDescriptor = 0;
  v480 = 0x10100000002LL;
  v479 = 12;
  ObjectAttributes.SecurityQualityOfService = &v479;
  P = 0;
  Information = 0;
  LODWORD(v391) = 0;
  v396 = 0;
  v55 = v330;
  if ( NtQueryInformationFile(*v330, &IoStatusBlock, &v427, 4u, FileEaInformation) >= 0 )
  {
    v56 = v427;
    if ( (_DWORD)v427 )
    {
      v396 = v427;
      do
      {
        while ( 1 )
        {
          v56 *= 2;
          v396 = v56;
          Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, KernelBaseGlobalData, v56);
          P = Heap;
          if ( !Heap )
          {
LABEL_85:
            v51 = 3221225495LL;
            goto LABEL_65;
          }
          v58 = NtQueryEaFile(*v55, &IoStatusBlock, Heap, v56, 0, 0, 0, 0, 1u);
          if ( v58 < 0 )
          {
            RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
            P = 0;
            IoStatusBlock.Information = 0;
          }
          if ( v58 != -2147483643 )
            break;
          v55 = v330;
        }
        v131 = v58 == -1073741789;
        v55 = v330;
      }
      while ( v131 );
      Information = IoStatusBlock.Information;
      LODWORD(v391) = IoStatusBlock.Information;
      v396 = IoStatusBlock.Information;
    }
    else
    {
      Information = v391;
    }
  }
  v59 = v47;
  DesiredAccess = v47;
  v354 = v47;
  v60 = (unsigned int)Handle;
  ShareAccess = (unsigned int)Handle;
  v429 = P;
  v425 = Information;
  v61 = v344 & 0xFFFFEFFF;
  v344 = v61;
  v457 = v61;
  LODWORD(v379) = 0;
  v410 = 0;
  LODWORD(v385) = 0;
  v443 = 0;
  v377 = 0;
  v375 = v61 & 0x10;
  if ( (v61 & 0x10) == 0 )
  {
    v62 = v333;
    if ( (v61 & v333 & 0x4000) != 0 && (v46 == 2 || v46 == 5) )
    {
      if ( v46 == 2 )
        v63 = 1;
      else
        v63 = 2;
      v333 &= ~1u;
      v374 = v62 & 0xFFFFFFFE;
      if ( (unsigned __int8)IsEfsClientQueryProtectorsPresent() )
      {
        v64 = EfsClientDuplicateEncryptionInfo(Str, SourceString, v63, v344 & v333 & 0xDAFFB7, 0);
        v65 = v64;
        if ( v64 == 6007 )
        {
          if ( (*v356 & 0x1000000) != 0 )
            BasepTransferEncryption(0, 0, v344, k, 0);
          else
            LODWORD(v379) = 1;
          goto LABEL_98;
        }
        v69 = 6023;
        if ( v64 == 6023 )
        {
LABEL_107:
          RtlSetLastWin32Error(v69);
          goto LABEL_66;
        }
      }
      else
      {
        v65 = 50;
      }
      if ( v65 )
      {
        LODWORD(v417) = 0;
        if ( (unsigned __int8)IsEfsClientQueryProtectorsPresent() )
        {
          EncryptedFileVersion = EfsClientGetEncryptedFileVersion(Str, &v417, 0);
          if ( !EncryptedFileVersion && (unsigned int)(v417 - 5) <= 1 || EncryptedFileVersion == 50 )
          {
            v333 &= ~0x4000u;
            v374 = v333;
          }
        }
        else
        {
          EncryptedFileVersion = 50;
        }
        if ( EncryptedFileVersion )
          v66 = EncryptedFileVersion;
        else
          v66 = v65;
        goto LABEL_99;
      }
LABEL_98:
      v46 = 1;
      v355 = 1;
      v66 = 0;
LABEL_99:
      RtlSetLastWin32Error(v66);
    }
  }
  v397 = 0;
  CreateDisposition = 0;
  v67 = 1;
  v408 = 1;
  if ( !(_DWORD)v379 )
  {
    v68 = (unsigned __int8)IsGetEnterpriseActionForCopyPresent() && (int)EdpGetEdpEnforcementLevel(&v377) >= 0 && v377;
    LODWORD(v385) = v68;
    v443 = v68;
    if ( v68 )
    {
      if ( v46 == 5 )
      {
        v397 = 1;
        CreateDisposition = 5;
        v46 = 1;
        v355 = 1;
      }
      else
      {
        if ( v46 == 2 )
          v67 = 0;
        v408 = v67;
      }
    }
  }
LABEL_126:
  v71 = v333;
  while ( 1 )
  {
    while ( 1 )
    {
      if ( (((unsigned __int64)FileHandle + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
        goto LABEL_235;
      *((_QWORD *)&EaBuffer + 1) = v429;
      LODWORD(v419) = v391;
      v343 = (v45 >> 3) & 1;
      v72 = v344 & v71;
      v73 = v344 & v71 & 0xDAFFB7;
      v59 |= 1u;
      v74 = NtCreateFile(
              &FileHandle,
              v59,
              &ObjectAttributes,
              &IoStatusBlock,
              0,
              v73,
              ShareAccess,
              v46,
              CreateOptions,
              &EaBuffer,
              0x20u);
      v75 = v74;
      if ( v397 && v74 == -1073741772 )
      {
        v408 = 0;
        v397 = 0;
        v46 = CreateDisposition;
        v355 = CreateDisposition;
        v59 = DesiredAccess;
        goto LABEL_131;
      }
      if ( v74 >= 0 )
        goto LABEL_136;
      if ( v362 )
      {
        v59 = DesiredAccess;
        goto LABEL_139;
      }
      DesiredAccess &= ~0x80000000;
      v354 = DesiredAccess;
      v59 = DesiredAccess | 1;
      v75 = NtCreateFile(
              &FileHandle,
              DesiredAccess | 1,
              &ObjectAttributes,
              &IoStatusBlock,
              0,
              v73,
              ShareAccess,
              v46,
              CreateOptions,
              &EaBuffer,
              0x20u);
      if ( v75 < 0 )
      {
        v59 = DesiredAccess;
        v75 = NtCreateFile(
                &FileHandle,
                DesiredAccess,
                &ObjectAttributes,
                &IoStatusBlock,
                0,
                v73,
                ShareAccess,
                v46,
                CreateOptions,
                &EaBuffer,
                0x20u);
      }
      else
      {
LABEL_136:
        v362 = 1;
        v381 = 1;
        DesiredAccess = v59;
        v354 = v59;
      }
LABEL_139:
      if ( v75 >= 0 )
      {
        if ( (_DWORD)v385 )
        {
          BasepGetEdpFileCopyAction(
            (int)*v330,
            (int)Str,
            v344,
            (int)FileHandle,
            (__int64)v428,
            *v356,
            (__int64)&v405,
            (__int64)&v379,
            (__int64)&v410,
            &ActivityId);
          if ( (_DWORD)v379 == 2 )
          {
            if ( !v408 )
            {
              if ( (v59 & 0x10000) != 0
                || (NtClose(FileHandle),
                    FileHandle = (HANDLE)-1LL,
                    *((_QWORD *)&EaBuffer + 1) = 0,
                    LODWORD(v419) = 0,
                    NtCreateFile(
                      &FileHandle,
                      v59 | 0x10000,
                      &ObjectAttributes,
                      &IoStatusBlock,
                      0,
                      v73,
                      ShareAccess,
                      1u,
                      CreateOptions,
                      &EaBuffer,
                      0x20u) >= 0) )
              {
                BaseMarkFileForDelete(FileHandle);
              }
            }
            v69 = 356;
            goto LABEL_107;
          }
          if ( v397 )
          {
            NtClose(FileHandle);
            FileHandle = (HANDLE)-1LL;
            v46 = CreateDisposition;
            v355 = CreateDisposition;
            v75 = NtCreateFile(
                    &FileHandle,
                    v59,
                    &ObjectAttributes,
                    &IoStatusBlock,
                    0,
                    v73,
                    ShareAccess,
                    CreateDisposition,
                    CreateOptions,
                    &EaBuffer,
                    0x20u);
          }
        }
        if ( v75 >= 0 )
          break;
      }
      BaseSetLastNTError((unsigned int)v75);
      if ( (*v356 & 1) != 0 && v75 == -1073741771 )
      {
        v53 = 80;
        goto LABEL_72;
      }
      if ( v75 == -1073741638 )
      {
        v53 = 3;
        if ( v359[0] != 92 )
          v53 = 5;
        goto LABEL_72;
      }
      if ( *(char *)v356 < 0 && v75 == -1073741565 && (*v356 & 1) == 0 )
      {
        v52 = NtCreateFile(&FileHandle, 0x110000u, &ObjectAttributes, &IoStatusBlock, 0, 0x80u, 0, 1u, 0x1020u, 0, 0);
        if ( v52 < 0 )
          goto LABEL_73;
        NtClose(FileHandle);
        FileHandle = (HANDLE)-1LL;
LABEL_131:
        v45 = CreateOptions;
LABEL_132:
        v60 = ShareAccess;
        goto LABEL_126;
      }
      if ( NtCurrentTeb()->LastErrorValue == 32 || NtCurrentTeb()->LastErrorValue == 5 )
      {
        v60 = ShareAccess;
        if ( (ShareAccess & 3) != 3 )
        {
          v60 = 3;
LABEL_165:
          ShareAccess = v60;
LABEL_166:
          v45 = CreateOptions;
          goto LABEL_126;
        }
        if ( (v59 & 0x10000) != 0 )
        {
          v59 &= ~0x10000u;
LABEL_169:
          DesiredAccess = v59;
          v354 = v59;
          goto LABEL_166;
        }
      }
      else
      {
        v60 = ShareAccess;
      }
      if ( v429 && NtCurrentTeb()->LastErrorValue == 282 )
      {
        v423 = 1;
        v429 = 0;
        LODWORD(v391) = 0;
        v425 = 0;
        v59 = v360;
        goto LABEL_174;
      }
      if ( (NtCurrentTeb()->LastErrorValue == 1314 || NtCurrentTeb()->LastErrorValue == 5) && (v59 & 0x1000000) != 0 )
      {
        v59 &= ~0x1000000u;
        goto LABEL_169;
      }
      if ( NtCurrentTeb()->LastErrorValue == 5 && (v59 & 0xC0000) != 0 )
      {
        if ( (v59 & 0x40000) != 0 )
        {
          v59 &= ~0x40000u;
          goto LABEL_174;
        }
        if ( (v59 & 0x80000) != 0 )
        {
          v354 = v59 & 0xFFF7FFFF;
          v59 = v59 & 0xFFF7FFFF | v360 & 0x40000;
LABEL_174:
          v354 = v59;
          DesiredAccess = v59;
        }
        v60 = (unsigned int)Handle;
        goto LABEL_165;
      }
      v71 = v333;
      if ( (v72 & 0x4000) != 0 )
      {
        v71 = v333 & 0xFFFFBFFF;
LABEL_188:
        v333 = v71;
        v374 = v71;
        v45 = lDistanceToMove[0];
        v350 = lDistanceToMove[0];
        v59 = v360;
        DesiredAccess = v360;
        v354 = v360;
        goto LABEL_189;
      }
      if ( (v344 & 0x110) == 0x110 && (v333 & 0x100) != 0 )
      {
        v71 = v333 & 0xFFFFFEFF;
        goto LABEL_188;
      }
      if ( NtCurrentTeb()->LastErrorValue == 87 || NtCurrentTeb()->LastErrorValue == 183 )
      {
        v76 = v375;
        if ( !v375 )
          goto LABEL_74;
        if ( v46 == 3 )
        {
          v46 = 1;
          v355 = 1;
          v71 = -1;
          goto LABEL_188;
        }
      }
      else
      {
        v76 = v375;
      }
      if ( !v76 )
        goto LABEL_74;
      v77 = v360;
      if ( ((unsigned __int8)v360 & (unsigned __int8)v59 & 2) == 0 )
        goto LABEL_74;
      v360 &= ~2u;
      v361 = v77 & 0xFFFFFFFD;
      v59 = v77 & 0xFFFFFFFD;
      DesiredAccess = v77 & 0xFFFFFFFD;
      v354 = v77 & 0xFFFFFFFD;
      v46 = NumberOfBytesTransferred[0];
      v355 = NumberOfBytesTransferred[0];
      v45 = lDistanceToMove[0];
      v350 = lDistanceToMove[0];
LABEL_189:
      CreateOptions = v45;
      v60 = (unsigned int)Handle;
      ShareAccess = (unsigned int)Handle;
    }
    v45 = CreateOptions;
    if ( v375 )
    {
      if ( v46 == 1 && (v59 & 2) != 0 && (CreateOptions & 1) != 0 )
      {
        v45 = CreateOptions & 0xFFFFFFFE;
        CreateOptions = v45;
        v350 = v45;
        NtClose(FileHandle);
        v78 = ShareAccess;
        v75 = NtCreateFile(
                &FileHandle,
                v59,
                &ObjectAttributes,
                &IoStatusBlock,
                0,
                v73,
                ShareAccess,
                1u,
                v45,
                &EaBuffer,
                0x20u);
        if ( v75 < 0 )
        {
          v45 |= 1u;
          CreateOptions = v45;
          v350 = v45;
          v50 = NtCreateFile(
                  &FileHandle,
                  v59,
                  &ObjectAttributes,
                  &IoStatusBlock,
                  0,
                  v73,
                  v78,
                  1u,
                  v45,
                  &EaBuffer,
                  0x20u);
          v75 = v50;
          if ( v50 < 0 )
          {
            FileHandle = (HANDLE)-1LL;
            goto LABEL_64;
          }
        }
      }
      else if ( v46 == 3 )
      {
        v483 = 0;
        v484 = 0;
        v485 = 0;
        v75 = NtQueryInformationFile(FileHandle, &IoStatusBlock, &v483, 0x28u, FileBasicInformation);
        if ( v75 < 0 )
          goto LABEL_211;
        if ( (v485 & 0x10) == 0 )
        {
          BaseMarkFileForDelete(FileHandle);
          NtClose(FileHandle);
          FileHandle = (HANDLE)-1LL;
          v46 = 2;
          v355 = 2;
          v59 &= ~2u;
          DesiredAccess = v59;
          v354 = v59;
          goto LABEL_132;
        }
      }
    }
    if ( !(unsigned int)BasepQueryDeviceCharacteristics(FileHandle, &v353) )
      goto LABEL_211;
    v370 = 1;
    v458 = 1;
    v80 = v353;
    v81 = v353 & 0x1010;
    v82 = v81 == 16;
    LODWORD(v368) = v82;
    v442 = v82;
    v83 = 0;
    v441 = 0;
    v84 = v331;
    if ( v81 == 16 && *v331 > 0x800000 )
    {
      IsCopyOverSMBCAWithLargeMTU = (unsigned __int8)BasepIsCopyOverSMBCAWithLargeMTU(FileHandle);
      v369 = (unsigned __int8)IsCopyOverSMBCAWithLargeMTU;
      v80 = v353;
    }
    else
    {
      IsCopyOverSMBCAWithLargeMTU = 0;
      v369 = 0;
    }
    if ( (v80 & 0x10000) != 0 )
    {
      if ( !(unsigned __int8)BasepAllowProduceDirtyPagesOnCsvFs(*v84) )
        v83 = 1;
      v441 = v83;
      IsCopyOverSMBCAWithLargeMTU = v369;
    }
    if ( v347 || (v45 & 8) != 0 )
      goto LABEL_230;
    if ( !IsCopyOverSMBCAWithLargeMTU && !v83 )
      break;
    v71 = v333;
    if ( (v344 & 1) != 0 && (v333 & 1) != 0 )
    {
      memset(v497, 0, sizeof(v497));
      v498 = 0;
      v75 = NtQueryInformationFile(FileHandle, &IoStatusBlock, v497, 0x28u, FileBasicInformation);
      if ( v75 < 0 )
        goto LABEL_211;
      LODWORD(v498) = v498 & 0xFFFFFFFE;
      LODWORD(v498) = v498 | 0x80;
      v75 = NtSetInformationFile(FileHandle, &IoStatusBlock, v497, 0x28u, FileBasicInformation);
      if ( v75 < 0 )
        goto LABEL_211;
      v71 = v333 & 0xFFFFFFFE;
      v333 = v71;
      v374 = v71;
    }
    NtClose(FileHandle);
    FileHandle = (HANDLE)-1LL;
    if ( v369 || v83 )
    {
      v45 |= 8u;
      CreateOptions = v45;
      v350 = v45;
    }
    v46 = v375 != 0 ? 1 : 3;
    v355 = v46;
    v59 = DesiredAccess;
    v60 = ShareAccess;
  }
  if ( v82 )
    BasepDisableLocalFileBuffering(FileHandle);
LABEL_230:
  if ( (v344 & 1) != 0 && (v333 & 1) == 0 )
  {
    v483 = 0;
    v484 = 0;
    v485 = 0;
    v75 = NtQueryInformationFile(FileHandle, &IoStatusBlock, &v483, 0x28u, FileBasicInformation);
    v79 = FileHandle;
    if ( v75 < 0 )
      goto LABEL_212;
    LODWORD(v485) = v485 | 1;
    v75 = NtSetInformationFile(FileHandle, &IoStatusBlock, &v483, 0x28u, FileBasicInformation);
    if ( v75 < 0 )
      goto LABEL_211;
  }
  v60 = ShareAccess;
LABEL_235:
  v86 = v356;
  if ( v423 && (*(_BYTE *)v356 & 0x10) != 0 )
  {
    if ( v328 )
    {
      *(_DWORD *)(v328 + 20) = 1;
      *(_DWORD *)(v328 + 24) = 282;
      *(_QWORD *)(v328 + 64) = 0;
      *(_QWORD *)(v328 + 32) = *v330;
      *(_QWORD *)(v328 + 40) = -1;
    }
    if ( !(unsigned int)BasepCopyFileCallback(13) )
    {
      if ( (unsigned int)BasepIsCopyCancelled(v328) )
        BaseMarkFileForDelete(FileHandle);
      NtClose(FileHandle);
      goto LABEL_74;
    }
  }
  if ( a14 && FileHandle != (HANDLE)-1LL )
  {
    Event = CreateEventExW(0, 0, 0, 0x1F0003u);
    v88 = Event;
    if ( Event )
    {
      v89 = CopyReparsePoint(*v330, FileHandle, Event);
      CloseHandle(v88);
      if ( !v89 )
      {
        if ( (*(_BYTE *)v86 & 1) != 0 )
        {
          LOBYTE(v359[0]) = 1;
          NtSetInformationFile(FileHandle, &IoStatusBlock, v359, 1u, FileDispositionInformation);
        }
        *v452 = FileHandle;
        goto LABEL_66;
      }
      goto LABEL_259;
    }
LABEL_66:
    v42 = 26;
    goto LABEL_67;
  }
LABEL_259:
  v90 = *(int **)DistanceToMoveHigh;
  **(_DWORD **)DistanceToMoveHigh = 0;
  k = 0;
  if ( NtQueryVolumeInformationFile(FileHandle, &IoStatusBlock, FsInformation, 0x218u, FileFsAttributeInformation) >= 0 )
  {
    *v90 = FsInformation[0];
    v401 = 1;
    v439 = 1;
  }
  if ( NtQueryInformationFile(FileHandle, &IoStatusBlock, &v494, 0x28u, FileBasicInformation) >= 0 )
    k = v496;
  v75 = NtQueryVolumeInformationFile(*v330, &IoStatusBlock, v531, 0x218u, FileFsAttributeInformation);
  if ( v75 < 0 )
    goto LABEL_211;
  v403 = 1;
  v459 = 1;
  v91 = v330;
  if ( (v531[0] & 8) != 0 && SecurityInfo )
  {
    LODWORD(v385) = 0;
    v92 = DesiredAccess;
    if ( !(unsigned int)BasepCopySecurityInformation(
                          (int)Str,
                          (int)*v330,
                          v395[0],
                          (int)SourceString,
                          FileHandle,
                          DesiredAccess,
                          SecurityInfo,
                          v328,
                          *v90,
                          (__int64)&v385,
                          0) )
    {
      if ( (_DWORD)v385 )
      {
        BaseMarkFileForDelete(FileHandle);
        if ( v328 )
        {
          v93 = *(_DWORD **)(v328 + 112);
          if ( v93 )
            *v93 = 1;
        }
      }
      goto LABEL_66;
    }
  }
  else
  {
    v92 = DesiredAccess;
  }
  if ( (*v356 & 0x10) != 0 )
  {
    v422 = 0;
    v94 = ((unsigned int)k >> 11) & 1;
    v95 = CreateEventExA(0, 0, 0, 0x1F0003u);
    for ( i = 0; ; ++i )
    {
      v422 = i;
      if ( i >= 2 )
        break;
      v97 = *v356;
      v98 = **(_DWORD **)DistanceToMoveHigh;
      if ( v94 )
      {
        v94 = 0;
        v99 = BasepCopyCompression(*v330, FileHandle, (unsigned int)v344, (unsigned int)k, v98, v97, v95, &v328);
      }
      else
      {
        v94 = 1;
        v99 = BasepCopyEncryptionIfNeeded(
                *v330,
                SourceString,
                &FileHandle,
                &ObjectAttributes,
                v92,
                ShareAccess,
                v45 & 0xEFFFFFFF,
                v344,
                v333,
                &k,
                v98,
                v97,
                v379,
                v405,
                v410,
                &v328,
                v368,
                &ActivityId);
      }
      v337 = v99;
      NextSparseRange = v99;
      if ( !v99 )
      {
        CloseHandle(v95);
        goto LABEL_66;
      }
    }
    CloseHandle(v95);
    v90 = *(int **)DistanceToMoveHigh;
  }
  else
  {
    NextSparseRange = BasepCopyEncryptionIfNeeded(
                        *v91,
                        SourceString,
                        &FileHandle,
                        &ObjectAttributes,
                        v92,
                        v60,
                        v45 & 0xEFFFFFFF,
                        v344,
                        v333,
                        &k,
                        *v90,
                        *v356,
                        v379,
                        v405,
                        v410,
                        &v328,
                        v368,
                        &ActivityId);
    v337 = NextSparseRange;
    if ( !NextSparseRange )
      goto LABEL_66;
  }
  v100 = CreateEventExA(0, 0, 0, 0x1F0003u);
  v101 = v344;
  BasepCopyIntegrity(*v330, FileHandle, (unsigned int)v344, (unsigned int)k, *v90, v100);
  CloseHandle(v100);
  v102 = v375;
  if ( !v375 || (*v356 & 0x200) == 0 )
    goto LABEL_300;
  j = 0;
  v103 = 4096;
  v424 = 4096;
  do
  {
    v104 = (unsigned int *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, KernelBaseGlobalData, v103);
    v105 = v104;
    if ( !v104 )
      goto LABEL_85;
    v106 = NtQueryInformationFile(FileHandle, &IoStatusBlock, v104, v103, FileStreamInformation);
    if ( v106 >= 0 )
    {
      if ( !IoStatusBlock.Information )
      {
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v105);
        v105 = 0;
      }
    }
    else
    {
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v105);
      v105 = 0;
      v103 *= 2;
      v424 = v103;
    }
  }
  while ( v106 == -2147483643 || v106 == -1073741789 );
  if ( !v105 )
    goto LABEL_299;
  v107 = v105;
  for ( j = v105; ; j = v107 )
  {
    memset(&v472, 0, sizeof(v472));
    v456 = 0;
    Handle = 0;
    LOWORD(v456) = *((_WORD *)v107 + 2);
    WORD1(v456) = v456;
    *((_QWORD *)&v456 + 1) = v107 + 6;
    v472.Length = 48;
    v472.RootDirectory = FileHandle;
    v472.Attributes = 64;
    v472.ObjectName = (PUNICODE_STRING)&v456;
    v108 = NtCreateFile(&Handle, 0x110000u, &v472, &IoStatusBlock, 0, 0, 7u, 1u, 0x1020u, 0, 0);
    if ( v108 < 0 )
    {
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v105);
      BaseMarkFileForDelete(FileHandle);
      v51 = (unsigned int)v108;
      goto LABEL_65;
    }
    NtClose(Handle);
    if ( !*v107 )
      break;
    v107 = (unsigned int *)((char *)v107 + *v107);
  }
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v105);
  v101 = v344;
LABEL_299:
  v102 = v375;
LABEL_300:
  if ( v101 != k && v102 || (v101 & 0xFFFF0000) != 0 && (v101 & 0xFFFF0000) != (k & 0xFFFF0000) )
  {
    if ( v102 )
      v109 = v101 | k;
    else
      v109 = v101 & 0xFFFF0000 | k;
    for ( k = v109; ; k &= ~0x100u )
    {
      v494 = 0;
      v495 = 0;
      v496 = v109;
      v75 = NtSetInformationFile(FileHandle, &IoStatusBlock, &v494, 0x28u, FileBasicInformation);
      if ( v75 >= 0 )
        break;
      if ( (k & 0x100) == 0 || (v101 & 0x10) == 0 )
        goto LABEL_211;
      v109 = k & 0xFFFFFEFF;
    }
    k = 0;
    v75 = NtQueryInformationFile(FileHandle, &IoStatusBlock, &v494, 0x28u, FileBasicInformation);
    if ( v75 >= 0 )
    {
      k = v496;
      goto LABEL_317;
    }
LABEL_211:
    v79 = FileHandle;
LABEL_212:
    BaseMarkFileForDelete(v79);
    v51 = (unsigned int)v75;
    goto LABEL_65;
  }
LABEL_317:
  v110 = 0x2000000;
  if ( (v101 & 0x10) != 0 || (v111 = v356, (*v356 & 0x100000) != 0) )
  {
    v402 = 1;
    if ( v328 )
    {
      *(_DWORD *)(v328 + 48) = 4;
      *(_DWORD *)(v328 + 20) = 1;
      v112 = v328;
      *(_DWORD *)(v112 + 24) = RtlNtStatusToDosError(-1073741248);
      *(_QWORD *)(v328 + 64) = 0;
      *(_QWORD *)(v328 + 32) = *v330;
      *(_QWORD *)(v328 + 40) = FileHandle;
    }
    if ( !(unsigned int)BasepCopyFileCallback(3) || (unsigned int)BasepIsCopyCancelled(v328) )
    {
      v41 = 0;
      v326 = 0;
      v352 = 0;
      if ( (unsigned int)BasepIsCopyCancelled(v328) )
        BaseMarkFileForDelete(FileHandle);
    }
    else
    {
LABEL_323:
      v41 = 1;
      v326 = 1;
      v352 = 1;
    }
    v42 = 26;
    goto LABEL_1034;
  }
LABEL_375:
  if ( !v370 )
    BasepQueryDeviceCharacteristics(FileHandle, &v353);
  if ( !v401 )
  {
    memset_0(FsInformation, 0, 0x218u);
    v401 = NtQueryVolumeInformationFile(FileHandle, &IoStatusBlock, FsInformation, 0x218u, FileFsAttributeInformation) >= 0;
    v439 = v401;
  }
  v126 = v347;
  if ( v347 && (((unsigned __int8)v358 | (unsigned __int8)v353) & 0x10) == 0 )
  {
    *v111 &= ~2u;
    v126 = 0;
    v347 = 0;
    *(_WORD *)lpBuffer = 19139;
  }
  Overlapped.hEvent = CreateEventExA(0, 0, 1u, 0x1F0003u);
  if ( !Overlapped.hEvent )
  {
    v124 = hFile;
    if ( !hFile && !v126 && (*v111 & 0x4000) == 0 )
      BaseMarkFileForDelete(FileHandle);
    v125 = 3221225495LL;
    goto LABEL_371;
  }
  if ( (a18 & 2) != 0 || a20 || (FsInformation[0] & v531[0] & 0x8000000) == 0 || (v344 & 0x400000) != 0 )
  {
    v127 = v330;
LABEL_398:
    v128 = v342;
    goto LABEL_399;
  }
  memset_0(InputBufferLength, 0, 0x220u);
  memset_0(&OutputBuffer, 0, 0x220u);
  v127 = v330;
  if ( NtQueryVolumeInformationFile(*v330, &IoStatusBlock, InputBufferLength, 0x220u, FileFsVolumeInformation) < 0
    || NtQueryVolumeInformationFile(FileHandle, &IoStatusBlock, &OutputBuffer, 0x220u, FileFsVolumeInformation) < 0 )
  {
    goto LABEL_398;
  }
  v128 = v342;
  if ( v524 == (_DWORD)v502 )
    v128 = 1;
  v342 = v128;
  v400 = v128;
LABEL_399:
  v124 = hFile;
  if ( hFile || v343 || v128 || (v129 = a21) != 0 )
  {
    DestinationString = 0;
    v482 = 0;
    v130 = NtQueryVolumeInformationFile(*v127, &IoStatusBlock, &DestinationString, 0x18u, FileFsSizeInformation);
    if ( v130 < 0 )
    {
      if ( !v124 && !v347 )
      {
        v131 = (*v111 & 0x4000) == 0;
LABEL_407:
        if ( v131 )
          BaseMarkFileForDelete(FileHandle);
      }
      goto LABEL_409;
    }
    v132 = HIDWORD(v482);
    v366 = HIDWORD(v482);
    v414 = HIDWORD(v482);
    v133 = (unsigned int)(HIDWORD(v482) * v482);
    v364 = v133;
    v447 = HIDWORD(v482) * v482;
    if ( v124 || v343 || (v128 = v342) != 0 )
    {
      v130 = NtQueryVolumeInformationFile(FileHandle, &IoStatusBlock, &DestinationString, 0x18u, FileFsSizeInformation);
      if ( v130 < 0 )
      {
        if ( !v124 && !v347 )
        {
          v131 = (*v356 & 0x4000) == 0;
          goto LABEL_407;
        }
LABEL_409:
        v125 = (unsigned int)v130;
LABEL_371:
        BaseSetLastNTError(v125);
        v42 = 26;
        goto LABEL_372;
      }
      v132 = v366;
      if ( HIDWORD(v482) > v366 )
        v132 = HIDWORD(v482);
      v366 = v132;
      v414 = v132;
      if ( HIDWORD(v482) * (int)v482 > (unsigned int)v133 )
        v133 = (unsigned int)(HIDWORD(v482) * v482);
      v364 = v133;
      v447 = v133;
      v129 = a21;
      v128 = v342;
    }
    else
    {
      v129 = a21;
    }
  }
  else
  {
    LODWORD(v133) = v364;
    v132 = v366;
  }
  if ( v128 && *v331 >= (unsigned int)v133 )
  {
    *v407 |= 1u;
    v134 = 0;
    v349 = 0;
    v411 = 0;
    v135 = 0;
    v376 = 0;
    v398 = 0;
  }
  else
  {
    v128 = 0;
    v342 = 0;
    v400 = 0;
    *v407 &= ~1u;
    v134 = v349;
    v135 = v376;
  }
  if ( v128 )
  {
    v382 = v133;
  }
  else
  {
    if ( v129 || (v136 = 1, v343) )
      v136 = (unsigned int)v132;
    v382 = v136;
    v364 = v136;
  }
  if ( v135 )
  {
    v137 = 0;
    v376 = 0;
    v398 = 0;
    v138 = v330;
    if ( ((unsigned __int8)v358 & (unsigned __int8)v353 & 0x10) != 0 )
    {
      v137 = BasepCheckCopyChunkFile(*v330, FileHandle, &v499);
      v376 = v137;
      v398 = v137;
    }
    if ( !v137 && (v358 & v353 & 0x10000) != 0 )
    {
      v376 = BasepCsvCheckCopyChunkFile(*v138, FileHandle, &v499);
      v398 = v376;
      v139 = v380;
      if ( v376 )
        v139 = 1;
      LODWORD(v380) = v139;
    }
  }
  v140 = v356;
  if ( (*v356 & 0x20000000) != 0 && (v344 & 0x400200) == 0x200 && (FsInformation[0] & 0x40) != 0 )
  {
    v141 = 1;
    v338 = 1;
    v431 = 1;
    v134 = 0;
    v349 = 0;
    v411 = 0;
  }
  else
  {
    v141 = v338;
  }
  v142 = v342;
  v143 = v331;
  if ( v141 || v342 && *v331 )
  {
    v421 = 0;
    NumberOfBytesTransferred[0] = 0;
    OverlappedResult = DeviceIoControl(FileHandle, 0x900C4u, 0, 0, 0, 0, 0, &Overlapped);
    v421 = OverlappedResult;
    if ( !OverlappedResult && NtCurrentTeb()->LastErrorValue == 997 )
    {
      OverlappedResult = GetOverlappedResultEx(
                           (HANDLE)((unsigned __int64)FileHandle | 1),
                           &Overlapped,
                           NumberOfBytesTransferred,
                           0xFFFFFFFF,
                           0);
      v421 = OverlappedResult;
    }
    if ( !v142 || !OverlappedResult || v338 || (v387 = 1, (v344 & 0x200) != 0) )
      v387 = 0;
    v141 = OverlappedResult && v338;
    v338 = v141;
    v431 = v141;
    v140 = v356;
  }
  if ( !v141 )
    *v140 &= ~0x20000000u;
  v145 = v384;
  if ( !v384 && (!v347 || !*((_QWORD *)lpBuffer + 5)) )
  {
    v146 = *v143;
    if ( *v143 )
    {
      if ( v343 )
        v146 = ~(v366 - 1LL) & (v366 + v146 - 1);
      v363 = v146;
      if ( NtSetInformationFile(FileHandle, &IoStatusBlock, &v363, 8u, FileEndOfFileInformation) == -1073741697 )
      {
        if ( !v383 )
        {
          BaseSetLastNTError(3221225599LL);
          if ( (*v356 & 0x4000) == 0 )
            BaseMarkFileForDelete(FileHandle);
          CloseHandle(FileHandle);
LABEL_74:
          FileHandle = (HANDLE)-1LL;
          goto LABEL_66;
        }
        v145 = 1;
        v384 = 1;
      }
    }
  }
  v147 = v356;
  if ( (*v356 & 0x4000) != 0 )
    v25 = *((_QWORD *)lpBuffer + 5);
  else
    v25 = 0;
  v371 = v25;
  v402 = 1;
  v148 = v328;
  if ( v328 )
  {
    *(_DWORD *)(v328 + 20) = 1;
    v149 = v328;
    *(_DWORD *)(v149 + 24) = RtlNtStatusToDosError(-1073741248);
    *(_QWORD *)(v328 + 56) = *v143;
    *(_QWORD *)(v328 + 64) = v25;
    *(_QWORD *)(v328 + 32) = *v330;
    *(_QWORD *)(v328 + 40) = FileHandle;
    if ( !(unsigned int)BasepCopyFileCallback(3) || (unsigned int)BasepIsCopyCancelled(v328) )
    {
      IsCopyCancelled = BasepIsCopyCancelled(v328);
      v124 = hFile;
      if ( IsCopyCancelled )
      {
        v151 = FileHandle;
        if ( hFile )
          v151 = hFile;
        BaseMarkFileForDelete(v151);
      }
      v125 = 3221226048LL;
      goto LABEL_371;
    }
    v134 = v349;
    v147 = v356;
  }
  if ( !*v143 )
    goto LABEL_323;
  v152 = v347;
  if ( v347 || (*v147 & 0x4000) != 0 )
  {
    v25 = *((_QWORD *)lpBuffer + 5);
    v371 = v25;
  }
  if ( v134 )
  {
    v134 &= -((unsigned int)PrivCopyOffloadCapable(
                              (unsigned int)*v330,
                              (_DWORD)FileHandle,
                              v358 & 0x10,
                              v353 & 0x10,
                              (__int64)&v393) != 0);
    v349 = v134;
    v411 = v134;
    v152 = v347;
  }
  if ( v383 && v145 )
  {
    v134 = 0;
    v349 = 0;
    v411 = 0;
    v376 = 0;
    v398 = 0;
  }
  if ( (v358 & 0x10) != 0 || (v353 & 0x10) != 0 )
    a19 = 0;
  v377 = a19;
  if ( v152 )
  {
    if ( (v358 & 0x10) != 0 && (unsigned int)BasepRemoteIsSMBv1(*v330) )
    {
      v158 = v365;
      *v365 = 61440;
    }
    else
    {
      v158 = v365;
      *v365 = 0x10000;
    }
    if ( a20 )
    {
      if ( !v343 || !(unsigned int)BasepCopyIsServerSku() )
        v110 = 0x100000;
      BasepCopyTuneThrottlingParams(a19, v364, a20, 1, v110, (__int64)v158);
    }
LABEL_558:
    v160 = v331;
  }
  else
  {
    v154 = 0;
    v432 = 0;
    if ( (v358 & 0x10) != 0 && (unsigned int)BasepRemoteIsSMBv1(*v330)
      || (v353 & 0x10) != 0 && (unsigned int)BasepRemoteIsSMBv1(FileHandle) )
    {
      v154 = 1;
      v432 = 1;
    }
    if ( v369 )
      BasepCopyGetSMBCAChunkInfo(v365, &v340, v148, v132);
    else
      BasepCopyGetChunkInfo(v365, &v340, v148, v132);
    if ( !*v365 )
    {
      if ( v154 )
      {
        LODWORD(v155) = 0x8000;
        goto LABEL_521;
      }
      if ( v369 )
      {
        LODWORD(v155) = 0x800000;
        goto LABEL_521;
      }
      v155 = *v331;
      if ( (unsigned __int64)*v331 > 0x40000000 && v343 && (unsigned int)BasepCopyIsServerSku() )
      {
        LODWORD(v155) = 0x2000000;
        goto LABEL_521;
      }
      if ( v155 > 0x100000 )
      {
        LODWORD(v155) = 0x100000;
        v333 = 0x100000;
      }
      else
      {
LABEL_521:
        v333 = v155;
      }
      *v365 = v155;
      v134 = v349;
    }
    if ( a19 || a20 )
    {
      if ( !v343 || (IsServerSku = BasepCopyIsServerSku(), v157 = 0x2000000, !IsServerSku) )
        v157 = 0x100000;
      BasepCopyTuneThrottlingParams(
        a19,
        v364,
        a20,
        (((unsigned __int8)v358 | (unsigned __int8)v353) & 0x10) != 0,
        v157,
        (__int64)v365);
      if ( a20 )
        v340 = 1;
    }
    if ( v340 )
    {
LABEL_534:
      v158 = v365;
      goto LABEL_558;
    }
    if ( v154 )
    {
      v340 = 16;
      goto LABEL_534;
    }
    v158 = v365;
    if ( v369 && *v365 >= 0x800000u || *v365 >= 0x2000000u )
    {
      v340 = 2;
      goto LABEL_558;
    }
    if ( !_wcsicmp(String1, L"FAT") )
    {
      v340 = 1;
      goto LABEL_558;
    }
    if ( (v343 || (((unsigned __int8)v358 | (unsigned __int8)v353) & 0x10) != 0) && (!v383 || !v384) )
    {
      v340 = 8;
      v159 = 7;
    }
    else
    {
      v340 = 3;
      v159 = 2;
    }
    v160 = v331;
    if ( *v331 <= (unsigned int)(*v158 * v159) )
      v340 = ((unsigned int)*v158 + *v331 - 1) / (unsigned int)*v158;
  }
  v161 = ~((_DWORD)v364 - 1) & (unsigned int)(*v158 + v364 - 1);
  *v158 = v161;
  if ( v328 )
    *(_QWORD *)(v328 + 96) = v25 / v161;
  if ( !v134 || *v160 < v25 )
  {
    v42 = 26;
    goto LABEL_664;
  }
  memset_0(&OutputBuffer, 0, 0x210u);
  *(_QWORD *)DistanceToMoveHigh = v25;
  v399 = 0;
  v427 = (((unsigned __int64)MEMORY[0x7FFE0004] << 32) * (unsigned __int128)(unsigned __int64)(MEMORY[0x7FFE0320] << 8)) >> 64;
  v162 = v25;
  *(_QWORD *)NumberOfBytesTransferred = v25;
  v23 = v331;
  if ( *v331 == v25 )
  {
    v41 = 1;
LABEL_32:
    v326 = v41;
    v352 = v41;
    v42 = 26;
    goto LABEL_1035;
  }
  v163 = 0;
  if ( v328 )
  {
    *(_DWORD *)(v328 + 20) = 1;
    v164 = v328;
    *(_DWORD *)(v164 + 24) = RtlNtStatusToDosError(-1073741248);
    v165 = v330;
    *(_QWORD *)(v328 + 32) = *v330;
    *(_QWORD *)(v328 + 40) = FileHandle;
    v162 = v25;
  }
  else
  {
    v165 = v330;
  }
  if ( a20 )
    v163 = (((unsigned __int64)a20 << 10 >> 2) + 0xFFFFF) & 0xFFFFFFFFFFF00000uLL;
  v166 = v162;
  *(_QWORD *)v395 = v162;
  v42 = 26;
  while ( 2 )
  {
    InputBuffer = 0x20u;
    v490 = (unsigned __int64)v25;
    *((_QWORD *)&v490 + 1) = (*v23 - v166 + 0xFFFFF) & 0xFFFFFFFFFFF00000uLL;
    Status = NtFsControlFile(
               *v165,
               Overlapped.hEvent,
               0,
               &Overlapped,
               &IoStatusBlock,
               0x94264u,
               &InputBuffer,
               0x20u,
               &OutputBuffer,
               0x210u);
    if ( Status == 259 )
      WaitForSingleObjectEx(Overlapped.hEvent, 0xFFFFFFFF, 0);
    if ( Status >= 0 )
      Status = IoStatusBlock.Status;
    PrivCopyOffloadStatus(1, (unsigned int)Status, v393);
    if ( Status < 0 || OutputBuffer != 528 )
    {
      v399 = 1;
LABEL_649:
      if ( v328 )
        *(_DWORD *)(v328 + 88) &= ~1u;
      goto LABEL_651;
    }
    if ( !v502 )
      goto LABEL_579;
    v168 = 1;
    while ( 2 )
    {
      memset_0(InputBufferLength, 0, 0x220u);
      v486 = 0;
      v169 = v25;
      v417 = (((unsigned __int64)MEMORY[0x7FFE0004] << 32)
            * (unsigned __int128)(unsigned __int64)(MEMORY[0x7FFE0320] << 8)) >> 64;
      *(_QWORD *)InputBufferLength = 544;
      v524 = v25;
      v525 = HIDWORD(v371);
      v170 = v502 - v25 + *(_QWORD *)DistanceToMoveHigh;
      v526 = v170;
      if ( v163 && v170 > v163 )
      {
        v170 = v163;
        v526 = v163;
        v171 = v163;
      }
      else
      {
        v171 = v502 - v25 + *(_QWORD *)DistanceToMoveHigh;
      }
      if ( v171 > 0x10000000 )
        v170 = 0x10000000;
      v526 = v170;
      v527 = v25 - *(_QWORD *)v395;
      v172 = &v528;
      v173 = &v503;
      v174 = 4;
      do
      {
        *(_OWORD *)v172 = *(_OWORD *)v173;
        *((_OWORD *)v172 + 1) = *((_OWORD *)v173 + 1);
        *((_OWORD *)v172 + 2) = *((_OWORD *)v173 + 2);
        *((_OWORD *)v172 + 3) = *((_OWORD *)v173 + 3);
        *((_OWORD *)v172 + 4) = *((_OWORD *)v173 + 4);
        *((_OWORD *)v172 + 5) = *((_OWORD *)v173 + 5);
        *((_OWORD *)v172 + 6) = *((_OWORD *)v173 + 6);
        *((_OWORD *)v172 + 7) = *((_OWORD *)v173 + 7);
        v172 += 128;
        v173 += 128;
        --v174;
      }
      while ( v174 );
      if ( v328 )
      {
        *(_DWORD *)(v328 + 48) = 3;
        *(_QWORD *)(v328 + 64) = v25;
        *(_QWORD *)(v328 + 72) = v526;
        *(_QWORD *)(v328 + 80) = *(_QWORD *)(v328 + 96);
        *(_DWORD *)(v328 + 88) |= 1u;
        v175 = *v331 - v25;
        if ( *(_QWORD *)(v328 + 72) > v175 )
          *(_QWORD *)(v328 + 72) = v175;
        if ( v390[0] )
          v176 = BasepCopyFileCallback(1) == 0;
        else
          v176 = 0;
        if ( v176 || (unsigned int)BasepIsCopyCancelled(v328) )
        {
          v179 = BasepIsCopyCancelled(v328);
          v124 = hFile;
          if ( v179 && !hFile )
            BaseMarkFileForDelete(FileHandle);
          v180 = 3221226048LL;
          goto LABEL_611;
        }
        v390[0] = 0;
        v412 = 0;
      }
      v177 = NtFsControlFile(
               FileHandle,
               Overlapped.hEvent,
               0,
               &Overlapped,
               &IoStatusBlock,
               0x98268u,
               InputBufferLength,
               InputBufferLength[0],
               &v486,
               0x10u);
      if ( v177 == 259 )
        WaitForSingleObjectEx(Overlapped.hEvent, 0xFFFFFFFF, 0);
      if ( v177 >= 0 )
        v177 = IoStatusBlock.Status;
      PrivCopyOffloadStatus(2, (unsigned int)v177, v393);
      if ( v177 >= 0 )
      {
        v168 = 0;
        v25 += *((_QWORD *)&v486 + 1);
        v371 = v25;
        v181 = BytesReturned + 1;
        BytesReturned = v181;
        v413 = v181;
        if ( v347 )
        {
          if ( (v181 & 3) != 0 || !v25 )
          {
            v182 = v331;
            if ( v25 != *v331 )
            {
LABEL_631:
              if ( v328 )
              {
                *(_DWORD *)(v328 + 48) = 4;
                *(_QWORD *)(v328 + 8) += *((_QWORD *)&v486 + 1);
                *(_QWORD *)(v328 + 64) = v25;
                *(_QWORD *)(v328 + 72) = *((_QWORD *)&v486 + 1);
                v193 = *v182 - v169;
                if ( *(_QWORD *)(v328 + 72) > v193 )
                  *(_QWORD *)(v328 + 72) = v193;
                if ( !(unsigned int)BasepCopyFileCallback(2) || (unsigned int)BasepIsCopyCancelled(v328) )
                {
                  v195 = BasepIsCopyCancelled(v328);
                  v124 = hFile;
                  if ( v195 && !hFile )
                    BaseMarkFileForDelete(FileHandle);
                  BaseSetLastNTError(3221226048LL);
                  v23 = v331;
                  if ( v25 > *v331 )
                  {
                    v25 = *v331;
                    v371 = *v331;
                  }
                  goto LABEL_373;
                }
                ++*(_QWORD *)(v328 + 96);
                v390[0] = 1;
                v412 = 1;
              }
              if ( a20 && v25 < *v182 && v25 > *(__int64 *)NumberOfBytesTransferred )
                BasepCopyThrottlingDelay(v25 - NumberOfBytesTransferred[0], DWORD2(v486), v427, v417, a20);
              if ( v25 - *(_QWORD *)DistanceToMoveHigh >= v502 )
              {
                v178 = v399;
                goto LABEL_643;
              }
              continue;
            }
          }
          *(_QWORD *)lDistanceToMove = 0;
          v370 = 0;
          v183 = FileHandle;
          if ( hFile )
            v183 = hFile;
          v184 = NtFlushBuffersFile(v183, &IoStatusBlock);
          if ( v184 < 0 )
            goto LABEL_619;
          *(_QWORD *)lDistanceToMove = v25;
          if ( v25 > *v331 )
            *(_QWORD *)lDistanceToMove = *v331;
          SetFilePointer(v183, 0, 0, 0);
          v186 = (unsigned __int16 *)lpBuffer;
          *((_QWORD *)lpBuffer + 5) = *(_QWORD *)lDistanceToMove;
          v187 = 26;
          v433 = 26;
          v188 = v186;
          v460 = v186;
          for ( m = 0; ; m = (unsigned __int16)v191 + HIWORD(v191) )
          {
            v190 = v187--;
            v433 = v187;
            if ( !v190 )
              break;
            v191 = m + *v188++;
            v460 = v188;
          }
          v192 = lpBuffer;
          *((_DWORD *)lpBuffer + 13) = (unsigned __int16)(m + HIWORD(m));
          NextSparseRange = WriteFile(v183, v192, 0x38u, &v370, 0);
          v337 = NextSparseRange;
          if ( !NextSparseRange || v370 != 56 )
            goto LABEL_736;
          v184 = NtFlushBuffersFile(v183, &IoStatusBlock);
          if ( v184 < 0 )
            goto LABEL_619;
          SetFilePointer(v183, lDistanceToMove[0], &lDistanceToMove[1], 0);
        }
        v182 = v331;
        goto LABEL_631;
      }
      break;
    }
    v178 = v168;
    v399 = v168;
    if ( v168 && v177 == -1073740699 && !v25 )
      PrivCopyOffloadStatus(2, 3221226596LL, v393);
LABEL_643:
    if ( v178 )
      goto LABEL_649;
    *(_QWORD *)DistanceToMoveHigh = v25;
    v166 = v25;
    if ( v25 < (unsigned __int64)*v331 )
    {
      *(_QWORD *)v395 = v25;
      v23 = v331;
      v165 = v330;
      continue;
    }
    break;
  }
  if ( v25 < *v331
    || !v343
    || (v363 = *v331,
        v194 = NtSetInformationFile(FileHandle, &IoStatusBlock, &v363, 8u, FileEndOfFileInformation),
        v194 >= 0) )
  {
    v23 = v331;
    if ( v25 > *v331 )
      v25 = *v331;
    v371 = v25;
    goto LABEL_579;
  }
  BaseSetLastNTError((unsigned int)v194);
  v326 = 0;
  v352 = 0;
LABEL_651:
  if ( v393 )
  {
    PrivCopyOffloadStatus(3, 0, v393);
    v393 = 0;
  }
  v413 = 0;
LABEL_664:
  if ( !v376 )
  {
    v41 = 0;
    v349 = 0;
    goto LABEL_751;
  }
  OutBuffer = 0;
  v488 = 0;
  v196 = 1;
  v435 = 1;
  BytesReturned = 0;
  v197 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, KernelBaseGlobalData, 0x1B8u);
  lpInBuffer = v197;
  if ( !v197 )
  {
    v185 = 3221225495LL;
    goto LABEL_620;
  }
  memset_0(v197, 0, 0x1B8u);
  v198 = lpInBuffer;
  *(_OWORD *)lpInBuffer = v499;
  v198[2] = v500;
  v339 = 0x1000000;
  v199 = 0;
  v349 = 0;
  v200 = NextSparseRange;
  v201 = v331;
  do
  {
LABEL_669:
    v202 = *v201 - v25;
    v203 = v339;
    if ( v202 <= v339 )
    {
      v203 = v202;
      v333 = v202;
      if ( a21 || v343 )
      {
        v204 = v202 & ~(v364 - 1);
        v203 = v204;
        v333 = v204;
      }
      else
      {
        v204 = v202;
      }
    }
    else
    {
      v333 = v339;
      v204 = v339;
    }
    if ( !v204 || v473 )
      goto LABEL_737;
    *((_DWORD *)v198 + 6) = 0;
    v205 = 0;
    v434 = 0;
    v206 = 0;
    v207 = 0;
    while ( v205 < v203 && (unsigned int)v206 < 0x10 )
    {
      if ( v338 )
      {
        v23 = v331;
        NextSparseRange = BasepGetNextSparseRange(
                            (unsigned int)&v473,
                            0x100000,
                            *v331,
                            (int)v198 + 8 * (3 * (int)v206 + 4),
                            (__int64)&v198[3 * v206 + 6]);
        v337 = NextSparseRange;
        if ( !NextSparseRange )
        {
          v124 = hFile;
          goto LABEL_683;
        }
        if ( a21 || v343 )
        {
          v198 = lpInBuffer;
          if ( *((_DWORD *)lpInBuffer + 6 * *((unsigned int *)lpInBuffer + 6) + 12) % (unsigned int)v364 )
            break;
        }
        else
        {
          v198 = lpInBuffer;
        }
        if ( !v475 )
        {
          v473 = 1;
          break;
        }
      }
      else
      {
        v211 = 0x100000;
        if ( v203 - v205 < 0x100000 )
          v211 = v203 - v205;
        LODWORD(v198[3 * v207 + 6]) = v211;
        v198[3 * *((unsigned int *)v198 + 6) + 4] = v25 + (unsigned int)(*((_DWORD *)v198 + 6) << 20);
      }
      v212 = 3LL * *((unsigned int *)v198 + 6);
      v205 += LODWORD(v198[3 * *((unsigned int *)v198 + 6) + 6]);
      v434 = v205;
      v198[v212 + 5] = v198[v212 + 4];
      v206 = (unsigned int)(*((_DWORD *)v198 + 6) + 1);
      *((_DWORD *)v198 + 6) = v206;
      v207 = v206;
    }
    v209 = *((_DWORD *)v198 + 6);
    v199 = v349;
    v200 = NextSparseRange;
    v201 = v331;
  }
  while ( !v209 );
  if ( v338 )
  {
    v203 = LODWORD(v198[3 * (unsigned int)(v209 - 1) + 4]) + LODWORD(v198[3 * (unsigned int)(v209 - 1) + 6]) - v25;
    v333 = v203;
  }
  v23 = v331;
  if ( v328 )
  {
    *(_DWORD *)(v328 + 48) = 5;
    *(_QWORD *)(v328 + 80) = (*(_QWORD *)(v328 + 96))++;
    v210 = v330;
    if ( (unsigned int)BasepCopySetContextAndCheckCallback(
                         v328,
                         &FileInformation,
                         *v330,
                         FileHandle,
                         *v23,
                         v25,
                         v203,
                         hFile,
                         1,
                         v390[0]) == -1073741248 )
    {
      v337 = 0;
      BaseSetLastNTError(3221226048LL);
      v124 = hFile;
      v41 = 0;
      goto LABEL_1037;
    }
    v390[0] = 0;
    v412 = 0;
    v198 = lpInBuffer;
  }
  v200 = DeviceIoControl(
           FileHandle,
           v362 != 0 ? 1328152 : 1344540,
           v198,
           24 * *((_DWORD *)v198 + 6) + 32,
           &OutBuffer,
           0xCu,
           &BytesReturned,
           &Overlapped);
  NextSparseRange = v200;
  v337 = v200;
  if ( !v200 && NtCurrentTeb()->LastErrorValue == 997 )
  {
    v200 = GetOverlappedResultEx(
             (HANDLE)((unsigned __int64)FileHandle | 1),
             &Overlapped,
             &BytesReturned,
             0xFFFFFFFF,
             v200);
    NextSparseRange = v200;
    v337 = v200;
  }
  if ( v200 )
  {
    v213 = v25;
    v25 += v203;
    v371 = v25;
    v214 = *v23;
    if ( v25 < *v23 )
    {
      v214 = v25;
    }
    else
    {
      v25 = *v23;
      v371 = *v23;
      v203 = v214 - v213;
      v333 = v214 - v213;
      v363 = v214;
      v215 = NtSetInformationFile(FileHandle, &IoStatusBlock, &v363, 8u, FileEndOfFileInformation);
      if ( v215 < 0 )
      {
        v337 = 0;
        BaseSetLastNTError((unsigned int)v215);
        goto LABEL_328;
      }
    }
    v199 = v349 + 1;
    v349 = v199;
    v413 = v199;
    if ( v347 )
    {
      if ( (v199 & 3) != 0 || !v214 )
      {
        v201 = v331;
        if ( v214 != *v331 )
          goto LABEL_733;
      }
      *(_QWORD *)DistanceToMoveHigh = 0;
      v395[0] = 0;
      v216 = FileHandle;
      if ( hFile )
        v216 = hFile;
      v184 = NtFlushBuffersFile(v216, &IoStatusBlock);
      if ( v184 < 0 )
        goto LABEL_619;
      *(_QWORD *)DistanceToMoveHigh = v25;
      SetFilePointer(v216, 0, 0, 0);
      v217 = (unsigned __int16 *)lpBuffer;
      *((_QWORD *)lpBuffer + 5) = v25;
      v218 = 26;
      v436 = 26;
      v219 = v217;
      v471 = v217;
      for ( n = 0; ; n = (unsigned __int16)v222 + HIWORD(v222) )
      {
        v221 = v218--;
        v436 = v218;
        if ( !v221 )
          break;
        v222 = n + *v219++;
        v471 = v219;
      }
      v223 = lpBuffer;
      *((_DWORD *)lpBuffer + 13) = (unsigned __int16)(n + HIWORD(n));
      NextSparseRange = WriteFile(v216, v223, 0x38u, v395, 0);
      v337 = NextSparseRange;
      if ( !NextSparseRange || v395[0] != 56 )
        goto LABEL_736;
      v184 = NtFlushBuffersFile(v216, &IoStatusBlock);
      if ( v184 < 0 )
        goto LABEL_619;
      SetFilePointer(v216, DistanceToMoveHigh[0], &DistanceToMoveHigh[1], 0);
    }
    v201 = v331;
LABEL_733:
    v200 = NextSparseRange;
    if ( !v328 )
      goto LABEL_668;
    v390[0] = 1;
    v412 = 1;
    *(_QWORD *)(v328 + 8) += v203;
    v327 = BasepCopySetContextAndCheckCallback(v328, &FileInformation, *v330, FileHandle, *v201, v25, v203, hFile, 2, 1);
    v201 = v331;
    v198 = lpInBuffer;
    if ( v327 == -1073741248 )
    {
      v337 = 0;
      v185 = 3221226048LL;
      goto LABEL_620;
    }
    goto LABEL_669;
  }
  if ( NtCurrentTeb()->LastErrorValue == 87 && v196 && (unsigned int)(HIDWORD(OutBuffer) - 0x10000) <= 0xF0000 )
  {
    v339 = HIDWORD(OutBuffer);
    v196 = 0;
    v435 = 0;
    v199 = v349;
    v201 = v331;
LABEL_668:
    v198 = lpInBuffer;
    goto LABEL_669;
  }
  v199 = v349;
LABEL_737:
  v224 = v380;
  if ( (_DWORD)v380 )
  {
    BasepCsvEnableDirectIO(*v330, FileHandle);
    v224 = v380;
  }
  if ( v200 )
  {
    v23 = v331;
    if ( *v331 != v25 )
      goto LABEL_741;
LABEL_579:
    v41 = 1;
    v326 = 1;
    v352 = 1;
    goto LABEL_1035;
  }
  if ( v199 && !v224 )
  {
    v124 = hFile;
    if ( !hFile && NtCurrentTeb()->LastErrorValue != 1112 )
    {
      v225 = v347 == (_DWORD)hFile;
      goto LABEL_747;
    }
LABEL_372:
    v23 = v331;
    goto LABEL_373;
  }
LABEL_741:
  v41 = 0;
LABEL_751:
  v226 = v330;
  if ( v328 && *(_QWORD *)(v328 + 128) )
  {
    v449 = v330;
    v450 = *(_QWORD *)(v328 + 136);
    v451 = FileHandle;
    v415 = 0;
    v227 = TpAllocWait(&v415, &BasepCopyFileCancelEventCallback, &CriticalSection, 0);
    if ( v227 >= 0 )
    {
      v228 = v415;
    }
    else
    {
      RtlSetLastWin32ErrorAndNtStatusFromNtStatus(v227);
      v228 = 0;
    }
    v415 = v228;
    v446 = v228;
    if ( !v228 )
      goto LABEL_1034;
    TpSetWait(v228, *(_QWORD *)(v328 + 128), 0);
  }
  v229 = v356;
  if ( (*v356 & 0x10000000) != 0 )
  {
    if ( (v358 & 0x10) != 0 && (unsigned __int8)BasepIsCopyOverSMB311OrNewer(*v226) )
      BasepRequestCompressedTrafficForFile(*v226);
    if ( (v353 & 0x10) != 0 && (unsigned __int8)BasepIsCopyOverSMB311OrNewer(FileHandle) )
      BasepRequestCompressedTrafficForFile(FileHandle);
  }
  if ( v347 )
  {
    *(_QWORD *)NumberOfBytesTransferred = (((unsigned __int64)MEMORY[0x7FFE0004] << 32)
                                         * (unsigned __int128)(unsigned __int64)(MEMORY[0x7FFE0320] << 8)) >> 64;
    v271 = (int *)v25;
    *(_QWORD *)DistanceToMoveHigh = v25;
    v272 = 0;
    v466 = 0;
    v368 = 0;
    v380 = 0;
    v273 = v365;
    v339 = *v365;
    v368 = v25;
    while ( 1 )
    {
      v274 = (((unsigned __int64)MEMORY[0x7FFE0004] << 32)
            * (unsigned __int128)(unsigned __int64)(MEMORY[0x7FFE0320] << 8)) >> 64;
      v267 = v338;
      v275 = v331;
      if ( v338 )
      {
        NextSparseRange = BasepGetNextSparseRange(
                            (unsigned int)&v473,
                            *v273,
                            *v331,
                            (unsigned int)&v368,
                            (__int64)&v339);
        v337 = NextSparseRange;
        v380 = v368;
        if ( !NextSparseRange )
        {
          v23 = v275;
          goto LABEL_328;
        }
        if ( !v475 )
        {
          v239 = NextSparseRange;
          goto LABEL_931;
        }
        v276 = v339;
      }
      else
      {
        v368 = v25;
        v380 = v25;
        v276 = v339;
        if ( v339 > *v331 - v25 )
        {
          v276 = *(_DWORD *)v331 - v25;
          v339 = v276;
        }
        if ( v25 == *v331 )
        {
          v239 = NextSparseRange;
          goto LABEL_932;
        }
      }
      if ( v342 )
        v339 = ~(v364 - 1) & (v276 + v364 - 1);
      RtlEnterCriticalSection(&CriticalSection);
      v346 = 11703;
      v277 = v328;
      if ( v328 )
      {
        if ( v338 )
        {
          *(_DWORD *)(v328 + 52) = 22;
          *(_QWORD *)(v328 + 160) = v368;
          *(_QWORD *)(v328 + 72) = v339;
          BasepCopyFileCallbackNew(v328);
          v277 = v328;
        }
        *(_DWORD *)(v277 + 48) = 4;
        *(_QWORD *)(v328 + 80) = (*(_QWORD *)(v328 + 96))++;
        if ( v338 )
          v278 = v339 + v368 - v25;
        else
          v278 = v339;
        v333 = v278;
        *(_QWORD *)FileInformationClass = *v275;
        v279 = v330;
        if ( (unsigned int)BasepCopySetContextAndCheckCallback(
                             v328,
                             &FileInformation,
                             *v330,
                             FileHandle,
                             *(_QWORD *)FileInformationClass,
                             v25,
                             v278,
                             hFile,
                             1,
                             1) == -1073741248 )
        {
          if ( *(_DWORD *)(v328 + 104) )
            *(_DWORD *)(v328 + 104) = 0;
          v337 = 0;
LABEL_974:
          BaseSetLastNTError(3221226048LL);
          v346 = 0;
          RtlLeaveCriticalSection(&CriticalSection);
          goto LABEL_67;
        }
      }
      else
      {
        v279 = v330;
      }
      v346 = 0;
      RtlLeaveCriticalSection(&CriticalSection);
      while ( 1 )
      {
        v280 = NtCopyFileChunk(*v279, FileHandle, 0, &IoStatusBlock, v339, &v368, &v380, 0, 0, *v407);
        v281 = TestBlockCloningFallbackEnabled;
        if ( TestBlockCloningFallbackEnabled == -1 )
        {
          v281 = 0;
          TestBlockCloningFallbackEnabled = 0;
        }
        if ( TestBlockCloningFallbackMode && v342 )
        {
          if ( v281 == -1 )
            TestBlockCloningFallbackEnabled = 0;
          if ( TestBlockCloningFallbackMode == 1 )
          {
            if ( !v368 )
              v280 = -1073741637;
          }
          else if ( (unsigned int)(TestBlockCloningFallbackMode - 2) <= 1 && v368 > 0 )
          {
            v280 = -1073741637;
          }
        }
        if ( v280 >= 0 )
          break;
        if ( v342 )
        {
          *v407 &= ~1u;
          v342 = 0;
          v400 = 0;
          goto LABEL_1023;
        }
        BaseSetLastNTError((unsigned int)v280);
        if ( RtlNtStatusToDosError(v280) != 112 || !v383 )
          goto LABEL_67;
        v296 = v339;
        v297 = *v331;
        v298 = v328;
        v299 = 0;
        v420 = 0;
        if ( v328 && !*(_QWORD *)(v328 + 144) )
        {
          if ( !*(_QWORD *)(v328 + 152) )
          {
            v420 = 1;
            goto LABEL_1023;
          }
          *(_DWORD *)(v328 + 48) = 4;
          *(_DWORD *)(v298 + 52) = 6;
          *(_DWORD *)(v298 + 92) = 112;
          *(_DWORD *)(v298 + 24) = 112;
          *(_QWORD *)(v298 + 56) = v297;
          *(_QWORD *)(v298 + 64) = v25;
          *(_QWORD *)(v298 + 72) = v296;
          v299 = BasepCopyFileCallbackNew(v298);
          v420 = v299;
        }
        if ( !v299 )
          goto LABEL_67;
LABEL_1023:
        v279 = v330;
      }
      if ( v342 )
      {
        v283 = *v331;
        v282 = v339;
        if ( v368 + v339 > *v331 )
        {
          v282 = v283 - v368;
          v339 = v283 - v368;
        }
      }
      else
      {
        v282 = IoStatusBlock.Information;
        v339 = IoStatusBlock.Information;
      }
      if ( v338 )
        v284 = v282 + v368 - v25;
      else
        v284 = v282;
      v333 = v284;
      v285 = v25 + v284;
      v25 = v285;
      v371 = v285;
      v272 += v282;
      v466 = v272;
      v413 = ++v349;
      if ( (v349 & 3) == 0 && v285 || v285 == *v331 )
      {
        *(_QWORD *)v390 = 0;
        v384 = 0;
        v286 = FileHandle;
        if ( hFile )
          v286 = hFile;
        v184 = NtFlushBuffersFile(v286, &IoStatusBlock);
        if ( v184 >= 0 )
        {
          *(_QWORD *)v390 = v25;
          SetFilePointer(v286, 0, 0, 0);
          v287 = (unsigned __int16 *)lpBuffer;
          *((_QWORD *)lpBuffer + 5) = v25;
          v288 = 26;
          v438 = 26;
          v289 = v287;
          v465 = v287;
          for ( ii = 0; ; ii = (unsigned __int16)v292 + HIWORD(v292) )
          {
            v291 = v288--;
            v438 = v288;
            if ( !v291 )
              break;
            v292 = ii + *v289++;
            v465 = v289;
          }
          v293 = lpBuffer;
          *((_DWORD *)lpBuffer + 13) = (unsigned __int16)(ii + HIWORD(ii));
          NextSparseRange = WriteFile(v286, v293, 0x38u, &v384, 0);
          v337 = NextSparseRange;
          if ( !NextSparseRange || v384 != 56 )
            goto LABEL_67;
          v184 = NtFlushBuffersFile(v286, &IoStatusBlock);
          if ( v184 >= 0 )
          {
            SetFilePointer(v286, v390[0], &v390[1], 0);
            v271 = *(int **)DistanceToMoveHigh;
            goto LABEL_1010;
          }
        }
LABEL_619:
        v185 = (unsigned int)v184;
LABEL_620:
        BaseSetLastNTError(v185);
        goto LABEL_67;
      }
LABEL_1010:
      RtlEnterCriticalSection(&CriticalSection);
      v346 = 11941;
      v294 = v328;
      if ( v328 )
      {
        if ( v338 )
        {
          *(_DWORD *)(v328 + 52) = 8;
          *(_QWORD *)(v328 + 160) = v368;
          *(_QWORD *)(v328 + 72) = v339;
          BasepCopyFileCallbackNew(v328);
          v294 = v328;
        }
        *(_QWORD *)(v294 + 8) += v284;
        EaListLengtha = v284;
        v295 = v331;
        if ( (unsigned int)BasepCopySetContextAndCheckCallback(
                             v328,
                             &FileInformation,
                             *v330,
                             FileHandle,
                             *v331,
                             v25,
                             EaListLengtha,
                             hFile,
                             2,
                             1) == -1073741248 )
        {
          if ( *(_DWORD *)(v328 + 104) )
            *(_DWORD *)(v328 + 104) = 0;
          goto LABEL_974;
        }
      }
      else
      {
        v295 = v331;
      }
      v346 = 0;
      RtlLeaveCriticalSection(&CriticalSection);
      v273 = v365;
      if ( a20 && v25 < *v295 && v25 > (__int64)v271 )
      {
        BasepCopyThrottlingDelay(v272, v339, NumberOfBytesTransferred[0], v274, a20);
        v273 = v365;
      }
    }
  }
  v357 = 0;
  DesiredAccess = 0;
  v230 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, KernelBaseGlobalData | 8, (unsigned __int64)v340 << 6);
  v386 = v230;
  if ( !v230 )
  {
    v124 = hFile;
    if ( !hFile && (*v229 & 0x4000) == 0 )
      BaseMarkFileForDelete(FileHandle);
    BaseSetLastNTError(3221225495LL);
    v23 = v331;
    goto LABEL_1036;
  }
  for ( jj = 0; ; ++jj )
  {
    v357 = jj;
    if ( jj >= v340 )
      break;
    v232 = CreateEventExA(0, 0, 1u, 0x1F0003u);
    *((_QWORD *)v230 + 8 * (unsigned __int64)jj + 4) = v232;
    if ( !v232 )
    {
      v124 = hFile;
      if ( !hFile && (*v229 & 0x4000) == 0 )
        BaseMarkFileForDelete(FileHandle);
      v180 = 3221225495LL;
LABEL_611:
      BaseSetLastNTError(v180);
      goto LABEL_372;
    }
  }
  if ( !v342 || v377 )
    v233 = *v365;
  else
    v233 = 0x40000000;
  v339 = v233;
  v23 = v331;
  v337 = BasepInitializeNtCopyChunkContexts(
           (_DWORD)v230,
           v340,
           v25,
           *v331,
           (unsigned __int64)&v473 & -(__int64)(v338 != 0),
           v342,
           v233,
           v364,
           (__int64)&DesiredAccess);
  if ( !v337 )
  {
    v124 = hFile;
    if ( !hFile )
    {
      v208 = (*v229 & 0x4000) == 0;
      goto LABEL_686;
    }
    goto LABEL_373;
  }
  *(_QWORD *)NumberOfBytesTransferred = (((unsigned __int64)MEMORY[0x7FFE0004] << 32)
                                       * (unsigned __int128)(unsigned __int64)(MEMORY[0x7FFE0320] << 8)) >> 64;
  v445 = *(_QWORD *)NumberOfBytesTransferred;
  *(_QWORD *)DistanceToMoveHigh = v25;
  v234 = v25;
  v391 = v25;
  v444 = 0;
  v333 = 0;
  v388 = 0;
  NextSparseRange = 1;
  v337 = 1;
  v235 = 0;
  v357 = 0;
  while ( 2 )
  {
    if ( v235 < v340 )
    {
      v236 = (char *)v386 + 64 * (unsigned __int64)v235;
      if ( *((_DWORD *)v236 + 14) )
      {
        v357 = ++v235;
        continue;
      }
      v445 = (((unsigned __int64)MEMORY[0x7FFE0004] << 32)
            * (unsigned __int128)(unsigned __int64)(MEMORY[0x7FFE0320] << 8)) >> 64;
      RtlEnterCriticalSection(&CriticalSection);
      v346 = 10976;
      if ( v328 )
      {
        v237 = *((_DWORD *)v236 + 6);
        v238 = v338;
        if ( v338 )
          v237 = *(_DWORD *)v236 + v237 - v234;
        v333 = v237;
        if ( v338 )
        {
          v234 += v237;
          v391 = v234;
        }
        *(_DWORD *)(v328 + 48) = 4;
        *((_QWORD *)v236 + 2) = (*(_QWORD *)(v328 + 96))++;
        *(_QWORD *)(v328 + 80) = *((_QWORD *)v236 + 2);
        if ( v238 )
        {
          *(_DWORD *)(v328 + 52) = 7;
          *(_QWORD *)(v328 + 160) = *(_QWORD *)v236;
          *(_QWORD *)(v328 + 72) = *((unsigned int *)v236 + 6);
          BasepCopyFileCallbackNew(v328);
        }
        if ( (unsigned int)BasepCopySetContextAndCheckCallback(
                             v328,
                             &FileInformation,
                             *v330,
                             FileHandle,
                             *v331,
                             v25,
                             v237,
                             hFile,
                             1,
                             1) == -1073741248 )
        {
          v239 = 0;
          NextSparseRange = 0;
          v337 = 0;
          BaseSetLastNTError(3221226048LL);
          *((_DWORD *)v236 + 14) = 1;
          ++DesiredAccess;
          v346 = 0;
          RtlLeaveCriticalSection(&CriticalSection);
          goto LABEL_818;
        }
      }
      v346 = 0;
      RtlLeaveCriticalSection(&CriticalSection);
      *((_DWORD *)v236 + 10) = 259;
      v240 = *v407;
      *((_DWORD *)v236 + 15) = *v407;
      v241 = NtCopyFileChunk(
               *v330,
               FileHandle,
               *((_QWORD *)v236 + 4),
               v236 + 40,
               *((_DWORD *)v236 + 6),
               v236,
               v236 + 8,
               0,
               0,
               v240);
      if ( TestBlockCloningFallbackEnabled == -1 )
        TestBlockCloningFallbackEnabled = 0;
      if ( TestBlockCloningFallbackMode == 1 && (v236[60] & 1) != 0 )
        v241 = -1073741637;
      if ( v241 == -1073741807 )
      {
        *((_DWORD *)v236 + 10) = -1073741807;
        goto LABEL_806;
      }
      if ( v241 >= 0 )
      {
LABEL_806:
        ++v235;
      }
      else
      {
        if ( (v236[60] & 1) == 0 )
        {
          v239 = 0;
          NextSparseRange = 0;
          v337 = 0;
          BaseSetLastNTError((unsigned int)v241);
          *((_DWORD *)v236 + 14) = 1;
          ++DesiredAccess;
          goto LABEL_818;
        }
        *v407 &= ~1u;
        v342 = 0;
        v400 = 0;
        if ( a21 || (v242 = 1, v343) )
          v242 = v366;
        v382 = v242;
        v364 = v242;
        v339 = *v365;
        v234 = v25;
        v391 = v25;
        NextSparseRange = BasepInitializeNtCopyChunkContexts(
                            (_DWORD)v386,
                            v340,
                            v25,
                            *v331,
                            (unsigned __int64)&v473 & -(__int64)(v338 != 0),
                            0,
                            v339,
                            v242,
                            (__int64)&DesiredAccess);
        v337 = NextSparseRange;
        if ( !NextSparseRange )
        {
          v124 = hFile;
          v225 = hFile == 0;
LABEL_747:
          if ( v225 && (*v356 & 0x4000) == 0 )
            BaseMarkFileForDelete(FileHandle);
          goto LABEL_372;
        }
        v235 = 0;
      }
      v357 = v235;
      continue;
    }
    break;
  }
  v239 = NextSparseRange;
LABEL_818:
  v243 = 0;
  v357 = 0;
  while ( 2 )
  {
    if ( v239 )
    {
      if ( DesiredAccess == v340 )
        goto LABEL_836;
      v244 = (char *)v386 + 64 * (unsigned __int64)v243;
      if ( *((_DWORD *)v244 + 14) )
      {
        v245 = (v243 + 1) % v340;
LABEL_823:
        v243 = v245;
        v357 = v245;
        continue;
      }
      v246 = 0;
      LODWORD(v380) = 0;
      v247 = *((_DWORD *)v244 + 10);
      if ( v247 == 259 )
      {
        v247 = NtWaitForSingleObject(*((HANDLE *)v244 + 4), 0, 0);
        if ( v247 >= 0 )
          v247 = *((_DWORD *)v244 + 10);
        v246 = v380;
      }
      if ( TestBlockCloningFallbackEnabled == -1 )
        TestBlockCloningFallbackEnabled = 0;
      if ( TestBlockCloningFallbackMode == 3 && (v244[60] & 1) != 0 && *((__int64 *)v244 + 2) > 1 )
        v247 = -1073741637;
      if ( v247 == -1073741807 )
        goto LABEL_836;
      if ( v247 >= 0 )
      {
        v253 = v342;
      }
      else
      {
        if ( (v244[60] & 1) == 0 )
          goto LABEL_847;
        *v407 &= ~1u;
        v253 = 0;
        v342 = 0;
        v400 = 0;
        v246 = 1;
        LODWORD(v380) = 1;
        if ( a21 || (v254 = 1, v343) )
          v254 = v366;
        v364 = v254;
        v382 = v254;
      }
      if ( v246 )
        goto LABEL_898;
      if ( !v253 )
        *((_DWORD *)v244 + 6) = *((_DWORD *)v244 + 12);
      v255 = *((unsigned int *)v244 + 6);
      v256 = *((_DWORD *)v244 + 6);
      if ( v338 )
        v256 = *(_DWORD *)v244 + v256 - v25;
      v333 = v256;
      v25 += v256;
      v371 = v25;
      v444 += v255;
      if ( v25 <= *v331 )
      {
        v257 = v256;
      }
      else
      {
        v257 = v256 + *(_DWORD *)v331 - v25;
        v256 = v257;
        v333 = v257;
        v25 = *v331;
        v371 = v25;
        v363 = v25;
        v247 = NtSetInformationFile(FileHandle, &IoStatusBlock, &v363, 8u, FileEndOfFileInformation);
        if ( v247 < 0 )
        {
LABEL_847:
          v239 = 0;
          NextSparseRange = 0;
          v337 = 0;
          BaseSetLastNTError((unsigned int)v247);
          *((_DWORD *)v244 + 14) = 1;
          ++DesiredAccess;
          if ( v328 )
            *(_QWORD *)(v328 + 80) = *((_QWORD *)v244 + 2);
          goto LABEL_836;
        }
      }
      RtlEnterCriticalSection(&CriticalSection);
      v346 = 11295;
      v258 = v328;
      if ( v328 )
      {
        if ( v338 )
        {
          *(_DWORD *)(v328 + 52) = 8;
          *(_QWORD *)(v328 + 160) = *(_QWORD *)v244;
          *(_QWORD *)(v328 + 72) = *((unsigned int *)v244 + 6);
          *(_QWORD *)(v328 + 80) = *((_QWORD *)v244 + 2);
          BasepCopyFileCallbackNew(v328);
          v258 = v328;
        }
        *(_QWORD *)(v258 + 8) += v257;
        *(_QWORD *)(v328 + 80) = *((_QWORD *)v244 + 2);
        EaListLength = v256;
        v259 = v331;
        if ( (unsigned int)BasepCopySetContextAndCheckCallback(
                             v328,
                             &FileInformation,
                             *v330,
                             FileHandle,
                             *v331,
                             v25,
                             EaListLength,
                             hFile,
                             2,
                             1) == -1073741248 )
        {
LABEL_863:
          v239 = 0;
          NextSparseRange = 0;
          v337 = 0;
          BaseSetLastNTError(3221226048LL);
          *((_DWORD *)v244 + 14) = 1;
          ++DesiredAccess;
          v346 = 0;
          RtlLeaveCriticalSection(&CriticalSection);
          goto LABEL_836;
        }
      }
      else
      {
        v259 = v331;
      }
      v346 = 0;
      RtlLeaveCriticalSection(&CriticalSection);
      if ( a20 && v340 == 1 && v25 < *v259 && v25 > *(__int64 *)DistanceToMoveHigh )
        BasepCopyThrottlingDelay(v444, *((_DWORD *)v244 + 6), NumberOfBytesTransferred[0], v445, a20);
      v260 = v388;
      if ( !v338 || v388 )
      {
        *(_QWORD *)v244 += v340 * (unsigned __int64)v339;
        v261 = *(_QWORD *)v244;
        *((_QWORD *)v244 + 1) = *(_QWORD *)v244;
        *((_DWORD *)v244 + 6) = v339;
        if ( v342 && v261 + v339 > *v259 )
          *((_DWORD *)v244 + 6) = ~(v364 - 1) & (*(_DWORD *)v259 - v261 + v364 - 1);
        if ( v261 >= *v259 )
          v260 = 1;
        v388 = v260;
      }
      else
      {
        if ( !v473 )
        {
          v239 = BasepGetNextSparseRange((unsigned int)&v473, v339, *v259, (_DWORD)v244, (__int64)(v244 + 24));
          NextSparseRange = v239;
          v337 = v239;
          *((_QWORD *)v244 + 1) = *(_QWORD *)v244;
          if ( a21 || v343 || v342 )
            *((_DWORD *)v244 + 6) = ~(v364 - 1) & (*((_DWORD *)v244 + 6) + v364 - 1);
          if ( !v239 )
            goto LABEL_878;
          if ( !v475 )
          {
            v260 = 1;
            v388 = 1;
          }
LABEL_889:
          if ( v260 )
          {
            *((_DWORD *)v244 + 14) = 1;
            ++DesiredAccess;
            v243 = (v243 + 1) % v340;
            v357 = v243;
            continue;
          }
          v445 = (((unsigned __int64)MEMORY[0x7FFE0004] << 32)
                * (unsigned __int128)(unsigned __int64)(MEMORY[0x7FFE0320] << 8)) >> 64;
          RtlEnterCriticalSection(&CriticalSection);
          v346 = 11432;
          if ( v328 )
          {
            *(_DWORD *)(v328 + 48) = 4;
            v262 = *((_DWORD *)v244 + 6);
            v263 = v338;
            if ( v338 )
              v262 = *(_DWORD *)v244 + v262 - v391;
            v333 = v262;
            v391 += v262;
            *((_QWORD *)v244 + 2) = (*(_QWORD *)(v328 + 96))++;
            *(_QWORD *)(v328 + 80) = *((_QWORD *)v244 + 2);
            if ( v263 )
            {
              *(_DWORD *)(v328 + 52) = 7;
              *(_QWORD *)(v328 + 160) = *(_QWORD *)v244;
              *(_QWORD *)(v328 + 72) = *((unsigned int *)v244 + 6);
              BasepCopyFileCallbackNew(v328);
            }
            if ( (unsigned int)BasepCopySetContextAndCheckCallback(
                                 v328,
                                 &FileInformation,
                                 *v330,
                                 FileHandle,
                                 *v331,
                                 v25,
                                 v262,
                                 hFile,
                                 1,
                                 1) == -1073741248 )
              goto LABEL_863;
          }
          v346 = 0;
          RtlLeaveCriticalSection(&CriticalSection);
          v239 = NextSparseRange;
LABEL_898:
          *((_DWORD *)v244 + 10) = 259;
          v264 = *v407;
          *((_DWORD *)v244 + 15) = *v407;
          v265 = NtCopyFileChunk(
                   *v330,
                   FileHandle,
                   *((_QWORD *)v244 + 4),
                   v244 + 40,
                   *((_DWORD *)v244 + 6),
                   v244,
                   v244 + 8,
                   0,
                   0,
                   v264);
          if ( v265 == -1073741807 )
          {
            *((_DWORD *)v244 + 10) = -1073741807;
          }
          else
          {
            if ( v265 < 0 )
            {
              v239 = 0;
              NextSparseRange = 0;
              v337 = 0;
              BaseSetLastNTError((unsigned int)v265);
LABEL_878:
              *((_DWORD *)v244 + 14) = 1;
              ++DesiredAccess;
LABEL_836:
              if ( v239 )
                goto LABEL_926;
              break;
            }
            if ( TestBlockCloningFallbackEnabled == -1 )
              TestBlockCloningFallbackEnabled = 0;
            if ( TestBlockCloningFallbackMode == 2 && (v244[60] & 1) != 0 && *((__int64 *)v244 + 2) > 1 )
              *((_DWORD *)v244 + 10) = -1073741637;
          }
          if ( !(_DWORD)v380 )
          {
            v245 = (v243 + 1) % v340;
            goto LABEL_823;
          }
          continue;
        }
        v260 = 1;
        v388 = 1;
      }
      v239 = NextSparseRange;
      goto LABEL_889;
    }
    break;
  }
  v248 = 0;
  v468 = 0;
  v249 = 1;
  v437 = 1;
  for ( kk = 0; ; ++kk )
  {
    v357 = kk;
    if ( kk >= v340 )
      break;
    v251 = (unsigned __int64)kk << 6;
    v252 = (char *)v386;
    if ( !*(_DWORD *)((char *)v386 + v251 + 56) )
    {
      v266 = *(_DWORD *)((char *)v386 + v251 + 40);
      if ( v266 == 259 )
      {
        v266 = NtWaitForSingleObject(*(HANDLE *)((char *)v386 + v251 + 32), 0, 0);
        v252 = (char *)v386;
        if ( v266 >= 0 )
          v266 = *(_DWORD *)((char *)v386 + v251 + 40);
      }
      if ( !v342 )
        *(_DWORD *)&v252[v251 + 24] = *(_DWORD *)&v252[v251 + 48];
      if ( v266 >= 0 && v328 && *(_DWORD *)(v328 + 104) && v249 )
      {
        v248 += *(unsigned int *)&v252[v251 + 24];
        v468 = v248;
      }
      else
      {
        v249 = 0;
        v437 = 0;
      }
    }
  }
  if ( v249 )
  {
    v25 += v248;
    v371 = v25;
    if ( v328 )
      *(_QWORD *)(v328 + 8) += v248;
  }
  v239 = NextSparseRange;
LABEL_926:
  if ( NtCurrentTeb()->LastErrorValue == 1112 )
  {
LABEL_736:
    v124 = hFile;
    goto LABEL_372;
  }
  if ( !v328 || !*(_DWORD *)(v328 + 104) )
  {
    if ( v239 )
      BaseSetLastNTError(0);
LABEL_931:
    v267 = v338;
LABEL_932:
    v23 = v331;
    if ( !v239 || !v267 || v25 >= *v331 )
      goto LABEL_962;
    if ( a21 || v343 )
    {
      v363 = *v331;
      v268 = NtSetInformationFile(FileHandle, &IoStatusBlock, &v363, 8u, FileEndOfFileInformation);
      if ( v268 < 0 )
      {
        v239 = 0;
        v337 = 0;
        BaseSetLastNTError((unsigned int)v268);
      }
    }
    v269 = *(_DWORD *)v23 - v25;
    v333 = v269;
    if ( v239 && v328 )
    {
      RtlEnterCriticalSection(&CriticalSection);
      v346 = 12046;
      *(_DWORD *)(v328 + 48) = 4;
      *(_QWORD *)(v328 + 80) = (*(_QWORD *)(v328 + 96))++;
      v124 = hFile;
      v270 = BasepCopySetContextAndCheckCallback(
               v328,
               &FileInformation,
               *v330,
               FileHandle,
               *v23,
               v25,
               v269,
               hFile,
               1,
               1);
      if ( v270 < 0
        || (v371 = *v23,
            v25 = v371,
            *(_QWORD *)(v328 + 8) += v269,
            v270 = BasepCopySetContextAndCheckCallback(
                     v328,
                     &FileInformation,
                     *v330,
                     FileHandle,
                     *v23,
                     v25,
                     v269,
                     v124,
                     2,
                     1),
            v270 < 0) )
      {
        v239 = 0;
        v337 = 0;
        BaseSetLastNTError((unsigned int)v270);
      }
      v346 = 0;
      RtlLeaveCriticalSection(&CriticalSection);
    }
    else
    {
LABEL_962:
      v124 = hFile;
    }
    if ( v387 )
    {
      InBuffer[0] = 0;
      if ( !DeviceIoControl(FileHandle, 0x900C4u, InBuffer, 1u, 0, 0, 0, &Overlapped)
        && NtCurrentTeb()->LastErrorValue == 997 )
      {
        v387 = 0;
        GetOverlappedResultEx((HANDLE)((unsigned __int64)FileHandle | 1), &Overlapped, &v387, 0xFFFFFFFF, 0);
      }
    }
    if ( v239 )
    {
      v41 = 1;
      v326 = 1;
      v352 = 1;
      goto LABEL_1036;
    }
LABEL_683:
    if ( !v124 && !v347 )
    {
      v208 = (*v356 & 0x4000) == 0;
LABEL_686:
      if ( v208 )
        BaseMarkFileForDelete(FileHandle);
    }
LABEL_373:
    v41 = 0;
    goto LABEL_1036;
  }
LABEL_67:
  v41 = 0;
LABEL_1034:
  v23 = v331;
LABEL_1035:
  v124 = hFile;
LABEL_1036:
  v210 = v330;
LABEL_1037:
  if ( v415 )
  {
    TpWaitForWait(v415, 1);
    TpReleaseWait(v415);
  }
  if ( v328 )
  {
    if ( v402 )
    {
      *(_QWORD *)(v328 + 56) = *v23;
      *(_QWORD *)(v328 + 64) = v25;
      *(_DWORD *)(v328 + 20) = 1;
      *(_DWORD *)(v328 + 24) = 1235;
      *(_QWORD *)(v328 + 32) = *v210;
      *(_QWORD *)(v328 + 40) = FileHandle;
      if ( !(unsigned int)BasepCopyFileCallback(4) || (unsigned int)BasepIsCopyCancelled(v328) )
      {
        if ( v41 )
        {
          if ( (unsigned int)BasepIsCopyCancelled(v328) && !v124 )
            BaseMarkFileForDelete(FileHandle);
          BaseSetLastNTError(3221226048LL);
          v326 = 0;
        }
      }
    }
  }
  if ( v328 && *(_DWORD *)(v328 + 104) )
  {
    v326 = 0;
    if ( *(_QWORD *)(v328 + 8) < *(_QWORD *)v328 || (unsigned int)BasepIsCopyCancelled(v328) )
    {
      v302 = (unsigned __int16 *)lpBuffer;
      *((_QWORD *)lpBuffer + 5) = v25;
      v303 = v302;
      v304 = 0;
      do
      {
        v305 = v304 + *v303++;
        v304 = (unsigned __int16)v305 + HIWORD(v305);
        --v42;
      }
      while ( v42 );
      *((_DWORD *)v302 + 13) = (unsigned __int16)(v304 + HIWORD(v304));
      v363 = v25;
      NtSetInformationFile(FileHandle, &IoStatusBlock, &v363, 8u, FileEndOfFileInformation);
      v306 = FileHandle;
      if ( v124 )
        v306 = v124;
      if ( (unsigned int)BasepWriteRestartState(v306, v302) )
      {
        v301 = 3221226585LL;
        goto LABEL_1061;
      }
    }
    else
    {
      v363 = v25;
      v300 = NtSetInformationFile(FileHandle, &IoStatusBlock, &v363, 8u, FileEndOfFileInformation);
      if ( v300 >= 0 )
      {
        v326 = 1;
        *(_DWORD *)(v328 + 104) = 0;
      }
      v301 = (unsigned int)v300;
LABEL_1061:
      BaseSetLastNTError(v301);
    }
  }
  *v452 = FileHandle;
  if ( v440 )
    *v440 = v343;
  if ( Overlapped.hEvent )
    CloseHandle(Overlapped.hEvent);
  v307 = (char *)v386;
  if ( v386 )
  {
    v308 = 0;
    for ( mm = v340; v308 < mm; ++v308 )
    {
      v310 = (unsigned __int64)v308 << 6;
      if ( *(_QWORD *)&v307[v310 + 32] )
      {
        CloseHandle(*(HANDLE *)&v307[v310 + 32]);
        mm = v340;
      }
    }
  }
  if ( v393 )
  {
    PrivCopyOffloadStatus(3, 0, v393);
    v311 = 0;
    v393 = 0;
  }
  else
  {
    v311 = 0;
  }
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, lpInBuffer);
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v307);
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v428);
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
  if ( v405 )
  {
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v405);
    v405 = 0;
  }
  v312 = Str;
  if ( Str == (wchar_t *)v533 )
  {
    v313 = NtCurrentTeb()->StaticUnicodeBuffer;
    v314 = v533;
    v315 = 4;
    do
    {
      *(_OWORD *)v313 = *v314;
      *((_OWORD *)v313 + 1) = v314[1];
      *((_OWORD *)v313 + 2) = v314[2];
      *((_OWORD *)v313 + 3) = v314[3];
      *((_OWORD *)v313 + 4) = v314[4];
      *((_OWORD *)v313 + 5) = v314[5];
      *((_OWORD *)v313 + 6) = v314[6];
      *((_OWORD *)v313 + 7) = v314[7];
      v313 += 64;
      v314 += 8;
      --v315;
    }
    while ( v315 );
    *(_OWORD *)(v313 - 3) = *(_OWORD *)((char *)v314 - 6);
  }
  RtlDeleteCriticalSection(&CriticalSection);
  if ( v493 )
  {
    BytesReturned = 0;
    v370 = 0;
    v483 = 0;
    v484 = 0;
    v485 = 0;
    LastWin32Error = RtlGetLastWin32Error();
    LastNtStatus = RtlGetLastNtStatus();
    if ( v312 )
      v311 = wcsrchr(v312, 0x2Eu);
    if ( !v403 )
    {
      memset_0(v531, 0, 0x218u);
      if ( v330 )
      {
        if ( *v330 != (HANDLE)-1LL )
          NtQueryVolumeInformationFile(*v330, &IoStatusBlock, v531, 0x218u, FileFsAttributeInformation);
      }
    }
    if ( !v401 )
    {
      memset_0(FsInformation, 0, 0x218u);
      if ( FileHandle != (HANDLE)-1LL )
      {
        NtQueryVolumeInformationFile(FileHandle, &IoStatusBlock, FsInformation, 0x218u, FileFsAttributeInformation);
        if ( NtQueryInformationFile(FileHandle, &IoStatusBlock, &v483, 0x28u, FileBasicInformation) >= 0 )
          k = v485;
      }
    }
    if ( (unsigned __int8)IsEfsClientQueryProtectorsPresent() )
    {
      if ( v312 && (v344 & 0x4000) != 0 && (v358 & 0x10) == 0 )
        EfsClientGetEncryptedFileVersion(v312, &BytesReturned, 0);
      if ( SourceString && (k & 0x4000) != 0 && (v353 & 0x10) == 0 )
        EfsClientGetEncryptedFileVersion(SourceString, &v370, 0);
    }
    if ( (unsigned int)dword_18039CC08 > 5
      && (qword_18039CC18 & 0x400000000000LL) != 0
      && (qword_18039CC20 & 0x400000000000LL) == qword_18039CC20 )
    {
      v318 = LastWin32Error;
      if ( v326 )
        v318 = 0;
      NumberOfBytesTransferred[0] = v318;
      v504 = NumberOfBytesTransferred;
      v505 = 4;
      if ( v23 )
        v319 = (int *)*v23;
      else
        v319 = 0;
      v440 = v319;
      v506 = &v440;
      v507 = 8;
      LOBYTE(v359[0]) = (v344 & 0x4000) != 0;
      v508 = v359;
      v509 = 1;
      InBuffer[0] = (k & 0x4000) != 0;
      v510 = InBuffer;
      v511 = 1;
      v403 = BytesReturned;
      v512 = &v403;
      v513 = 4;
      v395[0] = v370;
      v514 = v395;
      v515 = 4;
      tlgCreate1Sz_wchar_t(v516, v532);
      tlgCreate1Sz_wchar_t(v517, String1);
      v377 = v358;
      v518 = &v377;
      v519 = 4;
      LODWORD(v417) = v353;
      v520 = &v417;
      v521 = 4;
      v320 = L"NA";
      if ( v311 )
        v320 = v311;
      tlgCreate1Sz_wchar_t(v522, v320);
      tlgWriteTransfer_EventWriteTransfer(&dword_18039CC08, &unk_180359248, &v492, &ActivityId, 13, &OutputBuffer);
    }
    EventActivityIdControl(2u, &ActivityId);
    BaseSetLastNTError(LastNtStatus);
    RtlSetLastWin32Error(LastWin32Error);
  }
  return v326;
}

```

## disassembly

```asm
0x1800d061c  push    rbx
0x1800d061e  push    rsi
0x1800d061f  push    rdi
0x1800d0620  push    r12
0x1800d0622  push    r13
0x1800d0624  push    r14
0x1800d0626  push    r15
0x1800d0628  mov     eax, 20D0h
0x1800d062d  call    __chkstk_1
0x1800d0632  sub     rsp, rax
0x1800d0635  mov     rax, cs:__security_cookie
0x1800d063c  xor     rax, rsp
0x1800d063f  mov     [rsp+2108h+var_48], rax
0x1800d0647  mov     [rsp+2108h+SourceString], r9
0x1800d064f  mov     [rsp+2108h+var_1EF8], r8d
0x1800d0657  mov     r14, rdx
0x1800d065a  mov     [rsp+2108h+var_2060], rdx
0x1800d0662  mov     rax, rcx
0x1800d0665  mov     [rsp+2108h+Str], rcx
0x1800d066d  mov     rcx, [rsp+2108h+arg_60]
0x1800d0675  mov     [rsp+2108h+lpBuffer], rcx
0x1800d067d  mov     r13, [rsp+2108h+arg_30]
0x1800d0685  mov     [rsp+2108h+var_2058], r13
0x1800d068d  mov     [rsp+2108h+var_1D18], rax
0x1800d0695  mov     [rsp+2108h+var_1CE0], rdx
0x1800d069d  mov     rax, [rsp+2108h+arg_20]
0x1800d06a5  mov     [rsp+2108h+hFile], rax
0x1800d06ad  mov     [rsp+2108h+var_1D20], rax
0x1800d06b5  mov     [rsp+2108h+var_1CB0], r13
0x1800d06bd  mov     rdi, [rsp+2108h+arg_38]
0x1800d06c5  mov     [rsp+2108h+var_1FE0], rdi
0x1800d06cd  mov     rax, [rsp+2108h+arg_40]
0x1800d06d5  mov     [rsp+2108h+var_1D28], rax
0x1800d06dd  mov     [rsp+2108h+var_1CD0], rax
0x1800d06e5  mov     rax, [rsp+2108h+arg_48]
0x1800d06ed  mov     [rsp+2108h+var_1DA0], rax
0x1800d06f5  mov     [rsp+2108h+var_1CC8], rax
0x1800d06fd  mov     r12, [rsp+2108h+arg_50]
0x1800d0705  mov     [rsp+2108h+var_1FB0], r12
0x1800d070d  mov     r15, [rsp+2108h+arg_58]
0x1800d0715  mov     [rsp+2108h+var_1CD8], rcx
0x1800d071d  mov     rax, [rsp+2108h+arg_80]
0x1800d0725  mov     qword ptr [rsp+2108h+DistanceToMoveHigh], rax
0x1800d072d  mov     rax, [rsp+2108h+arg_A8]
0x1800d0735  mov     [rsp+2108h+var_1EB8], rax
0x1800d073d  xorps   xmm0, xmm0
0x1800d0740  movups  xmmword ptr [rsp+2108h+IoStatusBlock], xmm0
0x1800d0748  xorps   xmm1, xmm1
0x1800d074b  movups  xmmword ptr [rsp+2108h+Overlapped.Internal], xmm1
0x1800d0753  movups  xmmword ptr [rsp+2108h+Overlapped.10h], xmm1
0x1800d075b  movups  [rsp+2108h+var_AF8], xmm0
0x1800d0763  movups  [rsp+2108h+var_AE8], xmm0
0x1800d076b  xor     esi, esi
0x1800d076d  mov     [rsp+2108h+var_1F08], rsi
0x1800d0775  mov     dword ptr [rsp+2108h+var_1F98], esi
0x1800d077c  mov     rbx, [r15]
0x1800d077f  mov     [rsp+2108h+var_2070], rbx
0x1800d0787  xor     edx, edx; Val
0x1800d0789  lea     r8d, [rsi+40h]; Size
0x1800d078d  lea     rcx, [rsp+2108h+CriticalSection]; void *
0x1800d0795  call    memset_0
0x1800d079a  mov     [rsp+2108h+FileHandle], 0FFFFFFFFFFFFFFFFh
0x1800d07a6  xorps   xmm0, xmm0
0x1800d07a9  xor     eax, eax
0x1800d07ab  movups  [rsp+2108h+FileInformation], xmm0
0x1800d07b3  movups  [rsp+2108h+var_C18], xmm0
0x1800d07bb  mov     qword ptr [rsp+2108h+var_C08], rax
0x1800d07c3  mov     [rsp+2108h+var_1FC0], rsi
0x1800d07cb  mov     [rsp+2108h+var_200C], esi
0x1800d07d2  mov     [rsp+2108h+var_1FD4], esi
0x1800d07d9  mov     [rsp+2108h+var_1FEC], esi
0x1800d07e0  mov     esi, [rdi]
0x1800d07e2  mov     [rsp+2108h+var_1F48], esi
0x1800d07e9  mov     eax, esi
0x1800d07eb  and     eax, 11000h
0x1800d07f0  mov     [rsp+2108h+var_2020], eax
0x1800d07f7  mov     edi, 218h
0x1800d07fc  mov     r8d, edi; Size
0x1800d07ff  xor     edx, edx; Val
0x1800d0801  lea     rcx, [rsp+2108h+var_478]; void *
0x1800d0809  call    memset_0
0x1800d080e  mov     r8d, edi; Size
0x1800d0811  xor     edx, edx; Val
0x1800d0813  lea     rcx, [rsp+2108h+FsInformation]; void *
0x1800d081b  call    memset_0
0x1800d0820  xorps   xmm0, xmm0
0x1800d0823  movups  [rsp+2108h+var_1E78], xmm0
0x1800d082b  movups  [rsp+2108h+var_1E68], xmm0
0x1800d0833  xor     eax, eax
0x1800d0835  movups  xmmword ptr [rsp+2108h+ObjectAttributes.Length], xmm0
0x1800d083d  movups  xmmword ptr [rsp+2108h+ObjectAttributes.ObjectName], xmm0
0x1800d0845  movups  xmmword ptr [rsp+2108h+ObjectAttributes+1Ch], xmm0
0x1800d084d  mov     [rsp+2108h+var_1EC8], rax
0x1800d0855  mov     edi, eax
0x1800d0857  mov     [rsp+2108h+var_1F90], rax
0x1800d085f  mov     [rsp+2108h+var_202C], eax
0x1800d0866  mov     [rsp+2108h+var_2030], eax
0x1800d086d  xor     edx, edx; Val
0x1800d086f  mov     r8d, 1020h; Size
0x1800d0875  lea     rcx, [rsp+2108h+var_1C48]; void *
0x1800d087d  call    memset_0
0x1800d0882  mov     rax, [r14]
0x1800d0885  mov     [rsp+2108h+var_1C40], rax
0x1800d088d  xorps   xmm0, xmm0
0x1800d0890  xor     eax, eax
0x1800d0892  movups  xmmword ptr [rsp+2108h+ActivityId.Data1], xmm0
0x1800d089a  movups  [rsp+2108h+var_B60], xmm0
0x1800d08a2  mov     [rsp+2108h+var_B50], eax
0x1800d08a9  xor     edx, edx; Val
0x1800d08ab  mov     r8d, 20Ah; Size
0x1800d08b1  lea     rcx, [rsp+2108h+var_258]; void *
0x1800d08b9  call    memset_0
0x1800d08be  mov     edx, 40000h
0x1800d08c3  test    edx, esi
0x1800d08c5  lea     esi, [rdi+1]
0x1800d08c8  jz      short loc_1800D08CE
0x1800d08ca  xor     ecx, ecx
0x1800d08cc  jmp     short loc_1800D08D9
0x1800d08ce  mov     ecx, esi
0x1800d08d0  xor     eax, eax
0x1800d08d2  cmp     [r13+0], rdx
0x1800d08d6  cmovl   ecx, eax
0x1800d08d9  mov     [rsp+2108h+var_2008], ecx
0x1800d08e0  mov     dword ptr [r12], 100000h
0x1800d08e8  mov     rax, gs:30h
0x1800d08f1  add     rax, 1268h
0x1800d08f7  cmp     [rsp+2108h+Str], rax
0x1800d08ff  jnz     loc_1800D098F
0x1800d0905  mov     rax, gs:30h
0x1800d090e  add     rax, 1268h
0x1800d0914  lea     rcx, [rsp+2108h+var_258]
0x1800d091c  mov     edx, 4
0x1800d0921  lea     r8d, [rdx+7Ch]
0x1800d0925  movups  xmm0, xmmword ptr [rax]
0x1800d0928  movups  xmmword ptr [rcx], xmm0
0x1800d092b  movups  xmm1, xmmword ptr [rax+10h]
0x1800d092f  movups  xmmword ptr [rcx+10h], xmm1
0x1800d0933  movups  xmm0, xmmword ptr [rax+20h]
0x1800d0937  movups  xmmword ptr [rcx+20h], xmm0
0x1800d093b  movups  xmm1, xmmword ptr [rax+30h]
0x1800d093f  movups  xmmword ptr [rcx+30h], xmm1
0x1800d0943  movups  xmm0, xmmword ptr [rax+40h]
0x1800d0947  movups  xmmword ptr [rcx+40h], xmm0
0x1800d094b  movups  xmm1, xmmword ptr [rax+50h]
0x1800d094f  movups  xmmword ptr [rcx+50h], xmm1
0x1800d0953  movups  xmm0, xmmword ptr [rax+60h]
0x1800d0957  movups  xmmword ptr [rcx+60h], xmm0
0x1800d095b  movups  xmm1, xmmword ptr [rax+70h]
0x1800d095f  movups  xmmword ptr [rcx+70h], xmm1
0x1800d0963  add     rcx, r8
0x1800d0966  add     rax, r8
0x1800d0969  sub     rdx, 1
0x1800d096d  jnz     short loc_1800D0925
0x1800d096f  movups  xmm0, xmmword ptr [rax-6]
0x1800d0973  movups  xmmword ptr [rcx-6], xmm0
0x1800d0977  lea     rax, [rsp+2108h+var_258]
0x1800d097f  mov     [rsp+2108h+Str], rax
0x1800d0987  mov     [rsp+2108h+var_1D18], rax
0x1800d098f  test    rbx, rbx
0x1800d0992  jz      loc_1800D0A1B
0x1800d0998  mov     dword ptr [rbx+30h], 2
0x1800d099f  mov     rcx, [r13+0]
0x1800d09a3  mov     rax, [rsp+2108h+var_2070]
0x1800d09ab  mov     [rax+38h], rcx
0x1800d09af  mov     rax, [rsp+2108h+var_2070]
0x1800d09b7  mov     [rax+40h], rdi
0x1800d09bb  mov     rax, [rsp+2108h+var_2070]
0x1800d09c3  add     [rax+10h], esi
0x1800d09c6  mov     rax, [rsp+2108h+var_2070]
0x1800d09ce  mov     [rax+14h], esi
0x1800d09d1  mov     rax, [rsp+2108h+var_2070]
0x1800d09d9  mov     dword ptr [rax+18h], 4D3h
0x1800d09e0  mov     rcx, [r14]
0x1800d09e3  mov     rax, [rsp+2108h+var_2070]
0x1800d09eb  mov     [rax+20h], rcx
0x1800d09ef  mov     rcx, [rsp+2108h+FileHandle]
0x1800d09f7  mov     rax, [rsp+2108h+var_2070]
0x1800d09ff  mov     [rax+28h], rcx
0x1800d0a03  mov     rax, [rsp+2108h+var_2070]
0x1800d0a0b  mov     [rax+50h], rdi
0x1800d0a0f  mov     rax, [rsp+2108h+var_2070]
0x1800d0a17  mov     [rax+60h], rdi
0x1800d0a1b  lea     rdx, [rsp+2108h+var_1FD4]
0x1800d0a23  mov     rcx, [r14]
0x1800d0a26  call    BasepQueryDeviceCharacteristics
0x1800d0a2b  mov     [rsp+2108h+FileInformationClass], 4; FileInformationClass
0x1800d0a33  mov     r9d, 28h ; '('; Length
0x1800d0a39  lea     r8, [rsp+2108h+FileInformation]; FileInformation
0x1800d0a41  lea     rdx, [rsp+2108h+IoStatusBlock]; IoStatusBlock
0x1800d0a49  mov     rcx, [r14]; FileHandle
0x1800d0a4c  call    cs:__imp_NtQueryInformationFile
0x1800d0a52  mov     ebx, eax
0x1800d0a54  xor     edx, edx
0x1800d0a56  mov     eax, edx
0x1800d0a58  test    ebx, ebx
0x1800d0a5a  cmovns  eax, [rsp+2108h+var_C08]
0x1800d0a62  mov     [rsp+2108h+var_201C], eax
0x1800d0a69  mov     r14d, eax
0x1800d0a6c  and     r14d, 10h
0x1800d0a70  jnz     short loc_1800D0A94
0x1800d0a72  bt      eax, 0Eh
0x1800d0a76  mov     rax, [rsp+2108h+hFile]
0x1800d0a7e  jnb     short loc_1800D0A9C
0x1800d0a80  test    rax, rax
0x1800d0a83  jnz     short loc_1800D0AD1
0x1800d0a85  lea     rcx, [rsp+2108h+ActivityId]; ActivityId
0x1800d0a8d  call    BasepBaseCopyStreamStartActivity
0x1800d0a92  xor     edx, edx
0x1800d0a94  mov     rax, [rsp+2108h+hFile]
0x1800d0a9c  test    rax, rax
0x1800d0a9f  jnz     short loc_1800D0AD1
0x1800d0aa1  test    ebx, ebx
0x1800d0aa3  jns     short loc_1800D0AD8
0x1800d0aa5  mov     ecx, ebx
0x1800d0aa7  call    BaseSetLastNTError
0x1800d0aac  xor     eax, eax
0x1800d0aae  mov     rcx, [rsp+2108h+var_48]
0x1800d0ab6  xor     rcx, rsp; StackCookie
0x1800d0ab9  call    __security_check_cookie
0x1800d0abe  add     rsp, 20D0h
0x1800d0ac5  pop     r15
0x1800d0ac7  pop     r14
0x1800d0ac9  pop     r13
0x1800d0acb  pop     r12
0x1800d0acd  pop     rdi
0x1800d0ace  pop     rsi
0x1800d0acf  pop     rbx
0x1800d0ad0  retn
0x1800d0ad1  mov     [rsp+2108h+var_C08], edx
0x1800d0ad8  mov     [rsp+2108h+var_2040], edx
0x1800d0adf  mov     [rsp+2108h+var_2078], edx
0x1800d0ae6  mov     [rsp+2108h+var_1FF0], edx
0x1800d0aed  mov     [rsp+2108h+var_1F70], esi
0x1800d0af4  mov     ebx, edx
0x1800d0af6  mov     [rsp+2108h+var_1FC4], edx
0x1800d0afd  mov     dword ptr [rsp+2108h+var_1F58], edx
0x1800d0b04  mov     [rsp+2108h+lpInBuffer], rdx
0x1800d0b0c  mov     [rsp+2108h+var_1F38], rdx
0x1800d0b14  mov     [rsp+2108h+var_2024], edx
0x1800d0b1b  mov     [rsp+2108h+var_2034], edx
0x1800d0b22  mov     [rsp+2108h+var_1F30], edx
0x1800d0b29  mov     [rsp+2108h+var_2014], edi
0x1800d0b30  mov     [rsp+2108h+var_1E90], rdx
0x1800d0b38  mov     [rsp+2108h+var_1D78], rdx
0x1800d0b40  mov     [rsp+2108h+var_1ED8], edx
0x1800d0b47  mov     dword ptr [rsp+2108h+var_1F98+4], edx
0x1800d0b4e  mov     [rsp+2108h+var_1E08], rdx
0x1800d0b56  mov     [rsp+2108h+var_1ED4], edx
0x1800d0b5d  mov     [rsp+2108h+var_1EDC], edx
0x1800d0b64  mov     [rsp+2108h+P], rdx
0x1800d0b6c  mov     dword ptr [rsp+2108h+var_1FB8], edx
0x1800d0b73  mov     [rsp+2108h+var_1FA8], edx
0x1800d0b7a  mov     [rsp+2108h+var_1E98], edx
0x1800d0b81  mov     [rsp+2108h+BytesReturned], edx
0x1800d0b88  mov     ecx, [rsp+2108h+var_1F48]
0x1800d0b8f  mov     eax, ecx
0x1800d0b91  and     eax, 4000000h
0x1800d0b96  mov     [rsp+2108h+var_1F44], eax
0x1800d0b9d  and     ecx, 8000000h
0x1800d0ba3  mov     [rsp+2108h+var_1F48], ecx
0x1800d0baa  mov     [rsp+2108h+var_1F20], esi
0x1800d0bb1  mov     rcx, [rsp+2108h+var_1FE0]
0x1800d0bb9  mov     eax, [rcx]
0x1800d0bbb  test    al, 2
0x1800d0bbd  jz      short loc_1800D0BDD
0x1800d0bbf  mov     [rsp+2108h+var_2010], esi
0x1800d0bc6  test    r14d, r14d
0x1800d0bc9  jz      short loc_1800D0BE4
0x1800d0bcb  and     eax, 0FFFFFFFDh
0x1800d0bce  mov     [rcx], eax
0x1800d0bd0  mov     rcx, [rsp+2108h+lpBuffer]
0x1800d0bd8  mov     word ptr [rcx], 4AC3h
0x1800d0bdd  mov     [rsp+2108h+var_2010], edx
0x1800d0be4  mov     qword ptr [rsp+2108h+var_1E78+8], rdx
0x1800d0bec  mov     dword ptr [rsp+2108h+var_1E68], edx
0x1800d0bf3  mov     qword ptr [rsp+2108h+var_1E78], 2
0x1800d0bff  lea     rcx, [rsp+2108h+CriticalSection]; CriticalSection
0x1800d0c07  call    cs:__imp_RtlInitializeCriticalSection
0x1800d0c0d  cmp     [rsp+2108h+hFile], 0
0x1800d0c16  jnz     loc_1800D2D1E
0x1800d0c1c  mov     dword ptr [rsp+2108h+var_1E10], 0
0x1800d0c27  mov     [rsp+2108h+var_1EF0], 0
0x1800d0c32  xor     eax, eax
0x1800d0c34  mov     [rsp+2108h+var_1E4C], eax
0x1800d0c3b  mov     [rsp+2108h+var_1E00], rax
0x1800d0c43  mov     [rsp+2108h+var_1E44], eax
0x1800d0c4a  mov     r8d, [rsp+2108h+var_2010]
0x1800d0c52  mov     rdx, [rsp+2108h+var_1FE0]
0x1800d0c5a  test    r8d, r8d
0x1800d0c5d  jnz     short loc_1800D0C6B
0x1800d0c5f  test    dword ptr [rdx], 4000h
0x1800d0c65  jz      loc_1800D0D2E
0x1800d0c6b  lea     rax, [rsp+2108h+var_1F98]
0x1800d0c73  mov     qword ptr [rsp+2108h+EaLength], rax; __int64
0x1800d0c78  mov     eax, [rsp+2108h+arg_68]
0x1800d0c7f  mov     dword ptr [rsp+2108h+EaBuffer], eax; int
0x1800d0c83  mov     eax, [rsp+2108h+var_C08]
0x1800d0c8a  mov     dword ptr [rsp+2108h+RestartScan], eax; int
0x1800d0c8e  mov     [rsp+2108h+EaIndex], r15; __int64
0x1800d0c93  mov     qword ptr [rsp+2108h+EaListLength], r13; __int64
  ... truncated ...
```
