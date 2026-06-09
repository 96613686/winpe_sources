# AppDefaultHelpers::CheckCredentials(HSTRING__ *,HSTRING__ *,Windows::UI::WindowId,Windows::Internal::ApplicationDefaults::CheckCredentialsResult *)

- ea: `0x1803722c0`
- end: `0x180372a70`
- name: `?CheckCredentials@AppDefaultHelpers@@UEAAJPEAUHSTRING__@@0UWindowId@UI@Windows@@PEAW4CheckCredentialsResult@ApplicationDefaults@Internal@5@@Z`
- size: `1968`
- prototype: ``
- caller_count: `0`
- callee_count: `19`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x18000ee68`
- `0x18001a000`
- `0x18001b390`
- `0x1800432f0`
- `0x180060a10`
- `0x1800a5580`
- `0x1800c39dc`
- `0x180190990`
- `0x1802cc0a0`
- `0x18033b5a8`
- `0x1803722c0`
- `0x180372a78`
- `0x180372a98`
- `0x18037a72c`
- `0x1803a4cb0`
- `0x180534bd8`
- `0x180552db8`
- `0x180552f1c`
- `0x180552f58`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180372363`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1803727e5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180372363`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1803727e5`
- `ntdll!RtlNtStatusToDosError` at `0x180372713`
- `ntdll!RtlNtStatusToDosError` at `0x180372713`
- `ntdll!RtlInitString` at `0x180372321`
- `ntdll!RtlInitString` at `0x180372339`
- `ntdll!RtlInitString` at `0x180372321`
- `ntdll!RtlInitString` at `0x180372339`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1803724db`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180372538`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180372541`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180372563`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18037256c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180372610`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18037263d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1803726a1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1803726aa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1803726b3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180372900`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180372909`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180372912`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1803729aa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1803729b3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1803729bc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180372a10`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180372a19`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180372a22`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1803724db`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180372538`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180372541`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180372563`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18037256c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180372610`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18037263d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1803726a1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1803726aa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1803726b3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180372900`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180372909`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180372912`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1803729aa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1803729b3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1803729bc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180372a10`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180372a19`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180372a22`
- `ext-ms-win-security-credui-l1-1-0!CredUIPromptForWindowsCredentialsW` at `0x180372766`
- `ext-ms-win-security-credui-l1-1-0!CredUIPromptForWindowsCredentialsW` at `0x180372766`
- `ext-ms-win-security-credui-l1-1-0!CredPackAuthenticationBufferW` at `0x1803725c5`
- `ext-ms-win-security-credui-l1-1-0!CredPackAuthenticationBufferW` at `0x18037266b`
- `ext-ms-win-security-credui-l1-1-0!CredPackAuthenticationBufferW` at `0x1803725c5`
- `ext-ms-win-security-credui-l1-1-0!CredPackAuthenticationBufferW` at `0x18037266b`
- `Secur32!LsaFreeReturnBuffer` at `0x1803727d4`
- `Secur32!LsaFreeReturnBuffer` at `0x1803727d4`
- `Secur32!LsaLogonUser` at `0x18037285d`
- `Secur32!LsaLogonUser` at `0x18037285d`
- `Secur32!LsaLookupAuthenticationPackage` at `0x180372397`
- `Secur32!LsaLookupAuthenticationPackage` at `0x180372397`
- `Secur32!LsaConnectUntrusted` at `0x180372371`
- `Secur32!LsaConnectUntrusted` at `0x180372371`
- `Secur32!LsaDeregisterLogonProcess` at `0x180372354`
- `Secur32!LsaDeregisterLogonProcess` at `0x180372354`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1803726e8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1803726f8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1803726e8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1803726f8`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x1803723ff`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x180372506`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x1803723ff`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x180372506`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall AppDefaultHelpers::CheckCredentials(__int64 a1, HSTRING a2, HSTRING a3, int a4, _DWORD *a5)
{
  NTSTATUS v6; // eax
  unsigned int LastError; // r15d
  __int64 v8; // rdx
  NTSTATUS v9; // eax
  BOOL v10; // eax
  void *v11; // rcx
  void *v12; // rdi
  void *v13; // rcx
  void *v14; // rsi
  BOOL v15; // eax
  int v16; // eax
  AppDefaultHelpers *v17; // rcx
  __int64 v18; // r8
  void *v19; // rcx
  WCHAR *v20; // rdx
  WCHAR *v21; // rbx
  BOOL v22; // eax
  void **unique_cotaskmem; // rax
  void *v24; // r12
  int v25; // r15d
  WCHAR *v26; // rcx
  WCHAR *v27; // rdx
  const char *v28; // r9
  __int64 v29; // rcx
  NTSTATUS v30; // r14d
  DWORD v31; // eax
  DWORD v32; // r14d
  __int64 v33; // rcx
  PVOID v34; // r14
  NTSTATUS v35; // eax
  __int64 v36; // rcx
  HSTRING v37; // rdx
  HSTRING v38; // rdx
  __int64 v40; // rcx
  HSTRING v41; // rdx
  HSTRING v42; // rdx
  void *v43; // rcx
  bool v44; // zf
  int cchReferencedDomainName; // [rsp+20h] [rbp-E0h]
  int cchReferencedDomainNamea; // [rsp+20h] [rbp-E0h]
  int cchReferencedDomainNameb; // [rsp+20h] [rbp-E0h]
  int cchReferencedDomainNamec; // [rsp+20h] [rbp-E0h]
  unsigned int cchReferencedDomainNamed; // [rsp+20h] [rbp-E0h]
  LPVOID pv; // [rsp+70h] [rbp-90h] BYREF
  HSTRING *p_string; // [rsp+78h] [rbp-88h] BYREF
  LPVOID ppvOutAuthBuffer; // [rsp+80h] [rbp-80h] BYREF
  char v53; // [rsp+88h] [rbp-78h]
  DWORD pcbPackedCredentials; // [rsp+90h] [rbp-70h] BYREF
  DWORD v55; // [rsp+94h] [rbp-6Ch] BYREF
  DWORD cchName; // [rsp+98h] [rbp-68h] BYREF
  _CREDUI_INFOW pUiInfo; // [rsp+A0h] [rbp-60h] BYREF
  void *lpMem; // [rsp+C8h] [rbp-38h] BYREF
  DWORD dwErrCode[2]; // [rsp+D0h] [rbp-30h] BYREF
  HSTRING string; // [rsp+D8h] [rbp-28h] BYREF
  HANDLE LsaHandle; // [rsp+E0h] [rbp-20h] BYREF
  ULONG AuthenticationPackage; // [rsp+E8h] [rbp-18h] BYREF
  PVOID Buffer; // [rsp+F0h] [rbp-10h] BYREF
  enum _SID_NAME_USE peUse; // [rsp+F8h] [rbp-8h] BYREF
  ULONG ProfileBufferLength; // [rsp+FCh] [rbp-4h] BYREF
  HSTRING pulOutAuthBufferSize; // [rsp+100h] [rbp+0h] BYREF
  int SubStatus; // [rsp+108h] [rbp+8h] BYREF
  struct _LUID LogonId; // [rsp+110h] [rbp+10h] BYREF
  struct _STRING DestinationString; // [rsp+118h] [rbp+18h] BYREF
  struct _STRING v70; // [rsp+128h] [rbp+28h] BYREF
  _TOKEN_SOURCE SourceContext; // [rsp+138h] [rbp+38h] BYREF
  struct _QUOTA_LIMITS Quotas; // [rsp+148h] [rbp+48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1B8h] [rbp+B8h]

  pulOutAuthBufferSize = a3;
  string = a2;
  *a5 = 1;
  AuthenticationPackage = 0;
  DestinationString = 0;
  RtlInitString(&DestinationString, "Negotiate");
  v70 = 0;
  RtlInitString(&v70, "AppDefaultsHelpers");
  LsaHandle = 0;
  v6 = LsaConnectUntrusted(&LsaHandle);
  LastError = v6 | 0x10000000;
  if ( v6 < 0 )
  {
    v8 = 328;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\appdefaultshelpers.cpp",
      (const char *)LastError,
      cchReferencedDomainName);
LABEL_69:
    wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long LsaDeregisterLogonProcess(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long LsaDeregisterLogonProcess(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&LsaHandle);
    return LastError;
  }
  v9 = LsaLookupAuthenticationPackage(LsaHandle, (PLSA_STRING)&DestinationString, &AuthenticationPackage);
  LastError = v9 | 0x10000000;
  if ( v9 < 0 )
  {
    v8 = 329;
    goto LABEL_5;
  }
  wil::details::GetTokenInfoWrap<_TOKEN_USER,wil::err_exception_policy,0>(&lpMem);
  cchName = 0;
  v55 = 0;
  peUse = SidTypeInvalid;
  v10 = LookupAccountSidLocalW(*(PSID *)lpMem, 0, &cchName, 0, &v55, &peUse);
  LastError = ResultFromWin32Bool(v10);
  if ( (int)(LastError + 0x80000000) >= 0 && LastError != -2147024774 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x152,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\appdefaultshelpers.cpp",
      (const char *)LastError,
      cchReferencedDomainNamea);
LABEL_9:
    v11 = lpMem;
    lpMem = 0;
LABEL_10:
    if ( v11 )
      CZeroInitNew::operator delete(v11);
    goto LABEL_69;
  }
  wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
    &pv,
    0,
    cchName);
  v12 = pv;
  if ( !pv )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x156,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\appdefaultshelpers.cpp",
      (const char *)0x8007000ELL,
      cchReferencedDomainNamea);
LABEL_14:
    v13 = lpMem;
    lpMem = 0;
LABEL_73:
    if ( v13 )
      CZeroInitNew::operator delete(v13);
    wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long LsaDeregisterLogonProcess(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long LsaDeregisterLogonProcess(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&LsaHandle);
    return 2147942414LL;
  }
  wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
    &pv,
    0,
    v55);
  v14 = pv;
  if ( !pv )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x159,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\appdefaultshelpers.cpp",
      (const char *)0x8007000ELL,
      cchReferencedDomainNamea);
    CoTaskMemFree(v12);
    goto LABEL_14;
  }
  v15 = LookupAccountSidLocalW(*(PSID *)lpMem, (LPWSTR)v12, &cchName, (LPWSTR)pv, &v55, &peUse);
  v16 = ResultFromWin32Bool(v15);
  LastError = v16;
  if ( v16 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x15B,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\appdefaultshelpers.cpp",
      (const char *)(unsigned int)v16,
      cchReferencedDomainNameb);
    goto LABEL_19;
  }
  if ( !AppDefaultHelpers::IsLocalUserNoPassword(v17, (const unsigned __int16 *)v12) )
  {
    *(_QWORD *)dwErrCode = 0;
    pv = v12;
    Buffer = v14;
    wil::str_concat_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,unsigned short *,unsigned short [2],unsigned short *>(
      dwErrCode,
      &Buffer,
      v18,
      &pv);
    pcbPackedCredentials = 0;
    v20 = (WCHAR *)v12;
    v21 = *(WCHAR **)dwErrCode;
    if ( *(_QWORD *)dwErrCode )
      v20 = *(WCHAR **)dwErrCode;
    v22 = CredPackAuthenticationBufferW(0, v20, (LPWSTR)&WindowName, 0, &pcbPackedCredentials);
    LastError = ResultFromWin32Bool(v22);
    if ( (int)(LastError + 0x80000000) < 0 || LastError == -2147024774 )
    {
      unique_cotaskmem = (void **)wil::make_unique_cotaskmem_nothrow<unsigned char [0]>(dwErrCode, pcbPackedCredentials);
      v24 = *unique_cotaskmem;
      v25 = 0;
      *unique_cotaskmem = 0;
      v26 = *(WCHAR **)dwErrCode;
      *(_QWORD *)dwErrCode = 0;
      if ( v26 )
        CoTaskMemFree(v26);
      if ( v24 )
      {
        v27 = (WCHAR *)v12;
        if ( v21 )
          v27 = v21;
        if ( CredPackAuthenticationBufferW(0, v27, (LPWSTR)&WindowName, (PBYTE)v24, &pcbPackedCredentials) )
        {
          memset(&pUiInfo, 0, sizeof(pUiInfo));
          pUiInfo.cbSize = 40;
          pUiInfo.pszCaptionText = WindowsGetStringRawBuffer(string, 0);
          pUiInfo.pszMessageText = WindowsGetStringRawBuffer(pulOutAuthBufferSize, 0);
          pUiInfo.hwndParent = (HWND)a4;
          SubStatus = 0;
          v30 = 0;
          while ( 1 )
          {
            v31 = RtlNtStatusToDosError(v30);
            string = 0;
            LODWORD(pulOutAuthBufferSize) = 0;
            p_string = &string;
            ppvOutAuthBuffer = 0;
            v53 = 1;
            v32 = CredUIPromptForWindowsCredentialsW(
                    &pUiInfo,
                    v31,
                    &AuthenticationPackage,
                    v24,
                    pcbPackedCredentials,
                    &ppvOutAuthBuffer,
                    (ULONG *)&pulOutAuthBufferSize,
                    0,
                    0x8000220u);
            wil::details::out_param_t<wistd::unique_ptr<void,wil::cotaskmem_secure_deleter>>::~out_param_t<wistd::unique_ptr<void,wil::cotaskmem_secure_deleter>>(&p_string);
            if ( v32 == 1223 )
            {
              v42 = string;
              string = 0;
              if ( v42 )
                ((void (*)(void))wil::cotaskmem_secure_deleter::operator()<void>)();
              goto LABEL_64;
            }
            if ( v32 )
              break;
            SourceContext = 0;
            Buffer = 0;
            ProfileBufferLength = 0;
            LogonId = 0;
            *(_QWORD *)dwErrCode = 0;
            memset(&Quotas, 0, sizeof(Quotas));
            wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
              dwErrCode,
              0);
            v34 = Buffer;
            if ( Buffer )
            {
              wil::last_error_context::last_error_context((wil::last_error_context *)&pv);
              LsaFreeReturnBuffer(v34);
              if ( !(_BYTE)pv )
                SetLastError(HIDWORD(pv));
            }
            Buffer = 0;
            v35 = LsaLogonUser(
                    LsaHandle,
                    (PLSA_STRING)&v70,
                    Interactive,
                    AuthenticationPackage,
                    string,
                    (ULONG)pulOutAuthBufferSize,
                    0,
                    &SourceContext,
                    &Buffer,
                    &ProfileBufferLength,
                    &LogonId,
                    (PHANDLE)dwErrCode,
                    &Quotas,
                    &SubStatus);
            v30 = v35;
            if ( v25 >= 3 && v35 < 0 )
            {
              *a5 = 3;
              wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(dwErrCode);
              wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long LsaFreeReturnBuffer(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long LsaFreeReturnBuffer(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&Buffer);
              v38 = string;
              string = 0;
              if ( v38 )
                wil::cotaskmem_secure_deleter::operator()<void>(v33, v38);
LABEL_64:
              wil::cotaskmem_secure_deleter::operator()<void>(v33, v24);
              if ( v21 )
                CoTaskMemFree(v21);
              CoTaskMemFree(v14);
              CoTaskMemFree(v12);
              v43 = lpMem;
              v44 = lpMem == 0;
              lpMem = 0;
              if ( !v44 )
                CZeroInitNew::operator delete(v43);
              LastError = 0;
              goto LABEL_69;
            }
            wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(dwErrCode);
            wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long LsaFreeReturnBuffer(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long LsaFreeReturnBuffer(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&Buffer);
            v37 = string;
            string = 0;
            if ( v37 )
              wil::cotaskmem_secure_deleter::operator()<void>(v36, v37);
            if ( v30 >= 0 )
            {
              *a5 = 0;
              wil::cotaskmem_secure_deleter::operator()<void>(v36, v24);
              if ( v21 )
                CoTaskMemFree(v21);
              CoTaskMemFree(v14);
              CoTaskMemFree(v12);
              v19 = lpMem;
              lpMem = 0;
              goto LABEL_56;
            }
            ++v25;
          }
          LastError = wil::details::in1diag3::Return_Win32(
                        retaddr,
                        (void *)0x194,
                        (unsigned int)"onecoreuap\\shell\\windows.storage\\appdefaultshelpers.cpp",
                        (const char *)v32,
                        cchReferencedDomainNamed);
          v41 = string;
          string = 0;
          if ( v41 )
            wil::cotaskmem_secure_deleter::operator()<void>(v40, v41);
          wil::cotaskmem_secure_deleter::operator()<void>(v40, v24);
        }
        else
        {
          LastError = wil::details::in1diag3::Return_GetLastError(
                        retaddr,
                        (void *)0x171,
                        (unsigned int)"onecoreuap\\shell\\windows.storage\\appdefaultshelpers.cpp",
                        v28);
          wil::cotaskmem_secure_deleter::operator()<void>(v29, v24);
        }
        if ( v21 )
          CoTaskMemFree(v21);
        CoTaskMemFree(v14);
        CoTaskMemFree(v12);
        v11 = lpMem;
        lpMem = 0;
        goto LABEL_10;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x170,
        (unsigned int)"onecoreuap\\shell\\windows.storage\\appdefaultshelpers.cpp",
        (const char *)0x8007000ELL,
        cchReferencedDomainNamec);
      if ( v21 )
        CoTaskMemFree(v21);
      CoTaskMemFree(v14);
      CoTaskMemFree(v12);
      v13 = lpMem;
      lpMem = 0;
      goto LABEL_73;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x16D,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\appdefaultshelpers.cpp",
      (const char *)LastError,
      cchReferencedDomainNamec);
    if ( v21 )
      CoTaskMemFree(v21);
LABEL_19:
    CoTaskMemFree(v14);
    CoTaskMemFree(v12);
    goto LABEL_9;
  }
  *a5 = 2;
  CoTaskMemFree(v14);
  CoTaskMemFree(v12);
  v19 = lpMem;
  lpMem = 0;
LABEL_56:
  if ( v19 )
    CZeroInitNew::operator delete(v19);
  wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long LsaDeregisterLogonProcess(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long LsaDeregisterLogonProcess(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&LsaHandle);
  return 0;
}

```

