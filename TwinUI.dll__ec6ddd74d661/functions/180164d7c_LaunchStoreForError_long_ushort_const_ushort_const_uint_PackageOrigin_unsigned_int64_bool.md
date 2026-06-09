# LaunchStoreForError(long,ushort const *,ushort const *,uint,_PackageOrigin,unsigned __int64,bool)

- ea: `0x180164d7c`
- end: `0x1801657eb`
- name: `?LaunchStoreForError@@YAJJPEBG0IW4_PackageOrigin@@_K_N@Z`
- size: `2671`
- prototype: `int __high(int, const unsigned __int16 *, const unsigned __int16 *, unsigned int, enum _PackageOrigin, unsigned __int64, bool)`
- caller_count: `1`
- callee_count: `21`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180161a40`

## callees

- `0x180009dd0`
- `0x180009dfc`
- `0x18001c710`
- `0x18002fb8c`
- `0x1800378dc`
- `0x180041d1c`
- `0x180041f54`
- `0x180043bac`
- `0x180053740`
- `0x1800651dc`
- `0x180077dc8`
- `0x180080e10`
- `0x1800a6704`
- `0x1800f8fd4`
- `0x180108c7c`
- `0x180142e10`
- `0x1801613d4`
- `0x180161418`
- `0x180164d7c`
- `0x1801657f4`
- `0x1803bb010`

## import_xrefs

- `SHELL32!ShellExecuteW` at `0x18016506a`
- `SHELL32!ShellExecuteW` at `0x18016506a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18016501c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801654af`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180165506`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180165577`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18016568b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180165702`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180165799`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18016501c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801654af`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180165506`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180165577`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18016568b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180165702`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180165799`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801654dc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801654dc`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18016503d`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18016503d`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18016527f`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18016527f`
- `api-ms-win-shell-namespace-l1-1-0!SHCreateItemFromParsingName` at `0x180165185`
- `api-ms-win-shell-namespace-l1-1-0!SHCreateItemFromParsingName` at `0x180165185`
- `api-ms-win-appmodel-runtime-l1-1-0!PackageFamilyNameFromFullName` at `0x180164dcf`
- `api-ms-win-appmodel-runtime-l1-1-0!PackageFamilyNameFromFullName` at `0x180164dcf`
- `api-ms-win-shell-namespace-l1-1-1!SHCreateShellItemArrayFromShellItem` at `0x1801651d7`
- `api-ms-win-shell-namespace-l1-1-1!SHCreateShellItemArrayFromShellItem` at `0x1801651d7`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpIW` at `0x1801654f2`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpIW` at `0x1801654f2`

## string_xrefs

- `0x1801652c6`: `Windows.Foundation.ExtensionCatalog`
- `0x180164e08`: `Microsoft.GamingServices_8wekyb3d8bbwe`
- `0x180165358`: `Windows.Protocol`
- `0x1801655c2`: `Windows.Protocol`

## pseudocode

```c
// Hidden C++ exception states: #wind=20
int __fastcall LaunchStoreForError(int a1, const WCHAR *a2, int a3, __int64 a4, __int64 a5, __int64 a6, char a7)
{
  unsigned int v10; // eax
  int v12; // eax
  int v13; // ebx
  char v14; // r15
  int v15; // eax
  __int64 v16; // rdi
  __int64 (__fastcall *v17)(__int64, _QWORD, __int64 *); // rbx
  __int64 v18; // rax
  int v19; // eax
  __int64 v20; // rdx
  unsigned __int64 v21; // rcx
  bool IgnoreListForPFN; // al
  bool v23; // di
  char v24; // cl
  int v25; // edx
  int v26; // eax
  HINSTANCE v27; // rbx
  int v28; // eax
  __int64 v29; // rdx
  HRESULT v30; // eax
  HRESULT v31; // eax
  int v32; // eax
  HRESULT v33; // eax
  int v34; // eax
  __int64 v35; // rsi
  __int64 (__fastcall *v36)(__int64, __int64, __int64, __int64 *); // rdi
  __int64 v37; // rbx
  int v38; // eax
  unsigned __int64 v39; // r9
  __int64 v40; // rdx
  __int64 v41; // rdi
  __int64 (__fastcall *v42)(__int64, __int64 *); // rbx
  int v43; // eax
  __int64 v44; // rdi
  __int64 (__fastcall *v45)(__int64, void **); // rbx
  int v46; // eax
  void *v47; // rdi
  unsigned int (__fastcall *v48)(void *, __int64, struct IInspectable **); // rbx
  int v49; // eax
  const WCHAR *StringRawBuffer; // rax
  LPVOID v51; // rsi
  __int64 (__fastcall *v52)(LPVOID, const WCHAR *, __int64, _QWORD, __int64, void *, int, __int64, unsigned int *); // rdi
  void *v53; // rbx
  unsigned int lpDirectory; // [rsp+20h] [rbp-E0h]
  int lpDirectorya; // [rsp+20h] [rbp-E0h]
  char v56; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v57[7]; // [rsp+51h] [rbp-AFh] BYREF
  HSTRING string; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v59; // [rsp+60h] [rbp-A0h] BYREF
  void *ppv; // [rsp+68h] [rbp-98h] BYREF
  void *v61; // [rsp+70h] [rbp-90h] BYREF
  void *v62; // [rsp+78h] [rbp-88h] BYREF
  __int64 v63; // [rsp+80h] [rbp-80h] BYREF
  LPVOID v64; // [rsp+88h] [rbp-78h] BYREF
  __int64 v65; // [rsp+90h] [rbp-70h] BYREF
  unsigned int v66; // [rsp+98h] [rbp-68h] BYREF
  __int64 v67; // [rsp+A0h] [rbp-60h] BYREF
  void *v68; // [rsp+A8h] [rbp-58h] BYREF
  HSTRING v69; // [rsp+B0h] [rbp-50h] BYREF
  LPCWSTR lpFile; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v71; // [rsp+C0h] [rbp-40h]
  __int64 v72; // [rsp+C8h] [rbp-38h]
  __int64 v73; // [rsp+D0h] [rbp-30h] BYREF
  const WCHAR *v74; // [rsp+D8h] [rbp-28h] BYREF
  UINT32 packageFamilyNameLength; // [rsp+E0h] [rbp-20h] BYREF
  void *v76; // [rsp+E8h] [rbp-18h] BYREF
  int v77; // [rsp+F0h] [rbp-10h]
  __int64 v78; // [rsp+F8h] [rbp-8h] BYREF
  RoVariant *v79; // [rsp+100h] [rbp+0h]
  struct IInspectable *v80; // [rsp+108h] [rbp+8h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+110h] [rbp+10h] BYREF
  __int64 v82; // [rsp+128h] [rbp+28h]
  HSTRING_HEADER v83; // [rsp+130h] [rbp+30h] BYREF
  __int64 v84; // [rsp+148h] [rbp+48h]
  WCHAR packageFamilyName[72]; // [rsp+150h] [rbp+50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+228h] [rbp+128h]

  v74 = a2;
  packageFamilyNameLength = 65;
  v10 = PackageFamilyNameFromFullName(a2, &packageFamilyNameLength, packageFamilyName);
  if ( v10 )
    return wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0xAD,
             (unsigned int)"shell\\twinui\\activationerrorpopup\\lib\\desktopstoreremediationhandler.cpp",
             (const char *)v10,
             lpDirectory);
  if ( a7 )
  {
    v12 = StringCchPrintfW(packageFamilyName, 0x41u, L"%s", L"Microsoft.GamingServices_8wekyb3d8bbwe");
    v13 = v12;
    if ( v12 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xB3,
        (unsigned int)"shell\\twinui\\activationerrorpopup\\lib\\desktopstoreremediationhandler.cpp",
        (const char *)(unsigned int)v12,
        lpDirectory);
      return v13;
    }
    goto LABEL_10;
  }
  v14 = 0;
  if ( a1 == -2147217664 )
  {
    a1 = -2147009284;
  }
  else if ( a1 == -2147217656 )
  {
    a1 = -2147009284;
LABEL_10:
    v14 = 1;
  }
  v73 = 0;
  v82 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Internal.StateRepository.Package",
    0x29u,
    0x28u);
  v15 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackageStatics>>(
          v82,
          &v73);
  v13 = v15;
  if ( v15 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD0,
      (unsigned int)"shell\\twinui\\activationerrorpopup\\lib\\desktopstoreremediationhandler.cpp",
      (const char *)(unsigned int)v15,
      lpDirectory);
