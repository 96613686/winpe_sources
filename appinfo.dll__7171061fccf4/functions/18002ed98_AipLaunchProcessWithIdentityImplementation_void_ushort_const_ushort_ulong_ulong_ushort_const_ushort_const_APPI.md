# AipLaunchProcessWithIdentityImplementation(void *,ushort const *,ushort *,ulong,ulong,ushort const *,ushort const *,_APPINFO_STARTUPINFO *,_STARTUPINFO_STDHANDLES *,ushort * *,unsigned __int64,ushort const *,ushort const *,unsigned __int64,ulong,ulong,ulong,void *,unsigned __int64,unsigned __int64 *,_GUID *,unsigned __int64,char const *,int *,UACPROMPT_POLICY *,_APPINFO_PROCESS_INFORMATION *)

- ea: `0x18002ed98`
- end: `0x180030a48`
- name: `?AipLaunchProcessWithIdentityImplementation@@YAKPEAXPEBGPEAGKK11PEAU_APPINFO_STARTUPINFO@@PEAU_STARTUPINFO_STDHANDLES@@PEAPEAG_K116KKK06PEA_KPEAU_GUID@@6PEBDPEAHPEAW4UACPROMPT_POLICY@@PEAU_APPINFO_PROCESS_INFORMATION@@@Z`
- size: `7344`
- prototype: `__int64 __fastcall(void *, unsigned __int16 *, unsigned __int16 *, unsigned int, unsigned int, unsigned __int16 *, WCHAR *, struct _APPINFO_STARTUPINFO *, struct _STARTUPINFO_STDHANDLES *, unsigned __int16 **, unsigned __int64, const unsigned __int16 *, wchar_t *, unsigned __int64, unsigned int, unsigned int, char, void *, unsigned __int64, unsigned __int64 *, struct _GUID *, unsigned __int64, char *Source, int *, enum UACPROMPT_POLICY *, void **)`
- caller_count: `2`
- callee_count: `63`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18002e8bc`
- `0x18002ebec`

## callees

- `0x180009ba8`
- `0x180009d10`
- `0x180009d50`
- `0x18000a938`
- `0x18000ba10`
- `0x18000c920`
- `0x18000d974`
- `0x18000f210`
- `0x180010430`
- `0x1800107f8`
- `0x180010878`
- `0x180010dd4`
- `0x180011414`
- `0x18001158c`
- `0x1800187f0`
- `0x180019fa0`
- `0x18001aee4`
- `0x18001b25c`
- `0x18001b408`
- `0x18001b7c0`
- `0x18001b9e4`
- `0x18001d034`
- `0x18001e7bc`
- `0x18001e7c8`
- `0x18001f8ec`
- `0x18001f940`
- `0x18002079c`
- `0x180020980`
- `0x180026630`
- `0x180027668`
- `0x180028eb8`
- `0x18002a1dc`
- `0x18002ad54`
- `0x18002b064`
- `0x18002b0c0`
- `0x18002ce70`
- `0x18002d8fc`
- `0x18002ed98`
- `0x180030b24`
- `0x180036898`
- `0x180037250`
- `0x180038b44`
- `0x180038ce4`
- `0x18003b3f0`
- `0x18003bb18`
- `0x18003bb44`
- `0x18003bbc4`
- `0x18003bd90`
- `0x18003c6ac`
- `0x18003e354`

## import_xrefs

- `msvcrt!strncpy_s` at `0x18002f170`
- `msvcrt!strncpy_s` at `0x18002f170`
- `RPCRT4!RpcImpersonateClient` at `0x18002f62b`
- `RPCRT4!RpcImpersonateClient` at `0x18002f7f3`
- `RPCRT4!RpcImpersonateClient` at `0x1800302a8`
- `RPCRT4!RpcImpersonateClient` at `0x18002f62b`
- `RPCRT4!RpcImpersonateClient` at `0x18002f7f3`
- `RPCRT4!RpcImpersonateClient` at `0x1800302a8`
- `RPCRT4!RpcRevertToSelf` at `0x18002f646`
- `RPCRT4!RpcRevertToSelf` at `0x18002f890`
- `RPCRT4!RpcRevertToSelf` at `0x180030358`
- `RPCRT4!RpcRevertToSelf` at `0x18002f646`
- `RPCRT4!RpcRevertToSelf` at `0x18002f890`
- `RPCRT4!RpcRevertToSelf` at `0x180030358`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f594`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f911`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f97f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030723`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030764`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f594`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f911`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f97f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030723`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030764`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x180030759`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x180030759`
- `api-ms-win-core-processthreads-l1-1-0!OpenThread` at `0x180030711`
- `api-ms-win-core-processthreads-l1-1-0!OpenThread` at `0x180030711`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002f557`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002f560`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002f557`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002f560`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x1800309b5`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x1800309b5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800308c3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180030975`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003098a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800309be`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800308c3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180030975`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003098a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800309be`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18002f586`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18002f586`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800308d5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800308e7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800308fd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003090e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800309f1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800308d5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800308e7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800308fd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003090e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800309f1`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800309a2`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800309a2`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002f96f`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002f96f`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x18002f029`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x18002f029`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18002f01c`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18002f5e4`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18002f01c`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18002f5e4`
- `api-ms-win-core-kernel32-private-l1-1-0!CheckElevationEnabled` at `0x18002f7b9`
- `api-ms-win-core-kernel32-private-l1-1-0!CheckElevationEnabled` at `0x18002f7b9`
- `api-ms-win-core-kernel32-private-l1-1-0!CheckElevation` at `0x18002fa0a`
- `api-ms-win-core-kernel32-private-l1-1-0!CheckElevation` at `0x18002fa0a`
- `api-ms-win-core-psm-key-l1-1-0!PsmCreateKey` at `0x18002ff15`
- `api-ms-win-core-psm-key-l1-1-0!PsmCreateKey` at `0x18002ff15`
- `ntdll!NtClose` at `0x180030391`
- `ntdll!NtClose` at `0x18003091d`
- `ntdll!NtClose` at `0x180030933`
- `ntdll!NtClose` at `0x180030942`
- `ntdll!NtClose` at `0x180030391`
- `ntdll!NtClose` at `0x18003091d`
- `ntdll!NtClose` at `0x180030933`
- `ntdll!NtClose` at `0x180030942`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18002f32e`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18002f373`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18002f32e`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18002f373`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18002f905`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800300f8`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18002f905`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800300f8`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18002f9de`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18002fae9`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180030127`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18003013a`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18002f9de`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18002fae9`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180030127`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18003013a`
- `USERENV!UnloadUserProfile` at `0x1800300e9`
- `USERENV!UnloadUserProfile` at `0x180030255`
- `USERENV!UnloadUserProfile` at `0x18003028a`
- `USERENV!UnloadUserProfile` at `0x1800300e9`
- `USERENV!UnloadUserProfile` at `0x180030255`
- `USERENV!UnloadUserProfile` at `0x18003028a`
- `ext-ms-win-desktopappx-l1-1-0!FreeDesktopAppXLaunchContext` at `0x180030951`
- `ext-ms-win-desktopappx-l1-1-0!FreeDesktopAppXLaunchContext` at `0x180030951`
- `ext-ms-win-desktopappx-l1-1-0!PrepareDesktopAppXActivation` at `0x1800301e3`
- `ext-ms-win-desktopappx-l1-1-0!PrepareDesktopAppXActivation` at `0x1800301e3`
- `ext-ms-win-desktopappx-l1-1-0!PostCreateProcessDesktopAppXActivation` at `0x1800306a1`
- `ext-ms-win-desktopappx-l1-1-0!PostCreateProcessDesktopAppXActivation` at `0x1800306a1`
- `ext-ms-win-desktopappx-l1-1-4!DoesPackageHaveElevationCapability` at `0x18002fbfd`
- `ext-ms-win-desktopappx-l1-1-4!DoesPackageHaveElevationCapability` at `0x18002fbfd`
- `ext-ms-win-desktopappx-l1-1-5!DoesPackageHaveUIAccessCapability` at `0x18002fb26`
- `ext-ms-win-desktopappx-l1-1-5!DoesPackageHaveUIAccessCapability` at `0x18002fb26`
- `ext-ms-win-desktopappx-l1-2-2!BeginCreatingHeliumContainerForDesktopAppXActivation` at `0x1800303ba`
- `ext-ms-win-desktopappx-l1-2-2!BeginCreatingHeliumContainerForDesktopAppXActivation` at `0x1800303ba`
- `ext-ms-win-desktopappx-l1-2-2!RundownHeliumContainerForDesktopAppXActivation` at `0x1800309fa`
- `ext-ms-win-desktopappx-l1-2-2!RundownHeliumContainerForDesktopAppXActivation` at `0x1800309fa`
- `ext-ms-win-desktopappx-l1-1-6!VerifyFileIsTrustedAndInPackage` at `0x18002fad1`
- `ext-ms-win-desktopappx-l1-1-6!VerifyFileIsTrustedAndInPackage` at `0x18002fad1`
- `ext-ms-win-appmodel-activation-l1-1-0!PostCreateProcessAppXActivation` at `0x180030653`
- `ext-ms-win-appmodel-activation-l1-1-0!PostCreateProcessAppXActivation` at `0x180030653`
- `ext-ms-win-appmodel-activation-l1-1-0!PrepareAppXActivation` at `0x180030024`
- `ext-ms-win-appmodel-activation-l1-1-0!PrepareAppXActivation` at `0x180030024`
- `ext-ms-win-appmodel-activation-l1-1-0!FreeAppXLaunchContext` at `0x180030960`
- `ext-ms-win-appmodel-activation-l1-1-0!FreeAppXLaunchContext` at `0x180030960`
- `ext-ms-win-appmodel-activation-l1-1-1!RegisterAppXPackageIfNecessary2` at `0x180030118`
- `ext-ms-win-appmodel-activation-l1-1-1!RegisterAppXPackageIfNecessary2` at `0x180030118`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x18002f4e9`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x18002f4e9`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrIsAllowedToActivateAsUser` at `0x18002f4bb`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrIsAllowedToActivateAsUser` at `0x18002f4bb`
- `ext-ms-win-core-app-package-volume-l1-1-0!MountVolumeForAppPackage` at `0x18002ff3a`
- `ext-ms-win-core-app-package-volume-l1-1-0!MountVolumeForAppPackage` at `0x18002ff3a`
- `ext-ms-win-core-app-package-volume-l1-1-0!UnmountVolumeForAppPackage` at `0x1800309dc`
- `ext-ms-win-core-app-package-volume-l1-1-0!UnmountVolumeForAppPackage` at `0x1800309dc`

## string_xrefs

- `0x18002f080`: `++. hwnd = %x dwClientFlags = %x dwCreationFlags = %x dwTimeout = %x\n	lpDesktop = %ws\n	lpApplicationName = %ws\n	lpCommandLine = %ws\n	lpCurrentDirectory = %ws\n	packageFamilyName = %ws\n	applicationId = %ws\n	szLocalCorrelationVector = %s\n`

## pseudocode

```c
__int64 __fastcall AipLaunchProcessWithIdentityImplementation(
        void *a1,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        unsigned int a4,
        unsigned int a5,
        unsigned __int16 *a6,
        WCHAR *a7,
        struct _APPINFO_STARTUPINFO *a8,
        struct _STARTUPINFO_STDHANDLES *a9,
        unsigned __int16 **a10,
        unsigned __int64 a11,
        const unsigned __int16 *a12,
        wchar_t *a13,
        unsigned __int64 a14,
        unsigned int a15,
        unsigned int a16,
        char a17,
        void *a18,
        unsigned __int64 a19,
        unsigned __int64 *a20,
        struct _GUID *a21,
        unsigned __int64 a22,
        char *Source,
        int *a24,
        enum UACPROMPT_POLICY *a25,
        void **a26)
{
  const char *v26; // rsi
  unsigned __int16 *v27; // r15
  unsigned __int16 *v28; // r13
  signed int AppModelIdentityActivationProperties; // r12d
  __int64 v30; // rdi
  unsigned __int16 *v31; // rbx
  const wchar_t *v32; // r14
  const wchar_t *v33; // r8
  PCWSTR v34; // r9
  wchar_t *v35; // r10
  unsigned __int16 *v36; // rdx
  const wchar_t *v37; // rcx
  const wchar_t *v38; // rax
  void *v39; // rax
  volatile signed __int64 *v40; // rsi
  void **v41; // rax
  unsigned __int64 v42; // rsi
  const wchar_t *v43; // r8
  const wchar_t *v44; // rdx
  const wchar_t *v45; // rax
  unsigned __int64 v46; // rax
  signed int ClientInformation; // esi
  NTSTATUS v48; // eax
  HANDLE v49; // rsi
  int v50; // eax
  NTSTATUS v51; // ecx
  DWORD LastError; // eax
  int v53; // r8d
  int v54; // ecx
  int IsAllowedToActivateAsUser; // eax
  unsigned int v56; // eax
  unsigned __int64 v57; // rcx
  HANDLE CurrentProcess; // rsi
  HANDLE v59; // rax
  unsigned __int64 v60; // rax
  unsigned __int16 *v61; // rbx
  unsigned __int8 v62; // cl
  unsigned int v63; // r14d
  int PackageFullNameFromFamilyName; // esi
  const unsigned __int16 *v65; // rsi
  int PackageProperties; // eax
  __int64 v67; // rdx
  int v68; // r8d
  _QWORD *v69; // rcx
  int v70; // edx
  __int64 v71; // rcx
  const wchar_t *v72; // rax
  const unsigned __int16 *v73; // rdx
  int DoesExecutableExistInPackage; // eax
  _QWORD *v75; // rcx
  int v76; // edx
  __int64 v77; // rcx
  const wchar_t *v78; // rax
  const WCHAR *v79; // rcx
  _QWORD *v80; // rcx
  int v81; // edx
  __int64 v82; // rcx
  const wchar_t *v83; // rax
  unsigned __int16 *v84; // rcx
  __int64 v85; // rdx
  __int64 v86; // rcx
  const unsigned __int16 *v87; // rcx
  __int64 v88; // rcx
  unsigned int v89; // eax
  const unsigned __int16 *v90; // rcx
  HLOCAL v91; // rsi
  int IsTrustedAndInPackage; // eax
  __int64 v93; // rdx
  __int64 v94; // rcx
  int HaveUIAccessCapability; // eax
  unsigned int v96; // r8d
  _QWORD *v97; // rcx
  int v98; // edx
  __int64 v99; // rcx
  const wchar_t *v100; // rax
  unsigned int v101; // esi
  const unsigned __int16 *v102; // rcx
  unsigned int v103; // eax
  HLOCAL v104; // rcx
  __int64 v105; // rdx
  wchar_t *v106; // rcx
  void *v107; // rsi
  unsigned __int16 **v108; // rdx
  int v109; // eax
  unsigned int v110; // eax
  int v111; // eax
  int v112; // eax
  int v113; // r8d
  const wchar_t *v114; // rax
  HANDLE v115; // rdx
  int v116; // eax
  int v117; // ecx
  int v118; // ecx
  int v119; // eax
  int v120; // eax
  int v121; // eax
  int v122; // r8d
  const wchar_t *v123; // rax
  __int64 v124; // rcx
  HANDLE v125; // rcx
  __int64 v126; // rcx
  bool v127; // cf
  signed int v128; // eax
  int v129; // edx
  _QWORD *v130; // rcx
  int v131; // edx
  __int64 v132; // rcx
  const wchar_t *v133; // rax
  void **v134; // rsi
  DWORD v135; // r8d
  HANDLE v136; // rax
  __int64 v137; // rcx
  unsigned int v138; // r14d
  const unsigned __int16 *v139; // rax
  PCWSTR v140; // r8
  void **v141; // r14
  const unsigned __int16 *v142; // rax
  DWORD v143; // r8d
  HANDLE v144; // rax
  void *v145; // rbx
  _BYTE v147[8]; // [rsp+B0h] [rbp-80h] BYREF
  HLOCAL v148; // [rsp+B8h] [rbp-78h] BYREF
  unsigned __int8 v149; // [rsp+C0h] [rbp-70h]
  bool v150; // [rsp+C1h] [rbp-6Fh] BYREF
  bool v151; // [rsp+C2h] [rbp-6Eh] BYREF
  bool v152; // [rsp+C3h] [rbp-6Dh] BYREF
  bool v153; // [rsp+C4h] [rbp-6Ch] BYREF
  bool v154; // [rsp+C5h] [rbp-6Bh] BYREF
  bool v155; // [rsp+C6h] [rbp-6Ah] BYREF
  bool v156; // [rsp+C7h] [rbp-69h] BYREF
  bool v157; // [rsp+C8h] [rbp-68h] BYREF
  bool v158; // [rsp+C9h] [rbp-67h] BYREF
  bool v159; // [rsp+CAh] [rbp-66h] BYREF
  bool v160; // [rsp+CBh] [rbp-65h] BYREF
  int v161; // [rsp+CCh] [rbp-64h] BYREF
  HANDLE TargetHandle; // [rsp+D0h] [rbp-60h] BYREF
  unsigned int v163; // [rsp+D8h] [rbp-58h] BYREF
  bool v164; // [rsp+DCh] [rbp-54h] BYREF
  char v165; // [rsp+DDh] [rbp-53h]
  int v166; // [rsp+E0h] [rbp-50h] BYREF
  unsigned int v167; // [rsp+E4h] [rbp-4Ch]
  wchar_t *v168; // [rsp+E8h] [rbp-48h]
  HANDLE hProfile; // [rsp+F0h] [rbp-40h] BYREF
  unsigned int v170; // [rsp+F8h] [rbp-38h] BYREF
  unsigned int v171; // [rsp+FCh] [rbp-34h] BYREF
  int v172; // [rsp+100h] [rbp-30h]
  unsigned int v173; // [rsp+104h] [rbp-2Ch] BYREF
  PCWSTR packageFamilyName; // [rsp+108h] [rbp-28h]
  unsigned int v175; // [rsp+110h] [rbp-20h]
  unsigned int v176[2]; // [rsp+118h] [rbp-18h]
  unsigned int v177; // [rsp+120h] [rbp-10h]
  unsigned int v178; // [rsp+124h] [rbp-Ch]
  unsigned __int16 *v179; // [rsp+128h] [rbp-8h] BYREF
  int v180; // [rsp+130h] [rbp+0h] BYREF
  int v181; // [rsp+134h] [rbp+4h] BYREF
  int v182; // [rsp+138h] [rbp+8h] BYREF
  void **v183; // [rsp+140h] [rbp+10h]
  __int64 v184; // [rsp+148h] [rbp+18h] BYREF
  HANDLE hSourceHandle; // [rsp+150h] [rbp+20h] BYREF
  unsigned int v186; // [rsp+158h] [rbp+28h] BYREF
  unsigned int v187; // [rsp+15Ch] [rbp+2Ch]
  int v188; // [rsp+160h] [rbp+30h] BYREF
  HANDLE hObject; // [rsp+168h] [rbp+38h]
  HLOCAL hMem; // [rsp+170h] [rbp+40h] BYREF
  __int64 v191; // [rsp+178h] [rbp+48h] BYREF
  unsigned int v192[2]; // [rsp+180h] [rbp+50h]
  int v193; // [rsp+188h] [rbp+58h] BYREF
  WCHAR *v194; // [rsp+190h] [rbp+60h]
  HANDLE Handle; // [rsp+198h] [rbp+68h] BYREF
  unsigned __int16 *v196; // [rsp+1A0h] [rbp+70h] BYREF
  void *Block; // [rsp+1A8h] [rbp+78h] BYREF
  unsigned __int16 *v198; // [rsp+1B0h] [rbp+80h] BYREF
  HLOCAL v199; // [rsp+1B8h] [rbp+88h] BYREF
  int v200; // [rsp+1C0h] [rbp+90h] BYREF
  unsigned int *v201; // [rsp+1C8h] [rbp+98h] BYREF
  unsigned int v202; // [rsp+1D0h] [rbp+A0h] BYREF
  unsigned int v203; // [rsp+1D8h] [rbp+A8h] BYREF
  int v204; // [rsp+1E0h] [rbp+B0h] BYREF
  void *v205; // [rsp+1E8h] [rbp+B8h] BYREF
  unsigned __int64 v206; // [rsp+1F0h] [rbp+C0h]
  __int64 v207; // [rsp+1F8h] [rbp+C8h]
  struct _STARTUPINFO_STDHANDLES *v208; // [rsp+200h] [rbp+D0h]
  struct _APPINFO_STARTUPINFO *v209; // [rsp+208h] [rbp+D8h]
  unsigned __int16 *v210; // [rsp+210h] [rbp+E0h]
  unsigned __int16 *v211; // [rsp+218h] [rbp+E8h]
  unsigned __int16 *v212; // [rsp+220h] [rbp+F0h]
  HANDLE hToken; // [rsp+228h] [rbp+F8h] BYREF
  __int64 v214; // [rsp+230h] [rbp+100h]
  void *v215; // [rsp+238h] [rbp+108h] BYREF
  struct _GUID *v216; // [rsp+240h] [rbp+110h]
  unsigned __int64 *v217; // [rsp+248h] [rbp+118h]
  void *v218; // [rsp+250h] [rbp+120h] BYREF
  LARGE_INTEGER v219; // [rsp+258h] [rbp+128h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+260h] [rbp+130h] BYREF
  LARGE_INTEGER Frequency; // [rsp+268h] [rbp+138h] BYREF
  HANDLE v222; // [rsp+270h] [rbp+140h]
  __int128 v223; // [rsp+278h] [rbp+148h] BYREF
  void *v224; // [rsp+288h] [rbp+158h]
  __int128 v225; // [rsp+290h] [rbp+160h] BYREF
  __int128 v226; // [rsp+2A0h] [rbp+170h]
  __int64 v227; // [rsp+2B0h] [rbp+180h]
  __int128 v228; // [rsp+2B8h] [rbp+188h] BYREF
  __int128 v229; // [rsp+2C8h] [rbp+198h]
  __int64 v230; // [rsp+2D8h] [rbp+1A8h]
  __int128 v231; // [rsp+2E0h] [rbp+1B0h] BYREF
  __int64 v232; // [rsp+2F0h] [rbp+1C0h]
  char v233[80]; // [rsp+300h] [rbp+1D0h] BYREF
  char Destination[144]; // [rsp+350h] [rbp+220h] BYREF
  _BYTE v235[464]; // [rsp+3E0h] [rbp+2B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+608h] [rbp+4D8h]

  v26 = Source;
  v194 = a7;
  v27 = a2;
  packageFamilyName = a12;
  v28 = a3;
  AppModelIdentityActivationProperties = 0;
  v168 = a13;
  v30 = 0;
  v167 = a5;
  v202 = a5;
  v209 = a8;
  v208 = a9;
  v206 = a14;
  v187 = a15;
  v207 = (__int64)a18;
  v217 = a20;
  v216 = a21;
  v214 = (__int64)a24;
  v201 = (unsigned int *)a25;
  v183 = a26;
  v205 = a1;
  v171 = 0;
  v163 = 0;
  v224 = 0;
  v227 = 0;
  v230 = 0;
  v175 = a4;
  v211 = a3;
  v210 = a2;
  v212 = a6;
  v198 = a2;
  v179 = a3;
  v203 = a4;
  hMem = a6;
  v173 = 0;
  v200 = 0;
  v170 = 0;
  v148 = 0;
  v218 = 0;
  Handle = 0;
  hSourceHandle = 0;
  v215 = 0;
  TargetHandle = 0;
  v222 = 0;
  hToken = 0;
  v188 = 0;
  v186 = 0;
  v178 = 0;
  v193 = 0;
  v180 = 6;
  v199 = 0;
  v223 = 0;
  v184 = 0;
  v225 = 0;
  v191 = 0;
  v226 = 0;
  v172 = 0;
  v228 = 0;
  hObject = (HANDLE)-1LL;
  v229 = 0;
  v166 = 0;
  v181 = 0;
  v177 = 0;
  v161 = 0;
  v149 = 0;
  v159 = 0;
  v151 = 0;
  v158 = 0;
  v157 = 0;
  v156 = 0;
  v150 = 0;
  v153 = 0;
  memset_0(v235, 0, sizeof(v235));
  v204 = 464;
  Block = 0;
  v165 = 0;
  memset_0(Destination, 0, 0x81u);
  Frequency.QuadPart = 0;
  PerformanceCount.QuadPart = 0;
  v31 = 0;
  v232 = 0;
  v219.QuadPart = 0;
  v231 = 0;
  v196 = 0;
  QueryPerformanceCounter(&PerformanceCount);
  QueryPerformanceFrequency(&Frequency);
  v32 = L"NULL";
  v33 = a13;
  if ( !a13 )
    v33 = L"NULL";
  v34 = packageFamilyName;
  if ( !packageFamilyName )
    v34 = L"NULL";
  v35 = v194;
  *(_QWORD *)v192 = v33;
  v36 = v212;
  *(_QWORD *)v176 = v34;
  if ( !v194 )
    v35 = L"NULL";
  hProfile = v35;
  v37 = v28;
  if ( !v212 )
    v36 = L"NULL";
  v38 = v27;
  if ( !v28 )
    v37 = L"NULL";
  if ( !v27 )
    v38 = L"NULL";
  LUATelemetry::WatchCurrentThread(
    v233,
    "AipLaunchProcessWithIdentityImplementation",
    "++. hwnd = %x dwClientFlags = %x dwCreationFlags = %x dwTimeout = %x\n"
    "\tlpDesktop = %ws\n"
    "\tlpApplicationName = %ws\n"
    "\tlpCommandLine = %ws\n"
    "\tlpCurrentDirectory = %ws\n"
    "\tpackageFamilyName = %ws\n"
    "\tapplicationId = %ws\n"
    "\tszLocalCorrelationVector = %s\n",
    (unsigned int)v206,
    v175,
    v167,
    v187,
    v35,
    v38,
    v37,
    v36,
    v34,
    v33,
    Destination);
  if ( g_pCentennialElevationTelemetryRateLimiter
    && (unsigned int)RateLimiter::RequestPermission(g_pCentennialElevationTelemetryRateLimiter) )
  {
    if ( v26 )
    {
      strncpy_s(Destination, 0x81u, v26, 0x81u);
    }
    else
    {
      v39 = operator new(0x90u);
      if ( v39 )
        v40 = (volatile signed __int64 *)TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(v39);
      else
        v40 = 0;
      TraceLoggingCorrelationVector::ToStringImpl(
        (TraceLoggingCorrelationVector *)v40,
        _InterlockedExchangeAdd64(v40 + 17, 0),
        Destination);
      if ( v40 )
        operator delete((void *)v40);
    }
  }
  v41 = v183;
  *(_OWORD *)v183 = 0;
  v41[2] = 0;
  v42 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v43 = L"NULL";
    if ( hMem )
      v43 = (const wchar_t *)hMem;
    v44 = L"NULL";
    if ( v28 )
      v44 = v28;
    v45 = L"NULL";
    if ( v27 )
      v45 = v27;
    WPP_SF_DDDDSSSSSSs(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      (_DWORD)v44,
      (_DWORD)v43,
      v206,
      v175,
      v167,
      v187,
      (__int64)hProfile,
      (__int64)v45,
      (__int64)v44,
      (__int64)v43,
      *(__int64 *)v176,
      *(__int64 *)v192,
      (__int64)Destination);
  }
  if ( (a16 & 1) != 0 )
  {
    v178 = AiLogPerfTrackEvent(&AppInfo_PerfTrack_Elevation_PackagedApp_Start);
    v149 = 1;
  }
  if ( !v27 || !packageFamilyName || !v168 )
    goto LABEL_95;
  *(_QWORD *)v176 = 0;
  AipJustFileName(v27);
  v46 = -1;
  do
    ++v46;
  while ( v27[v46] );
  *(_QWORD *)v192 = v46;
  if ( v28 )
  {
    v42 = -1;
    do
      ++v42;
    while ( v28[v42] );
    *(_QWORD *)v176 = v42;
  }
  if ( v46 > 0x7FFF || v42 > 0x7FFF || (a16 & 0x120) == 0x100 || (a16 & 0x810) == 0x800 )
    goto LABEL_95;
  ClientInformation = AiGetClientInformation(v205, &Handle, &hSourceHandle, &v173, &v186);
  if ( ClientInformation )
  {
LABEL_96:
    v61 = (unsigned __int16 *)v148;
    goto LABEL_97;
  }
  if ( v201 )
  {
    v177 = *v201;
    goto LABEL_52;
  }
  v182 = 0;
  v48 = LUAGetUACPromptPolicy(&v182, &v161);
  if ( v48 < 0 )
  {
    ClientInformation = RtlNtStatusToDosErrorNoTeb(v48);
    v177 = v161;
    goto LABEL_96;
  }
  v177 = v161;
