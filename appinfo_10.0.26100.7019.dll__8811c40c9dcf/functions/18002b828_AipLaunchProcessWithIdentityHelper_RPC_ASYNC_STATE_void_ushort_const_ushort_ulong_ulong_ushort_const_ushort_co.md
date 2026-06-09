# AipLaunchProcessWithIdentityHelper(_RPC_ASYNC_STATE *,void *,ushort const *,ushort *,ulong,ulong,ushort const *,ushort const *,_APPINFO_STARTUPINFO *,ushort const *,ushort const *,unsigned __int64,ulong,ulong,void *,unsigned __int64,unsigned __int64 *,_GUID *,unsigned __int64,char const *,int *,UACPROMPT_POLICY *,_APPINFO_PROCESS_INFORMATION *)

- ea: `0x18002b828`
- end: `0x18002d4cb`
- name: `?AipLaunchProcessWithIdentityHelper@@YAXPEAU_RPC_ASYNC_STATE@@PEAXPEBGPEAGKK22PEAU_APPINFO_STARTUPINFO@@22_KKK15PEA_KPEAU_GUID@@5PEBDPEAHPEAW4UACPROMPT_POLICY@@PEAU_APPINFO_PROCESS_INFORMATION@@@Z`
- size: `7331`
- prototype: `void __fastcall(struct _RPC_ASYNC_STATE *, void *, const unsigned __int16 *, unsigned __int16 *, unsigned int, unsigned int, const unsigned __int16 *, const unsigned __int16 *, struct _APPINFO_STARTUPINFO *, const unsigned __int16 *, const unsigned __int16 *, unsigned __int64, unsigned int, unsigned int, void *, unsigned __int64, unsigned __int64 *, struct _GUID *, unsigned __int64, const char *Source, int *, enum UACPROMPT_POLICY *, struct _APPINFO_PROCESS_INFORMATION *)`
- caller_count: `2`
- callee_count: `56`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180039cb0`
- `0x18003acc0`

## callees

- `0x18000a1f0`
- `0x18000a230`
- `0x18000c390`
- `0x18000cf00`
- `0x18000f11c`
- `0x180010f3c`
- `0x1800114ac`
- `0x18001152c`
- `0x180011eb8`
- `0x1800128d4`
- `0x180012b9c`
- `0x180014d40`
- `0x1800168f0`
- `0x180016c54`
- `0x18001800c`
- `0x180018f18`
- `0x18001943c`
- `0x180019748`
- `0x18001ac0c`
- `0x18001b0c4`
- `0x18001b0d0`
- `0x18001c058`
- `0x18001c0ac`
- `0x18001cf08`
- `0x18001d0ec`
- `0x18002444c`
- `0x180024db0`
- `0x180025724`
- `0x18002618c`
- `0x180027698`
- `0x180027784`
- `0x180028424`
- `0x1800287fc`
- `0x180028864`
- `0x18002a750`
- `0x18002b2a4`
- `0x18002b828`
- `0x18002d4d4`
- `0x1800334c8`
- `0x180035d08`
- `0x180035f20`
- `0x180037fd0`
- `0x180038d0c`
- `0x180038d40`
- `0x180038dac`
- `0x18003aee8`
- `0x18003b384`
- `0x18003b45c`
- `0x18003b8d8`
- `0x1800402e4`

## import_xrefs

- `msvcrt!strncpy_s` at `0x18002bc13`
- `msvcrt!strncpy_s` at `0x18002bc13`
- `RPCRT4!RpcRevertToSelf` at `0x18002c12d`
- `RPCRT4!RpcRevertToSelf` at `0x18002c381`
- `RPCRT4!RpcRevertToSelf` at `0x18002ce33`
- `RPCRT4!RpcRevertToSelf` at `0x18002c12d`
- `RPCRT4!RpcRevertToSelf` at `0x18002c381`
- `RPCRT4!RpcRevertToSelf` at `0x18002ce33`
- `RPCRT4!RpcImpersonateClient` at `0x18002c10a`
- `RPCRT4!RpcImpersonateClient` at `0x18002c2e3`
- `RPCRT4!RpcImpersonateClient` at `0x18002cd82`
- `RPCRT4!RpcImpersonateClient` at `0x18002c10a`
- `RPCRT4!RpcImpersonateClient` at `0x18002c2e3`
- `RPCRT4!RpcImpersonateClient` at `0x18002cd82`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18002d44c`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18002d44c`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18002c3fa`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18002cc0b`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18002c3fa`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18002cc0b`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18002c4ef`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18002c5ac`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18002cc48`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18002cc64`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18002c4ef`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18002c5ac`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18002cc48`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18002cc64`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002bfea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c40c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c48d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d0bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d134`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002bfea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c40c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c48d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d0bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d134`
- `api-ms-win-core-processthreads-l1-1-0!OpenThread` at `0x18002d0a5`
- `api-ms-win-core-processthreads-l1-1-0!OpenThread` at `0x18002d0a5`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x18002d123`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x18002d123`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x18002d3d8`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x18002d3d8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002bf9f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002bfae`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002bf9f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002bfae`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002d296`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002d387`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002d39f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002d3e7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002d296`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002d387`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002d39f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002d3e7`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18002bfda`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18002bfda`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002d2ae`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002d2c6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002d2e5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002d2f9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002d426`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002d2ae`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002d2c6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002d2e5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002d2f9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002d426`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18002d3be`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18002d3be`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002c474`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002c474`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18002ba84`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18002c0ae`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18002ba84`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18002c0ae`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x18002ba97`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x18002ba97`
- `api-ms-win-core-kernel32-private-l1-1-0!CheckElevation` at `0x18002c521`
- `api-ms-win-core-kernel32-private-l1-1-0!CheckElevation` at `0x18002c521`
- `api-ms-win-core-kernel32-private-l1-1-0!CheckElevationEnabled` at `0x18002c2a8`
- `api-ms-win-core-kernel32-private-l1-1-0!CheckElevationEnabled` at `0x18002c2a8`
- `api-ms-win-core-psm-key-l1-1-0!PsmCreateKey` at `0x18002ca09`
- `api-ms-win-core-psm-key-l1-1-0!PsmCreateKey` at `0x18002ca09`
- `ntdll!NtClose` at `0x18002ce77`
- `ntdll!NtClose` at `0x18002d30e`
- `ntdll!NtClose` at `0x18002d32a`
- `ntdll!NtClose` at `0x18002d342`
- `ntdll!NtClose` at `0x18002ce77`
- `ntdll!NtClose` at `0x18002d30e`
- `ntdll!NtClose` at `0x18002d32a`
- `ntdll!NtClose` at `0x18002d342`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18002bdf2`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18002c13f`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18002bdf2`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18002c13f`
- `USERENV!UnloadUserProfile` at `0x18002cbf6`
- `USERENV!UnloadUserProfile` at `0x18002cd5e`
- `USERENV!UnloadUserProfile` at `0x18002cbf6`
- `USERENV!UnloadUserProfile` at `0x18002cd5e`
- `ext-ms-win-desktopappx-l1-1-0!PostCreateProcessDesktopAppXActivation` at `0x18002d02c`
- `ext-ms-win-desktopappx-l1-1-0!PostCreateProcessDesktopAppXActivation` at `0x18002d02c`
- `ext-ms-win-desktopappx-l1-1-0!FreeDesktopAppXLaunchContext` at `0x18002d357`
- `ext-ms-win-desktopappx-l1-1-0!FreeDesktopAppXLaunchContext` at `0x18002d357`
- `ext-ms-win-desktopappx-l1-1-0!PrepareDesktopAppXActivation` at `0x18002ccc0`
- `ext-ms-win-desktopappx-l1-1-0!PrepareDesktopAppXActivation` at `0x18002ccc0`
- `ext-ms-win-desktopappx-l1-1-4!DoesPackageHaveElevationCapability` at `0x18002c6cd`
- `ext-ms-win-desktopappx-l1-1-4!DoesPackageHaveElevationCapability` at `0x18002c6cd`
- `ext-ms-win-desktopappx-l1-1-5!DoesPackageHaveUIAccessCapability` at `0x18002c5f1`
- `ext-ms-win-desktopappx-l1-1-5!DoesPackageHaveUIAccessCapability` at `0x18002c5f1`
- `ext-ms-win-desktopappx-l1-2-2!RundownHeliumContainerForDesktopAppXActivation` at `0x18002d435`
- `ext-ms-win-desktopappx-l1-2-2!RundownHeliumContainerForDesktopAppXActivation` at `0x18002d435`
- `ext-ms-win-desktopappx-l1-2-2!BeginCreatingHeliumContainerForDesktopAppXActivation` at `0x18002cea5`
- `ext-ms-win-desktopappx-l1-2-2!BeginCreatingHeliumContainerForDesktopAppXActivation` at `0x18002cea5`
- `ext-ms-win-desktopappx-l1-1-6!VerifyFileIsTrustedAndInPackage` at `0x18002c58d`
- `ext-ms-win-desktopappx-l1-1-6!VerifyFileIsTrustedAndInPackage` at `0x18002c58d`
- `ext-ms-win-appmodel-activation-l1-1-0!FreeAppXLaunchContext` at `0x18002d36c`
- `ext-ms-win-appmodel-activation-l1-1-0!FreeAppXLaunchContext` at `0x18002d36c`
- `ext-ms-win-appmodel-activation-l1-1-0!PrepareAppXActivation` at `0x18002cb22`
- `ext-ms-win-appmodel-activation-l1-1-0!PrepareAppXActivation` at `0x18002cb22`
- `ext-ms-win-appmodel-activation-l1-1-0!PostCreateProcessAppXActivation` at `0x18002cfde`
- `ext-ms-win-appmodel-activation-l1-1-0!PostCreateProcessAppXActivation` at `0x18002cfde`
- `ext-ms-win-appmodel-activation-l1-1-1!RegisterAppXPackageIfNecessary2` at `0x18002cc31`
- `ext-ms-win-appmodel-activation-l1-1-1!RegisterAppXPackageIfNecessary2` at `0x18002cc31`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrIsAllowedToActivateAsUser` at `0x18002bf58`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrIsAllowedToActivateAsUser` at `0x18002bf58`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x18002bf8a`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x18002bf8a`
- `ext-ms-win-core-app-package-volume-l1-1-0!UnmountVolumeForAppPackage` at `0x18002d40e`
- `ext-ms-win-core-app-package-volume-l1-1-0!UnmountVolumeForAppPackage` at `0x18002d40e`
- `ext-ms-win-core-app-package-volume-l1-1-0!MountVolumeForAppPackage` at `0x18002ca37`
- `ext-ms-win-core-app-package-volume-l1-1-0!MountVolumeForAppPackage` at `0x18002ca37`

## string_xrefs

- `0x18002baf7`: `++. hwnd = %x dwClientFlags = %x dwCreationFlags = %x dwTimeout = %x\n	lpDesktop = %ws\n	lpApplicationName = %ws\n	lpCommandLine = %ws\n	lpCurrentDirectory = %ws\n	packageFamilyName = %ws\n	applicationId = %ws\n	szLocalCorrelationVector = %s\n`

## pseudocode

```c
void __fastcall AipLaunchProcessWithIdentityHelper(
        struct _RPC_ASYNC_STATE *a1,
        void *a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4,
        unsigned int a5,
        unsigned int a6,
        unsigned __int16 *a7,
        unsigned __int16 *a8,
        struct _APPINFO_STARTUPINFO *a9,
        const unsigned __int16 *a10,
        wchar_t *a11,
        void *a12,
        unsigned int a13,
        unsigned int a14,
        void *a15,
        unsigned __int64 a16,
        unsigned __int64 *a17,
        struct _GUID *a18,
        unsigned __int64 a19,
        char *Source,
        int *a21,
        enum UACPROMPT_POLICY *a22,
        struct _APPINFO_PROCESS_INFORMATION *a23)
{
  const char *v23; // rdi
  unsigned __int16 *v24; // r14
  unsigned __int16 *v25; // r12
  unsigned __int16 *v26; // r13
  signed int AppModelIdentityActivationProperties; // r15d
  __int64 v28; // rbx
  const unsigned __int16 *v29; // rsi
  const unsigned __int16 *v30; // r8
  PCWSTR v31; // r9
  unsigned __int16 *v32; // r10
  unsigned __int16 *v33; // rdx
  const unsigned __int16 *v34; // rcx
  const unsigned __int16 *v35; // rax
  void *v36; // rax
  volatile signed __int64 *v37; // rdi
  char v38; // r10
  char v39; // r11
  struct _PROCESS_INFORMATION *v40; // rax
  const unsigned __int16 *v41; // rdx
  const unsigned __int16 *v42; // rcx
  const unsigned __int16 *v43; // rax
  unsigned __int64 v44; // rax
  unsigned __int64 v45; // rdi
  NTSTATUS v46; // eax
  UINT LastError; // eax
  int v48; // r8d
  int v49; // ecx
  HANDLE CurrentProcess; // rdi
  HANDLE v51; // rax
  UINT v52; // eax
  unsigned __int64 v53; // rax
  wchar_t *v54; // rdi
  UINT v55; // eax
  NTSTATUS PackageFullNameFromFamilyName; // edi
  UINT v57; // eax
  int PackageProperties; // eax
  __int64 v59; // rdx
  int v60; // r8d
  _QWORD *v61; // rcx
  int v62; // edx
  const unsigned __int16 *v63; // rax
  const unsigned __int16 *v64; // rdx
  int DoesExecutableExistInPackage; // eax
  __int64 v66; // r8
  _QWORD *v67; // r8
  __int64 v68; // r9
  _QWORD *v69; // rcx
  int v70; // edx
  __int64 v71; // rcx
  const unsigned __int16 *v72; // rax
  const WCHAR *v73; // rcx
  int v74; // r8d
  UINT v75; // r9d
  _QWORD *v76; // rcx
  int v77; // edx
  __int64 v78; // rcx
  const unsigned __int16 *v79; // rax
  unsigned __int16 *v80; // rcx
  const unsigned __int16 *v81; // rcx
  int IsTrustedAndInPackage; // eax
  __int64 v83; // rdx
  __int64 v84; // rcx
  unsigned int v85; // r8d
  int HaveUIAccessCapability; // eax
  _QWORD *v87; // rcx
  int v88; // edx
  __int64 v89; // rcx
  const unsigned __int16 *v90; // rax
  unsigned int v91; // edi
  const unsigned __int16 *v92; // rcx
  UINT v93; // eax
  HLOCAL v94; // rcx
  wchar_t *v95; // rcx
  void *v96; // rdi
  unsigned int v97; // eax
  int token_information; // eax
  unsigned __int16 **v99; // rdx
  int v100; // eax
  UINT v101; // eax
  int v102; // eax
  int v103; // eax
  int v104; // edi
  int v105; // r8d
  const unsigned __int16 *v106; // rax
  bool v107; // al
  BOOL v108; // edi
  int v109; // eax
  int v110; // eax
  int v111; // eax
  int v112; // r8d
  const unsigned __int16 *v113; // rax
  __int64 v114; // r8
  __int64 v115; // r9
  __int64 v116; // rcx
  void *v117; // r10
  __int64 v118; // rax
  int v119; // edi
  bool v120; // cf
  int v121; // eax
  HANDLE v122; // rax
  UINT v123; // eax
  const unsigned __int16 *v124; // rcx
  unsigned int v125; // esi
  const unsigned __int16 *v126; // rax
  PCWSTR v127; // r8
  struct _PROCESS_INFORMATION *v128; // rdi
  const unsigned __int16 *v129; // rax
  const unsigned __int16 *v130; // r9
  DWORD dwProcessId; // r8d
  HANDLE v132; // rax
  void *v133; // rdi
  int dwDesiredAccess; // [rsp+20h] [rbp-F0h]
  int bInheritHandle; // [rsp+28h] [rbp-E8h]
  __int64 bInheritHandlea; // [rsp+28h] [rbp-E8h]
  int dwOptions; // [rsp+30h] [rbp-E0h]
  PCWSTR dwOptionsa; // [rsp+30h] [rbp-E0h]
  int v139; // [rsp+38h] [rbp-D8h]
  struct _CONSENTUI_PARAM_HEADER **v140; // [rsp+38h] [rbp-D8h]
  int v141; // [rsp+40h] [rbp-D0h]
  int v142; // [rsp+48h] [rbp-C8h]
  int v143; // [rsp+50h] [rbp-C0h]
  int lpValue; // [rsp+58h] [rbp-B8h]
  UINT uExitCode; // [rsp+90h] [rbp-80h] BYREF
  wchar_t *v146; // [rsp+98h] [rbp-78h]
  char v147; // [rsp+A0h] [rbp-70h] BYREF
  bool v148; // [rsp+A1h] [rbp-6Fh] BYREF
  bool v149; // [rsp+A2h] [rbp-6Eh] BYREF
  bool v150; // [rsp+A3h] [rbp-6Dh] BYREF
  bool v151; // [rsp+A4h] [rbp-6Ch] BYREF
  bool v152; // [rsp+A5h] [rbp-6Bh] BYREF
  bool v153; // [rsp+A6h] [rbp-6Ah] BYREF
  bool v154; // [rsp+A7h] [rbp-69h] BYREF
  bool v155; // [rsp+A8h] [rbp-68h] BYREF
  bool v156; // [rsp+A9h] [rbp-67h] BYREF
  bool v157; // [rsp+AAh] [rbp-66h] BYREF
  bool v158; // [rsp+ABh] [rbp-65h] BYREF
  HANDLE TargetHandle; // [rsp+B0h] [rbp-60h] BYREF
  bool v160; // [rsp+B8h] [rbp-58h] BYREF
  char v161; // [rsp+B9h] [rbp-57h] BYREF
  char v162; // [rsp+BAh] [rbp-56h]
  unsigned int v163; // [rsp+BCh] [rbp-54h] BYREF
  unsigned int v164; // [rsp+C0h] [rbp-50h]
  unsigned int v165; // [rsp+C4h] [rbp-4Ch] BYREF
  unsigned int v166; // [rsp+C8h] [rbp-48h] BYREF
  unsigned int v167; // [rsp+CCh] [rbp-44h] BYREF
  unsigned int v168; // [rsp+D0h] [rbp-40h]
  unsigned int v169; // [rsp+D4h] [rbp-3Ch] BYREF
  int v170; // [rsp+D8h] [rbp-38h]
  PCWSTR packageFamilyName; // [rsp+E0h] [rbp-30h]
  int v172[2]; // [rsp+E8h] [rbp-28h] BYREF
  unsigned int v173; // [rsp+F0h] [rbp-20h] BYREF
  unsigned __int16 *v174; // [rsp+F8h] [rbp-18h] BYREF
  HANDLE hProfile; // [rsp+100h] [rbp-10h] BYREF
  unsigned int v176; // [rsp+108h] [rbp-8h] BYREF
  unsigned int v177; // [rsp+110h] [rbp+0h]
  HANDLE hSourceHandle; // [rsp+118h] [rbp+8h] BYREF
  int v179; // [rsp+120h] [rbp+10h] BYREF
  int v180; // [rsp+124h] [rbp+14h] BYREF
  int v181; // [rsp+128h] [rbp+18h] BYREF
  unsigned int v182; // [rsp+130h] [rbp+20h] BYREF
  HLOCAL hMem; // [rsp+138h] [rbp+28h] BYREF
  __int64 v184; // [rsp+140h] [rbp+30h] BYREF
  unsigned int v185; // [rsp+148h] [rbp+38h] BYREF
  HLOCAL v186; // [rsp+150h] [rbp+40h] BYREF
  int v187; // [rsp+158h] [rbp+48h] BYREF
  struct _PROCESS_INFORMATION *v188; // [rsp+160h] [rbp+50h]
  int v189; // [rsp+168h] [rbp+58h] BYREF
  LPCWSTR lpFileName; // [rsp+170h] [rbp+60h] BYREF
  __int64 v191; // [rsp+178h] [rbp+68h] BYREF
  unsigned int v192[2]; // [rsp+180h] [rbp+70h]
  int v193; // [rsp+188h] [rbp+78h] BYREF
  void *v194; // [rsp+190h] [rbp+80h] BYREF
  HANDLE hObject; // [rsp+198h] [rbp+88h]
  HLOCAL v196; // [rsp+1A0h] [rbp+90h] BYREF
  HLOCAL v197; // [rsp+1A8h] [rbp+98h] BYREF
  void *Block; // [rsp+1B0h] [rbp+A0h] BYREF
  int v199; // [rsp+1B8h] [rbp+A8h] BYREF
  unsigned __int16 *v200; // [rsp+1C0h] [rbp+B0h] BYREF
  PCWSTR v201; // [rsp+1C8h] [rbp+B8h] BYREF
  int v202; // [rsp+1D0h] [rbp+C0h] BYREF
  unsigned __int16 *Src; // [rsp+1D8h] [rbp+C8h]
  unsigned __int16 *v204; // [rsp+1E0h] [rbp+D0h]
  unsigned __int16 *v205; // [rsp+1E8h] [rbp+D8h]
  unsigned __int16 *v206; // [rsp+1F0h] [rbp+E0h]
  unsigned __int16 *v207; // [rsp+1F8h] [rbp+E8h]
  HANDLE Handle; // [rsp+200h] [rbp+F0h] BYREF
  HANDLE hToken; // [rsp+208h] [rbp+F8h] BYREF
  struct _APPINFO_STARTUPINFO *v210; // [rsp+210h] [rbp+100h] BYREF
  void *v211; // [rsp+218h] [rbp+108h] BYREF
  struct _GUID *v212; // [rsp+220h] [rbp+110h]
  unsigned __int64 *v213; // [rsp+228h] [rbp+118h]
  void *v214; // [rsp+230h] [rbp+120h] BYREF
  LARGE_INTEGER v215; // [rsp+238h] [rbp+128h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+240h] [rbp+130h] BYREF
  LARGE_INTEGER Frequency; // [rsp+248h] [rbp+138h] BYREF
  HANDLE v218; // [rsp+250h] [rbp+140h]
  __int128 v219; // [rsp+258h] [rbp+148h] BYREF
  __int64 v220; // [rsp+268h] [rbp+158h]
  int *v221; // [rsp+270h] [rbp+160h]
  void *v222; // [rsp+278h] [rbp+168h]
  PRPC_ASYNC_STATE pAsync; // [rsp+280h] [rbp+170h]
  __int128 v224; // [rsp+288h] [rbp+178h] BYREF
  __int128 v225; // [rsp+298h] [rbp+188h]
  __int64 v226; // [rsp+2A8h] [rbp+198h]
  __int128 v227; // [rsp+2B0h] [rbp+1A0h] BYREF
  __int128 v228; // [rsp+2C0h] [rbp+1B0h]
  __int64 v229; // [rsp+2D0h] [rbp+1C0h]
  char v230[80]; // [rsp+2E0h] [rbp+1D0h] BYREF
  char Destination[144]; // [rsp+330h] [rbp+220h] BYREF
  _BYTE v232[464]; // [rsp+3C0h] [rbp+2B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+5E8h] [rbp+4D8h]