## disassembly

```asm
0x1803722c0  mov     [rsp-8+arg_0], rbx
0x1803722c5  push    rbp
0x1803722c6  push    rsi
0x1803722c7  push    rdi
0x1803722c8  push    r12
0x1803722ca  push    r13
0x1803722cc  push    r14
0x1803722ce  push    r15
0x1803722d0  lea     rbp, [rsp-80h]
0x1803722d5  sub     rsp, 180h
0x1803722dc  mov     rax, cs:__security_cookie
0x1803722e3  xor     rax, rsp
0x1803722e6  mov     [rbp+0B0h+var_38], rax
0x1803722ea  mov     r14, r9
0x1803722ed  mov     [rbp+0B0h+var_B0], r8
0x1803722f1  mov     [rbp+0B0h+string], rdx
0x1803722f5  mov     r13, [rbp+0B0h+arg_20]
0x1803722fc  xor     r12d, r12d
0x1803722ff  mov     dword ptr [r13+0], 1
0x180372307  mov     [rbp+0B0h+LsaHandle], r12
0x18037230b  mov     [rbp+0B0h+AuthenticationPackage], r12d
0x18037230f  xorps   xmm0, xmm0
0x180372312  movups  xmmword ptr [rbp+0B0h+DestinationString.Length], xmm0
0x180372316  lea     rdx, aNegotiate; "Negotiate"
0x18037231d  lea     rcx, [rbp+0B0h+DestinationString]; DestinationString
0x180372321  call    cs:__imp_RtlInitString
0x180372327  xorps   xmm0, xmm0
0x18037232a  movups  xmmword ptr [rbp+0B0h+var_88.Length], xmm0
0x18037232e  lea     rdx, aAppdefaultshel; "AppDefaultsHelpers"
0x180372335  lea     rcx, [rbp+0B0h+var_88]; DestinationString
0x180372339  call    cs:__imp_RtlInitString
0x18037233f  mov     rbx, [rbp+0B0h+LsaHandle]
0x180372343  test    rbx, rbx
0x180372346  jz      short loc_180372369
0x180372348  lea     rcx, [rbp+0B0h+dwErrCode]; this
0x18037234c  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180372351  mov     rcx, rbx; LsaHandle
0x180372354  call    cs:__imp_LsaDeregisterLogonProcess
0x18037235a  cmp     byte ptr [rbp+0B0h+dwErrCode], r12b
0x18037235e  jnz     short loc_180372369
0x180372360  mov     ecx, [rbp+0B0h+dwErrCode+4]; dwErrCode
0x180372363  call    cs:__imp_SetLastError
0x180372369  mov     [rbp+0B0h+LsaHandle], r12
0x18037236d  lea     rcx, [rbp+0B0h+LsaHandle]; LsaHandle
0x180372371  call    cs:__imp_LsaConnectUntrusted
0x180372377  mov     r15d, eax
0x18037237a  mov     ebx, 10000000h
0x18037237f  or      r15d, ebx
0x180372382  jge     short loc_18037238B
0x180372384  mov     edx, 148h
0x180372389  jmp     short loc_1803723AA
0x18037238b  lea     r8, [rbp+0B0h+AuthenticationPackage]; AuthenticationPackage
0x18037238f  lea     rdx, [rbp+0B0h+DestinationString]; PackageName
0x180372393  mov     rcx, [rbp+0B0h+LsaHandle]; LsaHandle
0x180372397  call    cs:__imp_LsaLookupAuthenticationPackage
0x18037239d  mov     r15d, eax
0x1803723a0  or      r15d, ebx
0x1803723a3  jge     short loc_1803723C5
0x1803723a5  mov     edx, 149h; void *
0x1803723aa  lea     r8, aOnecoreuapShel_8; "onecoreuap\\shell\\windows.storage\\app"...
0x1803723b1  mov     r9d, r15d; char *
0x1803723b4  mov     rcx, [rbp+0B8h]; this
0x1803723bb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1803723c0  jmp     loc_1803729DB
0x1803723c5  lea     rcx, [rbp+0B0h+lpMem]
0x1803723c9  call    ??$GetTokenInfoWrap@U_TOKEN_USER@@Uerr_exception_policy@wil@@$0A@@details@wil@@YA?AV?$unique_ptr@U_TOKEN_USER@@Utoken_info_deleter@details@wil@@@wistd@@PEAX@Z; wil::details::GetTokenInfoWrap<_TOKEN_USER,wil::err_exception_policy,0>(void *)
0x1803723ce  mov     [rbp+0B0h+cchName], r12d
0x1803723d2  mov     [rbp+0B0h+var_11C], r12d
0x1803723d6  mov     [rbp+0B0h+var_B8], 7
0x1803723dd  lea     rax, [rbp+0B0h+var_B8]
0x1803723e1  mov     [rsp+1B0h+peUse], rax; peUse
0x1803723e6  lea     rax, [rbp+0B0h+var_11C]
0x1803723ea  mov     [rsp+1B0h+cchReferencedDomainName], rax; int
0x1803723ef  xor     r9d, r9d; ReferencedDomainName
0x1803723f2  lea     r8, [rbp+0B0h+cchName]; cchName
0x1803723f6  xor     edx, edx; Name
0x1803723f8  mov     rcx, [rbp+0B0h+lpMem]
0x1803723fc  mov     rcx, [rcx]; Sid
0x1803723ff  call    cs:__imp_LookupAccountSidLocalW
0x180372405  mov     ecx, eax; int
0x180372407  call    ?ResultFromWin32Bool@@YAJH@Z; ResultFromWin32Bool(int)
0x18037240c  mov     r15d, eax
0x18037240f  mov     eax, 80000000h
0x180372414  lea     ecx, [r15+rax]
0x180372418  test    eax, ecx
0x18037241a  jnz     short loc_18037245B
0x18037241c  cmp     r15d, 8007007Ah
0x180372423  jz      short loc_18037245B
0x180372425  mov     rcx, [rbp+0B8h]; this
0x18037242c  mov     r9d, r15d; char *
0x18037242f  lea     r8, aOnecoreuapShel_8; "onecoreuap\\shell\\windows.storage\\app"...
0x180372436  mov     edx, 152h; void *
0x18037243b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180372440  mov     rcx, [rbp+0B0h+lpMem]; lpMem
0x180372444  mov     [rbp+0B0h+lpMem], r12
0x180372448  test    rcx, rcx
0x18037244b  jz      loc_1803729DB
0x180372451  call    ??3CZeroInitNew@@SAXPEAX@Z; CZeroInitNew::operator delete(void *)
0x180372456  jmp     loc_1803729DB
0x18037245b  mov     r8d, [rbp+0B0h+cchName]
0x18037245f  xor     edx, edx
0x180372461  lea     rcx, [rsp+1B0h+pv]
0x180372466  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x18037246b  mov     rdi, [rsp+1B0h+pv]
0x180372470  test    rdi, rdi
0x180372473  jnz     short loc_1803724A0
0x180372475  mov     rcx, [rbp+0B8h]; this
0x18037247c  mov     r9d, 8007000Eh; char *
0x180372482  lea     r8, aOnecoreuapShel_8; "onecoreuap\\shell\\windows.storage\\app"...
0x180372489  mov     edx, 156h; void *
0x18037248e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180372493  mov     rcx, [rbp+0B0h+lpMem]
0x180372497  mov     [rbp+0B0h+lpMem], r12
0x18037249b  jmp     loc_180372A30
0x1803724a0  mov     r8d, [rbp+0B0h+var_11C]
0x1803724a4  xor     edx, edx
0x1803724a6  lea     rcx, [rsp+1B0h+pv]
0x1803724ab  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x1803724b0  mov     rsi, [rsp+1B0h+pv]
0x1803724b5  test    rsi, rsi
0x1803724b8  jnz     short loc_1803724E3
0x1803724ba  mov     rcx, [rbp+0B8h]; this
0x1803724c1  mov     r9d, 8007000Eh; char *
0x1803724c7  lea     r8, aOnecoreuapShel_8; "onecoreuap\\shell\\windows.storage\\app"...
0x1803724ce  mov     edx, 159h; void *
0x1803724d3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1803724d8  mov     rcx, rdi; pv
0x1803724db  call    cs:__imp_CoTaskMemFree
0x1803724e1  jmp     short loc_180372493
0x1803724e3  lea     rax, [rbp+0B0h+var_B8]
0x1803724e7  mov     [rsp+1B0h+peUse], rax; peUse
0x1803724ec  lea     rax, [rbp+0B0h+var_11C]
0x1803724f0  mov     [rsp+1B0h+cchReferencedDomainName], rax; int
0x1803724f5  mov     r9, rsi; ReferencedDomainName
0x1803724f8  lea     r8, [rbp+0B0h+cchName]; cchName
0x1803724fc  mov     rdx, rdi; Name
0x1803724ff  mov     rcx, [rbp+0B0h+lpMem]
0x180372503  mov     rcx, [rcx]; Sid
0x180372506  call    cs:__imp_LookupAccountSidLocalW
0x18037250c  mov     ecx, eax; int
0x18037250e  call    ?ResultFromWin32Bool@@YAJH@Z; ResultFromWin32Bool(int)
0x180372513  mov     r15d, eax
0x180372516  test    eax, eax
0x180372518  jns     short loc_18037254C
0x18037251a  mov     rcx, [rbp+0B8h]; this
0x180372521  mov     r9d, eax; char *
0x180372524  lea     r8, aOnecoreuapShel_8; "onecoreuap\\shell\\windows.storage\\app"...
0x18037252b  mov     edx, 15Bh; void *
0x180372530  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180372535  mov     rcx, rsi; pv
0x180372538  call    cs:__imp_CoTaskMemFree
0x18037253e  mov     rcx, rdi; pv
0x180372541  call    cs:__imp_CoTaskMemFree
0x180372547  jmp     loc_180372440
0x18037254c  mov     rdx, rdi; unsigned __int16 *
0x18037254f  call    ?IsLocalUserNoPassword@AppDefaultHelpers@@AEAA_NPEBG@Z; AppDefaultHelpers::IsLocalUserNoPassword(ushort const *)
0x180372554  test    al, al
0x180372556  jz      short loc_18037257F
0x180372558  mov     dword ptr [r13+0], 2
0x180372560  mov     rcx, rsi; pv
0x180372563  call    cs:__imp_CoTaskMemFree
0x180372569  mov     rcx, rdi; pv
0x18037256c  call    cs:__imp_CoTaskMemFree
0x180372572  mov     rcx, [rbp+0B0h+lpMem]
0x180372576  mov     [rbp+0B0h+lpMem], r12
0x18037257a  jmp     loc_180372924
0x18037257f  mov     qword ptr [rbp+0B0h+dwErrCode], r12
0x180372583  mov     [rsp+1B0h+pv], rdi
0x180372588  mov     [rbp+0B0h+Buffer], rsi
0x18037258c  lea     r9, [rsp+1B0h+pv]
0x180372591  lea     rdx, [rbp+0B0h+Buffer]
0x180372595  lea     rcx, [rbp+0B0h+dwErrCode]
0x180372599  call    ??$str_concat_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@PEAG$$BY01GPEAG@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@AEBQEAGAEAY01$$CBG1@Z; wil::str_concat_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,ushort *,ushort [2],ushort *>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ushort * const &,ushort const (&)[2],ushort * const &)
0x18037259e  mov     [rbp+0B0h+pcbPackedCredentials], r12d
0x1803725a2  mov     rdx, rdi
0x1803725a5  mov     rbx, qword ptr [rbp+0B0h+dwErrCode]
0x1803725a9  test    rbx, rbx
0x1803725ac  cmovnz  rdx, rbx; pszUserName
0x1803725b0  lea     rax, [rbp+0B0h+pcbPackedCredentials]
0x1803725b4  mov     [rsp+1B0h+cchReferencedDomainName], rax; int
0x1803725b9  xor     r9d, r9d; pPackedCredentials
0x1803725bc  lea     r8, WindowName; pszPassword
0x1803725c3  xor     ecx, ecx; dwFlags
0x1803725c5  call    cs:__imp_CredPackAuthenticationBufferW
0x1803725cb  mov     ecx, eax; int
0x1803725cd  call    ?ResultFromWin32Bool@@YAJH@Z; ResultFromWin32Bool(int)
0x1803725d2  mov     r15d, eax
0x1803725d5  mov     ecx, 80000000h
0x1803725da  add     eax, ecx
0x1803725dc  test    ecx, eax
0x1803725de  jnz     short loc_18037261B
0x1803725e0  cmp     r15d, 8007007Ah
0x1803725e7  jz      short loc_18037261B
0x1803725e9  mov     rcx, [rbp+0B8h]; this
0x1803725f0  mov     r9d, r15d; char *
0x1803725f3  lea     r8, aOnecoreuapShel_8; "onecoreuap\\shell\\windows.storage\\app"...
0x1803725fa  mov     edx, 16Dh; void *
0x1803725ff  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180372604  test    rbx, rbx
0x180372607  jz      loc_180372535
0x18037260d  mov     rcx, rbx; pv
0x180372610  call    cs:__imp_CoTaskMemFree
0x180372616  jmp     loc_180372535
0x18037261b  mov     edx, [rbp+0B0h+pcbPackedCredentials]
0x18037261e  lea     rcx, [rbp+0B0h+dwErrCode]
0x180372622  call    ??$make_unique_cotaskmem_nothrow@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@_K@Z; wil::make_unique_cotaskmem_nothrow<uchar [0]>(unsigned __int64)
0x180372627  mov     r12, [rax]
0x18037262a  xor     r15d, r15d
0x18037262d  mov     [rax], r15
0x180372630  mov     rcx, qword ptr [rbp+0B0h+dwErrCode]; pv
0x180372634  mov     qword ptr [rbp+0B0h+dwErrCode], r15
0x180372638  test    rcx, rcx
0x18037263b  jz      short loc_180372643
0x18037263d  call    cs:__imp_CoTaskMemFree
0x180372643  test    r12, r12
0x180372646  jz      loc_1803729E9
0x18037264c  mov     rdx, rdi
0x18037264f  test    rbx, rbx
0x180372652  cmovnz  rdx, rbx; pszUserName
0x180372656  lea     rax, [rbp+0B0h+pcbPackedCredentials]
0x18037265a  mov     [rsp+1B0h+cchReferencedDomainName], rax; pcbPackedCredentials
0x18037265f  mov     r9, r12; pPackedCredentials
0x180372662  lea     r8, WindowName; pszPassword
0x180372669  xor     ecx, ecx; dwFlags
0x18037266b  call    cs:__imp_CredPackAuthenticationBufferW
0x180372671  test    eax, eax
0x180372673  jnz     short loc_1803726CA
0x180372675  mov     rcx, [rbp+0B8h]; this
0x18037267c  lea     r8, aOnecoreuapShel_8; "onecoreuap\\shell\\windows.storage\\app"...
0x180372683  mov     edx, 171h; void *
0x180372688  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18037268d  mov     r15d, eax
0x180372690  mov     rdx, r12
0x180372693  call    ??$?RX@cotaskmem_secure_deleter@wil@@QEBAXPEAX@Z; wil::cotaskmem_secure_deleter::operator()<void>(void *)
0x180372698  nop
0x180372699  test    rbx, rbx
0x18037269c  jz      short loc_1803726A7
0x18037269e  mov     rcx, rbx; pv
0x1803726a1  call    cs:__imp_CoTaskMemFree
0x1803726a7  mov     rcx, rsi; pv
0x1803726aa  call    cs:__imp_CoTaskMemFree
0x1803726b0  mov     rcx, rdi; pv
0x1803726b3  call    cs:__imp_CoTaskMemFree
0x1803726b9  mov     rcx, [rbp+0B0h+lpMem]
0x1803726bd  mov     [rbp+0B0h+lpMem], 0
0x1803726c5  jmp     loc_180372448
0x1803726ca  xorps   xmm0, xmm0
0x1803726cd  xor     eax, eax
0x1803726cf  movups  xmmword ptr [rbp+0B0h+pUiInfo.cbSize], xmm0
0x1803726d3  movups  xmmword ptr [rbp+0B0h+pUiInfo.pszMessageText], xmm0
0x1803726d7  mov     [rbp+0B0h+pUiInfo.hbmBanner], rax
0x1803726db  mov     [rbp+0B0h+pUiInfo.cbSize], 28h ; '('
0x1803726e2  xor     edx, edx; length
0x1803726e4  mov     rcx, [rbp+0B0h+string]; string
0x1803726e8  call    cs:__imp_WindowsGetStringRawBuffer
0x1803726ee  mov     [rbp+0B0h+pUiInfo.pszCaptionText], rax
0x1803726f2  xor     edx, edx; length
0x1803726f4  mov     rcx, [rbp+0B0h+var_B0]; string
0x1803726f8  call    cs:__imp_WindowsGetStringRawBuffer
0x1803726fe  mov     [rbp+0B0h+pUiInfo.pszMessageText], rax
0x180372702  movsxd  rax, r14d
0x180372705  mov     [rbp+0B0h+pUiInfo.hwndParent], rax
0x180372709  mov     [rbp+0B0h+var_A8], r15d
0x18037270d  mov     r14d, r15d
0x180372710  mov     ecx, r14d; Status
0x180372713  call    cs:__imp_RtlNtStatusToDosError
0x180372719  xor     edx, edx
0x18037271b  mov     [rbp+0B0h+string], rdx
0x18037271f  mov     dword ptr [rbp+0B0h+var_B0], edx
0x180372722  lea     rcx, [rbp+0B0h+string]
0x180372726  mov     [rsp+1B0h+var_138], rcx
0x18037272b  mov     [rbp+0B0h+ppvOutAuthBuffer], rdx
0x18037272f  mov     [rbp+0B0h+var_128], 1
0x180372733  mov     ecx, [rbp+0B0h+pcbPackedCredentials]
0x180372736  mov     [rsp+1B0h+dwFlags], 8000220h; dwFlags
0x18037273e  mov     [rsp+1B0h+pfSave], rdx; pfSave
0x180372743  lea     rdx, [rbp+0B0h+var_B0]
0x180372747  mov     [rsp+1B0h+pulOutAuthBufferSize], rdx; pulOutAuthBufferSize
0x18037274c  lea     rdx, [rbp+0B0h+ppvOutAuthBuffer]
0x180372750  mov     [rsp+1B0h+peUse], rdx; ppvOutAuthBuffer
0x180372755  mov     dword ptr [rsp+1B0h+cchReferencedDomainName], ecx; unsigned int
0x180372759  mov     r9, r12; pvInAuthBuffer
0x18037275c  lea     r8, [rbp+0B0h+AuthenticationPackage]; pulAuthPackage
0x180372760  mov     edx, eax; dwAuthError
0x180372762  lea     rcx, [rbp+0B0h+pUiInfo]; pUiInfo
0x180372766  call    cs:__imp_CredUIPromptForWindowsCredentialsW
0x18037276c  mov     r14d, eax
0x18037276f  lea     rcx, [rsp+1B0h+var_138]
0x180372774  call    ??1?$out_param_t@V?$unique_ptr@XUcotaskmem_secure_deleter@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<void,wil::cotaskmem_secure_deleter>>::~out_param_t<wistd::unique_ptr<void,wil::cotaskmem_secure_deleter>>(void)
0x180372779  cmp     r14d, 4C7h
0x180372780  jz      loc_180372982
0x180372786  xor     eax, eax
0x180372788  test    r14d, r14d
0x18037278b  jnz     loc_18037293F
0x180372791  xorps   xmm0, xmm0
0x180372794  movups  xmmword ptr [rbp+0B0h+SourceContext.SourceName], xmm0
0x180372798  mov     [rbp+0B0h+Buffer], rax
0x18037279c  mov     [rbp+0B0h+var_B4], eax
0x18037279f  mov     qword ptr [rbp+0B0h+var_A0.LowPart], rax
0x1803727a3  mov     qword ptr [rbp+0B0h+dwErrCode], rax
  ... truncated ...
```