LABEL_82:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v73);
    return v13;
  }
  v59 = 0;
  v16 = v73;
  v17 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v73 + 176LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v59);
  v18 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v74);
  v19 = v17(v16, *(_QWORD *)(v18 + 24), &v59);
  v13 = v19;
  if ( v19 < 0 )
  {
    v20 = 210;
LABEL_15:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v20,
      (unsigned int)"shell\\twinui\\activationerrorpopup\\lib\\desktopstoreremediationhandler.cpp",
      (const char *)(unsigned int)v19,
      lpDirectory);
LABEL_81:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v59);
    goto LABEL_82;
  }
  v56 = 0;
  v19 = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v59 + 320LL))(v59, &v56);
  v13 = v19;
  if ( v19 < 0 )
  {
    v20 = 212;
    goto LABEL_15;
  }
  string = 0;
  v66 = 0;
  v21 = -1;
  do
    ++v21;
  while ( packageFamilyName[v21] );
  if ( (int)ULongLongToULong(v21, &v66) >= 0 )
    Microsoft::WRL::Wrappers::HString::Set((Microsoft::WRL::Wrappers::HString *)&string, packageFamilyName, v66);
  IgnoreListForPFN = QueryIgnoreListForPFN((struct Microsoft::WRL::Wrappers::HString *)&string);
  v23 = IgnoreListForPFN;
  v24 = v56;
  if ( v56 )
  {
    v25 = 0;
    if ( !v14 && !IgnoreListForPFN )
    {
      lpFile = 0;
      v71 = 0;
      v72 = 0;
      v26 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::InitializeFormat(
              &lpFile,
              L"msxbox://remediation/?PFN=%s&PN=%s&appUserModelId=%s&errorCode=%d&appxState=%d",
              packageFamilyName,
              a2);
      v13 = v26;
      if ( v26 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xE0,
          (unsigned int)"shell\\twinui\\activationerrorpopup\\lib\\desktopstoreremediationhandler.cpp",
          (const char *)(unsigned int)v26,
          a3);
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&lpFile);
        WindowsDeleteString(string);
        string = 0;
        goto LABEL_81;
      }
      CoInitializeEx(0, 6u);
      v27 = ShellExecuteW(0, L"open", lpFile, 0, 0, 1);
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&lpFile);
      v25 = -2147467259;
      if ( (unsigned __int64)v27 > 0x20 )
        v25 = 0;
      v24 = v56;
    }
    if ( v24 && !v14 && !v23 && v25 >= 0 )
      goto LABEL_70;
  }
  lpFile = 0;
  v71 = 0;
  v72 = 0;
  if ( v14 )
  {
    v28 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::InitializeFormat(
            &lpFile,
            L"ms-windows-store://pdp/?PFN=%s",
            packageFamilyName);
    v13 = v28;
    if ( v28 < 0 )
    {
      v29 = 289;
      goto LABEL_37;
    }
  }
  else
  {
    lpDirectory = a3;
    v28 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::InitializeFormat(
            &lpFile,
            L"ms-windows-store:Remediation?PFN=%s&PN=%s&appUserModelId=%s&errorCode=%d&appxState=%d",
            packageFamilyName,
            a2);
    v13 = v28;
    if ( v28 < 0 )
    {
      v29 = 285;
LABEL_37:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v29,
        (unsigned int)"shell\\twinui\\activationerrorpopup\\lib\\desktopstoreremediationhandler.cpp",
        (const char *)(unsigned int)v28,
        lpDirectory);
LABEL_80:
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&lpFile);
      WindowsDeleteString(string);
      string = 0;
      goto LABEL_81;
    }
  }
  ppv = 0;
  Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&ppv);
  v30 = SHCreateItemFromParsingName(lpFile, 0, &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe, &ppv);
  v13 = v30;
  if ( v30 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x125,
      (unsigned int)"shell\\twinui\\activationerrorpopup\\lib\\desktopstoreremediationhandler.cpp",
      (const char *)(unsigned int)v30,
      lpDirectory);