  v23 = Source;
  v204 = a8;
  v24 = a3;
  v25 = a4;
  packageFamilyName = a10;
  v146 = a11;
  v168 = a5;
  v182 = a5;
  v164 = a6;
  v176 = a6;
  v210 = a9;
  hProfile = a12;
  v165 = a13;
  v222 = a15;
  v213 = a17;
  v212 = a18;
  v221 = a21;
  *(_QWORD *)v172 = a22;
  pAsync = a1;
  v188 = (struct _PROCESS_INFORMATION *)a23;
  v207 = a7;
  v196 = a7;
  hObject = (HANDLE)-1LL;
  v26 = 0;
  v220 = 0;
  AppModelIdentityActivationProperties = 0;
  v226 = 0;
  v229 = 0;
  v206 = a4;
  v205 = a3;
  v194 = a2;
  lpFileName = a3;
  hMem = a4;
  v173 = 0;
  v167 = 0;
  v163 = 0;
  v199 = 0;
  v169 = 0;
  v186 = 0;
  v214 = 0;
  Handle = 0;
  hSourceHandle = 0;
  v211 = 0;
  TargetHandle = 0;
  v218 = 0;
  hToken = 0;
  v187 = 0;
  v174 = 0;
  v185 = 0;
  v177 = 0;
  v193 = 0;
  v179 = 6;
  v197 = 0;
  v219 = 0;
  v184 = 0;
  v224 = 0;
  v191 = 0;
  v225 = 0;
  v170 = 0;
  v227 = 0;
  Src = 0;
  v228 = 0;
  v28 = 0;
  v166 = 0;
  v181 = 0;
  v180 = 0;
  v147 = 0;
  v157 = 0;
  v149 = 0;
  v156 = 0;
  v155 = 0;
  v154 = 0;
  v148 = 0;
  v151 = 0;
  memset_0(v232, 0, sizeof(v232));
  v202 = 464;
  Block = 0;
  v162 = 0;
  memset_0(Destination, 0, 0x81u);
  Frequency.QuadPart = 0;
  PerformanceCount.QuadPart = 0;
  v215.QuadPart = 0;
  QueryPerformanceCounter(&PerformanceCount);
  QueryPerformanceFrequency(&Frequency);
  v29 = L"NULL";
  v30 = a11;
  if ( !a11 )
    v30 = L"NULL";
  v31 = packageFamilyName;
  if ( !packageFamilyName )
    v31 = L"NULL";
  v32 = v204;
  *(_QWORD *)v192 = v30;
  v33 = v207;
  v201 = v31;
  if ( !v204 )
    v32 = L"NULL";
  v200 = v32;
  v34 = v25;
  if ( !v207 )
    v33 = L"NULL";
  v35 = v24;
  if ( !v25 )
    v34 = L"NULL";
  if ( !v24 )
    v35 = L"NULL";
  LUATelemetry::WatchCurrentThread(
    v230,
    "AipLaunchProcessWithIdentityHelper",
    "++. hwnd = %x dwClientFlags = %x dwCreationFlags = %x dwTimeout = %x\n"
    "\tlpDesktop = %ws\n"
    "\tlpApplicationName = %ws\n"
    "\tlpCommandLine = %ws\n"
    "\tlpCurrentDirectory = %ws\n"
    "\tpackageFamilyName = %ws\n"
    "\tapplicationId = %ws\n"
    "\tszLocalCorrelationVector = %s\n",
    (unsigned int)hProfile,
    v168,
    v164,
    v165,
    v32,
    v35,
    v34,
    v33,
    v31,
    v30,
    Destination);
  if ( !g_pCentennialElevationTelemetryRateLimiter
    || !(unsigned int)RateLimiter::RequestPermission(g_pCentennialElevationTelemetryRateLimiter) )
  {
    goto LABEL_23;
  }
  if ( v23 )
  {
    strncpy_s(Destination, 0x81u, v23, 0x81u);
LABEL_23:
    v38 = v168;
    v39 = v164;
    goto LABEL_24;
  }
  v36 = operator new(0x90u);
  if ( v36 )
    v37 = (volatile signed __int64 *)TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(v36);
  else
    v37 = 0;
  TraceLoggingCorrelationVector::ToStringImpl(
    (TraceLoggingCorrelationVector *)v37,
    _InterlockedExchangeAdd64(v37 + 17, 0),
    Destination);
  if ( v37 )
    operator delete((void *)v37);
  v38 = v182;
  v39 = v176;
  v26 = (unsigned __int16 *)v186;
  v24 = (unsigned __int16 *)lpFileName;
  v25 = (unsigned __int16 *)hMem;
  v167 = v163;
  v168 = v182;
  v164 = v176;
LABEL_24:
  v40 = v188;
  *(_OWORD *)&v188->hProcess = 0;
  *(_QWORD *)&v40->dwProcessId = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v41 = L"NULL";
    if ( v196 )
      v41 = (const unsigned __int16 *)v196;
    v42 = L"NULL";
    if ( v25 )
      v42 = v25;
    v43 = L"NULL";
    if ( v24 )
      v43 = v24;
    WPP_SF_DDDDSSSSSSs(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      (_DWORD)v41,
      (_DWORD)WPP_GLOBAL_Control,
      (_DWORD)hProfile,
      v38,
      v39,
      v165,
      (__int64)v200,
      (__int64)v43,
      (__int64)v42,
      (__int64)v41,
      (__int64)v201,
      *(__int64 *)v192,
      (__int64)Destination);
  }
  if ( (a14 & 1) != 0 )
  {
    v177 = AiLogPerfTrackEvent(&AppInfo_PerfTrack_Elevation_PackagedApp_Start);
    v147 = 1;
  }
  if ( !v24 || !packageFamilyName || !v146 )
    goto LABEL_94;
  AipJustFileName(v24);
  v44 = -1;
  v45 = -1;
  do
    ++v45;
  while ( v24[v45] );
  *(_QWORD *)v192 = v45;
  if ( v25 )
  {
    do
      ++v44;
    while ( v25[v44] );
    v174 = (unsigned __int16 *)v44;
  }
  else
  {
    v44 = (unsigned __int64)v174;
  }
  if ( v45 > 0x7FFF || v44 > 0x7FFF || (a14 & 0x120) == 0x100 || (a14 & 0x810) == 0x800 )
    goto LABEL_94;
  uExitCode = AiGetClientInformation(v194, &Handle, &hSourceHandle, &v173, &v185);
  if ( uExitCode )
  {
LABEL_95:
    v54 = v146;
    goto LABEL_96;
  }
  if ( *(_QWORD *)v172 )
  {
    v180 = **(_DWORD **)v172;
  }
  else
  {
    v172[0] = 0;
    v46 = LUAGetUACPromptPolicy(v172, &v180);
    if ( v46 < 0 )
      goto LABEL_54;
  }
  if ( v221 )
  {
    v181 = *v221;
  }
  else
  {
    v172[0] = 0;
    v46 = AiCheckForElevatedUser(hSourceHandle, v172);
    if ( v46 < 0 )
      goto LABEL_54;
    v46 = AiCheckForAdminUser(hSourceHandle, v172[0], &v181);
    if ( v46 < 0 )
      goto LABEL_54;
  }
  v150 = 0;
  v158 = 0;
  v153 = 0;
  v152 = 0;
  v160 = 0;
  AppModelIdentityActivationProperties = GetAppModelIdentityActivationProperties(
                                           hSourceHandle,
                                           v146,
                                           0,
                                           a14,
                                           (enum AppModel::RuntimeBehavior *)&v166,
                                           &v150,
                                           &v158,
                                           &v153,
                                           &v152,
                                           &v160);
  if ( AppModelIdentityActivationProperties < 0 )
  {
    uExitCode = WIN32_FROM_HRESULT(AppModelIdentityActivationProperties);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_DSS(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        44,
        v48,
        AppModelIdentityActivationProperties,
        (__int64)v24,
        (__int64)L"NULL");
    goto LABEL_95;
  }
  if ( v160 )
    a14 |= 0x2000u;
  if ( v147 && v150 )
    goto LABEL_66;
  if ( v166 == 1 )
  {
    AppModelIdentityActivationProperties = ReplaceDSMAIfPresent(hSourceHandle);
    if ( AppModelIdentityActivationProperties < 0 )
      goto LABEL_69;
  }
  if ( a16 )
  {
    if ( !(unsigned __int8)IsUMgrIsAllowedToActivateAsUserPresent() )
    {
LABEL_75:
      uExitCode = 5;
      goto LABEL_95;
    }
    v161 = 0;
    AppModelIdentityActivationProperties = UMgrIsAllowedToActivateAsUser(hSourceHandle, a16, &v161);
    if ( AppModelIdentityActivationProperties < 0 )
      goto LABEL_69;
    if ( !v161 )
      goto LABEL_75;
    AppModelIdentityActivationProperties = UMgrQueryUserToken(a16, &TargetHandle);
    if ( AppModelIdentityActivationProperties < 0 )
    {
LABEL_69:
      v49 = AppModelIdentityActivationProperties;
LABEL_70:
      LastError = WIN32_FROM_HRESULT(v49);
      goto LABEL_55;
    }
  }
  else
  {
    CurrentProcess = GetCurrentProcess();
    v51 = GetCurrentProcess();
    if ( !DuplicateHandle(v51, hSourceHandle, CurrentProcess, &TargetHandle, 0, 0, 2u) )
    {
      LastError = GetLastError();
      goto LABEL_55;
    }
    v45 = *(_QWORD *)v192;
  }
  if ( (v168 & 8) != 0 )
  {
    v52 = AiConvertWow64Paths(
            v205,
            &lpFileName,
            v206,
            (unsigned __int16 **)&hMem,
            v207,
            (const unsigned __int16 **)&v196);
    v24 = (unsigned __int16 *)lpFileName;
    uExitCode = v52;
    if ( v52 )
    {
      v25 = (unsigned __int16 *)hMem;
      goto LABEL_95;
    }
    if ( lpFileName )
    {
      v45 = -1;
      do
        ++v45;
      while ( lpFileName[v45] );
      *(_QWORD *)v192 = v45;
    }
    v25 = (unsigned __int16 *)hMem;
    if ( hMem )
    {
      v53 = -1;
      do
        ++v53;
      while ( *((_WORD *)hMem + v53) );
      v174 = (unsigned __int16 *)v53;
    }
    else
    {
      v53 = (unsigned __int64)v174;
    }
    if ( v45 > 0x7FFF || v53 > 0x7FFF )
    {
LABEL_94:
      uExitCode = 87;
      goto LABEL_95;
    }
  }
  LastError = RpcImpersonateClient(0);
  if ( LastError )
    goto LABEL_55;
  PackageFullNameFromFamilyName = GetPackageFullNameFromFamilyName(packageFamilyName, (unsigned __int16 **)&v186);
  RpcRevertToSelf();
  if ( PackageFullNameFromFamilyName < 0 )
  {
    v57 = RtlNtStatusToDosErrorNoTeb(PackageFullNameFromFamilyName);
    v26 = (unsigned __int16 *)v186;
    uExitCode = v57;
    goto LABEL_95;
  }
  v26 = (unsigned __int16 *)v186;
  PackageProperties = GetPackageProperties(
                        (const unsigned __int16 *)v186,
                        &v157,
                        &v149,
                        &v156,
                        &v155,
                        &v154,
                        &v148,
                        &v151,
                        0);
  AppModelIdentityActivationProperties = PackageProperties;
  if ( PackageProperties < 0 )
  {
    uExitCode = WIN32_FROM_HRESULT(PackageProperties);
    v61 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_95;
    v62 = 45;
LABEL_106:
    v63 = L"NULL";
    if ( v26 )
      v63 = v26;
    if ( v24 )
      v29 = v24;
    WPP_SF_DSS(v61[2], v62, v60, AppModelIdentityActivationProperties, (__int64)v29, (__int64)v63);
    goto LABEL_95;
  }
  LOBYTE(v59) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID52930508>::ReportUsage(
    &`wil::Feature<__WilFeatureTraits_Feature_ID52930508>::GetImpl'::`2'::impl,
    v59);
  if ( v148 && !v149 )
  {
    v172[0] = 0;
    v46 = AiCheckForTcbPrivilege(hSourceHandle, v172);
    if ( v46 < 0 )
      goto LABEL_54;
    if ( !v172[0] )
    {
      v148 = 0;
      v64 = v25;
      if ( v24 )
        v64 = v24;
      DoesExecutableExistInPackage = AiDoesExecutableExistInPackage(v26, v64, &v148);
      AppModelIdentityActivationProperties = DoesExecutableExistInPackage;
      if ( DoesExecutableExistInPackage < 0 )
      {
        uExitCode = WIN32_FROM_HRESULT(DoesExecutableExistInPackage);
        v61 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_95;
        v62 = 46;
        goto LABEL_106;
      }
      if ( !v148 )
        goto LABEL_75;
    }
  }
  if ( !v166 )
    goto LABEL_221;
  v170 = 2;
  if ( !v147 )
    goto LABEL_221;
  uExitCode = CheckElevationEnabled(&v193);
  if ( uExitCode )
    goto LABEL_95;
  if ( !v193 )
  {
    v147 = 0;
    goto LABEL_221;
  }
  v147 = 1;
  v46 = LUAGetUserType(TargetHandle, &v187);
  if ( v46 < 0 )
  {
LABEL_54:
    LastError = RtlNtStatusToDosErrorNoTeb(v46);
LABEL_55:
    uExitCode = LastError;
    goto LABEL_95;
  }
  LastError = RpcImpersonateClient(0);
  if ( LastError )
    goto LABEL_55;
  LOBYTE(v66) = v150;
  v54 = v146;
  LOBYTE(lpValue) = 0;
  LOBYTE(v143) = v151;
  LOBYTE(v142) = v152;
  LOBYTE(v141) = v153;
  LOBYTE(v139) = v154;
  LOBYTE(dwOptions) = v155;
  LOBYTE(bInheritHandle) = v156;
  LOBYTE(dwDesiredAccess) = v157;
  uExitCode = AdjustActivationToken(
                TargetHandle,
                v166,
                v66,
                0,
                dwDesiredAccess,
                bInheritHandle,
                dwOptions,
                v139,
                v141,
                v142,
                v143,
                lpValue,
                v26,
                v146,
                v213,
                v212,
                0,
                &hToken);
  RpcRevertToSelf();
  LODWORD(v68) = uExitCode;
  if ( uExitCode )
  {
    v69 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_96;
    v70 = 47;
    goto LABEL_132;
  }
  if ( !ImpersonateLoggedOnUser(hToken) )
  {
    LODWORD(v68) = GetLastError();
    uExitCode = v68;
    v69 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_96;
    v70 = 48;
    goto LABEL_132;
  }
  v73 = v25;
  if ( v24 )
    v73 = v24;
  hObject = CreateFileW(v73, 0xA0000000, 5u, 0, 3u, 0x80u, 0);
  if ( hObject == (HANDLE)-1LL )
  {
    v75 = GetLastError();
    uExitCode = v75;
    v76 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v77 = 49;
LABEL_148:
      v78 = v76[2];
      v79 = L"NULL";
      if ( v25 )
        v79 = v25;
      if ( v24 )
        v29 = v24;
      WPP_SF_DSSSS(v78, v77, v74, v75, (__int64)v29, (__int64)v79, (__int64)packageFamilyName, (__int64)v146);
      goto LABEL_153;
    }
    goto LABEL_153;
  }
  v80 = v25;
  if ( v24 )
    v80 = v24;
  uExitCode = CheckElevation(v80, &v199, 0, &v169);
  v75 = uExitCode;
  if ( uExitCode )
  {
    v76 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v77 = 50;
      goto LABEL_148;
    }
