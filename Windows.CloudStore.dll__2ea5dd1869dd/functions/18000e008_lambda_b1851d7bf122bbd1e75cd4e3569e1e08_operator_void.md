# _lambda_b1851d7bf122bbd1e75cd4e3569e1e08_::operator()(void)

- ea: `0x18000e008`
- end: `0x18000e7a6`
- name: `??R_lambda_b1851d7bf122bbd1e75cd4e3569e1e08_@@QEBA@XZ`
- size: `1950`
- prototype: ``
- caller_count: `2`
- callee_count: `17`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800ad6ac`
- `0x18017f704`

## callees

- `0x18000dfe4`
- `0x18000e008`
- `0x18000e7ac`
- `0x18000e84c`
- `0x18000e878`
- `0x18000e8d0`
- `0x18000f7a0`
- `0x180016cf4`
- `0x180032a50`
- `0x18004436c`
- `0x180065614`
- `0x1800d1d50`
- `0x1800fcffc`
- `0x18010d418`
- `0x1801201a0`
- `0x180178038`
- `0x180208010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000e037`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000e037`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18000e357`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18000e357`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000e765`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000e775`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000e785`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000e765`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000e775`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000e785`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000e0ca`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000e0ca`
- `urlmon!MkParseDisplayNameEx` at `0x18000e4dc`
- `urlmon!MkParseDisplayNameEx` at `0x18000e4dc`
- `ext-ms-win-ole32-bindctx-l1-1-0!CreateBindCtx` at `0x18000e3dd`
- `ext-ms-win-ole32-bindctx-l1-1-0!CreateBindCtx` at `0x18000e3dd`

## string_xrefs

- `0x18000e38a`: `Session:%u!clsid:%s`

## pseudocode

