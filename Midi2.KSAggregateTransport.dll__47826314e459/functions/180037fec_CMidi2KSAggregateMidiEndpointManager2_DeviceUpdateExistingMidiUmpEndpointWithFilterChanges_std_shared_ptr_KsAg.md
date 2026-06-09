# CMidi2KSAggregateMidiEndpointManager2::DeviceUpdateExistingMidiUmpEndpointWithFilterChanges(std::shared_ptr<KsAggregateEndpointDefinition2>)

- ea: `0x180037fec`
- end: `0x180038d28`
- name: `?DeviceUpdateExistingMidiUmpEndpointWithFilterChanges@CMidi2KSAggregateMidiEndpointManager2@@AEAAJV?$shared_ptr@UKsAggregateEndpointDefinition2@@@std@@@Z`
- size: `3388`
- prototype: ``
- caller_count: `2`
- callee_count: `28`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18003c890`
- `0x18003dcf0`

## callees

- `0x1800017d0`
- `0x180001a94`
- `0x180002640`
- `0x180005020`
- `0x180005e9c`
- `0x18000b394`
- `0x18000d430`
- `0x18000d920`
- `0x18000e37c`
- `0x1800117d8`
- `0x180014194`
- `0x180019924`
- `0x18001ca4c`
- `0x180020b58`
- `0x1800224f8`
- `0x180022648`
- `0x180022f64`
- `0x180029298`
- `0x180029460`
- `0x18002dff8`
- `0x180035c78`
- `0x180037fec`
- `0x180039928`
- `0x18003fc04`
- `0x18004c470`
- `0x18004d024`
- `0x1800570d0`
- `0x18005e010`

## string_xrefs

- `0x1800387ad`: `Found custom properties cached for this endpoint`
- `0x180038848`: `No cached custom properties for this endpoint.`
- `0x1800381ba`: `CMidi2KSAggregateMidiEndpointManager2::DeviceUpdateExistingMidiUmpEndpointWithFilterChanges`
- `0x1800387c0`: `CMidi2KSAggregateMidiEndpointManager2::DeviceUpdateExistingMidiUmpEndpointWithFilterChanges`
- `0x180038818`: `CMidi2KSAggregateMidiEndpointManager2::DeviceUpdateExistingMidiUmpEndpointWithFilterChanges`
- `0x18003885b`: `CMidi2KSAggregateMidiEndpointManager2::DeviceUpdateExistingMidiUmpEndpointWithFilterChanges`
- `0x18003889f`: `CMidi2KSAggregateMidiEndpointManager2::DeviceUpdateExistingMidiUmpEndpointWithFilterChanges`
- `0x1800389eb`: `CMidi2KSAggregateMidiEndpointManager2::DeviceUpdateExistingMidiUmpEndpointWithFilterChanges`
- `0x180038ad7`: `CMidi2KSAggregateMidiEndpointManager2::DeviceUpdateExistingMidiUmpEndpointWithFilterChanges`
- `0x180038b64`: `CMidi2KSAggregateMidiEndpointManager2::DeviceUpdateExistingMidiUmpEndpointWithFilterChanges`
- `0x1800384ac`: `About to write group terminal blocks`
- `0x1800388df`: `About to update name table`
- `0x1800389d8`: `About to update endpoint properties in the MIDI Device Manager`
- `0x180038b51`: `Aggregate UMP endpoint updated with new filter`
- `0x180038ac4`: `Aggregate UMP endpoint update failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=19
__int64 __fastcall CMidi2KSAggregateMidiEndpointManager2::DeviceUpdateExistingMidiUmpEndpointWithFilterChanges(
        __int64 a1,
        _QWORD *a2)
{
  volatile signed __int32 *v4; // rdi
  __int64 v5; // rax
  int ExistingParentDeviceDefinitionForEndpoint; // eax
  unsigned int v7; // r15d
  volatile signed __int32 *v8; // rsi
  volatile signed __int32 *v9; // rdi
  _DWORD *v11; // rcx
  int v12; // r8d
  int v13; // r9d
  _QWORD *v14; // rax
  volatile signed __int32 *v15; // rsi
  volatile signed __int32 *v16; // rdi
  _DWORD *v17; // rcx
  int v18; // r8d
  int v19; // r9d
  _QWORD *v20; // rax
  __int64 v21; // rax
  int v22; // eax
  __int64 v23; // rdx
  _DWORD *v24; // rcx
  int v25; // r8d
  int v26; // r9d
  _QWORD *v27; // rax
  __int64 v28; // rdx
  _DWORD *v29; // rcx
  int v30; // r8d
  int v31; // r9d
  _QWORD *v32; // rax
  __int64 v33; // rax
  __int128 *v34; // rax
  __int64 v35; // r15
  __int64 v36; // rax
  volatile signed __int32 *v37; // rsi
  __int64 v38; // rsi
  unsigned int *v39; // rcx
  int v40; // r8d
  int v41; // r9d
  unsigned int v42; // eax
  _QWORD *v43; // rax
  _QWORD *v44; // rax
  _DWORD *v45; // rcx
  int v46; // r8d
  int v47; // r9d
  _QWORD *v48; // rax
  volatile signed __int32 *v49; // rsi
  __int64 v50; // rax
  int updated; // eax
  _DWORD *v52; // rcx
  int v53; // r8d
  int v54; // r9d
  _QWORD *v55; // rax
  _QWORD *v56; // rdx
  int v57; // eax
  _DWORD *v58; // r8
  int v59; // r9d
  _QWORD *v60; // rax
  _DWORD *v61; // rcx
  int v62; // r8d
  int v63; // r9d
  _QWORD *v64; // rax
  __int64 v65; // rax
  volatile signed __int32 *v66; // rsi
  volatile signed __int32 *v67; // rdi
  int v68; // [rsp+20h] [rbp-E0h]
  int v69[2]; // [rsp+50h] [rbp-B0h] BYREF
  int v70[2]; // [rsp+58h] [rbp-A8h] BYREF
  __int128 v71; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD *v72; // [rsp+70h] [rbp-90h] BYREF
  int v73[2]; // [rsp+78h] [rbp-88h] BYREF
  __int128 v74; // [rsp+80h] [rbp-80h] BYREF
  __int64 v75; // [rsp+90h] [rbp-70h]
  __int128 v76; // [rsp+98h] [rbp-68h] BYREF
  __int128 v77; // [rsp+A8h] [rbp-58h] BYREF
  __int128 v78; // [rsp+B8h] [rbp-48h]
  __int128 v79; // [rsp+C8h] [rbp-38h]
  __int128 v80; // [rsp+E0h] [rbp-20h] BYREF
  __int128 v81; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v82; // [rsp+100h] [rbp+0h]
  __int128 v83; // [rsp+108h] [rbp+8h] BYREF
  __int64 v84; // [rsp+118h] [rbp+18h]
  __int128 v85; // [rsp+120h] [rbp+20h] BYREF
  __int64 v86; // [rsp+130h] [rbp+30h]
  __int128 v87; // [rsp+140h] [rbp+40h] BYREF
  int v88; // [rsp+150h] [rbp+50h]
  __int64 v89; // [rsp+158h] [rbp+58h]
  __int128 v90; // [rsp+160h] [rbp+60h]
  __int64 v91; // [rsp+170h] [rbp+70h]
  __int16 v92; // [rsp+178h] [rbp+78h]
  __int128 v93; // [rsp+180h] [rbp+80h]
  __int128 v94; // [rsp+190h] [rbp+90h] BYREF
  __int64 v95; // [rsp+1A0h] [rbp+A0h]
  _QWORD *v96; // [rsp+1A8h] [rbp+A8h]
  __int128 v97; // [rsp+1B0h] [rbp+B0h] BYREF
  __int64 v98; // [rsp+1C0h] [rbp+C0h]
  unsigned __int64 v99; // [rsp+1C8h] [rbp+C8h]
  __int128 v100; // [rsp+1D0h] [rbp+D0h] BYREF
  __m128i si128; // [rsp+1E0h] [rbp+E0h]
  _OWORD v102[2]; // [rsp+1F0h] [rbp+F0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+248h] [rbp+148h]

  v96 = a2;
  if ( !*a2 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x279,
      (unsigned int)"avcore\\midi2\\transport\\ksaggregatetransport\\midi2.ksaggregatemidiendpointmanager2.cpp",
      (const char *)0x80070057LL,
      v68);
    v4 = (volatile signed __int32 *)a2[1];
    if ( v4 && _InterlockedExchangeAdd(v4 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v4)(v4);
      if ( _InterlockedExchangeAdd(v4 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v4 + 8LL))(v4);
    }
    return 2147942487LL;
  }
  v76 = 0;
  v71 = 0;
  v5 = a2[1];
  if ( v5 )
    _InterlockedIncrement((volatile signed __int32 *)(v5 + 8));
  v71 = *(_OWORD *)a2;
  ExistingParentDeviceDefinitionForEndpoint = CMidi2KSAggregateMidiEndpointManager2::FindExistingParentDeviceDefinitionForEndpoint(
                                                a1,
                                                &v71,
                                                &v76);
  v7 = ExistingParentDeviceDefinitionForEndpoint;
  if ( ExistingParentDeviceDefinitionForEndpoint < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x27C,
      (unsigned int)"avcore\\midi2\\transport\\ksaggregatetransport\\midi2.ksaggregatemidiendpointmanager2.cpp",
      (const char *)(unsigned int)ExistingParentDeviceDefinitionForEndpoint,
      v68);