LABEL_153:
    RevertToSelf();
    goto LABEL_96;
  }
  v81 = v25;
  if ( v24 )
    v81 = v24;
  uExitCode = AiCheckSecureApplicationDirectory(v81, &v163);
  if ( uExitCode )
    goto LABEL_153;
  LODWORD(v194) = 0;
  IsTrustedAndInPackage = VerifyFileIsTrustedAndInPackage(v24, v26, &v194);
  if ( IsTrustedAndInPackage < 0 )
  {
    uExitCode = WIN32_FROM_HRESULT(IsTrustedAndInPackage);
    goto LABEL_153;
  }
  RevertToSelf();
  v84 = v169;
  if ( v169 - 16 > 2 )
  {
    v91 = v163;
  }
  else
  {
    v170 = 3;
    v172[0] = 0;
    LOBYTE(v83) = 1;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_CentennialUIAccess>::ReportUsage(
      &`wil::Feature<__WilFeatureTraits_Feature_CentennialUIAccess>::GetImpl'::`2'::impl,
      v83);
    if ( !(unsigned __int8)IsDoesPackageHaveUIAccessCapabilityPresent() )
      goto LABEL_169;
    HaveUIAccessCapability = DoesPackageHaveUIAccessCapability(v26, v172);
    if ( HaveUIAccessCapability < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x1F92,
        v85,
        (const char *)(unsigned int)HaveUIAccessCapability,
        (int)&v179);
      goto LABEL_169;
    }
    if ( !v172[0] )
    {
LABEL_169:
      uExitCode = 50;
      v87 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_96;
      v88 = 51;
      goto LABEL_172;
    }
    v84 = v169;
    if ( v169 >= 3 )
    {
      v84 = v169 - 16;
      v169 -= 16;
    }
    v91 = v163 | 0x8000C;
    v163 |= 0x8000Cu;
  }
  LODWORD(hMem) = v168 & 1;
  if ( (v168 & 1) != 0 )
  {
LABEL_188:
    if ( (_DWORD)v84 )
      goto LABEL_190;
    goto LABEL_189;
  }
  if ( !(_DWORD)v84 )
  {
LABEL_189:
    if ( (v91 & 4) != 0 )
    {
LABEL_192:
      if ( (_DWORD)hMem )
      {
        if ( (unsigned int)v84 <= 1 )
        {
          v91 |= 0x200u;
          v163 = v91;
        }
        v169 = 2;
        v179 = 6;
      }
      if ( (v168 & 0x10) != 0 )
        v163 = v91 | 0x800;
      if ( v149 || !(_DWORD)v194 )
      {
        v95 = v25;
        if ( v24 )
          v95 = v24;
        v93 = AiBuildEXEParams(
                v95,
                hObject,
                v24,
                v192[0],
                v25,
                (unsigned int)v174,
                0,
                v185,
                (struct _CONSENTUI_PARAM_HEADER **)&v197);
        v54 = v146;
      }
      else
      {
        v54 = v146;
        v92 = v25;
        v179 = 8;
        if ( v24 )
          v92 = v24;
        v93 = AiBuildPackagedAppParams(
                v92,
                v192[0],
                v25,
                (unsigned int)v174,
                v185,
                (wchar_t *)packageFamilyName,
                v146,
                (struct _CONSENTUI_PARAM_HEADER **)&v197);
      }
      uExitCode = v93;
      if ( v93 )
        goto LABEL_96;
      v94 = v197;
      *((_DWORD *)v197 + 13) = v177;
      uExitCode = AiCheckLUA(
                    v169,
                    &v163,
                    (unsigned int)v179,
                    TargetHandle,
                    v94,
                    v204,
                    hProfile,
                    v173,
                    v165,
                    Destination,
                    &v211);
      LODWORD(v68) = uExitCode;
      if ( uExitCode )
      {
        v69 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_96;
        v70 = 53;
        goto LABEL_132;
      }
      v96 = v211;
      if ( v211 )
      {
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShadowAdmin>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_ShadowAdmin>::GetImpl'::`2'::impl) )
        {
          v164 &= 0xFFFFFFFC;
          v176 = v164;
        }
        v97 = v163 | 1;
        TargetHandle = v96;
      }
      else
      {
        v97 = v163;
      }
      v167 = v97;
