# ChatServiceStartMigrationTransaction::_PackStartMigrationRequest(ushort const *,ushort const *,ChatServiceRegistrationToken *,unsigned __int64)

- ea: `0x1800a53e0`
- end: `0x1800a5f4c`
- name: `?_PackStartMigrationRequest@ChatServiceStartMigrationTransaction@@AEAAJPEBG0PEAVChatServiceRegistrationToken@@_K@Z`
- size: `2924`
- prototype: `__int64 __fastcall(ChatServiceStartMigrationTransaction *__hidden this, const unsigned __int16 *, const unsigned __int16 *, struct ChatServiceRegistrationToken *, unsigned __int64)`
- caller_count: `0`
- callee_count: `23`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180005c50`
- `0x180008870`
- `0x18000a754`
- `0x18000b7d4`
- `0x1800176b4`
- `0x180030bd0`
- `0x18004b0e8`
- `0x18006b108`
- `0x180084738`
- `0x1800847b8`
- `0x180084864`
- `0x1800848b4`
- `0x18009dba0`
- `0x18009dc9c`
- `0x18009f658`
- `0x1800a3004`
- `0x1800a3360`
- `0x1800a33f8`
- `0x1800a5208`
- `0x1800a53e0`
- `0x1800b3c54`
- `0x1800c6940`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800a554f`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800a5621`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800a56d8`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800a57e0`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800a5b6f`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800a5d06`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800a554f`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800a5621`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800a56d8`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800a57e0`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800a5b6f`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800a5d06`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a5c91`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a5cc6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a5df3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a5c91`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a5cc6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a5df3`

## string_xrefs

- `0x1800a5525`: `Windows.Foundation.Uri`
- `0x1800a5b45`: `Windows.Data.Json.JsonValue`
- `0x1800a5abd`: `Windows.Data.Json.JsonObject`
- `0x1800a5958`: `registrationToken`

## pseudocode

