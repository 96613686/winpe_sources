# CMidi2KSAggregateMidi::Initialize(ushort const *,__MIDL___MIDL_itf_windowsmidiservices_0000_0000_0002,__MIDL___MIDL_itf_windowsmidiservices_0000_0000_0005 *,ulong *,IMidiCallback *,__int64)

- ea: `0x1800163a8`
- end: `0x18001793e`
- name: `?Initialize@CMidi2KSAggregateMidi@@QEAAJPEBGW4__MIDL___MIDL_itf_windowsmidiservices_0000_0000_0002@@PEAU__MIDL___MIDL_itf_windowsmidiservices_0000_0000_0005@@PEAKPEAUIMidiCallback@@_J@Z`
- size: `5526`
- prototype: ``
- caller_count: `1`
- callee_count: `44`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18001ab10`

## callees

- `0x1800017d0`
- `0x1800018e8`
- `0x180001a94`
- `0x180001bb8`
- `0x180005020`
- `0x180005044`
- `0x180005070`
- `0x180005f44`
- `0x18000b394`
- `0x18000d430`
- `0x1800106c8`
- `0x180010b94`
- `0x1800117d8`
- `0x180012c1c`
- `0x180012cf8`
- `0x180012dd0`
- `0x180013118`
- `0x180013498`
- `0x180013540`
- `0x1800138b8`
- `0x180013cc0`
- `0x180013df4`
- `0x180013f60`
- `0x180014194`
- `0x180014d2c`
- `0x180014ff4`
- `0x1800150c0`
- `0x1800154d4`
- `0x1800161e0`
- `0x1800163a8`
- `0x180017af8`
- `0x180017d30`
- `0x180019094`
- `0x180019b34`
- `0x18001a4a8`
- `0x18001a844`
- `0x180043eb4`
- `0x1800456dc`
- `0x180046490`
- `0x1800467b0`
- `0x180047210`
- `0x180047294`
- `0x1800580b8`
- `0x18005e010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180016579`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180016579`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001704a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001716f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001730f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001753b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180017676`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001771e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001704a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001716f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001730f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001753b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180017676`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001771e`

## string_xrefs

- `0x180017852`: `Completed all initialization`

## pseudocode

```c
// Hidden C++ exception states: #wind=32
__int64 __fastcall CMidi2KSAggregateMidi::Initialize(
        RTL_SRWLOCK *a1,
        unsigned int *a2,
        __int64 a3,
        __int64 a4,
        unsigned int *a5,
        void *a6,
        __int64 a7)
{
  RTL_SRWLOCK *v8; // r14
  __int64 v9; // rdx
  unsigned int v10; // ebx
  _DWORD *v12; // rcx
  int v13; // r8d
  int v14; // r9d
  __int64 v15; // rcx
  char *v16; // rax
  int RequiredBufferSize; // eax
  __int64 v18; // rax
  char HasKey; // bl
  _DWORD *v20; // rcx
  int v21; // r8d
  int v22; // r9d
  bool v23; // zf
  __int64 v24; // rax
  __int64 (__fastcall ***v25)(_QWORD, __int64 *, void **); // rcx
  void *v26; // rdi
  void *v27; // rbx
  int v28; // eax
  int v29; // eax
  char v30; // al
  _DWORD *v31; // rcx
  int v32; // r8d
  int v33; // r9d
  bool v34; // zf
  __int64 v35; // rax
  __int64 (__fastcall ***v36)(_QWORD, __int64 *, const char **); // rcx
  const char *v37; // rsi
  const char *v38; // rbx
  int v39; // eax
  _DWORD *v40; // rcx
  int v41; // r8d
  int v42; // r9d
  char *v43; // r15
  _DWORD *v44; // rcx
  int v45; // r8d
  int v46; // r9d
  __int64 v47; // rbx
  unsigned int *v48; // r13
  _DWORD *v49; // rcx
  int v50; // r8d
  int v51; // r9d
  __int64 *v52; // rax
  __int64 v53; // r8
  __int64 v54; // r8
  unsigned int v55; // ecx
  unsigned int v56; // ecx
  _DWORD *v57; // rcx
  int v58; // r8d
  int v59; // r9d
  const char *v60; // rax
  wchar_t **v61; // rax
  const wchar_t *v62; // rdx
  size_t v63; // rbx
  const wchar_t *v64; // rcx
  size_t v65; // r8
  int v66; // eax
  char v67; // al
  RTL_SRWLOCK *v68; // rcx
  void *v69; // rbx
  __int64 v70; // rax
  RTL_SRWLOCK *v71; // rbx
  int v72; // eax
  void *v73; // rbx
  char *Handle; // rbx
  int v75; // eax
  char IsEnabled; // al
  int v77; // r9d
  CMidi2KSAggregateMidiInProxy *v78; // r14
  const unsigned __int16 *v79; // rdx
  char *v80; // rdx
  CMidi2KSAggregateMidiInProxy *v81; // r14
  void *v82; // rcx
  int v83; // eax
  unsigned int v84; // r14d
  char v85; // al
  PSRWLOCK v86; // r14
  unsigned int v87; // r9d
  wchar_t **v88; // rdx
  __int128 *v89; // rdx
  _DWORD *v90; // rcx
  int v91; // r8d
  int v92; // r9d
  wchar_t **v93; // rax
  unsigned int v94; // r12d
  _DWORD *v95; // rcx
  int v96; // r8d
  int v97; // r9d
  wchar_t **v98; // rax
  _DWORD *v99; // rcx
  int v100; // r8d
  int v101; // r9d
  wchar_t **v102; // rax
  _DWORD *v103; // rcx
  int v104; // r8d
  int v105; // r9d
  wchar_t **v106; // rax
  bool v107; // zf
  _DWORD *v108; // rcx
  int v109; // r8d
  int v110; // r9d
  wchar_t **v111; // rax
  _DWORD *v112; // rcx
  int v113; // r8d
  int v114; // r9d
  int v115; // [rsp+20h] [rbp-E0h]
  struct IMidiCallback *Ptr; // [rsp+30h] [rbp-D0h]
  unsigned __int8 v117; // [rsp+38h] [rbp-C8h]
  char v118; // [rsp+40h] [rbp-C0h]
  char v119[8]; // [rsp+60h] [rbp-A0h] BYREF
  PSRWLOCK SRWLock; // [rsp+68h] [rbp-98h] BYREF
  RTL_SRWLOCK *v121; // [rsp+70h] [rbp-90h] BYREF
  __int64 v122; // [rsp+78h] [rbp-88h] BYREF
  void *v123; // [rsp+80h] [rbp-80h] BYREF
  const char *v124; // [rsp+88h] [rbp-78h] BYREF
  void *Block; // [rsp+90h] [rbp-70h] BYREF
  CMidi2KSAggregateMidiInProxy *v126; // [rsp+98h] [rbp-68h] BYREF
  unsigned int v127; // [rsp+A0h] [rbp-60h] BYREF
  unsigned int v128; // [rsp+A4h] [rbp-5Ch] BYREF
  const wchar_t *v129; // [rsp+A8h] [rbp-58h] BYREF
  int v130[2]; // [rsp+B0h] [rbp-50h] BYREF
  const char *v131; // [rsp+B8h] [rbp-48h] BYREF
  __int64 *i; // [rsp+C0h] [rbp-40h] BYREF
  int v133[2]; // [rsp+C8h] [rbp-38h] BYREF
  const wchar_t *v134; // [rsp+D0h] [rbp-30h] BYREF
  unsigned int *v135; // [rsp+D8h] [rbp-28h] BYREF
  __int128 v136; // [rsp+E0h] [rbp-20h] BYREF
  unsigned int *v137; // [rsp+F0h] [rbp-10h]
  char *v138; // [rsp+F8h] [rbp-8h] BYREF
  char v139; // [rsp+100h] [rbp+0h]
  __int64 v140; // [rsp+108h] [rbp+8h]
  void *v141; // [rsp+118h] [rbp+18h]
  LPVOID pv[2]; // [rsp+120h] [rbp+20h] BYREF
  __int64 v143; // [rsp+130h] [rbp+30h] BYREF
  char v144; // [rsp+140h] [rbp+40h] BYREF
  char v145; // [rsp+150h] [rbp+50h] BYREF
  char v146; // [rsp+160h] [rbp+60h] BYREF
  wchar_t *S1[2]; // [rsp+170h] [rbp+70h] BYREF
  size_t v148; // [rsp+180h] [rbp+80h]
  const wchar_t *v149; // [rsp+188h] [rbp+88h]
  __int128 v150; // [rsp+190h] [rbp+90h] BYREF
  __int64 v151; // [rsp+1A0h] [rbp+A0h]
  unsigned __int64 v152; // [rsp+1A8h] [rbp+A8h]
  wil::details::in1diag3 *retaddr; // [rsp+1F8h] [rbp+F8h]

  v8 = a1;
  v129 = (const wchar_t *)a1;
  v135 = a5;
  LODWORD(v126) = 0;
  if ( !a6 )
  {
    v9 = 25;
LABEL_3:
    v10 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"avcore\\midi2\\transport\\ksaggregatetransport\\midi2.ksaggregatemidi.cpp",
      (const char *)0x80070057LL,
      v115);
    return v10;
  }
  if ( !a5 )
  {
    v9 = 26;
    goto LABEL_3;
  }
  if ( !a2 )
  {
    v9 = 27;
    goto LABEL_3;
  }
  v12 = (_DWORD *)*((_QWORD *)MidiKSAggregateTransportTelemetryProvider::Instance() + 1);
  if ( *v12 > 4u )
  {
    v123 = a2;
    v124 = (const char *)L"Initializing";
    v121 = v8;
    SRWLock = (PSRWLOCK)"CMidi2KSAggregateMidi::Initialize";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
      (_DWORD)v12,
      (unsigned int)&byte_180088CC7,
      v13,
      v14,
      (__int64)&SRWLock,
      (__int64)&v121,
      (__int64)&v124,
      (__int64)&v123);
  }
  v8[5].Ptr = a6;
  v136 = 0;
  v137 = 0;
  winrt::single_threaded_vector<winrt::hstring,std::allocator<winrt::hstring>>(&v121, &v136);
  std::vector<winrt::hstring>::~vector<winrt::hstring>(&v136);
  *((_QWORD *)&v150 + 1) = 0x2800000001LL;
  v152 = (unsigned __int64)L"{05279CB1-002F-4E6B-A3A3-29A87D82B4F7},3";
  *(_QWORD *)&v150 = (char *)&v150 + 8;
  winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Foundation::Collections::IVector<winrt::hstring>,winrt::hstring>::Append(
    &v121,
    &v150);
  *((_QWORD *)&v150 + 1) = 0x2900000001LL;
  v152 = (unsigned __int64)L"{05279CB1-002F-4E6B-A3A3-29A87D82B4F7},16";
  *(_QWORD *)&v150 = (char *)&v150 + 8;
  winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Foundation::Collections::IVector<winrt::hstring>,winrt::hstring>::Append(
    &v121,
    &v150);
  v128 = 1;
  winrt::param::async_iterable<winrt::hstring>::async_iterable<winrt::hstring>(&v138, &v121);
  v15 = -1;
  do
    ++v15;
  while ( *((_WORD *)a2 + v15) );
  if ( (_DWORD)v15 )
  {
    if ( *((_WORD *)a2 + (unsigned int)v15) )
      abort();
    DWORD2(v150) = 1;
    HIDWORD(v150) = v15;
    v152 = (unsigned __int64)a2;
    *(_QWORD *)&v150 = (char *)&v150 + 8;
  }
  else
  {
    *(_QWORD *)&v150 = 0;
  }
  *(_QWORD *)&v136 = &v150;
  *((_QWORD *)&v136 + 1) = &v138;
  v137 = &v128;
  i = &qword_180096B08;
  _InterlockedAdd64(&qword_180096B08, 1u);
  if ( winrt::impl::factory_cache_entry_v<winrt::Windows::Devices::Enumeration::DeviceInformation,winrt::Windows::Devices::Enumeration::IDeviceInformationStatics2> )
  {
    `winrt::Windows::Devices::Enumeration::DeviceInformation::CreateFromIdAsync'::`2'::_lambda_1_::operator()(
      &v136,
      &v123,
      &winrt::impl::factory_cache_entry_v<winrt::Windows::Devices::Enumeration::DeviceInformation,winrt::Windows::Devices::Enumeration::IDeviceInformationStatics2>);
    _InterlockedDecrement64(&qword_180096B08);
  }
  else
  {
    _InterlockedDecrement64(&qword_180096B08);
    ___call_AEAV_lambda_1___1__CreateFromIdAsync_DeviceInformation_Enumeration_Devices_Windows_winrt__SA_AEBUhstring_param_7_AEBU__async_iterable_Uhstring_winrt___97_AEBW4DeviceInformationKind_4567__Z____factory_cache_entry_UDeviceInformation_Enumeration_Devices_Windows_winrt__UIDeviceInformationStatics2_2345__impl_winrt__QEAA_A_PAEAV_lambda_1___1__CreateFromIdAsync_DeviceInformation_Enumeration_Devices_Windows_2_SA_AEBUhstring_param_2_AEBU__async_iterable_Uhstring_winrt___param_2_AEBW4DeviceInformationKind_6782__Z__Z(
      v15,
      &v123,
      &v136);
  }
  winrt::impl::consume_Windows_Foundation_IAsyncOperation<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Devices::Enumeration::DeviceInformation>,winrt::Windows::Devices::Enumeration::DeviceInformation>::get(
    &v123,
    &v122);
  if ( v123 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v123);
  if ( v139 )
  {
    v16 = v138;
  }
  else
  {
    v16 = 0;
    v138 = 0;
  }
  if ( v16 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v138);
  v127 = 4096;
  RequiredBufferSize = GetRequiredBufferSize(&v127);
  v10 = RequiredBufferSize;
  if ( RequiredBufferSize < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3A,
      (unsigned int)"avcore\\midi2\\transport\\ksaggregatetransport\\midi2.ksaggregatemidi.cpp",
      (const char *)(unsigned int)RequiredBufferSize,
      v115);
    if ( v122 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v122);
    if ( v121 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v121);
    return v10;
  }
  v18 = winrt::impl::consume_Windows_Devices_Enumeration_IDeviceInformation<winrt::Windows::Devices::Enumeration::IDeviceInformation>::Properties(
          &v122,
          &v123);
  S1[1] = (wchar_t *)0x2900000001LL;
  v149 = L"{05279CB1-002F-4E6B-A3A3-29A87D82B4F7},16";
  S1[0] = (wchar_t *)&S1[1];
  HasKey = winrt::impl::consume_Windows_Foundation_Collections_IMapView<winrt::Windows::Foundation::Collections::IMapView<winrt::hstring,winrt::Windows::Foundation::IInspectable>,winrt::hstring,winrt::Windows::Foundation::IInspectable>::HasKey(
             v18,
             S1);
  if ( v123 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v123);
  if ( !HasKey )
  {
    v20 = (_DWORD *)*((_QWORD *)MidiKSAggregateTransportTelemetryProvider::Instance() + 1);
    if ( *v20 > 2u )
    {
      v135 = a2;
      v129 = L"Endpoint device properties are missing the pin map";
      v123 = v8;
      v124 = "CMidi2KSAggregateMidi::Initialize";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
        (_DWORD)v20,
        (unsigned int)qword_180088C70,
        v21,
        v22,
        (__int64)&v124,
        (__int64)&v123,
        (__int64)&v129,
        (__int64)&v135);
    }
