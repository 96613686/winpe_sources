# ApplicationActivationImpl::ActivateApplicationForComponentUI(HSTRING__ *,HSTRING__ *,IInspectable *,uint,unsigned __int64,_GUID,void *,ulong,uchar *,ulong,ulong,ulong *,IInspectable * *)

- ea: `0x180027d50`
- end: `0x180028c0f`
- name: `?ActivateApplicationForComponentUI@ApplicationActivationImpl@@UEAAJPEAUHSTRING__@@0PEAUIInspectable@@I_KU_GUID@@PEAXKPEAEKKPEAKPEAPEAU3@@Z`
- size: `3775`
- prototype: `__int64 __fastcall(ApplicationActivationImpl *__hidden this, HSTRING, HSTRING, struct IInspectable *, unsigned int, unsigned __int64, struct _GUID *, HANDLE hSourceHandle, unsigned int, unsigned __int8 *, unsigned int, unsigned int, unsigned int *, struct IInspectable **)`
- caller_count: `0`
- callee_count: `24`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x18000b5c0`
- `0x18000cbc0`
- `0x180011328`
- `0x18001c14c`
- `0x18001f318`
- `0x180027cb8`
- `0x180027ce8`
- `0x180027d50`
- `0x180029028`
- `0x18002a380`
- `0x18002b860`
- `0x180036014`
- `0x180038c70`
- `0x180044408`
- `0x18004e098`
- `0x18004eab8`
- `0x18004ebe4`
- `0x18004f278`
- `0x18005ae90`
- `0x18005ba40`
- `0x180067e64`
- `0x180076734`
- `0x18007695c`
- `0x1800a0010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180027e3b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180027ef6`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180027f2b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180027fea`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002808f`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800283ef`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180028bdc`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180028bf2`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180028c08`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180027e3b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180027ef6`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180027f2b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180027fea`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002808f`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800283ef`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180028bdc`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180028bf2`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180028c08`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800285b4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800285bd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800285b4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800285bd`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180028812`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180028812`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18002809d`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x1800284a4`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18002809d`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x1800284a4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800287fe`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800287fe`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x1800285e1`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x1800285e1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180028693`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002873b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180028693`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002873b`
- `ntdll!RtlIsParentOfChildAppContainer` at `0x18002858c`
- `ntdll!RtlIsParentOfChildAppContainer` at `0x18002858c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002865d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002865d`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18002887c`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18002887c`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x1800287bd`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x1800287bd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002827e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800282d1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800283c1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180028669`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180028679`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180028789`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002879b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180028a82`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180028a92`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180028b49`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180028b59`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002827e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800282d1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800283c1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180028669`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180028679`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180028789`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002879b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180028a82`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180028a92`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180028b49`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180028b59`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x180028362`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x180028362`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180027e25`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180027ee0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180027f15`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180027fd4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180028078`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180027e25`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180027ee0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180027f15`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180027fd4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180028078`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002851c`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002856d`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002851c`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002856d`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18002886b`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18002886b`
- `api-ms-win-ro-typeresolution-l1-1-1!RoCreatePropertySetSerializer` at `0x180028314`
- `api-ms-win-ro-typeresolution-l1-1-1!RoCreatePropertySetSerializer` at `0x180028314`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrOpenProcessTokenForQuery` at `0x1800284b0`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrOpenProcessTokenForQuery` at `0x1800284b0`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserContext` at `0x180028947`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserContext` at `0x180028947`

## string_xrefs

- `0x180027f0e`: `Windows.Internal.ShellExperience.ComponentUI`

## pseudocode

```c
// Hidden C++ exception states: #wind=27
__int64 __fastcall ApplicationActivationImpl::ActivateApplicationForComponentUI(
        ApplicationActivationImpl *this,
        HSTRING a2,
        void **a3,
        struct IInspectable *a4,
        unsigned int a5,
        unsigned __int64 a6,
        struct _GUID *a7,
        HANDLE hSourceHandle,
        unsigned int a9,
        unsigned __int8 *a10,
        unsigned int a11,
        char a12,
        unsigned int *a13,
        struct IInspectable **a14)
{
  HANDLE v15; // r12
  unsigned int *v16; // rcx
  int CallingProcessHandle; // eax
  unsigned int LastError; // ebx
  HRESULT v19; // eax
  int v20; // eax
  unsigned __int64 v21; // rbx
  unsigned __int64 v22; // rdi
  unsigned int v23; // eax
  UINT32 v24; // edx
  HRESULT v25; // eax
  HRESULT v26; // eax
  int v27; // eax
  unsigned int v28; // edi
  unsigned __int64 v29; // rdi
  unsigned int v30; // eax
  UINT32 v31; // edx
  HRESULT v32; // eax
  __int64 v33; // r8
  int v34; // eax
  unsigned int v35; // eax
  UINT32 v36; // edx
  HRESULT v37; // eax
  char *v38; // r14
  DWORD ProcessId; // eax
  __int64 v40; // r8
  int v41; // eax
  char v42; // r15
  int v43; // eax
  int v44; // eax
  HRESULT (__stdcall *QueryInterface)(IInspectable *, const IID *const, void **); // rbx
  int v46; // eax
  __int64 v47; // rdi
  __int64 (__fastcall *v48)(__int64, struct Windows::Foundation::Collections::IPropertySet **); // rbx
  int v49; // eax
  int v50; // eax
  __int64 v51; // rcx
  int v52; // eax
  __int64 v53; // rdx
  HRESULT v54; // eax
  int v55; // eax
  __int64 v56; // rdi
  __int64 (__fastcall *v57)(__int64, __int64, struct IInspectable **); // rbx
  ApplicationActivationImpl *v58; // rcx
  int v59; // eax
  unsigned __int16 **v60; // rdx
  char *v61; // rcx
  DWORD v62; // eax
  int v63; // eax
  __int64 v64; // r9
  __int64 v65; // rdx
  const char *v66; // r9
  __int64 v67; // rdx
  HANDLE CurrentProcess; // rbx
  HANDLE v69; // rax
  unsigned int v70; // edi
  int CallingProcessAppId; // eax
  struct IApplicationActivationManagerPriv *v72; // rcx
  __int64 v73; // rcx
  struct IInspectable *v74; // rcx
  __int64 v75; // rcx
  int v76; // eax
  HRESULT v77; // eax
  __int64 v78; // r9
  __int64 v79; // rdx
  HANDLE CurrentThread; // rax
  const char *v81; // r9
  __int64 v82; // rdx
  HRESULT v83; // eax
  unsigned int v84; // r8d
  const unsigned __int16 *v85; // rdx
  int v86; // eax
  char *v87; // rax
  _DWORD *v88; // rax
  int v89; // r14d
  struct IApplicationActivationManagerPriv *v90; // rdi
  __int64 (__fastcall *v91)(struct IApplicationActivationManagerPriv *, HSTRING, void **, struct IInspectable *); // rbx
  int v92; // eax
  struct IInspectable *v94; // rax
  int ReturnLength; // [rsp+20h] [rbp-E0h]
  int ReturnLengtha; // [rsp+20h] [rbp-E0h]
  __int64 v97; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v98; // [rsp+58h] [rbp-A8h] BYREF
  HSTRING v99; // [rsp+60h] [rbp-A0h] BYREF
  HSTRING v100; // [rsp+68h] [rbp-98h] BYREF
  HANDLE TargetHandle; // [rsp+70h] [rbp-90h] BYREF
  __int64 v102; // [rsp+78h] [rbp-88h] BYREF
  struct IInspectable *v103; // [rsp+80h] [rbp-80h] BYREF
  struct IApplicationActivationManagerPriv *v104; // [rsp+88h] [rbp-78h] BYREF
  HANDLE hExistingToken; // [rsp+90h] [rbp-70h] BYREF
  LPVOID pv; // [rsp+98h] [rbp-68h] BYREF
  INT32 result; // [rsp+A0h] [rbp-60h] BYREF
  HANDLE TokenHandle; // [rsp+A8h] [rbp-58h] BYREF
  HSTRING string1; // [rsp+B0h] [rbp-50h]
  __int64 v110; // [rsp+B8h] [rbp-48h] BYREF
  struct IInspectable *v111; // [rsp+C0h] [rbp-40h] BYREF
  struct Windows::Foundation::Collections::IPropertySet *v112; // [rsp+C8h] [rbp-38h] BYREF
  HSTRING v113; // [rsp+D0h] [rbp-30h]
  HANDLE Process; // [rsp+D8h] [rbp-28h] BYREF
  DWORD v115; // [rsp+E0h] [rbp-20h] BYREF
  struct _GUID *v116; // [rsp+E8h] [rbp-18h]
  unsigned __int8 *v117; // [rsp+F0h] [rbp-10h]
  unsigned int *v118; // [rsp+F8h] [rbp-8h]
  void **v119; // [rsp+100h] [rbp+0h]
  struct IInspectable **v120; // [rsp+108h] [rbp+8h]
  _DWORD v121[2]; // [rsp+110h] [rbp+10h] BYREF
  unsigned __int8 *v122; // [rsp+118h] [rbp+18h]
  __int128 v123; // [rsp+120h] [rbp+20h]
  __int128 v124; // [rsp+130h] [rbp+30h]
  struct _GUID v125; // [rsp+140h] [rbp+40h]
  __int64 v126; // [rsp+150h] [rbp+50h]
  HSTRING_HEADER v127; // [rsp+158h] [rbp+58h] BYREF
  HSTRING v128; // [rsp+170h] [rbp+70h] BYREF
  HSTRING_HEADER v129; // [rsp+178h] [rbp+78h] BYREF
  HSTRING v130; // [rsp+190h] [rbp+90h] BYREF
  HSTRING_HEADER v131; // [rsp+198h] [rbp+98h] BYREF
  HSTRING v132; // [rsp+1B0h] [rbp+B0h] BYREF
  HSTRING_HEADER v133; // [rsp+1B8h] [rbp+B8h] BYREF
  HSTRING v134; // [rsp+1D0h] [rbp+D0h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+1D8h] [rbp+D8h] BYREF
  HSTRING string; // [rsp+1F0h] [rbp+F0h] BYREF
  char v137[24]; // [rsp+1F8h] [rbp+F8h] BYREF
  HSTRING v138; // [rsp+210h] [rbp+110h]
  char v139[24]; // [rsp+218h] [rbp+118h] BYREF
  HSTRING v140; // [rsp+230h] [rbp+130h]
  _QWORD v141[10]; // [rsp+240h] [rbp+140h] BYREF
  _QWORD TokenInformation[10]; // [rsp+290h] [rbp+190h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+328h] [rbp+228h]