```c
__int64 __fastcall ChatServiceStartMigrationTransaction::_PackStartMigrationRequest(
        ChatServiceStartMigrationTransaction *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        struct ChatServiceRegistrationToken *a4)
{
  __int64 v6; // r10
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
  __int64 v27; // rcx
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
  int v42; // eax
  char v43; // r8
  __int64 v44; // r14
  const WCHAR *v45; // rbx
  __int64 (__fastcall *v46)(__int64, PVOID, PVOID); // rsi
  HSTRING_HEADER *v47; // rax
  PVOID v48; // rdi
  char v49; // r8
  HSTRING_HEADER *v50; // rax
  __int64 v51; // rsi
  __int64 (__fastcall *v52)(__int64, __int64, PVOID); // rdi
  char v53; // r8
  PVOID v54; // rbx
  int v55; // eax
  int v56; // eax
  int v57; // eax
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
  __int64 v77; // rcx
  __int64 v78; // rcx
  __int64 v79; // rcx
  __int64 v80; // rcx
  __int64 v81; // rcx
  const WCHAR *v83; // [rsp+30h] [rbp-D0h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v85; // [rsp+50h] [rbp-B0h]
  HSTRING_HEADER v86; // [rsp+58h] [rbp-A8h] BYREF
  const WCHAR *ClientInfoValue; // [rsp+78h] [rbp-88h] BYREF
  __int64 v88; // [rsp+80h] [rbp-80h] BYREF
  __int64 v89; // [rsp+88h] [rbp-78h] BYREF
  __int64 v90; // [rsp+90h] [rbp-70h] BYREF
  __int64 v91; // [rsp+98h] [rbp-68h] BYREF
  __int64 v92; // [rsp+A0h] [rbp-60h] BYREF
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
  __int64 v109; // [rsp+140h] [rbp+40h]
  _OWORD v110[2]; // [rsp+148h] [rbp+48h] BYREF

  ClientInfoValue = a3;
  memset(v110, 0, sizeof(v110));
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(v110);
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                           v110,
                           v6) )
    goto LABEL_12;
  v7 = -1;
  v8 = -1;
  do
    ++v8;
  while ( c_pRestApiVersionUri[v8] );
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                           v110,
                           L"v1/",
                           v8) )
    goto LABEL_12;
  v9 = -1;
  do
    ++v9;
  while ( c_pRestApiUsersUri[v9] );
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                           v110,
                           L"users/",
                           v9) )
    goto LABEL_12;
  do
    ++v7;
  while ( c_pRestApiMeUri[v7] );
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                           v110,
                           L"ME/",
                           v7)
    || !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                           v110,
                           L"properties",
                           10)
    || !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                           v110,
                           L"?name=smsSyncStart",
                           18) )
  {
LABEL_12:
    v10 = -2147024882;
    Log_HREvent_80(-2147024882);
    goto LABEL_112;
  }
  v97 = 0;
  v85 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"Windows.Foundation.Uri", 0x17u, 0x16u);
  ActivationFactory = RoGetActivationFactory(v85, &GUID_44a9796f_723e_4fdf_a218_033e75b0c084, &v97);
  v10 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    Log_HREvent_80(ActivationFactory);
LABEL_15:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v97);
    goto LABEL_112;
  }
  v13 = v97;
  v96 = 0;
  v83 = *(const WCHAR **)&v110[0];
  v14 = *(__int64 (__fastcall **)(__int64, PVOID, struct Windows::Foundation::IUriRuntimeClass **))(*(_QWORD *)v97 + 48LL);
  v15 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v83, v12);
  v16 = v14(v13, v15[1].Reserved.Reserved1, &v96);
  v10 = v16;
  if ( v16 < 0 || (v16 = ChatServiceTransaction::_RemoveAuthCookie(v17, v96), v10 = v16, v16 < 0) )
  {
    Log_HREvent_80(v16);
LABEL_18:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v96);
    goto LABEL_15;
  }
  v88 = 0;
  v85 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Web.Http.HttpMethod",
    0x1Cu,
    0x1Bu);
  v18 = RoGetActivationFactory(v85, &GUID_64d171f0_d99a_4153_8dc6_d68cc4cce317, &v88);
  v10 = v18;
  if ( v18 < 0 )
  {
    Log_HREvent_80(v18);
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
    Log_HREvent_80(v20);
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
  v85 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Web.Http.HttpRequestMessage",
    0x24u,
    0x23u);
  v22 = RoGetActivationFactory(v85, &GUID_5bac994e_3886_412e_aec3_52ec7f25616f, &v91);
  v10 = v22;
  if ( v22 < 0 )
  {
    Log_HREvent_80(v22);
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
    Log_HREvent_80(v24);
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
  v26 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v90 + 64LL))(v90, &v92);
  v10 = v26;
  if ( v26 < 0 )
  {
    Log_HREvent_80(v26);
LABEL_38:
    v27 = v92;
    if ( v92 )
    {
      v92 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
    }
    goto LABEL_34;
  }
  v93 = 0;
  v85 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Web.Http.Headers.HttpCookiePairHeaderValue",
    0x33u,
    0x32u);
  v28 = RoGetActivationFactory(v85, &GUID_635e326f_146f_4f56_aa21_2cb7d6d58b1e, &v93);
  v10 = v28;
  if ( v28 < 0 )
  {
    Log_HREvent_80(v28);
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
  v35 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v86, (const WCHAR **)off_1800FD810, v34);
  v36 = v32(v31, v35[1].Reserved.Reserved1, Reserved1, &v94);
  v10 = v36;
  if ( v36 < 0 )
  {
    Log_HREvent_80(v36);
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
  v38 = (*(__int64 (__fastcall **)(__int64, __int64 (__fastcall ****)(_QWORD, GUID *, __int64)))(*(_QWORD *)v92 + 104LL))(
          v92,
          &v95);
  v10 = v38;
  if ( v38 < 0 )
  {
    Log_HREvent_80(v38);
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
    Log_HREvent_80(v40);
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
  v109 = 0;
  utl::unordered_set<enum __MIDL___MIDL_itf_messagingdatamodel_0000_0000_0007,utl::hash<enum __MIDL___MIDL_itf_messagingdatamodel_0000_0000_0007>,utl::equal_to<enum __MIDL___MIDL_itf_messagingdatamodel_0000_0000_0007>,utl::allocator<enum __MIDL___MIDL_itf_messagingdatamodel_0000_0000_0007>>::unordered_set<enum __MIDL___MIDL_itf_messagingdatamodel_0000_0000_0007,utl::hash<enum __MIDL___MIDL_itf_messagingdatamodel_0000_0000_0007>,utl::equal_to<enum __MIDL___MIDL_itf_messagingdatamodel_0000_0000_0007>,utl::allocator<enum __MIDL___MIDL_itf_messagingdatamodel_0000_0000_0007>>(v108);
  ClientInfoValue = (const WCHAR *)*((_QWORD *)a4 + 3);
  v83 = L"registrationToken";
  if ( !*(_QWORD *)utl::_HashTable<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>,utl::pair<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>> const,utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>,utl::hash<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>,utl::equal_to<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>,utl::allocator<utl::pair<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>> const,utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>>,0>::emplace<unsigned short const *,unsigned short const *,0>(
                     v108,
                     &hstringHeader,
                     &v83,
                     &ClientInfoValue) )
  {
    v10 = -2147024882;
    Log_HREvent_80(-2147024882);
LABEL_58:
    utl::_HashTable<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>,utl::pair<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>> const,utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>,utl::hash<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>,utl::equal_to<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>,utl::allocator<utl::pair<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>> const,utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>>,0>::_Uninit(v108);
    goto LABEL_54;
  }
  v83 = 0;
  v42 = ChatServiceHttpHeader::CreateInstance(v41, v108, &v83);
  v10 = v42;
  if ( v42 < 0 )
    goto LABEL_60;
  v44 = v92;
  v45 = v83;
  v46 = *(__int64 (__fastcall **)(__int64, PVOID, PVOID))(*(_QWORD *)v92 + 264LL);
  ClientInfoValue = (const WCHAR *)*((_QWORD *)v83 + 7);
  v47 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v86, &ClientInfoValue, v43);
  ClientInfoValue = (const WCHAR *)*((_QWORD *)v45 + 3);
  v48 = v47[1].Reserved.Reserved1;
  v50 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &ClientInfoValue, v49);
  v42 = v46(v44, v50[1].Reserved.Reserved1, v48);
  v10 = v42;
  if ( v42 < 0 )
    goto LABEL_60;
  v51 = v92;
  v52 = *(__int64 (__fastcall **)(__int64, __int64, PVOID))(*(_QWORD *)v92 + 264LL);
  ClientInfoValue = ChatServiceTransaction::get_ClientInfoValue();
  v54 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v86, &ClientInfoValue, v53)[1].Reserved.Reserved1;
  v85 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"ClientInfo", 0xBu, 0xAu);
  v42 = v52(v51, v85, v54);
  v10 = v42;
  if ( v42 < 0 )
  {
LABEL_60:
    Log_HREvent_80(v42);
LABEL_61:
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v83);
    goto LABEL_58;
  }
  v100 = 0;
  v85 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Data.Json.JsonObject",
    0x1Du,
    0x1Cu);
  v55 = Windows::Foundation::ActivateInstance<Windows::Data::Json::IJsonObject>(v85, &v100);
  v10 = v55;
  if ( v55 < 0 )
  {
    Log_HREvent_80(v55);
LABEL_66:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v100);
    goto LABEL_61;
  }
  v102 = 0;
  v56 = Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>::As<Windows::Foundation::Collections::IMap<HSTRING__ *,Windows::Data::Json::IJsonValue *>>(
          &v100,
          (__int64)&v102);
  v10 = v56;
  if ( v56 < 0 )
  {
    Log_HREvent_80(v56);
LABEL_69:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v102);
    goto LABEL_66;
  }
  v103 = 0;
  v85 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Data.Json.JsonValue",
    0x1Cu,
    0x1Bu);
  v57 = RoGetActivationFactory(v85, &GUID_5f6b544a_2f53_48e1_91a3_f78b50a6345c, &v103);
  v10 = v57;
  if ( v57 < 0 )
  {
    Log_HREvent_80(v57);
LABEL_72:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v103);
    goto LABEL_69;
  }
  v105 = 0;
  v58 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v103 + 72LL))(v103, v103, &v105);
  v10 = v58;
  if ( v58 < 0
    || (v60 = v102,
        v61 = v105,
        v99[0] = 0,
        v62 = *(__int64 (__fastcall **)(__int64, PVOID, __int64, _BYTE *))(*(_QWORD *)v102 + 80LL),
        v63 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v86, (const WCHAR **)off_1800FD808, v59),
        v58 = v62(v60, v63[1].Reserved.Reserved1, v61, v99),
        v10 = v58,
        v58 < 0) )
  {
    Log_HREvent_80(v58);
LABEL_75:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v105);
    goto LABEL_72;
  }
  v107 = 0;
  v64 = Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>::As<Windows::Data::Json::IJsonValue>(
          &v100,
          (__int64)&v107);
  v10 = v64;
  if ( v64 < 0 )
  {
    Log_HREvent_80(v64);
LABEL_79:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v107);
    goto LABEL_75;
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
    Log_HREvent_80(v67);
LABEL_82:
    WindowsDeleteString(string);
    string = 0;
    goto LABEL_79;
  }
  v104 = 0;
  v85 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Web.Http.HttpStringContent",
    0x23u,
    0x22u);
  v68 = RoGetActivationFactory(v85, &GUID_46649d5b_2e93_48eb_8e61_19677878e57f, &v104);
  v10 = v68;
  if ( v68 < 0 )
  {
    Log_HREvent_80(v68);
LABEL_85:
    v69 = v104;
    if ( v104 )
    {
      v104 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v69 + 16LL))(v69);
    }
    goto LABEL_82;
  }
  v106 = 0;
  v70 = (*(__int64 (__fastcall **)(__int64, HSTRING, __int64 *))(*(_QWORD *)v104 + 48LL))(v104, string, &v106);
  v10 = v70;
  if ( v70 < 0
    || (v70 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v90 + 56LL))(v90, v106), v10 = v70, v70 < 0) )
  {
    Log_HREvent_80(v70);
    v71 = v106;
    if ( v106 )
    {
      v106 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v71 + 16LL))(v71);
    }
    goto LABEL_85;
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
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v83);
  utl::_HashTable<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>,utl::pair<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>> const,utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>,utl::hash<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>,utl::equal_to<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>,utl::allocator<utl::pair<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>> const,utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>>,0>::_Uninit(v108);
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
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v77 + 16LL))(v77);
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
LABEL_112:
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v110);
  return v10;
}

```

