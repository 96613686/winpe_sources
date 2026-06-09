# CLanguageManagerSingleton::_GetProductIdFromPackageFamilyName(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *)

- ea: `0x140052e9c`
- end: `0x140053905`
- name: `?_GetProductIdFromPackageFamilyName@CLanguageManagerSingleton@@AEAAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAV23@@Z`
- size: `2665`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x140053df0`

## callees

- `0x140005f30`
- `0x140006d2c`
- `0x14000c214`
- `0x140011b68`
- `0x14001a2a0`
- `0x14001f3d4`
- `0x140029eb8`
- `0x14002a2c0`
- `0x140045180`
- `0x14004610c`
- `0x140052e9c`
- `0x14007d010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1400537d2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1400537d2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14005309f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140053371`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1400533ad`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140053439`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1400534cb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14005358b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140053672`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1400536c6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140053708`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140053734`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140053794`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1400537f6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140053822`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140053882`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14005309f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140053371`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1400533ad`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140053439`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1400534cb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14005358b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140053672`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1400536c6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140053708`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140053734`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140053794`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1400537f6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140053822`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140053882`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x140052f0b`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x140053119`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1400531ca`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x140052f0b`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x140053119`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1400531ca`

## string_xrefs

- `0x1400538f3`: `onecore\internal\sdk\inc\wil\opensource\wil\winrt.h`
- `0x140052faf`: `Windows.Data.Json.JsonObject`
- `0x140052edf`: `Windows.Data.Json.JsonValue`
- `0x14005319e`: `Windows.Services.Store.StoreRequestHelper`
- `0x1400530ed`: `Windows.Services.Store.StoreContext`

## pseudocode