LABEL_221:
      if ( (unsigned __int8)IsMountVolumeForAppPackagePresent() )
      {
        token_information = wil::get_token_information_nothrow<_TOKEN_USER,0>(&Block, TargetHandle);
        AppModelIdentityActivationProperties = token_information;
        if ( token_information < 0 )
        {
          v49 = token_information;
          goto LABEL_70;
        }
        v174 = 0;
        v54 = v146;
        v100 = ParseAppUserModelId(v146, v99, &v174);
        AppModelIdentityActivationProperties = v100;
        if ( v100 < 0 )
        {
          v101 = WIN32_FROM_HRESULT(v100);
LABEL_226:
          uExitCode = v101;
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v174);
          goto LABEL_96;
        }
        v102 = PsmCreateKey(v26, v174, v232, &v202);
        if ( v102 < 0 )
        {
          v101 = WIN32_FROM_NTSTATUS(v102);
          goto LABEL_226;
        }
        v103 = MountVolumeForAppPackage(v232, *(_QWORD *)Block, v173);
        v104 = v103;
        if ( v103 < 0 )
        {
          uExitCode = WIN32_FROM_NTSTATUS(v103);
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v106 = L"NULL";
            if ( v26 )
              v106 = v26;
            if ( v24 )
              v29 = v24;
            WPP_SF_DSS(*((_QWORD *)WPP_GLOBAL_Control + 2), 54, v105, v104, (__int64)v29, (__int64)v106);
          }
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v174);
          goto LABEL_95;
        }
        v162 = 1;
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v174);
      }
      v107 = ShouldAdjustActivationToken();
      v108 = v107;
      v148 = v107;
      if ( v149 || (v177 = 0, (a14 & 6) != 0) )
        v177 = 1;
      v170 = 1;
      if ( !v166 )
      {
        *(_QWORD *)&v227 = TargetHandle;
        *((_QWORD *)&v227 + 1) = hSourceHandle;
        HIDWORD(v229) = v158;
        *(_QWORD *)&v228 = v26;
        *((_QWORD *)&v228 + 1) = v24;
        v109 = PrepareAppXActivation(&v227, &v191);
        AppModelIdentityActivationProperties = v109;
        if ( v109 < 0 )
        {
          uExitCode = WIN32_FROM_HRESULT(v109);
          v61 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            goto LABEL_95;
          v62 = 55;
          goto LABEL_106;
        }
        if ( *(_DWORD *)(v191 + 8) )
          Src = *(unsigned __int16 **)(v191 + 24);
LABEL_278:
        if ( v108 )
        {
          v170 = 4;
          LastError = RpcImpersonateClient(0);
          if ( LastError )
            goto LABEL_55;
          if ( v184 )
            v116 = *(_QWORD *)(v184 + 56);
          else
            v116 = 0;
          v54 = v146;
          LOBYTE(v115) = v158;
          LOBYTE(v114) = v150;
          LOBYTE(lpValue) = 0;
          LOBYTE(v143) = v151;
          LOBYTE(v142) = v152;
          LOBYTE(v141) = v153;
          LOBYTE(v139) = v154;
          LOBYTE(dwOptions) = v155;
          LOBYTE(bInheritHandle) = v156;
          LOBYTE(dwDesiredAccess) = v157;
          uExitCode = AdjustActivationToken(
                        TargetHandle,
                        v166,
                        v114,
                        v115,
                        dwDesiredAccess,
                        bInheritHandle,
                        dwOptions,
                        v139,
                        v141,
                        v142,
                        v143,
                        lpValue,
                        v26,
                        v146,
                        v213,
                        v212,
                        v116,
                        &v214);
          RpcRevertToSelf();
          LODWORD(v68) = uExitCode;
          if ( uExitCode )
          {
            v69 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
              goto LABEL_96;
            v70 = 57;
            goto LABEL_132;
          }
          NtClose(TargetHandle);
          v117 = v214;
          TargetHandle = v214;
        }
        else
        {
          v117 = TargetHandle;
        }
        if ( v166 - 1 <= 2 )
        {
          v118 = BeginCreatingHeliumContainerForDesktopAppXActivation(v117, v184);
          v117 = TargetHandle;
          v28 = v118;
        }
        v119 = v164 & 4;
        v120 = v148;
        v148 = -v148;
        v170 = 5;
        uExitCode = AiLaunchProcess(
                      Handle,
                      v117,
                      (char *)hObject,
                      v167,
                      v24,
                      v25,
                      v164 | 4,
                      (const unsigned __int16 *)v196,
                      v204,
                      v210,
                      v173,
                      (_WORD *)((unsigned __int64)v26 & -(__int64)v120),
                      a14,
                      v222,
                      a19,
                      Src,
                      v188);
        v68 = uExitCode;
        if ( uExitCode )
        {
          v69 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
            goto LABEL_95;
          v54 = v146;
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v70 = 58;
LABEL_132:
            v71 = v69[2];
            v72 = L"NULL";
            v140 = (struct _CONSENTUI_PARAM_HEADER **)v54;
            if ( v25 )
              v72 = v25;
            dwOptionsa = packageFamilyName;
            bInheritHandlea = (__int64)v72;
LABEL_135:
            if ( v24 )
              v29 = v24;
            WPP_SF_DSSSS(v71, v70, (_DWORD)v67, v68, (__int64)v29, bInheritHandlea, (__int64)dwOptionsa, (__int64)v140);
            goto LABEL_96;
          }
          goto LABEL_96;
        }
        v170 = 6;
        if ( v166 )
        {
          if ( v166 - 1 > 2 )
          {
            v121 = 0;
          }
          else
          {
            *(_DWORD *)(v184 + 40) = v164;
            v220 = *(_QWORD *)&v188->dwProcessId;
            AppModelIdentityActivationProperties = PostCreateProcessDesktopAppXActivation(
                                                     TargetHandle,
                                                     v184,
                                                     &v219,
                                                     v68);
            v121 = *(_DWORD *)(v184 + 16);
          }
        }
        else
        {
          *(_DWORD *)(v191 + 32) = v164;
          v220 = *(_QWORD *)&v188->dwProcessId;
          AppModelIdentityActivationProperties = PostCreateProcessAppXActivation(TargetHandle, v191, &v219, v68);
          v121 = *(_DWORD *)(v191 + 8);
        }
        if ( AppModelIdentityActivationProperties < 0 )
        {
          uExitCode = WIN32_FROM_HRESULT(AppModelIdentityActivationProperties);
          v61 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            goto LABEL_95;
          v62 = 59;
          goto LABEL_106;
        }
        if ( !v119 && !v121 )
        {
          v170 = 7;
          v122 = OpenThread(2u, 0, v188->dwThreadId);
          v218 = v122;
          if ( !v122 )
          {
            v123 = GetLastError();
            uExitCode = v123;
            v67 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
              goto LABEL_95;
            v54 = v146;
            if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
              goto LABEL_96;
            v70 = 60;
LABEL_310:
            v140 = (struct _CONSENTUI_PARAM_HEADER **)v54;
            v124 = L"NULL";
            if ( v25 )
              v124 = v25;
            dwOptionsa = packageFamilyName;
            bInheritHandlea = (__int64)v124;
            LODWORD(v68) = v123;
            v71 = v67[2];
            goto LABEL_135;
          }
          if ( ResumeThread(v122) == -1 )
          {
            v123 = GetLastError();
            uExitCode = v123;
            v67 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
              goto LABEL_95;
            v54 = v146;
            if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
              goto LABEL_96;
            v70 = 61;
            goto LABEL_310;
          }
        }
        v54 = v146;
        uExitCode = 0;
        goto LABEL_96;
      }
      if ( v166 - 1 > 2 )
        goto LABEL_278;
      hProfile = 0;
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShadowAdmin>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_ShadowAdmin>::GetImpl'::`2'::impl) )
      {
        if ( (v167 & 0x21) != 1 && ((v167 & 0x8000000) == 0 || !(unsigned int)LUAIsShadowAdminEnabled()) )
          goto LABEL_262;
      }
      else if ( (v167 & 0x21) != 1 )
      {
        goto LABEL_262;
      }
      uExitCode = AipLoadUserProfile(TargetHandle, &hProfile);
      if ( uExitCode )
        goto LABEL_255;
      ImpersonateLoggedOnUser(TargetHandle);
      v165 = 0;
      if ( (int)RegisterAppXPackageIfNecessary2(0, v146, 0, 0, &v165) < 0 )
      {
        uExitCode = 15669;
        RevertToSelf();
        goto LABEL_255;
      }
      RevertToSelf();