LABEL_38:
    if ( v122 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v122);
    v23 = v121 == 0;
    goto LABEL_208;
  }
  v24 = winrt::impl::consume_Windows_Devices_Enumeration_IDeviceInformation<winrt::Windows::Devices::Enumeration::IDeviceInformation>::Properties(
          &v122,
          &SRWLock);
  S1[1] = (wchar_t *)0x2900000001LL;
  v149 = L"{05279CB1-002F-4E6B-A3A3-29A87D82B4F7},16";
  S1[0] = (wchar_t *)&S1[1];
  v25 = *(__int64 (__fastcall ****)(_QWORD, __int64 *, void **))winrt::impl::consume_Windows_Foundation_Collections_IMapView<winrt::Windows::Foundation::Collections::IMapView<winrt::hstring,winrt::Windows::Foundation::IInspectable>,winrt::hstring,winrt::Windows::Foundation::IInspectable>::Lookup(
                                                                  v24,
                                                                  &v124,
                                                                  S1);
  v123 = 0;
  if ( v25 )
  {
    LODWORD(v136) = 2123;
    *((_QWORD *)&v136 + 1) = "onecoreuap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt\\base.h";
    v137 = 0;
    v28 = (**v25)(v25, winrt::impl::guid_v<winrt::Windows::Foundation::IPropertyValue>, &v123);
    if ( v28 < 0 )
      winrt::throw_hresult((unsigned int)v28, &v136);
    v26 = v123;
    v27 = v123;
  }
  else
  {
    v26 = 0;
    v27 = 0;
  }
  if ( v124 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v124);
  if ( SRWLock )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&SRWLock);
  Block = 0;
  LODWORD(v126) = 31;
  if ( (unsigned __int8)winrt::Windows::Foundation::operator==(&v123, &Block) )
    goto LABEL_52;
  v128 = 0;
  LODWORD(v136) = 599;
  *((_QWORD *)&v136 + 1) = "onecoreuap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt\\Windows.Foundation.h";
  v137 = 0;
  v29 = (*(__int64 (__fastcall **)(void *, unsigned int *))(*(_QWORD *)v27 + 48LL))(v27, &v128);
  if ( v29 < 0 )
    winrt::throw_hresult((unsigned int)v29, &v136);
  v30 = 0;
  if ( v128 != 1025 )
