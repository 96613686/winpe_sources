# CMidi2KSAggregateMidiConfigurationManager::UpdateConfiguration(ushort const *,ushort * *)

- ea: `0x18001e790`
- end: `0x18001f598`
- name: `?UpdateConfiguration@CMidi2KSAggregateMidiConfigurationManager@@UEAAJPEBGPEAPEAG@Z`
- size: `3592`
- prototype: `int(CMidi2KSAggregateMidiConfigurationManager *__hidden this, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `35`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x1800016dc`
- `0x1800017d0`
- `0x180002268`
- `0x180005f2c`
- `0x180005fa4`
- `0x18000b394`
- `0x18000e37c`
- `0x1800106c8`
- `0x180010b94`
- `0x1800117d8`
- `0x180014f84`
- `0x180014ff4`
- `0x180019924`
- `0x1800199c4`
- `0x18001bab4`
- `0x18001c7e4`
- `0x18001c85c`
- `0x18001ca4c`
- `0x18001cb00`
- `0x18001cc0c`
- `0x18001cca8`
- `0x18001cd34`
- `0x18001ce9c`
- `0x18001cfe4`
- `0x18001d204`
- `0x18001d474`
- `0x18001dae8`
- `0x18001dd50`
- `0x18001e4a4`
- `0x18001e600`
- `0x18001e790`
- `0x180024c84`
- `0x180039c00`
- `0x18004d0f4`
- `0x18005e010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18001ed38`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18001ed47`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18001ef10`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18001f23e`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18001f566`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18001ed38`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18001ed47`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18001ef10`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18001f23e`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18001f566`

## string_xrefs

- `0x18001ea99`: `transportCommand`
- `0x18001e7ce`: `avcore\midi2\transport\ksaggregatetransport\midi2.ksaggregatemidiconfigurationmanager.cpp`
- `0x18001ea0f`: `avcore\midi2\transport\ksaggregatetransport\midi2.ksaggregatemidiconfigurationmanager.cpp`
- `0x18001f0a7`: `avcore\midi2\transport\ksaggregatetransport\midi2.ksaggregatemidiconfigurationmanager.cpp`
- `0x18001f3d3`: `avcore\midi2\transport\ksaggregatetransport\midi2.ksaggregatemidiconfigurationmanager.cpp`
- `0x18001e831`: `CMidi2KSAggregateMidiConfigurationManager::UpdateConfiguration`
- `0x18001e86c`: `CMidi2KSAggregateMidiConfigurationManager::UpdateConfiguration`
- `0x18001f2c3`: `CMidi2KSAggregateMidiConfigurationManager::UpdateConfiguration`
- `0x18001f36f`: `CMidi2KSAggregateMidiConfigurationManager::UpdateConfiguration`
- `0x18001e9b9`: `Failed to parse Configuration JSON`
- `0x18001eb9a`: `update`
- `0x18001f2ac`: `Properties updated`

## pseudocode

```c
// Hidden C++ exception states: #wind=29
__int64 __fastcall CMidi2KSAggregateMidiConfigurationManager::UpdateConfiguration(
        CMidi2KSAggregateMidiConfigurationManager *this,
        unsigned __int16 *a2,
        unsigned __int16 **a3)
{
  const struct winrt::Windows::Data::Json::JsonObject *v3; // r15
  __int64 v6; // rdx
  unsigned int v7; // ebx
  __int64 result; // rax
  __int64 v9; // rax
  _DWORD *v10; // rcx
  int v11; // r8d
  int v12; // r9d
  struct winrt::impl::hstring_header *v13; // rdx
  __int64 v14; // rcx
  volatile signed __int32 *v15; // rbx
  char v16; // di
  int v17; // eax
  HANDLE ProcessHeap; // rax
  void *v19; // rbx
  int v20; // eax
  HANDLE v21; // rax
  _DWORD *v22; // rcx
  int v23; // r8d
  int v24; // r9d
  __int64 NamedObject; // rax
  CMidi2KSAggregateMidiConfigurationManager *v26; // rcx
  char v27; // bl
  unsigned int v28; // ebx
  unsigned __int16 **v29; // r8
  unsigned __int16 **v30; // r8
  bool v31; // zf
  char v32; // al
  int v33; // r14d
  int v34; // r15d
  int v35; // eax
  const wchar_t *v36; // r12
  wchar_t *v37; // rbx
  struct TransportState *v38; // rdi
  struct winrt::impl::hstring_header *v39; // rdx
  __int64 v40; // rdi
  __int64 v41; // rax
  __int64 MatchingInstantiatedEndpoint; // rax
  void *v43; // rbx
  int v44; // eax
  HANDLE v45; // rax
  struct TransportState *v46; // rdi
  __int64 v47; // rdi
  __int64 v48; // rax
  __int64 v49; // rax
  void *v50; // rbx
  int v51; // eax
  HANDLE v52; // rax
  int v53; // eax
  int v54; // eax
  HANDLE v55; // rax
  volatile signed __int32 *v56; // rbx
  volatile signed __int32 *v57; // rbx
  volatile signed __int32 *v58; // rbx
  int v59; // edi
  _DWORD *v60; // r8
  int v61; // r9d
  const wchar_t *v62; // rax
  _DWORD *v63; // r8
  int v64; // r9d
  int v65; // eax
  HANDLE v66; // rax
  volatile signed __int32 *v67; // rbx
  volatile signed __int32 *v68; // rbx
  volatile signed __int32 *v69; // rbx
  _DWORD *v70; // rbx
  int v71; // r8d
  int v72; // r9d
  _DWORD *v73; // rcx
  int v74; // r8d
  int v75; // r9d
  int v76; // [rsp+20h] [rbp-198h]
  int v77; // [rsp+20h] [rbp-198h]
  __int64 v78; // [rsp+38h] [rbp-180h]
  int v79[2]; // [rsp+50h] [rbp-168h] BYREF
  __int64 v80; // [rsp+58h] [rbp-160h] BYREF
  struct winrt::impl::hstring_header *v81; // [rsp+60h] [rbp-158h] BYREF
  __int64 v82; // [rsp+68h] [rbp-150h] BYREF
  void *v83; // [rsp+70h] [rbp-148h] BYREF
  __int64 v84; // [rsp+78h] [rbp-140h] BYREF
  const wchar_t *v85; // [rsp+80h] [rbp-138h] BYREF
  __int64 v86; // [rsp+88h] [rbp-130h] BYREF
  const char *p_lpMem; // [rsp+90h] [rbp-128h] BYREF
  __int64 v88; // [rsp+98h] [rbp-120h] BYREF
  _QWORD v89[2]; // [rsp+A0h] [rbp-118h] BYREF
  __int128 v90; // [rsp+B0h] [rbp-108h] BYREF
  __int128 v91; // [rsp+C0h] [rbp-F8h] BYREF
  __int64 v92; // [rsp+D0h] [rbp-E8h]
  const wchar_t *v93; // [rsp+D8h] [rbp-E0h]
  int *v94; // [rsp+E0h] [rbp-D8h] BYREF
  int v95; // [rsp+E8h] [rbp-D0h] BYREF
  int v96; // [rsp+ECh] [rbp-CCh]
  const wchar_t *v97; // [rsp+F8h] [rbp-C0h]
  LPVOID v98; // [rsp+100h] [rbp-B8h] BYREF
  LPVOID v99; // [rsp+108h] [rbp-B0h] BYREF
  int v100[4]; // [rsp+110h] [rbp-A8h] BYREF
  __int128 v101; // [rsp+130h] [rbp-88h] BYREF
  __int128 v102; // [rsp+140h] [rbp-78h] BYREF
  __int64 *v103; // [rsp+150h] [rbp-68h] BYREF
  int v104; // [rsp+158h] [rbp-60h]
  __int128 *v105; // [rsp+160h] [rbp-58h]
  const std::exception *v106; // [rsp+170h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1B8h] [rbp+0h]
  unsigned __int16 *v109; // [rsp+1C8h] [rbp+10h] BYREF
  unsigned __int16 **v110; // [rsp+1D0h] [rbp+18h]
  LPVOID lpMem; // [rsp+1D8h] [rbp+20h] BYREF

  v110 = a3;
  v109 = a2;
  v3 = (const struct winrt::Windows::Data::Json::JsonObject *)a3;
  LODWORD(lpMem) = 0;
  if ( !a2 )
  {
    v6 = 182;
LABEL_3:
    v7 = -2147024809;
LABEL_4:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"avcore\\midi2\\transport\\ksaggregatetransport\\midi2.ksaggregatemidiconfigurationmanager.cpp",
      (const char *)v7,
      v76);
    return v7;
  }
  if ( !a3 )
  {
    v6 = 183;
    goto LABEL_3;
  }
  v9 = -1;
  do
    ++v9;
  while ( a2[v9] );
  if ( !v9 )
  {
    v6 = 184;
    goto LABEL_3;
  }
  v10 = (_DWORD *)*((_QWORD *)MidiKSAggregateTransportTelemetryProvider::Instance() + 1);
  if ( *v10 > 4u )
  {
    lpMem = a2;
    v81 = this;
    *(_QWORD *)v79 = "CMidi2KSAggregateMidiConfigurationManager::UpdateConfiguration";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>>(
      (_DWORD)v10,
      (unsigned int)&dword_180089044,
      v11,
      v12,
      (__int64)v79,
      (__int64)&v81,
      (__int64)&lpMem);
  }
  if ( !*((_QWORD *)this + 5) )
  {
    v7 = -2147467261;
    v6 = 195;
    goto LABEL_4;
  }
  WindowsMidiServicesInternal::BuildConfigurationResponseObject(&v80);
  try
  {
    winrt::Windows::Data::Json::JsonObject::JsonObject((winrt::Windows::Data::Json::JsonObject *)&v83);
    winrt::hstring::hstring((winrt::hstring *)&lpMem, a2);
    v15 = (volatile signed __int32 *)winrt::impl::duplicate_hstring((winrt::impl *)lpMem, v13);
    p_lpMem = (const char *)v15;
    v94 = (int *)v15;
    *(_QWORD *)v100 = &v94;
    *(_QWORD *)&v100[2] = &v83;
    v89[0] = &qword_180096B48;
    _InterlockedIncrement64(&qword_180096B48);
    if ( winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Data::Json::IJsonObjectStatics> )
    {
      v16 = `winrt::Windows::Data::Json::JsonObject::TryParse'::`2'::_lambda_1_::operator()(
              v100,
              &winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Data::Json::IJsonObjectStatics>);
      _InterlockedAdd64(&qword_180096B48, 0xFFFFFFFFFFFFFFFFuLL);
    }
    else
    {
      _InterlockedAdd64(&qword_180096B48, 0xFFFFFFFFFFFFFFFFuLL);
      v16 = ___call_AEAV_lambda_1___1__TryParse_JsonObject_Json_Data_Windows_winrt__SA_AEBUhstring_param_7_AEAU34567__Z____factory_cache_entry_UJsonObject_Json_Data_Windows_winrt__UIJsonObjectStatics_2345__impl_winrt__QEAA_A_PAEAV_lambda_1___1__TryParse_JsonObject_Json_Data_Windows_2_SA_AEBUhstring_param_2_AEAU56782__Z__Z(
              v14,
              v100);
    }
    if ( v15 )
    {
      v17 = _InterlockedDecrement(v15 + 6);
      if ( v17 )
      {
        if ( v17 < 0 )
          abort();
      }
      else
      {
        ProcessHeap = WINRT_IMPL_GetProcessHeap();
        WINRT_IMPL_HeapFree(ProcessHeap, 0, (LPVOID)v15);
      }
    }
    v19 = lpMem;
    if ( lpMem )
    {
      v20 = _InterlockedDecrement((volatile signed __int32 *)lpMem + 6);
      if ( v20 )
      {
        if ( v20 < 0 )
          abort();
      }
      else
      {
        v21 = WINRT_IMPL_GetProcessHeap();
        WINRT_IMPL_HeapFree(v21, 0, v19);
      }
    }
    if ( v16 )
    {
      lpMem = v83;
      if ( v83 )
        (*(void (__fastcall **)(void *))(*(_QWORD *)v83 + 8LL))(v83);
      p_lpMem = (const char *)&lpMem;
      *(_QWORD *)v79 = 0;
      v81 = 0;
      *((_QWORD *)&v91 + 1) = 0x1000000001LL;
      v93 = L"transportCommand";
      *(_QWORD *)&v91 = (char *)&v91 + 8;
      NamedObject = winrt::impl::consume_Windows_Data_Json_IJsonObjectWithDefaultValues<winrt::Windows::Data::Json::JsonObject>::GetNamedObject(
                      &lpMem,
                      &v85,
                      &v91,
                      &v81);
      v27 = winrt::Windows::Foundation::operator==(NamedObject, v79);
      if ( v85 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v85);
      if ( v27 )
      {
        if ( lpMem )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&lpMem);
        lpMem = 0;
        v95 = 1;
        v96 = 6;
        v97 = L"update";
        v94 = &v95;
        winrt::impl::consume_Windows_Data_Json_IJsonObjectWithDefaultValues<winrt::Windows::Data::Json::JsonObject>::GetNamedArray(
          &v83,
          &v88,
          &v94,
          &lpMem);
        v81 = 0;
        LODWORD(lpMem) = 1;
        if ( (unsigned __int8)winrt::Windows::Foundation::operator==(&v88, &v81)
          || (v31 = (unsigned int)winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Data::Json::JsonArray,winrt::Windows::Data::Json::IJsonValue>::Size(&v88) == 0,
              v32 = 1,
              v31) )
        {
          v32 = 0;
        }
        v33 = 0;
        if ( v32 )
        {
          v103 = &v88;
          v34 = 0;
          v104 = 0;
          v35 = winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Data::Json::JsonArray,winrt::Windows::Data::Json::IJsonValue>::Size(&v88);
          LODWORD(lpMem) = v35;
          v36 = &S1;
          while ( 1 )
          {
            if ( v34 == v35 )
            {
              winrt::Windows::Data::Json::JsonValue::CreateBooleanValue((bool)&lpMem);
              v95 = 1;
              v96 = 7;
              v97 = L"success";
              v94 = &v95;
              winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(
                &v80,
                &v94,
                &lpMem);
              if ( lpMem )
                winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&lpMem);
              v3 = (const struct winrt::Windows::Data::Json::JsonObject *)v110;
              break;
            }
            winrt::impl::fast_iterator<winrt::Windows::Data::Json::JsonArray>::operator*(&v103, &v84);
            winrt::impl::consume_Windows_Data_Json_IJsonValue<winrt::Windows::Data::Json::IJsonValue>::GetObject(
              &v84,
              &v82);
            *(_QWORD *)v79 = 0;
            if ( !(unsigned __int8)winrt::Windows::Foundation::operator==(&v82, v79) )
            {
              *(_QWORD *)v79 = 0;
              *(_QWORD *)v100 = WindowsMidiServicesPluginConfigurationLib::MidiEndpointMatchCriteria::PropertyKey;
              winrt::impl::consume_Windows_Data_Json_IJsonObjectWithDefaultValues<winrt::Windows::Data::Json::JsonObject>::GetNamedObject(
                &v82,
                &v86,
                v100,
                v79);
              *(_QWORD *)v79 = 0;
              if ( !(unsigned __int8)winrt::Windows::Foundation::operator==(&v86, v79) )
              {
                *(_OWORD *)v100 = 0;
                v101 = 0;
                WindowsMidiServicesPluginConfigurationLib::MidiEndpointMatchCriteria::FromJson(&v90, &v86);
                v91 = 0;
                v92 = 0;
                v37 = 0;
                v85 = 0;
                if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_MIDI2VirtualPortDriversFix>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_MIDI2VirtualPortDriversFix>::GetImpl'::`2'::impl) )
                {
                  v38 = TransportState::Current();
                  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_MIDI2VirtualPortDriversFix>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_MIDI2VirtualPortDriversFix>::GetImpl'::`2'::impl) )
                  {
                    v40 = *((_QWORD *)v38 + 1);
                    *(_QWORD *)v79 = v40;
                    if ( v40 )
                      (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 8LL))(v40);
                    v41 = v40;
                  }
                  else
                  {
                    v40 = 0;
                    *(_QWORD *)v79 = 0;
                    v41 = 0;
                  }
                  v33 |= 4u;
                  if ( v41 )
                  {
                    MatchingInstantiatedEndpoint = CMidi2KSAggregateMidiEndpointManager2::FindMatchingInstantiatedEndpoint(
                                                     v40,
                                                     &v98,
                                                     v90);
                    winrt::hstring::operator=(&v85, MatchingInstantiatedEndpoint);
                    v43 = v98;
                    if ( v98 )
                    {
                      v44 = _InterlockedDecrement((volatile signed __int32 *)v98 + 6);
                      if ( v44 )
                      {
                        if ( v44 < 0 )
                          abort();
                      }
                      else
                      {
                        v45 = WINRT_IMPL_GetProcessHeap();
                        WINRT_IMPL_HeapFree(v45, 0, v43);
                      }
                      v98 = 0;
                    }
                    v37 = (wchar_t *)v85;
                  }
                  if ( v40 )
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 16LL))(v40);
                }
                else
                {
                  v46 = TransportState::Current();
                  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_MIDI2VirtualPortDriversFix>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_MIDI2VirtualPortDriversFix>::GetImpl'::`2'::impl) )
                  {
                    v47 = 0;
                    *(_QWORD *)v79 = 0;
                    v48 = 0;
                  }
                  else
                  {
                    v47 = *(_QWORD *)v46;
                    *(_QWORD *)v79 = v47;
                    if ( v47 )
                      (*(void (__fastcall **)(__int64))(*(_QWORD *)v47 + 8LL))(v47);
                    v48 = v47;
                  }
                  v33 |= 8u;
                  if ( v48 )
                  {
                    v49 = CMidi2KSAggregateMidiEndpointManager::FindMatchingInstantiatedEndpoint(v47, &v99, v90);
                    winrt::hstring::operator=(&v85, v49);
                    v50 = v99;
                    if ( v99 )
                    {
                      v51 = _InterlockedDecrement((volatile signed __int32 *)v99 + 6);
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
                      v99 = 0;
                    }
                    v37 = (wchar_t *)v85;
                  }
                  if ( v47 )
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v47 + 16LL))(v47);
                }
                p_lpMem = (const char *)v79;
                *(_QWORD *)v79 = v82;
                if ( v82 )
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v82 + 8LL))(v82);
                v105 = &v102;
                v102 = 0;
                if ( *((_QWORD *)&v90 + 1) )
                  _InterlockedIncrement((volatile signed __int32 *)(*((_QWORD *)&v90 + 1) + 8LL));
                v102 = v90;
                v81 = winrt::impl::duplicate_hstring((winrt::impl *)v37, v39);
                v53 = CMidi2KSAggregateMidiConfigurationManager::ProcessCustomProperties(
                        (_DWORD)this,
                        (unsigned int)&v81,
                        (unsigned int)&v102,
                        (unsigned int)v79,
                        (__int64)v100,
                        (__int64)&v91,
                        (__int64)&v101,
                        v78);
                if ( v53 < 0 )
                  wil::details::in1diag3::_Log_Hr(
                    retaddr,
                    (void *)0x121,
                    (unsigned int)"avcore\\midi2\\transport\\ksaggregatetransport\\midi2.ksaggregatemidiconfigurationmanager.cpp",
                    (const char *)(unsigned int)v53,
                    v77);
                if ( 0xAAAAAAAAAAAAAAABuLL * ((__int64)(*((_QWORD *)&v91 + 1) - v91) >> 4) && v37 )
                {
                  v59 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 5) + 48LL))(
                          *((_QWORD *)this + 5),
                          *((_QWORD *)v37 + 2));
                  if ( v59 < 0 )
                  {
                    if ( v59 != -2147023728 )
                    {
                      v63 = (_DWORD *)*((_QWORD *)MidiKSAggregateTransportTelemetryProvider::Instance() + 1);
                      if ( *v63 > 2u )
                      {
                        if ( *(_QWORD *)v90 )
                          v36 = *(const wchar_t **)(*(_QWORD *)v90 + 16LL);
                        p_lpMem = (const char *)v36;
                        LODWORD(lpMem) = v59;
                        v89[0] = L"Error updating device properties";
                        v81 = this;
                        *(_QWORD *)v79 = "CMidi2KSAggregateMidiConfigurationManager::UpdateConfiguration";
                        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
                          (_DWORD)v63,
                          (unsigned int)qword_180088F98,
                          (_DWORD)v63,
                          v64,
                          (__int64)v79,
                          (__int64)&v81,
                          (__int64)v89,
                          (__int64)&lpMem,
                          (__int64)&p_lpMem);
                      }
                      wil::details::in1diag3::Return_Hr(
                        retaddr,
                        (void *)0x151,
                        (unsigned int)"avcore\\midi2\\transport\\ksaggregatetransport\\midi2.ksaggregatemidiconfigurationmanager.cpp",
                        (const char *)0x80004005LL,
                        v77);
                      v65 = _InterlockedDecrement((volatile signed __int32 *)v37 + 6);
                      if ( v65 )
                      {
                        if ( v65 < 0 )
LABEL_172:
                          abort();
                      }
                      else
                      {
                        v66 = WINRT_IMPL_GetProcessHeap();
                        WINRT_IMPL_HeapFree(v66, 0, v37);
                      }
                      std::vector<_DEVPROPERTY>::~vector<_DEVPROPERTY>(&v91);
                      v67 = (volatile signed __int32 *)*((_QWORD *)&v90 + 1);
                      if ( *((_QWORD *)&v90 + 1) )
                      {
                        if ( !_InterlockedDecrement((volatile signed __int32 *)(*((_QWORD *)&v90 + 1) + 8LL)) )
                        {
                          (**(void (__fastcall ***)(volatile signed __int32 *))v67)(v67);
                          if ( !_InterlockedDecrement(v67 + 3) )
                            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v67 + 8LL))(v67);
                        }
                      }
                      v68 = (volatile signed __int32 *)*((_QWORD *)&v101 + 1);
                      if ( *((_QWORD *)&v101 + 1) )
                      {
                        if ( !_InterlockedDecrement((volatile signed __int32 *)(*((_QWORD *)&v101 + 1) + 8LL)) )
                        {
                          (**(void (__fastcall ***)(volatile signed __int32 *))v68)(v68);
                          if ( !_InterlockedDecrement(v68 + 3) )
                            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v68 + 8LL))(v68);
                        }
                      }
                      v69 = *(volatile signed __int32 **)&v100[2];
                      if ( *(_QWORD *)&v100[2] )
                      {
                        if ( !_InterlockedDecrement((volatile signed __int32 *)(*(_QWORD *)&v100[2] + 8LL)) )
                        {
                          (**(void (__fastcall ***)(volatile signed __int32 *))v69)(v69);
                          if ( !_InterlockedDecrement(v69 + 3) )
                            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v69 + 8LL))(v69);
                        }
                      }
                      if ( v86 )
                        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v86);
                      if ( v82 )
                        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v82);
                      if ( v84 )
                        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v84);
                      if ( v88 )
                        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v88);
                      if ( v83 )
                        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v83);
                      if ( v80 )
                        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v80);
                      return 2147500037LL;
                    }
                  }
                  else
                  {
                    v60 = (_DWORD *)*((_QWORD *)MidiKSAggregateTransportTelemetryProvider::Instance() + 1);
                    if ( *v60 > 4u )
                    {
                      if ( *(_QWORD *)v90 )
                        v62 = *(const wchar_t **)(*(_QWORD *)v90 + 16LL);
                      else
                        v62 = &S1;
                      *(_QWORD *)v79 = v62;
                      v85 = L"Properties updated";
                      v89[0] = this;
                      p_lpMem = "CMidi2KSAggregateMidiConfigurationManager::UpdateConfiguration";
                      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
                        (_DWORD)v60,
                        (unsigned int)word_180088FDA,
                        (_DWORD)v60,
                        v61,
                        (__int64)&p_lpMem,
                        (__int64)v89,
                        (__int64)&v85,
                        (__int64)v79);
                    }
                  }
                }
                if ( v37 )
                {
                  v54 = _InterlockedDecrement((volatile signed __int32 *)v37 + 6);
                  if ( v54 )
                  {
                    if ( v54 < 0 )
                      goto LABEL_172;
                  }
                  else
                  {
                    v55 = WINRT_IMPL_GetProcessHeap();
                    WINRT_IMPL_HeapFree(v55, 0, v37);
                  }
                }
                std::vector<_DEVPROPERTY>::~vector<_DEVPROPERTY>(&v91);
                v56 = (volatile signed __int32 *)*((_QWORD *)&v90 + 1);
                if ( *((_QWORD *)&v90 + 1) )
                {
                  if ( !_InterlockedDecrement((volatile signed __int32 *)(*((_QWORD *)&v90 + 1) + 8LL)) )
                  {
                    (**(void (__fastcall ***)(volatile signed __int32 *))v56)(v56);
                    if ( !_InterlockedDecrement(v56 + 3) )
                      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v56 + 8LL))(v56);
                  }
                }
                v57 = (volatile signed __int32 *)*((_QWORD *)&v101 + 1);
                if ( *((_QWORD *)&v101 + 1) )
                {
                  if ( !_InterlockedDecrement((volatile signed __int32 *)(*((_QWORD *)&v101 + 1) + 8LL)) )
                  {
                    (**(void (__fastcall ***)(volatile signed __int32 *))v57)(v57);
                    if ( !_InterlockedDecrement(v57 + 3) )
                      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v57 + 8LL))(v57);
                  }
                }
                v58 = *(volatile signed __int32 **)&v100[2];
                if ( *(_QWORD *)&v100[2] )
                {
                  if ( !_InterlockedDecrement((volatile signed __int32 *)(*(_QWORD *)&v100[2] + 8LL)) )
                  {
                    (**(void (__fastcall ***)(volatile signed __int32 *))v58)(v58);
                    if ( !_InterlockedDecrement(v58 + 3) )
                      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v58 + 8LL))(v58);
                  }
                }
              }
              if ( v86 )
                winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v86);
            }
            if ( v82 )
              winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v82);
            if ( v84 )
              winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v84);
            v104 = ++v34;
            v35 = (int)lpMem;
          }
        }
        if ( v88 )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v88);
        if ( v83 )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v83);
        WindowsMidiServicesInternal::JsonStringifyObjectToOutParam((WindowsMidiServicesInternal *)&v80, v3, v30);
        if ( v80 )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v80);
        result = 0;
      }
      else
      {
        if ( lpMem )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&lpMem);
        v28 = CMidi2KSAggregateMidiConfigurationManager::ProcessCommand(
                v26,
                (const struct winrt::Windows::Data::Json::JsonObject *)&v83,
                (struct winrt::Windows::Data::Json::JsonObject *)&v80);
        WindowsMidiServicesInternal::JsonStringifyObjectToOutParam((WindowsMidiServicesInternal *)&v80, v3, v29);
        if ( v83 )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v83);
        if ( v80 )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v80);
        result = v28;
      }
    }
    else
    {
      v22 = (_DWORD *)*((_QWORD *)MidiKSAggregateTransportTelemetryProvider::Instance() + 1);
      if ( *v22 > 2u )
      {
        lpMem = L"Failed to parse Configuration JSON";
        v81 = this;
        *(_QWORD *)v79 = "CMidi2KSAggregateMidiConfigurationManager::UpdateConfiguration";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>>(
          (_DWORD)v22,
          (unsigned int)byte_180089011,
          v23,
          v24,
          (__int64)v79,
          (__int64)&v81,
          (__int64)&lpMem);
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xD9,
        (unsigned int)"avcore\\midi2\\transport\\ksaggregatetransport\\midi2.ksaggregatemidiconfigurationmanager.cpp",
        (const char *)0x80070057LL,
        v76);
      if ( v83 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v83);
      if ( v80 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v80);
      result = 2147942487LL;
    }
  }
  catch ( const std::exception *v106 )
  {
    v70 = (_DWORD *)*((_QWORD *)MidiKSAggregateTransportTelemetryProvider::Instance() + 1);
    if ( *v70 > 2u )
    {
      lpMem = (LPVOID)(*(__int64 (__fastcall **)(const std::exception *))(*(_QWORD *)v106 + 8LL))(v106);
      p_lpMem = (const char *)L"std exception processing json";
      v89[0] = this;
      v81 = (struct winrt::impl::hstring_header *)"CMidi2KSAggregateMidiConfigurationManager::UpdateConfiguration";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
        (_DWORD)v70,
        (unsigned int)&dword_180088F54,
        v71,
        v72,
        (__int64)&v81,
        (__int64)v89,
        (__int64)&p_lpMem,
        (__int64)&lpMem,
        (__int64)&v109);
    }
    goto LABEL_173;
  }
  catch ( ... )
  {
    v73 = (_DWORD *)*((_QWORD *)MidiKSAggregateTransportTelemetryProvider::Instance() + 1);
    if ( *v73 > 2u )
    {
      lpMem = L"Other exception processing json";
      p_lpMem = (const char *)this;
      v89[0] = "CMidi2KSAggregateMidiConfigurationManager::UpdateConfiguration";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
        (_DWORD)v73,
        (unsigned int)byte_180088F1B,
        v74,
        v75,
        (__int64)v89,
        (__int64)&p_lpMem,
        (__int64)&lpMem,
        (__int64)&v109);
    }
