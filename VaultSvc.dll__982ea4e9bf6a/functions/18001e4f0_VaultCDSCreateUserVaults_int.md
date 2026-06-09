# VaultCDSCreateUserVaults(int)

- ea: `0x18001e4f0`
- end: `0x18001ed93`
- name: `?VaultCDSCreateUserVaults@@YAJH@Z`
- size: `2211`
- prototype: `__int64 __fastcall(int)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001d7b4`

## callees

- `0x180003140`
- `0x180006610`
- `0x18001cea8`
- `0x18001cecc`
- `0x18001e4f0`
- `0x18001eda0`
- `0x18001f818`
- `0x18001fb9c`
- `0x18001fe80`
- `0x180038730`
- `0x180038c6c`
- `0x180038d64`
- `0x18003a580`
- `0x180045600`
- `0x18004d010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18001e58c`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18001e58c`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001eb04`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001eb04`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18001e551`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18001e551`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001ece2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001eced`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001ed7c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001ed87`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001ece2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001eced`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001ed7c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001ed87`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001e534`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001e534`

## string_xrefs

- `0x18001e52d`: `Windows.Internal.Security.Authentication.Web.TokenBrokerInternal`
- `0x18001e616`: `onecore\ds\security\vault\vaultserver\vaultcds.cpp`
- `0x18001ea1d`: `onecore\ds\security\vault\vaultserver\vaultcds.cpp`
- `0x18001ea80`: `onecore\ds\security\vault\vaultserver\vaultcds.cpp`
- `0x18001eb12`: `onecore\ds\security\vault\vaultserver\vaultcds.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall VaultCDSCreateUserVaults(int a1)
{
  HRESULT v2; // eax
  int ActivationFactory; // eax
  unsigned int DefaultSignInAccount; // edi
  HRESULT v5; // eax
  CVaultMgr *v6; // rcx
  unsigned int UserVaultManager; // eax
  unsigned int v8; // r8d
  struct IUnknownVtbl *lpVtbl; // rax
  int v10; // eax
  __int64 v11; // rsi
  int v12; // eax
  __int64 v13; // rax
  int v14; // eax
  __int64 v16; // rax
  int v17; // eax
  __int64 (__fastcall **v18)(__int64 *, GUID *, __int64 *); // rax
  int v19; // eax
  __int64 (__fastcall **v20)(__int64, GUID *, __int64 **); // rax
  int v21; // eax
  __int64 (__fastcall **v22)(__int64, GUID *, __int64 **); // rax
  int v23; // eax
  __int64 v24; // rax
  int v25; // eax
  unsigned int DefaultVault; // eax
  unsigned int v27; // r8d
  unsigned int v28; // eax
  unsigned int v29; // r8d
  unsigned int v30; // eax
  unsigned int v31; // r8d
  int dwAuthnLevel; // [rsp+20h] [rbp-89h]
  int dwAuthnLevela; // [rsp+20h] [rbp-89h]
  unsigned int dwAuthnLevelb; // [rsp+20h] [rbp-89h]
  int dwAuthnLevelc; // [rsp+20h] [rbp-89h]
  __int64 *v36; // [rsp+40h] [rbp-69h] BYREF
  __int64 *v37; // [rsp+48h] [rbp-61h] BYREF
  __int64 (__fastcall ***v38)(__int64, GUID *, __int64 **); // [rsp+50h] [rbp-59h] BYREF
  HSTRING v39; // [rsp+58h] [rbp-51h] BYREF
  __int64 v40; // [rsp+60h] [rbp-49h] BYREF
  IUnknown *pProxy; // [rsp+68h] [rbp-41h] BYREF
  __int64 v42; // [rsp+70h] [rbp-39h] BYREF
  __int64 *v43; // [rsp+78h] [rbp-31h] BYREF
  HSTRING v44; // [rsp+80h] [rbp-29h] BYREF
  __int64 v45; // [rsp+88h] [rbp-21h] BYREF
  __int64 (__fastcall *v46)(_QWORD); // [rsp+90h] [rbp-19h] BYREF
  CUserVaultMgr *v47; // [rsp+98h] [rbp-11h] BYREF
  int v48; // [rsp+A0h] [rbp-9h]
  HSTRING_HEADER hstringHeader; // [rsp+A8h] [rbp-1h] BYREF
  HSTRING string; // [rsp+C0h] [rbp+17h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+5Fh]

  pProxy = 0;
  string = 0;
  v2 = WindowsCreateStringReference(
         L"Windows.Internal.Security.Authentication.Web.TokenBrokerInternal",
         0x40u,
         &hstringHeader,
         &string);
  if ( v2 < 0 )
  {
    RaiseException(v2, 1u, 0, 0);
    __debugbreak();
  }
  ActivationFactory = RoGetActivationFactory(string, &GUID_07650a66_66ea_489d_aa90_0dabc75f3567, &pProxy);
  DefaultSignInAccount = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2A4,
      (unsigned int)"onecore\\ds\\security\\vault\\vaultserver\\vaultcds.cpp",
      (const char *)(unsigned int)ActivationFactory,
      dwAuthnLevel);
    if ( pProxy )
      ((void (__fastcall *)(IUnknown *))pProxy->lpVtbl->Release)(pProxy);
    return DefaultSignInAccount;
  }
  v5 = CoSetProxyBlanket(pProxy, 0xFFFFFFFF, 0xFFFFFFFF, (OLECHAR *)0xFFFFFFFFFFFFFFFFLL, 2u, 3u, 0, 0x20u);
  DefaultSignInAccount = v5;
  if ( v5 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2B3,
      (unsigned int)"onecore\\ds\\security\\vault\\vaultserver\\vaultcds.cpp",
      (const char *)(unsigned int)v5,
      dwAuthnLevela);
    goto LABEL_79;
  }
  v46 = AutoDereference<IVaultKeyManager>;
  v47 = 0;
  v48 = 0;
  UserVaultManager = CVaultMgr::GetUserVaultManager(v6, 0, &v47, 0, 0);
  if ( UserVaultManager )
  {
    DefaultSignInAccount = wil::details::in1diag3::Return_Win32(
                             retaddr,
                             (void *)0x2B6,
                             v8,
                             (const char *)UserVaultManager,
                             dwAuthnLevelb);
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v46);
    goto LABEL_79;
  }
  v36 = 0;
  v40 = 0;
  lpVtbl = pProxy->lpVtbl;
  v45 = 0;
  v10 = ((__int64 (__fastcall *)(IUnknown *, __int64 *))lpVtbl[9].Release)(pProxy, &v45);
  DefaultSignInAccount = v10;
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x49,
      (unsigned int)"onecore\\ds\\security\\vault\\vaultserver\\vaultcds.cpp",
      (const char *)(unsigned int)v10,
      dwAuthnLevelb);
    if ( v45 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 16LL))(v45);
    goto LABEL_78;
  }
  v40 = 0;
  v11 = v45;
  DefaultSignInAccount = WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *>,Windows::Foundation::IAsyncOperation<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *>>(v45);
  if ( (DefaultSignInAccount & 0x80000000) != 0
    || (DefaultSignInAccount = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v11 + 64LL))(v11, &v40),
        (DefaultSignInAccount & 0x80000000) != 0) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4B,
      (unsigned int)"onecore\\ds\\security\\vault\\vaultserver\\vaultcds.cpp",
      (const char *)DefaultSignInAccount,
      dwAuthnLevelb);
    if ( v40 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 16LL))(v40);
    if ( v45 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 16LL))(v45);
    goto LABEL_78;
  }
  v12 = (*(__int64 (__fastcall **)(__int64, __int64 **))(*(_QWORD *)v40 + 48LL))(v40, &v36);
  DefaultSignInAccount = v12;
  if ( v12 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4D,
      (unsigned int)"onecore\\ds\\security\\vault\\vaultserver\\vaultcds.cpp",
      (const char *)(unsigned int)v12,
      dwAuthnLevelb);
    wil::com_ptr_t<Windows::Security::Credentials::IWebAccountProvider3,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccountProvider3,wil::err_returncode_policy>(&v40);
    wil::com_ptr_t<Windows::Security::Credentials::IWebAccountProvider3,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccountProvider3,wil::err_returncode_policy>(&v45);
