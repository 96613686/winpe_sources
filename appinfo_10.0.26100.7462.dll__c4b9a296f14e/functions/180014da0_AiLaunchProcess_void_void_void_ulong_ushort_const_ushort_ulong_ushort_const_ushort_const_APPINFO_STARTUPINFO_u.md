# AiLaunchProcess(void *,void *,void *,ulong,ushort const *,ushort *,ulong,ushort const *,ushort const *,_APPINFO_STARTUPINFO *,ulong,ushort *,ulong,void *,unsigned __int64,ushort const *,_PROCESS_INFORMATION *)

- ea: `0x180014da0`
- end: `0x18001689d`
- name: `?AiLaunchProcess@@YAKPEAX00KPEBGPEAGK11PEAU_APPINFO_STARTUPINFO@@K2K0_K1PEAU_PROCESS_INFORMATION@@@Z`
- size: `6909`
- prototype: `__int64 __fastcall(void *, void *, void *, int, const unsigned __int16 *, unsigned __int16 *, unsigned int, const unsigned __int16 *, unsigned __int16 *, struct _APPINFO_STARTUPINFO *, unsigned int, _WORD *lpValue, __int16, void *, unsigned __int64, const unsigned __int16 *Src, struct _PROCESS_INFORMATION *)`
- caller_count: `4`
- callee_count: `31`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180024a98`
- `0x18002a2a8`
- `0x18003ac30`
- `0x18003e0d0`

## callees

- `0x180001008`
- `0x180007c78`
- `0x18000a4f0`
- `0x18000edf0`
- `0x180010cc0`
- `0x1800126c4`
- `0x180012a14`
- `0x180014da0`
- `0x180018218`
- `0x18001913c`
- `0x18001980c`
- `0x18001ba60`
- `0x18001d038`
- `0x18001fd94`
- `0x180022b74`
- `0x180022bb0`
- `0x1800234a0`
- `0x1800241b4`
- `0x180025880`
- `0x18002cae8`
- `0x180036fb0`
- `0x18003a2fc`
- `0x18003c74c`
- `0x18003c7b4`
- `0x18003c8d4`
- `0x18003c988`
- `0x180043f6c`
- `0x1800449e2`
- `0x1800449fa`
- `0x180044a20`
- `0x180046010`

## import_xrefs

- `msvcrt!wcsstr` at `0x180015490`
- `msvcrt!wcsstr` at `0x180015490`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800161b4`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001648a`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800161b4`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001648a`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180015d76`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180015d76`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18001650a`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800165b7`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18001650a`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800165b7`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180015ee1`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180016043`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180015ee1`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180016043`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180015e2b`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180015f9b`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180015e2b`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180015f9b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001510b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800153a3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015422`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015814`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016240`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800162dc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800164fc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800165a9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016731`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001510b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800153a3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015422`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015814`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016240`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800162dc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800164fc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800165a9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016731`
- `api-ms-win-core-processthreads-l1-1-0!DeleteProcThreadAttributeList` at `0x18001675d`
- `api-ms-win-core-processthreads-l1-1-0!DeleteProcThreadAttributeList` at `0x18001675d`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x1800166d7`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x1800166d7`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x1800167bc`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x1800167bc`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x1800164ec`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x180016599`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x1800164ec`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x180016599`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800152a8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800152bb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800152a8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800152bb`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x180015804`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x180015855`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x1800158a0`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x1800158ee`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x180015953`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x180015aa0`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x180015c92`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x180015804`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x180015855`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x1800158a0`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x1800158ee`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x180015953`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x180015aa0`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x180015c92`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x1800150fb`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x1800150fb`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x1800152e6`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x1800152e6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800167a1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800167cc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800167e1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180016864`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800167a1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800167cc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800167e1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180016864`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180014ff0`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180015ba1`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180015bfe`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180014ff0`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180015ba1`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180015bfe`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180015713`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180015799`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800159b1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180015ada`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180015b09`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001680a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001684f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180015713`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180015799`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800159b1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180015ada`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180015b09`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001680a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001684f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001526a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800156fc`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001628f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001526a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800156fc`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001628f`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x18001626e`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x1800162cc`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x18001626e`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x1800162cc`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180015ddb`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180015ddb`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x180015dbf`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x180015dbf`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180016226`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180016226`
- `api-ms-win-core-appcompat-l1-1-1!BaseFreeAppCompatDataForProcess` at `0x1800167f6`
- `api-ms-win-core-appcompat-l1-1-1!BaseFreeAppCompatDataForProcess` at `0x1800167f6`
- `api-ms-win-core-appcompat-l1-1-1!BaseReadAppCompatDataForProcess` at `0x180015305`
- `api-ms-win-core-appcompat-l1-1-1!BaseReadAppCompatDataForProcess` at `0x180015305`
- `api-ms-win-appmodel-runtime-l1-1-1!GetApplicationUserModelIdFromToken` at `0x180015f6a`
- `api-ms-win-appmodel-runtime-l1-1-1!GetApplicationUserModelIdFromToken` at `0x180015f6a`
- `api-ms-win-core-psm-key-l1-1-0!PsmGetKeyFromToken` at `0x180015f3b`
- `api-ms-win-core-psm-key-l1-1-0!PsmGetKeyFromToken` at `0x180015f3b`
- `ntdll!NtClose` at `0x180016826`
- `ntdll!NtClose` at `0x180016826`
- `ntdll!NtDuplicateObject` at `0x180016641`
- `ntdll!NtDuplicateObject` at `0x180016699`
- `ntdll!NtDuplicateObject` at `0x180016641`
- `ntdll!NtDuplicateObject` at `0x180016699`
- `ntdll!RtlAllocateHeap` at `0x1800151ed`
- `ntdll!RtlAllocateHeap` at `0x1800151ed`
- `ntdll!RtlExpandEnvironmentStrings` at `0x1800156d8`
- `ntdll!RtlExpandEnvironmentStrings` at `0x18001574c`
- `ntdll!RtlExpandEnvironmentStrings` at `0x1800156d8`
- `ntdll!RtlExpandEnvironmentStrings` at `0x18001574c`
- `ntdll!RtlDestroyEnvironment` at `0x180015760`
- `ntdll!RtlDestroyEnvironment` at `0x180015760`
- `ntdll!RtlQueryEnvironmentVariable` at `0x180015598`
- `ntdll!RtlQueryEnvironmentVariable` at `0x180015598`
- `ntdll!RtlCreateEnvironmentEx` at `0x180015776`
- `ntdll!RtlCreateEnvironmentEx` at `0x180015776`
- `ntdll!RtlSetEnvironmentVar` at `0x180015524`
- `ntdll!RtlSetEnvironmentVar` at `0x1800155c8`
- `ntdll!RtlSetEnvironmentVar` at `0x180015524`
- `ntdll!RtlSetEnvironmentVar` at `0x1800155c8`
- `ntdll!NtDuplicateToken` at `0x180014f79`
- `ntdll!NtDuplicateToken` at `0x180014f79`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180014f8b`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180015536`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18001566d`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180015788`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180016653`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180014f8b`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180015536`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18001566d`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180015788`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180016653`
- `USERENV!DestroyEnvironmentBlock` at `0x180015238`
- `USERENV!DestroyEnvironmentBlock` at `0x180016772`
- `USERENV!DestroyEnvironmentBlock` at `0x180015238`
- `USERENV!DestroyEnvironmentBlock` at `0x180016772`
- `USERENV!CreateEnvironmentBlock` at `0x180015157`
- `USERENV!CreateEnvironmentBlock` at `0x180015157`
- `USERENV!UnloadUserProfile` at `0x18001678c`
- `USERENV!UnloadUserProfile` at `0x18001678c`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!MonitorFromPoint` at `0x180015d4d`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!MonitorFromPoint` at `0x180015d4d`
- `ext-ms-win-appcompat-apphelp-l1-1-1!__imp_SdbGetKnownSafeLayers` at `0x180015379`
- `ext-ms-win-appcompat-apphelp-l1-1-1!__imp_SdbGetKnownSafeLayers` at `0x180015379`

## string_xrefs

- `0x180015998`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x180015abe`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x180014fc0`: `EnableSecureUIAPaths`
- `0x180015515`: `__COMPAT_LAYER`

## pseudocode

```c
__int64 __fastcall AiLaunchProcess(
        void *a1,
        void *a2,
        void *a3,
        int a4,
        const unsigned __int16 *a5,
        unsigned __int16 *a6,
        unsigned int a7,
        const unsigned __int16 *a8,
        unsigned __int16 *a9,
        struct _APPINFO_STARTUPINFO *a10,
        unsigned int a11,
        _WORD *lpValue,
        __int16 a13,
        void *a14,
        unsigned __int64 a15,
        const unsigned __int16 *Src,
        struct _PROCESS_INFORMATION *a17)
{
  WCHAR *v17; // r12
  struct _APPINFO_STARTUPINFO *v18; // rsi
  int v19; // r15d
  UINT LastError; // ebx
  DWORD v21; // edi
  int v22; // eax
  unsigned __int16 *v23; // r14
  char IsEnabled; // al
  unsigned int v25; // edx
  int v26; // eax
  int v27; // ecx
  DWORD v28; // eax
  DWORD v29; // ecx
  DWORD v30; // edi
  const void *v31; // r15
  unsigned int i; // r8d
  int j; // edx
  __int64 v34; // rbx
  unsigned int v35; // esi
  __int64 v36; // rax
  unsigned __int64 v37; // rax
  char *Heap; // rax
  char *v39; // rdi
  size_t v40; // rbx
  LPCWSTR v41; // rsi
  HANDLE CurrentProcess; // rax
  HANDLE v43; // rdi
  void *v44; // rbx
  HANDLE v45; // rax
  int v46; // eax
  int v47; // r8d
  _QWORD *v48; // rcx
  char v49; // al
  int v50; // r8d
  DWORD v51; // eax
  const unsigned __int16 *v52; // r8
  __int64 v53; // rax
  NTSTATUS v54; // eax
  wchar_t **v55; // rsi
  unsigned int v56; // r14d
  wchar_t *v57; // rdx
  __int64 v58; // rbx
  int v59; // edi
  int v60; // r8d
  int v61; // eax
  NTSTATUS v62; // ebx
  NTSTATUS v63; // ecx
  __int64 v64; // rsi
  HLOCAL v65; // r14
  char *v66; // rdx
  __int64 v67; // rax
  __int64 v68; // rax
  bool v69; // zf
  NTSTATUS v70; // eax
  __int64 v71; // rdi
  HANDLE *p_hSourceHandle; // r9
  __int64 v73; // rax
  int v74; // eax
  int LastErrorMsg; // edi
  unsigned __int64 v76; // r9
  __int64 v77; // rdx
  signed __int64 v78; // r8
  _WORD *v79; // rcx
  __int64 v80; // rdx
  __int16 v81; // ax
  _WORD *v82; // rax
  __int64 v83; // rcx
  struct _PROC_THREAD_ATTRIBUTE_LIST *v84; // rax
  LPCWSTR v85; // rsi
  DWORD FileAttributesW; // eax
  _DWORD *v87; // rcx
  __int64 v89; // r10
  __int64 v90; // rax
  __int64 v91; // rax
  LPCWSTR v92; // r12
  const WCHAR *v93; // r14
  const WCHAR *v94; // rdi
  HANDLE FileW; // rax
  __int64 v96; // rsi
  DWORD FinalPathNameByHandleW; // eax
  DWORD v98; // esi
  WCHAR *v99; // rax
  const WCHAR *v100; // r13
  DWORD v101; // r8d
  DWORD v102; // eax
  _DWORD *v103; // rcx
  __int64 v104; // rcx
  __int64 v105; // rax
  __int64 v106; // rax
  int v107; // eax
  char v108; // r15
  const WCHAR *v109; // rcx
  const WCHAR *v110; // rdi
  LPCWSTR v111; // rsi
  PHANDLE v112; // r12
  char v113; // r14
  int v114; // esi
  ACCESS_MASK v115; // edi
  ULONG v116; // eax
  int v117; // eax
  ULONG v118; // eax
  ULONG v119; // eax
  int TokenType; // [rsp+20h] [rbp-E0h]
  const char *TokenTypea; // [rsp+20h] [rbp-E0h]
  const WCHAR *lpCurrentDirectory; // [rsp+40h] [rbp-C0h]
  __int64 hFile; // [rsp+60h] [rbp-A0h]
  WCHAR *v125; // [rsp+68h] [rbp-98h]
  unsigned __int16 *v126; // [rsp+70h] [rbp-90h]
  HANDLE hToken; // [rsp+78h] [rbp-88h] BYREF
  int v128; // [rsp+80h] [rbp-80h]
  DWORD v129; // [rsp+84h] [rbp-7Ch] BYREF
  LPVOID Environment; // [rsp+88h] [rbp-78h] BYREF
  ULONG Value; // [rsp+90h] [rbp-70h] BYREF
  unsigned int v132; // [rsp+94h] [rbp-6Ch]
  WINBOOL v133; // [rsp+98h] [rbp-68h] BYREF
  struct _APPINFO_STARTUPINFO *v134; // [rsp+A0h] [rbp-60h]
  LPCWSTR SourceString; // [rsp+A8h] [rbp-58h]
  HANDLE hSourceHandle; // [rsp+B0h] [rbp-50h] BYREF
  HLOCAL hMem; // [rsp+B8h] [rbp-48h] BYREF
  int pvData; // [rsp+C0h] [rbp-40h] BYREF
  int v139; // [rsp+C4h] [rbp-3Ch] BYREF
  DWORD v140; // [rsp+C8h] [rbp-38h] BYREF
  int v141; // [rsp+CCh] [rbp-34h] BYREF
  WINBOOL fPending; // [rsp+D0h] [rbp-30h] BYREF
  LPVOID v143; // [rsp+D8h] [rbp-28h] BYREF
  LPCWSTR lpApplicationName; // [rsp+E0h] [rbp-20h] BYREF
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+E8h] [rbp-18h] BYREF
  HANDLE hProfile; // [rsp+100h] [rbp+0h] BYREF
  int v147; // [rsp+108h] [rbp+8h] BYREF
  UINT32 applicationUserModelIdLength; // [rsp+10Ch] [rbp+Ch] BYREF
  __int64 v149; // [rsp+110h] [rbp+10h] BYREF
  LPVOID Context; // [rsp+118h] [rbp+18h] BYREF
  LPCWSTR lpFileName; // [rsp+120h] [rbp+20h]
  DWORD pcbData; // [rsp+128h] [rbp+28h] BYREF
  HANDLE TargetHandle; // [rsp+130h] [rbp+30h] BYREF
  __int64 v154; // [rsp+138h] [rbp+38h] BYREF
  HANDLE ExistingTokenHandle; // [rsp+140h] [rbp+40h]
  DWORD v156; // [rsp+148h] [rbp+48h] BYREF
  void *v157; // [rsp+150h] [rbp+50h] BYREF
  void *v158; // [rsp+158h] [rbp+58h]
  PHANDLE p_hProcess; // [rsp+160h] [rbp+60h]
  __int64 v160; // [rsp+168h] [rbp+68h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+170h] [rbp+70h] BYREF
  LPPROC_THREAD_ATTRIBUTE_LIST lpAttributeList; // [rsp+1D8h] [rbp+D8h]
  ULONG_PTR Size; // [rsp+1E0h] [rbp+E0h] BYREF
  LPWSTR FilePart; // [rsp+1E8h] [rbp+E8h] BYREF
  unsigned __int64 v165; // [rsp+1F0h] [rbp+F0h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+1F8h] [rbp+F8h] BYREF
  EVENT_DESCRIPTOR v167; // [rsp+208h] [rbp+108h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+218h] [rbp+118h] BYREF
  __int128 v169; // [rsp+248h] [rbp+148h] BYREF
  int v170; // [rsp+260h] [rbp+160h] BYREF
  _BYTE v171[284]; // [rsp+264h] [rbp+164h] BYREF
  int v172; // [rsp+380h] [rbp+280h] BYREF
  _BYTE v173[524]; // [rsp+384h] [rbp+284h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+590h] [rbp+490h] BYREF
  void *v175; // [rsp+5A0h] [rbp+4A0h]
  int v176; // [rsp+5A8h] [rbp+4A8h]
  int v177; // [rsp+5ACh] [rbp+4ACh]
  _WORD *v178; // [rsp+5B0h] [rbp+4B0h]
  int v179; // [rsp+5B8h] [rbp+4B8h]
  int v180; // [rsp+5BCh] [rbp+4BCh]
  WCHAR *v181; // [rsp+5C0h] [rbp+4C0h]
  int v182; // [rsp+5C8h] [rbp+4C8h]
  int v183; // [rsp+5CCh] [rbp+4CCh]
  unsigned __int64 *v184; // [rsp+5D0h] [rbp+4D0h]
  __int64 v185; // [rsp+5D8h] [rbp+4D8h]
  struct _EVENT_DATA_DESCRIPTOR v186; // [rsp+5E0h] [rbp+4E0h] BYREF
  void *v187; // [rsp+5F0h] [rbp+4F0h]
  int v188; // [rsp+5F8h] [rbp+4F8h]
  int v189; // [rsp+5FCh] [rbp+4FCh]
  const WCHAR *v190; // [rsp+600h] [rbp+500h]
  int v191; // [rsp+608h] [rbp+508h]
  int v192; // [rsp+60Ch] [rbp+50Ch]
  const WCHAR *v193; // [rsp+610h] [rbp+510h]
  int v194; // [rsp+618h] [rbp+518h]
  int v195; // [rsp+61Ch] [rbp+51Ch]
  LPCWSTR *p_lpApplicationName; // [rsp+620h] [rbp+520h]
  __int64 v197; // [rsp+628h] [rbp+528h]
  int v198; // [rsp+630h] [rbp+530h] BYREF
  char v199[332]; // [rsp+634h] [rbp+534h] BYREF
  WCHAR applicationUserModelId[136]; // [rsp+780h] [rbp+680h] BYREF
  _WORD v201[232]; // [rsp+890h] [rbp+790h] BYREF
  _BYTE v202[528]; // [rsp+A60h] [rbp+960h] BYREF
  WCHAR Buffer[264]; // [rsp+C70h] [rbp+B70h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+EC8h] [rbp+DC8h]

  v17 = 0;
  v18 = a10;
  v19 = a4;
  LastError = 0;
  lpApplicationName = a5;
  SourceString = a6;
  lpFileName = a8;
  v143 = a9;
  v157 = a14;
  p_hProcess = &a17->hProcess;
  v158 = a3;
  ExistingTokenHandle = a2;
  hSourceHandle = a1;
  lpAttributeList = 0;
  v128 = a4;
  v134 = a10;
  Value = 0;
  v126 = 0;
  TargetHandle = 0;
  hToken = 0;
  hProfile = 0;
  Environment = 0;
  memset(&StartupInfo, 0, sizeof(StartupInfo));
  v198 = 0;
  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  memset_0(v199, 0, sizeof(v199));
  Size = 336;
  v154 = 0;
  v139 = 4;
  v21 = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  v169 = 0;
  memset_0(&v172, 0, 0x20Cu);
  memset_0(&v170, 0, 0x114u);
  hFile = -1;
  v125 = 0;
  if ( (v19 & 0x80u) != 0 )
  {
    hToken = ExistingTokenHandle;
LABEL_5:
    if ( (v19 & 4) != 0 )
    {
      pvData = 0;
      pcbData = 4;
      if ( !RegGetValueW(
              HKEY_LOCAL_MACHINE,
              L"Software\\Microsoft\\Windows\\CurrentVersion\\Policies\\System",
              L"EnableSecureUIAPaths",
              0x10u,
              0,
              &pvData,
              &pcbData)
        && !pvData
        || (v19 & 0x2000) != 0 )
      {
        v19 |= 0x400u;
        v128 = v19;
      }
      if ( (v19 & 0x400) != 0 )
      {
        IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShadowAdmin>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_ShadowAdmin>::GetImpl'::`2'::impl);
        v25 = a7 & 0xFFFFFFFC;
        if ( !IsEnabled )
          v25 = a7;
        v132 = v25;
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_2045735225>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_2045735225>::GetImpl'::`2'::impl) )
        {
          LastError = LUASetUIAToken2(&hToken);
          v26 = LUAIsShadowAdminEnabled();
          v27 = v19 | 1;
          if ( !v26 )
            v27 = v19;
          v19 = v27;
          v128 = v27;
        }
        else
        {
          LastError = LUASetUIAToken(hToken);
        }
        if ( LastError )
        {
          v23 = 0;
          goto LABEL_289;
        }
