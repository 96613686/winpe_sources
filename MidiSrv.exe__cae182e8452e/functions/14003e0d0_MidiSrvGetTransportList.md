# MidiSrvGetTransportList

- ea: `0x14003e0d0`
- end: `0x14003e96f`
- name: `MidiSrvGetTransportList`
- size: `2207`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `18`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x1400018e4`
- `0x1400054c0`
- `0x140007c20`
- `0x14000984c`
- `0x14000a6b4`
- `0x14000c598`
- `0x14000cc2c`
- `0x140022e58`
- `0x140023004`
- `0x140023398`
- `0x1400250ac`
- `0x1400261b4`
- `0x14003a534`
- `0x14003be6c`
- `0x14003ce84`
- `0x14003cfe0`
- `0x14003e0d0`
- `0x14005a010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x14003e81b`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x14003e822`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x14003e829`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x14003e830`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x14003e837`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x14003e83e`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x14003e845`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x14003e81b`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x14003e822`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x14003e829`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x14003e830`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x14003e837`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x14003e83e`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x14003e845`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14003e92e`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14003e92e`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x14003e17b`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x14003e17b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14003e798`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14003e7ab`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14003e7be`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14003e7d1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14003e7e4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14003e7f7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14003e798`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14003e7ab`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14003e7be`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14003e7d1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14003e7e4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14003e7f7`

## string_xrefs