LABEL_111:
    v66 = (volatile signed __int32 *)*((_QWORD *)&v76 + 1);
    if ( *((_QWORD *)&v76 + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v76 + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v66)(v66);
        if ( _InterlockedExchangeAdd(v66 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v66 + 8LL))(v66);
      }
    }
    v67 = (volatile signed __int32 *)a2[1];
    if ( v67 )
    {
      if ( _InterlockedExchangeAdd(v67 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v67)(v67);
        if ( _InterlockedExchangeAdd(v67 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v67 + 8LL))(v67);
      }
    }
    return v7;
  }
  if ( (_QWORD)v76 )
  {
    v11 = (_DWORD *)*((_QWORD *)MidiKSAggregateTransportTelemetryProvider::Instance() + 1);
    if ( *v11 > 4u )
    {
      v14 = (_QWORD *)(*a2 + 64LL);
      if ( *(_QWORD *)(*a2 + 88LL) > 7u )
        v14 = (_QWORD *)*v14;
      v72 = v14;
      *(_QWORD *)v73 = L"Enter";
      *(_QWORD *)v69 = a1;
      *(_QWORD *)v70 = "CMidi2KSAggregateMidiEndpointManager2::DeviceUpdateExistingMidiUmpEndpointWithFilterChanges";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
        (_DWORD)v11,
        (unsigned int)&dword_18008A8DC,
        v12,
        v13,
        (__int64)v70,
        (__int64)v69,
        (__int64)v73,
        (__int64)&v72);
    }
    if ( *(_QWORD *)(*a2 + 152LL) == *(_QWORD *)(*a2 + 160LL) && *(_QWORD *)(*a2 + 128LL) == *(_QWORD *)(*a2 + 136LL) )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x28B,
        (unsigned int)"avcore\\midi2\\transport\\ksaggregatetransport\\midi2.ksaggregatemidiendpointmanager2.cpp",
        (const char *)0x80070057LL,
        v68);
      v15 = (volatile signed __int32 *)*((_QWORD *)&v76 + 1);
      if ( *((_QWORD *)&v76 + 1) )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v76 + 1) + 8LL), 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v15)(v15);
          if ( _InterlockedExchangeAdd(v15 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v15 + 8LL))(v15);
        }
      }
      v16 = (volatile signed __int32 *)a2[1];
      if ( v16 )
      {
        if ( _InterlockedExchangeAdd(v16 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v16)(v16);
          if ( _InterlockedExchangeAdd(v16 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v16 + 8LL))(v16);
        }
      }
      return 2147942487LL;
    }
    v74 = 0;
    v75 = 0;
    v81 = 0;
    v82 = 0;
    v85 = 0;
    v86 = 0;
    v94 = 0;
    v95 = 0;
    v17 = (_DWORD *)*((_QWORD *)MidiKSAggregateTransportTelemetryProvider::Instance() + 1);
    if ( *v17 > 4u )
    {
      v20 = (_QWORD *)(*a2 + 64LL);
      if ( *(_QWORD *)(*a2 + 88LL) > 7u )
        v20 = (_QWORD *)*v20;
      *(_QWORD *)v70 = v20;
      *(_QWORD *)v69 = L"About to build pins and GTB property data";
      v72 = (_QWORD *)a1;
      *(_QWORD *)v73 = "CMidi2KSAggregateMidiEndpointManager2::DeviceUpdateExistingMidiUmpEndpointWithFilterChanges";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
        (_DWORD)v17,
        (unsigned int)byte_18008A8A1,
        v18,
        v19,
        (__int64)v73,
        (__int64)&v72,
        (__int64)v69,
        (__int64)v70);
    }
    v71 = 0;
    v21 = a2[1];
    if ( v21 )
      _InterlockedIncrement((volatile signed __int32 *)(v21 + 8));
    v71 = *(_OWORD *)a2;
    v22 = CMidi2KSAggregateMidiEndpointManager2::BuildPinsAndGroupTerminalBlocksPropertyData(a1, &v71, &v81, &v85);
    v7 = v22;
    if ( v22 >= 0 )
    {
      v77 = DEVPKEY_KsAggMidiGroupPinMap;
      v78 = 0x10u;
      LODWORD(v79) = 4099;
      DWORD1(v79) = DWORD2(v81) - v81;
      *((_QWORD *)&v79 + 1) = v81;
      v23 = *((_QWORD *)&v74 + 1);
      if ( *((_QWORD *)&v74 + 1) == v75 )
      {
        std::vector<_DEVPROPERTY>::_Emplace_reallocate<_DEVPROPERTY>(&v74, *((_QWORD *)&v74 + 1), &v77);
      }
      else
      {
        **((_OWORD **)&v74 + 1) = DEVPKEY_KsAggMidiGroupPinMap;
        *(_OWORD *)(v23 + 16) = v78;
        *(_OWORD *)(v23 + 32) = v79;
        *((_QWORD *)&v74 + 1) += 48LL;
      }
      v24 = (_DWORD *)*((_QWORD *)MidiKSAggregateTransportTelemetryProvider::Instance() + 1);
      if ( *v24 > 4u )
      {
        v27 = (_QWORD *)(*a2 + 64LL);
        if ( *(_QWORD *)(*a2 + 88LL) > 7u )
          v27 = (_QWORD *)*v27;
        *(_QWORD *)v70 = v27;
        *(_QWORD *)v69 = L"About to write group terminal blocks";
        v72 = (_QWORD *)a1;
        *(_QWORD *)v73 = "CMidi2KSAggregateMidiEndpointManager2::DeviceUpdateExistingMidiUmpEndpointWithFilterChanges";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
          (_DWORD)v24,
          (unsigned int)&word_18008A866,
          v25,
          v26,
          (__int64)v73,
          (__int64)&v72,
          (__int64)v69,
          (__int64)v70);
      }
      v83 = 0;
      v84 = 0;
      if ( (unsigned __int8)WindowsMidiServicesInternal::WriteGroupTerminalBlocksToPropertyDataPointer(&v85, &v83) )
      {
        v77 = PKEY_MIDI_GroupTerminalBlocks;
        v78 = 0x32u;
        LODWORD(v79) = 4099;
        DWORD1(v79) = DWORD2(v83) - v83;
        *((_QWORD *)&v79 + 1) = v83;
        v28 = *((_QWORD *)&v74 + 1);
        if ( *((_QWORD *)&v74 + 1) == v75 )
        {
          std::vector<_DEVPROPERTY>::_Emplace_reallocate<_DEVPROPERTY>(&v74, *((_QWORD *)&v74 + 1), &v77);
        }
        else
        {
          **((_OWORD **)&v74 + 1) = PKEY_MIDI_GroupTerminalBlocks;
          *(_OWORD *)(v28 + 16) = v78;
          *(_OWORD *)(v28 + 32) = v79;
          *((_QWORD *)&v74 + 1) += 48LL;
        }
      }
      v29 = (_DWORD *)*((_QWORD *)MidiKSAggregateTransportTelemetryProvider::Instance() + 1);
      if ( *v29 > 4u )
      {
        v32 = (_QWORD *)(*a2 + 64LL);
        if ( *(_QWORD *)(*a2 + 88LL) > 7u )
          v32 = (_QWORD *)*v32;
        *(_QWORD *)v70 = v32;
        *(_QWORD *)v69 = L"About to fold in custom properties";
        v72 = (_QWORD *)a1;
        *(_QWORD *)v73 = "CMidi2KSAggregateMidiEndpointManager2::DeviceUpdateExistingMidiUmpEndpointWithFilterChanges";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
          (_DWORD)v29,
          (unsigned int)byte_18008A82B,
          v30,
          v31,
          (__int64)v73,
          (__int64)&v72,
          (__int64)v69,
          (__int64)v70);
      }
      memset_0(&v87, 0, 0x50u);
      v87 = 0u;
      v88 = 0;
      v89 = 0;
      v90 = 0u;
      v91 = 0;
      v92 = 0;
      v93 = 0u;
      v33 = std::wstring::wstring(&v100, *a2 + 96LL);
      WindowsMidiServicesInternal::ToUpperTrimmedWStringCopy(&v97, v33);
      v34 = &v97;
      if ( v99 > 7 )
        v34 = (__int128 *)v97;
      *(_QWORD *)&v80 = v34;
      *((_QWORD *)&v80 + 1) = v98;
      winrt::hstring::operator=((char *)&v87 + 8, &v80);
      std::wstring::~wstring(&v97);
      v35 = *((_QWORD *)TransportState::Current() + 2);
      *(_QWORD *)&v71 = v35;
      if ( v35 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 8LL))(v35);
      v36 = *(_QWORD *)(v35 + 24);
      if ( v36 )
        _InterlockedIncrement((volatile signed __int32 *)(v36 + 8));
      v97 = *(_OWORD *)(v35 + 16);
      v37 = (volatile signed __int32 *)*((_QWORD *)&v97 + 1);
      WindowsMidiServicesPluginConfigurationLib::MidiEndpointCustomPropertiesCache::GetProperties(v97, &v80, &v87);
      if ( v37 )
      {
        if ( _InterlockedExchangeAdd(v37 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v37)(v37);
          if ( _InterlockedExchangeAdd(v37 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v37 + 8LL))(v37);
        }
      }
      if ( v35 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
      v100 = 0;
      si128 = _mm_load_si128((const __m128i *)&_xmm);
      LOWORD(v100) = 0;
      v102[0] = 0;
      v102[1] = si128;
      LOWORD(v102[0]) = 0;
      v38 = v80;
      v39 = (unsigned int *)*((_QWORD *)MidiKSAggregateTransportTelemetryProvider::Instance() + 1);
      v42 = *v39;
      if ( v38 )
      {
        if ( v42 > 5 )
        {
          v73[0] = *(_DWORD *)(v38 + 56);
          LODWORD(v72) = *(_DWORD *)(v38 + 40);
          v43 = (_QWORD *)(*a2 + 96LL);
          if ( *(_QWORD *)(*a2 + 120LL) > 7u )
            v43 = (_QWORD *)*v43;
          *(_QWORD *)v70 = v43;
          *(_QWORD *)v69 = L"Found custom properties cached for this endpoint";
          *(_QWORD *)&v97 = a1;
          *(_QWORD *)&v71 = "CMidi2KSAggregateMidiEndpointManager2::DeviceUpdateExistingMidiUmpEndpointWithFilterChanges";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            (_DWORD)v39,
            (unsigned int)&word_18008A7B6,
            v40,
            v41,
            (__int64)&v71,
            (__int64)&v97,
            (__int64)v69,
            (__int64)v70,
            (__int64)&v72,
            (__int64)v73);
        }
        WindowsMidiServicesPluginConfigurationLib::MidiEndpointCustomProperties::WriteNonCommonProperties(v38, &v74);
      }
      else if ( v42 > 5 )
      {
        v44 = (_QWORD *)(*a2 + 96LL);
        if ( *(_QWORD *)(*a2 + 120LL) > 7u )
          v44 = (_QWORD *)*v44;
        *(_QWORD *)&v71 = v44;
        *(_QWORD *)&v97 = L"No cached custom properties for this endpoint.";
        *(_QWORD *)v70 = a1;
        *(_QWORD *)v69 = "CMidi2KSAggregateMidiEndpointManager2::DeviceUpdateExistingMidiUmpEndpointWithFilterChanges";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
          (_DWORD)v39,
          (unsigned int)qword_18008A770,
          v40,
          v41,
          (__int64)v69,
          (__int64)v70,
          (__int64)&v97,
          (__int64)&v71);
      }
      WindowsMidiServicesNamingLib::MidiEndpointNameTable::WriteProperties(*a2 + 176LL, &v74);
      v45 = (_DWORD *)*((_QWORD *)MidiKSAggregateTransportTelemetryProvider::Instance() + 1);
      if ( *v45 > 4u )
      {
        v48 = (_QWORD *)(*a2 + 64LL);
        if ( *(_QWORD *)(*a2 + 88LL) > 7u )
          v48 = (_QWORD *)*v48;
        *(_QWORD *)&v71 = v48;
        *(_QWORD *)&v97 = L"About to update name table";
        *(_QWORD *)v70 = a1;
        *(_QWORD *)v69 = "CMidi2KSAggregateMidiEndpointManager2::DeviceUpdateExistingMidiUmpEndpointWithFilterChanges";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
          (_DWORD)v45,
          (unsigned int)byte_18008A735,
          v46,
          v47,
          (__int64)v69,
          (__int64)v70,
          (__int64)&v97,
          (__int64)&v71);
      }
      v49 = (volatile signed __int32 *)*((_QWORD *)&v80 + 1);
      if ( *((_QWORD *)&v80 + 1) )
        _InterlockedIncrement((volatile signed __int32 *)(*((_QWORD *)&v80 + 1) + 8LL));
      v97 = v80;
      v50 = a2[1];
      if ( v50 )
        _InterlockedIncrement((volatile signed __int32 *)(v50 + 8));
      v71 = *(_OWORD *)a2;
      updated = CMidi2KSAggregateMidiEndpointManager2::UpdateNameTableWithCustomProperties(a1, &v71, &v97);
      v7 = updated;
      if ( updated >= 0 )
      {
        WindowsMidiServicesNamingLib::MidiEndpointNameTable::WriteProperties(*a2 + 176LL, &v74);
        v52 = (_DWORD *)*((_QWORD *)MidiKSAggregateTransportTelemetryProvider::Instance() + 1);
        if ( *v52 > 4u )
        {
          v55 = (_QWORD *)(*a2 + 64LL);
          if ( *(_QWORD *)(*a2 + 88LL) > 7u )
            v55 = (_QWORD *)*v55;
          *(_QWORD *)&v71 = v55;
          *(_QWORD *)&v97 = L"About to update endpoint properties in the MIDI Device Manager";
          *(_QWORD *)v70 = a1;
          *(_QWORD *)v69 = "CMidi2KSAggregateMidiEndpointManager2::DeviceUpdateExistingMidiUmpEndpointWithFilterChanges";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
            (_DWORD)v52,
            (unsigned int)word_18008A6FA,
            v53,
            v54,
            (__int64)v69,
            (__int64)v70,
            (__int64)&v97,
            (__int64)&v71);
        }
        v56 = (_QWORD *)(*a2 + 32LL);
        if ( *(_QWORD *)(*a2 + 56LL) > 7u )
          v56 = (_QWORD *)*v56;
        v57 = (*(__int64 (__fastcall **)(_QWORD, _QWORD *, unsigned __int64))(**(_QWORD **)(a1 + 32) + 48LL))(
                *(_QWORD *)(a1 + 32),
                v56,
                0xAAAAAAAAAAAAAAABuLL * ((__int64)(*((_QWORD *)&v74 + 1) - v74) >> 4));
        v7 = v57;
        if ( v57 >= 0 )
        {
          v61 = (_DWORD *)*((_QWORD *)MidiKSAggregateTransportTelemetryProvider::Instance() + 1);
          if ( *v61 > 4u )
          {
            v64 = (_QWORD *)(*a2 + 32LL);
            if ( *(_QWORD *)(*a2 + 56LL) > 7u )
              v64 = (_QWORD *)*v64;
            *(_QWORD *)&v71 = v64;
            *(_QWORD *)&v97 = L"Aggregate UMP endpoint updated with new filter";
            *(_QWORD *)v70 = a1;
            *(_QWORD *)v69 = "CMidi2KSAggregateMidiEndpointManager2::DeviceUpdateExistingMidiUmpEndpointWithFilterChanges";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
              (_DWORD)v61,
              (unsigned int)&dword_18008A6A4,
              v62,
              v63,
              (__int64)v69,
              (__int64)v70,
              (__int64)&v97,
              (__int64)&v71);
          }
          v65 = std::wstring::wstring(&v77, *a2 + 96LL);
          WindowsMidiServicesInternal::ToUpperTrimmedWStringCopy(&v97, v65);
          std::map<std::wstring,std::shared_ptr<KsAggregateEndpointDefinition2>>::_Insert_or_assign<std::wstring,std::shared_ptr<KsAggregateEndpointDefinition2> &>(
            a1 + 168,
            &v71,
            &v97,
            a2);
          std::wstring::~wstring(&v97);
        }
        else
        {
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x324,
            (unsigned int)"avcore\\midi2\\transport\\ksaggregatetransport\\midi2.ksaggregatemidiendpointmanager2.cpp",
            (const char *)(unsigned int)v57,
            v68);
          v58 = (_DWORD *)*((_QWORD *)MidiKSAggregateTransportTelemetryProvider::Instance() + 1);
          if ( *v58 > 2u )
          {
            LODWORD(v72) = v7;
            v60 = (_QWORD *)(*a2 + 64LL);
            if ( *(_QWORD *)(*a2 + 88LL) > 7u )
              v60 = (_QWORD *)*v60;
            *(_QWORD *)&v71 = v60;
            *(_QWORD *)&v97 = L"Aggregate UMP endpoint update failed";
            *(_QWORD *)v70 = a1;
            *(_QWORD *)v69 = "CMidi2KSAggregateMidiEndpointManager2::DeviceUpdateExistingMidiUmpEndpointWithFilterChanges";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
              (_DWORD)v58,
              (unsigned int)byte_18008A661,
              (_DWORD)v58,
              v59,
              (__int64)v69,
              (__int64)v70,
              (__int64)&v97,
              (__int64)&v71,
              (__int64)&v72);
          }
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x310,
          (unsigned int)"avcore\\midi2\\transport\\ksaggregatetransport\\midi2.ksaggregatemidiendpointmanager2.cpp",
          (const char *)(unsigned int)updated,
          v68);
      }
      std::wstring::~wstring(v102);
      std::wstring::~wstring(&v100);
      if ( v49 )
      {
        if ( _InterlockedExchangeAdd(v49 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v49)(v49);
          if ( _InterlockedExchangeAdd(v49 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v49 + 8LL))(v49);
        }
      }
      WindowsMidiServicesPluginConfigurationLib::MidiEndpointMatchCriteria::~MidiEndpointMatchCriteria((WindowsMidiServicesPluginConfigurationLib::MidiEndpointMatchCriteria *)&v87);
      std::vector<enum std::byte>::~vector<enum std::byte>(&v83);
      std::vector<enum std::byte>::~vector<enum std::byte>(&v94);
      std::vector<PinMapEntryStagingEntry>::~vector<PinMapEntryStagingEntry>(&v85);
      std::vector<enum std::byte>::~vector<enum std::byte>(&v81);
      std::vector<_DEVPROPERTY>::~vector<_DEVPROPERTY>(&v74);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2A2,
        (unsigned int)"avcore\\midi2\\transport\\ksaggregatetransport\\midi2.ksaggregatemidiendpointmanager2.cpp",
        (const char *)(unsigned int)v22,
        v68);
      std::vector<enum std::byte>::~vector<enum std::byte>(&v94);
      std::vector<PinMapEntryStagingEntry>::~vector<PinMapEntryStagingEntry>(&v85);
      std::vector<enum std::byte>::~vector<enum std::byte>(&v81);
      std::vector<_DEVPROPERTY>::~vector<_DEVPROPERTY>(&v74);
    }
    goto LABEL_111;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x27D,
    (unsigned int)"avcore\\midi2\\transport\\ksaggregatetransport\\midi2.ksaggregatemidiendpointmanager2.cpp",
    (const char *)0x8000FFFFLL,
    v68);
  v8 = (volatile signed __int32 *)*((_QWORD *)&v76 + 1);
  if ( *((_QWORD *)&v76 + 1) )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v76 + 1) + 8LL), 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v8)(v8);
      if ( _InterlockedExchangeAdd(v8 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v8 + 8LL))(v8);
    }
  }
  v9 = (volatile signed __int32 *)a2[1];
  if ( v9 )
  {
    if ( _InterlockedExchangeAdd(v9 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v9)(v9);
      if ( _InterlockedExchangeAdd(v9 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v9 + 8LL))(v9);
    }
  }
  return 2147549183LL;
}

