# AipLaunchProcessWithIdentityHelper(_RPC_ASYNC_STATE *,void *,ushort const *,ushort *,ulong,ulong,ushort const *,ushort const *,_APPINFO_STARTUPINFO *,ushort const *,ushort const *,unsigned __int64,ulong,ulong,void *,unsigned __int64,unsigned __int64 *,_GUID *,unsigned __int64,char const *,int *,UACPROMPT_POLICY *,_APPINFO_PROCESS_INFORMATION *)

- ea: `0x18002a1d8`
- end: `0x18002beae`
- name: `?AipLaunchProcessWithIdentityHelper@@YAXPEAU_RPC_ASYNC_STATE@@PEAXPEBGPEAGKK22PEAU_APPINFO_STARTUPINFO@@22_KKK15PEA_KPEAU_GUID@@5PEBDPEAHPEAW4UACPROMPT_POLICY@@PEAU_APPINFO_PROCESS_INFORMATION@@@Z`
- size: `7382`
- prototype: `void __fastcall(struct _RPC_ASYNC_STATE *, void *, const unsigned __int16 *, unsigned __int16 *, unsigned int, unsigned int, const unsigned __int16 *, const unsigned __int16 *, struct _APPINFO_STARTUPINFO *, const unsigned __int16 *, const unsigned __int16 *, unsigned __int64, unsigned int, unsigned int, void *, unsigned __int64, unsigned __int64 *, struct _GUID *, unsigned __int64, const char *Source, int *, enum UACPROMPT_POLICY *, struct _APPINFO_PROCESS_INFORMATION *)`
- caller_count: `2`
- callee_count: `59`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18003a8b0`
- `0x18003b900`

## callees

- `0x18000a1f0`
- `0x18000a230`
- `0x18000c390`
- `0x18000cf00`
- `0x18000f24c`
- `0x18001107c`
- `0x1800115ec`
- `0x18001166c`
- `0x180011ff8`
- `0x180012a14`
- `0x180012cdc`
- `0x180014da0`
- `0x180016a40`
- `0x180016da4`
- `0x1800182bc`
- `0x1800192e8`
- `0x18001980c`
- `0x180019b18`
- `0x18001afdc`
- `0x18001b494`
- `0x18001b4a0`
- `0x18001c434`
- `0x18001c488`
- `0x18001d2e4`
- `0x18001d4c8`
- `0x180022b74`
- `0x180022bb0`
- `0x1800234a0`
- `0x180023e14`
- `0x18002487c`
- `0x180026058`
- `0x180026144`
- `0x180026de4`
- `0x1800271bc`
- `0x180027224`
- `0x180029110`
- `0x180029c54`
- `0x18002a1d8`
- `0x18002beb4`
- `0x180033538`
- `0x180035db8`
- `0x180036054`
- `0x180038670`
- `0x1800393ac`
- `0x1800393e0`
- `0x18003944c`
- `0x180039e84`
- `0x18003bb28`
- `0x18003bfc4`
- `0x18003c09c`

## import_xrefs

- `msvcrt!strncpy_s` at `0x18002a5c0`
- `msvcrt!strncpy_s` at `0x18002a5c0`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18002be2f`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18002be2f`
- `RPCRT4!RpcImpersonateClient` at `0x18002aab7`
- `RPCRT4!RpcImpersonateClient` at `0x18002ac90`
- `RPCRT4!RpcImpersonateClient` at `0x18002b76b`
- `RPCRT4!RpcImpersonateClient` at `0x18002aab7`
- `RPCRT4!RpcImpersonateClient` at `0x18002ac90`
- `RPCRT4!RpcImpersonateClient` at `0x18002b76b`
- `RPCRT4!RpcRevertToSelf` at `0x18002aada`
- `RPCRT4!RpcRevertToSelf` at `0x18002ad2e`
- `RPCRT4!RpcRevertToSelf` at `0x18002b81c`
- `RPCRT4!RpcRevertToSelf` at `0x18002aada`
- `RPCRT4!RpcRevertToSelf` at `0x18002ad2e`
- `RPCRT4!RpcRevertToSelf` at `0x18002b81c`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18002ada7`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18002b5f4`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18002ada7`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18002b5f4`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18002ae99`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18002af8d`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18002b631`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18002b64d`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18002ae99`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18002af8d`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18002b631`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18002b64d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a997`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002adb9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ae37`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002baa3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002bb1a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a997`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002adb9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ae37`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002baa3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002bb1a`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x18002bb09`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x18002bb09`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x18002bdbb`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x18002bdbb`
- `api-ms-win-core-processthreads-l1-1-0!OpenThread` at `0x18002ba8b`
- `api-ms-win-core-processthreads-l1-1-0!OpenThread` at `0x18002ba8b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002a94c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002a95b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002a94c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002a95b`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18002a987`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18002a987`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002bc79`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002bd6a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002bd82`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002bdca`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002bc79`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002bd6a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002bd82`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002bdca`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002bc91`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002bca9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002bcc8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002bcdc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002be09`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002bc91`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002bca9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002bcc8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002bcdc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002be09`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18002bda1`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18002bda1`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002ae21`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002ae21`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x18002a444`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x18002a444`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18002a431`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18002aa5b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18002a431`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18002aa5b`
- `api-ms-win-core-kernel32-private-l1-1-0!CheckElevation` at `0x18002aecb`
- `api-ms-win-core-kernel32-private-l1-1-0!CheckElevation` at `0x18002aecb`
- `api-ms-win-core-kernel32-private-l1-1-0!CheckElevationEnabled` at `0x18002ac55`
- `api-ms-win-core-kernel32-private-l1-1-0!CheckElevationEnabled` at `0x18002ac55`
- `api-ms-win-core-psm-key-l1-1-0!PsmCreateKey` at `0x18002b3f2`
- `api-ms-win-core-psm-key-l1-1-0!PsmCreateKey` at `0x18002b3f2`
- `ntdll!NtClose` at `0x18002b860`
- `ntdll!NtClose` at `0x18002bcf1`
- `ntdll!NtClose` at `0x18002bd0d`
- `ntdll!NtClose` at `0x18002bd25`
- `ntdll!NtClose` at `0x18002b860`
- `ntdll!NtClose` at `0x18002bcf1`
- `ntdll!NtClose` at `0x18002bd0d`
- `ntdll!NtClose` at `0x18002bd25`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18002a79f`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18002aaec`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18002a79f`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18002aaec`
- `USERENV!UnloadUserProfile` at `0x18002b5df`
- `USERENV!UnloadUserProfile` at `0x18002b747`
- `USERENV!UnloadUserProfile` at `0x18002b5df`
- `USERENV!UnloadUserProfile` at `0x18002b747`
- `ext-ms-win-desktopappx-l1-1-0!FreeDesktopAppXLaunchContext` at `0x18002bd3a`
- `ext-ms-win-desktopappx-l1-1-0!FreeDesktopAppXLaunchContext` at `0x18002bd3a`
- `ext-ms-win-desktopappx-l1-1-0!PostCreateProcessDesktopAppXActivation` at `0x18002ba12`
- `ext-ms-win-desktopappx-l1-1-0!PostCreateProcessDesktopAppXActivation` at `0x18002ba12`
- `ext-ms-win-desktopappx-l1-1-0!PrepareDesktopAppXActivation` at `0x18002b6a9`
- `ext-ms-win-desktopappx-l1-1-0!PrepareDesktopAppXActivation` at `0x18002b6a9`
- `ext-ms-win-desktopappx-l1-1-4!DoesPackageHaveElevationCapability` at `0x18002b0ae`
- `ext-ms-win-desktopappx-l1-1-4!DoesPackageHaveElevationCapability` at `0x18002b0ae`
- `ext-ms-win-desktopappx-l1-1-5!DoesPackageHaveUIAccessCapability` at `0x18002afd2`
- `ext-ms-win-desktopappx-l1-1-5!DoesPackageHaveUIAccessCapability` at `0x18002afd2`
- `ext-ms-win-desktopappx-l1-2-2!RundownHeliumContainerForDesktopAppXActivation` at `0x18002be18`
- `ext-ms-win-desktopappx-l1-2-2!RundownHeliumContainerForDesktopAppXActivation` at `0x18002be18`
- `ext-ms-win-desktopappx-l1-2-2!BeginCreatingHeliumContainerForDesktopAppXActivation` at `0x18002b88e`
- `ext-ms-win-desktopappx-l1-2-2!BeginCreatingHeliumContainerForDesktopAppXActivation` at `0x18002b88e`
- `ext-ms-win-desktopappx-l1-1-6!VerifyFileIsTrustedAndInPackage` at `0x18002af6e`
- `ext-ms-win-desktopappx-l1-1-6!VerifyFileIsTrustedAndInPackage` at `0x18002af6e`
- `ext-ms-win-appmodel-activation-l1-1-0!PostCreateProcessAppXActivation` at `0x18002b9c4`
- `ext-ms-win-appmodel-activation-l1-1-0!PostCreateProcessAppXActivation` at `0x18002b9c4`
- `ext-ms-win-appmodel-activation-l1-1-0!PrepareAppXActivation` at `0x18002b50b`
- `ext-ms-win-appmodel-activation-l1-1-0!PrepareAppXActivation` at `0x18002b50b`
- `ext-ms-win-appmodel-activation-l1-1-0!FreeAppXLaunchContext` at `0x18002bd4f`
- `ext-ms-win-appmodel-activation-l1-1-0!FreeAppXLaunchContext` at `0x18002bd4f`
- `ext-ms-win-appmodel-activation-l1-1-1!RegisterAppXPackageIfNecessary2` at `0x18002b61a`
- `ext-ms-win-appmodel-activation-l1-1-1!RegisterAppXPackageIfNecessary2` at `0x18002b61a`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x18002a937`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x18002a937`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrIsAllowedToActivateAsUser` at `0x18002a905`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrIsAllowedToActivateAsUser` at `0x18002a905`
- `ext-ms-win-core-app-package-volume-l1-1-0!MountVolumeForAppPackage` at `0x18002b420`
- `ext-ms-win-core-app-package-volume-l1-1-0!MountVolumeForAppPackage` at `0x18002b420`
- `ext-ms-win-core-app-package-volume-l1-1-0!UnmountVolumeForAppPackage` at `0x18002bdf1`
- `ext-ms-win-core-app-package-volume-l1-1-0!UnmountVolumeForAppPackage` at `0x18002bdf1`

