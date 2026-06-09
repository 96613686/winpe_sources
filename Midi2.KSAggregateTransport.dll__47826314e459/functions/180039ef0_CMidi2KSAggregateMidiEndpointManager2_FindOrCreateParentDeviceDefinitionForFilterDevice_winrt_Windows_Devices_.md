# CMidi2KSAggregateMidiEndpointManager2::FindOrCreateParentDeviceDefinitionForFilterDevice(winrt::Windows::Devices::Enumeration::DeviceInformation,std::shared_ptr<KsAggregateParentDeviceDefinition2> &)

- ea: `0x180039ef0`
- end: `0x18003abc8`
- name: `?FindOrCreateParentDeviceDefinitionForFilterDevice@CMidi2KSAggregateMidiEndpointManager2@@AEAAJUDeviceInformation@Enumeration@Devices@Windows@winrt@@AEAV?$shared_ptr@VKsAggregateParentDeviceDefinition2@@@std@@@Z`
- size: `3288`
- prototype: ``
- caller_count: `2`
- callee_count: `40`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800365e8`
- `0x18003c890`

## callees

- `0x1800017d0`
- `0x180002390`
- `0x180005020`
- `0x180005070`
- `0x180005e16`
- `0x180005f2c`
- `0x180005fa4`
- `0x18000b394`
- `0x18000d430`
- `0x18000d778`
- `0x180010b94`
- `0x1800117d8`
- `0x180012c1c`
- `0x180013118`
- `0x1800138b8`
- `0x180013f60`
- `0x180014194`
- `0x180014d2c`
- `0x180014f00`
- `0x1800150c0`
- `0x1800154d4`
- `0x180019924`
- `0x180019b34`
- `0x18001a124`
- `0x18001a844`
- `0x18001fa30`
- `0x18001fcd0`
- `0x1800229bc`
- `0x18002301c`
- `0x18002548c`
- `0x180025c34`
- `0x180029298`
- `0x18002a2e8`
- `0x1800344e4`
- `0x1800346e0`
- `0x180034aac`
- `0x180039ef0`
- `0x18003ef8c`
- `0x180042bf8`
- `0x18005e010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18003a031`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18003a72f`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18003a7e7`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18003a031`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18003a72f`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18003a7e7`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18003a048`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18003a43b`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18003a635`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18003a74a`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18003a048`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18003a43b`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18003a635`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18003a74a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003a285`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003a285`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003a3e2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003a5c4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003ab5f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003a3e2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003a5c4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003ab5f`

## string_xrefs

- `0x180039f42`: `CMidi2KSAggregateMidiEndpointManager2::FindOrCreateParentDeviceDefinitionForFilterDevice`
- `0x18003a382`: `CMidi2KSAggregateMidiEndpointManager2::FindOrCreateParentDeviceDefinitionForFilterDevice`
- `0x18003a48d`: `CMidi2KSAggregateMidiEndpointManager2::FindOrCreateParentDeviceDefinitionForFilterDevice`
- `0x18003a8f6`: `CMidi2KSAggregateMidiEndpointManager2::FindOrCreateParentDeviceDefinitionForFilterDevice`
- `0x18003a9ca`: `CMidi2KSAggregateMidiEndpointManager2::FindOrCreateParentDeviceDefinitionForFilterDevice`
- `0x18003aa50`: `CMidi2KSAggregateMidiEndpointManager2::FindOrCreateParentDeviceDefinitionForFilterDevice`
- `0x18003aa99`: `CMidi2KSAggregateMidiEndpointManager2::FindOrCreateParentDeviceDefinitionForFilterDevice`
- `0x18003a47e`: `Parent device definition not already created. Creating now.`

## pseudocode