LABEL_262:
      *(_QWORD *)&v224 = TargetHandle;
      *((_QWORD *)&v224 + 1) = hSourceHandle;
      v110 = 0;
      *(_QWORD *)&v225 = v26;
      *((_QWORD *)&v225 + 1) = v24;
      if ( v166 == 2 )
        v110 = 8;
      LODWORD(v226) = v177 | v226 | (2 * v108) | v110;
      v111 = PrepareDesktopAppXActivation(&v224, &v184);
      AppModelIdentityActivationProperties = v111;
      if ( v111 >= 0 )
      {
        if ( v147 )
          *(_DWORD *)(v184 + 16) = 0;
        if ( *(_DWORD *)(v184 + 16) )
          Src = *(unsigned __int16 **)(v184 + 32);
        if ( hProfile )
        {
          UnloadUserProfile(TargetHandle, hProfile);
          hProfile = 0;
        }
        goto LABEL_278;
      }
      uExitCode = WIN32_FROM_HRESULT(v111);
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v113 = L"NULL";
        if ( v26 )
          v113 = v26;
        if ( v24 )
          v29 = v24;
        WPP_SF_DSS(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          56,
          v112,
          AppModelIdentityActivationProperties,
          (__int64)v29,
          (__int64)v113);
      }
LABEL_255:
      if ( hProfile )
        UnloadUserProfile(TargetHandle, hProfile);
      goto LABEL_95;
    }
