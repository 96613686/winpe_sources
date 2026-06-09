# CMidi2KSMidiConfigurationManager::UpdateConfiguration(ushort const *,ushort * *)

- ea: `0x180023ac0`
- end: `0x18002494b`
- name: `?UpdateConfiguration@CMidi2KSMidiConfigurationManager@@UEAAJPEBGPEAPEAG@Z`
- size: `3723`
- prototype: `int(CMidi2KSMidiConfigurationManager *__hidden this, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `33`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x1800016dc`
- `0x180001c20`
- `0x1800021ec`
- `0x1800052fc`
- `0x180005374`
- `0x18000a814`
- `0x18000cdcc`
- `0x18000d1c0`
- `0x18000db18`
- `0x180011240`
- `0x1800112b0`
- `0x180014864`
- `0x180017e18`
- `0x180018098`
- `0x180018e84`
- `0x18001fdb0`
- `0x180020f0c`
- `0x180021c3c`
- `0x180021e4c`
- `0x180021f58`
- `0x180021ff4`
- `0x180022080`
- `0x1800221e8`
- `0x180022330`
- `0x180022550`
- `0x1800227c4`
- `0x180022e38`
- `0x1800230a0`
- `0x1800237f4`
- `0x180023930`
- `0x180023ac0`
- `0x18002c4a4`
- `0x180041010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800240be`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800240cd`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180024290`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180024919`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800240be`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800240cd`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180024290`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180024919`

## string_xrefs

- `0x180023e29`: `transportCommand`
- `0x180023b09`: `avcore\midi2\transport\kstransport\midi2.ksmidiconfigurationmanager.cpp`
- `0x18002435f`: `avcore\midi2\transport\kstransport\midi2.ksmidiconfigurationmanager.cpp`
- `0x180024658`: `avcore\midi2\transport\kstransport\midi2.ksmidiconfigurationmanager.cpp`
- `0x180023b77`: `CMidi2KSMidiConfigurationManager::UpdateConfiguration`
- `0x180023bdf`: `CMidi2KSMidiConfigurationManager::UpdateConfiguration`
- `0x180023c1a`: `CMidi2KSMidiConfigurationManager::UpdateConfiguration`
- `0x180023d5a`: `Failed to parse Configuration JSON`
- `0x180023f2a`: `update`
- `0x18002452e`: `Properties updated`

## pseudocode

```c
// Hidden C++ exception states: #wind=28
__int64 __fastcall CMidi2KSMidiConfigurationManager::UpdateConfiguration(
        CMidi2KSMidiConfigurationManager *this,
        unsigned __int16 *a2,
        unsigned __int16 **a3)
{
  const struct winrt::Windows::Data::Json::JsonObject *v3; // r15
  __int64 v6; // rdx
  __int64 result; // rax
  __int64 v8; // rax
  _DWORD *v9; // rcx
  int v10; // r8d
  int v11; // r9d
  _DWORD *v12; // rcx
  int v13; // r8d
  int v14; // r9d
  struct winrt::impl::hstring_header *v15; // rdx
  __int64 v16; // rcx
  volatile signed __int32 *v17; // rsi
  char v18; // r14
  int v19; // eax
  HANDLE ProcessHeap; // rax
  void *v21; // rsi
  int v22; // eax
  HANDLE v23; // rax
  _DWORD *v24; // rcx
  int v25; // r8d
  int v26; // r9d
  __int64 NamedObject; // rax
  CMidi2KSMidiConfigurationManager *v28; // rcx
  char v29; // bl
  unsigned int v30; // ebx
  unsigned __int16 **v31; // r8
  unsigned __int16 **v32; // r8
  bool v33; // zf
  char v34; // al
  int v35; // r15d
  int v36; // eax
  winrt::impl *v37; // rbx
  struct winrt::impl::hstring_header *v38; // rdx
  LPVOID *v39; // rsi
  __int64 MatchingInstantiatedEndpoint; // rax
  void *v41; // rbx
  int v42; // eax
  HANDLE v43; // rax
  int v44; // eax
  int v45; // eax
  HANDLE v46; // rax
  volatile signed __int32 *v47; // rbx
  volatile signed __int32 *v48; // rbx
  volatile signed __int32 *v49; // rbx
  int v50; // r14d
  _DWORD *v51; // r8
  int v52; // r9d
  const wchar_t *v53; // rax
  _DWORD *v54; // r8
  int v55; // r9d
  const wchar_t *v56; // rax
  int v57; // eax
  HANDLE v58; // rax
  volatile signed __int32 *v59; // rbx
  volatile signed __int32 *v60; // rbx
  volatile signed __int32 *v61; // rbx
  int v62; // eax
  HANDLE v63; // rax
  volatile signed __int32 *v64; // rbx
  volatile signed __int32 *v65; // rbx
  _DWORD *v66; // rbx
  int v67; // r8d
  int v68; // r9d
  _DWORD *v69; // rcx
  int v70; // r8d
  int v71; // r9d
  int v72; // [rsp+20h] [rbp-198h]
  int v73; // [rsp+20h] [rbp-198h]
  __int64 v74; // [rsp+38h] [rbp-180h]
  const char *v75; // [rsp+50h] [rbp-168h] BYREF
  __int64 v76; // [rsp+58h] [rbp-160h] BYREF
  int v77[2]; // [rsp+60h] [rbp-158h] BYREF
  const char *v78; // [rsp+68h] [rbp-150h] BYREF
  void *v79; // [rsp+70h] [rbp-148h] BYREF
  __int64 v80; // [rsp+78h] [rbp-140h] BYREF
  LPVOID *p_lpMem; // [rsp+80h] [rbp-138h] BYREF
  __int64 v82; // [rsp+88h] [rbp-130h] BYREF
  __int64 v83; // [rsp+90h] [rbp-128h] BYREF
  __int64 *v84; // [rsp+98h] [rbp-120h] BYREF
  winrt::impl *v85; // [rsp+A0h] [rbp-118h] BYREF
  const char **v86; // [rsp+A8h] [rbp-110h] BYREF
  LPVOID v87[2]; // [rsp+B0h] [rbp-108h] BYREF
  __int128 v88; // [rsp+C0h] [rbp-F8h] BYREF
  __int128 v89; // [rsp+D0h] [rbp-E8h] BYREF
  __int64 v90; // [rsp+E0h] [rbp-D8h]
  const wchar_t *v91; // [rsp+E8h] [rbp-D0h]
  int *v92; // [rsp+F0h] [rbp-C8h] BYREF
  int v93; // [rsp+F8h] [rbp-C0h] BYREF
  int v94; // [rsp+FCh] [rbp-BCh]
  const wchar_t *v95; // [rsp+108h] [rbp-B0h]
  int v96[4]; // [rsp+110h] [rbp-A8h] BYREF
  __int128 v97; // [rsp+130h] [rbp-88h] BYREF
  __int128 v98; // [rsp+140h] [rbp-78h] BYREF
  __int64 *v99; // [rsp+150h] [rbp-68h] BYREF
  int v100; // [rsp+158h] [rbp-60h]
  __int128 *v101; // [rsp+160h] [rbp-58h]
  const std::exception *v102; // [rsp+170h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1B8h] [rbp+0h]
  unsigned __int16 *v105; // [rsp+1C8h] [rbp+10h] BYREF
  unsigned __int16 **v106; // [rsp+1D0h] [rbp+18h]
  LPVOID lpMem; // [rsp+1D8h] [rbp+20h] BYREF

  v106 = a3;
  v105 = a2;
  v3 = (const struct winrt::Windows::Data::Json::JsonObject *)a3;
  LODWORD(lpMem) = 0;
  if ( !a2 )
  {
    v6 = 175;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"avcore\\midi2\\transport\\kstransport\\midi2.ksmidiconfigurationmanager.cpp",
      (const char *)0x80070057LL,
      v72);
    return 2147942487LL;
  }
  if ( !a3 )
  {
    v6 = 176;
    goto LABEL_3;
  }
  v8 = -1;
  do
    ++v8;
  while ( a2[v8] );
  if ( !v8 )
  {
    v6 = 177;
    goto LABEL_3;
  }
  if ( !*((_QWORD *)this + 5) )
  {
    v9 = (_DWORD *)*((_QWORD *)MidiKSTransportTelemetryProvider::Instance() + 1);
    if ( *v9 > 2u )
    {
      v105 = a2;
      lpMem = L"Device Manager is nullptr";
      *(_QWORD *)v77 = this;
      v75 = "CMidi2KSMidiConfigurationManager::UpdateConfiguration";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
        (_DWORD)v9,
        (unsigned int)byte_180068DF1,
        v10,
        v11,
        (__int64)&v75,
        (__int64)v77,
        (__int64)&lpMem,
        (__int64)&v105);
    }
    return 2147500037LL;
  }
  v12 = (_DWORD *)*((_QWORD *)MidiKSTransportTelemetryProvider::Instance() + 1);
  if ( *v12 > 4u )
  {
    lpMem = a2;
    *(_QWORD *)v77 = this;
    v75 = "CMidi2KSMidiConfigurationManager::UpdateConfiguration";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>>(
      (_DWORD)v12,
      (unsigned int)word_180068DC2,
      v13,
      v14,
      (__int64)&v75,
      (__int64)v77,
      (__int64)&lpMem);
  }
  WindowsMidiServicesInternal::BuildConfigurationResponseObject(&v76);
  try
  {
    winrt::Windows::Data::Json::JsonObject::JsonObject((winrt::Windows::Data::Json::JsonObject *)&v79);
    winrt::hstring::hstring((winrt::hstring *)&lpMem, a2);
    v17 = (volatile signed __int32 *)winrt::impl::duplicate_hstring((winrt::impl *)lpMem, v15);
    p_lpMem = (LPVOID *)v17;
    v92 = (int *)v17;
    *(_QWORD *)v96 = &v92;
    *(_QWORD *)&v96[2] = &v79;
    v84 = &qword_180071CC8;
    _InterlockedIncrement64(&qword_180071CC8);
    if ( winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Data::Json::IJsonObjectStatics> )
    {
      v18 = `winrt::Windows::Data::Json::JsonObject::TryParse'::`2'::_lambda_1_::operator()(
              v96,
              &winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Data::Json::IJsonObjectStatics>);
      _InterlockedDecrement64(&qword_180071CC8);
    }
    else
    {
      _InterlockedDecrement64(&qword_180071CC8);
      v18 = ___call_AEAV_lambda_1___1__TryParse_JsonObject_Json_Data_Windows_winrt__SA_AEBUhstring_param_7_AEAU34567__Z____factory_cache_entry_UJsonObject_Json_Data_Windows_winrt__UIJsonObjectStatics_2345__impl_winrt__QEAA_A_PAEAV_lambda_1___1__TryParse_JsonObject_Json_Data_Windows_2_SA_AEBUhstring_param_2_AEAU56782__Z__Z(
              v16,
              v96);
    }
    if ( v17 )
    {
      v19 = _InterlockedDecrement(v17 + 6);
      if ( v19 )
      {
        if ( v19 < 0 )
          abort();
      }
      else
      {
        ProcessHeap = WINRT_IMPL_GetProcessHeap();
        WINRT_IMPL_HeapFree(ProcessHeap, 0, (LPVOID)v17);
      }
    }
    v21 = lpMem;
    if ( lpMem )
    {
      v22 = _InterlockedDecrement((volatile signed __int32 *)lpMem + 6);
      if ( v22 )
      {
        if ( v22 < 0 )
          abort();
      }
      else
      {
        v23 = WINRT_IMPL_GetProcessHeap();
        WINRT_IMPL_HeapFree(v23, 0, v21);
      }
    }
    if ( !v18 )
    {
      v24 = (_DWORD *)*((_QWORD *)MidiKSTransportTelemetryProvider::Instance() + 1);
      if ( *v24 > 2u )
      {
        lpMem = a2;
        *(_QWORD *)v77 = L"Failed to parse Configuration JSON";
        v75 = (const char *)this;
        v87[0] = "CMidi2KSMidiConfigurationManager::UpdateConfiguration";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
          (_DWORD)v24,
          (unsigned int)byte_180068D89,
          v25,
          v26,
          (__int64)v87,
          (__int64)&v75,
          (__int64)v77,
          (__int64)&lpMem);
      }
      if ( v79 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v79);
      if ( v76 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v76);
      return 2147942487LL;
    }
    lpMem = v79;
    if ( v79 )
      (*(void (__fastcall **)(void *))(*(_QWORD *)v79 + 8LL))(v79);
    p_lpMem = &lpMem;
    v75 = 0;
    *(_QWORD *)v77 = 0;
    *((_QWORD *)&v89 + 1) = 0x1000000001LL;
    v91 = L"transportCommand";
    *(_QWORD *)&v89 = (char *)&v89 + 8;
    NamedObject = winrt::impl::consume_Windows_Data_Json_IJsonObjectWithDefaultValues<winrt::Windows::Data::Json::JsonObject>::GetNamedObject(
                    &lpMem,
                    &v85,
                    &v89,
                    v77);
    v29 = winrt::Windows::Foundation::operator==(NamedObject, &v75);
    if ( v85 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v85);
    if ( !v29 )
    {
      if ( lpMem )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&lpMem);
      v30 = CMidi2KSMidiConfigurationManager::ProcessCommand(
              v28,
              (const struct winrt::Windows::Data::Json::JsonObject *)&v79,
              (struct winrt::Windows::Data::Json::JsonObject *)&v76);
      WindowsMidiServicesInternal::JsonStringifyObjectToOutParam((WindowsMidiServicesInternal *)&v76, v3, v31);
      if ( v79 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v79);
      if ( v76 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v76);
      return v30;
    }
    if ( lpMem )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&lpMem);
    lpMem = 0;
    v93 = 1;
    v94 = 6;
    v95 = L"update";
    v92 = &v93;
    winrt::impl::consume_Windows_Data_Json_IJsonObjectWithDefaultValues<winrt::Windows::Data::Json::JsonObject>::GetNamedArray(
      &v79,
      &v83,
      &v92,
      &lpMem);
    *(_QWORD *)v77 = 0;
    LODWORD(lpMem) = 1;
    if ( (unsigned __int8)winrt::Windows::Foundation::operator==(&v83, v77)
      || (v33 = (unsigned int)winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Data::Json::JsonArray,winrt::Windows::Data::Json::IJsonValue>::Size(&v83) == 0,
          v34 = 1,
          v33) )
    {
      v34 = 0;
    }
    if ( !v34 )
    {
LABEL_56:
      if ( v83 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v83);
      if ( v79 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v79);
      WindowsMidiServicesInternal::JsonStringifyObjectToOutParam((WindowsMidiServicesInternal *)&v76, v3, v32);
      if ( v76 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v76);
      return 0;
    }
    v99 = &v83;
    v35 = 0;
    v100 = 0;
    v36 = winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Data::Json::JsonArray,winrt::Windows::Data::Json::IJsonValue>::Size(&v83);
    LODWORD(lpMem) = v36;
    while ( 1 )
    {
      if ( v35 == v36 )
      {
        winrt::Windows::Data::Json::JsonValue::CreateBooleanValue((bool)&lpMem);
        v93 = 1;
        v94 = 7;
        v95 = L"success";
        v92 = &v93;
        winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(
          &v76,
          &v92,
          &lpMem);
        if ( lpMem )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&lpMem);
        v3 = (const struct winrt::Windows::Data::Json::JsonObject *)v106;
        goto LABEL_56;
      }
      winrt::impl::fast_iterator<winrt::Windows::Data::Json::JsonArray>::operator*(&v99, &v82);
      winrt::impl::consume_Windows_Data_Json_IJsonValue<winrt::Windows::Data::Json::IJsonValue>::GetObject(&v82, &v78);
      v75 = 0;
      if ( !(unsigned __int8)winrt::Windows::Foundation::operator==(&v78, &v75) )
        break;