## string_xrefs

- `0x18002a4a4`: `++. hwnd = %x dwClientFlags = %x dwCreationFlags = %x dwTimeout = %x\n	lpDesktop = %ws\n	lpApplicationName = %ws\n	lpCommandLine = %ws\n	lpCurrentDirectory = %ws\n	packageFamilyName = %ws\n	applicationId = %ws\n	szLocalCorrelationVector = %s\n`

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
  const unsigned __int16 *v82; // rcx
  int IsTrustedAndInPackage; // eax
  __int64 v84; // rdx
  unsigned int v85; // ecx
  unsigned int v86; // r8d
  int HaveUIAccessCapability; // eax
  _QWORD *v88; // rcx
  int v89; // edx
  __int64 v90; // rcx
  const unsigned __int16 *v91; // rax
  unsigned int v92; // edi
  const unsigned __int16 *v93; // rcx
  UINT v94; // eax
  HLOCAL v95; // rcx
  wchar_t *v96; // rcx
  void *v97; // rdi
  unsigned int v98; // eax
  int token_information; // eax
  unsigned __int16 **v100; // rdx
  int v101; // eax
  UINT v102; // eax
  int v103; // eax
  int v104; // eax
  int v105; // edi
  int v106; // r8d
  const unsigned __int16 *v107; // rax
  bool v108; // al
  BOOL v109; // edi
  int v110; // eax
  int v111; // eax
  int v112; // eax
  int v113; // r8d
  const unsigned __int16 *v114; // rax
  __int64 v115; // r8
  __int64 v116; // r9
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
  __int64 v128; // rdx
  struct _PROCESS_INFORMATION *v129; // rdi
  const unsigned __int16 *v130; // rax
  const unsigned __int16 *v131; // r9
  DWORD dwProcessId; // r8d
  HANDLE v133; // rax
  void *v134; // rdi
  int dwDesiredAccess; // [rsp+20h] [rbp-F0h]
  DWORD dwDesiredAccessa[2]; // [rsp+20h] [rbp-F0h]
  __int64 bInheritHandle; // [rsp+28h] [rbp-E8h]
  PCWSTR dwOptions; // [rsp+30h] [rbp-E0h]
  struct _CONSENTUI_PARAM_HEADER **v139; // [rsp+38h] [rbp-D8h]
  UINT uExitCode; // [rsp+90h] [rbp-80h] BYREF
  wchar_t *v141; // [rsp+98h] [rbp-78h]
  char v142; // [rsp+A0h] [rbp-70h] BYREF
  bool v143; // [rsp+A1h] [rbp-6Fh] BYREF
  bool v144; // [rsp+A2h] [rbp-6Eh] BYREF
  bool v145; // [rsp+A3h] [rbp-6Dh] BYREF
  bool v146; // [rsp+A4h] [rbp-6Ch] BYREF
  bool v147; // [rsp+A5h] [rbp-6Bh] BYREF
  bool v148; // [rsp+A6h] [rbp-6Ah] BYREF
  bool v149; // [rsp+A7h] [rbp-69h] BYREF
  bool v150; // [rsp+A8h] [rbp-68h] BYREF
  bool v151; // [rsp+A9h] [rbp-67h] BYREF
  bool v152; // [rsp+AAh] [rbp-66h] BYREF
  bool v153; // [rsp+ABh] [rbp-65h] BYREF
  HANDLE TargetHandle; // [rsp+B0h] [rbp-60h] BYREF
  unsigned int v155; // [rsp+B8h] [rbp-58h] BYREF
  bool v156; // [rsp+BCh] [rbp-54h] BYREF
  char v157; // [rsp+BDh] [rbp-53h] BYREF
  char v158; // [rsp+BEh] [rbp-52h]
  unsigned int v159; // [rsp+C0h] [rbp-50h]
  unsigned int v160; // [rsp+C4h] [rbp-4Ch] BYREF
  unsigned int v161; // [rsp+C8h] [rbp-48h] BYREF
  unsigned int v162; // [rsp+CCh] [rbp-44h] BYREF
  unsigned int v163; // [rsp+D0h] [rbp-40h] BYREF
  unsigned int v164; // [rsp+D4h] [rbp-3Ch]
  int v165; // [rsp+D8h] [rbp-38h]
  HLOCAL hMem; // [rsp+E0h] [rbp-30h] BYREF
  PCWSTR packageFamilyName; // [rsp+E8h] [rbp-28h]
  int v168[2]; // [rsp+F0h] [rbp-20h] BYREF
  unsigned int v169; // [rsp+F8h] [rbp-18h] BYREF
  HANDLE hProfile; // [rsp+100h] [rbp-10h] BYREF
  unsigned int v171; // [rsp+108h] [rbp-8h] BYREF
  unsigned int v172; // [rsp+110h] [rbp+0h]
  HANDLE hSourceHandle; // [rsp+118h] [rbp+8h] BYREF
  int v174; // [rsp+120h] [rbp+10h] BYREF
  int v175; // [rsp+124h] [rbp+14h] BYREF
  int v176; // [rsp+128h] [rbp+18h] BYREF
  unsigned int v177; // [rsp+130h] [rbp+20h] BYREF
  __int64 v178; // [rsp+138h] [rbp+28h] BYREF
  unsigned int v179; // [rsp+140h] [rbp+30h] BYREF
  int v180; // [rsp+144h] [rbp+34h] BYREF
  int v181; // [rsp+148h] [rbp+38h] BYREF
  LPCWSTR lpFileName; // [rsp+150h] [rbp+40h] BYREF
  HLOCAL v183; // [rsp+158h] [rbp+48h] BYREF
  struct _PROCESS_INFORMATION *v184; // [rsp+160h] [rbp+50h]
  unsigned int v185[2]; // [rsp+168h] [rbp+58h]
  __int64 v186; // [rsp+170h] [rbp+60h] BYREF
  unsigned int v187[2]; // [rsp+178h] [rbp+68h]
  int v188; // [rsp+180h] [rbp+70h] BYREF
  HANDLE hObject; // [rsp+188h] [rbp+78h]
  void *v190; // [rsp+190h] [rbp+80h] BYREF
  HLOCAL v191; // [rsp+198h] [rbp+88h] BYREF
  HLOCAL v192; // [rsp+1A0h] [rbp+90h] BYREF
  void *Block; // [rsp+1A8h] [rbp+98h] BYREF
  int v194; // [rsp+1B0h] [rbp+A0h] BYREF
  int v195; // [rsp+1B4h] [rbp+A4h] BYREF
  PCWSTR v196; // [rsp+1B8h] [rbp+A8h] BYREF
  unsigned __int16 *v197; // [rsp+1C0h] [rbp+B0h] BYREF
  unsigned __int16 *Src; // [rsp+1C8h] [rbp+B8h]
  unsigned __int16 *v199; // [rsp+1D0h] [rbp+C0h]
  unsigned __int16 *v200; // [rsp+1D8h] [rbp+C8h]
  unsigned __int16 *v201; // [rsp+1E0h] [rbp+D0h]
  unsigned __int16 *v202; // [rsp+1E8h] [rbp+D8h]
  HANDLE Handle; // [rsp+1F0h] [rbp+E0h] BYREF
  HANDLE hToken; // [rsp+1F8h] [rbp+E8h]
  struct _APPINFO_STARTUPINFO *v205[3]; // [rsp+200h] [rbp+F0h] BYREF
  void *v206; // [rsp+218h] [rbp+108h]
  LARGE_INTEGER v207; // [rsp+220h] [rbp+110h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+228h] [rbp+118h] BYREF
  LARGE_INTEGER Frequency; // [rsp+230h] [rbp+120h] BYREF
  HANDLE v210; // [rsp+238h] [rbp+128h]
  void *v211; // [rsp+240h] [rbp+130h] BYREF
  __int128 v212; // [rsp+248h] [rbp+138h] BYREF
  __int64 v213; // [rsp+258h] [rbp+148h]
  int *v214; // [rsp+260h] [rbp+150h]
  void *v215; // [rsp+268h] [rbp+158h]
  PRPC_ASYNC_STATE pAsync; // [rsp+270h] [rbp+160h]
  __int128 v217; // [rsp+278h] [rbp+168h] BYREF
  __int128 v218; // [rsp+288h] [rbp+178h]
  __int64 v219; // [rsp+298h] [rbp+188h]
  __int128 v220; // [rsp+2A0h] [rbp+190h] BYREF
  __int128 v221; // [rsp+2B0h] [rbp+1A0h]
  __int64 v222; // [rsp+2C0h] [rbp+1B0h]
  char v223[80]; // [rsp+2D0h] [rbp+1C0h] BYREF
  char Destination[144]; // [rsp+320h] [rbp+210h] BYREF
  _BYTE v225[464]; // [rsp+3B0h] [rbp+2A0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+5D8h] [rbp+4C8h]

  v23 = Source;
  v199 = a8;
  v24 = a3;
  v25 = a4;
  packageFamilyName = a10;
  v141 = a11;
  v164 = a5;
  v177 = a5;
  v159 = a6;
  v171 = a6;
  v205[0] = a9;
  hProfile = a12;
  v160 = a13;
  v215 = a15;
  v205[2] = (struct _APPINFO_STARTUPINFO *)a17;
  v205[1] = (struct _APPINFO_STARTUPINFO *)a18;
  v214 = a21;
  *(_QWORD *)v168 = a22;
  pAsync = a1;
  v184 = (struct _PROCESS_INFORMATION *)a23;
  v202 = a7;
  v191 = a7;
  hObject = (HANDLE)-1LL;
  v26 = 0;
  v213 = 0;
  AppModelIdentityActivationProperties = 0;
  v219 = 0;
  v222 = 0;
  v201 = a4;
  v200 = a3;
  v190 = a2;
  lpFileName = a3;
  hMem = a4;
  v169 = 0;
  v161 = 0;
  v155 = 0;
  v194 = 0;
  v163 = 0;
  v183 = 0;
  v206 = 0;
  Handle = 0;
  hSourceHandle = 0;
  v211 = 0;
  TargetHandle = 0;
  v210 = 0;
  hToken = 0;
  v180 = 0;
  *(_QWORD *)v185 = 0;
  v179 = 0;
  v172 = 0;
  v188 = 0;
  v174 = 6;
  v192 = 0;
  v212 = 0;
  v178 = 0;
  v217 = 0;
  v186 = 0;
  v218 = 0;
  v165 = 0;
  v220 = 0;
  Src = 0;
  v221 = 0;
  v28 = 0;
  v162 = 0;
  v176 = 0;
  v175 = 0;
  v142 = 0;
  v152 = 0;
  v144 = 0;
  v151 = 0;
  v150 = 0;
  v149 = 0;
  v143 = 0;
  v146 = 0;
  memset_0(v225, 0, sizeof(v225));
  v195 = 464;
  Block = 0;
  v158 = 0;
  memset_0(Destination, 0, 0x81u);
  Frequency.QuadPart = 0;
  PerformanceCount.QuadPart = 0;
  v207.QuadPart = 0;
  QueryPerformanceCounter(&PerformanceCount);
  QueryPerformanceFrequency(&Frequency);
  v29 = L"NULL";
  v30 = a11;
  if ( !a11 )
    v30 = L"NULL";
  v31 = packageFamilyName;
  if ( !packageFamilyName )
    v31 = L"NULL";
  v32 = v199;
  *(_QWORD *)v187 = v30;
  v33 = v202;
  v196 = v31;
  if ( !v199 )
    v32 = L"NULL";
  v197 = v32;
  v34 = v25;
  if ( !v202 )
    v33 = L"NULL";
  v35 = v24;
  if ( !v25 )
    v34 = L"NULL";
  if ( !v24 )
    v35 = L"NULL";
  LUATelemetry::WatchCurrentThread(
    v223,
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
    v164,
    v159,
    v160,
    v32,
    v35,
    v34,
    v33,
    v31);
  if ( !g_pCentennialElevationTelemetryRateLimiter
    || !(unsigned int)RateLimiter::RequestPermission(g_pCentennialElevationTelemetryRateLimiter) )
  {
    goto LABEL_23;
  }
  if ( v23 )
  {
    strncpy_s(Destination, 0x81u, v23, 0x81u);
LABEL_23:
    v38 = v164;
    v39 = v159;
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
  v38 = v177;
  v39 = v171;
  v26 = (unsigned __int16 *)v183;
  v24 = (unsigned __int16 *)lpFileName;
  v25 = (unsigned __int16 *)hMem;
  v161 = v155;
  v164 = v177;
  v159 = v171;
LABEL_24:
  v40 = v184;
  *(_OWORD *)&v184->hProcess = 0;
  *(_QWORD *)&v40->dwProcessId = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v41 = L"NULL";
    if ( v191 )
      v41 = (const unsigned __int16 *)v191;
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
      v160,
      (__int64)v197,
      (__int64)v43,
      (__int64)v42,
      (__int64)v41,
      (__int64)v196,
      *(__int64 *)v187,
      (__int64)Destination);
  }
  if ( (a14 & 1) != 0 )
  {
    v172 = AiLogPerfTrackEvent(&AppInfo_PerfTrack_Elevation_PackagedApp_Start);
    v142 = 1;
  }
  if ( !v24 || !packageFamilyName || !v141 )
    goto LABEL_94;
  AipJustFileName(v24);
  v44 = -1;
  v45 = -1;
  do
    ++v45;
  while ( v24[v45] );
  *(_QWORD *)v187 = v45;
  if ( v25 )
  {
    do
      ++v44;
    while ( v25[v44] );
    *(_QWORD *)v185 = v44;
  }
  else
  {
    v44 = *(_QWORD *)v185;
  }
  if ( v45 > 0x7FFF || v44 > 0x7FFF || (a14 & 0x120) == 0x100 || (a14 & 0x810) == 0x800 )
    goto LABEL_94;
  uExitCode = AiGetClientInformation(v190, &Handle, &hSourceHandle, &v169, &v179);
  if ( uExitCode )
  {
LABEL_95:
    v54 = v141;
    goto LABEL_96;
  }
  if ( *(_QWORD *)v168 )
  {
    v175 = **(_DWORD **)v168;
  }
  else
  {
    v168[0] = 0;
    v46 = LUAGetUACPromptPolicy(v168, &v175);
    if ( v46 < 0 )
      goto LABEL_54;
  }
  if ( v214 )
  {
    v176 = *v214;
  }
  else
  {
    v168[0] = 0;
    v46 = AiCheckForElevatedUser(hSourceHandle, v168);
    if ( v46 < 0 )
      goto LABEL_54;
    v46 = AiCheckForAdminUser(hSourceHandle, v168[0], &v176);
    if ( v46 < 0 )
      goto LABEL_54;
  }
  v145 = 0;
  v153 = 0;
  v148 = 0;
  v147 = 0;
  v156 = 0;
  AppModelIdentityActivationProperties = GetAppModelIdentityActivationProperties(
                                           hSourceHandle,
                                           v141,
                                           0,
                                           a14,
                                           (enum AppModel::RuntimeBehavior *)&v162,
                                           &v145,
                                           &v153,
                                           &v148,
                                           &v147,
                                           &v156);
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
  if ( v156 )
    a14 |= 0x2000u;
  if ( v142 && v145 )
    goto LABEL_66;
  if ( v162 == 1 )
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
    v157 = 0;
    AppModelIdentityActivationProperties = UMgrIsAllowedToActivateAsUser(hSourceHandle, a16, &v157);
    if ( AppModelIdentityActivationProperties < 0 )
      goto LABEL_69;
    if ( !v157 )
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
    v45 = *(_QWORD *)v187;
  }
  if ( (v164 & 8) != 0 )
  {
    v52 = AiConvertWow64Paths(
            v200,
            &lpFileName,
            v201,
            (unsigned __int16 **)&hMem,
            v202,
            (const unsigned __int16 **)&v191);
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
      *(_QWORD *)v187 = v45;
    }
    v25 = (unsigned __int16 *)hMem;
    if ( hMem )
    {
      v53 = -1;
      do
        ++v53;
      while ( *((_WORD *)hMem + v53) );
      *(_QWORD *)v185 = v53;
    }
    else
    {
      v53 = *(_QWORD *)v185;
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
  PackageFullNameFromFamilyName = GetPackageFullNameFromFamilyName(packageFamilyName, (unsigned __int16 **)&v183);
  RpcRevertToSelf();
  if ( PackageFullNameFromFamilyName < 0 )
  {
    v57 = RtlNtStatusToDosErrorNoTeb(PackageFullNameFromFamilyName);
    v26 = (unsigned __int16 *)v183;
    uExitCode = v57;
    goto LABEL_95;
  }
  v26 = (unsigned __int16 *)v183;
  PackageProperties = GetPackageProperties(
                        (const unsigned __int16 *)v183,
                        &v152,
                        &v144,
                        &v151,
                        &v150,
                        &v149,
                        &v143,
                        &v146,
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
  if ( v143 && !v144 )
  {
    v168[0] = 0;
    v46 = AiCheckForTcbPrivilege(hSourceHandle, v168);
    if ( v46 < 0 )
      goto LABEL_54;
    if ( !v168[0] )
    {
      v143 = 0;
      v64 = v25;
      if ( v24 )
        v64 = v24;
      DoesExecutableExistInPackage = AiDoesExecutableExistInPackage(v26, v64, &v143);
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
      if ( !v143 )
        goto LABEL_75;
    }
  }
  if ( !v162 )
    goto LABEL_227;
  v165 = 2;
  if ( !v142 )
    goto LABEL_227;
  uExitCode = CheckElevationEnabled(&v188);
  if ( uExitCode )
    goto LABEL_95;
  if ( !v188 )
  {
    v142 = 0;
    goto LABEL_227;
  }
  v142 = 1;
  v46 = LUAGetUserType(TargetHandle, &v180);
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
  LOBYTE(v66) = v145;
  v54 = v141;
  uExitCode = AdjustActivationToken(TargetHandle, v162, v66, 0);
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
      WPP_SF_DSSSS(v78, v77, v74, v75, (__int64)v29, (__int64)v79, (__int64)packageFamilyName, (__int64)v141);
      goto LABEL_153;
    }
    goto LABEL_153;
  }
  v80 = v25;
  if ( v24 )
    v80 = v24;
  uExitCode = CheckElevation(v80, &v194, 0, &v163, &v174);
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
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_2045735225>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_2045735225>::GetImpl'::`2'::impl)
    && v163 - 16 <= 2
    && (unsigned int)LUAIsShadowAdminEnabled() )
  {
    v81 = v25;
    if ( v24 )
      v81 = v24;
    AipCheckAssistiveTechnologyList(v81, &v155);
  }
  v82 = v25;
  if ( v24 )
    v82 = v24;
  uExitCode = AiCheckSecureApplicationDirectory(v82, &v155);
  if ( uExitCode )
    goto LABEL_153;
  LODWORD(v190) = 0;
  IsTrustedAndInPackage = VerifyFileIsTrustedAndInPackage(v24, v26, &v190);
  if ( IsTrustedAndInPackage < 0 )
  {
    uExitCode = WIN32_FROM_HRESULT(IsTrustedAndInPackage);
    goto LABEL_153;
  }
  RevertToSelf();
  v85 = v163;
  if ( v163 - 16 > 2 )
  {
    v92 = v155;
  }
  else
  {
    v165 = 3;
    v168[0] = 0;
    LOBYTE(v84) = 1;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_CentennialUIAccess>::ReportUsage(
      &`wil::Feature<__WilFeatureTraits_Feature_CentennialUIAccess>::GetImpl'::`2'::impl,
      v84);
    if ( !(unsigned __int8)IsDoesPackageHaveUIAccessCapabilityPresent() )
      goto LABEL_175;
    HaveUIAccessCapability = DoesPackageHaveUIAccessCapability(v26, v168);
    if ( HaveUIAccessCapability < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x206A,
        v86,
        (const char *)(unsigned int)HaveUIAccessCapability,
        dwDesiredAccess);
      goto LABEL_175;
    }
    if ( !v168[0] )
    {
LABEL_175:
      uExitCode = 50;
      v88 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_96;
      v89 = 51;
      goto LABEL_178;
    }
    v85 = v163;
    if ( v163 >= 3 )
    {
      v85 = v163 - 16;
      v163 -= 16;
    }
    v92 = v155 | 0x8000C;
    v155 |= 0x8000Cu;
  }
  LODWORD(hMem) = v164 & 1;
  if ( (v164 & 1) != 0 )
  {
LABEL_194:
    if ( v85 )
      goto LABEL_196;
    goto LABEL_195;
  }
  if ( !v85 )
  {
LABEL_195:
    if ( (v92 & 4) != 0 )
    {
LABEL_198:
      if ( (_DWORD)hMem )
      {
        if ( v85 <= 1 )
        {
          v92 |= 0x200u;
          v155 = v92;
        }
        v163 = 2;
        v174 = 6;
      }
      if ( (v164 & 0x10) != 0 )
        v155 = v92 | 0x800;
      if ( v144 || !(_DWORD)v190 )
      {
        v96 = v25;
        if ( v24 )
          v96 = v24;
        v94 = AiBuildEXEParams(
                v96,
                hObject,
                v24,
                v187[0],
                v25,
                v185[0],
                0,
                v179,
                (struct _CONSENTUI_PARAM_HEADER **)&v192);
        v54 = v141;
      }
      else
      {
        v54 = v141;
        v93 = v25;
        v174 = 8;
        if ( v24 )
          v93 = v24;
        v94 = AiBuildPackagedAppParams(
                v93,
                v187[0],
                v25,
                v185[0],
                v179,
                (wchar_t *)packageFamilyName,
                v141,
                (struct _CONSENTUI_PARAM_HEADER **)&v192);
      }
      uExitCode = v94;
      if ( v94 )
        goto LABEL_96;
      v95 = v192;
      *((_DWORD *)v192 + 13) = v172;
      uExitCode = AiCheckLUA(
                    v163,
                    &v155,
                    (unsigned int)v174,
                    TargetHandle,
                    v95,
                    v199,
                    hProfile,
                    v169,
                    v160,
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
      v97 = v211;
      if ( v211 )
      {
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShadowAdmin>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_ShadowAdmin>::GetImpl'::`2'::impl) )
        {
          v159 &= 0xFFFFFFFC;
          v171 = v159;
        }
        v98 = v155 | 1;
        TargetHandle = v97;
      }
      else
      {
        v98 = v155;
      }
      v161 = v98;
LABEL_227:
      if ( (unsigned __int8)IsMountVolumeForAppPackagePresent() )
      {
        token_information = wil::get_token_information_nothrow<_TOKEN_USER,0>(&Block, TargetHandle);
        AppModelIdentityActivationProperties = token_information;
        if ( token_information < 0 )
        {
          v49 = token_information;
          goto LABEL_70;
        }
        hMem = 0;
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
          &hMem,
          0);
        v54 = v141;
        v101 = ParseAppUserModelId(v141, v100, (unsigned __int16 **)&hMem);
        AppModelIdentityActivationProperties = v101;
        if ( v101 < 0 )
        {
          v102 = WIN32_FROM_HRESULT(v101);
LABEL_232:
          uExitCode = v102;
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&hMem);
          goto LABEL_96;
        }
        v103 = PsmCreateKey(v26, hMem, v225, &v195);
        if ( v103 < 0 )
        {
          v102 = WIN32_FROM_NTSTATUS(v103);
          goto LABEL_232;
        }
        v104 = MountVolumeForAppPackage(v225, *(_QWORD *)Block, v169);
        v105 = v104;
        if ( v104 < 0 )
        {
          uExitCode = WIN32_FROM_NTSTATUS(v104);
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v107 = L"NULL";
            if ( v26 )
              v107 = v26;
            if ( v24 )
              v29 = v24;
            WPP_SF_DSS(*((_QWORD *)WPP_GLOBAL_Control + 2), 54, v106, v105, (__int64)v29, (__int64)v107);
          }
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&hMem);
          goto LABEL_95;
        }
        v158 = 1;
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&hMem);
      }
      v108 = ShouldAdjustActivationToken();
      v109 = v108;
      v143 = v108;
      if ( v144 || (v172 = 0, (a14 & 6) != 0) )
        v172 = 1;
      v165 = 1;
      if ( !v162 )
      {
        *(_QWORD *)&v220 = TargetHandle;
        *((_QWORD *)&v220 + 1) = hSourceHandle;
        HIDWORD(v222) = v153;
        *(_QWORD *)&v221 = v26;
        *((_QWORD *)&v221 + 1) = v24;
        v110 = PrepareAppXActivation(&v220, &v186);
        AppModelIdentityActivationProperties = v110;
        if ( v110 < 0 )
        {
          uExitCode = WIN32_FROM_HRESULT(v110);
          v61 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            goto LABEL_95;
          v62 = 55;
          goto LABEL_106;
        }
        if ( *(_DWORD *)(v186 + 8) )
          Src = *(unsigned __int16 **)(v186 + 24);
LABEL_284:
        if ( v109 )
        {
          v165 = 4;
          LastError = RpcImpersonateClient(0);
          if ( LastError )
            goto LABEL_55;
          v54 = v141;
          LOBYTE(v116) = v153;
          LOBYTE(v115) = v145;
          uExitCode = AdjustActivationToken(TargetHandle, v162, v115, v116);
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
          v117 = v206;
          TargetHandle = v206;
        }
        else
        {
          v117 = TargetHandle;
        }
        if ( v162 - 1 <= 2 )
        {
          v118 = BeginCreatingHeliumContainerForDesktopAppXActivation(v117, v178);
          v117 = TargetHandle;
          v28 = v118;
        }
        v119 = v159 & 4;
        v120 = v143;
        v143 = -v143;
        v165 = 5;
        uExitCode = AiLaunchProcess(
                      Handle,
                      v117,
                      hObject,
                      v161,
                      v24,
                      v25,
                      v159 | 4,
                      (const unsigned __int16 *)v191,
                      v199,
                      v205[0],
                      v169,
                      (_WORD *)((unsigned __int64)v26 & -(__int64)v120),
                      a14,
                      v215,
                      a19,
                      Src,
                      v184);
        v68 = uExitCode;
        if ( uExitCode )
        {
          v69 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
            goto LABEL_95;
          v54 = v141;
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v70 = 58;
LABEL_132:
            v71 = v69[2];
            v72 = L"NULL";
            v139 = (struct _CONSENTUI_PARAM_HEADER **)v54;
            if ( v25 )
              v72 = v25;
            dwOptions = packageFamilyName;
            bInheritHandle = (__int64)v72;
LABEL_135:
            if ( v24 )
              v29 = v24;
            WPP_SF_DSSSS(v71, v70, (_DWORD)v67, v68, (__int64)v29, bInheritHandle, (__int64)dwOptions, (__int64)v139);
            goto LABEL_96;
          }
          goto LABEL_96;
        }
        v165 = 6;
        if ( v162 )
        {
          if ( v162 - 1 > 2 )
          {
            v121 = 0;
          }
          else
          {
            *(_DWORD *)(v178 + 40) = v159;
            v213 = *(_QWORD *)&v184->dwProcessId;
            AppModelIdentityActivationProperties = PostCreateProcessDesktopAppXActivation(
                                                     TargetHandle,
                                                     v178,
                                                     &v212,
                                                     v68);
            v121 = *(_DWORD *)(v178 + 16);
          }
        }
        else
        {
          *(_DWORD *)(v186 + 32) = v159;
          v213 = *(_QWORD *)&v184->dwProcessId;
          AppModelIdentityActivationProperties = PostCreateProcessAppXActivation(TargetHandle, v186, &v212, v68);
          v121 = *(_DWORD *)(v186 + 8);
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
          v165 = 7;
          v122 = OpenThread(2u, 0, v184->dwThreadId);
          v210 = v122;
          if ( !v122 )
          {
            v123 = GetLastError();
            uExitCode = v123;
            v67 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
              goto LABEL_95;
            v54 = v141;
            if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
              goto LABEL_96;
            v70 = 60;
LABEL_313:
            v139 = (struct _CONSENTUI_PARAM_HEADER **)v54;
            v124 = L"NULL";
            if ( v25 )
              v124 = v25;
            dwOptions = packageFamilyName;
            bInheritHandle = (__int64)v124;
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
            v54 = v141;
            if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
              goto LABEL_96;
            v70 = 61;
            goto LABEL_313;
          }
        }
        v54 = v141;
        uExitCode = 0;
        goto LABEL_96;
      }
      if ( v162 - 1 > 2 )
        goto LABEL_284;
      hProfile = 0;
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShadowAdmin>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_ShadowAdmin>::GetImpl'::`2'::impl) )
      {
        if ( (v161 & 0x21) != 1 && ((v161 & 0x8000000) == 0 || !(unsigned int)LUAIsShadowAdminEnabled()) )
          goto LABEL_268;
      }
      else if ( (v161 & 0x21) != 1 )
      {
        goto LABEL_268;
      }
      uExitCode = AipLoadUserProfile(TargetHandle, &hProfile);
      if ( uExitCode )
        goto LABEL_261;
      ImpersonateLoggedOnUser(TargetHandle);
      v160 = 0;
      if ( (int)RegisterAppXPackageIfNecessary2(0, v141, 0, 0) < 0 )
      {
        uExitCode = 15669;
        RevertToSelf();
        goto LABEL_261;
      }
      RevertToSelf();
