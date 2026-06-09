# CMidi2VirtualMidiConfigurationManager::UpdateConfiguration(ushort const *,ushort * *)

- ea: `0x18001d680`
- end: `0x18001e500`
- name: `?UpdateConfiguration@CMidi2VirtualMidiConfigurationManager@@UEAAJPEBGPEAPEAG@Z`
- size: `3712`
- prototype: `int(CMidi2VirtualMidiConfigurationManager *__hidden this, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `45`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x1800016dc`
- `0x180001878`
- `0x1800038f0`
- `0x180004694`
- `0x180004718`
- `0x180004784`
- `0x180009784`
- `0x18000b5f8`
- `0x18000bf6c`
- `0x18000cb48`
- `0x18000ce74`
- `0x18000d1ac`
- `0x18000d7cc`
- `0x18000e0a4`
- `0x1800116e0`
- `0x1800137f8`
- `0x180013f64`
- `0x180014484`
- `0x180016348`
- `0x1800194c8`
- `0x18001a3fc`
- `0x18001a798`
- `0x18001adc4`
- `0x18001bad0`
- `0x18001bea8`
- `0x18001c008`
- `0x18001c12c`
- `0x18001c828`
- `0x18001c8f4`
- `0x18001c9a8`
- `0x18001ca5c`
- `0x18001caf8`
- `0x18001cbb4`
- `0x18001cc70`
- `0x18001cd1c`
- `0x18001cdf4`
- `0x18001cec4`
- `0x18001cf9c`
- `0x18001d184`
- `0x18001d33c`
- `0x18001d3d8`
- `0x18001d4f4`
- `0x18001d5b0`
- `0x18001d680`
- `0x180021010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18001da74`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18001e26f`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18001e276`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18001e27d`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18001e284`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18001e28b`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18001e44e`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18001da74`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18001e26f`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18001e276`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18001e27d`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18001e284`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18001e28b`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18001e44e`
- `api-ms-win-crt-private-l1-1-0!_o_isalnum` at `0x18001e01b`
- `api-ms-win-crt-private-l1-1-0!_o_isalnum` at `0x18001e043`
- `api-ms-win-crt-private-l1-1-0!_o_isalnum` at `0x18001e01b`
- `api-ms-win-crt-private-l1-1-0!_o_isalnum` at `0x18001e043`

## string_xrefs

- `0x18001d850`: `avcore\midi2\transport\virtualmiditransport\midi2.virtualmidiconfigurationmanager.cpp`
- `0x18001d9f7`: `avcore\midi2\transport\virtualmiditransport\midi2.virtualmidiconfigurationmanager.cpp`
- `0x18001e29c`: `avcore\midi2\transport\virtualmiditransport\midi2.virtualmidiconfigurationmanager.cpp`
- `0x18001db0c`: `onecoreuap\Internal\BuildMetadata\internal\cppwinrt\winrt\Windows.Data.Json.h`
- `0x18001d6cb`: `CMidi2VirtualMidiConfigurationManager::UpdateConfiguration`
- `0x18001d9a1`: `CMidi2VirtualMidiConfigurationManager::UpdateConfiguration`
- `0x18001e3df`: `CMidi2VirtualMidiConfigurationManager::UpdateConfiguration`
- `0x18001d991`: `Failed to parse Configuration JSON`
- `0x18001da91`: `create`
- `0x18001e359`: `createdDevices`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CMidi2VirtualMidiConfigurationManager::UpdateConfiguration(
        CMidi2VirtualMidiConfigurationManager *this,
        const unsigned __int16 *a2,
        unsigned __int16 **a3)
{
  _DWORD *v6; // rcx
  int v7; // r8d
  int v8; // r9d
  __int64 v9; // rcx
  __int64 v10; // rcx
  unsigned __int16 **v11; // r8
  bool v12; // zf
  volatile signed __int32 *v13; // rbx
  struct winrt::impl::hstring_header *v14; // rdx
  __int64 v15; // rcx
  volatile signed __int32 *v16; // rdi
  char v17; // al
  char v18; // r15
  int v19; // ecx
  HANDLE ProcessHeap; // rax
  int v21; // eax
  HANDLE v22; // rax
  _DWORD *v23; // rcx
  unsigned __int16 **v24; // r8
  int v25; // r9d
  unsigned __int16 **v27; // r8
  unsigned int v28; // r13d
  int v29; // eax
  __int64 v30; // rbx
  int v31; // eax
  __int64 NamedString; // rax
  void *v33; // rdi
  int v34; // eax
  HANDLE v35; // rax
  __int64 v36; // rax
  void *v37; // rdi
  int v38; // eax
  HANDLE v39; // rax
  __int64 v40; // rax
  void *v41; // rdi
  int v42; // eax
  HANDLE v43; // rax
  __int64 v44; // rax
  void *v45; // rdi
  int v46; // eax
  HANDLE v47; // rax
  __int64 v48; // rax
  void *v49; // rdi
  int v50; // eax
  HANDLE v51; // rax
  __int64 v52; // r8
  __int64 v53; // rax
  _WORD *v54; // rdi
  _QWORD *v55; // rdx
  __int64 v56; // rax
  __int64 v57; // rax
  struct TransportState *v58; // rax
  __int64 v59; // rcx
  __int64 v60; // rdi
  volatile signed __int32 *v61; // r14
  __int64 v62; // rax
  char IsUniqueIdInUse; // di
  unsigned __int16 **v64; // r8
  _QWORD *v65; // rcx
  char *v66; // r8
  _WORD *v67; // r15
  _WORD *v68; // r14
  _WORD *v69; // rdi
  char *v70; // rax
  __int64 v71; // r14
  __int64 v72; // rdx
  _QWORD *v73; // rax
  __int64 v74; // rdi
  __int64 v75; // rax
  __int64 v76; // rax
  struct TransportState *v77; // rax
  CMidi2VirtualMidiEndpointManager *v78; // rdi
  int DeviceSideEndpoint; // r14d
  LPVOID v80; // rdi
  _DWORD *v81; // rbx
  unsigned __int16 **v82; // r8
  __int64 v83; // rax
  int v84; // r8d
  int v85; // r9d
  const wchar_t *v86; // rax
  void *v87; // rbx
  int v88; // esi
  HANDLE v89; // rax
  int v90; // [rsp+20h] [rbp-E0h]
  __int64 v91; // [rsp+40h] [rbp-C0h] BYREF
  void (__fastcall ***v92)(_QWORD, __int64 *, LPVOID *); // [rsp+48h] [rbp-B8h] BYREF
  __int64 v93; // [rsp+50h] [rbp-B0h] BYREF
  bool v94[8]; // [rsp+58h] [rbp-A8h] BYREF
  bool v95[8]; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v96; // [rsp+68h] [rbp-98h] BYREF
  LPVOID v97; // [rsp+70h] [rbp-90h] BYREF
  LPVOID v98; // [rsp+78h] [rbp-88h] BYREF
  LPVOID v99; // [rsp+80h] [rbp-80h] BYREF
  LPVOID v100; // [rsp+88h] [rbp-78h] BYREF
  LPVOID v101; // [rsp+90h] [rbp-70h] BYREF
  LPVOID v102; // [rsp+98h] [rbp-68h] BYREF
  void (__fastcall ***v103)(_QWORD, __int64 *, LPVOID *); // [rsp+A0h] [rbp-60h] BYREF
  char *v104; // [rsp+A8h] [rbp-58h] BYREF
  LPVOID v105; // [rsp+B0h] [rbp-50h] BYREF
  LPVOID v106; // [rsp+B8h] [rbp-48h] BYREF
  LPVOID lpMem[2]; // [rsp+C0h] [rbp-40h] BYREF
  __int128 v108; // [rsp+D0h] [rbp-30h]
  int *v109; // [rsp+E0h] [rbp-20h] BYREF
  int v110; // [rsp+E8h] [rbp-18h] BYREF
  int v111; // [rsp+ECh] [rbp-14h]
  const wchar_t *v112; // [rsp+F8h] [rbp-8h]
  _QWORD v113[2]; // [rsp+100h] [rbp+0h] BYREF
  __int64 v114; // [rsp+110h] [rbp+10h]
  unsigned __int64 v115; // [rsp+118h] [rbp+18h]
  _QWORD v116[4]; // [rsp+120h] [rbp+20h] BYREF
  _BYTE v117[16]; // [rsp+140h] [rbp+40h] BYREF
  __int64 v118; // [rsp+150h] [rbp+50h]
  void *v119[2]; // [rsp+160h] [rbp+60h] BYREF
  __int64 v120; // [rsp+170h] [rbp+70h]
  unsigned __int64 v121; // [rsp+178h] [rbp+78h]
  char v122[32]; // [rsp+180h] [rbp+80h] BYREF
  _QWORD v123[4]; // [rsp+1A0h] [rbp+A0h] BYREF
  char v124[32]; // [rsp+1C0h] [rbp+C0h] BYREF
  _BYTE v125[160]; // [rsp+1E0h] [rbp+E0h] BYREF
  _BYTE v126[32]; // [rsp+290h] [rbp+190h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2F8h] [rbp+1F8h]

  v104 = (char *)this;
  v6 = (_DWORD *)*((_QWORD *)MidiVirtualMidiTransportTelemetryProvider::Instance() + 1);
  if ( *v6 > 4u )
  {
    lpMem[0] = (LPVOID)a2;
    v99 = this;
    v98 = "CMidi2VirtualMidiConfigurationManager::UpdateConfiguration";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>>(
      (_DWORD)v6,
      (unsigned int)qword_1800273B8,
      v7,
      v8,
      (__int64)&v98,
      (__int64)&v99,
      (__int64)lpMem);
  }
  _InterlockedIncrement64(&qword_18002DA68);
  if ( winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Foundation::IActivationFactory> )
  {
    `winrt::Windows::Data::Json::JsonObject::JsonObject'::`1'::_lambda_17__::operator()(
      v6,
      &v93,
      &winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Foundation::IActivationFactory>);
    _InterlockedAdd64(&qword_18002DA68, 0xFFFFFFFFFFFFFFFFuLL);
  }
  else
  {
    _InterlockedAdd64(&qword_18002DA68, 0xFFFFFFFFFFFFFFFFuLL);
    lpMem[0] = `winrt::Windows::Data::Json::JsonObject::JsonObject'::`1'::_lambda_17__::_lambda_invoker_cdecl_;
    winrt::impl::factory_cache_entry<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Foundation::IActivationFactory>::call<winrt::Windows::Data::Json::JsonObject (*)(winrt::Windows::Foundation::IActivationFactory const &)>(
      v6,
      &v93,
      lpMem);
  }
  _InterlockedIncrement64(&qword_18002DA68);
  if ( winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Foundation::IActivationFactory> )
  {
    `winrt::Windows::Data::Json::JsonObject::JsonObject'::`1'::_lambda_17__::operator()(
      v9,
      &v91,
      &winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Foundation::IActivationFactory>);
    _InterlockedAdd64(&qword_18002DA68, 0xFFFFFFFFFFFFFFFFuLL);
  }
  else
  {
    _InterlockedAdd64(&qword_18002DA68, 0xFFFFFFFFFFFFFFFFuLL);
    lpMem[0] = `winrt::Windows::Data::Json::JsonObject::JsonObject'::`1'::_lambda_17__::_lambda_invoker_cdecl_;
    winrt::impl::factory_cache_entry<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Foundation::IActivationFactory>::call<winrt::Windows::Data::Json::JsonObject (*)(winrt::Windows::Foundation::IActivationFactory const &)>(
      v9,
      &v91,
      lpMem);
  }
  _InterlockedIncrement64(&qword_18002DA48);
  if ( winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonArray,winrt::Windows::Foundation::IActivationFactory> )
  {
    `winrt::Windows::Data::Json::JsonArray::JsonArray'::`1'::_lambda_16__::operator()(
      v10,
      &v92,
      &winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonArray,winrt::Windows::Foundation::IActivationFactory>);
    _InterlockedAdd64(&qword_18002DA48, 0xFFFFFFFFFFFFFFFFuLL);
  }
  else
  {
    _InterlockedAdd64(&qword_18002DA48, 0xFFFFFFFFFFFFFFFFuLL);
    lpMem[0] = `winrt::Windows::Data::Json::JsonArray::JsonArray'::`1'::_lambda_16__::_lambda_invoker_cdecl_;
    winrt::impl::factory_cache_entry<winrt::Windows::Data::Json::JsonArray,winrt::Windows::Foundation::IActivationFactory>::call<winrt::Windows::Data::Json::JsonArray (*)(winrt::Windows::Foundation::IActivationFactory const &)>(
      v10,
      &v92,
      lpMem);
  }
  winrt::Windows::Data::Json::JsonValue::CreateBooleanValue((bool)v94);
  winrt::Windows::Data::Json::JsonValue::CreateBooleanValue((bool)v95);
  v110 = 1;
  v111 = 7;
  v112 = L"success";
  v109 = &v110;
  winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(
    &v91,
    &v109,
    v94);
  if ( !a2 )
  {
    WindowsMidiServicesInternal::JsonStringifyObjectToOutParam(
      (WindowsMidiServicesInternal *)&v91,
      (const struct winrt::Windows::Data::Json::JsonObject *)a3,
      v11);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x49,
      (unsigned int)"avcore\\midi2\\transport\\virtualmiditransport\\midi2.virtualmidiconfigurationmanager.cpp",
      (const char *)0x80070057LL,
      v90);
    if ( *(_QWORD *)v95 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v95);
    if ( *(_QWORD *)v94 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v94);
    if ( v92 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v92);
    if ( v91 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v91);
    v12 = v93 == 0;