LABEL_78:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2B9,
      (unsigned int)"onecore\\ds\\security\\vault\\vaultserver\\vaultcds.cpp",
      (const char *)DefaultSignInAccount,
      dwAuthnLevelc);
    wil::com_ptr_t<Windows::Security::Credentials::IWebAccountProvider3,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccountProvider3,wil::err_returncode_policy>(&v36);
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v46);
LABEL_79:
    wil::com_ptr_t<Windows::Security::Credentials::IWebAccountProvider3,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccountProvider3,wil::err_returncode_policy>(&pProxy);
    return DefaultSignInAccount;
  }
  if ( v40 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 16LL))(v40);
  if ( v45 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 16LL))(v45);
  if ( !v36 )
  {
    wil::com_ptr_t<Windows::Security::Credentials::IWebAccountProvider3,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccountProvider3,wil::err_returncode_policy>(&v36);
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v46);
    DefaultSignInAccount = 0;
    goto LABEL_79;
  }
  v37 = 0;
  v13 = *v36;
  v37 = 0;
  v14 = (*(__int64 (__fastcall **)(__int64 *, __int64 **))(v13 + 48))(v36, &v37);
  DefaultSignInAccount = v14;
  if ( v14 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2BE,
      (unsigned int)"onecore\\ds\\security\\vault\\vaultserver\\vaultcds.cpp",
      (const char *)(unsigned int)v14,
      dwAuthnLevelb);
    if ( v37 )
      (*(void (__fastcall **)(__int64 *))(*v37 + 16))(v37);
    if ( v36 )
      (*(void (__fastcall **)(__int64 *))(*v36 + 16))(v36);
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v46);
    if ( pProxy )
      ((void (__fastcall *)(IUnknown *))pProxy->lpVtbl->Release)(pProxy);
    return DefaultSignInAccount;
  }
  v39 = 0;
  v16 = *v37;
  v39 = 0;
  v17 = (*(__int64 (__fastcall **)(__int64 *, HSTRING *))(v16 + 48))(v37, &v39);
  DefaultSignInAccount = v17;
  if ( v17 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2C1,
      (unsigned int)"onecore\\ds\\security\\vault\\vaultserver\\vaultcds.cpp",
      (const char *)(unsigned int)v17,
      dwAuthnLevelb);
    wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&v39);
    wil::com_ptr_t<Windows::Security::Credentials::IWebAccountProvider3,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccountProvider3,wil::err_returncode_policy>(&v37);
    wil::com_ptr_t<Windows::Security::Credentials::IWebAccountProvider3,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccountProvider3,wil::err_returncode_policy>(&v36);
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v46);
    goto LABEL_79;
  }
  v38 = 0;
  v18 = (__int64 (__fastcall **)(__int64 *, GUID *, __int64 *))*v37;
  v38 = 0;
  v19 = (*v18)(v37, &GUID_4a01eb05_4e42_41d4_b518_e008a5163614, (__int64 *)&v38);
  DefaultSignInAccount = v19;
  if ( v19 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2C4,
      (unsigned int)"onecore\\ds\\security\\vault\\vaultserver\\vaultcds.cpp",
      (const char *)(unsigned int)v19,
      dwAuthnLevelb);
    wil::com_ptr_t<Windows::Security::Credentials::IWebAccountProvider3,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccountProvider3,wil::err_returncode_policy>(&v38);
    wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&v39);
    wil::com_ptr_t<Windows::Security::Credentials::IWebAccountProvider3,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccountProvider3,wil::err_returncode_policy>(&v37);
    wil::com_ptr_t<Windows::Security::Credentials::IWebAccountProvider3,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccountProvider3,wil::err_returncode_policy>(&v36);
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v46);
    goto LABEL_79;
  }
  v44 = 0;
  v20 = *v38;
  v44 = 0;
  v21 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(__int64, GUID *, __int64 **), HSTRING *))v20[7])(v38, &v44);
  DefaultSignInAccount = v21;
  if ( v21 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2C7,
      (unsigned int)"onecore\\ds\\security\\vault\\vaultserver\\vaultcds.cpp",
      (const char *)(unsigned int)v21,
      dwAuthnLevelb);
    wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&v44);
    wil::com_ptr_t<Windows::Security::Credentials::IWebAccountProvider3,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccountProvider3,wil::err_returncode_policy>(&v38);
    wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&v39);
    wil::com_ptr_t<Windows::Security::Credentials::IWebAccountProvider3,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccountProvider3,wil::err_returncode_policy>(&v37);
    wil::com_ptr_t<Windows::Security::Credentials::IWebAccountProvider3,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccountProvider3,wil::err_returncode_policy>(&v36);
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v46);
    goto LABEL_79;
  }
  v43 = 0;
  v22 = *v38;
  v43 = 0;
  v23 = (*v22)((__int64)v38, &GUID_da1c518b_970d_4d49_825c_f2706f8ca7fe, &v43);
  DefaultSignInAccount = v23;
  if ( v23 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2CA,
      (unsigned int)"onecore\\ds\\security\\vault\\vaultserver\\vaultcds.cpp",
      (const char *)(unsigned int)v23,
      dwAuthnLevelb);
    wil::com_ptr_t<Windows::Security::Credentials::IWebAccountProvider3,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccountProvider3,wil::err_returncode_policy>(&v43);
    wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&v44);
    wil::com_ptr_t<Windows::Security::Credentials::IWebAccountProvider3,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccountProvider3,wil::err_returncode_policy>(&v38);
    wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&v39);
    wil::com_ptr_t<Windows::Security::Credentials::IWebAccountProvider3,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccountProvider3,wil::err_returncode_policy>(&v37);
    wil::com_ptr_t<Windows::Security::Credentials::IWebAccountProvider3,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccountProvider3,wil::err_returncode_policy>(&v36);
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v46);
    goto LABEL_79;
  }
  v42 = 0;
  v24 = *v43;
  v42 = 0;
  v25 = (*(__int64 (__fastcall **)(__int64 *, __int64 *))(v24 + 48))(v43, &v42);
  DefaultSignInAccount = v25;
  if ( v25 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2CD,
      (unsigned int)"onecore\\ds\\security\\vault\\vaultserver\\vaultcds.cpp",
      (const char *)(unsigned int)v25,
      dwAuthnLevelb);
    if ( v42 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v42 + 16LL))(v42);
    if ( v43 )
      (*(void (__fastcall **)(__int64 *))(*v43 + 16))(v43);
    if ( v44 )
      WindowsDeleteString(v44);
    if ( v38 )
      ((void (__fastcall *)(__int64 (__fastcall ***)(__int64, GUID *, __int64 **)))(*v38)[2])(v38);
    if ( v39 )
      WindowsDeleteString(v39);
    if ( v37 )
      (*(void (__fastcall **)(__int64 *))(*v37 + 16))(v37);
    if ( v36 )
      (*(void (__fastcall **)(__int64 *))(*v36 + 16))(v36);
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v46);
    if ( pProxy )
      ((void (__fastcall *)(IUnknown *))pProxy->lpVtbl->Release)(pProxy);
    return DefaultSignInAccount;
  }
  hstringHeader.Reserved.Reserved1 = AutoDereference<IVaultKeyManager>;
  *(_QWORD *)&hstringHeader.Reserved.Reserved2[8] = 0;
  *(_DWORD *)&hstringHeader.Reserved.Reserved2[16] = 0;
  DefaultVault = CUserVaultMgr::GetDefaultVault(v47, (struct CUserVault **)&hstringHeader.Reserved.Reserved2[8]);
  if ( DefaultVault )
  {
    DefaultSignInAccount = wil::details::in1diag3::Return_Win32(
                             retaddr,
                             (void *)0x2D0,
                             v27,
                             (const char *)DefaultVault,
                             dwAuthnLevelb);
    CVaultAutoPtr<CUserVault *,void,CUserVault *,0>::Delete(&hstringHeader);
    wil::com_ptr_t<Windows::Security::Credentials::IWebAccountProvider3,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccountProvider3,wil::err_returncode_policy>(&v42);
    wil::com_ptr_t<Windows::Security::Credentials::IWebAccountProvider3,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccountProvider3,wil::err_returncode_policy>(&v43);
    wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&v44);
    wil::com_ptr_t<Windows::Security::Credentials::IWebAccountProvider3,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccountProvider3,wil::err_returncode_policy>(&v38);
    wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&v39);
    wil::com_ptr_t<Windows::Security::Credentials::IWebAccountProvider3,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccountProvider3,wil::err_returncode_policy>(&v37);
    wil::com_ptr_t<Windows::Security::Credentials::IWebAccountProvider3,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccountProvider3,wil::err_returncode_policy>(&v36);
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v46);
    goto LABEL_79;
  }
  v28 = SyncFromCdsToUserVault(v42, (__int64)v36, *(__int64 *)&hstringHeader.Reserved.Reserved2[8], a1 == 0);
  if ( v28 )
    wil::details::in1diag3::_Log_Win32(retaddr, (void *)0x2D6, v29, (const char *)v28, dwAuthnLevelb);
  if ( a1 )
  {
    v30 = SyncFromUserVaultToCdsOneTime(v42, (__int64)v36, *(CUserVault **)&hstringHeader.Reserved.Reserved2[8]);
    if ( v30 )
      wil::details::in1diag3::_Log_Win32(retaddr, (void *)0x2DA, v31, (const char *)v30, dwAuthnLevelb);
  }
  CVaultAutoPtr<CUserVault *,void,CUserVault *,0>::Delete(&hstringHeader);
  if ( v42 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v42 + 16LL))(v42);
  if ( v43 )
    (*(void (__fastcall **)(__int64 *))(*v43 + 16))(v43);
  if ( v44 )
    WindowsDeleteString(v44);
  if ( v38 )
    ((void (__fastcall *)(__int64 (__fastcall ***)(__int64, GUID *, __int64 **)))(*v38)[2])(v38);
  if ( v39 )
    WindowsDeleteString(v39);
  if ( v37 )
    (*(void (__fastcall **)(__int64 *))(*v37 + 16))(v37);
  if ( v36 )
    (*(void (__fastcall **)(__int64 *))(*v36 + 16))(v36);
  CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v46);
  if ( pProxy )
    ((void (__fastcall *)(IUnknown *))pProxy->lpVtbl->Release)(pProxy);
  return 0;
}