LABEL_52:
  v49 = hSourceHandle;
  if ( v214 )
  {
    v181 = *(_DWORD *)v214;
  }
  else
  {
    v161 = 0;
    v50 = AiCheckForElevatedUser(hSourceHandle, &v161);
    if ( v50 < 0 )
      goto LABEL_55;
    v50 = AiCheckForAdminUser(v49, v161, &v181);
    if ( v50 < 0 )
      goto LABEL_55;
  }
  v152 = 0;
  v160 = 0;
  v155 = 0;
  v154 = 0;
  v164 = 0;
  AppModelIdentityActivationProperties = GetAppModelIdentityActivationProperties(
                                           v49,
                                           v168,
                                           0,
                                           a16,
                                           (enum AppModel::RuntimeBehavior *)&v166,
                                           &v152,
                                           &v160,
                                           &v155,
                                           &v154,
                                           &v164);
  if ( AppModelIdentityActivationProperties < 0 )
  {
    ClientInformation = WIN32_FROM_HRESULT(AppModelIdentityActivationProperties);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_DSS(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        45,
        v53,
        AppModelIdentityActivationProperties,
        (__int64)v27,
        (__int64)L"NULL");
    goto LABEL_96;
  }
  if ( v164 )
    a16 |= 0x2000u;
  if ( v149 && v152 )
    goto LABEL_67;
  if ( v166 == 1 )
  {
    AppModelIdentityActivationProperties = ReplaceDSMAIfPresent(v49);
    if ( AppModelIdentityActivationProperties < 0 )
      goto LABEL_70;
  }
  if ( a19 )
  {
    if ( !(unsigned __int8)IsUMgrIsAllowedToActivateAsUserPresent() )
      goto LABEL_77;
    v147[0] = 0;
    IsAllowedToActivateAsUser = UMgrIsAllowedToActivateAsUser(v49, a19, v147);
    AppModelIdentityActivationProperties = IsAllowedToActivateAsUser;
    if ( IsAllowedToActivateAsUser < 0 )
    {
LABEL_75:
      v54 = IsAllowedToActivateAsUser;
      goto LABEL_71;
    }
    if ( !v147[0] )
    {
LABEL_77:
      ClientInformation = 5;
      goto LABEL_96;
    }
    IsAllowedToActivateAsUser = UMgrQueryUserToken(a19, &TargetHandle);
    AppModelIdentityActivationProperties = IsAllowedToActivateAsUser;
    if ( IsAllowedToActivateAsUser < 0 )
      goto LABEL_75;
  }
  else
  {
    CurrentProcess = GetCurrentProcess();
    v59 = GetCurrentProcess();
    if ( !DuplicateHandle(v59, hSourceHandle, CurrentProcess, &TargetHandle, 0, 0, 2u) )
    {
      LastError = GetLastError();
      goto LABEL_57;
    }
  }
  if ( (v175 & 8) != 0 )
  {
    v56 = AiConvertWow64Paths(v27, (const unsigned __int16 **)&v198, v28, &v179, v212, (const unsigned __int16 **)&hMem);
    v27 = v198;
    ClientInformation = v56;
    if ( v56 )
    {
      v28 = v179;
      goto LABEL_96;
    }
    if ( v198 )
    {
      v57 = -1;
      do
        ++v57;
      while ( v198[v57] );
      *(_QWORD *)v192 = v57;
    }
    else
    {
      v57 = *(_QWORD *)v192;
    }
    v28 = v179;
    if ( v179 )
    {
      v60 = -1;
      do
        ++v60;
      while ( v179[v60] );
      *(_QWORD *)v176 = v60;
    }
    else
    {
      v60 = *(_QWORD *)v176;
    }
    if ( v57 > 0x7FFF || v60 > 0x7FFF )
    {
LABEL_95:
      ClientInformation = 87;
      goto LABEL_96;
    }
  }
  ClientInformation = RpcImpersonateClient(0);
  if ( ClientInformation )
    goto LABEL_96;
  PackageFullNameFromFamilyName = GetPackageFullNameFromFamilyName(packageFamilyName, (unsigned __int16 **)&v148);
  RpcRevertToSelf();
  if ( PackageFullNameFromFamilyName < 0 )
  {
    v51 = PackageFullNameFromFamilyName;
    goto LABEL_56;
  }
  v65 = (const unsigned __int16 *)v148;
  PackageProperties = GetPackageProperties(
                        (const unsigned __int16 *)v148,
                        &v159,
                        &v151,
                        &v158,
                        &v157,
                        &v156,
                        &v150,
                        &v153,
                        0);
  AppModelIdentityActivationProperties = PackageProperties;
  if ( PackageProperties < 0 )
  {
    ClientInformation = WIN32_FROM_HRESULT(PackageProperties);
    v69 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_96;
    v70 = 46;
    goto LABEL_107;
  }
  LOBYTE(v67) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID52930508>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_ID52930508>::GetImpl'::`2'::impl,
    v67);
  if ( v150 && !v151 )
  {
    v161 = 0;
    v50 = AiCheckForTcbPrivilege(hSourceHandle, &v161);
    if ( v50 < 0 )
      goto LABEL_55;
    if ( !v161 )
    {
      v150 = 0;
      v73 = v28;
      if ( v27 )
        v73 = v27;
      DoesExecutableExistInPackage = AiDoesExecutableExistInPackage(v65, v73, &v150);
      AppModelIdentityActivationProperties = DoesExecutableExistInPackage;
      if ( DoesExecutableExistInPackage < 0 )
      {
        ClientInformation = WIN32_FROM_HRESULT(DoesExecutableExistInPackage);
        v69 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_96;
        v70 = 47;
        goto LABEL_107;
      }
      if ( !v150 )
        goto LABEL_77;
    }
  }
  if ( v166 )
  {
    v172 = 2;
    if ( v149 )
    {
      ClientInformation = CheckElevationEnabled(&v193);
      if ( ClientInformation )
        goto LABEL_96;
      if ( !v193 )
      {
        v149 = 0;
LABEL_230:
        v65 = (const unsigned __int16 *)v148;
        goto LABEL_231;
      }
      v149 = 1;
      v150 = 1;
      v50 = LUAGetUserType(TargetHandle, &v188);
      if ( v50 >= 0 )
      {
        ClientInformation = RpcImpersonateClient(0);
        if ( ClientInformation )
          goto LABEL_96;
        ClientInformation = AdjustActivationToken(
                              TargetHandle,
                              v166,
                              v152,
                              0,
                              v159,
                              v158,
                              v157,
                              v156,
                              v155,
                              v154,
                              v153,
                              0,
                              (wchar_t *)v148,
                              v168,
                              (__int64)v217,
                              (__int64)v216,
                              0,
                              &hToken);
        RpcRevertToSelf();
        if ( ClientInformation )
        {
          v75 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            goto LABEL_96;
          v76 = 48;
LABEL_134:
          v77 = v75[2];
          v78 = L"NULL";
          if ( v28 )
            v78 = v28;
          if ( v27 )
            v32 = v27;
          WPP_SF_DSSSS(
            v77,
            v76,
            (_DWORD)packageFamilyName,
            ClientInformation,
            (__int64)v32,
            (__int64)v78,
            (__int64)packageFamilyName,
            (__int64)v168);
          goto LABEL_96;
        }
        if ( !ImpersonateLoggedOnUser(hToken) )
        {
          ClientInformation = GetLastError();
          v75 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            goto LABEL_96;
          v76 = 49;
          goto LABEL_134;
        }
        v79 = v28;
        if ( v27 )
          v79 = v27;
        hObject = CreateFileW(v79, 0xA0000000, 5u, 0, 3u, 0x80u, 0);
        if ( hObject == (HANDLE)-1LL )
        {
          ClientInformation = GetLastError();
          v80 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v81 = 50;
LABEL_149:
            v82 = v80[2];
            v83 = L"NULL";
            if ( v28 )
              v83 = v28;
            if ( v27 )
              v32 = v27;
            WPP_SF_DSSSS(
              v82,
              v81,
              (_DWORD)packageFamilyName,
              ClientInformation,
              (__int64)v32,
              (__int64)v83,
              (__int64)packageFamilyName,
              (__int64)v168);
            goto LABEL_154;
          }
          goto LABEL_154;
        }
        v84 = v28;
        if ( v27 )
          v84 = v27;
        ClientInformation = CheckElevation(v84, &v200, 0, &v170);
        if ( ClientInformation )
        {
          v80 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v81 = 51;
            goto LABEL_149;
          }
LABEL_154:
          RevertToSelf();
          goto LABEL_96;
        }
        if ( v170 - 16 <= 2 && (unsigned int)LUAIsShadowAdminEnabled(v86) )
        {
          v87 = v28;
          if ( v27 )
            v87 = v27;
          AipCheckAssistiveTechnologyList(v87, &v163);
        }
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShadowAdmin>::__private_IsEnabled(
                                `wil::Feature<__WilFeatureTraits_Feature_ShadowAdmin>::GetImpl'::`2'::impl,
                                v85)
          && (unsigned int)LUAIsShadowAdminEnabled(v88) )
        {
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
            &v196,
            0);
          v89 = AiCheckSecureApplicationDirectoryEx(hObject, &v163, &v196);
          v31 = v196;
        }
        else
        {
          v90 = v28;
          if ( v27 )
            v90 = v27;
          v89 = AiCheckSecureApplicationDirectory(v90, &v163);
        }
        ClientInformation = v89;
        LODWORD(v205) = v89;
        if ( v89 )
          goto LABEL_154;
        v91 = v148;
        v182 = 0;
        IsTrustedAndInPackage = VerifyFileIsTrustedAndInPackage(v27, v148, &v182);
        if ( IsTrustedAndInPackage < 0 )
        {
          ClientInformation = WIN32_FROM_HRESULT(IsTrustedAndInPackage);
          goto LABEL_154;
        }
        RevertToSelf();
        v94 = v170;
        if ( v170 - 16 > 2 )
        {
          v101 = v163;
        }
        else
        {
          v172 = 3;
          v161 = 0;
          LOBYTE(v93) = 1;
          wil::details::FeatureImpl<__WilFeatureTraits_Feature_CentennialUIAccess>::ReportUsage(
            `wil::Feature<__WilFeatureTraits_Feature_CentennialUIAccess>::GetImpl'::`2'::impl,
            v93);
          if ( !(unsigned __int8)IsDoesPackageHaveUIAccessCapabilityPresent() )
            goto LABEL_179;
          HaveUIAccessCapability = DoesPackageHaveUIAccessCapability(v91, &v161);
          if ( HaveUIAccessCapability < 0 )
          {
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x25C8,
              v96,
              (const char *)(unsigned int)HaveUIAccessCapability,
              (int)&v180);
            goto LABEL_179;
          }
          if ( !v161 )
          {
LABEL_179:
            ClientInformation = 50;
            v97 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
              goto LABEL_96;
            v98 = 52;
LABEL_182:
            v99 = v97[2];
            v100 = L"NULL";
            if ( v28 )
              v100 = v28;
            if ( v27 )
              LODWORD(v32) = (_DWORD)v27;
            WPP_SF_SSSS(
              v99,
              v98,
              (_DWORD)packageFamilyName,
              (_DWORD)v32,
              (__int64)v100,
              (__int64)packageFamilyName,
              (__int64)v168);
            goto LABEL_96;
          }
          v94 = v170;
          if ( v170 >= 3 )
          {
            v94 = v170 - 16;
            v170 -= 16;
          }
          v101 = v163 | 0x8000C;
          v163 |= 0x8000Cu;
        }
        LODWORD(v179) = v175 & 1;
        if ( (v175 & 1) == 0 )
        {
          if ( !(_DWORD)v94 )
          {
LABEL_199:
            if ( (v101 & 4) != 0 )
            {
LABEL_202:
              if ( (_DWORD)v179 )
              {
                if ( (unsigned int)v94 <= 1 )
                {
                  v101 |= 0x200u;
                  v163 = v101;
                }
                v170 = 2;
                v180 = 6;
              }
              if ( (v175 & 0x10) != 0 )
                v163 = v101 | 0x800;
              if ( v151 || !v182 )
              {
                v106 = v28;
                if ( v27 )
                  v106 = v27;
                v103 = AiBuildEXEParams(
                         v106,
                         hObject,
                         v27,
                         v192[0],
                         v28,
                         v176[0],
                         0,
                         v186,
                         (struct _CONSENTUI_PARAM_HEADER **)&v199);
              }
              else
              {
                v102 = v28;
                if ( v27 )
                  v102 = v27;
                v180 = 8;
                v103 = AiBuildPackagedAppParams(
                         v102,
                         v192[0],
                         v28,
                         v176[0],
                         v186,
                         (wchar_t *)packageFamilyName,
                         v168,
                         (struct _CONSENTUI_PARAM_HEADER **)&v199);
              }
              ClientInformation = v103;
              if ( v103 )
                goto LABEL_96;
              v104 = v199;
              *((_DWORD *)v199 + 13) = v178;
              ClientInformation = AiCheckLUA(
                                    v170,
                                    &v163,
                                    (unsigned int)v180,
                                    TargetHandle,
                                    v104,
                                    v194,
                                    v206,
                                    v173,
                                    v187,
                                    Destination,
                                    &v215);
              if ( ClientInformation )
              {
                v75 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
                  || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
                {
                  goto LABEL_96;
                }
                v76 = 54;
                goto LABEL_134;
              }
              v107 = v215;
              if ( v215 )
              {
                if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShadowAdmin>::__private_IsEnabled(
                                        `wil::Feature<__WilFeatureTraits_Feature_ShadowAdmin>::GetImpl'::`2'::impl,
                                        v105) )
                  v167 &= 0xFFFFFFFC;
                TargetHandle = v107;
                v171 = v163 | 1;
              }
              else
              {
                v171 = v163;
              }
              goto LABEL_230;
            }
LABEL_200:
            if ( !(unsigned int)AiIsElevationAllowedForSession(v173) )
            {
LABEL_67:
              ClientInformation = 50;
              goto LABEL_96;
            }
            LODWORD(v94) = v170;
            goto LABEL_202;
          }
          v161 = 0;
          if ( !(unsigned __int8)IsDoesPackageHaveElevationCapabilityPresent(v94)
            || (int)DoesPackageHaveElevationCapability(v148, &v161) < 0
            || !v161 )
          {
            ClientInformation = 50;
            v97 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
              goto LABEL_96;
            v98 = 53;
            goto LABEL_182;
          }
          LODWORD(v201) = v177;
          v188 = 0;
          LODWORD(hProfile) = 0;
          v171 = -1;
          LUATelemetry::CentennialElevation<long,unsigned short * &,unsigned short const * &,unsigned long &,unsigned long &,unsigned long &,unsigned long &,bool &,int &,unsigned long,int,int,char (&)[129]>(
            (unsigned int)&hProfile,
            (unsigned int)&v148,
            (unsigned int)&v198,
            (unsigned int)&v205,
            (__int64)&v203,
            (__int64)&v202,
            (__int64)&a16,
            (__int64)&v150,
            (__int64)&v181,
            (__int64)&v201,
            (__int64)&v171,
            (__int64)&v188,
            Destination);
          LODWORD(v94) = v170;
        }
        if ( (_DWORD)v94 )
          goto LABEL_200;
        goto LABEL_199;
      }