LABEL_173:
    if ( v80 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v80);
    return 2147500037LL;
  }
  return result;
}

```

## disassembly

```asm
0x18001e790  mov     rax, rsp
0x18001e793  mov     [rax+18h], r8
0x18001e797  mov     [rax+10h], rdx
0x18001e79b  mov     [rax+8], rcx
0x18001e79f  push    rbx
0x18001e7a0  push    rsi
0x18001e7a1  push    rdi
0x18001e7a2  push    r12
0x18001e7a4  push    r13
0x18001e7a6  push    r14
0x18001e7a8  push    r15
0x18001e7aa  sub     rsp, 180h
0x18001e7b1  mov     r15, r8
0x18001e7b4  mov     rbx, rdx
0x18001e7b7  mov     r13, rcx
0x18001e7ba  xor     esi, esi
0x18001e7bc  mov     [rax+20h], esi
0x18001e7bf  test    rdx, rdx
0x18001e7c2  jnz     short loc_18001E7EC
0x18001e7c4  mov     edx, 0B6h; void *
0x18001e7c9  mov     ebx, 80070057h
0x18001e7ce  lea     r8, aAvcoreMidi2Tra_2; "avcore\\midi2\\transport\\ksaggregatetr"...
0x18001e7d5  mov     r9d, ebx; char *
0x18001e7d8  mov     rcx, [rsp+1B8h]; this
0x18001e7e0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001e7e5  mov     eax, ebx
0x18001e7e7  jmp     loc_18001F585
0x18001e7ec  test    r15, r15
0x18001e7ef  jnz     short loc_18001E7F8
0x18001e7f1  mov     edx, 0B7h
0x18001e7f6  jmp     short loc_18001E7C9
0x18001e7f8  or      r12, 0FFFFFFFFFFFFFFFFh
0x18001e7fc  mov     rax, r12
0x18001e7ff  inc     rax
0x18001e802  cmp     [rdx+rax*2], si
0x18001e806  jnz     short loc_18001E7FF
0x18001e808  test    rax, rax
0x18001e80b  jnz     short loc_18001E814
0x18001e80d  mov     edx, 0B8h
0x18001e812  jmp     short loc_18001E7C9
0x18001e814  call    ?Instance@MidiKSAggregateTransportTelemetryProvider@@KAPEAV1@XZ; MidiKSAggregateTransportTelemetryProvider::Instance(void)
0x18001e819  mov     rcx, [rax+8]
0x18001e81d  mov     eax, [rcx]
0x18001e81f  cmp     eax, 4
0x18001e822  jbe     short loc_18001E86C
0x18001e824  mov     [rsp+1B8h+lpMem], rbx
0x18001e82c  mov     [rsp+1B8h+var_158], r13
0x18001e831  lea     r14, aCmidi2ksaggreg_14; "CMidi2KSAggregateMidiConfigurationManag"...
0x18001e838  mov     qword ptr [rsp+1B8h+var_168], r14
0x18001e83d  lea     rax, [rsp+1B8h+lpMem]
0x18001e845  mov     [rsp+1B8h+var_188], rax
0x18001e84a  lea     rax, [rsp+1B8h+var_158]
0x18001e84f  mov     [rsp+1B8h+var_190], rax
0x18001e854  lea     rax, [rsp+1B8h+var_168]
0x18001e859  mov     qword ptr [rsp+1B8h+var_198], rax
0x18001e85e  lea     rdx, dword_180089044
0x18001e865  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &)
0x18001e86a  jmp     short loc_18001E873
0x18001e86c  lea     r14, aCmidi2ksaggreg_14; "CMidi2KSAggregateMidiConfigurationManag"...
0x18001e873  cmp     [r13+28h], rsi
0x18001e877  jnz     short loc_18001E888
0x18001e879  mov     ebx, 80004003h
0x18001e87e  mov     edx, 0C3h
0x18001e883  jmp     loc_18001E7CE
0x18001e888  lea     rcx, [rsp+1B8h+var_160]
0x18001e88d  call    ?BuildConfigurationResponseObject@WindowsMidiServicesInternal@@YA?AUJsonObject@Json@Data@Windows@winrt@@_N@Z; WindowsMidiServicesInternal::BuildConfigurationResponseObject(bool)
0x18001e892  nop
0x18001e893  lea     rcx, [rsp+1B8h+var_148]; this
0x18001e898  call    ??0JsonObject@Json@Data@Windows@winrt@@QEAA@XZ; winrt::Windows::Data::Json::JsonObject::JsonObject(void)
0x18001e89d  nop
0x18001e89e  mov     rdx, rbx; unsigned __int16 *
0x18001e8a1  lea     rcx, [rsp+1B8h+lpMem]; this
0x18001e8a9  call    ??0hstring@winrt@@QEAA@PEBG@Z; winrt::hstring::hstring(ushort const *)
0x18001e8ae  nop
0x18001e8af  mov     rcx, [rsp+1B8h+lpMem]; this
0x18001e8b7  call    ?duplicate_hstring@impl@winrt@@YAPEAUhstring_header@12@PEAU312@@Z; winrt::impl::duplicate_hstring(winrt::impl::hstring_header *)
0x18001e8bc  mov     rbx, rax
0x18001e8bf  mov     [rsp+1B8h+var_128], rax
0x18001e8c7  mov     [rsp+1B8h+var_D8], rax
0x18001e8cf  lea     rax, [rsp+1B8h+var_D8]
0x18001e8d7  mov     qword ptr [rsp+1B8h+var_A8], rax
0x18001e8df  lea     rax, [rsp+1B8h+var_148]
0x18001e8e4  mov     qword ptr [rsp+1B8h+var_A8+8], rax
0x18001e8ec  lea     rax, qword_180096B48
0x18001e8f3  mov     [rsp+1B8h+var_118], rax
0x18001e8fb  lock inc cs:qword_180096B48
0x18001e903  cmp     cs:??$factory_cache_entry_v@UJsonObject@Json@Data@Windows@winrt@@UIJsonObjectStatics@2345@@impl@winrt@@3U?$factory_cache_entry@UJsonObject@Json@Data@Windows@winrt@@UIJsonObjectStatics@2345@@12@A, rsi; factory_cache_entry<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Data::Json::IJsonObjectStatics>::winrt::factory_cache_entry<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Data::Json::IJsonObjectStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Data::Json::IJsonObjectStatics>
0x18001e90a  jz      short loc_18001E92D
0x18001e90c  lea     rdx, ??$factory_cache_entry_v@UJsonObject@Json@Data@Windows@winrt@@UIJsonObjectStatics@2345@@impl@winrt@@3U?$factory_cache_entry@UJsonObject@Json@Data@Windows@winrt@@UIJsonObjectStatics@2345@@12@A; factory_cache_entry<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Data::Json::IJsonObjectStatics>::winrt::factory_cache_entry<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Data::Json::IJsonObjectStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Data::Json::IJsonObjectStatics>
0x18001e913  lea     rcx, [rsp+1B8h+var_A8]
0x18001e91b  call    ??R_lambda_1_@?1??TryParse@JsonObject@Json@Data@Windows@winrt@@SA@AEBUhstring@param@6@AEAU23456@@Z@QEBA@AEBUIJsonObjectStatics@3456@@Z; `winrt::Windows::Data::Json::JsonObject::TryParse(winrt::param::hstring const &,winrt::Windows::Data::Json::JsonObject &)'::`2'::_lambda_1_::operator()(winrt::Windows::Data::Json::IJsonObjectStatics const &)
0x18001e920  mov     dil, al
0x18001e923  lock add cs:qword_180096B48, r12
0x18001e92b  jmp     short loc_18001E945
0x18001e92d  lock add cs:qword_180096B48, r12
0x18001e935  lea     rdx, [rsp+1B8h+var_A8]
0x18001e93d  call    ??$call@AEAV_lambda_1_@?1??TryParse@JsonObject@Json@Data@Windows@winrt@@SA@AEBUhstring@param@7@AEAU34567@@Z@@?$factory_cache_entry@UJsonObject@Json@Data@Windows@winrt@@UIJsonObjectStatics@2345@@impl@winrt@@QEAA?A_PAEAV_lambda_1_@?1??TryParse@JsonObject@Json@Data@Windows@2@SA@AEBUhstring@param@2@AEAU56782@@Z@@Z
0x18001e942  mov     dil, al
0x18001e945  test    rbx, rbx
0x18001e948  jz      short loc_18001E96F
0x18001e94a  mov     eax, r12d
0x18001e94d  lock xadd [rbx+18h], eax
0x18001e952  sub     eax, 1
0x18001e955  jnz     loc_18001ED30
0x18001e95b  nop
0x18001e95c  call    WINRT_IMPL_GetProcessHeap
0x18001e961  mov     rcx, rax; hHeap
0x18001e964  mov     r8, rbx; lpMem
0x18001e967  xor     edx, edx; dwFlags
0x18001e969  call    WINRT_IMPL_HeapFree
0x18001e96e  nop
0x18001e96f  mov     rbx, [rsp+1B8h+lpMem]
0x18001e977  test    rbx, rbx
0x18001e97a  jz      short loc_18001E9A0
0x18001e97c  mov     eax, r12d
0x18001e97f  lock xadd [rbx+18h], eax
0x18001e984  sub     eax, 1
0x18001e987  jnz     loc_18001ED3F
0x18001e98d  nop
0x18001e98e  call    WINRT_IMPL_GetProcessHeap
0x18001e993  mov     rcx, rax; hHeap
0x18001e996  mov     r8, rbx; lpMem
0x18001e999  xor     edx, edx; dwFlags
0x18001e99b  call    WINRT_IMPL_HeapFree
0x18001e9a0  test    dil, dil
0x18001e9a3  jnz     loc_18001EA4B
0x18001e9a9  call    ?Instance@MidiKSAggregateTransportTelemetryProvider@@KAPEAV1@XZ; MidiKSAggregateTransportTelemetryProvider::Instance(void)
0x18001e9ae  mov     rcx, [rax+8]
0x18001e9b2  mov     eax, [rcx]
0x18001e9b4  cmp     eax, 2
0x18001e9b7  jbe     short loc_18001E9FF
0x18001e9b9  lea     rax, aFailedToParseC; "Failed to parse Configuration JSON"
0x18001e9c0  mov     [rsp+1B8h+lpMem], rax
0x18001e9c8  mov     [rsp+1B8h+var_158], r13
0x18001e9cd  mov     qword ptr [rsp+1B8h+var_168], r14
0x18001e9d2  lea     rax, [rsp+1B8h+lpMem]
0x18001e9da  mov     [rsp+1B8h+var_188], rax
0x18001e9df  lea     rax, [rsp+1B8h+var_158]
0x18001e9e4  mov     [rsp+1B8h+var_190], rax
0x18001e9e9  lea     rax, [rsp+1B8h+var_168]
0x18001e9ee  mov     qword ptr [rsp+1B8h+var_198], rax; int
0x18001e9f3  lea     rdx, byte_180089011
0x18001e9fa  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &)
0x18001e9ff  mov     rcx, [rsp+1B8h]; this
0x18001ea07  mov     ebx, 80070057h
0x18001ea0c  mov     r9d, ebx; char *
0x18001ea0f  lea     r8, aAvcoreMidi2Tra_2; "avcore\\midi2\\transport\\ksaggregatetr"...
0x18001ea16  mov     edx, 0D9h; void *
0x18001ea1b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001ea20  nop
0x18001ea21  cmp     [rsp+1B8h+var_148], rsi
0x18001ea26  jz      short loc_18001EA33
0x18001ea28  lea     rcx, [rsp+1B8h+var_148]
0x18001ea2d  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001ea32  nop
0x18001ea33  cmp     [rsp+1B8h+var_160], rsi
0x18001ea38  jz      short loc_18001EA44
0x18001ea3a  lea     rcx, [rsp+1B8h+var_160]
0x18001ea3f  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001ea44  mov     eax, ebx
0x18001ea46  jmp     loc_18001F585
0x18001ea4b  mov     rcx, [rsp+1B8h+var_148]
0x18001ea50  mov     [rsp+1B8h+lpMem], rcx
0x18001ea58  test    rcx, rcx
0x18001ea5b  jz      short loc_18001EA69
0x18001ea5d  mov     rax, [rcx]
0x18001ea60  mov     rax, [rax+8]
0x18001ea64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ea69  lea     rax, [rsp+1B8h+lpMem]
0x18001ea71  mov     [rsp+1B8h+var_128], rax
0x18001ea79  mov     qword ptr [rsp+1B8h+var_168], rsi
0x18001ea7e  mov     [rsp+1B8h+var_158], rsi
0x18001ea83  mov     dword ptr [rsp+1B8h+var_F8+8], 1
0x18001ea8e  mov     dword ptr [rsp+1B8h+var_F8+0Ch], 10h
0x18001ea99  lea     rax, aTransportcomma; "transportCommand"
0x18001eaa0  mov     [rsp+1B8h+var_E0], rax
0x18001eaa8  lea     rax, [rsp+1B8h+var_F8+8]
0x18001eab0  mov     qword ptr [rsp+1B8h+var_F8], rax
0x18001eab8  lea     r9, [rsp+1B8h+var_158]
0x18001eabd  lea     r8, [rsp+1B8h+var_F8]
0x18001eac5  lea     rdx, [rsp+1B8h+var_138]
0x18001eacd  lea     rcx, [rsp+1B8h+lpMem]
0x18001ead5  call    ?GetNamedObject@?$consume_Windows_Data_Json_IJsonObjectWithDefaultValues@UJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@AEBUJsonObject@Json@Data@Windows@3@@Z; winrt::impl::consume_Windows_Data_Json_IJsonObjectWithDefaultValues<winrt::Windows::Data::Json::JsonObject>::GetNamedObject(winrt::param::hstring const &,winrt::Windows::Data::Json::JsonObject const &)
0x18001eada  lea     rdx, [rsp+1B8h+var_168]
0x18001eadf  mov     rcx, rax
0x18001eae2  call    ??8Foundation@Windows@winrt@@YA_NAEBUIUnknown@012@0@Z; winrt::Windows::Foundation::operator==(winrt::Windows::Foundation::IUnknown const &,winrt::Windows::Foundation::IUnknown const &)
0x18001eae7  mov     bl, al
0x18001eae9  cmp     [rsp+1B8h+var_138], rsi
0x18001eaf1  jz      short loc_18001EB01
0x18001eaf3  lea     rcx, [rsp+1B8h+var_138]
0x18001eafb  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001eb00  nop
0x18001eb01  test    bl, bl
0x18001eb03  jnz     short loc_18001EB65
0x18001eb05  cmp     [rsp+1B8h+lpMem], rsi
0x18001eb0d  jz      short loc_18001EB1C
0x18001eb0f  lea     rcx, [rsp+1B8h+lpMem]
0x18001eb17  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001eb1c  lea     r8, [rsp+1B8h+var_160]; struct winrt::Windows::Data::Json::JsonObject *
0x18001eb21  lea     rdx, [rsp+1B8h+var_148]; struct winrt::Windows::Data::Json::JsonObject *
0x18001eb26  call    ?ProcessCommand@CMidi2KSAggregateMidiConfigurationManager@@AEAAJAEBUJsonObject@Json@Data@Windows@winrt@@AEAU23456@@Z; CMidi2KSAggregateMidiConfigurationManager::ProcessCommand(winrt::Windows::Data::Json::JsonObject const &,winrt::Windows::Data::Json::JsonObject &)
0x18001eb2b  mov     ebx, eax
0x18001eb2d  mov     rdx, r15; struct winrt::Windows::Data::Json::JsonObject *
0x18001eb30  lea     rcx, [rsp+1B8h+var_160]; this
0x18001eb35  call    ?JsonStringifyObjectToOutParam@WindowsMidiServicesInternal@@YA_NAEBUJsonObject@Json@Data@Windows@winrt@@PEAPEAG@Z; WindowsMidiServicesInternal::JsonStringifyObjectToOutParam(winrt::Windows::Data::Json::JsonObject const &,ushort * *)
0x18001eb3a  nop
0x18001eb3b  cmp     [rsp+1B8h+var_148], rsi
0x18001eb40  jz      short loc_18001EB4D
0x18001eb42  lea     rcx, [rsp+1B8h+var_148]
0x18001eb47  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001eb4c  nop
0x18001eb4d  cmp     [rsp+1B8h+var_160], rsi
0x18001eb52  jz      short loc_18001EB5E
0x18001eb54  lea     rcx, [rsp+1B8h+var_160]
0x18001eb59  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001eb5e  mov     eax, ebx
0x18001eb60  jmp     loc_18001F585
0x18001eb65  cmp     [rsp+1B8h+lpMem], rsi
0x18001eb6d  jz      short loc_18001EB7C
0x18001eb6f  lea     rcx, [rsp+1B8h+lpMem]
0x18001eb77  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001eb7c  mov     [rsp+1B8h+lpMem], rsi
0x18001eb84  mov     [rsp+1B8h+var_D0], 1
0x18001eb8f  mov     [rsp+1B8h+var_CC], 6
0x18001eb9a  lea     rax, aUpdate; "update"
0x18001eba1  mov     [rsp+1B8h+var_C0], rax
0x18001eba9  lea     rax, [rsp+1B8h+var_D0]
0x18001ebb1  mov     [rsp+1B8h+var_D8], rax
0x18001ebb9  lea     r9, [rsp+1B8h+lpMem]
0x18001ebc1  lea     r8, [rsp+1B8h+var_D8]
0x18001ebc9  lea     rdx, [rsp+1B8h+var_120]
0x18001ebd1  lea     rcx, [rsp+1B8h+var_148]
0x18001ebd6  call    ?GetNamedArray@?$consume_Windows_Data_Json_IJsonObjectWithDefaultValues@UJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@AEBUJsonArray@Json@Data@Windows@3@@Z; winrt::impl::consume_Windows_Data_Json_IJsonObjectWithDefaultValues<winrt::Windows::Data::Json::JsonObject>::GetNamedArray(winrt::param::hstring const &,winrt::Windows::Data::Json::JsonArray const &)
0x18001ebdb  nop
0x18001ebdc  mov     [rsp+1B8h+var_158], rsi
0x18001ebe1  mov     dword ptr [rsp+1B8h+lpMem], 1
0x18001ebec  lea     rdx, [rsp+1B8h+var_158]
0x18001ebf1  lea     rcx, [rsp+1B8h+var_120]
0x18001ebf9  call    ??8Foundation@Windows@winrt@@YA_NAEBUIUnknown@012@0@Z; winrt::Windows::Foundation::operator==(winrt::Windows::Foundation::IUnknown const &,winrt::Windows::Foundation::IUnknown const &)
0x18001ebfe  test    al, al
0x18001ec00  jnz     short loc_18001EC15
0x18001ec02  lea     rcx, [rsp+1B8h+var_120]
0x18001ec0a  call    ?Size@?$consume_Windows_Foundation_Collections_IVector@UJsonArray@Json@Data@Windows@winrt@@UIJsonValue@2345@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Data::Json::JsonArray,winrt::Windows::Data::Json::IJsonValue>::Size(void)
0x18001ec0f  test    eax, eax
0x18001ec11  mov     al, 1
0x18001ec13  jnz     short loc_18001EC18
0x18001ec15  mov     al, sil
0x18001ec18  mov     r14d, esi
0x18001ec1b  test    al, al
0x18001ec1d  jz      loc_18001ECE0
0x18001ec23  lea     rax, [rsp+1B8h+var_120]
0x18001ec2b  mov     [rsp+1B8h+var_68], rax
0x18001ec33  mov     r15d, esi
0x18001ec36  mov     [rsp+1B8h+var_60], esi
0x18001ec3d  lea     rcx, [rsp+1B8h+var_120]
0x18001ec45  call    ?Size@?$consume_Windows_Foundation_Collections_IVector@UJsonArray@Json@Data@Windows@winrt@@UIJsonValue@2345@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Data::Json::JsonArray,winrt::Windows::Data::Json::IJsonValue>::Size(void)
0x18001ec4a  mov     dword ptr [rsp+1B8h+lpMem], eax
0x18001ec51  lea     r12, S1
0x18001ec58  cmp     r15d, eax
0x18001ec5b  jnz     loc_18001ED4E
0x18001ec61  mov     dl, 1
0x18001ec63  lea     rcx, [rsp+1B8h+lpMem]; bool
0x18001ec6b  call    ?CreateBooleanValue@JsonValue@Json@Data@Windows@winrt@@SA@_N@Z; winrt::Windows::Data::Json::JsonValue::CreateBooleanValue(bool)
0x18001ec70  nop
0x18001ec71  mov     [rsp+1B8h+var_D0], 1
0x18001ec7c  mov     [rsp+1B8h+var_CC], 7
0x18001ec87  lea     rax, aSuccess; "success"
0x18001ec8e  mov     [rsp+1B8h+var_C0], rax
0x18001ec96  lea     rax, [rsp+1B8h+var_D0]
0x18001ec9e  mov     [rsp+1B8h+var_D8], rax
0x18001eca6  lea     r8, [rsp+1B8h+lpMem]
0x18001ecae  lea     rdx, [rsp+1B8h+var_D8]
0x18001ecb6  lea     rcx, [rsp+1B8h+var_160]
0x18001ecbb  call    ?SetNamedValue@?$consume_Windows_Data_Json_IJsonObject@UIJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@AEBUIJsonValue@Json@Data@Windows@3@@Z; winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(winrt::param::hstring const &,winrt::Windows::Data::Json::IJsonValue const &)
0x18001ecc0  nop
0x18001ecc1  cmp     [rsp+1B8h+lpMem], rsi
0x18001ecc9  jz      short loc_18001ECD8
0x18001eccb  lea     rcx, [rsp+1B8h+lpMem]
0x18001ecd3  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001ecd8  mov     r15, [rsp+1B8h+arg_10]
0x18001ece0  cmp     [rsp+1B8h+var_120], rsi
0x18001ece8  jz      short loc_18001ECF8
0x18001ecea  lea     rcx, [rsp+1B8h+var_120]
0x18001ecf2  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001ecf7  nop
0x18001ecf8  cmp     [rsp+1B8h+var_148], rsi
0x18001ecfd  jz      short loc_18001ED0A
0x18001ecff  lea     rcx, [rsp+1B8h+var_148]
0x18001ed04  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001ed09  nop
0x18001ed0a  mov     rdx, r15; struct winrt::Windows::Data::Json::JsonObject *
0x18001ed0d  lea     rcx, [rsp+1B8h+var_160]; this
0x18001ed12  call    ?JsonStringifyObjectToOutParam@WindowsMidiServicesInternal@@YA_NAEBUJsonObject@Json@Data@Windows@winrt@@PEAPEAG@Z; WindowsMidiServicesInternal::JsonStringifyObjectToOutParam(winrt::Windows::Data::Json::JsonObject const &,ushort * *)
0x18001ed17  nop
0x18001ed18  cmp     [rsp+1B8h+var_160], rsi
0x18001ed1d  jz      short loc_18001ED29
0x18001ed1f  lea     rcx, [rsp+1B8h+var_160]
0x18001ed24  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001ed29  xor     eax, eax
0x18001ed2b  jmp     loc_18001F585
  ... truncated ...
```
