# AipLaunchProcessWithIdentityHelper(_RPC_ASYNC_STATE *,void *,ushort const *,ushort *,ulong,ulong,ushort const *,ushort const *,_APPINFO_STARTUPINFO *,ushort const *,ushort const *,unsigned __int64,ulong,ulong,void *,unsigned __int64,unsigned __int64 *,_GUID *,unsigned __int64,char const *,int *,UACPROMPT_POLICY *,_APPINFO_PROCESS_INFORMATION *)

- ea: `0x18002a2a8`
- end: `0x18002bf7e`
- name: `?AipLaunchProcessWithIdentityHelper@@YAXPEAU_RPC_ASYNC_STATE@@PEAXPEBGPEAGKK22PEAU_APPINFO_STARTUPINFO@@22_KKK15PEA_KPEAU_GUID@@5PEBDPEAHPEAW4UACPROMPT_POLICY@@PEAU_APPINFO_PROCESS_INFORMATION@@@Z`
- size: `7382`
- prototype: `void __fastcall(struct _RPC_ASYNC_STATE *, void *, const unsigned __int16 *, unsigned __int16 *, unsigned int, unsigned int, const unsigned __int16 *, const unsigned __int16 *, struct _APPINFO_STARTUPINFO *, const unsigned __int16 *, const unsigned __int16 *, unsigned __int64, unsigned int, unsigned int, void *, unsigned __int64, unsigned __int64 *, struct _GUID *, unsigned __int64, const char *Source, int *, enum UACPROMPT_POLICY *, struct _APPINFO_PROCESS_INFORMATION *)`
- caller_count: `2`
- callee_count: `59`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18003ac30`
- `0x18003be40`

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
- `0x180026eb4`
- `0x18002728c`
- `0x1800272f4`
- `0x1800291e0`
- `0x180029d24`
- `0x18002a2a8`
- `0x18002bf84`
- `0x1800337f8`
- `0x180036100`
- `0x18003639c`
- `0x1800389b0`
- `0x1800396ec`
- `0x180039720`
- `0x18003978c`
- `0x18003a204`
- `0x18003c068`
- `0x18003c504`
- `0x18003c5dc`

## import_xrefs

- `msvcrt!strncpy_s` at `0x18002a690`
- `msvcrt!strncpy_s` at `0x18002a690`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18002beff`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18002beff`
- `RPCRT4!RpcImpersonateClient` at `0x18002ab87`
- `RPCRT4!RpcImpersonateClient` at `0x18002ad60`
- `RPCRT4!RpcImpersonateClient` at `0x18002b83b`
- `RPCRT4!RpcImpersonateClient` at `0x18002ab87`
- `RPCRT4!RpcImpersonateClient` at `0x18002ad60`
- `RPCRT4!RpcImpersonateClient` at `0x18002b83b`
- `RPCRT4!RpcRevertToSelf` at `0x18002abaa`
- `RPCRT4!RpcRevertToSelf` at `0x18002adfe`
- `RPCRT4!RpcRevertToSelf` at `0x18002b8ec`
- `RPCRT4!RpcRevertToSelf` at `0x18002abaa`
- `RPCRT4!RpcRevertToSelf` at `0x18002adfe`
- `RPCRT4!RpcRevertToSelf` at `0x18002b8ec`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18002ae77`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18002b6c4`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18002ae77`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18002b6c4`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18002af69`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18002b05d`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18002b701`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18002b71d`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18002af69`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18002b05d`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18002b701`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18002b71d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002aa67`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ae89`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002af07`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002bb73`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002bbea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002aa67`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ae89`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002af07`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002bb73`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002bbea`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x18002bbd9`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x18002bbd9`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x18002be8b`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x18002be8b`
- `api-ms-win-core-processthreads-l1-1-0!OpenThread` at `0x18002bb5b`
- `api-ms-win-core-processthreads-l1-1-0!OpenThread` at `0x18002bb5b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002aa1c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002aa2b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002aa1c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002aa2b`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18002aa57`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18002aa57`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002bd49`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002be3a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002be52`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002be9a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002bd49`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002be3a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002be52`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002be9a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002bd61`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002bd79`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002bd98`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002bdac`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002bed9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002bd61`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002bd79`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002bd98`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002bdac`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002bed9`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18002be71`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18002be71`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002aef1`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002aef1`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x18002a514`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x18002a514`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18002a501`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18002ab2b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18002a501`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18002ab2b`
- `api-ms-win-core-kernel32-private-l1-1-0!CheckElevation` at `0x18002af9b`
- `api-ms-win-core-kernel32-private-l1-1-0!CheckElevation` at `0x18002af9b`
- `api-ms-win-core-kernel32-private-l1-1-0!CheckElevationEnabled` at `0x18002ad25`
- `api-ms-win-core-kernel32-private-l1-1-0!CheckElevationEnabled` at `0x18002ad25`
- `api-ms-win-core-psm-key-l1-1-0!PsmCreateKey` at `0x18002b4c2`
- `api-ms-win-core-psm-key-l1-1-0!PsmCreateKey` at `0x18002b4c2`
- `ntdll!NtClose` at `0x18002b930`
- `ntdll!NtClose` at `0x18002bdc1`
- `ntdll!NtClose` at `0x18002bddd`
- `ntdll!NtClose` at `0x18002bdf5`
- `ntdll!NtClose` at `0x18002b930`
- `ntdll!NtClose` at `0x18002bdc1`
- `ntdll!NtClose` at `0x18002bddd`
- `ntdll!NtClose` at `0x18002bdf5`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18002a86f`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18002abbc`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18002a86f`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18002abbc`
- `USERENV!UnloadUserProfile` at `0x18002b6af`
- `USERENV!UnloadUserProfile` at `0x18002b817`
- `USERENV!UnloadUserProfile` at `0x18002b6af`
- `USERENV!UnloadUserProfile` at `0x18002b817`
- `ext-ms-win-desktopappx-l1-1-0!FreeDesktopAppXLaunchContext` at `0x18002be0a`
- `ext-ms-win-desktopappx-l1-1-0!FreeDesktopAppXLaunchContext` at `0x18002be0a`
- `ext-ms-win-desktopappx-l1-1-0!PostCreateProcessDesktopAppXActivation` at `0x18002bae2`
- `ext-ms-win-desktopappx-l1-1-0!PostCreateProcessDesktopAppXActivation` at `0x18002bae2`
- `ext-ms-win-desktopappx-l1-1-0!PrepareDesktopAppXActivation` at `0x18002b779`
- `ext-ms-win-desktopappx-l1-1-0!PrepareDesktopAppXActivation` at `0x18002b779`
- `ext-ms-win-desktopappx-l1-1-4!DoesPackageHaveElevationCapability` at `0x18002b17e`
- `ext-ms-win-desktopappx-l1-1-4!DoesPackageHaveElevationCapability` at `0x18002b17e`
- `ext-ms-win-desktopappx-l1-1-5!DoesPackageHaveUIAccessCapability` at `0x18002b0a2`
- `ext-ms-win-desktopappx-l1-1-5!DoesPackageHaveUIAccessCapability` at `0x18002b0a2`
- `ext-ms-win-desktopappx-l1-2-2!RundownHeliumContainerForDesktopAppXActivation` at `0x18002bee8`
- `ext-ms-win-desktopappx-l1-2-2!RundownHeliumContainerForDesktopAppXActivation` at `0x18002bee8`
- `ext-ms-win-desktopappx-l1-2-2!BeginCreatingHeliumContainerForDesktopAppXActivation` at `0x18002b95e`
- `ext-ms-win-desktopappx-l1-2-2!BeginCreatingHeliumContainerForDesktopAppXActivation` at `0x18002b95e`
- `ext-ms-win-desktopappx-l1-1-6!VerifyFileIsTrustedAndInPackage` at `0x18002b03e`
- `ext-ms-win-desktopappx-l1-1-6!VerifyFileIsTrustedAndInPackage` at `0x18002b03e`
- `ext-ms-win-appmodel-activation-l1-1-0!PostCreateProcessAppXActivation` at `0x18002ba94`
- `ext-ms-win-appmodel-activation-l1-1-0!PostCreateProcessAppXActivation` at `0x18002ba94`
- `ext-ms-win-appmodel-activation-l1-1-0!PrepareAppXActivation` at `0x18002b5db`
- `ext-ms-win-appmodel-activation-l1-1-0!PrepareAppXActivation` at `0x18002b5db`
- `ext-ms-win-appmodel-activation-l1-1-0!FreeAppXLaunchContext` at `0x18002be1f`
- `ext-ms-win-appmodel-activation-l1-1-0!FreeAppXLaunchContext` at `0x18002be1f`
- `ext-ms-win-appmodel-activation-l1-1-1!RegisterAppXPackageIfNecessary2` at `0x18002b6ea`
- `ext-ms-win-appmodel-activation-l1-1-1!RegisterAppXPackageIfNecessary2` at `0x18002b6ea`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x18002aa07`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x18002aa07`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrIsAllowedToActivateAsUser` at `0x18002a9d5`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrIsAllowedToActivateAsUser` at `0x18002a9d5`
- `ext-ms-win-core-app-package-volume-l1-1-0!MountVolumeForAppPackage` at `0x18002b4f0`
- `ext-ms-win-core-app-package-volume-l1-1-0!MountVolumeForAppPackage` at `0x18002b4f0`
- `ext-ms-win-core-app-package-volume-l1-1-0!UnmountVolumeForAppPackage` at `0x18002bec1`
- `ext-ms-win-core-app-package-volume-l1-1-0!UnmountVolumeForAppPackage` at `0x18002bec1`

## string_xrefs

- `0x18002a574`: `++. hwnd = %x dwClientFlags = %x dwCreationFlags = %x dwTimeout = %x\n	lpDesktop = %ws\n	lpApplicationName = %ws\n	lpCommandLine = %ws\n	lpCurrentDirectory = %ws\n	packageFamilyName = %ws\n	applicationId = %ws\n	szLocalCorrelationVector = %s\n`

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
  struct _PROCESS_INFORMATION *v128; // rdi
  const unsigned __int16 *v129; // rax
  const unsigned __int16 *v130; // r9
  DWORD dwProcessId; // r8d
  HANDLE v132; // rax
  void *v133; // rdi
  int dwDesiredAccess; // [rsp+20h] [rbp-F0h]
  __int64 bInheritHandle; // [rsp+28h] [rbp-E8h]
  PCWSTR dwOptions; // [rsp+30h] [rbp-E0h]
  struct _CONSENTUI_PARAM_HEADER **v137; // [rsp+38h] [rbp-D8h]
  UINT uExitCode; // [rsp+90h] [rbp-80h] BYREF
  wchar_t *v139; // [rsp+98h] [rbp-78h]
  char v140; // [rsp+A0h] [rbp-70h] BYREF
  bool v141; // [rsp+A1h] [rbp-6Fh] BYREF
  bool v142; // [rsp+A2h] [rbp-6Eh] BYREF
  bool v143; // [rsp+A3h] [rbp-6Dh] BYREF
  bool v144; // [rsp+A4h] [rbp-6Ch] BYREF
  bool v145; // [rsp+A5h] [rbp-6Bh] BYREF
  bool v146; // [rsp+A6h] [rbp-6Ah] BYREF
  bool v147; // [rsp+A7h] [rbp-69h] BYREF
  bool v148; // [rsp+A8h] [rbp-68h] BYREF
  bool v149; // [rsp+A9h] [rbp-67h] BYREF
  bool v150; // [rsp+AAh] [rbp-66h] BYREF
  bool v151; // [rsp+ABh] [rbp-65h] BYREF
  HANDLE TargetHandle; // [rsp+B0h] [rbp-60h] BYREF
  unsigned int v153; // [rsp+B8h] [rbp-58h] BYREF
  bool v154; // [rsp+BCh] [rbp-54h] BYREF
  char v155; // [rsp+BDh] [rbp-53h] BYREF
  char v156; // [rsp+BEh] [rbp-52h]
  unsigned int v157; // [rsp+C0h] [rbp-50h]
  unsigned int v158; // [rsp+C4h] [rbp-4Ch] BYREF
  unsigned int v159; // [rsp+C8h] [rbp-48h] BYREF
  unsigned int v160; // [rsp+CCh] [rbp-44h] BYREF
  unsigned int v161; // [rsp+D0h] [rbp-40h] BYREF
  unsigned int v162; // [rsp+D4h] [rbp-3Ch]
  int v163; // [rsp+D8h] [rbp-38h]
  HLOCAL hMem; // [rsp+E0h] [rbp-30h] BYREF
  PCWSTR packageFamilyName; // [rsp+E8h] [rbp-28h]
  int v166[2]; // [rsp+F0h] [rbp-20h] BYREF
  unsigned int v167; // [rsp+F8h] [rbp-18h] BYREF
  HANDLE hProfile; // [rsp+100h] [rbp-10h] BYREF
  unsigned int v169; // [rsp+108h] [rbp-8h] BYREF
  unsigned int v170; // [rsp+110h] [rbp+0h]
  HANDLE hSourceHandle; // [rsp+118h] [rbp+8h] BYREF
  int v172; // [rsp+120h] [rbp+10h] BYREF
  int v173; // [rsp+124h] [rbp+14h] BYREF
  int v174; // [rsp+128h] [rbp+18h] BYREF
  unsigned int v175; // [rsp+130h] [rbp+20h] BYREF
  __int64 v176; // [rsp+138h] [rbp+28h] BYREF
  unsigned int v177; // [rsp+140h] [rbp+30h] BYREF
  int v178; // [rsp+144h] [rbp+34h] BYREF
  int v179; // [rsp+148h] [rbp+38h] BYREF
  LPCWSTR lpFileName; // [rsp+150h] [rbp+40h] BYREF
  HLOCAL v181; // [rsp+158h] [rbp+48h] BYREF
  struct _PROCESS_INFORMATION *v182; // [rsp+160h] [rbp+50h]
  unsigned int v183[2]; // [rsp+168h] [rbp+58h]
  __int64 v184; // [rsp+170h] [rbp+60h] BYREF
  unsigned int v185[2]; // [rsp+178h] [rbp+68h]
  int v186; // [rsp+180h] [rbp+70h] BYREF
  HANDLE hObject; // [rsp+188h] [rbp+78h]
  void *v188; // [rsp+190h] [rbp+80h] BYREF
  HLOCAL v189; // [rsp+198h] [rbp+88h] BYREF
  HLOCAL v190; // [rsp+1A0h] [rbp+90h] BYREF
  void *Block; // [rsp+1A8h] [rbp+98h] BYREF
  int v192; // [rsp+1B0h] [rbp+A0h] BYREF
  int v193; // [rsp+1B4h] [rbp+A4h] BYREF
  PCWSTR v194; // [rsp+1B8h] [rbp+A8h] BYREF
  unsigned __int16 *v195; // [rsp+1C0h] [rbp+B0h] BYREF
  unsigned __int16 *Src; // [rsp+1C8h] [rbp+B8h]
  unsigned __int16 *v197; // [rsp+1D0h] [rbp+C0h]
  unsigned __int16 *v198; // [rsp+1D8h] [rbp+C8h]
  unsigned __int16 *v199; // [rsp+1E0h] [rbp+D0h]
  unsigned __int16 *v200; // [rsp+1E8h] [rbp+D8h]
  HANDLE Handle; // [rsp+1F0h] [rbp+E0h] BYREF
  HANDLE hToken; // [rsp+1F8h] [rbp+E8h]
  struct _APPINFO_STARTUPINFO *v203[3]; // [rsp+200h] [rbp+F0h] BYREF
  void *v204; // [rsp+218h] [rbp+108h]
  LARGE_INTEGER v205; // [rsp+220h] [rbp+110h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+228h] [rbp+118h] BYREF
  LARGE_INTEGER Frequency; // [rsp+230h] [rbp+120h] BYREF
  HANDLE v208; // [rsp+238h] [rbp+128h]
  void *v209; // [rsp+240h] [rbp+130h] BYREF
  __int128 v210; // [rsp+248h] [rbp+138h] BYREF
  __int64 v211; // [rsp+258h] [rbp+148h]
  int *v212; // [rsp+260h] [rbp+150h]
  void *v213; // [rsp+268h] [rbp+158h]
  PRPC_ASYNC_STATE pAsync; // [rsp+270h] [rbp+160h]
  __int128 v215; // [rsp+278h] [rbp+168h] BYREF
  __int128 v216; // [rsp+288h] [rbp+178h]
  __int64 v217; // [rsp+298h] [rbp+188h]
  __int128 v218; // [rsp+2A0h] [rbp+190h] BYREF
  __int128 v219; // [rsp+2B0h] [rbp+1A0h]
  __int64 v220; // [rsp+2C0h] [rbp+1B0h]
  char v221[80]; // [rsp+2D0h] [rbp+1C0h] BYREF
  char Destination[144]; // [rsp+320h] [rbp+210h] BYREF
  _BYTE v223[464]; // [rsp+3B0h] [rbp+2A0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+5D8h] [rbp+4C8h]

  v23 = Source;
  v197 = a8;
  v24 = a3;
  v25 = a4;
  packageFamilyName = a10;
  v139 = a11;
  v162 = a5;
  v175 = a5;
  v157 = a6;
  v169 = a6;
  v203[0] = a9;
  hProfile = a12;
  v158 = a13;
  v213 = a15;
  v203[2] = (struct _APPINFO_STARTUPINFO *)a17;
  v203[1] = (struct _APPINFO_STARTUPINFO *)a18;
  v212 = a21;
  *(_QWORD *)v166 = a22;
  pAsync = a1;
  v182 = (struct _PROCESS_INFORMATION *)a23;
  v200 = a7;
  v189 = a7;
  hObject = (HANDLE)-1LL;
  v26 = 0;
  v211 = 0;
  AppModelIdentityActivationProperties = 0;
  v217 = 0;
  v220 = 0;
  v199 = a4;
  v198 = a3;
  v188 = a2;
  lpFileName = a3;
  hMem = a4;
  v167 = 0;
  v159 = 0;
  v153 = 0;
  v192 = 0;
  v161 = 0;
  v181 = 0;
  v204 = 0;
  Handle = 0;
  hSourceHandle = 0;
  v209 = 0;
  TargetHandle = 0;
  v208 = 0;
  hToken = 0;
  v178 = 0;
  *(_QWORD *)v183 = 0;
  v177 = 0;
  v170 = 0;
  v186 = 0;
  v172 = 6;
  v190 = 0;
  v210 = 0;
  v176 = 0;
  v215 = 0;
  v184 = 0;
  v216 = 0;
  v163 = 0;
  v218 = 0;
  Src = 0;
  v219 = 0;
  v28 = 0;
  v160 = 0;
  v174 = 0;
  v173 = 0;
  v140 = 0;
  v150 = 0;
  v142 = 0;
  v149 = 0;
  v148 = 0;
  v147 = 0;
  v141 = 0;
  v144 = 0;
  memset_0(v223, 0, sizeof(v223));
  v193 = 464;
  Block = 0;
  v156 = 0;
  memset_0(Destination, 0, 0x81u);
  Frequency.QuadPart = 0;
  PerformanceCount.QuadPart = 0;
  v205.QuadPart = 0;
  QueryPerformanceCounter(&PerformanceCount);
  QueryPerformanceFrequency(&Frequency);
  v29 = L"NULL";
  v30 = a11;
  if ( !a11 )
    v30 = L"NULL";
  v31 = packageFamilyName;
  if ( !packageFamilyName )
    v31 = L"NULL";
  v32 = v197;
  *(_QWORD *)v185 = v30;
  v33 = v200;
  v194 = v31;
  if ( !v197 )
    v32 = L"NULL";
  v195 = v32;
  v34 = v25;
  if ( !v200 )
    v33 = L"NULL";
  v35 = v24;
  if ( !v25 )
    v34 = L"NULL";
  if ( !v24 )
    v35 = L"NULL";
  LUATelemetry::WatchCurrentThread(
    v221,
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
    v162,
    v157,
    v158,
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
    v38 = v162;
    v39 = v157;
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
  v38 = v175;
  v39 = v169;
  v26 = (unsigned __int16 *)v181;
  v24 = (unsigned __int16 *)lpFileName;
  v25 = (unsigned __int16 *)hMem;
  v159 = v153;
  v162 = v175;
  v157 = v169;
LABEL_24:
  v40 = v182;
  *(_OWORD *)&v182->hProcess = 0;
  *(_QWORD *)&v40->dwProcessId = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v41 = L"NULL";
    if ( v189 )
      v41 = (const unsigned __int16 *)v189;
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
      v158,
      (__int64)v195,
      (__int64)v43,
      (__int64)v42,
      (__int64)v41,
      (__int64)v194,
      *(__int64 *)v185,
      (__int64)Destination);
  }
  if ( (a14 & 1) != 0 )
  {
    v170 = AiLogPerfTrackEvent(&AppInfo_PerfTrack_Elevation_PackagedApp_Start);
    v140 = 1;
  }
  if ( !v24 || !packageFamilyName || !v139 )
    goto LABEL_94;
  AipJustFileName(v24);
  v44 = -1;
  v45 = -1;
  do
    ++v45;
  while ( v24[v45] );
  *(_QWORD *)v185 = v45;
  if ( v25 )
  {
    do
      ++v44;
    while ( v25[v44] );
    *(_QWORD *)v183 = v44;
  }
  else
  {
    v44 = *(_QWORD *)v183;
  }
  if ( v45 > 0x7FFF || v44 > 0x7FFF || (a14 & 0x120) == 0x100 || (a14 & 0x810) == 0x800 )
    goto LABEL_94;
  uExitCode = AiGetClientInformation(v188, &Handle, &hSourceHandle, &v167, &v177);
  if ( uExitCode )
  {
LABEL_95:
    v54 = v139;
    goto LABEL_96;
  }
  if ( *(_QWORD *)v166 )
  {
    v173 = **(_DWORD **)v166;
  }
  else
  {
    v166[0] = 0;
    v46 = LUAGetUACPromptPolicy(v166, &v173);
    if ( v46 < 0 )
      goto LABEL_54;
  }
  if ( v212 )
  {
    v174 = *v212;
  }
  else
  {
    v166[0] = 0;
    v46 = AiCheckForElevatedUser(hSourceHandle, v166);
    if ( v46 < 0 )
      goto LABEL_54;
    v46 = AiCheckForAdminUser(hSourceHandle, v166[0], &v174);
    if ( v46 < 0 )
      goto LABEL_54;
  }
  v143 = 0;
  v151 = 0;
  v146 = 0;
  v145 = 0;
  v154 = 0;
  AppModelIdentityActivationProperties = GetAppModelIdentityActivationProperties(
                                           hSourceHandle,
                                           v139,
                                           0,
                                           a14,
                                           (enum AppModel::RuntimeBehavior *)&v160,
                                           &v143,
                                           &v151,
                                           &v146,
                                           &v145,
                                           &v154);
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
  if ( v154 )
    a14 |= 0x2000u;
  if ( v140 && v143 )
    goto LABEL_66;
  if ( v160 == 1 )
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
    v155 = 0;
    AppModelIdentityActivationProperties = UMgrIsAllowedToActivateAsUser(hSourceHandle, a16, &v155);
    if ( AppModelIdentityActivationProperties < 0 )
      goto LABEL_69;
    if ( !v155 )
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
    v45 = *(_QWORD *)v185;
  }
  if ( (v162 & 8) != 0 )
  {
    v52 = AiConvertWow64Paths(
            v198,
            &lpFileName,
            v199,
            (unsigned __int16 **)&hMem,
            v200,
            (const unsigned __int16 **)&v189);
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
      *(_QWORD *)v185 = v45;
    }
    v25 = (unsigned __int16 *)hMem;
    if ( hMem )
    {
      v53 = -1;
      do
        ++v53;
      while ( *((_WORD *)hMem + v53) );
      *(_QWORD *)v183 = v53;
    }
    else
    {
      v53 = *(_QWORD *)v183;
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
  PackageFullNameFromFamilyName = GetPackageFullNameFromFamilyName(packageFamilyName, (unsigned __int16 **)&v181);
  RpcRevertToSelf();
  if ( PackageFullNameFromFamilyName < 0 )
  {
    v57 = RtlNtStatusToDosErrorNoTeb(PackageFullNameFromFamilyName);
    v26 = (unsigned __int16 *)v181;
    uExitCode = v57;
    goto LABEL_95;
  }
  v26 = (unsigned __int16 *)v181;
  PackageProperties = GetPackageProperties(
                        (const unsigned __int16 *)v181,
                        &v150,
                        &v142,
                        &v149,
                        &v148,
                        &v147,
                        &v141,
                        &v144,
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
  if ( v141 && !v142 )
  {
    v166[0] = 0;
    v46 = AiCheckForTcbPrivilege(hSourceHandle, v166);
    if ( v46 < 0 )
      goto LABEL_54;
    if ( !v166[0] )
    {
      v141 = 0;
      v64 = v25;
      if ( v24 )
        v64 = v24;
      DoesExecutableExistInPackage = AiDoesExecutableExistInPackage(v26, v64, &v141);
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
      if ( !v141 )
        goto LABEL_75;
    }
  }
  if ( !v160 )
    goto LABEL_227;
  v163 = 2;
  if ( !v140 )
    goto LABEL_227;
  uExitCode = CheckElevationEnabled(&v186);
  if ( uExitCode )
    goto LABEL_95;
  if ( !v186 )
  {
    v140 = 0;
    goto LABEL_227;
  }
  v140 = 1;
  v46 = LUAGetUserType(TargetHandle, &v178);
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
  LOBYTE(v66) = v143;
  v54 = v139;
  uExitCode = AdjustActivationToken(TargetHandle, v160, v66, 0);
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
      WPP_SF_DSSSS(v78, v77, v74, v75, (__int64)v29, (__int64)v79, (__int64)packageFamilyName, (__int64)v139);
      goto LABEL_153;
    }
    goto LABEL_153;
  }
  v80 = v25;
  if ( v24 )
    v80 = v24;
  uExitCode = CheckElevation(v80, &v192, 0, &v161, &v172);
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
    && v161 - 16 <= 2
    && (unsigned int)LUAIsShadowAdminEnabled() )
  {
    v81 = v25;
    if ( v24 )
      v81 = v24;
    AipCheckAssistiveTechnologyList(v81, &v153);
  }
  v82 = v25;
  if ( v24 )
    v82 = v24;
  uExitCode = AiCheckSecureApplicationDirectory(v82, &v153);
  if ( uExitCode )
    goto LABEL_153;
  LODWORD(v188) = 0;
  IsTrustedAndInPackage = VerifyFileIsTrustedAndInPackage(v24, v26, &v188);
  if ( IsTrustedAndInPackage < 0 )
  {
    uExitCode = WIN32_FROM_HRESULT(IsTrustedAndInPackage);
    goto LABEL_153;
  }
  RevertToSelf();
  v85 = v161;
  if ( v161 - 16 > 2 )
  {
    v92 = v153;
  }
  else
  {
    v163 = 3;
    v166[0] = 0;
    LOBYTE(v84) = 1;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_CentennialUIAccess>::ReportUsage(
      &`wil::Feature<__WilFeatureTraits_Feature_CentennialUIAccess>::GetImpl'::`2'::impl,
      v84);
    if ( !(unsigned __int8)IsDoesPackageHaveUIAccessCapabilityPresent() )
      goto LABEL_175;
    HaveUIAccessCapability = DoesPackageHaveUIAccessCapability(v26, v166);
    if ( HaveUIAccessCapability < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x20A1,
        v86,
        (const char *)(unsigned int)HaveUIAccessCapability,
        dwDesiredAccess);
      goto LABEL_175;
    }
    if ( !v166[0] )
    {
LABEL_175:
      uExitCode = 50;
      v88 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_96;
      v89 = 51;
      goto LABEL_178;
    }
    v85 = v161;
    if ( v161 >= 3 )
    {
      v85 = v161 - 16;
      v161 -= 16;
    }
    v92 = v153 | 0x8000C;
    v153 |= 0x8000Cu;
  }
  LODWORD(hMem) = v162 & 1;
  if ( (v162 & 1) != 0 )
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
          v153 = v92;
        }
        v161 = 2;
        v172 = 6;
      }
      if ( (v162 & 0x10) != 0 )
        v153 = v92 | 0x800;
      if ( v142 || !(_DWORD)v188 )
      {
        v96 = v25;
        if ( v24 )
          v96 = v24;
        v94 = AiBuildEXEParams(
                v96,
                hObject,
                v24,
                v185[0],
                v25,
                v183[0],
                0,
                v177,
                (struct _CONSENTUI_PARAM_HEADER **)&v190);
        v54 = v139;
      }
      else
      {
        v54 = v139;
        v93 = v25;
        v172 = 8;
        if ( v24 )
          v93 = v24;
        v94 = AiBuildPackagedAppParams(
                v93,
                v185[0],
                v25,
                v183[0],
                v177,
                (wchar_t *)packageFamilyName,
                v139,
                (struct _CONSENTUI_PARAM_HEADER **)&v190);
      }
      uExitCode = v94;
      if ( v94 )
        goto LABEL_96;
      v95 = v190;
      *((_DWORD *)v190 + 13) = v170;
      uExitCode = AiCheckLUA(
                    v161,
                    &v153,
                    (unsigned int)v172,
                    TargetHandle,
                    v95,
                    v197,
                    hProfile,
                    v167,
                    v158,
                    Destination,
                    &v209);
      LODWORD(v68) = uExitCode;
      if ( uExitCode )
      {
        v69 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_96;
        v70 = 53;
        goto LABEL_132;
      }
      v97 = v209;
      if ( v209 )
      {
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShadowAdmin>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_ShadowAdmin>::GetImpl'::`2'::impl) )
        {
          v157 &= 0xFFFFFFFC;
          v169 = v157;
        }
        v98 = v153 | 1;
        TargetHandle = v97;
      }
      else
      {
        v98 = v153;
      }
      v159 = v98;
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
        v54 = v139;
        v101 = ParseAppUserModelId(v139, v100, (unsigned __int16 **)&hMem);
        AppModelIdentityActivationProperties = v101;
        if ( v101 < 0 )
        {
          v102 = WIN32_FROM_HRESULT(v101);
LABEL_232:
          uExitCode = v102;
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&hMem);
          goto LABEL_96;
        }
        v103 = PsmCreateKey(v26, hMem, v223, &v193);
        if ( v103 < 0 )
        {
          v102 = WIN32_FROM_NTSTATUS(v103);
          goto LABEL_232;
        }
        v104 = MountVolumeForAppPackage(v223, *(_QWORD *)Block, v167);
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
        v156 = 1;
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&hMem);
      }
      v108 = ShouldAdjustActivationToken();
      v109 = v108;
      v141 = v108;
      if ( v142 || (v170 = 0, (a14 & 6) != 0) )
        v170 = 1;
      v163 = 1;
      if ( !v160 )
      {
        *(_QWORD *)&v218 = TargetHandle;
        *((_QWORD *)&v218 + 1) = hSourceHandle;
        HIDWORD(v220) = v151;
        *(_QWORD *)&v219 = v26;
        *((_QWORD *)&v219 + 1) = v24;
        v110 = PrepareAppXActivation(&v218, &v184);
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
        if ( *(_DWORD *)(v184 + 8) )
          Src = *(unsigned __int16 **)(v184 + 24);
LABEL_284:
        if ( v109 )
        {
          v163 = 4;
          LastError = RpcImpersonateClient(0);
          if ( LastError )
            goto LABEL_55;
          v54 = v139;
          LOBYTE(v116) = v151;
          LOBYTE(v115) = v143;
          uExitCode = AdjustActivationToken(TargetHandle, v160, v115, v116);
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
          v117 = v204;
          TargetHandle = v204;
        }
        else
        {
          v117 = TargetHandle;
        }
        if ( v160 - 1 <= 2 )
        {
          v118 = BeginCreatingHeliumContainerForDesktopAppXActivation(v117, v176);
          v117 = TargetHandle;
          v28 = v118;
        }
        v119 = v157 & 4;
        v120 = v141;
        v141 = -v141;
        v163 = 5;
        uExitCode = AiLaunchProcess(
                      Handle,
                      v117,
                      hObject,
                      v159,
                      v24,
                      v25,
                      v157 | 4,
                      (const unsigned __int16 *)v189,
                      v197,
                      v203[0],
                      v167,
                      (_WORD *)((unsigned __int64)v26 & -(__int64)v120),
                      a14,
                      v213,
                      a19,
                      Src,
                      v182);
        v68 = uExitCode;
        if ( uExitCode )
        {
          v69 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
            goto LABEL_95;
          v54 = v139;
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v70 = 58;
LABEL_132:
            v71 = v69[2];
            v72 = L"NULL";
            v137 = (struct _CONSENTUI_PARAM_HEADER **)v54;
            if ( v25 )
              v72 = v25;
            dwOptions = packageFamilyName;
            bInheritHandle = (__int64)v72;
LABEL_135:
            if ( v24 )
              v29 = v24;
            WPP_SF_DSSSS(v71, v70, (_DWORD)v67, v68, (__int64)v29, bInheritHandle, (__int64)dwOptions, (__int64)v137);
            goto LABEL_96;
          }
          goto LABEL_96;
        }
        v163 = 6;
        if ( v160 )
        {
          if ( v160 - 1 > 2 )
          {
            v121 = 0;
          }
          else
          {
            *(_DWORD *)(v176 + 40) = v157;
            v211 = *(_QWORD *)&v182->dwProcessId;
            AppModelIdentityActivationProperties = PostCreateProcessDesktopAppXActivation(
                                                     TargetHandle,
                                                     v176,
                                                     &v210,
                                                     v68);
            v121 = *(_DWORD *)(v176 + 16);
          }
        }
        else
        {
          *(_DWORD *)(v184 + 32) = v157;
          v211 = *(_QWORD *)&v182->dwProcessId;
          AppModelIdentityActivationProperties = PostCreateProcessAppXActivation(TargetHandle, v184, &v210, v68);
          v121 = *(_DWORD *)(v184 + 8);
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
          v163 = 7;
          v122 = OpenThread(2u, 0, v182->dwThreadId);
          v208 = v122;
          if ( !v122 )
          {
            v123 = GetLastError();
            uExitCode = v123;
            v67 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
              goto LABEL_95;
            v54 = v139;
            if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
              goto LABEL_96;
            v70 = 60;
LABEL_313:
            v137 = (struct _CONSENTUI_PARAM_HEADER **)v54;
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
            v54 = v139;
            if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
              goto LABEL_96;
            v70 = 61;
            goto LABEL_313;
          }
        }
        v54 = v139;
        uExitCode = 0;
        goto LABEL_96;
      }
      if ( v160 - 1 > 2 )
        goto LABEL_284;
      hProfile = 0;
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShadowAdmin>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_ShadowAdmin>::GetImpl'::`2'::impl) )
      {
        if ( (v159 & 0x21) != 1 && ((v159 & 0x8000000) == 0 || !(unsigned int)LUAIsShadowAdminEnabled()) )
          goto LABEL_268;
      }
      else if ( (v159 & 0x21) != 1 )
      {
        goto LABEL_268;
      }
      uExitCode = AipLoadUserProfile(TargetHandle, &hProfile);
      if ( uExitCode )
        goto LABEL_261;
      ImpersonateLoggedOnUser(TargetHandle);
      v158 = 0;
      if ( (int)RegisterAppXPackageIfNecessary2(0, v139, 0, 0) < 0 )
      {
        uExitCode = 15669;
        RevertToSelf();
        goto LABEL_261;
      }
      RevertToSelf();