LABEL_55:
      v51 = v50;
LABEL_56:
      LastError = RtlNtStatusToDosErrorNoTeb(v51);
LABEL_57:
      ClientInformation = LastError;
      goto LABEL_96;
    }
  }
LABEL_231:
  if ( (unsigned __int8)IsMountVolumeForAppPackagePresent() )
  {
    AppModelIdentityActivationProperties = wil::get_token_information_nothrow<_TOKEN_USER,0>(&Block, TargetHandle);
    if ( AppModelIdentityActivationProperties < 0 )
    {
LABEL_70:
      v54 = AppModelIdentityActivationProperties;
LABEL_71:
      LastError = WIN32_FROM_HRESULT(v54);
      goto LABEL_57;
    }
    hProfile = 0;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &hProfile,
      0);
    v109 = ParseAppUserModelId(v168, v108, (unsigned __int16 **)&hProfile);
    AppModelIdentityActivationProperties = v109;
    if ( v109 < 0 )
    {
      v110 = WIN32_FROM_HRESULT(v109);
LABEL_235:
      ClientInformation = v110;
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&hProfile);
      goto LABEL_96;
    }
    v111 = PsmCreateKey(v65, hProfile, v235, &v204);
    if ( v111 < 0 )
    {
      v110 = WIN32_FROM_NTSTATUS(v111);
      goto LABEL_235;
    }
    v112 = MountVolumeForAppPackage(v235, *(_QWORD *)Block, v173);
    LODWORD(v179) = v112;
    if ( v112 < 0 )
    {
      ClientInformation = WIN32_FROM_NTSTATUS(v112);
      v61 = (unsigned __int16 *)v148;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v114 = L"NULL";
        if ( v148 )
          v114 = (const wchar_t *)v148;
        if ( v27 )
          v32 = v27;
        WPP_SF_DSS(*((_QWORD *)WPP_GLOBAL_Control + 2), 55, v113, (_DWORD)v179, (__int64)v32, (__int64)v114);
      }
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&hProfile);
      goto LABEL_97;
    }
    v165 = 1;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&hProfile);
  }
  *(_QWORD *)v176 = 0;
  v147[0] = ShouldAdjustActivationToken();
  if ( v151 || (v178 = 0, (a16 & 6) != 0) )
    v178 = 1;
  v172 = 1;
  if ( !v166 )
  {
    *(_QWORD *)&v228 = TargetHandle;
    *((_QWORD *)&v228 + 1) = hSourceHandle;
    HIDWORD(v230) = v160;
    *(_QWORD *)&v229 = v65;
    *((_QWORD *)&v229 + 1) = v27;
    v116 = PrepareAppXActivation(&v228, &v191);
    AppModelIdentityActivationProperties = v116;
    if ( v116 < 0 )
    {
      ClientInformation = WIN32_FROM_HRESULT(v116);
      v69 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_96;
      v70 = 56;
LABEL_107:
      v61 = (unsigned __int16 *)v148;
LABEL_108:
      v71 = v69[2];
      v72 = L"NULL";
      if ( v61 )
        v72 = v61;
      if ( v27 )
        v32 = v27;
      WPP_SF_DSS(v71, v70, v68, AppModelIdentityActivationProperties, (__int64)v32, (__int64)v72);
      goto LABEL_97;
    }
    if ( *(_DWORD *)(v191 + 8) )
      *(_QWORD *)v176 = *(_QWORD *)(v191 + 24);
LABEL_296:
    if ( v147[0] )
    {
      v172 = 4;
      ClientInformation = RpcImpersonateClient(0);
      if ( ClientInformation )
        goto LABEL_96;
      if ( v184 )
        v124 = *(_QWORD *)(v184 + 56);
      else
        v124 = 0;
      ClientInformation = AdjustActivationToken(
                            TargetHandle,
                            v166,
                            v152,
                            v160,
                            v159,
                            v158,
                            v157,
                            v156,
                            v155,
                            v154,
                            v153,
                            0,
                            (wchar_t *)v148,
                            v168,
                            (__int64)v217,
                            (__int64)v216,
                            v124,
                            &v218);
      RpcRevertToSelf();
      if ( ClientInformation )
      {
        v75 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_96;
        v76 = 58;
        goto LABEL_134;
      }
      NtClose(TargetHandle);
      v125 = v218;
      v65 = (const unsigned __int16 *)v148;
      TargetHandle = v218;
    }
    else
    {
      v125 = TargetHandle;
    }
    if ( (unsigned int)(v166 - 1) <= 2 )
      v30 = BeginCreatingHeliumContainerForDesktopAppXActivation(v125, v184);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShadowAdmin>::__private_IsEnabled(
                            `wil::Feature<__WilFeatureTraits_Feature_ShadowAdmin>::GetImpl'::`2'::impl,
                            v115)
      && (unsigned int)LUAIsShadowAdminEnabled(v126) )
    {
      v127 = v147[0] != 0;
      v147[0] = -v147[0];
      v128 = AiLaunchProcess(
               Handle,
               TargetHandle,
               hObject,
               v171,
               v27,
               v28,
               v167 | 4,
               (const WCHAR *)hMem,
               v194,
               (__int64)v209,
               (__int64)v208,
               (unsigned __int64)&v231 & -(__int64)((a17 & 1) != 0),
               v173,
               (void *)((unsigned __int64)v65 & -(__int64)v127),
               a16,
               a17,
               v207,
               a22,
               *(unsigned __int16 **)v176,
               v183,
               v31);
      v61 = (unsigned __int16 *)v148;
    }
    else
    {
      v127 = v147[0] != 0;
      v147[0] = -v147[0];
      v61 = (unsigned __int16 *)v148;
      v128 = AiLaunchProcess(
               Handle,
               TargetHandle,
               hObject,
               v171,
               v27,
               v28,
               v167 | 4,
               (const WCHAR *)hMem,
               v194,
               (__int64)v209,
               (__int64)v208,
               (unsigned __int64)&v231 & -(__int64)((a17 & 1) != 0),
               v173,
               (void *)((unsigned __int64)v148 & -(__int64)v127),
               a16,
               a17,
               v207,
               a22,
               *(unsigned __int16 **)v176,
               v183,
               0);
    }
    v129 = 0;
    ClientInformation = v128;
    if ( v128 )
    {
      v172 = 5;
      v130 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_97;
      v131 = 59;
      goto LABEL_317;
    }
    v172 = 6;
    if ( v166 )
    {
      if ( (unsigned int)(v166 - 1) <= 1 || v166 == 3 )
      {
        v134 = v183;
        *(_DWORD *)(v184 + 40) = v167;
        v224 = v134[2];
        AppModelIdentityActivationProperties = PostCreateProcessDesktopAppXActivation(TargetHandle, v184, &v223);
        v129 = *(_DWORD *)(v184 + 16);
      }
      else
      {
        v134 = v183;
      }
    }
    else
    {
      v134 = v183;
      *(_DWORD *)(v191 + 32) = v167;
      v224 = v134[2];
      AppModelIdentityActivationProperties = PostCreateProcessAppXActivation(TargetHandle, v191, &v223);
      v129 = *(_DWORD *)(v191 + 8);
    }
    if ( AppModelIdentityActivationProperties < 0 )
    {
      ClientInformation = WIN32_FROM_HRESULT(AppModelIdentityActivationProperties);
      v69 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_97;
      v70 = 60;
      goto LABEL_108;
    }
    if ( (v167 & 4) == 0 && !v129 )
    {
      v135 = *((_DWORD *)v134 + 5);
      v172 = 7;
      v136 = OpenThread(2u, 0, v135);
      v222 = v136;
      if ( !v136 )
      {
        ClientInformation = GetLastError();
        v130 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_97;
        v131 = 61;
        goto LABEL_317;
      }
      if ( ResumeThread(v136) == -1 )
      {
        ClientInformation = GetLastError();
        v130 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_97;
        v131 = 62;
LABEL_317:
        v132 = v130[2];
        v133 = L"NULL";
        if ( v28 )
          v133 = v28;
        if ( v27 )
          v32 = v27;
        WPP_SF_DSSSS(
          v132,
          v131,
          (_DWORD)packageFamilyName,
          ClientInformation,
          (__int64)v32,
          (__int64)v133,
          (__int64)packageFamilyName,
          (__int64)v168);
        goto LABEL_97;
      }
    }
    ClientInformation = 0;
    goto LABEL_97;
  }
  if ( (unsigned int)(v166 - 1) > 2 )
    goto LABEL_296;
  hProfile = 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShadowAdmin>::__private_IsEnabled(
                          `wil::Feature<__WilFeatureTraits_Feature_ShadowAdmin>::GetImpl'::`2'::impl,
                          v115) )
  {
    if ( (v171 & 0x21) != 1 && ((v171 & 0x8000000) == 0 || !(unsigned int)LUAIsShadowAdminEnabled(v171)) )
      goto LABEL_271;
  }
  else if ( (v171 & 0x21) != 1 )
  {
    goto LABEL_271;
  }
  ClientInformation = AipLoadUserProfile(TargetHandle, &hProfile);
  if ( ClientInformation )
    goto LABEL_264;
  ImpersonateLoggedOnUser(TargetHandle);
  LODWORD(v179) = 0;
  if ( (int)RegisterAppXPackageIfNecessary2(0, v168, 0, 0) < 0 )
  {
    ClientInformation = 15669;
    RevertToSelf();
LABEL_264:
    if ( hProfile )
      UnloadUserProfile(TargetHandle, hProfile);
    goto LABEL_96;
  }
  RevertToSelf();
  v65 = (const unsigned __int16 *)v148;
