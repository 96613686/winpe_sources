# LocationSignalManager::Finalize(void)

- ea: `0x18003aa00`
- end: `0x18003b359`
- name: `?Finalize@LocationSignalManager@@UEAAJXZ`
- size: `2393`
- prototype: `__int64 __fastcall(LocationSignalManager *__hidden this)`
- caller_count: `0`
- callee_count: `18`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x180019618`
- `0x18001be08`
- `0x180021450`
- `0x1800244ac`
- `0x1800266e0`
- `0x180028434`
- `0x18003aa00`
- `0x18003b360`
- `0x18003b3b0`
- `0x180081638`
- `0x1800831e0`
- `0x180091664`
- `0x180093994`
- `0x180095728`
- `0x1800a98c0`
- `0x1800d2640`
- `0x1800e9238`
- `0x18015e010`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18003b352`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18003b352`
- `tzautoupdate!IsTimeZoneAutoUpdateEnabled` at `0x18003af4f`
- `tzautoupdate!IsTimeZoneAutoUpdateEnabled` at `0x18003af4f`

## string_xrefs

- `0x18003b1d3`: `m_networkConnectedInStandbyWnf.SubscribeToWnfState( LocWnfCommon::ActualStateNameToLoc(WNF_SEB_NETWORK_CONNECTIVITY_IN_STANDBY), networkConnectedInStandbyFn)`
- `0x18003b031`: `m_airplaneModeWnf.SubscribeToWnfState(LocWnfCommon::ActualStateNameToLoc(WNF_SRC_SYSTEM_RADIO_CHANGED), airplaneModeFn)`
- `0x18003b102`: `m_modernStandbyActiveWnf.SubscribeToWnfState( LocWnfCommon::ActualStateNameToLoc(WNF_PO_SCENARIO_CHANGE), modernStandbyFn)`
- `0x18003ae4e`: `m_fmdEnabledWindowsSettingsWnf.SubscribeToWnfState( LocWnfCommon::ActualStateNameToLoc(WNF_SHEL_SETTINGS_CHANGED), fmdCheckFn)`
- `0x18003add6`: `m_fmdEnabledMdmWnf.SubscribeToWnfState(LocWnfCommon::ActualStateNameToLoc(WNF_GPOL_SYSTEM_CHANGES), fmdCheckFn)`
- `0x18003af25`: `m_nonCellularConnectedWnf.SubscribeToWnfState( LocWnfCommon::ActualStateNameToLoc(WNF_CNET_NON_CELLULAR_CONNECTED), nonCellularConnectedFn)`

## pseudocode

```c
// Hidden C++ exception states: #wind=35
__int64 __fastcall LocationSignalManager::Finalize(LocationSignalManager *this)
{
  __int64 v2; // rbx
  _QWORD *v3; // rax
  _QWORD *v4; // rcx
  __int64 v5; // rbx
  _QWORD *v6; // rax
  _QWORD *v7; // rcx
  __int64 v8; // rbx
  _QWORD *v9; // rax
  _QWORD *v10; // rcx
  __int64 v11; // rbx
  _QWORD *v12; // rax
  _QWORD *v13; // rcx
  __int64 v14; // rbx
  _QWORD *v15; // rax
  _QWORD *v16; // rcx
  __int64 *v17; // rax
  volatile signed __int32 *v18; // rbx
  __int64 v19; // rsi
  __int64 v20; // rsi
  int v21; // eax
  __int64 v22; // rax
  __int64 v23; // rax
  int v24; // eax
  int v25; // eax
  __int64 v26; // rax
  __int64 v27; // rax
  int v28; // eax
  __int64 v29; // rax
  __int64 v30; // rax
  int v31; // eax
  __int64 v32; // rax
  __int64 v33; // rax
  int v34; // eax
  __int64 v35; // rax
  __int64 v36; // rax
  int v37; // eax
  _BYTE *v38; // rdx
  _BYTE *v39; // rdx
  _BYTE *v40; // rdx
  _BYTE *v41; // rdx
  _BYTE *v42; // rdx
  _BYTE *v43; // rdx
  _QWORD **v44; // rcx
  _QWORD *v45; // rcx
  _QWORD *v46; // rbx
  char *v48; // [rsp+28h] [rbp-D8h]
  int v49; // [rsp+30h] [rbp-D0h] BYREF
  __int64 (__fastcall ***v50)(); // [rsp+38h] [rbp-C8h] BYREF
  __int128 v51; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v52; // [rsp+50h] [rbp-B0h]
  _BYTE v53[8]; // [rsp+60h] [rbp-A0h] BYREF
  std::_Ref_count_base *v54; // [rsp+68h] [rbp-98h]
  _BYTE v55[8]; // [rsp+70h] [rbp-90h] BYREF
  std::_Ref_count_base *v56; // [rsp+78h] [rbp-88h]
  __int64 (__fastcall **v57)(); // [rsp+80h] [rbp-80h] BYREF
  LocationSignalManager *v58; // [rsp+88h] [rbp-78h]
  __int64 (__fastcall ***v59)(); // [rsp+B8h] [rbp-48h]
  _BYTE v60[56]; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v61; // [rsp+F8h] [rbp-8h]
  _BYTE v62[56]; // [rsp+100h] [rbp+0h] BYREF
  _BYTE *v63; // [rsp+138h] [rbp+38h]
  _BYTE v64[56]; // [rsp+140h] [rbp+40h] BYREF
  _BYTE *v65; // [rsp+178h] [rbp+78h]
  _BYTE v66[56]; // [rsp+180h] [rbp+80h] BYREF
  _BYTE *v67; // [rsp+1B8h] [rbp+B8h]
  _BYTE v68[56]; // [rsp+1C0h] [rbp+C0h] BYREF
  _BYTE *v69; // [rsp+1F8h] [rbp+F8h]
  _BYTE v70[56]; // [rsp+200h] [rbp+100h] BYREF
  _BYTE *v71; // [rsp+238h] [rbp+138h]
  _BYTE v72[56]; // [rsp+240h] [rbp+140h] BYREF
  _BYTE *v73; // [rsp+278h] [rbp+178h]
  __int128 v74; // [rsp+280h] [rbp+180h] BYREF
  int v75; // [rsp+290h] [rbp+190h] BYREF
  wil::details::in1diag5 *retaddr; // [rsp+2E8h] [rbp+1E8h]

  v74 = 0;
  std::list<ATL::CAdapt<ATL::CComPtr<ILocationAcquire>>>::_Alloc_sentinel_and_proxy(&v74);
  if ( *((_QWORD *)&v74 + 1) == 0xAAAAAAAAAAAAAAALL )
    goto LABEL_71;
  *(_QWORD *)&v52 = &v74;
  *((_QWORD *)&v52 + 1) = 0;
  v2 = v74;
  v3 = std::_Allocate<16,std::_Default_allocate_traits>(0x18u);
  *((_DWORD *)v3 + 4) = 2;
  ++*((_QWORD *)&v74 + 1);
  v4 = *(_QWORD **)(v2 + 8);
  *v3 = v2;
  v3[1] = v4;
  *(_QWORD *)(v2 + 8) = v3;
  *v4 = v3;
  if ( *((_QWORD *)&v74 + 1) == 0xAAAAAAAAAAAAAAALL )
    goto LABEL_71;
  *(_QWORD *)&v52 = &v74;
  *((_QWORD *)&v52 + 1) = 0;
  v5 = v74;
  v6 = std::_Allocate<16,std::_Default_allocate_traits>(0x18u);
  *((_DWORD *)v6 + 4) = 1;
  ++*((_QWORD *)&v74 + 1);
  v7 = *(_QWORD **)(v5 + 8);
  *v6 = v5;
  v6[1] = v7;
  *(_QWORD *)(v5 + 8) = v6;
  *v7 = v6;
  if ( *((_QWORD *)&v74 + 1) == 0xAAAAAAAAAAAAAAALL )
    goto LABEL_71;
  *(_QWORD *)&v52 = &v74;
  *((_QWORD *)&v52 + 1) = 0;
  v8 = v74;
  v9 = std::_Allocate<16,std::_Default_allocate_traits>(0x18u);
  *((_DWORD *)v9 + 4) = 4;
  ++*((_QWORD *)&v74 + 1);
  v10 = *(_QWORD **)(v8 + 8);
  *v9 = v8;
  v9[1] = v10;
  *(_QWORD *)(v8 + 8) = v9;
  *v10 = v9;
  if ( *((_QWORD *)&v74 + 1) == 0xAAAAAAAAAAAAAAALL )
    goto LABEL_71;
  *(_QWORD *)&v52 = &v74;
  *((_QWORD *)&v52 + 1) = 0;
  v11 = v74;
  v12 = std::_Allocate<16,std::_Default_allocate_traits>(0x18u);
  *((_DWORD *)v12 + 4) = 3;
  ++*((_QWORD *)&v74 + 1);
  v13 = *(_QWORD **)(v11 + 8);
  *v12 = v11;
  v12[1] = v13;
  *(_QWORD *)(v11 + 8) = v12;
  *v13 = v12;
  if ( *((_QWORD *)&v74 + 1) == 0xAAAAAAAAAAAAAAALL )
LABEL_71:
    std::_Xlength_error("list too long");
  *(_QWORD *)&v52 = &v74;
  *((_QWORD *)&v52 + 1) = 0;
  v14 = v74;
  v15 = std::_Allocate<16,std::_Default_allocate_traits>(0x18u);
  *((_DWORD *)v15 + 4) = 5;
  ++*((_QWORD *)&v74 + 1);
  v16 = *(_QWORD **)(v14 + 8);
  *v15 = v14;
  v15[1] = v16;
  *(_QWORD *)(v14 + 8) = v15;
  *v16 = v15;
  v17 = (__int64 *)std::enable_shared_from_this<LocationSignalManager>::shared_from_this((char *)this + 48, v53);
  v52 = 0;
  v18 = (volatile signed __int32 *)v17[1];
  if ( v18 )
  {
    v19 = *v17;
    *(_QWORD *)&v52 = *v17;
    *((_QWORD *)&v52 + 1) = v18;
    _InterlockedAdd(v18 + 3, 1u);
  }
  else
  {
    v18 = (volatile signed __int32 *)*((_QWORD *)&v52 + 1);
    v19 = v52;
  }
  if ( v54 )
    std::_Ref_count_base::_Decref(v54);
  v57 = off_180160C10;
  v58 = this;
  v59 = &v57;
  v51 = 0;
  if ( v18 )
  {
    *(_QWORD *)&v51 = v19;
    *((_QWORD *)&v51 + 1) = v18;
    _InterlockedAdd(v18 + 3, 1u);
  }
  ILocationSingletonComponent::CreateWeakCallback(v72, &v51, &v57);
  if ( !(unsigned __int8)LocationSignalManager::Finalize_::_1_::_lambda_2_::operator()() )
  {
    v20 = *((_QWORD *)this + 110);
    v50 = (__int64 (__fastcall ***)())v60;
    v61 = 0;
    if ( v73 )
      v61 = (**(__int64 (__fastcall ***)(_BYTE *, _BYTE *))v73)(v73, v60);
    v21 = SignalManager::RegisterForSignals(v20, &v74, v60);
    if ( v21 < 0 )
    {
      LODWORD(v48) = v21;
      wil::details::in1diag5::_Log_Hr(
        retaddr,
        (void *)0x85,
        (unsigned int)"onecoreuap\\drivers\\mobilepc\\location\\product\\core\\framework\\locationsignalmanager.cpp",
        "LocationSignalManager::Finalize",
        "m_legacySignalManager->RegisterForSignals(monitoredSignals, signalFn, 5 * 1000)",
        v48,
        v49);
    }
    v50 = &v57;
    v57 = off_1801600C0;
    v58 = this;
    v59 = &v57;
    v22 = std::enable_shared_from_this<LocationSignalManager>::shared_from_this((char *)this + 48, v55);
    v23 = std::weak_ptr<SignalValue<bool>::SignalState>::weak_ptr<SignalValue<bool>::SignalState>(v53, v22);
    ILocationSingletonComponent::CreateWeakWnfCallback(v70, v23, &v57);
    if ( v56 )
      std::_Ref_count_base::_Decref(v56);
    LOBYTE(v49) = GetFindMyDeviceEnabled();
    SignalValue<bool>::SetValue((char *)this + 680, &v49);
    *(_QWORD *)&v51 = v60;
    v61 = 0;
    if ( v71 )
      v61 = (**(__int64 (__fastcall ***)(_BYTE *, _BYTE *))v71)(v71, v60);
    v50 = (__int64 (__fastcall ***)())WNF_GPOL_SYSTEM_CHANGES;
    v24 = LocationWnfSubscribe_Impl::SubscribeToWnfState((char *)this + 896, &v50, v60);
    if ( v24 < 0 )
    {
      LODWORD(v48) = v24;
      wil::details::in1diag5::_Log_Hr(
        retaddr,
        (void *)0x8C,
        (unsigned int)"onecoreuap\\drivers\\mobilepc\\location\\product\\core\\framework\\locationsignalmanager.cpp",
        "LocationSignalManager::Finalize",
        "m_fmdEnabledMdmWnf.SubscribeToWnfState(LocWnfCommon::ActualStateNameToLoc(WNF_GPOL_SYSTEM_CHANGES), fmdCheckFn)",
        v48,
        v49);
    }
    *(_QWORD *)&v51 = v60;
    v61 = 0;
    if ( v71 )
      v61 = (**(__int64 (__fastcall ***)(_BYTE *, _BYTE *))v71)(v71, v60);
    v50 = (__int64 (__fastcall ***)())WNF_SHEL_SETTINGS_CHANGED;
    v25 = LocationWnfSubscribe_Impl::SubscribeToWnfState((char *)this + 944, &v50, v60);
    if ( v25 < 0 )
    {
      LODWORD(v48) = v25;
      wil::details::in1diag5::_Log_Hr(
        retaddr,
        (void *)0x8E,
        (unsigned int)"onecoreuap\\drivers\\mobilepc\\location\\product\\core\\framework\\locationsignalmanager.cpp",
        "LocationSignalManager::Finalize",
        "m_fmdEnabledWindowsSettingsWnf.SubscribeToWnfState( LocWnfCommon::ActualStateNameToLoc(WNF_SHEL_SETTINGS_CHANGED), fmdCheckFn)",
        v48,
        v49);
    }
    *(_QWORD *)&v51 = &v57;
    v57 = off_1801600F0;
    v58 = this;
    v59 = &v57;
    v26 = std::enable_shared_from_this<LocationSignalManager>::shared_from_this((char *)this + 48, v53);
    v27 = std::weak_ptr<SignalValue<bool>::SignalState>::weak_ptr<SignalValue<bool>::SignalState>(v55, v26);
    ILocationSingletonComponent::CreateWeakWnfCallback(v68, v27, &v57);
    if ( v54 )
      std::_Ref_count_base::_Decref(v54);
    *(_QWORD *)&v51 = v60;
    v61 = 0;
    if ( v69 )
      v61 = (**(__int64 (__fastcall ***)(_BYTE *, _BYTE *))v69)(v69, v60);
    v50 = (__int64 (__fastcall ***)())WNF_CNET_NON_CELLULAR_CONNECTED;
    v28 = LocationWnfSubscribe_Impl::SubscribeToWnfState((char *)this + 1040, &v50, v60);
    if ( v28 < 0 )
    {
      LODWORD(v48) = v28;
      wil::details::in1diag5::_Log_Hr(
        retaddr,
        (void *)0xA1,
        (unsigned int)"onecoreuap\\drivers\\mobilepc\\location\\product\\core\\framework\\locationsignalmanager.cpp",
        "LocationSignalManager::Finalize",
        "m_nonCellularConnectedWnf.SubscribeToWnfState( LocWnfCommon::ActualStateNameToLoc(WNF_CNET_NON_CELLULAR_CONNECTE"
        "D), nonCellularConnectedFn)",
        v48,
        v49);
    }
    v75 = 0;
    if ( (int)IsTimeZoneAutoUpdateEnabled(&v75) >= 0 )
    {
      LOBYTE(v49) = v75 != 0;
      SignalValue<bool>::SetValue((char *)this + 800, &v49);
    }
    *(_QWORD *)&v51 = &v57;
    v57 = off_180160120;
    v58 = this;
    v59 = &v57;
    v29 = std::enable_shared_from_this<LocationSignalManager>::shared_from_this((char *)this + 48, v53);
    v30 = std::weak_ptr<SignalValue<bool>::SignalState>::weak_ptr<SignalValue<bool>::SignalState>(v55, v29);
    ILocationSingletonComponent::CreateWeakWnfCallback(v66, v30, &v57);
    if ( v54 )
      std::_Ref_count_base::_Decref(v54);
    *(_QWORD *)&v51 = v60;
    v61 = 0;
    if ( v67 )
      v61 = (**(__int64 (__fastcall ***)(_BYTE *, _BYTE *))v67)(v67, v60);
    v50 = (__int64 (__fastcall ***)())WNF_SRC_SYSTEM_RADIO_CHANGED;
    v31 = LocationWnfSubscribe_Impl::SubscribeToWnfState((char *)this + 1088, &v50, v60);
    if ( v31 < 0 )
    {
      LODWORD(v48) = v31;
      wil::details::in1diag5::_Log_Hr(
        retaddr,
        (void *)0xB9,
        (unsigned int)"onecoreuap\\drivers\\mobilepc\\location\\product\\core\\framework\\locationsignalmanager.cpp",
        "LocationSignalManager::Finalize",
        "m_airplaneModeWnf.SubscribeToWnfState(LocWnfCommon::ActualStateNameToLoc(WNF_SRC_SYSTEM_RADIO_CHANGED), airplaneModeFn)",
        v48,
        v49);
    }
    *(_QWORD *)&v51 = &v57;
    v57 = off_180160F80;
    v58 = this;
    v59 = &v57;
    v32 = std::enable_shared_from_this<LocationSignalManager>::shared_from_this((char *)this + 48, v53);
    v33 = std::weak_ptr<SignalValue<bool>::SignalState>::weak_ptr<SignalValue<bool>::SignalState>(v55, v32);
    ILocationSingletonComponent::CreateWeakWnfCallback(v64, v33, &v57);
    if ( v54 )
      std::_Ref_count_base::_Decref(v54);
    *(_QWORD *)&v51 = v60;
    v61 = 0;
    if ( v65 )
      v61 = (**(__int64 (__fastcall ***)(_BYTE *, _BYTE *))v65)(v65, v60);
    v50 = (__int64 (__fastcall ***)())WNF_PO_SCENARIO_CHANGE;
    v34 = LocationWnfSubscribe_Impl::SubscribeToWnfState((char *)this + 1136, &v50, v60);
    if ( v34 < 0 )
    {
      LODWORD(v48) = v34;
      wil::details::in1diag5::_Log_Hr(
        retaddr,
        (void *)0xD1,
        (unsigned int)"onecoreuap\\drivers\\mobilepc\\location\\product\\core\\framework\\locationsignalmanager.cpp",
        "LocationSignalManager::Finalize",
        "m_modernStandbyActiveWnf.SubscribeToWnfState( LocWnfCommon::ActualStateNameToLoc(WNF_PO_SCENARIO_CHANGE), modernStandbyFn)",
        v48,
        v49);
    }
    *(_QWORD *)&v51 = &v57;
    v57 = off_180161B18;
    v58 = this;
    v59 = &v57;
    v35 = std::enable_shared_from_this<LocationSignalManager>::shared_from_this((char *)this + 48, v53);
    v36 = std::weak_ptr<SignalValue<bool>::SignalState>::weak_ptr<SignalValue<bool>::SignalState>(v55, v35);
    ILocationSingletonComponent::CreateWeakWnfCallback(v62, v36, &v57);
    if ( v54 )
      std::_Ref_count_base::_Decref(v54);
    *(_QWORD *)&v51 = v60;
    v61 = 0;
    if ( v63 )
      v61 = (**(__int64 (__fastcall ***)(_BYTE *, _BYTE *))v63)(v63, v60);
    v50 = (__int64 (__fastcall ***)())WNF_SEB_NETWORK_CONNECTIVITY_IN_STANDBY;
    v37 = LocationWnfSubscribe_Impl::SubscribeToWnfState((char *)this + 1184, &v50, v60);
    if ( v37 < 0 )
    {
      LODWORD(v48) = v37;
      wil::details::in1diag5::_Log_Hr(
        retaddr,
        (void *)0xE9,
        (unsigned int)"onecoreuap\\drivers\\mobilepc\\location\\product\\core\\framework\\locationsignalmanager.cpp",
        "LocationSignalManager::Finalize",
        "m_networkConnectedInStandbyWnf.SubscribeToWnfState( LocWnfCommon::ActualStateNameToLoc(WNF_SEB_NETWORK_CONNECTIV"
        "ITY_IN_STANDBY), networkConnectedInStandbyFn)",
        v48,
        v49);
    }
    if ( v63 )
    {
      v38 = v62;
      LOBYTE(v38) = v63 != v62;
      (*(void (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v63 + 32LL))(v63, v38);
      v63 = 0;
    }
    if ( v65 )
    {
      v39 = v64;
      LOBYTE(v39) = v65 != v64;
      (*(void (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v65 + 32LL))(v65, v39);
      v65 = 0;
    }
    if ( v67 )
    {
      v40 = v66;
      LOBYTE(v40) = v67 != v66;
      (*(void (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v67 + 32LL))(v67, v40);
      v67 = 0;
    }
    if ( v69 )
    {
      v41 = v68;
      LOBYTE(v41) = v69 != v68;
      (*(void (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v69 + 32LL))(v69, v41);
      v69 = 0;
    }
    if ( v71 )
    {
      v42 = v70;
      LOBYTE(v42) = v71 != v70;
      (*(void (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v71 + 32LL))(v71, v42);
    }
  }
  if ( v73 )
  {
    v43 = v72;
    LOBYTE(v43) = v73 != v72;
    (*(void (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v73 + 32LL))(v73, v43);
    v73 = 0;
  }
  if ( v18 )
    std::_Ref_count_base::_Decwref((std::_Ref_count_base *)v18);
  v44 = (_QWORD **)v74;
  **(_QWORD **)(v74 + 8) = 0;
  v45 = *v44;
  if ( v45 )
  {
    do
    {
      v46 = (_QWORD *)*v45;
      std::_Deallocate<16>(v45, 0x18u);
      v45 = v46;
    }
    while ( v46 );
  }
  std::_Deallocate<16>((void *)v74, 0x18u);
  return 0;
}

```

## disassembly

```asm
0x18003aa00  push    rbp
0x18003aa02  push    rbx
0x18003aa03  push    rsi
0x18003aa04  push    rdi
0x18003aa05  push    r12
0x18003aa07  push    r13
0x18003aa09  push    r14
0x18003aa0b  push    r15
0x18003aa0d  lea     rbp, [rsp-1A8h]
0x18003aa15  sub     rsp, 2A8h
0x18003aa1c  mov     rax, cs:__security_cookie
0x18003aa23  xor     rax, rsp
0x18003aa26  mov     [rbp+1E0h+var_48], rax
0x18003aa2d  mov     rdi, rcx
0x18003aa30  xor     r15d, r15d
0x18003aa33  xorps   xmm1, xmm1
0x18003aa36  movdqu  [rbp+1E0h+var_60], xmm1
0x18003aa3e  lea     rcx, [rbp+1E0h+var_60]
0x18003aa45  call    ?_Alloc_sentinel_and_proxy@?$list@V?$CAdapt@V?$CComPtr@UILocationAcquire@@@ATL@@@ATL@@V?$allocator@V?$CAdapt@V?$CComPtr@UILocationAcquire@@@ATL@@@ATL@@@std@@@std@@AEAAXXZ; std::list<ATL::CAdapt<ATL::CComPtr<ILocationAcquire>>>::_Alloc_sentinel_and_proxy(void)
0x18003aa4a  nop
0x18003aa4b  mov     rsi, 0AAAAAAAAAAAAAAAh
0x18003aa55  cmp     qword ptr [rbp+1E0h+var_60+8], rsi
0x18003aa5c  jz      loc_18003B34B
0x18003aa62  lea     rax, [rbp+1E0h+var_60]
0x18003aa69  mov     qword ptr [rsp+2E0h+var_290], rax
0x18003aa6e  mov     qword ptr [rsp+2E0h+var_290+8], r15
0x18003aa73  mov     rbx, qword ptr [rbp+1E0h+var_60]
0x18003aa7a  lea     r13d, [r15+18h]
0x18003aa7e  mov     ecx, r13d
0x18003aa81  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x18003aa86  mov     dword ptr [rax+10h], 2
0x18003aa8d  lea     r12d, [r15+1]
0x18003aa91  add     qword ptr [rbp+1E0h+var_60+8], r12
0x18003aa98  mov     rcx, [rbx+8]
0x18003aa9c  mov     [rax], rbx
0x18003aa9f  mov     [rax+8], rcx
0x18003aaa3  mov     [rbx+8], rax
0x18003aaa7  mov     [rcx], rax
0x18003aaaa  cmp     qword ptr [rbp+1E0h+var_60+8], rsi
0x18003aab1  jz      loc_18003B34B
0x18003aab7  lea     rax, [rbp+1E0h+var_60]
0x18003aabe  mov     qword ptr [rsp+2E0h+var_290], rax
0x18003aac3  mov     qword ptr [rsp+2E0h+var_290+8], r15
0x18003aac8  mov     rbx, qword ptr [rbp+1E0h+var_60]
0x18003aacf  mov     ecx, r13d
0x18003aad2  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x18003aad7  mov     [rax+10h], r12d
0x18003aadb  add     qword ptr [rbp+1E0h+var_60+8], r12
0x18003aae2  mov     rcx, [rbx+8]
0x18003aae6  mov     [rax], rbx
0x18003aae9  mov     [rax+8], rcx
0x18003aaed  mov     [rbx+8], rax
0x18003aaf1  mov     [rcx], rax
0x18003aaf4  cmp     qword ptr [rbp+1E0h+var_60+8], rsi
0x18003aafb  jz      loc_18003B34B
0x18003ab01  lea     rax, [rbp+1E0h+var_60]
0x18003ab08  mov     qword ptr [rsp+2E0h+var_290], rax
0x18003ab0d  mov     qword ptr [rsp+2E0h+var_290+8], r15
0x18003ab12  mov     rbx, qword ptr [rbp+1E0h+var_60]
0x18003ab19  mov     ecx, r13d
0x18003ab1c  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x18003ab21  mov     dword ptr [rax+10h], 4
0x18003ab28  add     qword ptr [rbp+1E0h+var_60+8], r12
0x18003ab2f  mov     rcx, [rbx+8]
0x18003ab33  mov     [rax], rbx
0x18003ab36  mov     [rax+8], rcx
0x18003ab3a  mov     [rbx+8], rax
0x18003ab3e  mov     [rcx], rax
0x18003ab41  cmp     qword ptr [rbp+1E0h+var_60+8], rsi
0x18003ab48  jz      loc_18003B34B
0x18003ab4e  lea     rax, [rbp+1E0h+var_60]
0x18003ab55  mov     qword ptr [rsp+2E0h+var_290], rax
0x18003ab5a  mov     qword ptr [rsp+2E0h+var_290+8], r15
0x18003ab5f  mov     rbx, qword ptr [rbp+1E0h+var_60]
0x18003ab66  mov     ecx, r13d
0x18003ab69  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x18003ab6e  mov     dword ptr [rax+10h], 3
0x18003ab75  add     qword ptr [rbp+1E0h+var_60+8], r12
0x18003ab7c  mov     rcx, [rbx+8]
0x18003ab80  mov     [rax], rbx
0x18003ab83  mov     [rax+8], rcx
0x18003ab87  mov     [rbx+8], rax
0x18003ab8b  mov     [rcx], rax
0x18003ab8e  cmp     qword ptr [rbp+1E0h+var_60+8], rsi
0x18003ab95  jz      loc_18003B34B
0x18003ab9b  lea     rax, [rbp+1E0h+var_60]
0x18003aba2  mov     qword ptr [rsp+2E0h+var_290], rax
0x18003aba7  mov     qword ptr [rsp+2E0h+var_290+8], r15
0x18003abac  mov     rbx, qword ptr [rbp+1E0h+var_60]
0x18003abb3  mov     ecx, r13d
0x18003abb6  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x18003abbb  mov     dword ptr [rax+10h], 5
0x18003abc2  add     qword ptr [rbp+1E0h+var_60+8], r12
0x18003abc9  mov     rcx, [rbx+8]
0x18003abcd  mov     [rax], rbx
0x18003abd0  mov     [rax+8], rcx
0x18003abd4  mov     [rbx+8], rax
0x18003abd8  mov     [rcx], rax
0x18003abdb  lea     r14, [rdi+30h]
0x18003abdf  lea     rdx, [rsp+2E0h+var_280]
0x18003abe4  mov     rcx, r14
0x18003abe7  call    ?shared_from_this@?$enable_shared_from_this@VLocationSignalManager@@@std@@QEAA?AV?$shared_ptr@VLocationSignalManager@@@2@XZ; std::enable_shared_from_this<LocationSignalManager>::shared_from_this(void)
0x18003abec  xorps   xmm0, xmm0
0x18003abef  movdqu  [rsp+2E0h+var_290], xmm0
0x18003abf5  mov     rbx, [rax+8]
0x18003abf9  test    rbx, rbx
0x18003abfc  jz      short loc_18003AC12
0x18003abfe  mov     rsi, [rax]
0x18003ac01  mov     qword ptr [rsp+2E0h+var_290], rsi
0x18003ac06  mov     qword ptr [rsp+2E0h+var_290+8], rbx
0x18003ac0b  lock add [rbx+0Ch], r12d
0x18003ac10  jmp     short loc_18003AC1C
0x18003ac12  mov     rbx, qword ptr [rsp+2E0h+var_290+8]
0x18003ac17  mov     rsi, qword ptr [rsp+2E0h+var_290]
0x18003ac1c  mov     rcx, [rsp+2E0h+var_278]; this
0x18003ac21  test    rcx, rcx
0x18003ac24  jz      short loc_18003AC2B
0x18003ac26  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18003ac2b  lea     rax, off_180160C10
0x18003ac32  mov     [rbp+1E0h+var_260], rax
0x18003ac36  mov     [rbp+1E0h+var_258], rdi
0x18003ac3a  lea     rax, [rbp+1E0h+var_260]
0x18003ac3e  mov     [rbp+1E0h+var_228], rax
0x18003ac42  xorps   xmm0, xmm0
0x18003ac45  movdqu  [rsp+2E0h+var_2A0], xmm0
0x18003ac4b  test    rbx, rbx
0x18003ac4e  jz      short loc_18003AC5F
0x18003ac50  mov     qword ptr [rsp+2E0h+var_2A0], rsi
0x18003ac55  mov     qword ptr [rsp+2E0h+var_2A0+8], rbx
0x18003ac5a  lock add [rbx+0Ch], r12d
0x18003ac5f  lea     r8, [rbp+1E0h+var_260]
0x18003ac63  lea     rdx, [rsp+2E0h+var_2A0]
0x18003ac68  lea     rcx, [rbp+1E0h+var_A0]
0x18003ac6f  call    ?CreateWeakCallback@ILocationSingletonComponent@@SA?AV?$function@$$A6AJXZ@std@@V?$weak_ptr@VILocationSingletonComponent@@@3@V23@@Z; ILocationSingletonComponent::CreateWeakCallback(std::weak_ptr<ILocationSingletonComponent>,std::function<long (void)>)
0x18003ac74  nop
0x18003ac75  call    _LocationSignalManager__Finalize____1____lambda_2___operator__
0x18003ac7a  test    al, al
0x18003ac7c  jnz     loc_18003B2B4
0x18003ac82  mov     rsi, [rdi+370h]
0x18003ac89  lea     rax, [rbp+1E0h+var_220]
0x18003ac8d  mov     [rsp+2E0h+var_2A8], rax
0x18003ac92  mov     [rbp+1E0h+var_1E8], r15
0x18003ac96  mov     rcx, [rbp+1E0h+var_68]
0x18003ac9d  test    rcx, rcx
0x18003aca0  jz      short loc_18003ACB5
0x18003aca2  mov     rax, [rcx]
0x18003aca5  lea     rdx, [rbp+1E0h+var_220]
0x18003aca9  mov     rax, [rax]
0x18003acac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003acb1  mov     [rbp+1E0h+var_1E8], rax
0x18003acb5  lea     r8, [rbp+1E0h+var_220]
0x18003acb9  lea     rdx, [rbp+1E0h+var_60]
0x18003acc0  mov     rcx, rsi
0x18003acc3  call    ?RegisterForSignals@SignalManager@@QEAAJAEBV?$list@W4SignalType@@V?$allocator@W4SignalType@@@std@@@std@@V?$function@$$A6AJXZ@3@K@Z; SignalManager::RegisterForSignals(std::list<SignalType> const &,std::function<long (void)>,ulong)
0x18003acc8  mov     rcx, [rbp+1E8h]; this
0x18003accf  lea     rsi, aLocationsignal_3; "LocationSignalManager::Finalize"
0x18003acd6  lea     r12, aOnecoreuapDriv_1; "onecoreuap\\drivers\\mobilepc\\location"...
0x18003acdd  test    eax, eax
0x18003acdf  jns     short loc_18003AD01
0x18003ace1  mov     dword ptr [rsp+2E0h+var_2B8], eax; char *
0x18003ace5  lea     rax, aMLegacysignalm; "m_legacySignalManager->RegisterForSigna"...
0x18003acec  mov     [rsp+2E0h+var_2C0], rax; char *
0x18003acf1  mov     r9, rsi; char *
0x18003acf4  mov     r8, r12; unsigned int
0x18003acf7  mov     edx, 85h; void *
0x18003acfc  call    ?_Log_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::_Log_Hr(void *,uint,char const *,char const *,char const *,long)
0x18003ad01  lea     rax, [rbp+1E0h+var_260]
0x18003ad05  mov     [rsp+2E0h+var_2A8], rax
0x18003ad0a  lea     rax, off_1801600C0
0x18003ad11  mov     [rbp+1E0h+var_260], rax
0x18003ad15  mov     [rbp+1E0h+var_258], rdi
0x18003ad19  lea     rax, [rbp+1E0h+var_260]
0x18003ad1d  mov     [rbp+1E0h+var_228], rax
0x18003ad21  lea     rdx, [rsp+2E0h+var_270]
0x18003ad26  mov     rcx, r14
0x18003ad29  call    ?shared_from_this@?$enable_shared_from_this@VLocationSignalManager@@@std@@QEAA?AV?$shared_ptr@VLocationSignalManager@@@2@XZ; std::enable_shared_from_this<LocationSignalManager>::shared_from_this(void)
0x18003ad2e  nop
0x18003ad2f  mov     rdx, rax
0x18003ad32  lea     rcx, [rsp+2E0h+var_280]
0x18003ad37  call    ??0?$weak_ptr@USignalState@?$SignalValue@_N@@@std@@QEAA@AEBV01@@Z; std::weak_ptr<SignalValue<bool>::SignalState>::weak_ptr<SignalValue<bool>::SignalState>(std::weak_ptr<SignalValue<bool>::SignalState> const &)
0x18003ad3c  nop
0x18003ad3d  lea     r8, [rbp+1E0h+var_260]
0x18003ad41  mov     rdx, rax
0x18003ad44  lea     rcx, [rbp+1E0h+var_E0]
0x18003ad4b  call    ?CreateWeakWnfCallback@ILocationSingletonComponent@@SA?AV?$function@$$A6AXPEBXK@Z@std@@V?$weak_ptr@VILocationSingletonComponent@@@3@V23@@Z; ILocationSingletonComponent::CreateWeakWnfCallback(std::weak_ptr<ILocationSingletonComponent>,std::function<void (void const *,ulong)>)
0x18003ad50  nop
0x18003ad51  mov     rcx, [rsp+2E0h+var_268]; this
0x18003ad56  test    rcx, rcx
0x18003ad59  jz      short loc_18003AD60
0x18003ad5b  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18003ad60  call    GetFindMyDeviceEnabled
0x18003ad65  mov     byte ptr [rsp+2E0h+var_2B0], al; int
0x18003ad69  lea     rcx, [rdi+2A8h]
0x18003ad70  lea     rdx, [rsp+2E0h+var_2B0]
0x18003ad75  call    ?SetValue@?$SignalValue@_N@@QEAAXAEB_N@Z; SignalValue<bool>::SetValue(bool const &)
0x18003ad7a  lea     rax, [rbp+1E0h+var_220]
0x18003ad7e  mov     qword ptr [rsp+2E0h+var_2A0], rax
0x18003ad83  mov     [rbp+1E0h+var_1E8], r15
0x18003ad87  mov     rcx, [rbp+1E0h+var_A8]
0x18003ad8e  test    rcx, rcx
0x18003ad91  jz      short loc_18003ADA6
0x18003ad93  mov     rax, [rcx]
0x18003ad96  lea     rdx, [rbp+1E0h+var_220]
0x18003ad9a  mov     rax, [rax]
0x18003ad9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ada2  mov     [rbp+1E0h+var_1E8], rax
0x18003ada6  mov     rax, cs:WNF_GPOL_SYSTEM_CHANGES
0x18003adad  mov     [rsp+2E0h+var_2A8], rax
0x18003adb2  lea     rcx, [rdi+380h]
0x18003adb9  lea     r8, [rbp+1E0h+var_220]
0x18003adbd  lea     rdx, [rsp+2E0h+var_2A8]
0x18003adc2  call    ?SubscribeToWnfState@LocationWnfSubscribe_Impl@@QEAAJAEBULOC_WNF_STATE_NAME@@V?$function@$$A6AXPEBXK@Z@std@@@Z; LocationWnfSubscribe_Impl::SubscribeToWnfState(LOC_WNF_STATE_NAME const &,std::function<void (void const *,ulong)>)
0x18003adc7  mov     rcx, [rbp+1E8h]; this
0x18003adce  test    eax, eax
0x18003add0  jns     short loc_18003ADF2
0x18003add2  mov     dword ptr [rsp+2E0h+var_2B8], eax; char *
0x18003add6  lea     rax, aMFmdenabledmdm; "m_fmdEnabledMdmWnf.SubscribeToWnfState("...
0x18003addd  mov     [rsp+2E0h+var_2C0], rax; char *
0x18003ade2  mov     r9, rsi; char *
0x18003ade5  mov     r8, r12; unsigned int
0x18003ade8  mov     edx, 8Ch; void *
0x18003aded  call    ?_Log_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::_Log_Hr(void *,uint,char const *,char const *,char const *,long)
0x18003adf2  lea     rax, [rbp+1E0h+var_220]
0x18003adf6  mov     qword ptr [rsp+2E0h+var_2A0], rax
0x18003adfb  mov     [rbp+1E0h+var_1E8], r15
0x18003adff  mov     rcx, [rbp+1E0h+var_A8]
0x18003ae06  test    rcx, rcx
0x18003ae09  jz      short loc_18003AE1E
0x18003ae0b  mov     rax, [rcx]
0x18003ae0e  lea     rdx, [rbp+1E0h+var_220]
0x18003ae12  mov     rax, [rax]
0x18003ae15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ae1a  mov     [rbp+1E0h+var_1E8], rax
0x18003ae1e  mov     rax, cs:WNF_SHEL_SETTINGS_CHANGED
0x18003ae25  mov     [rsp+2E0h+var_2A8], rax
0x18003ae2a  lea     rcx, [rdi+3B0h]
0x18003ae31  lea     r8, [rbp+1E0h+var_220]
0x18003ae35  lea     rdx, [rsp+2E0h+var_2A8]
0x18003ae3a  call    ?SubscribeToWnfState@LocationWnfSubscribe_Impl@@QEAAJAEBULOC_WNF_STATE_NAME@@V?$function@$$A6AXPEBXK@Z@std@@@Z; LocationWnfSubscribe_Impl::SubscribeToWnfState(LOC_WNF_STATE_NAME const &,std::function<void (void const *,ulong)>)
0x18003ae3f  mov     rcx, [rbp+1E8h]; this
0x18003ae46  test    eax, eax
0x18003ae48  jns     short loc_18003AE6A
0x18003ae4a  mov     dword ptr [rsp+2E0h+var_2B8], eax; char *
0x18003ae4e  lea     rax, aMFmdenabledwin; "m_fmdEnabledWindowsSettingsWnf.Subscrib"...
0x18003ae55  mov     [rsp+2E0h+var_2C0], rax; char *
0x18003ae5a  mov     r9, rsi; char *
0x18003ae5d  mov     r8, r12; unsigned int
0x18003ae60  mov     edx, 8Eh; void *
0x18003ae65  call    ?_Log_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::_Log_Hr(void *,uint,char const *,char const *,char const *,long)
0x18003ae6a  lea     rax, [rbp+1E0h+var_260]
0x18003ae6e  mov     qword ptr [rsp+2E0h+var_2A0], rax
0x18003ae73  lea     rax, off_1801600F0
0x18003ae7a  mov     [rbp+1E0h+var_260], rax
0x18003ae7e  mov     [rbp+1E0h+var_258], rdi
0x18003ae82  lea     rax, [rbp+1E0h+var_260]
0x18003ae86  mov     [rbp+1E0h+var_228], rax
0x18003ae8a  lea     rdx, [rsp+2E0h+var_280]
0x18003ae8f  mov     rcx, r14
0x18003ae92  call    ?shared_from_this@?$enable_shared_from_this@VLocationSignalManager@@@std@@QEAA?AV?$shared_ptr@VLocationSignalManager@@@2@XZ; std::enable_shared_from_this<LocationSignalManager>::shared_from_this(void)
0x18003ae97  nop
0x18003ae98  mov     rdx, rax
0x18003ae9b  lea     rcx, [rsp+2E0h+var_270]
0x18003aea0  call    ??0?$weak_ptr@USignalState@?$SignalValue@_N@@@std@@QEAA@AEBV01@@Z; std::weak_ptr<SignalValue<bool>::SignalState>::weak_ptr<SignalValue<bool>::SignalState>(std::weak_ptr<SignalValue<bool>::SignalState> const &)
0x18003aea5  nop
0x18003aea6  lea     r8, [rbp+1E0h+var_260]
0x18003aeaa  mov     rdx, rax
0x18003aead  lea     rcx, [rbp+1E0h+var_120]
0x18003aeb4  call    ?CreateWeakWnfCallback@ILocationSingletonComponent@@SA?AV?$function@$$A6AXPEBXK@Z@std@@V?$weak_ptr@VILocationSingletonComponent@@@3@V23@@Z; ILocationSingletonComponent::CreateWeakWnfCallback(std::weak_ptr<ILocationSingletonComponent>,std::function<void (void const *,ulong)>)
0x18003aeb9  nop
0x18003aeba  mov     rcx, [rsp+2E0h+var_278]; this
0x18003aebf  test    rcx, rcx
0x18003aec2  jz      short loc_18003AEC9
0x18003aec4  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18003aec9  lea     rax, [rbp+1E0h+var_220]
0x18003aecd  mov     qword ptr [rsp+2E0h+var_2A0], rax
0x18003aed2  mov     [rbp+1E0h+var_1E8], r15
0x18003aed6  mov     rcx, [rbp+1E0h+var_E8]
0x18003aedd  test    rcx, rcx
0x18003aee0  jz      short loc_18003AEF5
0x18003aee2  mov     rax, [rcx]
0x18003aee5  lea     rdx, [rbp+1E0h+var_220]
0x18003aee9  mov     rax, [rax]
0x18003aeec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003aef1  mov     [rbp+1E0h+var_1E8], rax
0x18003aef5  mov     rax, cs:WNF_CNET_NON_CELLULAR_CONNECTED
0x18003aefc  mov     [rsp+2E0h+var_2A8], rax
0x18003af01  lea     rcx, [rdi+410h]
0x18003af08  lea     r8, [rbp+1E0h+var_220]
0x18003af0c  lea     rdx, [rsp+2E0h+var_2A8]
0x18003af11  call    ?SubscribeToWnfState@LocationWnfSubscribe_Impl@@QEAAJAEBULOC_WNF_STATE_NAME@@V?$function@$$A6AXPEBXK@Z@std@@@Z; LocationWnfSubscribe_Impl::SubscribeToWnfState(LOC_WNF_STATE_NAME const &,std::function<void (void const *,ulong)>)
0x18003af16  mov     rcx, [rbp+1E8h]; this
0x18003af1d  test    eax, eax
0x18003af1f  jns     short loc_18003AF41
0x18003af21  mov     dword ptr [rsp+2E0h+var_2B8], eax; char *
0x18003af25  lea     rax, aMNoncellularco; "m_nonCellularConnectedWnf.SubscribeToWn"...
0x18003af2c  mov     [rsp+2E0h+var_2C0], rax; char *
0x18003af31  mov     r9, rsi; char *
0x18003af34  mov     r8, r12; unsigned int
0x18003af37  mov     edx, 0A1h; void *
0x18003af3c  call    ?_Log_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::_Log_Hr(void *,uint,char const *,char const *,char const *,long)
  ... truncated ...
```