LABEL_268:
      *(_QWORD *)&v217 = TargetHandle;
      *((_QWORD *)&v217 + 1) = hSourceHandle;
      v111 = 0;
      *(_QWORD *)&v218 = v26;
      *((_QWORD *)&v218 + 1) = v24;
      if ( v162 == 2 )
        v111 = 8;
      LODWORD(v219) = v172 | v219 | (2 * v109) | v111;
      v112 = PrepareDesktopAppXActivation(&v217, &v178);
      AppModelIdentityActivationProperties = v112;
      if ( v112 >= 0 )
      {
        if ( v142 )
          *(_DWORD *)(v178 + 16) = 0;
        if ( *(_DWORD *)(v178 + 16) )
          Src = *(unsigned __int16 **)(v178 + 32);
        if ( hProfile )
        {
          UnloadUserProfile(TargetHandle, hProfile);
          hProfile = 0;
        }
        goto LABEL_284;
      }
      uExitCode = WIN32_FROM_HRESULT(v112);
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v114 = L"NULL";
        if ( v26 )
          v114 = v26;
        if ( v24 )
          v29 = v24;
        WPP_SF_DSS(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          56,
          v113,
          AppModelIdentityActivationProperties,
          (__int64)v29,
          (__int64)v114);
      }
LABEL_261:
      if ( hProfile )
        UnloadUserProfile(TargetHandle, hProfile);
      goto LABEL_95;
    }