LABEL_271:
  *(_QWORD *)&v225 = TargetHandle;
  v117 = 0;
  *((_QWORD *)&v225 + 1) = hSourceHandle;
  *(_QWORD *)&v226 = v65;
  *((_QWORD *)&v226 + 1) = v27;
  if ( v166 == 2 )
    v117 = 8;
  v118 = v227 | v178 | (2 * v147[0]) | v117;
  v119 = 0;
  if ( v166 == 3 )
    v119 = 64;
  LODWORD(v227) = v118 | v119;
  if ( (a17 & 2) == 0
    && (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_CentennialInUIJob>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_CentennialInUIJob>::GetImpl'::`2'::impl) )
  {
    v120 = HIDWORD(v227);
    if ( (v227 & 2) != 0 )
      v120 = 728;
    HIDWORD(v227) = v120;
  }
  v121 = PrepareDesktopAppXActivation(&v225, &v184);
  AppModelIdentityActivationProperties = v121;
  if ( v121 >= 0 )
  {
    if ( v149 )
      *(_DWORD *)(v184 + 16) = 0;
    if ( *(_DWORD *)(v184 + 16) )
      *(_QWORD *)v176 = *(_QWORD *)(v184 + 32);
    v115 = hProfile;
    if ( hProfile )
    {
      UnloadUserProfile(TargetHandle, hProfile);
      hProfile = 0;
    }
    goto LABEL_296;
  }
  ClientInformation = WIN32_FROM_HRESULT(v121);
  v61 = (unsigned __int16 *)v148;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v123 = L"NULL";
    if ( v148 )
      v123 = (const wchar_t *)v148;
    if ( v27 )
      v32 = v27;
    WPP_SF_DSS(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      57,
      v122,
      AppModelIdentityActivationProperties,
      (__int64)v32,
      (__int64)v123);
  }
  if ( !hProfile )
    goto LABEL_96;
  UnloadUserProfile(TargetHandle, hProfile);