LABEL_52:
    v30 = 1;
  if ( v30 )
  {
    v31 = (_DWORD *)*((_QWORD *)MidiKSAggregateTransportTelemetryProvider::Instance() + 1);
    if ( *v31 > 2u )
    {
      v135 = a2;
      v129 = L"Unable to retrieve pin map. Property value was nullptr or incorrect property type.";
      v124 = (const char *)v8;
      SRWLock = (PSRWLOCK)"CMidi2KSAggregateMidi::Initialize";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
        (_DWORD)v31,
        (unsigned int)byte_180088C19,
        v32,
        v33,
        (__int64)&SRWLock,
        (__int64)&v124,
        (__int64)&v129,
        (__int64)&v135);
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5D,
      (unsigned int)"avcore\\midi2\\transport\\ksaggregatetransport\\midi2.ksaggregatemidi.cpp",
      (const char *)0x80004005LL,
      v115);
    v34 = v27 == 0;
LABEL_57:
    if ( !v34 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v123);
    goto LABEL_38;
  }
  v35 = winrt::impl::consume_Windows_Devices_Enumeration_IDeviceInformation<winrt::Windows::Devices::Enumeration::IDeviceInformation>::Properties(
          &v122,
          &v126);
  *((_QWORD *)&v150 + 1) = 0x2900000001LL;
  v152 = (unsigned __int64)L"{05279CB1-002F-4E6B-A3A3-29A87D82B4F7},16";
  *(_QWORD *)&v150 = (char *)&v150 + 8;
  v36 = *(__int64 (__fastcall ****)(_QWORD, __int64 *, const char **))winrt::impl::consume_Windows_Foundation_Collections_IMapView<winrt::Windows::Foundation::Collections::IMapView<winrt::hstring,winrt::Windows::Foundation::IInspectable>,winrt::hstring,winrt::Windows::Foundation::IInspectable>::Lookup(
                                                                        v35,
                                                                        &Block,
                                                                        &v150);
  v124 = 0;
  if ( v36 )
  {
    LODWORD(v136) = 2123;
    *((_QWORD *)&v136 + 1) = "onecoreuap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt\\base.h";
    v137 = 0;
    v39 = (**v36)(v36, winrt::impl::guid_v<winrt::Windows::Foundation::IReferenceArray<unsigned char>>, &v124);
    if ( v39 < 0 )
      winrt::throw_hresult((unsigned int)v39, &v136);
    v37 = v124;
    v38 = v124;
  }
  else
  {
    v37 = 0;
    v38 = 0;
  }
  v128 = 254;
  if ( Block )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&Block);
  if ( v126 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v126);
  SRWLock = 0;
  if ( (unsigned __int8)winrt::Windows::Foundation::operator==(&v124, &SRWLock) )
  {
    v40 = (_DWORD *)*((_QWORD *)MidiKSAggregateTransportTelemetryProvider::Instance() + 1);
    if ( *v40 > 2u )
    {
      v135 = a2;
      v129 = L"Unable to retrieve pin map. Property data was nullptr";
      SRWLock = v8;
      Block = "CMidi2KSAggregateMidi::Initialize";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
        (_DWORD)v40,
        (unsigned int)word_180088BC2,
        v41,
        v42,
        (__int64)&Block,
        (__int64)&SRWLock,
        (__int64)&v129,
        (__int64)&v135);
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x6E,
      (unsigned int)"avcore\\midi2\\transport\\ksaggregatetransport\\midi2.ksaggregatemidi.cpp",
      (const char *)0x80004005LL,
      v115);
LABEL_71:
    if ( v38 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v124);
    v34 = v26 == 0;
    goto LABEL_57;
  }
  winrt::impl::consume_Windows_Foundation_IReferenceArray<winrt::Windows::Foundation::IReferenceArray<unsigned char>,unsigned char>::Value(
    &v124,
    pv);
  v43 = (char *)pv[0];
  if ( !pv[0] )
  {
    v44 = (_DWORD *)*((_QWORD *)MidiKSAggregateTransportTelemetryProvider::Instance() + 1);
    if ( *v44 > 2u )
    {
      v135 = a2;
      v129 = L"Unable to retrieve pin map. Pinmap was nullptr";
      SRWLock = v8;
      Block = "CMidi2KSAggregateMidi::Initialize";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
        (_DWORD)v44,
        (unsigned int)byte_180088B6B,
        v45,
        v46,
        (__int64)&Block,
        (__int64)&SRWLock,
        (__int64)&v129,
        (__int64)&v135);
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x80,
      (unsigned int)"avcore\\midi2\\transport\\ksaggregatetransport\\midi2.ksaggregatemidi.cpp",
      (const char *)0x80004005LL,
      v115);
    goto LABEL_71;
  }
  v47 = *(unsigned int *)pv[0];
  v48 = (unsigned int *)((char *)pv[0] + 4);
  v49 = (_DWORD *)*((_QWORD *)MidiKSAggregateTransportTelemetryProvider::Instance() + 1);
  if ( *v49 > 4u )
  {
    LODWORD(v126) = v47;
    SRWLock = (PSRWLOCK)a2;
    Block = L"Pin map retrieved. Processing entries.";
    *(_QWORD *)v133 = v8;
    v131 = "CMidi2KSAggregateMidi::Initialize";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
      (_DWORD)v49,
      (unsigned int)byte_180088B01,
      v50,
      v51,
      (__int64)&v131,
      (__int64)v133,
      (__int64)&Block,
      (__int64)&SRWLock,
      (__int64)&v126);
  }
  if ( v43 == (char *)-4LL )
  {
LABEL_236:
    v112 = (_DWORD *)*((_QWORD *)MidiKSAggregateTransportTelemetryProvider::Instance() + 1);
    if ( *v112 > 4u )
    {
      i = (__int64 *)a2;
      *(_QWORD *)v130 = L"Completed all initialization";
      v134 = (const wchar_t *)v8;
      v131 = "CMidi2KSAggregateMidi::Initialize";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
        (_DWORD)v112,
        (unsigned int)&word_1800887C6,
        v113,
        v114,
        (__int64)&v131,
        (__int64)&v134,
        (__int64)v130,
        (__int64)&i);
    }
    if ( v43 )
      CoTaskMemFree_0(v43);
    if ( v37 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v124);
    if ( v26 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v123);
    if ( v122 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v122);
    if ( v121 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v121);
    return 0;
  }
  v52 = (__int64 *)&v43[v47];
  for ( i = (__int64 *)&v43[v47]; ; v52 = i )
  {
    if ( v48 >= (unsigned int *)v52 )
      goto LABEL_236;
    *(_OWORD *)S1 = 0;
    v148 = 0;
    v149 = 0;
    v53 = -1;
    do
      ++v53;
    while ( *((_WORD *)v48 + v53 + 8) );
    std::wstring::_Construct<1,unsigned short const *>(S1);
    v150 = 0;
    v151 = 0;
    v152 = 7;
    LOWORD(v150) = 0;
    v55 = v48[3];
    if ( v55 )
    {
      v56 = v55 - 1;
      if ( v56 )
      {
        if ( v56 == 1 )
        {
          v151 = 4;
          *(_QWORD *)&v150 = *(_QWORD *)L"Both";
          WORD4(v150) = 0;
        }
      }
      else
      {
        v151 = 6;
        *(_QWORD *)&v150 = *(_QWORD *)L"Source";
        DWORD2(v150) = *(_DWORD *)L"ce";
        WORD6(v150) = 0;
      }
    }
    else
    {
      ____Reallocate_for_V_lambda_1___1_____Assign_G___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV23_QEBG_K_Z_PEBG___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV01__KV_lambda_1___1_____Assign_G_01_AEAAAEAV01_QEBG0_Z_PEBG_Z(
        &v150,
        11,
        v54,
        L"Destination");
    }
    v57 = (_DWORD *)*((_QWORD *)MidiKSAggregateTransportTelemetryProvider::Instance() + 1);
    if ( *v57 > 4u )
    {
      v60 = (const char *)&v150;
      if ( v152 > 7 )
        v60 = (const char *)v150;
      v131 = v60;
      v119[0] = *((_BYTE *)v48 + 4);
      LODWORD(v126) = v48[2];
      v61 = S1;
      if ( (unsigned __int64)v149 > 7 )
        v61 = (wchar_t **)S1[0];
      *(_QWORD *)v133 = v61;
      SRWLock = (PSRWLOCK)a2;
      Block = L"Processing pin map entry.";
      v134 = (const wchar_t *)v8;
      *(_QWORD *)v130 = "CMidi2KSAggregateMidi::Initialize";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapSz<unsigned short>>(
        (_DWORD)v57,
        (unsigned int)byte_180088A83,
        v58,
        v59,
        (__int64)v130,
        (__int64)&v134,
        (__int64)&Block,
        (__int64)&SRWLock,
        (__int64)v133,
        (__int64)&v126,
        (__int64)v119,
        (__int64)&v131);
    }
    std::_Tree<std::_Tmap_traits<std::wstring,std::shared_ptr<KsAggregateParentDeviceDefinition2>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::shared_ptr<KsAggregateParentDeviceDefinition2>>>,0>>::_Find_lower_bound<std::wstring>(
      &v8[10],
      &v138,
      S1);
    if ( *(_BYTE *)(v140 + 25) )
      goto LABEL_114;
    v62 = (const wchar_t *)(v140 + 32);
    v63 = *(_QWORD *)(v140 + 48);
    if ( *(_QWORD *)(v140 + 56) > 7u )
      v62 = *(const wchar_t **)v62;
    *(_QWORD *)v130 = v148;
    v64 = (const wchar_t *)S1;
    if ( (unsigned __int64)v149 > 7 )
      v64 = S1[0];
    v65 = v148;
    if ( v63 < v148 )
      v65 = v63;
    v66 = wmemcmp(v64, v62, v65);
    if ( v66 )
    {
      if ( v66 >= 0 )
LABEL_110:
        v67 = 1;
      else
LABEL_108:
        v67 = -1;
      if ( v67 < 0 )
        goto LABEL_114;
      goto LABEL_112;
    }
    if ( *(_QWORD *)v130 < v63 )
      goto LABEL_108;
    if ( *(_QWORD *)v130 > v63 )
      goto LABEL_110;
LABEL_112:
    if ( (PVOID)v140 != v8[10].Ptr )
    {
      v68 = *(RTL_SRWLOCK **)(v140 + 64);
      goto LABEL_118;
    }
LABEL_114:
    v69 = operator new(0xD8u);
    v141 = v69;
    v70 = std::wstring::wstring(&v138, S1);
    v71 = (RTL_SRWLOCK *)KsHandleWrapper::KsHandleWrapper(v69, v70);
    Block = v71;
    v128 |= 0x100u;
    v72 = KsHandleWrapper::Open(v71);
    LODWORD(SRWLock) = v72;
    if ( v72 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xBE,
        (unsigned int)"avcore\\midi2\\transport\\ksaggregatetransport\\midi2.ksaggregatemidi.cpp",
        (const char *)(unsigned int)v72,
        v115);
      if ( v71 )
      {
        KsHandleWrapper::~KsHandleWrapper((KsHandleWrapper *)v71);
        operator delete(v71);
      }
      goto LABEL_225;
    }
    std::map<std::wstring,std::unique_ptr<KsHandleWrapper>>::insert_or_assign<std::unique_ptr<KsHandleWrapper>>(
      &v8[10],
      &v143,
      S1,
      &Block);
    SRWLock = *(PSRWLOCK *)(v143 + 64);
    v73 = Block;
    if ( Block )
    {
      KsHandleWrapper::~KsHandleWrapper((KsHandleWrapper *)Block);
      operator delete(v73);
    }
    v68 = SRWLock;
