# Execution::ActivationManagerShim::ActivateApplicationForContractCore(HSTRING__ *,HSTRING__ *,unsigned __int64,ACTIVATEOPTIONSINTERNAL,IInspectable *,_ActivateComponentInfo const *,ActivateByExtensionArgs *,IInspectable *,ActivateType,void *,unsigned __int64 *,ulong *,IInspectable * *)

- ea: `0x180029270`
- end: `0x18002a2b9`
- name: `?ActivateApplicationForContractCore@ActivationManagerShim@Execution@@IEAAJPEAUHSTRING__@@0_KW4ACTIVATEOPTIONSINTERNAL@@PEAUIInspectable@@PEBU_ActivateComponentInfo@@PEAUActivateByExtensionArgs@@3W4ActivateType@@PEAXPEA_KPEAKPEAPEAU5@@Z`
- size: `4169`
- prototype: `int __high(HSTRING, HSTRING, unsigned __int64, enum ACTIVATEOPTIONSINTERNAL, struct IInspectable *, const struct _ActivateComponentInfo *, struct ActivateByExtensionArgs *, struct IInspectable *, enum ActivateType, void *, unsigned __int64 *, unsigned int *, struct IInspectable **)`
- caller_count: `9`
- callee_count: `42`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180028c20`
- `0x180029060`
- `0x180029110`
- `0x1800291c0`
- `0x18003fda0`
- `0x18006aea8`
- `0x18006c7b0`
- `0x18006ca20`
- `0x18006ce40`

## callees

- `0x18000b5c0`
- `0x18000cbc0`
- `0x18000e9f8`
- `0x18000ea34`
- `0x18000eac0`
- `0x18000f288`
- `0x180011328`
- `0x180014040`
- `0x180023620`
- `0x180023af0`
- `0x180024840`
- `0x180024b70`
- `0x180029270`
- `0x18002a380`
- `0x18002c4b0`
- `0x18002c930`
- `0x180031540`
- `0x180035e10`
- `0x1800381f4`
- `0x18003b4c0`
- `0x18003db64`
- `0x18003f38c`
- `0x180044408`
- `0x1800445ac`
- `0x1800475b0`
- `0x18004be80`
- `0x18004caf8`
- `0x1800501dc`
- `0x180059df8`
- `0x18005ae90`
- `0x18005b31c`
- `0x18005b33c`
- `0x18005b37c`
- `0x18005b3c4`
- `0x180067e64`
- `0x180069fbc`
- `0x18006b040`
- `0x18006f2f4`
- `0x1800708f4`
- `0x180073aa0`
- `0x1800803f4`
- `0x1800a0010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180029861`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002a04b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002a0b4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180029861`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002a04b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002a0b4`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800297ba`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002a081`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800297ba`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002a081`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002954c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002954c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180029441`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180029653`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002a1b5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180029441`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180029653`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002a1b5`
- `ntdll!RtlIsMultiSessionSku` at `0x1800298c3`
- `ntdll!RtlIsMultiSessionSku` at `0x1800298c3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180029453`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002947b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180029496`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800294b1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002a1c7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002a1ff`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002a21a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002a235`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180029453`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002947b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180029496`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800294b1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002a1c7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002a1ff`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002a21a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002a235`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002945e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002a1d2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002945e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002a1d2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002931b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002932b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002931b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002932b`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180029df8`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180029df8`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800297f7`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800297f7`
- `api-ms-win-core-com-private-l1-1-0!CoSetErrorInfo` at `0x18002a004`
- `api-ms-win-core-com-private-l1-1-0!CoSetErrorInfo` at `0x18002a004`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002953e`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800295a8`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002953e`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800295a8`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x180029628`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x180029628`
- `api-ms-win-security-base-l1-2-0!CheckTokenMembershipEx` at `0x1800298fd`
- `api-ms-win-security-base-l1-2-0!CheckTokenMembershipEx` at `0x1800298fd`
- `api-ms-win-appmodel-runtime-internal-l1-1-1!GetPackageStatus` at `0x180029b90`
- `api-ms-win-appmodel-runtime-internal-l1-1-1!GetPackageStatus` at `0x180029b90`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x1800294e7`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x1800294e7`

## string_xrefs