  v119 = a3;
  v113 = a2;
  v116 = a7;
  v15 = hSourceHandle;
  v117 = a10;
  v16 = a13;
  v118 = a13;
  v120 = a14;
  *a14 = 0;
  *v16 = 0;
  Process = 0;
  CallingProcessHandle = UserAwareCallerIdentity::GetCallingProcessHandle(
                           (UserAwareCallerIdentity *)0x440,
                           (unsigned int)&Process,
                           a3);
  LastError = CallingProcessHandle;
  if ( CallingProcessHandle < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x231,
      (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\applicationactivationimpl.cpp",
      (const char *)(unsigned int)CallingProcessHandle,
      ReturnLength);
LABEL_148:
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&Process);
    return LastError;
  }
  v98 = 0;
  string = 0;
  v19 = WindowsCreateStringReference(L"Windows.Foundation.Collections.ValueSet", 0x27u, &hstringHeader, &string);
  if ( v19 < 0 )
  {
    RaiseException(v19, 1u, 0, 0);
    __debugbreak();
  }
  v20 = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet>>(
          string,
          &v98);
  LastError = v20;
  if ( v20 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x238,
      (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\applicationactivationimpl.cpp",
      (const char *)(unsigned int)v20,
      ReturnLength);
LABEL_147:
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v98);
    goto LABEL_148;
  }
  v97 = v98;
  if ( v98 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v98 + 8LL))(v98);
  v130 = 0;
  v21 = -1;
  v22 = -1;
  do
    ++v22;
  while ( aExperienceid[v22] );
  if ( v22 > 0xFFFFFFFF )
  {
LABEL_153:
    RaiseException(0x80070216, 1u, 0, 0);
    JUMPOUT(0x180028C0ELL);
  }
  v23 = Microsoft::WRL::Wrappers::HStringReference::AddOne(v22);
  v24 = v23 - 1;
  if ( (unsigned int)v22 < v23 )
    v24 = v22;
  v25 = WindowsCreateStringReference(L"ExperienceId", v24, &v129, &v130);
  if ( v25 < 0 )
    RaiseException(v25, 1u, 0, 0);
  v128 = 0;
  v26 = WindowsCreateStringReference(L"Windows.Internal.ShellExperience.ComponentUI", 0x2Cu, &v127, &v128);
  if ( v26 < 0 )
    RaiseException(v26, 1u, 0, 0);
  v27 = Windows::Internal::ShellHelpers::PropertySetHelper::SetValue<HSTRING__ *>(
          (Windows::Internal::ShellHelpers::PropertySetHelper *)&v97,
          v130);
  v28 = v27;
  if ( v27 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x240,
      (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\applicationactivationimpl.cpp",
      (const char *)(unsigned int)v27,
      ReturnLength);
LABEL_20:
    v128 = 0;
    v130 = 0;
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v97);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v98);
    LastError = v28;
    goto LABEL_148;
  }
  v132 = 0;
  v29 = -1;
  do
    ++v29;
  while ( c_HostViewIdPropertyKey[v29] );
  if ( v29 > 0xFFFFFFFF )
  {
LABEL_152:
    RaiseException(0x80070216, 1u, 0, 0);
    goto LABEL_153;
  }
  v30 = Microsoft::WRL::Wrappers::HStringReference::AddOne(v29);
  v31 = v30 - 1;
  if ( (unsigned int)v29 < v30 )
    v31 = v29;
  v32 = WindowsCreateStringReference(c_HostViewIdPropertyKey, v31, &v131, &v132);
  if ( v32 < 0 )
    RaiseException(v32, 1u, 0, 0);
  v34 = Windows::Internal::ShellHelpers::PropertySetHelper::SetValue<unsigned int>(&v97, v132, v33, a5);
  v28 = v34;
  if ( v34 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x244,
      (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\applicationactivationimpl.cpp",
      (const char *)(unsigned int)v34,
      ReturnLength);
    v132 = 0;
    goto LABEL_20;
  }
  v134 = 0;
  do
    ++v21;
  while ( c_HostProcessIdPropertyKey[v21] );
  if ( v21 > 0xFFFFFFFF )
  {
    RaiseException(0x80070216, 1u, 0, 0);
    goto LABEL_152;
  }
  v35 = Microsoft::WRL::Wrappers::HStringReference::AddOne(v21);
  v36 = v35 - 1;
  if ( (unsigned int)v21 < v35 )
    v36 = v21;
  v37 = WindowsCreateStringReference(c_HostProcessIdPropertyKey, v36, &v133, &v134);
  if ( v37 < 0 )
    RaiseException(v37, 1u, 0, 0);
  v38 = (char *)Process;
  ProcessId = GetProcessId(Process);
  if ( ProcessId )
  {
    v41 = Windows::Internal::ShellHelpers::PropertySetHelper::SetValue<unsigned int>(&v97, v134, v40, ProcessId);
    LastError = v41;
    if ( v41 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x24A,
        (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\applicationactivationimpl.cpp",
        (const char *)(unsigned int)v41,
        ReturnLength);
LABEL_40:
      v134 = 0;
      v132 = 0;
      v128 = 0;
      v130 = 0;
LABEL_146:
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v97);
      goto LABEL_147;
    }
  }
  v42 = a12;
  if ( (a12 & 1) != 0 )
  {
    Microsoft::WRL::Wrappers::HStringReference::HStringReference(v137, c_IsDisconnected);
    v43 = Windows::Internal::ShellHelpers::PropertySetHelper::SetValue<unsigned char>(
            (Windows::Internal::ShellHelpers::PropertySetHelper *)&v97,
            v138);
    LastError = v43;
    if ( v43 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x250,
        (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\applicationactivationimpl.cpp",
        (const char *)(unsigned int)v43,
        ReturnLength);
      v138 = 0;
      goto LABEL_40;
    }
  }
  if ( (v42 & 0x10) != 0 )
  {
    Microsoft::WRL::Wrappers::HStringReference::HStringReference(v139, &c_MakeComponentHidden);
    v44 = Windows::Internal::ShellHelpers::PropertySetHelper::SetValue<unsigned char>(
            (Windows::Internal::ShellHelpers::PropertySetHelper *)&v97,
            v140);
    LastError = v44;
    if ( v44 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x256,
        (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\applicationactivationimpl.cpp",
        (const char *)(unsigned int)v44,
        ReturnLength);
      v140 = 0;
      goto LABEL_40;
    }
  }
  if ( a4 )
  {
    v110 = 0;
    QueryInterface = a4->lpVtbl->QueryInterface;
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v110);
    v46 = ((__int64 (__fastcall *)(struct IInspectable *, GUID *, __int64 *))QueryInterface)(
            a4,
            &GUID_55bb3fd1_0ecd_4945_ab2c_60d6d1385e86,
            &v110);
    if ( v46 >= 0 )
    {
      v112 = 0;
      v47 = v110;
      v48 = *(__int64 (__fastcall **)(__int64, struct Windows::Foundation::Collections::IPropertySet **))(*(_QWORD *)v110 + 48LL);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v112);
      v49 = v48(v47, &v112);
      if ( v49 >= 0 )
      {
        string1 = 0;
        Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &c_CustomResourceSetPropertyKey);
        Windows::Internal::ShellHelpers::PropertySetHelper::PropertySetHelper(
          (Windows::Internal::ShellHelpers::PropertySetHelper *)&hExistingToken,
          v112);
        WindowsDeleteString(string1);
        string1 = 0;
        v50 = Windows::Internal::ShellHelpers::PropertySetHelper::GetValue<HSTRING__ *>(
                (Windows::Internal::ShellHelpers::PropertySetHelper *)&hExistingToken,
                string);
        if ( v50 >= 0 )
        {
          result = 0;
          v54 = WindowsCompareStringOrdinal(string1, 0, &result);
          if ( v54 < 0 )
          {
            RaiseException(v54, 1u, 0, 0);
            goto LABEL_67;
          }
          if ( result )
          {
            v55 = Windows::Internal::ShellHelpers::PropertySetHelper::SetValue<HSTRING__ *>(
                    (Windows::Internal::ShellHelpers::PropertySetHelper *)&v97,
                    string);
            LastError = v55;
            if ( v55 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x267,
                (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\applicationactivationimpl.cpp",
                (const char *)(unsigned int)v55,
                ReturnLength);
              Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&hExistingToken);
              string = 0;
              WindowsDeleteString(string1);
              string1 = 0;
              Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v112);
              Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v110);
              goto LABEL_40;
            }
          }
        }
        else
        {
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x265,
            (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\applicationactivationimpl.cpp",
            (const char *)(unsigned int)v50,
            ReturnLength);
        }
        Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&hExistingToken);
        string = 0;
        WindowsDeleteString(string1);
      }
      else
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x260,
          (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\applicationactivationimpl.cpp",
          (const char *)(unsigned int)v49,
          ReturnLength);
      }
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v112);
    }
    else
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x25D,
        (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\applicationactivationimpl.cpp",
        (const char *)(unsigned int)v46,
        ReturnLength);
    }
    v51 = v110;
    if ( v110 )
    {
      v110 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v51 + 16LL))(v51);
    }
  }
  v103 = 0;
  v102 = 0;
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v102);
  v52 = RoCreatePropertySetSerializer(&v102);
  LastError = v52;
  if ( v52 < 0 )
  {
    v53 = 624;
LABEL_60:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v53,
      (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\applicationactivationimpl.cpp",
      (const char *)(unsigned int)v52,
      ReturnLength);
LABEL_61:
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v102);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v103);
    goto LABEL_40;
  }
