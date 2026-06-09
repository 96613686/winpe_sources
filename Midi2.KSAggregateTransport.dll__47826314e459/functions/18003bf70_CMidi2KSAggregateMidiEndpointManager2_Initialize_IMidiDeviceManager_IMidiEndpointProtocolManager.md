# CMidi2KSAggregateMidiEndpointManager2::Initialize(IMidiDeviceManager *,IMidiEndpointProtocolManager *)

- ea: `0x18003bf70`
- end: `0x18003c823`
- name: `?Initialize@CMidi2KSAggregateMidiEndpointManager2@@UEAAJPEAUIMidiDeviceManager@@PEAUIMidiEndpointProtocolManager@@@Z`
- size: `2227`
- prototype: `__int64 __fastcall(CMidi2KSAggregateMidiEndpointManager2 *__hidden this, struct IMidiDeviceManager *, struct IMidiEndpointProtocolManager *)`
- caller_count: `0`
- callee_count: `42`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x18000163c`
- `0x1800016dc`
- `0x180001d3c`
- `0x180005020`
- `0x180005070`
- `0x180005e16`
- `0x180005f2c`
- `0x180005fa4`
- `0x180008950`
- `0x18000b394`
- `0x18000d4dc`
- `0x18000d54c`
- `0x18000d5bc`
- `0x18000d62c`
- `0x18000d69c`
- `0x18000de1c`
- `0x180010b94`
- `0x1800117d8`
- `0x180013f60`
- `0x180014d2c`
- `0x1800154d4`
- `0x18001a124`
- `0x18001a4a8`
- `0x18001f960`
- `0x18001f9c8`
- `0x180022a38`
- `0x180022ad0`
- `0x180022b68`
- `0x180022c00`
- `0x180022c98`
- `0x18002328c`
- `0x180024bfc`
- `0x180028d40`
- `0x180029110`
- `0x180029210`
- `0x1800293d8`
- `0x180033538`
- `0x180033a24`
- `0x1800345e0`
- `0x18003bf70`
- `0x180042480`
- `0x18005e010`

## import_xrefs

- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18003c7eb`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18003c7eb`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18003c2c3`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18003c2c3`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18003c7dc`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18003c7dc`
- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x18003c664`
- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x18003c664`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18003c69f`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18003c6c2`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18003c69f`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18003c6c2`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x18003c120`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x18003c120`

## string_xrefs

- `0x18003c6ff`: `Enumeration completed or timed out with endpoint definitions left pending.`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CMidi2KSAggregateMidiEndpointManager2::Initialize(
        CMidi2KSAggregateMidiEndpointManager2 *this,
        __int64 (__fastcall ***a2)(struct IMidiDeviceManager *, GUID *, char *),
        __int64 (__fastcall ***a3)(struct IMidiEndpointProtocolManager *, GUID *, char *))
{
  _DWORD *v6; // rcx
  int v7; // r8d
  int v8; // r9d
  __int64 v9; // rdx
  int v10; // ebx
  __int64 (__fastcall *v12)(struct IMidiDeviceManager *, GUID *, char *); // r15
  __int64 v13; // rcx
  __int64 (__fastcall *v14)(struct IMidiEndpointProtocolManager *, GUID *, char *); // rsi
  __int64 v15; // rcx
  __int64 v16; // rdx
  __int64 v17; // rcx
  int *v18; // rbx
  int v19; // eax
  double LowPart; // xmm1_8
  double v21; // xmm1_8
  unsigned __int64 v22; // rcx
  unsigned int v23; // edx
  _DWORD *v24; // rcx
  volatile signed __int32 *v25; // r14
  _OWORD *v26; // rcx
  const wchar_t *v27; // rax
  __int64 v28; // rdx
  int v29; // eax
  __int64 v30; // rbx
  _QWORD *v31; // r15
  __int64 v32; // rax
  char *v33; // rax
  __int64 v34; // r8
  __int64 v35; // rax
  __int64 v36; // r8
  __int64 v37; // rax
  __int64 v38; // r8
  __int64 v39; // rax
  __int64 v40; // r8
  __int64 v41; // rax
  __int64 v42; // r8
  __int64 v43; // rax
  _DWORD *v44; // rbx
  _QWORD *v45; // rax
  DWORD v46; // eax
  unsigned int v47; // r8d
  const char *v48; // r9
  DWORD v49; // eax
  unsigned int v50; // r8d
  const char *v51; // r9
  _DWORD *v52; // rcx
  int v53; // r8d
  int v54; // r9d
  int v55; // esi
  HANDLE ProcessHeap; // rax
  int v57; // [rsp+20h] [rbp-E0h]
  _BYTE v58[24]; // [rsp+40h] [rbp-C0h] BYREF
  const wchar_t *v59; // [rsp+58h] [rbp-A8h]
  LARGE_INTEGER Frequency; // [rsp+60h] [rbp-A0h] BYREF
  int v61[2]; // [rsp+68h] [rbp-98h] BYREF
  const wchar_t *v62; // [rsp+70h] [rbp-90h] BYREF
  int v63; // [rsp+78h] [rbp-88h] BYREF
  __int64 v64; // [rsp+80h] [rbp-80h] BYREF
  __int64 v65; // [rsp+88h] [rbp-78h] BYREF
  __int64 v66; // [rsp+90h] [rbp-70h] BYREF
  __int64 v67; // [rsp+98h] [rbp-68h] BYREF
  __int128 v68; // [rsp+A0h] [rbp-60h] BYREF
  _DWORD *v69; // [rsp+B0h] [rbp-50h]
  const wchar_t *v70; // [rsp+B8h] [rbp-48h] BYREF
  CMidi2KSAggregateMidiEndpointManager2 *v71; // [rsp+C0h] [rbp-40h] BYREF
  volatile signed __int32 *v72; // [rsp+C8h] [rbp-38h] BYREF
  _BYTE v73[32]; // [rsp+F0h] [rbp-10h] BYREF
  const char *v74; // [rsp+110h] [rbp+10h]
  __int64 v75; // [rsp+118h] [rbp+18h]
  LARGE_INTEGER *p_Frequency; // [rsp+120h] [rbp+20h]
  __int64 v77; // [rsp+128h] [rbp+28h]
  const wchar_t *v78; // [rsp+130h] [rbp+30h]
  __int64 v79; // [rsp+138h] [rbp+38h]
  const wchar_t **v80; // [rsp+140h] [rbp+40h]
  __int64 v81; // [rsp+148h] [rbp+48h]
  int *v82; // [rsp+150h] [rbp+50h]
  __int64 v83; // [rsp+158h] [rbp+58h]
  wil::details::in1diag3 *retaddr; // [rsp+1A8h] [rbp+A8h]

  v6 = (_DWORD *)*((_QWORD *)MidiKSAggregateTransportTelemetryProvider::Instance() + 1);
  if ( *v6 > 4u )
  {
    v62 = L"Enter";
    Frequency.QuadPart = (LONGLONG)this;
    *(_QWORD *)v61 = "CMidi2KSAggregateMidiEndpointManager2::Initialize";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>>(
      (_DWORD)v6,
      (unsigned int)word_18008AD62,
      v7,
      v8,
      (__int64)v61,
      (__int64)&Frequency,
      (__int64)&v62);
  }
  if ( !a2 )
  {
    v9 = 42;
LABEL_5:
    v10 = -2147024809;
LABEL_6:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"avcore\\midi2\\transport\\ksaggregatetransport\\midi2.ksaggregatemidiendpointmanager2.cpp",
      (const char *)(unsigned int)v10,
      v57);
    return (unsigned int)v10;
  }
  if ( !a3 )
  {
    v9 = 43;
    goto LABEL_5;
  }
  v12 = **a2;
  v13 = *((_QWORD *)this + 4);
  *((_QWORD *)this + 4) = 0;
  if ( v13 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
  v10 = v12((struct IMidiDeviceManager *)a2, &GUID_a04374d3_4514_44e1_a2f9_7d8b907aef1f, (char *)this + 32);
  if ( v10 < 0 )
  {
    v9 = 45;
    goto LABEL_6;
  }
  v14 = **a3;
  v15 = *((_QWORD *)this + 5);
  *((_QWORD *)this + 5) = 0;
  if ( v15 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
  v10 = v14((struct IMidiEndpointProtocolManager *)a3, &GUID_7a3def20_fb76_49b6_a3a0_3dcbcda8f482, (char *)this + 40);
  if ( v10 < 0 )
  {
    v9 = 46;
    goto LABEL_6;
  }
  v18 = (int *)((char *)this + 24);
  if ( (int)wil::reg::get_value_dword_nothrow<unsigned long,0>(
              v17,
              v16,
              L"KsaInterfaceEnumTimeoutMS",
              (char *)this + 24) < 0 )
  {
    v19 = 300;
  }
  else
  {
    v19 = 20;
    if ( (unsigned int)*v18 > 0x14 )
    {
      v19 = 2500;
      if ( (unsigned int)*v18 < 0x9C4 )
        v19 = *v18;
    }
  }
  *v18 = v19;
  Frequency.QuadPart = 0;
  QueryPerformanceFrequency(&Frequency);
  if ( Frequency.QuadPart < 0 )
    LowPart = (double)(int)(Frequency.LowPart & 1 | ((unsigned __int64)Frequency.QuadPart >> 1))
            + (double)(int)(Frequency.LowPart & 1 | ((unsigned __int64)Frequency.QuadPart >> 1));
  else
    LowPart = (double)(int)Frequency.LowPart;
  v21 = LowPart * (double)*v18 / 1000.0;
  v22 = 0;
  if ( v21 >= 9.223372036854776e18 )
  {
    v21 = v21 - 9.223372036854776e18;
    if ( v21 < 9.223372036854776e18 )
      v22 = 0x8000000000000000uLL;
  }
  *((_QWORD *)this + 2) = v22 + (unsigned int)(int)v21;
  v24 = (_DWORD *)*((_QWORD *)MidiKSAggregateTransportTelemetryProvider::Instance() + 1);
  if ( *v24 > 4u )
  {
    v63 = *v18;
    v62 = (const wchar_t *)*((_QWORD *)this + 2);
    Frequency.QuadPart = (LONGLONG)this;
    v82 = &v63;
    v83 = 4;
    v80 = &v62;
    v81 = 8;
    v78 = L"Calculated max timeout for interfact arrival";
    v79 = 90;
    p_Frequency = &Frequency;
    v77 = 8;
    v74 = "CMidi2KSAggregateMidiEndpointManager2::Initialize";
    v75 = 50;
    tlgWriteTransfer_EventWriteTransfer(v24, byte_18008AD15, 0, 0, 7, v73);
  }
  v25 = (volatile signed __int32 *)winrt::impl::precreate_hstring_on_heap((winrt::impl *)0x9A, v23);
  v26 = v25 + 7;
  if ( v25 == (volatile signed __int32 *)-28LL )
  {
    *(_DWORD *)_o__errno() = 22;
    invalid_parameter_noinfo();
  }
  else
  {
    v27 = L"System.Devices.InterfaceClassGuid:=\"{6994AD04-93EF-11D0-A3CC-00A0C9223196}\" AND System.Devices.InterfaceEnab"
           "led: = System.StructuredQueryType.Boolean#True";
    v28 = 2;
    do
    {
      *v26 = *(_OWORD *)v27;
      v26[1] = *((_OWORD *)v27 + 1);
      v26[2] = *((_OWORD *)v27 + 2);
      v26[3] = *((_OWORD *)v27 + 3);
      v26[4] = *((_OWORD *)v27 + 4);
      v26[5] = *((_OWORD *)v27 + 5);
      v26[6] = *((_OWORD *)v27 + 6);
      v26[7] = *((_OWORD *)v27 + 7);
      v26 += 8;
      v27 += 64;
      --v28;
    }
    while ( v28 );
    *v26 = *(_OWORD *)v27;
    v26[1] = *((_OWORD *)v27 + 1);
    v26[2] = *((_OWORD *)v27 + 2);
    *((_DWORD *)v26 + 12) = *((_DWORD *)v27 + 12);
  }
  memset(v58, 0, sizeof(v58));
  winrt::single_threaded_vector<winrt::hstring,std::allocator<winrt::hstring>>(&Frequency, v58);
  std::vector<winrt::hstring>::~vector<winrt::hstring>(v58);
  *(_QWORD *)&v58[8] = 0x1500000001LL;
  v59 = L"System.Devices.Parent";
  *(_QWORD *)v58 = &v58[8];
  winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Foundation::Collections::IVector<winrt::hstring>,winrt::hstring>::Append(
    &Frequency,
    v58);
  v72 = v25;
  v62 = (const wchar_t *)&v72;
  _InterlockedIncrement64(&qword_180096AE8);
  if ( winrt::impl::factory_cache_entry_v<winrt::Windows::Devices::Enumeration::DeviceInformation,winrt::Windows::Devices::Enumeration::IDeviceInformationStatics> )
  {
    *(_QWORD *)v61 = 0;
    *(_DWORD *)v58 = 918;
    *(_QWORD *)&v58[8] = "onecoreuap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt/Windows.Devices.Enumeration.h";
    *(_QWORD *)&v58[16] = 0;
    v29 = (*(__int64 (__fastcall **)(__int64, volatile signed __int32 *, int *))(*(_QWORD *)winrt::impl::factory_cache_entry_v<winrt::Windows::Devices::Enumeration::DeviceInformation,winrt::Windows::Devices::Enumeration::IDeviceInformationStatics>
                                                                               + 112LL))(
            winrt::impl::factory_cache_entry_v<winrt::Windows::Devices::Enumeration::DeviceInformation,winrt::Windows::Devices::Enumeration::IDeviceInformationStatics>,
            v72,
            v61);
    if ( v29 < 0 )
      winrt::throw_hresult((unsigned int)v29, v58);
    v30 = *(_QWORD *)v61;
    v64 = *(_QWORD *)v61;
    _InterlockedAdd64(&qword_180096AE8, 0xFFFFFFFFFFFFFFFFuLL);
  }
  else
  {
    _InterlockedAdd64(&qword_180096AE8, 0xFFFFFFFFFFFFFFFFuLL);
    ___call_AEAV_lambda_1___1__CreateWatcher_DeviceInformation_Enumeration_Devices_Windows_winrt__SA_AEBUhstring_param_7__Z____factory_cache_entry_UDeviceInformation_Enumeration_Devices_Windows_winrt__UIDeviceInformationStatics_2345__impl_winrt__QEAA_A_PAEAV_lambda_1___1__CreateWatcher_DeviceInformation_Enumeration_Devices_Windows_2_SA_AEBUhstring_param_2__Z__Z(
      0,
      &v64,
      &v62);
    v30 = v64;
  }
  v31 = (_QWORD *)((char *)this + 272);
  if ( (__int64 *)((char *)this + 272) != &v64 )
  {
    if ( *v31 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref((char *)this + 272);
    v32 = v30;
    v30 = 0;
    v64 = 0;
    *v31 = v32;
  }
  if ( v30 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v64);
  *(_QWORD *)&v58[8] = &CMidi2KSAggregateMidiEndpointManager2::OnFilterDeviceInterfaceAdded;
  *(_DWORD *)&v58[16] = 0;
  *(_DWORD *)&v58[20] = (unsigned __int64)&CMidi2KSAggregateMidiEndpointManager2::OnFilterDeviceInterfaceAdded >> 32;
  v33 = (char *)operator new(0x28u);
  *((_DWORD *)v33 + 2) = 1;
  *((_QWORD *)v33 + 2) = this;
  *(_OWORD *)(v33 + 24) = *(_OWORD *)&v58[8];
  _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
  *(_QWORD *)v33 = ___7__delegate_U__TypedEventHandler_UDeviceWatcher_Enumeration_Devices_Windows_winrt__UDeviceInformation_2345__Foundation_Windows_winrt__V_lambda_20____0_____0VCMidi2KSAggregateMidiEndpointManager__P80_EAAJUDeviceWatcher_Enumeration_Devices_Windows_winrt__UDeviceInformation_2345__Z_1234_QEAA_PEAVCMidi2KSAggregateMidiEndpointManager__P86_EAAJUDeviceWatcher_Enumeration_Devices_34_UDeviceInformation_8934__Z_Z__impl_winrt__6B_;
  v62 = (const wchar_t *)v33;
  *(_QWORD *)v58 = CMidi2KSAggregateMidiEndpointManager2::OnFilterDeviceInterfaceRemoved;
  *(_DWORD *)&v58[8] = 0;
  winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Devices::Enumeration::DeviceWatcher,winrt::Windows::Devices::Enumeration::DeviceInformationUpdate>::TypedEventHandler<winrt::Windows::Devices::Enumeration::DeviceWatcher,winrt::Windows::Devices::Enumeration::DeviceInformationUpdate>(
    v61,
    this,
    v58);
  *(_QWORD *)v58 = &CMidi2KSAggregateMidiEndpointManager2::OnFilterDeviceInterfaceUpdated;
  *(_DWORD *)&v58[8] = 0;
  winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Devices::Enumeration::DeviceWatcher,winrt::Windows::Devices::Enumeration::DeviceInformationUpdate>::TypedEventHandler<winrt::Windows::Devices::Enumeration::DeviceWatcher,winrt::Windows::Devices::Enumeration::DeviceInformationUpdate>(
    &v67,
    this,
    v58);
  *(_QWORD *)v58 = &CMidi2KSAggregateMidiEndpointManager2::OnEnumerationCompleted;
  *(_DWORD *)&v58[8] = 0;
  winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Devices::Enumeration::DeviceWatcher,winrt::Windows::Foundation::IInspectable>::TypedEventHandler<winrt::Windows::Devices::Enumeration::DeviceWatcher,winrt::Windows::Foundation::IInspectable>(
    &v66,
    this,
    v58);
  *(_QWORD *)v58 = &CMidi2KSAggregateMidiEndpointManager2::OnEnumerationCompleted;
  *(_DWORD *)&v58[8] = 0;
  winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Devices::Enumeration::DeviceWatcher,winrt::Windows::Foundation::IInspectable>::TypedEventHandler<winrt::Windows::Devices::Enumeration::DeviceWatcher,winrt::Windows::Foundation::IInspectable>(
    &v65,
    this,
    v58);
  v35 = winrt::impl::consume_Windows_Devices_Enumeration_IDeviceWatcher<winrt::Windows::Devices::Enumeration::IDeviceWatcher>::Added(
          (char *)this + 272,
          v58,
          v34,
          &v62);
  __4__event_revoker_UIDeviceWatcher_Enumeration_Devices_Windows_winrt___MP8type___abi_UIDeviceWatcher_Enumeration_Devices_Windows_winrt__X_impl_5_EAAHUevent_token_5___E1___96785__BDI_AA_impl_winrt__QEAAAEAU012___QEAU012__Z(
    (char *)this + 280,
    v35);
  __1__event_revoker_UIDeviceWatcher_Enumeration_Devices_Windows_winrt___MP8type___abi_UIDeviceWatcher_Enumeration_Devices_Windows_winrt__X_impl_5_EAAHUevent_token_5___E1___96785__BDI_AA_impl_winrt__QEAA_XZ(v58);
  v37 = winrt::impl::consume_Windows_Devices_Enumeration_IDeviceWatcher<winrt::Windows::Devices::Enumeration::IDeviceWatcher>::Removed(
          (char *)this + 272,
          v58,
          v36,
          v61);
  __4__event_revoker_UIDeviceWatcher_Enumeration_Devices_Windows_winrt___MP8type___abi_UIDeviceWatcher_Enumeration_Devices_Windows_winrt__X_impl_5_EAAHUevent_token_5___E1___96785__BFI_AA_impl_winrt__QEAAAEAU012___QEAU012__Z(
    (char *)this + 296,
    v37);
  __1__event_revoker_UIDeviceWatcher_Enumeration_Devices_Windows_winrt___MP8type___abi_UIDeviceWatcher_Enumeration_Devices_Windows_winrt__X_impl_5_EAAHUevent_token_5___E1___96785__BFI_AA_impl_winrt__QEAA_XZ(v58);
  v39 = winrt::impl::consume_Windows_Devices_Enumeration_IDeviceWatcher<winrt::Windows::Devices::Enumeration::IDeviceWatcher>::Updated(
          (char *)this + 272,
          v58,
          v38,
          &v67);
  __4__event_revoker_UIDeviceWatcher_Enumeration_Devices_Windows_winrt___MP8type___abi_UIDeviceWatcher_Enumeration_Devices_Windows_winrt__X_impl_5_EAAHUevent_token_5___E1___96785__BEI_AA_impl_winrt__QEAAAEAU012___QEAU012__Z(
    (char *)this + 312,
    v39);
  __1__event_revoker_UIDeviceWatcher_Enumeration_Devices_Windows_winrt___MP8type___abi_UIDeviceWatcher_Enumeration_Devices_Windows_winrt__X_impl_5_EAAHUevent_token_5___E1___96785__BEI_AA_impl_winrt__QEAA_XZ(v58);
  v41 = winrt::impl::consume_Windows_Devices_Enumeration_IDeviceWatcher<winrt::Windows::Devices::Enumeration::IDeviceWatcher>::Stopped(
          (char *)this + 272,
          v58,
          v40,
          &v66);
  __4__event_revoker_UIDeviceWatcher_Enumeration_Devices_Windows_winrt___MP8type___abi_UIDeviceWatcher_Enumeration_Devices_Windows_winrt__X_impl_5_EAAHUevent_token_5___E1___96785__BHI_AA_impl_winrt__QEAAAEAU012___QEAU012__Z(
    (char *)this + 328,
    v41);
  __1__event_revoker_UIDeviceWatcher_Enumeration_Devices_Windows_winrt___MP8type___abi_UIDeviceWatcher_Enumeration_Devices_Windows_winrt__X_impl_5_EAAHUevent_token_5___E1___96785__BHI_AA_impl_winrt__QEAA_XZ(v58);
  v43 = winrt::impl::consume_Windows_Devices_Enumeration_IDeviceWatcher<winrt::Windows::Devices::Enumeration::IDeviceWatcher>::EnumerationCompleted(
          (char *)this + 272,
          v58,
          v42,
          &v65);
  __4__event_revoker_UIDeviceWatcher_Enumeration_Devices_Windows_winrt___MP8type___abi_UIDeviceWatcher_Enumeration_Devices_Windows_winrt__X_impl_5_EAAHUevent_token_5___E1___96785__BGI_AA_impl_winrt__QEAAAEAU012___QEAU012__Z(
    (char *)this + 344,
    v43);
  __1__event_revoker_UIDeviceWatcher_Enumeration_Devices_Windows_winrt___MP8type___abi_UIDeviceWatcher_Enumeration_Devices_Windows_winrt__X_impl_5_EAAHUevent_token_5___E1___96785__BGI_AA_impl_winrt__QEAA_XZ(v58);
  _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z((char *)this + 232);
  _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z((char *)this + 224);
  _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z((char *)this + 240);
  v68 = 0;
  v44 = operator new(0x20u);
  *v44 = 1;
  v44[1] = 2;
  *((_QWORD *)v44 + 1) = 0;
  *((_QWORD *)v44 + 2) = 0;
  v44[6] = 0;
  v69 = v44;
  _InterlockedIncrement(v44);
  v45 = operator new(0x20u);
  *v45 = v44;
  v45[1] = CMidi2KSAggregateMidiEndpointManager2::EndpointCreationThreadWorker;
  *((_DWORD *)v45 + 4) = 0;
  *((_DWORD *)v45 + 5) = *(_DWORD *)&v58[12];
  v45[3] = this;
  *(_QWORD *)&v68 = _o__beginthreadex(
                      0,
                      0,
                      std::thread::_Invoke<std::tuple<std::_Front_binder<void (CMidi2KSAggregateMidiEndpointManager2::*)(std::stop_token),CMidi2KSAggregateMidiEndpointManager2 *>,std::stop_token>,0,1>,
                      v45,
                      0,
                      (char *)&v68 + 8);
  if ( !(_QWORD)v68 )
  {
    DWORD2(v68) = 0;
    std::_Throw_Cpp_error(6);
    __debugbreak();
  }
  std::jthread::operator=((char *)this + 248, &v68);
  winrt::impl::consume_Windows_Devices_Enumeration_IDeviceWatcher<winrt::Windows::Devices::Enumeration::IDeviceWatcher>::Start((char *)this + 272);
  v46 = WaitForSingleObjectEx(*((HANDLE *)this + 28), 0x9C40u, 0);
  if ( v46 != 258 && v46 )
    wil::details::in1diag3::FailFast_Unexpected(retaddr, (void *)0xB0F, v47, v48);
  v49 = WaitForSingleObjectEx(*((HANDLE *)this + 29), 0x9C40u, 0);
  if ( v49 != 258 && v49 )
    wil::details::in1diag3::FailFast_Unexpected(retaddr, (void *)0xB0F, v50, v51);
  if ( *((_QWORD *)this + 13) != *((_QWORD *)this + 14) )
  {
    v52 = (_DWORD *)*((_QWORD *)MidiKSAggregateTransportTelemetryProvider::Instance() + 1);
    if ( *v52 > 4u )
    {
      v63 = (__int64)(*((_QWORD *)this + 14) - *((_QWORD *)this + 13)) >> 4;
      v70 = L"Enumeration completed or timed out with endpoint definitions left pending.";
      v71 = this;
      *(_QWORD *)v58 = "CMidi2KSAggregateMidiEndpointManager2::Initialize";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
        (_DWORD)v52,
        (unsigned int)qword_18008ACC8,
        v53,
        v54,
        (__int64)v58,
        (__int64)&v71,
        (__int64)&v70,
        (__int64)&v63);
    }
  }
  std::jthread::~jthread((std::jthread *)&v68);
  if ( v65 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v65);
  if ( v66 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v66);
  if ( v67 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v67);
  if ( *(_QWORD *)v61 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v61);
  winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v62);
  if ( Frequency.QuadPart )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&Frequency);
  if ( v25 )
  {
    v55 = _InterlockedDecrement(v25 + 6);
    if ( v55 )
    {
      if ( v55 < 0 )
        abort();
    }
    else
    {
      ProcessHeap = WINRT_IMPL_GetProcessHeap();
      WINRT_IMPL_HeapFree(ProcessHeap, 0, (LPVOID)v25);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18003bf70  mov     [rsp-8+arg_18], rbx
0x18003bf75  push    rbp
0x18003bf76  push    rsi
0x18003bf77  push    rdi
0x18003bf78  push    r12
0x18003bf7a  push    r13
0x18003bf7c  push    r14
0x18003bf7e  push    r15
0x18003bf80  lea     rbp, [rsp-70h]
0x18003bf85  sub     rsp, 170h
0x18003bf8c  mov     rax, cs:__security_cookie
0x18003bf93  xor     rax, rsp
0x18003bf96  mov     [rbp+0A0h+var_40], rax
0x18003bf9a  mov     r14, r8
0x18003bf9d  mov     rsi, rdx
0x18003bfa0  mov     rdi, rcx
0x18003bfa3  call    ?Instance@MidiKSAggregateTransportTelemetryProvider@@KAPEAV1@XZ; MidiKSAggregateTransportTelemetryProvider::Instance(void)
0x18003bfa8  mov     rcx, [rax+8]
0x18003bfac  mov     eax, [rcx]
0x18003bfae  lea     r13, aCmidi2ksaggreg_9; "CMidi2KSAggregateMidiEndpointManager2::"...
0x18003bfb5  cmp     eax, 4
0x18003bfb8  jbe     short loc_18003BFFA
0x18003bfba  lea     rax, aEnter_0; "Enter"
0x18003bfc1  mov     [rsp+1A0h+var_130], rax
0x18003bfc6  mov     qword ptr [rsp+1A0h+Frequency], rdi
0x18003bfcb  mov     qword ptr [rsp+1A0h+var_138], r13
0x18003bfd0  lea     rax, [rsp+1A0h+var_130]
0x18003bfd5  mov     [rsp+1A0h+var_170], rax
0x18003bfda  lea     rax, [rsp+1A0h+Frequency]
0x18003bfdf  mov     [rsp+1A0h+var_178], rax
0x18003bfe4  lea     rax, [rsp+1A0h+var_138]
0x18003bfe9  mov     qword ptr [rsp+1A0h+var_180], rax; int
0x18003bfee  lea     rdx, word_18008AD62
0x18003bff5  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &)
0x18003bffa  xor     r12d, r12d
0x18003bffd  test    rsi, rsi
0x18003c000  jnz     short loc_18003C049
0x18003c002  lea     edx, [rsi+2Ah]; void *
0x18003c005  mov     ebx, 80070057h
0x18003c00a  lea     r8, aAvcoreMidi2Tra_4; "avcore\\midi2\\transport\\ksaggregatetr"...
0x18003c011  mov     r9d, ebx; char *
0x18003c014  mov     rcx, [rbp+0A8h]; this
0x18003c01b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003c020  mov     eax, ebx
0x18003c022  mov     rcx, [rbp+0A0h+var_40]
0x18003c026  xor     rcx, rsp; StackCookie
0x18003c029  call    __security_check_cookie
0x18003c02e  mov     rbx, [rsp+1A0h+arg_18]
0x18003c036  add     rsp, 170h
0x18003c03d  pop     r15
0x18003c03f  pop     r14
0x18003c041  pop     r13
0x18003c043  pop     r12
0x18003c045  pop     rdi
0x18003c046  pop     rsi
0x18003c047  pop     rbp
0x18003c048  retn
0x18003c049  test    r14, r14
0x18003c04c  jnz     short loc_18003C054
0x18003c04e  lea     edx, [r14+2Bh]
0x18003c052  jmp     short loc_18003C005
0x18003c054  mov     rax, [rsi]
0x18003c057  mov     r15, [rax]
0x18003c05a  lea     rbx, [rdi+20h]
0x18003c05e  mov     rcx, [rbx]
0x18003c061  mov     [rbx], r12
0x18003c064  test    rcx, rcx
0x18003c067  jz      short loc_18003C076
0x18003c069  mov     rdx, [rcx]
0x18003c06c  mov     rax, [rdx+10h]
0x18003c070  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c075  nop
0x18003c076  mov     r8, rbx
0x18003c079  lea     rdx, _GUID_a04374d3_4514_44e1_a2f9_7d8b907aef1f
0x18003c080  mov     rcx, rsi
0x18003c083  mov     rax, r15
0x18003c086  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c08b  mov     ebx, eax
0x18003c08d  test    eax, eax
0x18003c08f  jns     short loc_18003C09B
0x18003c091  mov     edx, 2Dh ; '-'
0x18003c096  jmp     loc_18003C00A
0x18003c09b  mov     rax, [r14]
0x18003c09e  mov     rsi, [rax]
0x18003c0a1  lea     rbx, [rdi+28h]
0x18003c0a5  mov     rcx, [rbx]
0x18003c0a8  mov     [rbx], r12
0x18003c0ab  test    rcx, rcx
0x18003c0ae  jz      short loc_18003C0BD
0x18003c0b0  mov     rdx, [rcx]
0x18003c0b3  mov     rax, [rdx+10h]
0x18003c0b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c0bc  nop
0x18003c0bd  mov     r8, rbx
0x18003c0c0  lea     rdx, _GUID_7a3def20_fb76_49b6_a3a0_3dcbcda8f482
0x18003c0c7  mov     rcx, r14
0x18003c0ca  mov     rax, rsi
0x18003c0cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c0d2  mov     ebx, eax
0x18003c0d4  test    eax, eax
0x18003c0d6  jns     short loc_18003C0E2
0x18003c0d8  mov     edx, 2Eh ; '.'
0x18003c0dd  jmp     loc_18003C00A
0x18003c0e2  lea     rbx, [rdi+18h]
0x18003c0e6  mov     r9, rbx
0x18003c0e9  lea     r8, aKsainterfaceen; "KsaInterfaceEnumTimeoutMS"
0x18003c0f0  call    ??$get_value_dword_nothrow@K$0A@@reg@wil@@YAJPEAUHKEY__@@PEBG1PEAK@Z; wil::reg::get_value_dword_nothrow<ulong,0>(HKEY__ *,ushort const *,ushort const *,ulong *)
0x18003c0f5  test    eax, eax
0x18003c0f7  js      short loc_18003C10F
0x18003c0f9  mov     eax, 14h
0x18003c0fe  cmp     [rbx], eax
0x18003c100  jbe     short loc_18003C114
0x18003c102  mov     eax, 9C4h
0x18003c107  cmp     [rbx], eax
0x18003c109  jnb     short loc_18003C114
0x18003c10b  mov     eax, [rbx]
0x18003c10d  jmp     short loc_18003C114
0x18003c10f  mov     eax, 12Ch
0x18003c114  mov     [rbx], eax
0x18003c116  mov     qword ptr [rsp+1A0h+Frequency], r12
0x18003c11b  lea     rcx, [rsp+1A0h+Frequency]; lpFrequency
0x18003c120  call    cs:__imp_QueryPerformanceFrequency
0x18003c126  mov     rcx, qword ptr [rsp+1A0h+Frequency]
0x18003c12b  xorps   xmm1, xmm1
0x18003c12e  test    rcx, rcx
0x18003c131  js      short loc_18003C13A
0x18003c133  cvtsi2sd xmm1, rcx
0x18003c138  jmp     short loc_18003C14F
0x18003c13a  mov     rax, rcx
0x18003c13d  shr     rax, 1
0x18003c140  and     ecx, 1
0x18003c143  or      rax, rcx
0x18003c146  cvtsi2sd xmm1, rax
0x18003c14b  addsd   xmm1, xmm1
0x18003c14f  mov     eax, [rbx]
0x18003c151  xorps   xmm0, xmm0
0x18003c154  cvtsi2sd xmm0, rax
0x18003c159  mulsd   xmm1, xmm0
0x18003c15d  divsd   xmm1, cs:__real@408f400000000000
0x18003c165  xor     ecx, ecx
0x18003c167  movsd   xmm0, cs:__real@43e0000000000000
0x18003c16f  comisd  xmm1, xmm0
0x18003c173  jb      short loc_18003C18C
0x18003c175  subsd   xmm1, xmm0
0x18003c179  comisd  xmm1, xmm0
0x18003c17d  jnb     short loc_18003C18C
0x18003c17f  mov     rax, 8000000000000000h
0x18003c189  mov     rcx, rax
0x18003c18c  cvttsd2si rax, xmm1
0x18003c191  add     rax, rcx
0x18003c194  mov     [rdi+10h], rax
0x18003c198  call    ?Instance@MidiKSAggregateTransportTelemetryProvider@@KAPEAV1@XZ; MidiKSAggregateTransportTelemetryProvider::Instance(void)
0x18003c19d  mov     rcx, [rax+8]
0x18003c1a1  mov     eax, [rcx]
0x18003c1a3  cmp     eax, 4
0x18003c1a6  jbe     loc_18003C235
0x18003c1ac  mov     eax, [rbx]
0x18003c1ae  mov     [rsp+1A0h+var_128], eax
0x18003c1b2  mov     rax, [rdi+10h]
0x18003c1b6  mov     [rsp+1A0h+var_130], rax
0x18003c1bb  mov     qword ptr [rsp+1A0h+Frequency], rdi
0x18003c1c0  lea     rax, [rsp+1A0h+var_128]
0x18003c1c5  mov     [rbp+0A0h+var_50], rax
0x18003c1c9  mov     [rbp+0A0h+var_48], 4
0x18003c1d1  lea     rax, [rsp+1A0h+var_130]
0x18003c1d6  mov     [rbp+0A0h+var_60], rax
0x18003c1da  mov     [rbp+0A0h+var_58], 8
0x18003c1e2  lea     rax, aCalculatedMaxT; "Calculated max timeout for interfact ar"...
0x18003c1e9  mov     [rbp+0A0h+var_70], rax
0x18003c1ed  mov     [rbp+0A0h+var_68], 5Ah ; 'Z'
0x18003c1f5  lea     rax, [rsp+1A0h+Frequency]
0x18003c1fa  mov     [rbp+0A0h+var_80], rax
0x18003c1fe  mov     [rbp+0A0h+var_78], 8
0x18003c206  mov     [rbp+0A0h+var_90], r13
0x18003c20a  mov     [rbp+0A0h+var_88], 32h ; '2'
0x18003c212  lea     rax, [rbp+0A0h+var_B0]
0x18003c216  mov     [rsp+1A0h+var_178], rax
0x18003c21b  mov     [rsp+1A0h+var_180], 7
0x18003c223  xor     r9d, r9d
0x18003c226  xor     r8d, r8d
0x18003c229  lea     rdx, byte_18008AD15
0x18003c230  call    _tlgWriteTransfer_EventWriteTransfer
0x18003c235  mov     ecx, 9Ah; this
0x18003c23a  call    ?precreate_hstring_on_heap@impl@winrt@@YAPEAUshared_hstring_header@12@I@Z; winrt::impl::precreate_hstring_on_heap(uint)
0x18003c23f  mov     r14, rax
0x18003c242  lea     rcx, [rax+1Ch]
0x18003c246  test    rcx, rcx
0x18003c249  jz      short loc_18003C2C3
0x18003c24b  lea     rax, aSystemDevicesI; "System.Devices.InterfaceClassGuid:=\"{6"...
0x18003c252  mov     edx, 2
0x18003c257  lea     r8d, [rdx+7Eh]
0x18003c25b  movups  xmm0, xmmword ptr [rax]
0x18003c25e  movups  xmmword ptr [rcx], xmm0
0x18003c261  movups  xmm1, xmmword ptr [rax+10h]
0x18003c265  movups  xmmword ptr [rcx+10h], xmm1
0x18003c269  movups  xmm0, xmmword ptr [rax+20h]
0x18003c26d  movups  xmmword ptr [rcx+20h], xmm0
0x18003c271  movups  xmm1, xmmword ptr [rax+30h]
0x18003c275  movups  xmmword ptr [rcx+30h], xmm1
0x18003c279  movups  xmm0, xmmword ptr [rax+40h]
0x18003c27d  movups  xmmword ptr [rcx+40h], xmm0
0x18003c281  movups  xmm1, xmmword ptr [rax+50h]
0x18003c285  movups  xmmword ptr [rcx+50h], xmm1
0x18003c289  movups  xmm0, xmmword ptr [rax+60h]
0x18003c28d  movups  xmmword ptr [rcx+60h], xmm0
0x18003c291  movups  xmm1, xmmword ptr [rax+70h]
0x18003c295  movups  xmmword ptr [rcx+70h], xmm1
0x18003c299  add     rcx, r8
0x18003c29c  add     rax, r8
0x18003c29f  sub     rdx, 1
0x18003c2a3  jnz     short loc_18003C25B
0x18003c2a5  movups  xmm0, xmmword ptr [rax]
0x18003c2a8  movups  xmmword ptr [rcx], xmm0
0x18003c2ab  movups  xmm1, xmmword ptr [rax+10h]
0x18003c2af  movups  xmmword ptr [rcx+10h], xmm1
0x18003c2b3  movups  xmm0, xmmword ptr [rax+20h]
0x18003c2b7  movups  xmmword ptr [rcx+20h], xmm0
0x18003c2bb  mov     eax, [rax+30h]
0x18003c2be  mov     [rcx+30h], eax
0x18003c2c1  jmp     short loc_18003C2D4
0x18003c2c3  call    cs:__imp__o__errno
0x18003c2c9  mov     dword ptr [rax], 16h
0x18003c2cf  call    _invalid_parameter_noinfo
0x18003c2d4  xorps   xmm0, xmm0
0x18003c2d7  movdqu  [rsp+1A0h+var_160], xmm0
0x18003c2dd  mov     [rsp+1A0h+var_150], r12
0x18003c2e2  lea     rdx, [rsp+1A0h+var_160]
0x18003c2e7  lea     rcx, [rsp+1A0h+Frequency]
0x18003c2ec  call    ??$single_threaded_vector@Uhstring@winrt@@V?$allocator@Uhstring@winrt@@@std@@@winrt@@YA?AU?$IVector@Uhstring@winrt@@@Collections@Foundation@Windows@0@$$QEAV?$vector@Uhstring@winrt@@V?$allocator@Uhstring@winrt@@@std@@@std@@@Z; winrt::single_threaded_vector<winrt::hstring,std::allocator<winrt::hstring>>(std::vector<winrt::hstring> &&)
0x18003c2f1  lea     rcx, [rsp+1A0h+var_160]
0x18003c2f6  call    ??1?$vector@Uhstring@winrt@@V?$allocator@Uhstring@winrt@@@std@@@std@@QEAA@XZ; std::vector<winrt::hstring>::~vector<winrt::hstring>(void)
0x18003c2fb  mov     dword ptr [rsp+1A0h+var_160+8], 1
0x18003c303  mov     dword ptr [rsp+1A0h+var_160+0Ch], 15h
0x18003c30b  lea     rax, aSystemDevicesP_0; "System.Devices.Parent"
0x18003c312  mov     [rsp+1A0h+var_148], rax
0x18003c317  lea     rax, [rsp+1A0h+var_160+8]
0x18003c31c  mov     qword ptr [rsp+1A0h+var_160], rax
0x18003c321  lea     rdx, [rsp+1A0h+var_160]
0x18003c326  lea     rcx, [rsp+1A0h+Frequency]
0x18003c32b  call    ?Append@?$consume_Windows_Foundation_Collections_IVector@U?$IVector@Uhstring@winrt@@@Collections@Foundation@Windows@winrt@@Uhstring@5@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Foundation::Collections::IVector<winrt::hstring>,winrt::hstring>::Append(winrt::param::hstring const &)
0x18003c330  mov     [rbp+0A0h+var_D8], r14
0x18003c334  lea     rax, [rbp+0A0h+var_D8]
0x18003c338  mov     [rsp+1A0h+var_130], rax
0x18003c33d  lock inc cs:qword_180096AE8
0x18003c345  mov     rcx, cs:??$factory_cache_entry_v@UDeviceInformation@Enumeration@Devices@Windows@winrt@@UIDeviceInformationStatics@2345@@impl@winrt@@3U?$factory_cache_entry@UDeviceInformation@Enumeration@Devices@Windows@winrt@@UIDeviceInformationStatics@2345@@12@A; factory_cache_entry<winrt::Windows::Devices::Enumeration::DeviceInformation,winrt::Windows::Devices::Enumeration::IDeviceInformationStatics>::winrt::factory_cache_entry<winrt::Windows::Devices::Enumeration::DeviceInformation,winrt::Windows::Devices::Enumeration::IDeviceInformationStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::Devices::Enumeration::DeviceInformation,winrt::Windows::Devices::Enumeration::IDeviceInformationStatics>
0x18003c34c  test    rcx, rcx
0x18003c34f  jz      short loc_18003C3A3
0x18003c351  mov     qword ptr [rsp+1A0h+var_138], r12
0x18003c356  mov     dword ptr [rsp+1A0h+var_160], 396h
0x18003c35e  lea     rax, aOnecoreuapInte_7; "onecoreuap\\Internal\\BuildMetadata\\in"...
0x18003c365  mov     qword ptr [rsp+1A0h+var_160+8], rax
0x18003c36a  mov     [rsp+1A0h+var_150], r12
0x18003c36f  mov     rax, [rcx]
0x18003c372  lea     r8, [rsp+1A0h+var_138]
0x18003c377  mov     rdx, [rbp+0A0h+var_D8]
0x18003c37b  mov     rax, [rax+70h]
0x18003c37f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c384  test    eax, eax
0x18003c386  js      loc_18003C804
0x18003c38c  mov     rbx, qword ptr [rsp+1A0h+var_138]
0x18003c391  mov     [rbp+0A0h+var_120], rbx
0x18003c395  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18003c399  lock add cs:qword_180096AE8, rsi
0x18003c3a1  jmp     short loc_18003C3C1
0x18003c3a3  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18003c3a7  lock add cs:qword_180096AE8, rsi
0x18003c3af  lea     r8, [rsp+1A0h+var_130]
0x18003c3b4  lea     rdx, [rbp+0A0h+var_120]
0x18003c3b8  call    ??$call@AEAV_lambda_1_@?1??CreateWatcher@DeviceInformation@Enumeration@Devices@Windows@winrt@@SA@AEBUhstring@param@7@@Z@@?$factory_cache_entry@UDeviceInformation@Enumeration@Devices@Windows@winrt@@UIDeviceInformationStatics@2345@@impl@winrt@@QEAA?A_PAEAV_lambda_1_@?1??CreateWatcher@DeviceInformation@Enumeration@Devices@Windows@2@SA@AEBUhstring@param@2@@Z@@Z
0x18003c3bd  mov     rbx, [rbp+0A0h+var_120]
0x18003c3c1  lea     r15, [rdi+110h]
0x18003c3c8  lea     rax, [rbp+0A0h+var_120]
0x18003c3cc  cmp     r15, rax
0x18003c3cf  jz      short loc_18003C3EB
0x18003c3d1  cmp     [r15], r12
0x18003c3d4  jz      short loc_18003C3DE
0x18003c3d6  mov     rcx, r15
0x18003c3d9  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18003c3de  mov     rax, rbx
0x18003c3e1  mov     rbx, r12
0x18003c3e4  mov     [rbp+0A0h+var_120], rbx
0x18003c3e8  mov     [r15], rax
0x18003c3eb  test    rbx, rbx
0x18003c3ee  jz      short loc_18003C3F9
0x18003c3f0  lea     rcx, [rbp+0A0h+var_120]
0x18003c3f4  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18003c3f9  lea     rax, ?OnFilterDeviceInterfaceAdded@CMidi2KSAggregateMidiEndpointManager2@@AEAAJUDeviceWatcher@Enumeration@Devices@Windows@winrt@@UDeviceInformation@3456@@Z; CMidi2KSAggregateMidiEndpointManager2::OnFilterDeviceInterfaceAdded(winrt::Windows::Devices::Enumeration::DeviceWatcher,winrt::Windows::Devices::Enumeration::DeviceInformation)
0x18003c400  mov     qword ptr [rsp+1A0h+var_160+8], rax
0x18003c405  mov     dword ptr [rsp+1A0h+var_150], r12d
0x18003c40a  mov     eax, dword ptr [rsp+1A0h+var_160+0Ch]
0x18003c40e  mov     dword ptr [rsp+1A0h+var_150+4], eax
0x18003c412  mov     ecx, 28h ; '('; Size
0x18003c417  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003c41c  mov     dword ptr [rax+8], 1
0x18003c423  mov     [rax+10h], rdi
0x18003c427  movups  xmm0, [rsp+1A0h+var_160+8]
0x18003c42c  movdqu  xmmword ptr [rax+18h], xmm0
0x18003c431  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x18003c438  lea     rcx, ??_7?$delegate@U?$TypedEventHandler@UDeviceWatcher@Enumeration@Devices@Windows@winrt@@UDeviceInformation@2345@@Foundation@Windows@winrt@@V_lambda_20__@?0???$?0VCMidi2KSAggregateMidiEndpointManager@@P80@EAAJUDeviceWatcher@Enumeration@Devices@Windows@winrt@@UDeviceInformation@2345@@Z@1234@QEAA@PEAVCMidi2KSAggregateMidiEndpointManager@@P86@EAAJUDeviceWatcher@Enumeration@Devices@34@UDeviceInformation@8934@@Z@Z@@impl@winrt@@6B@; const winrt::impl::delegate<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Devices::Enumeration::DeviceWatcher,winrt::Windows::Devices::Enumeration::DeviceInformation>,`winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Devices::Enumeration::DeviceWatcher,winrt::Windows::Devices::Enumeration::DeviceInformation>::DeviceWatcher(CMidi2KSAggregateMidiEndpointManager *,long (CMidi2KSAggregateMidiEndpointManager::*)(winrt::Windows::Devices::Enumeration::DeviceWatcher,winrt::Windows::Devices::Enumeration::DeviceInformation))'::`1'::_lambda_20__>::`vftable'
0x18003c43f  mov     [rax], rcx
  ... truncated ...
```