LABEL_71:
      if ( v78 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v78);
      if ( v82 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v82);
      v100 = ++v35;
      v36 = (int)lpMem;
    }
    v75 = 0;
    *(_QWORD *)v96 = WindowsMidiServicesPluginConfigurationLib::MidiEndpointMatchCriteria::PropertyKey;
    winrt::impl::consume_Windows_Data_Json_IJsonObjectWithDefaultValues<winrt::Windows::Data::Json::JsonObject>::GetNamedObject(
      &v78,
      &v80,
      v96,
      &v75);
    v75 = 0;
    if ( !(unsigned __int8)winrt::Windows::Foundation::operator==(&v80, &v75) )
    {
      *(_OWORD *)v96 = 0;
      v97 = 0;
      WindowsMidiServicesPluginConfigurationLib::MidiEndpointMatchCriteria::FromJson(&v88, &v80);
      v89 = 0;
      v90 = 0;
      v37 = 0;
      v85 = 0;
      v39 = *(LPVOID **)TransportState::Current();
      p_lpMem = v39;
      if ( v39 )
      {
        (*((void (__fastcall **)(LPVOID *))*v39 + 1))(v39);
        MatchingInstantiatedEndpoint = CMidi2KSMidiEndpointManager::FindMatchingInstantiatedEndpoint(v39, v87, v88);
        winrt::hstring::operator=(&v85, MatchingInstantiatedEndpoint);
        v41 = v87[0];
        if ( v87[0] )
        {
          v42 = _InterlockedDecrement((volatile signed __int32 *)v87[0] + 6);
          if ( v42 )
          {
            if ( v42 < 0 )
              abort();
          }
          else
          {
            v43 = WINRT_IMPL_GetProcessHeap();
            WINRT_IMPL_HeapFree(v43, 0, v41);
          }
          v87[0] = 0;
        }
        v37 = v85;
      }
      v86 = &v75;
      v75 = v78;
      if ( v78 )
        (*(void (__fastcall **)(const char *))(*(_QWORD *)v78 + 8LL))(v78);
      v101 = &v98;
      v98 = 0;
      if ( *((_QWORD *)&v88 + 1) )
        _InterlockedIncrement((volatile signed __int32 *)(*((_QWORD *)&v88 + 1) + 8LL));
      v98 = v88;
      *(_QWORD *)v77 = winrt::impl::duplicate_hstring(v37, v38);
      v44 = CMidi2KSMidiConfigurationManager::ProcessCustomProperties(
              (_DWORD)this,
              (unsigned int)v77,
              (unsigned int)&v98,
              (unsigned int)&v75,
              (__int64)v96,
              (__int64)&v89,
              (__int64)&v97,
              v74);
      if ( v44 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x119,
          (unsigned int)"avcore\\midi2\\transport\\kstransport\\midi2.ksmidiconfigurationmanager.cpp",
          (const char *)(unsigned int)v44,
          v73);
      if ( 0xAAAAAAAAAAAAAAABuLL * ((__int64)(*((_QWORD *)&v89 + 1) - v89) >> 4) )
      {
        if ( v37 )
        {
          v50 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 5) + 48LL))(
                  *((_QWORD *)this + 5),
                  *((_QWORD *)v37 + 2));
          if ( v50 < 0 )
          {
            if ( v50 != -2147023728 )
            {
              v54 = (_DWORD *)*((_QWORD *)MidiKSTransportTelemetryProvider::Instance() + 1);
              if ( *v54 > 2u )
              {
                if ( *(_QWORD *)v88 )
                  v56 = *(const wchar_t **)(*(_QWORD *)v88 + 16LL);
                else
                  v56 = &S1;
                p_lpMem = (LPVOID *)v56;
                LODWORD(lpMem) = v50;
                v84 = (__int64 *)L"Error updating device properties";
                v86 = (const char **)this;
                *(_QWORD *)v77 = "CMidi2KSMidiConfigurationManager::UpdateConfiguration";
                _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
                  (_DWORD)v54,
                  (unsigned int)qword_180068D10,
                  (_DWORD)v54,
                  v55,
                  (__int64)v77,
                  (__int64)&v86,
                  (__int64)&v84,
                  (__int64)&lpMem,
                  (__int64)&p_lpMem);
              }
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x149,
                (unsigned int)"avcore\\midi2\\transport\\kstransport\\midi2.ksmidiconfigurationmanager.cpp",
                (const char *)0x80004005LL,
                v73);
              if ( v39 )
                (*((void (__fastcall **)(LPVOID *))*v39 + 2))(v39);
              v57 = _InterlockedDecrement((volatile signed __int32 *)v37 + 6);
              if ( v57 )
              {
                if ( v57 < 0 )
LABEL_169:
                  abort();
              }
              else
              {
                v58 = WINRT_IMPL_GetProcessHeap();
                WINRT_IMPL_HeapFree(v58, 0, v37);
              }
              std::vector<_DEVPROPERTY>::~vector<_DEVPROPERTY>(&v89);
              v59 = (volatile signed __int32 *)*((_QWORD *)&v88 + 1);
              if ( *((_QWORD *)&v88 + 1) )
              {
                if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v88 + 1) + 8LL), 0xFFFFFFFF) == 1 )
                {
                  (**(void (__fastcall ***)(volatile signed __int32 *))v59)(v59);
                  if ( _InterlockedExchangeAdd(v59 + 3, 0xFFFFFFFF) == 1 )
                    (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v59 + 8LL))(v59);
                }
              }
              v60 = (volatile signed __int32 *)*((_QWORD *)&v97 + 1);
              if ( *((_QWORD *)&v97 + 1) )
              {
                if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v97 + 1) + 8LL), 0xFFFFFFFF) == 1 )
                {
                  (**(void (__fastcall ***)(volatile signed __int32 *))v60)(v60);
                  if ( _InterlockedExchangeAdd(v60 + 3, 0xFFFFFFFF) == 1 )
                    (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v60 + 8LL))(v60);
                }
              }
              v61 = *(volatile signed __int32 **)&v96[2];
              if ( *(_QWORD *)&v96[2] )
              {
                if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*(_QWORD *)&v96[2] + 8LL), 0xFFFFFFFF) == 1 )
                {
                  (**(void (__fastcall ***)(volatile signed __int32 *))v61)(v61);
                  if ( _InterlockedExchangeAdd(v61 + 3, 0xFFFFFFFF) == 1 )
                    (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v61 + 8LL))(v61);
                }
              }
              if ( v80 )
                winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v80);
              if ( v78 )
                winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v78);
              if ( v82 )
                winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v82);
              if ( v83 )
                winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v83);
              if ( v79 )
                winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v79);
              if ( v76 )
                winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v76);
              return 2147500037LL;
            }
          }
          else
          {
            v51 = (_DWORD *)*((_QWORD *)MidiKSTransportTelemetryProvider::Instance() + 1);
            if ( *v51 > 4u )
            {
              if ( *(_QWORD *)v88 )
                v53 = *(const wchar_t **)(*(_QWORD *)v88 + 16LL);
              else
                v53 = &S1;
              v75 = (const char *)v53;
              v86 = (const char **)L"Properties updated";
              v84 = (__int64 *)this;
              p_lpMem = (LPVOID *)"CMidi2KSMidiConfigurationManager::UpdateConfiguration";
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
                (_DWORD)v51,
                (unsigned int)word_180068D52,
                (_DWORD)v51,
                v52,
                (__int64)&p_lpMem,
                (__int64)&v84,
                (__int64)&v86,
                (__int64)&v75);
            }
          }
        }
        if ( v39 )
          (*((void (__fastcall **)(LPVOID *))*v39 + 2))(v39);
        if ( v37 )
        {
          v62 = _InterlockedDecrement((volatile signed __int32 *)v37 + 6);
          if ( v62 )
          {
            if ( v62 < 0 )
              goto LABEL_169;
          }
          else
          {
            v63 = WINRT_IMPL_GetProcessHeap();
            WINRT_IMPL_HeapFree(v63, 0, v37);
          }
        }
        std::vector<_DEVPROPERTY>::~vector<_DEVPROPERTY>(&v89);
        v64 = (volatile signed __int32 *)*((_QWORD *)&v88 + 1);
        if ( *((_QWORD *)&v88 + 1) )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v88 + 1) + 8LL), 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v64)(v64);
            if ( _InterlockedExchangeAdd(v64 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v64 + 8LL))(v64);
          }
        }
        v65 = (volatile signed __int32 *)*((_QWORD *)&v97 + 1);
        if ( *((_QWORD *)&v97 + 1) )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v97 + 1) + 8LL), 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v65)(v65);
            if ( _InterlockedExchangeAdd(v65 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v65 + 8LL))(v65);
          }
        }
        v49 = *(volatile signed __int32 **)&v96[2];
        if ( !*(_QWORD *)&v96[2]
          || _InterlockedExchangeAdd((volatile signed __int32 *)(*(_QWORD *)&v96[2] + 8LL), 0xFFFFFFFF) != 1 )
        {
          goto LABEL_69;
        }
      }
      else
      {
        if ( v39 )
          (*((void (__fastcall **)(LPVOID *))*v39 + 2))(v39);
        if ( v37 )
        {
          v45 = _InterlockedDecrement((volatile signed __int32 *)v37 + 6);
          if ( v45 )
          {
            if ( v45 < 0 )
              goto LABEL_169;
          }
          else
          {
            v46 = WINRT_IMPL_GetProcessHeap();
            WINRT_IMPL_HeapFree(v46, 0, v37);
          }
        }
        std::vector<_DEVPROPERTY>::~vector<_DEVPROPERTY>(&v89);
        v47 = (volatile signed __int32 *)*((_QWORD *)&v88 + 1);
        if ( *((_QWORD *)&v88 + 1) )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v88 + 1) + 8LL), 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v47)(v47);
            if ( _InterlockedExchangeAdd(v47 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v47 + 8LL))(v47);
          }
        }
        v48 = (volatile signed __int32 *)*((_QWORD *)&v97 + 1);
        if ( *((_QWORD *)&v97 + 1) )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v97 + 1) + 8LL), 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v48)(v48);
            if ( _InterlockedExchangeAdd(v48 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v48 + 8LL))(v48);
          }
        }
        v49 = *(volatile signed __int32 **)&v96[2];
        if ( !*(_QWORD *)&v96[2]
          || _InterlockedExchangeAdd((volatile signed __int32 *)(*(_QWORD *)&v96[2] + 8LL), 0xFFFFFFFF) != 1 )
        {
          goto LABEL_69;
        }
      }
      (**(void (__fastcall ***)(volatile signed __int32 *))v49)(v49);
      if ( _InterlockedExchangeAdd(v49 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v49 + 8LL))(v49);
    }