LABEL_190:
    if ( !(unsigned int)AiIsElevationAllowedForSession(v173) )
    {
LABEL_66:
      uExitCode = 50;
      goto LABEL_95;
    }
    LODWORD(v84) = v169;
    goto LABEL_192;
  }
  v172[0] = 0;
  if ( (unsigned __int8)IsDoesPackageHaveElevationCapabilityPresent(v84)
    && (int)DoesPackageHaveElevationCapability(v26, v172) >= 0
    && v172[0] )
  {
    LODWORD(v200) = -1;
    LODWORD(v201) = v180;
    v187 = 0;
    v167 = uExitCode;
    LUATelemetry::CentennialElevation<long,unsigned short * &,unsigned short const * &,unsigned long &,unsigned long &,unsigned long &,unsigned long &,bool &,int &,unsigned long,int,int,char (&)[129]>(
      (unsigned int)&v167,
      (unsigned int)&v186,
      (unsigned int)&lpFileName,
      (unsigned int)&uExitCode,
      (__int64)&v182,
      (__int64)&v176,
      (__int64)&a14,
      (__int64)&v147,
      (__int64)&v181,
      (__int64)&v201,
      (__int64)&v200,
      (__int64)&v187,
      Destination);
    LODWORD(v84) = v169;
    goto LABEL_188;
  }
  uExitCode = 50;
  v87 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
    goto LABEL_95;
  v54 = v146;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v88 = 52;
LABEL_172:
    v89 = v87[2];
    v90 = L"NULL";
    if ( v25 )
      v90 = v25;
    if ( v24 )
      LODWORD(v29) = (_DWORD)v24;
    WPP_SF_SSSS(v89, v88, v85, (_DWORD)v29, (__int64)v90, (__int64)packageFamilyName, (__int64)v54);
  }
LABEL_96:
  QueryPerformanceCounter(&v215);
  v189 = 1;
  v210 = (struct _APPINFO_STARTUPINFO *)(1000 * (v215.QuadPart - PerformanceCount.QuadPart) / Frequency.QuadPart);
  LODWORD(hMem) = v180;
  v55 = uExitCode;
  if ( uExitCode == 1223 )
  {
    v165 = 0;
  }
  else
  {
    if ( (int)uExitCode > 0 )
      v55 = (unsigned __int16)uExitCode | 0x80070000;
    v165 = v55;
  }
  LUATelemetry::CentennialElevation<long,unsigned short * &,unsigned short const * &,unsigned long &,unsigned long &,unsigned long &,unsigned long &,bool &,int &,unsigned long,__int64 &,int,char (&)[129]>(
    (unsigned int)&v165,
    (unsigned int)&v186,
    (unsigned int)&lpFileName,
    (unsigned int)&uExitCode,
    (__int64)&v182,
    (__int64)&v176,
    (__int64)&a14,
    (__int64)&v147,
    (__int64)&v181,
    (__int64)&hMem,
    (__int64)&v210,
    (__int64)&v189,
    Destination);
  if ( uExitCode )
  {
    v125 = v170;
    if ( v170 != 1 && v170 != 6 )
    {
      if ( (int)uExitCode > 0 )
        AppModelIdentityActivationProperties = (unsigned __int16)uExitCode | 0x80070000;
      else
        AppModelIdentityActivationProperties = uExitCode;
    }
    v126 = AipJustFileName(v24);
    v127 = packageFamilyName;
    if ( v26 )
      v127 = v26;
    AipLogDesktopAppXProcessStartFailure(
      v125,
      (unsigned int)AppModelIdentityActivationProperties,
      v127,
      v126,
      v54,
      L"[LaunchProcess]");
    v128 = v188;
  }
  else
  {
    v129 = AipJustFileName(v24);
    v130 = v54;
    v128 = v188;
    AipLogDesktopAppXProcessStartSuccess(v188->dwProcessId, v26, v129, v130, L"[LaunchProcess]");
  }
  if ( hObject != (HANDLE)-1LL )
    CloseHandle(hObject);
  if ( v24 != v205 )
    LocalFree(v24);
  if ( v25 != v206 )
    LocalFree(v25);
  if ( v196 != v207 )
    LocalFree(v196);
  if ( v26 )
    LocalFree(v26);
  if ( TargetHandle )
  {
    NtClose(TargetHandle);
    TargetHandle = 0;
  }
  if ( hSourceHandle )
    NtClose(hSourceHandle);
  if ( Handle )
    NtClose(Handle);
  if ( v184 )
    FreeDesktopAppXLaunchContext();
  if ( v191 )
    FreeAppXLaunchContext();
  if ( v218 )
    CloseHandle(v218);
  if ( hToken )
    CloseHandle(hToken);
  if ( uExitCode )
  {
    dwProcessId = v128->dwProcessId;
    if ( dwProcessId )
    {
      v132 = OpenProcess(1u, 0, dwProcessId);
      v133 = v132;
      if ( v132 )
      {
        TerminateProcess(v132, uExitCode);
        CloseHandle(v133);
      }
    }
    if ( v162 )
      UnmountVolumeForAppPackage(v232, *(_QWORD *)Block, v173);
  }
  if ( v197 )
    LocalFree(v197);
  RundownHeliumContainerForDesktopAppXActivation(v28);
  RpcAsyncCompleteCall(pAsync, &uExitCode);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 62, &WPP_e8c8bde4cfdd31ad7ca53050940b7a3e_Traceguids, uExitCode);
  wil::ActivityThreadWatcher::~ActivityThreadWatcher((wil::ActivityThreadWatcher *)v230);
  if ( Block )
    operator delete(Block);
}

