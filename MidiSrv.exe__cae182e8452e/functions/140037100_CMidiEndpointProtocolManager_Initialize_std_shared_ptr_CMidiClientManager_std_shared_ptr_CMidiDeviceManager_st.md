# CMidiEndpointProtocolManager::Initialize(std::shared_ptr<CMidiClientManager> &,std::shared_ptr<CMidiDeviceManager> &,std::shared_ptr<CMidiSessionTracker> &)

- ea: `0x140037100`
- end: `0x140037a3e`
- name: `?Initialize@CMidiEndpointProtocolManager@@UEAAJAEAV?$shared_ptr@VCMidiClientManager@@@std@@AEAV?$shared_ptr@VCMidiDeviceManager@@@3@AEAV?$shared_ptr@VCMidiSessionTracker@@@3@@Z`
- size: `2366`
- prototype: ``
- caller_count: `0`
- callee_count: `25`
- tags: `authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x140002580`
- `0x140002670`
- `0x1400054e4`
- `0x14000617c`
- `0x1400061e8`
- `0x140006218`
- `0x14000984c`
- `0x14000a6b4`
- `0x14000c7f4`
- `0x14000ca00`
- `0x14000cc2c`
- `0x14000cd78`
- `0x14000d848`
- `0x14000d8b8`
- `0x14000d928`
- `0x14000d998`
- `0x14000da08`
- `0x1400144ac`
- `0x140035da8`
- `0x140035f40`
- `0x140035fa8`
- `0x1400361c4`
- `0x140036378`
- `0x140037100`
- `0x14005a010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1400379bc`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1400379bc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140037274`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140037274`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x14003725f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x14003725f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400372da`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14003799c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400372da`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14003799c`

## string_xrefs

- `0x1400371b1`: `CMidiEndpointProtocolManager::Initialize`
- `0x140037221`: `CMidiEndpointProtocolManager::Initialize`
- `0x1400371a6`: `Discovery and protocol negotiation (and metadata capture) are disabled`
- `0x1400372b8`: `avcore\midi2\service\exe\midiendpointprotocolmanager.cpp`
- `0x14003728b`: `MIDI 2.0 Protocol Manager`

## pseudocode

```c
__int64 __fastcall CMidiEndpointProtocolManager::Initialize(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v7; // rdx
  __int64 v8; // rcx
  bool v9; // al
  _DWORD *v10; // rcx
  __int64 v11; // r8
  __int64 v12; // r9
  HRESULT v13; // eax
  _DWORD *v14; // rcx
  __int64 v15; // r8
  __int64 v16; // r9
  HANDLE CurrentProcess; // rax
  __int64 v18; // rdi
  __int64 (__fastcall *v19)(__int64, _BYTE *, const wchar_t *, _QWORD); // rbx
  DWORD CurrentProcessId; // eax
  int v21; // eax
  unsigned int v22; // edx
  unsigned int v23; // ebx
  LPVOID v25; // rbx
  __int64 v26; // rax
  int v27; // eax
  __int64 *v28; // rbx
  __int64 **v29; // r12
  __int64 *v30; // rax
  char *v31; // rax
  __int128 v32; // xmm0
  char *v33; // rbx
  int v34; // ecx
  __int64 *v35; // rcx
  __int64 v36; // rax
  int v37; // eax
  __int64 v38; // rbx
  __int64 v39; // rsi
  __int64 *v40; // rdi
  __int64 *v41; // rcx
  LPVOID *v42; // r15
  __int64 v43; // rax
  int v44; // eax
  __int64 v45; // rbx
  __int64 v46; // rsi
  __int64 *v47; // rdi
  __int64 *v48; // rcx
  __int64 v49; // rax
  const wchar_t *v50; // r14
  int v51; // eax
  unsigned __int64 v52; // rbx
  __int64 v53; // rsi
  __int64 *v54; // rdi
  __int64 *v55; // rcx
  const char *v56; // rsi
  __int64 v57; // rax
  int v58; // eax
  __int64 v59; // rbx
  __int64 v60; // rax
  __int64 *v61; // rdi
  __int64 *v62; // rcx
  const char *v63; // rdi
  __int64 v64; // rax
  int v65; // eax
  __int64 v66; // rbx
  __int64 v67; // rax
  __int64 *v68; // r12
  __int64 v69; // rcx
  int v70; // eax
  void *v71; // rbx
  int v72; // eax
  HANDLE ProcessHeap; // rax
  _QWORD v74[2]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v75[24]; // [rsp+50h] [rbp-B0h] BYREF
  LPVOID *v76; // [rsp+70h] [rbp-90h] BYREF
  const char *v77; // [rsp+78h] [rbp-88h] BYREF
  const wchar_t *v78; // [rsp+80h] [rbp-80h] BYREF
  LPVOID v79; // [rsp+88h] [rbp-78h] BYREF
  const char *v80; // [rsp+90h] [rbp-70h]
  __int64 v81; // [rsp+98h] [rbp-68h]
  __int64 *v82; // [rsp+A8h] [rbp-58h] BYREF
  const char *v83; // [rsp+B0h] [rbp-50h] BYREF
  HANDLE hObject; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v85; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v86; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v87; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v88; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v89; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v90[2]; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v91[2]; // [rsp+F8h] [rbp-8h] BYREF
  __int64 v92[2]; // [rsp+108h] [rbp+8h] BYREF
  __int64 v93[2]; // [rsp+118h] [rbp+18h] BYREF
  __int64 v94[2]; // [rsp+128h] [rbp+28h] BYREF
  char *v95; // [rsp+138h] [rbp+38h] BYREF
  LPVOID lpMem; // [rsp+140h] [rbp+40h]
  wil::details::in1diag3 *retaddr; // [rsp+198h] [rbp+98h]
  int v98; // [rsp+1A0h] [rbp+A0h] BYREF

  std::shared_ptr<CMidiSessionTracker>::operator=(a1 + 40, a2);
  std::shared_ptr<CMidiSessionTracker>::operator=(a1 + 56, a3);
  std::shared_ptr<CMidiSessionTracker>::operator=(a1 + 72, a4);
  v98 = 1;
  if ( wil::reg::get_value_dword_nothrow<unsigned long,0>(v8, v7, L"Midi2DiscoveryEnabled", &v98) < 0 )
  {
    *(_BYTE *)(a1 + 16) = 1;
  }
  else
  {
    v9 = v98 != 0;
    *(_BYTE *)(a1 + 16) = v98 != 0;
    if ( !v9 )
    {
      v10 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
      if ( *v10 > 3u )
      {
        v77 = (const char *)a1;
        v76 = (LPVOID *)(a1 + 20);
        v78 = L"Discovery and protocol negotiation (and metadata capture) are disabled";
        v83 = "CMidiEndpointProtocolManager::Initialize";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapperByRef<16>>(
          (__int64)v10,
          (__int64)&byte_14008A6CF,
          v11,
          v12,
          &v83,
          (__int64)&v77,
          &v78);
      }
      return 0;
    }
  }
  v13 = CoInitializeEx_0(0, 0);
  if ( v13 < 0 )
  {
    *(_DWORD *)v75 = 6532;
    *(_QWORD *)&v75[8] = "onecoreuap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt\\base.h";
    *(_QWORD *)&v75[16] = 0;
    winrt::throw_hresult((unsigned int)v13, v75);
  }
  *(GUID *)(a1 + 20) = GUID_7a3def20_fb76_49b6_a3a0_3dcbcda8f482;
  v14 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
  if ( *v14 > 4u )
  {
    v76 = (LPVOID *)(a1 + 20);
    v77 = "CMidiEndpointProtocolManager::Initialize";
    v78 = (const wchar_t *)a1;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByRef<16>>(
      (__int64)v14,
      (__int64)&dword_14008A844,
      v15,
      v16,
      &v77);
  }
  CurrentProcess = GetCurrentProcess();
  v18 = *(_QWORD *)(a1 + 72);
  hObject = CurrentProcess;
  v19 = *(__int64 (__fastcall **)(__int64, _BYTE *, const wchar_t *, _QWORD))(*(_QWORD *)v18 + 16LL);
  CurrentProcessId = GetCurrentProcessId();
  *(_OWORD *)v75 = *(_OWORD *)(a1 + 20);
  v21 = v19(v18, v75, L"MIDI 2.0 Protocol Manager", CurrentProcessId);
  v23 = v21;
  if ( v21 >= 0 )
  {
    lpMem = winrt::impl::precreate_hstring_on_heap((winrt::impl *)0x9A, v22);
    v25 = lpMem;
    memcpy_s(
      (char *)lpMem + 28,
      0x134u,
      L"System.Devices.InterfaceClassGuid:=\"{E7CCE071-3C03-423f-88D3-F1045D02552B}\" AND System.Devices.InterfaceEnabled:"
       " = System.StructuredQueryType.Boolean#True",
      0x134u);
    v79 = v25;
    v76 = &v79;
    _InterlockedIncrement64(&qword_1400969D8);
    if ( winrt::impl::factory_cache_entry_v<winrt::Windows::Devices::Enumeration::DeviceInformation,winrt::Windows::Devices::Enumeration::IDeviceInformationStatics> )
    {
      v74[0] = 0;
      v26 = *(_QWORD *)winrt::impl::factory_cache_entry_v<winrt::Windows::Devices::Enumeration::DeviceInformation,winrt::Windows::Devices::Enumeration::IDeviceInformationStatics>;
      *(_DWORD *)v75 = 918;
      *(_QWORD *)&v75[8] = "onecoreuap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt\\Windows.Devices.Enumeration.h";
      *(_QWORD *)&v75[16] = 0;
      v27 = (*(__int64 (__fastcall **)(__int64, LPVOID, _QWORD *))(v26 + 112))(
              winrt::impl::factory_cache_entry_v<winrt::Windows::Devices::Enumeration::DeviceInformation,winrt::Windows::Devices::Enumeration::IDeviceInformationStatics>,
              v79,
              v74);
      if ( v27 < 0 )
        winrt::throw_hresult((unsigned int)v27, v75);
      v28 = (__int64 *)v74[0];
      _InterlockedDecrement64(&qword_1400969D8);
      v82 = (__int64 *)v74[0];
    }
    else
    {
      _InterlockedDecrement64(&qword_1400969D8);
      ___call_AEAV_lambda_1___1__CreateWatcher_DeviceInformation_Enumeration_Devices_Windows_winrt__SA_AEBUhstring_param_7__Z____factory_cache_entry_UDeviceInformation_Enumeration_Devices_Windows_winrt__UIDeviceInformationStatics_2345__impl_winrt__QEAA_A_PAEAV_lambda_1___1__CreateWatcher_DeviceInformation_Enumeration_Devices_Windows_2_SA_AEBUhstring_param_2__Z__Z(
        0,
        &v82,
        &v76);
      v28 = v82;
    }
    v29 = (__int64 **)(a1 + 184);
    if ( (__int64 **)(a1 + 184) != &v82 )
    {
      if ( *v29 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 + 184);
      v30 = v28;
      v28 = 0;
      v82 = 0;
      *v29 = v30;
    }
    if ( v28 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v82);
    *(_DWORD *)&v75[16] = 0;
    *(_QWORD *)&v75[8] = &CMidiEndpointProtocolManager::OnDeviceUpdated;
    *(_DWORD *)&v75[20] = (unsigned __int64)&CMidiEndpointProtocolManager::OnDeviceUpdated >> 32;
    v31 = (char *)operator new(0x28u);
    v32 = *(_OWORD *)&v75[8];
    v33 = v31;
    *((_DWORD *)v31 + 2) = 1;
    *((_QWORD *)v31 + 2) = a1;
    *(_OWORD *)(v31 + 24) = v32;
    _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
    v34 = *(_DWORD *)&v75[12];
    *(_QWORD *)v31 = ___7__delegate_U__TypedEventHandler_UDeviceWatcher_Enumeration_Devices_Windows_winrt__UDeviceInformation_2345__Foundation_Windows_winrt__V_lambda_27____0_____0VCMidiEndpointProtocolManager__P80_EAAJUDeviceWatcher_Enumeration_Devices_Windows_winrt__UDeviceInformation_2345__Z_1234_QEAA_PEAVCMidiEndpointProtocolManager__P86_EAAJUDeviceWatcher_Enumeration_Devices_34_UDeviceInformation_8934__Z_Z__impl_winrt__6B_;
    *(_DWORD *)&v75[12] = v34;
    *(_QWORD *)v75 = &CMidiEndpointProtocolManager::OnDeviceRemoved;
    v95 = v31;
    *(_DWORD *)&v75[8] = 0;
    winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Devices::Enumeration::DeviceWatcher,winrt::Windows::Devices::Enumeration::DeviceInformationUpdate>::TypedEventHandler<winrt::Windows::Devices::Enumeration::DeviceWatcher,winrt::Windows::Devices::Enumeration::DeviceInformationUpdate>(
      &v76,
      a1,
      (__int128 *)v75);
    *(_DWORD *)&v75[8] = 0;
    *(_QWORD *)v75 = &CMidiEndpointProtocolManager::OnDeviceUpdated;
    winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Devices::Enumeration::DeviceWatcher,winrt::Windows::Devices::Enumeration::DeviceInformationUpdate>::TypedEventHandler<winrt::Windows::Devices::Enumeration::DeviceWatcher,winrt::Windows::Devices::Enumeration::DeviceInformationUpdate>(
      &v78,
      a1,
      (__int128 *)v75);
    *(_DWORD *)&v75[8] = 0;
    *(_QWORD *)v75 = &CMidiEndpointProtocolManager::OnDeviceUpdated;
    winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Devices::Enumeration::DeviceWatcher,winrt::Windows::Foundation::IInspectable>::TypedEventHandler<winrt::Windows::Devices::Enumeration::DeviceWatcher,winrt::Windows::Foundation::IInspectable>(
      &v77,
      a1,
      (__int128 *)v75);
    *(_DWORD *)&v75[8] = 0;
    *(_QWORD *)v75 = &CMidiEndpointProtocolManager::OnDeviceUpdated;
    winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Devices::Enumeration::DeviceWatcher,winrt::Windows::Foundation::IInspectable>::TypedEventHandler<winrt::Windows::Devices::Enumeration::DeviceWatcher,winrt::Windows::Foundation::IInspectable>(
      &v83,
      a1,
      (__int128 *)v75);
    v35 = *v29;
    v74[0] = 0;
    LODWORD(v79) = 1938;
    v80 = "onecoreuap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt\\Windows.Devices.Enumeration.h";
    v36 = *v35;
    v81 = 0;
    v37 = (*(__int64 (__fastcall **)(__int64 *, char *, _QWORD *))(v36 + 48))(v35, v33, v74);
    if ( v37 < 0 )
      winrt::throw_hresult((unsigned int)v37, &v79);
    v38 = v74[0];
    winrt::weak_ref<winrt::Windows::Devices::Enumeration::IDeviceWatcher>::weak_ref<winrt::Windows::Devices::Enumeration::IDeviceWatcher>(
      v75,
      a1 + 184);
    v39 = *(_QWORD *)v75;
    v40 = (__int64 *)(a1 + 192);
    *(_QWORD *)&v75[8] = v38;
    *(_QWORD *)v75 = 0;
    v90[0] = 0;
    v85 = v39;
    if ( v90 != (__int64 *)(a1 + 192) )
    {
      v90[0] = *v40;
      *v40 = 0;
    }
    if ( v40 == &v85 )
    {
      if ( v39 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v85);
    }
    else
    {
      if ( *v40 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 + 192);
      *v40 = v39;
    }
    v90[1] = *(_QWORD *)(a1 + 200);
    *(_QWORD *)(a1 + 200) = v38;
    __1__event_revoker_UIDeviceWatcher_Enumeration_Devices_Windows_winrt___MP8type___abi_UIDeviceWatcher_Enumeration_Devices_Windows_winrt__X_impl_5_EAAHUevent_token_5___E1___96785__BDI_AA_impl_winrt__QEAA_XZ(v90);
    __1__event_revoker_UIDeviceWatcher_Enumeration_Devices_Windows_winrt___MP8type___abi_UIDeviceWatcher_Enumeration_Devices_Windows_winrt__X_impl_5_EAAHUevent_token_5___E1___96785__BDI_AA_impl_winrt__QEAA_XZ((__int64 *)v75);
    v41 = *v29;
    v74[0] = 0;
    v80 = "onecoreuap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt\\Windows.Devices.Enumeration.h";
    v42 = v76;
    v43 = *v41;
    LODWORD(v79) = 2014;
    v81 = 0;
    v44 = (*(__int64 (__fastcall **)(__int64 *, LPVOID *, _QWORD *))(v43 + 80))(v41, v76, v74);
    if ( v44 < 0 )
      winrt::throw_hresult((unsigned int)v44, &v79);
    v45 = v74[0];
    winrt::weak_ref<winrt::Windows::Devices::Enumeration::IDeviceWatcher>::weak_ref<winrt::Windows::Devices::Enumeration::IDeviceWatcher>(
      v75,
      a1 + 184);
    v46 = *(_QWORD *)v75;
    v47 = (__int64 *)(a1 + 208);
    *(_QWORD *)&v75[8] = v45;
    *(_QWORD *)v75 = 0;
    v91[0] = 0;
    v86 = v46;
    if ( v91 != (__int64 *)(a1 + 208) )
    {
      v91[0] = *v47;
      *v47 = 0;
    }
    if ( v47 == &v86 )
    {
      if ( v46 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v86);
    }
    else
    {
      if ( *v47 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 + 208);
      *v47 = v46;
    }
    v91[1] = *(_QWORD *)(a1 + 216);
    *(_QWORD *)(a1 + 216) = v45;
    __1__event_revoker_UIDeviceWatcher_Enumeration_Devices_Windows_winrt___MP8type___abi_UIDeviceWatcher_Enumeration_Devices_Windows_winrt__X_impl_5_EAAHUevent_token_5___E1___96785__BFI_AA_impl_winrt__QEAA_XZ(v91);
    __1__event_revoker_UIDeviceWatcher_Enumeration_Devices_Windows_winrt___MP8type___abi_UIDeviceWatcher_Enumeration_Devices_Windows_winrt__X_impl_5_EAAHUevent_token_5___E1___96785__BFI_AA_impl_winrt__QEAA_XZ((__int64 *)v75);
    v48 = *v29;
    v74[0] = 0;
    v80 = "onecoreuap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt\\Windows.Devices.Enumeration.h";
    v81 = 0;
    v49 = *v48;
    v50 = v78;
    LODWORD(v79) = 1976;
    v51 = (*(__int64 (__fastcall **)(__int64 *, const wchar_t *, _QWORD *))(v49 + 64))(v48, v78, v74);
    if ( v51 < 0 )
      winrt::throw_hresult((unsigned int)v51, &v79);
    v52 = v74[0];
    winrt::weak_ref<winrt::Windows::Devices::Enumeration::IDeviceWatcher>::weak_ref<winrt::Windows::Devices::Enumeration::IDeviceWatcher>(
      v75,
      a1 + 184);
    v53 = *(_QWORD *)v75;
    v54 = (__int64 *)(a1 + 224);
    *(_OWORD *)v75 = __PAIR128__(v52, 0);
    v92[0] = 0;
    v87 = v53;
    if ( v92 != (__int64 *)(a1 + 224) )
    {
      v92[0] = *v54;
      *v54 = 0;
    }
    if ( v54 == &v87 )
    {
      if ( v53 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v87);
    }
    else
    {
      if ( *v54 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 + 224);
      *v54 = v53;
    }
    v92[1] = *(_QWORD *)(a1 + 232);
    *(_QWORD *)(a1 + 232) = v52;
    __1__event_revoker_UIDeviceWatcher_Enumeration_Devices_Windows_winrt___MP8type___abi_UIDeviceWatcher_Enumeration_Devices_Windows_winrt__X_impl_5_EAAHUevent_token_5___E1___96785__BEI_AA_impl_winrt__QEAA_XZ(v92);
    __1__event_revoker_UIDeviceWatcher_Enumeration_Devices_Windows_winrt___MP8type___abi_UIDeviceWatcher_Enumeration_Devices_Windows_winrt__X_impl_5_EAAHUevent_token_5___E1___96785__BEI_AA_impl_winrt__QEAA_XZ((__int64 *)v75);
    v55 = *v29;
    v56 = v77;
    v80 = "onecoreuap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt\\Windows.Devices.Enumeration.h";
    v74[0] = 0;
    v57 = *v55;
    LODWORD(v79) = 2090;
    v81 = 0;
    v58 = (*(__int64 (__fastcall **)(__int64 *, const char *, _QWORD *))(v57 + 112))(v55, v77, v74);
    if ( v58 < 0 )
      winrt::throw_hresult((unsigned int)v58, &v79);
    v59 = v74[0];
    winrt::weak_ref<winrt::Windows::Devices::Enumeration::IDeviceWatcher>::weak_ref<winrt::Windows::Devices::Enumeration::IDeviceWatcher>(
      v75,
      a1 + 184);
    v60 = *(_QWORD *)v75;
    *(_QWORD *)&v75[8] = v59;
    v61 = (__int64 *)(a1 + 240);
    v74[0] = *(_QWORD *)v75;
    *(_QWORD *)v75 = 0;
    v93[0] = 0;
    v88 = v74[0];
    if ( v93 != (__int64 *)(a1 + 240) )
    {
      v93[0] = *v61;
      v60 = v74[0];
      *v61 = 0;
    }
    if ( v61 == &v88 )
    {
      if ( v60 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v88);
    }
    else
    {
      if ( *v61 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 + 240);
      *v61 = v74[0];
    }
    v93[1] = *(_QWORD *)(a1 + 248);
    *(_QWORD *)(a1 + 248) = v59;
    __1__event_revoker_UIDeviceWatcher_Enumeration_Devices_Windows_winrt___MP8type___abi_UIDeviceWatcher_Enumeration_Devices_Windows_winrt__X_impl_5_EAAHUevent_token_5___E1___96785__BHI_AA_impl_winrt__QEAA_XZ(v93);
    __1__event_revoker_UIDeviceWatcher_Enumeration_Devices_Windows_winrt___MP8type___abi_UIDeviceWatcher_Enumeration_Devices_Windows_winrt__X_impl_5_EAAHUevent_token_5___E1___96785__BHI_AA_impl_winrt__QEAA_XZ((__int64 *)v75);
    v62 = *v29;
    v63 = v83;
    v80 = "onecoreuap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt\\Windows.Devices.Enumeration.h";
    v74[0] = 0;
    v64 = *v62;
    LODWORD(v79) = 2052;
    v81 = 0;
    v65 = (*(__int64 (__fastcall **)(__int64 *, const char *, _QWORD *))(v64 + 96))(v62, v83, v74);
    if ( v65 < 0 )
      winrt::throw_hresult((unsigned int)v65, &v79);
    v66 = v74[0];
    winrt::weak_ref<winrt::Windows::Devices::Enumeration::IDeviceWatcher>::weak_ref<winrt::Windows::Devices::Enumeration::IDeviceWatcher>(
      v75,
      a1 + 184);
    v67 = *(_QWORD *)v75;
    *(_QWORD *)&v75[8] = v66;
    v68 = (__int64 *)(a1 + 256);
    v74[0] = *(_QWORD *)v75;
    *(_QWORD *)v75 = 0;
    v94[0] = 0;
    v89 = v74[0];
    if ( v94 != (__int64 *)(a1 + 256) )
    {
      v94[0] = *v68;
      v67 = v74[0];
      *v68 = 0;
    }
    if ( v68 == &v89 )
    {
      if ( v67 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v89);
    }
    else
    {
      if ( *v68 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 + 256);
      *v68 = v74[0];
    }
    v94[1] = *(_QWORD *)(a1 + 264);
    *(_QWORD *)(a1 + 264) = v66;
    __1__event_revoker_UIDeviceWatcher_Enumeration_Devices_Windows_winrt___MP8type___abi_UIDeviceWatcher_Enumeration_Devices_Windows_winrt__X_impl_5_EAAHUevent_token_5___E1___96785__BGI_AA_impl_winrt__QEAA_XZ(v94);
    __1__event_revoker_UIDeviceWatcher_Enumeration_Devices_Windows_winrt___MP8type___abi_UIDeviceWatcher_Enumeration_Devices_Windows_winrt__X_impl_5_EAAHUevent_token_5___E1___96785__BGI_AA_impl_winrt__QEAA_XZ((__int64 *)v75);
    v69 = *(_QWORD *)(a1 + 184);
    v80 = "onecoreuap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt\\Windows.Devices.Enumeration.h";
    LODWORD(v79) = 2145;
    v81 = 0;
    v70 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v69 + 136LL))(v69);
    if ( v70 < 0 )
      winrt::throw_hresult((unsigned int)v70, &v79);
    if ( v63 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v83);
    if ( v56 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v77);
    if ( v50 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v78);
    if ( v42 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v76);
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v95);
    v71 = lpMem;
    if ( lpMem )
    {
      v72 = _InterlockedDecrement((volatile signed __int32 *)lpMem + 6);
      if ( v72 )
      {
        if ( v72 < 0 )
          abort();
      }
      else
      {
        ProcessHeap = WINRT_IMPL_GetProcessHeap();
        WINRT_IMPL_HeapFree(ProcessHeap, 0, v71);
      }
    }
    if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(hObject);
    return 0;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x51,
    (unsigned int)"avcore\\midi2\\service\\exe\\midiendpointprotocolmanager.cpp",
    (const char *)(unsigned int)v21,
    (int)&hObject);
  if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(hObject);
  return v23;
}