```c
// Hidden C++ exception states: #wind=25
int __fastcall _lambda_b1851d7bf122bbd1e75cd4e3569e1e08_::operator()(__int64 a1)
{
  HANDLE CurrentProcess; // rax
  bool *v3; // r8
  int IsProcessAppContainer; // eax
  void **v5; // rcx
  void *v6; // rcx
  const char *v7; // r9
  int v8; // eax
  __int64 *v9; // rcx
  __int64 v10; // rax
  int v11; // eax
  __int64 v12; // rax
  int v13; // eax
  __int64 **v14; // rax
  __int64 *v15; // rcx
  __int64 v16; // rax
  int v17; // eax
  __int64 **v18; // rax
  __int64 *v19; // rcx
  __int64 v20; // rax
  int v21; // eax
  int v22; // eax
  HRESULT v23; // eax
  __int64 v24; // rcx
  int v25; // eax
  int v26; // eax
  HRESULT v27; // eax
  __int64 v28; // rcx
  __int64 v29; // rdx
  __int64 v30; // rax
  int v31; // eax
  struct IUnknownVtbl *lpVtbl; // rax
  int v33; // eax
  struct IUnknownVtbl *v34; // rax
  int v35; // eax
  struct IUnknown **v36; // rax
  struct IUnknown *v37; // rcx
  struct IUnknown *v38; // rbx
  int ReturnLength; // [rsp+20h] [rbp-E0h]
  int ReturnLengtha; // [rsp+20h] [rbp-E0h]
  int ReturnLengthb; // [rsp+20h] [rbp-E0h]
  char v43[8]; // [rsp+50h] [rbp-B0h] BYREF
  __int64 *p_string; // [rsp+58h] [rbp-A8h] BYREF
  LPBC ppbc; // [rsp+60h] [rbp-A0h] BYREF
  char v46; // [rsp+68h] [rbp-98h]
  unsigned int TokenInformation; // [rsp+70h] [rbp-90h] BYREF
  __int64 *v48; // [rsp+78h] [rbp-88h] BYREF
  IBindCtx *pbc; // [rsp+80h] [rbp-80h] BYREF
  DWORD v50; // [rsp+88h] [rbp-78h] BYREF
  ULONG pchEaten; // [rsp+8Ch] [rbp-74h] BYREF
  struct IUnknown *v52; // [rsp+90h] [rbp-70h] BYREF
  struct IUnknown *v53; // [rsp+98h] [rbp-68h] BYREF
  struct IUnknown *v54; // [rsp+A0h] [rbp-60h] BYREF
  __int64 *v55; // [rsp+A8h] [rbp-58h] BYREF
  HSTRING string; // [rsp+B0h] [rbp-50h] BYREF
  HSTRING v57; // [rsp+B8h] [rbp-48h] BYREF
  HSTRING v58; // [rsp+C0h] [rbp-40h] BYREF
  char v59[8]; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v60; // [rsp+D0h] [rbp-30h] BYREF
  __int128 v61; // [rsp+D8h] [rbp-28h] BYREF
  __int128 v62; // [rsp+E8h] [rbp-18h]
  __int128 v63; // [rsp+F8h] [rbp-8h]
  OLECHAR sz[40]; // [rsp+110h] [rbp+10h] BYREF
  WCHAR szDisplayName[264]; // [rsp+160h] [rbp+60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+3A8h] [rbp+2A8h]

  v43[0] = 0;
  CurrentProcess = GetCurrentProcess();
  IsProcessAppContainer = CallerIdentity::IsProcessAppContainer(CurrentProcess, v43, v3);
  if ( IsProcessAppContainer < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x293,
      (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\api\\src\\remotecloudstore.cpp",
      (const char *)(unsigned int)IsProcessAppContainer,
      ReturnLength);
  if ( v43[0] )
    wil::details::in1diag3::FailFast_Hr(
      retaddr,
      (void *)0x294,
      (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\api\\src\\remotecloudstore.cpp",
      (const char *)0x80070005LL,
      ReturnLength);
  TokenInformation = 0;
  v50 = 0;
  v5 = *(void ***)(*(_QWORD *)a1 + 80LL);
  if ( v5 )
    v6 = *v5;
  else
    v6 = 0;
  if ( !GetTokenInformation(v6, TokenSessionId, &TokenInformation, 4u, &v50) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x29B,
      (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\api\\src\\remotecloudstore.cpp",
      v7);
  if ( v50 != 4 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x29C,
      (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\api\\src\\remotecloudstore.cpp",
      v7);
  if ( !TokenInformation )
    wil::details::in1diag3::FailFast_Hr(
      retaddr,
      (void *)0x29D,
      (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\api\\src\\remotecloudstore.cpp",
      (const char *)0x80070032LL,
      ReturnLengtha);
  v60 = 0;
  if ( *(_QWORD *)(*(_QWORD *)a1 + 120LL) )
  {
    wil::GetActivationFactory<Windows::System::Internal::ISignInStateManager>(&v48);
    v8 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, __int64 *))(*v48 + 136))(
           v48,
           *(_QWORD *)(*(_QWORD *)a1 + 120LL),
           &v60);
    if ( v8 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x2A4,
        (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\api\\src\\remotecloudstore.cpp",
        (const char *)(unsigned int)v8,
        ReturnLengtha);
    wil::com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>(&v48);
  }
  v58 = 0;
  v57 = 0;
  string = 0;
  v9 = *(__int64 **)(*(_QWORD *)a1 + 128LL);
  if ( v9 )
  {
    v48 = 0;
    v10 = *v9;
    p_string = (__int64 *)&v48;
    ppbc = 0;
    v46 = 1;
    v11 = (*(__int64 (__fastcall **)(__int64 *, LPBC *))(v10 + 48))(v9, &ppbc);
    if ( v11 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x2AE,
        (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\api\\src\\remotecloudstore.cpp",
        (const char *)(unsigned int)v11,
        ReturnLengtha);
    wil::details::out_param_t<wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *>,wil::err_exception_policy>>::~out_param_t<wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *>,wil::err_exception_policy>>(&p_string);
    v12 = *v48;
    p_string = (__int64 *)&v58;
    ppbc = 0;
    v46 = 1;
    v13 = (*(__int64 (__fastcall **)(__int64 *, LPBC *))(v12 + 48))(v48, &ppbc);
    if ( v13 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x2AF,
        (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\api\\src\\remotecloudstore.cpp",
        (const char *)(unsigned int)v13,
        ReturnLengtha);
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>(&p_string);
    v14 = (__int64 **)wil::com_ptr_t<Windows::Security::Credentials::IWebAccountProvider,wil::err_exception_policy>::query<Windows::Security::Credentials::IWebAccountProvider2>(
                        &v48,
                        v59);
    v15 = *v14;
    v16 = **v14;
    p_string = (__int64 *)&v57;
    ppbc = 0;
    v46 = 1;
    v17 = (*(__int64 (__fastcall **)(__int64 *, LPBC *))(v16 + 56))(v15, &ppbc);
    if ( v17 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x2B0,
        (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\api\\src\\remotecloudstore.cpp",
        (const char *)(unsigned int)v17,
        ReturnLengtha);
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>(&p_string);
    wil::com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>(v59);
    v18 = (__int64 **)wil::com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>::query<Windows::Security::Credentials::IWebAccount2>(
                        *(_QWORD *)a1 + 128LL,
                        v59);
    v19 = *v18;
    v20 = **v18;
    p_string = (__int64 *)&string;
    ppbc = 0;
    v46 = 1;
    v21 = (*(__int64 (__fastcall **)(__int64 *, LPBC *))(v20 + 48))(v19, &ppbc);
    if ( v21 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x2B1,
        (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\api\\src\\remotecloudstore.cpp",
        (const char *)(unsigned int)v21,
        ReturnLengtha);
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>(&p_string);
    wil::com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>(v59);
    wil::com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>(&v48);
  }
  if ( !StringFromGUID2(&GUID_d4872b74_3afc_47cd_b8a2_9e4f998539bc, sz, 40) )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x2B5,
      (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\api\\src\\remotecloudstore.cpp",
      (const char *)0x8007007ALL,
      ReturnLengtha);
  v22 = StringCchPrintfW(szDisplayName, 0x104u, L"Session:%u!clsid:%s", TokenInformation);
  if ( v22 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x2B8,
      (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\api\\src\\remotecloudstore.cpp",
      (const char *)(unsigned int)v22,
      (int)sz);
  pbc = 0;
  p_string = (__int64 *)&pbc;
  ppbc = 0;
  v46 = 1;
  v23 = CreateBindCtx(0, &ppbc);
  if ( v23 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x2BB,
      (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\api\\src\\remotecloudstore.cpp",
      (const char *)(unsigned int)v23,
      (int)sz);
  if ( v46 )
  {
    v24 = *p_string;
    *p_string = (__int64)ppbc;
    if ( v24 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
  }
  v61 = 0;
  v62 = 0;
  v63 = 0;
  LODWORD(v61) = 48;
  v25 = ((__int64 (__fastcall *)(IBindCtx *, __int128 *))pbc->lpVtbl->GetBindOptions)(pbc, &v61);
  if ( v25 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x2BF,
      (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\api\\src\\remotecloudstore.cpp",
      (const char *)(unsigned int)v25,
      (int)sz);
  DWORD1(v62) = 4;
  v26 = ((__int64 (__fastcall *)(IBindCtx *, __int128 *))pbc->lpVtbl->SetBindOptions)(pbc, &v61);
  if ( v26 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x2C1,
      (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\api\\src\\remotecloudstore.cpp",
      (const char *)(unsigned int)v26,
      (int)sz);
  pchEaten = 0;
  v55 = 0;
  p_string = (__int64 *)&v55;
  ppbc = 0;
  v46 = 1;
  v27 = MkParseDisplayNameEx(pbc, szDisplayName, &pchEaten, (LPMONIKER *)&ppbc);
  if ( v27 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x2C5,
      (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\api\\src\\remotecloudstore.cpp",
      (const char *)(unsigned int)v27,
      (int)sz);
  if ( v46 )
  {
    v28 = *p_string;
    *p_string = (__int64)ppbc;
    if ( v28 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
  }
  v29 = -1;
  do
    ++v29;
  while ( szDisplayName[v29] );
  if ( pchEaten != v29 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x2C6,
      (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\api\\src\\remotecloudstore.cpp",
      (const char *)0x80004005LL,
      (int)sz);
  v53 = 0;
  v30 = *v55;
  v53 = 0;
  v31 = (*(__int64 (__fastcall **)(__int64 *, IBindCtx *, _QWORD, GUID *))(v30 + 64))(
          v55,
          pbc,
          0,
          &GUID_00000001_0000_0000_c000_000000000046);
  if ( v31 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x2C9,
      (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\api\\src\\remotecloudstore.cpp",
      (const char *)(unsigned int)v31,
      (int)&v53);
  RemoteCloudStoreProxy::ConfigureProxySecurity(*(RemoteCloudStoreProxy **)a1, v53);
  v52 = 0;
  lpVtbl = v53->lpVtbl;
  v52 = 0;
  v33 = ((__int64 (__fastcall *)(struct IUnknown *, _QWORD, GUID *, struct IUnknown **))lpVtbl[1].QueryInterface)(
          v53,
          0,
          &GUID_7d341022_b665_409e_9774_b400dc9efedb,
          &v52);
  if ( v33 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x2CD,
      (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\api\\src\\remotecloudstore.cpp",
      (const char *)(unsigned int)v33,
      (int)&v53);
  RemoteCloudStoreProxy::ConfigureProxySecurity(*(RemoteCloudStoreProxy **)a1, v52);
  v54 = 0;
  v34 = v52->lpVtbl;
  p_string = (__int64 *)&v54;
  ppbc = 0;
  v46 = 1;
  ReturnLengthb = (int)v57;
  v35 = ((__int64 (__fastcall *)(struct IUnknown *, _QWORD, __int64, HSTRING))v34[2].AddRef)(
          v52,
          *(unsigned int *)(*(_QWORD *)a1 + 112LL),
          v60,
          v58);
  if ( v35 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x2D9,
      (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\api\\src\\remotecloudstore.cpp",
      (const char *)(unsigned int)v35,
      ReturnLengthb);
  if ( v46 )
    wil::com_ptr_t<Windows::Internal::Storage::Cloud::State::ICloudStoreStateManager,wil::err_exception_policy>::attach(
      p_string,
      ppbc);
  RemoteCloudStoreProxy::ConfigureProxySecurity(*(RemoteCloudStoreProxy **)a1, v54);
  v36 = *(struct IUnknown ***)(a1 + 8);
  v37 = v54;
  v38 = *v36;
  *v36 = v54;
  if ( v37 )
    LODWORD(v36) = ((__int64 (__fastcall *)(struct IUnknown *))v37->lpVtbl->AddRef)(v37);
  if ( v38 )
    LODWORD(v36) = ((__int64 (__fastcall *)(struct IUnknown *))v38->lpVtbl->Release)(v38);
  if ( v54 )
    LODWORD(v36) = ((__int64 (__fastcall *)(struct IUnknown *))v54->lpVtbl->Release)(v54);
  if ( v52 )
    LODWORD(v36) = ((__int64 (__fastcall *)(struct IUnknown *))v52->lpVtbl->Release)(v52);
  if ( v53 )
    LODWORD(v36) = ((__int64 (__fastcall *)(struct IUnknown *))v53->lpVtbl->Release)(v53);
  if ( v55 )
    LODWORD(v36) = (*(__int64 (__fastcall **)(__int64 *))(*v55 + 16))(v55);
  if ( pbc )
    LODWORD(v36) = ((__int64 (__fastcall *)(IBindCtx *))pbc->lpVtbl->Release)(pbc);
  if ( string )
    LODWORD(v36) = WindowsDeleteString(string);
  if ( v57 )
    LODWORD(v36) = WindowsDeleteString(v57);
  if ( v58 )
    LODWORD(v36) = WindowsDeleteString(v58);
  return (int)v36;
}

```