```c
// Hidden C++ exception states: #wind=28
__int64 __fastcall CMidi2KSAggregateMidiEndpointManager2::FindOrCreateParentDeviceDefinitionForFilterDevice(
        __int64 a1,
        __int64 *a2,
        const wchar_t *a3)
{
  unsigned int v5; // edx
  _DWORD *v6; // rbx
  const wchar_t *v7; // rsi
  __int64 v8; // rax
  int v9; // r8d
  int v10; // r9d
  wchar_t *v11; // rax
  void *v12; // rbx
  int v13; // eax
  HANDLE ProcessHeap; // rax
  __int64 v15; // rcx
  struct winrt::impl::shared_hstring_header *v16; // rax
  struct winrt::impl::shared_hstring_header *v17; // rbx
  void *v18; // rbx
  int v19; // edi
  HANDLE v20; // rax
  __int64 v22; // rcx
  __int64 v23; // rax
  struct _RTL_CRITICAL_SECTION *v24; // r12
  __int64 v25; // rax
  __int64 v26; // r8
  __int64 v27; // rax
  void *v28; // rbx
  int v29; // eax
  HANDLE v30; // rax
  char *v31; // rbx
  _DWORD *v32; // rcx
  int v33; // r8d
  int v34; // r9d
  _QWORD *v35; // rax
  void *v36; // rbx
  int v37; // edi
  HANDLE v38; // rax
  bool v39; // zf
  _DWORD *v40; // rcx
  int v41; // r8d
  int v42; // r9d
  _QWORD *v43; // rax
  char *v44; // rsi
  char *v45; // r14
  void *v46; // rbx
  int v47; // edi
  HANDLE v48; // rax
  __int64 v49; // rax
  void *v50; // rbx
  int v51; // edi
  HANDLE v52; // rax
  __int64 v53; // rax
  __int64 v54; // rcx
  int v55; // eax
  unsigned int v56; // edx
  unsigned int v57; // edi
  struct winrt::impl::shared_hstring_header *v58; // rax
  struct winrt::impl::shared_hstring_header *v59; // rbx
  unsigned int v60; // edx
  struct winrt::impl::shared_hstring_header *v61; // rax
  struct winrt::impl::shared_hstring_header *v62; // rbx
  __int64 *v63; // rdx
  _DWORD *v64; // rcx
  int v65; // r8d
  int v66; // r9d
  _QWORD *v67; // rax
  _QWORD **v68; // rsi
  char v69; // r10
  _QWORD **v70; // rbx
  _QWORD *v71; // rax
  _DWORD *v72; // rcx
  int v73; // r8d
  int v74; // r9d
  _QWORD *v75; // rax
  _DWORD *v76; // rcx
  int v77; // r8d
  int v78; // r9d
  _QWORD *v79; // rax
  __int64 v80; // rax
  _DWORD *v81; // rcx
  int v82; // r8d
  int v83; // r9d
  LPVOID *v84; // rax
  int v85; // [rsp+20h] [rbp-E0h]
  LPVOID lpMem; // [rsp+58h] [rbp-A8h] BYREF
  LPVOID v87; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD **v88; // [rsp+68h] [rbp-98h] BYREF
  const char *v89; // [rsp+70h] [rbp-90h] BYREF
  __int64 v90; // [rsp+78h] [rbp-88h] BYREF
  int v91[2]; // [rsp+80h] [rbp-80h] BYREF
  const char *v92; // [rsp+88h] [rbp-78h] BYREF
  const wchar_t *v93; // [rsp+90h] [rbp-70h] BYREF
  LPVOID *p_lpMem; // [rsp+98h] [rbp-68h] BYREF
  LPVOID v95; // [rsp+A0h] [rbp-60h] BYREF
  const char *v96; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v97; // [rsp+B0h] [rbp-50h] BYREF
  __int128 v98; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v99; // [rsp+C8h] [rbp-38h] BYREF
  const wchar_t *v100; // [rsp+D0h] [rbp-30h] BYREF
  _QWORD v101[7]; // [rsp+D8h] [rbp-28h] BYREF
  __int128 v102; // [rsp+110h] [rbp+10h] BYREF
  const char **v103; // [rsp+120h] [rbp+20h]
  const wchar_t *v104; // [rsp+128h] [rbp+28h]
  _QWORD v105[3]; // [rsp+130h] [rbp+30h] BYREF
  unsigned __int64 v106; // [rsp+148h] [rbp+48h]
  wil::details::in1diag3 *retaddr; // [rsp+198h] [rbp+98h]

  v100 = a3;
  v88 = (_QWORD **)a1;
  v101[4] = a2;
  v6 = (_DWORD *)*((_QWORD *)MidiKSAggregateTransportTelemetryProvider::Instance() + 1);
  v7 = &S1;
  if ( *v6 > 4u )
  {
    v8 = winrt::impl::consume_Windows_Devices_Enumeration_IDeviceInformation<winrt::Windows::Devices::Enumeration::IDeviceInformation>::Id(
           a2,
           &lpMem);
    v11 = *(_QWORD *)v8 ? *(wchar_t **)(*(_QWORD *)v8 + 16LL) : (wchar_t *)&S1;
    v87 = v11;
    v93 = L"Enter.";
    v96 = (const char *)a1;
    *(_QWORD *)v91 = "CMidi2KSAggregateMidiEndpointManager2::FindOrCreateParentDeviceDefinitionForFilterDevice";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
      (_DWORD)v6,
      (unsigned int)byte_18008A2B1,
      v9,
      v10,
      (__int64)v91,
      (__int64)&v96,
      (__int64)&v93,
      (__int64)&v87);
    v12 = lpMem;
    if ( lpMem )
    {
      v13 = _InterlockedDecrement((volatile signed __int32 *)lpMem + 6);
      if ( v13 )
      {
        if ( v13 < 0 )
          abort();
      }
      else
      {
        ProcessHeap = WINRT_IMPL_GetProcessHeap();
        WINRT_IMPL_HeapFree(ProcessHeap, 0, v12);
      }
    }
  }
  p_lpMem = &lpMem;
  lpMem = 0;
  v87 = &v90;
  v15 = *a2;
  v90 = v15;
  if ( v15 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 8LL))(v15);
  v16 = winrt::impl::precreate_hstring_on_heap((winrt::impl *)0x1F, v5);
  v17 = v16;
  if ( v16 == (struct winrt::impl::shared_hstring_header *)-28LL )
  {
    *(_DWORD *)_o__errno() = 22;
    invalid_parameter_noinfo();
  }
  else
  {
    *(_OWORD *)((char *)v16 + 28) = *(_OWORD *)L"System.Devices.DeviceInstanceId";
    *(_OWORD *)((char *)v16 + 44) = *(_OWORD *)L"evices.DeviceInstanceId";
    *(_OWORD *)((char *)v16 + 60) = *(_OWORD *)L"eviceInstanceId";
    *(_OWORD *)((char *)v16 + 74) = *(_OWORD *)L"stanceId";
  }
  v89 = (const char *)v17;
  WindowsMidiServicesInternal::SafeGetSwdPropertyFromDeviceInformation<winrt::hstring>(&v95, &v89, &v90, &lpMem);
  if ( !v95 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x568,
      (unsigned int)"avcore\\midi2\\transport\\ksaggregatetransport\\midi2.ksaggregatemidiendpointmanager2.cpp",
      (const char *)0x80004005LL,
      v85);
    v18 = v95;
    if ( !v95 )
    {
LABEL_21:
      if ( *a2 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a2);
      return 2147500037LL;
    }
    v19 = _InterlockedDecrement((volatile signed __int32 *)v95 + 6);
    if ( !v19 )
    {
      v20 = WINRT_IMPL_GetProcessHeap();
      WINRT_IMPL_HeapFree(v20, 0, v18);
LABEL_20:
      v95 = 0;
      goto LABEL_21;
    }
    if ( v19 >= 0 )
      goto LABEL_20;
LABEL_83:
    abort();
  }
  v102 = 0;
  v103 = 0;
  winrt::single_threaded_vector<winrt::hstring,std::allocator<winrt::hstring>>(&v90, &v102);
  std::vector<winrt::hstring>::~vector<winrt::hstring>(&v102);
  *((_QWORD *)&v102 + 1) = 0x2100000001LL;
  v104 = L"System.Devices.DeviceManufacturer";
  *(_QWORD *)&v102 = (char *)&v102 + 8;
  winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Foundation::Collections::IVector<winrt::hstring>,winrt::hstring>::Append(
    &v90,
    &v102);
  *((_QWORD *)&v102 + 1) = 0x1B00000001LL;
  v104 = L"System.Devices.Manufacturer";
  *(_QWORD *)&v102 = (char *)&v102 + 8;
  winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Foundation::Collections::IVector<winrt::hstring>,winrt::hstring>::Append(
    &v90,
    &v102);
  *((_QWORD *)&v102 + 1) = 0x1500000001LL;
  v104 = L"System.Devices.Parent";
  *(_QWORD *)&v102 = (char *)&v102 + 8;
  winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Foundation::Collections::IVector<winrt::hstring>,winrt::hstring>::Append(
    &v90,
    &v102);
  LODWORD(v89) = 3;
  winrt::param::async_iterable<winrt::hstring>::async_iterable<winrt::hstring>(&v98, &v90);
  v101[0] = v95;
  *(_QWORD *)&v102 = v101;
  *((_QWORD *)&v102 + 1) = &v98;
  v103 = &v89;
  p_lpMem = (LPVOID *)&qword_180096B08;
  _InterlockedAdd64(&qword_180096B08, 1u);
  if ( winrt::impl::factory_cache_entry_v<winrt::Windows::Devices::Enumeration::DeviceInformation,winrt::Windows::Devices::Enumeration::IDeviceInformationStatics2> )
  {
    `winrt::Windows::Devices::Enumeration::DeviceInformation::CreateFromIdAsync'::`2'::_lambda_1_::operator()(
      &v102,
      &lpMem,
      &winrt::impl::factory_cache_entry_v<winrt::Windows::Devices::Enumeration::DeviceInformation,winrt::Windows::Devices::Enumeration::IDeviceInformationStatics2>);
    _InterlockedAdd64(&qword_180096B08, 0xFFFFFFFFFFFFFFFFuLL);
  }
  else
  {
    _InterlockedAdd64(&qword_180096B08, 0xFFFFFFFFFFFFFFFFuLL);
    ___call_AEAV_lambda_1___1__CreateFromIdAsync_DeviceInformation_Enumeration_Devices_Windows_winrt__SA_AEBUhstring_param_7_AEBU__async_iterable_Uhstring_winrt___97_AEBW4DeviceInformationKind_4567__Z____factory_cache_entry_UDeviceInformation_Enumeration_Devices_Windows_winrt__UIDeviceInformationStatics2_2345__impl_winrt__QEAA_A_PAEAV_lambda_1___1__CreateFromIdAsync_DeviceInformation_Enumeration_Devices_Windows_2_SA_AEBUhstring_param_2_AEBU__async_iterable_Uhstring_winrt___param_2_AEBW4DeviceInformationKind_6782__Z__Z(
      v22,
      &lpMem,
      &v102);
  }
  winrt::impl::consume_Windows_Foundation_IAsyncOperation<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Devices::Enumeration::DeviceInformation>,winrt::Windows::Devices::Enumeration::DeviceInformation>::get(
    &lpMem,
    &v92);
  if ( lpMem )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&lpMem);
  if ( BYTE8(v98) )
  {
    v23 = v98;
  }
  else
  {
    v23 = 0;
    *(_QWORD *)&v98 = 0;
  }
  if ( v23 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v98);
  v24 = (struct _RTL_CRITICAL_SECTION *)(a1 + 64);
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 64));
  v101[5] = a1 + 64;
  v25 = winrt::impl::consume_Windows_Devices_Enumeration_IDeviceInformation<winrt::Windows::Devices::Enumeration::IDeviceInformation>::Id(
          &v92,
          &lpMem);
  if ( *(_QWORD *)v25 )
    v7 = *(const wchar_t **)(*(_QWORD *)v25 + 16LL);
  v102 = 0;
  v103 = 0;
  v104 = 0;
  v26 = -1;
  do
    ++v26;
  while ( v7[v26] );
  std::wstring::_Construct<1,unsigned short const *>(&v102);
  v27 = std::wstring::wstring(v101, &v102);
  WindowsMidiServicesInternal::ToUpperTrimmedWStringCopy(v105, v27);
  std::wstring::~wstring(&v102);
  v28 = lpMem;
  if ( lpMem )
  {
    v29 = _InterlockedDecrement((volatile signed __int32 *)lpMem + 6);
    if ( v29 )
    {
      if ( v29 < 0 )
        abort();
    }
    else
    {
      v30 = WINRT_IMPL_GetProcessHeap();
      WINRT_IMPL_HeapFree(v30, 0, v28);
    }
    lpMem = 0;
  }
  std::_Tree<std::_Tmap_traits<std::wstring,std::shared_ptr<KsAggregateParentDeviceDefinition2>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::shared_ptr<KsAggregateParentDeviceDefinition2>>>,0>>::find(
    a1 + 48,
    &v87,
    v105);
  v31 = (char *)v87;
  if ( v87 != *(LPVOID *)(a1 + 48) )
  {
    v32 = (_DWORD *)*((_QWORD *)MidiKSAggregateTransportTelemetryProvider::Instance() + 1);
    if ( *v32 > 4u )
    {
      v35 = v105;
      if ( v106 > 7 )
        v35 = (_QWORD *)v105[0];
      v88 = (_QWORD **)v35;
      v87 = L"Found existing parent device.";
      v93 = (const wchar_t *)a1;
      v96 = "CMidi2KSAggregateMidiEndpointManager2::FindOrCreateParentDeviceDefinitionForFilterDevice";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
        (_DWORD)v32,
        (unsigned int)&dword_18008A274,
        v33,
        v34,
        (__int64)&v96,
        (__int64)&v93,
        (__int64)&v87,
        (__int64)&v88);
    }
    std::shared_ptr<KsAggregateEndpointDefinition2>::operator=(v100, v31 + 64);
    std::wstring::~wstring(v105);
    if ( a1 != -64 )
      LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 64));
    if ( v92 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v92);
    if ( v90 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v90);
    v36 = v95;
    if ( v95 )
    {
      v37 = _InterlockedDecrement((volatile signed __int32 *)v95 + 6);
      if ( v37 )
      {
        if ( v37 < 0 )
          goto LABEL_83;
      }
      else
      {
        v38 = WINRT_IMPL_GetProcessHeap();
        WINRT_IMPL_HeapFree(v38, 0, v36);
      }
      v95 = 0;
    }
    v39 = *a2 == 0;
    goto LABEL_145;
  }
  v40 = (_DWORD *)*((_QWORD *)MidiKSAggregateTransportTelemetryProvider::Instance() + 1);
  if ( *v40 > 4u )
  {
    v43 = v105;
    if ( v106 > 7 )
      v43 = (_QWORD *)v105[0];
    v87 = v43;
    v93 = L"Parent device definition not already created. Creating now.";
    v96 = (const char *)a1;
    *(_QWORD *)v91 = "CMidi2KSAggregateMidiEndpointManager2::FindOrCreateParentDeviceDefinitionForFilterDevice";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
      (_DWORD)v40,
      (unsigned int)&byte_18008A237,
      v41,
      v42,
      (__int64)v91,
      (__int64)&v96,
      (__int64)&v93,
      (__int64)&v87);
  }
  v44 = (char *)operator new(0x98u);
  p_lpMem = (LPVOID *)v44;
  *(_OWORD *)v44 = 0;
  *((_DWORD *)v44 + 2) = 1;
  *((_DWORD *)v44 + 3) = 1;
  *(_QWORD *)v44 = &std::_Ref_count_obj2<KsAggregateParentDeviceDefinition2>::`vftable';
  v45 = v44 + 16;
  *((_OWORD *)v44 + 1) = 0;
  *((_QWORD *)v44 + 4) = 0;
  *((_QWORD *)v44 + 5) = 7;
  *((_WORD *)v44 + 8) = 0;
  *((_OWORD *)v44 + 3) = 0;
  *((_QWORD *)v44 + 8) = 0;
  *((_QWORD *)v44 + 9) = 7;
  *((_WORD *)v44 + 24) = 0;
  *((_QWORD *)v44 + 10) = 0;
  *(_OWORD *)(v44 + 88) = 0;
  *((_QWORD *)v44 + 13) = 0;
  *((_QWORD *)v44 + 14) = 7;
  *((_WORD *)v44 + 44) = 0;
  *(_OWORD *)(v44 + 120) = 0;
  *((_QWORD *)v44 + 17) = 0;
  *((_QWORD *)v44 + 18) = 7;
  *((_WORD *)v44 + 60) = 0;
  *(_QWORD *)&v102 = v44 + 16;
  *((_QWORD *)&v102 + 1) = v44;
  if ( v44 != (char *)-16LL )
  {
    v49 = winrt::impl::consume_Windows_Devices_Enumeration_IDeviceInformation<winrt::Windows::Devices::Enumeration::IDeviceInformation>::Name(
            &v92,
            &v87);
    std::wstring::operator=<winrt::hstring,0>(v44 + 16, v49);
    v50 = v87;
    if ( v87 )
    {
      v51 = _InterlockedDecrement((volatile signed __int32 *)v87 + 6);
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
    }
    std::wstring::operator=(v44 + 48, v105);
    p_lpMem = (LPVOID *)&v98;
    v98 = 0;
    _InterlockedIncrement((volatile signed __int32 *)v44 + 2);
    *(_QWORD *)&v98 = v44 + 16;
    *((_QWORD *)&v98 + 1) = v44;
    v53 = std::wstring::wstring(v101, v44 + 48);
    v55 = CMidi2KSAggregateMidiEndpointManager2::ParseParentIdIntoVidPidSerial(v54, v53, &v98);
    v57 = 0;
    if ( v55 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x59E,
        (unsigned int)"avcore\\midi2\\transport\\ksaggregatetransport\\midi2.ksaggregatemidiendpointmanager2.cpp",
        (const char *)(unsigned int)v55,
        v85);
    p_lpMem = &lpMem;
    lpMem = 0;
    v87 = &v89;
    v89 = v92;
    if ( v92 )
      (*(void (__fastcall **)(const char *))(*(_QWORD *)v92 + 8LL))(v92);
    v58 = winrt::impl::precreate_hstring_on_heap((winrt::impl *)0x21, v56);
    v59 = v58;
    if ( v58 == (struct winrt::impl::shared_hstring_header *)-28LL )
    {
      *(_DWORD *)_o__errno() = 22;
      invalid_parameter_noinfo();
    }
    else
    {
      *(_OWORD *)((char *)v58 + 28) = *(_OWORD *)L"System.Devices.DeviceManufacturer";
      *(_OWORD *)((char *)v58 + 44) = *(_OWORD *)L"evices.DeviceManufacturer";
      *(_OWORD *)((char *)v58 + 60) = *(_OWORD *)L"eviceManufacturer";
      *(_OWORD *)((char *)v58 + 76) = *(_OWORD *)L"ufacturer";
      *((_WORD *)v58 + 46) = aSystemDevicesD_0[32];
    }
    *(_QWORD *)v91 = v59;
    WindowsMidiServicesInternal::SafeGetSwdPropertyFromDeviceInformation<winrt::hstring>(&v99, v91, &v89, &lpMem);
    p_lpMem = (LPVOID *)&v96;
    v96 = 0;
    v101[6] = &v93;
    v93 = (const wchar_t *)v92;
    if ( v92 )
      (*(void (__fastcall **)(const char *))(*(_QWORD *)v92 + 8LL))(v92);
    v61 = winrt::impl::precreate_hstring_on_heap((winrt::impl *)0x1B, v60);
    v62 = v61;
    if ( v61 == (struct winrt::impl::shared_hstring_header *)-28LL )
    {
      *(_DWORD *)_o__errno() = 22;
      invalid_parameter_noinfo();
    }
    else
    {
      *(_OWORD *)((char *)v61 + 28) = *(_OWORD *)L"System.Devices.Manufacturer";
      *(_OWORD *)((char *)v61 + 44) = *(_OWORD *)L"evices.Manufacturer";
      *(_OWORD *)((char *)v61 + 60) = *(_OWORD *)L"anufacturer";
      *(_QWORD *)((char *)v61 + 74) = *(_QWORD *)L"urer";
    }
    v87 = v62;
    WindowsMidiServicesInternal::SafeGetSwdPropertyFromDeviceInformation<winrt::hstring>(&v97, &v87, &v93, &v96);
    if ( !v99
      || *(_DWORD *)(v99 + 4) == 19 && !wmemcmp(*(const wchar_t **)(v99 + 16), L"(Generic USB Audio)", 0x13u)
      || !(unsigned __int8)winrt::operator!=(&v99, L"Microsoft") )
    {
      if ( !v97
        || !(unsigned __int8)winrt::operator!=(&v97, L"(Generic USB Audio)")
        || !(unsigned __int8)winrt::operator!=(&v97, L"Microsoft") )
      {
        goto LABEL_111;
      }
      v63 = &v97;
    }
    else
    {
      v63 = &v99;
    }
    std::wstring::operator=<winrt::hstring,0>(v44 + 120, v63);
LABEL_111:
    v64 = (_DWORD *)*((_QWORD *)MidiKSAggregateTransportTelemetryProvider::Instance() + 1);
    if ( *v64 <= 4u )
    {
      v68 = v88;
    }
    else
    {
      v67 = v105;
      if ( v106 > 7 )
        v67 = (_QWORD *)v105[0];
      *(_QWORD *)v91 = v67;
      lpMem = L"Checking for other parents with same name.";
      v68 = v88;
      v89 = "CMidi2KSAggregateMidiEndpointManager2::FindOrCreateParentDeviceDefinitionForFilterDevice";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
        (_DWORD)v64,
        (unsigned int)word_18008A1FA,
        v65,
        v66,
        (__int64)&v89,
        (__int64)&v88,
        (__int64)&lpMem,
        (__int64)v91);
    }
    v69 = 0;
    v70 = (_QWORD **)*v68[6];
    v88 = v70;
    while ( !*((_BYTE *)v70 + 25) )
    {
      if ( (unsigned __int8)std::operator==<unsigned short>(v70[8], v45) )
      {
        v71 = v70[8];
        if ( v57 <= *((_DWORD *)v71 + 16) )
          v57 = *((_DWORD *)v71 + 16);
      }
      std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::shared_ptr<KsAggregateParentDeviceDefinition2>>>>,std::_Iterator_base0>::operator++(&v88);
      v70 = v88;
    }
    if ( v69 )
    {
      v72 = (_DWORD *)*((_QWORD *)MidiKSAggregateTransportTelemetryProvider::Instance() + 1);
      if ( *v72 > 4u )
      {
        v75 = v105;
        if ( v106 > 7 )
          v75 = (_QWORD *)v105[0];
        v88 = (_QWORD **)v75;
        *(_QWORD *)v91 = L"Found other parents with the same name.";
        lpMem = v68;
        v89 = "CMidi2KSAggregateMidiEndpointManager2::FindOrCreateParentDeviceDefinitionForFilterDevice";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
          (_DWORD)v72,
          (unsigned int)byte_18008A1BD,
          v73,
          v74,
          (__int64)&v89,
          (__int64)&lpMem,
          (__int64)v91,
          (__int64)&v88);
      }
      *((_DWORD *)v45 + 16) = v57 + 1;
    }
    v76 = (_DWORD *)*((_QWORD *)MidiKSAggregateTransportTelemetryProvider::Instance() + 1);
    if ( *v76 > 4u )
    {
      if ( *((_QWORD *)v45 + 3) > 7u )
        v45 = *(char **)v45;
      v88 = (_QWORD **)v45;
      v79 = v105;
      if ( v106 > 7 )
        v79 = (_QWORD *)v105[0];
      *(_QWORD *)v91 = v79;
      lpMem = L"Adding parent to device definitions list.";
      v89 = (const char *)v68;
      p_lpMem = (LPVOID *)"CMidi2KSAggregateMidiEndpointManager2::FindOrCreateParentDeviceDefinitionForFilterDevice";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
        (_DWORD)v76,
        (unsigned int)byte_18008A173,
        v77,
        v78,
        (__int64)&p_lpMem,
        (__int64)&v89,
        (__int64)&lpMem,
        (__int64)v91,
        (__int64)&v88);
    }
    v80 = std::map<std::wstring,std::shared_ptr<KsAggregateParentDeviceDefinition2>>::operator[](v68 + 6, v105);
    std::shared_ptr<KsAggregateEndpointDefinition2>::operator=(v80, &v102);
    std::shared_ptr<KsAggregateEndpointDefinition2>::operator=(v100, &v102);
    v81 = (_DWORD *)*((_QWORD *)MidiKSAggregateTransportTelemetryProvider::Instance() + 1);
    if ( *v81 > 4u )
    {
      v84 = (LPVOID *)v105;
      if ( v106 > 7 )
        v84 = (LPVOID *)v105[0];
      p_lpMem = v84;
      v100 = L"Parent device definition added.";
      v88 = v68;
      v87 = "CMidi2KSAggregateMidiEndpointManager2::FindOrCreateParentDeviceDefinitionForFilterDevice";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
        (_DWORD)v81,
        (unsigned int)&dword_18008A124,
        v82,
        v83,
        (__int64)&v87,
        (__int64)&v88,
        (__int64)&v100,
        (__int64)&p_lpMem);
    }
    winrt::hstring::~hstring((winrt::hstring *)&v97);
    winrt::hstring::~hstring((winrt::hstring *)&v99);
    std::shared_ptr<WindowsMidiServicesPluginConfigurationLib::MidiEndpointMatchCriteria>::~shared_ptr<WindowsMidiServicesPluginConfigurationLib::MidiEndpointMatchCriteria>(&v102);
    std::wstring::~wstring(v105);
    if ( v24 )
      LeaveCriticalSection(v24);
    if ( v92 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v92);
    if ( v90 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v90);
    winrt::hstring::~hstring((winrt::hstring *)&v95);
    v39 = *a2 == 0;
LABEL_145:
    if ( !v39 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a2);
    return 0;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x599,
    (unsigned int)"avcore\\midi2\\transport\\ksaggregatetransport\\midi2.ksaggregatemidiendpointmanager2.cpp",
    (const char *)0x8007000ELL,
    v85);
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)0xFFFFFFFFFFFFFFF8LL, 0xFFFFFFFF) == 1 )
  {
    ((void (__fastcall *)(__int64))*MEMORY[0xFFFFFFFFFFFFFFF0])(-16);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)0xFFFFFFFFFFFFFFFCLL, 0xFFFFFFFF) == 1 )
      (*(void (__fastcall **)(__int64))(MEMORY[0xFFFFFFFFFFFFFFF0] + 8LL))(-16);
  }
  std::wstring::~wstring(v105);
  if ( v24 )
    LeaveCriticalSection(v24);
  if ( v92 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v92);
  if ( v90 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v90);
  v46 = v95;
  if ( v95 )
  {
    v47 = _InterlockedDecrement((volatile signed __int32 *)v95 + 6);
    if ( v47 )
    {
      if ( v47 < 0 )
        goto LABEL_83;
    }
    else
    {
      v48 = WINRT_IMPL_GetProcessHeap();
      WINRT_IMPL_HeapFree(v48, 0, v46);
    }
    v95 = 0;
  }
  if ( *a2 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a2);
  return 2147942414LL;
}

```

