# CMidi2KSAggregateMidiEndpointManager::Initialize(IMidiDeviceManager *,IMidiEndpointProtocolManager *)

- ea: `0x180025570`
- end: `0x180025b9c`
- name: `?Initialize@CMidi2KSAggregateMidiEndpointManager@@UEAAJPEAUIMidiDeviceManager@@PEAUIMidiEndpointProtocolManager@@@Z`
- size: `1580`
- prototype: `__int64 __fastcall(CMidi2KSAggregateMidiEndpointManager *__hidden this, struct IMidiDeviceManager *, struct IMidiEndpointProtocolManager *)`
- caller_count: `0`
- callee_count: `35`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x1800016dc`
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
- `0x180010b94`
- `0x1800117d8`
- `0x180013f60`
- `0x180014d2c`
- `0x1800154d4`
- `0x18001a124`
- `0x18001f960`
- `0x18001f9c8`
- `0x180021420`
- `0x180022a38`
- `0x180022ad0`
- `0x180022b68`
- `0x180022c00`
- `0x180022c98`
- `0x180023078`
- `0x18002328c`
- `0x180024bfc`
- `0x180025570`
- `0x180028d40`
- `0x180029110`
- `0x180029210`
- `0x1800293d8`
- `0x18005e010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180025721`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180025721`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180025b86`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180025b86`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180025ada`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180025ada`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CMidi2KSAggregateMidiEndpointManager::Initialize(
        HANDLE *this,
        __int64 (__fastcall ***a2)(struct IMidiDeviceManager *, GUID *, HANDLE *),
        __int64 (__fastcall ***a3)(struct IMidiEndpointProtocolManager *, GUID *, HANDLE *))
{
  _DWORD *v6; // rcx
  int v7; // r8d
  int v8; // r9d
  __int64 v9; // rdx
  int v10; // ebx
  __int64 (__fastcall *v12)(struct IMidiDeviceManager *, GUID *, HANDLE *); // r15
  HANDLE v13; // rcx
  __int64 (__fastcall *v14)(struct IMidiEndpointProtocolManager *, GUID *, HANDLE *); // rdi
  HANDLE v15; // rcx
  unsigned int v16; // edx
  __int64 v17; // rdx
  volatile signed __int32 *v18; // rdi
  __int64 v19; // r8
  __int64 v20; // r9
  _OWORD *v21; // rcx
  const wchar_t *v22; // rdx
  __int64 v23; // rax
  CMidi2KSAggregateMidiEndpointManager *v24; // r15
  __int64 v25; // rbx
  __int64 *v26; // rcx
  _QWORD *v27; // rsi
  __int64 v28; // rcx
  __int64 v29; // rax
  __int64 v30; // rax
  char *v31; // rax
  __int64 v32; // r8
  __int64 v33; // rax
  __int64 v34; // r8
  __int64 v35; // rax
  __int64 v36; // r8
  __int64 v37; // rax
  __int64 v38; // r8
  __int64 v39; // rax
  __int64 v40; // r8
  __int64 v41; // rax
  DWORD v42; // eax
  unsigned int v43; // r8d
  const char *v44; // r9
  int v45; // ebx
  HANDLE ProcessHeap; // rax
  int v47; // [rsp+20h] [rbp-79h]
  _BYTE v48[24]; // [rsp+40h] [rbp-59h] BYREF
  const wchar_t *v49; // [rsp+58h] [rbp-41h]
  __int64 v50; // [rsp+60h] [rbp-39h] BYREF
  __int64 v51; // [rsp+68h] [rbp-31h] BYREF
  int v52[2]; // [rsp+70h] [rbp-29h] BYREF
  __int64 v53; // [rsp+78h] [rbp-21h] BYREF
  __int64 (__fastcall *v54)(__int64, _QWORD *, _QWORD *); // [rsp+80h] [rbp-19h] BYREF
  int v55; // [rsp+88h] [rbp-11h]
  int v56; // [rsp+8Ch] [rbp-Dh]
  __int128 v57; // [rsp+90h] [rbp-9h] BYREF
  char v58; // [rsp+A0h] [rbp+7h]
  volatile signed __int32 *v59; // [rsp+B0h] [rbp+17h] BYREF
  int v60; // [rsp+B8h] [rbp+1Fh]
  int v61; // [rsp+BCh] [rbp+23h]
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+5Fh]
  const wchar_t *v63; // [rsp+108h] [rbp+6Fh] BYREF
  CMidi2KSAggregateMidiEndpointManager *v64; // [rsp+118h] [rbp+7Fh] BYREF

  v6 = (_DWORD *)*((_QWORD *)MidiKSAggregateTransportTelemetryProvider::Instance() + 1);
  if ( *v6 > 4u )
  {
    v63 = L"Enter";
    v64 = (CMidi2KSAggregateMidiEndpointManager *)this;
    *(_QWORD *)v52 = "CMidi2KSAggregateMidiEndpointManager::Initialize";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>>(
      (_DWORD)v6,
      (unsigned int)byte_18008970B,
      v7,
      v8,
      (__int64)v52,
      (__int64)&v64,
      (__int64)&v63);
  }
  if ( !a2 )
  {
    v9 = 43;
LABEL_5:
    v10 = -2147024809;
LABEL_6:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"avcore\\midi2\\transport\\ksaggregatetransport\\midi2.ksaggregatemidiendpointmanager.cpp",
      (const char *)(unsigned int)v10,
      v47);
    return (unsigned int)v10;
  }
  if ( !a3 )
  {
    v9 = 44;
    goto LABEL_5;
  }
  v12 = **a2;
  v13 = this[2];
  this[2] = 0;
  if ( v13 )
    (*(void (__fastcall **)(HANDLE))(*(_QWORD *)v13 + 16LL))(v13);
  v10 = v12((struct IMidiDeviceManager *)a2, &GUID_a04374d3_4514_44e1_a2f9_7d8b907aef1f, this + 2);
  if ( v10 < 0 )
  {
    v9 = 46;
    goto LABEL_6;
  }
  v14 = **a3;
  v15 = this[3];
  this[3] = 0;
  if ( v15 )
    (*(void (__fastcall **)(HANDLE))(*(_QWORD *)v15 + 16LL))(v15);
  v10 = v14((struct IMidiEndpointProtocolManager *)a3, &GUID_7a3def20_fb76_49b6_a3a0_3dcbcda8f482, this + 3);
  if ( v10 < 0 )
  {
    v9 = 47;
    goto LABEL_6;
  }
  v18 = (volatile signed __int32 *)winrt::impl::precreate_hstring_on_heap((winrt::impl *)0x86, v16);
  v21 = v18 + 7;
  if ( v18 == (volatile signed __int32 *)-28LL )
  {
    *(_DWORD *)_o__errno(v21, v17, v19, v20) = 22;
    invalid_parameter_noinfo();
  }
  else
  {
    v22 = L"System.Devices.ClassGuid:=\"{4d36e96c-e325-11ce-bfc1-08002be10318}\" AND System.Devices.Present:=System.Struct"
           "uredQueryType.Boolean#True";
    v23 = 2;
    do
    {
      *v21 = *(_OWORD *)v22;
      v21[1] = *((_OWORD *)v22 + 1);
      v21[2] = *((_OWORD *)v22 + 2);
      v21[3] = *((_OWORD *)v22 + 3);
      v21[4] = *((_OWORD *)v22 + 4);
      v21[5] = *((_OWORD *)v22 + 5);
      v21[6] = *((_OWORD *)v22 + 6);
      v21[7] = *((_OWORD *)v22 + 7);
      v21 += 8;
      v22 += 64;
      --v23;
    }
    while ( v23 );
    *(_OWORD *)((char *)v21 - 4) = *(_OWORD *)(v22 - 2);
  }
  memset(v48, 0, sizeof(v48));
  winrt::single_threaded_vector<winrt::hstring,std::allocator<winrt::hstring>>(&v64, v48);
  std::vector<winrt::hstring>::~vector<winrt::hstring>(v48);
  *(_QWORD *)&v48[8] = 0x2100000001LL;
  v49 = L"System.Devices.DeviceManufacturer";
  *(_QWORD *)v48 = &v48[8];
  winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Foundation::Collections::IVector<winrt::hstring>,winrt::hstring>::Append(
    &v64,
    v48);
  *(_QWORD *)&v48[8] = 0x1B00000001LL;
  v49 = L"System.Devices.Manufacturer";
  *(_QWORD *)v48 = &v48[8];
  winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Foundation::Collections::IVector<winrt::hstring>,winrt::hstring>::Append(
    &v64,
    v48);
  *(_QWORD *)&v48[8] = 0x1500000001LL;
  v49 = L"System.Devices.Parent";
  *(_QWORD *)v48 = &v48[8];
  winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Foundation::Collections::IVector<winrt::hstring>,winrt::hstring>::Append(
    &v64,
    v48);
  LODWORD(v63) = 3;
  v57 = 0;
  v58 = 1;
  v24 = v64;
  if ( v64 )
  {
    v51 = 0;
    (**(void (__fastcall ***)(CMidi2KSAggregateMidiEndpointManager *, __int64 *, __int64 *))v64)(
      v64,
      &winrt::impl::guid_v<winrt::Windows::Foundation::Collections::IIterable<winrt::hstring>>,
      &v51);
    v25 = v51;
    v53 = v51;
  }
  else
  {
    v53 = 0;
    v25 = 0;
  }
  v26 = &v53;
  if ( &v57 == (__int128 *)&v53 )
  {
    if ( v25 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v53);
  }
  else
  {
    if ( (_QWORD)v57 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v57);
    *(_QWORD *)&v57 = v25;
  }
  v59 = v18;
  *(_QWORD *)v48 = &v59;
  *(_QWORD *)&v48[8] = &v57;
  *(_QWORD *)&v48[16] = &v63;
  _InterlockedIncrement64(&qword_180096B08);
  if ( winrt::impl::factory_cache_entry_v<winrt::Windows::Devices::Enumeration::DeviceInformation,winrt::Windows::Devices::Enumeration::IDeviceInformationStatics2> )
  {
    `winrt::Windows::Devices::Enumeration::DeviceInformation::CreateWatcher'::`2'::_lambda_1_::operator()(
      v48,
      &v50,
      &winrt::impl::factory_cache_entry_v<winrt::Windows::Devices::Enumeration::DeviceInformation,winrt::Windows::Devices::Enumeration::IDeviceInformationStatics2>);
    _InterlockedAdd64(&qword_180096B08, 0xFFFFFFFFFFFFFFFFuLL);
  }
  else
  {
    _InterlockedAdd64(&qword_180096B08, 0xFFFFFFFFFFFFFFFFuLL);
    ___call_AEAV_lambda_1___1__CreateWatcher_DeviceInformation_Enumeration_Devices_Windows_winrt__SA_AEBUhstring_param_7_AEBU__iterable_Uhstring_winrt___97_AEBW4DeviceInformationKind_4567__Z____factory_cache_entry_UDeviceInformation_Enumeration_Devices_Windows_winrt__UIDeviceInformationStatics2_2345__impl_winrt__QEAA_A_PAEAV_lambda_1___1__CreateWatcher_DeviceInformation_Enumeration_Devices_Windows_2_SA_AEBUhstring_param_2_AEBU__iterable_Uhstring_winrt___param_2_AEBW4DeviceInformationKind_6782__Z__Z(
      v26,
      &v50,
      v48);
  }
  v27 = this + 11;
  if ( this + 11 == (HANDLE *)&v50 )
  {
    v29 = v50;
  }
  else
  {
    if ( *v27 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(this + 11);
    v28 = v50;
    v29 = 0;
    v50 = 0;
    *v27 = v28;
  }
  if ( v29 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v50);
  if ( *((_QWORD *)&v57 + 1) )
    **((_BYTE **)&v57 + 1) = 1;
  if ( v58 )
  {
    v30 = v57;
  }
  else
  {
    v30 = 0;
    *(_QWORD *)&v57 = 0;
  }
  if ( v30 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v57);
  *(_QWORD *)&v48[8] = CMidi2KSAggregateMidiEndpointManager::OnDeviceAdded;
  *(_DWORD *)&v48[16] = 0;
  *(_DWORD *)&v48[20] = (unsigned __int64)CMidi2KSAggregateMidiEndpointManager::OnDeviceAdded >> 32;
  v31 = (char *)operator new(0x28u);
  *((_DWORD *)v31 + 2) = 1;
  *((_QWORD *)v31 + 2) = this;
  *(_OWORD *)(v31 + 24) = *(_OWORD *)&v48[8];
  _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
  *(_QWORD *)v31 = ___7__delegate_U__TypedEventHandler_UDeviceWatcher_Enumeration_Devices_Windows_winrt__UDeviceInformation_2345__Foundation_Windows_winrt__V_lambda_20____0_____0VCMidi2KSAggregateMidiEndpointManager__P80_EAAJUDeviceWatcher_Enumeration_Devices_Windows_winrt__UDeviceInformation_2345__Z_1234_QEAA_PEAVCMidi2KSAggregateMidiEndpointManager__P86_EAAJUDeviceWatcher_Enumeration_Devices_34_UDeviceInformation_8934__Z_Z__impl_winrt__6B_;
  *(_QWORD *)v52 = v31;
  v59 = (volatile signed __int32 *)CMidi2KSAggregateMidiEndpointManager::OnDeviceRemoved;
  v60 = 0;
  v61 = *(_DWORD *)&v48[12];
  winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Devices::Enumeration::DeviceWatcher,winrt::Windows::Devices::Enumeration::DeviceInformationUpdate>::TypedEventHandler<winrt::Windows::Devices::Enumeration::DeviceWatcher,winrt::Windows::Devices::Enumeration::DeviceInformationUpdate>(
    &v51,
    this,
    &v59);
  v54 = CMidi2KSAggregateMidiEndpointManager::OnDeviceUpdated;
  v55 = 0;
  v56 = *(_DWORD *)&v48[12];
  winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Devices::Enumeration::DeviceWatcher,winrt::Windows::Devices::Enumeration::DeviceInformationUpdate>::TypedEventHandler<winrt::Windows::Devices::Enumeration::DeviceWatcher,winrt::Windows::Devices::Enumeration::DeviceInformationUpdate>(
    &v59,
    this,
    &v54);
  *(_QWORD *)v48 = &CMidi2KSAggregateMidiEndpointManager::OnDeviceStopped;
  *(_DWORD *)&v48[8] = 0;
  winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Devices::Enumeration::DeviceWatcher,winrt::Windows::Foundation::IInspectable>::TypedEventHandler<winrt::Windows::Devices::Enumeration::DeviceWatcher,winrt::Windows::Foundation::IInspectable>(
    &v54,
    this,
    v48);
  *(_QWORD *)v48 = &CMidi2KSAggregateMidiEndpointManager::OnDeviceStopped;
  *(_DWORD *)&v48[8] = 0;
  winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Devices::Enumeration::DeviceWatcher,winrt::Windows::Foundation::IInspectable>::TypedEventHandler<winrt::Windows::Devices::Enumeration::DeviceWatcher,winrt::Windows::Foundation::IInspectable>(
    &v63,
    this,
    v48);
  v33 = winrt::impl::consume_Windows_Devices_Enumeration_IDeviceWatcher<winrt::Windows::Devices::Enumeration::IDeviceWatcher>::Added(
          this + 11,
          v48,
          v32,
          v52);
  __4__event_revoker_UIDeviceWatcher_Enumeration_Devices_Windows_winrt___MP8type___abi_UIDeviceWatcher_Enumeration_Devices_Windows_winrt__X_impl_5_EAAHUevent_token_5___E1___96785__BDI_AA_impl_winrt__QEAAAEAU012___QEAU012__Z(
    this + 12,
    v33);
  __1__event_revoker_UIDeviceWatcher_Enumeration_Devices_Windows_winrt___MP8type___abi_UIDeviceWatcher_Enumeration_Devices_Windows_winrt__X_impl_5_EAAHUevent_token_5___E1___96785__BDI_AA_impl_winrt__QEAA_XZ(v48);
  v35 = winrt::impl::consume_Windows_Devices_Enumeration_IDeviceWatcher<winrt::Windows::Devices::Enumeration::IDeviceWatcher>::Removed(
          this + 11,
          v48,
          v34,
          &v51);
  __4__event_revoker_UIDeviceWatcher_Enumeration_Devices_Windows_winrt___MP8type___abi_UIDeviceWatcher_Enumeration_Devices_Windows_winrt__X_impl_5_EAAHUevent_token_5___E1___96785__BFI_AA_impl_winrt__QEAAAEAU012___QEAU012__Z(
    this + 14,
    v35);
  __1__event_revoker_UIDeviceWatcher_Enumeration_Devices_Windows_winrt___MP8type___abi_UIDeviceWatcher_Enumeration_Devices_Windows_winrt__X_impl_5_EAAHUevent_token_5___E1___96785__BFI_AA_impl_winrt__QEAA_XZ(v48);
  v37 = winrt::impl::consume_Windows_Devices_Enumeration_IDeviceWatcher<winrt::Windows::Devices::Enumeration::IDeviceWatcher>::Updated(
          this + 11,
          v48,
          v36,
          &v59);
  __4__event_revoker_UIDeviceWatcher_Enumeration_Devices_Windows_winrt___MP8type___abi_UIDeviceWatcher_Enumeration_Devices_Windows_winrt__X_impl_5_EAAHUevent_token_5___E1___96785__BEI_AA_impl_winrt__QEAAAEAU012___QEAU012__Z(
    this + 16,
    v37);
  __1__event_revoker_UIDeviceWatcher_Enumeration_Devices_Windows_winrt___MP8type___abi_UIDeviceWatcher_Enumeration_Devices_Windows_winrt__X_impl_5_EAAHUevent_token_5___E1___96785__BEI_AA_impl_winrt__QEAA_XZ(v48);
  v39 = winrt::impl::consume_Windows_Devices_Enumeration_IDeviceWatcher<winrt::Windows::Devices::Enumeration::IDeviceWatcher>::Stopped(
          this + 11,
          v48,
          v38,
          &v54);
  __4__event_revoker_UIDeviceWatcher_Enumeration_Devices_Windows_winrt___MP8type___abi_UIDeviceWatcher_Enumeration_Devices_Windows_winrt__X_impl_5_EAAHUevent_token_5___E1___96785__BHI_AA_impl_winrt__QEAAAEAU012___QEAU012__Z(
    this + 18,
    v39);
  __1__event_revoker_UIDeviceWatcher_Enumeration_Devices_Windows_winrt___MP8type___abi_UIDeviceWatcher_Enumeration_Devices_Windows_winrt__X_impl_5_EAAHUevent_token_5___E1___96785__BHI_AA_impl_winrt__QEAA_XZ(v48);
  v41 = winrt::impl::consume_Windows_Devices_Enumeration_IDeviceWatcher<winrt::Windows::Devices::Enumeration::IDeviceWatcher>::EnumerationCompleted(
          this + 11,
          v48,
          v40,
          &v63);
  __4__event_revoker_UIDeviceWatcher_Enumeration_Devices_Windows_winrt___MP8type___abi_UIDeviceWatcher_Enumeration_Devices_Windows_winrt__X_impl_5_EAAHUevent_token_5___E1___96785__BGI_AA_impl_winrt__QEAAAEAU012___QEAU012__Z(
    this + 20,
    v41);
  __1__event_revoker_UIDeviceWatcher_Enumeration_Devices_Windows_winrt___MP8type___abi_UIDeviceWatcher_Enumeration_Devices_Windows_winrt__X_impl_5_EAAHUevent_token_5___E1___96785__BGI_AA_impl_winrt__QEAA_XZ(v48);
  winrt::impl::consume_Windows_Devices_Enumeration_IDeviceWatcher<winrt::Windows::Devices::Enumeration::IDeviceWatcher>::Start(this + 11);
  v42 = WaitForSingleObjectEx(this[22], 0x2710u, 0);
  if ( v42 != 258 && v42 )
    wil::details::in1diag3::FailFast_Unexpected(retaddr, (void *)0xB0F, v43, v44);
  if ( v63 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v63);
  if ( v54 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v54);
  if ( v59 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v59);
  if ( v51 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v51);
  winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v52);
  if ( v24 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v64);
  if ( v18 )
  {
    v45 = _InterlockedDecrement(v18 + 6);
    if ( v45 )
    {
      if ( v45 < 0 )
        abort();
    }
    else
    {
      ProcessHeap = WINRT_IMPL_GetProcessHeap();
      WINRT_IMPL_HeapFree(ProcessHeap, 0, (LPVOID)v18);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180025570  mov     [rsp-8+arg_0], rbx
0x180025575  mov     [rsp-8+arg_10], rsi
0x18002557a  push    rbp
0x18002557b  push    rdi
0x18002557c  push    r12
0x18002557e  push    r14
0x180025580  push    r15
0x180025582  lea     rbp, [rsp-37h]
0x180025587  sub     rsp, 0D0h
0x18002558e  mov     rsi, r8
0x180025591  mov     rbx, rdx
0x180025594  mov     r14, rcx
0x180025597  call    ?Instance@MidiKSAggregateTransportTelemetryProvider@@KAPEAV1@XZ; MidiKSAggregateTransportTelemetryProvider::Instance(void)
0x18002559c  mov     rcx, [rax+8]
0x1800255a0  mov     eax, [rcx]
0x1800255a2  cmp     eax, 4
0x1800255a5  jbe     short loc_1800255E8
0x1800255a7  lea     rax, aEnter_0; "Enter"
0x1800255ae  mov     [rbp+57h+arg_8], rax
0x1800255b2  mov     [rbp+57h+arg_18], r14
0x1800255b6  lea     rax, aCmidi2ksaggreg_19; "CMidi2KSAggregateMidiEndpointManager::I"...
0x1800255bd  mov     qword ptr [rbp+57h+var_80], rax
0x1800255c1  lea     rax, [rbp+57h+arg_8]
0x1800255c5  mov     [rsp+0F0h+var_C0], rax
0x1800255ca  lea     rax, [rbp+57h+arg_18]
0x1800255ce  mov     [rsp+0F0h+var_C8], rax
0x1800255d3  lea     rax, [rbp+57h+var_80]
0x1800255d7  mov     qword ptr [rsp+0F0h+var_D0], rax; int
0x1800255dc  lea     rdx, byte_18008970B
0x1800255e3  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &)
0x1800255e8  xor     r12d, r12d
0x1800255eb  test    rbx, rbx
0x1800255ee  jnz     short loc_180025612
0x1800255f0  lea     edx, [rbx+2Bh]; void *
0x1800255f3  mov     ebx, 80070057h
0x1800255f8  lea     r8, aAvcoreMidi2Tra_0; "avcore\\midi2\\transport\\ksaggregatetr"...
0x1800255ff  mov     r9d, ebx; char *
0x180025602  mov     rcx, [rbp+5Fh]; this
0x180025606  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002560b  mov     eax, ebx
0x18002560d  jmp     loc_180025B66
0x180025612  test    rsi, rsi
0x180025615  jnz     short loc_18002561C
0x180025617  lea     edx, [rsi+2Ch]
0x18002561a  jmp     short loc_1800255F3
0x18002561c  mov     rax, [rbx]
0x18002561f  mov     r15, [rax]
0x180025622  lea     rdi, [r14+10h]
0x180025626  mov     rcx, [rdi]
0x180025629  mov     [rdi], r12
0x18002562c  test    rcx, rcx
0x18002562f  jz      short loc_18002563E
0x180025631  mov     rdx, [rcx]
0x180025634  mov     rax, [rdx+10h]
0x180025638  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002563d  nop
0x18002563e  mov     r8, rdi
0x180025641  lea     rdx, _GUID_a04374d3_4514_44e1_a2f9_7d8b907aef1f
0x180025648  mov     rcx, rbx
0x18002564b  mov     rax, r15
0x18002564e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025653  mov     ebx, eax
0x180025655  test    eax, eax
0x180025657  jns     short loc_180025660
0x180025659  mov     edx, 2Eh ; '.'
0x18002565e  jmp     short loc_1800255F8
0x180025660  mov     rax, [rsi]
0x180025663  mov     rdi, [rax]
0x180025666  lea     rbx, [r14+18h]
0x18002566a  mov     rcx, [rbx]
0x18002566d  mov     [rbx], r12
0x180025670  test    rcx, rcx
0x180025673  jz      short loc_180025682
0x180025675  mov     rdx, [rcx]
0x180025678  mov     rax, [rdx+10h]
0x18002567c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025681  nop
0x180025682  mov     r8, rbx
0x180025685  lea     rdx, _GUID_7a3def20_fb76_49b6_a3a0_3dcbcda8f482
0x18002568c  mov     rcx, rsi
0x18002568f  mov     rax, rdi
0x180025692  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025697  mov     ebx, eax
0x180025699  test    eax, eax
0x18002569b  jns     short loc_1800256A7
0x18002569d  mov     edx, 2Fh ; '/'
0x1800256a2  jmp     loc_1800255F8
0x1800256a7  mov     ecx, 86h; this
0x1800256ac  call    ?precreate_hstring_on_heap@impl@winrt@@YAPEAUshared_hstring_header@12@I@Z; winrt::impl::precreate_hstring_on_heap(uint)
0x1800256b1  mov     rdi, rax
0x1800256b4  lea     rcx, [rax+1Ch]
0x1800256b8  test    rcx, rcx
0x1800256bb  jz      short loc_180025721
0x1800256bd  lea     rdx, aSystemDevicesC; "System.Devices.ClassGuid:=\"{4d36e96c-e"...
0x1800256c4  mov     eax, 2
0x1800256c9  lea     r8d, [rax+7Eh]
0x1800256cd  movups  xmm0, xmmword ptr [rdx]
0x1800256d0  movups  xmmword ptr [rcx], xmm0
0x1800256d3  movups  xmm1, xmmword ptr [rdx+10h]
0x1800256d7  movups  xmmword ptr [rcx+10h], xmm1
0x1800256db  movups  xmm0, xmmword ptr [rdx+20h]
0x1800256df  movups  xmmword ptr [rcx+20h], xmm0
0x1800256e3  movups  xmm1, xmmword ptr [rdx+30h]
0x1800256e7  movups  xmmword ptr [rcx+30h], xmm1
0x1800256eb  movups  xmm0, xmmword ptr [rdx+40h]
0x1800256ef  movups  xmmword ptr [rcx+40h], xmm0
0x1800256f3  movups  xmm1, xmmword ptr [rdx+50h]
0x1800256f7  movups  xmmword ptr [rcx+50h], xmm1
0x1800256fb  movups  xmm0, xmmword ptr [rdx+60h]
0x1800256ff  movups  xmmword ptr [rcx+60h], xmm0
0x180025703  movups  xmm1, xmmword ptr [rdx+70h]
0x180025707  movups  xmmword ptr [rcx+70h], xmm1
0x18002570b  add     rcx, r8
0x18002570e  add     rdx, r8
0x180025711  sub     rax, 1
0x180025715  jnz     short loc_1800256CD
0x180025717  movups  xmm0, xmmword ptr [rdx-4]
0x18002571b  movups  xmmword ptr [rcx-4], xmm0
0x18002571f  jmp     short loc_180025732
0x180025721  call    cs:__imp__o__errno
0x180025727  mov     dword ptr [rax], 16h
0x18002572d  call    _invalid_parameter_noinfo
0x180025732  xorps   xmm0, xmm0
0x180025735  movdqu  [rbp+57h+var_B0], xmm0
0x18002573a  mov     [rbp+57h+var_A0], r12
0x18002573e  lea     rdx, [rbp+57h+var_B0]
0x180025742  lea     rcx, [rbp+57h+arg_18]
0x180025746  call    ??$single_threaded_vector@Uhstring@winrt@@V?$allocator@Uhstring@winrt@@@std@@@winrt@@YA?AU?$IVector@Uhstring@winrt@@@Collections@Foundation@Windows@0@$$QEAV?$vector@Uhstring@winrt@@V?$allocator@Uhstring@winrt@@@std@@@std@@@Z; winrt::single_threaded_vector<winrt::hstring,std::allocator<winrt::hstring>>(std::vector<winrt::hstring> &&)
0x18002574b  lea     rcx, [rbp+57h+var_B0]
0x18002574f  call    ??1?$vector@Uhstring@winrt@@V?$allocator@Uhstring@winrt@@@std@@@std@@QEAA@XZ; std::vector<winrt::hstring>::~vector<winrt::hstring>(void)
0x180025754  mov     dword ptr [rbp+57h+var_B0+8], 1
0x18002575b  mov     dword ptr [rbp+57h+var_B0+0Ch], 21h ; '!'
0x180025762  lea     rax, aSystemDevicesD_0; "System.Devices.DeviceManufacturer"
0x180025769  mov     [rbp+57h+var_98], rax
0x18002576d  lea     rax, [rbp+57h+var_B0+8]
0x180025771  mov     qword ptr [rbp+57h+var_B0], rax
0x180025775  lea     rdx, [rbp+57h+var_B0]
0x180025779  lea     rcx, [rbp+57h+arg_18]
0x18002577d  call    ?Append@?$consume_Windows_Foundation_Collections_IVector@U?$IVector@Uhstring@winrt@@@Collections@Foundation@Windows@winrt@@Uhstring@5@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Foundation::Collections::IVector<winrt::hstring>,winrt::hstring>::Append(winrt::param::hstring const &)
0x180025782  mov     dword ptr [rbp+57h+var_B0+8], 1
0x180025789  mov     dword ptr [rbp+57h+var_B0+0Ch], 1Bh
0x180025790  lea     rax, aSystemDevicesM; "System.Devices.Manufacturer"
0x180025797  mov     [rbp+57h+var_98], rax
0x18002579b  lea     rax, [rbp+57h+var_B0+8]
0x18002579f  mov     qword ptr [rbp+57h+var_B0], rax
0x1800257a3  lea     rdx, [rbp+57h+var_B0]
0x1800257a7  lea     rcx, [rbp+57h+arg_18]
0x1800257ab  call    ?Append@?$consume_Windows_Foundation_Collections_IVector@U?$IVector@Uhstring@winrt@@@Collections@Foundation@Windows@winrt@@Uhstring@5@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Foundation::Collections::IVector<winrt::hstring>,winrt::hstring>::Append(winrt::param::hstring const &)
0x1800257b0  mov     dword ptr [rbp+57h+var_B0+8], 1
0x1800257b7  mov     dword ptr [rbp+57h+var_B0+0Ch], 15h
0x1800257be  lea     rax, aSystemDevicesP_0; "System.Devices.Parent"
0x1800257c5  mov     [rbp+57h+var_98], rax
0x1800257c9  lea     rax, [rbp+57h+var_B0+8]
0x1800257cd  mov     qword ptr [rbp+57h+var_B0], rax
0x1800257d1  lea     rdx, [rbp+57h+var_B0]
0x1800257d5  lea     rcx, [rbp+57h+arg_18]
0x1800257d9  call    ?Append@?$consume_Windows_Foundation_Collections_IVector@U?$IVector@Uhstring@winrt@@@Collections@Foundation@Windows@winrt@@Uhstring@5@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Foundation::Collections::IVector<winrt::hstring>,winrt::hstring>::Append(winrt::param::hstring const &)
0x1800257de  mov     dword ptr [rbp+57h+arg_8], 3
0x1800257e5  xorps   xmm0, xmm0
0x1800257e8  movdqu  [rbp+57h+var_60], xmm0
0x1800257ed  mov     [rbp+57h+var_50], 1
0x1800257f1  mov     r15, [rbp+57h+arg_18]
0x1800257f5  test    r15, r15
0x1800257f8  jnz     short loc_180025803
0x1800257fa  mov     [rbp+57h+var_78], r12
0x1800257fe  mov     rbx, r12
0x180025801  jmp     short loc_180025828
0x180025803  mov     [rbp+57h+var_88], r12
0x180025807  mov     rax, [r15]
0x18002580a  lea     r8, [rbp+57h+var_88]
0x18002580e  lea     rdx, ??$guid_v@U?$IIterable@Uhstring@winrt@@@Collections@Foundation@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Foundation::Collections::IIterable<winrt::hstring>>
0x180025815  mov     rcx, r15
0x180025818  mov     rax, [rax]
0x18002581b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025820  mov     rbx, [rbp+57h+var_88]
0x180025824  mov     [rbp+57h+var_78], rbx
0x180025828  lea     rcx, [rbp+57h+var_78]
0x18002582c  lea     rax, [rbp+57h+var_60]
0x180025830  cmp     rax, rcx
0x180025833  jz      short loc_18002584A
0x180025835  cmp     qword ptr [rbp+57h+var_60], r12
0x180025839  jz      short loc_180025844
0x18002583b  lea     rcx, [rbp+57h+var_60]
0x18002583f  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180025844  mov     qword ptr [rbp+57h+var_60], rbx
0x180025848  jmp     short loc_180025858
0x18002584a  test    rbx, rbx
0x18002584d  jz      short loc_180025858
0x18002584f  lea     rcx, [rbp+57h+var_78]
0x180025853  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180025858  mov     [rbp+57h+var_40], rdi
0x18002585c  lea     rax, [rbp+57h+var_40]
0x180025860  mov     qword ptr [rbp+57h+var_B0], rax
0x180025864  lea     rax, [rbp+57h+var_60]
0x180025868  mov     qword ptr [rbp+57h+var_B0+8], rax
0x18002586c  lea     rax, [rbp+57h+arg_8]
0x180025870  mov     [rbp+57h+var_A0], rax
0x180025874  lock inc cs:qword_180096B08
0x18002587c  lea     rdx, [rbp+57h+var_90]
0x180025880  cmp     cs:??$factory_cache_entry_v@UDeviceInformation@Enumeration@Devices@Windows@winrt@@UIDeviceInformationStatics2@2345@@impl@winrt@@3U?$factory_cache_entry@UDeviceInformation@Enumeration@Devices@Windows@winrt@@UIDeviceInformationStatics2@2345@@12@A, r12; factory_cache_entry<winrt::Windows::Devices::Enumeration::DeviceInformation,winrt::Windows::Devices::Enumeration::IDeviceInformationStatics2>::winrt::factory_cache_entry<winrt::Windows::Devices::Enumeration::DeviceInformation,winrt::Windows::Devices::Enumeration::IDeviceInformationStatics2> winrt::impl::factory_cache_entry_v<winrt::Windows::Devices::Enumeration::DeviceInformation,winrt::Windows::Devices::Enumeration::IDeviceInformationStatics2>
0x180025887  jz      short loc_1800258A7
0x180025889  lea     r8, ??$factory_cache_entry_v@UDeviceInformation@Enumeration@Devices@Windows@winrt@@UIDeviceInformationStatics2@2345@@impl@winrt@@3U?$factory_cache_entry@UDeviceInformation@Enumeration@Devices@Windows@winrt@@UIDeviceInformationStatics2@2345@@12@A; factory_cache_entry<winrt::Windows::Devices::Enumeration::DeviceInformation,winrt::Windows::Devices::Enumeration::IDeviceInformationStatics2>::winrt::factory_cache_entry<winrt::Windows::Devices::Enumeration::DeviceInformation,winrt::Windows::Devices::Enumeration::IDeviceInformationStatics2> winrt::impl::factory_cache_entry_v<winrt::Windows::Devices::Enumeration::DeviceInformation,winrt::Windows::Devices::Enumeration::IDeviceInformationStatics2>
0x180025890  lea     rcx, [rbp+57h+var_B0]
0x180025894  call    ??R_lambda_1_@?1??CreateWatcher@DeviceInformation@Enumeration@Devices@Windows@winrt@@SA@AEBUhstring@param@6@AEBU?$iterable@Uhstring@winrt@@@86@AEBW4DeviceInformationKind@3456@@Z@QEBA@AEBUIDeviceInformationStatics2@3456@@Z; `winrt::Windows::Devices::Enumeration::DeviceInformation::CreateWatcher(winrt::param::hstring const &,winrt::param::iterable<winrt::hstring> const &,winrt::Windows::Devices::Enumeration::DeviceInformationKind const &)'::`2'::_lambda_1_::operator()(winrt::Windows::Devices::Enumeration::IDeviceInformationStatics2 const &)
0x180025899  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18002589d  lock add cs:qword_180096B08, rbx
0x1800258a5  jmp     short loc_1800258BC
0x1800258a7  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800258ab  lock add cs:qword_180096B08, rbx
0x1800258b3  lea     r8, [rbp+57h+var_B0]
0x1800258b7  call    ??$call@AEAV_lambda_1_@?1??CreateWatcher@DeviceInformation@Enumeration@Devices@Windows@winrt@@SA@AEBUhstring@param@7@AEBU?$iterable@Uhstring@winrt@@@97@AEBW4DeviceInformationKind@4567@@Z@@?$factory_cache_entry@UDeviceInformation@Enumeration@Devices@Windows@winrt@@UIDeviceInformationStatics2@2345@@impl@winrt@@QEAA?A_PAEAV_lambda_1_@?1??CreateWatcher@DeviceInformation@Enumeration@Devices@Windows@2@SA@AEBUhstring@param@2@AEBU?$iterable@Uhstring@winrt@@@param@2@AEBW4DeviceInformationKind@6782@@Z@@Z
0x1800258bc  lea     rsi, [r14+58h]
0x1800258c0  lea     rax, [rbp+57h+var_90]
0x1800258c4  cmp     rsi, rax
0x1800258c7  jz      short loc_1800258E6
0x1800258c9  cmp     [rsi], r12
0x1800258cc  jz      short loc_1800258D6
0x1800258ce  mov     rcx, rsi
0x1800258d1  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x1800258d6  mov     rcx, [rbp+57h+var_90]
0x1800258da  mov     rax, r12
0x1800258dd  mov     [rbp+57h+var_90], rax
0x1800258e1  mov     [rsi], rcx
0x1800258e4  jmp     short loc_1800258EA
0x1800258e6  mov     rax, [rbp+57h+var_90]
0x1800258ea  test    rax, rax
0x1800258ed  jz      short loc_1800258F8
0x1800258ef  lea     rcx, [rbp+57h+var_90]
0x1800258f3  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x1800258f8  mov     rax, qword ptr [rbp+57h+var_60+8]
0x1800258fc  test    rax, rax
0x1800258ff  jz      short loc_180025904
0x180025901  mov     byte ptr [rax], 1
0x180025904  cmp     [rbp+57h+var_50], r12b
0x180025908  jnz     short loc_180025913
0x18002590a  mov     rax, r12
0x18002590d  mov     qword ptr [rbp+57h+var_60], rax
0x180025911  jmp     short loc_180025917
0x180025913  mov     rax, qword ptr [rbp+57h+var_60]
0x180025917  test    rax, rax
0x18002591a  jz      short loc_180025925
0x18002591c  lea     rcx, [rbp+57h+var_60]
0x180025920  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180025925  lea     rax, ?OnDeviceAdded@CMidi2KSAggregateMidiEndpointManager@@AEAAJUDeviceWatcher@Enumeration@Devices@Windows@winrt@@UDeviceInformation@3456@@Z; CMidi2KSAggregateMidiEndpointManager::OnDeviceAdded(winrt::Windows::Devices::Enumeration::DeviceWatcher,winrt::Windows::Devices::Enumeration::DeviceInformation)
0x18002592c  mov     qword ptr [rbp+57h+var_B0+8], rax
0x180025930  mov     dword ptr [rbp+57h+var_A0], r12d
0x180025934  mov     eax, dword ptr [rbp+57h+var_B0+0Ch]
0x180025937  mov     dword ptr [rbp+57h+var_A0+4], eax
0x18002593a  mov     ecx, 28h ; '('; Size
0x18002593f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180025944  mov     dword ptr [rax+8], 1
0x18002594b  mov     [rax+10h], r14
0x18002594f  movups  xmm0, [rbp+57h+var_B0+8]
0x180025953  movdqu  xmmword ptr [rax+18h], xmm0
0x180025958  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x18002595f  lea     rcx, ??_7?$delegate@U?$TypedEventHandler@UDeviceWatcher@Enumeration@Devices@Windows@winrt@@UDeviceInformation@2345@@Foundation@Windows@winrt@@V_lambda_20__@?0???$?0VCMidi2KSAggregateMidiEndpointManager@@P80@EAAJUDeviceWatcher@Enumeration@Devices@Windows@winrt@@UDeviceInformation@2345@@Z@1234@QEAA@PEAVCMidi2KSAggregateMidiEndpointManager@@P86@EAAJUDeviceWatcher@Enumeration@Devices@34@UDeviceInformation@8934@@Z@Z@@impl@winrt@@6B@; const winrt::impl::delegate<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Devices::Enumeration::DeviceWatcher,winrt::Windows::Devices::Enumeration::DeviceInformation>,`winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Devices::Enumeration::DeviceWatcher,winrt::Windows::Devices::Enumeration::DeviceInformation>::DeviceWatcher(CMidi2KSAggregateMidiEndpointManager *,long (CMidi2KSAggregateMidiEndpointManager::*)(winrt::Windows::Devices::Enumeration::DeviceWatcher,winrt::Windows::Devices::Enumeration::DeviceInformation))'::`1'::_lambda_20__>::`vftable'
0x180025966  mov     [rax], rcx
0x180025969  mov     qword ptr [rbp+57h+var_80], rax
0x18002596d  lea     rax, ?OnDeviceRemoved@CMidi2KSAggregateMidiEndpointManager@@AEAAJUDeviceWatcher@Enumeration@Devices@Windows@winrt@@UDeviceInformationUpdate@3456@@Z; CMidi2KSAggregateMidiEndpointManager::OnDeviceRemoved(winrt::Windows::Devices::Enumeration::DeviceWatcher,winrt::Windows::Devices::Enumeration::DeviceInformationUpdate)
0x180025974  mov     [rbp+57h+var_40], rax
0x180025978  mov     [rbp+57h+var_38], r12d
0x18002597c  mov     eax, dword ptr [rbp+57h+var_B0+0Ch]
0x18002597f  mov     [rbp+57h+var_34], eax
0x180025982  lea     r8, [rbp+57h+var_40]
0x180025986  mov     rdx, r14
0x180025989  lea     rcx, [rbp+57h+var_88]
0x18002598d  call    ??$?0VCMidi2KSAggregateMidiEndpointManager2@@P80@EAAJUDeviceWatcher@Enumeration@Devices@Windows@winrt@@UDeviceInformationUpdate@2345@@Z@?$TypedEventHandler@UDeviceWatcher@Enumeration@Devices@Windows@winrt@@UDeviceInformationUpdate@2345@@Foundation@Windows@winrt@@QEAA@PEAVCMidi2KSAggregateMidiEndpointManager2@@P84@EAAJUDeviceWatcher@Enumeration@Devices@23@UDeviceInformationUpdate@6723@@Z@Z; winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Devices::Enumeration::DeviceWatcher,winrt::Windows::Devices::Enumeration::DeviceInformationUpdate>::TypedEventHandler<winrt::Windows::Devices::Enumeration::DeviceWatcher,winrt::Windows::Devices::Enumeration::DeviceInformationUpdate>(CMidi2KSAggregateMidiEndpointManager2 *,long (CMidi2KSAggregateMidiEndpointManager2::*)(winrt::Windows::Devices::Enumeration::DeviceWatcher,winrt::Windows::Devices::Enumeration::DeviceInformationUpdate))
0x180025992  lea     rax, ?OnDeviceUpdated@CMidi2KSAggregateMidiEndpointManager@@AEAAJUDeviceWatcher@Enumeration@Devices@Windows@winrt@@UDeviceInformationUpdate@3456@@Z; CMidi2KSAggregateMidiEndpointManager::OnDeviceUpdated(winrt::Windows::Devices::Enumeration::DeviceWatcher,winrt::Windows::Devices::Enumeration::DeviceInformationUpdate)
0x180025999  mov     [rbp+57h+var_70], rax
0x18002599d  mov     [rbp+57h+var_68], r12d
0x1800259a1  mov     eax, dword ptr [rbp+57h+var_B0+0Ch]
0x1800259a4  mov     [rbp+57h+var_64], eax
0x1800259a7  lea     r8, [rbp+57h+var_70]
0x1800259ab  mov     rdx, r14
0x1800259ae  lea     rcx, [rbp+57h+var_40]
0x1800259b2  call    ??$?0VCMidi2KSAggregateMidiEndpointManager2@@P80@EAAJUDeviceWatcher@Enumeration@Devices@Windows@winrt@@UDeviceInformationUpdate@2345@@Z@?$TypedEventHandler@UDeviceWatcher@Enumeration@Devices@Windows@winrt@@UDeviceInformationUpdate@2345@@Foundation@Windows@winrt@@QEAA@PEAVCMidi2KSAggregateMidiEndpointManager2@@P84@EAAJUDeviceWatcher@Enumeration@Devices@23@UDeviceInformationUpdate@6723@@Z@Z; winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Devices::Enumeration::DeviceWatcher,winrt::Windows::Devices::Enumeration::DeviceInformationUpdate>::TypedEventHandler<winrt::Windows::Devices::Enumeration::DeviceWatcher,winrt::Windows::Devices::Enumeration::DeviceInformationUpdate>(CMidi2KSAggregateMidiEndpointManager2 *,long (CMidi2KSAggregateMidiEndpointManager2::*)(winrt::Windows::Devices::Enumeration::DeviceWatcher,winrt::Windows::Devices::Enumeration::DeviceInformationUpdate))
0x1800259b7  lea     rax, ?OnDeviceStopped@CMidi2KSAggregateMidiEndpointManager@@AEAAJUDeviceWatcher@Enumeration@Devices@Windows@winrt@@UIInspectable@Foundation@56@@Z; CMidi2KSAggregateMidiEndpointManager::OnDeviceStopped(winrt::Windows::Devices::Enumeration::DeviceWatcher,winrt::Windows::Foundation::IInspectable)
0x1800259be  mov     qword ptr [rbp+57h+var_B0], rax
0x1800259c2  mov     dword ptr [rbp+57h+var_B0+8], r12d
0x1800259c6  mov     eax, dword ptr [rbp+57h+var_B0+0Ch]
0x1800259c9  mov     dword ptr [rbp+57h+var_B0+0Ch], eax
0x1800259cc  lea     r8, [rbp+57h+var_B0]
0x1800259d0  mov     rdx, r14
0x1800259d3  lea     rcx, [rbp+57h+var_70]
0x1800259d7  call    ??$?0VCMidi2KSAggregateMidiEndpointManager2@@P80@EAAJUDeviceWatcher@Enumeration@Devices@Windows@winrt@@UIInspectable@Foundation@45@@Z@?$TypedEventHandler@UDeviceWatcher@Enumeration@Devices@Windows@winrt@@UIInspectable@Foundation@45@@Foundation@Windows@winrt@@QEAA@PEAVCMidi2KSAggregateMidiEndpointManager2@@P84@EAAJUDeviceWatcher@Enumeration@Devices@23@UIInspectable@123@@Z@Z; winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Devices::Enumeration::DeviceWatcher,winrt::Windows::Foundation::IInspectable>::TypedEventHandler<winrt::Windows::Devices::Enumeration::DeviceWatcher,winrt::Windows::Foundation::IInspectable>(CMidi2KSAggregateMidiEndpointManager2 *,long (CMidi2KSAggregateMidiEndpointManager2::*)(winrt::Windows::Devices::Enumeration::DeviceWatcher,winrt::Windows::Foundation::IInspectable))
0x1800259dc  lea     rax, ?OnDeviceStopped@CMidi2KSAggregateMidiEndpointManager@@AEAAJUDeviceWatcher@Enumeration@Devices@Windows@winrt@@UIInspectable@Foundation@56@@Z; CMidi2KSAggregateMidiEndpointManager::OnDeviceStopped(winrt::Windows::Devices::Enumeration::DeviceWatcher,winrt::Windows::Foundation::IInspectable)
0x1800259e3  mov     qword ptr [rbp+57h+var_B0], rax
0x1800259e7  mov     dword ptr [rbp+57h+var_B0+8], r12d
0x1800259eb  mov     eax, dword ptr [rbp+57h+var_B0+0Ch]
0x1800259ee  mov     dword ptr [rbp+57h+var_B0+0Ch], eax
0x1800259f1  lea     r8, [rbp+57h+var_B0]
0x1800259f5  mov     rdx, r14
0x1800259f8  lea     rcx, [rbp+57h+arg_8]
0x1800259fc  call    ??$?0VCMidi2KSAggregateMidiEndpointManager2@@P80@EAAJUDeviceWatcher@Enumeration@Devices@Windows@winrt@@UIInspectable@Foundation@45@@Z@?$TypedEventHandler@UDeviceWatcher@Enumeration@Devices@Windows@winrt@@UIInspectable@Foundation@45@@Foundation@Windows@winrt@@QEAA@PEAVCMidi2KSAggregateMidiEndpointManager2@@P84@EAAJUDeviceWatcher@Enumeration@Devices@23@UIInspectable@123@@Z@Z; winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Devices::Enumeration::DeviceWatcher,winrt::Windows::Foundation::IInspectable>::TypedEventHandler<winrt::Windows::Devices::Enumeration::DeviceWatcher,winrt::Windows::Foundation::IInspectable>(CMidi2KSAggregateMidiEndpointManager2 *,long (CMidi2KSAggregateMidiEndpointManager2::*)(winrt::Windows::Devices::Enumeration::DeviceWatcher,winrt::Windows::Foundation::IInspectable))
0x180025a01  lea     r9, [rbp+57h+var_80]
0x180025a05  lea     rdx, [rbp+57h+var_B0]
0x180025a09  mov     rcx, rsi
0x180025a0c  call    ?Added@?$consume_Windows_Devices_Enumeration_IDeviceWatcher@UIDeviceWatcher@Enumeration@Devices@Windows@winrt@@@impl@winrt@@QEBA@Uauto_revoke_t@3@AEBU?$TypedEventHandler@UDeviceWatcher@Enumeration@Devices@Windows@winrt@@UDeviceInformation@2345@@Foundation@Windows@3@@Z; winrt::impl::consume_Windows_Devices_Enumeration_IDeviceWatcher<winrt::Windows::Devices::Enumeration::IDeviceWatcher>::Added(winrt::auto_revoke_t,winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Devices::Enumeration::DeviceWatcher,winrt::Windows::Devices::Enumeration::DeviceInformation> const &)
0x180025a11  mov     rdx, rax
0x180025a14  lea     rcx, [r14+60h]
  ... truncated ...
```