```c
// Hidden C++ exception states: #wind=24
__int64 __fastcall CLanguageManagerSingleton::_GetProductIdFromPackageFamilyName(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v5; // rbx
  int ActivationFactory; // eax
  unsigned int v7; // ebx
  __int64 v8; // rdi
  __int64 (__fastcall *v9)(__int64, _QWORD, _QWORD **); // rbx
  __int64 v10; // rax
  int v11; // eax
  int v12; // eax
  __int64 v13; // rdx
  __int64 (__fastcall ***v14)(_QWORD, _QWORD, _QWORD); // rsi
  __int64 (__fastcall *v15)(_QWORD, GUID *, __int64 *); // rdi
  __int64 *v16; // rbx
  __int64 (__fastcall ***v17)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v18)(_QWORD, GUID *, __int64 *); // rdi
  int v19; // eax
  __int64 v20; // rdi
  __int64 (__fastcall *v21)(__int64, HSTRING *); // rbx
  int v22; // eax
  __int64 v23; // rbx
  int v24; // eax
  __int64 v25; // rdi
  __int64 (__fastcall *v26)(__int64, __int64 *); // rbx
  int v27; // eax
  __int64 v28; // rbx
  int v29; // eax
  int v30; // eax
  __int64 v31; // rcx
  __int64 v32; // rbx
  int v33; // eax
  int v34; // eax
  __int64 v35; // rcx
  __int64 v36; // rcx
  __int64 v37; // rcx
  __int64 v38; // rcx
  __int64 v39; // rdi
  __int64 (__fastcall *v40)(__int64, HSTRING *); // rbx
  int v41; // eax
  __int64 v42; // rcx
  __int64 v43; // rcx
  int v44; // eax
  __int64 v45; // rcx
  __int64 v46; // rcx
  int v47; // eax
  __int64 v48; // rcx
  __int64 v49; // rcx
  __int64 v50; // rdi
  __int64 (__fastcall *v51)(__int64, __int64, double *); // rbx
  int v52; // eax
  __int64 v53; // rcx
  __int64 v54; // rcx
  __int64 v55; // rdi
  __int64 (__fastcall *v56)(__int64, __int64, __int64 *); // rbx
  int v57; // eax
  __int64 v58; // rcx
  __int64 v59; // rcx
  __int64 v60; // rdi
  __int64 (__fastcall *v61)(__int64, _QWORD, HSTRING *); // rbx
  int v62; // eax
  __int64 v63; // rcx
  __int64 v64; // rcx
  PCWSTR StringRawBuffer; // rax
  __int64 v67; // r8
  __int64 v68; // rcx
  __int64 v69; // rcx
  int v70; // [rsp+20h] [rbp-99h]
  HSTRING_HEADER hstringHeader; // [rsp+30h] [rbp-89h] BYREF
  GUID *v72; // [rsp+48h] [rbp-71h]
  __int64 v73; // [rsp+50h] [rbp-69h] BYREF
  HSTRING v74; // [rsp+58h] [rbp-61h] BYREF
  int v75[2]; // [rsp+60h] [rbp-59h] BYREF
  __int64 v76; // [rsp+68h] [rbp-51h] BYREF
  _QWORD *v77; // [rsp+70h] [rbp-49h] BYREF
  __int64 (__fastcall ***v78)(_QWORD, GUID *, __int64 *); // [rsp+78h] [rbp-41h] BYREF
  __int64 v79; // [rsp+80h] [rbp-39h] BYREF
  HSTRING string; // [rsp+88h] [rbp-31h] BYREF
  __int64 v81; // [rsp+90h] [rbp-29h] BYREF
  __int64 v82; // [rsp+98h] [rbp-21h] BYREF
  __int64 v83; // [rsp+A0h] [rbp-19h] BYREF
  __int64 v84; // [rsp+A8h] [rbp-11h] BYREF
  __int64 v85; // [rsp+B0h] [rbp-9h] BYREF
  HSTRING v86; // [rsp+B8h] [rbp-1h] BYREF
  __int64 v87; // [rsp+C0h] [rbp+7h] BYREF
  __int64 v88; // [rsp+C8h] [rbp+Fh] BYREF
  char *v89; // [rsp+D0h] [rbp+17h] BYREF
  double v90; // [rsp+D8h] [rbp+1Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+5Fh]

  LODWORD(v73) = 0;
  v88 = 0;
  v72 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Data.Json.JsonValue",
    0x1Cu,
    0x1Bu);
  v5 = (__int64)v72;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v88);
  ActivationFactory = RoGetActivationFactory(v5, &GUID_5f6b544a_2f53_48e1_91a3_f78b50a6345c, &v88);
  v7 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x441,
      (unsigned int)"pcshell\\shell\\systemsettings\\adminflows\\languagemanager\\lib\\languagemanagersingleton.cpp",
      (const char *)(unsigned int)ActivationFactory,
      v70);
LABEL_82:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v88);
    return v7;
  }
  v77 = 0;
  v8 = v88;
  v9 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD **))(*(_QWORD *)v88 + 80LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v77);
  v73 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a2);
  v10 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v73);
  v11 = v9(v8, *(_QWORD *)(v10 + 24), &v77);
  v7 = v11;
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x445,
      (unsigned int)"pcshell\\shell\\systemsettings\\adminflows\\languagemanager\\lib\\languagemanagersingleton.cpp",
      (const char *)(unsigned int)v11,
      v70);
LABEL_81:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v77);
    goto LABEL_82;
  }
  v78 = 0;
  v72 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Data.Json.JsonObject",
    0x1Du,
    0x1Cu);
  v12 = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>>(
          (__int64)v72,
          &v78);
  v7 = v12;
  if ( v12 < 0 )
  {
    v13 = 1097;
LABEL_7:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v13,
      (unsigned int)"pcshell\\shell\\systemsettings\\adminflows\\languagemanager\\lib\\languagemanagersingleton.cpp",
      (const char *)(unsigned int)v12,
      v70);
LABEL_80:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v78);
    goto LABEL_81;
  }
  v14 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v78;
  v15 = (*v78)[7];
  v16 = v77;
  v72 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"packageFamilyName", 0x12u, 0x11u);
  v12 = v15(v14, v72, v16);
  v7 = v12;
  if ( v12 < 0 )
  {
    v13 = 1100;
    goto LABEL_7;
  }
  v79 = 0;
  v17 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v78;
  v18 = **v78;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v79);
  v19 = v18(v17, &GUID_a3219ecb_f0b3_4dcd_beee_19d48cd3ed1e, &v79);
  v7 = v19;
  if ( v19 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x44F,
      (unsigned int)"pcshell\\shell\\systemsettings\\adminflows\\languagemanager\\lib\\languagemanagersingleton.cpp",
      (const char *)(unsigned int)v19,
      v70);
LABEL_79:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v79);
    goto LABEL_80;
  }
  v74 = 0;
  v20 = v79;
  v21 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v79 + 56LL);
  WindowsDeleteString(0);
  v74 = 0;
  v22 = v21(v20, &v74);
  v7 = v22;
  if ( v22 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x452,
      (unsigned int)"pcshell\\shell\\systemsettings\\adminflows\\languagemanager\\lib\\languagemanagersingleton.cpp",
      (const char *)(unsigned int)v22,
      v70);
LABEL_78:
    WindowsDeleteString(v74);
    v74 = 0;
    goto LABEL_79;
  }
  v81 = 0;
  v72 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Services.Store.StoreContext",
    0x24u,
    0x23u);
  v23 = (__int64)v72;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v81);
  v24 = RoGetActivationFactory(v23, &GUID_9c06ee5f_15c0_4e72_9330_d6191cebd19c, &v81);
  v7 = v24;
  if ( v24 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x457,
      (unsigned int)"pcshell\\shell\\systemsettings\\adminflows\\languagemanager\\lib\\languagemanagersingleton.cpp",
      (const char *)(unsigned int)v24,
      v70);
LABEL_77:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v81);
    goto LABEL_78;
  }
  v82 = 0;
  v25 = v81;
  v26 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v81 + 48LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v82);
  v27 = v26(v25, &v82);
  v7 = v27;
  if ( v27 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x45A,
      (unsigned int)"pcshell\\shell\\systemsettings\\adminflows\\languagemanager\\lib\\languagemanagersingleton.cpp",
      (const char *)(unsigned int)v27,
      v70);
LABEL_76:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v82);
    goto LABEL_77;
  }
  v83 = 0;
  v72 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Services.Store.StoreRequestHelper",
    0x2Au,
    0x29u);
  v28 = (__int64)v72;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v83);
  v29 = RoGetActivationFactory(v28, &GUID_6ce5e5f9_a0c9_4b2c_96a6_a171c630038d, &v83);
  v7 = v29;
  if ( v29 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x45F,
      (unsigned int)"pcshell\\shell\\systemsettings\\adminflows\\languagemanager\\lib\\languagemanagersingleton.cpp",
      (const char *)(unsigned int)v29,
      v70);
LABEL_75:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v83);
    goto LABEL_76;
  }
  *(_QWORD *)v75 = 0;
  v30 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, HSTRING))(*(_QWORD *)v83 + 48LL))(v83, v82, 9, v74);
  v7 = v30;
  if ( v30 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x466,
      (unsigned int)"pcshell\\shell\\systemsettings\\adminflows\\languagemanager\\lib\\languagemanagersingleton.cpp",
      (const char *)(unsigned int)v30,
      (int)v75);
    v31 = *(_QWORD *)v75;
    if ( *(_QWORD *)v75 )
    {
      *(_QWORD *)v75 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
    }
    goto LABEL_75;
  }
  v32 = *(_QWORD *)v75;
  v76 = 0;
  LODWORD(v73) = 2;
  v33 = wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Services::Store::StoreSendRequestResult *> *>(*(__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))v75);
  if ( v33 >= 0 )
    v33 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v32 + 64LL))(v32, &v76);
  if ( v33 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x71B,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\winrt.h",
      (const char *)(unsigned int)v33,
      (int)v75);
  LODWORD(v89) = 0;
  v34 = (*(__int64 (__fastcall **)(__int64, char **))(*(_QWORD *)v76 + 56LL))(v76, &v89);
  v7 = v34;
  if ( v34 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x46B,
      (unsigned int)"pcshell\\shell\\systemsettings\\adminflows\\languagemanager\\lib\\languagemanagersingleton.cpp",
      (const char *)(unsigned int)v34,
      (int)v75);
    v35 = v76;
    if ( v76 )
    {
      v76 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
    }
    v36 = *(_QWORD *)v75;
    if ( *(_QWORD *)v75 )
    {
      *(_QWORD *)v75 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
    }
    goto LABEL_75;
  }
  v7 = (unsigned int)v89;
  if ( (int)v89 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x46C,
      (unsigned int)"pcshell\\shell\\systemsettings\\adminflows\\languagemanager\\lib\\languagemanagersingleton.cpp",
      (const char *)(unsigned int)v89,
      (int)v75);
    v37 = v76;
    if ( v76 )
    {
      v76 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
    }
    v38 = *(_QWORD *)v75;
    if ( *(_QWORD *)v75 )
    {
      *(_QWORD *)v75 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
    }
    goto LABEL_75;
  }
  string = 0;
  v39 = v76;
  v40 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v76 + 48LL);
  WindowsDeleteString(0);
  string = 0;
  v41 = v40(v39, &string);
  v7 = v41;
  if ( v41 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x46F,
      (unsigned int)"pcshell\\shell\\systemsettings\\adminflows\\languagemanager\\lib\\languagemanagersingleton.cpp",
      (const char *)(unsigned int)v41,
      (int)v75);
    WindowsDeleteString(string);
    string = 0;
    v42 = v76;
    if ( v76 )
    {
      v76 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v42 + 16LL))(v42);
    }
    v43 = *(_QWORD *)v75;
    if ( *(_QWORD *)v75 )
    {
      *(_QWORD *)v75 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
    }
    goto LABEL_75;
  }
  v85 = 0;
  v44 = (*(__int64 (__fastcall **)(__int64, HSTRING, __int64 *))(*(_QWORD *)v88 + 48LL))(v88, string, &v85);
  v7 = v44;
  if ( v44 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x472,
      (unsigned int)"pcshell\\shell\\systemsettings\\adminflows\\languagemanager\\lib\\languagemanagersingleton.cpp",
      (const char *)(unsigned int)v44,
      (int)v75);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v85);
    WindowsDeleteString(string);
    string = 0;
    v45 = v76;
    if ( v76 )
    {
      v76 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 16LL))(v45);
    }
    v46 = *(_QWORD *)v75;
    if ( *(_QWORD *)v75 )
    {
      *(_QWORD *)v75 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v46 + 16LL))(v46);
    }
    goto LABEL_75;
  }
  v84 = 0;
  v47 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v85 + 96LL))(v85, &v84);
  v7 = v47;
  if ( v47 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x475,
      (unsigned int)"pcshell\\shell\\systemsettings\\adminflows\\languagemanager\\lib\\languagemanagersingleton.cpp",
      (const char *)(unsigned int)v47,
      (int)v75);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v84);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v85);
    WindowsDeleteString(string);
    string = 0;
    v48 = v76;
    if ( v76 )
    {
      v76 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v48 + 16LL))(v48);
    }
    v49 = *(_QWORD *)v75;
    if ( *(_QWORD *)v75 )
    {
      *(_QWORD *)v75 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v49 + 16LL))(v49);
    }
    goto LABEL_75;
  }
  v90 = 0.0;
  v50 = v84;
  v51 = *(__int64 (__fastcall **)(__int64, __int64, double *))(*(_QWORD *)v84 + 88LL);
  v72 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"TotalResultCount", 0x11u, 0x10u);
  v52 = v51(v50, (__int64)v72, &v90);
  v7 = v52;
  if ( v52 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x478,
      (unsigned int)"pcshell\\shell\\systemsettings\\adminflows\\languagemanager\\lib\\languagemanagersingleton.cpp",
      (const char *)(unsigned int)v52,
      (int)v75);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v84);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v85);
    WindowsDeleteString(string);
    string = 0;
    v53 = v76;
    if ( v76 )
    {
      v76 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v53 + 16LL))(v53);
    }
    v54 = *(_QWORD *)v75;
    if ( *(_QWORD *)v75 )
    {
      *(_QWORD *)v75 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v54 + 16LL))(v54);
    }
    goto LABEL_75;
  }
  if ( v90 < 1.0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x479,
      (unsigned int)"pcshell\\shell\\systemsettings\\adminflows\\languagemanager\\lib\\languagemanagersingleton.cpp",
      (const char *)0x80070490LL,
      (int)v75);
  v87 = 0;
  v55 = v84;
  v56 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v84 + 72LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v87);
  v72 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"BigIds", 7u, 6u);
  v57 = v56(v55, (__int64)v72, &v87);
  v7 = v57;
  if ( v57 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x47C,
      (unsigned int)"pcshell\\shell\\systemsettings\\adminflows\\languagemanager\\lib\\languagemanagersingleton.cpp",
      (const char *)(unsigned int)v57,
      (int)v75);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v87);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v84);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v85);
    WindowsDeleteString(string);
    string = 0;
    v58 = v76;
    if ( v76 )
    {
      v76 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v58 + 16LL))(v58);
    }
    v59 = *(_QWORD *)v75;
    if ( *(_QWORD *)v75 )
    {
      *(_QWORD *)v75 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v59 + 16LL))(v59);
    }
    goto LABEL_75;
  }
  v86 = 0;
  v60 = v87;
  v61 = *(__int64 (__fastcall **)(__int64, _QWORD, HSTRING *))(*(_QWORD *)v87 + 64LL);
  WindowsDeleteString(0);
  v86 = 0;
  v62 = v61(v60, 0, &v86);
  v7 = v62;
  if ( v62 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x47F,
      (unsigned int)"pcshell\\shell\\systemsettings\\adminflows\\languagemanager\\lib\\languagemanagersingleton.cpp",
      (const char *)(unsigned int)v62,
      (int)v75);
    WindowsDeleteString(v86);
    v86 = 0;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v87);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v84);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v85);
    WindowsDeleteString(string);
    string = 0;
    v63 = v76;
    if ( v76 )
    {
      v76 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v63 + 16LL))(v63);
    }
    v64 = *(_QWORD *)v75;
    if ( *(_QWORD *)v75 )
    {
      *(_QWORD *)v75 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v64 + 16LL))(v64);
    }
    goto LABEL_75;
  }
  StringRawBuffer = WindowsGetStringRawBuffer(v86, 0);
  v67 = -1;
  do
    ++v67;
  while ( StringRawBuffer[v67] );
  std::wstring::_Assign<unsigned short>(a3, StringRawBuffer, v67);
  WindowsDeleteString(v86);
  v86 = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v87);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v84);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v85);
  WindowsDeleteString(string);
  string = 0;
  v68 = v76;
  if ( v76 )
  {
    v76 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v68 + 16LL))(v68);
  }
  v69 = *(_QWORD *)v75;
  if ( *(_QWORD *)v75 )
  {
    *(_QWORD *)v75 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v69 + 16LL))(v69);
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v83);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v82);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v81);
  WindowsDeleteString(v74);
  v74 = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v79);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v78);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v77);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v88);
  return 0;
}

```