## disassembly

```asm
0x180039ef0  mov     [rsp-8+arg_18], rbx
0x180039ef5  push    rbp
0x180039ef6  push    rsi
0x180039ef7  push    rdi
0x180039ef8  push    r12
0x180039efa  push    r13
0x180039efc  push    r14
0x180039efe  push    r15
0x180039f00  lea     rbp, [rsp-60h]
0x180039f05  sub     rsp, 160h
0x180039f0c  mov     rax, cs:__security_cookie
0x180039f13  xor     rax, rsp
0x180039f16  mov     [rbp+90h+var_40], rax
0x180039f1a  mov     [rbp+90h+var_C0], r8
0x180039f1e  mov     r15, rdx
0x180039f21  mov     r14, rcx
0x180039f24  mov     [rsp+190h+var_128], rcx
0x180039f29  mov     [rbp+90h+var_98], rdx
0x180039f2d  xor     r13d, r13d
0x180039f30  call    ?Instance@MidiKSAggregateTransportTelemetryProvider@@KAPEAV1@XZ; MidiKSAggregateTransportTelemetryProvider::Instance(void)
0x180039f35  mov     rbx, [rax+8]
0x180039f39  mov     eax, [rbx]
0x180039f3b  lea     rsi, S1
0x180039f42  lea     r12, aCmidi2ksaggreg_33; "CMidi2KSAggregateMidiEndpointManager2::"...
0x180039f49  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180039f4d  cmp     eax, 4
0x180039f50  jbe     loc_180039FE9
0x180039f56  lea     rdx, [rsp+190h+lpMem]
0x180039f5b  mov     rcx, r15
0x180039f5e  call    ?Id@?$consume_Windows_Devices_Enumeration_IDeviceInformation@UIDeviceInformation@Enumeration@Devices@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Devices_Enumeration_IDeviceInformation<winrt::Windows::Devices::Enumeration::IDeviceInformation>::Id(void)
0x180039f63  mov     rcx, [rax]
0x180039f66  test    rcx, rcx
0x180039f69  jz      short loc_180039F71
0x180039f6b  mov     rax, [rcx+10h]
0x180039f6f  jmp     short loc_180039F74
0x180039f71  mov     rax, rsi
0x180039f74  mov     [rsp+190h+var_130], rax
0x180039f79  lea     rax, aEnter; "Enter."
0x180039f80  mov     [rbp+90h+var_100], rax
0x180039f84  mov     [rbp+90h+var_E8], r14
0x180039f88  mov     qword ptr [rbp+90h+var_110], r12
0x180039f8c  lea     rax, [rsp+190h+var_130]
0x180039f91  mov     [rsp+190h+var_158], rax
0x180039f96  lea     rax, [rbp+90h+var_100]
0x180039f9a  mov     [rsp+190h+var_160], rax
0x180039f9f  lea     rax, [rbp+90h+var_E8]
0x180039fa3  mov     [rsp+190h+var_168], rax
0x180039fa8  lea     rax, [rbp+90h+var_110]
0x180039fac  mov     qword ptr [rsp+190h+var_170], rax; int
0x180039fb1  lea     rdx, byte_18008A2B1
0x180039fb8  mov     rcx, rbx
0x180039fbb  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x180039fc0  mov     rbx, [rsp+190h+lpMem]
0x180039fc5  test    rbx, rbx
0x180039fc8  jz      short loc_180039FE9
0x180039fca  mov     eax, edi
0x180039fcc  lock xadd [rbx+18h], eax
0x180039fd1  sub     eax, 1
0x180039fd4  jnz     short loc_18003A044
0x180039fd6  nop
0x180039fd7  call    WINRT_IMPL_GetProcessHeap
0x180039fdc  mov     rcx, rax; hHeap
0x180039fdf  mov     r8, rbx; lpMem
0x180039fe2  xor     edx, edx; dwFlags
0x180039fe4  call    WINRT_IMPL_HeapFree
0x180039fe9  lea     rax, [rsp+190h+lpMem]
0x180039fee  mov     [rbp+90h+var_F8], rax
0x180039ff2  mov     [rsp+190h+lpMem], r13
0x180039ff7  lea     rax, [rsp+190h+var_118]
0x180039ffc  mov     [rsp+190h+var_130], rax
0x18003a001  mov     rcx, [r15]
0x18003a004  mov     [rsp+190h+var_118], rcx
0x18003a009  test    rcx, rcx
0x18003a00c  jz      short loc_18003A01B
0x18003a00e  mov     rax, [rcx]
0x18003a011  mov     rax, [rax+8]
0x18003a015  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a01a  nop
0x18003a01b  mov     ecx, 1Fh; this
0x18003a020  call    ?precreate_hstring_on_heap@impl@winrt@@YAPEAUshared_hstring_header@12@I@Z; winrt::impl::precreate_hstring_on_heap(uint)
0x18003a025  mov     rbx, rax
0x18003a028  lea     rcx, [rax+1Ch]
0x18003a02c  test    rcx, rcx
0x18003a02f  jnz     short loc_18003A04F
0x18003a031  call    cs:__imp__o__errno
0x18003a037  mov     dword ptr [rax], 16h
0x18003a03d  call    _invalid_parameter_noinfo
0x18003a042  jmp     short loc_18003A07A
0x18003a044  test    eax, eax
0x18003a046  jns     short loc_180039FE9
0x18003a048  call    cs:__imp_abort
0x18003a04f  movaps  xmm0, xmmword ptr cs:aSystemDevicesD; "System.Devices.DeviceInstanceId"
0x18003a056  movups  xmmword ptr [rcx], xmm0
0x18003a059  movaps  xmm1, xmmword ptr cs:aSystemDevicesD+10h; "evices.DeviceInstanceId"
0x18003a060  movups  xmmword ptr [rcx+10h], xmm1
0x18003a064  movaps  xmm0, xmmword ptr cs:aSystemDevicesD+20h; "eviceInstanceId"
0x18003a06b  movups  xmmword ptr [rcx+20h], xmm0
0x18003a06f  movups  xmm1, xmmword ptr cs:aSystemDevicesD+2Eh; "stanceId"
0x18003a076  movups  xmmword ptr [rcx+2Eh], xmm1
0x18003a07a  mov     [rsp+190h+var_120], rbx
0x18003a07f  lea     r9, [rsp+190h+lpMem]
0x18003a084  lea     r8, [rsp+190h+var_118]
0x18003a089  lea     rdx, [rsp+190h+var_120]
0x18003a08e  lea     rcx, [rbp+90h+var_F0]
0x18003a092  call    ??$SafeGetSwdPropertyFromDeviceInformation@Uhstring@winrt@@@WindowsMidiServicesInternal@@YA?AUhstring@winrt@@U12@UDeviceInformation@Enumeration@Devices@Windows@2@0@Z; WindowsMidiServicesInternal::SafeGetSwdPropertyFromDeviceInformation<winrt::hstring>(winrt::hstring,winrt::Windows::Devices::Enumeration::DeviceInformation,winrt::hstring)
0x18003a097  nop
0x18003a098  cmp     [rbp+90h+var_F0], r13
0x18003a09c  jnz     short loc_18003A107
0x18003a09e  mov     rcx, [rbp+98h]; this
0x18003a0a5  mov     esi, 80004005h
0x18003a0aa  mov     r9d, esi; char *
0x18003a0ad  lea     r8, aAvcoreMidi2Tra_4; "avcore\\midi2\\transport\\ksaggregatetr"...
0x18003a0b4  mov     edx, 568h; void *
0x18003a0b9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003a0be  nop
0x18003a0bf  mov     rbx, [rbp+90h+var_F0]
0x18003a0c3  test    rbx, rbx
0x18003a0c6  jz      short loc_18003A0F3
0x18003a0c8  lock xadd [rbx+18h], edi
0x18003a0cd  sub     edi, 1
0x18003a0d0  jnz     short loc_18003A0E7
0x18003a0d2  nop
0x18003a0d3  call    WINRT_IMPL_GetProcessHeap
0x18003a0d8  mov     rcx, rax; hHeap
0x18003a0db  mov     r8, rbx; lpMem
0x18003a0de  xor     edx, edx; dwFlags
0x18003a0e0  call    WINRT_IMPL_HeapFree
0x18003a0e5  jmp     short loc_18003A0EF
0x18003a0e7  test    edi, edi
0x18003a0e9  js      loc_18003A635
0x18003a0ef  mov     [rbp+90h+var_F0], r13
0x18003a0f3  cmp     [r15], r13
0x18003a0f6  jz      short loc_18003A100
0x18003a0f8  mov     rcx, r15
0x18003a0fb  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18003a100  mov     eax, esi
0x18003a102  jmp     loc_18003ABA1
0x18003a107  xorps   xmm0, xmm0
0x18003a10a  movdqu  [rbp+90h+var_80], xmm0
0x18003a10f  mov     [rbp+90h+var_70], r13
0x18003a113  lea     rdx, [rbp+90h+var_80]
0x18003a117  lea     rcx, [rsp+190h+var_118]
0x18003a11c  call    ??$single_threaded_vector@Uhstring@winrt@@V?$allocator@Uhstring@winrt@@@std@@@winrt@@YA?AU?$IVector@Uhstring@winrt@@@Collections@Foundation@Windows@0@$$QEAV?$vector@Uhstring@winrt@@V?$allocator@Uhstring@winrt@@@std@@@std@@@Z; winrt::single_threaded_vector<winrt::hstring,std::allocator<winrt::hstring>>(std::vector<winrt::hstring> &&)
0x18003a121  nop
0x18003a122  lea     rcx, [rbp+90h+var_80]
0x18003a126  call    ??1?$vector@Uhstring@winrt@@V?$allocator@Uhstring@winrt@@@std@@@std@@QEAA@XZ; std::vector<winrt::hstring>::~vector<winrt::hstring>(void)
0x18003a12b  mov     ebx, 1
0x18003a130  mov     dword ptr [rbp+90h+var_80+8], ebx
0x18003a133  mov     dword ptr [rbp+90h+var_80+0Ch], 21h ; '!'
0x18003a13a  lea     rax, aSystemDevicesD_0; "System.Devices.DeviceManufacturer"
0x18003a141  mov     [rbp+90h+var_68], rax
0x18003a145  lea     rax, [rbp+90h+var_80+8]
0x18003a149  mov     qword ptr [rbp+90h+var_80], rax
0x18003a14d  lea     rdx, [rbp+90h+var_80]
0x18003a151  lea     rcx, [rsp+190h+var_118]
0x18003a156  call    ?Append@?$consume_Windows_Foundation_Collections_IVector@U?$IVector@Uhstring@winrt@@@Collections@Foundation@Windows@winrt@@Uhstring@5@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Foundation::Collections::IVector<winrt::hstring>,winrt::hstring>::Append(winrt::param::hstring const &)
0x18003a15b  mov     dword ptr [rbp+90h+var_80+8], ebx
0x18003a15e  mov     dword ptr [rbp+90h+var_80+0Ch], 1Bh
0x18003a165  lea     rax, aSystemDevicesM; "System.Devices.Manufacturer"
0x18003a16c  mov     [rbp+90h+var_68], rax
0x18003a170  lea     rax, [rbp+90h+var_80+8]
0x18003a174  mov     qword ptr [rbp+90h+var_80], rax
0x18003a178  lea     rdx, [rbp+90h+var_80]
0x18003a17c  lea     rcx, [rsp+190h+var_118]
0x18003a181  call    ?Append@?$consume_Windows_Foundation_Collections_IVector@U?$IVector@Uhstring@winrt@@@Collections@Foundation@Windows@winrt@@Uhstring@5@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Foundation::Collections::IVector<winrt::hstring>,winrt::hstring>::Append(winrt::param::hstring const &)
0x18003a186  mov     dword ptr [rbp+90h+var_80+8], ebx
0x18003a189  mov     dword ptr [rbp+90h+var_80+0Ch], 15h
0x18003a190  lea     rax, aSystemDevicesP_0; "System.Devices.Parent"
0x18003a197  mov     [rbp+90h+var_68], rax
0x18003a19b  lea     rax, [rbp+90h+var_80+8]
0x18003a19f  mov     qword ptr [rbp+90h+var_80], rax
0x18003a1a3  lea     rdx, [rbp+90h+var_80]
0x18003a1a7  lea     rcx, [rsp+190h+var_118]
0x18003a1ac  call    ?Append@?$consume_Windows_Foundation_Collections_IVector@U?$IVector@Uhstring@winrt@@@Collections@Foundation@Windows@winrt@@Uhstring@5@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Foundation::Collections::IVector<winrt::hstring>,winrt::hstring>::Append(winrt::param::hstring const &)
0x18003a1b1  mov     dword ptr [rsp+190h+var_120], 3
0x18003a1b9  lea     rdx, [rsp+190h+var_118]
0x18003a1be  lea     rcx, [rbp+90h+var_D8]
0x18003a1c2  call    ??$?0U?$IVector@Uhstring@winrt@@@Collections@Foundation@Windows@winrt@@$0A@@?$async_iterable@Uhstring@winrt@@@param@winrt@@QEAA@AEBU?$IVector@Uhstring@winrt@@@Collections@Foundation@Windows@2@@Z; winrt::param::async_iterable<winrt::hstring>::async_iterable<winrt::hstring>(winrt::Windows::Foundation::Collections::IVector<winrt::hstring> const &)
0x18003a1c7  nop
0x18003a1c8  mov     rax, [rbp+90h+var_F0]
0x18003a1cc  mov     [rbp+90h+var_B8], rax
0x18003a1d0  lea     rax, [rbp+90h+var_B8]
0x18003a1d4  mov     qword ptr [rbp+90h+var_80], rax
0x18003a1d8  lea     rax, [rbp+90h+var_D8]
0x18003a1dc  mov     qword ptr [rbp+90h+var_80+8], rax
0x18003a1e0  lea     rax, [rsp+190h+var_120]
0x18003a1e5  mov     [rbp+90h+var_70], rax
0x18003a1e9  lea     rax, qword_180096B08
0x18003a1f0  mov     [rbp+90h+var_F8], rax
0x18003a1f4  lock add cs:qword_180096B08, rbx
0x18003a1fc  cmp     cs:??$factory_cache_entry_v@UDeviceInformation@Enumeration@Devices@Windows@winrt@@UIDeviceInformationStatics2@2345@@impl@winrt@@3U?$factory_cache_entry@UDeviceInformation@Enumeration@Devices@Windows@winrt@@UIDeviceInformationStatics2@2345@@12@A, r13; factory_cache_entry<winrt::Windows::Devices::Enumeration::DeviceInformation,winrt::Windows::Devices::Enumeration::IDeviceInformationStatics2>::winrt::factory_cache_entry<winrt::Windows::Devices::Enumeration::DeviceInformation,winrt::Windows::Devices::Enumeration::IDeviceInformationStatics2> winrt::impl::factory_cache_entry_v<winrt::Windows::Devices::Enumeration::DeviceInformation,winrt::Windows::Devices::Enumeration::IDeviceInformationStatics2>
0x18003a203  jz      short loc_18003A225
0x18003a205  lea     r8, ??$factory_cache_entry_v@UDeviceInformation@Enumeration@Devices@Windows@winrt@@UIDeviceInformationStatics2@2345@@impl@winrt@@3U?$factory_cache_entry@UDeviceInformation@Enumeration@Devices@Windows@winrt@@UIDeviceInformationStatics2@2345@@12@A; factory_cache_entry<winrt::Windows::Devices::Enumeration::DeviceInformation,winrt::Windows::Devices::Enumeration::IDeviceInformationStatics2>::winrt::factory_cache_entry<winrt::Windows::Devices::Enumeration::DeviceInformation,winrt::Windows::Devices::Enumeration::IDeviceInformationStatics2> winrt::impl::factory_cache_entry_v<winrt::Windows::Devices::Enumeration::DeviceInformation,winrt::Windows::Devices::Enumeration::IDeviceInformationStatics2>
0x18003a20c  lea     rdx, [rsp+190h+lpMem]
0x18003a211  lea     rcx, [rbp+90h+var_80]
0x18003a215  call    ??R_lambda_1_@?1??CreateFromIdAsync@DeviceInformation@Enumeration@Devices@Windows@winrt@@SA@AEBUhstring@param@6@AEBU?$async_iterable@Uhstring@winrt@@@86@AEBW4DeviceInformationKind@3456@@Z@QEBA@AEBUIDeviceInformationStatics2@3456@@Z; `winrt::Windows::Devices::Enumeration::DeviceInformation::CreateFromIdAsync(winrt::param::hstring const &,winrt::param::async_iterable<winrt::hstring> const &,winrt::Windows::Devices::Enumeration::DeviceInformationKind const &)'::`2'::_lambda_1_::operator()(winrt::Windows::Devices::Enumeration::IDeviceInformationStatics2 const &)
0x18003a21a  nop
0x18003a21b  lock add cs:qword_180096B08, rdi
0x18003a223  jmp     short loc_18003A23C
0x18003a225  lock add cs:qword_180096B08, rdi
0x18003a22d  lea     r8, [rbp+90h+var_80]
0x18003a231  lea     rdx, [rsp+190h+lpMem]
0x18003a236  call    ??$call@AEAV_lambda_1_@?1??CreateFromIdAsync@DeviceInformation@Enumeration@Devices@Windows@winrt@@SA@AEBUhstring@param@7@AEBU?$async_iterable@Uhstring@winrt@@@97@AEBW4DeviceInformationKind@4567@@Z@@?$factory_cache_entry@UDeviceInformation@Enumeration@Devices@Windows@winrt@@UIDeviceInformationStatics2@2345@@impl@winrt@@QEAA?A_PAEAV_lambda_1_@?1??CreateFromIdAsync@DeviceInformation@Enumeration@Devices@Windows@2@SA@AEBUhstring@param@2@AEBU?$async_iterable@Uhstring@winrt@@@param@2@AEBW4DeviceInformationKind@6782@@Z@@Z
0x18003a23b  nop
0x18003a23c  lea     rdx, [rbp+90h+var_108]
0x18003a240  lea     rcx, [rsp+190h+lpMem]
0x18003a245  call    ?get@?$consume_Windows_Foundation_IAsyncOperation@U?$IAsyncOperation@UDeviceInformation@Enumeration@Devices@Windows@winrt@@@Foundation@Windows@winrt@@UDeviceInformation@Enumeration@Devices@34@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_IAsyncOperation<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Devices::Enumeration::DeviceInformation>,winrt::Windows::Devices::Enumeration::DeviceInformation>::get(void)
0x18003a24a  nop
0x18003a24b  cmp     [rsp+190h+lpMem], r13
0x18003a250  jz      short loc_18003A25D
0x18003a252  lea     rcx, [rsp+190h+lpMem]
0x18003a257  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18003a25c  nop
0x18003a25d  cmp     byte ptr [rbp+90h+var_D8+8], r13b
0x18003a261  jnz     short loc_18003A26C
0x18003a263  mov     rax, r13
0x18003a266  mov     qword ptr [rbp+90h+var_D8], rax
0x18003a26a  jmp     short loc_18003A270
0x18003a26c  mov     rax, qword ptr [rbp+90h+var_D8]
0x18003a270  test    rax, rax
0x18003a273  jz      short loc_18003A27E
0x18003a275  lea     rcx, [rbp+90h+var_D8]
0x18003a279  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18003a27e  lea     r12, [r14+40h]
0x18003a282  mov     rcx, r12; lpCriticalSection
0x18003a285  call    cs:__imp_EnterCriticalSection
0x18003a28b  mov     [rbp+90h+var_90], r12
0x18003a28f  lea     rdx, [rsp+190h+lpMem]
0x18003a294  lea     rcx, [rbp+90h+var_108]
0x18003a298  call    ?Id@?$consume_Windows_Devices_Enumeration_IDeviceInformation@UIDeviceInformation@Enumeration@Devices@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Devices_Enumeration_IDeviceInformation<winrt::Windows::Devices::Enumeration::IDeviceInformation>::Id(void)
0x18003a29d  nop
0x18003a29e  mov     rcx, [rax]
0x18003a2a1  test    rcx, rcx
0x18003a2a4  jz      short loc_18003A2AA
0x18003a2a6  mov     rsi, [rcx+10h]
0x18003a2aa  xorps   xmm0, xmm0
0x18003a2ad  movups  [rbp+90h+var_80], xmm0
0x18003a2b1  mov     [rbp+90h+var_70], r13
0x18003a2b5  mov     [rbp+90h+var_68], r13
0x18003a2b9  mov     r8, rdi
0x18003a2bc  inc     r8
0x18003a2bf  cmp     [rsi+r8*2], r13w
0x18003a2c4  jnz     short loc_18003A2BC
0x18003a2c6  mov     rdx, rsi
0x18003a2c9  lea     rcx, [rbp+90h+var_80]
0x18003a2cd  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18003a2d2  nop
0x18003a2d3  lea     rdx, [rbp+90h+var_80]
0x18003a2d7  lea     rcx, [rbp+90h+var_B8]
0x18003a2db  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18003a2e0  mov     rdx, rax
0x18003a2e3  lea     rcx, [rbp+90h+var_60]
0x18003a2e7  call    ?ToUpperTrimmedWStringCopy@WindowsMidiServicesInternal@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V23@@Z; WindowsMidiServicesInternal::ToUpperTrimmedWStringCopy(std::wstring)
0x18003a2ec  nop
0x18003a2ed  lea     rcx, [rbp+90h+var_80]; void *
0x18003a2f1  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003a2f6  nop
0x18003a2f7  mov     rbx, [rsp+190h+lpMem]
0x18003a2fc  test    rbx, rbx
0x18003a2ff  jz      short loc_18003A329
0x18003a301  mov     eax, edi
0x18003a303  lock xadd [rbx+18h], eax
0x18003a308  sub     eax, 1
0x18003a30b  jnz     loc_18003A433
0x18003a311  nop
0x18003a312  call    WINRT_IMPL_GetProcessHeap
0x18003a317  mov     rcx, rax; hHeap
0x18003a31a  mov     r8, rbx; lpMem
0x18003a31d  xor     edx, edx; dwFlags
0x18003a31f  call    WINRT_IMPL_HeapFree
0x18003a324  mov     [rsp+190h+lpMem], r13
0x18003a329  lea     r8, [rbp+90h+var_60]
0x18003a32d  lea     rdx, [rsp+190h+var_130]
0x18003a332  lea     rcx, [r14+30h]
0x18003a336  call    ?find@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VKsAggregateParentDeviceDefinition2@@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VKsAggregateParentDeviceDefinition2@@@2@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VKsAggregateParentDeviceDefinition2@@@2@@std@@@std@@@std@@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Tree<std::_Tmap_traits<std::wstring,std::shared_ptr<KsAggregateParentDeviceDefinition2>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::shared_ptr<KsAggregateParentDeviceDefinition2>>>,0>>::find(std::wstring const &)
0x18003a33b  mov     rbx, [rsp+190h+var_130]
0x18003a340  cmp     rbx, [r14+30h]
0x18003a344  jz      loc_18003A456
0x18003a34a  call    ?Instance@MidiKSAggregateTransportTelemetryProvider@@KAPEAV1@XZ; MidiKSAggregateTransportTelemetryProvider::Instance(void)
0x18003a34f  mov     rcx, [rax+8]
0x18003a353  mov     eax, [rcx]
0x18003a355  cmp     eax, 4
0x18003a358  jbe     short loc_18003A3C2
0x18003a35a  lea     rax, [rbp+90h+var_60]
0x18003a35e  mov     r13d, 7
0x18003a364  cmp     [rbp+90h+var_48], r13
0x18003a368  cmova   rax, [rbp+90h+var_60]
0x18003a36d  mov     [rsp+190h+var_128], rax
0x18003a372  lea     rax, aFoundExistingP; "Found existing parent device."
0x18003a379  mov     [rsp+190h+var_130], rax
0x18003a37e  mov     [rbp+90h+var_100], r14
0x18003a382  lea     rax, aCmidi2ksaggreg_33; "CMidi2KSAggregateMidiEndpointManager2::"...
0x18003a389  mov     [rbp+90h+var_E8], rax
0x18003a38d  lea     rax, [rsp+190h+var_128]
0x18003a392  mov     [rsp+190h+var_158], rax
0x18003a397  lea     rax, [rsp+190h+var_130]
0x18003a39c  mov     [rsp+190h+var_160], rax
0x18003a3a1  lea     rax, [rbp+90h+var_100]
0x18003a3a5  mov     [rsp+190h+var_168], rax
0x18003a3aa  lea     rax, [rbp+90h+var_E8]
  ... truncated ...
```
