# Windows::Internal::AssignedAccess::PackageManagerHelper::FindExeFromInstallPath(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x1800521fc`
- end: `0x180052914`
- name: `?FindExeFromInstallPath@PackageManagerHelper@AssignedAccess@Internal@Windows@@CAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0AEAV56@@Z`
- size: `1816`
- prototype: ``
- caller_count: `1`
- callee_count: `21`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x180051f98`

## callees

- `0x180006640`
- `0x180009a74`
- `0x180009d58`
- `0x18000b6b4`
- `0x18000cfe4`
- `0x180010c98`
- `0x180013fac`
- `0x180014a5c`
- `0x18001f2b0`
- `0x18002001c`
- `0x180021548`
- `0x1800221e0`
- `0x1800271c4`
- `0x18003a4d0`
- `0x180051e2c`
- `0x180051ee4`
- `0x1800521fc`
- `0x18005307c`
- `0x18005391c`
- `0x1800737ec`
- `0x180096010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18005254f`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18005254f`
- `OLEAUT32!__imp_SysFreeString` at `0x180052693`
- `OLEAUT32!__imp_SysFreeString` at `0x180052693`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18005229c`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18005229c`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x1800526c1`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x1800526c1`

## string_xrefs

- `0x18005227c`: `\AppxManifest.xml`
- `0x1800528c2`: `One or more empty arguments. App install path:  %ws, AppId: %ws`
- `0x1800522fa`: `xmlns:ns='http://schemas.microsoft.com/appx/manifest/foundation/windows10'`
- `0x1800522bc`: `AppxManifest file not found. Manifest path: %ws`
- `0x1800527c0`: `AppxManifest Id attribute cannot be null. Manifest path: %ws`
- `0x180052824`: `AppxManifest missing required Id attribute in an Application element. Manifest path: %ws`
- `0x180052781`: `No corresponding Executable found for matching AppId in the AppxManifest. Manifest path: %ws, AppId: %ws`
- `0x1800525aa`: `No matching AppId found in the AppxManifest. Manifest path: %ws, AppId: %ws`
- `0x180052230`: `FindExeFromInstallPath`

## pseudocode

