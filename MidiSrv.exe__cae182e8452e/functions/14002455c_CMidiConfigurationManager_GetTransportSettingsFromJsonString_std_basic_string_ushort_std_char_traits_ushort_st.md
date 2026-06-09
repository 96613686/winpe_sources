# CMidiConfigurationManager::GetTransportSettingsFromJsonString(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>)

- ea: `0x14002455c`
- end: `0x140025040`
- name: `?GetTransportSettingsFromJsonString@CMidiConfigurationManager@@QEBA?AV?$map@U_GUID@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UGUIDCompare@@V?$allocator@U?$pair@$$CBU_GUID@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@3@@std@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@3@@Z`
- size: `2788`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `29`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x14003ed10`

## callees

- `0x14000183c`
- `0x1400018e4`
- `0x140001ce8`
- `0x140002580`
- `0x1400054c0`
- `0x1400054e4`
- `0x1400060d4`
- `0x14000617c`
- `0x1400061e8`
- `0x1400072d4`
- `0x140007c20`
- `0x14000984c`
- `0x14000ca00`
- `0x14000cc2c`
- `0x140013a38`
- `0x1400145bc`
- `0x14001e5e0`
- `0x14001e810`
- `0x1400223c0`
- `0x140022e58`
- `0x14002308c`
- `0x140023108`
- `0x140023258`
- `0x1400232c8`
- `0x140023f38`
- `0x14002455c`
- `0x140026070`
- `0x1400260e4`
- `0x14005a010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x140024652`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x140024b63`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x140024ce0`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x140024652`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x140024b63`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x140024ce0`

## string_xrefs

- `0x140024b82`: `onecoreuap\Internal\BuildMetadata\internal\cppwinrt\winrt\Windows.Data.Json.h`
- `0x1400247be`: `JSON Object null after parsing`
- `0x1400245bb`: `CMidiConfigurationManager::GetTransportSettingsFromJsonString`
- `0x1400245e9`: `CMidiConfigurationManager::GetTransportSettingsFromJsonString`
- `0x140024e89`: `CMidiConfigurationManager::GetTransportSettingsFromJsonString`
- `0x140024ed1`: `CMidiConfigurationManager::GetTransportSettingsFromJsonString`
- `0x140024720`: `JSON Object parsing failed`
- `0x14002483f`: `endpointTransportPluginSettings`
- `0x1400248ad`: `No transport plugins node in JSON`

## pseudocode