LABEL_196:
    if ( !AiIsElevationAllowedForSession(v169) )
    {
LABEL_66:
      uExitCode = 50;
      goto LABEL_95;
    }
    v85 = v163;
    goto LABEL_198;
  }
  v168[0] = 0;
  if ( (unsigned __int8)IsDoesPackageHaveElevationCapabilityPresent()
    && (int)DoesPackageHaveElevationCapability(v26, v168) >= 0
    && v168[0] )
  {
    LODWORD(v197) = -1;
    LODWORD(v196) = v175;
    v180 = 0;
    v161 = uExitCode;
    LUATelemetry::CentennialElevation<long,unsigned short * &,unsigned short const * &,unsigned long &,unsigned long &,unsigned long &,unsigned long &,bool &,int &,unsigned long,int,int,char (&)[129]>(
      (unsigned int)&v161,
      (unsigned int)&v183,
      (unsigned int)&lpFileName,
      (unsigned int)&uExitCode,
      (__int64)&v177,
      (__int64)&v171,
      (__int64)&a14,
      (__int64)&v142,
      (__int64)&v176,
      (__int64)&v196,
      (__int64)&v197,
      (__int64)&v180,
      Destination);
    v85 = v163;
    goto LABEL_194;
  }
  uExitCode = 50;
  v88 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
    goto LABEL_95;
  v54 = v141;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v89 = 52;
