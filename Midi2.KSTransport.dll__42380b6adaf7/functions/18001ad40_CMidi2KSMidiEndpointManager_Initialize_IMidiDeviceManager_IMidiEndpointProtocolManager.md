# CMidi2KSMidiEndpointManager::Initialize(IMidiDeviceManager *,IMidiEndpointProtocolManager *)

- ea: `0x18001ad40`
- end: `0x18001b644`
- name: `?Initialize@CMidi2KSMidiEndpointManager@@UEAAJPEAUIMidiDeviceManager@@PEAUIMidiEndpointProtocolManager@@@Z`
- size: `2308`
- prototype: `__int64 __fastcall(CMidi2KSMidiEndpointManager *__hidden this, struct IMidiDeviceManager *, struct IMidiEndpointProtocolManager *)`
- caller_count: `0`
- callee_count: `22`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x1800016dc`
- `0x180004460`
- `0x1800051e6`
- `0x1800052fc`
- `0x180005374`
- `0x180007dd0`
- `0x18000a814`
- `0x18000c2fc`
- `0x18000c36c`
- `0x18000c3dc`
- `0x18000c44c`
- `0x18000c4bc`
- `0x18000d1c0`
- `0x18000db18`
- `0x180014fc4`
- `0x180015348`
- `0x1800161c0`
- `0x180016374`
- `0x1800163dc`
- `0x180017854`
- `0x18001ad40`
- `0x180041010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18001b5d3`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18001b5d3`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18001af10`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18001af10`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18001b52f`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18001b52f`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CMidi2KSMidiEndpointManager::Initialize(
        HANDLE *this,
        __int64 (__fastcall ***a2)(struct IMidiDeviceManager *, GUID *, HANDLE *),
        __int64 (__fastcall ***a3)(struct IMidiEndpointProtocolManager *, GUID *, HANDLE *))
{
  _DWORD *v6; // rcx
  int v7; // r8d
  int v8; // r9d
  __int64 v9; // rdx
  int v10; // ebx
  __int64 (__fastcall *v12)(struct IMidiDeviceManager *, GUID *, HANDLE *); // r14
  HANDLE v13; // rcx
  __int64 (__fastcall *v14)(struct IMidiEndpointProtocolManager *, GUID *, HANDLE *); // rdi
  HANDLE v15; // rcx
  unsigned int v16; // edx
  __int64 v17; // rdx
  struct winrt::impl::shared_hstring_header *v18; // rbx
  __int64 v19; // r8
  __int64 v20; // r9
  _OWORD *v21; // rcx
  const wchar_t *v22; // rax
  __int64 v23; // rdx
  int v24; // eax
  const wchar_t *v25; // rbx
  const wchar_t **v26; // r12
  const wchar_t *v27; // rax
  char *v28; // rbx
  const wchar_t *v29; // rcx
  int v30; // eax
  const wchar_t *v31; // rbx
  const wchar_t **v32; // rdi
  const wchar_t *v33; // rsi
  const wchar_t *v34; // rax
  const wchar_t *v35; // rcx
  __int64 v36; // r15
  int v37; // eax
  const wchar_t *v38; // rbx
  const wchar_t **v39; // rdi
  const wchar_t *v40; // rsi
  const wchar_t *v41; // rax
  const wchar_t *v42; // rcx
  __int64 v43; // r14
  int v44; // eax
  const wchar_t *v45; // rbx
  const wchar_t **v46; // rdi
  const wchar_t *v47; // rsi
  const wchar_t *v48; // rax
  const wchar_t *v49; // rcx
  __int64 v50; // rsi
  int v51; // eax
  const wchar_t *v52; // rbx
  const wchar_t **v53; // rdi
  const wchar_t *v54; // rax
  const wchar_t *v55; // rax
  const wchar_t *v56; // rcx
  CMidi2KSMidiEndpointManager *v57; // rdi
  int v58; // eax
  const wchar_t *v59; // rbx
  const wchar_t **v60; // r12
  const wchar_t *v61; // rax
  const wchar_t *v62; // rax
  HANDLE v63; // rcx
  int v64; // eax
  DWORD v65; // eax
  unsigned int v66; // r8d
  const char *v67; // r9
  void *v68; // rbx
  int v69; // eax
  HANDLE ProcessHeap; // rax
  int v71; // [rsp+20h] [rbp-E0h]
  const wchar_t *v72; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v73; // [rsp+48h] [rbp-B8h]
  struct winrt::impl::shared_hstring_header *v74; // [rsp+60h] [rbp-A0h] BYREF
  const char *v75; // [rsp+68h] [rbp-98h]
  __int64 v76; // [rsp+70h] [rbp-90h]
  const wchar_t *v77; // [rsp+80h] [rbp-80h] BYREF
  int v78[2]; // [rsp+88h] [rbp-78h] BYREF
  const wchar_t *v79; // [rsp+90h] [rbp-70h] BYREF
  const wchar_t *v80; // [rsp+98h] [rbp-68h] BYREF
  const wchar_t *v81; // [rsp+A0h] [rbp-60h] BYREF
  const wchar_t *v82; // [rsp+A8h] [rbp-58h] BYREF
  const wchar_t *v83; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v84; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v85; // [rsp+C0h] [rbp-40h] BYREF
  _QWORD v86[2]; // [rsp+C8h] [rbp-38h] BYREF
  _QWORD v87[2]; // [rsp+D8h] [rbp-28h] BYREF
  _QWORD v88[2]; // [rsp+E8h] [rbp-18h] BYREF
  _QWORD v89[2]; // [rsp+F8h] [rbp-8h] BYREF
  _QWORD v90[2]; // [rsp+108h] [rbp+8h] BYREF
  char *v91; // [rsp+118h] [rbp+18h] BYREF
  LPVOID lpMem; // [rsp+120h] [rbp+20h]
  wil::details::in1diag3 *retaddr; // [rsp+168h] [rbp+68h]
  const wchar_t *v94; // [rsp+178h] [rbp+78h] BYREF
  CMidi2KSMidiEndpointManager *v95; // [rsp+188h] [rbp+88h] BYREF

  v6 = (_DWORD *)*((_QWORD *)MidiKSTransportTelemetryProvider::Instance() + 1);
  if ( *v6 > 4u )
  {
    v94 = L"Enter";
    v95 = (CMidi2KSMidiEndpointManager *)this;
    *(_QWORD *)v78 = "CMidi2KSMidiEndpointManager::Initialize";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>>(
      (_DWORD)v6,
      (unsigned int)qword_180068C38,
      v7,
      v8,
      (__int64)v78,
      (__int64)&v95,
      (__int64)&v94);
  }
  if ( !a2 )
  {
    v9 = 41;
LABEL_5:
    v10 = -2147024809;
LABEL_6:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"avcore\\midi2\\transport\\kstransport\\midi2.ksmidiendpointmanager.cpp",
      (const char *)(unsigned int)v10,
      v71);
    return (unsigned int)v10;
  }
  if ( !a3 )
  {
    v9 = 42;
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
    v9 = 44;
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
    v9 = 45;
    goto LABEL_6;
  }
  v18 = winrt::impl::precreate_hstring_on_heap((winrt::impl *)0x9A, v16);
  lpMem = v18;
  v21 = (_OWORD *)((char *)v18 + 28);
  if ( v18 == (struct winrt::impl::shared_hstring_header *)-28LL )
  {
    *(_DWORD *)_o__errno(v21, v17, v19, v20) = 22;
    invalid_parameter_noinfo();
  }
  else
  {
    v22 = L"System.Devices.InterfaceClassGuid:=\"{6994AD04-93EF-11D0-A3CC-00A0C9223196}\" AND System.Devices.InterfaceEnab"
           "led: = System.StructuredQueryType.Boolean#True";
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
    *v21 = *(_OWORD *)v22;
    v21[1] = *((_OWORD *)v22 + 1);
    v21[2] = *((_OWORD *)v22 + 2);
    *((_DWORD *)v21 + 12) = *((_DWORD *)v22 + 12);
  }
  v74 = v18;
  v94 = (const wchar_t *)&v74;
  _InterlockedIncrement64(&qword_180071C68);
  if ( winrt::impl::factory_cache_entry_v<winrt::Windows::Devices::Enumeration::DeviceInformation,winrt::Windows::Devices::Enumeration::IDeviceInformationStatics> )
  {
    v94 = 0;
    LODWORD(v72) = 918;
    *(_QWORD *)&v73 = "onecoreuap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt/Windows.Devices.Enumeration.h";
    *((_QWORD *)&v73 + 1) = 0;
    v24 = (*(__int64 (__fastcall **)(__int64, struct winrt::impl::shared_hstring_header *, const wchar_t **))(*(_QWORD *)winrt::impl::factory_cache_entry_v<winrt::Windows::Devices::Enumeration::DeviceInformation,winrt::Windows::Devices::Enumeration::IDeviceInformationStatics> + 112LL))(
            winrt::impl::factory_cache_entry_v<winrt::Windows::Devices::Enumeration::DeviceInformation,winrt::Windows::Devices::Enumeration::IDeviceInformationStatics>,
            v74,
            &v94);
    if ( v24 < 0 )
      winrt::throw_hresult((unsigned int)v24, &v72);
    v25 = v94;
    v77 = v94;
    _InterlockedDecrement64(&qword_180071C68);
  }
  else
  {
    _InterlockedDecrement64(&qword_180071C68);
    ___call_AEAV_lambda_1___1__CreateWatcher_DeviceInformation_Enumeration_Devices_Windows_winrt__SA_AEBUhstring_param_7__Z____factory_cache_entry_UDeviceInformation_Enumeration_Devices_Windows_winrt__UIDeviceInformationStatics_2345__impl_winrt__QEAA_A_PAEAV_lambda_1___1__CreateWatcher_DeviceInformation_Enumeration_Devices_Windows_2_SA_AEBUhstring_param_2__Z__Z(
      0,
      &v77,
      &v94);
    v25 = v77;
  }
  v26 = (const wchar_t **)(this + 7);
  if ( this + 7 != (HANDLE *)&v77 )
  {
    if ( *v26 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(this + 7);
    v27 = v25;
    v25 = 0;
    v77 = 0;
    *v26 = v27;
  }
  if ( v25 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v77);
  *(_QWORD *)&v73 = CMidi2KSMidiEndpointManager::OnDeviceAdded;
  DWORD2(v73) = 0;
  HIDWORD(v73) = (unsigned __int64)CMidi2KSMidiEndpointManager::OnDeviceAdded >> 32;
  v28 = (char *)operator new(0x28u);
  *((_DWORD *)v28 + 2) = 1;
  *((_QWORD *)v28 + 2) = this;
  *(_OWORD *)(v28 + 24) = v73;
  _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
  *(_QWORD *)v28 = ___7__delegate_U__TypedEventHandler_UDeviceWatcher_Enumeration_Devices_Windows_winrt__UDeviceInformation_2345__Foundation_Windows_winrt__V_lambda_20____0_____0VCMidi2KSMidiEndpointManager__P80_EAAJUDeviceWatcher_Enumeration_Devices_Windows_winrt__UDeviceInformation_2345__Z_1234_QEAA_PEAVCMidi2KSMidiEndpointManager__P86_EAAJUDeviceWatcher_Enumeration_Devices_34_UDeviceInformation_8934__Z_Z__impl_winrt__6B_;
  v91 = v28;
  v72 = (const wchar_t *)CMidi2KSMidiEndpointManager::OnDeviceRemoved;
  LODWORD(v73) = 0;
  winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Devices::Enumeration::DeviceWatcher,winrt::Windows::Devices::Enumeration::DeviceInformationUpdate>::TypedEventHandler<winrt::Windows::Devices::Enumeration::DeviceWatcher,winrt::Windows::Devices::Enumeration::DeviceInformationUpdate>(
    v78,
    this,
    &v72);
  v72 = (const wchar_t *)&CMidi2KSMidiEndpointManager::OnDeviceUpdated;
  LODWORD(v73) = 0;
  winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Devices::Enumeration::DeviceWatcher,winrt::Windows::Devices::Enumeration::DeviceInformationUpdate>::TypedEventHandler<winrt::Windows::Devices::Enumeration::DeviceWatcher,winrt::Windows::Devices::Enumeration::DeviceInformationUpdate>(
    &v85,
    this,
    &v72);
  v72 = (const wchar_t *)&CMidi2KSMidiEndpointManager::OnEnumerationCompleted;
  LODWORD(v73) = 0;
  winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Devices::Enumeration::DeviceWatcher,winrt::Windows::Foundation::IInspectable>::TypedEventHandler<winrt::Windows::Devices::Enumeration::DeviceWatcher,winrt::Windows::Foundation::IInspectable>(
    &v84,
    this,
    &v72);
  v72 = (const wchar_t *)&CMidi2KSMidiEndpointManager::OnEnumerationCompleted;
  LODWORD(v73) = 0;
  winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Devices::Enumeration::DeviceWatcher,winrt::Windows::Foundation::IInspectable>::TypedEventHandler<winrt::Windows::Devices::Enumeration::DeviceWatcher,winrt::Windows::Foundation::IInspectable>(
    &v95,
    this,
    &v72);
  v94 = 0;
  v29 = *v26;
  LODWORD(v74) = 1938;
  v75 = "onecoreuap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt\\Windows.Devices.Enumeration.h";
  v76 = 0;
  v30 = (*(__int64 (__fastcall **)(const wchar_t *, char *, const wchar_t **))(*(_QWORD *)v29 + 48LL))(v29, v28, &v94);
  if ( v30 < 0 )
    winrt::throw_hresult((unsigned int)v30, &v74);
  v31 = v94;
  winrt::weak_ref<winrt::Windows::Devices::Enumeration::IDeviceWatcher>::weak_ref<winrt::Windows::Devices::Enumeration::IDeviceWatcher>(
    &v72,
    this + 7);
  *(_QWORD *)&v73 = v31;
  v32 = (const wchar_t **)(this + 8);
  v33 = v72;
  v72 = 0;
  v86[0] = 0;
  v79 = v33;
  if ( v86 != this + 8 )
  {
    v34 = *v32;
    *v32 = 0;
    v86[0] = v34;
  }
  if ( v32 == &v79 )
  {
    if ( v33 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v79);
  }
  else
  {
    if ( *v32 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v32);
    *v32 = v33;
  }
  v86[1] = this[9];
  this[9] = (HANDLE)v31;
  __1__event_revoker_UIDeviceWatcher_Enumeration_Devices_Windows_winrt___MP8type___abi_UIDeviceWatcher_Enumeration_Devices_Windows_winrt__X_impl_5_EAAHUevent_token_5___E1___96785__BDI_AA_impl_winrt__QEAA_XZ(v86);
  __1__event_revoker_UIDeviceWatcher_Enumeration_Devices_Windows_winrt___MP8type___abi_UIDeviceWatcher_Enumeration_Devices_Windows_winrt__X_impl_5_EAAHUevent_token_5___E1___96785__BDI_AA_impl_winrt__QEAA_XZ(&v72);
  v94 = 0;
  v35 = *v26;
  LODWORD(v74) = 2014;
  v75 = "onecoreuap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt\\Windows.Devices.Enumeration.h";
  v76 = 0;
  v36 = *(_QWORD *)v78;
  v37 = (*(__int64 (__fastcall **)(const wchar_t *, _QWORD, const wchar_t **))(*(_QWORD *)v35 + 80LL))(
          v35,
          *(_QWORD *)v78,
          &v94);
  if ( v37 < 0 )
    winrt::throw_hresult((unsigned int)v37, &v74);
  v38 = v94;
  winrt::weak_ref<winrt::Windows::Devices::Enumeration::IDeviceWatcher>::weak_ref<winrt::Windows::Devices::Enumeration::IDeviceWatcher>(
    &v72,
    this + 7);
  *(_QWORD *)&v73 = v38;
  v39 = (const wchar_t **)(this + 10);
  v40 = v72;
  v72 = 0;
  v87[0] = 0;
  v80 = v40;
  if ( v87 != this + 10 )
  {
    v41 = *v39;
    *v39 = 0;
    v87[0] = v41;
  }
  if ( v39 == &v80 )
  {
    if ( v40 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v80);
  }
  else
  {
    if ( *v39 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v39);
    *v39 = v40;
  }
  v87[1] = this[11];
  this[11] = (HANDLE)v38;
  __1__event_revoker_UIDeviceWatcher_Enumeration_Devices_Windows_winrt___MP8type___abi_UIDeviceWatcher_Enumeration_Devices_Windows_winrt__X_impl_5_EAAHUevent_token_5___E1___96785__BFI_AA_impl_winrt__QEAA_XZ(v87);
  __1__event_revoker_UIDeviceWatcher_Enumeration_Devices_Windows_winrt___MP8type___abi_UIDeviceWatcher_Enumeration_Devices_Windows_winrt__X_impl_5_EAAHUevent_token_5___E1___96785__BFI_AA_impl_winrt__QEAA_XZ(&v72);
  v94 = 0;
  v42 = *v26;
  LODWORD(v74) = 1976;
  v75 = "onecoreuap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt\\Windows.Devices.Enumeration.h";
  v76 = 0;
  v43 = v85;
  v44 = (*(__int64 (__fastcall **)(const wchar_t *, __int64, const wchar_t **))(*(_QWORD *)v42 + 64LL))(v42, v85, &v94);
  if ( v44 < 0 )
    winrt::throw_hresult((unsigned int)v44, &v74);
  v45 = v94;
  winrt::weak_ref<winrt::Windows::Devices::Enumeration::IDeviceWatcher>::weak_ref<winrt::Windows::Devices::Enumeration::IDeviceWatcher>(
    &v72,
    this + 7);
  *(_QWORD *)&v73 = v45;
  v46 = (const wchar_t **)(this + 12);
  v47 = v72;
  v72 = 0;
  v88[0] = 0;
  v81 = v47;
  if ( v88 != this + 12 )
  {
    v48 = *v46;
    *v46 = 0;
    v88[0] = v48;
  }
  if ( v46 == &v81 )
  {
    if ( v47 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v81);
  }
  else
  {
    if ( *v46 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v46);
    *v46 = v47;
  }
  v88[1] = this[13];
  this[13] = (HANDLE)v45;
  __1__event_revoker_UIDeviceWatcher_Enumeration_Devices_Windows_winrt___MP8type___abi_UIDeviceWatcher_Enumeration_Devices_Windows_winrt__X_impl_5_EAAHUevent_token_5___E1___96785__BEI_AA_impl_winrt__QEAA_XZ(v88);
  __1__event_revoker_UIDeviceWatcher_Enumeration_Devices_Windows_winrt___MP8type___abi_UIDeviceWatcher_Enumeration_Devices_Windows_winrt__X_impl_5_EAAHUevent_token_5___E1___96785__BEI_AA_impl_winrt__QEAA_XZ(&v72);
  v94 = 0;
  v49 = *v26;
  LODWORD(v74) = 2090;
  v75 = "onecoreuap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt\\Windows.Devices.Enumeration.h";
  v76 = 0;
  v50 = v84;
  v51 = (*(__int64 (__fastcall **)(const wchar_t *, __int64, const wchar_t **))(*(_QWORD *)v49 + 112LL))(v49, v84, &v94);
  if ( v51 < 0 )
    winrt::throw_hresult((unsigned int)v51, &v74);
  v52 = v94;
  winrt::weak_ref<winrt::Windows::Devices::Enumeration::IDeviceWatcher>::weak_ref<winrt::Windows::Devices::Enumeration::IDeviceWatcher>(
    &v72,
    this + 7);
  *(_QWORD *)&v73 = v52;
  v53 = (const wchar_t **)(this + 14);
  v54 = v72;
  v94 = v72;
  v72 = 0;
  v89[0] = 0;
  v82 = v94;
  if ( v89 != this + 14 )
  {
    v55 = *v53;
    *v53 = 0;
    v89[0] = v55;
    v54 = v94;
  }
  if ( v53 == &v82 )
  {
    if ( v54 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v82);
  }
  else
  {
    if ( *v53 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(this + 14);
    *v53 = v94;
  }
  v89[1] = this[15];
  this[15] = (HANDLE)v52;
  __1__event_revoker_UIDeviceWatcher_Enumeration_Devices_Windows_winrt___MP8type___abi_UIDeviceWatcher_Enumeration_Devices_Windows_winrt__X_impl_5_EAAHUevent_token_5___E1___96785__BHI_AA_impl_winrt__QEAA_XZ(v89);
  __1__event_revoker_UIDeviceWatcher_Enumeration_Devices_Windows_winrt___MP8type___abi_UIDeviceWatcher_Enumeration_Devices_Windows_winrt__X_impl_5_EAAHUevent_token_5___E1___96785__BHI_AA_impl_winrt__QEAA_XZ(&v72);
  v94 = 0;
  v56 = *v26;
  LODWORD(v74) = 2052;
  v75 = "onecoreuap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt\\Windows.Devices.Enumeration.h";
  v76 = 0;
  v57 = v95;
  v58 = (*(__int64 (__fastcall **)(const wchar_t *, CMidi2KSMidiEndpointManager *, const wchar_t **))(*(_QWORD *)v56 + 96LL))(
          v56,
          v95,
          &v94);
  if ( v58 < 0 )
    winrt::throw_hresult((unsigned int)v58, &v74);
  v59 = v94;
  winrt::weak_ref<winrt::Windows::Devices::Enumeration::IDeviceWatcher>::weak_ref<winrt::Windows::Devices::Enumeration::IDeviceWatcher>(
    &v72,
    this + 7);
  *(_QWORD *)&v73 = v59;
  v60 = (const wchar_t **)(this + 16);
  v61 = v72;
  v94 = v72;
  v72 = 0;
  v90[0] = 0;
  v83 = v94;
  if ( v90 != this + 16 )
  {
    v62 = *v60;
    *v60 = 0;
    v90[0] = v62;
    v61 = v94;
  }
  if ( v60 == &v83 )
  {
    if ( v61 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v83);
  }
  else
  {
    if ( *v60 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(this + 16);
    *v60 = v94;
  }
  v90[1] = this[17];
  this[17] = (HANDLE)v59;
  __1__event_revoker_UIDeviceWatcher_Enumeration_Devices_Windows_winrt___MP8type___abi_UIDeviceWatcher_Enumeration_Devices_Windows_winrt__X_impl_5_EAAHUevent_token_5___E1___96785__BGI_AA_impl_winrt__QEAA_XZ(v90);
  __1__event_revoker_UIDeviceWatcher_Enumeration_Devices_Windows_winrt___MP8type___abi_UIDeviceWatcher_Enumeration_Devices_Windows_winrt__X_impl_5_EAAHUevent_token_5___E1___96785__BGI_AA_impl_winrt__QEAA_XZ(&v72);
  v63 = this[7];
  LODWORD(v74) = 2145;
  v75 = "onecoreuap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt\\Windows.Devices.Enumeration.h";
  v76 = 0;
  v64 = (*(__int64 (__fastcall **)(HANDLE))(*(_QWORD *)v63 + 136LL))(v63);
  if ( v64 < 0 )
    winrt::throw_hresult((unsigned int)v64, &v74);
  v65 = WaitForSingleObjectEx(this[18], 0x2710u, 0);
  if ( v65 != 258 && v65 )
    wil::details::in1diag3::FailFast_Unexpected(retaddr, (void *)0xB0F, v66, v67);
  if ( v57 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v95);
  if ( v50 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v84);
  if ( v43 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v85);
  if ( v36 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v78);
  winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v91);
  v68 = lpMem;
  if ( lpMem )
  {
    v69 = _InterlockedDecrement((volatile signed __int32 *)lpMem + 6);
    if ( v69 )
    {
      if ( v69 < 0 )
        abort();
    }
    else
    {
      ProcessHeap = WINRT_IMPL_GetProcessHeap();
      WINRT_IMPL_HeapFree(ProcessHeap, 0, v68);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18001ad40  mov     [rsp-8+arg_0], rbx
0x18001ad45  push    rbp
0x18001ad46  push    rsi
0x18001ad47  push    rdi
0x18001ad48  push    r12
0x18001ad4a  push    r13
0x18001ad4c  push    r14
0x18001ad4e  push    r15
0x18001ad50  lea     rbp, [rsp-30h]
0x18001ad55  sub     rsp, 130h
0x18001ad5c  mov     rsi, r8
0x18001ad5f  mov     rbx, rdx
0x18001ad62  mov     r13, rcx
0x18001ad65  call    ?Instance@MidiKSTransportTelemetryProvider@@KAPEAV1@XZ; MidiKSTransportTelemetryProvider::Instance(void)
0x18001ad6a  mov     rcx, [rax+8]
0x18001ad6e  mov     eax, [rcx]
0x18001ad70  cmp     eax, 4
0x18001ad73  jbe     short loc_18001ADBC
0x18001ad75  lea     rax, aEnter; "Enter"
0x18001ad7c  mov     [rbp+60h+arg_8], rax
0x18001ad80  mov     [rbp+60h+arg_18], r13
0x18001ad87  lea     rax, aCmidi2ksmidien_1; "CMidi2KSMidiEndpointManager::Initialize"
0x18001ad8e  mov     qword ptr [rbp+60h+var_D8], rax
0x18001ad92  lea     rax, [rbp+60h+arg_8]
0x18001ad96  mov     [rsp+160h+var_130], rax
0x18001ad9b  lea     rax, [rbp+60h+arg_18]
0x18001ada2  mov     [rsp+160h+var_138], rax
0x18001ada7  lea     rax, [rbp+60h+var_D8]
0x18001adab  mov     qword ptr [rsp+160h+var_140], rax; int
0x18001adb0  lea     rdx, qword_180068C38
0x18001adb7  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &)
0x18001adbc  test    rbx, rbx
0x18001adbf  jnz     short loc_18001ADE3
0x18001adc1  lea     edx, [rbx+29h]; void *
0x18001adc4  mov     ebx, 80070057h
0x18001adc9  lea     r8, aAvcoreMidi2Tra_4; "avcore\\midi2\\transport\\kstransport\\"...
0x18001add0  mov     r9d, ebx; char *
0x18001add3  mov     rcx, [rbp+68h]; this
0x18001add7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001addc  mov     eax, ebx
0x18001adde  jmp     loc_18001B5B4
0x18001ade3  test    rsi, rsi
0x18001ade6  jnz     short loc_18001ADED
0x18001ade8  lea     edx, [rsi+2Ah]
0x18001adeb  jmp     short loc_18001ADC4
0x18001aded  mov     rax, [rbx]
0x18001adf0  mov     r14, [rax]
0x18001adf3  lea     rdi, [r13+10h]
0x18001adf7  mov     rcx, [rdi]
0x18001adfa  mov     qword ptr [rdi], 0
0x18001ae01  test    rcx, rcx
0x18001ae04  jz      short loc_18001AE13
0x18001ae06  mov     rdx, [rcx]
0x18001ae09  mov     rax, [rdx+10h]
0x18001ae0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ae12  nop
0x18001ae13  mov     r8, rdi
0x18001ae16  lea     rdx, _GUID_a04374d3_4514_44e1_a2f9_7d8b907aef1f
0x18001ae1d  mov     rcx, rbx
0x18001ae20  mov     rax, r14
0x18001ae23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ae28  mov     ebx, eax
0x18001ae2a  xor     r14d, r14d
0x18001ae2d  test    eax, eax
0x18001ae2f  jns     short loc_18001AE37
0x18001ae31  lea     edx, [r14+2Ch]
0x18001ae35  jmp     short loc_18001ADC9
0x18001ae37  mov     rax, [rsi]
0x18001ae3a  mov     rdi, [rax]
0x18001ae3d  lea     rbx, [r13+18h]
0x18001ae41  mov     rcx, [rbx]
0x18001ae44  mov     [rbx], r14
0x18001ae47  test    rcx, rcx
0x18001ae4a  jz      short loc_18001AE59
0x18001ae4c  mov     rdx, [rcx]
0x18001ae4f  mov     rax, [rdx+10h]
0x18001ae53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ae58  nop
0x18001ae59  mov     r8, rbx
0x18001ae5c  lea     rdx, _GUID_7a3def20_fb76_49b6_a3a0_3dcbcda8f482
0x18001ae63  mov     rcx, rsi
0x18001ae66  mov     rax, rdi
0x18001ae69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ae6e  mov     ebx, eax
0x18001ae70  test    eax, eax
0x18001ae72  jns     short loc_18001AE7E
0x18001ae74  mov     edx, 2Dh ; '-'
0x18001ae79  jmp     loc_18001ADC9
0x18001ae7e  mov     ecx, 9Ah; this
0x18001ae83  call    ?precreate_hstring_on_heap@impl@winrt@@YAPEAUshared_hstring_header@12@I@Z; winrt::impl::precreate_hstring_on_heap(uint)
0x18001ae88  mov     rbx, rax
0x18001ae8b  mov     [rbp+60h+lpMem], rax
0x18001ae8f  lea     rcx, [rax+1Ch]
0x18001ae93  test    rcx, rcx
0x18001ae96  jz      short loc_18001AF10
0x18001ae98  lea     rax, aSystemDevicesI; "System.Devices.InterfaceClassGuid:=\"{6"...
0x18001ae9f  mov     edx, 2
0x18001aea4  lea     r8d, [rdx+7Eh]
0x18001aea8  movups  xmm0, xmmword ptr [rax]
0x18001aeab  movups  xmmword ptr [rcx], xmm0
0x18001aeae  movups  xmm1, xmmword ptr [rax+10h]
0x18001aeb2  movups  xmmword ptr [rcx+10h], xmm1
0x18001aeb6  movups  xmm0, xmmword ptr [rax+20h]
0x18001aeba  movups  xmmword ptr [rcx+20h], xmm0
0x18001aebe  movups  xmm1, xmmword ptr [rax+30h]
0x18001aec2  movups  xmmword ptr [rcx+30h], xmm1
0x18001aec6  movups  xmm0, xmmword ptr [rax+40h]
0x18001aeca  movups  xmmword ptr [rcx+40h], xmm0
0x18001aece  movups  xmm1, xmmword ptr [rax+50h]
0x18001aed2  movups  xmmword ptr [rcx+50h], xmm1
0x18001aed6  movups  xmm0, xmmword ptr [rax+60h]
0x18001aeda  movups  xmmword ptr [rcx+60h], xmm0
0x18001aede  movups  xmm1, xmmword ptr [rax+70h]
0x18001aee2  movups  xmmword ptr [rcx+70h], xmm1
0x18001aee6  add     rcx, r8
0x18001aee9  add     rax, r8
0x18001aeec  sub     rdx, 1
0x18001aef0  jnz     short loc_18001AEA8
0x18001aef2  movups  xmm0, xmmword ptr [rax]
0x18001aef5  movups  xmmword ptr [rcx], xmm0
0x18001aef8  movups  xmm1, xmmword ptr [rax+10h]
0x18001aefc  movups  xmmword ptr [rcx+10h], xmm1
0x18001af00  movups  xmm0, xmmword ptr [rax+20h]
0x18001af04  movups  xmmword ptr [rcx+20h], xmm0
0x18001af08  mov     eax, [rax+30h]
0x18001af0b  mov     [rcx+30h], eax
0x18001af0e  jmp     short loc_18001AF21
0x18001af10  call    cs:__imp__o__errno
0x18001af16  mov     dword ptr [rax], 16h
0x18001af1c  call    _invalid_parameter_noinfo
0x18001af21  mov     [rsp+160h+var_100], rbx
0x18001af26  lea     rax, [rsp+160h+var_100]
0x18001af2b  mov     [rbp+60h+arg_8], rax
0x18001af2f  lock inc cs:qword_180071C68
0x18001af37  mov     rcx, cs:??$factory_cache_entry_v@UDeviceInformation@Enumeration@Devices@Windows@winrt@@UIDeviceInformationStatics@2345@@impl@winrt@@3U?$factory_cache_entry@UDeviceInformation@Enumeration@Devices@Windows@winrt@@UIDeviceInformationStatics@2345@@12@A; factory_cache_entry<winrt::Windows::Devices::Enumeration::DeviceInformation,winrt::Windows::Devices::Enumeration::IDeviceInformationStatics>::winrt::factory_cache_entry<winrt::Windows::Devices::Enumeration::DeviceInformation,winrt::Windows::Devices::Enumeration::IDeviceInformationStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::Devices::Enumeration::DeviceInformation,winrt::Windows::Devices::Enumeration::IDeviceInformationStatics>
0x18001af3e  lea     r8, [rbp+60h+arg_8]
0x18001af42  test    rcx, rcx
0x18001af45  jz      short loc_18001AF8F
0x18001af47  mov     [rbp+60h+arg_8], r14
0x18001af4b  mov     dword ptr [rsp+160h+var_120], 396h
0x18001af53  lea     rax, aOnecoreuapInte_9; "onecoreuap\\Internal\\BuildMetadata\\in"...
0x18001af5a  mov     qword ptr [rsp+160h+var_118], rax
0x18001af5f  mov     qword ptr [rsp+160h+var_118+8], r14
0x18001af64  mov     rax, [rcx]
0x18001af67  mov     rdx, [rsp+160h+var_100]
0x18001af6c  mov     rax, [rax+70h]
0x18001af70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001af75  test    eax, eax
0x18001af77  js      loc_18001B5E9
0x18001af7d  mov     rbx, [rbp+60h+arg_8]
0x18001af81  mov     [rbp+60h+var_E0], rbx
0x18001af85  lock dec cs:qword_180071C68
0x18001af8d  jmp     short loc_18001AFA4
0x18001af8f  lock dec cs:qword_180071C68
0x18001af97  lea     rdx, [rbp+60h+var_E0]
0x18001af9b  call    ??$call@AEAV_lambda_1_@?1??CreateWatcher@DeviceInformation@Enumeration@Devices@Windows@winrt@@SA@AEBUhstring@param@7@@Z@@?$factory_cache_entry@UDeviceInformation@Enumeration@Devices@Windows@winrt@@UIDeviceInformationStatics@2345@@impl@winrt@@QEAA?A_PAEAV_lambda_1_@?1??CreateWatcher@DeviceInformation@Enumeration@Devices@Windows@2@SA@AEBUhstring@param@2@@Z@@Z
0x18001afa0  mov     rbx, [rbp+60h+var_E0]
0x18001afa4  lea     r12, [r13+38h]
0x18001afa8  lea     rax, [rbp+60h+var_E0]
0x18001afac  cmp     r12, rax
0x18001afaf  jz      short loc_18001AFCD
0x18001afb1  cmp     [r12], r14
0x18001afb5  jz      short loc_18001AFBF
0x18001afb7  mov     rcx, r12
0x18001afba  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001afbf  mov     rax, rbx
0x18001afc2  mov     rbx, r14
0x18001afc5  mov     [rbp+60h+var_E0], rbx
0x18001afc9  mov     [r12], rax
0x18001afcd  test    rbx, rbx
0x18001afd0  jz      short loc_18001AFDB
0x18001afd2  lea     rcx, [rbp+60h+var_E0]
0x18001afd6  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001afdb  lea     rax, ?OnDeviceAdded@CMidi2KSMidiEndpointManager@@AEAAJUDeviceWatcher@Enumeration@Devices@Windows@winrt@@UDeviceInformation@3456@@Z; CMidi2KSMidiEndpointManager::OnDeviceAdded(winrt::Windows::Devices::Enumeration::DeviceWatcher,winrt::Windows::Devices::Enumeration::DeviceInformation)
0x18001afe2  mov     qword ptr [rsp+160h+var_118], rax
0x18001afe7  mov     dword ptr [rsp+160h+var_118+8], r14d
0x18001afec  mov     eax, dword ptr [rsp+160h+var_118+4]
0x18001aff0  mov     dword ptr [rsp+160h+var_118+0Ch], eax
0x18001aff4  mov     ecx, 28h ; '('; Size
0x18001aff9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001affe  mov     rbx, rax
0x18001b001  mov     dword ptr [rax+8], 1
0x18001b008  mov     [rax+10h], r13
0x18001b00c  movups  xmm0, [rsp+160h+var_118]
0x18001b011  movdqu  xmmword ptr [rax+18h], xmm0
0x18001b016  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x18001b01d  lea     rax, ??_7?$delegate@U?$TypedEventHandler@UDeviceWatcher@Enumeration@Devices@Windows@winrt@@UDeviceInformation@2345@@Foundation@Windows@winrt@@V_lambda_20__@?0???$?0VCMidi2KSMidiEndpointManager@@P80@EAAJUDeviceWatcher@Enumeration@Devices@Windows@winrt@@UDeviceInformation@2345@@Z@1234@QEAA@PEAVCMidi2KSMidiEndpointManager@@P86@EAAJUDeviceWatcher@Enumeration@Devices@34@UDeviceInformation@8934@@Z@Z@@impl@winrt@@6B@; const winrt::impl::delegate<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Devices::Enumeration::DeviceWatcher,winrt::Windows::Devices::Enumeration::DeviceInformation>,`winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Devices::Enumeration::DeviceWatcher,winrt::Windows::Devices::Enumeration::DeviceInformation>::DeviceWatcher(CMidi2KSMidiEndpointManager *,long (CMidi2KSMidiEndpointManager::*)(winrt::Windows::Devices::Enumeration::DeviceWatcher,winrt::Windows::Devices::Enumeration::DeviceInformation))'::`1'::_lambda_20__>::`vftable'
0x18001b024  mov     [rbx], rax
0x18001b027  mov     [rbp+60h+var_48], rbx
0x18001b02b  lea     rax, ?OnDeviceRemoved@CMidi2KSMidiEndpointManager@@AEAAJUDeviceWatcher@Enumeration@Devices@Windows@winrt@@UDeviceInformationUpdate@3456@@Z; CMidi2KSMidiEndpointManager::OnDeviceRemoved(winrt::Windows::Devices::Enumeration::DeviceWatcher,winrt::Windows::Devices::Enumeration::DeviceInformationUpdate)
0x18001b032  mov     [rsp+160h+var_120], rax
0x18001b037  mov     dword ptr [rsp+160h+var_118], r14d
0x18001b03c  mov     ecx, dword ptr [rsp+160h+var_118+4]
0x18001b040  mov     dword ptr [rsp+160h+var_118+4], ecx
0x18001b044  lea     r8, [rsp+160h+var_120]
0x18001b049  mov     rdx, r13
0x18001b04c  lea     rcx, [rbp+60h+var_D8]
0x18001b050  call    ??$?0VCMidi2KSMidiEndpointManager@@P80@EAAJUDeviceWatcher@Enumeration@Devices@Windows@winrt@@UDeviceInformationUpdate@2345@@Z@?$TypedEventHandler@UDeviceWatcher@Enumeration@Devices@Windows@winrt@@UDeviceInformationUpdate@2345@@Foundation@Windows@winrt@@QEAA@PEAVCMidi2KSMidiEndpointManager@@P84@EAAJUDeviceWatcher@Enumeration@Devices@23@UDeviceInformationUpdate@6723@@Z@Z; winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Devices::Enumeration::DeviceWatcher,winrt::Windows::Devices::Enumeration::DeviceInformationUpdate>::TypedEventHandler<winrt::Windows::Devices::Enumeration::DeviceWatcher,winrt::Windows::Devices::Enumeration::DeviceInformationUpdate>(CMidi2KSMidiEndpointManager *,long (CMidi2KSMidiEndpointManager::*)(winrt::Windows::Devices::Enumeration::DeviceWatcher,winrt::Windows::Devices::Enumeration::DeviceInformationUpdate))
0x18001b055  lea     rax, ?OnDeviceUpdated@CMidi2KSMidiEndpointManager@@AEAAJUDeviceWatcher@Enumeration@Devices@Windows@winrt@@UDeviceInformationUpdate@3456@@Z; CMidi2KSMidiEndpointManager::OnDeviceUpdated(winrt::Windows::Devices::Enumeration::DeviceWatcher,winrt::Windows::Devices::Enumeration::DeviceInformationUpdate)
0x18001b05c  mov     [rsp+160h+var_120], rax
0x18001b061  mov     dword ptr [rsp+160h+var_118], r14d
0x18001b066  mov     eax, dword ptr [rsp+160h+var_118+4]
0x18001b06a  mov     dword ptr [rsp+160h+var_118+4], eax
0x18001b06e  lea     r8, [rsp+160h+var_120]
0x18001b073  mov     rdx, r13
0x18001b076  lea     rcx, [rbp+60h+var_A0]
0x18001b07a  call    ??$?0VCMidi2KSMidiEndpointManager@@P80@EAAJUDeviceWatcher@Enumeration@Devices@Windows@winrt@@UDeviceInformationUpdate@2345@@Z@?$TypedEventHandler@UDeviceWatcher@Enumeration@Devices@Windows@winrt@@UDeviceInformationUpdate@2345@@Foundation@Windows@winrt@@QEAA@PEAVCMidi2KSMidiEndpointManager@@P84@EAAJUDeviceWatcher@Enumeration@Devices@23@UDeviceInformationUpdate@6723@@Z@Z; winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Devices::Enumeration::DeviceWatcher,winrt::Windows::Devices::Enumeration::DeviceInformationUpdate>::TypedEventHandler<winrt::Windows::Devices::Enumeration::DeviceWatcher,winrt::Windows::Devices::Enumeration::DeviceInformationUpdate>(CMidi2KSMidiEndpointManager *,long (CMidi2KSMidiEndpointManager::*)(winrt::Windows::Devices::Enumeration::DeviceWatcher,winrt::Windows::Devices::Enumeration::DeviceInformationUpdate))
0x18001b07f  lea     rax, ?OnEnumerationCompleted@CMidi2KSMidiEndpointManager@@AEAAJUDeviceWatcher@Enumeration@Devices@Windows@winrt@@UIInspectable@Foundation@56@@Z; CMidi2KSMidiEndpointManager::OnEnumerationCompleted(winrt::Windows::Devices::Enumeration::DeviceWatcher,winrt::Windows::Foundation::IInspectable)
0x18001b086  mov     [rsp+160h+var_120], rax
0x18001b08b  mov     dword ptr [rsp+160h+var_118], r14d
0x18001b090  mov     eax, dword ptr [rsp+160h+var_118+4]
0x18001b094  mov     dword ptr [rsp+160h+var_118+4], eax
0x18001b098  lea     r8, [rsp+160h+var_120]
0x18001b09d  mov     rdx, r13
0x18001b0a0  lea     rcx, [rbp+60h+var_A8]
0x18001b0a4  call    ??$?0VCMidi2KSMidiEndpointManager@@P80@EAAJUDeviceWatcher@Enumeration@Devices@Windows@winrt@@UIInspectable@Foundation@45@@Z@?$TypedEventHandler@UDeviceWatcher@Enumeration@Devices@Windows@winrt@@UIInspectable@Foundation@45@@Foundation@Windows@winrt@@QEAA@PEAVCMidi2KSMidiEndpointManager@@P84@EAAJUDeviceWatcher@Enumeration@Devices@23@UIInspectable@123@@Z@Z; winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Devices::Enumeration::DeviceWatcher,winrt::Windows::Foundation::IInspectable>::TypedEventHandler<winrt::Windows::Devices::Enumeration::DeviceWatcher,winrt::Windows::Foundation::IInspectable>(CMidi2KSMidiEndpointManager *,long (CMidi2KSMidiEndpointManager::*)(winrt::Windows::Devices::Enumeration::DeviceWatcher,winrt::Windows::Foundation::IInspectable))
0x18001b0a9  lea     rax, ?OnEnumerationCompleted@CMidi2KSMidiEndpointManager@@AEAAJUDeviceWatcher@Enumeration@Devices@Windows@winrt@@UIInspectable@Foundation@56@@Z; CMidi2KSMidiEndpointManager::OnEnumerationCompleted(winrt::Windows::Devices::Enumeration::DeviceWatcher,winrt::Windows::Foundation::IInspectable)
0x18001b0b0  mov     [rsp+160h+var_120], rax
0x18001b0b5  mov     dword ptr [rsp+160h+var_118], r14d
0x18001b0ba  mov     eax, dword ptr [rsp+160h+var_118+4]
0x18001b0be  mov     dword ptr [rsp+160h+var_118+4], eax
0x18001b0c2  lea     r8, [rsp+160h+var_120]
0x18001b0c7  mov     rdx, r13
0x18001b0ca  lea     rcx, [rbp+60h+arg_18]
0x18001b0d1  call    ??$?0VCMidi2KSMidiEndpointManager@@P80@EAAJUDeviceWatcher@Enumeration@Devices@Windows@winrt@@UIInspectable@Foundation@45@@Z@?$TypedEventHandler@UDeviceWatcher@Enumeration@Devices@Windows@winrt@@UIInspectable@Foundation@45@@Foundation@Windows@winrt@@QEAA@PEAVCMidi2KSMidiEndpointManager@@P84@EAAJUDeviceWatcher@Enumeration@Devices@23@UIInspectable@123@@Z@Z; winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Devices::Enumeration::DeviceWatcher,winrt::Windows::Foundation::IInspectable>::TypedEventHandler<winrt::Windows::Devices::Enumeration::DeviceWatcher,winrt::Windows::Foundation::IInspectable>(CMidi2KSMidiEndpointManager *,long (CMidi2KSMidiEndpointManager::*)(winrt::Windows::Devices::Enumeration::DeviceWatcher,winrt::Windows::Foundation::IInspectable))
0x18001b0d6  mov     [rbp+60h+arg_8], r14
0x18001b0da  mov     rcx, [r12]
0x18001b0de  mov     dword ptr [rsp+160h+var_100], 792h
0x18001b0e6  lea     r15, aOnecoreuapInte_11; "onecoreuap\\Internal\\BuildMetadata\\in"...
0x18001b0ed  mov     [rsp+160h+var_F8], r15
0x18001b0f2  mov     [rsp+160h+var_F0], r14
0x18001b0f7  mov     rax, [rcx]
0x18001b0fa  lea     r8, [rbp+60h+arg_8]
0x18001b0fe  mov     rdx, rbx
0x18001b101  mov     rax, [rax+30h]
0x18001b105  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b10a  test    eax, eax
0x18001b10c  js      loc_18001B5F6
0x18001b112  mov     rbx, [rbp+60h+arg_8]
0x18001b116  mov     rdx, r12
0x18001b119  lea     rcx, [rsp+160h+var_120]
0x18001b11e  call    ??$?0AEBUIDeviceWatcher@Enumeration@Devices@Windows@winrt@@X@?$weak_ref@UIDeviceWatcher@Enumeration@Devices@Windows@winrt@@@winrt@@QEAA@AEBUIDeviceWatcher@Enumeration@Devices@Windows@1@@Z; winrt::weak_ref<winrt::Windows::Devices::Enumeration::IDeviceWatcher>::weak_ref<winrt::Windows::Devices::Enumeration::IDeviceWatcher>(winrt::Windows::Devices::Enumeration::IDeviceWatcher const &)
0x18001b123  mov     qword ptr [rsp+160h+var_118], rbx
0x18001b128  lea     rdi, [r13+40h]
0x18001b12c  mov     rsi, [rsp+160h+var_120]
0x18001b131  mov     [rsp+160h+var_120], r14
0x18001b136  mov     [rbp+60h+var_98], r14
0x18001b13a  mov     [rbp+60h+var_D0], rsi
0x18001b13e  lea     rax, [rbp+60h+var_98]
0x18001b142  cmp     rax, rdi
0x18001b145  jz      short loc_18001B151
0x18001b147  mov     rax, [rdi]
0x18001b14a  mov     [rdi], r14
0x18001b14d  mov     [rbp+60h+var_98], rax
0x18001b151  lea     rax, [rbp+60h+var_D0]
0x18001b155  cmp     rdi, rax
0x18001b158  jz      short loc_18001B16C
0x18001b15a  cmp     [rdi], r14
0x18001b15d  jz      short loc_18001B167
0x18001b15f  mov     rcx, rdi
0x18001b162  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001b167  mov     [rdi], rsi
0x18001b16a  jmp     short loc_18001B17A
0x18001b16c  test    rsi, rsi
0x18001b16f  jz      short loc_18001B17A
0x18001b171  lea     rcx, [rbp+60h+var_D0]
0x18001b175  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001b17a  mov     rax, [rdi+8]
0x18001b17e  mov     [rbp+60h+var_90], rax
0x18001b182  mov     [rdi+8], rbx
0x18001b186  lea     rcx, [rbp+60h+var_98]
0x18001b18a  call    ??1?$event_revoker@UIDeviceWatcher@Enumeration@Devices@Windows@winrt@@$MP8type@?$abi@UIDeviceWatcher@Enumeration@Devices@Windows@winrt@@X@impl@5@EAAHUevent_token@5@@_E1??_96785@$BDI@AA@impl@winrt@@QEAA@XZ
0x18001b18f  lea     rcx, [rsp+160h+var_120]
0x18001b194  call    ??1?$event_revoker@UIDeviceWatcher@Enumeration@Devices@Windows@winrt@@$MP8type@?$abi@UIDeviceWatcher@Enumeration@Devices@Windows@winrt@@X@impl@5@EAAHUevent_token@5@@_E1??_96785@$BDI@AA@impl@winrt@@QEAA@XZ
0x18001b199  mov     [rbp+60h+arg_8], r14
0x18001b19d  mov     rcx, [r12]
0x18001b1a1  mov     dword ptr [rsp+160h+var_100], 7DEh
0x18001b1a9  mov     [rsp+160h+var_F8], r15
0x18001b1ae  mov     [rsp+160h+var_F0], r14
0x18001b1b3  mov     rax, [rcx]
0x18001b1b6  lea     r8, [rbp+60h+arg_8]
0x18001b1ba  mov     r15, qword ptr [rbp+60h+var_D8]
0x18001b1be  mov     rdx, r15
0x18001b1c1  mov     rax, [rax+50h]
0x18001b1c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b1ca  test    eax, eax
0x18001b1cc  js      loc_18001B603
0x18001b1d2  mov     rbx, [rbp+60h+arg_8]
0x18001b1d6  mov     rdx, r12
0x18001b1d9  lea     rcx, [rsp+160h+var_120]
0x18001b1de  call    ??$?0AEBUIDeviceWatcher@Enumeration@Devices@Windows@winrt@@X@?$weak_ref@UIDeviceWatcher@Enumeration@Devices@Windows@winrt@@@winrt@@QEAA@AEBUIDeviceWatcher@Enumeration@Devices@Windows@1@@Z; winrt::weak_ref<winrt::Windows::Devices::Enumeration::IDeviceWatcher>::weak_ref<winrt::Windows::Devices::Enumeration::IDeviceWatcher>(winrt::Windows::Devices::Enumeration::IDeviceWatcher const &)
0x18001b1e3  mov     qword ptr [rsp+160h+var_118], rbx
0x18001b1e8  lea     rdi, [r13+50h]
0x18001b1ec  mov     rsi, [rsp+160h+var_120]
0x18001b1f1  mov     [rsp+160h+var_120], r14
0x18001b1f6  mov     [rbp+60h+var_88], r14
0x18001b1fa  mov     [rbp+60h+var_C8], rsi
0x18001b1fe  lea     rax, [rbp+60h+var_88]
0x18001b202  cmp     rax, rdi
0x18001b205  jz      short loc_18001B211
  ... truncated ...
```