```c
// Hidden C++ exception states: #wind=24 #try_helpers=1
const char **__fastcall CMidiConfigurationManager::GetTransportSettingsFromJsonString(
        wchar_t *a1,
        const char **a2,
        char *a3)
{
  char *v3; // rdi
  const char **v4; // r15
  wchar_t *v5; // r13
  _DWORD *v6; // rcx
  __int64 v7; // r8
  __int64 v8; // r9
  _QWORD *v9; // rax
  unsigned int v10; // r14d
  __int64 v11; // rdx
  char *v12; // rcx
  char v13; // al
  _DWORD *v14; // rcx
  __int64 v15; // r8
  __int64 v16; // r9
  const wchar_t *v17; // rax
  _DWORD *v18; // rcx
  __int64 v19; // r8
  __int64 v20; // r9
  _DWORD *v21; // rcx
  __int64 v22; // r8
  __int64 v23; // r9
  int v25; // eax
  __int64 *v26; // rax
  int v27; // r14d
  __int64 v28; // rcx
  int v29; // eax
  const wchar_t *v30; // rdx
  unsigned __int64 v31; // r8
  unsigned int v32; // r14d
  void *v33; // rsi
  int v34; // eax
  HANDLE ProcessHeap; // rax
  _DWORD *v36; // rcx
  __int64 v37; // r8
  __int64 v38; // r9
  const char *v39; // rax
  __int64 *v40; // rax
  int v41; // r14d
  __int64 v42; // rcx
  int v43; // eax
  int v44; // eax
  const char *v45; // r12
  int v46; // r14d
  __int64 v47; // rax
  const wchar_t *v48; // rdx
  unsigned __int64 v49; // r8
  void *v50; // rsi
  int v51; // eax
  HANDLE v52; // rax
  __int64 v53; // rax
  const char *v54; // r12
  const char *v55; // r13
  const char *v56; // rsi
  _OWORD *v57; // rsi
  _DWORD *v58; // rcx
  __int64 v59; // r8
  __int64 v60; // r9
  const char *v61; // rax
  int v62; // eax
  _DWORD *v63; // rcx
  __int64 v64; // r8
  __int64 v65; // r9
  const char *v66; // rax
  _DWORD *v67; // rcx
  __int64 v68; // r8
  __int64 v69; // r9
  _BYTE v70[4]; // [rsp+40h] [rbp-158h] BYREF
  int v71; // [rsp+44h] [rbp-154h]
  const char *v72; // [rsp+48h] [rbp-150h] BYREF
  const wchar_t *v73; // [rsp+50h] [rbp-148h] BYREF
  const char *v74; // [rsp+58h] [rbp-140h] BYREF
  void (__fastcall ***v75)(_QWORD, __int64 *, __int64 *); // [rsp+60h] [rbp-138h] BYREF
  const char *p_Buf2; // [rsp+68h] [rbp-130h] BYREF
  LPVOID v77; // [rsp+70h] [rbp-128h] BYREF
  __int64 v78; // [rsp+78h] [rbp-120h] BYREF
  void (__fastcall ***v79)(_QWORD, __int64 *, __int64 *); // [rsp+80h] [rbp-118h] BYREF
  __int64 *v80; // [rsp+88h] [rbp-110h] BYREF
  int v81; // [rsp+90h] [rbp-108h] BYREF
  const char *v82; // [rsp+98h] [rbp-100h]
  __int64 v83; // [rsp+A0h] [rbp-F8h]
  LPVOID lpMem; // [rsp+B0h] [rbp-E8h] BYREF
  __int64 v85; // [rsp+B8h] [rbp-E0h] BYREF
  const char *v86; // [rsp+C0h] [rbp-D8h] BYREF
  const char **v87; // [rsp+C8h] [rbp-D0h]
  const char **v88; // [rsp+D0h] [rbp-C8h]
  _OWORD *v89; // [rsp+D8h] [rbp-C0h]
  const char *v90; // [rsp+E0h] [rbp-B8h] BYREF
  int v91; // [rsp+E8h] [rbp-B0h]
  int v92; // [rsp+ECh] [rbp-ACh]
  char v93[16]; // [rsp+F0h] [rbp-A8h] BYREF
  void *v94; // [rsp+100h] [rbp-98h]
  __int128 v95; // [rsp+108h] [rbp-90h] BYREF
  __int64 v96; // [rsp+118h] [rbp-80h]
  const wchar_t *v97; // [rsp+120h] [rbp-78h]
  __int128 Buf2; // [rsp+128h] [rbp-70h] BYREF
  __int128 v99; // [rsp+138h] [rbp-60h] BYREF
  __int64 v100; // [rsp+148h] [rbp-50h]
  unsigned __int64 v101; // [rsp+150h] [rbp-48h]

  v3 = a3;
  v4 = a2;
  v5 = a1;
  v87 = a2;
  v94 = a3;
  v71 = 1;
  v6 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
  if ( *v6 > 4u )
  {
    v73 = v5;
    v72 = "CMidiConfigurationManager::GetTransportSettingsFromJsonString";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
      (__int64)v6,
      (__int64)&word_1400887EE,
      v7,
      v8,
      &v72);
  }
  *v4 = 0;
  v4[1] = 0;
  v9 = operator new(0x50u);
  *v9 = v9;
  v9[1] = v9;
  v9[2] = v9;
  *((_WORD *)v9 + 12) = 257;
  *v4 = (const char *)v9;
  v10 = 1;
  v71 = 1;
  winrt::Windows::Data::Json::JsonObject::JsonObject((winrt::Windows::Data::Json::JsonObject *)&v75);
  v11 = *((_QWORD *)v3 + 2);
  if ( *((_QWORD *)v3 + 3) <= 7u )
    v12 = v3;
  else
    v12 = *(char **)v3;
  if ( (_DWORD)v11 )
  {
    if ( *(_WORD *)&v12[2 * (unsigned int)v11] )
      abort();
    DWORD2(v95) = 1;
    HIDWORD(v95) = v11;
    v97 = (const wchar_t *)v12;
    *(_QWORD *)&v95 = (char *)&v95 + 8;
  }
  else
  {
    *(_QWORD *)&v95 = 0;
  }
  try
  {
    *(_QWORD *)&Buf2 = &v95;
    *((_QWORD *)&Buf2 + 1) = &v75;
    v80 = &qword_140096A98;
    _InterlockedIncrement64(&qword_140096A98);
    if ( winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Data::Json::IJsonObjectStatics> )
    {
      v13 = `winrt::Windows::Data::Json::JsonObject::TryParse'::`2'::_lambda_1_::operator()(
              &Buf2,
              (__int64 **)&winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Data::Json::IJsonObjectStatics>);
      _InterlockedDecrement64(&qword_140096A98);
    }
    else
    {
      _InterlockedDecrement64(&qword_140096A98);
      v13 = ___call_AEAV_lambda_1___1__TryParse_JsonObject_Json_Data_Windows_winrt__SA_AEBUhstring_param_7_AEAU34567__Z____factory_cache_entry_UJsonObject_Json_Data_Windows_winrt__UIJsonObjectStatics_2345__impl_winrt__QEAA_A_PAEAV_lambda_1___1__TryParse_JsonObject_Json_Data_Windows_2_SA_AEBUhstring_param_2_AEAU56782__Z__Z(
              (void (__fastcall ***)(_QWORD, __int64 *, __int64 **))v12,
              (__int64)&Buf2);
    }
  }
  catch ( ... )
  {
    v67 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
    if ( *v67 > 2u )
    {
      v80 = (__int64 *)L"JSON Object parsing failed. Exception.";
      p_Buf2 = (const char *)a1;
      v73 = (const wchar_t *)"CMidiConfigurationManager::GetTransportSettingsFromJsonString";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>>(
        (__int64)v67,
        (__int64)&dword_140088714,
        v68,
        v69,
        &v73,
        (__int64)&p_Buf2,
        &v80);
    }
    v71 = 0;
    if ( v75 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v75);
    std::wstring::~wstring((char **)v94);
    return v87;
  }
  if ( !v13 )
  {
    v14 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
    if ( *v14 > 2u )
    {
      if ( *((_QWORD *)v3 + 3) <= 7u )
        v17 = (const wchar_t *)v3;
      else
        v17 = *(const wchar_t **)v3;
      v73 = v17;
      v72 = (const char *)L"JSON Object parsing failed";
      v77 = v5;
      v86 = "CMidiConfigurationManager::GetTransportSettingsFromJsonString";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
        (__int64)v14,
        (__int64)&dword_140088664,
        v15,
        v16,
        &v86,
        (__int64)&v77,
        &v72,
        &v73);
    }
    v71 = 0;
    if ( v75 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v75);