LABEL_97:
  QueryPerformanceCounter(&v219);
  v214 = 1000 * (v219.QuadPart - PerformanceCount.QuadPart) / Frequency.QuadPart;
  if ( ClientInformation == 1223 )
  {
    v63 = 0;
  }
  else if ( ClientInformation > 0 )
  {
    v63 = (unsigned __int16)ClientInformation | 0x80070000;
  }
  else
  {
    v63 = ClientInformation;
  }
  if ( LUATelemetry::IsEnabled(v62, 1000 * (v219.QuadPart - PerformanceCount.QuadPart) % Frequency.QuadPart) )
  {
    wil::details::static_lazy<LUATelemetry>::get(
      v137,
      _lambda_8fd1dd6eff698f29c42c633fb94303b5_::_lambda_invoker_cdecl_);
    LUATelemetry::CentennialElevation_(
      (LUATelemetry *)v149,
      v63,
      v61,
      v27,
      ClientInformation,
      v175,
      v167,
      a16,
      v149,
      v181,
      v177,
      v214,
      1,
      Destination);
  }
  if ( ClientInformation )
  {
    v138 = v172;
    if ( v172 != 1 && v172 != 6 )
    {
      if ( ClientInformation > 0 )
        AppModelIdentityActivationProperties = (unsigned __int16)ClientInformation | 0x80070000;
      else
        AppModelIdentityActivationProperties = ClientInformation;
    }
    v139 = AipJustFileName(v27);
    v140 = packageFamilyName;
    if ( v61 )
      v140 = v61;
    AipLogDesktopAppXProcessStartFailure(
      v138,
      (unsigned int)AppModelIdentityActivationProperties,
      v140,
      v139,
      v168,
      L"[LaunchProcess]");
    v141 = v183;
  }
  else
  {
    v142 = AipJustFileName(v27);
    v141 = v183;
    AipLogDesktopAppXProcessStartSuccess(*((_DWORD *)v183 + 4), v61, v142, v168, L"[LaunchProcess]");
  }
  if ( hObject != (HANDLE)-1LL )
    CloseHandle(hObject);
  if ( v27 != v210 )
    LocalFree(v27);
  if ( v28 != v211 )
    LocalFree(v28);
  if ( hMem != v212 )
    LocalFree(hMem);
  if ( v61 )
    LocalFree(v61);
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
  if ( v222 )
    CloseHandle(v222);
  if ( hToken )
    CloseHandle(hToken);
  if ( ClientInformation )
  {
    v143 = *((_DWORD *)v141 + 4);
    if ( v143 )
    {
      v144 = OpenProcess(1u, 0, v143);
      v145 = v144;
      if ( v144 )
      {
        TerminateProcess(v144, ClientInformation);
        CloseHandle(v145);
      }
    }
    if ( v165 )
      UnmountVolumeForAppPackage(v235, *(_QWORD *)Block, v173);
  }
  if ( v199 )
    LocalFree(v199);
  RundownHeliumContainerForDesktopAppXActivation(v30);
  wil::ActivityThreadWatcher::~ActivityThreadWatcher((wil::ActivityThreadWatcher *)v233);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v196);
  if ( Block )
    operator delete(Block);
  return (unsigned int)ClientInformation;
}