LABEL_44:
    if ( !v12 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v93);
    return 2147942487LL;
  }
  winrt::hstring::hstring((winrt::hstring *)lpMem, a2);
  v13 = (volatile signed __int32 *)lpMem[0];
  v16 = (volatile signed __int32 *)winrt::impl::duplicate_hstring((winrt::impl *)lpMem[0], v14);
  v109 = (int *)v16;
  lpMem[0] = &v109;
  lpMem[1] = &v93;
  _InterlockedIncrement64(&qword_18002DA88);
  if ( winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Data::Json::IJsonObjectStatics> )
  {
    v17 = `winrt::Windows::Data::Json::JsonObject::TryParse'::`2'::_lambda_1_::operator()(
            lpMem,
            &winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Data::Json::IJsonObjectStatics>);
    _InterlockedAdd64(&qword_18002DA88, 0xFFFFFFFFFFFFFFFFuLL);
  }
  else
  {
    _InterlockedAdd64(&qword_18002DA88, 0xFFFFFFFFFFFFFFFFuLL);
    v17 = ___call_AEAV_lambda_1___1__TryParse_JsonObject_Json_Data_Windows_winrt__SA_AEBUhstring_param_7_AEAU34567__Z____factory_cache_entry_UJsonObject_Json_Data_Windows_winrt__UIJsonObjectStatics_2345__impl_winrt__QEAA_A_PAEAV_lambda_1___1__TryParse_JsonObject_Json_Data_Windows_2_SA_AEBUhstring_param_2_AEAU56782__Z__Z(
            v15,
            lpMem);
  }
  v18 = v17;
  if ( v16 )
  {
    v19 = _InterlockedDecrement(v16 + 6);
    if ( v19 )
    {
      if ( v19 < 0 )
        goto LABEL_48;
    }
    else
    {
      ProcessHeap = WINRT_IMPL_GetProcessHeap();
      WINRT_IMPL_HeapFree(ProcessHeap, 0, (LPVOID)v16);
    }
  }
  if ( !v13 )
    goto LABEL_32;
  v21 = _InterlockedDecrement(v13 + 6);
  if ( !v21 )
  {
    v22 = WINRT_IMPL_GetProcessHeap();
    WINRT_IMPL_HeapFree(v22, 0, (LPVOID)v13);
    goto LABEL_32;
  }
  if ( v21 < 0 )