LABEL_118:
    Handle = (char *)KsHandleWrapper::GetHandle(v68);
    v138 = Handle;
    if ( (unsigned __int64)(Handle - 1) > 0xFFFFFFFFFFFFFFFDuLL )
    {
      v84 = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xC6,
        (unsigned int)"avcore\\midi2\\transport\\ksaggregatetransport\\midi2.ksaggregatemidi.cpp",
        (const char *)0x8007000ELL,
        v115);
      std::wstring::~wstring(&v150);
      std::wstring::~wstring(S1);
      if ( v43 )
        CoTaskMemFree_0(v43);
      if ( v37 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v124);
      if ( v26 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v123);
      if ( v122 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v122);
      v107 = v121 == 0;
LABEL_220:
      if ( !v107 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v121);
      return v84;
    }
    if ( v48[3] == 1 )
    {
      v126 = 0;
      v75 = Microsoft::WRL::Details::MakeAndInitialize<CMidi2KSAggregateMidiInProxy,CMidi2KSAggregateMidiInProxy,>(&v126);
      LODWORD(SRWLock) = v75;
      if ( v75 >= 0 )
      {
        IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_MIDI2VirtualPortDriversFix>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_MIDI2VirtualPortDriversFix>::GetImpl'::`2'::impl);
        v77 = v48[2];
        v118 = *((_BYTE *)v48 + 4);
        if ( IsEnabled )
        {
          v78 = v126;
          v79 = (const unsigned __int16 *)S1;
          if ( (unsigned __int64)v149 > 7 )
            v79 = S1[0];
          LODWORD(Block) = CMidi2KSAggregateMidiInProxy::Initialize(
                             v126,
                             v79,
                             Handle,
                             v77,
                             v127,
                             v135,
                             *((struct IMidiCallback **)v129 + 5),
                             a7,
                             v118);
          if ( (int)Block < 0 )
          {
            v90 = (_DWORD *)*((_QWORD *)MidiKSAggregateTransportTelemetryProvider::Instance() + 1);
            if ( *v90 > 2u )
            {
              v93 = S1;
              if ( (unsigned __int64)v149 > 7 )
                v93 = (wchar_t **)S1[0];
              i = (__int64 *)v93;
              v119[0] = *((_BYTE *)v48 + 4);
              LODWORD(v126) = v48[2];
              v128 = v127;
              *(_QWORD *)v130 = a2;
              v134 = L"Unable to initialize Midi Input proxy";
              v131 = (const char *)v129;
              *(_QWORD *)v133 = "CMidi2KSAggregateMidi::Initialize";
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapSz<unsigned short>>(
                (_DWORD)v90,
                (unsigned int)&unk_180088A08,
                v91,
                v92,
                (__int64)v133,
                (__int64)&v131,
                (__int64)&v134,
                (__int64)v130,
                (__int64)&v128,
                (__int64)&v126,
                (__int64)v119,
                (__int64)&i);
            }
            v94 = (unsigned int)Block;
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0xF3,
              (unsigned int)"avcore\\midi2\\transport\\ksaggregatetransport\\midi2.ksaggregatemidi.cpp",
              (const char *)(unsigned int)Block,
              v115);
            if ( v78 )
              (*(void (__fastcall **)(CMidi2KSAggregateMidiInProxy *))(*(_QWORD *)v78 + 16LL))(v78);
LABEL_149:
            CloseHandle(Handle);
            std::wstring::~wstring(&v150);
            std::wstring::~wstring(S1);
            if ( v43 )
              CoTaskMemFree_0(v43);
            if ( v37 )
              winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v124);
            if ( v26 )
              winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v123);
            if ( v122 )
              winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v122);
            if ( v121 )
              winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v121);
            return v94;
          }
          v80 = &v144;
        }
        else
        {
          Ptr = (struct IMidiCallback *)v8[5].Ptr;
          v81 = v126;
          LODWORD(SRWLock) = CMidi2KSAggregateMidiInProxy::Initialize(
                               v126,
                               (const unsigned __int16 *)a2,
                               Handle,
                               v77,
                               v127,
                               v135,
                               Ptr,
                               a7,
                               v118);
          if ( (int)SRWLock < 0 )
          {
            v95 = (_DWORD *)*((_QWORD *)MidiKSAggregateTransportTelemetryProvider::Instance() + 1);
            if ( *v95 > 2u )
            {
              v98 = S1;
              if ( (unsigned __int64)v149 > 7 )
                v98 = (wchar_t **)S1[0];
              i = (__int64 *)v98;
              v119[0] = *((_BYTE *)v48 + 4);
              LODWORD(Block) = v48[2];
              LODWORD(v126) = v127;
              *(_QWORD *)v130 = a2;
              v134 = L"Unable to initialize Midi Input proxy";
              v131 = (const char *)v129;
              *(_QWORD *)v133 = "CMidi2KSAggregateMidi::Initialize";
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapSz<unsigned short>>(
                (_DWORD)v95,
                (unsigned int)byte_18008898D,
                v96,
                v97,
                (__int64)v133,
                (__int64)&v131,
                (__int64)&v134,
                (__int64)v130,
                (__int64)&v126,
                (__int64)&Block,
                (__int64)v119,
                (__int64)&i);
            }
            v94 = (unsigned int)SRWLock;
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x118,
              (unsigned int)"avcore\\midi2\\transport\\ksaggregatetransport\\midi2.ksaggregatemidi.cpp",
              (const char *)(unsigned int)SRWLock,
              v115);
            if ( v81 )
              (*(void (__fastcall **)(CMidi2KSAggregateMidiInProxy *))(*(_QWORD *)v81 + 16LL))(v81);
            goto LABEL_149;
          }
          v80 = &v145;
        }
        std::map<unsigned char,wil::com_ptr_t<CMidi2KSAggregateMidiInProxy,wil::err_returncode_policy>>::insert_or_assign<wil::com_ptr_t<CMidi2KSAggregateMidiInProxy,wil::err_returncode_policy>>(
          v129 + 24,
          v80,
          v48 + 1,
          &v126);
        v82 = v126;
        goto LABEL_139;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xCD,
        (unsigned int)"avcore\\midi2\\transport\\ksaggregatetransport\\midi2.ksaggregatemidi.cpp",
        (const char *)(unsigned int)v75,
        v115);
      if ( v126 )
        (*(void (__fastcall **)(CMidi2KSAggregateMidiInProxy *))(*(_QWORD *)v126 + 16LL))(v126);
      CloseHandle(Handle);