LABEL_268:
      *(_QWORD *)&v215 = TargetHandle;
      *((_QWORD *)&v215 + 1) = hSourceHandle;
      v111 = 0;
      *(_QWORD *)&v216 = v26;
      *((_QWORD *)&v216 + 1) = v24;
      if ( v160 == 2 )
        v111 = 8;
      LODWORD(v217) = v170 | v217 | (2 * v109) | v111;
      v112 = PrepareDesktopAppXActivation(&v215, &v176);
      AppModelIdentityActivationProperties = v112;
      if ( v112 >= 0 )
      {
        if ( v140 )
          *(_DWORD *)(v176 + 16) = 0;
        if ( *(_DWORD *)(v176 + 16) )
          Src = *(unsigned __int16 **)(v176 + 32);
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
    if ( !AiIsElevationAllowedForSession(v167) )
    {
LABEL_66:
      uExitCode = 50;
      goto LABEL_95;
    }
    v85 = v161;
    goto LABEL_198;
  }
  v166[0] = 0;
  if ( (unsigned __int8)IsDoesPackageHaveElevationCapabilityPresent()
    && (int)DoesPackageHaveElevationCapability(v26, v166) >= 0
    && v166[0] )
  {
    LODWORD(v195) = -1;
    LODWORD(v194) = v173;
    v178 = 0;
    v159 = uExitCode;
    LUATelemetry::CentennialElevation<long,unsigned short * &,unsigned short const * &,unsigned long &,unsigned long &,unsigned long &,unsigned long &,bool &,int &,unsigned long,int,int,char (&)[129]>(
      (unsigned int)&v159,
      (unsigned int)&v181,
      (unsigned int)&lpFileName,
      (unsigned int)&uExitCode,
      (__int64)&v175,
      (__int64)&v169,
      (__int64)&a14,
      (__int64)&v140,
      (__int64)&v174,
      (__int64)&v194,
      (__int64)&v195,
      (__int64)&v178,
      Destination);
    v85 = v161;
    goto LABEL_194;
  }
  uExitCode = 50;
  v88 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
    goto LABEL_95;
  v54 = v139;
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
  QueryPerformanceCounter(&v205);
  v179 = 1;
  v203[0] = (struct _APPINFO_STARTUPINFO *)(1000 * (v205.QuadPart - PerformanceCount.QuadPart) / Frequency.QuadPart);
  LODWORD(hMem) = v173;
  v55 = uExitCode;
  if ( uExitCode == 1223 )
  {
    v158 = 0;
  }
  else
  {
    if ( (int)uExitCode > 0 )
      v55 = (unsigned __int16)uExitCode | 0x80070000;
    v158 = v55;
  }
  LUATelemetry::CentennialElevation<long,unsigned short * &,unsigned short const * &,unsigned long &,unsigned long &,unsigned long &,unsigned long &,bool &,int &,unsigned long,__int64 &,int,char (&)[129]>(
    (unsigned int)&v158,
    (unsigned int)&v181,
    (unsigned int)&lpFileName,
    (unsigned int)&uExitCode,
    (__int64)&v175,
    (__int64)&v169,
    (__int64)&a14,
    (__int64)&v140,
    (__int64)&v174,
    (__int64)&hMem,
    (__int64)v203,
    (__int64)&v179,
    Destination);
  if ( uExitCode )
  {
    v125 = v163;
    if ( v163 != 1 && v163 != 6 )
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
    v128 = v182;
  }
  else
  {
    v129 = AipJustFileName(v24);
    v130 = v54;
    v128 = v182;
    AipLogDesktopAppXProcessStartSuccess(v182->dwProcessId, v26, v129, v130, L"[LaunchProcess]");
  }
  if ( hObject != (HANDLE)-1LL )
    CloseHandle(hObject);
  if ( v24 != v198 )
    LocalFree(v24);
  if ( v25 != v199 )
    LocalFree(v25);
  if ( v189 != v200 )
    LocalFree(v189);
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
  if ( v176 )
    FreeDesktopAppXLaunchContext();
  if ( v184 )
    FreeAppXLaunchContext();
  if ( v208 )
    CloseHandle(v208);
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
    if ( v156 )
      UnmountVolumeForAppPackage(v223, *(_QWORD *)Block, v167);
  }
  if ( v190 )
    LocalFree(v190);
  RundownHeliumContainerForDesktopAppXActivation(v28);
  RpcAsyncCompleteCall(pAsync, &uExitCode);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 62, &WPP_5a99e4d32d543c5ccd81a78831f70868_Traceguids, uExitCode);
  wil::ActivityThreadWatcher::~ActivityThreadWatcher((wil::ActivityThreadWatcher *)v221);
  if ( Block )
    operator delete(Block);
}