LABEL_67:
  v56 = v102;
  v57 = *(__int64 (__fastcall **)(__int64, __int64, struct IInspectable **))(*(_QWORD *)v102 + 48LL);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v103);
  v52 = v57(v56, v98, &v103);
  LastError = v52;
  if ( v52 < 0 )
  {
    v53 = 625;
    goto LABEL_60;
  }
  v104 = 0;
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v104);
  v59 = ApplicationActivationImpl::CreateActivationManagerAndSetInfo(v58, 0, 0, v103, &v104);
  LastError = v59;
  if ( v59 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x276,
      (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\applicationactivationimpl.cpp",
      (const char *)(unsigned int)v59,
      ReturnLengtha);
LABEL_71:
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v104);
    goto LABEL_61;
  }
  v61 = 0;
  TargetHandle = 0;
  if ( v15 )
  {
    TokenHandle = 0;
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      &TokenHandle,
      0);
    v62 = GetProcessId(v38);
    v63 = UMgrOpenProcessTokenForQuery(v62, &TokenHandle);
    LastError = v63;
    if ( v63 < 0 )
    {
      v64 = (unsigned int)v63;
      v65 = 637;
LABEL_75:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v65,
        (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\applicationactivationimpl.cpp",
        (const char *)v64,
        ReturnLengtha);
LABEL_76:
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
LABEL_77:
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TargetHandle);
      goto LABEL_71;
    }
    memset_0(TokenInformation, 0, 0x4Cu);
    result = 76;
    if ( !GetTokenInformation(TokenHandle, TokenAppContainerSid, TokenInformation, 0x4Cu, (PDWORD)&result) )
    {
      v67 = 640;
LABEL_80:
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)v67,
                    (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\applicationactivationimpl.cpp",
                    v66);
      goto LABEL_76;
    }
    memset_0(v141, 0, 0x4Cu);
    v115 = 76;
    if ( !GetTokenInformation(v15, TokenAppContainerSid, v141, 0x4Cu, &v115) )
    {
      v67 = 645;
      goto LABEL_80;
    }
    if ( !(unsigned __int8)RtlIsParentOfChildAppContainer(TokenInformation[0], v141[0]) )
    {
      LastError = -2147024891;
      v64 = 2147942405LL;
      v65 = 648;
      goto LABEL_75;
    }
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      &TargetHandle,
      0);
    CurrentProcess = GetCurrentProcess();
    v69 = GetCurrentProcess();
    if ( !DuplicateHandle(v69, v15, CurrentProcess, &TargetHandle, 0, 0, 2u) )
    {
      v67 = 650;
      goto LABEL_80;
    }
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
    v61 = (char *)TargetHandle;
  }
  v99 = 0;
  v100 = 0;
  v70 = a11;
  if ( a11 - 1 <= 3 )
  {
    pv = 0;
    CallingProcessAppId = UserAwareCallerIdentity::GetCallingProcessAppId((UserAwareCallerIdentity *)&pv, v60);
    LastError = CallingProcessAppId;
    if ( CallingProcessAppId < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x296,
        (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\applicationactivationimpl.cpp",
        (const char *)(unsigned int)CallingProcessAppId,
        ReturnLengtha);
      if ( pv )
        CoTaskMemFree(pv);
      WindowsDeleteString(v100);
      v100 = 0;
      WindowsDeleteString(v99);
      v99 = 0;
      if ( (char *)TargetHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        CloseHandle(TargetHandle);
      v72 = v104;
      if ( v104 )
      {
        v104 = 0;
        (*(void (__fastcall **)(struct IApplicationActivationManagerPriv *))(*(_QWORD *)v72 + 16LL))(v72);
      }
      v73 = v102;
      if ( v102 )
      {
        v102 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v73 + 16LL))(v73);
      }
      v74 = v103;
      if ( v103 )
      {
        v103 = 0;
        ((void (__fastcall *)(struct IInspectable *))v74->lpVtbl->Release)(v74);
      }
      v134 = 0;
      v132 = 0;
      v128 = 0;
      v130 = 0;
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v97);
      v75 = v98;
      if ( v98 )
      {
        v98 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v75 + 16LL))(v75);
      }
      if ( (unsigned __int64)(v38 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
        CloseHandle(v38);
      return LastError;
    }
    v113 = (HSTRING)pv;
    v76 = Microsoft::WRL::Wrappers::HString::Set<unsigned short *>(&v100);
    LastError = v76;
    if ( v76 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x297,
        (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\applicationactivationimpl.cpp",
        (const char *)(unsigned int)v76,
        ReturnLengtha);
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&pv);
      WindowsDeleteString(v100);
      v100 = 0;
      WindowsDeleteString(v99);
      v99 = 0;
      goto LABEL_77;
    }
    v113 = v100;
    if ( !v15 )
    {
      v77 = CoImpersonateClient();
      LastError = v77;
      if ( v77 < 0 )
      {
        v78 = (unsigned int)v77;
        v79 = 669;
LABEL_109:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v79,
          (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\applicationactivationimpl.cpp",
          (const char *)v78,
          ReturnLengtha);
LABEL_110:
        wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&pv);
LABEL_145:
        WindowsDeleteString(v100);
        v100 = 0;
        WindowsDeleteString(v99);
        v99 = 0;
        wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TargetHandle);
        Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v104);
        Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v102);
        Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v103);
        v134 = 0;
        v132 = 0;
        v128 = 0;
        v130 = 0;
        goto LABEL_146;
      }
      hExistingToken = 0;
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
        &hExistingToken,
        0);
      CurrentThread = GetCurrentThread();
      if ( !OpenThreadToken(CurrentThread, 0xEu, 0, &hExistingToken) )
      {
        v82 = 671;
LABEL_113:
        LastError = wil::details::in1diag3::Return_GetLastError(
                      retaddr,
                      (void *)v82,
                      (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\applicationactivationimpl.cpp",
                      v81);
LABEL_114:
        wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hExistingToken);
        goto LABEL_110;
      }
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
        &TargetHandle,
        0);
      if ( !DuplicateTokenEx(hExistingToken, 0x2000000u, 0, SecurityImpersonation, TokenImpersonation, &TargetHandle) )
      {
        v82 = 672;
        goto LABEL_113;
      }
      v83 = CoRevertToSelf();
      LastError = v83;
      if ( v83 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x2A1,
          (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\applicationactivationimpl.cpp",
          (const char *)(unsigned int)v83,
          ReturnLengtha);
        goto LABEL_114;
      }
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hExistingToken);
    }
    switch ( v70 )
    {
      case 1u:
        v84 = 35;
        v85 = L"Windows.Internal.WebView.OopWebView";
        break;
      case 2u:
        v84 = 42;
        v85 = L"Windows.Internal.WebRuntime.ContentProcess";
        break;
      case 3u:
        v84 = 34;
        v85 = L"Windows.Internal.WebRuntime.BCHost";
        break;
      case 4u:
        v84 = 31;
        v85 = L"Windows.Internal.WebRuntime.F12";
        break;
      default:
        LastError = -2147024809;
        v78 = 2147942487LL;
        v79 = 691;
        goto LABEL_109;
    }
    Microsoft::WRL::Wrappers::HString::Set((Microsoft::WRL::Wrappers::HString *)&v99, v85, v84);
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&pv);
    v61 = (char *)TargetHandle;
  }
  if ( (unsigned __int64)(v61 - 1) <= 0xFFFFFFFFFFFFFFFDuLL && !a6 )
  {
    v86 = UMgrQueryUserContext(v61, &a6);
    LastError = v86;
    if ( v86 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2B8,
        (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\applicationactivationimpl.cpp",
        (const char *)(unsigned int)v86,
        ReturnLengtha);
      goto LABEL_145;
    }
    v61 = (char *)TargetHandle;
  }
  v126 = 0;
  v123 = (unsigned __int64)v61;
  v124 = (unsigned __int64)v99;
  v125 = *v116;
  LODWORD(v126) = v70;
  v87 = 0;
  if ( (v42 & 2) != 0 )
    v87 = v38;
  *((_QWORD *)&v123 + 1) = v87;
  v121[0] = a9;
  v121[1] = 0;
  v122 = v117;
  v88 = v121;
  if ( !a9 )
    v88 = (_DWORD *)*((_QWORD *)&v124 + 1);
  *((_QWORD *)&v124 + 1) = v88;
  if ( (v42 & 4) != 0 )
  {
    v89 = 0x2000;
  }
  else
  {
    v89 = 0;
    if ( (v42 & 8) != 0 )
      v89 = 4096;
  }
  v111 = 0;
  v90 = v104;
  v91 = *(__int64 (__fastcall **)(struct IApplicationActivationManagerPriv *, HSTRING, void **, struct IInspectable *))(*(_QWORD *)v104 + 184LL);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v111);
  v92 = v91(v90, v113, v119, a4);
  LastError = v92;
  if ( v92 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2E5,
      (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\applicationactivationimpl.cpp",
      (const char *)(unsigned int)v92,
      v89);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v111);
    goto LABEL_145;
  }
  v94 = v111;
  v111 = 0;
  *v120 = v94;
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v111);
  WindowsDeleteString(v100);
  v100 = 0;
  WindowsDeleteString(v99);
  v99 = 0;
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TargetHandle);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v104);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v102);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v103);
  v134 = 0;
  v132 = 0;
  v128 = 0;
  v130 = 0;
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v97);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v98);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&Process);
  return 0;
}