LABEL_225:
      std::wstring::~wstring(&v150);
      std::wstring::~wstring(S1);
      if ( v43 )
        CoTaskMemFree_0(v43);
      if ( v37 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v124);
      if ( v26 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v123);
      if ( v122 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v122);
      if ( v121 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v121);
      return (unsigned int)SRWLock;
    }
    if ( v48[3] )
      break;
    SRWLock = 0;
    v83 = Microsoft::WRL::Details::MakeAndInitialize<CMidi2KSAggregateMidiOutProxy,CMidi2KSAggregateMidiOutProxy,>(&SRWLock);
    v84 = v83;
    if ( v83 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x123,
        (unsigned int)"avcore\\midi2\\transport\\ksaggregatetransport\\midi2.ksaggregatemidi.cpp",
        (const char *)(unsigned int)v83,
        v115);
      if ( SRWLock )
        (*((void (__fastcall **)(PSRWLOCK))SRWLock->Ptr + 2))(SRWLock);
      CloseHandle(Handle);
      std::wstring::~wstring(&v150);
      std::wstring::~wstring(S1);
      if ( v43 )
        CoTaskMemFree_0(v43);
      if ( v37 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v124);
      if ( v26 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v123);
      if ( v122 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v122);
      v107 = v121 == 0;
      goto LABEL_220;
    }
    v85 = wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_MIDI2VirtualPortDriversFix>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_MIDI2VirtualPortDriversFix>::GetImpl'::`2'::impl);
    v86 = SRWLock;
    v87 = v48[2];
    v117 = *((_BYTE *)v48 + 4);
    if ( v85 )
    {
      v88 = S1;
      if ( (unsigned __int64)v149 > 7 )
        v88 = (wchar_t **)S1[0];
      LODWORD(v126) = CMidi2KSAggregateMidiOutProxy::Initialize(
                        (CMidi2KSAggregateMidiOutProxy *)SRWLock,
                        (const char *)v88,
                        Handle,
                        v87,
                        v127,
                        v135,
                        a7,
                        v117);
      if ( (int)v126 < 0 )
      {
        v99 = (_DWORD *)*((_QWORD *)MidiKSAggregateTransportTelemetryProvider::Instance() + 1);
        if ( *v99 > 2u )
        {
          v102 = S1;
          if ( (unsigned __int64)v149 > 7 )
            v102 = (wchar_t **)S1[0];
          i = (__int64 *)v102;
          v119[0] = *((_BYTE *)v48 + 4);
          LODWORD(SRWLock) = v48[2];
          LODWORD(Block) = v127;
          *(_QWORD *)v130 = a2;
          v134 = L"Unable to initialize Midi Output proxy";
          v131 = (const char *)v129;
          *(_QWORD *)v133 = "CMidi2KSAggregateMidi::Initialize";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapSz<unsigned short>>(
            (_DWORD)v99,
            (unsigned int)word_180088912,
            v100,
            v101,
            (__int64)v133,
            (__int64)&v131,
            (__int64)&v134,
            (__int64)v130,
            (__int64)&Block,
            (__int64)&SRWLock,
            (__int64)v119,
            (__int64)&i);
        }
        v94 = (unsigned int)v126;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x148,
          (unsigned int)"avcore\\midi2\\transport\\ksaggregatetransport\\midi2.ksaggregatemidi.cpp",
          (const char *)(unsigned int)v126,
          v115);
        if ( v86 )
          (*((void (__fastcall **)(PSRWLOCK))v86->Ptr + 2))(v86);
        goto LABEL_149;
      }
      v89 = (__int128 *)&v146;
    }
    else
    {
      LODWORD(v126) = CMidi2KSAggregateMidiOutProxy::Initialize(
                        (CMidi2KSAggregateMidiOutProxy *)SRWLock,
                        (const char *)a2,
                        Handle,
                        v87,
                        v127,
                        v135,
                        a7,
                        v117);
      if ( (int)v126 < 0 )
      {
        v103 = (_DWORD *)*((_QWORD *)MidiKSAggregateTransportTelemetryProvider::Instance() + 1);
        if ( *v103 > 2u )
        {
          v106 = S1;
          if ( (unsigned __int64)v149 > 7 )
            v106 = (wchar_t **)S1[0];
          i = (__int64 *)v106;
          v119[0] = *((_BYTE *)v48 + 4);
          LODWORD(SRWLock) = v48[2];
          LODWORD(Block) = v127;
          *(_QWORD *)v130 = a2;
          v134 = L"Unable to initialize Midi Output proxy";
          v131 = (const char *)v129;
          *(_QWORD *)v133 = "CMidi2KSAggregateMidi::Initialize";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapSz<unsigned short>>(
            (_DWORD)v103,
            (unsigned int)&byte_180088897,
            v104,
            v105,
            (__int64)v133,
            (__int64)&v131,
            (__int64)&v134,
            (__int64)v130,
            (__int64)&Block,
            (__int64)&SRWLock,
            (__int64)v119,
            (__int64)&i);
        }
        v94 = (unsigned int)v126;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x16C,
          (unsigned int)"avcore\\midi2\\transport\\ksaggregatetransport\\midi2.ksaggregatemidi.cpp",
          (const char *)(unsigned int)v126,
          v115);
        if ( v86 )
          (*((void (__fastcall **)(PSRWLOCK))v86->Ptr + 2))(v86);
        goto LABEL_149;
      }
      v89 = &v136;
    }
    std::map<unsigned char,wil::com_ptr_t<CMidi2KSAggregateMidiInProxy,wil::err_returncode_policy>>::insert_or_assign<wil::com_ptr_t<CMidi2KSAggregateMidiInProxy,wil::err_returncode_policy>>(
      v129 + 32,
      v89,
      v48 + 1,
      &SRWLock);
    v82 = SRWLock;
LABEL_139:
    if ( v82 )
      (*(void (__fastcall **)(void *))(*(_QWORD *)v82 + 16LL))(v82);
    v48 = (unsigned int *)((char *)v48 + *v48);
    CloseHandle(Handle);
    std::wstring::~wstring(&v150);
    std::wstring::~wstring(S1);
    v8 = (RTL_SRWLOCK *)v129;
    if ( !v48 )
      goto LABEL_236;
  }
  v108 = (_DWORD *)*((_QWORD *)MidiKSAggregateTransportTelemetryProvider::Instance() + 1);
  if ( *v108 > 2u )
  {
    v111 = S1;
    if ( (unsigned __int64)v149 > 7 )
      v111 = (wchar_t **)S1[0];
    i = (__int64 *)v111;
    v119[0] = *((_BYTE *)v48 + 4);
    LODWORD(SRWLock) = v48[2];
    LODWORD(Block) = v127;
    *(_QWORD *)v130 = a2;
    v134 = L"Invalid midi flow";
    v131 = (const char *)v8;
    *(_QWORD *)v133 = "CMidi2KSAggregateMidi::Initialize";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapSz<unsigned short>>(
      (_DWORD)v108,
      (unsigned int)&dword_18008881C,
      v109,
      v110,
      (__int64)v133,
      (__int64)&v131,
      (__int64)&v134,
      (__int64)v130,
      (__int64)&Block,
      (__int64)&SRWLock,
      (__int64)v119,
      (__int64)&i);
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x181,
    (unsigned int)"avcore\\midi2\\transport\\ksaggregatetransport\\midi2.ksaggregatemidi.cpp",
    (const char *)0x80004005LL,
    v115);
  CloseHandle(Handle);
  std::wstring::~wstring(&v150);
  std::wstring::~wstring(S1);
  if ( v43 )
    CoTaskMemFree_0(v43);
  if ( v37 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v124);
  if ( v26 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v123);
  if ( v122 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v122);
  v23 = v121 == 0;