```

## disassembly

```asm
0x18002ed98  push    rbp
0x18002ed9a  push    rbx
0x18002ed9b  push    rsi
0x18002ed9c  push    rdi
0x18002ed9d  push    r12
0x18002ed9f  push    r13
0x18002eda1  push    r14
0x18002eda3  push    r15
0x18002eda5  lea     rbp, [rsp-498h]
0x18002edad  sub     rsp, 5C8h
0x18002edb4  mov     rax, cs:__security_cookie
0x18002edbb  xor     rax, rsp
0x18002edbe  mov     [rbp+4D0h+var_50], rax
0x18002edc5  mov     rax, [rbp+4D0h+arg_30]
0x18002edcc  xor     r14d, r14d
0x18002edcf  mov     rsi, [rbp+4D0h+Source]
0x18002edd6  xorps   xmm0, xmm0
0x18002edd9  mov     [rbp+4D0h+var_470], rax
0x18002eddd  xorps   xmm1, xmm1
0x18002ede0  mov     rax, [rbp+4D0h+arg_58]
0x18002ede7  mov     r15, rdx
0x18002edea  mov     [rbp+4D0h+packageFamilyName], rax
0x18002edee  mov     r13, r8
0x18002edf1  mov     rax, [rbp+4D0h+arg_60]
0x18002edf8  mov     r12d, r14d
0x18002edfb  mov     [rbp+4D0h+var_518], rax
0x18002edff  mov     edi, r14d
0x18002ee02  mov     eax, [rbp+4D0h+arg_20]
0x18002ee08  mov     [rbp+4D0h+var_51C], eax
0x18002ee0b  mov     [rbp+4D0h+var_430], eax
0x18002ee11  mov     rax, [rbp+4D0h+arg_38]
0x18002ee18  mov     [rbp+4D0h+var_3F8], rax
0x18002ee1f  mov     rax, [rbp+4D0h+arg_40]
0x18002ee26  mov     [rbp+4D0h+var_400], rax
0x18002ee2d  mov     rax, [rbp+4D0h+arg_68]
0x18002ee34  mov     [rbp+4D0h+var_410], rax
0x18002ee3b  mov     eax, [rbp+4D0h+arg_70]
0x18002ee41  mov     [rbp+4D0h+var_4A4], eax
0x18002ee44  mov     rax, [rbp+4D0h+arg_88]
0x18002ee4b  mov     [rbp+4D0h+var_408], rax
0x18002ee52  mov     rax, [rbp+4D0h+arg_98]
0x18002ee59  mov     [rbp+4D0h+var_3B8], rax
0x18002ee60  mov     rax, [rbp+4D0h+arg_A0]
0x18002ee67  mov     [rbp+4D0h+var_3C0], rax
0x18002ee6e  mov     rax, [rbp+4D0h+arg_B8]
0x18002ee75  mov     [rbp+4D0h+var_3D0], rax
0x18002ee7c  mov     rax, [rbp+4D0h+arg_C0]
0x18002ee83  mov     [rbp+4D0h+var_438], rax
0x18002ee8a  mov     rax, [rbp+4D0h+arg_C8]
0x18002ee91  mov     [rbp+4D0h+var_4C0], rax
0x18002ee95  mov     eax, r14d
0x18002ee98  mov     [rbp+4D0h+var_418], rcx
0x18002ee9f  mov     rcx, [rbp+4D0h+arg_28]
0x18002eea6  mov     [rbp+4D0h+var_504], eax
0x18002eea9  mov     [rbp+4D0h+var_528], eax
0x18002eeac  mov     [rbp+4D0h+var_378], rax
0x18002eeb3  mov     [rbp+4D0h+var_350], rax
0x18002eeba  mov     [rbp+4D0h+var_328], rax
0x18002eec1  mov     [rbp+4D0h+var_4F0], r9d
0x18002eec5  mov     [rbp+4D0h+var_3E8], r8
0x18002eecc  mov     [rbp+4D0h+var_3F0], rdx
0x18002eed3  mov     [rbp+4D0h+var_3E0], rcx
0x18002eeda  mov     [rbp+4D0h+var_450], rdx
0x18002eee1  mov     [rbp+4D0h+var_4D8], r8
0x18002eee5  mov     [rbp+4D0h+var_428], r9d
0x18002eeec  mov     [rbp+4D0h+hMem], rcx
0x18002eef0  mov     [rbp+4D0h+var_4FC], r14d
0x18002eef4  mov     [rbp+4D0h+var_440], r14d
0x18002eefb  mov     [rbp+4D0h+var_508], r14d
0x18002eeff  mov     [rbp+4D0h+var_548], r14
0x18002ef03  mov     [rbp+4D0h+var_3B0], r14
0x18002ef0a  mov     [rbp+4D0h+Handle], r14
0x18002ef0e  mov     [rbp+4D0h+hSourceHandle], r14
0x18002ef12  mov     [rbp+4D0h+var_3C8], r14
0x18002ef19  mov     [rbp+4D0h+TargetHandle], r14
0x18002ef1d  mov     [rbp+4D0h+var_390], r14
0x18002ef24  mov     [rbp+4D0h+hToken], r14
0x18002ef2b  mov     [rbp+4D0h+var_4A0], r14d
0x18002ef2f  mov     [rbp+4D0h+var_4A8], r14d
0x18002ef33  mov     [rbp+4D0h+var_4DC], r14d
0x18002ef37  mov     [rbp+4D0h+var_478], r14d
0x18002ef3b  mov     [rbp+4D0h+var_4D0], 6
0x18002ef42  mov     [rbp+4D0h+var_448], r14
0x18002ef49  movups  [rbp+4D0h+var_388], xmm0
0x18002ef50  mov     [rbp+4D0h+var_4B8], r14
0x18002ef54  movups  [rbp+4D0h+var_370], xmm1
0x18002ef5b  mov     [rbp+4D0h+var_488], r14
0x18002ef5f  movups  [rbp+4D0h+var_360], xmm1
0x18002ef66  mov     [rbp+4D0h+var_500], r14d
0x18002ef6a  movups  [rbp+4D0h+var_348], xmm0
0x18002ef71  mov     [rbp+4D0h+hObject], 0FFFFFFFFFFFFFFFFh
0x18002ef79  movups  [rbp+4D0h+var_338], xmm0
0x18002ef80  mov     [rbp+4D0h+var_520], r14d
0x18002ef84  mov     [rbp+4D0h+var_4CC], r14d
0x18002ef88  mov     ebx, 1D0h
0x18002ef8d  mov     [rbp+4D0h+var_4E0], eax
0x18002ef90  mov     r8d, ebx; Size
0x18002ef93  mov     [rbp+4D0h+var_534], eax
0x18002ef96  xor     edx, edx; Val
0x18002ef98  mov     [rbp+4D0h+var_540], r14b
0x18002ef9c  lea     rcx, [rbp+4D0h+var_220]; void *
0x18002efa3  mov     [rbp+4D0h+var_536], r14b
0x18002efa7  mov     [rbp+4D0h+var_53E], r14b
0x18002efab  mov     [rbp+4D0h+var_537], r14b
0x18002efaf  mov     [rbp+4D0h+var_538], r14b
0x18002efb3  mov     [rbp+4D0h+var_539], r14b
0x18002efb7  mov     [rbp+4D0h+var_53F], r14b
0x18002efbb  mov     [rbp+4D0h+var_53C], r14b
0x18002efbf  call    memset_0
0x18002efc4  xor     edx, edx; Val
0x18002efc6  mov     [rbp+4D0h+var_420], ebx
0x18002efcc  mov     r8d, 81h; Size
0x18002efd2  mov     [rbp+4D0h+Block], r14
0x18002efd6  lea     rcx, [rbp+4D0h+Destination]; void *
0x18002efdd  mov     [rbp+4D0h+var_523], r14b
0x18002efe1  call    memset_0
0x18002efe6  xorps   xmm0, xmm0
0x18002efe9  mov     qword ptr [rbp+4D0h+Frequency], r14
0x18002eff0  xor     eax, eax
0x18002eff2  mov     qword ptr [rbp+4D0h+PerformanceCount], r14
0x18002eff9  mov     ebx, r14d
0x18002effc  mov     [rbp+4D0h+var_310], rax
0x18002f003  lea     rcx, [rbp+4D0h+PerformanceCount]; lpPerformanceCount
0x18002f00a  mov     qword ptr [rbp+4D0h+var_3A8], r14
0x18002f011  movups  [rbp+4D0h+var_320], xmm0
0x18002f018  mov     [rbp+4D0h+var_460], rbx
0x18002f01c  call    cs:__imp_QueryPerformanceCounter
0x18002f022  lea     rcx, [rbp+4D0h+Frequency]; lpFrequency
0x18002f029  call    cs:__imp_QueryPerformanceFrequency
0x18002f02f  mov     rax, [rbp+4D0h+var_518]
0x18002f033  lea     r14, aNull_0; "NULL"
0x18002f03a  test    rax, rax
0x18002f03d  mov     r8, rax
0x18002f040  mov     rax, [rbp+4D0h+packageFamilyName]
0x18002f044  mov     r11, r15
0x18002f047  cmovz   r8, r14
0x18002f04b  lea     r11, [rbp+4D0h+Destination]
0x18002f052  test    rax, rax
0x18002f055  mov     [rsp+600h+var_598], r11
0x18002f05a  mov     qword ptr [rsp+600h+var_5A0], r8
0x18002f05f  mov     r9, rax
0x18002f062  mov     rax, [rbp+4D0h+var_470]
0x18002f066  cmovz   r9, r14
0x18002f06a  test    rax, rax
0x18002f06d  mov     [rsp+600h+var_5A8], r9
0x18002f072  mov     r10, rax
0x18002f075  mov     qword ptr [rbp+4D0h+var_480], r8
0x18002f079  mov     rax, [rbp+4D0h+var_3E0]
0x18002f080  lea     r8, aHwndXDwclientf_0; "++. hwnd = %x dwClientFlags = %x dwCrea"...
0x18002f087  mov     rdx, rax
0x18002f08a  mov     qword ptr [rbp+4D0h+var_4E8], r9
0x18002f08e  mov     r9d, dword ptr [rbp+4D0h+var_410]
0x18002f095  cmovz   r10, r14
0x18002f099  test    rax, rax
0x18002f09c  mov     [rbp+4D0h+hProfile], r10
0x18002f0a0  mov     rax, r13
0x18002f0a3  mov     rcx, rax
0x18002f0a6  cmovz   rdx, r14
0x18002f0aa  mov     qword ptr [rsp+600h+var_5B0], rdx
0x18002f0af  test    rax, rax
0x18002f0b2  mov     rax, r15
0x18002f0b5  lea     rdx, aAiplaunchproce; "AipLaunchProcessWithIdentityImplementat"...
0x18002f0bc  cmovz   rcx, r14
0x18002f0c0  test    r15, r15
0x18002f0c3  mov     [rsp+600h+var_5B8], rcx
0x18002f0c8  mov     ecx, [rbp+4D0h+var_51C]
0x18002f0cb  cmovz   rax, r14
0x18002f0cf  mov     [rsp+600h+var_5C0], rax
0x18002f0d4  mov     eax, [rbp+4D0h+var_4A4]
0x18002f0d7  mov     [rsp+600h+var_5C8], r10
0x18002f0dc  mov     [rsp+600h+dwOptions], eax
0x18002f0e0  mov     eax, [rbp+4D0h+var_4F0]
0x18002f0e3  mov     [rsp+600h+bInheritHandle], ecx
0x18002f0e7  lea     rcx, [rbp+4D0h+var_300]
0x18002f0ee  mov     [rsp+600h+dwDesiredAccess], eax
0x18002f0f2  call    ?WatchCurrentThread@LUATelemetry@@SA?AVActivityThreadWatcher@wil@@PEBD0ZZ; LUATelemetry::WatchCurrentThread(char const *,char const *,...)
0x18002f0f7  mov     rcx, cs:?g_pCentennialElevationTelemetryRateLimiter@@3V?$unique_ptr@VRateLimiter@@U?$default_delete@VRateLimiter@@@wistd@@@wistd@@A; this
0x18002f0fe  test    rcx, rcx
0x18002f101  jz      short loc_18002F176
0x18002f103  call    ?RequestPermission@RateLimiter@@QEAAHXZ; RateLimiter::RequestPermission(void)
0x18002f108  test    eax, eax
0x18002f10a  jz      short loc_18002F176
0x18002f10c  test    rsi, rsi
0x18002f10f  jnz     short loc_18002F15E
0x18002f111  mov     ecx, 90h; Size
0x18002f116  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002f11b  xor     ecx, ecx
0x18002f11d  test    rax, rax
0x18002f120  jz      short loc_18002F131
0x18002f122  mov     rcx, rax
0x18002f125  call    ??0TraceLoggingCorrelationVector@@QEAA@UTraceLoggingCorrelationVectorV2_t@@@Z; TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(TraceLoggingCorrelationVectorV2_t)
0x18002f12a  mov     rsi, rax
0x18002f12d  xor     ecx, ecx
0x18002f12f  jmp     short loc_18002F134
0x18002f131  mov     rsi, rcx
0x18002f134  mov     rdx, rcx
0x18002f137  lock xadd [rsi+88h], rdx; unsigned __int64
0x18002f140  lea     r8, [rbp+4D0h+Destination]; char *
0x18002f147  mov     rcx, rsi; this
0x18002f14a  call    ?ToStringImpl@TraceLoggingCorrelationVector@@AEAA_N_KPEAD@Z; TraceLoggingCorrelationVector::ToStringImpl(unsigned __int64,char *)
0x18002f14f  test    rsi, rsi
0x18002f152  jz      short loc_18002F176
0x18002f154  mov     rcx, rsi; Block
0x18002f157  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002f15c  jmp     short loc_18002F176
0x18002f15e  mov     edx, 81h; SizeInBytes
0x18002f163  lea     rcx, [rbp+4D0h+Destination]; Destination
0x18002f16a  mov     r9d, edx; MaxCount
0x18002f16d  mov     r8, rsi; Source
0x18002f170  call    cs:__imp_strncpy_s
0x18002f176  mov     rax, [rbp+4D0h+var_4C0]
0x18002f17a  xorps   xmm0, xmm0
0x18002f17d  xor     ecx, ecx
0x18002f17f  movups  xmmword ptr [rax], xmm0
0x18002f182  mov     [rax+10h], rcx
0x18002f186  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f18d  lea     rax, WPP_GLOBAL_Control
0x18002f194  xor     esi, esi
0x18002f196  cmp     rcx, rax
0x18002f199  jz      loc_18002F222
0x18002f19f  test    byte ptr [rcx+1Ch], 1
0x18002f1a3  jz      short loc_18002F222
0x18002f1a5  mov     rax, [rbp+4D0h+hMem]
0x18002f1a9  lea     r9, [rbp+4D0h+Destination]
0x18002f1b0  mov     rcx, [rcx+10h]
0x18002f1b4  test    rax, rax
0x18002f1b7  mov     [rsp+600h+var_598], r9
0x18002f1bc  mov     r8, r14
0x18002f1bf  mov     r9, qword ptr [rbp+4D0h+var_480]
0x18002f1c3  cmovnz  r8, rax
0x18002f1c7  mov     qword ptr [rsp+600h+var_5A0], r9
0x18002f1cc  test    r13, r13
0x18002f1cf  mov     r9, qword ptr [rbp+4D0h+var_4E8]
0x18002f1d3  mov     rdx, r14
0x18002f1d6  mov     [rsp+600h+var_5A8], r9
0x18002f1db  cmovnz  rdx, r13
0x18002f1df  mov     r9d, dword ptr [rbp+4D0h+var_410]
0x18002f1e6  test    r15, r15
0x18002f1e9  mov     qword ptr [rsp+600h+var_5B0], r8
0x18002f1ee  mov     rax, r14
0x18002f1f1  cmovnz  rax, r15
0x18002f1f5  mov     [rsp+600h+var_5B8], rdx
0x18002f1fa  mov     [rsp+600h+var_5C0], rax
0x18002f1ff  mov     rax, [rbp+4D0h+hProfile]
0x18002f203  mov     [rsp+600h+var_5C8], rax
0x18002f208  mov     eax, [rbp+4D0h+var_4A4]
0x18002f20b  mov     [rsp+600h+dwOptions], eax
0x18002f20f  mov     eax, [rbp+4D0h+var_51C]
0x18002f212  mov     [rsp+600h+bInheritHandle], eax
0x18002f216  mov     eax, [rbp+4D0h+var_4F0]
0x18002f219  mov     [rsp+600h+dwDesiredAccess], eax
0x18002f21d  call    WPP_SF_DDDDSSSSSSs
0x18002f222  test    byte ptr [rbp+4D0h+arg_78], 1
0x18002f229  jz      short loc_18002F23E
0x18002f22b  lea     rcx, AppInfo_PerfTrack_Elevation_PackagedApp_Start; struct _EVENT_DESCRIPTOR *
0x18002f232  call    ?AiLogPerfTrackEvent@@YAKPEBU_EVENT_DESCRIPTOR@@@Z; AiLogPerfTrackEvent(_EVENT_DESCRIPTOR const *)
0x18002f237  mov     [rbp+4D0h+var_4DC], eax
0x18002f23a  mov     [rbp+4D0h+var_540], 1
0x18002f23e  test    r15, r15
0x18002f241  jz      loc_18002F5D4
0x18002f247  cmp     [rbp+4D0h+packageFamilyName], rbx
0x18002f24b  jz      loc_18002F5D4
0x18002f251  cmp     [rbp+4D0h+var_518], rsi
0x18002f255  jz      loc_18002F5D4
0x18002f25b  mov     rcx, r15; unsigned __int16 *
0x18002f25e  mov     qword ptr [rbp+4D0h+var_4E8], rsi
0x18002f262  call    ?AipJustFileName@@YAPEBGPEBG@Z; AipJustFileName(ushort const *)
0x18002f267  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18002f26b  mov     rax, rdx
0x18002f26e  xor     ecx, ecx
0x18002f270  inc     rax
0x18002f273  cmp     [r15+rax*2], cx
0x18002f278  jnz     short loc_18002F270
0x18002f27a  mov     qword ptr [rbp+4D0h+var_480], rax
0x18002f27e  test    r13, r13
0x18002f281  jz      short loc_18002F295
0x18002f283  mov     rsi, rdx
0x18002f286  inc     rsi
0x18002f289  cmp     [r13+rsi*2+0], cx
0x18002f28f  jnz     short loc_18002F286
0x18002f291  mov     qword ptr [rbp+4D0h+var_4E8], rsi
0x18002f295  mov     ecx, 7FFFh
0x18002f29a  cmp     rax, rcx
0x18002f29d  ja      loc_18002F5D4
0x18002f2a3  cmp     rsi, rcx
0x18002f2a6  ja      loc_18002F5D4
0x18002f2ac  mov     ecx, [rbp+4D0h+arg_78]
0x18002f2b2  mov     eax, ecx
0x18002f2b4  and     eax, 120h
0x18002f2b9  cmp     eax, 100h
0x18002f2be  jz      loc_18002F5D4
0x18002f2c4  mov     eax, ecx
0x18002f2c6  and     eax, 810h
0x18002f2cb  cmp     eax, 800h
0x18002f2d0  jz      loc_18002F5D4
0x18002f2d6  mov     rcx, [rbp+4D0h+var_418]; void *
0x18002f2dd  lea     rax, [rbp+4D0h+var_4A8]
0x18002f2e1  lea     r9, [rbp+4D0h+var_4FC]; unsigned int *
0x18002f2e5  mov     qword ptr [rsp+600h+dwDesiredAccess], rax; unsigned int *
0x18002f2ea  lea     r8, [rbp+4D0h+hSourceHandle]; void **
  ... truncated ...
```
