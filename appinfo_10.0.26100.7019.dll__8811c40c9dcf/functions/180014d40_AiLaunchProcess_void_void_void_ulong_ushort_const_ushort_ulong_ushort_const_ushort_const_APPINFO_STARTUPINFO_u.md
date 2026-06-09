# AiLaunchProcess(void *,void *,void *,ulong,ushort const *,ushort *,ulong,ushort const *,ushort const *,_APPINFO_STARTUPINFO *,ulong,ushort *,ulong,void *,unsigned __int64,ushort const *,_PROCESS_INFORMATION *)

- ea: `0x180014d40`
- end: `0x18001675a`
- name: `?AiLaunchProcess@@YAKPEAX00KPEBGPEAGK11PEAU_APPINFO_STARTUPINFO@@K2K0_K1PEAU_PROCESS_INFORMATION@@@Z`
- size: `6682`
- prototype: `__int64 __fastcall(void *, void *, char *, DWORD, const unsigned __int16 *, unsigned __int16 *, unsigned int, const unsigned __int16 *, unsigned __int16 *, struct _APPINFO_STARTUPINFO *, unsigned int, _WORD *lpValue, __int16, void *, unsigned __int64, const unsigned __int16 *Src, struct _PROCESS_INFORMATION *)`
- caller_count: `4`
- callee_count: `25`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1800263a8`
- `0x18002b828`
- `0x180039cb0`
- `0x18003bfe0`

## callees

- `0x180001008`
- `0x180007c78`
- `0x18000a4f0`
- `0x180010b80`
- `0x180012584`
- `0x1800128d4`
- `0x180014d40`
- `0x180017f68`
- `0x18001943c`
- `0x18001b690`
- `0x18001cc5c`
- `0x18002444c`
- `0x180024db0`
- `0x180025ac4`
- `0x18002e038`
- `0x1800365d0`
- `0x18003b5cc`
- `0x18003b634`
- `0x18003b754`
- `0x18003b808`
- `0x180042912`
- `0x18004292a`
- `0x180042950`
- `0x180042a10`
- `0x180043010`

## import_xrefs

- `msvcrt!wcscat_s` at `0x18001622c`
- `msvcrt!wcscat_s` at `0x1800162a2`
- `msvcrt!wcscat_s` at `0x18001622c`
- `msvcrt!wcscat_s` at `0x1800162a2`
- `msvcrt!wcscpy_s` at `0x18001620d`
- `msvcrt!wcscpy_s` at `0x180016283`
- `msvcrt!wcscpy_s` at `0x18001620d`
- `msvcrt!wcscpy_s` at `0x180016283`
- `msvcrt!wcsstr` at `0x1800153d8`
- `msvcrt!wcsstr` at `0x1800153d8`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800160e8`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800160e8`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180015cb8`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180015cb8`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180016166`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180016166`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180015d5c`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180015eca`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180015d5c`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180015eca`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180015e12`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180015f72`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180015e12`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180015f72`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015064`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800152ea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015369`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016158`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015064`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800152ea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015369`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016158`
- `api-ms-win-core-processthreads-l1-1-0!DeleteProcThreadAttributeList` at `0x180016657`
- `api-ms-win-core-processthreads-l1-1-0!DeleteProcThreadAttributeList` at `0x180016657`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x18001660e`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x18001660e`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x1800166b9`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x1800166b9`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x180016148`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x180016148`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800151ef`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180015202`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800151ef`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180015202`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x180015716`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x180015750`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x1800157a0`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x1800157ee`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x180015853`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x1800159e3`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x180015bd2`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x180015716`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x180015750`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x1800157a0`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x1800157ee`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x180015853`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x1800159e3`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x180015bd2`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x180015054`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x180015054`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001640a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180016420`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001669b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800166c9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800166de`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001640a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180016420`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001669b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800166c9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800166de`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18001522d`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18001522d`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180014f80`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180015add`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180015b3e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180014f80`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180015add`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180015b3e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180015653`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800156ae`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800158b4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180015a1d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180015a44`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001659b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016707`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180015653`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800156ae`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800158b4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180015a1d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180015a44`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001659b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016707`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800151b7`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001563c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180016520`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800151b7`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001563c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180016520`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180015d17`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180015d17`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x180015cfb`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x180015cfb`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180016260`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800162d6`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180016260`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800162d6`
- `api-ms-win-core-appcompat-l1-1-1!BaseFreeAppCompatDataForProcess` at `0x1800166f3`
- `api-ms-win-core-appcompat-l1-1-1!BaseFreeAppCompatDataForProcess` at `0x1800166f3`
- `api-ms-win-core-appcompat-l1-1-1!BaseReadAppCompatDataForProcess` at `0x18001524c`
- `api-ms-win-core-appcompat-l1-1-1!BaseReadAppCompatDataForProcess` at `0x18001524c`
- `api-ms-win-appmodel-runtime-l1-1-1!GetApplicationUserModelIdFromToken` at `0x180015e99`
- `api-ms-win-appmodel-runtime-l1-1-1!GetApplicationUserModelIdFromToken` at `0x180015e99`
- `api-ms-win-core-psm-key-l1-1-0!PsmGetKeyFromToken` at `0x180015e6b`
- `api-ms-win-core-psm-key-l1-1-0!PsmGetKeyFromToken` at `0x180015e6b`
- `ntdll!NtClose` at `0x1800163ef`
- `ntdll!NtClose` at `0x180016721`
- `ntdll!NtClose` at `0x1800163ef`
- `ntdll!NtClose` at `0x180016721`
- `ntdll!NtDuplicateObject` at `0x180016485`
- `ntdll!NtDuplicateObject` at `0x1800164de`
- `ntdll!NtDuplicateObject` at `0x18001656d`
- `ntdll!NtDuplicateObject` at `0x180016485`
- `ntdll!NtDuplicateObject` at `0x1800164de`
- `ntdll!NtDuplicateObject` at `0x18001656d`
- `ntdll!LdrQueryImageFileKeyOption` at `0x18001637a`
- `ntdll!LdrQueryImageFileKeyOption` at `0x1800163b4`
- `ntdll!LdrQueryImageFileKeyOption` at `0x18001637a`
- `ntdll!LdrQueryImageFileKeyOption` at `0x1800163b4`
- `ntdll!RtlAllocateHeap` at `0x18001513f`
- `ntdll!RtlAllocateHeap` at `0x18001513f`
- `ntdll!RtlInitUnicodeString` at `0x180016338`
- `ntdll!RtlInitUnicodeString` at `0x180016338`
- `ntdll!LdrOpenImageFileOptionsKey` at `0x18001634e`
- `ntdll!LdrOpenImageFileOptionsKey` at `0x18001634e`
- `ntdll!RtlExpandEnvironmentStrings` at `0x180015618`
- `ntdll!RtlExpandEnvironmentStrings` at `0x180015685`
- `ntdll!RtlExpandEnvironmentStrings` at `0x180015618`
- `ntdll!RtlExpandEnvironmentStrings` at `0x180015685`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800165b3`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800165b3`
- `ntdll!RtlDestroyEnvironment` at `0x1800158d3`
- `ntdll!RtlDestroyEnvironment` at `0x1800158d3`
- `ntdll!RtlQueryEnvironmentVariable` at `0x1800154d8`
- `ntdll!RtlQueryEnvironmentVariable` at `0x1800154d8`
- `ntdll!RtlCreateEnvironmentEx` at `0x1800158ea`
- `ntdll!RtlCreateEnvironmentEx` at `0x1800158ea`
- `ntdll!RtlSetEnvironmentVar` at `0x180015465`
- `ntdll!RtlSetEnvironmentVar` at `0x180015509`
- `ntdll!RtlSetEnvironmentVar` at `0x180015465`
- `ntdll!RtlSetEnvironmentVar` at `0x180015509`
- `ntdll!NtQueryInformationProcess` at `0x1800161cf`
- `ntdll!NtQueryInformationProcess` at `0x18001630f`
- `ntdll!NtQueryInformationProcess` at `0x1800161cf`
- `ntdll!NtQueryInformationProcess` at `0x18001630f`
- `ntdll!NtDuplicateToken` at `0x180014f0e`
- `ntdll!NtDuplicateToken` at `0x180014f0e`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180014f20`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180015477`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x1800155a8`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18001569b`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180015905`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x1800163d8`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180016497`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x1800164f0`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18001657f`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180014f20`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180015477`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x1800155a8`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18001569b`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180015905`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x1800163d8`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180016497`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x1800164f0`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18001657f`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800165f1`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800165f1`
- `USERENV!CreateEnvironmentBlock` at `0x1800150ab`
- `USERENV!CreateEnvironmentBlock` at `0x1800150ab`
- `USERENV!UnloadUserProfile` at `0x180016686`
- `USERENV!UnloadUserProfile` at `0x180016686`
- `USERENV!DestroyEnvironmentBlock` at `0x180015183`
- `USERENV!DestroyEnvironmentBlock` at `0x18001666d`
- `USERENV!DestroyEnvironmentBlock` at `0x180015183`
- `USERENV!DestroyEnvironmentBlock` at `0x18001666d`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!MonitorFromPoint` at `0x180015c90`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!MonitorFromPoint` at `0x180015c90`
- `ext-ms-win-appcompat-apphelp-l1-1-1!__imp_SdbGetKnownSafeLayers` at `0x1800152c0`
- `ext-ms-win-appcompat-apphelp-l1-1-1!__imp_SdbGetKnownSafeLayers` at `0x1800152c0`

## string_xrefs

- `0x18001589b`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x180015a01`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x180014f50`: `EnableSecureUIAPaths`
- `0x180015455`: `__COMPAT_LAYER`
- `0x18001628f`: `\InstallShield\setup.exe`

## pseudocode

```c
__int64 __fastcall AiLaunchProcess(
        void *a1,
        void *a2,
        char *a3,
        DWORD a4,
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
  DWORD v17; // edi
  struct _APPINFO_STARTUPINFO *v18; // rsi
  HANDLE v19; // r12
  DWORD v20; // r15d
  __int64 v21; // rbx
  int v22; // eax
  unsigned __int16 *v23; // r14
  char IsEnabled; // al
  unsigned int v25; // edx
  DWORD v26; // eax
  DWORD v27; // ecx
  DWORD v28; // edi
  const void *v29; // r15
  unsigned int i; // r8d
  int j; // edx
  __int64 v32; // rbx
  unsigned int v33; // esi
  __int64 v34; // rax
  unsigned __int64 v35; // rax
  char *Heap; // rax
  char *v37; // rdi
  size_t v38; // rbx
  LPCWSTR v39; // rsi
  HANDLE CurrentProcess; // rax
  HANDLE v41; // rdi
  void *v42; // rbx
  HANDLE v43; // rax
  int v44; // eax
  int v45; // r8d
  _QWORD *v46; // rcx
  char v47; // al
  int v48; // r8d
  DWORD LastError; // eax
  const unsigned __int16 *v50; // r8
  __int64 v51; // rax
  NTSTATUS v52; // eax
  wchar_t **v53; // rsi
  __int64 v54; // r14
  wchar_t *v55; // rdx
  __int64 v56; // rbx
  int v57; // edi
  int v58; // r8d
  int v59; // eax
  NTSTATUS v60; // ebx
  NTSTATUS v61; // ecx
  __int64 v62; // rsi
  HLOCAL v63; // r14
  char *v64; // rdx
  __int64 v65; // rax
  __int64 v66; // rax
  bool v67; // zf
  NTSTATUS v68; // eax
  __int64 v69; // rdi
  HANDLE *p_hSourceHandle; // r9
  __int64 v71; // rax
  int v72; // eax
  int LastErrorMsg; // edi
  unsigned __int64 v74; // r9
  __int64 v75; // rdx
  signed __int64 v76; // r8
  _WORD *v77; // rcx
  __int64 v78; // rdx
  __int16 v79; // ax
  _WORD *v80; // rax
  __int64 v81; // rcx
  struct _PROC_THREAD_ATTRIBUTE_LIST *v82; // rax
  const WCHAR *lpCurrentDirectory; // rsi
  DWORD FileAttributesW; // eax
  _DWORD *v85; // rcx
  __int64 v87; // r10
  __int64 v88; // rax
  __int64 v89; // rax
  char v90; // r12
  LPWSTR v91; // rdi
  const WCHAR *v92; // r14
  __m128i si128; // xmm1
  HANDLE hProcess; // rsi
  NTSTATUS InformationProcess; // eax
  HANDLE *v96; // rdi
  PHANDLE v97; // r14
  ULONG v98; // eax
  ACCESS_MASK v99; // edi
  int v100; // eax
  ULONG v101; // eax
  HANDLE v102; // rbx
  HLOCAL v103; // rax
  _QWORD *v104; // rdi
  int v105; // eax
  _QWORD *v106; // rax
  int TokenType; // [rsp+20h] [rbp-E0h]
  const char *TokenTypea; // [rsp+20h] [rbp-E0h]
  unsigned __int16 *v110; // [rsp+60h] [rbp-A0h]
  DWORD v112; // [rsp+70h] [rbp-90h] BYREF
  DWORD v113; // [rsp+74h] [rbp-8Ch] BYREF
  LPVOID Environment; // [rsp+78h] [rbp-88h] BYREF
  HANDLE hToken; // [rsp+80h] [rbp-80h] BYREF
  ULONG Value; // [rsp+88h] [rbp-78h] BYREF
  unsigned int v117; // [rsp+8Ch] [rbp-74h] BYREF
  void *NewKeyHandle; // [rsp+90h] [rbp-70h] BYREF
  WINBOOL v119; // [rsp+98h] [rbp-68h] BYREF
  HANDLE hSourceHandle; // [rsp+A0h] [rbp-60h] BYREF
  HLOCAL hMem; // [rsp+A8h] [rbp-58h] BYREF
  int pvData; // [rsp+B0h] [rbp-50h] BYREF
  int v123; // [rsp+B4h] [rbp-4Ch] BYREF
  int v124; // [rsp+B8h] [rbp-48h] BYREF
  WINBOOL fPending; // [rsp+BCh] [rbp-44h] BYREF
  LPVOID Context; // [rsp+C0h] [rbp-40h] BYREF
  LPCWSTR lpFileName; // [rsp+C8h] [rbp-38h] BYREF
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+D0h] [rbp-30h] BYREF
  HANDLE hProfile; // [rsp+E8h] [rbp-18h] BYREF
  DWORD v130; // [rsp+F0h] [rbp-10h] BYREF
  int v131; // [rsp+F4h] [rbp-Ch] BYREF
  UINT32 applicationUserModelIdLength; // [rsp+F8h] [rbp-8h] BYREF
  __int64 v133; // [rsp+100h] [rbp+0h] BYREF
  HANDLE TargetHandle; // [rsp+108h] [rbp+8h] BYREF
  __int64 v135; // [rsp+110h] [rbp+10h] BYREF
  char *v136; // [rsp+118h] [rbp+18h] BYREF
  DWORD pcbData; // [rsp+120h] [rbp+20h] BYREF
  HANDLE hObject[2]; // [rsp+128h] [rbp+28h] BYREF
  LPCWSTR lpApplicationName; // [rsp+138h] [rbp+38h]
  PHANDLE p_hProcess; // [rsp+140h] [rbp+40h]
  __int64 v141; // [rsp+148h] [rbp+48h] BYREF
  void *v142; // [rsp+150h] [rbp+50h] BYREF
  LPWSTR lpCommandLine[2]; // [rsp+158h] [rbp+58h] BYREF
  ULONG_PTR Size; // [rsp+168h] [rbp+68h] BYREF
  LPWSTR FilePart; // [rsp+170h] [rbp+70h] BYREF
  unsigned __int64 v146; // [rsp+178h] [rbp+78h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+180h] [rbp+80h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+190h] [rbp+90h] BYREF
  LPPROC_THREAD_ATTRIBUTE_LIST lpAttributeList; // [rsp+1F8h] [rbp+F8h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+200h] [rbp+100h] BYREF
  __int128 v151; // [rsp+230h] [rbp+130h] BYREF
  int v152; // [rsp+240h] [rbp+140h] BYREF
  _BYTE v153[284]; // [rsp+244h] [rbp+144h] BYREF
  int v154; // [rsp+360h] [rbp+260h] BYREF
  _BYTE v155[524]; // [rsp+364h] [rbp+264h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+570h] [rbp+470h] BYREF
  void *v157; // [rsp+580h] [rbp+480h]
  int v158; // [rsp+588h] [rbp+488h]
  int v159; // [rsp+58Ch] [rbp+48Ch]
  _WORD *v160; // [rsp+590h] [rbp+490h]
  int v161; // [rsp+598h] [rbp+498h]
  int v162; // [rsp+59Ch] [rbp+49Ch]
  WCHAR *v163; // [rsp+5A0h] [rbp+4A0h]
  int v164; // [rsp+5A8h] [rbp+4A8h]
  int v165; // [rsp+5ACh] [rbp+4ACh]
  unsigned __int64 *v166; // [rsp+5B0h] [rbp+4B0h]
  __int64 v167; // [rsp+5B8h] [rbp+4B8h]
  int v168; // [rsp+5C0h] [rbp+4C0h] BYREF
  char v169[332]; // [rsp+5C4h] [rbp+4C4h] BYREF
  WCHAR applicationUserModelId[136]; // [rsp+710h] [rbp+610h] BYREF
  wchar_t Destination[264]; // [rsp+820h] [rbp+720h] BYREF
  _WORD v172[232]; // [rsp+A30h] [rbp+930h] BYREF
  _BYTE v173[528]; // [rsp+C00h] [rbp+B00h] BYREF
  WCHAR Buffer[264]; // [rsp+E10h] [rbp+D10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1068h] [rbp+F68h]

  v17 = 0;
  v18 = a10;
  v19 = a2;
  v20 = a4;
  lpApplicationName = a5;
  LODWORD(v21) = 0;
  lpCommandLine[0] = a6;
  lpFileName = a8;
  Context = a9;
  v142 = a14;
  p_hProcess = &a17->hProcess;
  v136 = a3;
  hSourceHandle = a1;
  lpAttributeList = 0;
  v112 = a4;
  NewKeyHandle = a10;
  Value = 0;
  v110 = 0;
  TargetHandle = 0;
  hToken = 0;
  hProfile = 0;
  Environment = 0;
  memset(&StartupInfo, 0, sizeof(StartupInfo));
  v168 = 0;
  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  memset_0(v169, 0, sizeof(v169));
  Size = 336;
  v135 = 0;
  v123 = 4;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  v151 = 0;
  memset_0(&v154, 0, 0x20Cu);
  memset_0(&v152, 0, 0x114u);
  if ( (v20 & 0x80u) != 0 )
  {
    hToken = v19;
  }
  else
  {
    ObjectAttributes.Length = 48;
    memset(&ObjectAttributes.RootDirectory, 0, 20);
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    v22 = NtDuplicateToken(v19, 0, &ObjectAttributes, 0, TokenPrimary, &hToken);
    if ( v22 < 0 )
    {
      LODWORD(v21) = RtlNtStatusToDosErrorNoTeb(v22);
      v23 = 0;
      goto LABEL_265;
    }
  }
  if ( (v20 & 4) == 0 )
    goto LABEL_16;
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
    || (v20 & 0x2000) != 0 )
  {
    v20 |= 0x400u;
    v112 = v20;
  }
  if ( (v20 & 0x400) == 0 )
  {
    Value |= 2u;
LABEL_16:
    v117 = a7;
    goto LABEL_17;
  }
  IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShadowAdmin>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_ShadowAdmin>::GetImpl'::`2'::impl);
  v25 = a7 & 0xFFFFFFFC;
  if ( !IsEnabled )
    v25 = a7;
  v117 = v25;
  LODWORD(v21) = LUASetUIAToken(hToken);
  if ( (_DWORD)v21 )
  {
    v23 = 0;
    goto LABEL_265;
  }