LABEL_79:
    Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&ppv);
    goto LABEL_80;
  }
  v61 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v61);
  v31 = SHCreateShellItemArrayFromShellItem((IShellItem *)ppv, &GUID_b63ea76d_1f85_456f_a19c_48159efa858b, &v61);
  v13 = v31;
  if ( v31 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x128,
      (unsigned int)"shell\\twinui\\activationerrorpopup\\lib\\desktopstoreremediationhandler.cpp",
      (const char *)(unsigned int)v31,
      lpDirectory);
LABEL_78:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v61);
    goto LABEL_79;
  }
  v62 = 0;
  v68 = v61;
  Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v62);
  v32 = Microsoft::WRL::Details::MakeAndInitialize<CProtocolActivatedEventArgs,Windows::ApplicationModel::Activation::IActivatedEventArgs,IShellItemArray *>(&v62);
  v13 = v32;
  if ( v32 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x12B,
      (unsigned int)"shell\\twinui\\activationerrorpopup\\lib\\desktopstoreremediationhandler.cpp",
      (const char *)(unsigned int)v32,
      lpDirectory);
LABEL_77:
    Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v62);
    goto LABEL_78;
  }
  v64 = 0;
  Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v64);
  v33 = CoCreateInstance(&CLSID_ApplicationActivationManager, 0, 1u, &GUID_54e4c428_d1d4_47d4_ade6_46c829114a7d, &v64);
  v13 = v33;
  if ( v33 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x12F,
      (unsigned int)"shell\\twinui\\activationerrorpopup\\lib\\desktopstoreremediationhandler.cpp",
      (const char *)(unsigned int)v33,
      lpDirectorya);