```c
// Hidden C++ exception states: #wind=20
__int64 __fastcall Windows::Internal::AssignedAccess::PackageManagerHelper::FindExeFromInstallPath(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  const WCHAR *v6; // rax
  const char *v7; // rax
  int v8; // ebx
  __int64 v9; // rcx
  _QWORD *v10; // rdx
  __int64 v11; // rbx
  __int64 (__fastcall *v12)(__int64, __int64, __int64 **); // rdi
  _bstr_t *v13; // rax
  __int64 v14; // rdx
  unsigned __int64 v15; // r9
  __int64 v16; // rdx
  int v17; // eax
  unsigned int v18; // edi
  __int64 v19; // rax
  int v20; // eax
  __int64 v21; // rbx
  __int64 (__fastcall *v22)(__int64, __int64, __int64 **); // r14
  _bstr_t *v23; // rax
  __int64 v24; // rdx
  __int64 v25; // rax
  int v26; // eax
  __int64 v27; // r8
  const char *v28; // rax
  __int64 v29; // rdx
  __int64 v30; // rbx
  __int64 (__fastcall *v31)(__int64, __int64, __int64 *); // rdi
  _bstr_t *v32; // rax
  __int64 v33; // rdx
  __int64 v34; // rbx
  unsigned int (__fastcall *v35)(__int64, BSTR *); // r14
  OLECHAR *v36; // rdi
  LPWSTR FileNameW; // rax
  unsigned __int64 v38; // r8
  const char *v39; // rax
  __int64 v40; // rdx
  const char *v41; // rax
  const char *v42; // rax
  const char *v43; // rax
  __int64 v44; // rdx
  int v46; // [rsp+20h] [rbp-E0h]
  __int64 *v47; // [rsp+40h] [rbp-C0h] BYREF
  int v48[2]; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v49; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v50; // [rsp+58h] [rbp-A8h] BYREF
  __int64 *v51; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v52; // [rsp+68h] [rbp-98h] BYREF
  __int64 v53; // [rsp+70h] [rbp-90h] BYREF
  int v54; // [rsp+78h] [rbp-88h] BYREF
  BSTR bstrString; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v56[8]; // [rsp+88h] [rbp-78h] BYREF
  _BYTE v57[32]; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v58[32]; // [rsp+B0h] [rbp-50h] BYREF
  _QWORD v59[7]; // [rsp+D0h] [rbp-30h] BYREF
  _QWORD *v60; // [rsp+108h] [rbp+8h]
  _QWORD v61[42]; // [rsp+110h] [rbp+10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2A8h] [rbp+1A8h]

  wil::ActivityBase<AssignedAccessTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<AssignedAccessTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
    v61,
    "FindExeFromInstallPath");
  v61[0] = &AssignedAccessTelemetry::FindExeFromInstallPath::`vftable';
  AssignedAccessTelemetry::FindExeFromInstallPath::StartActivity((AssignedAccessTelemetry::FindExeFromInstallPath *)v61);
  *(_QWORD *)(a3 + 16) = 0;
  *(_WORD *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a3) = 0;
  if ( !*(_QWORD *)(a1 + 16) || !*(_QWORD *)(a2 + 16) )
  {
    std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a2);
    v43 = (const char *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a1);
    v8 = -2147024809;
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x76,
      (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\worker\\packagemanagerhelper.cpp",
      (const char *)0x80070057LL,
      (int)"One or more empty arguments. App install path:  %ws, AppId: %ws",
      v43,
      v44);
    goto LABEL_55;
  }
  std::operator+<unsigned short>(v57, a1, L"\\AppxManifest.xml");
  v6 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v57);
  if ( GetFileAttributesW(v6) == -1 )
  {
    v7 = (const char *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v57);
    v8 = -2147024894;
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x7C,
      (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\worker\\packagemanagerhelper.cpp",
      (const char *)0x80070002LL,
      (int)"AppxManifest file not found. Manifest path: %ws",
      v7);
LABEL_5:
    std::wstring::_Tidy_deallocate(v57);
    goto LABEL_55;
  }
  v50 = 0;
  std::wstring::wstring(v58, L"xmlns:ns='http://schemas.microsoft.com/appx/manifest/foundation/windows10'");
  *(_QWORD *)v48 = 0;
  v59[0] = off_18009B128;
  v59[1] = v57;
  v59[2] = v61;
  v60 = v59;
  v8 = XmlLoader::LoadFromFile(v9, (__int64)v57, (__int64)v58, (__int64)v59, (__int64)v48);
  if ( v60 )
  {
    v10 = v59;
    LOBYTE(v10) = v60 != v59;
    (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v60 + 32LL))(v60, v10);
  }
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x8C,
      (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\worker\\packagemanagerhelper.cpp",
      (const char *)(unsigned int)v8,
      v46);