LABEL_17:
  if ( hSourceHandle )
  {
    LOBYTE(v17) = lpValue != 0;
    v17 += 2;
    if ( (a13 & 6) != 0 )
      ++v17;
  }
  v26 = v17 + 1;
  if ( (v20 & 0x1800000) == 0 )
    v26 = v17;
  v27 = v26 + 1;
  if ( (a13 & 0x408) == 0 )
    v27 = v26;
  v119 = a13 & 0x2000;
  v28 = v27 + 1;
  if ( (a13 & 0x2000) == 0 )
    v28 = v27;
  v113 = v28;
  if ( v28 && !InitializeProcThreadAttributeList((LPPROC_THREAD_ATTRIBUTE_LIST)&v168, v28, 0, &Size) )
    goto LABEL_28;
  if ( !hSourceHandle )
    goto LABEL_158;
  if ( (v20 & 1) != 0 )
  {
    LODWORD(v21) = AipLoadUserProfile(hToken, &hProfile);
    if ( (_DWORD)v21 )
      goto LABEL_263;
  }
  if ( !CreateEnvironmentBlock(&Environment, hToken, 0) )
    goto LABEL_28;
  if ( Src )
  {
    v29 = Environment;
    for ( i = 0; *((_WORD *)Environment + i) || *((_WORD *)Environment + i + 1); ++i )
      ;
    for ( j = 0; Src[j] || Src[j + 1]; ++j )
      ;
    v32 = i + 1;
    v33 = j + 2;
    v34 = (unsigned int)(j + 2 + v32);
    if ( (unsigned int)v34 < (unsigned int)v32 || (v35 = 2 * v34, v35 > 0xFFFFFFFF) )
    {
      LODWORD(v21) = 534;
      goto LABEL_263;
    }
    Heap = (char *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, (unsigned int)v35);
    v37 = Heap;
    if ( !Heap )
    {
      LODWORD(v21) = 8;
      goto LABEL_263;
    }
    v38 = 2 * v32;
    memcpy_0(Heap, v29, v38);
    memcpy_0(&v37[v38], Src, 2LL * v33);
    DestroyEnvironmentBlock(Environment);
    Environment = v37;
  }
  v39 = lpApplicationName;
  LODWORD(v21) = AipCheckForAppPathsKey((wchar_t *)lpApplicationName, &Environment);
  if ( (_DWORD)v21 )
    goto LABEL_263;
  v110 = (unsigned __int16 *)LocalAlloc(0x40u, 0x218u);
  v23 = v110;
  if ( v110 )
  {
    if ( !(unsigned __int8)IsSdbGetKnownSafeLayersPresent() )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, &WPP_e8c8bde4cfdd31ad7ca53050940b7a3e_Traceguids);
      goto LABEL_74;
    }
    CurrentProcess = GetCurrentProcess();
    v41 = hSourceHandle;
    v42 = CurrentProcess;
    v43 = GetCurrentProcess();
    if ( !DuplicateHandle(v43, v41, v42, &TargetHandle, 0x410u, 0, 0) )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        LastError = GetLastError();
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, &WPP_e8c8bde4cfdd31ad7ca53050940b7a3e_Traceguids, LastError);
      }
      goto LABEL_74;
    }
    v44 = BaseReadAppCompatDataForProcess(TargetHandle, &v135, 0);
    if ( v44 )
    {
      v46 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      {
LABEL_61:
        if ( (unsigned int)SdbGetKnownSafeLayers(v135, 256, v110) )
        {
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_SS(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              16,
              (unsigned int)&WPP_e8c8bde4cfdd31ad7ca53050940b7a3e_Traceguids,
              (_DWORD)v39,
              (__int64)v110);
        }
        else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
               && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v47 = GetLastError();
          WPP_SF_SD(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, v48, (_DWORD)v39, v47);
        }
LABEL_74:
        if ( (v112 & 2) != 0 && !wcsstr(v110, L"VistaSetUp") )
        {
          v50 = L" VistaSetUp";
          if ( !*v110 )
            v50 = L"VistaSetUp";
          if ( StringCchCatW(v110, 0x10Cu, v50) < 0
            && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, &WPP_e8c8bde4cfdd31ad7ca53050940b7a3e_Traceguids);
          }
        }
        if ( *v110 )
        {
          v51 = -1;
          do
            ++v51;
          while ( v110[v51] );
          LODWORD(v21) = 0;
          v52 = RtlSetEnvironmentVar(&Environment, L"__COMPAT_LAYER", 14, v110, v51);
          if ( v52 < 0 )
            LODWORD(v21) = RtlNtStatusToDosErrorNoTeb(v52);
          if ( (_DWORD)v21 )
            goto LABEL_264;
        }
        v141 = 0;
        v53 = off_180044000;
        v54 = 0;
        while ( 1 )
        {
          v55 = *v53;
          v56 = -1;
          do
            ++v56;
          while ( v55[v56] );
          v57 = RtlQueryEnvironmentVariable(0, v55, v56, v173, 260, &v141);
          if ( v57 < 0 )
            break;
          v59 = RtlSetEnvironmentVar(&Environment, *v53, v56, v173, v141);
          v60 = v59;
          if ( v59 < 0 )
          {
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              WPP_SF_SSD(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                21,
                (unsigned int)&WPP_e8c8bde4cfdd31ad7ca53050940b7a3e_Traceguids,
                (unsigned int)off_180044000[v54],
                (__int64)v173,
                v59);
            v61 = v60;
            goto LABEL_103;
          }
          v54 = (unsigned int)(v54 + 1);
          ++v53;
          if ( (unsigned int)v54 >= 3 )
            goto LABEL_104;
        }
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_SD(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, v58, (unsigned int)off_180044000[v54], v57);
        v61 = v57;