LABEL_36:
    std::wstring::~wstring((char **)v3);
    return v4;
  }
  v73 = 0;
  if ( winrt::Windows::Foundation::operator==(&v75, &v73) )
  {
    v18 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
    if ( *v18 > 2u )
    {
      v73 = L"JSON Object null after parsing";
      v72 = (const char *)v5;
      v77 = "CMidiConfigurationManager::GetTransportSettingsFromJsonString";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>>(
        (__int64)v18,
        (__int64)byte_140088631,
        v19,
        v20,
        &v77,
        (__int64)&v72,
        &v73);
    }
    v71 = 0;
    if ( v75 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v75);
    goto LABEL_36;
  }
  v73 = 0;
  *((_QWORD *)&v95 + 1) = 0x1F00000001LL;
  v97 = L"endpointTransportPluginSettings";
  *(_QWORD *)&v95 = (char *)&v95 + 8;
  winrt::impl::consume_Windows_Data_Json_IJsonObjectWithDefaultValues<winrt::Windows::Data::Json::JsonObject>::GetNamedObject(
    &v75,
    &v79,
    &v95,
    &v73);
  v73 = 0;
  if ( winrt::Windows::Foundation::operator==(&v79, &v73) )
  {
    v21 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
    if ( *v21 > 2u )
    {
      v73 = L"No transport plugins node in JSON";
      v72 = (const char *)v5;
      v77 = "CMidiConfigurationManager::GetTransportSettingsFromJsonString";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>>(
        (__int64)v21,
        (__int64)byte_1400889A1,
        v22,
        v23,
        &v77,
        (__int64)&v72,
        &v73);
    }
    v71 = 0;
    if ( v79 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v79);
    if ( v75 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v75);
    goto LABEL_36;
  }
  winrt::impl::consume_Windows_Foundation_Collections_IIterable<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::hstring,winrt::Windows::Data::Json::IJsonValue>>::First(
    &v79,
    &v78);
  while ( 1 )
  {
    v70[0] = 0;
    v81 = 64;
    v82 = "onecoreuap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt\\Windows.Foundation.Collections.h";
    v83 = 0;
    v25 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v78 + 56LL))(v78, v70);
    if ( v25 < 0 )
      winrt::throw_hresult((unsigned int)v25, &v81);
    if ( !v70[0] )
      break;
    v26 = (__int64 *)winrt::impl::consume_Windows_Foundation_Collections_IIterator<winrt::Windows::Foundation::Collections::IIterator<winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::hstring,winrt::Windows::Data::Json::IJsonValue>>,winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::hstring,winrt::Windows::Data::Json::IJsonValue>>::Current(
                       &v78,
                       &v86);
    lpMem = 0;
    v27 = v10 | 2;
    v71 = v27;
    v28 = *v26;
    v81 = 118;
    v82 = "onecoreuap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt\\Windows.Foundation.Collections.h";
    v83 = 0;
    v29 = (*(__int64 (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v28 + 48LL))(v28, &lpMem);
    if ( v29 < 0 )
      winrt::throw_hresult((unsigned int)v29, &v81);
    if ( lpMem )
      v30 = (const wchar_t *)*((_QWORD *)lpMem + 2);
    else
      v30 = &S2;
    v99 = 0;
    v100 = 0;
    v101 = 0;
    v31 = -1;
    do
      ++v31;
    while ( v30[v31] );
    std::wstring::_Construct<1,unsigned short const *>((char **)&v99, v30, v31);
    v32 = v27 & 0xFFFFFFFD;
    v71 = v32;
    v33 = lpMem;
    if ( lpMem )
    {
      v34 = _InterlockedDecrement((volatile signed __int32 *)lpMem + 6);
      if ( v34 )
      {
        if ( v34 < 0 )
          abort();
      }
      else
      {
        ProcessHeap = WINRT_IMPL_GetProcessHeap();
        WINRT_IMPL_HeapFree(ProcessHeap, 0, v33);
      }
      lpMem = 0;
    }
    if ( v86 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v86);
    v36 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
    if ( *v36 > 4u )
    {
      v39 = (const char *)&v99;
      if ( v101 > 7 )
        v39 = (const char *)v99;
      v72 = v39;
      v74 = (const char *)v5;
      p_Buf2 = "CMidiConfigurationManager::GetTransportSettingsFromJsonString";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>>(
        (__int64)v36,
        (__int64)&dword_1400886D4,
        v37,
        v38,
        &p_Buf2,
        (__int64)&v74,
        &v72);
    }
    v40 = (__int64 *)winrt::impl::consume_Windows_Foundation_Collections_IIterator<winrt::Windows::Foundation::Collections::IIterator<winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::hstring,winrt::Windows::Data::Json::IJsonValue>>,winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::hstring,winrt::Windows::Data::Json::IJsonValue>>::Current(
                       &v78,
                       &v73);
    v85 = 0;
    v41 = v32 | 4;
    v71 = v41;
    v42 = *v40;
    v81 = 136;
    v82 = "onecoreuap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt\\Windows.Foundation.Collections.h";
    v83 = 0;
    v43 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v42 + 56LL))(v42, &v85);
    if ( v43 < 0 )
      winrt::throw_hresult((unsigned int)v43, &v81);
    v74 = 0;
    v81 = 548;
    v82 = "onecoreuap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt\\Windows.Data.Json.h";
    v83 = 0;
    v44 = (*(__int64 (__fastcall **)(__int64, const char **))(*(_QWORD *)v85 + 96LL))(v85, &v74);
    if ( v44 < 0 )
      winrt::throw_hresult((unsigned int)v44, &v81);
    v45 = v74;
    v72 = v74;
    v46 = v41 | 8;
    v71 = v46;
    v47 = *(_QWORD *)winrt::impl::consume_Windows_Data_Json_IJsonValue<winrt::Windows::Data::Json::IJsonObject>::Stringify(
                       &v72,
                       &v77);
    if ( v47 )
      v48 = *(const wchar_t **)(v47 + 16);
    else
      v48 = &S2;
    v95 = 0;
    v96 = 0;
    v97 = 0;
    v49 = -1;
    do
      ++v49;
    while ( v48[v49] );
    std::wstring::_Construct<1,unsigned short const *>((char **)&v95, v48, v49);
    v50 = v77;
    if ( v77 )
    {
      v51 = _InterlockedDecrement((volatile signed __int32 *)v77 + 6);
      if ( v51 )
      {
        if ( v51 < 0 )
          abort();
      }
      else
      {
        v52 = WINRT_IMPL_GetProcessHeap();
        WINRT_IMPL_HeapFree(v52, 0, v50);
      }
      v77 = 0;
      v45 = v74;
    }
    if ( v45 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v72);
    v10 = v46 & 0xFFFFFFFB;
    v71 = v10;
    if ( v85 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v85);
    if ( v73 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v73);
    try
    {
      Buf2 = 0;
      v53 = std::wstring::wstring((__int64)&v81, (__int64)&v99);
      Buf2 = *(_OWORD *)WindowsMidiServicesInternal::StringToGuid(v93, v53);
    }
    catch ( ... )
    {
      v63 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
      if ( *v63 > 2u )
      {
        v66 = (const char *)&v99;
        if ( v101 > 7 )
          v66 = (const char *)v99;
        p_Buf2 = v66;
        v72 = (const char *)a1;
        v74 = "CMidiConfigurationManager::GetTransportSettingsFromJsonString";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>>(
          (__int64)v63,
          (__int64)&byte_140088817,
          v64,
          v65,
          &v74,
          (__int64)&v72,
          &p_Buf2);
      }
      v10 = v71;
      v4 = v87;
      v3 = (char *)v94;
    }
    v54 = *v4;
    v72 = (const char *)*((_QWORD *)*v4 + 1);
    LODWORD(v74) = 0;
    p_Buf2 = 0;
    v55 = v54;
    v56 = v72;
    while ( !v56[25] )
    {
      v72 = v56;
      if ( memcmp_0(v56 + 32, &Buf2, 0x10u) >= 0 )
      {
        LODWORD(v74) = 1;
        v55 = v56;
        v56 = *(const char **)v56;
      }
      else
      {
        LODWORD(v74) = 0;
        v56 = (const char *)*((_QWORD *)v56 + 2);
      }
    }
    if ( v55[25] || memcmp_0(&Buf2, v55 + 32, 0x10u) < 0 )
    {
      if ( v4[1] == (const char *)0x333333333333333LL )
        std::_Throw_tree_length_error();
      v88 = v4;
      v89 = 0;
      v57 = operator new(0x50u);
      v89 = v57;
      v57[2] = Buf2;
      std::wstring::wstring((__int64)(v57 + 3), (__int64)&v95);
      *(_QWORD *)v57 = v54;
      *((_QWORD *)v57 + 1) = v54;
      *((_QWORD *)v57 + 2) = v54;
      *((_WORD *)v57 + 12) = 0;
      v89 = 0;
      v90 = v72;
      v91 = (int)v74;
      v92 = (int)p_Buf2;
      std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,wil::com_ptr_t<CMidiPipe,wil::err_returncode_policy>>>>::_Insert_node(
        v4,
        (__int64)&v90,
        (__int64)v57);
    }
    else
    {
      std::wstring::operator=(v55 + 48, &v95);
    }
    v58 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
    if ( *v58 <= 4u )
    {
      v5 = a1;
    }
    else
    {
      p_Buf2 = (const char *)&Buf2;
      v61 = (const char *)&v95;
      if ( (unsigned __int64)v97 > 7 )
        v61 = (const char *)v95;
      v72 = v61;
      v5 = a1;
      v74 = (const char *)a1;
      v80 = (__int64 *)"CMidiConfigurationManager::GetTransportSettingsFromJsonString";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapperByRef<16>>(
        (__int64)v58,
        (__int64)&dword_1400885E4,
        v59,
        v60,
        &v80,
        (__int64)&v74,
        &v72);
    }
    v70[0] = 0;
    v81 = 82;
    v82 = "onecoreuap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt\\Windows.Foundation.Collections.h";
    v83 = 0;
    v62 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v78 + 64LL))(v78, v70);
    if ( v62 < 0 )
      winrt::throw_hresult((unsigned int)v62, &v81);
    std::wstring::~wstring((char **)&v95);
    std::wstring::~wstring((char **)&v99);
  }
  if ( v78 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v78);
  if ( v79 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v79);
  if ( v75 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v75);
  std::wstring::~wstring((char **)v3);
  return v4;
}