```

## disassembly

```asm
0x180037fec  mov     [rsp-8+arg_10], rbx
0x180037ff1  mov     [rsp-8+arg_18], rsi
0x180037ff6  push    rbp
0x180037ff7  push    rdi
0x180037ff8  push    r12
0x180037ffa  push    r14
0x180037ffc  push    r15
0x180037ffe  lea     rbp, [rsp-120h]
0x180038006  sub     rsp, 220h
0x18003800d  mov     rax, cs:__security_cookie
0x180038014  xor     rax, rsp
0x180038017  mov     [rbp+140h+var_30], rax
0x18003801e  mov     rdi, rdx
0x180038021  mov     r14, rcx
0x180038024  mov     [rbp+140h+var_98], rdx
0x18003802b  xor     r12d, r12d
0x18003802e  cmp     [rdx], r12
0x180038031  jnz     short loc_18003809A
0x180038033  mov     rcx, [rbp+148h]; this
0x18003803a  mov     r9d, 80070057h; char *
0x180038040  lea     r8, aAvcoreMidi2Tra_4; "avcore\\midi2\\transport\\ksaggregatetr"...
0x180038047  mov     edx, 279h; void *
0x18003804c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180038051  nop
0x180038052  mov     rdi, [rdi+8]
0x180038056  test    rdi, rdi
0x180038059  jz      loc_1800382EC
0x18003805f  or      ebx, 0FFFFFFFFh
0x180038062  mov     eax, ebx
0x180038064  lock xadd [rdi+8], eax
0x180038069  add     eax, ebx
0x18003806b  jnz     loc_1800382EC
0x180038071  mov     rax, [rdi]
0x180038074  mov     rcx, rdi
0x180038077  mov     rax, [rax]
0x18003807a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003807f  mov     eax, ebx
0x180038081  lock xadd [rdi+0Ch], eax
0x180038086  add     eax, ebx
0x180038088  jnz     loc_1800382EC
0x18003808e  mov     rax, [rdi]
0x180038091  mov     rax, [rax+8]
0x180038095  jmp     loc_1800382E4
0x18003809a  xorps   xmm0, xmm0
0x18003809d  movdqu  [rbp+140h+var_1A8], xmm0
0x1800380a2  movdqu  [rsp+240h+var_1E0], xmm0
0x1800380a8  mov     rax, [rdx+8]
0x1800380ac  test    rax, rax
0x1800380af  jz      short loc_1800380B5
0x1800380b1  lock inc dword ptr [rax+8]
0x1800380b5  mov     rax, [rdx]
0x1800380b8  mov     qword ptr [rsp+240h+var_1E0], rax
0x1800380bd  mov     rax, [rdx+8]
0x1800380c1  mov     qword ptr [rsp+240h+var_1E0+8], rax
0x1800380c6  lea     r8, [rbp+140h+var_1A8]
0x1800380ca  lea     rdx, [rsp+240h+var_1E0]
0x1800380cf  call    ?FindExistingParentDeviceDefinitionForEndpoint@CMidi2KSAggregateMidiEndpointManager2@@AEAAJV?$shared_ptr@UKsAggregateEndpointDefinition2@@@std@@AEAV?$shared_ptr@VKsAggregateParentDeviceDefinition2@@@3@@Z; CMidi2KSAggregateMidiEndpointManager2::FindExistingParentDeviceDefinitionForEndpoint(std::shared_ptr<KsAggregateEndpointDefinition2>,std::shared_ptr<KsAggregateParentDeviceDefinition2> &)
0x1800380d4  mov     r15d, eax
0x1800380d7  test    eax, eax
0x1800380d9  jns     short loc_1800380FF
0x1800380db  mov     rcx, [rbp+148h]; this
0x1800380e2  mov     r9d, eax; char *
0x1800380e5  lea     r8, aAvcoreMidi2Tra_4; "avcore\\midi2\\transport\\ksaggregatetr"...
0x1800380ec  mov     edx, 27Ch; void *
0x1800380f1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800380f6  nop
0x1800380f7  or      ebx, 0FFFFFFFFh
0x1800380fa  jmp     loc_180038C81
0x1800380ff  cmp     qword ptr [rbp+140h+var_1A8], r12
0x180038103  jnz     loc_1800381AF
0x180038109  mov     rcx, [rbp+148h]; this
0x180038110  mov     r14d, 8000FFFFh
0x180038116  mov     r9d, r14d; char *
0x180038119  lea     r8, aAvcoreMidi2Tra_4; "avcore\\midi2\\transport\\ksaggregatetr"...
0x180038120  mov     edx, 27Dh; void *
0x180038125  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003812a  nop
0x18003812b  or      ebx, 0FFFFFFFFh
0x18003812e  mov     rsi, qword ptr [rbp+140h+var_1A8+8]
0x180038132  test    rsi, rsi
0x180038135  jz      short loc_18003816B
0x180038137  mov     eax, ebx
0x180038139  lock xadd [rsi+8], eax
0x18003813e  add     eax, ebx
0x180038140  jnz     short loc_18003816B
0x180038142  mov     rax, [rsi]
0x180038145  mov     rcx, rsi
0x180038148  mov     rax, [rax]
0x18003814b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038150  mov     eax, ebx
0x180038152  lock xadd [rsi+0Ch], eax
0x180038157  add     eax, ebx
0x180038159  jnz     short loc_18003816B
0x18003815b  mov     rax, [rsi]
0x18003815e  mov     rcx, rsi
0x180038161  mov     rax, [rax+8]
0x180038165  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003816a  nop
0x18003816b  mov     rdi, [rdi+8]
0x18003816f  test    rdi, rdi
0x180038172  jz      short loc_1800381A7
0x180038174  mov     eax, ebx
0x180038176  lock xadd [rdi+8], eax
0x18003817b  add     eax, ebx
0x18003817d  jnz     short loc_1800381A7
0x18003817f  mov     rax, [rdi]
0x180038182  mov     rcx, rdi
0x180038185  mov     rax, [rax]
0x180038188  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003818d  mov     eax, ebx
0x18003818f  lock xadd [rdi+0Ch], eax
0x180038194  add     eax, ebx
0x180038196  jnz     short loc_1800381A7
0x180038198  mov     rax, [rdi]
0x18003819b  mov     rcx, rdi
0x18003819e  mov     rax, [rax+8]
0x1800381a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800381a7  mov     eax, r14d
0x1800381aa  jmp     loc_180038CFD
0x1800381af  call    ?Instance@MidiKSAggregateTransportTelemetryProvider@@KAPEAV1@XZ; MidiKSAggregateTransportTelemetryProvider::Instance(void)
0x1800381b4  mov     rcx, [rax+8]
0x1800381b8  mov     eax, [rcx]
0x1800381ba  lea     rbx, aCmidi2ksaggreg_29; "CMidi2KSAggregateMidiEndpointManager2::"...
0x1800381c1  cmp     eax, 4
0x1800381c4  jbe     short loc_180038226
0x1800381c6  mov     rax, [rdi]
0x1800381c9  add     rax, 40h ; '@'
0x1800381cd  cmp     qword ptr [rax+18h], 7
0x1800381d2  jbe     short loc_1800381D7
0x1800381d4  mov     rax, [rax]
0x1800381d7  mov     [rsp+240h+var_1D0], rax
0x1800381dc  lea     rax, aEnter_0; "Enter"
0x1800381e3  mov     qword ptr [rsp+240h+var_1C8], rax
0x1800381e8  mov     qword ptr [rsp+240h+var_1F0], r14
0x1800381ed  mov     qword ptr [rsp+240h+var_1E8], rbx
0x1800381f2  lea     rax, [rsp+240h+var_1D0]
0x1800381f7  mov     [rsp+240h+var_208], rax
0x1800381fc  lea     rax, [rsp+240h+var_1C8]
0x180038201  mov     [rsp+240h+var_210], rax
0x180038206  lea     rax, [rsp+240h+var_1F0]
0x18003820b  mov     [rsp+240h+var_218], rax
0x180038210  lea     rax, [rsp+240h+var_1E8]
0x180038215  mov     qword ptr [rsp+240h+var_220], rax; int
0x18003821a  lea     rdx, dword_18008A8DC
0x180038221  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x180038226  mov     rcx, [rdi]
0x180038229  mov     rax, [rcx+0A0h]
0x180038230  cmp     [rcx+98h], rax
0x180038237  jnz     loc_1800382F6
0x18003823d  mov     rax, [rcx+88h]
0x180038244  cmp     [rcx+80h], rax
0x18003824b  jnz     loc_1800382F6
0x180038251  mov     rcx, [rbp+148h]; this
0x180038258  mov     r9d, 80070057h; char *
0x18003825e  lea     r8, aAvcoreMidi2Tra_4; "avcore\\midi2\\transport\\ksaggregatetr"...
0x180038265  mov     edx, 28Bh; void *
0x18003826a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003826f  nop
0x180038270  or      ebx, 0FFFFFFFFh
0x180038273  mov     rsi, qword ptr [rbp+140h+var_1A8+8]
0x180038277  test    rsi, rsi
0x18003827a  jz      short loc_1800382B0
0x18003827c  mov     eax, ebx
0x18003827e  lock xadd [rsi+8], eax
0x180038283  add     eax, ebx
0x180038285  jnz     short loc_1800382B0
0x180038287  mov     rax, [rsi]
0x18003828a  mov     rcx, rsi
0x18003828d  mov     rax, [rax]
0x180038290  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038295  mov     eax, ebx
0x180038297  lock xadd [rsi+0Ch], eax
0x18003829c  add     eax, ebx
0x18003829e  jnz     short loc_1800382B0
0x1800382a0  mov     rax, [rsi]
0x1800382a3  mov     rcx, rsi
0x1800382a6  mov     rax, [rax+8]
0x1800382aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800382af  nop
0x1800382b0  mov     rdi, [rdi+8]
0x1800382b4  test    rdi, rdi
0x1800382b7  jz      short loc_1800382EC
0x1800382b9  mov     eax, ebx
0x1800382bb  lock xadd [rdi+8], eax
0x1800382c0  add     eax, ebx
0x1800382c2  jnz     short loc_1800382EC
0x1800382c4  mov     rax, [rdi]
0x1800382c7  mov     rcx, rdi
0x1800382ca  mov     rax, [rax]
0x1800382cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800382d2  mov     edx, ebx
0x1800382d4  lock xadd [rdi+0Ch], edx
0x1800382d9  add     edx, ebx
0x1800382db  jnz     short loc_1800382EC
0x1800382dd  mov     rdx, [rdi]
0x1800382e0  mov     rax, [rdx+8]
0x1800382e4  mov     rcx, rdi
0x1800382e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800382ec  mov     eax, 80070057h
0x1800382f1  jmp     loc_180038CFD
0x1800382f6  xorps   xmm0, xmm0
0x1800382f9  movdqu  [rbp+140h+var_1C0], xmm0
0x1800382fe  mov     [rbp+140h+var_1B0], r12
0x180038302  movdqu  [rbp+140h+var_150], xmm0
0x180038307  mov     [rbp+140h+var_140], r12
0x18003830b  movdqu  [rbp+140h+var_120], xmm0
0x180038310  mov     [rbp+140h+var_110], r12
0x180038314  movdqu  [rbp+140h+var_B0], xmm0
0x18003831c  mov     [rbp+140h+var_A0], r12
0x180038323  call    ?Instance@MidiKSAggregateTransportTelemetryProvider@@KAPEAV1@XZ; MidiKSAggregateTransportTelemetryProvider::Instance(void)
0x180038328  mov     rcx, [rax+8]
0x18003832c  mov     eax, [rcx]
0x18003832e  cmp     eax, 4
0x180038331  jbe     short loc_180038393
0x180038333  mov     rax, [rdi]
0x180038336  add     rax, 40h ; '@'
0x18003833a  cmp     qword ptr [rax+18h], 7
0x18003833f  jbe     short loc_180038344
0x180038341  mov     rax, [rax]
0x180038344  mov     qword ptr [rsp+240h+var_1E8], rax
0x180038349  lea     rax, aAboutToBuildPi; "About to build pins and GTB property da"...
0x180038350  mov     qword ptr [rsp+240h+var_1F0], rax
0x180038355  mov     [rsp+240h+var_1D0], r14
0x18003835a  mov     qword ptr [rsp+240h+var_1C8], rbx
0x18003835f  lea     rax, [rsp+240h+var_1E8]
0x180038364  mov     [rsp+240h+var_208], rax
0x180038369  lea     rax, [rsp+240h+var_1F0]
0x18003836e  mov     [rsp+240h+var_210], rax
0x180038373  lea     rax, [rsp+240h+var_1D0]
0x180038378  mov     [rsp+240h+var_218], rax
0x18003837d  lea     rax, [rsp+240h+var_1C8]
0x180038382  mov     qword ptr [rsp+240h+var_220], rax; int
0x180038387  lea     rdx, byte_18008A8A1
0x18003838e  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x180038393  xorps   xmm0, xmm0
0x180038396  movdqu  [rsp+240h+var_1E0], xmm0
0x18003839c  mov     rax, [rdi+8]
0x1800383a0  test    rax, rax
0x1800383a3  jz      short loc_1800383A9
0x1800383a5  lock inc dword ptr [rax+8]
0x1800383a9  mov     rax, [rdi]
0x1800383ac  mov     qword ptr [rsp+240h+var_1E0], rax
0x1800383b1  mov     rax, [rdi+8]
0x1800383b5  mov     qword ptr [rsp+240h+var_1E0+8], rax
0x1800383ba  lea     r9, [rbp+140h+var_120]
0x1800383be  lea     r8, [rbp+140h+var_150]
0x1800383c2  lea     rdx, [rsp+240h+var_1E0]
0x1800383c7  mov     rcx, r14
0x1800383ca  call    ?BuildPinsAndGroupTerminalBlocksPropertyData@CMidi2KSAggregateMidiEndpointManager2@@AEAAJV?$shared_ptr@UKsAggregateEndpointDefinition2@@@std@@AEAV?$vector@W4byte@std@@V?$allocator@W4byte@std@@@2@@3@AEAV?$vector@UGroupTerminalBlockInternal@WindowsMidiServicesInternal@@V?$allocator@UGroupTerminalBlockInternal@WindowsMidiServicesInternal@@@std@@@3@@Z; CMidi2KSAggregateMidiEndpointManager2::BuildPinsAndGroupTerminalBlocksPropertyData(std::shared_ptr<KsAggregateEndpointDefinition2>,std::vector<std::byte> &,std::vector<WindowsMidiServicesInternal::GroupTerminalBlockInternal> &)
0x1800383cf  mov     r15d, eax
0x1800383d2  test    eax, eax
0x1800383d4  jns     short loc_180038421
0x1800383d6  mov     rcx, [rbp+148h]; this
0x1800383dd  mov     r9d, eax; char *
0x1800383e0  lea     r8, aAvcoreMidi2Tra_4; "avcore\\midi2\\transport\\ksaggregatetr"...
0x1800383e7  mov     edx, 2A2h; void *
0x1800383ec  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800383f1  nop
0x1800383f2  lea     rcx, [rbp+140h+var_B0]
0x1800383f9  call    ??1?$vector@W4byte@std@@V?$allocator@W4byte@std@@@2@@std@@QEAA@XZ; std::vector<std::byte>::~vector<std::byte>(void)
0x1800383fe  nop
0x1800383ff  lea     rcx, [rbp+140h+var_120]
0x180038403  call    ??1?$vector@UPinMapEntryStagingEntry@@V?$allocator@UPinMapEntryStagingEntry@@@std@@@std@@QEAA@XZ; std::vector<PinMapEntryStagingEntry>::~vector<PinMapEntryStagingEntry>(void)
0x180038408  nop
0x180038409  lea     rcx, [rbp+140h+var_150]
0x18003840d  call    ??1?$vector@W4byte@std@@V?$allocator@W4byte@std@@@2@@std@@QEAA@XZ; std::vector<std::byte>::~vector<std::byte>(void)
0x180038412  nop
0x180038413  lea     rcx, [rbp+140h+var_1C0]
0x180038417  call    ??1?$vector@U_DEVPROPERTY@@V?$allocator@U_DEVPROPERTY@@@std@@@std@@QEAA@XZ; std::vector<_DEVPROPERTY>::~vector<_DEVPROPERTY>(void)
0x18003841c  jmp     loc_1800380F7
0x180038421  movups  xmm0, cs:DEVPKEY_KsAggMidiGroupPinMap
0x180038428  movups  [rbp+140h+var_198], xmm0
0x18003842c  mov     eax, cs:dword_18007E198
0x180038432  mov     dword ptr [rbp+140h+var_188], eax
0x180038435  mov     dword ptr [rbp+140h+var_188+4], r12d
0x180038439  mov     qword ptr [rbp+140h+var_188+8], r12
0x18003843d  mov     esi, 1003h
0x180038442  mov     dword ptr [rbp+140h+var_178], esi
0x180038445  mov     eax, dword ptr [rbp+140h+var_150+8]
0x180038448  mov     rcx, qword ptr [rbp+140h+var_150]
0x18003844c  sub     eax, ecx
0x18003844e  mov     dword ptr [rbp+140h+var_178+4], eax
0x180038451  mov     qword ptr [rbp+140h+var_178+8], rcx
0x180038455  mov     rdx, qword ptr [rbp+140h+var_1C0+8]
0x180038459  cmp     rdx, [rbp+140h+var_1B0]
0x18003845d  jz      short loc_180038479
0x18003845f  movups  xmmword ptr [rdx], xmm0
0x180038462  movups  xmm0, [rbp+140h+var_188]
0x180038466  movups  xmmword ptr [rdx+10h], xmm0
0x18003846a  movups  xmm1, [rbp+140h+var_178]
0x18003846e  movups  xmmword ptr [rdx+20h], xmm1
0x180038472  add     qword ptr [rbp+140h+var_1C0+8], 30h ; '0'
0x180038477  jmp     short loc_180038486
0x180038479  lea     r8, [rbp+140h+var_198]
0x18003847d  lea     rcx, [rbp+140h+var_1C0]
0x180038481  call    ??$_Emplace_reallocate@U_DEVPROPERTY@@@?$vector@U_DEVPROPERTY@@V?$allocator@U_DEVPROPERTY@@@std@@@std@@AEAAPEAU_DEVPROPERTY@@QEAU2@$$QEAU2@@Z; std::vector<_DEVPROPERTY>::_Emplace_reallocate<_DEVPROPERTY>(_DEVPROPERTY * const,_DEVPROPERTY &&)
0x180038486  call    ?Instance@MidiKSAggregateTransportTelemetryProvider@@KAPEAV1@XZ; MidiKSAggregateTransportTelemetryProvider::Instance(void)
0x18003848b  mov     rcx, [rax+8]
0x18003848f  mov     eax, [rcx]
0x180038491  cmp     eax, 4
  ... truncated ...
```