```

## disassembly

```asm
0x18002a2a8  push    rbp
0x18002a2aa  push    rbx
0x18002a2ab  push    rsi
0x18002a2ac  push    rdi
0x18002a2ad  push    r12
0x18002a2af  push    r13
0x18002a2b1  push    r14
0x18002a2b3  push    r15
0x18002a2b5  lea     rbp, [rsp-488h]
0x18002a2bd  sub     rsp, 598h
0x18002a2c4  mov     rax, cs:__security_cookie
0x18002a2cb  xor     rax, rsp
0x18002a2ce  mov     [rbp+4C0h+var_50], rax
0x18002a2d5  mov     rax, [rbp+4C0h+arg_38]
0x18002a2dc  xorps   xmm0, xmm0
0x18002a2df  mov     rdi, [rbp+4C0h+Source]
0x18002a2e6  xorps   xmm1, xmm1
0x18002a2e9  mov     [rbp+4C0h+var_400], rax
0x18002a2f0  mov     r14, r8
0x18002a2f3  mov     rax, [rbp+4C0h+arg_48]
0x18002a2fa  mov     r12, r9
0x18002a2fd  mov     [rbp+4C0h+packageFamilyName], rax
0x18002a301  mov     rax, [rbp+4C0h+arg_50]
0x18002a308  mov     [rbp+4C0h+var_538], rax
0x18002a30c  mov     eax, [rbp+4C0h+arg_20]
0x18002a312  mov     [rbp+4C0h+var_4FC], eax
0x18002a315  mov     [rbp+4C0h+var_4A0], eax
0x18002a318  mov     eax, [rbp+4C0h+arg_28]
0x18002a31e  mov     [rbp+4C0h+var_510], eax
0x18002a321  mov     [rbp+4C0h+var_4C8], eax
0x18002a324  mov     rax, [rbp+4C0h+arg_40]
0x18002a32b  mov     [rbp+4C0h+var_3D0], rax
0x18002a332  mov     rax, [rbp+4C0h+arg_58]
0x18002a339  mov     [rbp+4C0h+hProfile], rax
0x18002a33d  mov     eax, [rbp+4C0h+arg_60]
0x18002a343  mov     [rbp+4C0h+var_50C], eax
0x18002a346  mov     rax, [rbp+4C0h+arg_70]
0x18002a34d  mov     [rbp+4C0h+var_368], rax
0x18002a354  mov     rax, [rbp+4C0h+arg_80]
0x18002a35b  mov     [rbp+4C0h+var_3C0], rax
0x18002a362  mov     rax, [rbp+4C0h+arg_88]
0x18002a369  mov     [rbp+4C0h+var_3C8], rax
0x18002a370  mov     rax, [rbp+4C0h+arg_A0]
0x18002a377  mov     [rbp+4C0h+var_370], rax
0x18002a37e  mov     rax, [rbp+4C0h+arg_A8]
0x18002a385  mov     qword ptr [rbp+4C0h+var_4E0], rax
0x18002a389  mov     rax, [rbp+4C0h+arg_B0]
0x18002a390  mov     [rbp+4C0h+pAsync], rcx
0x18002a397  mov     rcx, [rbp+4C0h+arg_30]
0x18002a39e  mov     [rbp+4C0h+var_470], rax
0x18002a3a2  xor     eax, eax
0x18002a3a4  mov     [rbp+4C0h+var_3E8], rcx
0x18002a3ab  mov     [rbp+4C0h+var_438], rcx
0x18002a3b2  xor     ecx, ecx
0x18002a3b4  or      [rbp+4C0h+hObject], 0FFFFFFFFFFFFFFFFh
0x18002a3b9  mov     r13d, ecx
0x18002a3bc  mov     [rbp+4C0h+var_378], rax
0x18002a3c3  mov     r15d, ecx
0x18002a3c6  mov     [rbp+4C0h+var_338], rax
0x18002a3cd  mov     [rbp+4C0h+var_310], rax
0x18002a3d4  mov     [rbp+4C0h+var_3F0], r9
0x18002a3db  mov     [rbp+4C0h+var_3F8], r8
0x18002a3e2  mov     [rbp+4C0h+var_440], rdx
0x18002a3e9  mov     [rbp+4C0h+lpFileName], r8
0x18002a3ed  mov     [rbp+4C0h+hMem], r9
0x18002a3f1  mov     [rbp+4C0h+var_4D8], ecx
0x18002a3f4  mov     [rbp+4C0h+var_508], ecx
0x18002a3f7  mov     [rbp+4C0h+var_518], ecx
0x18002a3fa  mov     [rbp+4C0h+var_420], ecx
0x18002a400  mov     [rbp+4C0h+var_500], ecx
0x18002a403  mov     [rbp+4C0h+var_478], rcx
0x18002a407  mov     [rbp+4C0h+var_3B8], rcx
0x18002a40e  mov     [rbp+4C0h+Handle], rcx
0x18002a415  mov     [rbp+4C0h+hSourceHandle], rcx
0x18002a419  mov     [rbp+4C0h+var_390], rcx
0x18002a420  mov     [rbp+4C0h+TargetHandle], rcx
0x18002a424  mov     [rbp+4C0h+var_398], rcx
0x18002a42b  mov     [rbp+4C0h+hToken], rcx
0x18002a432  mov     [rbp+4C0h+var_48C], ecx
0x18002a435  mov     qword ptr [rbp+4C0h+var_468], rcx
0x18002a439  mov     [rbp+4C0h+var_490], ecx
0x18002a43c  mov     [rbp+4C0h+var_4C0], ecx
0x18002a43f  mov     [rbp+4C0h+var_450], ecx
0x18002a442  mov     [rbp+4C0h+var_4B0], 6
0x18002a449  mov     [rbp+4C0h+var_430], rcx
0x18002a450  movups  [rbp+4C0h+var_388], xmm0
0x18002a457  mov     [rbp+4C0h+var_498], rcx
0x18002a45b  movups  [rbp+4C0h+var_358], xmm1
0x18002a462  mov     [rbp+4C0h+var_460], rcx
0x18002a466  movups  [rbp+4C0h+var_348], xmm1
0x18002a46d  mov     [rbp+4C0h+var_4F8], ecx
0x18002a470  movups  [rbp+4C0h+var_330], xmm0
0x18002a477  mov     [rbp+4C0h+var_408], rcx
0x18002a47e  movups  [rbp+4C0h+var_320], xmm0
0x18002a485  mov     ebx, ecx
0x18002a487  mov     [rbp+4C0h+var_504], ecx
0x18002a48a  mov     [rbp+4C0h+var_4A8], ecx
0x18002a48d  mov     esi, 1D0h
0x18002a492  mov     [rbp+4C0h+var_4AC], ecx
0x18002a495  mov     r8d, esi; Size
0x18002a498  mov     [rbp+4C0h+var_530], cl
0x18002a49b  xor     edx, edx; Val
0x18002a49d  mov     [rbp+4C0h+var_526], cl
0x18002a4a0  mov     [rbp+4C0h+var_52E], cl
0x18002a4a3  mov     [rbp+4C0h+var_527], cl
0x18002a4a6  mov     [rbp+4C0h+var_528], cl
0x18002a4a9  mov     [rbp+4C0h+var_529], cl
0x18002a4ac  mov     [rbp+4C0h+var_52F], cl
0x18002a4af  mov     [rbp+4C0h+var_52C], cl
0x18002a4b2  lea     rcx, [rbp+4C0h+var_220]; void *
0x18002a4b9  call    memset_0
0x18002a4be  mov     [rbp+4C0h+var_41C], esi
0x18002a4c4  lea     rcx, [rbp+4C0h+Destination]; void *
0x18002a4cb  xor     esi, esi
0x18002a4cd  xor     edx, edx; Val
0x18002a4cf  mov     r8d, 81h; Size
0x18002a4d5  mov     [rbp+4C0h+Block], rsi
0x18002a4dc  mov     [rbp+4C0h+var_512], sil
0x18002a4e0  call    memset_0
0x18002a4e5  lea     rcx, [rbp+4C0h+PerformanceCount]; lpPerformanceCount
0x18002a4ec  mov     qword ptr [rbp+4C0h+Frequency], rsi
0x18002a4f3  mov     qword ptr [rbp+4C0h+PerformanceCount], rsi
0x18002a4fa  mov     qword ptr [rbp+4C0h+var_3B0], rsi
0x18002a501  call    cs:__imp_QueryPerformanceCounter
0x18002a508  nop     dword ptr [rax+rax+00h]
0x18002a50d  lea     rcx, [rbp+4C0h+Frequency]; lpFrequency
0x18002a514  call    cs:__imp_QueryPerformanceFrequency
0x18002a51b  nop     dword ptr [rax+rax+00h]
0x18002a520  mov     rax, [rbp+4C0h+var_538]
0x18002a524  lea     rsi, aNull_0; "NULL"
0x18002a52b  test    rax, rax
0x18002a52e  mov     r8, rax
0x18002a531  mov     rax, [rbp+4C0h+packageFamilyName]
0x18002a535  mov     r11, r14
0x18002a538  cmovz   r8, rsi
0x18002a53c  lea     r11, [rbp+4C0h+Destination]
0x18002a543  test    rax, rax
0x18002a546  mov     [rsp+5D0h+var_568], r11
0x18002a54b  mov     qword ptr [rsp+5D0h+var_570], r8
0x18002a550  mov     r9, rax
0x18002a553  mov     rax, [rbp+4C0h+var_400]
0x18002a55a  cmovz   r9, rsi
0x18002a55e  test    rax, rax
0x18002a561  mov     [rsp+5D0h+lpValue], r9
0x18002a566  mov     r10, rax
0x18002a569  mov     qword ptr [rbp+4C0h+var_458], r8
0x18002a56d  mov     rax, [rbp+4C0h+var_3E8]
0x18002a574  lea     r8, aHwndXDwclientf_0; "++. hwnd = %x dwClientFlags = %x dwCrea"...
0x18002a57b  mov     rdx, rax
0x18002a57e  mov     [rbp+4C0h+var_418], r9
0x18002a585  mov     r9d, dword ptr [rbp+4C0h+hProfile]
0x18002a589  cmovz   r10, rsi
0x18002a58d  test    rax, rax
0x18002a590  mov     [rbp+4C0h+var_410], r10
0x18002a597  mov     rax, r12
0x18002a59a  mov     rcx, rax
0x18002a59d  cmovz   rdx, rsi
0x18002a5a1  mov     qword ptr [rsp+5D0h+var_580], rdx
0x18002a5a6  test    rax, rax
0x18002a5a9  mov     rax, r14
0x18002a5ac  lea     rdx, aAiplaunchproce; "AipLaunchProcessWithIdentityHelper"
0x18002a5b3  cmovz   rcx, rsi
0x18002a5b7  test    r14, r14
0x18002a5ba  mov     [rsp+5D0h+var_588], rcx
0x18002a5bf  mov     ecx, [rbp+4C0h+var_510]
0x18002a5c2  cmovz   rax, rsi
0x18002a5c6  mov     [rsp+5D0h+var_590], rax
0x18002a5cb  mov     eax, [rbp+4C0h+var_50C]
0x18002a5ce  mov     [rsp+5D0h+var_598], r10
0x18002a5d3  mov     [rsp+5D0h+dwOptions], eax
0x18002a5d7  mov     eax, [rbp+4C0h+var_4FC]
0x18002a5da  mov     [rsp+5D0h+bInheritHandle], ecx
0x18002a5de  lea     rcx, [rbp+4C0h+var_300]
0x18002a5e5  mov     [rsp+5D0h+dwDesiredAccess], eax
0x18002a5e9  call    ?WatchCurrentThread@LUATelemetry@@SA?AVActivityThreadWatcher@wil@@PEBD0ZZ; LUATelemetry::WatchCurrentThread(char const *,char const *,...)
0x18002a5ee  mov     rcx, cs:?g_pCentennialElevationTelemetryRateLimiter@@3V?$unique_ptr@VRateLimiter@@U?$default_delete@VRateLimiter@@@wistd@@@wistd@@A; this
0x18002a5f5  test    rcx, rcx
0x18002a5f8  jz      loc_18002A69C
0x18002a5fe  call    ?RequestPermission@RateLimiter@@QEAAHXZ; RateLimiter::RequestPermission(void)
0x18002a603  test    eax, eax
0x18002a605  jz      loc_18002A69C
0x18002a60b  test    rdi, rdi
0x18002a60e  jnz     short loc_18002A67E
0x18002a610  mov     ecx, 90h; Size
0x18002a615  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002a61a  xor     r14d, r14d
0x18002a61d  test    rax, rax
0x18002a620  jz      short loc_18002A62F
0x18002a622  mov     rcx, rax
0x18002a625  call    ??0TraceLoggingCorrelationVector@@QEAA@UTraceLoggingCorrelationVectorV2_t@@@Z; TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(TraceLoggingCorrelationVectorV2_t)
0x18002a62a  mov     rdi, rax
0x18002a62d  jmp     short loc_18002A632
0x18002a62f  mov     rdi, r14
0x18002a632  mov     rdx, r14
0x18002a635  lock xadd [rdi+88h], rdx; unsigned __int64
0x18002a63e  lea     r8, [rbp+4C0h+Destination]; char *
0x18002a645  mov     rcx, rdi; this
0x18002a648  call    ?ToStringImpl@TraceLoggingCorrelationVector@@AEAA_N_KPEAD@Z; TraceLoggingCorrelationVector::ToStringImpl(unsigned __int64,char *)
0x18002a64d  test    rdi, rdi
0x18002a650  jz      short loc_18002A65A
0x18002a652  mov     rcx, rdi; Block
0x18002a655  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002a65a  mov     eax, [rbp+4C0h+var_518]
0x18002a65d  mov     r10d, [rbp+4C0h+var_4A0]
0x18002a661  mov     r11d, [rbp+4C0h+var_4C8]
0x18002a665  mov     r13, [rbp+4C0h+var_478]
0x18002a669  mov     r14, [rbp+4C0h+lpFileName]
0x18002a66d  mov     r12, [rbp+4C0h+hMem]
0x18002a671  mov     [rbp+4C0h+var_508], eax
0x18002a674  mov     [rbp+4C0h+var_4FC], r10d
0x18002a678  mov     [rbp+4C0h+var_510], r11d
0x18002a67c  jmp     short loc_18002A6A4
0x18002a67e  mov     edx, 81h; SizeInBytes
0x18002a683  lea     rcx, [rbp+4C0h+Destination]; Destination
0x18002a68a  mov     r9d, edx; MaxCount
0x18002a68d  mov     r8, rdi; Source
0x18002a690  call    cs:__imp_strncpy_s
0x18002a697  nop     dword ptr [rax+rax+00h]
0x18002a69c  mov     r10d, [rbp+4C0h+var_4FC]
0x18002a6a0  mov     r11d, [rbp+4C0h+var_510]
0x18002a6a4  mov     rax, [rbp+4C0h+var_470]
0x18002a6a8  xorps   xmm0, xmm0
0x18002a6ab  xor     ecx, ecx
0x18002a6ad  movups  xmmword ptr [rax], xmm0
0x18002a6b0  mov     [rax+10h], rcx
0x18002a6b4  mov     r8, cs:WPP_GLOBAL_Control
0x18002a6bb  lea     rax, WPP_GLOBAL_Control
0x18002a6c2  xor     edi, edi
0x18002a6c4  cmp     r8, rax
0x18002a6c7  jz      loc_18002A753
0x18002a6cd  test    byte ptr [r8+1Ch], 1
0x18002a6d2  jz      short loc_18002A753
0x18002a6d4  mov     rax, [rbp+4C0h+var_438]
0x18002a6db  lea     r9, [rbp+4C0h+Destination]
0x18002a6e2  mov     [rsp+5D0h+var_568], r9
0x18002a6e7  test    rax, rax
0x18002a6ea  mov     r9, qword ptr [rbp+4C0h+var_458]
0x18002a6ee  mov     rdx, rsi
0x18002a6f1  mov     qword ptr [rsp+5D0h+var_570], r9
0x18002a6f6  cmovnz  rdx, rax
0x18002a6fa  mov     r9, [rbp+4C0h+var_418]
0x18002a701  test    r12, r12
0x18002a704  mov     [rsp+5D0h+lpValue], r9
0x18002a709  mov     rcx, rsi
0x18002a70c  mov     r9d, dword ptr [rbp+4C0h+hProfile]
0x18002a710  cmovnz  rcx, r12
0x18002a714  mov     qword ptr [rsp+5D0h+var_580], rdx
0x18002a719  test    r14, r14
0x18002a71c  mov     [rsp+5D0h+var_588], rcx
0x18002a721  mov     rax, rsi
0x18002a724  mov     rcx, [r8+10h]
0x18002a728  cmovnz  rax, r14
0x18002a72c  mov     [rsp+5D0h+var_590], rax
0x18002a731  mov     rax, [rbp+4C0h+var_410]
0x18002a738  mov     [rsp+5D0h+var_598], rax
0x18002a73d  mov     eax, [rbp+4C0h+var_50C]
0x18002a740  mov     [rsp+5D0h+dwOptions], eax
0x18002a744  mov     [rsp+5D0h+bInheritHandle], r11d
0x18002a749  mov     [rsp+5D0h+dwDesiredAccess], r10d
0x18002a74e  call    WPP_SF_DDDDSSSSSSs
0x18002a753  test    byte ptr [rbp+4C0h+arg_68], 1
0x18002a75a  jz      short loc_18002A76F
0x18002a75c  lea     rcx, AppInfo_PerfTrack_Elevation_PackagedApp_Start; struct _EVENT_DESCRIPTOR *
0x18002a763  call    ?AiLogPerfTrackEvent@@YAKPEBU_EVENT_DESCRIPTOR@@@Z; AiLogPerfTrackEvent(_EVENT_DESCRIPTOR const *)
0x18002a768  mov     [rbp+4C0h+var_4C0], eax
0x18002a76b  mov     [rbp+4C0h+var_530], 1
0x18002a76f  test    r14, r14
0x18002a772  jz      loc_18002AB17
0x18002a778  cmp     [rbp+4C0h+packageFamilyName], rbx
0x18002a77c  jz      loc_18002AB17
0x18002a782  cmp     [rbp+4C0h+var_538], rdi
0x18002a786  jz      loc_18002AB17
0x18002a78c  mov     rcx, r14; unsigned __int16 *
0x18002a78f  call    ?AipJustFileName@@YAPEBGPEBG@Z; AipJustFileName(ushort const *)
0x18002a794  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002a798  mov     rdi, rax
0x18002a79b  xor     ecx, ecx
0x18002a79d  inc     rdi
0x18002a7a0  cmp     [r14+rdi*2], cx
0x18002a7a5  jnz     short loc_18002A79D
0x18002a7a7  mov     qword ptr [rbp+4C0h+var_458], rdi
0x18002a7ab  test    r12, r12
0x18002a7ae  jz      short loc_18002A7C0
0x18002a7b0  inc     rax
0x18002a7b3  cmp     [r12+rax*2], cx
0x18002a7b8  jnz     short loc_18002A7B0
0x18002a7ba  mov     qword ptr [rbp+4C0h+var_468], rax
0x18002a7be  jmp     short loc_18002A7C4
0x18002a7c0  mov     rax, qword ptr [rbp+4C0h+var_468]
0x18002a7c4  mov     ecx, 7FFFh
0x18002a7c9  cmp     rdi, rcx
0x18002a7cc  ja      loc_18002AB17
0x18002a7d2  cmp     rax, rcx
0x18002a7d5  ja      loc_18002AB17
0x18002a7db  mov     ecx, [rbp+4C0h+arg_68]
0x18002a7e1  mov     eax, ecx
0x18002a7e3  and     eax, 120h
0x18002a7e8  cmp     eax, 100h
0x18002a7ed  jz      loc_18002AB17
0x18002a7f3  mov     eax, ecx
  ... truncated ...
```