LABEL_178:
    v90 = v88[2];
    v91 = L"NULL";
    if ( v25 )
      v91 = v25;
    if ( v24 )
      LODWORD(v29) = (_DWORD)v24;
    WPP_SF_SSSS(v90, v89, v86, (_DWORD)v29, (__int64)v91, (__int64)packageFamilyName, (__int64)v54);
  }
LABEL_96:
  QueryPerformanceCounter(&v207);
  v181 = 1;
  v205[0] = (struct _APPINFO_STARTUPINFO *)(1000 * (v207.QuadPart - PerformanceCount.QuadPart) / Frequency.QuadPart);
  LODWORD(hMem) = v175;
  v55 = uExitCode;
  if ( uExitCode == 1223 )
  {
    v160 = 0;
  }
  else
  {
    if ( (int)uExitCode > 0 )
      v55 = (unsigned __int16)uExitCode | 0x80070000;
    v160 = v55;
  }
  LUATelemetry::CentennialElevation<long,unsigned short * &,unsigned short const * &,unsigned long &,unsigned long &,unsigned long &,unsigned long &,bool &,int &,unsigned long,__int64 &,int,char (&)[129]>(
    (unsigned int)&v160,
    (unsigned int)&v183,
    (unsigned int)&lpFileName,
    (unsigned int)&uExitCode,
    (__int64)&v177,
    (__int64)&v171,
    (__int64)&a14,
    (__int64)&v142,
    (__int64)&v176,
    (__int64)&hMem,
    (__int64)v205,
    (__int64)&v181,
    Destination);
  if ( uExitCode )
  {
    v125 = v165;
    if ( v165 != 1 && v165 != 6 )
    {
      if ( (int)uExitCode > 0 )
        AppModelIdentityActivationProperties = (unsigned __int16)uExitCode | 0x80070000;
      else
        AppModelIdentityActivationProperties = uExitCode;
    }
    v126 = AipJustFileName(v24);
    v127 = packageFamilyName;
    *(_QWORD *)dwDesiredAccessa = v54;
    if ( v26 )
      v127 = v26;
    AipLogDesktopAppXProcessStartFailure(v125, (unsigned int)AppModelIdentityActivationProperties, v127, v126);
    v129 = v184;
  }
  else
  {
    v130 = AipJustFileName(v24);
    v131 = v54;
    v129 = v184;
    AipLogDesktopAppXProcessStartSuccess(v184->dwProcessId, v26, v130, v131, L"[LaunchProcess]");
  }
  if ( hObject != (HANDLE)-1LL )
    CloseHandle(hObject);
  if ( v24 != v200 )
    LocalFree(v24);
  if ( v25 != v201 )
    LocalFree(v25);
  if ( v191 != v202 )
    LocalFree(v191);
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
  if ( v178 )
    FreeDesktopAppXLaunchContext(v178, v128);
  if ( v186 )
    FreeAppXLaunchContext(v186, v128);
  if ( v210 )
    CloseHandle(v210);
  if ( hToken )
    CloseHandle(hToken);
  if ( uExitCode )
  {
    dwProcessId = v129->dwProcessId;
    if ( dwProcessId )
    {
      v133 = OpenProcess(1u, 0, dwProcessId);
      v134 = v133;
      if ( v133 )
      {
        TerminateProcess(v133, uExitCode);
        CloseHandle(v134);
      }
    }
    if ( v158 )
      UnmountVolumeForAppPackage(v225, *(_QWORD *)Block, v169);
  }
  if ( v192 )
    LocalFree(v192);
  RundownHeliumContainerForDesktopAppXActivation(v28);
  RpcAsyncCompleteCall(pAsync, &uExitCode);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_D(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      62,
      &WPP_063934a2c6ca383cf9bd298d4f16efdb_Traceguids,
      uExitCode,
      *(_QWORD *)dwDesiredAccessa);
  wil::ActivityThreadWatcher::~ActivityThreadWatcher((wil::ActivityThreadWatcher *)v223);
  if ( Block )
    operator delete(Block);
}