LABEL_103:
        LODWORD(v21) = RtlNtStatusToDosErrorNoTeb(v61);
        if ( (_DWORD)v21 )
          goto LABEL_263;
LABEL_104:
        LODWORD(v21) = 0;
        v133 = 0;
        v62 = 0;
        v63 = 0;
        v64 = (char *)Environment;
        do
        {
          v65 = -1;
          do
            ++v65;
          while ( *(_WORD *)&v64[2 * v65] );
          v66 = v65 + 1;
          v62 += v66;
          v67 = *(_WORD *)&v64[2 * v66] == 0;
          v64 += 2 * v66;
        }
        while ( !v67 );
        v68 = RtlExpandEnvironmentStrings(Environment, Environment, v62 + 1, 0, 0, &v133);
        if ( v68 != -1073741789 )
          goto LABEL_112;
        v69 = v133;
        v63 = LocalAlloc(0x40u, 2 * v133);
        if ( !v63 )
        {
          LocalFree(0);
          LODWORD(v21) = 8;
          goto LABEL_263;
        }
        v68 = RtlExpandEnvironmentStrings(Environment, Environment, v62 + 1, v63, v69, &v133);
        if ( v68 < 0
          || (RtlDestroyEnvironment((PWSTR)Environment), v68 = RtlCreateEnvironmentEx(v63, &Environment, 0), v68 < 0) )
        {
LABEL_112:
          LODWORD(v21) = RtlNtStatusToDosErrorNoTeb(v68);
        }
        LocalFree(v63);
        if ( (_DWORD)v21 )
          goto LABEL_263;
        v20 = v112;
        if ( (v112 & 0x401) != 0 )
        {
          LODWORD(v21) = AiSetMandatoryPolicy(hToken);
          if ( (_DWORD)v21 )
            goto LABEL_263;
        }
        p_hSourceHandle = &v142;
        if ( !v142 )
          p_hSourceHandle = &hSourceHandle;
        if ( !UpdateProcThreadAttribute((LPPROC_THREAD_ATTRIBUTE_LIST)&v168, 0, 0x20000u, p_hSourceHandle, 8u, 0, 0) )
          goto LABEL_28;
        if ( !UpdateProcThreadAttribute((LPPROC_THREAD_ATTRIBUTE_LIST)&v168, 0, 0x60001u, &Value, 4u, 0, 0) )
          goto LABEL_28;
        if ( lpValue )
        {
          v71 = -1;
          do
            ++v71;
          while ( lpValue[v71] );
          if ( !UpdateProcThreadAttribute((LPPROC_THREAD_ATTRIBUTE_LIST)&v168, 0, 0x20008u, lpValue, 2 * v71, 0, 0) )
            goto LABEL_28;
        }
        if ( (a13 & 6) != 0 )
        {
          if ( (a13 & 4) != 0 )
            v123 = 2;
          if ( !UpdateProcThreadAttribute((LPPROC_THREAD_ATTRIBUTE_LIST)&v168, 0, 0x20012u, &v123, 4u, 0, 0) )
            goto LABEL_28;
        }
        if ( (a13 & 8) != 0 )
        {
          memset_0(v155, 0, 0x208u);
          v154 = 8;
        }
        else
        {
          if ( (a13 & 0x400) == 0 )
          {
LABEL_131:
            if ( v119 )
            {
              hMem = 0;
              v72 = CreateBnoIsolationPrefix(hToken, &hMem);
              LastErrorMsg = v72;
              if ( v72 < 0 )
              {
                v74 = (unsigned int)v72;
                v75 = 2452;
                goto LABEL_134;
              }
              v76 = (_BYTE *)hMem - v153;
              v77 = v153;
              v78 = 136;
              do
              {
                if ( v78 == -2147483510 )
                  break;
                v79 = *(_WORD *)((char *)v77 + v76);
                if ( !v79 )
                  break;
                *v77++ = v79;
                --v78;
              }
              while ( v78 );
              v80 = v77 - 1;
              LastErrorMsg = -2147024774;
              if ( v78 )
              {
                v80 = v77;
                LastErrorMsg = 0;
              }
              *v80 = 0;
              if ( !v78 )
              {
                v74 = (unsigned int)LastErrorMsg;
                v75 = 2454;
LABEL_134:
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)v75,
                  (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
                  (const char *)v74,
                  TokenType);
                if ( hMem )
                {
                  LocalFree(hMem);
                  LODWORD(v21) = WIN32_FROM_HRESULT(LastErrorMsg);
                  goto LABEL_263;
                }
LABEL_153:
                LODWORD(v21) = WIN32_FROM_HRESULT(LastErrorMsg);
                goto LABEL_263;
              }
              v152 = 1;
              if ( UpdateProcThreadAttribute((LPPROC_THREAD_ATTRIBUTE_LIST)&v168, 0, 0x20013u, &v152, 0x114u, 0, 0) )
              {
                if ( hMem )
                  LocalFree(hMem);
              }
              else
              {
                LastErrorMsg = wil::details::in1diag3::Return_GetLastErrorMsg(
                                 retaddr,
                                 (void *)0x999,
                                 (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
                                 "Failed to add bnoIsolationParameter attribute",
                                 TokenTypea);
                if ( hMem )
                  LocalFree(hMem);
                if ( LastErrorMsg < 0 )
                  goto LABEL_153;
              }
              v18 = (struct _APPINFO_STARTUPINFO *)NewKeyHandle;
              v28 = v113;
            }
            else
            {
              v18 = (struct _APPINFO_STARTUPINFO *)NewKeyHandle;
              v28 = v113;
            }
LABEL_158:
            if ( (v20 & 0x800000) != 0 )
              *(_QWORD *)&v151 = v151 | 0x1000000000000000LL;
            if ( (v20 & 0x1000000) != 0 )
            {
              if ( (v20 & 0x80u) != 0 )
              {
                v81 = 4144;
                *((_QWORD *)&v151 + 1) = 4144;
              }
              else
              {
                v124 = 0;
                v112 = 0;
                v113 = 0;
                v130 = 4;
                if ( RegGetValueW(
                       HKEY_LOCAL_MACHINE,
                       L"Software\\Microsoft\\Windows\\CurrentVersion\\Policies\\System",
                       L"EnableAutoApproveIntegrityContinuity",
                       0x10u,
                       0,
                       &v113,
                       &v130)
                  || v113 )
                {
                  v112 = 4;
                  if ( RegGetValueW(
                         HKEY_LOCAL_MACHINE,
                         L"Software\\Microsoft\\Windows\\CurrentVersion\\Policies\\System",
                         L"AutoApproveMitigationPolicy",
                         0x10u,
                         0,
                         &v124,
                         &v112) )
                  {
                    v81 = 4112;
                    *((_QWORD *)&v151 + 1) = 4112;
                  }
                  else
                  {
                    v81 = 16LL * (v124 & 1);
                    if ( (v124 & 2) != 0 )
                      v81 = 48;
                    if ( (v124 & 4) != 0 )
                      v81 |= 0x1000uLL;
                    *((_QWORD *)&v151 + 1) = v81;
                  }
                }
                else
                {
                  v81 = 0;
                  *((_QWORD *)&v151 + 1) = 0;
                }
              }
            }
            else
            {
              v81 = *((_QWORD *)&v151 + 1);
            }
            if ( !(_QWORD)v151 && !v81
              || UpdateProcThreadAttribute((LPPROC_THREAD_ATTRIBUTE_LIST)&v168, 0, 0x20007u, &v151, 0x10u, 0, 0) )
            {
              StartupInfo.cb = 112;
              v82 = (struct _PROC_THREAD_ATTRIBUTE_LIST *)&v168;
              if ( !v28 )
                v82 = lpAttributeList;
              lpAttributeList = v82;
              StartupInfo.lpDesktop = (LPWSTR)Context;
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
                v67 = (*((_DWORD *)v18 + 9) & 0x400) == 0;
                StartupInfo.dwFlags = *((_DWORD *)v18 + 9) & 0xFFFFFCFF;
                if ( !v67 )
                  StartupInfo.hStdOutput = MonitorFromPoint(*(POINT *)((char *)v18 + 44), 2u);
              }
              else
              {
                StartupInfo.dwFlags = 1;
                StartupInfo.wShowWindow = 1;
              }
              if ( ImpersonateLoggedOnUser(hToken) )
              {
                if ( (v20 & 0x4004) == 0x4000
                  || (lpCurrentDirectory = lpFileName, FilePart = 0, lpFileName)
                  && (GetFullPathNameW(lpFileName, 0x104u, Buffer, &FilePart) - 1 > 0x103
                   || (FileAttributesW = GetFileAttributesW(Buffer), FileAttributesW == -1)
                   || (FileAttributesW & 0x10) == 0) )
                {
                  lpCurrentDirectory = 0;
                }
                if ( a15 )
                {
                  lpFileName = 0;
                  fPending = 0;
                  if ( InitOnceBeginInitialize(
                         &`AAMTraceProvider::Instance'::`2'::wrapper,
                         0,
                         &fPending,
                         (LPVOID *)&lpFileName)
                    && fPending )
                  {
                    lpFileName = (LPCWSTR)&qword_18005BDD0;
                    qword_18005BDD8 = 0;
                    byte_18005BDE0 = 0;
                    dword_18005BDE4 = 0;
                    qword_18005BDD0 = (__int64)&wil::TraceLoggingProvider::`vftable';
                    CallbackContext = &`AAMTraceProvider::StaticHandle::StaticHandle'::`2'::__hInner;
                    atexit(_lambda_7e8ef9e9b596109f338594047241dcdf_::_lambda_invoker_cdecl_);
                    qword_18005BDD8 = (__int64)CallbackContext;
                    byte_18005BDE0 = 1;
                    TraceLoggingRegisterEx_EventRegister_EventSetInformation(CallbackContext);
                    dword_18005BDE4 = 1;
                    (*(void (__fastcall **)(__int64 *))(qword_18005BDD0 + 8))(&qword_18005BDD0);
                    InitOnceComplete(&`AAMTraceProvider::Instance'::`2'::wrapper, 0, &qword_18005BDD0);
                  }
                  v85 = (_DWORD *)*((_QWORD *)lpFileName + 1);
                  if ( v85 && *v85 )
                  {
                    memset_0(v172, 0, sizeof(v172));
                    v131 = 464;
                    if ( (int)PsmGetKeyFromToken(hToken, v172, &v131, 0) < 0 )
                      v172[0] = 0;
                    applicationUserModelIdLength = 131;
                    if ( GetApplicationUserModelIdFromToken(
                           hToken,
                           &applicationUserModelIdLength,
                           applicationUserModelId) )
                    {
                      applicationUserModelId[0] = 0;
                    }
                    Context = 0;
                    v119 = 0;
                    if ( InitOnceBeginInitialize(&`AAMTraceProvider::Instance'::`2'::wrapper, 0, &v119, &Context)
                      && v119 )
                    {
                      Context = &qword_18005BDD0;
                      qword_18005BDD8 = 0;
                      byte_18005BDE0 = 0;
                      dword_18005BDE4 = 0;
                      qword_18005BDD0 = (__int64)&wil::TraceLoggingProvider::`vftable';
                      CallbackContext = &`AAMTraceProvider::StaticHandle::StaticHandle'::`2'::__hInner;
                      atexit(_lambda_7e8ef9e9b596109f338594047241dcdf_::_lambda_invoker_cdecl_);
                      qword_18005BDD8 = (__int64)CallbackContext;
                      byte_18005BDE0 = 1;
                      TraceLoggingRegisterEx_EventRegister_EventSetInformation(CallbackContext);
                      dword_18005BDE4 = 1;
                      (*(void (__fastcall **)(__int64 *))(qword_18005BDD0 + 8))(&qword_18005BDD0);
                      InitOnceComplete(&`AAMTraceProvider::Instance'::`2'::wrapper, 0, &qword_18005BDD0);
                    }
                    v87 = *((_QWORD *)Context + 1);
                    if ( *(_DWORD *)v87 > 5u
                      && (*(_QWORD *)(v87 + 16) & 0x400000000000LL) != 0
                      && (*(_QWORD *)(v87 + 24) & 0x400000000000LL) == *(_QWORD *)(v87 + 24) )
                    {
                      v146 = a15;
                      v166 = &v146;
                      v88 = -1;
                      v167 = 8;
                      do
                        v67 = applicationUserModelId[++v88] == 0;
                      while ( !v67 );
                      v165 = 0;
                      v164 = 2 * v88 + 2;
                      v163 = applicationUserModelId;
                      v89 = -1;
                      do
                        v67 = v172[++v89] == 0;
                      while ( !v67 );
                      EventDescriptor.Keyword = 0x400000000000LL;
                      v161 = 2 * v89 + 2;
                      *(_DWORD *)&EventDescriptor.Level = 5;
                      UserData.Ptr = *(_QWORD *)(v87 + 8);
                      v160 = v172;
                      v162 = 0;
                      *(_DWORD *)&EventDescriptor.Id = 184549376;
                      UserData.Size = *(unsigned __int16 *)UserData.Ptr;
                      UserData.Reserved = 2;
                      v157 = &unk_180051087;
                      v158 = 62;
                      v159 = 1;
                      LODWORD(NewKeyHandle) = (unsigned int)&TraceLoggingMetadataEnd
                                            - (unsigned int)&TraceLoggingMetadata;
                      EventWriteTransfer(*(_QWORD *)(v87 + 32), &EventDescriptor, 0, 0, 5u, &UserData);
                    }
                  }
                }
                v90 = v117;
                v91 = lpCommandLine[0];
                v92 = lpApplicationName;
                if ( !CreateProcessAsUserW(
                        hToken,
                        lpApplicationName,
                        lpCommandLine[0],
                        0,
                        0,
                        0,
                        v117 | 0x80004,
                        Environment,
                        lpCurrentDirectory,
                        &StartupInfo,
                        &ProcessInformation) )
                  LODWORD(v21) = GetLastError();
                RevertToSelf();
                if ( (_DWORD)v21 )
                  goto LABEL_263;
                si128 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
                hProcess = ProcessInformation.hProcess;
                if ( !v92 )
                  v92 = v91;
                v21 = 0;
                NewKeyHandle = 0;
                v117 = 0;
                *(_OWORD *)lpCommandLine = 0;
                *(__m128i *)hObject = si128;
                if ( (unsigned __int64)(v136 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
                {
                  InformationProcess = NtQueryInformationProcess(
                                         ProcessInformation.hProcess,
                                         ProcessImageFileMapping,
                                         &v136,
                                         8u,
                                         0);
                  if ( InformationProcess == -1073741823 )
                  {
                    memset_0(Destination, 0, 0x208u);
                    wcscpy_s(Destination, 0x104u, &g_wszWow64Dir);
                    wcscat_s(Destination, 0x104u, L"\\setup16.exe");
                    hObject[0] = CreateFileW(Destination, 0xA0000000, 5u, 0, 3u, 0x80u, 0);
                    wcscpy_s(Destination, 0x104u, &g_wszWow64Dir);
                    wcscat_s(Destination, 0x104u, L"\\InstallShield\\setup.exe");
                    hObject[1] = CreateFileW(Destination, 0xA0000000, 5u, 0, 3u, 0x80u, 0);
                    v96 = hObject;
                    while ( 1 )
                    {
                      if ( *v96 != (HANDLE)-1LL )
                      {
                        InformationProcess = NtQueryInformationProcess(
                                               hProcess,
                                               ProcessImageFileMapping,
                                               &hObject[v21],
                                               8u,
                                               0);
                        if ( InformationProcess != -1073741823 )
                          break;
                      }
                      v21 = (unsigned int)(v21 + 1);
                      ++v96;
                      if ( (unsigned int)v21 >= 2 )
                      {
                        RtlInitUnicodeString((PUNICODE_STRING)lpCommandLine, v92);
                        if ( LdrOpenImageFileOptionsKey((PUNICODE_STRING)lpCommandLine, 0, &NewKeyHandle) < 0 )
                          goto LABEL_231;
                        if ( LdrQueryImageFileKeyOption(NewKeyHandle, L"Debugger", 1u, 0, 0, 0) == -2147483643 )
                        {
                          LODWORD(v21) = 0;
                          goto LABEL_233;
                        }
                        if ( LdrQueryImageFileKeyOption(NewKeyHandle, L"AppExecutionAliasRedirect", 4u, &v117, 4u, 0) >= 0
                          && v117 == 1 )
                        {
                          LODWORD(v21) = 0;
                        }
                        else
                        {
LABEL_231:
                          LODWORD(v21) = 5;
                        }
                        goto LABEL_233;
                      }
                    }
                  }
                  LODWORD(v21) = RtlNtStatusToDosErrorNoTeb(InformationProcess);
LABEL_233:
                  if ( NewKeyHandle )
                  {
                    NtClose(NewKeyHandle);
                    NewKeyHandle = 0;
                  }
                }
                if ( hObject[0] != (HANDLE)-1LL )
                  CloseHandle(hObject[0]);
                if ( hObject[1] != (HANDLE)-1LL )
                  CloseHandle(hObject[1]);
                if ( (_DWORD)v21 )
                  goto LABEL_263;
                v97 = p_hProcess;
                if ( hSourceHandle )
                {
                  v98 = 0;
                  v99 = (v20 & 0x401) != 0 ? 0x20000100 : 0;
                  if ( (v20 & 0x401) == 0 )
                    v98 = 2;
                  Value = v98;
                  v100 = NtDuplicateObject(
                           (HANDLE)0xFFFFFFFFFFFFFFFFLL,
                           ProcessInformation.hProcess,
                           hSourceHandle,
                           p_hProcess,
                           (v20 & 0x401) != 0 ? 0x20000100 : 0,
                           0,
                           v98);
                  if ( v100 < 0
                    || ((v20 & 0x401) == 0 ? (v101 = Value) : (v101 = 0, v99 = 536870914, Value = 0),
                        v100 = NtDuplicateObject(
                                 (HANDLE)0xFFFFFFFFFFFFFFFFLL,
                                 ProcessInformation.hThread,
                                 hSourceHandle,
                                 v97 + 1,
                                 v99,
                                 0,
                                 v101),
                        v100 < 0) )
                  {
                    LODWORD(v21) = RtlNtStatusToDosErrorNoTeb(v100);
                    goto LABEL_263;
                  }
                  if ( (v20 & 1) != 0 )
                  {
                    v102 = hToken;
                    _InterlockedIncrement(&g_ulProfileReferences);
                    v103 = LocalAlloc(0x40u, 0x28u);
                    v104 = v103;
                    if ( !v103 )
                    {
                      LODWORD(v21) = 8;
LABEL_254:
                      _InterlockedDecrement(&g_ulProfileReferences);
                      LocalFree(v104);
                      goto LABEL_263;
                    }
                    *((_DWORD *)v103 + 4) = a11;
                    *((_QWORD *)v103 + 4) = hProfile;
                    v105 = NtDuplicateObject(
                             (HANDLE)0xFFFFFFFFFFFFFFFFLL,
                             v102,
                             (HANDLE)0xFFFFFFFFFFFFFFFFLL,
                             (PHANDLE)v103 + 3,
                             0,
                             0,
                             2u);
                    if ( v105 >= 0 )
                    {
                      RtlAcquireSRWLockExclusive(&g_ProfileListLock);
                      v106 = (_QWORD *)qword_18005AEC8;
                      if ( *(HLOCAL **)qword_18005AEC8 != &g_ProfileList )
                        __fastfail(3u);
                      *v104 = &g_ProfileList;
                      v104[1] = v106;
                      *v106 = v104;
                      qword_18005AEC8 = (__int64)v104;
                      RtlReleaseSRWLockExclusive(&g_ProfileListLock);
                      LODWORD(v21) = 0;
                    }
                    else
                    {
                      LODWORD(v21) = RtlNtStatusToDosErrorNoTeb(v105);
                      if ( (_DWORD)v21 )
                        goto LABEL_254;
                    }
                    hProfile = 0;
                  }
                  if ( (v90 & 4) == 0 )
                    ResumeThread(ProcessInformation.hThread);
                }
                else
                {
                  *p_hProcess = ProcessInformation.hProcess;
                  v97[1] = ProcessInformation.hThread;
                  ProcessInformation.hProcess = 0;
                  ProcessInformation.hThread = 0;
                }
                *((_DWORD *)v97 + 4) = ProcessInformation.dwProcessId;
                *((_DWORD *)v97 + 5) = ProcessInformation.dwThreadId;
                goto LABEL_263;
              }
            }
LABEL_28:
            LODWORD(v21) = GetLastError();
LABEL_263:
            v23 = v110;
            goto LABEL_264;
          }
          memset_0(v155, 0, 0x208u);
          v154 = 256;
        }
        if ( !UpdateProcThreadAttribute((LPPROC_THREAD_ATTRIBUTE_LIST)&v168, 0, 0x20011u, &v154, 0x20Cu, 0, 0) )
          goto LABEL_28;
        goto LABEL_131;
      }
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      {
LABEL_58:
        if ( v46 != &WPP_GLOBAL_Control && (*((_BYTE *)v46 + 28) & 1) != 0 )
          WPP_SF_S(v46[2], 14, &WPP_e8c8bde4cfdd31ad7ca53050940b7a3e_Traceguids, v39);
        goto LABEL_61;
      }
      WPP_SF_SD(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, v45, (_DWORD)v39, v44);
    }
    v46 = WPP_GLOBAL_Control;
    goto LABEL_58;
  }
  LODWORD(v21) = 8;
LABEL_264:
  v19 = a2;
LABEL_265:
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
    if ( (_DWORD)v21 )
      TerminateProcess(ProcessInformation.hProcess, v21);
    CloseHandle(ProcessInformation.hProcess);
  }
  if ( TargetHandle )
    CloseHandle(TargetHandle);
  if ( v135 )
    BaseFreeAppCompatDataForProcess();
  if ( v23 )
    LocalFree(v23);
  if ( hToken && hToken != v19 )
    NtClose(hToken);
  return (unsigned int)v21;
}