- `0x18002957d`: `onecore\internal\sdk\inc\wil\opensource/wil/token_helpers.h`
- `0x1800295b9`: `onecore\internal\sdk\inc\wil\opensource/wil/token_helpers.h`
- `0x1800295dd`: `onecore\internal\sdk\inc\wil\opensource/wil/token_helpers.h`
- `0x18002a018`: `onecore\private\com\inc\combase\ComError.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=19
__int64 __fastcall Execution::ActivationManagerShim::ActivateApplicationForContractCore(
        __int64 a1,
        HSTRING a2,
        HSTRING a3,
        unsigned __int64 a4,
        unsigned int a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        __int64 a9,
        unsigned int a10,
        __int64 a11,
        __int64 a12,
        unsigned int *a13,
        __int64 a14)
{
  char *v16; // rcx
  UserContextHelpers *v17; // r14
  int v18; // eax
  __int64 v19; // rdi
  const char *v20; // r9
  PSID *v21; // rbx
  int LastError; // edi
  const char *v23; // r9
  unsigned __int64 v24; // rdx
  int v25; // eax
  unsigned int v26; // ebx
  const char *v27; // r9
  __int64 v28; // rax
  int v29; // r14d
  bool v30; // r13
  char v31; // bl
  unsigned __int16 *v32; // rcx
  unsigned __int64 v33; // r13
  unsigned int PackageStatus; // eax
  int v35; // eax
  HANDLE v36; // rdi
  __int64 (__fastcall *v37)(HANDLE, PVOID, unsigned __int64); // rbx
  HSTRING_HEADER *v38; // rax
  int v39; // eax
  unsigned int v40; // eax
  __int64 v41; // rcx
  int PackageExecutionContextForAumidAndUser; // eax
  int v43; // ecx
  int v44; // edx
  int v45; // ecx
  int v46; // edx
  unsigned int v47; // ebx
  LPVOID v48; // r13
  _DWORD *v49; // rax
  __int64 v50; // rcx
  unsigned int v51; // ecx
  __int64 v52; // rcx
  __int64 v53; // rcx
  __int64 v54; // rcx
  int v55; // eax
  RTL_SRWLOCK *v56; // rbx
  char v57; // di
  int *v58; // rcx
  int v59; // eax
  __int64 v60; // rdx
  int v61; // eax
  void *v62; // rbx
  HANDLE v63; // rcx
  HSTRING v64; // rcx
  int ReturnLength; // [rsp+20h] [rbp-180h]
  int ReturnLengtha; // [rsp+20h] [rbp-180h]
  int ReturnLengthb; // [rsp+20h] [rbp-180h]
  unsigned int ReturnLengthc; // [rsp+20h] [rbp-180h]
  int ReturnLengthd; // [rsp+20h] [rbp-180h]
  DWORD TokenInformationLength; // [rsp+120h] [rbp-80h] BYREF
  bool v71; // [rsp+124h] [rbp-7Ch] BYREF
  char v72; // [rsp+125h] [rbp-7Bh] BYREF
  char v73; // [rsp+126h] [rbp-7Ah] BYREF
  char v74; // [rsp+127h] [rbp-79h] BYREF
  HANDLE TokenHandle; // [rsp+128h] [rbp-78h] BYREF
  char v76; // [rsp+130h] [rbp-70h] BYREF
  bool v77[3]; // [rsp+131h] [rbp-6Fh] BYREF
  int v78; // [rsp+134h] [rbp-6Ch] BYREF
  unsigned int v79; // [rsp+138h] [rbp-68h] BYREF
  unsigned int v80; // [rsp+13Ch] [rbp-64h] BYREF
  unsigned __int64 v81; // [rsp+140h] [rbp-60h] BYREF
  unsigned __int16 *StringRawBuffer; // [rsp+148h] [rbp-58h] BYREF
  __int64 v83; // [rsp+150h] [rbp-50h] BYREF
  unsigned __int16 *v84; // [rsp+158h] [rbp-48h] BYREF
  __int64 v85; // [rsp+160h] [rbp-40h]
  __int64 v86; // [rsp+168h] [rbp-38h]
  unsigned int v87; // [rsp+170h] [rbp-30h] BYREF
  int v88; // [rsp+174h] [rbp-2Ch] BYREF
  __int64 v89; // [rsp+178h] [rbp-28h] BYREF
  unsigned __int16 *v90; // [rsp+180h] [rbp-20h] BYREF
  LPVOID v91; // [rsp+188h] [rbp-18h] BYREF
  __int64 v92; // [rsp+190h] [rbp-10h]
  __int64 v93; // [rsp+198h] [rbp-8h]
  unsigned __int64 v94; // [rsp+1A0h] [rbp+0h] BYREF
  unsigned int v95[2]; // [rsp+1A8h] [rbp+8h] BYREF
  __int64 v96; // [rsp+1B0h] [rbp+10h] BYREF
  HSTRING string; // [rsp+1B8h] [rbp+18h] BYREF
  unsigned int *v98; // [rsp+1C0h] [rbp+20h] BYREF
  __int128 v99; // [rsp+1C8h] [rbp+28h] BYREF
  HSTRING v100[2]; // [rsp+1D8h] [rbp+38h] BYREF
  LPVOID v101[3]; // [rsp+1E8h] [rbp+48h] BYREF
  const WCHAR *v102; // [rsp+200h] [rbp+60h] BYREF
  int v103; // [rsp+208h] [rbp+68h]
  __int64 v104; // [rsp+210h] [rbp+70h] BYREF
  __int64 v105; // [rsp+218h] [rbp+78h] BYREF
  __int64 v106; // [rsp+220h] [rbp+80h] BYREF
  __int64 v107; // [rsp+228h] [rbp+88h] BYREF
  __int64 v108; // [rsp+230h] [rbp+90h] BYREF
  _QWORD v109[3]; // [rsp+238h] [rbp+98h] BYREF
  _OWORD v110[9]; // [rsp+250h] [rbp+B0h] BYREF
  __int64 v111; // [rsp+2E0h] [rbp+140h]
  __int64 v112; // [rsp+370h] [rbp+1D0h] BYREF
  GUID v113; // [rsp+378h] [rbp+1D8h]
  LPVOID pv; // [rsp+388h] [rbp+1E8h]
  HANDLE hObject[2]; // [rsp+390h] [rbp+1F0h] BYREF
  char v116; // [rsp+3A0h] [rbp+200h]
  int v117; // [rsp+3A1h] [rbp+201h]
  __int16 v118; // [rsp+3A5h] [rbp+205h]
  char v119; // [rsp+3A7h] [rbp+207h]
  __int64 v120; // [rsp+3A8h] [rbp+208h]
  HSTRING_HEADER hstringHeader; // [rsp+3B0h] [rbp+210h] BYREF
  __int64 v122; // [rsp+3C8h] [rbp+228h]
  void **v123; // [rsp+3D0h] [rbp+230h] BYREF
  int v124; // [rsp+3D8h] [rbp+238h] BYREF
  char v125; // [rsp+3DCh] [rbp+23Ch]
  int v126; // [rsp+400h] [rbp+260h] BYREF
  const char *v127; // [rsp+408h] [rbp+268h]
  __int64 v128; // [rsp+410h] [rbp+270h]
  char v129; // [rsp+418h] [rbp+278h]
  int v130; // [rsp+420h] [rbp+280h]
  __int128 v131; // [rsp+428h] [rbp+288h]
  __int128 v132; // [rsp+438h] [rbp+298h]
  __int128 v133; // [rsp+448h] [rbp+2A8h]
  __int128 v134; // [rsp+458h] [rbp+2B8h]
  __int128 v135; // [rsp+468h] [rbp+2C8h]
  __int128 v136; // [rsp+478h] [rbp+2D8h]
  __int128 v137; // [rsp+488h] [rbp+2E8h]
  __int128 v138; // [rsp+498h] [rbp+2F8h]
  __int128 v139; // [rsp+4A8h] [rbp+308h]
  __int64 v140; // [rsp+4B8h] [rbp+318h]
  __int128 v141; // [rsp+4C0h] [rbp+320h]
  int v142; // [rsp+4D0h] [rbp+330h]
  __int64 v143; // [rsp+4D8h] [rbp+338h]
  int *v144; // [rsp+4E0h] [rbp+340h]
  void *v145; // [rsp+4E8h] [rbp+348h] BYREF
  _QWORD v146[3]; // [rsp+4F0h] [rbp+350h] BYREF
  int v147; // [rsp+508h] [rbp+368h]
  int *v148; // [rsp+510h] [rbp+370h]
  char v149; // [rsp+518h] [rbp+378h]
  _OWORD v150[3]; // [rsp+520h] [rbp+380h] BYREF
  __int64 v151; // [rsp+550h] [rbp+3B0h]
  wil::details::in1diag3 *retaddr; // [rsp+5B8h] [rbp+418h]

  v109[0] = a2;
  string = a3;
  v81 = a4;
  *(_QWORD *)v95 = a6;
  v96 = a7;
  v106 = a8;
  v108 = a9;
  v105 = a11;
  v107 = a12;
  v98 = a13;
  v104 = a14;
  StringRawBuffer = (unsigned __int16 *)WindowsGetStringRawBuffer(a2, 0);
  v90 = (unsigned __int16 *)WindowsGetStringRawBuffer(string, 0);
  memset(v101, 0, sizeof(v101));
  v84 = 0;
  v85 = 0;
  v86 = 0;
  v91 = 0;
  v92 = 0;
  v93 = 0;
  v80 = -1;
  v79 = 0;
  v72 = 0;
  v76 = 0;
  v73 = 0;
  v74 = 0;
  v87 = 2;
  v99 = 0;
  *(_OWORD *)v100 = 0;
  v112 = -1;
  v113 = GUID_NULL;
  pv = 0;
  *(_OWORD *)hObject = 0;
  v116 = 0;
  v117 = 0;
  v118 = 0;
  v119 = 0;
  v120 = 0;
  v88 = 0;
  if ( (a5 & 0x3000) == 0x3000 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x444,
      (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\activationmanagershim.cpp",
      (const char *)0x80070057LL,
      ReturnLength);
    if ( hObject[1] )
      HamActivityWrapper::Close((HamActivityWrapper *)hObject[1]);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&hObject[1]);
    if ( (unsigned __int64)hObject[0] - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle(hObject[0]);
    WindowsDeleteString(v100[1]);
    v100[1] = 0;
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(v100);
    v92 = 0;
    v93 = 0;
    v85 = 0;
    v86 = 0;
    if ( v101[0] )
      CoTaskMemFree(v101[0]);
    return 2147942487LL;
  }
  v78 = 0;
  v16 = 0;
  TokenHandle = 0;
  if ( !v81 )
    goto LABEL_27;
  v17 = Execution::ActivationManagerShim::s_userContextHelper;
  v18 = UMgrQueryUserToken(v81, &TokenHandle);
  if ( v18 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x52,
      (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\usercontexthelpers.cpp",
      (const char *)(unsigned int)v18,
      ReturnLength);
LABEL_26:
    v16 = (char *)TokenHandle;
LABEL_27:
    if ( (unsigned __int64)(v16 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle(v16);
    goto LABEL_29;
  }
  v19 = -6;
  if ( TokenHandle )
    v19 = (__int64)TokenHandle;
  TokenInformationLength = 0;
  if ( GetTokenInformation((HANDLE)v19, TokenUser, 0, 0, &TokenInformationLength) || GetLastError() != 122 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x117,
                  (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/token_helpers.h",
                  v20);
LABEL_21:
    v21 = 0;
    if ( LastError < 0 )
      goto LABEL_22;
    goto LABEL_23;
  }
  v21 = (PSID *)operator new(TokenInformationLength, (const struct std::nothrow_t *)&std::nothrow);
  if ( !v21 )
  {
    LastError = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x119,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/token_helpers.h",
      (const char *)0x8007000ELL,
      ReturnLengtha);
LABEL_22:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x56,
      (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\usercontexthelpers.cpp",
      (const char *)(unsigned int)LastError,
      ReturnLengtha);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
LABEL_40:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x447,
      (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\activationmanagershim.cpp",
      (const char *)(unsigned int)LastError,
      ReturnLengtha);
    ActivationHostInfo::~ActivationHostInfo((ActivationHostInfo *)&v112);
    ActivateByExtensionArgs::~ActivateByExtensionArgs((ActivateByExtensionArgs *)&v99);
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v91);
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v84);
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v101);
    return (unsigned int)LastError;
  }
  if ( !GetTokenInformation((HANDLE)v19, TokenUser, v21, TokenInformationLength, &TokenInformationLength) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x11A,
                  (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/token_helpers.h",
                  v23);
    operator delete(v21);
    goto LABEL_21;
  }
LABEL_23:
  if ( IsWellKnownSid(*v21, WinLocalAccountAndAdministratorSid|WinCreatorGroupSid) )
  {
    v78 = 1;
LABEL_25:
    operator delete(v21);
    goto LABEL_26;
  }
  if ( (unsigned __int8)RtlIsMultiSessionSku()
    || !*(_BYTE *)v17
    || (int)UserContextHelpers::GetResourceAccountSid(v17) < 0 )
  {
    goto LABEL_25;
  }
  TokenInformationLength = 0;
  if ( (unsigned int)CheckTokenMembershipEx(TokenHandle, (char *)v17 + 4, 0, &TokenInformationLength) )
  {
    if ( !TokenInformationLength )
      goto LABEL_25;
    v78 = 2;
    operator delete(v21);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
  }
  else
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x61,
                  (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\usercontexthelpers.cpp",
                  v27);
    operator delete(v21);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
    if ( LastError < 0 )
      goto LABEL_40;
  }
LABEL_29:
  v77[0] = v78 == 1;
  v24 = _InterlockedIncrement64(&Execution::ActivationManagerShim::s_activationCounter);
  if ( !v24 )
    v24 = _InterlockedIncrement64(&Execution::ActivationManagerShim::s_activationCounter);
  v94 = v24;
  v124 = 0;
  v125 = 0;
  v129 = 0;
  v126 = 0;
  v127 = "ForegroundActivation";
  v128 = 0;
  v130 = 0;
  v141 = 0;
  v131 = 0;
  v132 = 0;
  v133 = 0;
  v134 = 0;
  v135 = 0;
  v136 = 0;
  v137 = 0;
  v138 = 0;
  v139 = 0;
  v140 = 0;
  v142 = 1;
  v143 = 0;
  v144 = &v124;
  v145 = 0;
  v146[0] = 0;
  v146[1] = &v123;
  v146[2] = 0;
  v147 = 0;
  v148 = &v126;
  v149 = 0;
  v123 = &AAMTraceProvider::ForegroundActivation::`vftable';
  AAMTraceProvider::ForegroundActivation::StartActivity(
    (AAMTraceProvider::ForegroundActivation *)&v123,
    v24,
    StringRawBuffer,
    v90,
    a5,
    v81);
  v109[1] = a1 + 96;
  AcquireSRWLockExclusive((PSRWLOCK)(a1 + 96));
  *(_OWORD *)(a1 + 152) = 0;
  *(_OWORD *)(a1 + 168) = 0;
  *(_OWORD *)(a1 + 184) = 0;
  *(_QWORD *)(a1 + 200) = 0;
  *(LARGE_INTEGER *)(a1 + 152) = Execution::ActivationManagerShim::s_qpcFrequency;
  QueryPerformanceCounter((LARGE_INTEGER *)(a1 + 160));
  v83 = 0;
  v89 = 0;
  v25 = (***(__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))v95)(
          *(_QWORD *)v95,
          &GUID_99fc44e3_ce9a_4284_bf04_76331d1b1788,
          &v89);
  v26 = v25;
  if ( v25 >= 0 )
  {
    v28 = lambda_c4d050534b694ece78bf58b6639429c6_::_lambda_c4d050534b694ece78bf58b6639429c6_(
            (unsigned int)v110,
            (unsigned int)&StringRawBuffer,
            (unsigned int)v101,
            (unsigned int)&v91,
            (__int64)v95,
            (__int64)v109,
            (__int64)&string,
            (__int64)&v81,
            (__int64)&a5,
            (__int64)&v123,
            (__int64)&v94,
            (__int64)&v108,
            a1,
            (__int64)v77,
            (__int64)&v90,
            (__int64)&v89,
            (__int64)&v107,
            (__int64)&v98,
            (__int64)&v74,
            (__int64)&a10,
            (__int64)&v84,
            (__int64)&v73,
            (__int64)&v78,
            (__int64)&v76,
            (__int64)&v79,
            (__int64)&v88,
            (__int64)&v106,
            (__int64)&v96,
            (__int64)&v99,
            (__int64)&v72,
            (__int64)&v105,
            (__int64)&v112,
            (__int64)&v80,
            (__int64)&v104,
            (__int64)&v87,
            (__int64)&v83);
    v29 = lambda_c4d050534b694ece78bf58b6639429c6_::operator()(v28);
    (*(void (__fastcall **)(struct IApplicationInstanceManager *, __int64))(*(_QWORD *)Execution::ActivationManagerShim::s_applicationInstanceManager
                                                                          + 64LL))(
      Execution::ActivationManagerShim::s_applicationInstanceManager,
      v112);
    v30 = 0;
    v71 = 0;
    v31 = 0;
    v32 = v84;
    if ( v84 )
    {
      v33 = v81;
      v102 = v84;
      TokenInformationLength = 0;
      PackageStatus = GetPackageStatus(v84, &TokenInformationLength);
      if ( PackageStatus )
      {
        wil::details::in1diag3::Return_Win32(
          retaddr,
          (void *)0x1D7,
          (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\activationdeployment.cpp",
          (const char *)PackageStatus,
          ReturnLengthc);
      }
      else if ( (TokenInformationLength & 0x20000) != 0 )
      {
        TokenHandle = 0;
        v122 = 0;
        Microsoft::WRL::Wrappers::HStringReference::CreateReference(
          &hstringHeader,
          L"Windows.Management.Deployment.Internal.PackageManagerInternal",
          0x3Eu,
          0x3Du);
        v35 = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Management::Deployment::Internal::IPackageManagerInternal>>(
                v122,
                &TokenHandle);
        if ( v35 >= 0 )
        {
          v36 = TokenHandle;
          v37 = *(__int64 (__fastcall **)(HANDLE, PVOID, unsigned __int64))(*(_QWORD *)TokenHandle + 384LL);
          v38 = Microsoft::WRL::Wrappers::HStringReference::HStringReference((HSTRING_HEADER *)v150, &v102);
          v39 = v37(v36, v38[1].Reserved.Reserved1, v33);
          if ( v39 < 0 )
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x1DF,
              (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\activationdeployment.cpp",
              (const char *)(unsigned int)v39,
              ReturnLengthc);
          v122 = 0;
          Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&TokenHandle);
          v31 = 0;
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x1DC,
            (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\activationdeployment.cpp",
            (const char *)(unsigned int)v35,
            ReturnLengthc);
          v122 = 0;
          Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&TokenHandle);
        }
      }
      v32 = v84;
      if ( v96 )
      {
        Execution::ActivationManagerShim::IsNonSystemVolumeApp(v84, &v71);
        v32 = v84;
      }
      v30 = v71;
    }
    if ( v29 < 0 )
    {
      if ( v32 )
        ReRegisterPackageIfNeeded(v32, v29);
      ReturnLengthc = v95[0];
      v40 = CreateAndLaunchRemediationHandlerIfNeeded(StringRawBuffer, v90, v81, a5);
      if ( byte_1800D1F02 < 0 )
        McTemplateU0q_EventWriteTransfer(v41, Activation_RemediationAttempt, v40);
      v31 = IsSystemShuttingDown();
    }
    TokenInformationLength = 0;
    PackageExecutionContextForAumidAndUser = GetPackageExecutionContextForAumidAndUser(
                                               StringRawBuffer,
                                               v81,
                                               &TokenInformationLength);
    if ( PackageExecutionContextForAumidAndUser < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x55D,
        (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\activationmanagershim.cpp",
        (const char *)(unsigned int)PackageExecutionContextForAumidAndUser,
        ReturnLengthc);
    v43 = *(_DWORD *)(a1 + 204);
    if ( v30 )
      v43 = *(_DWORD *)(a1 + 204) | 2;
    if ( v72 )
      v43 |= 4u;
    v44 = v43 | 8;
    if ( !v31 )
      v44 = v43;
    v45 = v44 | 0x40;
    if ( !v79 )
      v45 = v44;
    v46 = v45 | 0x80;
    if ( !*(_QWORD *)(a1 + 208) )
      v46 = v45;
    if ( v73 )
      v46 |= 0x100u;
    if ( v74 )
      v46 |= 0x200u;
    v47 = v46 | 0x400;
    if ( TokenInformationLength - 2 > 1 )
      v47 = v46;
    if ( v29 < 0 )
    {
      if ( (Microsoft_Windows_Immersive_ShellEnableBits & 0x100) != 0 )
        McTemplateU0zdq_EventWriteTransfer(v45, v46, (_DWORD)StringRawBuffer, v29, *(_DWORD *)(a1 + 144));
    }
    else
    {
      v48 = pv;
      TokenHandle = 0;
      TokenInformationLength = 0;
      if ( __std_init_once_begin_initialize(
             &`AAMTraceProvider::Instance'::`2'::wrapper,
             0,
             (PBOOL)&TokenInformationLength,
             &TokenHandle)
        && TokenInformationLength )
      {
        v102 = (const WCHAR *)&`AAMTraceProvider::Instance'::`2'::wrapper;
        TokenHandle = &qword_1800D2210;
        qword_1800D2218 = 0;
        byte_1800D2220 = 0;
        dword_1800D2224 = 0;
        qword_1800D2210 = (__int64)&ActivationManagerPerftrack::`vftable';
        qword_1800D2228 = (__int64)&`AAMTraceProvider::StaticHandle::StaticHandle'::`2'::__hInner;
        atexit(_lambda_7e8ef9e9b596109f338594047241dcdf_::_lambda_invoker_cdecl_);
        v103 = 0;
        wil::details::static_lazy<DesktopAppXProvider>::Completer::~Completer(&v102);
      }
      v49 = (_DWORD *)*((_QWORD *)TokenHandle + 1);
      if ( v49 && *v49 )
      {
        AAMTraceProvider::Instance();
        v150[0] = *(_OWORD *)(a1 + 152);
        v150[1] = *(_OWORD *)(a1 + 168);
        v150[2] = *(_OWORD *)(a1 + 184);
        v151 = *(_QWORD *)(a1 + 200);
        ReturnLengthc = a5;
        AAMTraceProvider::ActivationPerfStats_(v50, v94, StringRawBuffer, v48);
      }
    }
    if ( v96 )
      v51 = *(_DWORD *)(v96 + 48);
    else
      v51 = 0;
    AAMTraceProvider::ForegroundActivation::Stop(
      (AAMTraceProvider::ForegroundActivation *)&v123,
      v94,
      StringRawBuffer,
      v84,
      ReturnLengthc,
      v90,
      v29,
      *v98,
      v80,
      a5,
      v47,
      v81,
      *(_DWORD *)(a1 + 144),
      v79,
      v88,
      a10,
      v51,
      v87);
    *(_QWORD *)(a1 + 104) = 0;
    *(_DWORD *)(a1 + 112) = 0;
    v52 = *(_QWORD *)(a1 + 136);
    if ( v52 )
    {
      *(_QWORD *)(a1 + 136) = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v52 + 16LL))(v52);
    }
    *(_DWORD *)(a1 + 144) = 0;
    v53 = v89;
    if ( v89 )
    {
      v89 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v53 + 16LL))(v53);
    }
    v54 = v83;
    if ( v83 )
    {
      v55 = CoSetErrorInfo(0, v83);
      if ( v55 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x1F,
          (unsigned int)"onecore\\private\\com\\inc\\combase\\ComError.h",
          (const char *)(unsigned int)v55,
          ReturnLengthd);
      v54 = v83;
    }
    if ( v54 )
    {
      v83 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v54 + 16LL))(v54);
    }
    if ( a1 != -96 )
      ReleaseSRWLockExclusive((PSRWLOCK)(a1 + 96));
    v123 = &AAMTraceProvider::ForegroundActivation::`vftable';
    if ( !v145 )
      goto LABEL_111;
    v56 = (RTL_SRWLOCK *)((char *)v145 + 264);
    AcquireSRWLockExclusive((PSRWLOCK)v145 + 33);
    if ( v145 && *(_DWORD *)v145 == 1 )
    {
      v57 = 1;
    }
    else
    {
      v57 = 0;
      wil::details::shared_object<wil::ActivityBase<AAMTraceProvider,2,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<AAMTraceProvider,_TlgReflectorTag_Param0IsProviderType>>::reset(&v145);
    }
    if ( v56 )
      ReleaseSRWLockExclusive(v56);
    if ( v57 )
    {
LABEL_111:
      v58 = v144;
      if ( *v144 == 1 )
      {
        v59 = v144[22];
        v60 = 2147942974LL;
        if ( v59 < 0 )
          v60 = (unsigned int)v59;
        v61 = v144[62];
        if ( v61 < 1 )
        {
          memset(v110, 0, sizeof(v110));
          v111 = 0;
          wil::details::WilFailFast((wil::details *)v110, (const struct wil::FailureInfo *)v60);
        }
        if ( v144[18] >= 0 )
          v144[18] = v60;
        v58[62] = v61 - 1;
        ((void (__fastcall *)(void ***, __int64))v123[1])(&v123, v60);
      }
    }
    if ( v147 )
      wil::details::ThreadFailureCallbackHolder::StopWatching((wil::details::ThreadFailureCallbackHolder *)v146);
    if ( v145 )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v145, 0xFFFFFFFF) == 1 )
      {
        v62 = v145;
        if ( v145 )
        {
          wil::ActivityBase<AAMTraceProvider,2,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<AAMTraceProvider,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<AAMTraceProvider,_TlgReflectorTag_Param0IsProviderType>((char *)v145 + 8);
          operator delete(v62, (const struct std::nothrow_t *)0x110);
        }
      }
      v145 = 0;
    }
    wil::ActivityBase<AAMTraceProvider,2,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<AAMTraceProvider,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<AAMTraceProvider,_TlgReflectorTag_Param0IsProviderType>(&v124);
    v63 = hObject[1];
    if ( hObject[1] )
    {
      HamActivityWrapper::Close((HamActivityWrapper *)hObject[1]);
      v63 = hObject[1];
    }
    if ( v63 )
    {
      hObject[1] = 0;
      (*(void (__fastcall **)(HANDLE))(*(_QWORD *)v63 + 16LL))(v63);
    }
    if ( (unsigned __int64)hObject[0] - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle(hObject[0]);
    if ( pv )
      CoTaskMemFree(pv);
    WindowsDeleteString(v100[1]);
    v100[1] = 0;
    v64 = v100[0];
    if ( v100[0] )
    {
      v100[0] = 0;
      (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v64 + 16LL))(v64);
    }
    if ( v91 )
    {
      CoTaskMemFree(v91);
      v91 = 0;
    }
    v92 = 0;
    v93 = 0;
    if ( v84 )
    {
      CoTaskMemFree(v84);
      v84 = 0;
    }
    v85 = 0;
    v86 = 0;
    if ( v101[0] )
      CoTaskMemFree(v101[0]);
    return (unsigned int)v29;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x455,
      (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\activationmanagershim.cpp",
      (const char *)(unsigned int)v25,
      ReturnLengthb);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v89);
    Com::CapturedComError::~CapturedComError((Com::CapturedComError *)&v83);
    if ( a1 != -96 )
      ReleaseSRWLockExclusive((PSRWLOCK)(a1 + 96));
    v123 = &AAMTraceProvider::ForegroundActivation::`vftable';
    wil::ActivityBase<AAMTraceProvider,2,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(&v123);
    wil::ActivityBase<AAMTraceProvider,2,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<AAMTraceProvider,2,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>(&v123);
    ActivationHostInfo::~ActivationHostInfo((ActivationHostInfo *)&v112);
    ActivateByExtensionArgs::~ActivateByExtensionArgs((ActivateByExtensionArgs *)&v99);
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v91);
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v84);
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v101);
    return v26;
  }
}