LABEL_69:
    if ( v80 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v80);
    goto LABEL_71;
  }
  catch ( const std::exception *v102 )
  {
    v66 = (_DWORD *)*((_QWORD *)MidiKSTransportTelemetryProvider::Instance() + 1);
    if ( *v66 > 2u )
    {
      lpMem = (LPVOID)(*(__int64 (__fastcall **)(const std::exception *))(*(_QWORD *)v102 + 8LL))(v102);
      p_lpMem = (LPVOID *)L"std exception processing json";
      v84 = (__int64 *)this;
      v86 = (const char **)"CMidi2KSMidiConfigurationManager::UpdateConfiguration";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
        (_DWORD)v66,
        (unsigned int)&dword_180068CCC,
        v67,
        v68,
        (__int64)&v86,
        (__int64)&v84,
        (__int64)&p_lpMem,
        (__int64)&lpMem,
        (__int64)&v105);
    }
    goto LABEL_170;
  }
  catch ( ... )
  {
    v69 = (_DWORD *)*((_QWORD *)MidiKSTransportTelemetryProvider::Instance() + 1);
    if ( *v69 > 2u )
    {
      lpMem = L"Other exception processing json";
      p_lpMem = (LPVOID *)this;
      v84 = (__int64 *)"CMidi2KSMidiConfigurationManager::UpdateConfiguration";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
        (_DWORD)v69,
        (unsigned int)byte_180068C93,
        v70,
        v71,
        (__int64)&v84,
        (__int64)&p_lpMem,
        (__int64)&lpMem,
        (__int64)&v105);
    }
