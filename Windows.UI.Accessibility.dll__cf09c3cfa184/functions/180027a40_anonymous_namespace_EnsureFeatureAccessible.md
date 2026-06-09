# _anonymous_namespace_::EnsureFeatureAccessible

- ea: `0x180027a40`
- end: `0x180027bf9`
- name: `_anonymous_namespace_::EnsureFeatureAccessible`
- size: `441`
- prototype: ``
- caller_count: `3`
- callee_count: `15`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180027990`
- `0x1800281bc`
- `0x18002e55c`

## callees

- `0x180003980`
- `0x1800050da`
- `0x180007e64`
- `0x18000df9c`
- `0x18000dfc0`
- `0x1800203ac`
- `0x180024334`
- `0x180026854`
- `0x180026934`
- `0x1800269c4`
- `0x180026a54`
- `0x180026c1c`
- `0x180027660`
- `0x180027a40`
- `0x180035010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180027a6d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180027a6d`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180027a7d`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180027a7d`
- `api-ms-win-core-psapi-l1-1-0!K32GetModuleBaseNameW` at `0x180027aa1`
- `api-ms-win-core-psapi-l1-1-0!K32GetModuleBaseNameW` at `0x180027aa1`

## string_xrefs

- `0x180027b07`: `com.microsoft.windows.focussessionmanager.1`
- `0x180027bc6`: `Feature com.microsoft.windows.focussessionmanager.1 is not available`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall anonymous_namespace_::EnsureFeatureAccessible(__int64 a1)
{
  bool v1; // di
  DWORD CurrentProcessId; // eax
  char *v3; // rax
  WCHAR *v4; // rbx
  __int64 v5; // rcx
  unsigned int v6; // eax
  const struct winrt::impl::slim_source_location *v8; // rbx
  int v9; // [rsp+20h] [rbp-E0h] BYREF
  WCHAR *v10; // [rsp+28h] [rbp-D8h] BYREF
  WCHAR *v11; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v12; // [rsp+38h] [rbp-C8h] BYREF
  char *v13; // [rsp+40h] [rbp-C0h] BYREF
  int pExceptionObject; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v15; // [rsp+50h] [rbp-B0h]
  _QWORD v16[4]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v17[32]; // [rsp+80h] [rbp-80h] BYREF
  WCHAR BaseName[64]; // [rsp+A0h] [rbp-60h] BYREF

  v12 = a1;
  v1 = 0;
  CurrentProcessId = GetCurrentProcessId();
  v3 = (char *)OpenProcess(0x410u, 0, CurrentProcessId);
  v13 = v3;
  if ( (unsigned __int64)(v3 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    v1 = K32GetModuleBaseNameW(v3, 0, BaseName, 0x40u) != 0;
  v4 = BaseName;
  if ( !v1 )
    v4 = L"Unknown process name";
  v10 = v4;
  winrt::Windows::Internal::Shell::implementation::FocusSessionTelemetry::FocusStartOrEndAPIAccessRequested<unsigned short const *,unsigned short const * &>(
    &v10,
    &v12);
  _InterlockedIncrement64(&qword_180046D68);
  if ( winrt::impl::factory_cache_entry_v<winrt::Windows::ApplicationModel::LimitedAccessFeatures,winrt::Windows::ApplicationModel::InternalApi::ILimitedAccessFeaturesInternal> )
  {
    _lambda_c098c4d09b8d941208075d7422bf37c2_::operator()<winrt::Windows::ApplicationModel::InternalApi::ILimitedAccessFeaturesInternal const &>(
      v5,
      &v10);
    _InterlockedDecrement64(&qword_180046D68);
  }
  else
  {
    _InterlockedDecrement64(&qword_180046D68);
    winrt::impl::factory_cache_entry<winrt::Windows::ApplicationModel::LimitedAccessFeatures,winrt::Windows::ApplicationModel::InternalApi::ILimitedAccessFeaturesInternal>::call<_lambda_c098c4d09b8d941208075d7422bf37c2_ &>(
      v5,
      &v10);
  }
  winrt::param::hstring::hstring((winrt::param::hstring *)v16, L"com.microsoft.windows.focussessionmanager.1");
  v9 = 0;
  pExceptionObject = 0;
  v15 = 0;
  v6 = (*(__int64 (__fastcall **)(WCHAR *, _QWORD, int *))(*(_QWORD *)v10 + 56LL))(v10, v16[0], &v9);
  winrt::check_hresult(&v11, v6, &pExceptionObject);
  v11 = v4;
  if ( (unsigned int)(v9 - 1) > 1 )
  {
    winrt::Windows::Internal::Shell::implementation::FocusSessionTelemetry::FocusStartOrEndAPIAccessDenied<unsigned short const *,unsigned short const * &>(
      &v11,
      &v12);
    v8 = (const struct winrt::impl::slim_source_location *)winrt::impl::slim_source_location::current(v16);
    winrt::param::hstring::hstring(
      (winrt::param::hstring *)v17,
      L"Feature com.microsoft.windows.focussessionmanager.1 is not available");
    winrt::hresult_access_denied::hresult_access_denied(
      (winrt::hresult_access_denied *)&pExceptionObject,
      (const struct winrt::param::hstring *)v17,
      v8);
    throw (winrt::hresult_access_denied *)&pExceptionObject;
  }
  winrt::Windows::Internal::Shell::implementation::FocusSessionTelemetry::FocusStartOrEndAPIAccessApproved<unsigned short const *,unsigned short const * &>(
    &v11,
    &v12);
  winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(&v10);
  return wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v13);
}

```