## disassembly

```asm
0x18000e008  push    rbp
0x18000e00a  push    rbx
0x18000e00b  push    rsi
0x18000e00c  push    rdi
0x18000e00d  lea     rbp, [rsp-288h]
0x18000e015  sub     rsp, 388h
0x18000e01c  mov     rax, cs:__security_cookie
0x18000e023  xor     rax, rsp
0x18000e026  mov     [rbp+2A0h+var_30], rax
0x18000e02d  mov     rdi, rcx
0x18000e030  xor     esi, esi
0x18000e032  mov     [rsp+3A0h+var_350], sil
0x18000e037  call    cs:__imp_GetCurrentProcess
0x18000e03d  mov     rcx, rax; ProcessHandle
0x18000e040  lea     rdx, [rsp+3A0h+var_350]; void *
0x18000e045  call    ?IsProcessAppContainer@CallerIdentity@@YAJPEAXPEA_N@Z; CallerIdentity::IsProcessAppContainer(void *,bool *)
0x18000e04a  mov     rcx, [rbp+2A8h]; this
0x18000e051  test    eax, eax
0x18000e053  jns     short loc_18000E06A
0x18000e055  mov     r9d, eax; char *
0x18000e058  lea     r8, aOnecoreuapShel_13; "onecoreuap\\shell\\cloudstore\\store\\a"...
0x18000e05f  mov     edx, 293h; void *
0x18000e064  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18000e06a  mov     rcx, [rbp+2A8h]; this
0x18000e071  cmp     [rsp+3A0h+var_350], sil
0x18000e076  jz      short loc_18000E090
0x18000e078  mov     r9d, 80070005h; char *
0x18000e07e  lea     r8, aOnecoreuapShel_13; "onecoreuap\\shell\\cloudstore\\store\\a"...
0x18000e085  mov     edx, 294h; void *
0x18000e08a  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x18000e090  mov     [rsp+3A0h+TokenInformation], esi
0x18000e094  mov     [rbp+2A0h+var_318], esi
0x18000e097  mov     rax, [rdi]
0x18000e09a  mov     rcx, [rax+50h]
0x18000e09e  test    rcx, rcx
0x18000e0a1  jz      short loc_18000E0A8
0x18000e0a3  mov     rcx, [rcx]
0x18000e0a6  jmp     short loc_18000E0AB
0x18000e0a8  mov     rcx, rsi; TokenHandle
0x18000e0ab  mov     rbx, [rbp+2A8h]
0x18000e0b2  lea     rax, [rbp+2A0h+var_318]
0x18000e0b6  mov     [rsp+3A0h+ReturnLength], rax; int
0x18000e0bb  mov     r9d, 4; TokenInformationLength
0x18000e0c1  lea     r8, [rsp+3A0h+TokenInformation]; TokenInformation
0x18000e0c6  lea     edx, [r9+8]; TokenInformationClass
0x18000e0ca  call    cs:__imp_GetTokenInformation
0x18000e0d0  test    eax, eax
0x18000e0d2  jnz     short loc_18000E0E9
0x18000e0d4  lea     r8, aOnecoreuapShel_13; "onecoreuap\\shell\\cloudstore\\store\\a"...
0x18000e0db  mov     edx, 29Bh; void *
0x18000e0e0  mov     rcx, rbx; this
0x18000e0e3  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18000e0e9  cmp     [rbp+2A0h+var_318], 4
0x18000e0ed  setnz   al
0x18000e0f0  mov     rcx, [rbp+2A8h]; this
0x18000e0f7  test    al, al
0x18000e0f9  jz      short loc_18000E10D
0x18000e0fb  lea     r8, aOnecoreuapShel_13; "onecoreuap\\shell\\cloudstore\\store\\a"...
0x18000e102  mov     edx, 29Ch; void *
0x18000e107  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18000e10d  cmp     [rsp+3A0h+TokenInformation], esi
0x18000e111  setz    al
0x18000e114  mov     rcx, [rbp+2A8h]; this
0x18000e11b  test    al, al
0x18000e11d  jz      short loc_18000E137
0x18000e11f  mov     r9d, 80070032h; char *
0x18000e125  lea     r8, aOnecoreuapShel_13; "onecoreuap\\shell\\cloudstore\\store\\a"...
0x18000e12c  mov     edx, 29Dh; void *
0x18000e131  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x18000e137  mov     [rbp+2A0h+var_2D0], rsi
0x18000e13b  mov     rax, [rdi]
0x18000e13e  cmp     [rax+78h], rsi
0x18000e142  jz      short loc_18000E198
0x18000e144  lea     rcx, [rsp+3A0h+var_328]
0x18000e149  call    ??$GetActivationFactory@UISignInStateManager@Internal@System@Windows@@@wil@@YA?AV?$com_ptr_t@UISignInStateManager@Internal@System@Windows@@Uerr_exception_policy@wil@@@0@PEBG@Z; wil::GetActivationFactory<Windows::System::Internal::ISignInStateManager>(ushort const *)
0x18000e14e  nop
0x18000e14f  mov     rcx, [rsp+3A0h+var_328]
0x18000e154  mov     rax, [rcx]
0x18000e157  mov     rdx, [rdi]
0x18000e15a  lea     r8, [rbp+2A0h+var_2D0]
0x18000e15e  mov     rdx, [rdx+78h]
0x18000e162  mov     rax, [rax+88h]
0x18000e169  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e16e  mov     rcx, [rbp+2A8h]; this
0x18000e175  test    eax, eax
0x18000e177  jns     short loc_18000E18E
0x18000e179  mov     r9d, eax; char *
0x18000e17c  lea     r8, aOnecoreuapShel_13; "onecoreuap\\shell\\cloudstore\\store\\a"...
0x18000e183  mov     edx, 2A4h; void *
0x18000e188  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18000e18e  lea     rcx, [rsp+3A0h+var_328]
0x18000e193  call    ??1?$com_ptr_t@V?$AgileVector@PEAVCloudStoreData@Cloud@Storage@Internal@Windows@@U?$DefaultEqualityPredicate@PEAVCloudStoreData@Cloud@Storage@Internal@Windows@@@4Collections@Foundation@5@U?$DefaultLifetimeTraits@PEAVCloudStoreData@Cloud@Storage@Internal@Windows@@@4785@$0A@@Internal@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>(void)
0x18000e198  mov     [rbp+2A0h+var_2E0], rsi
0x18000e19c  mov     [rbp+2A0h+var_2E8], rsi
0x18000e1a0  mov     [rbp+2A0h+string], rsi
0x18000e1a4  mov     rax, [rdi]
0x18000e1a7  mov     rcx, [rax+80h]
0x18000e1ae  test    rcx, rcx
0x18000e1b1  jz      loc_18000E33F
0x18000e1b7  mov     [rsp+3A0h+var_328], rsi
0x18000e1bc  mov     rax, [rcx]
0x18000e1bf  lea     rdx, [rsp+3A0h+var_328]
0x18000e1c4  mov     [rsp+3A0h+var_348], rdx
0x18000e1c9  mov     [rsp+3A0h+ppbc], rsi
0x18000e1ce  mov     [rsp+3A0h+var_338], 1
0x18000e1d3  lea     rdx, [rsp+3A0h+ppbc]
0x18000e1d8  mov     rax, [rax+30h]
0x18000e1dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e1e1  mov     rcx, [rbp+2A8h]; this
0x18000e1e8  test    eax, eax
0x18000e1ea  jns     short loc_18000E201
0x18000e1ec  mov     r9d, eax; char *
0x18000e1ef  lea     r8, aOnecoreuapShel_13; "onecoreuap\\shell\\cloudstore\\store\\a"...
0x18000e1f6  mov     edx, 2AEh; void *
0x18000e1fb  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18000e201  lea     rcx, [rsp+3A0h+var_348]
0x18000e206  call    ??1?$out_param_t@V?$com_ptr_t@U?$IAsyncOperation@PEAVGetDefaultSignInAccountResult@Web@Authentication@Security@Internal@Windows@@@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *>,wil::err_exception_policy>>::~out_param_t<wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *>,wil::err_exception_policy>>(void)
0x18000e20b  mov     rcx, [rsp+3A0h+var_328]
0x18000e210  mov     rax, [rcx]
0x18000e213  lea     rdx, [rbp+2A0h+var_2E0]
0x18000e217  mov     [rsp+3A0h+var_348], rdx
0x18000e21c  mov     [rsp+3A0h+ppbc], rsi
0x18000e221  mov     [rsp+3A0h+var_338], 1
0x18000e226  lea     rdx, [rsp+3A0h+ppbc]
0x18000e22b  mov     rax, [rax+30h]
0x18000e22f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e234  mov     rcx, [rbp+2A8h]; this
0x18000e23b  test    eax, eax
0x18000e23d  jns     short loc_18000E254
0x18000e23f  mov     r9d, eax; char *
0x18000e242  lea     r8, aOnecoreuapShel_13; "onecoreuap\\shell\\cloudstore\\store\\a"...
0x18000e249  mov     edx, 2AFh; void *
0x18000e24e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18000e254  lea     rcx, [rsp+3A0h+var_348]
0x18000e259  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>(void)
0x18000e25e  lea     rdx, [rbp+2A0h+var_2D8]
0x18000e262  lea     rcx, [rsp+3A0h+var_328]
0x18000e267  call    ??$query@UIWebAccountProvider2@Credentials@Security@Windows@@@?$com_ptr_t@UIWebAccountProvider@Credentials@Security@Windows@@Uerr_exception_policy@wil@@@wil@@QEBA?AV?$com_ptr_t@UIWebAccountProvider2@Credentials@Security@Windows@@Uerr_exception_policy@wil@@@1@XZ; wil::com_ptr_t<Windows::Security::Credentials::IWebAccountProvider,wil::err_exception_policy>::query<Windows::Security::Credentials::IWebAccountProvider2>(void)
0x18000e26c  nop
0x18000e26d  mov     rcx, [rax]
0x18000e270  mov     rax, [rcx]
0x18000e273  lea     rdx, [rbp+2A0h+var_2E8]
0x18000e277  mov     [rsp+3A0h+var_348], rdx
0x18000e27c  mov     [rsp+3A0h+ppbc], rsi
0x18000e281  mov     [rsp+3A0h+var_338], 1
0x18000e286  lea     rdx, [rsp+3A0h+ppbc]
0x18000e28b  mov     rax, [rax+38h]
0x18000e28f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e294  mov     rcx, [rbp+2A8h]; this
0x18000e29b  test    eax, eax
0x18000e29d  jns     short loc_18000E2B4
0x18000e29f  mov     r9d, eax; char *
0x18000e2a2  lea     r8, aOnecoreuapShel_13; "onecoreuap\\shell\\cloudstore\\store\\a"...
0x18000e2a9  mov     edx, 2B0h; void *
0x18000e2ae  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18000e2b4  lea     rcx, [rsp+3A0h+var_348]
0x18000e2b9  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>(void)
0x18000e2be  nop
0x18000e2bf  lea     rcx, [rbp+2A0h+var_2D8]
0x18000e2c3  call    ??1?$com_ptr_t@V?$AgileVector@PEAVCloudStoreData@Cloud@Storage@Internal@Windows@@U?$DefaultEqualityPredicate@PEAVCloudStoreData@Cloud@Storage@Internal@Windows@@@4Collections@Foundation@5@U?$DefaultLifetimeTraits@PEAVCloudStoreData@Cloud@Storage@Internal@Windows@@@4785@$0A@@Internal@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>(void)
0x18000e2c8  mov     rcx, [rdi]
0x18000e2cb  sub     rcx, 0FFFFFFFFFFFFFF80h
0x18000e2cf  lea     rdx, [rbp+2A0h+var_2D8]
0x18000e2d3  call    ??$query@UIWebAccount2@Credentials@Security@Windows@@@?$com_ptr_t@UIWebAccount@Credentials@Security@Windows@@Uerr_exception_policy@wil@@@wil@@QEBA?AV?$com_ptr_t@UIWebAccount2@Credentials@Security@Windows@@Uerr_exception_policy@wil@@@1@XZ; wil::com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>::query<Windows::Security::Credentials::IWebAccount2>(void)
0x18000e2d8  nop
0x18000e2d9  mov     rcx, [rax]
0x18000e2dc  mov     rax, [rcx]
0x18000e2df  lea     rdx, [rbp+2A0h+string]
0x18000e2e3  mov     [rsp+3A0h+var_348], rdx
0x18000e2e8  mov     [rsp+3A0h+ppbc], rsi
0x18000e2ed  mov     [rsp+3A0h+var_338], 1
0x18000e2f2  lea     rdx, [rsp+3A0h+ppbc]
0x18000e2f7  mov     rax, [rax+30h]
0x18000e2fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e300  mov     rcx, [rbp+2A8h]; this
0x18000e307  test    eax, eax
0x18000e309  jns     short loc_18000E320
0x18000e30b  mov     r9d, eax; char *
0x18000e30e  lea     r8, aOnecoreuapShel_13; "onecoreuap\\shell\\cloudstore\\store\\a"...
0x18000e315  mov     edx, 2B1h; void *
0x18000e31a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18000e320  lea     rcx, [rsp+3A0h+var_348]
0x18000e325  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>(void)
0x18000e32a  nop
0x18000e32b  lea     rcx, [rbp+2A0h+var_2D8]
0x18000e32f  call    ??1?$com_ptr_t@V?$AgileVector@PEAVCloudStoreData@Cloud@Storage@Internal@Windows@@U?$DefaultEqualityPredicate@PEAVCloudStoreData@Cloud@Storage@Internal@Windows@@@4Collections@Foundation@5@U?$DefaultLifetimeTraits@PEAVCloudStoreData@Cloud@Storage@Internal@Windows@@@4785@$0A@@Internal@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>(void)
0x18000e334  nop
0x18000e335  lea     rcx, [rsp+3A0h+var_328]
0x18000e33a  call    ??1?$com_ptr_t@V?$AgileVector@PEAVCloudStoreData@Cloud@Storage@Internal@Windows@@U?$DefaultEqualityPredicate@PEAVCloudStoreData@Cloud@Storage@Internal@Windows@@@4Collections@Foundation@5@U?$DefaultLifetimeTraits@PEAVCloudStoreData@Cloud@Storage@Internal@Windows@@@4785@$0A@@Internal@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>(void)
0x18000e33f  mov     rbx, [rbp+2A8h]
0x18000e346  mov     r8d, 28h ; '('; cchMax
0x18000e34c  lea     rdx, [rbp+2A0h+sz]; lpsz
0x18000e350  lea     rcx, _GUID_d4872b74_3afc_47cd_b8a2_9e4f998539bc; rguid
0x18000e357  call    cs:__imp_StringFromGUID2
0x18000e35d  test    eax, eax
0x18000e35f  jnz     short loc_18000E37C
0x18000e361  mov     r9d, 8007007Ah; char *
0x18000e367  lea     r8, aOnecoreuapShel_13; "onecoreuap\\shell\\cloudstore\\store\\a"...
0x18000e36e  mov     edx, 2B5h; void *
0x18000e373  mov     rcx, rbx; this
0x18000e376  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18000e37c  lea     rax, [rbp+2A0h+sz]
0x18000e380  mov     [rsp+3A0h+ReturnLength], rax; int
0x18000e385  mov     r9d, [rsp+3A0h+TokenInformation]
0x18000e38a  lea     r8, aSessionUClsidS; "Session:%u!clsid:%s"
0x18000e391  mov     edx, 104h; unsigned __int64
0x18000e396  lea     rcx, [rbp+2A0h+szDisplayName]; unsigned __int16 *
0x18000e39a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000e39f  mov     rcx, [rbp+2A8h]; this
0x18000e3a6  test    eax, eax
0x18000e3a8  jns     short loc_18000E3BF
0x18000e3aa  mov     r9d, eax; char *
0x18000e3ad  lea     r8, aOnecoreuapShel_13; "onecoreuap\\shell\\cloudstore\\store\\a"...
0x18000e3b4  mov     edx, 2B8h; void *
0x18000e3b9  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18000e3bf  mov     [rbp+2A0h+pbc], rsi
0x18000e3c3  lea     rax, [rbp+2A0h+pbc]
0x18000e3c7  mov     [rsp+3A0h+var_348], rax
0x18000e3cc  mov     [rsp+3A0h+ppbc], rsi
0x18000e3d1  mov     [rsp+3A0h+var_338], 1
0x18000e3d6  lea     rdx, [rsp+3A0h+ppbc]; ppbc
0x18000e3db  xor     ecx, ecx; reserved
0x18000e3dd  call    cs:__imp_CreateBindCtx
0x18000e3e3  mov     rcx, [rbp+2A8h]; this
0x18000e3ea  test    eax, eax
0x18000e3ec  jns     short loc_18000E403
0x18000e3ee  mov     r9d, eax; char *
0x18000e3f1  lea     r8, aOnecoreuapShel_13; "onecoreuap\\shell\\cloudstore\\store\\a"...
0x18000e3f8  mov     edx, 2BBh; void *
0x18000e3fd  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18000e403  cmp     [rsp+3A0h+var_338], sil
0x18000e408  jz      short loc_18000E42C
0x18000e40a  mov     rdx, [rsp+3A0h+ppbc]
0x18000e40f  mov     rax, [rsp+3A0h+var_348]
0x18000e414  mov     rcx, [rax]
0x18000e417  mov     [rax], rdx
0x18000e41a  test    rcx, rcx
0x18000e41d  jz      short loc_18000E42C
0x18000e41f  mov     rax, [rcx]
0x18000e422  mov     rax, [rax+10h]
0x18000e426  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e42b  nop
0x18000e42c  xorps   xmm0, xmm0
0x18000e42f  movups  [rbp+2A0h+var_2C8], xmm0
0x18000e433  movups  [rbp+2A0h+var_2B8], xmm0
0x18000e437  movups  [rbp+2A0h+var_2A8], xmm0
0x18000e43b  mov     dword ptr [rbp+2A0h+var_2C8], 30h ; '0'
0x18000e442  mov     rcx, [rbp+2A0h+pbc]
0x18000e446  mov     rax, [rcx]
0x18000e449  lea     rdx, [rbp+2A0h+var_2C8]
0x18000e44d  mov     rax, [rax+38h]
0x18000e451  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e456  mov     rcx, [rbp+2A8h]; this
0x18000e45d  test    eax, eax
0x18000e45f  jns     short loc_18000E476
0x18000e461  mov     r9d, eax; char *
0x18000e464  lea     r8, aOnecoreuapShel_13; "onecoreuap\\shell\\cloudstore\\store\\a"...
0x18000e46b  mov     edx, 2BFh; void *
0x18000e470  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18000e476  mov     dword ptr [rbp+2A0h+var_2B8+4], 4
0x18000e47d  mov     rcx, [rbp+2A0h+pbc]
0x18000e481  mov     rax, [rcx]
0x18000e484  lea     rdx, [rbp+2A0h+var_2C8]
0x18000e488  mov     rax, [rax+30h]
0x18000e48c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e491  mov     rcx, [rbp+2A8h]; this
0x18000e498  test    eax, eax
0x18000e49a  jns     short loc_18000E4B1
0x18000e49c  mov     r9d, eax; char *
0x18000e49f  lea     r8, aOnecoreuapShel_13; "onecoreuap\\shell\\cloudstore\\store\\a"...
0x18000e4a6  mov     edx, 2C1h; void *
0x18000e4ab  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18000e4b1  mov     [rbp+2A0h+pchEaten], esi
0x18000e4b4  mov     [rbp+2A0h+var_2F8], rsi
0x18000e4b8  lea     rax, [rbp+2A0h+var_2F8]
0x18000e4bc  mov     [rsp+3A0h+var_348], rax
0x18000e4c1  mov     [rsp+3A0h+ppbc], rsi
0x18000e4c6  mov     [rsp+3A0h+var_338], 1
0x18000e4cb  lea     r9, [rsp+3A0h+ppbc]; ppmk
0x18000e4d0  lea     r8, [rbp+2A0h+pchEaten]; pchEaten
0x18000e4d4  lea     rdx, [rbp+2A0h+szDisplayName]; szDisplayName
0x18000e4d8  mov     rcx, [rbp+2A0h+pbc]; pbc
0x18000e4dc  call    cs:__imp_MkParseDisplayNameEx
0x18000e4e2  mov     rcx, [rbp+2A8h]; this
0x18000e4e9  test    eax, eax
0x18000e4eb  jns     short loc_18000E502
0x18000e4ed  mov     r9d, eax; char *
0x18000e4f0  lea     r8, aOnecoreuapShel_13; "onecoreuap\\shell\\cloudstore\\store\\a"...
0x18000e4f7  mov     edx, 2C5h; void *
0x18000e4fc  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18000e502  cmp     [rsp+3A0h+var_338], sil
0x18000e507  jz      short loc_18000E52B
0x18000e509  mov     rdx, [rsp+3A0h+ppbc]
0x18000e50e  mov     rax, [rsp+3A0h+var_348]
0x18000e513  mov     rcx, [rax]
0x18000e516  mov     [rax], rdx
0x18000e519  test    rcx, rcx
0x18000e51c  jz      short loc_18000E52B
0x18000e51e  mov     rax, [rcx]
0x18000e521  mov     rax, [rax+10h]
  ... truncated ...
```