LABEL_48:
    abort();
LABEL_32:
  if ( !v18 )
  {
    v23 = (_DWORD *)*((_QWORD *)MidiVirtualMidiTransportTelemetryProvider::Instance() + 1);
    if ( *v23 > 2u )
    {
      lpMem[0] = (LPVOID)a2;
      v99 = L"Failed to parse Configuration JSON";
      v98 = this;
      v102 = "CMidi2VirtualMidiConfigurationManager::UpdateConfiguration";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
        (_DWORD)v23,
        (unsigned int)&byte_18002737F,
        (_DWORD)v24,
        v25,
        (__int64)&v102,
        (__int64)&v98,
        (__int64)&v99,
        (__int64)lpMem);
    }
    WindowsMidiServicesInternal::JsonStringifyObjectToOutParam(
      (WindowsMidiServicesInternal *)&v91,
      (const struct winrt::Windows::Data::Json::JsonObject *)a3,
      v24);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5B,
      (unsigned int)"avcore\\midi2\\transport\\virtualmiditransport\\midi2.virtualmidiconfigurationmanager.cpp",
      (const char *)0x80070057LL,
      v90);
    if ( *(_QWORD *)v95 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v95);
    if ( *(_QWORD *)v94 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v94);
    if ( v92 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v92);
    if ( v91 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v91);
    v12 = v93 == 0;
    goto LABEL_44;
  }
  lpMem[0] = 0;
  v110 = 1;
  v111 = 6;
  v112 = L"create";
  v109 = &v110;
  winrt::impl::consume_Windows_Data_Json_IJsonObjectWithDefaultValues<winrt::Windows::Data::Json::JsonObject>::GetNamedArray(
    &v93,
    &v96,
    &v109,
    lpMem);
  lpMem[0] = 0;
  if ( (unsigned __int8)winrt::Windows::Foundation::operator==(&v96, lpMem)
    || !(unsigned int)winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Data::Json::JsonArray,winrt::Windows::Data::Json::IJsonValue>::Size(&v96) )
  {
    WindowsMidiServicesInternal::JsonStringifyObjectToOutParam(
      (WindowsMidiServicesInternal *)&v91,
      (const struct winrt::Windows::Data::Json::JsonObject *)a3,
      v27);
    if ( v96 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v96);
    goto LABEL_169;
  }
  v28 = 0;
  v29 = winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Data::Json::JsonArray,winrt::Windows::Data::Json::IJsonValue>::Size(&v96);
  v30 = v96;
  if ( !v29 )
  {
LABEL_132:
    if ( v92 )
    {
      lpMem[0] = 0;
      (**v92)(v92, winrt::impl::guid_v<winrt::Windows::Data::Json::IJsonValue>, lpMem);
      v80 = lpMem[0];
      v100 = lpMem[0];
    }
    else
    {
      v100 = 0;
      v80 = 0;
    }
    v110 = 1;
    v111 = 14;
    v112 = L"createdDevices";
    v109 = &v110;
    winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(
      &v91,
      &v109,
      &v100);
    if ( v80 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v100);
    if ( v30 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v96);
    v81 = (_DWORD *)*((_QWORD *)MidiVirtualMidiTransportTelemetryProvider::Instance() + 1);
    if ( *v81 > 4u )
    {
      v83 = *(_QWORD *)winrt::impl::consume_Windows_Data_Json_IJsonValue<winrt::Windows::Data::Json::IJsonObject>::Stringify(
                         &v91,
                         &v98);
      v86 = v83 ? *(const wchar_t **)(v83 + 16) : &S2;
      lpMem[0] = (LPVOID)v86;
      v99 = v104;
      v104 = "CMidi2VirtualMidiConfigurationManager::UpdateConfiguration";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>>(
        (_DWORD)v81,
        (unsigned int)word_180027332,
        v84,
        v85,
        (__int64)&v104,
        (__int64)&v99,
        (__int64)lpMem);
      v87 = v98;
      if ( v98 )
      {
        v88 = _InterlockedDecrement((volatile signed __int32 *)v98 + 6);
        if ( v88 )
        {
          if ( v88 < 0 )
            abort();
        }
        else
        {
          v89 = WINRT_IMPL_GetProcessHeap();
          WINRT_IMPL_HeapFree(v89, 0, v87);
        }
      }
    }
    WindowsMidiServicesInternal::JsonStringifyObjectToOutParam(
      (WindowsMidiServicesInternal *)&v91,
      (const struct winrt::Windows::Data::Json::JsonObject *)a3,
      v82);
LABEL_169:
    if ( *(_QWORD *)v95 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v95);
    if ( *(_QWORD *)v94 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v94);
    if ( v92 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v92);
    if ( v91 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v91);
    if ( v93 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v93);
    return 0;
  }
  while ( 1 )
  {
    v100 = 0;
    LODWORD(lpMem[0]) = 28;
    lpMem[1] = "onecoreuap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt\\Windows.Data.Json.h";
    *(_QWORD *)&v108 = 0;
    v31 = (*(__int64 (__fastcall **)(__int64, _QWORD, LPVOID *))(*(_QWORD *)v30 + 48LL))(v30, v28, &v100);
    if ( v31 < 0 )
      winrt::throw_hresult((unsigned int)v31, lpMem);
    v97 = v100;
    if ( !v100 )
      goto LABEL_129;
    MidiVirtualDeviceEndpointEntry::MidiVirtualDeviceEndpointEntry((MidiVirtualDeviceEndpointEntry *)v117);
    v116[0] = 0;
    lpMem[1] = (LPVOID)0x1500000001LL;
    *((_QWORD *)&v108 + 1) = L"associationIdentifier";
    lpMem[0] = &lpMem[1];
    NamedString = winrt::impl::consume_Windows_Data_Json_IJsonObjectWithDefaultValues<winrt::Windows::Data::Json::JsonObject>::GetNamedString(
                    &v97,
                    &v105,
                    lpMem,
                    v116);
    std::wstring::operator=<winrt::hstring,0>(v117, NamedString);
    v33 = v105;
    if ( v105 )
    {
      v34 = _InterlockedDecrement((volatile signed __int32 *)v105 + 6);
      if ( v34 )
      {
        if ( v34 < 0 )
          abort();
      }
      else
      {
        v35 = WINRT_IMPL_GetProcessHeap();
        WINRT_IMPL_HeapFree(v35, 0, v33);
      }
      v105 = 0;
    }
    v116[0] = 0;
    lpMem[1] = (LPVOID)0x1000000001LL;
    *((_QWORD *)&v108 + 1) = L"uniqueIdentifier";
    lpMem[0] = &lpMem[1];
    v36 = winrt::impl::consume_Windows_Data_Json_IJsonObjectWithDefaultValues<winrt::Windows::Data::Json::JsonObject>::GetNamedString(
            &v97,
            &v106,
            lpMem,
            v116);
    std::wstring::operator=<winrt::hstring,0>(v123, v36);
    v37 = v106;
    if ( v106 )
    {
      v38 = _InterlockedDecrement((volatile signed __int32 *)v106 + 6);
      if ( v38 )
      {
        if ( v38 < 0 )
          abort();
      }
      else
      {
        v39 = WINRT_IMPL_GetProcessHeap();
        WINRT_IMPL_HeapFree(v39, 0, v37);
      }
      v106 = 0;
    }
    v116[0] = 0;
    lpMem[1] = (LPVOID)0x400000001LL;
    *((_QWORD *)&v108 + 1) = L"name";
    lpMem[0] = &lpMem[1];
    v40 = winrt::impl::consume_Windows_Data_Json_IJsonObjectWithDefaultValues<winrt::Windows::Data::Json::JsonObject>::GetNamedString(
            &v97,
            &v102,
            lpMem,
            v116);
    std::wstring::operator=<winrt::hstring,0>(v119, v40);
    v41 = v102;
    if ( v102 )
    {
      v42 = _InterlockedDecrement((volatile signed __int32 *)v102 + 6);
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
      v102 = 0;
    }
    v116[0] = 0;
    lpMem[1] = (LPVOID)0xB00000001LL;
    *((_QWORD *)&v108 + 1) = L"description";
    lpMem[0] = &lpMem[1];
    v44 = winrt::impl::consume_Windows_Data_Json_IJsonObjectWithDefaultValues<winrt::Windows::Data::Json::JsonObject>::GetNamedString(
            &v97,
            &v98,
            lpMem,
            v116);
    std::wstring::operator=<winrt::hstring,0>(v122, v44);
    v45 = v98;
    if ( v98 )
    {
      v46 = _InterlockedDecrement((volatile signed __int32 *)v98 + 6);
      if ( v46 )
      {
        if ( v46 < 0 )
          abort();
      }
      else
      {
        v47 = WINRT_IMPL_GetProcessHeap();
        WINRT_IMPL_HeapFree(v47, 0, v45);
      }
      v98 = 0;
    }
    v116[0] = 0;
    lpMem[1] = (LPVOID)0xC00000001LL;
    *((_QWORD *)&v108 + 1) = L"manufacturer";
    lpMem[0] = &lpMem[1];
    v48 = winrt::impl::consume_Windows_Data_Json_IJsonObjectWithDefaultValues<winrt::Windows::Data::Json::JsonObject>::GetNamedString(
            &v97,
            &v99,
            lpMem,
            v116);
    std::wstring::operator=<winrt::hstring,0>(v124, v48);
    v49 = v99;
    if ( v99 )
    {
      v50 = _InterlockedDecrement((volatile signed __int32 *)v99 + 6);
      if ( v50 )
      {
        if ( v50 < 0 )
          abort();
      }
      else
      {
        v51 = WINRT_IMPL_GetProcessHeap();
        WINRT_IMPL_HeapFree(v51, 0, v49);
      }
      v99 = 0;
    }
    lpMem[1] = (LPVOID)0x700000001LL;
    *((_QWORD *)&v108 + 1) = L"umpOnly";
    lpMem[0] = &lpMem[1];
    v125[128] = winrt::impl::consume_Windows_Data_Json_IJsonObjectWithDefaultValues<winrt::Windows::Data::Json::JsonObject>::GetNamedBoolean(
                  &v97,
                  lpMem);
    if ( !v118 )
    {
      *(_OWORD *)lpMem = *(_OWORD *)winrt::Windows::Foundation::GuidHelper::CreateNewGuid();
      v53 = WindowsMidiServicesInternal::GuidToString(v126, lpMem);
      std::wstring::operator=(v117, v53);
      std::wstring::~wstring(v126);
    }
    if ( !v120 )
    {
      if ( v121 < 0xF )
      {
        ____Reallocate_for_V_lambda_1___1_____Assign_G___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV23_QEBG_K_Z_PEBG___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV01__KV_lambda_1___1_____Assign_G_01_AEAAAEAV01_QEBG0_Z_PEBG_Z(
          v119,
          15,
          v52,
          L"Unnamed Virtual");
      }
      else
      {
        v54 = v119[0];
        v120 = 15;
        memmove_0(v119[0], L"Unnamed Virtual", 0x1Eu);
        v54[15] = 0;
      }
    }
    if ( v123[2] )
    {
      *(_OWORD *)lpMem = 0;
      v108 = 0;
      v55 = v123;
      if ( v123[3] > 7u )
        v55 = (_QWORD *)v123[0];
      std::wstring::_Construct<1,unsigned short const *>(lpMem, v55);
      std::wstring::operator=(v123, lpMem);
      std::wstring::~wstring(lpMem);
      v56 = std::wstring::wstring(lpMem, v123);
      v57 = WindowsMidiServicesInternal::ToLowerTrimmedWStringCopy(v116, v56);
      std::wstring::operator=(v123, v57);
      std::wstring::~wstring(v116);
      v58 = TransportState::Current();
      v59 = *((_QWORD *)v58 + 1);
      if ( v59 )
        _InterlockedAdd((volatile signed __int32 *)(v59 + 8), 1u);
      v60 = *(_QWORD *)v58;
      v61 = (volatile signed __int32 *)*((_QWORD *)v58 + 1);
      v62 = std::wstring::wstring(v116, v123);
      IsUniqueIdInUse = MidiEndpointTable::IsUniqueIdInUse(v60, v62);
      if ( v61 )
      {
        if ( _InterlockedExchangeAdd(v61 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v61)(v61);
          if ( _InterlockedExchangeAdd(v61 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v61 + 8LL))(v61);
        }
      }
      if ( IsUniqueIdInUse )
      {
        lpMem[1] = (LPVOID)0x700000001LL;
        *((_QWORD *)&v108 + 1) = L"success";
        lpMem[0] = &lpMem[1];
        winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(
          &v91,
          lpMem,
          v94);
      }
    }
    else
    {
      *(_OWORD *)lpMem = *(_OWORD *)winrt::Windows::Foundation::GuidHelper::CreateNewGuid();
      WindowsMidiServicesInternal::GuidToString(v113, lpMem);
      v65 = v113;
      v66 = (char *)v113[0];
      if ( v115 > 7 )
        v65 = (_QWORD *)v113[0];
      v67 = (_WORD *)v65 + v114;
      v68 = v113;
      if ( v115 > 7 )
        v68 = (_WORD *)v113[0];
      if ( v68 != v67 )
      {
        do
        {
          if ( !(unsigned int)_o_isalnum((unsigned __int16)*v68) )
            break;
          ++v68;
        }
        while ( v68 != v67 );
        v66 = (char *)v113[0];
        if ( v68 != v67 )
        {
          v69 = v68 + 1;
          if ( v68 + 1 != v67 )
          {
            do
            {
              if ( (unsigned int)_o_isalnum((unsigned __int16)*v69) )
                *v68++ = *v69;
              ++v69;
            }
            while ( v69 != v67 );
            v66 = (char *)v113[0];
          }
        }
      }
      v70 = (char *)v113;
      if ( v115 > 7 )
        v70 = v66;
      v71 = ((char *)v68 - v70) >> 1;
      v72 = 1;
      if ( v114 == v71 )
        v72 = v114 - v71;
      v73 = v113;
      if ( v115 > 7 )
        v73 = v66;
      v74 = v114 - v72;
      memmove_0((char *)v73 + 2 * v71, (char *)v73 + 2 * v71 + 2 * v72, 2 * (v114 - v72 - v71) + 2);
      v114 = v74;
      v75 = std::wstring::wstring(lpMem, v113);
      v76 = WindowsMidiServicesInternal::ToLowerTrimmedWStringCopy(v116, v75);
      std::wstring::operator=(v123, v76);
      std::wstring::~wstring(v116);
      std::wstring::~wstring(v113);
    }
    WindowsMidiServicesInternal::JsonStringifyObjectToOutParam(
      (WindowsMidiServicesInternal *)&v91,
      (const struct winrt::Windows::Data::Json::JsonObject *)a3,
      v64);
    v77 = TransportState::Current();
    v78 = (CMidi2VirtualMidiEndpointManager *)*((_QWORD *)v77 + 2);
    if ( v78 )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v78 + 8LL))(*((_QWORD *)v77 + 2));
    DeviceSideEndpoint = CMidi2VirtualMidiEndpointManager::CreateDeviceSideEndpoint(
                           v78,
                           (struct MidiVirtualDeviceEndpointEntry *)v117);
    if ( v78 )
      (*(void (__fastcall **)(CMidi2VirtualMidiEndpointManager *))(*(_QWORD *)v78 + 16LL))(v78);
    if ( DeviceSideEndpoint < 0 )
      break;
    lpMem[1] = (LPVOID)0x700000001LL;
    *((_QWORD *)&v108 + 1) = L"success";
    lpMem[0] = &lpMem[1];
    winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(
      &v91,
      lpMem,
      v95);
    *(_OWORD *)lpMem = 0;
    v108 = 0;
    std::wstring::_Construct<1,unsigned short const *>(lpMem, L"id");
    WindowsMidiServicesInternal::JsonCreateSingleWStringPropertyObject(&v103, lpMem, v125);
    std::wstring::~wstring(lpMem);
    if ( v103 )
    {
      lpMem[0] = 0;
      (**v103)(v103, winrt::impl::guid_v<winrt::Windows::Data::Json::IJsonValue>, lpMem);
      v101 = lpMem[0];
    }
    else
    {
      v101 = 0;
    }
    winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Data::Json::JsonArray,winrt::Windows::Data::Json::IJsonValue>::Append(
      &v92,
      &v101);
    if ( v101 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v101);
    if ( v103 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v103);
    MidiVirtualDeviceEndpointEntry::~MidiVirtualDeviceEndpointEntry((MidiVirtualDeviceEndpointEntry *)v117);