LABEL_208:
  if ( !v23 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v121);
  return 2147500037LL;
}

```

## disassembly

```asm
0x1800163a8  mov     [rsp-8+arg_10], rbx
0x1800163ad  push    rbp
0x1800163ae  push    rsi
0x1800163af  push    rdi
0x1800163b0  push    r12
0x1800163b2  push    r13
0x1800163b4  push    r14
0x1800163b6  push    r15
0x1800163b8  lea     rbp, [rsp-0C0h]
0x1800163c0  sub     rsp, 1C0h
0x1800163c7  mov     rax, cs:__security_cookie
0x1800163ce  xor     rax, rsp
0x1800163d1  mov     [rbp+0F0h+var_40], rax
0x1800163d8  mov     r12, rdx
0x1800163db  mov     r14, rcx
0x1800163de  mov     [rbp+0F0h+var_148], rcx
0x1800163e2  mov     rax, [rbp+0F0h+arg_20]
0x1800163e9  mov     [rbp+0F0h+var_118], rax
0x1800163ed  xor     r13d, r13d
0x1800163f0  mov     dword ptr [rbp+0F0h+var_158], r13d
0x1800163f4  mov     rbx, [rbp+0F0h+arg_28]
0x1800163fb  test    rbx, rbx
0x1800163fe  jnz     short loc_180016425
0x180016400  lea     edx, [rbx+19h]; void *
0x180016403  mov     ebx, 80070057h
0x180016408  mov     rcx, [rbp+0F8h]; this
0x18001640f  mov     r9d, ebx; char *
0x180016412  lea     r8, aAvcoreMidi2Tra_7; "avcore\\midi2\\transport\\ksaggregatetr"...
0x180016419  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001641e  mov     eax, ebx
0x180016420  jmp     loc_1800178F0
0x180016425  test    rax, rax
0x180016428  jnz     short loc_18001642F
0x18001642a  lea     edx, [rax+1Ah]
0x18001642d  jmp     short loc_180016403
0x18001642f  test    r12, r12
0x180016432  jnz     short loc_18001643B
0x180016434  lea     edx, [r12+1Bh]
0x180016439  jmp     short loc_180016403
0x18001643b  call    ?Instance@MidiKSAggregateTransportTelemetryProvider@@KAPEAV1@XZ; MidiKSAggregateTransportTelemetryProvider::Instance(void)
0x180016440  mov     rcx, [rax+8]
0x180016444  mov     eax, [rcx]
0x180016446  lea     rdi, aCmidi2ksaggreg_41; "CMidi2KSAggregateMidi::Initialize"
0x18001644d  cmp     eax, 4
0x180016450  jbe     short loc_18001649D
0x180016452  mov     [rbp+0F0h+var_170], r12
0x180016456  lea     rax, aInitializing; "Initializing"
0x18001645d  mov     [rbp+0F0h+var_168], rax
0x180016461  mov     [rsp+1F0h+var_180], r14
0x180016466  mov     [rsp+1F0h+SRWLock], rdi
0x18001646b  lea     rax, [rbp+0F0h+var_170]
0x18001646f  mov     qword ptr [rsp+1F0h+var_1B8], rax
0x180016474  lea     rax, [rbp+0F0h+var_168]
0x180016478  mov     [rsp+1F0h+var_1C0], rax
0x18001647d  lea     rax, [rsp+1F0h+var_180]
0x180016482  mov     [rsp+1F0h+var_1C8], rax
0x180016487  lea     rax, [rsp+1F0h+SRWLock]
0x18001648c  mov     qword ptr [rsp+1F0h+var_1D0], rax; int
0x180016491  lea     rdx, byte_180088CC7
0x180016498  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x18001649d  mov     [r14+28h], rbx
0x1800164a1  xorps   xmm0, xmm0
0x1800164a4  movdqu  [rbp+0F0h+var_110], xmm0
0x1800164a9  mov     [rbp+0F0h+var_100], r13
0x1800164ad  lea     rdx, [rbp+0F0h+var_110]
0x1800164b1  lea     rcx, [rsp+1F0h+var_180]
0x1800164b6  call    ??$single_threaded_vector@Uhstring@winrt@@V?$allocator@Uhstring@winrt@@@std@@@winrt@@YA?AU?$IVector@Uhstring@winrt@@@Collections@Foundation@Windows@0@$$QEAV?$vector@Uhstring@winrt@@V?$allocator@Uhstring@winrt@@@std@@@std@@@Z; winrt::single_threaded_vector<winrt::hstring,std::allocator<winrt::hstring>>(std::vector<winrt::hstring> &&)
0x1800164bb  nop
0x1800164bc  lea     rcx, [rbp+0F0h+var_110]
0x1800164c0  call    ??1?$vector@Uhstring@winrt@@V?$allocator@Uhstring@winrt@@@std@@@std@@QEAA@XZ; std::vector<winrt::hstring>::~vector<winrt::hstring>(void)
0x1800164c5  mov     ebx, 1
0x1800164ca  mov     dword ptr [rbp+0F0h+var_60+8], ebx
0x1800164d0  mov     dword ptr [rbp+0F0h+var_60+0Ch], 28h ; '('
0x1800164da  lea     rax, a05279cb1002f4e_0; "{05279CB1-002F-4E6B-A3A3-29A87D82B4F7},"...
0x1800164e1  mov     [rbp+0F0h+var_48], rax
0x1800164e8  lea     rax, [rbp+0F0h+var_60+8]
0x1800164ef  mov     qword ptr [rbp+0F0h+var_60], rax
0x1800164f6  lea     rdx, [rbp+0F0h+var_60]
0x1800164fd  lea     rcx, [rsp+1F0h+var_180]
0x180016502  call    ?Append@?$consume_Windows_Foundation_Collections_IVector@U?$IVector@Uhstring@winrt@@@Collections@Foundation@Windows@winrt@@Uhstring@5@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Foundation::Collections::IVector<winrt::hstring>,winrt::hstring>::Append(winrt::param::hstring const &)
0x180016507  mov     dword ptr [rbp+0F0h+var_60+8], ebx
0x18001650d  lea     esi, [rbx+28h]
0x180016510  mov     dword ptr [rbp+0F0h+var_60+0Ch], esi
0x180016516  lea     r15, a05279cb1002f4e; "{05279CB1-002F-4E6B-A3A3-29A87D82B4F7},"...
0x18001651d  mov     [rbp+0F0h+var_48], r15
0x180016524  lea     rax, [rbp+0F0h+var_60+8]
0x18001652b  mov     qword ptr [rbp+0F0h+var_60], rax
0x180016532  lea     rdx, [rbp+0F0h+var_60]
0x180016539  lea     rcx, [rsp+1F0h+var_180]
0x18001653e  call    ?Append@?$consume_Windows_Foundation_Collections_IVector@U?$IVector@Uhstring@winrt@@@Collections@Foundation@Windows@winrt@@Uhstring@5@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Foundation::Collections::IVector<winrt::hstring>,winrt::hstring>::Append(winrt::param::hstring const &)
0x180016543  mov     [rbp+0F0h+var_14C], ebx
0x180016546  lea     rdx, [rsp+1F0h+var_180]
0x18001654b  lea     rcx, [rbp+0F0h+var_F8]
0x18001654f  call    ??$?0U?$IVector@Uhstring@winrt@@@Collections@Foundation@Windows@winrt@@$0A@@?$async_iterable@Uhstring@winrt@@@param@winrt@@QEAA@AEBU?$IVector@Uhstring@winrt@@@Collections@Foundation@Windows@2@@Z; winrt::param::async_iterable<winrt::hstring>::async_iterable<winrt::hstring>(winrt::Windows::Foundation::Collections::IVector<winrt::hstring> const &)
0x180016554  nop
0x180016555  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180016559  inc     rcx
0x18001655c  cmp     [r12+rcx*2], r13w
0x180016561  jnz     short loc_180016559
0x180016563  test    ecx, ecx
0x180016565  jnz     short loc_180016570
0x180016567  mov     qword ptr [rbp+0F0h+var_60], r13
0x18001656e  jmp     short loc_1800165A1
0x180016570  mov     eax, ecx
0x180016572  cmp     [r12+rax*2], r13w
0x180016577  jz      short loc_180016580
0x180016579  call    cs:__imp_abort
0x180016580  mov     dword ptr [rbp+0F0h+var_60+8], ebx
0x180016586  mov     dword ptr [rbp+0F0h+var_60+0Ch], ecx
0x18001658c  mov     [rbp+0F0h+var_48], r12
0x180016593  lea     rax, [rbp+0F0h+var_60+8]
0x18001659a  mov     qword ptr [rbp+0F0h+var_60], rax
0x1800165a1  lea     rax, [rbp+0F0h+var_60]
0x1800165a8  mov     qword ptr [rbp+0F0h+var_110], rax
0x1800165ac  lea     rax, [rbp+0F0h+var_F8]
0x1800165b0  mov     qword ptr [rbp+0F0h+var_110+8], rax
0x1800165b4  lea     rax, [rbp+0F0h+var_14C]
0x1800165b8  mov     [rbp+0F0h+var_100], rax
0x1800165bc  lea     rax, qword_180096B08
0x1800165c3  mov     [rbp+0F0h+var_130], rax
0x1800165c7  lock add cs:qword_180096B08, rbx
0x1800165cf  cmp     cs:??$factory_cache_entry_v@UDeviceInformation@Enumeration@Devices@Windows@winrt@@UIDeviceInformationStatics2@2345@@impl@winrt@@3U?$factory_cache_entry@UDeviceInformation@Enumeration@Devices@Windows@winrt@@UIDeviceInformationStatics2@2345@@12@A, r13; factory_cache_entry<winrt::Windows::Devices::Enumeration::DeviceInformation,winrt::Windows::Devices::Enumeration::IDeviceInformationStatics2>::winrt::factory_cache_entry<winrt::Windows::Devices::Enumeration::DeviceInformation,winrt::Windows::Devices::Enumeration::IDeviceInformationStatics2> winrt::impl::factory_cache_entry_v<winrt::Windows::Devices::Enumeration::DeviceInformation,winrt::Windows::Devices::Enumeration::IDeviceInformationStatics2>
0x1800165d6  jz      short loc_1800165F7
0x1800165d8  lea     r8, ??$factory_cache_entry_v@UDeviceInformation@Enumeration@Devices@Windows@winrt@@UIDeviceInformationStatics2@2345@@impl@winrt@@3U?$factory_cache_entry@UDeviceInformation@Enumeration@Devices@Windows@winrt@@UIDeviceInformationStatics2@2345@@12@A; factory_cache_entry<winrt::Windows::Devices::Enumeration::DeviceInformation,winrt::Windows::Devices::Enumeration::IDeviceInformationStatics2>::winrt::factory_cache_entry<winrt::Windows::Devices::Enumeration::DeviceInformation,winrt::Windows::Devices::Enumeration::IDeviceInformationStatics2> winrt::impl::factory_cache_entry_v<winrt::Windows::Devices::Enumeration::DeviceInformation,winrt::Windows::Devices::Enumeration::IDeviceInformationStatics2>
0x1800165df  lea     rdx, [rbp+0F0h+var_170]
0x1800165e3  lea     rcx, [rbp+0F0h+var_110]
0x1800165e7  call    ??R_lambda_1_@?1??CreateFromIdAsync@DeviceInformation@Enumeration@Devices@Windows@winrt@@SA@AEBUhstring@param@6@AEBU?$async_iterable@Uhstring@winrt@@@86@AEBW4DeviceInformationKind@3456@@Z@QEBA@AEBUIDeviceInformationStatics2@3456@@Z; `winrt::Windows::Devices::Enumeration::DeviceInformation::CreateFromIdAsync(winrt::param::hstring const &,winrt::param::async_iterable<winrt::hstring> const &,winrt::Windows::Devices::Enumeration::DeviceInformationKind const &)'::`2'::_lambda_1_::operator()(winrt::Windows::Devices::Enumeration::IDeviceInformationStatics2 const &)
0x1800165ec  nop
0x1800165ed  lock dec cs:qword_180096B08
0x1800165f5  jmp     short loc_18001660D
0x1800165f7  lock dec cs:qword_180096B08
0x1800165ff  lea     r8, [rbp+0F0h+var_110]
0x180016603  lea     rdx, [rbp+0F0h+var_170]
0x180016607  call    ??$call@AEAV_lambda_1_@?1??CreateFromIdAsync@DeviceInformation@Enumeration@Devices@Windows@winrt@@SA@AEBUhstring@param@7@AEBU?$async_iterable@Uhstring@winrt@@@97@AEBW4DeviceInformationKind@4567@@Z@@?$factory_cache_entry@UDeviceInformation@Enumeration@Devices@Windows@winrt@@UIDeviceInformationStatics2@2345@@impl@winrt@@QEAA?A_PAEAV_lambda_1_@?1??CreateFromIdAsync@DeviceInformation@Enumeration@Devices@Windows@2@SA@AEBUhstring@param@2@AEBU?$async_iterable@Uhstring@winrt@@@param@2@AEBW4DeviceInformationKind@6782@@Z@@Z
0x18001660c  nop
0x18001660d  lea     rdx, [rsp+1F0h+var_178]
0x180016612  lea     rcx, [rbp+0F0h+var_170]
0x180016616  call    ?get@?$consume_Windows_Foundation_IAsyncOperation@U?$IAsyncOperation@UDeviceInformation@Enumeration@Devices@Windows@winrt@@@Foundation@Windows@winrt@@UDeviceInformation@Enumeration@Devices@34@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_IAsyncOperation<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Devices::Enumeration::DeviceInformation>,winrt::Windows::Devices::Enumeration::DeviceInformation>::get(void)
0x18001661b  nop
0x18001661c  cmp     [rbp+0F0h+var_170], r13
0x180016620  jz      short loc_18001662C
0x180016622  lea     rcx, [rbp+0F0h+var_170]
0x180016626  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001662b  nop
0x18001662c  cmp     [rbp+0F0h+var_F0], r13b
0x180016630  jnz     short loc_18001663B
0x180016632  mov     rax, r13
0x180016635  mov     [rbp+0F0h+var_F8], rax
0x180016639  jmp     short loc_18001663F
0x18001663b  mov     rax, [rbp+0F0h+var_F8]
0x18001663f  test    rax, rax
0x180016642  jz      short loc_18001664D
0x180016644  lea     rcx, [rbp+0F0h+var_F8]
0x180016648  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001664d  mov     [rbp+0F0h+var_150], 1000h
0x180016654  lea     rcx, [rbp+0F0h+var_150]; unsigned int *
0x180016658  call    ?GetRequiredBufferSize@@YAJAEAK@Z; GetRequiredBufferSize(ulong &)
0x18001665d  mov     ebx, eax
0x18001665f  test    eax, eax
0x180016661  jns     short loc_1800166AB
0x180016663  mov     rcx, [rbp+0F8h]; this
0x18001666a  mov     r9d, eax; char *
0x18001666d  lea     r8, aAvcoreMidi2Tra_7; "avcore\\midi2\\transport\\ksaggregatetr"...
0x180016674  mov     edx, 3Ah ; ':'; void *
0x180016679  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001667e  nop
0x18001667f  cmp     [rsp+1F0h+var_178], r13
0x180016684  jz      short loc_180016691
0x180016686  lea     rcx, [rsp+1F0h+var_178]
0x18001668b  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180016690  nop
0x180016691  cmp     [rsp+1F0h+var_180], r13
0x180016696  jz      loc_18001641E
0x18001669c  lea     rcx, [rsp+1F0h+var_180]
0x1800166a1  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x1800166a6  jmp     loc_18001641E
0x1800166ab  lea     rdx, [rbp+0F0h+var_170]
0x1800166af  lea     rcx, [rsp+1F0h+var_178]
0x1800166b4  call    ?Properties@?$consume_Windows_Devices_Enumeration_IDeviceInformation@UIDeviceInformation@Enumeration@Devices@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Devices_Enumeration_IDeviceInformation<winrt::Windows::Devices::Enumeration::IDeviceInformation>::Properties(void)
0x1800166b9  nop
0x1800166ba  mov     dword ptr [rbp+0F0h+S1+8], 1
0x1800166c1  mov     dword ptr [rbp+0F0h+S1+0Ch], esi
0x1800166c4  mov     [rbp+0F0h+var_68], r15
0x1800166cb  lea     rcx, [rbp+0F0h+S1+8]
0x1800166cf  mov     [rbp+0F0h+S1], rcx
0x1800166d3  lea     rdx, [rbp+0F0h+S1]
0x1800166d7  mov     rcx, rax
0x1800166da  call    ?HasKey@?$consume_Windows_Foundation_Collections_IMapView@U?$IMapView@Uhstring@winrt@@UIInspectable@Foundation@Windows@2@@Collections@Foundation@Windows@winrt@@Uhstring@5@UIInspectable@345@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Foundation_Collections_IMapView<winrt::Windows::Foundation::Collections::IMapView<winrt::hstring,winrt::Windows::Foundation::IInspectable>,winrt::hstring,winrt::Windows::Foundation::IInspectable>::HasKey(winrt::param::hstring const &)
0x1800166df  mov     bl, al
0x1800166e1  cmp     [rbp+0F0h+var_170], r13
0x1800166e5  jz      short loc_1800166F0
0x1800166e7  lea     rcx, [rbp+0F0h+var_170]
0x1800166eb  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x1800166f0  test    bl, bl
0x1800166f2  jnz     short loc_180016768
0x1800166f4  call    ?Instance@MidiKSAggregateTransportTelemetryProvider@@KAPEAV1@XZ; MidiKSAggregateTransportTelemetryProvider::Instance(void)
0x1800166f9  mov     rcx, [rax+8]
0x1800166fd  mov     eax, [rcx]
0x1800166ff  cmp     eax, 2
0x180016702  jbe     short loc_18001674C
0x180016704  mov     [rbp+0F0h+var_118], r12
0x180016708  lea     rax, aEndpointDevice; "Endpoint device properties are missing "...
0x18001670f  mov     [rbp+0F0h+var_148], rax
0x180016713  mov     [rbp+0F0h+var_170], r14
0x180016717  mov     [rbp+0F0h+var_168], rdi
0x18001671b  lea     rax, [rbp+0F0h+var_118]
0x18001671f  mov     qword ptr [rsp+1F0h+var_1B8], rax
0x180016724  lea     rax, [rbp+0F0h+var_148]
0x180016728  mov     [rsp+1F0h+var_1C0], rax
0x18001672d  lea     rax, [rbp+0F0h+var_170]
0x180016731  mov     [rsp+1F0h+var_1C8], rax
0x180016736  lea     rax, [rbp+0F0h+var_168]
0x18001673a  mov     qword ptr [rsp+1F0h+var_1D0], rax
0x18001673f  lea     rdx, qword_180088C70
0x180016746  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x18001674b  nop
0x18001674c  cmp     [rsp+1F0h+var_178], r13
0x180016751  jz      short loc_18001675E
0x180016753  lea     rcx, [rsp+1F0h+var_178]
0x180016758  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001675d  nop
0x18001675e  cmp     [rsp+1F0h+var_180], r13
0x180016763  jmp     loc_1800176D9
0x180016768  lea     rdx, [rsp+1F0h+SRWLock]
0x18001676d  lea     rcx, [rsp+1F0h+var_178]
0x180016772  call    ?Properties@?$consume_Windows_Devices_Enumeration_IDeviceInformation@UIDeviceInformation@Enumeration@Devices@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Devices_Enumeration_IDeviceInformation<winrt::Windows::Devices::Enumeration::IDeviceInformation>::Properties(void)
0x180016777  nop
0x180016778  mov     dword ptr [rbp+0F0h+S1+8], 1
0x18001677f  mov     dword ptr [rbp+0F0h+S1+0Ch], esi
0x180016782  mov     [rbp+0F0h+var_68], r15
0x180016789  lea     rcx, [rbp+0F0h+S1+8]
0x18001678d  mov     [rbp+0F0h+S1], rcx
0x180016791  lea     r8, [rbp+0F0h+S1]
0x180016795  lea     rdx, [rbp+0F0h+var_168]
0x180016799  mov     rcx, rax
0x18001679c  call    ?Lookup@?$consume_Windows_Foundation_Collections_IMapView@U?$IMapView@Uhstring@winrt@@UIInspectable@Foundation@Windows@2@@Collections@Foundation@Windows@winrt@@Uhstring@5@UIInspectable@345@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Foundation_Collections_IMapView<winrt::Windows::Foundation::Collections::IMapView<winrt::hstring,winrt::Windows::Foundation::IInspectable>,winrt::hstring,winrt::Windows::Foundation::IInspectable>::Lookup(winrt::param::hstring const &)
0x1800167a1  nop
0x1800167a2  mov     rcx, [rax]
0x1800167a5  lea     rax, aOnecoreuapInte_4; "onecoreuap\\Internal\\BuildMetadata\\in"...
0x1800167ac  mov     [rbp+0F0h+var_170], r13
0x1800167b0  test    rcx, rcx
0x1800167b3  jnz     short loc_1800167BD
0x1800167b5  mov     rdi, r13
0x1800167b8  mov     rbx, r13
0x1800167bb  jmp     short loc_1800167F5
0x1800167bd  mov     dword ptr [rbp+0F0h+var_110], 84Bh
0x1800167c4  mov     qword ptr [rbp+0F0h+var_110+8], rax
0x1800167c8  mov     [rbp+0F0h+var_100], r13
0x1800167cc  mov     rax, [rcx]
0x1800167cf  lea     r8, [rbp+0F0h+var_170]
0x1800167d3  lea     rdx, ??$guid_v@UIPropertyValue@Foundation@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Foundation::IPropertyValue>
0x1800167da  mov     rax, [rax]
0x1800167dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800167e2  test    eax, eax
0x1800167e4  js      loc_180017926
0x1800167ea  mov     rdi, [rbp+0F0h+var_170]
0x1800167ee  mov     [rbp+0F0h+var_170], rdi
0x1800167f2  mov     rbx, rdi
0x1800167f5  cmp     [rbp+0F0h+var_168], r13
0x1800167f9  jz      short loc_180016805
0x1800167fb  lea     rcx, [rbp+0F0h+var_168]
0x1800167ff  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180016804  nop
0x180016805  cmp     [rsp+1F0h+SRWLock], r13
0x18001680a  jz      short loc_180016816
0x18001680c  lea     rcx, [rsp+1F0h+SRWLock]
0x180016811  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180016816  mov     [rbp+0F0h+Block], r13
0x18001681a  mov     dword ptr [rbp+0F0h+var_158], 1Fh
0x180016821  lea     rdx, [rbp+0F0h+Block]
0x180016825  lea     rcx, [rbp+0F0h+var_170]
0x180016829  call    ??8Foundation@Windows@winrt@@YA_NAEBUIUnknown@012@0@Z; winrt::Windows::Foundation::operator==(winrt::Windows::Foundation::IUnknown const &,winrt::Windows::Foundation::IUnknown const &)
0x18001682e  test    al, al
0x180016830  jnz     short loc_180016873
0x180016832  mov     [rbp+0F0h+var_14C], r13d
0x180016836  mov     dword ptr [rbp+0F0h+var_110], 257h
0x18001683d  lea     rax, aOnecoreuapInte; "onecoreuap\\Internal\\BuildMetadata\\in"...
0x180016844  mov     qword ptr [rbp+0F0h+var_110+8], rax
0x180016848  mov     [rbp+0F0h+var_100], r13
0x18001684c  mov     rax, [rbx]
0x18001684f  lea     rdx, [rbp+0F0h+var_14C]
0x180016853  mov     rcx, rbx
0x180016856  mov     rax, [rax+30h]
0x18001685a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001685f  test    eax, eax
0x180016861  js      loc_180017932
0x180016867  cmp     [rbp+0F0h+var_14C], 401h
0x18001686e  mov     al, r13b
0x180016871  jz      short loc_180016875
0x180016873  mov     al, 1
0x180016875  test    al, al
0x180016877  jz      loc_180016913
0x18001687d  call    ?Instance@MidiKSAggregateTransportTelemetryProvider@@KAPEAV1@XZ; MidiKSAggregateTransportTelemetryProvider::Instance(void)
0x180016882  mov     rcx, [rax+8]
0x180016886  mov     eax, [rcx]
0x180016888  cmp     eax, 2
0x18001688b  jbe     short loc_1800168DD
0x18001688d  mov     [rbp+0F0h+var_118], r12
0x180016891  lea     rax, aUnableToRetrie_1; "Unable to retrieve pin map. Property va"...
0x180016898  mov     [rbp+0F0h+var_148], rax
  ... truncated ...
```