LABEL_170:
    if ( v76 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v76);
    return 2147500037LL;
  }
  return result;
}

```

## disassembly

```asm
0x180023ac0  mov     rax, rsp
0x180023ac3  mov     [rax+18h], r8
0x180023ac7  mov     [rax+10h], rdx
0x180023acb  mov     [rax+8], rcx
0x180023acf  push    rbx
0x180023ad0  push    rsi
0x180023ad1  push    rdi
0x180023ad2  push    r12
0x180023ad4  push    r13
0x180023ad6  push    r14
0x180023ad8  push    r15
0x180023ada  sub     rsp, 180h
0x180023ae1  mov     r15, r8
0x180023ae4  mov     rbx, rdx
0x180023ae7  mov     r13, rcx
0x180023aea  xor     edi, edi
0x180023aec  mov     [rax+20h], edi
0x180023aef  test    rdx, rdx
0x180023af2  jnz     short loc_180023B1C
0x180023af4  mov     edx, 0AFh; void *
0x180023af9  mov     ebx, 80070057h
0x180023afe  mov     rcx, [rsp+1B8h]; this
0x180023b06  mov     r9d, ebx; char *
0x180023b09  lea     r8, aAvcoreMidi2Tra_7; "avcore\\midi2\\transport\\kstransport\\"...
0x180023b10  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180023b15  mov     eax, ebx
0x180023b17  jmp     loc_180024938
0x180023b1c  test    r15, r15
0x180023b1f  jnz     short loc_180023B28
0x180023b21  mov     edx, 0B0h
0x180023b26  jmp     short loc_180023AF9
0x180023b28  or      rax, 0FFFFFFFFFFFFFFFFh
0x180023b2c  inc     rax
0x180023b2f  cmp     [rdx+rax*2], di
0x180023b33  jnz     short loc_180023B2C
0x180023b35  test    rax, rax
0x180023b38  jnz     short loc_180023B41
0x180023b3a  mov     edx, 0B1h
0x180023b3f  jmp     short loc_180023AF9
0x180023b41  cmp     [rcx+28h], rdi
0x180023b45  jnz     short loc_180023BC2
0x180023b47  call    ?Instance@MidiKSTransportTelemetryProvider@@KAPEAV1@XZ; MidiKSTransportTelemetryProvider::Instance(void)
0x180023b4c  mov     rcx, [rax+8]
0x180023b50  mov     eax, [rcx]
0x180023b52  cmp     eax, 2
0x180023b55  jbe     loc_180024933
0x180023b5b  mov     [rsp+1B8h+arg_8], rbx
0x180023b63  lea     rax, aDeviceManagerI; "Device Manager is nullptr"
0x180023b6a  mov     [rsp+1B8h+lpMem], rax
0x180023b72  mov     qword ptr [rsp+1B8h+var_158], r13
0x180023b77  lea     r12, aCmidi2ksmidico_2; "CMidi2KSMidiConfigurationManager::Updat"...
0x180023b7e  mov     [rsp+1B8h+var_168], r12
0x180023b83  lea     rax, [rsp+1B8h+arg_8]
0x180023b8b  mov     [rsp+1B8h+var_180], rax
0x180023b90  lea     rax, [rsp+1B8h+lpMem]
0x180023b98  mov     [rsp+1B8h+var_188], rax
0x180023b9d  lea     rax, [rsp+1B8h+var_158]
0x180023ba2  mov     [rsp+1B8h+var_190], rax
0x180023ba7  lea     rax, [rsp+1B8h+var_168]
0x180023bac  mov     qword ptr [rsp+1B8h+var_198], rax
0x180023bb1  lea     rdx, byte_180068DF1
0x180023bb8  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x180023bbd  jmp     loc_180024933
0x180023bc2  call    ?Instance@MidiKSTransportTelemetryProvider@@KAPEAV1@XZ; MidiKSTransportTelemetryProvider::Instance(void)
0x180023bc7  mov     rcx, [rax+8]
0x180023bcb  mov     eax, [rcx]
0x180023bcd  cmp     eax, 4
0x180023bd0  jbe     short loc_180023C1A
0x180023bd2  mov     [rsp+1B8h+lpMem], rbx
0x180023bda  mov     qword ptr [rsp+1B8h+var_158], r13
0x180023bdf  lea     r12, aCmidi2ksmidico_2; "CMidi2KSMidiConfigurationManager::Updat"...
0x180023be6  mov     [rsp+1B8h+var_168], r12
0x180023beb  lea     rax, [rsp+1B8h+lpMem]
0x180023bf3  mov     [rsp+1B8h+var_188], rax
0x180023bf8  lea     rax, [rsp+1B8h+var_158]
0x180023bfd  mov     [rsp+1B8h+var_190], rax
0x180023c02  lea     rax, [rsp+1B8h+var_168]
0x180023c07  mov     qword ptr [rsp+1B8h+var_198], rax
0x180023c0c  lea     rdx, word_180068DC2
0x180023c13  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &)
0x180023c18  jmp     short loc_180023C21
0x180023c1a  lea     r12, aCmidi2ksmidico_2; "CMidi2KSMidiConfigurationManager::Updat"...
0x180023c21  lea     rcx, [rsp+1B8h+var_160]
0x180023c26  call    ?BuildConfigurationResponseObject@WindowsMidiServicesInternal@@YA?AUJsonObject@Json@Data@Windows@winrt@@_N@Z; WindowsMidiServicesInternal::BuildConfigurationResponseObject(bool)
0x180023c2b  nop
0x180023c2c  lea     rcx, [rsp+1B8h+var_148]; this
0x180023c31  call    ??0JsonObject@Json@Data@Windows@winrt@@QEAA@XZ; winrt::Windows::Data::Json::JsonObject::JsonObject(void)
0x180023c36  nop
0x180023c37  mov     rdx, rbx; unsigned __int16 *
0x180023c3a  lea     rcx, [rsp+1B8h+lpMem]; this
0x180023c42  call    ??0hstring@winrt@@QEAA@PEBG@Z; winrt::hstring::hstring(ushort const *)
0x180023c47  nop
0x180023c48  mov     rcx, [rsp+1B8h+lpMem]; this
0x180023c50  call    ?duplicate_hstring@impl@winrt@@YAPEAUhstring_header@12@PEAU312@@Z; winrt::impl::duplicate_hstring(winrt::impl::hstring_header *)
0x180023c55  mov     rsi, rax
0x180023c58  mov     [rsp+1B8h+var_138], rax
0x180023c60  mov     [rsp+1B8h+var_C8], rax
0x180023c68  lea     rax, [rsp+1B8h+var_C8]
0x180023c70  mov     qword ptr [rsp+1B8h+var_A8], rax
0x180023c78  lea     rax, [rsp+1B8h+var_148]
0x180023c7d  mov     qword ptr [rsp+1B8h+var_A8+8], rax
0x180023c85  lea     rax, qword_180071CC8
0x180023c8c  mov     [rsp+1B8h+var_120], rax
0x180023c94  lock inc cs:qword_180071CC8
0x180023c9c  cmp     cs:??$factory_cache_entry_v@UJsonObject@Json@Data@Windows@winrt@@UIJsonObjectStatics@2345@@impl@winrt@@3U?$factory_cache_entry@UJsonObject@Json@Data@Windows@winrt@@UIJsonObjectStatics@2345@@12@A, rdi; factory_cache_entry<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Data::Json::IJsonObjectStatics>::winrt::factory_cache_entry<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Data::Json::IJsonObjectStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Data::Json::IJsonObjectStatics>
0x180023ca3  jz      short loc_180023CC6
0x180023ca5  lea     rdx, ??$factory_cache_entry_v@UJsonObject@Json@Data@Windows@winrt@@UIJsonObjectStatics@2345@@impl@winrt@@3U?$factory_cache_entry@UJsonObject@Json@Data@Windows@winrt@@UIJsonObjectStatics@2345@@12@A; factory_cache_entry<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Data::Json::IJsonObjectStatics>::winrt::factory_cache_entry<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Data::Json::IJsonObjectStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Data::Json::IJsonObjectStatics>
0x180023cac  lea     rcx, [rsp+1B8h+var_A8]
0x180023cb4  call    ??R_lambda_1_@?1??TryParse@JsonObject@Json@Data@Windows@winrt@@SA@AEBUhstring@param@6@AEAU23456@@Z@QEBA@AEBUIJsonObjectStatics@3456@@Z; `winrt::Windows::Data::Json::JsonObject::TryParse(winrt::param::hstring const &,winrt::Windows::Data::Json::JsonObject &)'::`2'::_lambda_1_::operator()(winrt::Windows::Data::Json::IJsonObjectStatics const &)
0x180023cb9  mov     r14b, al
0x180023cbc  lock dec cs:qword_180071CC8
0x180023cc4  jmp     short loc_180023CDE
0x180023cc6  lock dec cs:qword_180071CC8
0x180023cce  lea     rdx, [rsp+1B8h+var_A8]
0x180023cd6  call    ??$call@AEAV_lambda_1_@?1??TryParse@JsonObject@Json@Data@Windows@winrt@@SA@AEBUhstring@param@7@AEAU34567@@Z@@?$factory_cache_entry@UJsonObject@Json@Data@Windows@winrt@@UIJsonObjectStatics@2345@@impl@winrt@@QEAA?A_PAEAV_lambda_1_@?1??TryParse@JsonObject@Json@Data@Windows@2@SA@AEBUhstring@param@2@AEAU56782@@Z@@Z
0x180023cdb  mov     r14b, al
0x180023cde  test    rsi, rsi
0x180023ce1  jz      short loc_180023D08
0x180023ce3  or      eax, 0FFFFFFFFh
0x180023ce6  lock xadd [rsi+18h], eax
0x180023ceb  sub     eax, 1
0x180023cee  jnz     loc_1800240B6
0x180023cf4  nop
0x180023cf5  call    WINRT_IMPL_GetProcessHeap
0x180023cfa  mov     rcx, rax; hHeap
0x180023cfd  mov     r8, rsi; lpMem
0x180023d00  xor     edx, edx; dwFlags
0x180023d02  call    WINRT_IMPL_HeapFree
0x180023d07  nop
0x180023d08  mov     rsi, [rsp+1B8h+lpMem]
0x180023d10  test    rsi, rsi
0x180023d13  jz      short loc_180023D39
0x180023d15  or      eax, 0FFFFFFFFh
0x180023d18  lock xadd [rsi+18h], eax
0x180023d1d  sub     eax, 1
0x180023d20  jnz     loc_1800240C5
0x180023d26  nop
0x180023d27  call    WINRT_IMPL_GetProcessHeap
0x180023d2c  mov     rcx, rax; hHeap
0x180023d2f  mov     r8, rsi; lpMem
0x180023d32  xor     edx, edx; dwFlags
0x180023d34  call    WINRT_IMPL_HeapFree
0x180023d39  test    r14b, r14b
0x180023d3c  jnz     loc_180023DDB
0x180023d42  call    ?Instance@MidiKSTransportTelemetryProvider@@KAPEAV1@XZ; MidiKSTransportTelemetryProvider::Instance(void)
0x180023d47  mov     rcx, [rax+8]
0x180023d4b  mov     eax, [rcx]
0x180023d4d  cmp     eax, 2
0x180023d50  jbe     short loc_180023DAE
0x180023d52  mov     [rsp+1B8h+lpMem], rbx
0x180023d5a  lea     rax, aFailedToParseC; "Failed to parse Configuration JSON"
0x180023d61  mov     qword ptr [rsp+1B8h+var_158], rax
0x180023d66  mov     [rsp+1B8h+var_168], r13
0x180023d6b  mov     [rsp+1B8h+var_108], r12
0x180023d73  lea     rax, [rsp+1B8h+lpMem]
0x180023d7b  mov     [rsp+1B8h+var_180], rax
0x180023d80  lea     rax, [rsp+1B8h+var_158]
0x180023d85  mov     [rsp+1B8h+var_188], rax
0x180023d8a  lea     rax, [rsp+1B8h+var_168]
0x180023d8f  mov     [rsp+1B8h+var_190], rax
0x180023d94  lea     rax, [rsp+1B8h+var_108]
0x180023d9c  mov     qword ptr [rsp+1B8h+var_198], rax
0x180023da1  lea     rdx, byte_180068D89
0x180023da8  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x180023dad  nop
0x180023dae  cmp     [rsp+1B8h+var_148], rdi
0x180023db3  jz      short loc_180023DC0
0x180023db5  lea     rcx, [rsp+1B8h+var_148]
0x180023dba  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180023dbf  nop
0x180023dc0  cmp     [rsp+1B8h+var_160], rdi
0x180023dc5  jz      short loc_180023DD1
0x180023dc7  lea     rcx, [rsp+1B8h+var_160]
0x180023dcc  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180023dd1  mov     eax, 80070057h
0x180023dd6  jmp     loc_180024938
0x180023ddb  mov     rcx, [rsp+1B8h+var_148]
0x180023de0  mov     [rsp+1B8h+lpMem], rcx
0x180023de8  test    rcx, rcx
0x180023deb  jz      short loc_180023DF9
0x180023ded  mov     rax, [rcx]
0x180023df0  mov     rax, [rax+8]
0x180023df4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023df9  lea     rax, [rsp+1B8h+lpMem]
0x180023e01  mov     [rsp+1B8h+var_138], rax
0x180023e09  mov     [rsp+1B8h+var_168], rdi
0x180023e0e  mov     qword ptr [rsp+1B8h+var_158], rdi
0x180023e13  mov     dword ptr [rsp+1B8h+var_E8+8], 1
0x180023e1e  mov     dword ptr [rsp+1B8h+var_E8+0Ch], 10h
0x180023e29  lea     rax, aTransportcomma; "transportCommand"
0x180023e30  mov     [rsp+1B8h+var_D0], rax
0x180023e38  lea     rax, [rsp+1B8h+var_E8+8]
0x180023e40  mov     qword ptr [rsp+1B8h+var_E8], rax
0x180023e48  lea     r9, [rsp+1B8h+var_158]
0x180023e4d  lea     r8, [rsp+1B8h+var_E8]
0x180023e55  lea     rdx, [rsp+1B8h+var_118]
0x180023e5d  lea     rcx, [rsp+1B8h+lpMem]
0x180023e65  call    ?GetNamedObject@?$consume_Windows_Data_Json_IJsonObjectWithDefaultValues@UJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@AEBUJsonObject@Json@Data@Windows@3@@Z; winrt::impl::consume_Windows_Data_Json_IJsonObjectWithDefaultValues<winrt::Windows::Data::Json::JsonObject>::GetNamedObject(winrt::param::hstring const &,winrt::Windows::Data::Json::JsonObject const &)
0x180023e6a  lea     rdx, [rsp+1B8h+var_168]
0x180023e6f  mov     rcx, rax
0x180023e72  call    ??8Foundation@Windows@winrt@@YA_NAEBUIUnknown@012@0@Z; winrt::Windows::Foundation::operator==(winrt::Windows::Foundation::IUnknown const &,winrt::Windows::Foundation::IUnknown const &)
0x180023e77  mov     bl, al
0x180023e79  cmp     [rsp+1B8h+var_118], rdi
0x180023e81  jz      short loc_180023E91
0x180023e83  lea     rcx, [rsp+1B8h+var_118]
0x180023e8b  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180023e90  nop
0x180023e91  test    bl, bl
0x180023e93  jnz     short loc_180023EF5
0x180023e95  cmp     [rsp+1B8h+lpMem], rdi
0x180023e9d  jz      short loc_180023EAC
0x180023e9f  lea     rcx, [rsp+1B8h+lpMem]
0x180023ea7  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180023eac  lea     r8, [rsp+1B8h+var_160]; struct winrt::Windows::Data::Json::JsonObject *
0x180023eb1  lea     rdx, [rsp+1B8h+var_148]; struct winrt::Windows::Data::Json::JsonObject *
0x180023eb6  call    ?ProcessCommand@CMidi2KSMidiConfigurationManager@@AEAAJAEBUJsonObject@Json@Data@Windows@winrt@@AEAU23456@@Z; CMidi2KSMidiConfigurationManager::ProcessCommand(winrt::Windows::Data::Json::JsonObject const &,winrt::Windows::Data::Json::JsonObject &)
0x180023ebb  mov     ebx, eax
0x180023ebd  mov     rdx, r15; struct winrt::Windows::Data::Json::JsonObject *
0x180023ec0  lea     rcx, [rsp+1B8h+var_160]; this
0x180023ec5  call    ?JsonStringifyObjectToOutParam@WindowsMidiServicesInternal@@YA_NAEBUJsonObject@Json@Data@Windows@winrt@@PEAPEAG@Z; WindowsMidiServicesInternal::JsonStringifyObjectToOutParam(winrt::Windows::Data::Json::JsonObject const &,ushort * *)
0x180023eca  nop
0x180023ecb  cmp     [rsp+1B8h+var_148], rdi
0x180023ed0  jz      short loc_180023EDD
0x180023ed2  lea     rcx, [rsp+1B8h+var_148]
0x180023ed7  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180023edc  nop
0x180023edd  cmp     [rsp+1B8h+var_160], rdi
0x180023ee2  jz      short loc_180023EEE
0x180023ee4  lea     rcx, [rsp+1B8h+var_160]
0x180023ee9  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180023eee  mov     eax, ebx
0x180023ef0  jmp     loc_180024938
0x180023ef5  cmp     [rsp+1B8h+lpMem], rdi
0x180023efd  jz      short loc_180023F0C
0x180023eff  lea     rcx, [rsp+1B8h+lpMem]
0x180023f07  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180023f0c  mov     [rsp+1B8h+lpMem], rdi
0x180023f14  mov     [rsp+1B8h+var_C0], 1
0x180023f1f  mov     [rsp+1B8h+var_BC], 6
0x180023f2a  lea     rax, aUpdate; "update"
0x180023f31  mov     [rsp+1B8h+var_B0], rax
0x180023f39  lea     rax, [rsp+1B8h+var_C0]
0x180023f41  mov     [rsp+1B8h+var_C8], rax
0x180023f49  lea     r9, [rsp+1B8h+lpMem]
0x180023f51  lea     r8, [rsp+1B8h+var_C8]
0x180023f59  lea     rdx, [rsp+1B8h+var_128]
0x180023f61  lea     rcx, [rsp+1B8h+var_148]
0x180023f66  call    ?GetNamedArray@?$consume_Windows_Data_Json_IJsonObjectWithDefaultValues@UJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@AEBUJsonArray@Json@Data@Windows@3@@Z; winrt::impl::consume_Windows_Data_Json_IJsonObjectWithDefaultValues<winrt::Windows::Data::Json::JsonObject>::GetNamedArray(winrt::param::hstring const &,winrt::Windows::Data::Json::JsonArray const &)
0x180023f6b  nop
0x180023f6c  mov     qword ptr [rsp+1B8h+var_158], rdi
0x180023f71  mov     dword ptr [rsp+1B8h+lpMem], 1
0x180023f7c  lea     rdx, [rsp+1B8h+var_158]
0x180023f81  lea     rcx, [rsp+1B8h+var_128]
0x180023f89  call    ??8Foundation@Windows@winrt@@YA_NAEBUIUnknown@012@0@Z; winrt::Windows::Foundation::operator==(winrt::Windows::Foundation::IUnknown const &,winrt::Windows::Foundation::IUnknown const &)
0x180023f8e  test    al, al
0x180023f90  jnz     short loc_180023FA5
0x180023f92  lea     rcx, [rsp+1B8h+var_128]
0x180023f9a  call    ?Size@?$consume_Windows_Foundation_Collections_IVector@UJsonArray@Json@Data@Windows@winrt@@UIJsonValue@2345@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Data::Json::JsonArray,winrt::Windows::Data::Json::IJsonValue>::Size(void)
0x180023f9f  test    eax, eax
0x180023fa1  mov     al, 1
0x180023fa3  jnz     short loc_180023FA8
0x180023fa5  mov     al, dil
0x180023fa8  test    al, al
0x180023faa  jz      loc_180024066
0x180023fb0  lea     rax, [rsp+1B8h+var_128]
0x180023fb8  mov     [rsp+1B8h+var_68], rax
0x180023fc0  mov     r15d, edi
0x180023fc3  mov     [rsp+1B8h+var_60], edi
0x180023fca  lea     rcx, [rsp+1B8h+var_128]
0x180023fd2  call    ?Size@?$consume_Windows_Foundation_Collections_IVector@UJsonArray@Json@Data@Windows@winrt@@UIJsonValue@2345@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Data::Json::JsonArray,winrt::Windows::Data::Json::IJsonValue>::Size(void)
0x180023fd7  mov     dword ptr [rsp+1B8h+lpMem], eax
0x180023fde  cmp     r15d, eax
0x180023fe1  jnz     loc_1800240D4
0x180023fe7  mov     dl, 1
0x180023fe9  lea     rcx, [rsp+1B8h+lpMem]; bool
0x180023ff1  call    ?CreateBooleanValue@JsonValue@Json@Data@Windows@winrt@@SA@_N@Z; winrt::Windows::Data::Json::JsonValue::CreateBooleanValue(bool)
0x180023ff6  nop
0x180023ff7  mov     [rsp+1B8h+var_C0], 1
0x180024002  mov     [rsp+1B8h+var_BC], 7
0x18002400d  lea     rax, aSuccess; "success"
0x180024014  mov     [rsp+1B8h+var_B0], rax
0x18002401c  lea     rax, [rsp+1B8h+var_C0]
0x180024024  mov     [rsp+1B8h+var_C8], rax
0x18002402c  lea     r8, [rsp+1B8h+lpMem]
0x180024034  lea     rdx, [rsp+1B8h+var_C8]
0x18002403c  lea     rcx, [rsp+1B8h+var_160]
0x180024041  call    ?SetNamedValue@?$consume_Windows_Data_Json_IJsonObject@UIJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@AEBUIJsonValue@Json@Data@Windows@3@@Z; winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(winrt::param::hstring const &,winrt::Windows::Data::Json::IJsonValue const &)
0x180024046  nop
0x180024047  cmp     [rsp+1B8h+lpMem], rdi
0x18002404f  jz      short loc_18002405E
0x180024051  lea     rcx, [rsp+1B8h+lpMem]
0x180024059  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18002405e  mov     r15, [rsp+1B8h+arg_10]
0x180024066  cmp     [rsp+1B8h+var_128], rdi
0x18002406e  jz      short loc_18002407E
0x180024070  lea     rcx, [rsp+1B8h+var_128]
0x180024078  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18002407d  nop
0x18002407e  cmp     [rsp+1B8h+var_148], rdi
0x180024083  jz      short loc_180024090
  ... truncated ...
```