## disassembly

```asm
0x1800a53e0  push    rbp
0x1800a53e2  push    rbx
0x1800a53e3  push    rsi
0x1800a53e4  push    rdi
0x1800a53e5  push    r12
0x1800a53e7  push    r14
0x1800a53e9  push    r15
0x1800a53eb  lea     rbp, [rsp-70h]
0x1800a53f0  sub     rsp, 170h
0x1800a53f7  mov     rax, cs:__security_cookie
0x1800a53fe  xor     rax, rsp
0x1800a5401  mov     [rbp+0A0h+var_38], rax
0x1800a5405  xorps   xmm0, xmm0
0x1800a5408  mov     [rsp+1A0h+var_128], r8
0x1800a540d  mov     r15, rcx
0x1800a5410  mov     r14, r9
0x1800a5413  lea     rcx, [rbp+0A0h+var_58]
0x1800a5417  mov     r10, rdx
0x1800a541a  movups  [rbp+0A0h+var_58], xmm0
0x1800a541e  movups  [rbp+0A0h+var_48], xmm0
0x1800a5422  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x1800a5427  mov     rdx, r10
0x1800a542a  lea     rcx, [rbp+0A0h+var_58]
0x1800a542e  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *)
0x1800a5433  xor     r12d, r12d
0x1800a5436  test    al, al
0x1800a5438  jnz     short loc_1800A5444
0x1800a543a  lea     r9d, [r12+36h]
0x1800a543f  jmp     loc_1800A5508
0x1800a5444  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800a5448  lea     rdx, ?c_pRestApiVersionUri@@3QBGB; "v1/"
0x1800a544f  mov     r8, rbx
0x1800a5452  inc     r8
0x1800a5455  cmp     [rdx+r8*2], r12w
0x1800a545a  jnz     short loc_1800A5452
0x1800a545c  lea     rcx, [rbp+0A0h+var_58]
0x1800a5460  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x1800a5465  test    al, al
0x1800a5467  jnz     short loc_1800A5474
0x1800a5469  mov     r9d, 37h ; '7'
0x1800a546f  jmp     loc_1800A5508
0x1800a5474  lea     rdx, ?c_pRestApiUsersUri@@3QBGB; "users/"
0x1800a547b  mov     r8, rbx
0x1800a547e  inc     r8
0x1800a5481  cmp     [rdx+r8*2], r12w
0x1800a5486  jnz     short loc_1800A547E
0x1800a5488  lea     rcx, [rbp+0A0h+var_58]
0x1800a548c  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x1800a5491  test    al, al
0x1800a5493  jnz     short loc_1800A549D
0x1800a5495  mov     r9d, 38h ; '8'
0x1800a549b  jmp     short loc_1800A5508
0x1800a549d  lea     rdx, ?c_pRestApiMeUri@@3QBGB; "ME/"
0x1800a54a4  inc     rbx
0x1800a54a7  cmp     [rdx+rbx*2], r12w
0x1800a54ac  jnz     short loc_1800A54A4
0x1800a54ae  mov     r8, rbx
0x1800a54b1  lea     rcx, [rbp+0A0h+var_58]
0x1800a54b5  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x1800a54ba  test    al, al
0x1800a54bc  jnz     short loc_1800A54C6
0x1800a54be  mov     r9d, 39h ; '9'
0x1800a54c4  jmp     short loc_1800A5508
0x1800a54c6  mov     r8d, 0Ah
0x1800a54cc  lea     rdx, aProperties; "properties"
0x1800a54d3  lea     rcx, [rbp+0A0h+var_58]
0x1800a54d7  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x1800a54dc  test    al, al
0x1800a54de  jnz     short loc_1800A54E8
0x1800a54e0  mov     r9d, 3Ah ; ':'
0x1800a54e6  jmp     short loc_1800A5508
0x1800a54e8  mov     r8d, 12h
0x1800a54ee  lea     rdx, aNameSmssyncsta; "?name=smsSyncStart"
0x1800a54f5  lea     rcx, [rbp+0A0h+var_58]
0x1800a54f9  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x1800a54fe  test    al, al
0x1800a5500  jnz     short loc_1800A551B
0x1800a5502  mov     r9d, 3Bh ; ';'
0x1800a5508  mov     ebx, 8007000Eh
0x1800a550d  xor     edx, edx
0x1800a550f  mov     ecx, ebx; int
0x1800a5511  call    Log_HREvent_80
0x1800a5516  jmp     loc_1800A5F23
0x1800a551b  mov     r9d, 16h; unsigned int
0x1800a5521  mov     [rbp+0A0h+var_D8], r12
0x1800a5525  lea     rdx, ?RuntimeClass_Windows_Foundation_Uri@@3QBGB; "Windows.Foundation.Uri"
0x1800a552c  mov     [rsp+1A0h+var_150], r12
0x1800a5531  lea     rcx, [rsp+1A0h+hstringHeader]; hstringHeader
0x1800a5536  lea     r8d, [r9+1]; unsigned int
0x1800a553a  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800a553f  mov     rcx, [rsp+1A0h+var_150]
0x1800a5544  lea     r8, [rbp+0A0h+var_D8]
0x1800a5548  lea     rdx, _GUID_44a9796f_723e_4fdf_a218_033e75b0c084
0x1800a554f  call    cs:__imp_RoGetActivationFactory
0x1800a5555  mov     ebx, eax
0x1800a5557  test    eax, eax
0x1800a5559  jns     short loc_1800A5579
0x1800a555b  mov     edx, 1
0x1800a5560  mov     ecx, eax; int
0x1800a5562  lea     r9d, [rdx+3Dh]
0x1800a5566  call    Log_HREvent_80
0x1800a556b  lea     rcx, [rbp+0A0h+var_D8]
0x1800a556f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800a5574  jmp     loc_1800A5F23
0x1800a5579  mov     rdx, qword ptr [rbp+0A0h+var_58]
0x1800a557d  lea     rcx, [rsp+1A0h+hstringHeader]
0x1800a5582  mov     rdi, [rbp+0A0h+var_D8]
0x1800a5586  mov     [rbp+0A0h+var_E0], r12
0x1800a558a  mov     [rsp+1A0h+var_170], rdx
0x1800a558f  lea     rdx, [rsp+1A0h+var_170]
0x1800a5594  mov     rax, [rdi]
0x1800a5597  mov     rbx, [rax+30h]
0x1800a559b  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1800a55a0  lea     r8, [rbp+0A0h+var_E0]
0x1800a55a4  mov     rcx, rdi
0x1800a55a7  mov     rdx, [rax+18h]
0x1800a55ab  mov     rax, rbx
0x1800a55ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a55b3  mov     ebx, eax
0x1800a55b5  test    eax, eax
0x1800a55b7  jns     short loc_1800A55D6
0x1800a55b9  mov     r9d, 41h ; 'A'
0x1800a55bf  mov     edx, 1
0x1800a55c4  mov     ecx, eax; int
0x1800a55c6  call    Log_HREvent_80
0x1800a55cb  lea     rcx, [rbp+0A0h+var_E0]
0x1800a55cf  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800a55d4  jmp     short loc_1800A556B
0x1800a55d6  mov     rdx, [rbp+0A0h+var_E0]; struct Windows::Foundation::IUriRuntimeClass *
0x1800a55da  call    ?_RemoveAuthCookie@ChatServiceTransaction@@IEAAJPEAUIUriRuntimeClass@Foundation@Windows@@@Z; ChatServiceTransaction::_RemoveAuthCookie(Windows::Foundation::IUriRuntimeClass *)
0x1800a55df  mov     ebx, eax
0x1800a55e1  test    eax, eax
0x1800a55e3  jns     short loc_1800A55ED
0x1800a55e5  mov     r9d, 43h ; 'C'
0x1800a55eb  jmp     short loc_1800A55BF
0x1800a55ed  mov     r9d, 1Bh; unsigned int
0x1800a55f3  mov     [rbp+0A0h+var_120], r12
0x1800a55f7  lea     rdx, ?RuntimeClass_Windows_Web_Http_HttpMethod@@3QBGB; "Windows.Web.Http.HttpMethod"
0x1800a55fe  mov     [rsp+1A0h+var_150], r12
0x1800a5603  lea     rcx, [rsp+1A0h+hstringHeader]; hstringHeader
0x1800a5608  lea     r8d, [r9+1]; unsigned int
0x1800a560c  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800a5611  mov     rcx, [rsp+1A0h+var_150]
0x1800a5616  lea     r8, [rbp+0A0h+var_120]
0x1800a561a  lea     rdx, _GUID_64d171f0_d99a_4153_8dc6_d68cc4cce317
0x1800a5621  call    cs:__imp_RoGetActivationFactory
0x1800a5627  mov     ebx, eax
0x1800a5629  test    eax, eax
0x1800a562b  jns     short loc_1800A565B
0x1800a562d  mov     edx, 1
0x1800a5632  mov     ecx, eax; int
0x1800a5634  lea     r9d, [rdx+47h]
0x1800a5638  call    Log_HREvent_80
0x1800a563d  mov     rcx, [rbp+0A0h+var_120]
0x1800a5641  test    rcx, rcx
0x1800a5644  jz      short loc_1800A55CB
0x1800a5646  mov     [rbp+0A0h+var_120], r12
0x1800a564a  mov     rax, [rcx]
0x1800a564d  mov     rax, [rax+10h]
0x1800a5651  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a5656  jmp     loc_1800A55CB
0x1800a565b  mov     rcx, [rbp+0A0h+var_120]
0x1800a565f  lea     rdx, [rbp+0A0h+var_118]
0x1800a5663  mov     [rbp+0A0h+var_118], r12
0x1800a5667  mov     rax, [rcx]
0x1800a566a  mov     rax, [rax+60h]
0x1800a566e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a5673  mov     ebx, eax
0x1800a5675  test    eax, eax
0x1800a5677  jns     short loc_1800A56A4
0x1800a5679  mov     edx, 1
0x1800a567e  mov     ecx, eax; int
0x1800a5680  lea     r9d, [rdx+4Ah]
0x1800a5684  call    Log_HREvent_80
0x1800a5689  mov     rcx, [rbp+0A0h+var_118]
0x1800a568d  test    rcx, rcx
0x1800a5690  jz      short loc_1800A563D
0x1800a5692  mov     [rbp+0A0h+var_118], r12
0x1800a5696  mov     rax, [rcx]
0x1800a5699  mov     rax, [rax+10h]
0x1800a569d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a56a2  jmp     short loc_1800A563D
0x1800a56a4  mov     r9d, 23h ; '#'; unsigned int
0x1800a56aa  mov     [rbp+0A0h+var_108], r12
0x1800a56ae  lea     rdx, ?RuntimeClass_Windows_Web_Http_HttpRequestMessage@@3QBGB; "Windows.Web.Http.HttpRequestMessage"
0x1800a56b5  mov     [rsp+1A0h+var_150], r12
0x1800a56ba  lea     rcx, [rsp+1A0h+hstringHeader]; hstringHeader
0x1800a56bf  lea     r8d, [r9+1]; unsigned int
0x1800a56c3  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800a56c8  mov     rcx, [rsp+1A0h+var_150]
0x1800a56cd  lea     r8, [rbp+0A0h+var_108]
0x1800a56d1  lea     rdx, _GUID_5bac994e_3886_412e_aec3_52ec7f25616f
0x1800a56d8  call    cs:__imp_RoGetActivationFactory
0x1800a56de  mov     ebx, eax
0x1800a56e0  test    eax, eax
0x1800a56e2  jns     short loc_1800A5712
0x1800a56e4  mov     edx, 1
0x1800a56e9  mov     ecx, eax; int
0x1800a56eb  lea     r9d, [rdx+4Fh]
0x1800a56ef  call    Log_HREvent_80
0x1800a56f4  mov     rcx, [rbp+0A0h+var_108]
0x1800a56f8  test    rcx, rcx
0x1800a56fb  jz      short loc_1800A5689
0x1800a56fd  mov     [rbp+0A0h+var_108], r12
0x1800a5701  mov     rax, [rcx]
0x1800a5704  mov     rax, [rax+10h]
0x1800a5708  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a570d  jmp     loc_1800A5689
0x1800a5712  mov     rcx, [rbp+0A0h+var_108]
0x1800a5716  lea     r9, [rbp+0A0h+var_110]
0x1800a571a  mov     r8, [rbp+0A0h+var_E0]
0x1800a571e  mov     rdx, [rbp+0A0h+var_118]
0x1800a5722  mov     [rbp+0A0h+var_110], r12
0x1800a5726  mov     rax, [rcx]
0x1800a5729  mov     rax, [rax+30h]
0x1800a572d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a5732  mov     ebx, eax
0x1800a5734  test    eax, eax
0x1800a5736  jns     short loc_1800A5763
0x1800a5738  mov     edx, 1
0x1800a573d  mov     ecx, eax; int
0x1800a573f  lea     r9d, [rdx+52h]
0x1800a5743  call    Log_HREvent_80
0x1800a5748  mov     rcx, [rbp+0A0h+var_110]
0x1800a574c  test    rcx, rcx
0x1800a574f  jz      short loc_1800A56F4
0x1800a5751  mov     [rbp+0A0h+var_110], r12
0x1800a5755  mov     rax, [rcx]
0x1800a5758  mov     rax, [rax+10h]
0x1800a575c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a5761  jmp     short loc_1800A56F4
0x1800a5763  mov     rcx, [rbp+0A0h+var_110]
0x1800a5767  lea     rdx, [rbp+0A0h+var_100]
0x1800a576b  mov     [rbp+0A0h+var_100], r12
0x1800a576f  mov     rax, [rcx]
0x1800a5772  mov     rax, [rax+40h]
0x1800a5776  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a577b  mov     ebx, eax
0x1800a577d  test    eax, eax
0x1800a577f  jns     short loc_1800A57AC
0x1800a5781  mov     edx, 1
0x1800a5786  mov     ecx, eax; int
0x1800a5788  lea     r9d, [rdx+55h]
0x1800a578c  call    Log_HREvent_80
0x1800a5791  mov     rcx, [rbp+0A0h+var_100]
0x1800a5795  test    rcx, rcx
0x1800a5798  jz      short loc_1800A5748
0x1800a579a  mov     [rbp+0A0h+var_100], r12
0x1800a579e  mov     rax, [rcx]
0x1800a57a1  mov     rax, [rax+10h]
0x1800a57a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a57aa  jmp     short loc_1800A5748
0x1800a57ac  mov     r9d, 32h ; '2'; unsigned int
0x1800a57b2  mov     [rbp+0A0h+var_F8], r12
0x1800a57b6  lea     rdx, ?RuntimeClass_Windows_Web_Http_Headers_HttpCookiePairHeaderValue@@3QBGB; "Windows.Web.Http.Headers.HttpCookiePair"...
0x1800a57bd  mov     [rsp+1A0h+var_150], r12
0x1800a57c2  lea     rcx, [rsp+1A0h+hstringHeader]; hstringHeader
0x1800a57c7  lea     r8d, [r9+1]; unsigned int
0x1800a57cb  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800a57d0  mov     rcx, [rsp+1A0h+var_150]
0x1800a57d5  lea     r8, [rbp+0A0h+var_F8]
0x1800a57d9  lea     rdx, _GUID_635e326f_146f_4f56_aa21_2cb7d6d58b1e
0x1800a57e0  call    cs:__imp_RoGetActivationFactory
0x1800a57e6  mov     ebx, eax
0x1800a57e8  test    eax, eax
0x1800a57ea  jns     short loc_1800A581A
0x1800a57ec  mov     edx, 1
0x1800a57f1  mov     ecx, eax; int
0x1800a57f3  lea     r9d, [rdx+5Bh]
0x1800a57f7  call    Log_HREvent_80
0x1800a57fc  mov     rcx, [rbp+0A0h+var_F8]
0x1800a5800  test    rcx, rcx
0x1800a5803  jz      short loc_1800A5791
0x1800a5805  mov     [rbp+0A0h+var_F8], r12
0x1800a5809  mov     rax, [rcx]
0x1800a580c  mov     rax, [rax+10h]
0x1800a5810  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a5815  jmp     loc_1800A5791
0x1800a581a  mov     rsi, [rbp+0A0h+var_F8]
0x1800a581e  lea     rdx, [rsp+1A0h+var_128]
0x1800a5823  mov     [rbp+0A0h+var_F0], r12
0x1800a5827  lea     rcx, [rsp+1A0h+hstringHeader]
0x1800a582c  mov     rax, [rsi]
0x1800a582f  mov     rdi, [rax+38h]
0x1800a5833  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1800a5838  lea     rdx, off_1800FD810; "ssl-compact"
0x1800a583f  lea     rcx, [rsp+1A0h+var_148]
0x1800a5844  mov     rbx, [rax+18h]
0x1800a5848  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1800a584d  lea     r9, [rbp+0A0h+var_F0]
0x1800a5851  mov     r8, rbx
0x1800a5854  mov     rcx, rsi
0x1800a5857  mov     rdx, [rax+18h]
0x1800a585b  mov     rax, rdi
0x1800a585e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a5863  mov     ebx, eax
0x1800a5865  test    eax, eax
0x1800a5867  jns     short loc_1800A589B
0x1800a5869  mov     edx, 1
0x1800a586e  mov     ecx, eax; int
  ... truncated ...
```