```

## disassembly

```asm
0x18001e4f0  push    rbp
0x18001e4f2  push    rbx
0x18001e4f3  push    rsi
0x18001e4f4  push    rdi
0x18001e4f5  push    r14
0x18001e4f7  push    r15
0x18001e4f9  lea     rbp, [rsp-2Fh]
0x18001e4fe  sub     rsp, 0D8h
0x18001e505  mov     rax, cs:__security_cookie
0x18001e50c  xor     rax, rsp
0x18001e50f  mov     [rbp+57h+var_38], rax
0x18001e513  mov     r14d, ecx
0x18001e516  xor     r15d, r15d
0x18001e519  mov     [rbp+57h+pProxy], r15
0x18001e51d  mov     [rbp+57h+string], r15
0x18001e521  lea     r9, [rbp+57h+string]; string
0x18001e525  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x18001e529  lea     edx, [r15+40h]; length
0x18001e52d  lea     rcx, ?RuntimeClass_Windows_Internal_Security_Authentication_Web_TokenBrokerInternal@@3QBGB; "Windows.Internal.Security.Authenticatio"...
0x18001e534  call    cs:__imp_WindowsCreateStringReference
0x18001e53a  test    eax, eax
0x18001e53c  js      loc_18001EAF8
0x18001e542  lea     r8, [rbp+57h+pProxy]
0x18001e546  lea     rdx, _GUID_07650a66_66ea_489d_aa90_0dabc75f3567
0x18001e54d  mov     rcx, [rbp+57h+string]
0x18001e551  call    cs:__imp_RoGetActivationFactory
0x18001e557  mov     edi, eax
0x18001e559  test    eax, eax
0x18001e55b  js      loc_18001EA16
0x18001e561  mov     [rsp+100h+dwCapabilities], 20h ; ' '; dwCapabilities
0x18001e569  mov     [rsp+100h+pAuthInfo], r15; void **
0x18001e56e  mov     [rsp+100h+dwImpLevel], 3; unsigned int *
0x18001e576  mov     [rsp+100h+dwAuthnLevel], 2; int
0x18001e57e  or      r9, 0FFFFFFFFFFFFFFFFh; pServerPrincName
0x18001e582  or      edx, 0FFFFFFFFh; dwAuthnSvc
0x18001e585  mov     r8d, edx; dwAuthzSvc
0x18001e588  mov     rcx, [rbp+57h+pProxy]; pProxy
0x18001e58c  call    cs:__imp_CoSetProxyBlanket
0x18001e592  mov     edi, eax
0x18001e594  test    eax, eax
0x18001e596  js      loc_18001EB0B
0x18001e59c  lea     rax, ??$AutoDereference@UIVaultKeyManager@@@@YAXPEAUIVaultKeyManager@@@Z; AutoDereference<IVaultKeyManager>(IVaultKeyManager *)
0x18001e5a3  mov     [rbp+57h+var_70], rax
0x18001e5a7  mov     [rbp+57h+var_68], r15
0x18001e5ab  mov     [rbp+57h+var_60], r15d
0x18001e5af  mov     qword ptr [rsp+100h+dwAuthnLevel], r15; unsigned int
0x18001e5b4  xor     r9d, r9d; unsigned __int8 *
0x18001e5b7  lea     r8, [rbp+57h+var_68]; struct CUserVaultMgr **
0x18001e5bb  xor     edx, edx; unsigned __int8
0x18001e5bd  call    ?GetUserVaultManager@CVaultMgr@@QEAAKEPEAPEAVCUserVaultMgr@@QEAEPEAU_LUID@@PEAKPEAPEAX@Z; CVaultMgr::GetUserVaultManager(uchar,CUserVaultMgr * *,uchar * const,_LUID *,ulong *,void * *)
0x18001e5c2  test    eax, eax
0x18001e5c4  jnz     loc_18001EB25
0x18001e5ca  mov     [rbp+57h+var_C0], r15
0x18001e5ce  mov     rcx, [rbp+57h+pProxy]
0x18001e5d2  mov     [rbp+57h+var_A0], r15
0x18001e5d6  mov     rax, [rcx]
0x18001e5d9  mov     [rbp+57h+var_78], r15
0x18001e5dd  lea     rdx, [rbp+57h+var_78]
0x18001e5e1  mov     rax, [rax+0E8h]
0x18001e5e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e5ed  mov     edi, eax
0x18001e5ef  test    eax, eax
0x18001e5f1  js      loc_18001EA79
0x18001e5f7  mov     rcx, [rbp+57h+var_A0]
0x18001e5fb  mov     [rbp+57h+var_A0], r15
0x18001e5ff  test    rcx, rcx
0x18001e602  jnz     loc_18001EB44
0x18001e608  mov     rsi, [rbp+57h+var_78]
0x18001e60c  mov     rcx, rsi
0x18001e60f  call    ??$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVGetDefaultSignInAccountResult@Web@Authentication@Security@Internal@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVGetDefaultSignInAccountResult@Web@Authentication@Security@Internal@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVGetDefaultSignInAccountResult@Web@Authentication@Security@Internal@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z; WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *>,Windows::Foundation::IAsyncOperation<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *>>(Windows::Foundation::IAsyncOperation<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *> *,tagCOWAIT_FLAGS,void *)
0x18001e614  mov     edi, eax
0x18001e616  lea     rbx, aOnecoreDsSecur; "onecore\\ds\\security\\vault\\vaultserv"...
0x18001e61d  test    eax, eax
0x18001e61f  js      short loc_18001E686
0x18001e621  mov     rax, [rsi]
0x18001e624  lea     rdx, [rbp+57h+var_A0]
0x18001e628  mov     rcx, rsi
0x18001e62b  mov     rax, [rax+40h]
0x18001e62f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e634  mov     edi, eax
0x18001e636  test    eax, eax
0x18001e638  js      short loc_18001E686
0x18001e63a  mov     rcx, [rbp+57h+var_A0]
0x18001e63e  mov     rax, [rcx]
0x18001e641  lea     rdx, [rbp+57h+var_C0]
0x18001e645  mov     rax, [rax+30h]
0x18001e649  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e64e  mov     edi, eax
0x18001e650  test    eax, eax
0x18001e652  js      loc_18001EB55
0x18001e658  mov     rcx, [rbp+57h+var_A0]
0x18001e65c  test    rcx, rcx
0x18001e65f  jz      short loc_18001E66E
0x18001e661  mov     rax, [rcx]
0x18001e664  mov     rax, [rax+10h]
0x18001e668  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e66d  nop
0x18001e66e  mov     rcx, [rbp+57h+var_78]
0x18001e672  test    rcx, rcx
0x18001e675  jz      short loc_18001E684
0x18001e677  mov     rax, [rcx]
0x18001e67a  mov     rax, [rax+10h]
0x18001e67e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e683  nop
0x18001e684  jmp     short loc_18001E6CF
0x18001e686  mov     rcx, [rbp+5Fh]; this
0x18001e68a  mov     r9d, edi; char *
0x18001e68d  mov     r8, rbx; unsigned int
0x18001e690  mov     edx, 4Bh ; 'K'; void *
0x18001e695  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001e69a  nop
0x18001e69b  mov     rcx, [rbp+57h+var_A0]
0x18001e69f  test    rcx, rcx
0x18001e6a2  jz      short loc_18001E6B1
0x18001e6a4  mov     rax, [rcx]
0x18001e6a7  mov     rax, [rax+10h]
0x18001e6ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e6b0  nop
0x18001e6b1  mov     rcx, [rbp+57h+var_78]
0x18001e6b5  test    rcx, rcx
0x18001e6b8  jz      short loc_18001E6C7
0x18001e6ba  mov     rax, [rcx]
0x18001e6bd  mov     rax, [rax+10h]
0x18001e6c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e6c6  nop
0x18001e6c7  test    edi, edi
0x18001e6c9  js      loc_18001EAC1
0x18001e6cf  mov     rcx, [rbp+57h+var_C0]
0x18001e6d3  test    rcx, rcx
0x18001e6d6  jz      loc_18001EB82
0x18001e6dc  mov     [rbp+57h+var_B8], r15
0x18001e6e0  mov     rax, [rcx]
0x18001e6e3  mov     [rbp+57h+var_B8], r15
0x18001e6e7  lea     rdx, [rbp+57h+var_B8]
0x18001e6eb  mov     rax, [rax+30h]
0x18001e6ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e6f4  mov     edi, eax
0x18001e6f6  test    eax, eax
0x18001e6f8  jns     short loc_18001E779
0x18001e6fa  mov     rcx, [rbp+5Fh]; this
0x18001e6fe  mov     r9d, eax; char *
0x18001e701  mov     r8, rbx; unsigned int
0x18001e704  mov     edx, 2BEh; void *
0x18001e709  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001e70e  nop
0x18001e70f  mov     rcx, [rbp+57h+var_B8]
0x18001e713  test    rcx, rcx
0x18001e716  jz      short loc_18001E725
0x18001e718  mov     rax, [rcx]
0x18001e71b  mov     rax, [rax+10h]
0x18001e71f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e724  nop
0x18001e725  mov     rcx, [rbp+57h+var_C0]
0x18001e729  test    rcx, rcx
0x18001e72c  jz      short loc_18001E73B
0x18001e72e  mov     rax, [rcx]
0x18001e731  mov     rax, [rax+10h]
0x18001e735  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e73a  nop
0x18001e73b  lea     rcx, [rbp+57h+var_70]
0x18001e73f  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18001e744  nop
0x18001e745  mov     rcx, [rbp+57h+pProxy]
0x18001e749  test    rcx, rcx
0x18001e74c  jz      short loc_18001E75B
0x18001e74e  mov     rax, [rcx]
0x18001e751  mov     rax, [rax+10h]
0x18001e755  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e75a  nop
0x18001e75b  mov     eax, edi
0x18001e75d  mov     rcx, [rbp+57h+var_38]
0x18001e761  xor     rcx, rsp; StackCookie
0x18001e764  call    __security_check_cookie
0x18001e769  add     rsp, 0D8h
0x18001e770  pop     r15
0x18001e772  pop     r14
0x18001e774  pop     rdi
0x18001e775  pop     rsi
0x18001e776  pop     rbx
0x18001e777  pop     rbp
0x18001e778  retn
0x18001e779  mov     [rbp+57h+var_A8], r15
0x18001e77d  mov     rcx, [rbp+57h+var_B8]
0x18001e781  mov     rax, [rcx]
0x18001e784  mov     [rbp+57h+var_A8], r15
0x18001e788  lea     rdx, [rbp+57h+var_A8]
0x18001e78c  mov     rax, [rax+30h]
0x18001e790  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e795  mov     edi, eax
0x18001e797  test    eax, eax
0x18001e799  js      loc_18001EB9E
0x18001e79f  mov     [rbp+57h+var_B0], r15
0x18001e7a3  mov     rcx, [rbp+57h+var_B8]
0x18001e7a7  mov     rax, [rcx]
0x18001e7aa  mov     [rbp+57h+var_B0], r15
0x18001e7ae  lea     r8, [rbp+57h+var_B0]
0x18001e7b2  lea     rdx, _GUID_4a01eb05_4e42_41d4_b518_e008a5163614
0x18001e7b9  mov     rax, [rax]
0x18001e7bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e7c1  mov     edi, eax
0x18001e7c3  test    eax, eax
0x18001e7c5  js      loc_18001EBE0
0x18001e7cb  mov     [rbp+57h+var_80], r15
0x18001e7cf  mov     rcx, [rbp+57h+var_B0]
0x18001e7d3  mov     rax, [rcx]
0x18001e7d6  mov     [rbp+57h+var_80], r15
0x18001e7da  lea     rdx, [rbp+57h+var_80]
0x18001e7de  mov     rax, [rax+38h]
0x18001e7e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e7e7  mov     edi, eax
0x18001e7e9  test    eax, eax
0x18001e7eb  js      loc_18001EC2C
0x18001e7f1  mov     [rbp+57h+var_88], r15
0x18001e7f5  mov     rcx, [rbp+57h+var_B0]
0x18001e7f9  mov     rax, [rcx]
0x18001e7fc  mov     [rbp+57h+var_88], r15
0x18001e800  lea     r8, [rbp+57h+var_88]
0x18001e804  lea     rdx, _GUID_da1c518b_970d_4d49_825c_f2706f8ca7fe
0x18001e80b  mov     rax, [rax]
0x18001e80e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e813  mov     edi, eax
0x18001e815  test    eax, eax
0x18001e817  js      loc_18001EC82
0x18001e81d  mov     [rbp+57h+var_90], r15
0x18001e821  mov     rcx, [rbp+57h+var_88]
0x18001e825  mov     rax, [rcx]
0x18001e828  mov     [rbp+57h+var_90], r15
0x18001e82c  lea     rdx, [rbp+57h+var_90]
0x18001e830  mov     rax, [rax+30h]
0x18001e834  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e839  mov     edi, eax
0x18001e83b  test    eax, eax
0x18001e83d  js      loc_18001E954
0x18001e843  lea     rax, ??$AutoDereference@UIVaultKeyManager@@@@YAXPEAUIVaultKeyManager@@@Z; AutoDereference<IVaultKeyManager>(IVaultKeyManager *)
0x18001e84a  mov     qword ptr [rbp+57h+hstringHeader.Reserved], rax
0x18001e84e  mov     qword ptr [rbp+57h+hstringHeader.Reserved+8], r15
0x18001e852  mov     dword ptr [rbp+57h+hstringHeader.Reserved+10h], r15d
0x18001e856  lea     rdx, [rbp+57h+hstringHeader.Reserved+8]; struct CUserVault **
0x18001e85a  mov     rcx, [rbp+57h+var_68]; this
0x18001e85e  call    ?GetDefaultVault@CUserVaultMgr@@QEAAKPEAPEAVCUserVault@@@Z; CUserVaultMgr::GetDefaultVault(CUserVault * *)
0x18001e863  test    eax, eax
0x18001e865  jnz     loc_18001ECF8
0x18001e86b  mov     r9d, r15d
0x18001e86e  test    r14d, r14d
0x18001e871  setz    r9b
0x18001e875  mov     r8, qword ptr [rbp+57h+hstringHeader.Reserved+8]
0x18001e879  mov     rdx, [rbp+57h+var_C0]
0x18001e87d  mov     rcx, [rbp+57h+var_90]
0x18001e881  call    _SyncFromCdsToUserVault
0x18001e886  mov     rcx, [rbp+5Fh]; this
0x18001e88a  test    eax, eax
0x18001e88c  jnz     loc_18001ED6A
0x18001e892  test    r14d, r14d
0x18001e895  jnz     loc_18001EA4A
0x18001e89b  lea     rcx, [rbp+57h+hstringHeader]
0x18001e89f  call    ?Delete@?$CVaultAutoPtr@PEAVCUserVault@@XPEAV1@$0A@@@QEAAXXZ; CVaultAutoPtr<CUserVault *,void,CUserVault *,0>::Delete(void)
0x18001e8a4  nop
0x18001e8a5  mov     rcx, [rbp+57h+var_90]
0x18001e8a9  test    rcx, rcx
0x18001e8ac  jz      short loc_18001E8BB
0x18001e8ae  mov     rax, [rcx]
0x18001e8b1  mov     rax, [rax+10h]
0x18001e8b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e8ba  nop
0x18001e8bb  mov     rcx, [rbp+57h+var_88]
0x18001e8bf  test    rcx, rcx
0x18001e8c2  jz      short loc_18001E8D1
0x18001e8c4  mov     rax, [rcx]
0x18001e8c7  mov     rax, [rax+10h]
0x18001e8cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e8d0  nop
0x18001e8d1  mov     rcx, [rbp+57h+var_80]; string
0x18001e8d5  test    rcx, rcx
0x18001e8d8  jnz     loc_18001ED7C
0x18001e8de  mov     rcx, [rbp+57h+var_B0]
0x18001e8e2  test    rcx, rcx
0x18001e8e5  jz      short loc_18001E8F4
0x18001e8e7  mov     rax, [rcx]
0x18001e8ea  mov     rax, [rax+10h]
0x18001e8ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e8f3  nop
0x18001e8f4  mov     rcx, [rbp+57h+var_A8]; string
0x18001e8f8  test    rcx, rcx
0x18001e8fb  jnz     loc_18001ED87
0x18001e901  mov     rcx, [rbp+57h+var_B8]
0x18001e905  test    rcx, rcx
0x18001e908  jz      short loc_18001E917
0x18001e90a  mov     rax, [rcx]
0x18001e90d  mov     rax, [rax+10h]
0x18001e911  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e916  nop
0x18001e917  mov     rcx, [rbp+57h+var_C0]
0x18001e91b  test    rcx, rcx
0x18001e91e  jz      short loc_18001E92D
0x18001e920  mov     rax, [rcx]
0x18001e923  mov     rax, [rax+10h]
0x18001e927  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e92c  nop
0x18001e92d  lea     rcx, [rbp+57h+var_70]
0x18001e931  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
  ... truncated ...
```