LABEL_10:
    std::wstring::_Tidy_deallocate(v58);
    wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(v48);
    wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(&v50);
    goto LABEL_5;
  }
  v47 = 0;
  v11 = *(_QWORD *)v48;
  v12 = *(__int64 (__fastcall **)(__int64, __int64, __int64 **))(**(_QWORD **)v48 + 288LL);
  v47 = 0;
  v13 = _bstr_t::_bstr_t((_bstr_t *)&v52, L"//ns:Application");
  if ( *(_QWORD *)v13 )
    v14 = **(_QWORD **)v13;
  else
    v14 = 0;
  v8 = v12(v11, v14, &v47);
  _bstr_t::_Free((_bstr_t *)&v52);
  if ( v8 < 0 )
  {
    v15 = (unsigned int)v8;
    v16 = 144;
LABEL_16:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v16,
      (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\worker\\packagemanagerhelper.cpp",
      (const char *)v15,
      v46);
LABEL_17:
    wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(&v47);
    goto LABEL_10;
  }
  v54 = 0;
  v17 = (*(__int64 (__fastcall **)(__int64 *, int *))(*v47 + 64))(v47, &v54);
  v8 = v17;
  if ( v17 < 0 )
  {
    v15 = (unsigned int)v17;
    v16 = 146;
    goto LABEL_16;
  }
  v18 = 0;
  if ( v54 <= 0 )
  {
LABEL_31:
    std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a2);
    v28 = (const char *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v57);
    v8 = -2147023728;
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0xBE,
      (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\worker\\packagemanagerhelper.cpp",
      (const char *)0x80070490LL,
      (int)"No matching AppId found in the AppxManifest. Manifest path: %ws, AppId: %ws",
      v28,
      v29);
    goto LABEL_17;
  }
  while ( 1 )
  {
    v49 = 0;
    v19 = *v47;
    v49 = 0;
    v20 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, __int64 *))(v19 + 56))(v47, v18, &v49);
    v8 = v20;
    if ( v20 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x96,
        (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\worker\\packagemanagerhelper.cpp",
        (const char *)(unsigned int)v20,
        v46);
      goto LABEL_53;
    }
    v51 = 0;
    v21 = v49;
    v22 = *(__int64 (__fastcall **)(__int64, __int64, __int64 **))(*(_QWORD *)v49 + 296LL);
    v51 = 0;
    v23 = _bstr_t::_bstr_t((_bstr_t *)&v52, L"@Id");
    if ( *(_QWORD *)v23 )
      v24 = **(_QWORD **)v23;
    else
      v24 = 0;
    v8 = v22(v21, v24, &v51);
    _bstr_t::_Free((_bstr_t *)&v52);
    if ( v8 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x99,
        (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\worker\\packagemanagerhelper.cpp",
        (const char *)(unsigned int)v8,
        v46);
LABEL_51:
      wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(&v51);
LABEL_53:
      wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(&v49);
      goto LABEL_17;
    }
    if ( !v51 )
    {
      v42 = (const char *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v57);
      v8 = -2147023431;
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x9F,
        (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\worker\\packagemanagerhelper.cpp",
        (const char *)0x800705B9LL,
        (int)"AppxManifest missing required Id attribute in an Application element. Manifest path: %ws",
        v42);
      goto LABEL_51;
    }
    v53 = 0;
    v25 = *v51;
    v53 = 0;
    v26 = (*(__int64 (__fastcall **)(__int64 *, __int64 *))(v25 + 208))(v51, &v53);
    v8 = v26;
    if ( v26 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xA2,
        (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\worker\\packagemanagerhelper.cpp",
        (const char *)(unsigned int)v26,
        v46);
      goto LABEL_48;
    }
    if ( !v53 )
    {
      v41 = (const char *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v57);
      v8 = -2147023431;
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0xA8,
        (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\worker\\packagemanagerhelper.cpp",
        (const char *)0x800705B9LL,
        (int)"AppxManifest Id attribute cannot be null. Manifest path: %ws",
        v41);
      goto LABEL_48;
    }
    std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a2);
    if ( !(unsigned int)_o__wcsicmp(v27) )
      break;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v53);
    wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(&v51);
    wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(&v49);
    if ( (int)++v18 >= v54 )
      goto LABEL_31;
  }
  v52 = 0;
  bstrString = 0;
  v30 = v49;
  v31 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v49 + 296LL);
  v52 = 0;
  v32 = _bstr_t::_bstr_t((_bstr_t *)v56, L"@Executable");
  if ( *(_QWORD *)v32 )
    v33 = **(_QWORD **)v32;
  else
    v33 = 0;
  v8 = v31(v30, v33, &v52);
  _bstr_t::_Free((_bstr_t *)v56);
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xAE,
      (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\worker\\packagemanagerhelper.cpp",
      (const char *)(unsigned int)v8,
      v46);
LABEL_37:
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&bstrString);
    wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(&v52);
LABEL_48:
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v53);
    goto LABEL_51;
  }
  v34 = v52;
  if ( !v52 )
    goto LABEL_45;
  v35 = *(unsigned int (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v52 + 208LL);
  v36 = bstrString;
  if ( bstrString )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)v56);
    SysFreeString(v36);
    wil::last_error_context::~last_error_context((wil::last_error_context *)v56);
  }
  bstrString = 0;
  if ( v35(v34, &bstrString) )
  {
LABEL_45:
    std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a2);
    v39 = (const char *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v57);
    v8 = -2147023728;
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0xB9,
      (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\worker\\packagemanagerhelper.cpp",
      (const char *)0x80070490LL,
      (int)"No corresponding Executable found for matching AppId in the AppxManifest. Manifest path: %ws, AppId: %ws",
      v39,
      v40);
    goto LABEL_37;
  }
  FileNameW = PathFindFileNameW(bstrString);
  v38 = -1;
  do
    ++v38;
  while ( FileNameW[v38] );
  std::wstring::_Assign<unsigned short>(a3, (__int64)FileNameW, v38);
  wil::ActivityBase<AssignedAccessTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v61);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&bstrString);
  wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(&v52);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v53);
  wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(&v51);
  wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(&v49);
  wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(&v47);
  std::wstring::_Tidy_deallocate(v58);
  wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(v48);
  wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(&v50);
  std::wstring::_Tidy_deallocate(v57);
  v8 = 0;