## disassembly

```asm
0x140052e9c  mov     [rsp-8+arg_0], rbx
0x140052ea1  push    rbp
0x140052ea2  push    rsi
0x140052ea3  push    rdi
0x140052ea4  push    r14
0x140052ea6  push    r15
0x140052ea8  lea     rbp, [rsp-37h]
0x140052ead  sub     rsp, 0F0h
0x140052eb4  mov     rax, cs:__security_cookie
0x140052ebb  xor     rax, rsp
0x140052ebe  mov     [rbp+57h+var_30], rax
0x140052ec2  mov     r14, r8
0x140052ec5  mov     rsi, rdx
0x140052ec8  xor     r15d, r15d
0x140052ecb  mov     dword ptr [rbp+57h+var_C0], r15d
0x140052ecf  mov     [rbp+57h+var_48], r15
0x140052ed3  mov     [rbp+57h+var_C8], r15
0x140052ed7  lea     r9d, [r15+1Bh]; unsigned int
0x140052edb  lea     r8d, [r15+1Ch]; unsigned int
0x140052edf  lea     rdx, ?RuntimeClass_Windows_Data_Json_JsonValue@@3QBGB; "Windows.Data.Json.JsonValue"
0x140052ee6  lea     rcx, [rsp+110h+hstringHeader]; hstringHeader
0x140052eeb  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x140052ef0  mov     rbx, [rbp+57h+var_C8]
0x140052ef4  lea     rcx, [rbp+57h+var_48]
0x140052ef8  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x140052efd  lea     r8, [rbp+57h+var_48]
0x140052f01  lea     rdx, _GUID_5f6b544a_2f53_48e1_91a3_f78b50a6345c
0x140052f08  mov     rcx, rbx
0x140052f0b  call    cs:__imp_RoGetActivationFactory
0x140052f11  mov     ebx, eax
0x140052f13  test    eax, eax
0x140052f15  jns     short loc_140052F34
0x140052f17  mov     rcx, [rbp+5Fh]; this
0x140052f1b  mov     r9d, eax; char *
0x140052f1e  lea     r8, aPcshellShellSy_0; "pcshell\\shell\\systemsettings\\adminfl"...
0x140052f25  mov     edx, 441h; void *
0x140052f2a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140052f2f  jmp     loc_1400537BC
0x140052f34  mov     [rbp+57h+var_A0], r15
0x140052f38  mov     rdi, [rbp+57h+var_48]
0x140052f3c  mov     rax, [rdi]
0x140052f3f  mov     rbx, [rax+50h]
0x140052f43  lea     rcx, [rbp+57h+var_A0]
0x140052f47  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x140052f4c  mov     rcx, rsi
0x140052f4f  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x140052f54  mov     [rbp+57h+var_C0], rax
0x140052f58  lea     rdx, [rbp+57h+var_C0]
0x140052f5c  lea     rcx, [rsp+110h+hstringHeader]
0x140052f61  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x140052f66  nop
0x140052f67  lea     r8, [rbp+57h+var_A0]
0x140052f6b  mov     rdx, [rax+18h]
0x140052f6f  mov     rcx, rdi
0x140052f72  mov     rax, rbx
0x140052f75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140052f7a  mov     ebx, eax
0x140052f7c  test    eax, eax
0x140052f7e  jns     short loc_140052F9D
0x140052f80  mov     rcx, [rbp+5Fh]; this
0x140052f84  mov     r9d, eax; char *
0x140052f87  lea     r8, aPcshellShellSy_0; "pcshell\\shell\\systemsettings\\adminfl"...
0x140052f8e  mov     edx, 445h; void *
0x140052f93  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140052f98  jmp     loc_1400537B2
0x140052f9d  mov     [rbp+57h+var_98], r15
0x140052fa1  mov     [rbp+57h+var_C8], r15
0x140052fa5  mov     r9d, 1Ch; unsigned int
0x140052fab  lea     r8d, [r9+1]; unsigned int
0x140052faf  lea     rdx, ?RuntimeClass_Windows_Data_Json_JsonObject@@3QBGB; "Windows.Data.Json.JsonObject"
0x140052fb6  lea     rcx, [rsp+110h+hstringHeader]; hstringHeader
0x140052fbb  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x140052fc0  lea     rdx, [rbp+57h+var_98]
0x140052fc4  mov     rcx, [rbp+57h+var_C8]
0x140052fc8  call    ??$ActivateInstance@V?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>>)
0x140052fcd  mov     ebx, eax
0x140052fcf  test    eax, eax
0x140052fd1  jns     short loc_140052FF0
0x140052fd3  mov     edx, 449h; void *
0x140052fd8  lea     r8, aPcshellShellSy_0; "pcshell\\shell\\systemsettings\\adminfl"...
0x140052fdf  mov     r9d, eax; char *
0x140052fe2  mov     rcx, [rbp+5Fh]; this
0x140052fe6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140052feb  jmp     loc_1400537A8
0x140052ff0  mov     rsi, [rbp+57h+var_98]
0x140052ff4  mov     rax, [rsi]
0x140052ff7  mov     rdi, [rax+38h]
0x140052ffb  mov     rbx, [rbp+57h+var_A0]
0x140052fff  mov     [rbp+57h+var_C8], r15
0x140053003  mov     r9d, 11h; unsigned int
0x140053009  lea     r8d, [r9+1]; unsigned int
0x14005300d  lea     rdx, aPackagefamilyn; "packageFamilyName"
0x140053014  lea     rcx, [rsp+110h+hstringHeader]; hstringHeader
0x140053019  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x14005301e  nop
0x14005301f  mov     r8, rbx
0x140053022  mov     rdx, [rbp+57h+var_C8]
0x140053026  mov     rcx, rsi
0x140053029  mov     rax, rdi
0x14005302c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140053031  mov     ebx, eax
0x140053033  test    eax, eax
0x140053035  jns     short loc_14005303E
0x140053037  mov     edx, 44Ch
0x14005303c  jmp     short loc_140052FD8
0x14005303e  mov     [rbp+57h+var_90], r15
0x140053042  mov     rbx, [rbp+57h+var_98]
0x140053046  mov     rax, [rbx]
0x140053049  mov     rdi, [rax]
0x14005304c  lea     rcx, [rbp+57h+var_90]
0x140053050  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x140053055  lea     r8, [rbp+57h+var_90]
0x140053059  lea     rdx, _GUID_a3219ecb_f0b3_4dcd_beee_19d48cd3ed1e
0x140053060  mov     rcx, rbx
0x140053063  mov     rax, rdi
0x140053066  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005306b  mov     ebx, eax
0x14005306d  test    eax, eax
0x14005306f  jns     short loc_14005308E
0x140053071  mov     rcx, [rbp+5Fh]; this
0x140053075  mov     r9d, eax; char *
0x140053078  lea     r8, aPcshellShellSy_0; "pcshell\\shell\\systemsettings\\adminfl"...
0x14005307f  mov     edx, 44Fh; void *
0x140053084  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140053089  jmp     loc_14005379E
0x14005308e  mov     [rbp+57h+var_B8], r15
0x140053092  mov     rdi, [rbp+57h+var_90]
0x140053096  mov     rax, [rdi]
0x140053099  mov     rbx, [rax+38h]
0x14005309d  xor     ecx, ecx; string
0x14005309f  call    cs:__imp_WindowsDeleteString
0x1400530a5  mov     [rbp+57h+var_B8], r15
0x1400530a9  lea     rdx, [rbp+57h+var_B8]
0x1400530ad  mov     rcx, rdi
0x1400530b0  mov     rax, rbx
0x1400530b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400530b8  mov     ebx, eax
0x1400530ba  test    eax, eax
0x1400530bc  jns     short loc_1400530DB
0x1400530be  mov     rcx, [rbp+5Fh]; this
0x1400530c2  mov     r9d, eax; char *
0x1400530c5  lea     r8, aPcshellShellSy_0; "pcshell\\shell\\systemsettings\\adminfl"...
0x1400530cc  mov     edx, 452h; void *
0x1400530d1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400530d6  jmp     loc_140053790
0x1400530db  mov     [rbp+57h+var_80], r15
0x1400530df  mov     [rbp+57h+var_C8], r15
0x1400530e3  mov     r9d, 23h ; '#'; unsigned int
0x1400530e9  lea     r8d, [r9+1]; unsigned int
0x1400530ed  lea     rdx, ?RuntimeClass_Windows_Services_Store_StoreContext@@3QBGB; "Windows.Services.Store.StoreContext"
0x1400530f4  lea     rcx, [rsp+110h+hstringHeader]; hstringHeader
0x1400530f9  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1400530fe  mov     rbx, [rbp+57h+var_C8]
0x140053102  lea     rcx, [rbp+57h+var_80]
0x140053106  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x14005310b  lea     r8, [rbp+57h+var_80]
0x14005310f  lea     rdx, _GUID_9c06ee5f_15c0_4e72_9330_d6191cebd19c
0x140053116  mov     rcx, rbx
0x140053119  call    cs:__imp_RoGetActivationFactory
0x14005311f  mov     ebx, eax
0x140053121  test    eax, eax
0x140053123  jns     short loc_140053142
0x140053125  mov     rcx, [rbp+5Fh]; this
0x140053129  mov     r9d, eax; char *
0x14005312c  lea     r8, aPcshellShellSy_0; "pcshell\\shell\\systemsettings\\adminfl"...
0x140053133  mov     edx, 457h; void *
0x140053138  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14005313d  jmp     loc_140053786
0x140053142  mov     [rbp+57h+var_78], r15
0x140053146  mov     rdi, [rbp+57h+var_80]
0x14005314a  mov     rax, [rdi]
0x14005314d  mov     rbx, [rax+30h]
0x140053151  lea     rcx, [rbp+57h+var_78]
0x140053155  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x14005315a  lea     rdx, [rbp+57h+var_78]
0x14005315e  mov     rcx, rdi
0x140053161  mov     rax, rbx
0x140053164  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140053169  mov     ebx, eax
0x14005316b  test    eax, eax
0x14005316d  jns     short loc_14005318C
0x14005316f  mov     rcx, [rbp+5Fh]; this
0x140053173  mov     r9d, eax; char *
0x140053176  lea     r8, aPcshellShellSy_0; "pcshell\\shell\\systemsettings\\adminfl"...
0x14005317d  mov     edx, 45Ah; void *
0x140053182  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140053187  jmp     loc_14005377C
0x14005318c  mov     [rbp+57h+var_70], r15
0x140053190  mov     [rbp+57h+var_C8], r15
0x140053194  mov     r9d, 29h ; ')'; unsigned int
0x14005319a  lea     r8d, [r9+1]; unsigned int
0x14005319e  lea     rdx, ?RuntimeClass_Windows_Services_Store_StoreRequestHelper@@3QBGB; "Windows.Services.Store.StoreRequestHelp"...
0x1400531a5  lea     rcx, [rsp+110h+hstringHeader]; hstringHeader
0x1400531aa  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1400531af  mov     rbx, [rbp+57h+var_C8]
0x1400531b3  lea     rcx, [rbp+57h+var_70]
0x1400531b7  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1400531bc  lea     r8, [rbp+57h+var_70]
0x1400531c0  lea     rdx, _GUID_6ce5e5f9_a0c9_4b2c_96a6_a171c630038d
0x1400531c7  mov     rcx, rbx
0x1400531ca  call    cs:__imp_RoGetActivationFactory
0x1400531d0  mov     ebx, eax
0x1400531d2  test    eax, eax
0x1400531d4  jns     short loc_1400531F3
0x1400531d6  mov     rcx, [rbp+5Fh]; this
0x1400531da  mov     r9d, eax; char *
0x1400531dd  lea     r8, aPcshellShellSy_0; "pcshell\\shell\\systemsettings\\adminfl"...
0x1400531e4  mov     edx, 45Fh; void *
0x1400531e9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400531ee  jmp     loc_140053772
0x1400531f3  mov     qword ptr [rbp+57h+var_B0], r15
0x1400531f7  mov     rcx, [rbp+57h+var_70]
0x1400531fb  mov     rax, [rcx]
0x1400531fe  lea     rdx, [rbp+57h+var_B0]
0x140053202  mov     qword ptr [rsp+110h+var_F0], rdx; int
0x140053207  mov     r9, [rbp+57h+var_B8]
0x14005320b  mov     r8d, 9
0x140053211  mov     rdx, [rbp+57h+var_78]
0x140053215  mov     rax, [rax+30h]
0x140053219  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005321e  mov     ebx, eax
0x140053220  test    eax, eax
0x140053222  jns     short loc_14005325C
0x140053224  mov     rcx, [rbp+5Fh]; this
0x140053228  mov     r9d, eax; char *
0x14005322b  lea     r8, aPcshellShellSy_0; "pcshell\\shell\\systemsettings\\adminfl"...
0x140053232  mov     edx, 466h; void *
0x140053237  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14005323c  nop
0x14005323d  mov     rcx, qword ptr [rbp+57h+var_B0]
0x140053241  test    rcx, rcx
0x140053244  jz      short loc_140053257
0x140053246  mov     qword ptr [rbp+57h+var_B0], r15
0x14005324a  mov     rax, [rcx]
0x14005324d  mov     rax, [rax+10h]
0x140053251  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140053256  nop
0x140053257  jmp     loc_140053772
0x14005325c  mov     rbx, qword ptr [rbp+57h+var_B0]
0x140053260  mov     [rbp+57h+var_A8], r15
0x140053264  mov     dword ptr [rbp+57h+var_C0], 2
0x14005326b  mov     rcx, rbx
0x14005326e  call    ??$WaitForCompletion@PEAU?$IAsyncOperation@PEAVStoreSendRequestResult@Store@Services@Windows@@@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperation@PEAVStoreSendRequestResult@Store@Services@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z; wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Services::Store::StoreSendRequestResult *> *>(Windows::Foundation::IAsyncOperation<Windows::Services::Store::StoreSendRequestResult *> *,tagCOWAIT_FLAGS,ulong,bool *)
0x140053273  test    eax, eax
0x140053275  js      short loc_14005328B
0x140053277  mov     rax, [rbx]
0x14005327a  lea     rdx, [rbp+57h+var_A8]
0x14005327e  mov     rcx, rbx
0x140053281  mov     rax, [rax+40h]
0x140053285  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005328a  nop
0x14005328b  mov     rcx, [rbp+5Fh]; this
0x14005328f  test    eax, eax
0x140053291  js      loc_1400538F0
0x140053297  mov     dword ptr [rbp+57h+var_40], r15d
0x14005329b  mov     rcx, [rbp+57h+var_A8]
0x14005329f  mov     rax, [rcx]
0x1400532a2  lea     rdx, [rbp+57h+var_40]
0x1400532a6  mov     rax, [rax+38h]
0x1400532aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400532af  mov     ebx, eax
0x1400532b1  test    eax, eax
0x1400532b3  jns     short loc_140053307
0x1400532b5  mov     rcx, [rbp+5Fh]; this
0x1400532b9  mov     r9d, eax; char *
0x1400532bc  lea     r8, aPcshellShellSy_0; "pcshell\\shell\\systemsettings\\adminfl"...
0x1400532c3  mov     edx, 46Bh; void *
0x1400532c8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400532cd  nop
0x1400532ce  mov     rcx, [rbp+57h+var_A8]
0x1400532d2  test    rcx, rcx
0x1400532d5  jz      short loc_1400532E8
0x1400532d7  mov     [rbp+57h+var_A8], r15
0x1400532db  mov     rax, [rcx]
0x1400532de  mov     rax, [rax+10h]
0x1400532e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400532e7  nop
0x1400532e8  mov     rcx, qword ptr [rbp+57h+var_B0]
0x1400532ec  test    rcx, rcx
0x1400532ef  jz      short loc_140053302
0x1400532f1  mov     qword ptr [rbp+57h+var_B0], r15
0x1400532f5  mov     rax, [rcx]
0x1400532f8  mov     rax, [rax+10h]
0x1400532fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140053301  nop
0x140053302  jmp     loc_140053772
0x140053307  mov     ebx, dword ptr [rbp+57h+var_40]
0x14005330a  test    ebx, ebx
0x14005330c  jns     short loc_140053360
0x14005330e  mov     rcx, [rbp+5Fh]; this
0x140053312  mov     r9d, ebx; char *
0x140053315  lea     r8, aPcshellShellSy_0; "pcshell\\shell\\systemsettings\\adminfl"...
0x14005331c  mov     edx, 46Ch; void *
0x140053321  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140053326  nop
0x140053327  mov     rcx, [rbp+57h+var_A8]
0x14005332b  test    rcx, rcx
0x14005332e  jz      short loc_140053341
0x140053330  mov     [rbp+57h+var_A8], r15
0x140053334  mov     rax, [rcx]
  ... truncated ...
```