LABEL_76:
    Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v64);
    goto LABEL_77;
  }
  v67 = 0;
  v82 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Foundation.ExtensionCatalog",
    0x24u,
    0x23u);
  v34 = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Foundation::IExtensionCatalog>>(v82, &v67);
  v13 = v34;
  if ( v34 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x133,
      (unsigned int)"shell\\twinui\\activationerrorpopup\\lib\\desktopstoreremediationhandler.cpp",
      (const char *)(unsigned int)v34,
      lpDirectorya);
LABEL_75:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v67);
    goto LABEL_76;
  }
  v63 = 0;
  v35 = v67;
  v36 = *(__int64 (__fastcall **)(__int64, __int64, __int64, __int64 *))(*(_QWORD *)v67 + 56LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v63);
  v82 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Microsoft.WindowsStore_8wekyb3d8bbwe",
    0x25u,
    0x24u);
  v37 = v82;
  v84 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&v83, L"Windows.Protocol", 0x11u, 0x10u);
  v38 = v36(v35, v84, v37, &v63);
  v13 = v38;
  if ( v38 < 0 )
  {
    v39 = (unsigned int)v38;
    v40 = 314;
LABEL_73:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v40,
      (unsigned int)"shell\\twinui\\activationerrorpopup\\lib\\desktopstoreremediationhandler.cpp",
      (const char *)v39,
      lpDirectorya);
LABEL_74:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v63);
    goto LABEL_75;
  }
  v78 = 0;
  v74 = 0;
  v57[0] = 0;
  while ( 1 )
  {
    v13 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v63 + 56LL))(v63, v57);
    if ( v13 < 0 )
    {
      v39 = (unsigned int)v13;
      v40 = 348;
      goto LABEL_73;
    }
    if ( !v57[0] )
      goto LABEL_63;
    v65 = 0;
    v41 = v63;
    v42 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v63 + 48LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v65);
    v43 = v42(v41, &v65);
    v13 = v43;
    if ( v43 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x145,
        (unsigned int)"shell\\twinui\\activationerrorpopup\\lib\\desktopstoreremediationhandler.cpp",
        (const char *)(unsigned int)v43,
        lpDirectorya);
      goto LABEL_69;
    }
    v68 = 0;
    v44 = v65;
    v45 = *(__int64 (__fastcall **)(__int64, void **))(*(_QWORD *)v65 + 128LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v68);
    v46 = v45(v44, &v68);
    v13 = v46;
    if ( v46 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x149,
        (unsigned int)"shell\\twinui\\activationerrorpopup\\lib\\desktopstoreremediationhandler.cpp",
        (const char *)(unsigned int)v46,
        lpDirectorya);
      goto LABEL_66;
    }
    v76 = 0;
    v77 = 0;
    v47 = v68;
    v48 = *(unsigned int (__fastcall **)(void *, __int64, struct IInspectable **))(*(_QWORD *)v68 + 48LL);
    v79 = (RoVariant *)&v76;
    v80 = 0;
    v82 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"Name", 5u, 4u);
    LODWORD(v48) = v48(v47, v82, &v80) >> 31;
    v82 = 0;
    RoVariant::Attach(v79, v80);
    if ( (unsigned __int8)v48 != 1 )
      break;
LABEL_61:
    RoVariant::~RoVariant((RoVariant *)&v76);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v68);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v65);
    (*(void (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v63 + 64LL))(v63, v57);
  }
  v69 = 0;
  v83.Reserved.Reserved1 = v76;
  *(_DWORD *)&v83.Reserved.Reserved2[8] = v77;
  WindowsDeleteString(0);
  v69 = 0;
  v49 = RoVariant::Accessor::GetString((RoVariant::Accessor *)&v83, &v69);
  v13 = v49;
  if ( v49 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x14E,
      (unsigned int)"shell\\twinui\\activationerrorpopup\\lib\\desktopstoreremediationhandler.cpp",
      (const char *)(unsigned int)v49,
      lpDirectorya);
    WindowsDeleteString(v69);
    v69 = 0;
    RoVariant::~RoVariant((RoVariant *)&v76);
LABEL_66:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v68);
LABEL_69:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v65);
    goto LABEL_74;
  }
  StringRawBuffer = WindowsGetStringRawBuffer(v69, 0);
  if ( StrCmpIW(L"ms-windows-store", StringRawBuffer) )
  {
    WindowsDeleteString(v69);
    goto LABEL_61;
  }
  (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v65 + 48LL))(v65, &v78);
  (*(void (__fastcall **)(__int64, const WCHAR **))(*(_QWORD *)v65 + 64LL))(v65, &v74);
  WindowsDeleteString(v69);
  v69 = 0;
  RoVariant::~RoVariant((RoVariant *)&v76);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v68);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v65);