LABEL_55:
  AssignedAccessTelemetry::FindExeFromInstallPath::~FindExeFromInstallPath((AssignedAccessTelemetry::FindExeFromInstallPath *)v61);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800521fc  push    rbp
0x1800521fe  push    rbx
0x1800521ff  push    rsi
0x180052200  push    rdi
0x180052201  push    r12
0x180052203  push    r14
0x180052205  push    r15
0x180052207  lea     rbp, [rsp-170h]
0x18005220f  sub     rsp, 270h
0x180052216  mov     rax, cs:__security_cookie
0x18005221d  xor     rax, rsp
0x180052220  mov     [rbp+1A0h+var_40], rax
0x180052227  mov     r15, r8
0x18005222a  mov     rsi, rdx
0x18005222d  mov     rbx, rcx
0x180052230  lea     rdx, aFindexefromins; "FindExeFromInstallPath"
0x180052237  lea     rcx, [rbp+1A0h+var_190]
0x18005223b  call    ??0?$ActivityBase@VAssignedAccessTelemetry@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<AssignedAccessTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<AssignedAccessTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180052240  lea     rax, ??_7FindExeFromInstallPath@AssignedAccessTelemetry@@6B@; const AssignedAccessTelemetry::FindExeFromInstallPath::`vftable'
0x180052247  mov     [rbp+1A0h+var_190], rax
0x18005224b  lea     rcx, [rbp+1A0h+var_190]; this
0x18005224f  call    ?StartActivity@FindExeFromInstallPath@AssignedAccessTelemetry@@QEAAXXZ; AssignedAccessTelemetry::FindExeFromInstallPath::StartActivity(void)
0x180052254  nop
0x180052255  xor     r12d, r12d
0x180052258  mov     [r15+10h], r12
0x18005225c  mov     rcx, r15
0x18005225f  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180052264  mov     [rax], r12w
0x180052268  cmp     [rbx+10h], r12
0x18005226c  jz      loc_18005289E
0x180052272  cmp     [rsi+10h], r12
0x180052276  jz      loc_18005289E
0x18005227c  lea     r8, aAppxmanifestXm; "\\AppxManifest.xml"
0x180052283  mov     rdx, rbx
0x180052286  lea     rcx, [rbp+1A0h+var_210]
0x18005228a  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@QEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const * const)
0x18005228f  nop
0x180052290  lea     rcx, [rbp+1A0h+var_210]
0x180052294  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180052299  mov     rcx, rax; lpFileName
0x18005229c  call    cs:__imp_GetFileAttributesW
0x1800522a2  cmp     eax, 0FFFFFFFFh
0x1800522a5  jnz     short loc_1800522F0
0x1800522a7  lea     rcx, [rbp+1A0h+var_210]
0x1800522ab  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800522b0  mov     rcx, [rbp+1A8h]; this
0x1800522b7  mov     [rsp+2A0h+var_278], rax; char *
0x1800522bc  lea     rax, aAppxmanifestFi; "AppxManifest file not found. Manifest p"...
0x1800522c3  mov     qword ptr [rsp+2A0h+var_280], rax; int
0x1800522c8  mov     ebx, 80070002h
0x1800522cd  mov     r9d, ebx; char *
0x1800522d0  lea     r8, aOnecoreuapBase_52; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x1800522d7  lea     edx, [r12+7Ch]; void *
0x1800522dc  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800522e1  nop
0x1800522e2  lea     rcx, [rbp+1A0h+var_210]
0x1800522e6  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800522eb  jmp     loc_1800528E8
0x1800522f0  mov     [rsp+2A0h+var_248], r12
0x1800522f5  mov     qword ptr [rsp+2A0h+var_258], r12
0x1800522fa  lea     rdx, aXmlnsNsHttpSch; "xmlns:ns='http://schemas.microsoft.com/"...
0x180052301  lea     rcx, [rbp+1A0h+var_1F0]
0x180052305  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18005230a  nop
0x18005230b  mov     qword ptr [rsp+2A0h+var_258], r12
0x180052310  lea     rax, off_18009B128
0x180052317  mov     [rbp+1A0h+var_1D0], rax
0x18005231b  lea     rax, [rbp+1A0h+var_210]
0x18005231f  mov     [rbp+1A0h+var_1C8], rax
0x180052323  lea     rax, [rbp+1A0h+var_190]
0x180052327  mov     [rbp+1A0h+var_1C0], rax
0x18005232b  lea     rax, [rbp+1A0h+var_1D0]
0x18005232f  mov     [rbp+1A0h+var_198], rax
0x180052333  lea     rax, [rsp+2A0h+var_258]
0x180052338  mov     qword ptr [rsp+2A0h+var_280], rax; int
0x18005233d  lea     r9, [rbp+1A0h+var_1D0]
0x180052341  lea     r8, [rbp+1A0h+var_1F0]
0x180052345  lea     rdx, [rbp+1A0h+var_210]
0x180052349  call    ?LoadFromFile@XmlLoader@@QEAAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0AEBV?$function@$$A6AXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@JJJ@Z@3@PEAPEAUIXMLDOMDocument3@@@Z; XmlLoader::LoadFromFile(std::wstring const &,std::wstring const &,std::function<void (std::wstring &,long,long,long)> const &,IXMLDOMDocument3 * *)
0x18005234e  mov     ebx, eax
0x180052350  mov     rcx, [rbp+1A0h+var_198]
0x180052354  test    rcx, rcx
0x180052357  jz      short loc_18005236F
0x180052359  mov     rax, [rcx]
0x18005235c  lea     rdx, [rbp+1A0h+var_1D0]
0x180052360  cmp     rcx, rdx
0x180052363  setnz   dl
0x180052366  mov     rax, [rax+20h]
0x18005236a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005236f  test    ebx, ebx
0x180052371  jns     short loc_1800523B3
0x180052373  mov     rcx, [rbp+1A8h]; this
0x18005237a  mov     r9d, ebx; char *
0x18005237d  lea     r8, aOnecoreuapBase_52; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x180052384  mov     edx, 8Ch; void *
0x180052389  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005238e  nop
0x18005238f  lea     rcx, [rbp+1A0h+var_1F0]
0x180052393  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180052398  nop
0x180052399  lea     rcx, [rsp+2A0h+var_258]
0x18005239e  call    ??1?$com_ptr_t@UIStorageFolder@Storage@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(void)
0x1800523a3  nop
0x1800523a4  lea     rcx, [rsp+2A0h+var_248]
0x1800523a9  call    ??1?$com_ptr_t@UIStorageFolder@Storage@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(void)
0x1800523ae  jmp     loc_1800522E2
0x1800523b3  mov     [rsp+2A0h+var_260], r12
0x1800523b8  mov     rbx, qword ptr [rsp+2A0h+var_258]
0x1800523bd  mov     rax, [rbx]
0x1800523c0  mov     rdi, [rax+120h]
0x1800523c7  mov     [rsp+2A0h+var_260], r12
0x1800523cc  lea     rdx, aNsApplication; "//ns:Application"
0x1800523d3  lea     rcx, [rsp+2A0h+var_238]; this
0x1800523d8  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x1800523dd  nop
0x1800523de  mov     rdx, [rax]
0x1800523e1  test    rdx, rdx
0x1800523e4  jz      short loc_1800523EB
0x1800523e6  mov     rdx, [rdx]
0x1800523e9  jmp     short loc_1800523EE
0x1800523eb  mov     rdx, r12
0x1800523ee  lea     r8, [rsp+2A0h+var_260]
0x1800523f3  mov     rcx, rbx
0x1800523f6  mov     rax, rdi
0x1800523f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800523fe  mov     ebx, eax
0x180052400  lea     rcx, [rsp+2A0h+var_238]; this
0x180052405  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18005240a  test    ebx, ebx
0x18005240c  jns     short loc_180052439
0x18005240e  mov     r9d, ebx; char *
0x180052411  mov     edx, 90h; void *
0x180052416  lea     r8, aOnecoreuapBase_52; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x18005241d  mov     rcx, [rbp+1A8h]; this
0x180052424  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180052429  nop
0x18005242a  lea     rcx, [rsp+2A0h+var_260]
0x18005242f  call    ??1?$com_ptr_t@UIStorageFolder@Storage@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(void)
0x180052434  jmp     loc_18005238F
0x180052439  mov     [rsp+2A0h+var_228], r12d
0x18005243e  mov     rcx, [rsp+2A0h+var_260]
0x180052443  mov     rax, [rcx]
0x180052446  lea     rdx, [rsp+2A0h+var_228]
0x18005244b  mov     rax, [rax+40h]
0x18005244f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052454  mov     ebx, eax
0x180052456  test    eax, eax
0x180052458  jns     short loc_180052464
0x18005245a  mov     r9d, eax
0x18005245d  mov     edx, 92h
0x180052462  jmp     short loc_180052416
0x180052464  mov     edi, r12d
0x180052467  cmp     [rsp+2A0h+var_228], r12d
0x18005246c  jle     loc_180052585
0x180052472  mov     [rsp+2A0h+var_250], r12
0x180052477  mov     rcx, [rsp+2A0h+var_260]
0x18005247c  mov     rax, [rcx]
0x18005247f  mov     [rsp+2A0h+var_250], r12
0x180052484  lea     r8, [rsp+2A0h+var_250]
0x180052489  mov     edx, edi
0x18005248b  mov     rax, [rax+38h]
0x18005248f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052494  mov     ebx, eax
0x180052496  test    eax, eax
0x180052498  js      loc_180052873
0x18005249e  mov     [rsp+2A0h+var_240], r12
0x1800524a3  mov     rbx, [rsp+2A0h+var_250]
0x1800524a8  mov     rax, [rbx]
0x1800524ab  mov     r14, [rax+128h]
0x1800524b2  mov     [rsp+2A0h+var_240], r12
0x1800524b7  lea     rdx, aId_0; "@Id"
0x1800524be  lea     rcx, [rsp+2A0h+var_238]; this
0x1800524c3  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x1800524c8  nop
0x1800524c9  mov     rdx, [rax]
0x1800524cc  test    rdx, rdx
0x1800524cf  jz      short loc_1800524D6
0x1800524d1  mov     rdx, [rdx]
0x1800524d4  jmp     short loc_1800524D9
0x1800524d6  mov     rdx, r12
0x1800524d9  lea     r8, [rsp+2A0h+var_240]
0x1800524de  mov     rcx, rbx
0x1800524e1  mov     rax, r14
0x1800524e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800524e9  mov     ebx, eax
0x1800524eb  lea     rcx, [rsp+2A0h+var_238]; this
0x1800524f0  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x1800524f5  test    ebx, ebx
0x1800524f7  js      loc_18005284B
0x1800524fd  mov     rcx, [rsp+2A0h+var_240]
0x180052502  test    rcx, rcx
0x180052505  jz      loc_18005280F
0x18005250b  mov     [rsp+2A0h+var_230], r12
0x180052510  mov     rax, [rcx]
0x180052513  mov     [rsp+2A0h+var_230], r12
0x180052518  lea     rdx, [rsp+2A0h+var_230]
0x18005251d  mov     rax, [rax+0D0h]
0x180052524  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052529  mov     ebx, eax
0x18005252b  test    eax, eax
0x18005252d  js      loc_1800527E7
0x180052533  mov     r8, [rsp+2A0h+var_230]
0x180052538  test    r8, r8
0x18005253b  jz      loc_1800527AB
0x180052541  mov     rcx, rsi
0x180052544  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180052549  mov     rdx, rax
0x18005254c  mov     rcx, r8
0x18005254f  call    cs:__imp__o__wcsicmp
0x180052555  test    eax, eax
0x180052557  jz      short loc_1800525D4
0x180052559  lea     rcx, [rsp+2A0h+var_230]
0x18005255e  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180052563  nop
0x180052564  lea     rcx, [rsp+2A0h+var_240]
0x180052569  call    ??1?$com_ptr_t@UIStorageFolder@Storage@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(void)
0x18005256e  nop
0x18005256f  lea     rcx, [rsp+2A0h+var_250]
0x180052574  call    ??1?$com_ptr_t@UIStorageFolder@Storage@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(void)
0x180052579  inc     edi
0x18005257b  cmp     edi, [rsp+2A0h+var_228]
0x18005257f  jl      loc_180052472
0x180052585  mov     rcx, rsi
0x180052588  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18005258d  mov     rdx, rax
0x180052590  lea     rcx, [rbp+1A0h+var_210]
0x180052594  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180052599  mov     rcx, [rbp+1A8h]; this
0x1800525a0  mov     [rsp+2A0h+var_270], rdx
0x1800525a5  mov     [rsp+2A0h+var_278], rax; char *
0x1800525aa  lea     rax, aNoMatchingAppi; "No matching AppId found in the AppxMani"...
0x1800525b1  mov     qword ptr [rsp+2A0h+var_280], rax; int
0x1800525b6  mov     ebx, 80070490h
0x1800525bb  mov     r9d, ebx; char *
0x1800525be  lea     r8, aOnecoreuapBase_52; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x1800525c5  mov     edx, 0BEh; void *
0x1800525ca  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800525cf  jmp     loc_18005242A
0x1800525d4  mov     [rsp+2A0h+var_238], r12
0x1800525d9  mov     [rbp+1A0h+bstrString], r12
0x1800525dd  mov     rbx, [rsp+2A0h+var_250]
0x1800525e2  mov     rax, [rbx]
0x1800525e5  mov     rdi, [rax+128h]
0x1800525ec  mov     [rsp+2A0h+var_238], r12
0x1800525f1  lea     rdx, aExecutable; "@Executable"
0x1800525f8  lea     rcx, [rbp+1A0h+var_218]; this
0x1800525fc  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x180052601  nop
0x180052602  mov     rdx, [rax]
0x180052605  test    rdx, rdx
0x180052608  jz      short loc_18005260F
0x18005260a  mov     rdx, [rdx]
0x18005260d  jmp     short loc_180052612
0x18005260f  mov     rdx, r12
0x180052612  lea     r8, [rsp+2A0h+var_238]
0x180052617  mov     rcx, rbx
0x18005261a  mov     rax, rdi
0x18005261d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052622  mov     ebx, eax
0x180052624  lea     rcx, [rbp+1A0h+var_218]; this
0x180052628  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18005262d  test    ebx, ebx
0x18005262f  jns     short loc_180052666
0x180052631  mov     rcx, [rbp+1A8h]; this
0x180052638  mov     r9d, ebx; char *
0x18005263b  lea     r8, aOnecoreuapBase_52; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x180052642  mov     edx, 0AEh; void *
0x180052647  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005264c  nop
0x18005264d  lea     rcx, [rbp+1A0h+bstrString]
0x180052651  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180052656  nop
0x180052657  lea     rcx, [rsp+2A0h+var_238]
0x18005265c  call    ??1?$com_ptr_t@UIStorageFolder@Storage@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(void)
0x180052661  jmp     loc_180052803
0x180052666  mov     rbx, [rsp+2A0h+var_238]
0x18005266b  test    rbx, rbx
0x18005266e  jz      loc_18005275C
0x180052674  mov     rax, [rbx]
0x180052677  mov     r14, [rax+0D0h]
0x18005267e  mov     rdi, [rbp+1A0h+bstrString]
0x180052682  test    rdi, rdi
0x180052685  jz      short loc_1800526A2
0x180052687  lea     rcx, [rbp+1A0h+var_218]; this
0x18005268b  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180052690  mov     rcx, rdi; bstrString
0x180052693  call    cs:__imp_SysFreeString
0x180052699  lea     rcx, [rbp+1A0h+var_218]; this
0x18005269d  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1800526a2  mov     [rbp+1A0h+bstrString], r12
0x1800526a6  lea     rdx, [rbp+1A0h+bstrString]
0x1800526aa  mov     rcx, rbx
0x1800526ad  mov     rax, r14
0x1800526b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800526b5  test    eax, eax
0x1800526b7  jnz     loc_18005275C
0x1800526bd  mov     rcx, [rbp+1A0h+bstrString]; pszPath
0x1800526c1  call    cs:__imp_PathFindFileNameW
0x1800526c7  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800526cb  inc     r8
  ... truncated ...
```