LABEL_22:
        if ( hSourceHandle )
        {
          LOBYTE(v21) = lpValue != 0;
          v21 += 2;
          if ( (a13 & 6) != 0 )
            ++v21;
        }
        v28 = v21 + 1;
        if ( (v19 & 0x1800000) == 0 )
          v28 = v21;
        v29 = v28 + 1;
        if ( (a13 & 0x408) == 0 )
          v29 = v28;
        v133 = a13 & 0x2000;
        v30 = v29 + 1;
        if ( (a13 & 0x2000) == 0 )
          v30 = v29;
        v129 = v30;
        if ( v30 && !InitializeProcThreadAttributeList((LPPROC_THREAD_ATTRIBUTE_LIST)&v198, v30, 0, &Size) )
          goto LABEL_33;
        if ( !hSourceHandle )
          goto LABEL_164;
        if ( (v19 & 1) != 0 )
        {
          LastError = AipLoadUserProfile(hToken, &hProfile);
          if ( LastError )
            goto LABEL_34;
        }
        if ( !CreateEnvironmentBlock(&Environment, hToken, 0) )
        {
LABEL_33:
          LastError = GetLastError();
LABEL_34:
          v17 = 0;
          v23 = 0;
          goto LABEL_289;
        }
        if ( Src )
        {
          v31 = Environment;
          for ( i = 0; *((_WORD *)Environment + i) || *((_WORD *)Environment + i + 1); ++i )
            ;
          for ( j = 0; Src[j] || Src[j + 1]; ++j )
            ;
          v34 = i + 1;
          v35 = j + 2;
          v36 = (unsigned int)(v34 + j + 2);
          if ( (unsigned int)v36 < (unsigned int)v34 || (v37 = 2 * v36, v37 > 0xFFFFFFFF) )
          {
            LastError = 534;
            v17 = 0;
            v23 = 0;
            goto LABEL_289;
          }
          Heap = (char *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, (unsigned int)v37);
          v39 = Heap;
          if ( !Heap )
          {
            v17 = 0;
            LastError = 8;
            v23 = 0;
            goto LABEL_289;
          }
          v40 = 2 * v34;
          memcpy_0(Heap, v31, v40);
          memcpy_0(&v39[v40], Src, 2LL * v35);
          DestroyEnvironmentBlock(Environment);
          Environment = v39;
        }
        v41 = lpApplicationName;
        LastError = AipCheckForAppPathsKey((wchar_t *)lpApplicationName, &Environment);
        if ( LastError )
          goto LABEL_34;
        v126 = (unsigned __int16 *)LocalAlloc(0x40u, 0x218u);
        v23 = v126;
        if ( !v126 )
        {
          LastError = 8;
LABEL_288:
          v17 = v125;
          goto LABEL_289;
        }
        if ( !(unsigned __int8)IsSdbGetKnownSafeLayersPresent() )
        {
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, &WPP_5a99e4d32d543c5ccd81a78831f70868_Traceguids);
          goto LABEL_80;
        }
        CurrentProcess = GetCurrentProcess();
        v43 = hSourceHandle;
        v44 = CurrentProcess;
        v45 = GetCurrentProcess();
        if ( !DuplicateHandle(v45, v43, v44, &TargetHandle, 0x410u, 0, 0) )
        {
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v51 = GetLastError();
            WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, &WPP_5a99e4d32d543c5ccd81a78831f70868_Traceguids, v51);
          }
          goto LABEL_80;
        }
        v46 = BaseReadAppCompatDataForProcess(TargetHandle, &v154, 0);
        if ( v46 )
        {
          v48 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
          {
LABEL_67:
            if ( (unsigned int)SdbGetKnownSafeLayers(v154, 256, v126) )
            {
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              {
                WPP_SF_SS(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  16,
                  (unsigned int)&WPP_5a99e4d32d543c5ccd81a78831f70868_Traceguids,
                  (_DWORD)v41,
                  (__int64)v126);
              }
            }
            else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                   && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              v49 = GetLastError();
              WPP_SF_SD(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, v50, (_DWORD)v41, v49);
            }
LABEL_80:
            if ( (v128 & 2) != 0 && !wcsstr(v126, L"VistaSetUp") )
            {
              v52 = L" VistaSetUp";
              if ( !*v126 )
                v52 = L"VistaSetUp";
              if ( StringCchCatW(v126, 0x10Cu, v52) < 0
                && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              {
                WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, &WPP_5a99e4d32d543c5ccd81a78831f70868_Traceguids);
              }
            }
            if ( *v126 )
            {
              v53 = -1;
              do
                ++v53;
              while ( v126[v53] );
              LastError = 0;
              v54 = RtlSetEnvironmentVar(&Environment, L"__COMPAT_LAYER", 14, v126, v53);
              if ( v54 < 0 )
                LastError = RtlNtStatusToDosErrorNoTeb(v54);
              if ( LastError )
                goto LABEL_288;
            }
            v55 = off_180047000;
            v160 = 0;
            v56 = 0;
            while ( 1 )
            {
              v57 = *v55;
              v58 = -1;
              do
                ++v58;
              while ( v57[v58] );
              v59 = RtlQueryEnvironmentVariable(0, v57, v58, v202, 260, &v160);
              if ( v59 < 0 )
                break;
              v61 = RtlSetEnvironmentVar(&Environment, *v55, v58, v202, v160);
              v62 = v61;
              if ( v61 < 0 )
              {
                if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                {
                  WPP_SF_SSD(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    21,
                    (unsigned int)&WPP_5a99e4d32d543c5ccd81a78831f70868_Traceguids,
                    (unsigned int)off_180047000[v56],
                    (__int64)v202,
                    v61);
                }
                v63 = v62;
                goto LABEL_109;
              }
              ++v56;
              ++v55;
              if ( v56 >= 3 )
                goto LABEL_110;
            }
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              WPP_SF_SD(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, v60, (unsigned int)off_180047000[v56], v59);
            v63 = v59;
LABEL_109:
            LastError = RtlNtStatusToDosErrorNoTeb(v63);
            if ( LastError )
              goto LABEL_287;
LABEL_110:
            LastError = 0;
            v149 = 0;
            v64 = 0;
            v65 = 0;
            v66 = (char *)Environment;
            do
            {
              v67 = -1;
              do
                ++v67;
              while ( *(_WORD *)&v66[2 * v67] );
              v68 = v67 + 1;
              v64 += v68;
              v69 = *(_WORD *)&v66[2 * v68] == 0;
              v66 += 2 * v68;
            }
            while ( !v69 );
            v70 = RtlExpandEnvironmentStrings(Environment, Environment, v64 + 1, 0, 0, &v149);
            if ( v70 != -1073741789 )
              goto LABEL_120;
            v71 = v149;
            v65 = LocalAlloc(0x40u, 2 * v149);
            if ( !v65 )
            {
              LocalFree(0);
              LastError = 8;
LABEL_117:
              v23 = v126;
              v17 = 0;
              goto LABEL_289;
            }
            v70 = RtlExpandEnvironmentStrings(Environment, Environment, v64 + 1, v65, v71, &v149);
            if ( v70 < 0
              || (RtlDestroyEnvironment((PWSTR)Environment), v70 = RtlCreateEnvironmentEx(v65, &Environment, 0), v70 < 0) )
            {
LABEL_120:
              LastError = RtlNtStatusToDosErrorNoTeb(v70);
            }
            LocalFree(v65);
            if ( LastError )
              goto LABEL_117;
            v19 = v128;
            if ( (v128 & 0x401) != 0 )
            {
              LastError = AiSetMandatoryPolicy(hToken);
              if ( LastError )
                goto LABEL_287;
            }
            p_hSourceHandle = &v157;
            if ( !v157 )
              p_hSourceHandle = &hSourceHandle;
            if ( UpdateProcThreadAttribute((LPPROC_THREAD_ATTRIBUTE_LIST)&v198, 0, 0x20000u, p_hSourceHandle, 8u, 0, 0) )
            {
              if ( UpdateProcThreadAttribute((LPPROC_THREAD_ATTRIBUTE_LIST)&v198, 0, 0x60001u, &Value, 4u, 0, 0) )
              {
                if ( !lpValue )
                  goto LABEL_133;
                v73 = -1;
                do
                  ++v73;
                while ( lpValue[v73] );
                if ( UpdateProcThreadAttribute((LPPROC_THREAD_ATTRIBUTE_LIST)&v198, 0, 0x20008u, lpValue, 2 * v73, 0, 0) )
                {
LABEL_133:
                  if ( (a13 & 6) == 0 )
                    goto LABEL_137;
                  if ( (a13 & 4) != 0 )
                    v139 = 2;
                  if ( UpdateProcThreadAttribute((LPPROC_THREAD_ATTRIBUTE_LIST)&v198, 0, 0x20012u, &v139, 4u, 0, 0) )
                  {
LABEL_137:
                    if ( (a13 & 8) != 0 )
                    {
                      memset_0(v173, 0, 0x208u);
                      v172 = 8;
                    }
                    else
                    {
                      if ( (a13 & 0x400) == 0 )
                      {
LABEL_140:
                        if ( v133 )
                        {
                          hMem = 0;
                          v74 = CreateBnoIsolationPrefix(hToken, &hMem);
                          LastErrorMsg = v74;
                          if ( v74 < 0 )
                          {
                            v76 = (unsigned int)v74;
                            v77 = 2535;
                            goto LABEL_143;
                          }
                          v78 = (_BYTE *)hMem - v171;
                          v79 = v171;
                          v80 = 136;
                          do
                          {
                            if ( v80 == -2147483510 )
                              break;
                            v81 = *(_WORD *)((char *)v79 + v78);
                            if ( !v81 )
                              break;
                            *v79++ = v81;
                            --v80;
                          }
                          while ( v80 );
                          v82 = v79 - 1;
                          LastErrorMsg = -2147024774;
                          if ( v80 )
                          {
                            v82 = v79;
                            LastErrorMsg = 0;
                          }
                          *v82 = 0;
                          if ( !v80 )
                          {
                            v76 = (unsigned int)LastErrorMsg;
                            v77 = 2537;
LABEL_143:
                            wil::details::in1diag3::Return_Hr(
                              retaddr,
                              (void *)v77,
                              (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
                              (const char *)v76,
                              TokenType);
                            if ( hMem )
                            {
                              LocalFree(hMem);
                              v17 = 0;
                              LastError = WIN32_FROM_HRESULT(LastErrorMsg);
                              v23 = v126;
                              goto LABEL_289;
                            }
LABEL_159:
                            v17 = 0;
                            LastError = WIN32_FROM_HRESULT(LastErrorMsg);
                            v23 = v126;
                            goto LABEL_289;
                          }
                          v170 = 1;
                          if ( UpdateProcThreadAttribute(
                                 (LPPROC_THREAD_ATTRIBUTE_LIST)&v198,
                                 0,
                                 0x20013u,
                                 &v170,
                                 0x114u,
                                 0,
                                 0) )
                          {
                            if ( hMem )
                              LocalFree(hMem);
                          }
                          else
                          {
                            LastErrorMsg = wil::details::in1diag3::Return_GetLastErrorMsg(
                                             retaddr,
                                             (void *)0x9EC,
                                             (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
                                             "Failed to add bnoIsolationParameter attribute",
                                             TokenTypea);
                            if ( hMem )
                              LocalFree(hMem);
                            if ( LastErrorMsg < 0 )
                              goto LABEL_159;
                          }
                          v18 = v134;
                          v30 = v129;
                        }
                        else
                        {
                          v18 = v134;
                          v30 = v129;
                        }
LABEL_164:
                        if ( (v19 & 0x800000) != 0 )
                          *(_QWORD *)&v169 = v169 | 0x1000000000000000LL;
                        if ( (v19 & 0x1000000) != 0 )
                        {
                          if ( (v19 & 0x80u) != 0 )
                          {
                            v83 = 4144;
                            *((_QWORD *)&v169 + 1) = 4144;
                          }
                          else
                          {
                            v141 = 0;
                            v140 = 0;
                            v129 = 0;
                            v156 = 4;
                            if ( RegGetValueW(
                                   HKEY_LOCAL_MACHINE,
                                   L"Software\\Microsoft\\Windows\\CurrentVersion\\Policies\\System",
                                   L"EnableAutoApproveIntegrityContinuity",
                                   0x10u,
                                   0,
                                   &v129,
                                   &v156)
                              || v129 )
                            {
                              v140 = 4;
                              if ( RegGetValueW(
                                     HKEY_LOCAL_MACHINE,
                                     L"Software\\Microsoft\\Windows\\CurrentVersion\\Policies\\System",
                                     L"AutoApproveMitigationPolicy",
                                     0x10u,
                                     0,
                                     &v141,
                                     &v140) )
                              {
                                v83 = 4112;
                                *((_QWORD *)&v169 + 1) = 4112;
                              }
                              else
                              {
                                v83 = 16LL * (v141 & 1);
                                if ( (v141 & 2) != 0 )
                                  v83 = 48;
                                if ( (v141 & 4) != 0 )
                                  v83 |= 0x1000uLL;
                                *((_QWORD *)&v169 + 1) = v83;
                              }
                            }
                            else
                            {
                              v83 = 0;
                              *((_QWORD *)&v169 + 1) = 0;
                            }
                          }
                        }
                        else
                        {
                          v83 = *((_QWORD *)&v169 + 1);
                        }
                        if ( !(_QWORD)v169 && !v83
                          || UpdateProcThreadAttribute(
                               (LPPROC_THREAD_ATTRIBUTE_LIST)&v198,
                               0,
                               0x20007u,
                               &v169,
                               0x10u,
                               0,
                               0) )
                        {
                          StartupInfo.cb = 112;
                          v84 = (struct _PROC_THREAD_ATTRIBUTE_LIST *)&v198;
                          if ( !v30 )
                            v84 = lpAttributeList;
                          lpAttributeList = v84;
                          StartupInfo.lpDesktop = (LPWSTR)v143;
                          if ( v18 )
                          {
                            StartupInfo.lpTitle = *(LPWSTR *)v18;
                            StartupInfo.dwX = *((_DWORD *)v18 + 2);
                            StartupInfo.dwY = *((_DWORD *)v18 + 3);
                            StartupInfo.dwXSize = *((_DWORD *)v18 + 4);
                            StartupInfo.dwYSize = *((_DWORD *)v18 + 5);
                            StartupInfo.dwXCountChars = *((_DWORD *)v18 + 6);
                            StartupInfo.dwYCountChars = *((_DWORD *)v18 + 7);
                            StartupInfo.dwFillAttribute = *((_DWORD *)v18 + 8);
                            StartupInfo.wShowWindow = *((_WORD *)v18 + 20);
                            v69 = (*((_DWORD *)v18 + 9) & 0x400) == 0;
                            StartupInfo.dwFlags = *((_DWORD *)v18 + 9) & 0xFFFFFCFF;
                            if ( !v69 )
                              StartupInfo.hStdOutput = MonitorFromPoint(*(POINT *)((char *)v18 + 44), 2u);
                          }
                          else
                          {
                            StartupInfo.dwFlags = 1;
                            StartupInfo.wShowWindow = 1;
                          }
                          if ( ImpersonateLoggedOnUser(hToken) )
                          {
                            if ( (v19 & 0x4004) == 0x4000
                              || (v85 = lpFileName, FilePart = 0, lpFileName)
                              && (GetFullPathNameW(lpFileName, 0x104u, Buffer, &FilePart) - 1 > 0x103
                               || (FileAttributesW = GetFileAttributesW(Buffer), FileAttributesW == -1)
                               || (FileAttributesW & 0x10) == 0) )
                            {
                              v85 = 0;
                              lpFileName = 0;
                            }
                            if ( a15 )
                            {
                              Context = 0;
                              fPending = 0;
                              if ( InitOnceBeginInitialize(
                                     &`AAMTraceProvider::Instance'::`2'::wrapper,
                                     0,
                                     &fPending,
                                     &Context)
                                && fPending )
                              {
                                Context = &qword_18005DD78;
                                qword_18005DD80 = 0;
                                byte_18005DD88 = 0;
                                dword_18005DD8C = 0;
                                qword_18005DD78 = (__int64)&wil::TraceLoggingProvider::`vftable';
                                CallbackContext = &`AAMTraceProvider::StaticHandle::StaticHandle'::`2'::__hInner;
                                atexit(_lambda_7e8ef9e9b596109f338594047241dcdf_::_lambda_invoker_cdecl_);
                                qword_18005DD80 = (__int64)CallbackContext;
                                byte_18005DD88 = 1;
                                TraceLoggingRegisterEx_EventRegister_EventSetInformation(CallbackContext);
                                dword_18005DD8C = 1;
                                (*(void (__fastcall **)(__int64 *))(qword_18005DD78 + 8))(&qword_18005DD78);
                                InitOnceComplete(&`AAMTraceProvider::Instance'::`2'::wrapper, 0, &qword_18005DD78);
                              }
                              v87 = (_DWORD *)*((_QWORD *)Context + 1);
                              if ( v87 && *v87 )
                              {
                                memset_0(v201, 0, sizeof(v201));
                                v147 = 464;
                                if ( (int)PsmGetKeyFromToken(hToken, v201, &v147, 0) < 0 )
                                  v201[0] = 0;
                                applicationUserModelIdLength = 131;
                                if ( GetApplicationUserModelIdFromToken(
                                       hToken,
                                       &applicationUserModelIdLength,
                                       applicationUserModelId) )
                                {
                                  applicationUserModelId[0] = 0;
                                }
                                v143 = 0;
                                v133 = 0;
                                if ( InitOnceBeginInitialize(
                                       &`AAMTraceProvider::Instance'::`2'::wrapper,
                                       0,
                                       &v133,
                                       &v143)
                                  && v133 )
                                {
                                  v143 = &qword_18005DD78;
                                  qword_18005DD80 = 0;
                                  byte_18005DD88 = 0;
                                  dword_18005DD8C = 0;
                                  qword_18005DD78 = (__int64)&wil::TraceLoggingProvider::`vftable';
                                  CallbackContext = &`AAMTraceProvider::StaticHandle::StaticHandle'::`2'::__hInner;
                                  atexit(_lambda_7e8ef9e9b596109f338594047241dcdf_::_lambda_invoker_cdecl_);
                                  qword_18005DD80 = (__int64)CallbackContext;
                                  byte_18005DD88 = 1;
                                  TraceLoggingRegisterEx_EventRegister_EventSetInformation(CallbackContext);
                                  dword_18005DD8C = 1;
                                  (*(void (__fastcall **)(__int64 *))(qword_18005DD78 + 8))(&qword_18005DD78);
                                  InitOnceComplete(&`AAMTraceProvider::Instance'::`2'::wrapper, 0, &qword_18005DD78);
                                }
                                v89 = *((_QWORD *)v143 + 1);
                                if ( *(_DWORD *)v89 > 5u
                                  && (*(_QWORD *)(v89 + 16) & 0x400000000000LL) != 0
                                  && (*(_QWORD *)(v89 + 24) & 0x400000000000LL) == *(_QWORD *)(v89 + 24) )
                                {
                                  v165 = a15;
                                  v184 = &v165;
                                  v90 = -1;
                                  v185 = 8;
                                  do
                                    v69 = applicationUserModelId[++v90] == 0;
                                  while ( !v69 );
                                  v183 = 0;
                                  v182 = 2 * v90 + 2;
                                  v181 = applicationUserModelId;
                                  v91 = -1;
                                  do
                                    v69 = v201[++v91] == 0;
                                  while ( !v69 );
                                  EventDescriptor.Keyword = 0x400000000000LL;
                                  v179 = 2 * v91 + 2;
                                  *(_DWORD *)&EventDescriptor.Level = 5;
                                  UserData.Ptr = *(_QWORD *)(v89 + 8);
                                  v178 = v201;
                                  v180 = 0;
                                  *(_DWORD *)&EventDescriptor.Id = 184549376;
                                  UserData.Size = *(unsigned __int16 *)UserData.Ptr;
                                  UserData.Reserved = 2;
                                  v175 = &unk_18005340F;
                                  v176 = 62;
                                  v177 = 1;
                                  LODWORD(v134) = (unsigned int)&TraceLoggingMetadataEnd
                                                - (unsigned int)&TraceLoggingMetadata;
                                  EventWriteTransfer(*(_QWORD *)(v89 + 32), &EventDescriptor, 0, 0, 5u, &UserData);
                                }
                              }
                            }
                            if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_1200131385>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_1200131385>::GetImpl'::`2'::impl) )
                            {
                              v108 = v132;
                              v110 = lpApplicationName;
                              lpCurrentDirectory = v85;
                              v111 = SourceString;
                              if ( !CreateProcessAsUserW(
                                      hToken,
                                      lpApplicationName,
                                      (LPWSTR)SourceString,
                                      0,
                                      0,
                                      0,
                                      v132 | 0x80004,
                                      Environment,
                                      lpCurrentDirectory,
                                      &StartupInfo,
                                      &ProcessInformation) )
                                LastError = GetLastError();
                              RevertToSelf();
                              if ( LastError )
                                goto LABEL_287;
                              if ( !v110 )
                                v110 = v111;
                              LastError = AipValidateLaunchedProcess(v110, ProcessInformation.hProcess, v158);
                              if ( !LastError )
                                goto LABEL_266;
                              v96 = -1;
                              goto LABEL_284;
                            }
                            v92 = lpApplicationName;
                            v93 = lpApplicationName;
                            if ( !(unsigned int)LUAIsShadowAdminEnabled() || (v128 & 0x20000000) != 0 )
                            {
                              v96 = -1;
                              goto LABEL_253;
                            }
                            v94 = v92;
                            if ( !v92 )
                              v94 = SourceString;
                            FileW = CreateFileW(v94, 0x80000000, 5u, 0, 3u, 0x2000000u, 0);
                            hFile = (__int64)FileW;
                            v96 = (__int64)FileW;
                            if ( FileW == (HANDLE)-1LL )
                            {
                              LastError = GetLastError();
LABEL_227:
                              v17 = v125;
                              v23 = v126;
                              goto LABEL_290;
                            }
                            FinalPathNameByHandleW = GetFinalPathNameByHandleW(FileW, 0, 0, 8u);
                            v98 = FinalPathNameByHandleW;
                            if ( FinalPathNameByHandleW )
                            {
                              v99 = (WCHAR *)LocalAlloc(0x40u, 2LL * (FinalPathNameByHandleW + 1));
                              v125 = v99;
                              v100 = v99;
                              if ( !v99 )
                              {
                                v23 = v126;
                                LastError = 8;
                                v17 = 0;
                                goto LABEL_289;
                              }
                              v101 = v98;
                              v96 = hFile;
                              v102 = GetFinalPathNameByHandleW((HANDLE)hFile, v99, v101, 8u);
                              if ( v102 )
                              {
                                if ( v102 - 3 > 0x104 )
                                {
                                  if ( v92 )
                                    v93 = v100;
                                  else
                                    SourceString = v100;
                                  v103 = (_DWORD *)*((_QWORD *)LUATelemetry::Instance() + 1);
                                  if ( v103 )
                                  {
                                    if ( *v103 )
                                    {
                                      LUATelemetry::Instance();
                                      v104 = *((_QWORD *)LUATelemetry::Instance() + 1);
                                      if ( *(_DWORD *)v104 > 5u )
                                      {
                                        lpApplicationName = (LPCWSTR)50331648;
                                        p_lpApplicationName = &lpApplicationName;
                                        v105 = -1;
                                        v197 = 8;
                                        do
                                          v69 = v100[++v105] == 0;
                                        while ( !v69 );
                                        v193 = v100;
                                        v194 = 2 * v105 + 2;
                                        v195 = 0;
                                        if ( v94 )
                                        {
                                          v106 = -1;
                                          do
                                            v69 = v94[++v106] == 0;
                                          while ( !v69 );
                                          v107 = 2 * v106 + 2;
                                        }
                                        else
                                        {
                                          v94 = &String2;
                                          v107 = 2;
                                        }
                                        v191 = v107;
                                        *(_DWORD *)&v167.Level = 5;
                                        v186.Ptr = *(_QWORD *)(v104 + 8);
                                        v192 = 0;
                                        v167.Keyword = 0;
                                        v190 = v94;
                                        *(_DWORD *)&v167.Id = 184549376;
                                        v186.Size = *(unsigned __int16 *)v186.Ptr;
                                        v186.Reserved = 2;
                                        v187 = &unk_180053FDE;
                                        v188 = 90;
                                        v189 = 1;
                                        LODWORD(v134) = (unsigned int)&TraceLoggingMetadataEnd
                                                      - (unsigned int)&TraceLoggingMetadata;
                                        EventWriteTransfer(*(_QWORD *)(v104 + 32), &v167, 0, 0, 5u, &v186);
                                      }
                                    }
                                  }
                                }
                                else if ( v92 )
                                {
                                  v93 = v100 + 4;
                                }
                                else
                                {
                                  SourceString = v100 + 4;
                                }
                              }
                              else
                              {
                                LastError = GetLastError();
                                if ( LastError != 5 )
                                {
                                  v23 = v126;
                                  v17 = (WCHAR *)v100;
                                  goto LABEL_290;
                                }
                                LastError = 0;
                              }
LABEL_253:
                              v108 = v132;
                              if ( !CreateProcessAsUserW(
                                      hToken,
                                      v93,
                                      (LPWSTR)SourceString,
                                      0,
                                      0,
                                      0,
                                      v132 | 0x80004,
                                      Environment,
                                      lpFileName,
                                      &StartupInfo,
                                      &ProcessInformation) )
                                LastError = GetLastError();
                              RevertToSelf();
                              if ( LastError )
                                goto LABEL_227;
                              v109 = SourceString;
                              if ( v92 )
                                v109 = v93;
                              LastError = AipValidateLaunchedProcess(v109, ProcessInformation.hProcess, v158);
                              if ( !LastError )
                              {
LABEL_266:
                                v112 = p_hProcess;
                                if ( !hSourceHandle )
                                {
                                  *p_hProcess = ProcessInformation.hProcess;
                                  v112[1] = ProcessInformation.hThread;
                                  ProcessInformation.hProcess = 0;
                                  ProcessInformation.hThread = 0;
LABEL_281:
                                  *((_DWORD *)v112 + 4) = ProcessInformation.dwProcessId;
                                  *((_DWORD *)v112 + 5) = ProcessInformation.dwThreadId;
                                  goto LABEL_287;
                                }
                                v113 = v128;
                                v114 = v128 & 0x401;
                                v115 = v114 != 0 ? 0x20000100 : 0;
                                v116 = 0;
                                if ( (v128 & 0x401) == 0 )
                                  v116 = 2;
                                Value = v116;
                                v117 = NtDuplicateObject(
                                         (HANDLE)0xFFFFFFFFFFFFFFFFLL,
                                         ProcessInformation.hProcess,
                                         hSourceHandle,
                                         p_hProcess,
                                         (v128 & 0x401) != 0 ? 0x20000100 : 0,
                                         0,
                                         v116);
                                if ( v117 >= 0 )
                                {
                                  if ( v114 )
                                  {
                                    v119 = 0;
                                    v115 = 536870914;
                                    Value = 0;
                                  }
                                  else
                                  {
                                    v119 = Value;
                                  }
                                  v117 = NtDuplicateObject(
                                           (HANDLE)0xFFFFFFFFFFFFFFFFLL,
                                           ProcessInformation.hThread,
                                           hSourceHandle,
                                           v112 + 1,
                                           v115,
                                           0,
                                           v119);
                                  if ( v117 >= 0 )
                                  {
                                    if ( (v113 & 1) == 0 )
                                      goto LABEL_278;
                                    LastError = AipAddProfileReference(a11, hToken, hProfile);
                                    if ( !LastError )
                                    {
                                      hProfile = 0;
LABEL_278:
                                      if ( (v108 & 4) == 0 )
                                        ResumeThread(ProcessInformation.hThread);
                                      goto LABEL_281;
                                    }
LABEL_287:
                                    v23 = v126;
                                    goto LABEL_288;
                                  }
                                }
                                v118 = RtlNtStatusToDosErrorNoTeb(v117);
LABEL_286:
                                LastError = v118;
                                goto LABEL_287;
                              }
LABEL_284:
                              v23 = v126;
                              v17 = v125;
                              goto LABEL_290;
                            }
                          }
                        }
                        v118 = GetLastError();
                        goto LABEL_286;
                      }
                      memset_0(v173, 0, 0x208u);
                      v172 = 256;
                    }
                    if ( UpdateProcThreadAttribute(
                           (LPPROC_THREAD_ATTRIBUTE_LIST)&v198,
                           0,
                           0x20011u,
                           &v172,
                           0x20Cu,
                           0,
                           0) )
                    {
                      goto LABEL_140;
                    }
                  }
                }
              }
            }
            v17 = 0;
            v23 = v126;
            LastError = GetLastError();
            goto LABEL_289;
          }
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          {
LABEL_64:
            if ( v48 != &WPP_GLOBAL_Control && (*((_BYTE *)v48 + 28) & 1) != 0 )
              WPP_SF_S(v48[2], 14, &WPP_5a99e4d32d543c5ccd81a78831f70868_Traceguids, v41);
            goto LABEL_67;
          }
          WPP_SF_SD(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, v47, (_DWORD)v41, v46);
        }
        v48 = WPP_GLOBAL_Control;
        goto LABEL_64;
      }
      Value |= 2u;
    }
    v132 = a7;
    goto LABEL_22;
  }
  ObjectAttributes.Length = 48;
  memset(&ObjectAttributes.RootDirectory, 0, 20);
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v22 = NtDuplicateToken(ExistingTokenHandle, 0, &ObjectAttributes, 0, TokenPrimary, &hToken);
  if ( v22 >= 0 )
    goto LABEL_5;
  LastError = RtlNtStatusToDosErrorNoTeb(v22);
  v23 = 0;
