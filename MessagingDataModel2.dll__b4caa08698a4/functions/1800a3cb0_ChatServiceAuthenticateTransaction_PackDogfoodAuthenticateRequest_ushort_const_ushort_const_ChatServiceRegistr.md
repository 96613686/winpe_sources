# ChatServiceAuthenticateTransaction::_PackDogfoodAuthenticateRequest(ushort const *,ushort const *,ChatServiceRegistrationToken *)

- ea: `0x1800a3cb0`
- end: `0x1800a47ab`
- name: `?_PackDogfoodAuthenticateRequest@ChatServiceAuthenticateTransaction@@AEAAJPEBG0PEAVChatServiceRegistrationToken@@@Z`
- size: `2811`
- prototype: `int(ChatServiceAuthenticateTransaction *__hidden this, const unsigned __int16 *, const unsigned __int16 *, struct ChatServiceRegistrationToken *)`
- caller_count: `0`
- callee_count: `20`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180008870`
- `0x18000a754`
- `0x18000b7d4`
- `0x1800176b4`
- `0x180030bd0`
- `0x18006b108`
- `0x180084738`
- `0x1800847b8`
- `0x180084864`
- `0x1800848b4`
- `0x18009dc9c`
- `0x1800a3004`
- `0x1800a3360`
- `0x1800a33f8`
- `0x1800a3718`
- `0x1800a3898`
- `0x1800a3a40`
- `0x1800a3cb0`
- `0x1800c6940`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800a3e20`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800a3ef4`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800a3faf`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800a40bd`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800a4404`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800a456f`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800a3e20`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800a3ef4`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800a3faf`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800a40bd`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800a4404`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800a456f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a44fa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a452f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a465c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a44fa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a452f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a465c`

## string_xrefs

- `0x1800a3df6`: `Windows.Foundation.Uri`
- `0x1800a43da`: `Windows.Data.Json.JsonValue`
- `0x1800a434e`: `Windows.Data.Json.JsonObject`

## pseudocode

```c
__int64 __fastcall ChatServiceAuthenticateTransaction::_PackDogfoodAuthenticateRequest(
        ChatServiceAuthenticateTransaction *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        struct ChatServiceRegistrationToken *a4)
{
  __int64 v6; // r9
  __int64 v7; // rbx
  __int64 v8; // r8
  __int64 v9; // r8
  unsigned int v10; // ebx
  int ActivationFactory; // eax
  char v12; // r8
  __int64 v13; // rdi
  __int64 (__fastcall *v14)(__int64, PVOID, struct Windows::Foundation::IUriRuntimeClass **); // rbx
  HSTRING_HEADER *v15; // rax
  int v16; // eax
  ChatServiceTransaction *v17; // rcx
  int v18; // eax
  __int64 v19; // rcx
  int v20; // eax
  __int64 v21; // rcx
  int v22; // eax
  __int64 v23; // rcx
  int v24; // eax
  __int64 v25; // rcx
  int v26; // eax
  struct Windows::Web::Http::Headers::IHttpRequestHeaderCollection *v27; // rcx
  int v28; // eax
  char v29; // r8
  __int64 v30; // rcx
  __int64 v31; // rsi
  __int64 (__fastcall *v32)(__int64, PVOID, PVOID, __int64 *); // rdi
  PVOID Reserved1; // rbx
  char v34; // r8
  HSTRING_HEADER *v35; // rax
  int v36; // eax
  __int64 v37; // rcx
  int v38; // eax
  __int64 (__fastcall ***v39)(_QWORD, GUID *, __int64); // rcx
  int v40; // eax
  __int64 v41; // rcx
  int LockAndKeyHeaderValue; // eax
  char v43; // r8
  struct Windows::Web::Http::Headers::IHttpRequestHeaderCollection *v44; // rsi
  __int64 (__fastcall *v45)(struct Windows::Web::Http::Headers::IHttpRequestHeaderCollection *, PVOID, PVOID); // rdi
  PVOID v46; // rbx
  char v47; // r8
  HSTRING_HEADER *v48; // rax
  ChatServiceAuthenticateTransaction *v49; // rcx
  struct Windows::Web::Http::Headers::IHttpRequestHeaderCollection *v50; // rsi
  __int64 (__fastcall *v51)(struct Windows::Web::Http::Headers::IHttpRequestHeaderCollection *, __int64, PVOID); // rdi
  char v52; // r8
  PVOID v53; // rbx
  int v54; // eax
  int v55; // eax
  int v56; // eax
  __int64 v57; // rdx
  int v58; // eax
  char v59; // r8
  __int64 v60; // rsi
  __int64 v61; // rbx
  __int64 (__fastcall *v62)(__int64, PVOID, __int64, _BYTE *); // rdi
  HSTRING_HEADER *v63; // rax
  int v64; // eax
  __int64 v65; // rdi
  __int64 (__fastcall *v66)(__int64, HSTRING *); // rbx
  int v67; // eax
  int v68; // eax
  __int64 v69; // rcx
  int v70; // eax
  __int64 v71; // rcx
  __int64 v72; // rcx
  __int64 v73; // rcx
  __int64 (__fastcall ***v74)(_QWORD, GUID *, __int64); // rcx
  __int64 v75; // rcx
  __int64 v76; // rcx
  struct Windows::Web::Http::Headers::IHttpRequestHeaderCollection *v77; // rcx
  __int64 v78; // rcx
  __int64 v79; // rcx
  __int64 v80; // rcx
  __int64 v81; // rcx
  HSTRING_HEADER hstringHeader; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v84; // [rsp+48h] [rbp-B8h]
  const WCHAR *v85; // [rsp+50h] [rbp-B0h] BYREF
  HSTRING_HEADER v86; // [rsp+58h] [rbp-A8h] BYREF
  const WCHAR *ClientInfoValue; // [rsp+78h] [rbp-88h] BYREF
  __int64 v88; // [rsp+80h] [rbp-80h] BYREF
  __int64 v89; // [rsp+88h] [rbp-78h] BYREF
  __int64 v90; // [rsp+90h] [rbp-70h] BYREF
  __int64 v91; // [rsp+98h] [rbp-68h] BYREF
  struct Windows::Web::Http::Headers::IHttpRequestHeaderCollection *v92; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v93; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v94; // [rsp+B0h] [rbp-50h] BYREF
  __int64 (__fastcall ***v95)(_QWORD, GUID *, __int64); // [rsp+B8h] [rbp-48h] BYREF
  struct Windows::Foundation::IUriRuntimeClass *v96; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v97; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v98; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v99[8]; // [rsp+D8h] [rbp-28h] BYREF
  __int64 (__fastcall ***v100)(_QWORD, GUID *, __int64); // [rsp+E0h] [rbp-20h] BYREF
  HSTRING string; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v102; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v103; // [rsp+F8h] [rbp-8h] BYREF
  __int64 v104; // [rsp+100h] [rbp+0h] BYREF
  __int64 v105; // [rsp+108h] [rbp+8h] BYREF
  __int64 v106; // [rsp+110h] [rbp+10h] BYREF
  __int64 v107; // [rsp+118h] [rbp+18h] BYREF
  _OWORD v108[2]; // [rsp+120h] [rbp+20h] BYREF
  _OWORD v109[2]; // [rsp+140h] [rbp+40h] BYREF

  ClientInfoValue = a3;
  memset(v109, 0, sizeof(v109));
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(v109);
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                           v109,
                           v6) )
    goto LABEL_12;
  v7 = -1;
  v8 = -1;
  do
    ++v8;
  while ( c_pRestApiVersionUri[v8] );
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                           v109,
                           L"v1/",
                           v8) )
    goto LABEL_12;
  v9 = -1;
  do
    ++v9;
  while ( c_pRestApiUsersUri[v9] );
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                           v109,
                           L"users/",
                           v9) )
    goto LABEL_12;
  do
    ++v7;
  while ( c_pRestApiMeUri[v7] );
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                           v109,
                           L"ME/",
                           v7)
    || !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                           v109,
                           L"properties",
                           10)
    || !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                           v109,
                           L"?name=dogfoodUser",
                           17) )
  {
LABEL_12:
    v10 = -2147024882;
    Log_HREvent_79(-2147024882);
    goto LABEL_110;
  }
  v97 = 0;
  v84 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"Windows.Foundation.Uri", 0x17u, 0x16u);
  ActivationFactory = RoGetActivationFactory(v84, &GUID_44a9796f_723e_4fdf_a218_033e75b0c084, &v97);
  v10 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    Log_HREvent_79(ActivationFactory);