```

## disassembly

```asm
0x180029270  push    rbp
0x180029272  push    rbx
0x180029273  push    rsi
0x180029274  push    rdi
0x180029275  push    r12
0x180029277  push    r13
0x180029279  push    r14
0x18002927b  push    r15
0x18002927d  lea     rbp, [rsp-3D8h]
0x180029285  sub     rsp, 578h
0x18002928c  mov     rax, cs:__security_cookie
0x180029293  xor     rax, rsp
0x180029296  mov     [rbp+410h+var_50], rax
0x18002929d  mov     r10, rdx
0x1800292a0  mov     rsi, rcx
0x1800292a3  mov     [rbp+410h+var_378], rdx
0x1800292aa  mov     [rbp+410h+string], r8
0x1800292ae  mov     [rbp+410h+var_470], r9
0x1800292b2  mov     rax, [rbp+410h+arg_28]
0x1800292b9  mov     qword ptr [rbp+410h+var_408], rax
0x1800292bd  mov     rax, [rbp+410h+arg_30]
0x1800292c4  mov     [rbp+410h+var_400], rax
0x1800292c8  mov     rax, [rbp+410h+arg_38]
0x1800292cf  mov     [rbp+410h+var_390], rax
0x1800292d6  mov     rax, [rbp+410h+arg_40]
0x1800292dd  mov     [rbp+410h+var_380], rax
0x1800292e4  mov     rax, [rbp+410h+arg_50]
0x1800292eb  mov     [rbp+410h+var_398], rax
0x1800292ef  mov     rax, [rbp+410h+arg_58]
0x1800292f6  mov     [rbp+410h+var_388], rax
0x1800292fd  mov     rax, [rbp+410h+arg_60]
0x180029304  mov     [rbp+410h+var_3F0], rax
0x180029308  mov     rax, [rbp+410h+arg_68]
0x18002930f  mov     [rbp+410h+var_3A0], rax
0x180029313  xor     r13d, r13d
0x180029316  xor     edx, edx; length
0x180029318  mov     rcx, r10; string
0x18002931b  call    cs:__imp_WindowsGetStringRawBuffer
0x180029321  mov     [rbp+410h+var_468], rax
0x180029325  xor     edx, edx; length
0x180029327  mov     rcx, [rbp+410h+string]; string
0x18002932b  call    cs:__imp_WindowsGetStringRawBuffer
0x180029331  mov     [rbp+410h+var_430], rax
0x180029335  mov     [rbp+410h+var_3C8], r13
0x180029339  mov     [rbp+410h+var_3C0], r13
0x18002933d  mov     [rbp+410h+var_3B8], r13
0x180029341  mov     [rbp+410h+var_458], r13
0x180029345  mov     [rbp+410h+var_450], r13
0x180029349  mov     [rbp+410h+var_448], r13
0x18002934d  mov     [rbp+410h+var_428], r13
0x180029351  mov     [rbp+410h+var_420], r13
0x180029355  mov     [rbp+410h+var_418], r13
0x180029359  mov     [rbp+410h+var_474], 0FFFFFFFFh
0x180029360  mov     [rbp+410h+var_478], r13d
0x180029364  mov     [rbp+410h+var_48B], r13b
0x180029368  mov     [rbp+410h+var_480], r13b
0x18002936c  mov     [rbp+410h+var_48A], r13b
0x180029370  mov     [rbp+410h+var_489], r13b
0x180029374  mov     [rbp+410h+var_440], 2
0x18002937b  xorps   xmm0, xmm0
0x18002937e  movups  [rbp+410h+var_3E8], xmm0
0x180029382  xorps   xmm1, xmm1
0x180029385  movdqu  xmmword ptr [rbp+410h+var_3D8], xmm1
0x18002938a  mov     r12, 0FFFFFFFFFFFFFFFFh
0x180029391  mov     [rbp+410h+var_240], r12
0x180029398  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18002939f  movups  [rbp+410h+var_238], xmm0
0x1800293a6  xor     eax, eax
0x1800293a8  mov     [rbp+410h+pv], r13
0x1800293af  xorps   xmm0, xmm0
0x1800293b2  movdqa  xmmword ptr [rbp+410h+hObject], xmm0
0x1800293ba  mov     [rbp+410h+var_210], al
0x1800293c0  mov     [rbp+410h+var_20F], eax
0x1800293c6  mov     [rbp+410h+var_20B], ax
0x1800293cd  mov     [rbp+410h+var_209], al
0x1800293d3  mov     [rbp+410h+var_208], rax
0x1800293da  mov     [rbp+410h+var_43C], r13d
0x1800293de  mov     eax, [rbp+410h+arg_20]
0x1800293e4  and     eax, 3000h
0x1800293e9  cmp     eax, 3000h
0x1800293ee  jnz     loc_1800294C1
0x1800293f4  mov     rcx, [rbp+418h]; this
0x1800293fb  mov     r9d, 80070057h; char *
0x180029401  lea     r8, aOnecoreuapBase_13; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x180029408  mov     edx, 444h; void *
0x18002940d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180029412  nop
0x180029413  mov     rcx, [rbp+410h+hObject+8]; this
0x18002941a  test    rcx, rcx
0x18002941d  jz      short loc_180029424
0x18002941f  call    ?Close@HamActivityWrapper@@QEAAXXZ; HamActivityWrapper::Close(void)
0x180029424  lea     rcx, [rbp+410h+hObject+8]
0x18002942b  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180029430  mov     rcx, [rbp+410h+hObject]; hObject
0x180029437  lea     rax, [rcx-1]
0x18002943b  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18002943f  ja      short loc_180029447
0x180029441  call    cs:__imp_CloseHandle
0x180029447  mov     rcx, [rbp+410h+pv]; pv
0x18002944e  test    rcx, rcx
0x180029451  jz      short loc_18002945A
0x180029453  call    cs:__imp_CoTaskMemFree
0x180029459  nop
0x18002945a  mov     rcx, [rbp+410h+var_3D8+8]; string
0x18002945e  call    cs:__imp_WindowsDeleteString
0x180029464  mov     [rbp+410h+var_3D8+8], r13
0x180029468  lea     rcx, [rbp+410h+var_3D8]
0x18002946c  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180029471  nop
0x180029472  mov     rcx, [rbp+410h+var_428]; pv
0x180029476  test    rcx, rcx
0x180029479  jz      short loc_180029485
0x18002947b  call    cs:__imp_CoTaskMemFree
0x180029481  mov     [rbp+410h+var_428], r13
0x180029485  mov     [rbp+410h+var_420], r13
0x180029489  mov     [rbp+410h+var_418], r13
0x18002948d  mov     rcx, [rbp+410h+var_458]; pv
0x180029491  test    rcx, rcx
0x180029494  jz      short loc_1800294A0
0x180029496  call    cs:__imp_CoTaskMemFree
0x18002949c  mov     [rbp+410h+var_458], r13
0x1800294a0  mov     [rbp+410h+var_450], r13
0x1800294a4  mov     [rbp+410h+var_448], r13
0x1800294a8  mov     rcx, [rbp+410h+var_3C8]; pv
0x1800294ac  test    rcx, rcx
0x1800294af  jz      short loc_1800294B7
0x1800294b1  call    cs:__imp_CoTaskMemFree
0x1800294b7  mov     eax, 80070057h
0x1800294bc  jmp     loc_18002A23E
0x1800294c1  mov     [rbp+410h+var_47C], r13d
0x1800294c5  mov     rcx, r13
0x1800294c8  mov     [rbp+410h+TokenHandle], rcx
0x1800294cc  mov     rax, [rbp+410h+var_470]
0x1800294d0  test    rax, rax
0x1800294d3  jz      loc_180029649
0x1800294d9  mov     r14, cs:?s_userContextHelper@ActivationManagerShim@Execution@@0V?$unique_ptr@VUserContextHelpers@@U?$default_delete@VUserContextHelpers@@@wistd@@@wistd@@A; wistd::unique_ptr<UserContextHelpers,wistd::default_delete<UserContextHelpers>> Execution::ActivationManagerShim::s_userContextHelper
0x1800294e0  lea     rdx, [rbp+410h+TokenHandle]
0x1800294e4  mov     rcx, rax
0x1800294e7  call    cs:__imp_UMgrQueryUserToken
0x1800294ed  mov     rcx, [rbp+418h]; this
0x1800294f4  test    eax, eax
0x1800294f6  jns     short loc_180029511
0x1800294f8  mov     r9d, eax; char *
0x1800294fb  lea     r8, aOnecoreuapBase_30; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x180029502  mov     edx, 52h ; 'R'; void *
0x180029507  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002950c  jmp     loc_180029645
0x180029511  mov     rax, [rbp+410h+TokenHandle]
0x180029515  mov     rdi, 0FFFFFFFFFFFFFFFAh
0x18002951c  test    rax, rax
0x18002951f  cmovnz  rdi, rax
0x180029523  mov     [rbp+410h+TokenInformationLength], r13d
0x180029527  lea     rax, [rbp+410h+TokenInformationLength]
0x18002952b  mov     [rsp+5B0h+ReturnLength], rax; int
0x180029530  xor     r9d, r9d; TokenInformationLength
0x180029533  xor     r8d, r8d; TokenInformation
0x180029536  mov     edx, 1; TokenInformationClass
0x18002953b  mov     rcx, rdi; TokenHandle
0x18002953e  call    cs:__imp_GetTokenInformation
0x180029544  test    eax, eax
0x180029546  jnz     loc_1800295D6
0x18002954c  call    cs:__imp_GetLastError
0x180029552  cmp     eax, 7Ah ; 'z'
0x180029555  jnz     short loc_1800295D6
0x180029557  mov     ecx, [rbp+410h+TokenInformationLength]; unsigned __int64
0x18002955a  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180029561  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180029566  mov     rbx, rax
0x180029569  test    rax, rax
0x18002956c  jnz     short loc_180029590
0x18002956e  mov     rcx, [rbp+418h]; this
0x180029575  mov     edi, 8007000Eh
0x18002957a  mov     r9d, edi; char *
0x18002957d  lea     r8, aOnecoreInterna_4; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180029584  mov     edx, 119h; void *
0x180029589  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002958e  jmp     short loc_1800295F7
0x180029590  lea     rax, [rbp+410h+TokenInformationLength]
0x180029594  mov     [rsp+5B0h+ReturnLength], rax; int
0x180029599  mov     r9d, [rbp+410h+TokenInformationLength]; TokenInformationLength
0x18002959d  mov     r8, rbx; TokenInformation
0x1800295a0  mov     edx, 1; TokenInformationClass
0x1800295a5  mov     rcx, rdi; TokenHandle
0x1800295a8  call    cs:__imp_GetTokenInformation
0x1800295ae  test    eax, eax
0x1800295b0  jnz     short loc_180029620
0x1800295b2  mov     rcx, [rbp+418h]; this
0x1800295b9  lea     r8, aOnecoreInterna_4; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800295c0  mov     edx, 11Ah; void *
0x1800295c5  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800295ca  mov     edi, eax
0x1800295cc  mov     rcx, rbx; Block
0x1800295cf  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800295d4  jmp     short loc_1800295F0
0x1800295d6  mov     rcx, [rbp+418h]; this
0x1800295dd  lea     r8, aOnecoreInterna_4; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800295e4  mov     edx, 117h; void *
0x1800295e9  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800295ee  mov     edi, eax
0x1800295f0  mov     rbx, r13
0x1800295f3  test    edi, edi
0x1800295f5  jns     short loc_180029620
0x1800295f7  mov     rcx, [rbp+418h]; this
0x1800295fe  mov     r9d, edi; char *
0x180029601  lea     r8, aOnecoreuapBase_30; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x180029608  mov     edx, 56h ; 'V'; void *
0x18002960d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180029612  lea     rcx, [rbp+410h+TokenHandle]
0x180029616  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18002961b  jmp     loc_18002993E
0x180029620  mov     edx, 6Eh ; 'n'; WellKnownSidType
0x180029625  mov     rcx, [rbx]; pSid
0x180029628  call    cs:__imp_IsWellKnownSid
0x18002962e  test    eax, eax
0x180029630  jz      loc_1800298C3
0x180029636  mov     [rbp+410h+var_47C], 1
0x18002963d  mov     rcx, rbx; Block
0x180029640  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180029645  mov     rcx, [rbp+410h+TokenHandle]; hObject
0x180029649  lea     rax, [rcx-1]
0x18002964d  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180029651  ja      short loc_180029659
0x180029653  call    cs:__imp_CloseHandle
0x180029659  cmp     [rbp+410h+var_47C], 1
0x18002965d  setz    [rbp+410h+var_47F]
0x180029661  mov     edx, 1
0x180029666  lock xadd cs:?s_activationCounter@ActivationManagerShim@Execution@@0_JC, rdx; __int64 volatile Execution::ActivationManagerShim::s_activationCounter
0x18002966f  add     rdx, 1
0x180029673  jnz     short loc_180029686
0x180029675  mov     edx, 1
0x18002967a  lock xadd cs:?s_activationCounter@ActivationManagerShim@Execution@@0_JC, rdx; __int64 volatile Execution::ActivationManagerShim::s_activationCounter
0x180029683  inc     rdx; unsigned __int64
0x180029686  mov     [rbp+410h+var_410], rdx
0x18002968a  mov     [rbp+410h+var_1D8], r13d
0x180029691  mov     [rbp+410h+var_1D4], 0
0x180029698  mov     [rbp+410h+var_198], 0
0x18002969f  mov     [rbp+410h+var_1B0], r13d
0x1800296a6  lea     rax, aForegroundacti; "ForegroundActivation"
0x1800296ad  mov     [rbp+410h+var_1A8], rax
0x1800296b4  mov     [rbp+410h+var_1A0], r13
0x1800296bb  mov     [rbp+410h+var_190], r13d
0x1800296c2  xorps   xmm0, xmm0
0x1800296c5  movdqa  [rbp+410h+var_F0], xmm0
0x1800296cd  xorps   xmm1, xmm1
0x1800296d0  xor     eax, eax
0x1800296d2  movups  [rbp+410h+var_188], xmm1
0x1800296d9  movups  [rbp+410h+var_178], xmm1
0x1800296e0  movups  [rbp+410h+var_168], xmm1
0x1800296e7  movups  [rbp+410h+var_158], xmm1
0x1800296ee  movups  [rbp+410h+var_148], xmm1
0x1800296f5  movups  [rbp+410h+var_138], xmm1
0x1800296fc  movups  [rbp+410h+var_128], xmm1
0x180029703  movups  [rbp+410h+var_118], xmm1
0x18002970a  movups  [rbp+410h+var_108], xmm1
0x180029711  mov     [rbp+410h+var_F8], rax
0x180029718  mov     [rbp+410h+var_E0], 1
0x180029722  mov     [rbp+410h+var_D8], rax
0x180029729  lea     rax, [rbp+410h+var_1D8]
0x180029730  mov     [rbp+410h+var_D0], rax
0x180029737  mov     [rbp+410h+var_C8], r13
0x18002973e  mov     [rbp+410h+var_C0], r13
0x180029745  lea     rax, [rbp+410h+var_1E0]
0x18002974c  mov     [rbp+410h+var_B8], rax
0x180029753  mov     [rbp+410h+var_B0], r13
0x18002975a  mov     [rbp+410h+var_A8], r13d
0x180029761  lea     rax, [rbp+410h+var_1B0]
0x180029768  mov     [rbp+410h+var_A0], rax
0x18002976f  mov     [rbp+410h+var_98], 0
0x180029776  lea     rdi, ??_7ForegroundActivation@AAMTraceProvider@@6B@; const AAMTraceProvider::ForegroundActivation::`vftable'
0x18002977d  mov     [rbp+410h+var_1E0], rdi
0x180029784  mov     rax, [rbp+410h+var_470]
0x180029788  mov     [rsp+5B0h+var_588], rax; unsigned __int64
0x18002978d  mov     eax, [rbp+410h+arg_20]
0x180029793  mov     dword ptr [rsp+5B0h+ReturnLength], eax; int
0x180029797  mov     r9, [rbp+410h+var_430]; unsigned __int16 *
0x18002979b  mov     r8, [rbp+410h+var_468]; unsigned __int16 *
0x18002979f  lea     rcx, [rbp+410h+var_1E0]; this
0x1800297a6  call    ?StartActivity@ForegroundActivation@AAMTraceProvider@@QEAAX_KPEBG1K0@Z; AAMTraceProvider::ForegroundActivation::StartActivity(unsigned __int64,ushort const *,ushort const *,ulong,unsigned __int64)
0x1800297ab  nop
0x1800297ac  lea     r15, [rsi+60h]
0x1800297b0  mov     [rbp+410h+var_370], r15
0x1800297b7  mov     rcx, r15; SRWLock
0x1800297ba  call    cs:__imp_AcquireSRWLockExclusive
0x1800297c0  nop
0x1800297c1  xorps   xmm0, xmm0
0x1800297c4  xor     eax, eax
0x1800297c6  movups  xmmword ptr [rsi+98h], xmm0
0x1800297cd  movups  xmmword ptr [rsi+0A8h], xmm0
0x1800297d4  movups  xmmword ptr [rsi+0B8h], xmm0
0x1800297db  mov     [rsi+0C8h], rax
0x1800297e2  mov     rax, qword ptr cs:?s_qpcFrequency@ActivationManagerShim@Execution@@0T_LARGE_INTEGER@@A; _LARGE_INTEGER Execution::ActivationManagerShim::s_qpcFrequency ...
0x1800297e9  mov     [rsi+98h], rax
0x1800297f0  lea     rcx, [rsi+0A0h]; lpPerformanceCount
0x1800297f7  call    cs:__imp_QueryPerformanceCounter
0x1800297fd  mov     [rbp+410h+var_460], r13
0x180029801  mov     [rbp+410h+var_438], r13
0x180029805  mov     rcx, qword ptr [rbp+410h+var_408]
0x180029809  mov     rax, [rcx]
0x18002980c  lea     r8, [rbp+410h+var_438]
0x180029810  lea     rdx, _GUID_99fc44e3_ce9a_4284_bf04_76331d1b1788
  ... truncated ...
```