```

## disassembly

```asm
0x140037100  push    rbp
0x140037102  push    rbx
0x140037103  push    rsi
0x140037104  push    rdi
0x140037105  push    r12
0x140037107  push    r13
0x140037109  push    r14
0x14003710b  push    r15
0x14003710d  lea     rbp, [rsp-58h]
0x140037112  sub     rsp, 158h
0x140037119  mov     r13, rcx
0x14003711c  mov     rdi, r9
0x14003711f  add     rcx, 28h ; '('
0x140037123  mov     rbx, r8
0x140037126  call    ??4?$shared_ptr@VCMidiSessionTracker@@@std@@QEAAAEAV01@AEBV01@@Z; std::shared_ptr<CMidiSessionTracker>::operator=(std::shared_ptr<CMidiSessionTracker> const &)
0x14003712b  lea     rcx, [r13+38h]
0x14003712f  mov     rdx, rbx
0x140037132  call    ??4?$shared_ptr@VCMidiSessionTracker@@@std@@QEAAAEAV01@AEBV01@@Z; std::shared_ptr<CMidiSessionTracker>::operator=(std::shared_ptr<CMidiSessionTracker> const &)
0x140037137  mov     rdx, rdi
0x14003713a  lea     rcx, [r13+48h]
0x14003713e  call    ??4?$shared_ptr@VCMidiSessionTracker@@@std@@QEAAAEAV01@AEBV01@@Z; std::shared_ptr<CMidiSessionTracker>::operator=(std::shared_ptr<CMidiSessionTracker> const &)
0x140037143  lea     r9, [rbp+90h+arg_0]
0x14003714a  mov     [rbp+90h+arg_0], 1
0x140037154  lea     r8, aMidi2discovery; "Midi2DiscoveryEnabled"
0x14003715b  call    ??$get_value_dword_nothrow@K$0A@@reg@wil@@YAJPEAUHKEY__@@PEBG1PEAK@Z; wil::reg::get_value_dword_nothrow<ulong,0>(HKEY__ *,ushort const *,ushort const *,ulong *)
0x140037160  xor     r14d, r14d
0x140037163  test    eax, eax
0x140037165  js      loc_1400371EC
0x14003716b  cmp     [rbp+90h+arg_0], r14d
0x140037172  setnbe  al
0x140037175  mov     [r13+10h], al
0x140037179  test    al, al
0x14003717b  jnz     short loc_1400371F1
0x14003717d  call    ?Instance@MidiSrvTelemetryProvider@@KAPEAV1@XZ; MidiSrvTelemetryProvider::Instance(void)
0x140037182  mov     rcx, [rax+8]
0x140037186  mov     eax, [rcx]
0x140037188  cmp     eax, 3
0x14003718b  jbe     loc_1400379A2
0x140037191  lea     rax, [r13+14h]
0x140037195  mov     [rsp+190h+var_118], r13
0x14003719a  mov     [rsp+190h+var_120], rax
0x14003719f  lea     rdx, byte_14008A6CF
0x1400371a6  lea     rax, aDiscoveryAndPr; "Discovery and protocol negotiation (and"...
0x1400371ad  mov     [rbp+90h+var_110], rax
0x1400371b1  lea     rax, aCmidiendpointp_6; "CMidiEndpointProtocolManager::Initializ"...
0x1400371b8  mov     [rbp+90h+var_E0], rax
0x1400371bc  lea     rax, [rsp+190h+var_120]
0x1400371c1  mov     [rsp+190h+var_158], rax
0x1400371c6  lea     rax, [rbp+90h+var_110]
0x1400371ca  mov     [rsp+190h+var_160], rax
0x1400371cf  lea     rax, [rsp+190h+var_118]
0x1400371d4  mov     [rsp+190h+var_168], rax
0x1400371d9  lea     rax, [rbp+90h+var_E0]
0x1400371dd  mov     qword ptr [rsp+190h+var_170], rax
0x1400371e2  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByRef@$0BA@@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByRef@$0BA@@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapperByRef<16>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByRef<16> const &)
0x1400371e7  jmp     loc_1400379A2
0x1400371ec  mov     byte ptr [r13+10h], 1
0x1400371f1  xor     edx, edx; dwCoInit
0x1400371f3  xor     ecx, ecx; pvReserved
0x1400371f5  call    CoInitializeEx_0
0x1400371fa  test    eax, eax
0x1400371fc  js      loc_1400379CF
0x140037202  movups  xmm0, xmmword ptr cs:_GUID_7a3def20_fb76_49b6_a3a0_3dcbcda8f482.Data1
0x140037209  lea     rsi, [r13+14h]
0x14003720d  movdqu  xmmword ptr [rsi], xmm0
0x140037211  call    ?Instance@MidiSrvTelemetryProvider@@KAPEAV1@XZ; MidiSrvTelemetryProvider::Instance(void)
0x140037216  mov     rcx, [rax+8]
0x14003721a  mov     eax, [rcx]
0x14003721c  cmp     eax, 4
0x14003721f  jbe     short loc_14003725F
0x140037221  lea     rax, aCmidiendpointp_6; "CMidiEndpointProtocolManager::Initializ"...
0x140037228  mov     [rsp+190h+var_120], rsi
0x14003722d  mov     [rsp+190h+var_118], rax
0x140037232  lea     rdx, dword_14008A844
0x140037239  lea     rax, [rsp+190h+var_120]
0x14003723e  mov     [rbp+90h+var_110], r13
0x140037242  mov     [rsp+190h+var_160], rax
0x140037247  lea     rax, [rbp+90h+var_110]
0x14003724b  mov     [rsp+190h+var_168], rax
0x140037250  lea     rax, [rsp+190h+var_118]
0x140037255  mov     qword ptr [rsp+190h+var_170], rax
0x14003725a  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByRef@$0BA@@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByRef@$0BA@@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByRef<16>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByRef<16> const &)
0x14003725f  call    cs:__imp_GetCurrentProcess
0x140037265  mov     rdi, [r13+48h]
0x140037269  mov     [rbp+90h+hObject], rax
0x14003726d  mov     rax, [rdi]
0x140037270  mov     rbx, [rax+10h]
0x140037274  call    cs:__imp_GetCurrentProcessId
0x14003727a  movups  xmm0, xmmword ptr [rsi]
0x14003727d  lea     rcx, [rbp+90h+hObject]
0x140037281  mov     [rsp+190h+var_168], r14
0x140037286  mov     qword ptr [rsp+190h+var_170], rcx; int
0x14003728b  lea     r8, aMidi20Protocol; "MIDI 2.0 Protocol Manager"
0x140037292  mov     r9d, eax
0x140037295  lea     rdx, [rsp+190h+var_140]
0x14003729a  mov     rcx, rdi
0x14003729d  mov     rax, rbx
0x1400372a0  movdqu  [rsp+190h+var_140], xmm0
0x1400372a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400372ab  mov     ebx, eax
0x1400372ad  test    eax, eax
0x1400372af  jns     short loc_1400372E7
0x1400372b1  mov     rcx, [rbp+98h]; this
0x1400372b8  lea     r8, aAvcoreMidi2Ser_12; "avcore\\midi2\\service\\exe\\midiendpoi"...
0x1400372bf  mov     r9d, eax; char *
0x1400372c2  mov     edx, 51h ; 'Q'; void *
0x1400372c7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400372cc  mov     rcx, [rbp+90h+hObject]; hObject
0x1400372d0  lea     rdx, [rcx-1]
0x1400372d4  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x1400372d8  ja      short loc_1400372E0
0x1400372da  call    cs:__imp_CloseHandle
0x1400372e0  mov     eax, ebx
0x1400372e2  jmp     loc_1400379A4
0x1400372e7  mov     ecx, 9Ah; this
0x1400372ec  call    ?precreate_hstring_on_heap@impl@winrt@@YAPEAUshared_hstring_header@12@I@Z; winrt::impl::precreate_hstring_on_heap(uint)
0x1400372f1  mov     edx, 134h; DestinationSize
0x1400372f6  mov     [rbp+90h+lpMem], rax
0x1400372fa  mov     r9d, edx; SourceSize
0x1400372fd  lea     r8, aSystemDevicesI_2; "System.Devices.InterfaceClassGuid:=\"{E"...
0x140037304  mov     rbx, rax
0x140037307  lea     rcx, [rax+1Ch]; Destination
0x14003730b  call    memcpy_s
0x140037310  lea     rax, [rbp+90h+var_108]
0x140037314  mov     [rbp+90h+var_108], rbx
0x140037318  mov     [rsp+190h+var_120], rax
0x14003731d  lock inc cs:qword_1400969D8
0x140037325  mov     rcx, cs:??$factory_cache_entry_v@UDeviceInformation@Enumeration@Devices@Windows@winrt@@UIDeviceInformationStatics@2345@@impl@winrt@@3U?$factory_cache_entry@UDeviceInformation@Enumeration@Devices@Windows@winrt@@UIDeviceInformationStatics@2345@@12@A; factory_cache_entry<winrt::Windows::Devices::Enumeration::DeviceInformation,winrt::Windows::Devices::Enumeration::IDeviceInformationStatics>::winrt::factory_cache_entry<winrt::Windows::Devices::Enumeration::DeviceInformation,winrt::Windows::Devices::Enumeration::IDeviceInformationStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::Devices::Enumeration::DeviceInformation,winrt::Windows::Devices::Enumeration::IDeviceInformationStatics>
0x14003732c  lea     r15, aOnecoreuapInte_4; "onecoreuap\\Internal\\BuildMetadata\\in"...
0x140037333  test    rcx, rcx
0x140037336  jz      short loc_14003737F
0x140037338  mov     rdx, [rbp+90h+var_108]
0x14003733c  lea     r8, [rsp+190h+var_150]
0x140037341  mov     [rsp+190h+var_150], r14
0x140037346  mov     rax, [rcx]
0x140037349  mov     dword ptr [rsp+190h+var_140], 396h
0x140037351  mov     qword ptr [rsp+190h+var_140+8], r15
0x140037356  mov     [rsp+190h+var_130], r14
0x14003735b  mov     rax, [rax+70h]
0x14003735f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140037364  test    eax, eax
0x140037366  js      loc_1400379F5
0x14003736c  mov     rbx, [rsp+190h+var_150]
0x140037371  lock dec cs:qword_1400969D8
0x140037379  mov     [rbp+90h+var_E8], rbx
0x14003737d  jmp     short loc_140037399
0x14003737f  lock dec cs:qword_1400969D8
0x140037387  lea     r8, [rsp+190h+var_120]
0x14003738c  lea     rdx, [rbp+90h+var_E8]
0x140037390  call    ??$call@AEAV_lambda_1_@?1??CreateWatcher@DeviceInformation@Enumeration@Devices@Windows@winrt@@SA@AEBUhstring@param@7@@Z@@?$factory_cache_entry@UDeviceInformation@Enumeration@Devices@Windows@winrt@@UIDeviceInformationStatics@2345@@impl@winrt@@QEAA?A_PAEAV_lambda_1_@?1??CreateWatcher@DeviceInformation@Enumeration@Devices@Windows@2@SA@AEBUhstring@param@2@@Z@@Z
0x140037395  mov     rbx, [rbp+90h+var_E8]
0x140037399  lea     r12, [r13+0B8h]
0x1400373a0  lea     rax, [rbp+90h+var_E8]
0x1400373a4  cmp     r12, rax
0x1400373a7  jz      short loc_1400373C5
0x1400373a9  cmp     [r12], r14
0x1400373ad  jz      short loc_1400373B7
0x1400373af  mov     rcx, r12
0x1400373b2  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x1400373b7  mov     rax, rbx
0x1400373ba  mov     rbx, r14
0x1400373bd  mov     [rbp+90h+var_E8], rbx
0x1400373c1  mov     [r12], rax
0x1400373c5  test    rbx, rbx
0x1400373c8  jz      short loc_1400373D3
0x1400373ca  lea     rcx, [rbp+90h+var_E8]
0x1400373ce  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x1400373d3  lea     rax, ?OnDeviceUpdated@CMidiEndpointProtocolManager@@AEAAJUDeviceWatcher@Enumeration@Devices@Windows@winrt@@UDeviceInformationUpdate@3456@@Z; CMidiEndpointProtocolManager::OnDeviceUpdated(winrt::Windows::Devices::Enumeration::DeviceWatcher,winrt::Windows::Devices::Enumeration::DeviceInformationUpdate)
0x1400373da  mov     dword ptr [rsp+190h+var_130], r14d
0x1400373df  mov     qword ptr [rsp+190h+var_140+8], rax
0x1400373e4  mov     ecx, 28h ; '('; Size
0x1400373e9  mov     eax, dword ptr [rsp+190h+var_140+0Ch]
0x1400373ed  mov     dword ptr [rsp+190h+var_130+4], eax
0x1400373f1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400373f6  movups  xmm0, [rsp+190h+var_140+8]
0x1400373fb  mov     rbx, rax
0x1400373fe  mov     dword ptr [rax+8], 1
0x140037405  mov     [rax+10h], r13
0x140037409  movdqu  xmmword ptr [rax+18h], xmm0
0x14003740e  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x140037415  mov     ecx, dword ptr [rsp+190h+var_140+0Ch]
0x140037419  lea     rax, ??_7?$delegate@U?$TypedEventHandler@UDeviceWatcher@Enumeration@Devices@Windows@winrt@@UDeviceInformation@2345@@Foundation@Windows@winrt@@V_lambda_27__@?0???$?0VCMidiEndpointProtocolManager@@P80@EAAJUDeviceWatcher@Enumeration@Devices@Windows@winrt@@UDeviceInformation@2345@@Z@1234@QEAA@PEAVCMidiEndpointProtocolManager@@P86@EAAJUDeviceWatcher@Enumeration@Devices@34@UDeviceInformation@8934@@Z@Z@@impl@winrt@@6B@; const winrt::impl::delegate<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Devices::Enumeration::DeviceWatcher,winrt::Windows::Devices::Enumeration::DeviceInformation>,`winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Devices::Enumeration::DeviceWatcher,winrt::Windows::Devices::Enumeration::DeviceInformation>::DeviceWatcher(CMidiEndpointProtocolManager *,long (CMidiEndpointProtocolManager::*)(winrt::Windows::Devices::Enumeration::DeviceWatcher,winrt::Windows::Devices::Enumeration::DeviceInformation))'::`1'::_lambda_27__>::`vftable'
0x140037420  mov     [rbx], rax
0x140037423  lea     r8, [rsp+190h+var_140]
0x140037428  lea     rax, ?OnDeviceRemoved@CMidiEndpointProtocolManager@@AEAAJUDeviceWatcher@Enumeration@Devices@Windows@winrt@@UDeviceInformationUpdate@3456@@Z; CMidiEndpointProtocolManager::OnDeviceRemoved(winrt::Windows::Devices::Enumeration::DeviceWatcher,winrt::Windows::Devices::Enumeration::DeviceInformationUpdate)
0x14003742f  mov     dword ptr [rsp+190h+var_140+0Ch], ecx
0x140037433  mov     rdx, r13
0x140037436  mov     qword ptr [rsp+190h+var_140], rax
0x14003743b  lea     rcx, [rsp+190h+var_120]
0x140037440  mov     [rbp+90h+var_58], rbx
0x140037444  mov     dword ptr [rsp+190h+var_140+8], r14d
0x140037449  call    ??$?0VCMidiEndpointProtocolManager@@P80@EAAJUDeviceWatcher@Enumeration@Devices@Windows@winrt@@UDeviceInformationUpdate@2345@@Z@?$TypedEventHandler@UDeviceWatcher@Enumeration@Devices@Windows@winrt@@UDeviceInformationUpdate@2345@@Foundation@Windows@winrt@@QEAA@PEAVCMidiEndpointProtocolManager@@P84@EAAJUDeviceWatcher@Enumeration@Devices@23@UDeviceInformationUpdate@6723@@Z@Z; winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Devices::Enumeration::DeviceWatcher,winrt::Windows::Devices::Enumeration::DeviceInformationUpdate>::TypedEventHandler<winrt::Windows::Devices::Enumeration::DeviceWatcher,winrt::Windows::Devices::Enumeration::DeviceInformationUpdate>(CMidiEndpointProtocolManager *,long (CMidiEndpointProtocolManager::*)(winrt::Windows::Devices::Enumeration::DeviceWatcher,winrt::Windows::Devices::Enumeration::DeviceInformationUpdate))
0x14003744e  lea     rax, ?OnDeviceUpdated@CMidiEndpointProtocolManager@@AEAAJUDeviceWatcher@Enumeration@Devices@Windows@winrt@@UDeviceInformationUpdate@3456@@Z; CMidiEndpointProtocolManager::OnDeviceUpdated(winrt::Windows::Devices::Enumeration::DeviceWatcher,winrt::Windows::Devices::Enumeration::DeviceInformationUpdate)
0x140037455  mov     dword ptr [rsp+190h+var_140+8], r14d
0x14003745a  mov     qword ptr [rsp+190h+var_140], rax
0x14003745f  lea     r8, [rsp+190h+var_140]
0x140037464  mov     eax, dword ptr [rsp+190h+var_140+0Ch]
0x140037468  lea     rcx, [rbp+90h+var_110]
0x14003746c  mov     rdx, r13
0x14003746f  mov     dword ptr [rsp+190h+var_140+0Ch], eax
0x140037473  call    ??$?0VCMidiEndpointProtocolManager@@P80@EAAJUDeviceWatcher@Enumeration@Devices@Windows@winrt@@UDeviceInformationUpdate@2345@@Z@?$TypedEventHandler@UDeviceWatcher@Enumeration@Devices@Windows@winrt@@UDeviceInformationUpdate@2345@@Foundation@Windows@winrt@@QEAA@PEAVCMidiEndpointProtocolManager@@P84@EAAJUDeviceWatcher@Enumeration@Devices@23@UDeviceInformationUpdate@6723@@Z@Z; winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Devices::Enumeration::DeviceWatcher,winrt::Windows::Devices::Enumeration::DeviceInformationUpdate>::TypedEventHandler<winrt::Windows::Devices::Enumeration::DeviceWatcher,winrt::Windows::Devices::Enumeration::DeviceInformationUpdate>(CMidiEndpointProtocolManager *,long (CMidiEndpointProtocolManager::*)(winrt::Windows::Devices::Enumeration::DeviceWatcher,winrt::Windows::Devices::Enumeration::DeviceInformationUpdate))
0x140037478  lea     rax, ?OnDeviceUpdated@CMidiEndpointProtocolManager@@AEAAJUDeviceWatcher@Enumeration@Devices@Windows@winrt@@UDeviceInformationUpdate@3456@@Z; CMidiEndpointProtocolManager::OnDeviceUpdated(winrt::Windows::Devices::Enumeration::DeviceWatcher,winrt::Windows::Devices::Enumeration::DeviceInformationUpdate)
0x14003747f  mov     dword ptr [rsp+190h+var_140+8], r14d
0x140037484  mov     qword ptr [rsp+190h+var_140], rax
0x140037489  lea     r8, [rsp+190h+var_140]
0x14003748e  mov     eax, dword ptr [rsp+190h+var_140+0Ch]
0x140037492  lea     rcx, [rsp+190h+var_118]
0x140037497  mov     rdx, r13
0x14003749a  mov     dword ptr [rsp+190h+var_140+0Ch], eax
0x14003749e  call    ??$?0VCMidiEndpointProtocolManager@@P80@EAAJUDeviceWatcher@Enumeration@Devices@Windows@winrt@@UIInspectable@Foundation@45@@Z@?$TypedEventHandler@UDeviceWatcher@Enumeration@Devices@Windows@winrt@@UIInspectable@Foundation@45@@Foundation@Windows@winrt@@QEAA@PEAVCMidiEndpointProtocolManager@@P84@EAAJUDeviceWatcher@Enumeration@Devices@23@UIInspectable@123@@Z@Z; winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Devices::Enumeration::DeviceWatcher,winrt::Windows::Foundation::IInspectable>::TypedEventHandler<winrt::Windows::Devices::Enumeration::DeviceWatcher,winrt::Windows::Foundation::IInspectable>(CMidiEndpointProtocolManager *,long (CMidiEndpointProtocolManager::*)(winrt::Windows::Devices::Enumeration::DeviceWatcher,winrt::Windows::Foundation::IInspectable))
0x1400374a3  lea     rax, ?OnDeviceUpdated@CMidiEndpointProtocolManager@@AEAAJUDeviceWatcher@Enumeration@Devices@Windows@winrt@@UDeviceInformationUpdate@3456@@Z; CMidiEndpointProtocolManager::OnDeviceUpdated(winrt::Windows::Devices::Enumeration::DeviceWatcher,winrt::Windows::Devices::Enumeration::DeviceInformationUpdate)
0x1400374aa  mov     dword ptr [rsp+190h+var_140+8], r14d
0x1400374af  mov     qword ptr [rsp+190h+var_140], rax
0x1400374b4  lea     r8, [rsp+190h+var_140]
0x1400374b9  mov     eax, dword ptr [rsp+190h+var_140+0Ch]
0x1400374bd  lea     rcx, [rbp+90h+var_E0]
0x1400374c1  mov     rdx, r13
0x1400374c4  mov     dword ptr [rsp+190h+var_140+0Ch], eax
0x1400374c8  call    ??$?0VCMidiEndpointProtocolManager@@P80@EAAJUDeviceWatcher@Enumeration@Devices@Windows@winrt@@UIInspectable@Foundation@45@@Z@?$TypedEventHandler@UDeviceWatcher@Enumeration@Devices@Windows@winrt@@UIInspectable@Foundation@45@@Foundation@Windows@winrt@@QEAA@PEAVCMidiEndpointProtocolManager@@P84@EAAJUDeviceWatcher@Enumeration@Devices@23@UIInspectable@123@@Z@Z; winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Devices::Enumeration::DeviceWatcher,winrt::Windows::Foundation::IInspectable>::TypedEventHandler<winrt::Windows::Devices::Enumeration::DeviceWatcher,winrt::Windows::Foundation::IInspectable>(CMidiEndpointProtocolManager *,long (CMidiEndpointProtocolManager::*)(winrt::Windows::Devices::Enumeration::DeviceWatcher,winrt::Windows::Foundation::IInspectable))
0x1400374cd  mov     rcx, [r12]
0x1400374d1  lea     r8, [rsp+190h+var_150]
0x1400374d6  mov     [rsp+190h+var_150], r14
0x1400374db  mov     rdx, rbx
0x1400374de  mov     dword ptr [rbp+90h+var_108], 792h
0x1400374e5  mov     [rbp+90h+var_100], r15
0x1400374e9  mov     rax, [rcx]
0x1400374ec  mov     [rbp+90h+var_F8], r14
0x1400374f0  mov     rax, [rax+30h]
0x1400374f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400374f9  test    eax, eax
0x1400374fb  js      loc_140037A02
0x140037501  mov     rbx, [rsp+190h+var_150]
0x140037506  lea     rcx, [rsp+190h+var_140]
0x14003750b  mov     rdx, r12
0x14003750e  call    ??$?0AEBUIDeviceWatcher@Enumeration@Devices@Windows@winrt@@X@?$weak_ref@UIDeviceWatcher@Enumeration@Devices@Windows@winrt@@@winrt@@QEAA@AEBUIDeviceWatcher@Enumeration@Devices@Windows@1@@Z; winrt::weak_ref<winrt::Windows::Devices::Enumeration::IDeviceWatcher>::weak_ref<winrt::Windows::Devices::Enumeration::IDeviceWatcher>(winrt::Windows::Devices::Enumeration::IDeviceWatcher const &)
0x140037513  mov     rsi, qword ptr [rsp+190h+var_140]
0x140037518  lea     rax, [rbp+90h+var_A8]
0x14003751c  lea     rdi, [r13+0C0h]
0x140037523  mov     qword ptr [rsp+190h+var_140+8], rbx
0x140037528  mov     qword ptr [rsp+190h+var_140], r14
0x14003752d  mov     [rbp+90h+var_A8], r14
0x140037531  mov     [rbp+90h+var_D0], rsi
0x140037535  cmp     rax, rdi
0x140037538  jz      short loc_140037544
0x14003753a  mov     rax, [rdi]
0x14003753d  mov     [rbp+90h+var_A8], rax
0x140037541  mov     [rdi], r14
0x140037544  lea     rax, [rbp+90h+var_D0]
0x140037548  cmp     rdi, rax
0x14003754b  jz      short loc_14003755F
0x14003754d  cmp     [rdi], r14
0x140037550  jz      short loc_14003755A
0x140037552  mov     rcx, rdi
0x140037555  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x14003755a  mov     [rdi], rsi
0x14003755d  jmp     short loc_14003756D
0x14003755f  test    rsi, rsi
0x140037562  jz      short loc_14003756D
0x140037564  lea     rcx, [rbp+90h+var_D0]
0x140037568  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x14003756d  mov     rax, [rdi+8]
0x140037571  lea     rcx, [rbp+90h+var_A8]
0x140037575  mov     [rbp+90h+var_A0], rax
0x140037579  mov     [rdi+8], rbx
0x14003757d  call    ??1?$event_revoker@UIDeviceWatcher@Enumeration@Devices@Windows@winrt@@$MP8type@?$abi@UIDeviceWatcher@Enumeration@Devices@Windows@winrt@@X@impl@5@EAAHUevent_token@5@@_E1??_96785@$BDI@AA@impl@winrt@@QEAA@XZ
0x140037582  lea     rcx, [rsp+190h+var_140]
0x140037587  call    ??1?$event_revoker@UIDeviceWatcher@Enumeration@Devices@Windows@winrt@@$MP8type@?$abi@UIDeviceWatcher@Enumeration@Devices@Windows@winrt@@X@impl@5@EAAHUevent_token@5@@_E1??_96785@$BDI@AA@impl@winrt@@QEAA@XZ
0x14003758c  mov     rcx, [r12]
0x140037590  lea     r8, [rsp+190h+var_150]
0x140037595  mov     [rsp+190h+var_150], r14
0x14003759a  mov     [rbp+90h+var_100], r15
0x14003759e  mov     r15, [rsp+190h+var_120]
0x1400375a3  mov     rax, [rcx]
0x1400375a6  mov     rdx, r15
0x1400375a9  mov     dword ptr [rbp+90h+var_108], 7DEh
0x1400375b0  mov     [rbp+90h+var_F8], r14
0x1400375b4  mov     rax, [rax+50h]
0x1400375b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400375bd  test    eax, eax
0x1400375bf  js      loc_140037A0E
0x1400375c5  mov     rbx, [rsp+190h+var_150]
0x1400375ca  lea     rcx, [rsp+190h+var_140]
0x1400375cf  mov     rdx, r12
0x1400375d2  call    ??$?0AEBUIDeviceWatcher@Enumeration@Devices@Windows@winrt@@X@?$weak_ref@UIDeviceWatcher@Enumeration@Devices@Windows@winrt@@@winrt@@QEAA@AEBUIDeviceWatcher@Enumeration@Devices@Windows@1@@Z; winrt::weak_ref<winrt::Windows::Devices::Enumeration::IDeviceWatcher>::weak_ref<winrt::Windows::Devices::Enumeration::IDeviceWatcher>(winrt::Windows::Devices::Enumeration::IDeviceWatcher const &)
0x1400375d7  mov     rsi, qword ptr [rsp+190h+var_140]
0x1400375dc  lea     rax, [rbp+90h+var_98]
0x1400375e0  lea     rdi, [r13+0D0h]
0x1400375e7  mov     qword ptr [rsp+190h+var_140+8], rbx
0x1400375ec  mov     qword ptr [rsp+190h+var_140], r14
0x1400375f1  mov     [rbp+90h+var_98], r14
0x1400375f5  mov     [rbp+90h+var_C8], rsi
0x1400375f9  cmp     rax, rdi
0x1400375fc  jz      short loc_140037608
0x1400375fe  mov     rax, [rdi]
0x140037601  mov     [rbp+90h+var_98], rax
0x140037605  mov     [rdi], r14
0x140037608  lea     rax, [rbp+90h+var_C8]
0x14003760c  cmp     rdi, rax
0x14003760f  jz      short loc_140037623
0x140037611  cmp     [rdi], r14
  ... truncated ...
```