```

## disassembly

```asm
0x18002b828  push    rbp
0x18002b82a  push    rbx
0x18002b82b  push    rsi
0x18002b82c  push    rdi
0x18002b82d  push    r12
0x18002b82f  push    r13
0x18002b831  push    r14
0x18002b833  push    r15
0x18002b835  lea     rbp, [rsp-498h]
0x18002b83d  sub     rsp, 5A8h
0x18002b844  mov     rax, cs:__security_cookie
0x18002b84b  xor     rax, rsp
0x18002b84e  mov     [rbp+4D0h+var_50], rax
0x18002b855  mov     rax, [rbp+4D0h+arg_38]
0x18002b85c  xorps   xmm0, xmm0
0x18002b85f  mov     rdi, [rbp+4D0h+Source]
0x18002b866  xorps   xmm1, xmm1
0x18002b869  mov     [rbp+4D0h+var_400], rax
0x18002b870  mov     r14, r8
0x18002b873  mov     rax, [rbp+4D0h+arg_48]
0x18002b87a  mov     r12, r9
0x18002b87d  mov     [rbp+4D0h+packageFamilyName], rax
0x18002b881  mov     rax, [rbp+4D0h+arg_50]
0x18002b888  mov     [rbp+4D0h+var_548], rax
0x18002b88c  mov     eax, [rbp+4D0h+arg_20]
0x18002b892  mov     [rbp+4D0h+var_510], eax
0x18002b895  mov     [rbp+4D0h+var_4B0], eax
0x18002b898  mov     eax, [rbp+4D0h+arg_28]
0x18002b89e  mov     [rbp+4D0h+var_520], eax
0x18002b8a1  mov     [rbp+4D0h+var_4D8], eax
0x18002b8a4  mov     rax, [rbp+4D0h+arg_40]
0x18002b8ab  mov     [rbp+4D0h+var_3D0], rax
0x18002b8b2  mov     rax, [rbp+4D0h+arg_58]
0x18002b8b9  mov     [rbp+4D0h+hProfile], rax
0x18002b8bd  mov     eax, [rbp+4D0h+arg_60]
0x18002b8c3  mov     [rbp+4D0h+var_51C], eax
0x18002b8c6  mov     rax, [rbp+4D0h+arg_70]
0x18002b8cd  mov     [rbp+4D0h+var_368], rax
0x18002b8d4  mov     rax, [rbp+4D0h+arg_80]
0x18002b8db  mov     [rbp+4D0h+var_3B8], rax
0x18002b8e2  mov     rax, [rbp+4D0h+arg_88]
0x18002b8e9  mov     [rbp+4D0h+var_3C0], rax
0x18002b8f0  mov     rax, [rbp+4D0h+arg_A0]
0x18002b8f7  mov     [rbp+4D0h+var_370], rax
0x18002b8fe  mov     rax, [rbp+4D0h+arg_A8]
0x18002b905  mov     qword ptr [rbp+4D0h+var_4F8], rax
0x18002b909  mov     rax, [rbp+4D0h+arg_B0]
0x18002b910  mov     [rbp+4D0h+pAsync], rcx
0x18002b917  mov     rcx, [rbp+4D0h+arg_30]
0x18002b91e  mov     [rbp+4D0h+var_480], rax
0x18002b922  xor     eax, eax
0x18002b924  mov     [rbp+4D0h+var_3E8], rcx
0x18002b92b  mov     [rbp+4D0h+var_440], rcx
0x18002b932  xor     ecx, ecx
0x18002b934  or      [rbp+4D0h+hObject], 0FFFFFFFFFFFFFFFFh
0x18002b93c  mov     r13d, ecx
0x18002b93f  mov     [rbp+4D0h+var_378], rax
0x18002b946  mov     r15d, ecx
0x18002b949  mov     [rbp+4D0h+var_338], rax
0x18002b950  mov     [rbp+4D0h+var_310], rax
0x18002b957  mov     [rbp+4D0h+var_3F0], r9
0x18002b95e  mov     [rbp+4D0h+var_3F8], r8
0x18002b965  mov     [rbp+4D0h+var_450], rdx
0x18002b96c  mov     [rbp+4D0h+lpFileName], r8
0x18002b970  mov     [rbp+4D0h+hMem], r9
0x18002b974  mov     [rbp+4D0h+var_4F0], ecx
0x18002b977  mov     [rbp+4D0h+var_514], ecx
0x18002b97a  mov     [rbp+4D0h+var_524], ecx
0x18002b97d  mov     [rbp+4D0h+var_428], ecx
0x18002b983  mov     [rbp+4D0h+var_50C], ecx
0x18002b986  mov     [rbp+4D0h+var_490], rcx
0x18002b98a  mov     [rbp+4D0h+var_3B0], rcx
0x18002b991  mov     [rbp+4D0h+Handle], rcx
0x18002b998  mov     [rbp+4D0h+hSourceHandle], rcx
0x18002b99c  mov     [rbp+4D0h+var_3C8], rcx
0x18002b9a3  mov     [rbp+4D0h+TargetHandle], rcx
0x18002b9a7  mov     [rbp+4D0h+var_390], rcx
0x18002b9ae  mov     [rbp+4D0h+hToken], rcx
0x18002b9b5  mov     [rbp+4D0h+var_488], ecx
0x18002b9b8  mov     [rbp+4D0h+var_4E8], rcx
0x18002b9bc  mov     [rbp+4D0h+var_498], ecx
0x18002b9bf  mov     [rbp+4D0h+var_4D0], ecx
0x18002b9c2  mov     [rbp+4D0h+var_458], ecx
0x18002b9c5  mov     [rbp+4D0h+var_4C0], 6
0x18002b9cc  mov     [rbp+4D0h+var_438], rcx
0x18002b9d3  movups  [rbp+4D0h+var_388], xmm0
0x18002b9da  mov     [rbp+4D0h+var_4A0], rcx
0x18002b9de  movups  [rbp+4D0h+var_358], xmm1
0x18002b9e5  mov     [rbp+4D0h+var_468], rcx
0x18002b9e9  movups  [rbp+4D0h+var_348], xmm1
0x18002b9f0  mov     [rbp+4D0h+var_508], ecx
0x18002b9f3  movups  [rbp+4D0h+var_330], xmm0
0x18002b9fa  mov     [rbp+4D0h+var_408], rcx
0x18002ba01  movups  [rbp+4D0h+var_320], xmm0
0x18002ba08  mov     ebx, ecx
0x18002ba0a  mov     [rbp+4D0h+var_518], ecx
0x18002ba0d  mov     [rbp+4D0h+var_4B8], ecx
0x18002ba10  mov     esi, 1D0h
0x18002ba15  mov     [rbp+4D0h+var_4BC], ecx
0x18002ba18  mov     r8d, esi; Size
0x18002ba1b  mov     [rbp+4D0h+var_540], cl
0x18002ba1e  xor     edx, edx; Val
0x18002ba20  mov     [rbp+4D0h+var_536], cl
0x18002ba23  mov     [rbp+4D0h+var_53E], cl
0x18002ba26  mov     [rbp+4D0h+var_537], cl
0x18002ba29  mov     [rbp+4D0h+var_538], cl
0x18002ba2c  mov     [rbp+4D0h+var_539], cl
0x18002ba2f  mov     [rbp+4D0h+var_53F], cl
0x18002ba32  mov     [rbp+4D0h+var_53C], cl
0x18002ba35  lea     rcx, [rbp+4D0h+var_220]; void *
0x18002ba3c  call    memset_0
0x18002ba41  mov     [rbp+4D0h+var_410], esi
0x18002ba47  lea     rcx, [rbp+4D0h+Destination]; void *
0x18002ba4e  xor     esi, esi
0x18002ba50  xor     edx, edx; Val
0x18002ba52  mov     r8d, 81h; Size
0x18002ba58  mov     [rbp+4D0h+Block], rsi
0x18002ba5f  mov     [rbp+4D0h+var_526], sil
0x18002ba63  call    memset_0
0x18002ba68  lea     rcx, [rbp+4D0h+PerformanceCount]; lpPerformanceCount
0x18002ba6f  mov     qword ptr [rbp+4D0h+Frequency], rsi
0x18002ba76  mov     qword ptr [rbp+4D0h+PerformanceCount], rsi
0x18002ba7d  mov     qword ptr [rbp+4D0h+var_3A8], rsi
0x18002ba84  call    cs:__imp_QueryPerformanceCounter
0x18002ba8b  nop     dword ptr [rax+rax+00h]
0x18002ba90  lea     rcx, [rbp+4D0h+Frequency]; lpFrequency
0x18002ba97  call    cs:__imp_QueryPerformanceFrequency
0x18002ba9e  nop     dword ptr [rax+rax+00h]
0x18002baa3  mov     rax, [rbp+4D0h+var_548]
0x18002baa7  lea     rsi, aNull_0; "NULL"
0x18002baae  test    rax, rax
0x18002bab1  mov     r8, rax
0x18002bab4  mov     rax, [rbp+4D0h+packageFamilyName]
0x18002bab8  mov     r11, r14
0x18002babb  cmovz   r8, rsi
0x18002babf  lea     r11, [rbp+4D0h+Destination]
0x18002bac6  test    rax, rax
0x18002bac9  mov     [rsp+5E0h+var_578], r11
0x18002bace  mov     qword ptr [rsp+5E0h+var_580], r8
0x18002bad3  mov     r9, rax
0x18002bad6  mov     rax, [rbp+4D0h+var_400]
0x18002badd  cmovz   r9, rsi
0x18002bae1  test    rax, rax
0x18002bae4  mov     [rsp+5E0h+lpValue], r9
0x18002bae9  mov     r10, rax
0x18002baec  mov     qword ptr [rbp+4D0h+var_460], r8
0x18002baf0  mov     rax, [rbp+4D0h+var_3E8]
0x18002baf7  lea     r8, aHwndXDwclientf_0; "++. hwnd = %x dwClientFlags = %x dwCrea"...
0x18002bafe  mov     rdx, rax
0x18002bb01  mov     [rbp+4D0h+var_418], r9
0x18002bb08  mov     r9d, dword ptr [rbp+4D0h+hProfile]
0x18002bb0c  cmovz   r10, rsi
0x18002bb10  test    rax, rax
0x18002bb13  mov     [rbp+4D0h+var_420], r10
0x18002bb1a  mov     rax, r12
0x18002bb1d  mov     rcx, rax
0x18002bb20  cmovz   rdx, rsi
0x18002bb24  mov     qword ptr [rsp+5E0h+var_590], rdx
0x18002bb29  test    rax, rax
0x18002bb2c  mov     rax, r14
0x18002bb2f  lea     rdx, aAiplaunchproce; "AipLaunchProcessWithIdentityHelper"
0x18002bb36  cmovz   rcx, rsi
0x18002bb3a  test    r14, r14
0x18002bb3d  mov     [rsp+5E0h+var_598], rcx
0x18002bb42  mov     ecx, [rbp+4D0h+var_520]
0x18002bb45  cmovz   rax, rsi
0x18002bb49  mov     [rsp+5E0h+var_5A0], rax
0x18002bb4e  mov     eax, [rbp+4D0h+var_51C]
0x18002bb51  mov     [rsp+5E0h+var_5A8], r10
0x18002bb56  mov     [rsp+5E0h+dwOptions], eax
0x18002bb5a  mov     eax, [rbp+4D0h+var_510]
0x18002bb5d  mov     [rsp+5E0h+bInheritHandle], ecx
0x18002bb61  lea     rcx, [rbp+4D0h+var_300]
0x18002bb68  mov     [rsp+5E0h+dwDesiredAccess], eax
0x18002bb6c  call    ?WatchCurrentThread@LUATelemetry@@SA?AVActivityThreadWatcher@wil@@PEBD0ZZ; LUATelemetry::WatchCurrentThread(char const *,char const *,...)
0x18002bb71  mov     rcx, cs:?g_pCentennialElevationTelemetryRateLimiter@@3V?$unique_ptr@VRateLimiter@@U?$default_delete@VRateLimiter@@@wistd@@@wistd@@A; this
0x18002bb78  test    rcx, rcx
0x18002bb7b  jz      loc_18002BC1F
0x18002bb81  call    ?RequestPermission@RateLimiter@@QEAAHXZ; RateLimiter::RequestPermission(void)
0x18002bb86  test    eax, eax
0x18002bb88  jz      loc_18002BC1F
0x18002bb8e  test    rdi, rdi
0x18002bb91  jnz     short loc_18002BC01
0x18002bb93  mov     ecx, 90h; Size
0x18002bb98  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002bb9d  xor     r14d, r14d
0x18002bba0  test    rax, rax
0x18002bba3  jz      short loc_18002BBB2
0x18002bba5  mov     rcx, rax
0x18002bba8  call    ??0TraceLoggingCorrelationVector@@QEAA@UTraceLoggingCorrelationVectorV2_t@@@Z; TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(TraceLoggingCorrelationVectorV2_t)
0x18002bbad  mov     rdi, rax
0x18002bbb0  jmp     short loc_18002BBB5
0x18002bbb2  mov     rdi, r14
0x18002bbb5  mov     rdx, r14
0x18002bbb8  lock xadd [rdi+88h], rdx; unsigned __int64
0x18002bbc1  lea     r8, [rbp+4D0h+Destination]; char *
0x18002bbc8  mov     rcx, rdi; this
0x18002bbcb  call    ?ToStringImpl@TraceLoggingCorrelationVector@@AEAA_N_KPEAD@Z; TraceLoggingCorrelationVector::ToStringImpl(unsigned __int64,char *)
0x18002bbd0  test    rdi, rdi
0x18002bbd3  jz      short loc_18002BBDD
0x18002bbd5  mov     rcx, rdi; Block
0x18002bbd8  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002bbdd  mov     eax, [rbp+4D0h+var_524]
0x18002bbe0  mov     r10d, [rbp+4D0h+var_4B0]
0x18002bbe4  mov     r11d, [rbp+4D0h+var_4D8]
0x18002bbe8  mov     r13, [rbp+4D0h+var_490]
0x18002bbec  mov     r14, [rbp+4D0h+lpFileName]
0x18002bbf0  mov     r12, [rbp+4D0h+hMem]
0x18002bbf4  mov     [rbp+4D0h+var_514], eax
0x18002bbf7  mov     [rbp+4D0h+var_510], r10d
0x18002bbfb  mov     [rbp+4D0h+var_520], r11d
0x18002bbff  jmp     short loc_18002BC27
0x18002bc01  mov     edx, 81h; SizeInBytes
0x18002bc06  lea     rcx, [rbp+4D0h+Destination]; Destination
0x18002bc0d  mov     r9d, edx; MaxCount
0x18002bc10  mov     r8, rdi; Source
0x18002bc13  call    cs:__imp_strncpy_s
0x18002bc1a  nop     dword ptr [rax+rax+00h]
0x18002bc1f  mov     r10d, [rbp+4D0h+var_510]
0x18002bc23  mov     r11d, [rbp+4D0h+var_520]
0x18002bc27  mov     rax, [rbp+4D0h+var_480]
0x18002bc2b  xorps   xmm0, xmm0
0x18002bc2e  xor     ecx, ecx
0x18002bc30  movups  xmmword ptr [rax], xmm0
0x18002bc33  mov     [rax+10h], rcx
0x18002bc37  mov     r8, cs:WPP_GLOBAL_Control
0x18002bc3e  lea     rax, WPP_GLOBAL_Control
0x18002bc45  xor     edi, edi
0x18002bc47  cmp     r8, rax
0x18002bc4a  jz      loc_18002BCD6
0x18002bc50  test    byte ptr [r8+1Ch], 1
0x18002bc55  jz      short loc_18002BCD6
0x18002bc57  mov     rax, [rbp+4D0h+var_440]
0x18002bc5e  lea     r9, [rbp+4D0h+Destination]
0x18002bc65  mov     [rsp+5E0h+var_578], r9
0x18002bc6a  test    rax, rax
0x18002bc6d  mov     r9, qword ptr [rbp+4D0h+var_460]
0x18002bc71  mov     rdx, rsi
0x18002bc74  mov     qword ptr [rsp+5E0h+var_580], r9
0x18002bc79  cmovnz  rdx, rax
0x18002bc7d  mov     r9, [rbp+4D0h+var_418]
0x18002bc84  test    r12, r12
0x18002bc87  mov     [rsp+5E0h+lpValue], r9
0x18002bc8c  mov     rcx, rsi
0x18002bc8f  mov     r9d, dword ptr [rbp+4D0h+hProfile]
0x18002bc93  cmovnz  rcx, r12
0x18002bc97  mov     qword ptr [rsp+5E0h+var_590], rdx
0x18002bc9c  test    r14, r14
0x18002bc9f  mov     [rsp+5E0h+var_598], rcx
0x18002bca4  mov     rax, rsi
0x18002bca7  mov     rcx, [r8+10h]
0x18002bcab  cmovnz  rax, r14
0x18002bcaf  mov     [rsp+5E0h+var_5A0], rax
0x18002bcb4  mov     rax, [rbp+4D0h+var_420]
0x18002bcbb  mov     [rsp+5E0h+var_5A8], rax
0x18002bcc0  mov     eax, [rbp+4D0h+var_51C]
0x18002bcc3  mov     [rsp+5E0h+dwOptions], eax
0x18002bcc7  mov     [rsp+5E0h+bInheritHandle], r11d
0x18002bccc  mov     [rsp+5E0h+dwDesiredAccess], r10d
0x18002bcd1  call    WPP_SF_DDDDSSSSSSs
0x18002bcd6  test    byte ptr [rbp+4D0h+arg_68], 1
0x18002bcdd  jz      short loc_18002BCF2
0x18002bcdf  lea     rcx, AppInfo_PerfTrack_Elevation_PackagedApp_Start; struct _EVENT_DESCRIPTOR *
0x18002bce6  call    ?AiLogPerfTrackEvent@@YAKPEBU_EVENT_DESCRIPTOR@@@Z; AiLogPerfTrackEvent(_EVENT_DESCRIPTOR const *)
0x18002bceb  mov     [rbp+4D0h+var_4D0], eax
0x18002bcee  mov     [rbp+4D0h+var_540], 1
0x18002bcf2  test    r14, r14
0x18002bcf5  jz      loc_18002C09A
0x18002bcfb  cmp     [rbp+4D0h+packageFamilyName], rbx
0x18002bcff  jz      loc_18002C09A
0x18002bd05  cmp     [rbp+4D0h+var_548], rdi
0x18002bd09  jz      loc_18002C09A
0x18002bd0f  mov     rcx, r14; unsigned __int16 *
0x18002bd12  call    ?AipJustFileName@@YAPEBGPEBG@Z; AipJustFileName(ushort const *)
0x18002bd17  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002bd1b  mov     rdi, rax
0x18002bd1e  xor     ecx, ecx
0x18002bd20  inc     rdi
0x18002bd23  cmp     [r14+rdi*2], cx
0x18002bd28  jnz     short loc_18002BD20
0x18002bd2a  mov     qword ptr [rbp+4D0h+var_460], rdi
0x18002bd2e  test    r12, r12
0x18002bd31  jz      short loc_18002BD43
0x18002bd33  inc     rax
0x18002bd36  cmp     [r12+rax*2], cx
0x18002bd3b  jnz     short loc_18002BD33
0x18002bd3d  mov     [rbp+4D0h+var_4E8], rax
0x18002bd41  jmp     short loc_18002BD47
0x18002bd43  mov     rax, [rbp+4D0h+var_4E8]
0x18002bd47  mov     ecx, 7FFFh
0x18002bd4c  cmp     rdi, rcx
0x18002bd4f  ja      loc_18002C09A
0x18002bd55  cmp     rax, rcx
0x18002bd58  ja      loc_18002C09A
0x18002bd5e  mov     ecx, [rbp+4D0h+arg_68]
0x18002bd64  mov     eax, ecx
0x18002bd66  and     eax, 120h
0x18002bd6b  cmp     eax, 100h
0x18002bd70  jz      loc_18002C09A
0x18002bd76  mov     eax, ecx
  ... truncated ...
```