- `0x14003e95a`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x14003e106`: `avcore\midi2\service\exe\midisrvrpc.cpp`
- `0x14003e879`: `avcore\midi2\service\exe\midisrvrpc.cpp`
- `0x14003e68f`: `isClientConfigurable`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall MidiSrvGetTransportList(__int64 a1, __int64 a2)
{
  _DWORD *v4; // rcx
  int v5; // r8d
  int v6; // r9d
  HRESULT v7; // eax
  CMidiSrv *v8; // rcx
  __int64 v9; // rax
  volatile signed __int32 *v10; // rsi
  __int128 *v11; // rbx
  __int128 *v12; // r15
  __int64 v13; // rdx
  __int64 v14; // rcx
  __int64 StringValue; // rax
  __int64 v16; // rdx
  __int64 v17; // rcx
  __int64 v18; // rax
  __int64 v19; // rdx
  __int64 v20; // rcx
  __int64 v21; // rax
  __int64 v22; // rdx
  __int64 v23; // rcx
  __int64 v24; // rax
  __int64 v25; // rdx
  __int64 v26; // rcx
  __int64 v27; // rax
  __int64 v28; // rdx
  __int64 v29; // rcx
  __int64 v30; // rax
  __int64 BooleanValue; // rax
  __int64 v32; // rax
  __int64 v33; // rax
  __int64 v34; // rax
  __int64 v35; // rdi
  const wchar_t **v36; // rax
  const wchar_t *v37; // rdx
  __int64 v38; // rcx
  void *v39; // rcx
  void *v40; // rcx
  void *v41; // rcx
  void *v42; // rcx
  void *v43; // rcx
  void *v44; // rcx
  int v45; // eax
  _DWORD *v46; // rcx
  int v47; // r8d
  int v48; // r9d
  int v49; // [rsp+20h] [rbp-E0h]
  int *v50; // [rsp+40h] [rbp-C0h] BYREF
  int v51; // [rsp+48h] [rbp-B8h] BYREF
  int v52; // [rsp+4Ch] [rbp-B4h]
  const wchar_t *v53; // [rsp+58h] [rbp-A8h]
  _QWORD v54[2]; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v55; // [rsp+70h] [rbp-90h] BYREF
  __int64 v56; // [rsp+88h] [rbp-78h]
  bool v57[8]; // [rsp+90h] [rbp-70h] BYREF
  __int64 v58; // [rsp+98h] [rbp-68h] BYREF
  bool v59[8]; // [rsp+A0h] [rbp-60h] BYREF
  bool v60[8]; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v61; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v62; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v63; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v64; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v65; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v66; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v67; // [rsp+E0h] [rbp-20h] BYREF
  bool v68[8]; // [rsp+E8h] [rbp-18h] BYREF
  _QWORD v69[3]; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE v70[32]; // [rsp+108h] [rbp+8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+178h] [rbp+78h]

  if ( a2 )
  {
    v4 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
    if ( *v4 > 4u )
    {
      *(_QWORD *)v59 = "MidiSrvGetTransportList";
      *(_QWORD *)v57 = L"Enter";
      *(_QWORD *)v60 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>>(
        (_DWORD)v4,
        (unsigned int)byte_14008B1AB,
        v5,
        v6,
        (__int64)v59,
        (__int64)v60,
        (__int64)v57);
    }
    v7 = CoInitializeEx(0, 0);
    if ( v7 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x14D3,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        (const char *)(unsigned int)v7,
        v49);
    v8 = g_MidiService;
    v9 = *((_QWORD *)g_MidiService + 9);
    if ( v9 )
      _InterlockedAdd((volatile signed __int32 *)(v9 + 8), 1u);
    v10 = (volatile signed __int32 *)*((_QWORD *)v8 + 9);
    CMidiConfigurationManager::GetAllEnabledTransportMetadata(*((_QWORD *)v8 + 8), v69);
    winrt::Windows::Data::Json::JsonObject::JsonObject((winrt::Windows::Data::Json::JsonObject *)&v61);
    v11 = (__int128 *)v69[0];
    v12 = (__int128 *)v69[1];
    while ( v11 != v12 )
    {
      winrt::Windows::Data::Json::JsonObject::JsonObject((winrt::Windows::Data::Json::JsonObject *)v54);
      v13 = *((_QWORD *)v11 + 3);
      if ( v13 )
      {
        v14 = -1;
        do
          ++v14;
        while ( *(_WORD *)(v13 + 2 * v14) );
        if ( (_DWORD)v14 )
        {
          if ( *(_WORD *)(v13 + 2LL * (unsigned int)v14) )
            abort();
          DWORD2(v55) = 1;
          *(_QWORD *)&v55 = (char *)&v55 + 8;
          HIDWORD(v55) = v14;
          v56 = v13;
        }
        else
        {
          *(_QWORD *)&v55 = 0;
        }
        StringValue = winrt::Windows::Data::Json::JsonValue::CreateStringValue((const struct winrt::param::hstring *)&v62);
        v51 = 1;
        v53 = L"name";
        v52 = 4;
        v50 = &v51;
        winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(
          v54,
          &v50,
          StringValue);
        if ( v62 )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v62);
      }
      v16 = *((_QWORD *)v11 + 2);
      if ( v16 )
      {
        v17 = -1;
        do
          ++v17;
        while ( *(_WORD *)(v16 + 2 * v17) );
        if ( (_DWORD)v17 )
        {
          if ( *(_WORD *)(v16 + 2LL * (unsigned int)v17) )
            abort();
          DWORD2(v55) = 1;
          *(_QWORD *)&v55 = (char *)&v55 + 8;
          HIDWORD(v55) = v17;
          v56 = v16;
        }
        else
        {
          *(_QWORD *)&v55 = 0;
        }
        v18 = winrt::Windows::Data::Json::JsonValue::CreateStringValue((const struct winrt::param::hstring *)&v63);
        v51 = 1;
        v53 = L"transportCode";
        v52 = 13;
        v50 = &v51;
        winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(
          v54,
          &v50,
          v18);
        if ( v63 )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v63);
      }
      v19 = *((_QWORD *)v11 + 4);
      if ( v19 )
      {
        v20 = -1;
        do
          ++v20;
        while ( *(_WORD *)(v19 + 2 * v20) );
        if ( (_DWORD)v20 )
        {
          if ( *(_WORD *)(v19 + 2LL * (unsigned int)v20) )
            abort();
          DWORD2(v55) = 1;
          *(_QWORD *)&v55 = (char *)&v55 + 8;
          HIDWORD(v55) = v20;
          v56 = v19;
        }
        else
        {
          *(_QWORD *)&v55 = 0;
        }
        v21 = winrt::Windows::Data::Json::JsonValue::CreateStringValue((const struct winrt::param::hstring *)&v64);
        v51 = 1;
        v53 = L"description";
        v52 = 11;
        v50 = &v51;
        winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(
          v54,
          &v50,
          v21);
        if ( v64 )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v64);
      }
      v22 = *((_QWORD *)v11 + 5);
      if ( v22 )
      {
        v23 = -1;
        do
          ++v23;
        while ( *(_WORD *)(v22 + 2 * v23) );
        if ( (_DWORD)v23 )
        {
          if ( *(_WORD *)(v22 + 2LL * (unsigned int)v23) )
            abort();
          DWORD2(v55) = 1;
          *(_QWORD *)&v55 = (char *)&v55 + 8;
          HIDWORD(v55) = v23;
          v56 = v22;
        }
        else
        {
          *(_QWORD *)&v55 = 0;
        }
        v24 = winrt::Windows::Data::Json::JsonValue::CreateStringValue((const struct winrt::param::hstring *)&v65);
        v51 = 1;
        v53 = L"author";
        v52 = 6;
        v50 = &v51;
        winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(
          v54,
          &v50,
          v24);
        if ( v65 )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v65);
      }
      v25 = *((_QWORD *)v11 + 6);
      if ( v25 )
      {
        v26 = -1;
        do
          ++v26;
        while ( *(_WORD *)(v25 + 2 * v26) );
        if ( (_DWORD)v26 )
        {
          if ( *(_WORD *)(v25 + 2LL * (unsigned int)v26) )
            abort();
          DWORD2(v55) = 1;
          *(_QWORD *)&v55 = (char *)&v55 + 8;
          HIDWORD(v55) = v26;
          v56 = v25;
        }
        else
        {
          *(_QWORD *)&v55 = 0;
        }
        v27 = winrt::Windows::Data::Json::JsonValue::CreateStringValue((const struct winrt::param::hstring *)&v66);
        v51 = 1;
        v53 = L"imageFileName";
        v52 = 13;
        v50 = &v51;
        winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(
          v54,
          &v50,
          v27);
        if ( v66 )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v66);
      }
      v28 = *((_QWORD *)v11 + 7);
      if ( v28 )
      {
        v29 = -1;
        do
          ++v29;
        while ( *(_WORD *)(v28 + 2 * v29) );
        if ( (_DWORD)v29 )
        {
          if ( *(_WORD *)(v28 + 2LL * (unsigned int)v29) )
            abort();
          DWORD2(v55) = 1;
          *(_QWORD *)&v55 = (char *)&v55 + 8;
          HIDWORD(v55) = v29;
          v56 = v28;
        }
        else
        {
          *(_QWORD *)&v55 = 0;
        }
        v30 = winrt::Windows::Data::Json::JsonValue::CreateStringValue((const struct winrt::param::hstring *)&v67);
        v51 = 1;
        v53 = L"version";
        v52 = 7;
        v50 = &v51;
        winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(
          v54,
          &v50,
          v30);
        if ( v67 )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v67);
      }
      BooleanValue = winrt::Windows::Data::Json::JsonValue::CreateBooleanValue((bool)v68);
      v51 = 1;
      v53 = L"isRuntimeCreatableByApps";
      v52 = 24;
      v50 = &v51;
      winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(
        v54,
        &v50,
        BooleanValue);
      if ( *(_QWORD *)v68 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v68);
      v32 = winrt::Windows::Data::Json::JsonValue::CreateBooleanValue((bool)v59);
      v51 = 1;
      v53 = L"isRuntimeCreatableBySettings";
      v52 = 28;
      v50 = &v51;
      winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(
        v54,
        &v50,
        v32);
      if ( *(_QWORD *)v59 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v59);
      v33 = winrt::Windows::Data::Json::JsonValue::CreateBooleanValue((bool)v60);
      v51 = 1;
      v53 = L"isSystemManaged";
      v52 = 15;
      v50 = &v51;
      winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(
        v54,
        &v50,
        v33);
      if ( *(_QWORD *)v60 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v60);
      v34 = winrt::Windows::Data::Json::JsonValue::CreateBooleanValue((bool)v57);
      v51 = 1;
      v53 = L"isClientConfigurable";
      v52 = 20;
      v50 = &v51;
      winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(
        v54,
        &v50,
        v34);
      if ( *(_QWORD *)v57 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v57);
      v58 = 0;
      if ( v54[0] )
      {
        (**(void (__fastcall ***)(_QWORD, __int64 *, __int64 *))v54[0])(
          v54[0],
          winrt::impl::guid_v<winrt::Windows::Data::Json::IJsonValue>,
          &v58);
        v35 = v58;
      }
      else
      {
        v35 = 0;
      }
      v55 = *v11;
      v36 = (const wchar_t **)WindowsMidiServicesInternal::GuidToString(v70, &v55);
      v37 = (const wchar_t *)v36;
      if ( (unsigned __int64)v36[3] > 7 )
        v37 = *v36;
      v38 = -1;
      do
        ++v38;
      while ( v37[v38] );
      if ( (_DWORD)v38 )
      {
        if ( v37[(unsigned int)v38] )
          abort();
        v51 = 1;
        v50 = &v51;
        v52 = v38;
        v53 = v37;
      }
      else
      {
        v50 = 0;
      }
      winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(
        &v61,
        &v50,
        &v58);
      std::wstring::~wstring(v70);
      if ( v35 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v58);
      v39 = (void *)*((_QWORD *)v11 + 3);
      if ( v39 )
      {
        CoTaskMemFree(v39);
        *((_QWORD *)v11 + 3) = 0;
      }
      v40 = (void *)*((_QWORD *)v11 + 2);
      if ( v40 )
      {
        CoTaskMemFree(v40);
        *((_QWORD *)v11 + 2) = 0;
      }
      v41 = (void *)*((_QWORD *)v11 + 4);
      if ( v41 )
      {
        CoTaskMemFree(v41);
        *((_QWORD *)v11 + 4) = 0;
      }
      v42 = (void *)*((_QWORD *)v11 + 5);
      if ( v42 )
      {
        CoTaskMemFree(v42);
        *((_QWORD *)v11 + 5) = 0;
      }
      v43 = (void *)*((_QWORD *)v11 + 6);
      if ( v43 )
      {
        CoTaskMemFree(v43);
        *((_QWORD *)v11 + 6) = 0;
      }
      v44 = (void *)*((_QWORD *)v11 + 7);
      if ( v44 )
      {
        CoTaskMemFree(v44);
        *((_QWORD *)v11 + 7) = 0;
      }
      if ( v54[0] )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v54);
      v11 = (__int128 *)((char *)v11 + 72);
    }
    *(_QWORD *)v57 = v61;
    if ( v61 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v61 + 8LL))(v61);
    v45 = StringifyJsonToOutputParameter(v57, a2);
    if ( v45 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x24A,
        (unsigned int)"avcore\\midi2\\service\\exe\\midisrvrpc.cpp",
        (const char *)(unsigned int)v45,
        v49);
    v46 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
    if ( *v46 > 4u )
    {
      *(_QWORD *)v60 = 0;
      *(_QWORD *)v57 = L"Exit success";
      *(_QWORD *)v59 = "MidiSrvGetTransportList";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>>(
        (_DWORD)v46,
        (unsigned int)qword_14008B2E0,
        v47,
        v48,
        (__int64)v59,
        (__int64)v60,
        (__int64)v57);
    }
    if ( v61 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v61);
    std::vector<__MIDL___MIDL_itf_windowsmidiservices_0000_0012_0001>::~vector<__MIDL___MIDL_itf_windowsmidiservices_0000_0012_0001>(v69);
    if ( v10 )
    {
      if ( _InterlockedExchangeAdd(v10 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v10)(v10);
        if ( _InterlockedExchangeAdd(v10 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v10 + 8LL))(v10);
      }
    }
    CoUninitialize();
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x217,
      (unsigned int)"avcore\\midi2\\service\\exe\\midisrvrpc.cpp",
      (const char *)0x80070057LL,
      v49);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x14003e0d0  push    rbp
0x14003e0d2  push    rbx
0x14003e0d3  push    rsi
0x14003e0d4  push    rdi
0x14003e0d5  push    r12
0x14003e0d7  push    r13
0x14003e0d9  push    r14
0x14003e0db  push    r15
0x14003e0dd  lea     rbp, [rsp-38h]
0x14003e0e2  sub     rsp, 138h
0x14003e0e9  mov     rax, cs:__security_cookie
0x14003e0f0  xor     rax, rsp
0x14003e0f3  mov     [rbp+70h+var_48], rax
0x14003e0f7  xor     r12d, r12d
0x14003e0fa  mov     r14, rdx
0x14003e0fd  test    rdx, rdx
0x14003e100  jnz     short loc_14003E126
0x14003e102  mov     rcx, [rbp+78h]; this
0x14003e106  lea     r8, aAvcoreMidi2Ser_10; "avcore\\midi2\\service\\exe\\midisrvrpc"...
0x14003e10d  mov     ebx, 80070057h
0x14003e112  mov     edx, 217h; void *
0x14003e117  mov     r9d, ebx; char *
0x14003e11a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14003e11f  mov     eax, ebx
0x14003e121  jmp     loc_14003E936
0x14003e126  call    ?Instance@MidiSrvTelemetryProvider@@KAPEAV1@XZ; MidiSrvTelemetryProvider::Instance(void)
0x14003e12b  lea     rdx, aMidisrvgettran_0; "MidiSrvGetTransportList"
0x14003e132  mov     rcx, [rax+8]
0x14003e136  mov     eax, [rcx]
0x14003e138  cmp     eax, 4
0x14003e13b  jbe     short loc_14003E177
0x14003e13d  lea     rax, aEnter; "Enter"
0x14003e144  mov     qword ptr [rbp+70h+var_D0], rdx
0x14003e148  mov     qword ptr [rbp+70h+var_E0], rax
0x14003e14c  lea     rdx, byte_14008B1AB
0x14003e153  lea     rax, [rbp+70h+var_E0]
0x14003e157  mov     qword ptr [rbp+70h+var_C8], r12
0x14003e15b  mov     [rsp+170h+var_140], rax
0x14003e160  lea     rax, [rbp+70h+var_C8]
0x14003e164  mov     [rsp+170h+var_148], rax
0x14003e169  lea     rax, [rbp+70h+var_D0]
0x14003e16d  mov     qword ptr [rsp+170h+var_150], rax; int
0x14003e172  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &)
0x14003e177  xor     edx, edx; dwCoInit
0x14003e179  xor     ecx, ecx; pvReserved
0x14003e17b  call    cs:__imp_CoInitializeEx
0x14003e181  test    eax, eax
0x14003e183  js      loc_14003E956
0x14003e189  mov     rcx, cs:?g_MidiService@@3V?$unique_ptr@VCMidiSrv@@U?$default_delete@VCMidiSrv@@@std@@@std@@A; std::unique_ptr<CMidiSrv> g_MidiService
0x14003e190  mov     r13d, 1
0x14003e196  mov     rax, [rcx+48h]
0x14003e19a  test    rax, rax
0x14003e19d  jz      short loc_14003E1A4
0x14003e19f  lock add [rax+8], r13d
0x14003e1a4  mov     rsi, [rcx+48h]
0x14003e1a8  lea     rdx, [rbp+70h+var_80]
0x14003e1ac  mov     rcx, [rcx+40h]
0x14003e1b0  call    ?GetAllEnabledTransportMetadata@CMidiConfigurationManager@@QEBA?AV?$vector@U__MIDL___MIDL_itf_windowsmidiservices_0000_0012_0001@@V?$allocator@U__MIDL___MIDL_itf_windowsmidiservices_0000_0012_0001@@@std@@@std@@XZ; CMidiConfigurationManager::GetAllEnabledTransportMetadata(void)
0x14003e1b5  lea     rcx, [rbp+70h+var_C0]; this
0x14003e1b9  call    ??0JsonObject@Json@Data@Windows@winrt@@QEAA@XZ; winrt::Windows::Data::Json::JsonObject::JsonObject(void)
0x14003e1be  mov     rbx, [rbp+70h+var_80]
0x14003e1c2  mov     r15, [rbp+70h+var_78]
0x14003e1c6  or      rdi, 0FFFFFFFFFFFFFFFFh
0x14003e1ca  cmp     rbx, r15
0x14003e1cd  jz      loc_14003E84C
0x14003e1d3  lea     rcx, [rsp+170h+var_110]; this
0x14003e1d8  call    ??0JsonObject@Json@Data@Windows@winrt@@QEAA@XZ; winrt::Windows::Data::Json::JsonObject::JsonObject(void)
0x14003e1dd  mov     rdx, [rbx+18h]
0x14003e1e1  test    rdx, rdx
0x14003e1e4  jz      loc_14003E278
0x14003e1ea  mov     rcx, rdi
0x14003e1ed  inc     rcx
0x14003e1f0  cmp     [rdx+rcx*2], r12w
0x14003e1f5  jnz     short loc_14003E1ED
0x14003e1f7  test    ecx, ecx
0x14003e1f9  jnz     short loc_14003E202
0x14003e1fb  mov     qword ptr [rsp+170h+var_100], r12
0x14003e200  jmp     short loc_14003E226
0x14003e202  mov     eax, ecx
0x14003e204  cmp     [rdx+rax*2], r12w
0x14003e209  jnz     loc_14003E81B
0x14003e20f  lea     rax, [rsp+170h+var_100+8]
0x14003e214  mov     dword ptr [rsp+170h+var_100+8], r13d
0x14003e219  mov     qword ptr [rsp+170h+var_100], rax
0x14003e21e  mov     dword ptr [rsp+170h+var_100+0Ch], ecx
0x14003e222  mov     [rbp+70h+var_E8], rdx
0x14003e226  lea     rdx, [rsp+170h+var_100]
0x14003e22b  lea     rcx, [rbp+70h+var_B8]; struct winrt::param::hstring *
0x14003e22f  call    ?CreateStringValue@JsonValue@Json@Data@Windows@winrt@@SA@AEBUhstring@param@5@@Z; winrt::Windows::Data::Json::JsonValue::CreateStringValue(winrt::param::hstring const &)
0x14003e234  lea     rcx, aName; "name"
0x14003e23b  mov     [rsp+170h+var_128], r13d
0x14003e240  mov     [rsp+170h+var_118], rcx
0x14003e245  lea     rdx, [rsp+170h+var_130]
0x14003e24a  lea     rcx, [rsp+170h+var_128]
0x14003e24f  mov     [rsp+170h+var_124], 4
0x14003e257  mov     [rsp+170h+var_130], rcx
0x14003e25c  mov     r8, rax
0x14003e25f  lea     rcx, [rsp+170h+var_110]
0x14003e264  call    ?SetNamedValue@?$consume_Windows_Data_Json_IJsonObject@UIJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@AEBUIJsonValue@Json@Data@Windows@3@@Z; winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(winrt::param::hstring const &,winrt::Windows::Data::Json::IJsonValue const &)
0x14003e269  cmp     [rbp+70h+var_B8], r12
0x14003e26d  jz      short loc_14003E278
0x14003e26f  lea     rcx, [rbp+70h+var_B8]
0x14003e273  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x14003e278  mov     rdx, [rbx+10h]
0x14003e27c  test    rdx, rdx
0x14003e27f  jz      loc_14003E313
0x14003e285  mov     rcx, rdi
0x14003e288  inc     rcx
0x14003e28b  cmp     [rdx+rcx*2], r12w
0x14003e290  jnz     short loc_14003E288
0x14003e292  test    ecx, ecx
0x14003e294  jnz     short loc_14003E29D
0x14003e296  mov     qword ptr [rsp+170h+var_100], r12
0x14003e29b  jmp     short loc_14003E2C1
0x14003e29d  mov     eax, ecx
0x14003e29f  cmp     [rdx+rax*2], r12w
0x14003e2a4  jnz     loc_14003E822
0x14003e2aa  lea     rax, [rsp+170h+var_100+8]
0x14003e2af  mov     dword ptr [rsp+170h+var_100+8], r13d
0x14003e2b4  mov     qword ptr [rsp+170h+var_100], rax
0x14003e2b9  mov     dword ptr [rsp+170h+var_100+0Ch], ecx
0x14003e2bd  mov     [rbp+70h+var_E8], rdx
0x14003e2c1  lea     rdx, [rsp+170h+var_100]
0x14003e2c6  lea     rcx, [rbp+70h+var_B0]; struct winrt::param::hstring *
0x14003e2ca  call    ?CreateStringValue@JsonValue@Json@Data@Windows@winrt@@SA@AEBUhstring@param@5@@Z; winrt::Windows::Data::Json::JsonValue::CreateStringValue(winrt::param::hstring const &)
0x14003e2cf  lea     rcx, aTransportcode; "transportCode"
0x14003e2d6  mov     [rsp+170h+var_128], r13d
0x14003e2db  mov     [rsp+170h+var_118], rcx
0x14003e2e0  lea     rdx, [rsp+170h+var_130]
0x14003e2e5  lea     rcx, [rsp+170h+var_128]
0x14003e2ea  mov     [rsp+170h+var_124], 0Dh
0x14003e2f2  mov     [rsp+170h+var_130], rcx
0x14003e2f7  mov     r8, rax
0x14003e2fa  lea     rcx, [rsp+170h+var_110]
0x14003e2ff  call    ?SetNamedValue@?$consume_Windows_Data_Json_IJsonObject@UIJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@AEBUIJsonValue@Json@Data@Windows@3@@Z; winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(winrt::param::hstring const &,winrt::Windows::Data::Json::IJsonValue const &)
0x14003e304  cmp     [rbp+70h+var_B0], r12
0x14003e308  jz      short loc_14003E313
0x14003e30a  lea     rcx, [rbp+70h+var_B0]
0x14003e30e  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x14003e313  mov     rdx, [rbx+20h]
0x14003e317  test    rdx, rdx
0x14003e31a  jz      loc_14003E3AE
0x14003e320  mov     rcx, rdi
0x14003e323  inc     rcx
0x14003e326  cmp     [rdx+rcx*2], r12w
0x14003e32b  jnz     short loc_14003E323
0x14003e32d  test    ecx, ecx
0x14003e32f  jnz     short loc_14003E338
0x14003e331  mov     qword ptr [rsp+170h+var_100], r12
0x14003e336  jmp     short loc_14003E35C
0x14003e338  mov     eax, ecx
0x14003e33a  cmp     [rdx+rax*2], r12w
0x14003e33f  jnz     loc_14003E829
0x14003e345  lea     rax, [rsp+170h+var_100+8]
0x14003e34a  mov     dword ptr [rsp+170h+var_100+8], r13d
0x14003e34f  mov     qword ptr [rsp+170h+var_100], rax
0x14003e354  mov     dword ptr [rsp+170h+var_100+0Ch], ecx
0x14003e358  mov     [rbp+70h+var_E8], rdx
0x14003e35c  lea     rdx, [rsp+170h+var_100]
0x14003e361  lea     rcx, [rbp+70h+var_A8]; struct winrt::param::hstring *
0x14003e365  call    ?CreateStringValue@JsonValue@Json@Data@Windows@winrt@@SA@AEBUhstring@param@5@@Z; winrt::Windows::Data::Json::JsonValue::CreateStringValue(winrt::param::hstring const &)
0x14003e36a  lea     rcx, aDescription; "description"
0x14003e371  mov     [rsp+170h+var_128], r13d
0x14003e376  mov     [rsp+170h+var_118], rcx
0x14003e37b  lea     rdx, [rsp+170h+var_130]
0x14003e380  lea     rcx, [rsp+170h+var_128]
0x14003e385  mov     [rsp+170h+var_124], 0Bh
0x14003e38d  mov     [rsp+170h+var_130], rcx
0x14003e392  mov     r8, rax
0x14003e395  lea     rcx, [rsp+170h+var_110]
0x14003e39a  call    ?SetNamedValue@?$consume_Windows_Data_Json_IJsonObject@UIJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@AEBUIJsonValue@Json@Data@Windows@3@@Z; winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(winrt::param::hstring const &,winrt::Windows::Data::Json::IJsonValue const &)
0x14003e39f  cmp     [rbp+70h+var_A8], r12
0x14003e3a3  jz      short loc_14003E3AE
0x14003e3a5  lea     rcx, [rbp+70h+var_A8]
0x14003e3a9  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x14003e3ae  mov     rdx, [rbx+28h]
0x14003e3b2  test    rdx, rdx
0x14003e3b5  jz      loc_14003E449
0x14003e3bb  mov     rcx, rdi
0x14003e3be  inc     rcx
0x14003e3c1  cmp     [rdx+rcx*2], r12w
0x14003e3c6  jnz     short loc_14003E3BE
0x14003e3c8  test    ecx, ecx
0x14003e3ca  jnz     short loc_14003E3D3
0x14003e3cc  mov     qword ptr [rsp+170h+var_100], r12
0x14003e3d1  jmp     short loc_14003E3F7
0x14003e3d3  mov     eax, ecx
0x14003e3d5  cmp     [rdx+rax*2], r12w
0x14003e3da  jnz     loc_14003E830
0x14003e3e0  lea     rax, [rsp+170h+var_100+8]
0x14003e3e5  mov     dword ptr [rsp+170h+var_100+8], r13d
0x14003e3ea  mov     qword ptr [rsp+170h+var_100], rax
0x14003e3ef  mov     dword ptr [rsp+170h+var_100+0Ch], ecx
0x14003e3f3  mov     [rbp+70h+var_E8], rdx
0x14003e3f7  lea     rdx, [rsp+170h+var_100]
0x14003e3fc  lea     rcx, [rbp+70h+var_A0]; struct winrt::param::hstring *
0x14003e400  call    ?CreateStringValue@JsonValue@Json@Data@Windows@winrt@@SA@AEBUhstring@param@5@@Z; winrt::Windows::Data::Json::JsonValue::CreateStringValue(winrt::param::hstring const &)
0x14003e405  lea     rcx, aAuthor; "author"
0x14003e40c  mov     [rsp+170h+var_128], r13d
0x14003e411  mov     [rsp+170h+var_118], rcx
0x14003e416  lea     rdx, [rsp+170h+var_130]
0x14003e41b  lea     rcx, [rsp+170h+var_128]
0x14003e420  mov     [rsp+170h+var_124], 6
0x14003e428  mov     [rsp+170h+var_130], rcx
0x14003e42d  mov     r8, rax
0x14003e430  lea     rcx, [rsp+170h+var_110]
0x14003e435  call    ?SetNamedValue@?$consume_Windows_Data_Json_IJsonObject@UIJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@AEBUIJsonValue@Json@Data@Windows@3@@Z; winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(winrt::param::hstring const &,winrt::Windows::Data::Json::IJsonValue const &)
0x14003e43a  cmp     [rbp+70h+var_A0], r12
0x14003e43e  jz      short loc_14003E449
0x14003e440  lea     rcx, [rbp+70h+var_A0]
0x14003e444  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x14003e449  mov     rdx, [rbx+30h]
0x14003e44d  test    rdx, rdx
0x14003e450  jz      loc_14003E4E4
0x14003e456  mov     rcx, rdi
0x14003e459  inc     rcx
0x14003e45c  cmp     [rdx+rcx*2], r12w
0x14003e461  jnz     short loc_14003E459
0x14003e463  test    ecx, ecx
0x14003e465  jnz     short loc_14003E46E
0x14003e467  mov     qword ptr [rsp+170h+var_100], r12
0x14003e46c  jmp     short loc_14003E492
0x14003e46e  mov     eax, ecx
0x14003e470  cmp     [rdx+rax*2], r12w
0x14003e475  jnz     loc_14003E837
0x14003e47b  lea     rax, [rsp+170h+var_100+8]
0x14003e480  mov     dword ptr [rsp+170h+var_100+8], r13d
0x14003e485  mov     qword ptr [rsp+170h+var_100], rax
0x14003e48a  mov     dword ptr [rsp+170h+var_100+0Ch], ecx
0x14003e48e  mov     [rbp+70h+var_E8], rdx
0x14003e492  lea     rdx, [rsp+170h+var_100]
0x14003e497  lea     rcx, [rbp+70h+var_98]; struct winrt::param::hstring *
0x14003e49b  call    ?CreateStringValue@JsonValue@Json@Data@Windows@winrt@@SA@AEBUhstring@param@5@@Z; winrt::Windows::Data::Json::JsonValue::CreateStringValue(winrt::param::hstring const &)
0x14003e4a0  lea     rcx, aImagefilename; "imageFileName"
0x14003e4a7  mov     [rsp+170h+var_128], r13d
0x14003e4ac  mov     [rsp+170h+var_118], rcx
0x14003e4b1  lea     rdx, [rsp+170h+var_130]
0x14003e4b6  lea     rcx, [rsp+170h+var_128]
0x14003e4bb  mov     [rsp+170h+var_124], 0Dh
0x14003e4c3  mov     [rsp+170h+var_130], rcx
0x14003e4c8  mov     r8, rax
0x14003e4cb  lea     rcx, [rsp+170h+var_110]
0x14003e4d0  call    ?SetNamedValue@?$consume_Windows_Data_Json_IJsonObject@UIJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@AEBUIJsonValue@Json@Data@Windows@3@@Z; winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(winrt::param::hstring const &,winrt::Windows::Data::Json::IJsonValue const &)
0x14003e4d5  cmp     [rbp+70h+var_98], r12
0x14003e4d9  jz      short loc_14003E4E4
0x14003e4db  lea     rcx, [rbp+70h+var_98]
0x14003e4df  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x14003e4e4  mov     rdx, [rbx+38h]
0x14003e4e8  test    rdx, rdx
0x14003e4eb  jz      loc_14003E57F
0x14003e4f1  mov     rcx, rdi
0x14003e4f4  inc     rcx
0x14003e4f7  cmp     [rdx+rcx*2], r12w
0x14003e4fc  jnz     short loc_14003E4F4
0x14003e4fe  test    ecx, ecx
0x14003e500  jnz     short loc_14003E509
0x14003e502  mov     qword ptr [rsp+170h+var_100], r12
0x14003e507  jmp     short loc_14003E52D
0x14003e509  mov     eax, ecx
0x14003e50b  cmp     [rdx+rax*2], r12w
0x14003e510  jnz     loc_14003E83E
0x14003e516  lea     rax, [rsp+170h+var_100+8]
0x14003e51b  mov     dword ptr [rsp+170h+var_100+8], r13d
0x14003e520  mov     qword ptr [rsp+170h+var_100], rax
0x14003e525  mov     dword ptr [rsp+170h+var_100+0Ch], ecx
0x14003e529  mov     [rbp+70h+var_E8], rdx
0x14003e52d  lea     rdx, [rsp+170h+var_100]
0x14003e532  lea     rcx, [rbp+70h+var_90]; struct winrt::param::hstring *
0x14003e536  call    ?CreateStringValue@JsonValue@Json@Data@Windows@winrt@@SA@AEBUhstring@param@5@@Z; winrt::Windows::Data::Json::JsonValue::CreateStringValue(winrt::param::hstring const &)
0x14003e53b  lea     rcx, aVersion; "version"
0x14003e542  mov     [rsp+170h+var_128], r13d
0x14003e547  mov     [rsp+170h+var_118], rcx
0x14003e54c  lea     rdx, [rsp+170h+var_130]
0x14003e551  lea     rcx, [rsp+170h+var_128]
0x14003e556  mov     [rsp+170h+var_124], 7
0x14003e55e  mov     [rsp+170h+var_130], rcx
0x14003e563  mov     r8, rax
0x14003e566  lea     rcx, [rsp+170h+var_110]
0x14003e56b  call    ?SetNamedValue@?$consume_Windows_Data_Json_IJsonObject@UIJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@AEBUIJsonValue@Json@Data@Windows@3@@Z; winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(winrt::param::hstring const &,winrt::Windows::Data::Json::IJsonValue const &)
0x14003e570  cmp     [rbp+70h+var_90], r12
0x14003e574  jz      short loc_14003E57F
0x14003e576  lea     rcx, [rbp+70h+var_90]
0x14003e57a  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x14003e57f  mov     dl, [rbx+40h]
0x14003e582  lea     rcx, [rbp+70h+var_88]; bool
0x14003e586  and     dl, r13b
0x14003e589  call    ?CreateBooleanValue@JsonValue@Json@Data@Windows@winrt@@SA@_N@Z; winrt::Windows::Data::Json::JsonValue::CreateBooleanValue(bool)
0x14003e58e  lea     rcx, aIsruntimecreat; "isRuntimeCreatableByApps"
0x14003e595  mov     [rsp+170h+var_128], r13d
0x14003e59a  mov     [rsp+170h+var_118], rcx
0x14003e59f  lea     rdx, [rsp+170h+var_130]
0x14003e5a4  lea     rcx, [rsp+170h+var_128]
0x14003e5a9  mov     [rsp+170h+var_124], 18h
0x14003e5b1  mov     [rsp+170h+var_130], rcx
0x14003e5b6  mov     r8, rax
0x14003e5b9  lea     rcx, [rsp+170h+var_110]
0x14003e5be  call    ?SetNamedValue@?$consume_Windows_Data_Json_IJsonObject@UIJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@AEBUIJsonValue@Json@Data@Windows@3@@Z; winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(winrt::param::hstring const &,winrt::Windows::Data::Json::IJsonValue const &)
0x14003e5c3  cmp     qword ptr [rbp+70h+var_88], r12
0x14003e5c7  jz      short loc_14003E5D2
0x14003e5c9  lea     rcx, [rbp+70h+var_88]
  ... truncated ...
```