## disassembly

```asm
0x180027a40  mov     [rsp-8+arg_8], rbx
0x180027a45  mov     [rsp-8+arg_10], rdi
0x180027a4a  push    rbp
0x180027a4b  lea     rbp, [rsp-30h]
0x180027a50  sub     rsp, 130h
0x180027a57  mov     rax, cs:__security_cookie
0x180027a5e  xor     rax, rsp
0x180027a61  mov     [rbp+30h+var_10], rax
0x180027a65  mov     [rsp+130h+var_F8], rcx
0x180027a6a  xor     dil, dil
0x180027a6d  call    cs:__imp_GetCurrentProcessId
0x180027a73  mov     r8d, eax; dwProcessId
0x180027a76  xor     edx, edx; bInheritHandle
0x180027a78  mov     ecx, 410h; dwDesiredAccess
0x180027a7d  call    cs:__imp_OpenProcess
0x180027a83  mov     [rsp+130h+var_F0], rax
0x180027a88  lea     rcx, [rax-1]
0x180027a8c  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x180027a90  ja      short loc_180027AAD
0x180027a92  mov     r9d, 40h ; '@'; nSize
0x180027a98  lea     r8, [rbp+30h+BaseName]; lpBaseName
0x180027a9c  xor     edx, edx; hModule
0x180027a9e  mov     rcx, rax; hProcess
0x180027aa1  call    cs:__imp_K32GetModuleBaseNameW
0x180027aa7  test    eax, eax
0x180027aa9  setnz   dil
0x180027aad  lea     rax, aUnknownProcess; "Unknown process name"
0x180027ab4  lea     rbx, [rbp+30h+BaseName]
0x180027ab8  test    dil, dil
0x180027abb  cmovz   rbx, rax
0x180027abf  mov     [rsp+130h+var_108], rbx
0x180027ac4  lea     rdx, [rsp+130h+var_F8]
0x180027ac9  lea     rcx, [rsp+130h+var_108]
0x180027ace  call    ??$FocusStartOrEndAPIAccessRequested@PEBGAEAPEBG@FocusSessionTelemetry@implementation@Shell@Internal@Windows@winrt@@SAX$$QEAPEBGAEAPEBG@Z; winrt::Windows::Internal::Shell::implementation::FocusSessionTelemetry::FocusStartOrEndAPIAccessRequested<ushort const *,ushort const * &>(ushort const * &&,ushort const * &)
0x180027ad3  lock inc cs:qword_180046D68
0x180027adb  lea     rdx, [rsp+130h+var_108]
0x180027ae0  cmp     cs:??$factory_cache_entry_v@ULimitedAccessFeatures@ApplicationModel@Windows@winrt@@UILimitedAccessFeaturesInternal@InternalApi@234@@impl@winrt@@3U?$factory_cache_entry@ULimitedAccessFeatures@ApplicationModel@Windows@winrt@@UILimitedAccessFeaturesInternal@InternalApi@234@@12@A, 0; factory_cache_entry<winrt::Windows::ApplicationModel::LimitedAccessFeatures,winrt::Windows::ApplicationModel::InternalApi::ILimitedAccessFeaturesInternal>::winrt::factory_cache_entry<winrt::Windows::ApplicationModel::LimitedAccessFeatures,winrt::Windows::ApplicationModel::InternalApi::ILimitedAccessFeaturesInternal> winrt::impl::factory_cache_entry_v<winrt::Windows::ApplicationModel::LimitedAccessFeatures,winrt::Windows::ApplicationModel::InternalApi::ILimitedAccessFeaturesInternal>
0x180027ae8  jz      short loc_180027AF9
0x180027aea  call    ??$?RAEBUILimitedAccessFeaturesInternal@InternalApi@ApplicationModel@Windows@winrt@@@_lambda_c098c4d09b8d941208075d7422bf37c2_@@QEBA?A_PAEBUILimitedAccessFeaturesInternal@InternalApi@ApplicationModel@Windows@winrt@@@Z
0x180027aef  lock dec cs:qword_180046D68
0x180027af7  jmp     short loc_180027B07
0x180027af9  lock dec cs:qword_180046D68
0x180027b01  call    ??$call@AEAV_lambda_c098c4d09b8d941208075d7422bf37c2_@@@?$factory_cache_entry@ULimitedAccessFeatures@ApplicationModel@Windows@winrt@@UILimitedAccessFeaturesInternal@InternalApi@234@@impl@winrt@@QEAA?A_PAEAV_lambda_c098c4d09b8d941208075d7422bf37c2_@@@Z
0x180027b06  nop
0x180027b07  lea     rdx, aComMicrosoftWi; "com.microsoft.windows.focussessionmanag"...
0x180027b0e  lea     rcx, [rsp+130h+var_D0]; this
0x180027b13  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x180027b18  mov     [rsp+130h+var_110], 0
0x180027b20  mov     rcx, [rsp+130h+var_108]
0x180027b25  mov     [rsp+130h+pExceptionObject], 0
0x180027b2d  xorps   xmm0, xmm0
0x180027b30  movdqu  [rsp+130h+var_E0], xmm0
0x180027b36  mov     rax, [rcx]
0x180027b39  lea     r8, [rsp+130h+var_110]
0x180027b3e  mov     rdx, [rsp+130h+var_D0]
0x180027b43  mov     rax, [rax+38h]
0x180027b47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027b4c  lea     r8, [rsp+130h+pExceptionObject]
0x180027b51  mov     edx, eax
0x180027b53  lea     rcx, [rsp+130h+var_100]
0x180027b58  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180027b5d  mov     eax, [rsp+130h+var_110]
0x180027b61  dec     eax
0x180027b63  mov     [rsp+130h+var_100], rbx
0x180027b68  lea     rdx, [rsp+130h+var_F8]
0x180027b6d  lea     rcx, [rsp+130h+var_100]
0x180027b72  cmp     eax, 1
0x180027b75  ja      short loc_180027BB3
0x180027b77  call    ??$FocusStartOrEndAPIAccessApproved@PEBGAEAPEBG@FocusSessionTelemetry@implementation@Shell@Internal@Windows@winrt@@SAX$$QEAPEBGAEAPEBG@Z; winrt::Windows::Internal::Shell::implementation::FocusSessionTelemetry::FocusStartOrEndAPIAccessApproved<ushort const *,ushort const * &>(ushort const * &&,ushort const * &)
0x180027b7c  nop
0x180027b7d  lea     rcx, [rsp+130h+var_108]
0x180027b82  call    ??1?$com_ptr@UIWeakReferenceSource@impl@winrt@@@winrt@@QEAA@XZ; winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(void)
0x180027b87  nop
0x180027b88  lea     rcx, [rsp+130h+var_F0]
0x180027b8d  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180027b92  mov     rcx, [rbp+30h+var_10]
0x180027b96  xor     rcx, rsp; StackCookie
0x180027b99  call    __security_check_cookie
0x180027b9e  lea     r11, [rsp+130h+var_s0]
0x180027ba6  mov     rbx, [r11+18h]
0x180027baa  mov     rdi, [r11+20h]
0x180027bae  mov     rsp, r11
0x180027bb1  pop     rbp
0x180027bb2  retn
0x180027bb3  call    ??$FocusStartOrEndAPIAccessDenied@PEBGAEAPEBG@FocusSessionTelemetry@implementation@Shell@Internal@Windows@winrt@@SAX$$QEAPEBGAEAPEBG@Z; winrt::Windows::Internal::Shell::implementation::FocusSessionTelemetry::FocusStartOrEndAPIAccessDenied<ushort const *,ushort const * &>(ushort const * &&,ushort const * &)
0x180027bb8  nop
0x180027bb9  lea     rcx, [rsp+130h+var_D0]
0x180027bbe  call    ?current@slim_source_location@impl@winrt@@SA?AU123@IQEBD0@Z; winrt::impl::slim_source_location::current(uint,char const * const,char const * const)
0x180027bc3  mov     rbx, rax
0x180027bc6  lea     rdx, aFeatureComMicr; "Feature com.microsoft.windows.focussess"...
0x180027bcd  lea     rcx, [rbp+30h+var_B0]; this
0x180027bd1  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x180027bd6  mov     r8, rbx; struct winrt::impl::slim_source_location *
0x180027bd9  lea     rdx, [rbp+30h+var_B0]; struct winrt::param::hstring *
0x180027bdd  lea     rcx, [rsp+130h+pExceptionObject]; this
0x180027be2  call    ??0hresult_access_denied@winrt@@QEAA@AEBUhstring@param@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_access_denied::hresult_access_denied(winrt::param::hstring const &,winrt::impl::slim_source_location const &)
0x180027be7  lea     rdx, _TI2?AUhresult_access_denied@winrt@@; pThrowInfo
0x180027bee  lea     rcx, [rsp+130h+pExceptionObject]; pExceptionObject
0x180027bf3  call    _CxxThrowException_0
```