LABEL_15:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v97);
    goto LABEL_110;
  }
  v13 = v97;
  v96 = 0;
  v85 = *(const WCHAR **)&v109[0];
  v14 = *(__int64 (__fastcall **)(__int64, PVOID, struct Windows::Foundation::IUriRuntimeClass **))(*(_QWORD *)v97 + 48LL);
  v15 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v85, v12);
  v16 = v14(v13, v15[1].Reserved.Reserved1, &v96);
  v10 = v16;
  if ( v16 < 0 || (v16 = ChatServiceTransaction::_RemoveAuthCookie(v17, v96), v10 = v16, v16 < 0) )
  {
    Log_HREvent_79(v16);
LABEL_18:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v96);
    goto LABEL_15;
  }
  v88 = 0;
  v84 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Web.Http.HttpMethod",
    0x1Cu,
    0x1Bu);
  v18 = RoGetActivationFactory(v84, &GUID_64d171f0_d99a_4153_8dc6_d68cc4cce317, &v88);
  v10 = v18;
  if ( v18 < 0 )
  {
    Log_HREvent_79(v18);
LABEL_22:
    v19 = v88;
    if ( v88 )
    {
      v88 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
    }
    goto LABEL_18;
  }
  v89 = 0;
  v20 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v88 + 96LL))(v88, &v89);
  v10 = v20;
  if ( v20 < 0 )
  {
    Log_HREvent_79(v20);
LABEL_26:
    v21 = v89;
    if ( v89 )
    {
      v89 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
    }
    goto LABEL_22;
  }
  v91 = 0;
  v84 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Web.Http.HttpRequestMessage",
    0x24u,
    0x23u);
  v22 = RoGetActivationFactory(v84, &GUID_5bac994e_3886_412e_aec3_52ec7f25616f, &v91);
  v10 = v22;
  if ( v22 < 0 )
  {
    Log_HREvent_79(v22);
LABEL_30:
    v23 = v91;
    if ( v91 )
    {
      v91 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
    }
    goto LABEL_26;
  }
  v90 = 0;
  v24 = (*(__int64 (__fastcall **)(__int64, __int64, struct Windows::Foundation::IUriRuntimeClass *, __int64 *))(*(_QWORD *)v91 + 48LL))(
          v91,
          v89,
          v96,
          &v90);
  v10 = v24;
  if ( v24 < 0 )
  {
    Log_HREvent_79(v24);
LABEL_34:
    v25 = v90;
    if ( v90 )
    {
      v90 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
    }
    goto LABEL_30;
  }
  v92 = 0;
  v26 = (*(__int64 (__fastcall **)(__int64, struct Windows::Web::Http::Headers::IHttpRequestHeaderCollection **))(*(_QWORD *)v90 + 64LL))(
          v90,
          &v92);
  v10 = v26;
  if ( v26 < 0 )
  {
    Log_HREvent_79(v26);
LABEL_38:
    v27 = v92;
    if ( v92 )
    {
      v92 = 0;
      (*(void (__fastcall **)(struct Windows::Web::Http::Headers::IHttpRequestHeaderCollection *))(*(_QWORD *)v27 + 16LL))(v27);
    }
    goto LABEL_34;
  }
  v93 = 0;
  v84 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Web.Http.Headers.HttpCookiePairHeaderValue",
    0x33u,
    0x32u);
  v28 = RoGetActivationFactory(v84, &GUID_635e326f_146f_4f56_aa21_2cb7d6d58b1e, &v93);
  v10 = v28;
  if ( v28 < 0 )
  {
    Log_HREvent_79(v28);
LABEL_42:
    v30 = v93;
    if ( v93 )
    {
      v93 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
    }
    goto LABEL_38;
  }
  v31 = v93;
  v94 = 0;
  v32 = *(__int64 (__fastcall **)(__int64, PVOID, PVOID, __int64 *))(*(_QWORD *)v93 + 56LL);
  Reserved1 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &ClientInfoValue, v29)[1].Reserved.Reserved1;
  v35 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v86, (const WCHAR **)off_1800FD800, v34);
  v36 = v32(v31, v35[1].Reserved.Reserved1, Reserved1, &v94);
  v10 = v36;
  if ( v36 < 0 )
  {
    Log_HREvent_79(v36);
LABEL_46:
    v37 = v94;
    if ( v94 )
    {
      v94 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
    }
    goto LABEL_42;
  }
  v95 = 0;
  v38 = (*(__int64 (__fastcall **)(struct Windows::Web::Http::Headers::IHttpRequestHeaderCollection *, __int64 (__fastcall ****)(_QWORD, GUID *, __int64)))(*(_QWORD *)v92 + 104LL))(
          v92,
          &v95);
  v10 = v38;
  if ( v38 < 0 )
  {
    Log_HREvent_79(v38);
    goto LABEL_50;
  }
  v98 = 0;
  v40 = Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpCookiePairHeaderValueCollection>::As<Windows::Foundation::Collections::IVector<Windows::Web::Http::Headers::HttpCookiePairHeaderValue *>>(
          &v95,
          (__int64)&v98);
  v10 = v40;
  if ( v40 < 0
    || (v40 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v98 + 104LL))(v98, v94), v10 = v40, v40 < 0) )
  {
    Log_HREvent_79(v40);
LABEL_54:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v98);
LABEL_50:
    v39 = v95;
    if ( v95 )
    {
      v95 = 0;
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64)))(*v39)[2])(v39);
    }
    goto LABEL_46;
  }
  memset(v108, 0, sizeof(v108));
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(v108);
  LockAndKeyHeaderValue = ChatServiceAuthenticateTransaction::_GenerateLockAndKeyHeaderValue(v41, v108);
  v10 = LockAndKeyHeaderValue;
  if ( LockAndKeyHeaderValue < 0 )
    goto LABEL_57;
  v44 = v92;
  v45 = *(__int64 (__fastcall **)(struct Windows::Web::Http::Headers::IHttpRequestHeaderCollection *, PVOID, PVOID))(*(_QWORD *)v92 + 264LL);
  ClientInfoValue = *(const WCHAR **)&v108[0];
  v46 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v86, &ClientInfoValue, v43)[1].Reserved.Reserved1;
  v48 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, (const WCHAR **)off_1800FD7F8, v47);
  LockAndKeyHeaderValue = v45(v44, v48[1].Reserved.Reserved1, v46);
  v10 = LockAndKeyHeaderValue;
  if ( LockAndKeyHeaderValue < 0 )
    goto LABEL_57;
  LockAndKeyHeaderValue = ChatServiceAuthenticateTransaction::_AppendRegistrationTokenHeader(v49, v92, a4);
  v10 = LockAndKeyHeaderValue;
  if ( LockAndKeyHeaderValue < 0 )
    goto LABEL_57;
  v50 = v92;
  v51 = *(__int64 (__fastcall **)(struct Windows::Web::Http::Headers::IHttpRequestHeaderCollection *, __int64, PVOID))(*(_QWORD *)v92 + 264LL);
  ClientInfoValue = ChatServiceTransaction::get_ClientInfoValue();
  v53 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v86, &ClientInfoValue, v52)[1].Reserved.Reserved1;
  v84 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"ClientInfo", 0xBu, 0xAu);
  LockAndKeyHeaderValue = v51(v50, v84, v53);
  v10 = LockAndKeyHeaderValue;
  if ( LockAndKeyHeaderValue < 0 )
  {
LABEL_57:
    Log_HREvent_79(LockAndKeyHeaderValue);
LABEL_58:
    utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v108);
    goto LABEL_54;
  }
  v100 = 0;
  v84 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Data.Json.JsonObject",
    0x1Du,
    0x1Cu);
  v54 = Windows::Foundation::ActivateInstance<Windows::Data::Json::IJsonObject>(v84, &v100);
  v10 = v54;
  if ( v54 < 0 )
  {
    Log_HREvent_79(v54);
LABEL_64:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v100);
    goto LABEL_58;
  }
  v102 = 0;
  v55 = Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>::As<Windows::Foundation::Collections::IMap<HSTRING__ *,Windows::Data::Json::IJsonValue *>>(
          &v100,
          (__int64)&v102);
  v10 = v55;
  if ( v55 < 0 )
  {
    Log_HREvent_79(v55);
LABEL_67:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v102);
    goto LABEL_64;
  }
  v103 = 0;
  v84 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Data.Json.JsonValue",
    0x1Cu,
    0x1Bu);
  v56 = RoGetActivationFactory(v84, &GUID_5f6b544a_2f53_48e1_91a3_f78b50a6345c, &v103);
  v10 = v56;
  if ( v56 < 0 )
  {
    Log_HREvent_79(v56);
LABEL_70:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v103);
    goto LABEL_67;
  }
  v105 = 0;
  LOBYTE(v57) = 1;
  v58 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v103 + 64LL))(v103, v57, &v105);
  v10 = v58;
  if ( v58 < 0
    || (v60 = v102,
        v61 = v105,
        v99[0] = 0,
        v62 = *(__int64 (__fastcall **)(__int64, PVOID, __int64, _BYTE *))(*(_QWORD *)v102 + 80LL),
        v63 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v86, (const WCHAR **)off_1800FD7F0, v59),
        v58 = v62(v60, v63[1].Reserved.Reserved1, v61, v99),
        v10 = v58,
        v58 < 0) )
  {
    Log_HREvent_79(v58);
LABEL_73:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v105);
    goto LABEL_70;
  }
  v107 = 0;
  v64 = Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>::As<Windows::Data::Json::IJsonValue>(
          &v100,
          (__int64)&v107);
  v10 = v64;
  if ( v64 < 0 )
  {
    Log_HREvent_79(v64);
LABEL_77:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v107);
    goto LABEL_73;
  }
  v65 = v107;
  string = 0;
  v66 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v107 + 56LL);
  WindowsDeleteString(0);
  string = 0;
  v67 = v66(v65, &string);
  v10 = v67;
  if ( v67 < 0 )
  {
    Log_HREvent_79(v67);
LABEL_80:
    WindowsDeleteString(string);
    string = 0;
    goto LABEL_77;
  }
  v104 = 0;
  v84 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Web.Http.HttpStringContent",
    0x23u,
    0x22u);
  v68 = RoGetActivationFactory(v84, &GUID_46649d5b_2e93_48eb_8e61_19677878e57f, &v104);
  v10 = v68;
  if ( v68 < 0 )
  {
    Log_HREvent_79(v68);
LABEL_83:
    v69 = v104;
    if ( v104 )
    {
      v104 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v69 + 16LL))(v69);
    }
    goto LABEL_80;
  }
  v106 = 0;
  v70 = (*(__int64 (__fastcall **)(__int64, HSTRING, __int64 *))(*(_QWORD *)v104 + 48LL))(v104, string, &v106);
  v10 = v70;
  if ( v70 < 0
    || (v70 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v90 + 56LL))(v90, v106), v10 = v70, v70 < 0) )
  {
    Log_HREvent_79(v70);
    v71 = v106;
    if ( v106 )
    {
      v106 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v71 + 16LL))(v71);
    }
    goto LABEL_83;
  }
  Microsoft::WRL::ComPtr<Windows::Web::Http::IHttpRequestMessage>::operator=((char *)this + 8, &v90);
  v72 = v106;
  if ( v106 )
  {
    v106 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v72 + 16LL))(v72);
  }
  v73 = v104;
  if ( v104 )
  {
    v104 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v73 + 16LL))(v73);
  }
  WindowsDeleteString(string);
  string = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v107);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v105);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v103);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v102);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v100);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v108);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v98);
  v74 = v95;
  if ( v95 )
  {
    v95 = 0;
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64)))(*v74)[2])(v74);
  }
  v75 = v94;
  if ( v94 )
  {
    v94 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v75 + 16LL))(v75);
  }
  v76 = v93;
  if ( v93 )
  {
    v93 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v76 + 16LL))(v76);
  }
  v77 = v92;
  if ( v92 )
  {
    v92 = 0;
    (*(void (__fastcall **)(struct Windows::Web::Http::Headers::IHttpRequestHeaderCollection *))(*(_QWORD *)v77 + 16LL))(v77);
  }
  v78 = v90;
  if ( v90 )
  {
    v90 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v78 + 16LL))(v78);
  }
  v79 = v91;
  if ( v91 )
  {
    v91 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v79 + 16LL))(v79);
  }
  v80 = v89;
  if ( v89 )
  {
    v89 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v80 + 16LL))(v80);
  }
  v81 = v88;
  if ( v88 )
  {
    v88 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v81 + 16LL))(v81);
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v96);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v97);
  v10 = 0;