```

## disassembly

```asm
0x14002455c  mov     [rsp+arg_0], rcx
0x140024561  push    rbx
0x140024562  push    rsi
0x140024563  push    rdi
0x140024564  push    r12
0x140024566  push    r13
0x140024568  push    r14
0x14002456a  push    r15
0x14002456c  sub     rsp, 160h
0x140024573  mov     rax, cs:__security_cookie
0x14002457a  xor     rax, rsp
0x14002457d  mov     [rsp+198h+var_40], rax
0x140024585  mov     rdi, r8
0x140024588  mov     r15, rdx
0x14002458b  mov     r13, rcx
0x14002458e  mov     [rsp+198h+var_D0], rdx
0x140024596  mov     [rsp+198h+var_98], r8
0x14002459e  mov     [rsp+198h+var_154], 1
0x1400245a6  call    ?Instance@MidiSrvTelemetryProvider@@KAPEAV1@XZ; MidiSrvTelemetryProvider::Instance(void)
0x1400245ab  mov     rcx, [rax+8]
0x1400245af  mov     eax, [rcx]
0x1400245b1  cmp     eax, 4
0x1400245b4  jbe     short loc_1400245E9
0x1400245b6  mov     [rsp+198h+var_148], r13
0x1400245bb  lea     r12, aCmidiconfigura_4; "CMidiConfigurationManager::GetTransport"...
0x1400245c2  mov     [rsp+198h+var_150], r12
0x1400245c7  lea     rax, [rsp+198h+var_148]
0x1400245cc  mov     [rsp+198h+var_170], rax
0x1400245d1  lea     rax, [rsp+198h+var_150]
0x1400245d6  mov     [rsp+198h+var_178], rax
0x1400245db  lea     rdx, word_1400887EE
0x1400245e2  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &)
0x1400245e7  jmp     short loc_1400245F0
0x1400245e9  lea     r12, aCmidiconfigura_4; "CMidiConfigurationManager::GetTransport"...
0x1400245f0  xor     ebx, ebx
0x1400245f2  mov     [r15], rbx
0x1400245f5  mov     [r15+8], rbx
0x1400245f9  lea     ecx, [rbx+50h]; Size
0x1400245fc  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140024601  mov     [rax], rax
0x140024604  mov     [rax+8], rax
0x140024608  mov     [rax+10h], rax
0x14002460c  mov     word ptr [rax+18h], 101h
0x140024612  mov     [r15], rax
0x140024615  lea     r14d, [rbx+1]
0x140024619  mov     [rsp+198h+var_154], r14d
0x14002461e  lea     rcx, [rsp+198h+var_138]; this
0x140024623  call    ??0JsonObject@Json@Data@Windows@winrt@@QEAA@XZ; winrt::Windows::Data::Json::JsonObject::JsonObject(void)
0x140024628  nop
0x140024629  mov     rdx, [rdi+10h]
0x14002462d  cmp     qword ptr [rdi+18h], 7
0x140024632  jbe     short loc_140024639
0x140024634  mov     rcx, [rdi]
0x140024637  jmp     short loc_14002463C
0x140024639  mov     rcx, rdi
0x14002463c  test    edx, edx
0x14002463e  jnz     short loc_14002464A
0x140024640  mov     qword ptr [rsp+198h+var_90], rbx
0x140024648  jmp     short loc_140024683
0x14002464a  mov     eax, edx
0x14002464c  cmp     [rcx+rax*2], bx
0x140024650  jz      short loc_140024659
0x140024652  call    cs:__imp_abort
0x140024659  mov     dword ptr [rsp+198h+var_90+8], 1
0x140024664  mov     dword ptr [rsp+198h+var_90+0Ch], edx
0x14002466b  mov     [rsp+198h+var_78], rcx
0x140024673  lea     rax, [rsp+198h+var_90+8]
0x14002467b  mov     qword ptr [rsp+198h+var_90], rax
0x140024683  lea     rax, [rsp+198h+var_90]
0x14002468b  mov     qword ptr [rsp+198h+Buf2], rax
0x140024693  lea     rax, [rsp+198h+var_138]
0x140024698  mov     qword ptr [rsp+198h+Buf2+8], rax
0x1400246a0  lea     rax, qword_140096A98
0x1400246a7  mov     [rsp+198h+var_110], rax
0x1400246af  lock inc cs:qword_140096A98
0x1400246b7  cmp     cs:??$factory_cache_entry_v@UJsonObject@Json@Data@Windows@winrt@@UIJsonObjectStatics@2345@@impl@winrt@@3U?$factory_cache_entry@UJsonObject@Json@Data@Windows@winrt@@UIJsonObjectStatics@2345@@12@A, rbx; factory_cache_entry<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Data::Json::IJsonObjectStatics>::winrt::factory_cache_entry<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Data::Json::IJsonObjectStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Data::Json::IJsonObjectStatics>
0x1400246be  jz      short loc_1400246DF
0x1400246c0  lea     rdx, ??$factory_cache_entry_v@UJsonObject@Json@Data@Windows@winrt@@UIJsonObjectStatics@2345@@impl@winrt@@3U?$factory_cache_entry@UJsonObject@Json@Data@Windows@winrt@@UIJsonObjectStatics@2345@@12@A; factory_cache_entry<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Data::Json::IJsonObjectStatics>::winrt::factory_cache_entry<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Data::Json::IJsonObjectStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Data::Json::IJsonObjectStatics>
0x1400246c7  lea     rcx, [rsp+198h+Buf2]
0x1400246cf  call    ??R_lambda_1_@?1??TryParse@JsonObject@Json@Data@Windows@winrt@@SA@AEBUhstring@param@6@AEAU23456@@Z@QEBA@AEBUIJsonObjectStatics@3456@@Z; `winrt::Windows::Data::Json::JsonObject::TryParse(winrt::param::hstring const &,winrt::Windows::Data::Json::JsonObject &)'::`2'::_lambda_1_::operator()(winrt::Windows::Data::Json::IJsonObjectStatics const &)
0x1400246d4  nop
0x1400246d5  lock dec cs:qword_140096A98
0x1400246dd  jmp     short loc_1400246F4
0x1400246df  lock dec cs:qword_140096A98
0x1400246e7  lea     rdx, [rsp+198h+Buf2]
0x1400246ef  call    ??$call@AEAV_lambda_1_@?1??TryParse@JsonObject@Json@Data@Windows@winrt@@SA@AEBUhstring@param@7@AEAU34567@@Z@@?$factory_cache_entry@UJsonObject@Json@Data@Windows@winrt@@UIJsonObjectStatics@2345@@impl@winrt@@QEAA?A_PAEAV_lambda_1_@?1??TryParse@JsonObject@Json@Data@Windows@2@SA@AEBUhstring@param@2@AEAU56782@@Z@@Z
0x1400246f4  test    al, al
0x1400246f6  jnz     loc_140024796
0x1400246fc  call    ?Instance@MidiSrvTelemetryProvider@@KAPEAV1@XZ; MidiSrvTelemetryProvider::Instance(void)
0x140024701  mov     rcx, [rax+8]
0x140024705  mov     eax, [rcx]
0x140024707  cmp     eax, 2
0x14002470a  jbe     short loc_140024770
0x14002470c  cmp     qword ptr [rdi+18h], 7
0x140024711  jbe     short loc_140024718
0x140024713  mov     rax, [rdi]
0x140024716  jmp     short loc_14002471B
0x140024718  mov     rax, rdi
0x14002471b  mov     [rsp+198h+var_148], rax
0x140024720  lea     rax, aJsonObjectPars; "JSON Object parsing failed"
0x140024727  mov     [rsp+198h+var_150], rax
0x14002472c  mov     [rsp+198h+var_128], r13
0x140024731  mov     [rsp+198h+var_D8], r12
0x140024739  lea     rax, [rsp+198h+var_148]
0x14002473e  mov     [rsp+198h+var_160], rax
0x140024743  lea     rax, [rsp+198h+var_150]
0x140024748  mov     [rsp+198h+var_168], rax
0x14002474d  lea     rax, [rsp+198h+var_128]
0x140024752  mov     [rsp+198h+var_170], rax
0x140024757  lea     rax, [rsp+198h+var_D8]
0x14002475f  mov     [rsp+198h+var_178], rax
0x140024764  lea     rdx, dword_140088664
0x14002476b  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x140024770  mov     [rsp+198h+var_154], ebx
0x140024774  cmp     [rsp+198h+var_138], rbx
0x140024779  jz      short loc_140024786
0x14002477b  lea     rcx, [rsp+198h+var_138]
0x140024780  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x140024785  nop
0x140024786  mov     rcx, rdi; void *
0x140024789  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14002478e  mov     rax, r15
0x140024791  jmp     loc_140024FC8
0x140024796  mov     [rsp+198h+var_148], rbx
0x14002479b  lea     rdx, [rsp+198h+var_148]
0x1400247a0  lea     rcx, [rsp+198h+var_138]
0x1400247a5  call    ??8Foundation@Windows@winrt@@YA_NAEBUIUnknown@012@0@Z; winrt::Windows::Foundation::operator==(winrt::Windows::Foundation::IUnknown const &,winrt::Windows::Foundation::IUnknown const &)
0x1400247aa  test    al, al
0x1400247ac  jz      short loc_140024824
0x1400247ae  call    ?Instance@MidiSrvTelemetryProvider@@KAPEAV1@XZ; MidiSrvTelemetryProvider::Instance(void)
0x1400247b3  mov     rcx, [rax+8]
0x1400247b7  mov     eax, [rcx]
0x1400247b9  cmp     eax, 2
0x1400247bc  jbe     short loc_1400247FE
0x1400247be  lea     rax, aJsonObjectNull; "JSON Object null after parsing"
0x1400247c5  mov     [rsp+198h+var_148], rax
0x1400247ca  mov     [rsp+198h+var_150], r13
0x1400247cf  mov     [rsp+198h+var_128], r12
0x1400247d4  lea     rax, [rsp+198h+var_148]
0x1400247d9  mov     [rsp+198h+var_168], rax
0x1400247de  lea     rax, [rsp+198h+var_150]
0x1400247e3  mov     [rsp+198h+var_170], rax
0x1400247e8  lea     rax, [rsp+198h+var_128]
0x1400247ed  mov     [rsp+198h+var_178], rax
0x1400247f2  lea     rdx, byte_140088631
0x1400247f9  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &)
0x1400247fe  mov     [rsp+198h+var_154], ebx
0x140024802  cmp     [rsp+198h+var_138], rbx
0x140024807  jz      short loc_140024814
0x140024809  lea     rcx, [rsp+198h+var_138]
0x14002480e  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x140024813  nop
0x140024814  mov     rcx, rdi; void *
0x140024817  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14002481c  mov     rax, r15
0x14002481f  jmp     loc_140024FC8
0x140024824  mov     [rsp+198h+var_148], rbx
0x140024829  mov     dword ptr [rsp+198h+var_90+8], 1
0x140024834  mov     dword ptr [rsp+198h+var_90+0Ch], 1Fh
0x14002483f  lea     rax, aEndpointtransp; "endpointTransportPluginSettings"
0x140024846  mov     [rsp+198h+var_78], rax
0x14002484e  lea     rax, [rsp+198h+var_90+8]
0x140024856  mov     qword ptr [rsp+198h+var_90], rax
0x14002485e  lea     r9, [rsp+198h+var_148]
0x140024863  lea     r8, [rsp+198h+var_90]
0x14002486b  lea     rdx, [rsp+198h+var_118]
0x140024873  lea     rcx, [rsp+198h+var_138]
0x140024878  call    ?GetNamedObject@?$consume_Windows_Data_Json_IJsonObjectWithDefaultValues@UJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@AEBUJsonObject@Json@Data@Windows@3@@Z; winrt::impl::consume_Windows_Data_Json_IJsonObjectWithDefaultValues<winrt::Windows::Data::Json::JsonObject>::GetNamedObject(winrt::param::hstring const &,winrt::Windows::Data::Json::JsonObject const &)
0x14002487d  nop
0x14002487e  mov     [rsp+198h+var_148], rbx
0x140024883  lea     rdx, [rsp+198h+var_148]
0x140024888  lea     rcx, [rsp+198h+var_118]
0x140024890  call    ??8Foundation@Windows@winrt@@YA_NAEBUIUnknown@012@0@Z; winrt::Windows::Foundation::operator==(winrt::Windows::Foundation::IUnknown const &,winrt::Windows::Foundation::IUnknown const &)
0x140024895  test    al, al
0x140024897  jz      loc_14002492B
0x14002489d  call    ?Instance@MidiSrvTelemetryProvider@@KAPEAV1@XZ; MidiSrvTelemetryProvider::Instance(void)
0x1400248a2  mov     rcx, [rax+8]
0x1400248a6  mov     eax, [rcx]
0x1400248a8  cmp     eax, 2
0x1400248ab  jbe     short loc_1400248ED
0x1400248ad  lea     rax, aNoTransportPlu; "No transport plugins node in JSON"
0x1400248b4  mov     [rsp+198h+var_148], rax
0x1400248b9  mov     [rsp+198h+var_150], r13
0x1400248be  mov     [rsp+198h+var_128], r12
0x1400248c3  lea     rax, [rsp+198h+var_148]
0x1400248c8  mov     [rsp+198h+var_168], rax
0x1400248cd  lea     rax, [rsp+198h+var_150]
0x1400248d2  mov     [rsp+198h+var_170], rax
0x1400248d7  lea     rax, [rsp+198h+var_128]
0x1400248dc  mov     [rsp+198h+var_178], rax
0x1400248e1  lea     rdx, byte_1400889A1
0x1400248e8  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &)
0x1400248ed  mov     [rsp+198h+var_154], ebx
0x1400248f1  cmp     [rsp+198h+var_118], rbx
0x1400248f9  jz      short loc_140024909
0x1400248fb  lea     rcx, [rsp+198h+var_118]
0x140024903  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x140024908  nop
0x140024909  cmp     [rsp+198h+var_138], rbx
0x14002490e  jz      short loc_14002491B
0x140024910  lea     rcx, [rsp+198h+var_138]
0x140024915  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x14002491a  nop
0x14002491b  mov     rcx, rdi; void *
0x14002491e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140024923  mov     rax, r15
0x140024926  jmp     loc_140024FC8
0x14002492b  lea     rdx, [rsp+198h+var_120]
0x140024930  lea     rcx, [rsp+198h+var_118]
0x140024938  call    ?First@?$consume_Windows_Foundation_Collections_IIterable@UJsonObject@Json@Data@Windows@winrt@@U?$IKeyValuePair@Uhstring@winrt@@UIJsonValue@Json@Data@Windows@2@@Collections@Foundation@45@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_Collections_IIterable<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::hstring,winrt::Windows::Data::Json::IJsonValue>>::First(void)
0x14002493d  nop
0x14002493e  lea     rsi, aOnecoreuapInte_1; "onecoreuap\\Internal\\BuildMetadata\\in"...
0x140024945  mov     [rsp+198h+var_158], bl
0x140024949  mov     rcx, [rsp+198h+var_120]
0x14002494e  mov     [rsp+198h+var_108], 40h ; '@'
0x140024959  mov     [rsp+198h+var_100], rsi
0x140024961  mov     [rsp+198h+var_F8], rbx
0x140024969  mov     rax, [rcx]
0x14002496c  lea     rdx, [rsp+198h+var_158]
0x140024971  mov     rax, [rax+38h]
0x140024975  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002497a  test    eax, eax
0x14002497c  js      loc_140024FEB
0x140024982  cmp     [rsp+198h+var_158], bl
0x140024986  jz      loc_140024F44
0x14002498c  lea     rdx, [rsp+198h+var_D8]
0x140024994  lea     rcx, [rsp+198h+var_120]
0x140024999  call    ?Current@?$consume_Windows_Foundation_Collections_IIterator@U?$IIterator@U?$IKeyValuePair@Uhstring@winrt@@UIJsonValue@Json@Data@Windows@2@@Collections@Foundation@Windows@winrt@@@Collections@Foundation@Windows@winrt@@U?$IKeyValuePair@Uhstring@winrt@@UIJsonValue@Json@Data@Windows@2@@2345@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_Collections_IIterator<winrt::Windows::Foundation::Collections::IIterator<winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::hstring,winrt::Windows::Data::Json::IJsonValue>>,winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::hstring,winrt::Windows::Data::Json::IJsonValue>>::Current(void)
0x14002499e  nop
0x14002499f  mov     [rsp+198h+lpMem], rbx
0x1400249a7  or      r14d, 2
0x1400249ab  mov     [rsp+198h+var_154], r14d
0x1400249b0  mov     rcx, [rax]
0x1400249b3  mov     [rsp+198h+var_108], 76h ; 'v'
0x1400249be  mov     [rsp+198h+var_100], rsi
0x1400249c6  mov     [rsp+198h+var_F8], rbx
0x1400249ce  mov     rax, [rcx]
0x1400249d1  lea     rdx, [rsp+198h+lpMem]
0x1400249d9  mov     rax, [rax+30h]
0x1400249dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400249e2  test    eax, eax
0x1400249e4  js      loc_140024FFB
0x1400249ea  mov     rax, [rsp+198h+lpMem]
0x1400249f2  test    rax, rax
0x1400249f5  jz      short loc_1400249FD
0x1400249f7  mov     rdx, [rax+10h]
0x1400249fb  jmp     short loc_140024A04
0x1400249fd  lea     rdx, S2
0x140024a04  xorps   xmm0, xmm0
0x140024a07  movups  [rsp+198h+var_60], xmm0
0x140024a0f  mov     [rsp+198h+var_50], rbx
0x140024a17  mov     [rsp+198h+var_48], rbx
0x140024a1f  or      r8, 0FFFFFFFFFFFFFFFFh
0x140024a23  inc     r8
0x140024a26  cmp     [rdx+r8*2], bx
0x140024a2b  jnz     short loc_140024A23
0x140024a2d  lea     rcx, [rsp+198h+var_60]
0x140024a35  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x140024a3a  nop
0x140024a3b  and     r14d, 0FFFFFFFDh
0x140024a3f  mov     [rsp+198h+var_154], r14d
0x140024a44  mov     rsi, [rsp+198h+lpMem]
0x140024a4c  test    rsi, rsi
0x140024a4f  jz      short loc_140024A7D
0x140024a51  or      eax, 0FFFFFFFFh
0x140024a54  lock xadd [rsi+18h], eax
0x140024a59  sub     eax, 1
0x140024a5c  jnz     loc_140024B5B
0x140024a62  nop
0x140024a63  call    WINRT_IMPL_GetProcessHeap
0x140024a68  mov     rcx, rax; hHeap
0x140024a6b  mov     r8, rsi; lpMem
0x140024a6e  xor     edx, edx; dwFlags
0x140024a70  call    WINRT_IMPL_HeapFree
0x140024a75  mov     [rsp+198h+lpMem], rbx
0x140024a7d  cmp     [rsp+198h+var_D8], rbx
0x140024a85  jz      short loc_140024A94
0x140024a87  lea     rcx, [rsp+198h+var_D8]
0x140024a8f  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x140024a94  call    ?Instance@MidiSrvTelemetryProvider@@KAPEAV1@XZ; MidiSrvTelemetryProvider::Instance(void)
0x140024a99  mov     rcx, [rax+8]
0x140024a9d  mov     eax, [rcx]
0x140024a9f  cmp     eax, 4
0x140024aa2  jbe     short loc_140024AF7
0x140024aa4  lea     rax, [rsp+198h+var_60]
0x140024aac  cmp     [rsp+198h+var_48], 7
0x140024ab5  cmova   rax, qword ptr [rsp+198h+var_60]
0x140024abe  mov     [rsp+198h+var_150], rax
0x140024ac3  mov     [rsp+198h+var_140], r13
0x140024ac8  mov     [rsp+198h+var_130], r12
0x140024acd  lea     rax, [rsp+198h+var_150]
0x140024ad2  mov     [rsp+198h+var_168], rax
0x140024ad7  lea     rax, [rsp+198h+var_140]
0x140024adc  mov     [rsp+198h+var_170], rax
0x140024ae1  lea     rax, [rsp+198h+var_130]
0x140024ae6  mov     [rsp+198h+var_178], rax
0x140024aeb  lea     rdx, dword_1400886D4
0x140024af2  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &)
0x140024af7  lea     rdx, [rsp+198h+var_148]
0x140024afc  lea     rcx, [rsp+198h+var_120]
  ... truncated ...
```