```

## disassembly

```asm
0x180014d40  mov     [rsp-8+arg_18], rbx
0x180014d45  push    rbp
0x180014d46  push    rsi
0x180014d47  push    rdi
0x180014d48  push    r12
0x180014d4a  push    r13
0x180014d4c  push    r14
0x180014d4e  push    r15
0x180014d50  lea     rbp, [rsp-0F30h]
0x180014d58  mov     eax, 1030h
0x180014d5d  call    _alloca_probe
0x180014d62  sub     rsp, rax
0x180014d65  mov     rax, cs:__security_cookie
0x180014d6c  xor     rax, rsp
0x180014d6f  mov     [rbp+0F60h+var_40], rax
0x180014d76  mov     rax, [rbp+0F60h+arg_20]
0x180014d7d  xor     edi, edi
0x180014d7f  mov     rsi, [rbp+0F60h+arg_48]
0x180014d86  xorps   xmm0, xmm0
0x180014d89  mov     r13, [rbp+0F60h+lpValue]
0x180014d90  mov     r12, rdx
0x180014d93  mov     r14, [rbp+0F60h+Src]
0x180014d9a  mov     r15d, r9d
0x180014d9d  mov     [rbp+0F60h+lpApplicationName], rax
0x180014da1  mov     ebx, edi
0x180014da3  mov     rax, [rbp+0F60h+arg_28]
0x180014daa  mov     [rbp+0F60h+lpCommandLine], rax
0x180014dae  mov     rax, [rbp+0F60h+arg_38]
0x180014db5  mov     [rbp+0F60h+lpFileName], rax
0x180014db9  mov     rax, [rbp+0F60h+arg_40]
0x180014dc0  mov     [rbp+0F60h+Context], rax
0x180014dc4  mov     rax, [rbp+0F60h+arg_68]
0x180014dcb  mov     [rbp+0F60h+var_F10], rax
0x180014dcf  mov     rax, [rbp+0F60h+arg_80]
0x180014dd6  mov     [rbp+0F60h+var_F20], rax
0x180014dda  xor     eax, eax
0x180014ddc  mov     [rbp+0F60h+var_F48], r8
0x180014de0  mov     r8d, 14Ch; Size
0x180014de6  mov     [rsp+1060h+var_FF8], rdx
0x180014deb  xor     edx, edx; Val
0x180014ded  mov     [rbp+0F60h+hSourceHandle], rcx
0x180014df1  lea     rcx, [rbp+0F60h+var_A9C]; void *
0x180014df8  mov     [rbp+0F60h+lpAttributeList], rax
0x180014dff  mov     qword ptr [rbp+0F60h+ProcessInformation.dwProcessId], rax
0x180014e03  mov     [rsp+1060h+var_FF0], r9d
0x180014e08  mov     [rbp+0F60h+NewKeyHandle], rsi
0x180014e0c  mov     [rbp+0F60h+Value], edi
0x180014e0f  mov     [rsp+1060h+var_1000], rdi
0x180014e14  mov     [rbp+0F60h+TargetHandle], rdi
0x180014e18  mov     [rbp+0F60h+hToken], rdi
0x180014e1c  mov     [rbp+0F60h+hProfile], rdi
0x180014e20  mov     [rsp+1060h+Environment], rdi
0x180014e25  mov     qword ptr [rbp+0F60h+StartupInfo.cb], rdi
0x180014e2c  movups  xmmword ptr [rbp+0F60h+StartupInfo.lpReserved], xmm0
0x180014e33  mov     [rbp+0F60h+var_AA0], edi
0x180014e39  movups  xmmword ptr [rbp+0F60h+StartupInfo.lpTitle], xmm0
0x180014e40  movups  xmmword ptr [rbp+0F60h+StartupInfo.dwXSize], xmm0
0x180014e47  movups  xmmword ptr [rbp+0F60h+StartupInfo.dwFillAttribute], xmm0
0x180014e4e  movups  xmmword ptr [rbp+0F60h+StartupInfo.lpReserved2], xmm0
0x180014e55  movups  xmmword ptr [rbp+0F60h+StartupInfo.hStdOutput], xmm0
0x180014e5c  movups  xmmword ptr [rbp+0F60h+ProcessInformation.hProcess], xmm0
0x180014e60  call    memset_0
0x180014e65  xorps   xmm0, xmm0
0x180014e68  mov     [rbp+0F60h+Size], 150h
0x180014e70  xor     edx, edx; Val
0x180014e72  mov     [rbp+0F60h+var_F50], rbx
0x180014e76  mov     r8d, 20Ch; Size
0x180014e7c  mov     [rbp+0F60h+var_FAC], 4
0x180014e83  lea     rcx, [rbp+0F60h+var_D00]; void *
0x180014e8a  movups  xmmword ptr [rbp+0F60h+ObjectAttributes.Length], xmm0
0x180014e91  movups  xmmword ptr [rbp+0F60h+ObjectAttributes.ObjectName], xmm0
0x180014e98  movups  xmmword ptr [rbp+0F60h+ObjectAttributes.SecurityDescriptor], xmm0
0x180014e9f  movups  [rbp+0F60h+var_E30], xmm0
0x180014ea6  call    memset_0
0x180014eab  xor     edx, edx; Val
0x180014ead  lea     rcx, [rbp+0F60h+var_E20]; void *
0x180014eb4  mov     r8d, 114h; Size
0x180014eba  call    memset_0
0x180014ebf  lea     eax, [rdi+30h]
0x180014ec2  test    r15b, r15b
0x180014ec5  js      short loc_180014F36
0x180014ec7  mov     [rbp+0F60h+ObjectAttributes.Length], eax
0x180014ecd  lea     r8, [rbp+0F60h+ObjectAttributes]; ObjectAttributes
0x180014ed4  xor     eax, eax
0x180014ed6  xorps   xmm0, xmm0
0x180014ed9  mov     [rbp+0F60h+ObjectAttributes.RootDirectory], rax
0x180014ee0  xor     r9d, r9d; EffectiveOnly
0x180014ee3  mov     [rbp+0F60h+ObjectAttributes.Attributes], eax
0x180014ee9  xor     edx, edx; DesiredAccess
0x180014eeb  mov     [rbp+0F60h+ObjectAttributes.ObjectName], rax
0x180014ef2  mov     rcx, r12; ExistingTokenHandle
0x180014ef5  lea     rax, [rbp+0F60h+hToken]
0x180014ef9  mov     [rsp+1060h+NewTokenHandle], rax; NewTokenHandle
0x180014efe  mov     [rsp+1060h+TokenType], 1; TokenType
0x180014f06  movdqu  xmmword ptr [rbp+0F60h+ObjectAttributes.SecurityDescriptor], xmm0
0x180014f0e  call    cs:__imp_NtDuplicateToken
0x180014f15  nop     dword ptr [rax+rax+00h]
0x180014f1a  test    eax, eax
0x180014f1c  jns     short loc_180014F3A
0x180014f1e  mov     ecx, eax; Status
0x180014f20  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x180014f27  nop     dword ptr [rax+rax+00h]
0x180014f2c  mov     ebx, eax
0x180014f2e  mov     r14d, edi
0x180014f31  jmp     loc_18001664B
0x180014f36  mov     [rbp+0F60h+hToken], r12
0x180014f3a  test    r15b, 4
0x180014f3e  jz      loc_180014FE9
0x180014f44  lea     rax, [rbp+0F60h+var_F40]
0x180014f48  mov     [rbp+0F60h+pvData], ebx
0x180014f4b  mov     [rsp+1060h+pcbData], rax; pcbData
0x180014f50  lea     r8, aEnablesecureui; "EnableSecureUIAPaths"
0x180014f57  lea     rax, [rbp+0F60h+pvData]
0x180014f5b  mov     [rbp+0F60h+var_F40], 4
0x180014f62  mov     [rsp+1060h+NewTokenHandle], rax; pvData
0x180014f67  lea     rdx, aSoftwareMicros_0; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180014f6e  mov     r9d, 10h; dwFlags
0x180014f74  mov     qword ptr [rsp+1060h+TokenType], rbx; pdwType
0x180014f79  mov     rcx, 0FFFFFFFF80000002h; hkey
0x180014f80  call    cs:__imp_RegGetValueW
0x180014f87  nop     dword ptr [rax+rax+00h]
0x180014f8c  test    eax, eax
0x180014f8e  jnz     short loc_180014F95
0x180014f90  cmp     [rbp+0F60h+pvData], ebx
0x180014f93  jz      short loc_180014F9C
0x180014f95  bt      r15d, 0Dh
0x180014f9a  jnb     short loc_180014FA6
0x180014f9c  bts     r15d, 0Ah
0x180014fa1  mov     [rsp+1060h+var_FF0], r15d
0x180014fa6  bt      r15d, 0Ah
0x180014fab  jnb     short loc_180014FE5
0x180014fad  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ShadowAdmin@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ShadowAdmin@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShadowAdmin> `wil::Feature<__WilFeatureTraits_Feature_ShadowAdmin>::GetImpl(void)'::`2'::impl
0x180014fb4  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ShadowAdmin@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShadowAdmin>::__private_IsEnabled(void)
0x180014fb9  mov     edx, [rbp+0F60h+arg_30]
0x180014fbf  mov     rcx, [rbp+0F60h+hToken]; TokenHandle
0x180014fc3  and     edx, 0FFFFFFFCh
0x180014fc6  test    al, al
0x180014fc8  cmovz   edx, [rbp+0F60h+arg_30]
0x180014fcf  mov     [rbp+0F60h+var_FD4], edx
0x180014fd2  call    LUASetUIAToken
0x180014fd7  mov     ebx, eax
0x180014fd9  test    eax, eax
0x180014fdb  jz      short loc_180014FF2
0x180014fdd  mov     r14, rdi
0x180014fe0  jmp     loc_18001664B
0x180014fe5  or      [rbp+0F60h+Value], 2
0x180014fe9  mov     eax, [rbp+0F60h+arg_30]
0x180014fef  mov     [rbp+0F60h+var_FD4], eax
0x180014ff2  mov     r12d, dword ptr [rbp+0F60h+arg_60]
0x180014ff9  cmp     [rbp+0F60h+hSourceHandle], rdi
0x180014ffd  jz      short loc_180015011
0x180014fff  test    r13, r13
0x180015002  setnz   dil
0x180015006  add     edi, 2
0x180015009  test    r12b, 6
0x18001500d  jz      short loc_180015011
0x18001500f  inc     edi
0x180015011  test    r15d, 1800000h
0x180015018  lea     eax, [rdi+1]
0x18001501b  cmovz   eax, edi
0x18001501e  test    r12d, 408h
0x180015025  lea     ecx, [rax+1]
0x180015028  cmovz   ecx, eax
0x18001502b  mov     eax, r12d
0x18001502e  and     eax, 2000h
0x180015033  mov     [rbp+0F60h+var_FC8], eax
0x180015036  lea     edi, [rcx+1]
0x180015039  cmovz   edi, ecx
0x18001503c  mov     [rsp+1060h+var_FEC], edi
0x180015040  test    edi, edi
0x180015042  jz      short loc_180015077
0x180015044  lea     r9, [rbp+0F60h+Size]; lpSize
0x180015048  xor     r8d, r8d; dwFlags
0x18001504b  mov     edx, edi; dwAttributeCount
0x18001504d  lea     rcx, [rbp+0F60h+var_AA0]; lpAttributeList
0x180015054  call    cs:__imp_InitializeProcThreadAttributeList
0x18001505b  nop     dword ptr [rax+rax+00h]
0x180015060  test    eax, eax
0x180015062  jnz     short loc_180015077
0x180015064  call    cs:__imp_GetLastError
0x18001506b  nop     dword ptr [rax+rax+00h]
0x180015070  mov     ebx, eax
0x180015072  jmp     loc_180016641
0x180015077  cmp     [rbp+0F60h+hSourceHandle], 0
0x18001507c  jz      loc_180015A62
0x180015082  test    r15b, 1
0x180015086  jz      short loc_18001509F
0x180015088  mov     rcx, [rbp+0F60h+hToken]; hToken
0x18001508c  lea     rdx, [rbp+0F60h+hProfile]; void **
0x180015090  call    ?AipLoadUserProfile@@YAKPEAXPEAPEAX@Z; AipLoadUserProfile(void *,void * *)
0x180015095  mov     ebx, eax
0x180015097  test    eax, eax
0x180015099  jnz     loc_180016641
0x18001509f  mov     rdx, [rbp+0F60h+hToken]; hToken
0x1800150a3  lea     rcx, [rsp+1060h+Environment]; lpEnvironment
0x1800150a8  xor     r8d, r8d; bInherit
0x1800150ab  call    cs:__imp_CreateEnvironmentBlock
0x1800150b2  nop     dword ptr [rax+rax+00h]
0x1800150b7  test    eax, eax
0x1800150b9  jz      short loc_180015064
0x1800150bb  test    r14, r14
0x1800150be  jz      loc_180015194
0x1800150c4  mov     r15, [rsp+1060h+Environment]
0x1800150c9  xor     r8d, r8d
0x1800150cc  nop     dword ptr [rax+00h]
0x1800150d0  mov     rcx, [rsp+1060h+Environment]
0x1800150d5  lea     edx, [r8+1]
0x1800150d9  mov     eax, r8d
0x1800150dc  cmp     word ptr [rcx+rax*2], 0
0x1800150e1  jnz     short loc_1800150EA
0x1800150e3  cmp     word ptr [rcx+rdx*2], 0
0x1800150e8  jz      short loc_1800150EF
0x1800150ea  mov     r8d, edx
0x1800150ed  jmp     short loc_1800150D0
0x1800150ef  xor     edx, edx
0x1800150f1  mov     eax, edx
0x1800150f3  lea     ecx, [rdx+1]
0x1800150f6  cmp     word ptr [r14+rax*2], 0
0x1800150fc  jnz     short loc_180015106
0x1800150fe  cmp     word ptr [r14+rcx*2], 0
0x180015104  jz      short loc_18001510A
0x180015106  mov     edx, ecx
0x180015108  jmp     short loc_1800150F1
0x18001510a  lea     ebx, [r8+1]
0x18001510e  lea     esi, [rdx+2]
0x180015111  lea     eax, [rsi+rbx]
0x180015114  cmp     eax, ebx
0x180015116  jb      loc_1800151D8
0x18001511c  add     rax, rax
0x18001511f  mov     ecx, 0FFFFFFFFh
0x180015124  cmp     rax, rcx
0x180015127  ja      loc_1800151D8
0x18001512d  mov     rcx, gs:60h
0x180015136  xor     edx, edx; Flags
0x180015138  mov     r8d, eax; Size
0x18001513b  mov     rcx, [rcx+30h]; HeapHandle
0x18001513f  call    cs:__imp_RtlAllocateHeap
0x180015146  nop     dword ptr [rax+rax+00h]
0x18001514b  mov     rdi, rax
0x18001514e  test    rax, rax
0x180015151  jnz     short loc_18001515B
0x180015153  lea     ebx, [rax+8]
0x180015156  jmp     loc_180016641
0x18001515b  add     rbx, rbx
0x18001515e  mov     rdx, r15; Src
0x180015161  mov     r8, rbx; Size
0x180015164  mov     rcx, rdi; void *
0x180015167  call    memcpy_0
0x18001516c  mov     r8d, esi
0x18001516f  lea     rcx, [rdi+rbx]; void *
0x180015173  add     r8, r8; Size
0x180015176  mov     rdx, r14; Src
0x180015179  call    memcpy_0
0x18001517e  mov     rcx, [rsp+1060h+Environment]; lpEnvironment
0x180015183  call    cs:__imp_DestroyEnvironmentBlock
0x18001518a  nop     dword ptr [rax+rax+00h]
0x18001518f  mov     [rsp+1060h+Environment], rdi
0x180015194  mov     rsi, [rbp+0F60h+lpApplicationName]
0x180015198  lea     rdx, [rsp+1060h+Environment]; void **
0x18001519d  mov     rcx, rsi; Str
0x1800151a0  call    ?AipCheckForAppPathsKey@@YAKPEBGPEAPEAX@Z; AipCheckForAppPathsKey(ushort const *,void * *)
0x1800151a5  mov     ebx, eax
0x1800151a7  test    eax, eax
0x1800151a9  jnz     loc_180016641
0x1800151af  mov     edx, 218h; uBytes
0x1800151b4  lea     ecx, [rax+40h]; uFlags
0x1800151b7  call    cs:__imp_LocalAlloc
0x1800151be  nop     dword ptr [rax+rax+00h]
0x1800151c3  mov     [rsp+1060h+var_1000], rax
0x1800151c8  mov     r14, rax
0x1800151cb  test    rax, rax
0x1800151ce  jnz     short loc_1800151E2
0x1800151d0  lea     ebx, [rax+8]
0x1800151d3  jmp     loc_180016646
0x1800151d8  mov     ebx, 216h
0x1800151dd  jmp     loc_180016641
0x1800151e2  call    IsSdbGetKnownSafeLayersPresent
0x1800151e7  test    al, al
0x1800151e9  jz      loc_180015396
0x1800151ef  call    cs:__imp_GetCurrentProcess
0x1800151f6  nop     dword ptr [rax+rax+00h]
0x1800151fb  mov     rdi, [rbp+0F60h+hSourceHandle]
0x1800151ff  mov     rbx, rax
0x180015202  call    cs:__imp_GetCurrentProcess
0x180015209  nop     dword ptr [rax+rax+00h]
0x18001520e  xor     ecx, ecx
0x180015210  lea     r9, [rbp+0F60h+TargetHandle]; lpTargetHandle
0x180015214  mov     dword ptr [rsp+1060h+pcbData], ecx; dwOptions
0x180015218  mov     r8, rbx; hTargetProcessHandle
0x18001521b  mov     dword ptr [rsp+1060h+NewTokenHandle], ecx; bInheritHandle
0x18001521f  mov     rdx, rdi; hSourceHandle
0x180015222  mov     rcx, rax; hSourceProcessHandle
0x180015225  mov     [rsp+1060h+TokenType], 410h; dwDesiredAccess
0x18001522d  call    cs:__imp_DuplicateHandle
0x180015234  nop     dword ptr [rax+rax+00h]
0x180015239  test    eax, eax
0x18001523b  jz      loc_180015350
0x180015241  mov     rcx, [rbp+0F60h+TargetHandle]
0x180015245  lea     rdx, [rbp+0F60h+var_F50]
0x180015249  xor     r8d, r8d
  ... truncated ...
```