LABEL_110:
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v109);
  return v10;
}

```

## disassembly

```asm
0x1800a3cb0  push    rbp
0x1800a3cb2  push    rbx
0x1800a3cb3  push    rsi
0x1800a3cb4  push    rdi
0x1800a3cb5  push    r12
0x1800a3cb7  push    r14
0x1800a3cb9  push    r15
0x1800a3cbb  lea     rbp, [rsp-70h]
0x1800a3cc0  sub     rsp, 170h
0x1800a3cc7  mov     rax, cs:__security_cookie
0x1800a3cce  xor     rax, rsp
0x1800a3cd1  mov     [rbp+0A0h+var_40], rax
0x1800a3cd5  xorps   xmm0, xmm0
0x1800a3cd8  mov     [rsp+1A0h+var_128], r8
0x1800a3cdd  mov     r15, rcx
0x1800a3ce0  mov     r14, r9
0x1800a3ce3  lea     rcx, [rbp+0A0h+var_60]
0x1800a3ce7  mov     r9, rdx
0x1800a3cea  movups  [rbp+0A0h+var_60], xmm0
0x1800a3cee  movups  [rbp+0A0h+var_50], xmm0
0x1800a3cf2  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x1800a3cf7  mov     rdx, r9
0x1800a3cfa  lea     rcx, [rbp+0A0h+var_60]
0x1800a3cfe  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *)
0x1800a3d03  xor     r12d, r12d
0x1800a3d06  test    al, al
0x1800a3d08  jnz     short loc_1800A3D15
0x1800a3d0a  mov     r9d, 9Bh
0x1800a3d10  jmp     loc_1800A3DD9
0x1800a3d15  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800a3d19  lea     rdx, ?c_pRestApiVersionUri@@3QBGB; "v1/"
0x1800a3d20  mov     r8, rbx
0x1800a3d23  inc     r8
0x1800a3d26  cmp     [rdx+r8*2], r12w
0x1800a3d2b  jnz     short loc_1800A3D23
0x1800a3d2d  lea     rcx, [rbp+0A0h+var_60]
0x1800a3d31  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x1800a3d36  test    al, al
0x1800a3d38  jnz     short loc_1800A3D45
0x1800a3d3a  mov     r9d, 9Ch
0x1800a3d40  jmp     loc_1800A3DD9
0x1800a3d45  lea     rdx, ?c_pRestApiUsersUri@@3QBGB; "users/"
0x1800a3d4c  mov     r8, rbx
0x1800a3d4f  inc     r8
0x1800a3d52  cmp     [rdx+r8*2], r12w
0x1800a3d57  jnz     short loc_1800A3D4F
0x1800a3d59  lea     rcx, [rbp+0A0h+var_60]
0x1800a3d5d  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x1800a3d62  test    al, al
0x1800a3d64  jnz     short loc_1800A3D6E
0x1800a3d66  mov     r9d, 9Dh
0x1800a3d6c  jmp     short loc_1800A3DD9
0x1800a3d6e  lea     rdx, ?c_pRestApiMeUri@@3QBGB; "ME/"
0x1800a3d75  inc     rbx
0x1800a3d78  cmp     [rdx+rbx*2], r12w
0x1800a3d7d  jnz     short loc_1800A3D75
0x1800a3d7f  mov     r8, rbx
0x1800a3d82  lea     rcx, [rbp+0A0h+var_60]
0x1800a3d86  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x1800a3d8b  test    al, al
0x1800a3d8d  jnz     short loc_1800A3D97
0x1800a3d8f  mov     r9d, 9Eh
0x1800a3d95  jmp     short loc_1800A3DD9
0x1800a3d97  mov     r8d, 0Ah
0x1800a3d9d  lea     rdx, aProperties; "properties"
0x1800a3da4  lea     rcx, [rbp+0A0h+var_60]
0x1800a3da8  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x1800a3dad  test    al, al
0x1800a3daf  jnz     short loc_1800A3DB9
0x1800a3db1  mov     r9d, 9Fh
0x1800a3db7  jmp     short loc_1800A3DD9
0x1800a3db9  mov     r8d, 11h
0x1800a3dbf  lea     rdx, aNameDogfooduse; "?name=dogfoodUser"
0x1800a3dc6  lea     rcx, [rbp+0A0h+var_60]
0x1800a3dca  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x1800a3dcf  test    al, al
0x1800a3dd1  jnz     short loc_1800A3DEC
0x1800a3dd3  mov     r9d, 0A0h
0x1800a3dd9  mov     ebx, 8007000Eh
0x1800a3dde  xor     edx, edx
0x1800a3de0  mov     ecx, ebx; int
0x1800a3de2  call    Log_HREvent_79
0x1800a3de7  jmp     loc_1800A4782
0x1800a3dec  mov     r9d, 16h; unsigned int
0x1800a3df2  mov     [rbp+0A0h+var_D8], r12
0x1800a3df6  lea     rdx, ?RuntimeClass_Windows_Foundation_Uri@@3QBGB; "Windows.Foundation.Uri"
0x1800a3dfd  mov     [rsp+1A0h+var_158], r12
0x1800a3e02  lea     rcx, [rsp+1A0h+hstringHeader]; hstringHeader
0x1800a3e07  lea     r8d, [r9+1]; unsigned int
0x1800a3e0b  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800a3e10  mov     rcx, [rsp+1A0h+var_158]
0x1800a3e15  lea     r8, [rbp+0A0h+var_D8]
0x1800a3e19  lea     rdx, _GUID_44a9796f_723e_4fdf_a218_033e75b0c084
0x1800a3e20  call    cs:__imp_RoGetActivationFactory
0x1800a3e26  mov     ebx, eax
0x1800a3e28  test    eax, eax
0x1800a3e2a  jns     short loc_1800A3E4C
0x1800a3e2c  mov     edx, 1
0x1800a3e31  mov     r9d, 0A3h
0x1800a3e37  mov     ecx, eax; int
0x1800a3e39  call    Log_HREvent_79
0x1800a3e3e  lea     rcx, [rbp+0A0h+var_D8]
0x1800a3e42  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800a3e47  jmp     loc_1800A4782
0x1800a3e4c  mov     rdx, qword ptr [rbp+0A0h+var_60]
0x1800a3e50  lea     rcx, [rsp+1A0h+hstringHeader]
0x1800a3e55  mov     rdi, [rbp+0A0h+var_D8]
0x1800a3e59  mov     [rbp+0A0h+var_E0], r12
0x1800a3e5d  mov     [rsp+1A0h+var_150], rdx
0x1800a3e62  lea     rdx, [rsp+1A0h+var_150]
0x1800a3e67  mov     rax, [rdi]
0x1800a3e6a  mov     rbx, [rax+30h]
0x1800a3e6e  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1800a3e73  lea     r8, [rbp+0A0h+var_E0]
0x1800a3e77  mov     rcx, rdi
0x1800a3e7a  mov     rdx, [rax+18h]
0x1800a3e7e  mov     rax, rbx
0x1800a3e81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a3e86  mov     ebx, eax
0x1800a3e88  test    eax, eax
0x1800a3e8a  jns     short loc_1800A3EA9
0x1800a3e8c  mov     r9d, 0A6h
0x1800a3e92  mov     edx, 1
0x1800a3e97  mov     ecx, eax; int
0x1800a3e99  call    Log_HREvent_79
0x1800a3e9e  lea     rcx, [rbp+0A0h+var_E0]
0x1800a3ea2  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800a3ea7  jmp     short loc_1800A3E3E
0x1800a3ea9  mov     rdx, [rbp+0A0h+var_E0]; struct Windows::Foundation::IUriRuntimeClass *
0x1800a3ead  call    ?_RemoveAuthCookie@ChatServiceTransaction@@IEAAJPEAUIUriRuntimeClass@Foundation@Windows@@@Z; ChatServiceTransaction::_RemoveAuthCookie(Windows::Foundation::IUriRuntimeClass *)
0x1800a3eb2  mov     ebx, eax
0x1800a3eb4  test    eax, eax
0x1800a3eb6  jns     short loc_1800A3EC0
0x1800a3eb8  mov     r9d, 0A8h
0x1800a3ebe  jmp     short loc_1800A3E92
0x1800a3ec0  mov     r9d, 1Bh; unsigned int
0x1800a3ec6  mov     [rbp+0A0h+var_120], r12
0x1800a3eca  lea     rdx, ?RuntimeClass_Windows_Web_Http_HttpMethod@@3QBGB; "Windows.Web.Http.HttpMethod"
0x1800a3ed1  mov     [rsp+1A0h+var_158], r12
0x1800a3ed6  lea     rcx, [rsp+1A0h+hstringHeader]; hstringHeader
0x1800a3edb  lea     r8d, [r9+1]; unsigned int
0x1800a3edf  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800a3ee4  mov     rcx, [rsp+1A0h+var_158]
0x1800a3ee9  lea     r8, [rbp+0A0h+var_120]
0x1800a3eed  lea     rdx, _GUID_64d171f0_d99a_4153_8dc6_d68cc4cce317
0x1800a3ef4  call    cs:__imp_RoGetActivationFactory
0x1800a3efa  mov     ebx, eax
0x1800a3efc  test    eax, eax
0x1800a3efe  jns     short loc_1800A3F30
0x1800a3f00  mov     edx, 1
0x1800a3f05  mov     r9d, 0ACh
0x1800a3f0b  mov     ecx, eax; int
0x1800a3f0d  call    Log_HREvent_79
0x1800a3f12  mov     rcx, [rbp+0A0h+var_120]
0x1800a3f16  test    rcx, rcx
0x1800a3f19  jz      short loc_1800A3E9E
0x1800a3f1b  mov     [rbp+0A0h+var_120], r12
0x1800a3f1f  mov     rax, [rcx]
0x1800a3f22  mov     rax, [rax+10h]
0x1800a3f26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a3f2b  jmp     loc_1800A3E9E
0x1800a3f30  mov     rcx, [rbp+0A0h+var_120]
0x1800a3f34  lea     rdx, [rbp+0A0h+var_118]
0x1800a3f38  mov     [rbp+0A0h+var_118], r12
0x1800a3f3c  mov     rax, [rcx]
0x1800a3f3f  mov     rax, [rax+60h]
0x1800a3f43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a3f48  mov     ebx, eax
0x1800a3f4a  test    eax, eax
0x1800a3f4c  jns     short loc_1800A3F7B
0x1800a3f4e  mov     edx, 1
0x1800a3f53  mov     r9d, 0AFh
0x1800a3f59  mov     ecx, eax; int
0x1800a3f5b  call    Log_HREvent_79
0x1800a3f60  mov     rcx, [rbp+0A0h+var_118]
0x1800a3f64  test    rcx, rcx
0x1800a3f67  jz      short loc_1800A3F12
0x1800a3f69  mov     [rbp+0A0h+var_118], r12
0x1800a3f6d  mov     rax, [rcx]
0x1800a3f70  mov     rax, [rax+10h]
0x1800a3f74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a3f79  jmp     short loc_1800A3F12
0x1800a3f7b  mov     r9d, 23h ; '#'; unsigned int
0x1800a3f81  mov     [rbp+0A0h+var_108], r12
0x1800a3f85  lea     rdx, ?RuntimeClass_Windows_Web_Http_HttpRequestMessage@@3QBGB; "Windows.Web.Http.HttpRequestMessage"
0x1800a3f8c  mov     [rsp+1A0h+var_158], r12
0x1800a3f91  lea     rcx, [rsp+1A0h+hstringHeader]; hstringHeader
0x1800a3f96  lea     r8d, [r9+1]; unsigned int
0x1800a3f9a  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800a3f9f  mov     rcx, [rsp+1A0h+var_158]
0x1800a3fa4  lea     r8, [rbp+0A0h+var_108]
0x1800a3fa8  lea     rdx, _GUID_5bac994e_3886_412e_aec3_52ec7f25616f
0x1800a3faf  call    cs:__imp_RoGetActivationFactory
0x1800a3fb5  mov     ebx, eax
0x1800a3fb7  test    eax, eax
0x1800a3fb9  jns     short loc_1800A3FEB
0x1800a3fbb  mov     edx, 1
0x1800a3fc0  mov     r9d, 0B4h
0x1800a3fc6  mov     ecx, eax; int
0x1800a3fc8  call    Log_HREvent_79
0x1800a3fcd  mov     rcx, [rbp+0A0h+var_108]
0x1800a3fd1  test    rcx, rcx
0x1800a3fd4  jz      short loc_1800A3F60
0x1800a3fd6  mov     [rbp+0A0h+var_108], r12
0x1800a3fda  mov     rax, [rcx]
0x1800a3fdd  mov     rax, [rax+10h]
0x1800a3fe1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a3fe6  jmp     loc_1800A3F60
0x1800a3feb  mov     rcx, [rbp+0A0h+var_108]
0x1800a3fef  lea     r9, [rbp+0A0h+var_110]
0x1800a3ff3  mov     r8, [rbp+0A0h+var_E0]
0x1800a3ff7  mov     rdx, [rbp+0A0h+var_118]
0x1800a3ffb  mov     [rbp+0A0h+var_110], r12
0x1800a3fff  mov     rax, [rcx]
0x1800a4002  mov     rax, [rax+30h]
0x1800a4006  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a400b  mov     ebx, eax
0x1800a400d  test    eax, eax
0x1800a400f  jns     short loc_1800A403E
0x1800a4011  mov     edx, 1
0x1800a4016  mov     r9d, 0B7h
0x1800a401c  mov     ecx, eax; int
0x1800a401e  call    Log_HREvent_79
0x1800a4023  mov     rcx, [rbp+0A0h+var_110]
0x1800a4027  test    rcx, rcx
0x1800a402a  jz      short loc_1800A3FCD
0x1800a402c  mov     [rbp+0A0h+var_110], r12
0x1800a4030  mov     rax, [rcx]
0x1800a4033  mov     rax, [rax+10h]
0x1800a4037  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a403c  jmp     short loc_1800A3FCD
0x1800a403e  mov     rcx, [rbp+0A0h+var_110]
0x1800a4042  lea     rdx, [rbp+0A0h+var_100]
0x1800a4046  mov     [rbp+0A0h+var_100], r12
0x1800a404a  mov     rax, [rcx]
0x1800a404d  mov     rax, [rax+40h]
0x1800a4051  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a4056  mov     ebx, eax
0x1800a4058  test    eax, eax
0x1800a405a  jns     short loc_1800A4089
0x1800a405c  mov     edx, 1
0x1800a4061  mov     r9d, 0BAh
0x1800a4067  mov     ecx, eax; int
0x1800a4069  call    Log_HREvent_79
0x1800a406e  mov     rcx, [rbp+0A0h+var_100]
0x1800a4072  test    rcx, rcx
0x1800a4075  jz      short loc_1800A4023
0x1800a4077  mov     [rbp+0A0h+var_100], r12
0x1800a407b  mov     rax, [rcx]
0x1800a407e  mov     rax, [rax+10h]
0x1800a4082  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a4087  jmp     short loc_1800A4023
0x1800a4089  mov     r9d, 32h ; '2'; unsigned int
0x1800a408f  mov     [rbp+0A0h+var_F8], r12
0x1800a4093  lea     rdx, ?RuntimeClass_Windows_Web_Http_Headers_HttpCookiePairHeaderValue@@3QBGB; "Windows.Web.Http.Headers.HttpCookiePair"...
0x1800a409a  mov     [rsp+1A0h+var_158], r12
0x1800a409f  lea     rcx, [rsp+1A0h+hstringHeader]; hstringHeader
0x1800a40a4  lea     r8d, [r9+1]; unsigned int
0x1800a40a8  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800a40ad  mov     rcx, [rsp+1A0h+var_158]
0x1800a40b2  lea     r8, [rbp+0A0h+var_F8]
0x1800a40b6  lea     rdx, _GUID_635e326f_146f_4f56_aa21_2cb7d6d58b1e
0x1800a40bd  call    cs:__imp_RoGetActivationFactory
0x1800a40c3  mov     ebx, eax
0x1800a40c5  test    eax, eax
0x1800a40c7  jns     short loc_1800A40F9
0x1800a40c9  mov     edx, 1
0x1800a40ce  mov     r9d, 0C0h
0x1800a40d4  mov     ecx, eax; int
0x1800a40d6  call    Log_HREvent_79
0x1800a40db  mov     rcx, [rbp+0A0h+var_F8]
0x1800a40df  test    rcx, rcx
0x1800a40e2  jz      short loc_1800A406E
0x1800a40e4  mov     [rbp+0A0h+var_F8], r12
0x1800a40e8  mov     rax, [rcx]
0x1800a40eb  mov     rax, [rax+10h]
0x1800a40ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a40f4  jmp     loc_1800A406E
0x1800a40f9  mov     rsi, [rbp+0A0h+var_F8]
0x1800a40fd  lea     rdx, [rsp+1A0h+var_128]
0x1800a4102  mov     [rbp+0A0h+var_F0], r12
0x1800a4106  lea     rcx, [rsp+1A0h+hstringHeader]
0x1800a410b  mov     rax, [rsi]
0x1800a410e  mov     rdi, [rax+38h]
0x1800a4112  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1800a4117  lea     rdx, off_1800FD800; "ssl-compact"
0x1800a411e  lea     rcx, [rsp+1A0h+var_148]
0x1800a4123  mov     rbx, [rax+18h]
0x1800a4127  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1800a412c  lea     r9, [rbp+0A0h+var_F0]
0x1800a4130  mov     r8, rbx
0x1800a4133  mov     rcx, rsi
0x1800a4136  mov     rdx, [rax+18h]
0x1800a413a  mov     rax, rdi
0x1800a413d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a4142  mov     ebx, eax
0x1800a4144  test    eax, eax
0x1800a4146  jns     short loc_1800A417C
0x1800a4148  mov     edx, 1
0x1800a414d  mov     r9d, 0C4h
  ... truncated ...
```