LABEL_129:
    if ( v100 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v97);
    if ( ++v28 >= (unsigned int)winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Data::Json::JsonArray,winrt::Windows::Data::Json::IJsonValue>::Size(&v96) )
      goto LABEL_132;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xAD,
    (unsigned int)"avcore\\midi2\\transport\\virtualmiditransport\\midi2.virtualmidiconfigurationmanager.cpp",
    (const char *)(unsigned int)DeviceSideEndpoint,
    v90);
  MidiVirtualDeviceEndpointEntry::~MidiVirtualDeviceEndpointEntry((MidiVirtualDeviceEndpointEntry *)v117);
  winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v97);
  if ( v30 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v96);
  if ( *(_QWORD *)v95 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v95);
  if ( *(_QWORD *)v94 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v94);
  if ( v92 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v92);
  if ( v91 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v91);
  if ( v93 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v93);
  return (unsigned int)DeviceSideEndpoint;
}

```

## disassembly

```asm
0x18001d680  mov     [rsp-8+arg_0], rbx
0x18001d685  push    rbp
0x18001d686  push    rsi
0x18001d687  push    rdi
0x18001d688  push    r12
0x18001d68a  push    r13
0x18001d68c  push    r14
0x18001d68e  push    r15
0x18001d690  lea     rbp, [rsp-1C0h]
0x18001d698  sub     rsp, 2C0h
0x18001d69f  mov     rax, cs:__security_cookie
0x18001d6a6  xor     rax, rsp
0x18001d6a9  mov     [rbp+1F0h+var_40], rax
0x18001d6b0  mov     r12, r8
0x18001d6b3  mov     r14, rdx
0x18001d6b6  mov     r13, rcx
0x18001d6b9  mov     [rbp+1F0h+var_248], rcx
0x18001d6bd  xor     r15d, r15d
0x18001d6c0  call    ?Instance@MidiVirtualMidiTransportTelemetryProvider@@KAPEAV1@XZ; MidiVirtualMidiTransportTelemetryProvider::Instance(void)
0x18001d6c5  mov     rcx, [rax+8]
0x18001d6c9  mov     eax, [rcx]
0x18001d6cb  lea     rdx, aCmidi2virtualm_10; "CMidi2VirtualMidiConfigurationManager::"...
0x18001d6d2  cmp     eax, 4
0x18001d6d5  jbe     short loc_18001D70C
0x18001d6d7  mov     [rbp+1F0h+lpMem], r14
0x18001d6db  mov     [rbp+1F0h+var_270], r13
0x18001d6df  mov     [rsp+2F0h+var_278], rdx
0x18001d6e4  lea     rax, [rbp+1F0h+lpMem]
0x18001d6e8  mov     [rsp+2F0h+var_2C0], rax
0x18001d6ed  lea     rax, [rbp+1F0h+var_270]
0x18001d6f1  mov     [rsp+2F0h+var_2C8], rax
0x18001d6f6  lea     rax, [rsp+2F0h+var_278]
0x18001d6fb  mov     qword ptr [rsp+2F0h+var_2D0], rax; int
0x18001d700  lea     rdx, qword_1800273B8
0x18001d707  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &)
0x18001d70c  lock inc cs:qword_18002DA68
0x18001d714  lea     rbx, ?_lambda_invoker_cdecl_@_lambda_17__@?0???0JsonObject@Json@Data@Windows@winrt@@QEAA@XZ@SA@AEBUIActivationFactory@Foundation@56@@Z; `winrt::Windows::Data::Json::JsonObject::JsonObject(void)'::`1'::_lambda_17__::_lambda_invoker_cdecl_(winrt::Windows::Foundation::IActivationFactory const &)
0x18001d71b  lea     rdx, [rsp+2F0h+var_2A0]
0x18001d720  cmp     cs:??$factory_cache_entry_v@UJsonObject@Json@Data@Windows@winrt@@UIActivationFactory@Foundation@45@@impl@winrt@@3U?$factory_cache_entry@UJsonObject@Json@Data@Windows@winrt@@UIActivationFactory@Foundation@45@@12@A, r15; factory_cache_entry<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Foundation::IActivationFactory>::winrt::factory_cache_entry<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Foundation::IActivationFactory> winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Foundation::IActivationFactory>
0x18001d727  jz      short loc_18001D743
0x18001d729  lea     r8, ??$factory_cache_entry_v@UJsonObject@Json@Data@Windows@winrt@@UIActivationFactory@Foundation@45@@impl@winrt@@3U?$factory_cache_entry@UJsonObject@Json@Data@Windows@winrt@@UIActivationFactory@Foundation@45@@12@A; factory_cache_entry<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Foundation::IActivationFactory>::winrt::factory_cache_entry<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Foundation::IActivationFactory> winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Foundation::IActivationFactory>
0x18001d730  call    ??R_lambda_17__@?0???0JsonObject@Json@Data@Windows@winrt@@QEAA@XZ@QEBA@AEBUIActivationFactory@Foundation@45@@Z; `winrt::Windows::Data::Json::JsonObject::JsonObject(void)'::`1'::_lambda_17__::operator()(winrt::Windows::Foundation::IActivationFactory const &)
0x18001d735  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18001d739  lock add cs:qword_18002DA68, rsi
0x18001d741  jmp     short loc_18001D75C
0x18001d743  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18001d747  lock add cs:qword_18002DA68, rsi
0x18001d74f  mov     [rbp+1F0h+lpMem], rbx
0x18001d753  lea     r8, [rbp+1F0h+lpMem]
0x18001d757  call    ??$call@P6A?AUJsonObject@Json@Data@Windows@winrt@@AEBUIActivationFactory@Foundation@45@@Z@?$factory_cache_entry@UJsonObject@Json@Data@Windows@winrt@@UIActivationFactory@Foundation@45@@impl@winrt@@QEAA?A_P$$QEAP6A?AUJsonObject@Json@Data@Windows@2@AEBUIActivationFactory@Foundation@62@@Z@Z
0x18001d75c  lock inc cs:qword_18002DA68
0x18001d764  lea     rdx, [rsp+2F0h+var_2B0]
0x18001d769  cmp     cs:??$factory_cache_entry_v@UJsonObject@Json@Data@Windows@winrt@@UIActivationFactory@Foundation@45@@impl@winrt@@3U?$factory_cache_entry@UJsonObject@Json@Data@Windows@winrt@@UIActivationFactory@Foundation@45@@12@A, r15; factory_cache_entry<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Foundation::IActivationFactory>::winrt::factory_cache_entry<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Foundation::IActivationFactory> winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Foundation::IActivationFactory>
0x18001d770  jz      short loc_18001D788
0x18001d772  lea     r8, ??$factory_cache_entry_v@UJsonObject@Json@Data@Windows@winrt@@UIActivationFactory@Foundation@45@@impl@winrt@@3U?$factory_cache_entry@UJsonObject@Json@Data@Windows@winrt@@UIActivationFactory@Foundation@45@@12@A; factory_cache_entry<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Foundation::IActivationFactory>::winrt::factory_cache_entry<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Foundation::IActivationFactory> winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Foundation::IActivationFactory>
0x18001d779  call    ??R_lambda_17__@?0???0JsonObject@Json@Data@Windows@winrt@@QEAA@XZ@QEBA@AEBUIActivationFactory@Foundation@45@@Z; `winrt::Windows::Data::Json::JsonObject::JsonObject(void)'::`1'::_lambda_17__::operator()(winrt::Windows::Foundation::IActivationFactory const &)
0x18001d77e  lock add cs:qword_18002DA68, rsi
0x18001d786  jmp     short loc_18001D79D
0x18001d788  lock add cs:qword_18002DA68, rsi
0x18001d790  mov     [rbp+1F0h+lpMem], rbx
0x18001d794  lea     r8, [rbp+1F0h+lpMem]
0x18001d798  call    ??$call@P6A?AUJsonObject@Json@Data@Windows@winrt@@AEBUIActivationFactory@Foundation@45@@Z@?$factory_cache_entry@UJsonObject@Json@Data@Windows@winrt@@UIActivationFactory@Foundation@45@@impl@winrt@@QEAA?A_P$$QEAP6A?AUJsonObject@Json@Data@Windows@2@AEBUIActivationFactory@Foundation@62@@Z@Z
0x18001d79d  lock inc cs:qword_18002DA48
0x18001d7a5  lea     rdx, [rsp+2F0h+var_2A8]
0x18001d7aa  cmp     cs:??$factory_cache_entry_v@UJsonArray@Json@Data@Windows@winrt@@UIActivationFactory@Foundation@45@@impl@winrt@@3U?$factory_cache_entry@UJsonArray@Json@Data@Windows@winrt@@UIActivationFactory@Foundation@45@@12@A, r15; factory_cache_entry<winrt::Windows::Data::Json::JsonArray,winrt::Windows::Foundation::IActivationFactory>::winrt::factory_cache_entry<winrt::Windows::Data::Json::JsonArray,winrt::Windows::Foundation::IActivationFactory> winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonArray,winrt::Windows::Foundation::IActivationFactory>
0x18001d7b1  jz      short loc_18001D7C9
0x18001d7b3  lea     r8, ??$factory_cache_entry_v@UJsonArray@Json@Data@Windows@winrt@@UIActivationFactory@Foundation@45@@impl@winrt@@3U?$factory_cache_entry@UJsonArray@Json@Data@Windows@winrt@@UIActivationFactory@Foundation@45@@12@A; factory_cache_entry<winrt::Windows::Data::Json::JsonArray,winrt::Windows::Foundation::IActivationFactory>::winrt::factory_cache_entry<winrt::Windows::Data::Json::JsonArray,winrt::Windows::Foundation::IActivationFactory> winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonArray,winrt::Windows::Foundation::IActivationFactory>
0x18001d7ba  call    ??R_lambda_16__@?0???0JsonArray@Json@Data@Windows@winrt@@QEAA@XZ@QEBA@AEBUIActivationFactory@Foundation@45@@Z; `winrt::Windows::Data::Json::JsonArray::JsonArray(void)'::`1'::_lambda_16__::operator()(winrt::Windows::Foundation::IActivationFactory const &)
0x18001d7bf  lock add cs:qword_18002DA48, rsi
0x18001d7c7  jmp     short loc_18001D7E5
0x18001d7c9  lock add cs:qword_18002DA48, rsi
0x18001d7d1  lea     rax, ?_lambda_invoker_cdecl_@_lambda_16__@?0???0JsonArray@Json@Data@Windows@winrt@@QEAA@XZ@SA@AEBUIActivationFactory@Foundation@56@@Z; `winrt::Windows::Data::Json::JsonArray::JsonArray(void)'::`1'::_lambda_16__::_lambda_invoker_cdecl_(winrt::Windows::Foundation::IActivationFactory const &)
0x18001d7d8  mov     [rbp+1F0h+lpMem], rax
0x18001d7dc  lea     r8, [rbp+1F0h+lpMem]
0x18001d7e0  call    ??$call@P6A?AUJsonArray@Json@Data@Windows@winrt@@AEBUIActivationFactory@Foundation@45@@Z@?$factory_cache_entry@UJsonArray@Json@Data@Windows@winrt@@UIActivationFactory@Foundation@45@@impl@winrt@@QEAA?A_P$$QEAP6A?AUJsonArray@Json@Data@Windows@2@AEBUIActivationFactory@Foundation@62@@Z@Z
0x18001d7e5  xor     edx, edx
0x18001d7e7  lea     rcx, [rsp+2F0h+var_298]; bool
0x18001d7ec  call    ?CreateBooleanValue@JsonValue@Json@Data@Windows@winrt@@SA@_N@Z; winrt::Windows::Data::Json::JsonValue::CreateBooleanValue(bool)
0x18001d7f1  mov     dl, 1
0x18001d7f3  lea     rcx, [rsp+2F0h+var_290]; bool
0x18001d7f8  call    ?CreateBooleanValue@JsonValue@Json@Data@Windows@winrt@@SA@_N@Z; winrt::Windows::Data::Json::JsonValue::CreateBooleanValue(bool)
0x18001d7fd  mov     [rbp+1F0h+var_208], 1
0x18001d804  mov     [rbp+1F0h+var_204], 7
0x18001d80b  lea     rax, aSuccess; "success"
0x18001d812  mov     [rbp+1F0h+var_1F8], rax
0x18001d816  lea     rax, [rbp+1F0h+var_208]
0x18001d81a  mov     [rbp+1F0h+var_210], rax
0x18001d81e  lea     r8, [rsp+2F0h+var_298]
0x18001d823  lea     rdx, [rbp+1F0h+var_210]
0x18001d827  lea     rcx, [rsp+2F0h+var_2B0]
0x18001d82c  call    ?SetNamedValue@?$consume_Windows_Data_Json_IJsonObject@UIJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@AEBUIJsonValue@Json@Data@Windows@3@@Z; winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(winrt::param::hstring const &,winrt::Windows::Data::Json::IJsonValue const &)
0x18001d831  test    r14, r14
0x18001d834  jnz     short loc_18001D8AE
0x18001d836  mov     rdx, r12; struct winrt::Windows::Data::Json::JsonObject *
0x18001d839  lea     rcx, [rsp+2F0h+var_2B0]; this
0x18001d83e  call    ?JsonStringifyObjectToOutParam@WindowsMidiServicesInternal@@YA_NAEBUJsonObject@Json@Data@Windows@winrt@@PEAPEAG@Z; WindowsMidiServicesInternal::JsonStringifyObjectToOutParam(winrt::Windows::Data::Json::JsonObject const &,ushort * *)
0x18001d843  mov     rcx, [rbp+1F8h]; this
0x18001d84a  mov     r9d, 80070057h; char *
0x18001d850  lea     r8, aAvcoreMidi2Tra; "avcore\\midi2\\transport\\virtualmiditr"...
0x18001d857  lea     edx, [r14+49h]; void *
0x18001d85b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001d860  cmp     qword ptr [rsp+2F0h+var_290], r15
0x18001d865  jz      short loc_18001D871
0x18001d867  lea     rcx, [rsp+2F0h+var_290]
0x18001d86c  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001d871  cmp     qword ptr [rsp+2F0h+var_298], r15
0x18001d876  jz      short loc_18001D882
0x18001d878  lea     rcx, [rsp+2F0h+var_298]
0x18001d87d  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001d882  cmp     [rsp+2F0h+var_2A8], r15
0x18001d887  jz      short loc_18001D893
0x18001d889  lea     rcx, [rsp+2F0h+var_2A8]
0x18001d88e  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001d893  cmp     [rsp+2F0h+var_2B0], r15
0x18001d898  jz      short loc_18001D8A4
0x18001d89a  lea     rcx, [rsp+2F0h+var_2B0]
0x18001d89f  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001d8a4  cmp     [rsp+2F0h+var_2A0], r15
0x18001d8a9  jmp     loc_18001DA56
0x18001d8ae  mov     rdx, r14; unsigned __int16 *
0x18001d8b1  lea     rcx, [rbp+1F0h+lpMem]; this
0x18001d8b5  call    ??0hstring@winrt@@QEAA@PEBG@Z; winrt::hstring::hstring(ushort const *)
0x18001d8ba  nop
0x18001d8bb  mov     rbx, [rbp+1F0h+lpMem]
0x18001d8bf  mov     rcx, rbx; this
0x18001d8c2  call    ?duplicate_hstring@impl@winrt@@YAPEAUhstring_header@12@PEAU312@@Z; winrt::impl::duplicate_hstring(winrt::impl::hstring_header *)
0x18001d8c7  mov     rdi, rax
0x18001d8ca  mov     [rbp+1F0h+var_210], rax
0x18001d8ce  lea     rax, [rbp+1F0h+var_210]
0x18001d8d2  mov     [rbp+1F0h+lpMem], rax
0x18001d8d6  lea     rax, [rsp+2F0h+var_2A0]
0x18001d8db  mov     [rbp+1F0h+lpMem+8], rax
0x18001d8df  lock inc cs:qword_18002DA88
0x18001d8e7  cmp     cs:??$factory_cache_entry_v@UJsonObject@Json@Data@Windows@winrt@@UIJsonObjectStatics@2345@@impl@winrt@@3U?$factory_cache_entry@UJsonObject@Json@Data@Windows@winrt@@UIJsonObjectStatics@2345@@12@A, r15; factory_cache_entry<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Data::Json::IJsonObjectStatics>::winrt::factory_cache_entry<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Data::Json::IJsonObjectStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Data::Json::IJsonObjectStatics>
0x18001d8ee  jz      short loc_18001D90A
0x18001d8f0  lea     rdx, ??$factory_cache_entry_v@UJsonObject@Json@Data@Windows@winrt@@UIJsonObjectStatics@2345@@impl@winrt@@3U?$factory_cache_entry@UJsonObject@Json@Data@Windows@winrt@@UIJsonObjectStatics@2345@@12@A; factory_cache_entry<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Data::Json::IJsonObjectStatics>::winrt::factory_cache_entry<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Data::Json::IJsonObjectStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Data::Json::IJsonObjectStatics>
0x18001d8f7  lea     rcx, [rbp+1F0h+lpMem]
0x18001d8fb  call    ??R_lambda_1_@?1??TryParse@JsonObject@Json@Data@Windows@winrt@@SA@AEBUhstring@param@6@AEAU23456@@Z@QEBA@AEBUIJsonObjectStatics@3456@@Z; `winrt::Windows::Data::Json::JsonObject::TryParse(winrt::param::hstring const &,winrt::Windows::Data::Json::JsonObject &)'::`2'::_lambda_1_::operator()(winrt::Windows::Data::Json::IJsonObjectStatics const &)
0x18001d900  lock add cs:qword_18002DA88, rsi
0x18001d908  jmp     short loc_18001D91B
0x18001d90a  lock add cs:qword_18002DA88, rsi
0x18001d912  lea     rdx, [rbp+1F0h+lpMem]
0x18001d916  call    ??$call@AEAV_lambda_1_@?1??TryParse@JsonObject@Json@Data@Windows@winrt@@SA@AEBUhstring@param@7@AEAU34567@@Z@@?$factory_cache_entry@UJsonObject@Json@Data@Windows@winrt@@UIJsonObjectStatics@2345@@impl@winrt@@QEAA?A_PAEAV_lambda_1_@?1??TryParse@JsonObject@Json@Data@Windows@2@SA@AEBUhstring@param@2@AEAU56782@@Z@@Z
0x18001d91b  mov     r15b, al
0x18001d91e  test    rdi, rdi
0x18001d921  jz      short loc_18001D94C
0x18001d923  mov     ecx, esi
0x18001d925  lock xadd [rdi+18h], ecx
0x18001d92a  sub     ecx, 1
0x18001d92d  jnz     short loc_18001D944
0x18001d92f  nop
0x18001d930  call    WINRT_IMPL_GetProcessHeap
0x18001d935  mov     rcx, rax; hHeap
0x18001d938  mov     r8, rdi; lpMem
0x18001d93b  xor     edx, edx; dwFlags
0x18001d93d  call    WINRT_IMPL_HeapFree
0x18001d942  jmp     short loc_18001D94C
0x18001d944  test    ecx, ecx
0x18001d946  js      loc_18001DA74
0x18001d94c  test    rbx, rbx
0x18001d94f  jz      short loc_18001D974
0x18001d951  mov     eax, esi
0x18001d953  lock xadd [rbx+18h], eax
0x18001d958  sub     eax, 1
0x18001d95b  jnz     loc_18001DA6C
0x18001d961  nop
0x18001d962  call    WINRT_IMPL_GetProcessHeap
0x18001d967  mov     rcx, rax; hHeap
0x18001d96a  mov     r8, rbx; lpMem
0x18001d96d  xor     edx, edx; dwFlags
0x18001d96f  call    WINRT_IMPL_HeapFree
0x18001d974  test    r15b, r15b
0x18001d977  jnz     loc_18001DA7B
0x18001d97d  call    ?Instance@MidiVirtualMidiTransportTelemetryProvider@@KAPEAV1@XZ; MidiVirtualMidiTransportTelemetryProvider::Instance(void)
0x18001d982  mov     rcx, [rax+8]
0x18001d986  mov     eax, [rcx]
0x18001d988  cmp     eax, 2
0x18001d98b  jbe     short loc_18001D9DD
0x18001d98d  mov     [rbp+1F0h+lpMem], r14
0x18001d991  lea     rax, aFailedToParseC; "Failed to parse Configuration JSON"
0x18001d998  mov     [rbp+1F0h+var_270], rax
0x18001d99c  mov     [rsp+2F0h+var_278], r13
0x18001d9a1  lea     rax, aCmidi2virtualm_10; "CMidi2VirtualMidiConfigurationManager::"...
0x18001d9a8  mov     [rbp+1F0h+var_258], rax
0x18001d9ac  lea     rax, [rbp+1F0h+lpMem]
0x18001d9b0  mov     [rsp+2F0h+var_2B8], rax
0x18001d9b5  lea     rax, [rbp+1F0h+var_270]
0x18001d9b9  mov     [rsp+2F0h+var_2C0], rax
0x18001d9be  lea     rax, [rsp+2F0h+var_278]
0x18001d9c3  mov     [rsp+2F0h+var_2C8], rax
0x18001d9c8  lea     rax, [rbp+1F0h+var_258]
0x18001d9cc  mov     qword ptr [rsp+2F0h+var_2D0], rax; int
0x18001d9d1  lea     rdx, byte_18002737F
0x18001d9d8  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x18001d9dd  mov     rdx, r12; struct winrt::Windows::Data::Json::JsonObject *
0x18001d9e0  lea     rcx, [rsp+2F0h+var_2B0]; this
0x18001d9e5  call    ?JsonStringifyObjectToOutParam@WindowsMidiServicesInternal@@YA_NAEBUJsonObject@Json@Data@Windows@winrt@@PEAPEAG@Z; WindowsMidiServicesInternal::JsonStringifyObjectToOutParam(winrt::Windows::Data::Json::JsonObject const &,ushort * *)
0x18001d9ea  mov     rcx, [rbp+1F8h]; this
0x18001d9f1  mov     r9d, 80070057h; char *
0x18001d9f7  lea     r8, aAvcoreMidi2Tra; "avcore\\midi2\\transport\\virtualmiditr"...
0x18001d9fe  mov     edx, 5Bh ; '['; void *
0x18001da03  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001da08  cmp     qword ptr [rsp+2F0h+var_290], 0
0x18001da0e  jz      short loc_18001DA1A
0x18001da10  lea     rcx, [rsp+2F0h+var_290]
0x18001da15  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001da1a  cmp     qword ptr [rsp+2F0h+var_298], 0
0x18001da20  jz      short loc_18001DA2C
0x18001da22  lea     rcx, [rsp+2F0h+var_298]
0x18001da27  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001da2c  cmp     [rsp+2F0h+var_2A8], 0
0x18001da32  jz      short loc_18001DA3E
0x18001da34  lea     rcx, [rsp+2F0h+var_2A8]
0x18001da39  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001da3e  cmp     [rsp+2F0h+var_2B0], 0
0x18001da44  jz      short loc_18001DA50
0x18001da46  lea     rcx, [rsp+2F0h+var_2B0]
0x18001da4b  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001da50  cmp     [rsp+2F0h+var_2A0], 0
0x18001da56  jz      short loc_18001DA62
0x18001da58  lea     rcx, [rsp+2F0h+var_2A0]
0x18001da5d  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001da62  mov     eax, 80070057h
0x18001da67  jmp     loc_18001E4CA
0x18001da6c  test    eax, eax
0x18001da6e  jns     loc_18001D974
0x18001da74  call    cs:__imp_abort
0x18001da7b  xor     r15d, r15d
0x18001da7e  mov     [rbp+1F0h+lpMem], r15
0x18001da82  lea     r14d, [r15+1]
0x18001da86  mov     [rbp+1F0h+var_208], r14d
0x18001da8a  mov     [rbp+1F0h+var_204], 6
0x18001da91  lea     rax, aCreate; "create"
0x18001da98  mov     [rbp+1F0h+var_1F8], rax
0x18001da9c  lea     rax, [rbp+1F0h+var_208]
0x18001daa0  mov     [rbp+1F0h+var_210], rax
0x18001daa4  lea     r9, [rbp+1F0h+lpMem]
0x18001daa8  lea     r8, [rbp+1F0h+var_210]
0x18001daac  lea     rdx, [rsp+2F0h+var_288]
0x18001dab1  lea     rcx, [rsp+2F0h+var_2A0]
0x18001dab6  call    ?GetNamedArray@?$consume_Windows_Data_Json_IJsonObjectWithDefaultValues@UJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@AEBUJsonArray@Json@Data@Windows@3@@Z; winrt::impl::consume_Windows_Data_Json_IJsonObjectWithDefaultValues<winrt::Windows::Data::Json::JsonObject>::GetNamedArray(winrt::param::hstring const &,winrt::Windows::Data::Json::JsonArray const &)
0x18001dabb  mov     [rbp+1F0h+lpMem], r15
0x18001dabf  lea     rdx, [rbp+1F0h+lpMem]
0x18001dac3  lea     rcx, [rsp+2F0h+var_288]
0x18001dac8  call    ??8Foundation@Windows@winrt@@YA_NAEBUIUnknown@012@0@Z; winrt::Windows::Foundation::operator==(winrt::Windows::Foundation::IUnknown const &,winrt::Windows::Foundation::IUnknown const &)
0x18001dacd  test    al, al
0x18001dacf  jnz     loc_18001E455
0x18001dad5  lea     rcx, [rsp+2F0h+var_288]
0x18001dada  call    ?Size@?$consume_Windows_Foundation_Collections_IVector@UJsonArray@Json@Data@Windows@winrt@@UIJsonValue@2345@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Data::Json::JsonArray,winrt::Windows::Data::Json::IJsonValue>::Size(void)
0x18001dadf  test    eax, eax
0x18001dae1  jz      loc_18001E455
0x18001dae7  mov     r13d, r15d
0x18001daea  lea     rcx, [rsp+2F0h+var_288]
0x18001daef  call    ?Size@?$consume_Windows_Foundation_Collections_IVector@UJsonArray@Json@Data@Windows@winrt@@UIJsonValue@2345@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Data::Json::JsonArray,winrt::Windows::Data::Json::IJsonValue>::Size(void)
0x18001daf4  mov     rbx, [rsp+2F0h+var_288]
0x18001daf9  test    eax, eax
0x18001dafb  jz      loc_18001E255
0x18001db01  mov     [rbp+1F0h+var_268], r15
0x18001db05  mov     dword ptr [rbp+1F0h+lpMem], 1Ch
0x18001db0c  lea     rax, aOnecoreuapInte_2; "onecoreuap\\Internal\\BuildMetadata\\in"...
0x18001db13  mov     [rbp+1F0h+lpMem+8], rax
0x18001db17  mov     qword ptr [rbp+1F0h+var_220], r15
0x18001db1b  mov     rax, [rbx]
0x18001db1e  lea     r8, [rbp+1F0h+var_268]
0x18001db22  mov     edx, r13d
0x18001db25  mov     rcx, rbx
0x18001db28  mov     rax, [rax+30h]
0x18001db2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001db31  test    eax, eax
0x18001db33  js      loc_18001E4F4
0x18001db39  mov     rax, [rbp+1F0h+var_268]
0x18001db3d  mov     [rsp+2F0h+var_280], rax
0x18001db42  test    rax, rax
0x18001db45  jz      loc_18001E22F
0x18001db4b  lea     rcx, [rbp+1F0h+var_1B0]; this
0x18001db4f  call    ??0MidiVirtualDeviceEndpointEntry@@QEAA@XZ; MidiVirtualDeviceEndpointEntry::MidiVirtualDeviceEndpointEntry(void)
0x18001db54  mov     [rbp+1F0h+var_1D0], r15
0x18001db58  mov     dword ptr [rbp+1F0h+lpMem+8], r14d
0x18001db5c  mov     dword ptr [rbp+1F0h+lpMem+0Ch], 15h
0x18001db63  lea     rax, aAssociationide; "associationIdentifier"
0x18001db6a  mov     qword ptr [rbp+1F0h+var_220+8], rax
0x18001db6e  lea     rax, [rbp+1F0h+lpMem+8]
0x18001db72  mov     [rbp+1F0h+lpMem], rax
0x18001db76  lea     r9, [rbp+1F0h+var_1D0]
0x18001db7a  lea     r8, [rbp+1F0h+lpMem]
0x18001db7e  lea     rdx, [rbp+1F0h+var_240]
0x18001db82  lea     rcx, [rsp+2F0h+var_280]
0x18001db87  call    ?GetNamedString@?$consume_Windows_Data_Json_IJsonObjectWithDefaultValues@UJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@0@Z; winrt::impl::consume_Windows_Data_Json_IJsonObjectWithDefaultValues<winrt::Windows::Data::Json::JsonObject>::GetNamedString(winrt::param::hstring const &,winrt::param::hstring const &)
0x18001db8c  mov     rdx, rax
0x18001db8f  lea     rcx, [rbp+1F0h+var_1B0]
0x18001db93  call    ??$?4Uhstring@winrt@@$0A@@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBUhstring@winrt@@@Z; std::wstring::operator=<winrt::hstring,0>(winrt::hstring const &)
0x18001db98  mov     rdi, [rbp+1F0h+var_240]
0x18001db9c  test    rdi, rdi
0x18001db9f  jz      short loc_18001DBCE
0x18001dba1  mov     eax, esi
0x18001dba3  lock xadd [rdi+18h], eax
0x18001dba8  sub     eax, 1
0x18001dbab  jnz     short loc_18001DBC2
0x18001dbad  nop
0x18001dbae  call    WINRT_IMPL_GetProcessHeap
  ... truncated ...
```