LABEL_63:
  v66 = 0;
  v51 = v64;
  v52 = *(__int64 (__fastcall **)(LPVOID, const WCHAR *, __int64, _QWORD, __int64, void *, int, __int64, unsigned int *))(*(_QWORD *)v64 + 120LL);
  v53 = v62;
  v82 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"Windows.Protocol", 0x11u, 0x10u);
  LODWORD(v53) = v52(v51, v74, v78, 0, v82, v53, 0x80000, a6, &v66);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v63);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v67);
  Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v64);
  Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v62);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v61);
  Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&ppv);
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&lpFile);
  if ( (int)v53 < 0 )
    goto LABEL_71;
LABEL_70:
  a1 = 2556504;
LABEL_71:
  WindowsDeleteString(string);
  string = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v59);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v73);
  return a1;
}

```

## disassembly

```asm
0x180164d7c  mov     [rsp-8+arg_0], rbx
0x180164d81  push    rbp
0x180164d82  push    rsi
0x180164d83  push    rdi
0x180164d84  push    r12
0x180164d86  push    r13
0x180164d88  push    r14
0x180164d8a  push    r15
0x180164d8c  lea     rbp, [rsp-0F0h]
0x180164d94  sub     rsp, 1F0h
0x180164d9b  mov     rax, cs:__security_cookie
0x180164da2  xor     rax, rsp
0x180164da5  mov     [rbp+120h+var_40], rax
0x180164dac  mov     esi, r9d
0x180164daf  mov     r13, r8
0x180164db2  mov     r12, rdx
0x180164db5  mov     r14d, ecx
0x180164db8  mov     [rbp+120h+var_148], rdx
0x180164dbc  mov     ebx, 41h ; 'A'
0x180164dc1  mov     [rbp+120h+packageFamilyNameLength], ebx
0x180164dc4  lea     r8, [rbp+120h+packageFamilyName]; packageFamilyName
0x180164dc8  lea     rdx, [rbp+120h+packageFamilyNameLength]; packageFamilyNameLength
0x180164dcc  mov     rcx, r12; packageFullName
0x180164dcf  call    cs:__imp_PackageFamilyNameFromFullName
0x180164dd6  nop     dword ptr [rax+rax+00h]
0x180164ddb  xor     edi, edi
0x180164ddd  test    eax, eax
0x180164ddf  jz      short loc_180164DFF
0x180164de1  mov     rcx, [rbp+128h]; this
0x180164de8  mov     r9d, eax; char *
0x180164deb  lea     r8, aShellTwinuiAct_0; "shell\\twinui\\activationerrorpopup\\li"...
0x180164df2  lea     edx, [rbx+6Ch]; void *
0x180164df5  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180164dfa  jmp     loc_1801657C0
0x180164dff  cmp     [rbp+120h+arg_30], dil
0x180164e06  jz      short loc_180164E48
0x180164e08  lea     r9, aMicrosoftGamin; "Microsoft.GamingServices_8wekyb3d8bbwe"
0x180164e0f  lea     r8, aS_5; "%s"
0x180164e16  mov     rdx, rbx; unsigned __int64
0x180164e19  lea     rcx, [rbp+120h+packageFamilyName]; unsigned __int16 *
0x180164e1d  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180164e22  mov     ebx, eax
0x180164e24  test    eax, eax
0x180164e26  jns     short loc_180164E6B
0x180164e28  mov     rcx, [rbp+128h]; this
0x180164e2f  mov     r9d, eax; char *
0x180164e32  lea     r8, aShellTwinuiAct_0; "shell\\twinui\\activationerrorpopup\\li"...
0x180164e39  mov     edx, 0B3h; void *
0x180164e3e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180164e43  jmp     loc_1801657BE
0x180164e48  mov     r15b, dil
0x180164e4b  cmp     r14d, 80040F00h
0x180164e52  jnz     short loc_180164E5C
0x180164e54  mov     r14d, 80073CFCh
0x180164e5a  jmp     short loc_180164E6E
0x180164e5c  cmp     r14d, 80040F08h
0x180164e63  jnz     short loc_180164E6E
0x180164e65  mov     r14d, 80073CFCh
0x180164e6b  mov     r15b, 1
0x180164e6e  mov     [rbp+120h+var_150], rdi
0x180164e72  mov     [rbp+120h+var_F8], rdi
0x180164e76  mov     r9d, 28h ; '('; unsigned int
0x180164e7c  lea     r8d, [r9+1]; unsigned int
0x180164e80  lea     rdx, ?RuntimeClass_Windows_Internal_StateRepository_Package@@3QBGB; "Windows.Internal.StateRepository.Packag"...
0x180164e87  lea     rcx, [rbp+120h+hstringHeader]; hstringHeader
0x180164e8b  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180164e90  lea     rdx, [rbp+120h+var_150]
0x180164e94  mov     rcx, [rbp+120h+var_F8]
0x180164e98  call    ??$GetActivationFactory@V?$ComPtr@UIPackageStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIPackageStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackageStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackageStatics>>)
0x180164e9d  mov     ebx, eax
0x180164e9f  test    eax, eax
0x180164ea1  jns     short loc_180164EC3
0x180164ea3  mov     rcx, [rbp+128h]; this
0x180164eaa  mov     r9d, eax; char *
0x180164ead  lea     r8, aShellTwinuiAct_0; "shell\\twinui\\activationerrorpopup\\li"...
0x180164eb4  mov     edx, 0D0h; void *
0x180164eb9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180164ebe  jmp     loc_1801657B5
0x180164ec3  mov     [rsp+220h+var_1C0], rdi
0x180164ec8  mov     rdi, [rbp+120h+var_150]
0x180164ecc  mov     rax, [rdi]
0x180164ecf  mov     rbx, [rax+0B0h]
0x180164ed6  lea     rcx, [rsp+220h+var_1C0]
0x180164edb  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180164ee0  lea     rdx, [rbp+120h+var_148]
0x180164ee4  lea     rcx, [rbp+120h+hstringHeader]
0x180164ee8  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180164eed  nop
0x180164eee  lea     r8, [rsp+220h+var_1C0]
0x180164ef3  mov     rdx, [rax+18h]
0x180164ef7  mov     rcx, rdi
0x180164efa  mov     rax, rbx
0x180164efd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180164f02  mov     ebx, eax
0x180164f04  xor     edi, edi
0x180164f06  test    eax, eax
0x180164f08  jns     short loc_180164F2A
0x180164f0a  mov     edx, 0D2h; void *
0x180164f0f  lea     r8, aShellTwinuiAct_0; "shell\\twinui\\activationerrorpopup\\li"...
0x180164f16  mov     r9d, eax; char *
0x180164f19  mov     rcx, [rbp+128h]; this
0x180164f20  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180164f25  jmp     loc_1801657AA
0x180164f2a  mov     [rsp+220h+var_1D0], dil
0x180164f2f  mov     rcx, [rsp+220h+var_1C0]
0x180164f34  mov     rax, [rcx]
0x180164f37  lea     rdx, [rsp+220h+var_1D0]
0x180164f3c  mov     rax, [rax+140h]
0x180164f43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180164f48  mov     ebx, eax
0x180164f4a  test    eax, eax
0x180164f4c  jns     short loc_180164F55
0x180164f4e  mov     edx, 0D4h
0x180164f53  jmp     short loc_180164F0F
0x180164f55  xor     ebx, ebx
0x180164f57  mov     [rsp+220h+string], rbx
0x180164f5c  mov     [rbp+120h+var_188], ebx
0x180164f5f  lea     rax, [rbp+120h+packageFamilyName]
0x180164f63  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180164f67  inc     rcx; unsigned __int64
0x180164f6a  cmp     [rax+rcx*2], bx
0x180164f6e  jnz     short loc_180164F67
0x180164f70  lea     rdx, [rbp+120h+var_188]; unsigned int *
0x180164f74  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x180164f79  test    eax, eax
0x180164f7b  js      short loc_180164F8F
0x180164f7d  mov     r8d, [rbp+120h+var_188]; unsigned int
0x180164f81  lea     rdx, [rbp+120h+packageFamilyName]; unsigned __int16 *
0x180164f85  lea     rcx, [rsp+220h+string]; this
0x180164f8a  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJPEBGI@Z; Microsoft::WRL::Wrappers::HString::Set(ushort const *,uint)
0x180164f8f  lea     rcx, [rsp+220h+string]; struct Microsoft::WRL::Wrappers::HString *
0x180164f94  call    ?QueryIgnoreListForPFN@@YA_NAEAVHString@Wrappers@WRL@Microsoft@@@Z; QueryIgnoreListForPFN(Microsoft::WRL::Wrappers::HString &)
0x180164f99  mov     dil, al
0x180164f9c  mov     cl, [rsp+220h+var_1D0]
0x180164fa0  test    cl, cl
0x180164fa2  jz      loc_1801650AC
0x180164fa8  mov     edx, ebx
0x180164faa  test    r15b, r15b
0x180164fad  jnz     loc_180165096
0x180164fb3  test    al, al
0x180164fb5  jnz     loc_180165096
0x180164fbb  mov     [rbp+120h+lpFile], rbx
0x180164fbf  mov     [rbp+120h+var_160], rbx
0x180164fc3  mov     [rbp+120h+var_158], rbx
0x180164fc7  mov     [rsp+220h+var_1F0], esi
0x180164fcb  mov     [rsp+220h+nShowCmd], ebx
0x180164fcf  mov     [rsp+220h+lpDirectory], r13; int
0x180164fd4  mov     r9, r12
0x180164fd7  lea     r8, [rbp+120h+packageFamilyName]
0x180164fdb  lea     rdx, aMsxboxRemediat; "msxbox://remediation/?PFN=%s&PN=%s&appU"...
0x180164fe2  lea     rcx, [rbp+120h+lpFile]
0x180164fe6  call    ?InitializeFormat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x180164feb  mov     ebx, eax
0x180164fed  test    eax, eax
0x180164fef  jns     short loc_180165036
0x180164ff1  mov     rcx, [rbp+128h]; this
0x180164ff8  mov     r9d, eax; char *
0x180164ffb  lea     r8, aShellTwinuiAct_0; "shell\\twinui\\activationerrorpopup\\li"...
0x180165002  mov     edx, 0E0h; void *
0x180165007  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18016500c  nop
0x18016500d  lea     rcx, [rbp+120h+lpFile]
0x180165011  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180165016  nop
0x180165017  mov     rcx, [rsp+220h+string]; string
0x18016501c  call    cs:__imp_WindowsDeleteString
0x180165023  nop     dword ptr [rax+rax+00h]
0x180165028  mov     [rsp+220h+string], 0
0x180165031  jmp     loc_1801657AA
0x180165036  mov     edx, 6; dwCoInit
0x18016503b  xor     ecx, ecx; pvReserved
0x18016503d  call    cs:__imp_CoInitializeEx
0x180165044  nop     dword ptr [rax+rax+00h]
0x180165049  mov     [rsp+220h+nShowCmd], 1; nShowCmd
0x180165051  mov     [rsp+220h+lpDirectory], 0; lpDirectory
0x18016505a  xor     r9d, r9d; lpParameters
0x18016505d  mov     r8, [rbp+120h+lpFile]; lpFile
0x180165061  lea     rdx, pwszSrc; "open"
0x180165068  xor     ecx, ecx; hwnd
0x18016506a  call    cs:__imp_ShellExecuteW
0x180165071  nop     dword ptr [rax+rax+00h]
0x180165076  mov     rbx, rax
0x180165079  lea     rcx, [rbp+120h+lpFile]
0x18016507d  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180165082  mov     edx, 80004005h
0x180165087  xor     ecx, ecx
0x180165089  cmp     rbx, 20h ; ' '
0x18016508d  cmova   edx, ecx
0x180165090  mov     cl, [rsp+220h+var_1D0]
0x180165094  xor     ebx, ebx
0x180165096  test    cl, cl
0x180165098  jz      short loc_1801650AC
0x18016509a  test    r15b, r15b
0x18016509d  jnz     short loc_1801650AC
0x18016509f  test    dil, dil
0x1801650a2  jnz     short loc_1801650AC
0x1801650a4  test    edx, edx
0x1801650a6  jns     loc_1801656F4
0x1801650ac  test    sil, 4
0x1801650b0  jz      short loc_1801650B9
0x1801650b2  mov     eax, 3
0x1801650b7  jmp     short loc_1801650E9
0x1801650b9  mov     eax, 2
0x1801650be  test    al, sil
0x1801650c1  jnz     short loc_1801650E9
0x1801650c3  test    sil, 1
0x1801650c7  jz      short loc_1801650D0
0x1801650c9  mov     eax, 1
0x1801650ce  jmp     short loc_1801650E9
0x1801650d0  test    sil, 20h
0x1801650d4  jz      short loc_1801650DD
0x1801650d6  mov     eax, 10h
0x1801650db  jmp     short loc_1801650E9
0x1801650dd  and     sil, 40h
0x1801650e1  neg     sil
0x1801650e4  sbb     eax, eax
0x1801650e6  and     eax, 11h
0x1801650e9  mov     [rbp+120h+lpFile], rbx
0x1801650ed  mov     [rbp+120h+var_160], rbx
0x1801650f1  mov     [rbp+120h+var_158], rbx
0x1801650f5  lea     r8, [rbp+120h+packageFamilyName]
0x1801650f9  lea     rcx, [rbp+120h+lpFile]
0x1801650fd  test    r15b, r15b
0x180165100  jnz     short loc_180165148
0x180165102  mov     [rsp+220h+var_1F0], eax
0x180165106  xor     r15d, r15d
0x180165109  mov     [rsp+220h+nShowCmd], r15d
0x18016510e  mov     [rsp+220h+lpDirectory], r13; int
0x180165113  mov     r9, r12
0x180165116  lea     rdx, aMsWindowsStore_17; "ms-windows-store:Remediation?PFN=%s&PN="...
0x18016511d  call    ?InitializeFormat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x180165122  mov     ebx, eax
0x180165124  test    eax, eax
0x180165126  jns     short loc_180165164
0x180165128  mov     edx, 11Dh; void *
0x18016512d  lea     r8, aShellTwinuiAct_0; "shell\\twinui\\activationerrorpopup\\li"...
0x180165134  mov     r9d, eax; char *
0x180165137  mov     rcx, [rbp+128h]; this
0x18016513e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180165143  jmp     loc_18016578A
0x180165148  lea     rdx, aMsWindowsStore_5; "ms-windows-store://pdp/?PFN=%s"
0x18016514f  call    ?InitializeFormat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x180165154  mov     ebx, eax
0x180165156  xor     r15d, r15d
0x180165159  test    eax, eax
0x18016515b  jns     short loc_180165164
0x18016515d  mov     edx, 121h
0x180165162  jmp     short loc_18016512D
0x180165164  mov     [rsp+220h+ppv], r15
0x180165169  lea     rcx, [rsp+220h+ppv]
0x18016516e  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x180165173  lea     r9, [rsp+220h+ppv]; ppv
0x180165178  lea     r8, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe; riid
0x18016517f  xor     edx, edx; pbc
0x180165181  mov     rcx, [rbp+120h+lpFile]; pszPath
0x180165185  call    cs:__imp_SHCreateItemFromParsingName
0x18016518c  nop     dword ptr [rax+rax+00h]
0x180165191  mov     ebx, eax
0x180165193  test    eax, eax
0x180165195  jns     short loc_1801651B7
0x180165197  mov     rcx, [rbp+128h]; this
0x18016519e  mov     r9d, eax; char *
0x1801651a1  lea     r8, aShellTwinuiAct_0; "shell\\twinui\\activationerrorpopup\\li"...
0x1801651a8  mov     edx, 125h; void *
0x1801651ad  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801651b2  jmp     loc_18016577F
0x1801651b7  mov     [rsp+220h+var_1B0], r15
0x1801651bc  lea     rcx, [rsp+220h+var_1B0]
0x1801651c1  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801651c6  lea     r8, [rsp+220h+var_1B0]; ppv
0x1801651cb  lea     rdx, _GUID_b63ea76d_1f85_456f_a19c_48159efa858b; riid
0x1801651d2  mov     rcx, [rsp+220h+ppv]; psi
0x1801651d7  call    cs:__imp_SHCreateShellItemArrayFromShellItem
0x1801651de  nop     dword ptr [rax+rax+00h]
0x1801651e3  mov     ebx, eax
0x1801651e5  test    eax, eax
0x1801651e7  jns     short loc_180165209
0x1801651e9  mov     rcx, [rbp+128h]; this
0x1801651f0  mov     r9d, eax; char *
0x1801651f3  lea     r8, aShellTwinuiAct_0; "shell\\twinui\\activationerrorpopup\\li"...
0x1801651fa  mov     edx, 128h; void *
0x1801651ff  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180165204  jmp     loc_180165774
0x180165209  mov     [rsp+220h+var_1A8], r15
0x18016520e  mov     rax, [rsp+220h+var_1B0]
0x180165213  mov     [rbp+120h+var_178], rax
0x180165217  lea     rcx, [rsp+220h+var_1A8]
0x18016521c  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x180165221  lea     rdx, [rbp+120h+var_178]
0x180165225  lea     rcx, [rsp+220h+var_1A8]; void **
0x18016522a  call    ??$MakeAndInitialize@VCProtocolActivatedEventArgs@@UIActivatedEventArgs@Activation@ApplicationModel@Windows@@PEAUIShellItemArray@@@Details@WRL@Microsoft@@YAJPEAPEAUIActivatedEventArgs@Activation@ApplicationModel@Windows@@$$QEAPEAUIShellItemArray@@@Z; Microsoft::WRL::Details::MakeAndInitialize<CProtocolActivatedEventArgs,Windows::ApplicationModel::Activation::IActivatedEventArgs,IShellItemArray *>(Windows::ApplicationModel::Activation::IActivatedEventArgs * *,IShellItemArray * &&)
0x18016522f  mov     ebx, eax
0x180165231  test    eax, eax
0x180165233  jns     short loc_180165255
0x180165235  mov     rcx, [rbp+128h]; this
0x18016523c  mov     r9d, eax; char *
0x18016523f  lea     r8, aShellTwinuiAct_0; "shell\\twinui\\activationerrorpopup\\li"...
0x180165246  mov     edx, 12Bh; void *
0x18016524b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180165250  jmp     loc_180165769
  ... truncated ...
```