```

## disassembly

```asm
0x180027d50  mov     [rsp-8+arg_0], rbx
0x180027d55  push    rbp
0x180027d56  push    rsi
0x180027d57  push    rdi
0x180027d58  push    r12
0x180027d5a  push    r13
0x180027d5c  push    r14
0x180027d5e  push    r15
0x180027d60  lea     rbp, [rsp-1F0h]
0x180027d68  sub     rsp, 2F0h
0x180027d6f  mov     rax, cs:__security_cookie
0x180027d76  xor     rax, rsp
0x180027d79  mov     [rbp+220h+var_40], rax
0x180027d80  mov     r13, r9
0x180027d83  mov     [rbp+220h+var_220], r8
0x180027d87  mov     [rbp+220h+var_250], rdx
0x180027d8b  mov     rax, [rbp+220h+arg_30]
0x180027d92  mov     [rbp+220h+var_238], rax
0x180027d96  mov     r12, [rbp+220h+hSourceHandle]
0x180027d9d  mov     rax, [rbp+220h+arg_48]
0x180027da4  mov     [rbp+220h+var_230], rax
0x180027da8  mov     rcx, [rbp+220h+arg_60]
0x180027daf  mov     [rbp+220h+var_228], rcx
0x180027db3  mov     rax, [rbp+220h+arg_68]
0x180027dba  mov     [rbp+220h+var_218], rax
0x180027dbe  xor     r14d, r14d
0x180027dc1  mov     [rax], r14
0x180027dc4  mov     [rcx], r14d
0x180027dc7  mov     [rbp+220h+Process], r14
0x180027dcb  lea     rdx, [rbp+220h+Process]; unsigned int
0x180027dcf  mov     ecx, 440h; this
0x180027dd4  call    ?GetCallingProcessHandle@UserAwareCallerIdentity@@YAJKPEAPEAX@Z; UserAwareCallerIdentity::GetCallingProcessHandle(ulong,void * *)
0x180027dd9  mov     ebx, eax
0x180027ddb  test    eax, eax
0x180027ddd  jns     short loc_180027DFF
0x180027ddf  mov     rcx, [rbp+228h]; this
0x180027de6  mov     r9d, eax; char *
0x180027de9  lea     r8, aOnecoreuapBase_12; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x180027df0  mov     edx, 231h; void *
0x180027df5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180027dfa  jmp     loc_180028AF6
0x180027dff  mov     [rsp+320h+var_2C8], r14
0x180027e04  mov     [rbp+220h+string], r14
0x180027e0b  lea     r9, [rbp+220h+string]; string
0x180027e12  lea     r8, [rbp+220h+hstringHeader]; hstringHeader
0x180027e19  mov     edx, 27h ; '''; length
0x180027e1e  lea     rcx, ?RuntimeClass_Windows_Foundation_Collections_ValueSet@@3QBGB; "Windows.Foundation.Collections.ValueSet"
0x180027e25  call    cs:__imp_WindowsCreateStringReference
0x180027e2b  test    eax, eax
0x180027e2d  jns     short loc_180027E42
0x180027e2f  xor     r9d, r9d; lpArguments
0x180027e32  xor     r8d, r8d; nNumberOfArguments
0x180027e35  lea     edx, [r9+1]; dwExceptionFlags
0x180027e39  mov     ecx, eax; dwExceptionCode
0x180027e3b  call    cs:__imp_RaiseException
0x180027e41  int     3; Trap to Debugger
0x180027e42  lea     rdx, [rsp+320h+var_2C8]
0x180027e47  mov     rcx, [rbp+220h+string]
0x180027e4e  call    ??$ActivateInstance@V?$ComPtr@UIPropertySet@Collections@Foundation@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIPropertySet@Collections@Foundation@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet>>)
0x180027e53  mov     ebx, eax
0x180027e55  test    eax, eax
0x180027e57  jns     short loc_180027E79
0x180027e59  mov     rcx, [rbp+228h]; this
0x180027e60  mov     r9d, eax; char *
0x180027e63  lea     r8, aOnecoreuapBase_12; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x180027e6a  mov     edx, 238h; void *
0x180027e6f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180027e74  jmp     loc_180028AEB
0x180027e79  mov     rcx, [rsp+320h+var_2C8]
0x180027e7e  mov     [rsp+320h+var_2D0], rcx
0x180027e83  test    rcx, rcx
0x180027e86  jz      short loc_180027E95
0x180027e88  mov     rax, [rcx]
0x180027e8b  mov     rax, [rax+8]
0x180027e8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027e94  nop
0x180027e95  mov     [rbp+220h+var_190], r14
0x180027e9c  mov     rsi, cs:off_1800A14E0; "ExperienceId"
0x180027ea3  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180027ea7  mov     rdi, rbx
0x180027eaa  inc     rdi
0x180027ead  cmp     [rsi+rdi*2], r14w
0x180027eb2  jnz     short loc_180027EAA
0x180027eb4  mov     r15d, 0FFFFFFFFh
0x180027eba  cmp     rdi, r15
0x180027ebd  ja      loc_180028BF9
0x180027ec3  mov     ecx, edi; unsigned int
0x180027ec5  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x180027eca  lea     edx, [rax-1]
0x180027ecd  cmp     edi, eax
0x180027ecf  cmovb   edx, edi; length
0x180027ed2  lea     r9, [rbp+220h+var_190]; string
0x180027ed9  lea     r8, [rbp+220h+var_1A8]; hstringHeader
0x180027edd  mov     rcx, rsi; sourceString
0x180027ee0  call    cs:__imp_WindowsCreateStringReference
0x180027ee6  test    eax, eax
0x180027ee8  jns     short loc_180027EFD
0x180027eea  xor     r9d, r9d; lpArguments
0x180027eed  xor     r8d, r8d; nNumberOfArguments
0x180027ef0  lea     edx, [r9+1]; dwExceptionFlags
0x180027ef4  mov     ecx, eax; dwExceptionCode
0x180027ef6  call    cs:__imp_RaiseException
0x180027efc  nop
0x180027efd  mov     [rbp+220h+var_1B0], r14
0x180027f01  lea     r9, [rbp+220h+var_1B0]; string
0x180027f05  lea     r8, [rbp+220h+var_1C8]; hstringHeader
0x180027f09  mov     edx, 2Ch ; ','; length
0x180027f0e  lea     rcx, aWindowsInterna_0; "Windows.Internal.ShellExperience.Compon"...
0x180027f15  call    cs:__imp_WindowsCreateStringReference
0x180027f1b  test    eax, eax
0x180027f1d  jns     short loc_180027F32
0x180027f1f  xor     r9d, r9d; lpArguments
0x180027f22  xor     r8d, r8d; nNumberOfArguments
0x180027f25  lea     edx, [r9+1]; dwExceptionFlags
0x180027f29  mov     ecx, eax; dwExceptionCode
0x180027f2b  call    cs:__imp_RaiseException
0x180027f31  nop
0x180027f32  mov     r9, [rbp+220h+var_1B0]
0x180027f36  mov     rdx, [rbp+220h+var_190]; HSTRING
0x180027f3d  lea     rcx, [rsp+320h+var_2D0]; this
0x180027f42  call    ??$SetValue@PEAUHSTRING__@@@PropertySetHelper@ShellHelpers@Internal@Windows@@AEAAJPEAUHSTRING__@@P8IPropertyValueStatics@Foundation@3@EAAJ0PEAPEAUIInspectable@@@Z0@Z; Windows::Internal::ShellHelpers::PropertySetHelper::SetValue<HSTRING__ *>(HSTRING__ *,long (Windows::Foundation::IPropertyValueStatics::*)(HSTRING__ *,IInspectable * *),HSTRING__ *)
0x180027f47  mov     edi, eax
0x180027f49  test    eax, eax
0x180027f4b  jns     short loc_180027F90
0x180027f4d  mov     rcx, [rbp+228h]; this
0x180027f54  mov     r9d, eax; char *
0x180027f57  lea     r8, aOnecoreuapBase_12; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x180027f5e  mov     edx, 240h; void *
0x180027f63  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180027f68  nop
0x180027f69  mov     [rbp+220h+var_1B0], r14
0x180027f6d  mov     [rbp+220h+var_190], r14
0x180027f74  lea     rcx, [rsp+320h+var_2D0]
0x180027f79  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180027f7e  nop
0x180027f7f  lea     rcx, [rsp+320h+var_2C8]
0x180027f84  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180027f89  mov     ebx, edi
0x180027f8b  jmp     loc_180028AF6
0x180027f90  mov     [rbp+220h+var_170], r14
0x180027f97  mov     rsi, cs:c_HostViewIdPropertyKey
0x180027f9e  mov     rdi, rbx
0x180027fa1  inc     rdi
0x180027fa4  cmp     [rsi+rdi*2], r14w
0x180027fa9  jnz     short loc_180027FA1
0x180027fab  cmp     rdi, r15
0x180027fae  ja      loc_180028BE3
0x180027fb4  mov     ecx, edi; unsigned int
0x180027fb6  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x180027fbb  lea     edx, [rax-1]
0x180027fbe  cmp     edi, eax
0x180027fc0  cmovb   edx, edi; length
0x180027fc3  lea     r9, [rbp+220h+var_170]; string
0x180027fca  lea     r8, [rbp+220h+var_188]; hstringHeader
0x180027fd1  mov     rcx, rsi; sourceString
0x180027fd4  call    cs:__imp_WindowsCreateStringReference
0x180027fda  test    eax, eax
0x180027fdc  jns     short loc_180027FF1
0x180027fde  xor     r9d, r9d; lpArguments
0x180027fe1  xor     r8d, r8d; nNumberOfArguments
0x180027fe4  lea     edx, [r9+1]; dwExceptionFlags
0x180027fe8  mov     ecx, eax; dwExceptionCode
0x180027fea  call    cs:__imp_RaiseException
0x180027ff0  nop
0x180027ff1  mov     r9d, [rbp+220h+arg_20]
0x180027ff8  mov     rdx, [rbp+220h+var_170]
0x180027fff  lea     rcx, [rsp+320h+var_2D0]
0x180028004  call    ??$SetValue@I@PropertySetHelper@ShellHelpers@Internal@Windows@@AEAAJPEAUHSTRING__@@P8IPropertyValueStatics@Foundation@3@EAAJIPEAPEAUIInspectable@@@ZI@Z; Windows::Internal::ShellHelpers::PropertySetHelper::SetValue<uint>(HSTRING__ *,long (Windows::Foundation::IPropertyValueStatics::*)(uint,IInspectable * *),uint)
0x180028009  mov     edi, eax
0x18002800b  test    eax, eax
0x18002800d  jns     short loc_180028037
0x18002800f  mov     rcx, [rbp+228h]; this
0x180028016  mov     r9d, eax; char *
0x180028019  lea     r8, aOnecoreuapBase_12; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x180028020  mov     edx, 244h; void *
0x180028025  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002802a  nop
0x18002802b  mov     [rbp+220h+var_170], r14
0x180028032  jmp     loc_180027F69
0x180028037  mov     [rbp+220h+var_150], r14
0x18002803e  mov     rdi, cs:c_HostProcessIdPropertyKey
0x180028045  inc     rbx
0x180028048  cmp     [rdi+rbx*2], r14w
0x18002804d  jnz     short loc_180028045
0x18002804f  cmp     rbx, r15
0x180028052  ja      loc_180028BCD
0x180028058  mov     ecx, ebx; unsigned int
0x18002805a  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x18002805f  lea     edx, [rax-1]
0x180028062  cmp     ebx, eax
0x180028064  cmovb   edx, ebx; length
0x180028067  lea     r9, [rbp+220h+var_150]; string
0x18002806e  lea     r8, [rbp+220h+var_168]; hstringHeader
0x180028075  mov     rcx, rdi; sourceString
0x180028078  call    cs:__imp_WindowsCreateStringReference
0x18002807e  xor     edi, edi
0x180028080  test    eax, eax
0x180028082  jns     short loc_180028096
0x180028084  xor     r9d, r9d; lpArguments
0x180028087  xor     r8d, r8d; nNumberOfArguments
0x18002808a  lea     edx, [rdi+1]; dwExceptionFlags
0x18002808d  mov     ecx, eax; dwExceptionCode
0x18002808f  call    cs:__imp_RaiseException
0x180028095  nop
0x180028096  mov     r14, [rbp+220h+Process]
0x18002809a  mov     rcx, r14; Process
0x18002809d  call    cs:__imp_GetProcessId
0x1800280a3  test    eax, eax
0x1800280a5  jz      short loc_1800280FB
0x1800280a7  mov     r9d, eax
0x1800280aa  mov     rdx, [rbp+220h+var_150]
0x1800280b1  lea     rcx, [rsp+320h+var_2D0]
0x1800280b6  call    ??$SetValue@I@PropertySetHelper@ShellHelpers@Internal@Windows@@AEAAJPEAUHSTRING__@@P8IPropertyValueStatics@Foundation@3@EAAJIPEAPEAUIInspectable@@@ZI@Z; Windows::Internal::ShellHelpers::PropertySetHelper::SetValue<uint>(HSTRING__ *,long (Windows::Foundation::IPropertyValueStatics::*)(uint,IInspectable * *),uint)
0x1800280bb  mov     ebx, eax
0x1800280bd  test    eax, eax
0x1800280bf  jns     short loc_1800280FB
0x1800280c1  mov     rcx, [rbp+228h]; this
0x1800280c8  mov     r9d, eax; char *
0x1800280cb  lea     r8, aOnecoreuapBase_12; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x1800280d2  mov     edx, 24Ah; void *
0x1800280d7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800280dc  nop
0x1800280dd  mov     [rbp+220h+var_150], rdi
0x1800280e4  mov     [rbp+220h+var_170], rdi
0x1800280eb  mov     [rbp+220h+var_1B0], rdi
0x1800280ef  mov     [rbp+220h+var_190], rdi
0x1800280f6  jmp     loc_180028AE0
0x1800280fb  mov     r15d, dword ptr [rbp+220h+arg_58]
0x180028102  test    r15b, 1
0x180028106  jz      short loc_180028158
0x180028108  lea     rdx, c_IsDisconnected
0x18002810f  lea     rcx, [rbp+220h+var_128]
0x180028116  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18002811b  nop
0x18002811c  mov     rdx, [rbp+220h+var_110]; HSTRING
0x180028123  lea     rcx, [rsp+320h+var_2D0]; this
0x180028128  call    ??$SetValue@E@PropertySetHelper@ShellHelpers@Internal@Windows@@AEAAJPEAUHSTRING__@@P8IPropertyValueStatics@Foundation@3@EAAJEPEAPEAUIInspectable@@@ZE@Z; Windows::Internal::ShellHelpers::PropertySetHelper::SetValue<uchar>(HSTRING__ *,long (Windows::Foundation::IPropertyValueStatics::*)(uchar,IInspectable * *),uchar)
0x18002812d  mov     ebx, eax
0x18002812f  test    eax, eax
0x180028131  jns     short loc_180028158
0x180028133  mov     rcx, [rbp+228h]; this
0x18002813a  mov     r9d, eax; char *
0x18002813d  lea     r8, aOnecoreuapBase_12; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x180028144  mov     edx, 250h; void *
0x180028149  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002814e  nop
0x18002814f  mov     [rbp+220h+var_110], rdi
0x180028156  jmp     short loc_1800280DD
0x180028158  test    r15b, 10h
0x18002815c  jz      short loc_1800281B1
0x18002815e  lea     rdx, c_MakeComponentHidden
0x180028165  lea     rcx, [rbp+220h+var_108]
0x18002816c  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180028171  nop
0x180028172  mov     rdx, [rbp+220h+var_F0]; HSTRING
0x180028179  lea     rcx, [rsp+320h+var_2D0]; this
0x18002817e  call    ??$SetValue@E@PropertySetHelper@ShellHelpers@Internal@Windows@@AEAAJPEAUHSTRING__@@P8IPropertyValueStatics@Foundation@3@EAAJEPEAPEAUIInspectable@@@ZE@Z; Windows::Internal::ShellHelpers::PropertySetHelper::SetValue<uchar>(HSTRING__ *,long (Windows::Foundation::IPropertyValueStatics::*)(uchar,IInspectable * *),uchar)
0x180028183  mov     ebx, eax
0x180028185  test    eax, eax
0x180028187  jns     short loc_1800281B1
0x180028189  mov     rcx, [rbp+228h]; this
0x180028190  mov     r9d, eax; char *
0x180028193  lea     r8, aOnecoreuapBase_12; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x18002819a  mov     edx, 256h; void *
0x18002819f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800281a4  nop
0x1800281a5  mov     [rbp+220h+var_F0], rdi
0x1800281ac  jmp     loc_1800280DD
0x1800281b1  lea     rsi, aOnecoreuapBase_12; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x1800281b8  test    r13, r13
0x1800281bb  jz      loc_1800282FC
0x1800281c1  mov     [rbp+220h+var_268], rdi
0x1800281c5  mov     rax, [r13+0]
0x1800281c9  mov     rbx, [rax]
0x1800281cc  lea     rcx, [rbp+220h+var_268]
0x1800281d0  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800281d5  lea     r8, [rbp+220h+var_268]
0x1800281d9  lea     rdx, _GUID_55bb3fd1_0ecd_4945_ab2c_60d6d1385e86
0x1800281e0  mov     rcx, r13
0x1800281e3  mov     rax, rbx
0x1800281e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800281eb  mov     rcx, [rbp+228h]; this
0x1800281f2  test    eax, eax
0x1800281f4  jns     short loc_18002820B
0x1800281f6  mov     r9d, eax; char *
0x1800281f9  mov     r8, rsi; unsigned int
0x1800281fc  mov     edx, 25Dh; void *
0x180028201  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180028206  jmp     loc_1800282E2
0x18002820b  mov     [rbp+220h+var_258], rdi
0x18002820f  mov     rdi, [rbp+220h+var_268]
0x180028213  mov     rax, [rdi]
0x180028216  mov     rbx, [rax+30h]
0x18002821a  lea     rcx, [rbp+220h+var_258]
0x18002821e  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180028223  lea     rdx, [rbp+220h+var_258]
0x180028227  mov     rcx, rdi
0x18002822a  mov     rax, rbx
0x18002822d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028232  mov     rcx, [rbp+228h]; this
  ... truncated ...
```