LABEL_289:
  v96 = hFile;
LABEL_290:
  if ( lpAttributeList )
    DeleteProcThreadAttributeList(lpAttributeList);
  if ( Environment )
    DestroyEnvironmentBlock(Environment);
  if ( hProfile )
    UnloadUserProfile(hToken, hProfile);
  if ( ProcessInformation.hThread )
    CloseHandle(ProcessInformation.hThread);
  if ( ProcessInformation.hProcess )
  {
    if ( LastError )
      TerminateProcess(ProcessInformation.hProcess, LastError);
    CloseHandle(ProcessInformation.hProcess);
  }
  if ( TargetHandle )
    CloseHandle(TargetHandle);
  if ( v154 )
    BaseFreeAppCompatDataForProcess();
  if ( v23 )
    LocalFree(v23);
  if ( hToken && hToken != ExistingTokenHandle )
  {
    NtClose(hToken);
    hToken = 0;
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_1200131385>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_1200131385>::GetImpl'::`2'::impl) )
  {
    if ( v17 )
      LocalFree(v17);
    if ( v96 != -1 )
      CloseHandle((HANDLE)v96);
  }
  return LastError;
}

```

## disassembly

```asm
0x180014da0  mov     [rsp-8+arg_18], rbx
0x180014da5  push    rbp
0x180014da6  push    rsi
0x180014da7  push    rdi
0x180014da8  push    r12
0x180014daa  push    r13
0x180014dac  push    r14
0x180014dae  push    r15
0x180014db0  lea     rbp, [rsp-0D90h]
0x180014db8  sub     rsp, 0E90h
0x180014dbf  mov     rax, cs:__security_cookie
0x180014dc6  xor     rax, rsp
0x180014dc9  mov     [rbp+0DC0h+var_40], rax
0x180014dd0  mov     rax, [rbp+0DC0h+arg_20]
0x180014dd7  xor     r12d, r12d
0x180014dda  mov     rsi, [rbp+0DC0h+arg_48]
0x180014de1  xorps   xmm0, xmm0
0x180014de4  mov     r13, [rbp+0DC0h+lpValue]
0x180014deb  mov     r15d, r9d
0x180014dee  mov     r14, [rbp+0DC0h+Src]
0x180014df5  mov     ebx, r12d
0x180014df8  mov     [rbp+0DC0h+lpApplicationName], rax
0x180014dfc  mov     rax, [rbp+0DC0h+arg_28]
0x180014e03  mov     [rbp+0DC0h+SourceString], rax
0x180014e07  mov     rax, [rbp+0DC0h+arg_38]
0x180014e0e  mov     [rbp+0DC0h+lpFileName], rax
0x180014e12  mov     rax, [rbp+0DC0h+arg_40]
0x180014e19  mov     [rbp+0DC0h+var_DE8], rax
0x180014e1d  mov     rax, [rbp+0DC0h+arg_68]
0x180014e24  mov     [rbp+0DC0h+var_D70], rax
0x180014e28  mov     rax, [rbp+0DC0h+arg_80]
0x180014e2f  mov     [rbp+0DC0h+var_D60], rax
0x180014e33  xor     eax, eax
0x180014e35  mov     [rbp+0DC0h+var_D68], r8
0x180014e39  mov     r8d, 14Ch; Size
0x180014e3f  mov     [rbp+0DC0h+ExistingTokenHandle], rdx
0x180014e43  xor     edx, edx; Val
0x180014e45  mov     [rbp+0DC0h+hSourceHandle], rcx
0x180014e49  lea     rcx, [rbp+0DC0h+var_88C]; void *
0x180014e50  mov     [rbp+0DC0h+lpAttributeList], rax
0x180014e57  mov     qword ptr [rbp+0DC0h+ProcessInformation.dwProcessId], rax
0x180014e5b  mov     [rbp+0DC0h+var_E40], r9d
0x180014e5f  mov     [rbp+0DC0h+var_E20], rsi
0x180014e63  mov     [rbp+0DC0h+Value], r12d
0x180014e67  mov     [rsp+0EC0h+var_E50], r12
0x180014e6c  mov     [rbp+0DC0h+TargetHandle], r12
0x180014e70  mov     [rsp+0EC0h+hToken], r12
0x180014e75  mov     [rbp+0DC0h+hProfile], r12
0x180014e79  mov     [rbp+0DC0h+Environment], r12
0x180014e7d  mov     qword ptr [rbp+0DC0h+StartupInfo.cb], r12
0x180014e81  movups  xmmword ptr [rbp+0DC0h+StartupInfo.lpReserved], xmm0
0x180014e85  mov     [rbp+0DC0h+var_890], r12d
0x180014e8c  movups  xmmword ptr [rbp+0DC0h+StartupInfo.lpTitle], xmm0
0x180014e93  movups  xmmword ptr [rbp+0DC0h+StartupInfo.dwXSize], xmm0
0x180014e9a  movups  xmmword ptr [rbp+0DC0h+StartupInfo.dwFillAttribute], xmm0
0x180014ea1  movups  xmmword ptr [rbp+0DC0h+StartupInfo.lpReserved2], xmm0
0x180014ea8  movups  xmmword ptr [rbp+0DC0h+StartupInfo.hStdOutput], xmm0
0x180014eaf  movups  xmmword ptr [rbp+0DC0h+ProcessInformation.hProcess], xmm0
0x180014eb3  call    memset_0
0x180014eb8  xorps   xmm0, xmm0
0x180014ebb  mov     [rbp+0DC0h+Size], 150h
0x180014ec6  xor     edx, edx; Val
0x180014ec8  mov     [rbp+0DC0h+var_D88], r12
0x180014ecc  mov     r8d, 20Ch; Size
0x180014ed2  mov     [rbp+0DC0h+var_DFC], 4
0x180014ed9  lea     rcx, [rbp+0DC0h+var_B40]; void *
0x180014ee0  mov     edi, r12d
0x180014ee3  movups  xmmword ptr [rbp+0DC0h+ObjectAttributes.Length], xmm0
0x180014eea  movups  xmmword ptr [rbp+0DC0h+ObjectAttributes.ObjectName], xmm0
0x180014ef1  movups  xmmword ptr [rbp+0DC0h+ObjectAttributes.SecurityDescriptor], xmm0
0x180014ef8  movups  [rbp+0DC0h+var_C78], xmm0
0x180014eff  call    memset_0
0x180014f04  xor     edx, edx; Val
0x180014f06  lea     rcx, [rbp+0DC0h+var_C60]; void *
0x180014f0d  mov     r8d, 114h; Size
0x180014f13  call    memset_0
0x180014f18  mov     [rsp+0EC0h+hFile], 0FFFFFFFFFFFFFFFFh
0x180014f21  lea     eax, [r12+30h]
0x180014f26  mov     [rsp+0EC0h+var_E58], r12
0x180014f2b  test    r15b, r15b
0x180014f2e  js      short loc_180014FA1
0x180014f30  mov     rcx, [rbp+0DC0h+ExistingTokenHandle]; ExistingTokenHandle
0x180014f34  lea     r8, [rbp+0DC0h+ObjectAttributes]; ObjectAttributes
0x180014f3b  mov     [rbp+0DC0h+ObjectAttributes.Length], eax
0x180014f41  xorps   xmm0, xmm0
0x180014f44  xor     eax, eax
0x180014f46  xor     r9d, r9d; EffectiveOnly
0x180014f49  mov     [rbp+0DC0h+ObjectAttributes.RootDirectory], rax
0x180014f50  xor     edx, edx; DesiredAccess
0x180014f52  mov     [rbp+0DC0h+ObjectAttributes.Attributes], eax
0x180014f58  mov     [rbp+0DC0h+ObjectAttributes.ObjectName], rax
0x180014f5f  lea     rax, [rsp+0EC0h+hToken]
0x180014f64  mov     [rsp+0EC0h+NewTokenHandle], rax; NewTokenHandle
0x180014f69  mov     [rsp+0EC0h+TokenType], 1; TokenType
0x180014f71  movdqu  xmmword ptr [rbp+0DC0h+ObjectAttributes.SecurityDescriptor], xmm0
0x180014f79  call    cs:__imp_NtDuplicateToken
0x180014f80  nop     dword ptr [rax+rax+00h]
0x180014f85  test    eax, eax
0x180014f87  jns     short loc_180014FAA
0x180014f89  mov     ecx, eax; Status
0x180014f8b  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x180014f92  nop     dword ptr [rax+rax+00h]
0x180014f97  mov     ebx, eax
0x180014f99  mov     r14d, edi
0x180014f9c  jmp     loc_180016749
0x180014fa1  mov     rax, [rbp+0DC0h+ExistingTokenHandle]
0x180014fa5  mov     [rsp+0EC0h+hToken], rax
0x180014faa  test    r15b, 4
0x180014fae  jz      loc_18001508E
0x180014fb4  lea     rax, [rbp+0DC0h+var_D98]
0x180014fb8  mov     [rbp+0DC0h+pvData], ebx
0x180014fbb  mov     [rsp+0EC0h+pcbData], rax; pcbData
0x180014fc0  lea     r8, aEnablesecureui; "EnableSecureUIAPaths"
0x180014fc7  lea     rax, [rbp+0DC0h+pvData]
0x180014fcb  mov     [rbp+0DC0h+var_D98], 4
0x180014fd2  mov     [rsp+0EC0h+NewTokenHandle], rax; pvData
0x180014fd7  lea     rdx, aSoftwareMicros_0; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180014fde  mov     r9d, 10h; dwFlags
0x180014fe4  mov     qword ptr [rsp+0EC0h+TokenType], rbx; pdwType
0x180014fe9  mov     rcx, 0FFFFFFFF80000002h; hkey
0x180014ff0  call    cs:__imp_RegGetValueW
0x180014ff7  nop     dword ptr [rax+rax+00h]
0x180014ffc  test    eax, eax
0x180014ffe  jnz     short loc_180015005
0x180015000  cmp     [rbp+0DC0h+pvData], ebx
0x180015003  jz      short loc_18001500C
0x180015005  bt      r15d, 0Dh
0x18001500a  jnb     short loc_180015015
0x18001500c  bts     r15d, 0Ah
0x180015011  mov     [rbp+0DC0h+var_E40], r15d
0x180015015  bt      r15d, 0Ah
0x18001501a  jnb     short loc_18001508A
0x18001501c  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ShadowAdmin@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ShadowAdmin@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShadowAdmin> `wil::Feature<__WilFeatureTraits_Feature_ShadowAdmin>::GetImpl(void)'::`2'::impl
0x180015023  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ShadowAdmin@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShadowAdmin>::__private_IsEnabled(void)
0x180015028  mov     edx, [rbp+0DC0h+arg_30]
0x18001502e  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_2045735225@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_2045735225@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_2045735225> `wil::Feature<__WilFeatureTraits_Feature_2045735225>::GetImpl(void)'::`2'::impl
0x180015035  and     edx, 0FFFFFFFCh
0x180015038  test    al, al
0x18001503a  cmovz   edx, [rbp+0DC0h+arg_30]
0x180015041  mov     [rbp+0DC0h+var_E2C], edx
0x180015044  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_2045735225@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_2045735225>::__private_IsEnabled(void)
0x180015049  test    al, al
0x18001504b  jz      short loc_180015072
0x18001504d  lea     rcx, [rsp+0EC0h+hToken]
0x180015052  call    LUASetUIAToken2
0x180015057  mov     ebx, eax
0x180015059  call    LUAIsShadowAdminEnabled
0x18001505e  mov     ecx, r15d
0x180015061  or      ecx, 1
0x180015064  test    eax, eax
0x180015066  cmovz   ecx, r15d
0x18001506a  mov     r15d, ecx
0x18001506d  mov     [rbp+0DC0h+var_E40], ecx
0x180015070  jmp     short loc_18001507E
0x180015072  mov     rcx, [rsp+0EC0h+hToken]; TokenHandle
0x180015077  call    LUASetUIAToken
0x18001507c  mov     ebx, eax
0x18001507e  test    ebx, ebx
0x180015080  jz      short loc_180015097
0x180015082  mov     r14, rdi
0x180015085  jmp     loc_180016749
0x18001508a  or      [rbp+0DC0h+Value], 2
0x18001508e  mov     eax, [rbp+0DC0h+arg_30]
0x180015094  mov     [rbp+0DC0h+var_E2C], eax
0x180015097  mov     r12d, dword ptr [rbp+0DC0h+arg_60]
0x18001509e  cmp     [rbp+0DC0h+hSourceHandle], rdi
0x1800150a2  jz      short loc_1800150B6
0x1800150a4  test    r13, r13
0x1800150a7  setnz   dil
0x1800150ab  add     edi, 2
0x1800150ae  test    r12b, 6
0x1800150b2  jz      short loc_1800150B6
0x1800150b4  inc     edi
0x1800150b6  test    r15d, 1800000h
0x1800150bd  lea     eax, [rdi+1]
0x1800150c0  cmovz   eax, edi
0x1800150c3  test    r12d, 408h
0x1800150ca  lea     ecx, [rax+1]
0x1800150cd  cmovz   ecx, eax
0x1800150d0  mov     eax, r12d
0x1800150d3  and     eax, 2000h
0x1800150d8  mov     [rbp+0DC0h+var_E28], eax
0x1800150db  lea     edi, [rcx+1]
0x1800150de  cmovz   edi, ecx
0x1800150e1  mov     [rbp+0DC0h+var_E3C], edi
0x1800150e4  test    edi, edi
0x1800150e6  jz      short loc_180015126
0x1800150e8  lea     r9, [rbp+0DC0h+Size]; lpSize
0x1800150ef  xor     r8d, r8d; dwFlags
0x1800150f2  mov     edx, edi; dwAttributeCount
0x1800150f4  lea     rcx, [rbp+0DC0h+var_890]; lpAttributeList
0x1800150fb  call    cs:__imp_InitializeProcThreadAttributeList
0x180015102  nop     dword ptr [rax+rax+00h]
0x180015107  test    eax, eax
0x180015109  jnz     short loc_180015126
0x18001510b  call    cs:__imp_GetLastError
0x180015112  nop     dword ptr [rax+rax+00h]
0x180015117  mov     ebx, eax
0x180015119  mov     r12, [rsp+0EC0h+var_E58]
0x18001511e  mov     r14, r12
0x180015121  jmp     loc_180016749
0x180015126  cmp     [rbp+0DC0h+hSourceHandle], 0
0x18001512b  jz      loc_180015B27
0x180015131  test    r15b, 1
0x180015135  jz      short loc_18001514B
0x180015137  mov     rcx, [rsp+0EC0h+hToken]; hToken
0x18001513c  lea     rdx, [rbp+0DC0h+hProfile]; void **
0x180015140  call    ?AipLoadUserProfile@@YAKPEAXPEAPEAX@Z; AipLoadUserProfile(void *,void * *)
0x180015145  mov     ebx, eax
0x180015147  test    eax, eax
0x180015149  jnz     short loc_180015119
0x18001514b  mov     rdx, [rsp+0EC0h+hToken]; hToken
0x180015150  lea     rcx, [rbp+0DC0h+Environment]; lpEnvironment
0x180015154  xor     r8d, r8d; bInherit
0x180015157  call    cs:__imp_CreateEnvironmentBlock
0x18001515e  nop     dword ptr [rax+rax+00h]
0x180015163  test    eax, eax
0x180015165  jz      short loc_18001510B
0x180015167  test    r14, r14
0x18001516a  jz      loc_180015248
0x180015170  mov     r15, [rbp+0DC0h+Environment]
0x180015174  xor     r9d, r9d
0x180015177  mov     r8d, r9d
0x18001517a  nop     word ptr [rax+rax+00h]
0x180015180  mov     rcx, [rbp+0DC0h+Environment]
0x180015184  lea     edx, [r8+1]
0x180015188  mov     eax, r8d
0x18001518b  cmp     [rcx+rax*2], r9w
0x180015190  jnz     short loc_180015199
0x180015192  cmp     [rcx+rdx*2], r9w
0x180015197  jz      short loc_18001519E
0x180015199  mov     r8d, edx
0x18001519c  jmp     short loc_180015180
0x18001519e  mov     edx, r9d
0x1800151a1  mov     eax, edx
0x1800151a3  lea     ecx, [rdx+1]
0x1800151a6  cmp     [r14+rax*2], r9w
0x1800151ab  jnz     short loc_1800151B4
0x1800151ad  cmp     [r14+rcx*2], r9w
0x1800151b2  jz      short loc_1800151B8
0x1800151b4  mov     edx, ecx
0x1800151b6  jmp     short loc_1800151A1
0x1800151b8  lea     ebx, [r8+1]
0x1800151bc  lea     esi, [rdx+2]
0x1800151bf  lea     eax, [rbx+rsi]
0x1800151c2  cmp     eax, ebx
0x1800151c4  jb      loc_18001528B
0x1800151ca  add     rax, rax
0x1800151cd  mov     ecx, 0FFFFFFFFh
0x1800151d2  cmp     rax, rcx
0x1800151d5  ja      loc_18001528B
0x1800151db  mov     rcx, gs:60h
0x1800151e4  xor     edx, edx; Flags
0x1800151e6  mov     r8d, eax; Size
0x1800151e9  mov     rcx, [rcx+30h]; HeapHandle
0x1800151ed  call    cs:__imp_RtlAllocateHeap
0x1800151f4  nop     dword ptr [rax+rax+00h]
0x1800151f9  mov     rdi, rax
0x1800151fc  test    rax, rax
0x1800151ff  jnz     short loc_180015211
0x180015201  mov     r12, [rsp+0EC0h+var_E58]
0x180015206  lea     ebx, [rax+8]
0x180015209  mov     r14, r12
0x18001520c  jmp     loc_180016749
0x180015211  add     rbx, rbx
0x180015214  mov     rdx, r15; Src
0x180015217  mov     r8, rbx; Size
0x18001521a  mov     rcx, rdi; void *
0x18001521d  call    memcpy_0
0x180015222  mov     r8d, esi
0x180015225  lea     rcx, [rbx+rdi]; void *
0x180015229  add     r8, r8; Size
0x18001522c  mov     rdx, r14; Src
0x18001522f  call    memcpy_0
0x180015234  mov     rcx, [rbp+0DC0h+Environment]; lpEnvironment
0x180015238  call    cs:__imp_DestroyEnvironmentBlock
0x18001523f  nop     dword ptr [rax+rax+00h]
0x180015244  mov     [rbp+0DC0h+Environment], rdi
0x180015248  mov     rsi, [rbp+0DC0h+lpApplicationName]
0x18001524c  lea     rdx, [rbp+0DC0h+Environment]; void **
0x180015250  mov     rcx, rsi; Str
0x180015253  call    ?AipCheckForAppPathsKey@@YAKPEBGPEAPEAX@Z; AipCheckForAppPathsKey(ushort const *,void * *)
0x180015258  mov     ebx, eax
0x18001525a  test    eax, eax
0x18001525c  jnz     loc_180015119
0x180015262  mov     edx, 218h; uBytes
0x180015267  lea     ecx, [rax+40h]; uFlags
0x18001526a  call    cs:__imp_LocalAlloc
0x180015271  nop     dword ptr [rax+rax+00h]
0x180015276  mov     [rsp+0EC0h+var_E50], rax
0x18001527b  mov     r14, rax
0x18001527e  test    rax, rax
0x180015281  jnz     short loc_18001529B
0x180015283  lea     ebx, [rax+8]
0x180015286  jmp     loc_180016744
0x18001528b  mov     ebx, 216h
0x180015290  mov     r12, r9
0x180015293  mov     r14, r9
0x180015296  jmp     loc_180016749
0x18001529b  call    IsSdbGetKnownSafeLayersPresent
  ... truncated ...
```