```

## disassembly

```asm
0x18002a1d8  push    rbp
0x18002a1da  push    rbx
0x18002a1db  push    rsi
0x18002a1dc  push    rdi
0x18002a1dd  push    r12
0x18002a1df  push    r13
0x18002a1e1  push    r14
0x18002a1e3  push    r15
0x18002a1e5  lea     rbp, [rsp-488h]
0x18002a1ed  sub     rsp, 598h
0x18002a1f4  mov     rax, cs:__security_cookie
0x18002a1fb  xor     rax, rsp
0x18002a1fe  mov     [rbp+4C0h+var_50], rax
0x18002a205  mov     rax, [rbp+4C0h+arg_38]
0x18002a20c  xorps   xmm0, xmm0
0x18002a20f  mov     rdi, [rbp+4C0h+Source]
0x18002a216  xorps   xmm1, xmm1
0x18002a219  mov     [rbp+4C0h+var_400], rax
0x18002a220  mov     r14, r8
0x18002a223  mov     rax, [rbp+4C0h+arg_48]
0x18002a22a  mov     r12, r9
0x18002a22d  mov     [rbp+4C0h+packageFamilyName], rax
0x18002a231  mov     rax, [rbp+4C0h+arg_50]
0x18002a238  mov     [rbp+4C0h+var_538], rax
0x18002a23c  mov     eax, [rbp+4C0h+arg_20]
0x18002a242  mov     [rbp+4C0h+var_4FC], eax
0x18002a245  mov     [rbp+4C0h+var_4A0], eax
0x18002a248  mov     eax, [rbp+4C0h+arg_28]
0x18002a24e  mov     [rbp+4C0h+var_510], eax
0x18002a251  mov     [rbp+4C0h+var_4C8], eax
0x18002a254  mov     rax, [rbp+4C0h+arg_40]
0x18002a25b  mov     [rbp+4C0h+var_3D0], rax
0x18002a262  mov     rax, [rbp+4C0h+arg_58]
0x18002a269  mov     [rbp+4C0h+hProfile], rax
0x18002a26d  mov     eax, [rbp+4C0h+arg_60]
0x18002a273  mov     [rbp+4C0h+var_50C], eax
0x18002a276  mov     rax, [rbp+4C0h+arg_70]
0x18002a27d  mov     [rbp+4C0h+var_368], rax
0x18002a284  mov     rax, [rbp+4C0h+arg_80]
0x18002a28b  mov     [rbp+4C0h+var_3C0], rax
0x18002a292  mov     rax, [rbp+4C0h+arg_88]
0x18002a299  mov     [rbp+4C0h+var_3C8], rax
0x18002a2a0  mov     rax, [rbp+4C0h+arg_A0]
0x18002a2a7  mov     [rbp+4C0h+var_370], rax
0x18002a2ae  mov     rax, [rbp+4C0h+arg_A8]
0x18002a2b5  mov     qword ptr [rbp+4C0h+var_4E0], rax
0x18002a2b9  mov     rax, [rbp+4C0h+arg_B0]
0x18002a2c0  mov     [rbp+4C0h+pAsync], rcx
0x18002a2c7  mov     rcx, [rbp+4C0h+arg_30]
0x18002a2ce  mov     [rbp+4C0h+var_470], rax
0x18002a2d2  xor     eax, eax
0x18002a2d4  mov     [rbp+4C0h+var_3E8], rcx
0x18002a2db  mov     [rbp+4C0h+var_438], rcx
0x18002a2e2  xor     ecx, ecx
0x18002a2e4  or      [rbp+4C0h+hObject], 0FFFFFFFFFFFFFFFFh
0x18002a2e9  mov     r13d, ecx
0x18002a2ec  mov     [rbp+4C0h+var_378], rax
0x18002a2f3  mov     r15d, ecx
0x18002a2f6  mov     [rbp+4C0h+var_338], rax
0x18002a2fd  mov     [rbp+4C0h+var_310], rax
0x18002a304  mov     [rbp+4C0h+var_3F0], r9
0x18002a30b  mov     [rbp+4C0h+var_3F8], r8
0x18002a312  mov     [rbp+4C0h+var_440], rdx
0x18002a319  mov     [rbp+4C0h+lpFileName], r8
0x18002a31d  mov     [rbp+4C0h+hMem], r9
0x18002a321  mov     [rbp+4C0h+var_4D8], ecx
0x18002a324  mov     [rbp+4C0h+var_508], ecx
0x18002a327  mov     [rbp+4C0h+var_518], ecx
0x18002a32a  mov     [rbp+4C0h+var_420], ecx
0x18002a330  mov     [rbp+4C0h+var_500], ecx
0x18002a333  mov     [rbp+4C0h+var_478], rcx
0x18002a337  mov     [rbp+4C0h+var_3B8], rcx
0x18002a33e  mov     [rbp+4C0h+Handle], rcx
0x18002a345  mov     [rbp+4C0h+hSourceHandle], rcx
0x18002a349  mov     [rbp+4C0h+var_390], rcx
0x18002a350  mov     [rbp+4C0h+TargetHandle], rcx
0x18002a354  mov     [rbp+4C0h+var_398], rcx
0x18002a35b  mov     [rbp+4C0h+hToken], rcx
0x18002a362  mov     [rbp+4C0h+var_48C], ecx
0x18002a365  mov     qword ptr [rbp+4C0h+var_468], rcx
0x18002a369  mov     [rbp+4C0h+var_490], ecx
0x18002a36c  mov     [rbp+4C0h+var_4C0], ecx
0x18002a36f  mov     [rbp+4C0h+var_450], ecx
0x18002a372  mov     [rbp+4C0h+var_4B0], 6
0x18002a379  mov     [rbp+4C0h+var_430], rcx
0x18002a380  movups  [rbp+4C0h+var_388], xmm0
0x18002a387  mov     [rbp+4C0h+var_498], rcx
0x18002a38b  movups  [rbp+4C0h+var_358], xmm1
0x18002a392  mov     [rbp+4C0h+var_460], rcx
0x18002a396  movups  [rbp+4C0h+var_348], xmm1
0x18002a39d  mov     [rbp+4C0h+var_4F8], ecx
0x18002a3a0  movups  [rbp+4C0h+var_330], xmm0
0x18002a3a7  mov     [rbp+4C0h+var_408], rcx
0x18002a3ae  movups  [rbp+4C0h+var_320], xmm0
0x18002a3b5  mov     ebx, ecx
0x18002a3b7  mov     [rbp+4C0h+var_504], ecx
0x18002a3ba  mov     [rbp+4C0h+var_4A8], ecx
0x18002a3bd  mov     esi, 1D0h
0x18002a3c2  mov     [rbp+4C0h+var_4AC], ecx
0x18002a3c5  mov     r8d, esi; Size
0x18002a3c8  mov     [rbp+4C0h+var_530], cl
0x18002a3cb  xor     edx, edx; Val
0x18002a3cd  mov     [rbp+4C0h+var_526], cl
0x18002a3d0  mov     [rbp+4C0h+var_52E], cl
0x18002a3d3  mov     [rbp+4C0h+var_527], cl
0x18002a3d6  mov     [rbp+4C0h+var_528], cl
0x18002a3d9  mov     [rbp+4C0h+var_529], cl
0x18002a3dc  mov     [rbp+4C0h+var_52F], cl
0x18002a3df  mov     [rbp+4C0h+var_52C], cl
0x18002a3e2  lea     rcx, [rbp+4C0h+var_220]; void *
0x18002a3e9  call    memset_0
0x18002a3ee  mov     [rbp+4C0h+var_41C], esi
0x18002a3f4  lea     rcx, [rbp+4C0h+Destination]; void *
0x18002a3fb  xor     esi, esi
0x18002a3fd  xor     edx, edx; Val
0x18002a3ff  mov     r8d, 81h; Size
0x18002a405  mov     [rbp+4C0h+Block], rsi
0x18002a40c  mov     [rbp+4C0h+var_512], sil
0x18002a410  call    memset_0
0x18002a415  lea     rcx, [rbp+4C0h+PerformanceCount]; lpPerformanceCount
0x18002a41c  mov     qword ptr [rbp+4C0h+Frequency], rsi
0x18002a423  mov     qword ptr [rbp+4C0h+PerformanceCount], rsi
0x18002a42a  mov     qword ptr [rbp+4C0h+var_3B0], rsi
0x18002a431  call    cs:__imp_QueryPerformanceCounter
0x18002a438  nop     dword ptr [rax+rax+00h]
0x18002a43d  lea     rcx, [rbp+4C0h+Frequency]; lpFrequency
0x18002a444  call    cs:__imp_QueryPerformanceFrequency
0x18002a44b  nop     dword ptr [rax+rax+00h]
0x18002a450  mov     rax, [rbp+4C0h+var_538]
0x18002a454  lea     rsi, aNull_0; "NULL"
0x18002a45b  test    rax, rax
0x18002a45e  mov     r8, rax
0x18002a461  mov     rax, [rbp+4C0h+packageFamilyName]
0x18002a465  mov     r11, r14
0x18002a468  cmovz   r8, rsi
0x18002a46c  lea     r11, [rbp+4C0h+Destination]
0x18002a473  test    rax, rax
0x18002a476  mov     [rsp+5D0h+var_568], r11
0x18002a47b  mov     qword ptr [rsp+5D0h+var_570], r8
0x18002a480  mov     r9, rax
0x18002a483  mov     rax, [rbp+4C0h+var_400]
0x18002a48a  cmovz   r9, rsi
0x18002a48e  test    rax, rax
0x18002a491  mov     [rsp+5D0h+lpValue], r9
0x18002a496  mov     r10, rax
0x18002a499  mov     qword ptr [rbp+4C0h+var_458], r8
0x18002a49d  mov     rax, [rbp+4C0h+var_3E8]
0x18002a4a4  lea     r8, aHwndXDwclientf_0; "++. hwnd = %x dwClientFlags = %x dwCrea"...
0x18002a4ab  mov     rdx, rax
0x18002a4ae  mov     [rbp+4C0h+var_418], r9
0x18002a4b5  mov     r9d, dword ptr [rbp+4C0h+hProfile]
0x18002a4b9  cmovz   r10, rsi
0x18002a4bd  test    rax, rax
0x18002a4c0  mov     [rbp+4C0h+var_410], r10
0x18002a4c7  mov     rax, r12
0x18002a4ca  mov     rcx, rax
0x18002a4cd  cmovz   rdx, rsi
0x18002a4d1  mov     qword ptr [rsp+5D0h+var_580], rdx
0x18002a4d6  test    rax, rax
0x18002a4d9  mov     rax, r14
0x18002a4dc  lea     rdx, aAiplaunchproce; "AipLaunchProcessWithIdentityHelper"
0x18002a4e3  cmovz   rcx, rsi
0x18002a4e7  test    r14, r14
0x18002a4ea  mov     [rsp+5D0h+var_588], rcx
0x18002a4ef  mov     ecx, [rbp+4C0h+var_510]
0x18002a4f2  cmovz   rax, rsi
0x18002a4f6  mov     [rsp+5D0h+var_590], rax
0x18002a4fb  mov     eax, [rbp+4C0h+var_50C]
0x18002a4fe  mov     [rsp+5D0h+var_598], r10
0x18002a503  mov     [rsp+5D0h+dwOptions], eax
0x18002a507  mov     eax, [rbp+4C0h+var_4FC]
0x18002a50a  mov     [rsp+5D0h+bInheritHandle], ecx
0x18002a50e  lea     rcx, [rbp+4C0h+var_300]
0x18002a515  mov     [rsp+5D0h+dwDesiredAccess], eax
0x18002a519  call    ?WatchCurrentThread@LUATelemetry@@SA?AVActivityThreadWatcher@wil@@PEBD0ZZ; LUATelemetry::WatchCurrentThread(char const *,char const *,...)
0x18002a51e  mov     rcx, cs:?g_pCentennialElevationTelemetryRateLimiter@@3V?$unique_ptr@VRateLimiter@@U?$default_delete@VRateLimiter@@@wistd@@@wistd@@A; this
0x18002a525  test    rcx, rcx
0x18002a528  jz      loc_18002A5CC
0x18002a52e  call    ?RequestPermission@RateLimiter@@QEAAHXZ; RateLimiter::RequestPermission(void)
0x18002a533  test    eax, eax
0x18002a535  jz      loc_18002A5CC
0x18002a53b  test    rdi, rdi
0x18002a53e  jnz     short loc_18002A5AE
0x18002a540  mov     ecx, 90h; Size
0x18002a545  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002a54a  xor     r14d, r14d
0x18002a54d  test    rax, rax
0x18002a550  jz      short loc_18002A55F
0x18002a552  mov     rcx, rax
0x18002a555  call    ??0TraceLoggingCorrelationVector@@QEAA@UTraceLoggingCorrelationVectorV2_t@@@Z; TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(TraceLoggingCorrelationVectorV2_t)
0x18002a55a  mov     rdi, rax
0x18002a55d  jmp     short loc_18002A562
0x18002a55f  mov     rdi, r14
0x18002a562  mov     rdx, r14
0x18002a565  lock xadd [rdi+88h], rdx; unsigned __int64
0x18002a56e  lea     r8, [rbp+4C0h+Destination]; char *
0x18002a575  mov     rcx, rdi; this
0x18002a578  call    ?ToStringImpl@TraceLoggingCorrelationVector@@AEAA_N_KPEAD@Z; TraceLoggingCorrelationVector::ToStringImpl(unsigned __int64,char *)
0x18002a57d  test    rdi, rdi
0x18002a580  jz      short loc_18002A58A
0x18002a582  mov     rcx, rdi; Block
0x18002a585  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002a58a  mov     eax, [rbp+4C0h+var_518]
0x18002a58d  mov     r10d, [rbp+4C0h+var_4A0]
0x18002a591  mov     r11d, [rbp+4C0h+var_4C8]
0x18002a595  mov     r13, [rbp+4C0h+var_478]
0x18002a599  mov     r14, [rbp+4C0h+lpFileName]
0x18002a59d  mov     r12, [rbp+4C0h+hMem]
0x18002a5a1  mov     [rbp+4C0h+var_508], eax
0x18002a5a4  mov     [rbp+4C0h+var_4FC], r10d
0x18002a5a8  mov     [rbp+4C0h+var_510], r11d
0x18002a5ac  jmp     short loc_18002A5D4
0x18002a5ae  mov     edx, 81h; SizeInBytes
0x18002a5b3  lea     rcx, [rbp+4C0h+Destination]; Destination
0x18002a5ba  mov     r9d, edx; MaxCount
0x18002a5bd  mov     r8, rdi; Source
0x18002a5c0  call    cs:__imp_strncpy_s
0x18002a5c7  nop     dword ptr [rax+rax+00h]
0x18002a5cc  mov     r10d, [rbp+4C0h+var_4FC]
0x18002a5d0  mov     r11d, [rbp+4C0h+var_510]
0x18002a5d4  mov     rax, [rbp+4C0h+var_470]
0x18002a5d8  xorps   xmm0, xmm0
0x18002a5db  xor     ecx, ecx
0x18002a5dd  movups  xmmword ptr [rax], xmm0
0x18002a5e0  mov     [rax+10h], rcx
0x18002a5e4  mov     r8, cs:WPP_GLOBAL_Control
0x18002a5eb  lea     rax, WPP_GLOBAL_Control
0x18002a5f2  xor     edi, edi
0x18002a5f4  cmp     r8, rax
0x18002a5f7  jz      loc_18002A683
0x18002a5fd  test    byte ptr [r8+1Ch], 1
0x18002a602  jz      short loc_18002A683
0x18002a604  mov     rax, [rbp+4C0h+var_438]
0x18002a60b  lea     r9, [rbp+4C0h+Destination]
0x18002a612  mov     [rsp+5D0h+var_568], r9
0x18002a617  test    rax, rax
0x18002a61a  mov     r9, qword ptr [rbp+4C0h+var_458]
0x18002a61e  mov     rdx, rsi
0x18002a621  mov     qword ptr [rsp+5D0h+var_570], r9
0x18002a626  cmovnz  rdx, rax
0x18002a62a  mov     r9, [rbp+4C0h+var_418]
0x18002a631  test    r12, r12
0x18002a634  mov     [rsp+5D0h+lpValue], r9
0x18002a639  mov     rcx, rsi
0x18002a63c  mov     r9d, dword ptr [rbp+4C0h+hProfile]
0x18002a640  cmovnz  rcx, r12
0x18002a644  mov     qword ptr [rsp+5D0h+var_580], rdx
0x18002a649  test    r14, r14
0x18002a64c  mov     [rsp+5D0h+var_588], rcx
0x18002a651  mov     rax, rsi
0x18002a654  mov     rcx, [r8+10h]
0x18002a658  cmovnz  rax, r14
0x18002a65c  mov     [rsp+5D0h+var_590], rax
0x18002a661  mov     rax, [rbp+4C0h+var_410]
0x18002a668  mov     [rsp+5D0h+var_598], rax
0x18002a66d  mov     eax, [rbp+4C0h+var_50C]
0x18002a670  mov     [rsp+5D0h+dwOptions], eax
0x18002a674  mov     [rsp+5D0h+bInheritHandle], r11d
0x18002a679  mov     [rsp+5D0h+dwDesiredAccess], r10d
0x18002a67e  call    WPP_SF_DDDDSSSSSSs
0x18002a683  test    byte ptr [rbp+4C0h+arg_68], 1
0x18002a68a  jz      short loc_18002A69F
0x18002a68c  lea     rcx, AppInfo_PerfTrack_Elevation_PackagedApp_Start; struct _EVENT_DESCRIPTOR *
0x18002a693  call    ?AiLogPerfTrackEvent@@YAKPEBU_EVENT_DESCRIPTOR@@@Z; AiLogPerfTrackEvent(_EVENT_DESCRIPTOR const *)
0x18002a698  mov     [rbp+4C0h+var_4C0], eax
0x18002a69b  mov     [rbp+4C0h+var_530], 1
0x18002a69f  test    r14, r14
0x18002a6a2  jz      loc_18002AA47
0x18002a6a8  cmp     [rbp+4C0h+packageFamilyName], rbx
0x18002a6ac  jz      loc_18002AA47
0x18002a6b2  cmp     [rbp+4C0h+var_538], rdi
0x18002a6b6  jz      loc_18002AA47
0x18002a6bc  mov     rcx, r14; unsigned __int16 *
0x18002a6bf  call    ?AipJustFileName@@YAPEBGPEBG@Z; AipJustFileName(ushort const *)
0x18002a6c4  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002a6c8  mov     rdi, rax
0x18002a6cb  xor     ecx, ecx
0x18002a6cd  inc     rdi
0x18002a6d0  cmp     [r14+rdi*2], cx
0x18002a6d5  jnz     short loc_18002A6CD
0x18002a6d7  mov     qword ptr [rbp+4C0h+var_458], rdi
0x18002a6db  test    r12, r12
0x18002a6de  jz      short loc_18002A6F0
0x18002a6e0  inc     rax
0x18002a6e3  cmp     [r12+rax*2], cx
0x18002a6e8  jnz     short loc_18002A6E0
0x18002a6ea  mov     qword ptr [rbp+4C0h+var_468], rax
0x18002a6ee  jmp     short loc_18002A6F4
0x18002a6f0  mov     rax, qword ptr [rbp+4C0h+var_468]
0x18002a6f4  mov     ecx, 7FFFh
0x18002a6f9  cmp     rdi, rcx
0x18002a6fc  ja      loc_18002AA47
0x18002a702  cmp     rax, rcx
0x18002a705  ja      loc_18002AA47
0x18002a70b  mov     ecx, [rbp+4C0h+arg_68]
0x18002a711  mov     eax, ecx
0x18002a713  and     eax, 120h
0x18002a718  cmp     eax, 100h
0x18002a71d  jz      loc_18002AA47
0x18002a723  mov     eax, ecx
  ... truncated ...
```
