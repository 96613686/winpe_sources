# CMidi2KSAggregateMidiEndpointManager2::DeviceCreateMidiUmpEndpoint(std::shared_ptr<KsAggregateEndpointDefinition2>)

- ea: `0x180036d5c`
- end: `0x180037fe5`
- name: `?DeviceCreateMidiUmpEndpoint@CMidi2KSAggregateMidiEndpointManager2@@AEAAJV?$shared_ptr@UKsAggregateEndpointDefinition2@@@std@@@Z`
- size: `4745`
- prototype: ``
- caller_count: `1`
- callee_count: `35`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180038d30`

## callees

- `0x1800017d0`
- `0x180001a94`
- `0x180002390`
- `0x180002640`
- `0x180002774`
- `0x180005020`
- `0x180005e9c`
- `0x18000b394`
- `0x18000d430`
- `0x18000d920`
- `0x18000e37c`
- `0x1800117d8`
- `0x180013118`
- `0x180014194`
- `0x180019924`
- `0x18001aa6c`
- `0x18001b160`
- `0x18001ca4c`
- `0x18001fa30`
- `0x180020b58`
- `0x1800224f8`
- `0x180022648`
- `0x180022f64`
- `0x180029298`
- `0x180029460`
- `0x18002dff8`
- `0x180035c78`
- `0x180036d5c`
- `0x180039928`
- `0x18003fc04`
- `0x18004003c`
- `0x18004c470`
- `0x18004d024`
- `0x1800570d0`
- `0x18005e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180037d2f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180037d2f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180037e92`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180037e92`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180037be1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180037be1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037bce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037bce`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180037bd9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180037ea2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180037bd9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180037ea2`

## string_xrefs

- `0x1800377c9`: `Found custom properties cached for this endpoint`
- `0x1800378bb`: `No cached custom properties for this endpoint.`
- `0x180037d6a`: `Aggregate UMP endpoint created`
- `0x180036f16`: `CMidi2KSAggregateMidiEndpointManager2::DeviceCreateMidiUmpEndpoint`
- `0x1800377db`: `CMidi2KSAggregateMidiEndpointManager2::DeviceCreateMidiUmpEndpoint`
- `0x1800378cd`: `CMidi2KSAggregateMidiEndpointManager2::DeviceCreateMidiUmpEndpoint`
- `0x180037b6f`: `CMidi2KSAggregateMidiEndpointManager2::DeviceCreateMidiUmpEndpoint`
- `0x180037cd5`: `CMidi2KSAggregateMidiEndpointManager2::DeviceCreateMidiUmpEndpoint`
- `0x180037d79`: `CMidi2KSAggregateMidiEndpointManager2::DeviceCreateMidiUmpEndpoint`

## pseudocode

```c
// Hidden C++ exception states: #wind=22
__int64 __fastcall CMidi2KSAggregateMidiEndpointManager2::DeviceCreateMidiUmpEndpoint(__int64 a1, _QWORD *a2)
{
  volatile signed __int32 *v4; // rbx
  __int64 v5; // rax
  int ExistingParentDeviceDefinitionForEndpoint; // esi
  __int64 v7; // rdx
  volatile signed __int32 *v8; // rbx
  volatile signed __int32 *v9; // rbx
  __int64 v11; // rbx
  _DWORD *v12; // r8
  int v13; // r9d
  _QWORD *v14; // rcx
  _WORD *v15; // rax
  _QWORD *v16; // rax
  _QWORD *v17; // rcx
  __int64 v18; // rcx
  __int64 v19; // rdx
  __int64 v20; // rdx
  volatile signed __int32 *v21; // rbx
  __int64 v22; // r9
  volatile signed __int32 *v23; // rbx
  volatile signed __int32 *v24; // rsi
  __int64 v25; // rax
  int updated; // eax
  unsigned int v27; // r14d
  volatile signed __int32 *v28; // rbx
  __int64 *v29; // rax
  __int64 v30; // rcx
  _QWORD *v31; // rax
  _QWORD *v32; // rax
  __int64 v33; // rax
  int v34; // eax
  __int64 v35; // rdx
  char v36; // al
  __int64 v37; // rdx
  __int64 v38; // rax
  __int128 *v39; // rax
  __int64 v40; // rcx
  __int64 v41; // rax
  __int64 v42; // rcx
  __int64 v43; // r14
  __int64 v44; // rax
  volatile signed __int32 *v45; // rbx
  volatile signed __int32 *v46; // r14
  __int128 v47; // xmm6
  __int64 v48; // rax
  int v49; // eax
  unsigned int v50; // r12d
  unsigned int *v51; // rcx
  int v52; // r8d
  int v53; // r9d
  unsigned int v54; // eax
  _QWORD *v55; // rax
  __int128 *v56; // rax
  __int128 *v57; // rax
  _QWORD *v58; // rax
  __int64 v59; // rax
  int v60; // eax
  __int64 v61; // rdx
  _OWORD *v62; // rdx
  __int64 v63; // rdx
  __int64 v64; // rcx
  _QWORD *v65; // rax
  _QWORD *v66; // rax
  _DWORD *v67; // rcx
  int v68; // r8d
  int v69; // r9d
  _QWORD *v70; // rax
  __int64 v71; // rcx
  __int64 (__fastcall *v72)(__int64, _QWORD *, _QWORD, __int64); // r10
  void *v73; // r12
  DWORD LastError; // ebx
  _QWORD *v75; // rdx
  int v76; // eax
  _DWORD *v77; // r8
  int v78; // r9d
  _QWORD *v79; // rax
  _DWORD *v80; // rcx
  int v81; // r8d
  int v82; // r9d
  _QWORD *v83; // rax
  __int64 v84; // r8
  __int64 v85; // rax
  __int64 v86; // rax
  volatile signed __int32 *v87; // rbx
  int v88; // [rsp+28h] [rbp-E0h]
  int v89[4]; // [rsp+68h] [rbp-A0h] BYREF
  __int128 v90; // [rsp+78h] [rbp-90h] BYREF
  _OWORD *v91; // [rsp+88h] [rbp-80h]
  char v92; // [rsp+90h] [rbp-78h] BYREF
  int v93; // [rsp+94h] [rbp-74h] BYREF
  __int128 v94; // [rsp+98h] [rbp-70h] BYREF
  __int128 v95; // [rsp+A8h] [rbp-60h]
  __int128 v96; // [rsp+B8h] [rbp-50h]
  int v97[2]; // [rsp+C8h] [rbp-40h] BYREF
  const wchar_t *v98; // [rsp+D0h] [rbp-38h] BYREF
  int v99; // [rsp+D8h] [rbp-30h] BYREF
  LPVOID pv; // [rsp+E0h] [rbp-28h]
  _QWORD v101[2]; // [rsp+E8h] [rbp-20h] BYREF
  __int128 v102; // [rsp+F8h] [rbp-10h] BYREF
  _WORD *v103; // [rsp+108h] [rbp+0h] BYREF
  __int128 v104; // [rsp+110h] [rbp+8h] BYREF
  __int64 v105; // [rsp+120h] [rbp+18h]
  __int128 v106; // [rsp+128h] [rbp+20h] BYREF
  __int64 v107; // [rsp+138h] [rbp+30h]
  __int128 v108; // [rsp+140h] [rbp+38h] BYREF
  __int64 v109; // [rsp+150h] [rbp+48h]
  __int128 v110; // [rsp+158h] [rbp+50h] BYREF
  int v111; // [rsp+168h] [rbp+60h]
  __int64 v112; // [rsp+170h] [rbp+68h] BYREF
  __int128 v113; // [rsp+178h] [rbp+70h]
  __int64 v114; // [rsp+188h] [rbp+80h]
  __int16 v115; // [rsp+190h] [rbp+88h]
  __int128 v116; // [rsp+198h] [rbp+90h] BYREF
  __int128 v117; // [rsp+1A8h] [rbp+A0h] BYREF
  __int64 v118; // [rsp+1B8h] [rbp+B0h]
  _QWORD *v119; // [rsp+1C0h] [rbp+B8h]
  int v120; // [rsp+1C8h] [rbp+C0h] BYREF
  _QWORD *v121; // [rsp+1D0h] [rbp+C8h]
  int v122; // [rsp+1F0h] [rbp+E8h]
  _QWORD *v123; // [rsp+1F8h] [rbp+F0h]
  int v124[4]; // [rsp+218h] [rbp+110h] BYREF
  int v125; // [rsp+228h] [rbp+120h]
  _BYTE v126[4]; // [rsp+22Ch] [rbp+124h] BYREF
  __int64 v127; // [rsp+230h] [rbp+128h]
  const unsigned __int16 *v128; // [rsp+238h] [rbp+130h]
  __int64 *v129; // [rsp+240h] [rbp+138h]
  __int128 v130; // [rsp+248h] [rbp+140h]
  __int128 *v131; // [rsp+258h] [rbp+150h]
  _QWORD *v132; // [rsp+260h] [rbp+158h]
  _QWORD *v133; // [rsp+268h] [rbp+160h]
  int v134; // [rsp+270h] [rbp+168h]
  int v135; // [rsp+274h] [rbp+16Ch]
  int v136; // [rsp+278h] [rbp+170h]
  _OWORD v137[2]; // [rsp+288h] [rbp+180h] BYREF
  __int128 v138; // [rsp+2A8h] [rbp+1A0h] BYREF
  __m128i v139; // [rsp+2B8h] [rbp+1B0h]
  __int128 v140; // [rsp+2C8h] [rbp+1C0h] BYREF
  __m128i si128; // [rsp+2D8h] [rbp+1D0h]
  __int128 v142; // [rsp+2E8h] [rbp+1E0h] BYREF
  __int64 v143; // [rsp+2F8h] [rbp+1F0h]
  unsigned __int64 v144; // [rsp+300h] [rbp+1F8h]
  _BYTE v145[32]; // [rsp+308h] [rbp+200h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+380h] [rbp+278h]

  v119 = a2;
  if ( !*a2 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x167,
      (unsigned int)"avcore\\midi2\\transport\\ksaggregatetransport\\midi2.ksaggregatemidiendpointmanager2.cpp",
      (const char *)0x80070057LL,
      v88);
    v4 = (volatile signed __int32 *)a2[1];
    if ( !v4 )
      return 2147942487LL;
    goto LABEL_3;
  }
  v102 = 0;
  *(_OWORD *)v89 = 0;
  v5 = a2[1];
  if ( v5 )
    _InterlockedIncrement((volatile signed __int32 *)(v5 + 8));
  *(_OWORD *)v89 = *(_OWORD *)a2;
  ExistingParentDeviceDefinitionForEndpoint = CMidi2KSAggregateMidiEndpointManager2::FindExistingParentDeviceDefinitionForEndpoint(
                                                a1,
                                                v89,
                                                &v102);
  if ( ExistingParentDeviceDefinitionForEndpoint < 0 )
  {
    v7 = 362;
    goto LABEL_10;
  }
  v11 = v102;
  if ( !(_QWORD)v102 )
  {
    ExistingParentDeviceDefinitionForEndpoint = -2147418113;
    v7 = 363;
LABEL_10:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"avcore\\midi2\\transport\\ksaggregatetransport\\midi2.ksaggregatemidiendpointmanager2.cpp",
      (const char *)(unsigned int)ExistingParentDeviceDefinitionForEndpoint,
      v88);
    v8 = (volatile signed __int32 *)*((_QWORD *)&v102 + 1);
    if ( *((_QWORD *)&v102 + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v102 + 1) + 8LL), 0xFFFFFFFF) == 1 )
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
    return (unsigned int)ExistingParentDeviceDefinitionForEndpoint;
  }
  v12 = (_DWORD *)*((_QWORD *)MidiKSAggregateTransportTelemetryProvider::Instance() + 1);
  if ( *v12 > 4u )
  {
    v14 = (_QWORD *)*a2;
    v99 = (__int64)(*(_QWORD *)(*a2 + 160LL) - *(_QWORD *)(*a2 + 152LL)) >> 4;
    v93 = (__int64)(v14[17] - v14[16]) >> 4;
    if ( *(_QWORD *)(v11 + 24) <= 7u )
      v15 = (_WORD *)v11;
    else
      v15 = *(_WORD **)v11;
    v103 = v15;
    v16 = v14 + 8;
    if ( v14[11] > 7u )
      v16 = (_QWORD *)*v16;
    v101[0] = v16;
    v17 = v14 + 12;
    if ( v17[3] > 7u )
      v17 = (_QWORD *)*v17;
    *(_QWORD *)v97 = v17;
    v98 = L"Enter";
    *(_QWORD *)&v137[0] = a1;
    *(_QWORD *)v89 = "CMidi2KSAggregateMidiEndpointManager2::DeviceCreateMidiUmpEndpoint";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      (_DWORD)v12,
      (unsigned int)&word_18008AAA6,
      (_DWORD)v12,
      v13,
      (__int64)v89,
      (__int64)v137,
      (__int64)&v98,
      (__int64)v97,
      (__int64)v101,
      (__int64)&v103,
      (__int64)&v93,
      (__int64)&v99);
  }
  v92 = -1;
  v18 = *a2;
  v19 = *(_QWORD *)(*a2 + 128LL);
  if ( (unsigned __int64)((*(_QWORD *)(*a2 + 136LL) - v19) >> 4) > 0x10 )
  {
    v20 = 382;
LABEL_32:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v20,
      (unsigned int)"avcore\\midi2\\transport\\ksaggregatetransport\\midi2.ksaggregatemidiendpointmanager2.cpp",
      (const char *)0x80070057LL,
      v88);
    v21 = (volatile signed __int32 *)*((_QWORD *)&v102 + 1);
    if ( *((_QWORD *)&v102 + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v102 + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v21)(v21);
        if ( _InterlockedExchangeAdd(v21 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v21 + 8LL))(v21);
      }
    }
    v4 = (volatile signed __int32 *)a2[1];
    if ( !v4 )
      return 2147942487LL;
LABEL_3:
    if ( _InterlockedExchangeAdd(v4 + 2, 0xFFFFFFFF) != 1 )
      return 2147942487LL;
    (**(void (__fastcall ***)(volatile signed __int32 *))v4)(v4);
    if ( _InterlockedExchangeAdd(v4 + 3, 0xFFFFFFFF) != 1 )
      return 2147942487LL;
    goto LABEL_49;
  }
  v22 = *(_QWORD *)(v18 + 152);
  if ( (unsigned __int64)((*(_QWORD *)(v18 + 160) - v22) >> 4) > 0x10 )
  {
    v20 = 383;
    goto LABEL_32;
  }
  if ( v19 == *(_QWORD *)(*a2 + 136LL) && v22 == *(_QWORD *)(v18 + 160) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x180,
      (unsigned int)"avcore\\midi2\\transport\\ksaggregatetransport\\midi2.ksaggregatemidiendpointmanager2.cpp",
      (const char *)0x80070057LL,
      v88);
    v23 = (volatile signed __int32 *)*((_QWORD *)&v102 + 1);
    if ( *((_QWORD *)&v102 + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v102 + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v23)(v23);
        if ( _InterlockedExchangeAdd(v23 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v23 + 8LL))(v23);
      }
    }
    v4 = (volatile signed __int32 *)a2[1];
    if ( !v4 )
      return 2147942487LL;
    if ( _InterlockedExchangeAdd(v4 + 2, 0xFFFFFFFF) != 1 )
      return 2147942487LL;
    (**(void (__fastcall ***)(volatile signed __int32 *))v4)(v4);
    if ( _InterlockedExchangeAdd(v4 + 3, 0xFFFFFFFF) != 1 )
      return 2147942487LL;
LABEL_49:
    (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v4 + 8LL))(v4);
    return 2147942487LL;
  }
  v137[0] = 0;
  v24 = (volatile signed __int32 *)*((_QWORD *)&v102 + 1);
  if ( *((_QWORD *)&v102 + 1) )
    _InterlockedIncrement((volatile signed __int32 *)(*((_QWORD *)&v102 + 1) + 8LL));
  v137[0] = v102;
  *(_OWORD *)v89 = 0;
  v25 = a2[1];
  if ( v25 )
    _InterlockedIncrement((volatile signed __int32 *)(v25 + 8));
  *(_OWORD *)v89 = *(_OWORD *)a2;
  updated = CMidi2KSAggregateMidiEndpointManager2::UpdateNewPinDefinitions(a1, v89, v137);
  v27 = updated;
  if ( updated < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x184,
      (unsigned int)"avcore\\midi2\\transport\\ksaggregatetransport\\midi2.ksaggregatemidiendpointmanager2.cpp",
      (const char *)(unsigned int)updated,
      v88);
    goto LABEL_57;
  }
  v90 = 0;
  v91 = 0;
  memset_0(v126, 0, 0x54u);
  *(GUID *)v124 = GUID_0f273b18_e372_4d95_87ac_c31c3d22e937;
  v125 = 0;
  v29 = (__int64 *)(*a2 + 64LL);
  if ( *(_QWORD *)(*a2 + 88LL) <= 7u )
    v30 = *a2 + 64LL;
  else
    v30 = *v29;
  v127 = v30;
  v128 = L"KSA";
  if ( (unsigned __int64)v29[3] > 7 )
    v29 = (__int64 *)*v29;
  v129 = v29;
  v130 = 0;
  v131 = 0;
  if ( *(_QWORD *)(v11 + 88) )
  {
    v31 = (_QWORD *)(v11 + 72);
    if ( *(_QWORD *)(v11 + 96) > 7u )
      v31 = (_QWORD *)*v31;
    v132 = v31;
  }
  else
  {
    v132 = 0;
  }
  if ( *(_QWORD *)(v11 + 120) )
  {
    v32 = (_QWORD *)(v11 + 104);
    if ( *(_QWORD *)(v11 + 128) > 7u )
      v32 = (_QWORD *)*v32;
    v133 = v32;
  }
  else
  {
    v133 = 0;
  }
  v134 = 2;
  v135 = 1;
  v136 = 13;
  v104 = 0;
  v105 = 0;
  v108 = 0;
  v109 = 0;
  v117 = 0;
  v118 = 0;
  *(_OWORD *)v89 = 0;
  v33 = a2[1];
  if ( v33 )
    _InterlockedIncrement((volatile signed __int32 *)(v33 + 8));
  *(_OWORD *)v89 = *(_OWORD *)a2;
  v34 = CMidi2KSAggregateMidiEndpointManager2::BuildPinsAndGroupTerminalBlocksPropertyData(a1, v89, &v104, &v108);
  v27 = v34;
  if ( v34 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1A6,
      (unsigned int)"avcore\\midi2\\transport\\ksaggregatetransport\\midi2.ksaggregatemidiendpointmanager2.cpp",
      (const char *)(unsigned int)v34,
      v88);
    std::vector<enum std::byte>::~vector<enum std::byte>(&v117);
    std::vector<PinMapEntryStagingEntry>::~vector<PinMapEntryStagingEntry>(&v108);
    std::vector<enum std::byte>::~vector<enum std::byte>(&v104);
    std::vector<_DEVPROPERTY>::~vector<_DEVPROPERTY>(&v90);
LABEL_57:
    if ( v24 )
    {
      if ( _InterlockedExchangeAdd(v24 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v24)(v24);
        if ( _InterlockedExchangeAdd(v24 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v24 + 8LL))(v24);
      }
    }
    v28 = (volatile signed __int32 *)a2[1];
    if ( v28 )
    {
      if ( _InterlockedExchangeAdd(v28 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v28)(v28);
        if ( _InterlockedExchangeAdd(v28 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v28 + 8LL))(v28);
      }
    }
    return v27;
  }
  v94 = DEVPKEY_KsAggMidiGroupPinMap;
  v95 = 0x10u;
  LODWORD(v96) = 4099;
  DWORD1(v96) = DWORD2(v104) - v104;
  *((_QWORD *)&v96 + 1) = v104;
  v35 = *((_QWORD *)&v90 + 1);
  if ( *((_OWORD **)&v90 + 1) == v91 )
  {
    std::vector<_DEVPROPERTY>::_Emplace_reallocate<_DEVPROPERTY>(&v90, *((_QWORD *)&v90 + 1), &v94);
  }
  else
  {
    **((_OWORD **)&v90 + 1) = DEVPKEY_KsAggMidiGroupPinMap;
    *(_OWORD *)(v35 + 16) = v95;
    *(_OWORD *)(v35 + 32) = v96;
    *((_QWORD *)&v90 + 1) += 48LL;
  }
  v106 = 0;
  v107 = 0;
  v36 = WindowsMidiServicesInternal::WriteGroupTerminalBlocksToPropertyDataPointer(&v108, &v106);
  v37 = *((_QWORD *)&v90 + 1);
  v94 = PKEY_MIDI_GroupTerminalBlocks;
  v95 = 0x32u;
  if ( v36 )
  {
    LODWORD(v96) = 4099;
    DWORD1(v96) = DWORD2(v106) - v106;
    *((_QWORD *)&v96 + 1) = v106;
  }
  else
  {
    v96 = 0u;
  }
  if ( *((_OWORD **)&v90 + 1) == v91 )
  {
    std::vector<_DEVPROPERTY>::_Emplace_reallocate<_DEVPROPERTY>(&v90, *((_QWORD *)&v90 + 1), &v94);
  }
  else
  {
    **((_OWORD **)&v90 + 1) = PKEY_MIDI_GroupTerminalBlocks;
    *(_OWORD *)(v37 + 16) = v95;
    *(_OWORD *)(v37 + 32) = v96;
    *((_QWORD *)&v90 + 1) += 48LL;
  }
  memset_0(&v110, 0, 0x50u);
  v110 = 0u;
  v111 = 0;
  v112 = 0;
  v113 = 0u;
  v114 = 0;
  v115 = 0;
  v116 = 0u;
  v38 = std::wstring::wstring(v145, *a2 + 96LL);
  WindowsMidiServicesInternal::ToUpperTrimmedWStringCopy(&v142, v38);
  v39 = &v142;
  if ( v144 > 7 )
    v39 = (__int128 *)v142;
  *(_QWORD *)v89 = v39;
  *(_QWORD *)&v89[2] = v143;
  winrt::hstring::operator=((char *)&v110 + 8, v89);
  std::wstring::~wstring(&v142);
  v101[0] = v11 + 68;
  LOWORD(v111) = *(_WORD *)(v11 + 68);
  v103 = (_WORD *)(v11 + 70);
  HIWORD(v111) = *(_WORD *)(v11 + 70);
  if ( *(_QWORD *)(v11 + 96) <= 7u )
    v40 = v11 + 72;
  else
    v40 = *(_QWORD *)(v11 + 72);
  *(_QWORD *)v89 = v40;
  *(_QWORD *)&v89[2] = *(_QWORD *)(v11 + 88);
  winrt::hstring::operator=(&v112, v89);
  v41 = *a2;
  if ( *(_QWORD *)(*a2 + 88LL) <= 7u )
    v42 = v41 + 64;
  else
    v42 = *(_QWORD *)(v41 + 64);
  *(_QWORD *)v89 = v42;
  *(_QWORD *)&v89[2] = *(_QWORD *)(v41 + 80);
  winrt::hstring::operator=(&v116, v89);
  v43 = *((_QWORD *)TransportState::Current() + 2);
  *(_QWORD *)v89 = v43;
  if ( v43 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 8LL))(v43);
  v44 = *(_QWORD *)(v43 + 24);
  if ( v44 )
    _InterlockedIncrement((volatile signed __int32 *)(v44 + 8));
  v137[0] = *(_OWORD *)(v43 + 16);
  v45 = (volatile signed __int32 *)*((_QWORD *)&v137[0] + 1);
  WindowsMidiServicesPluginConfigurationLib::MidiEndpointCustomPropertiesCache::GetProperties(
    *(_QWORD *)&v137[0],
    &v142,
    &v110);
  if ( v45 )
  {
    if ( _InterlockedExchangeAdd(v45 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v45)(v45);
      if ( _InterlockedExchangeAdd(v45 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v45 + 8LL))(v45);
    }
  }
  if ( v43 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
  v46 = (volatile signed __int32 *)*((_QWORD *)&v142 + 1);
  if ( *((_QWORD *)&v142 + 1) )
    _InterlockedIncrement((volatile signed __int32 *)(*((_QWORD *)&v142 + 1) + 8LL));
  v47 = v142;
  v137[0] = v142;
  v48 = a2[1];
  if ( v48 )
    _InterlockedIncrement((volatile signed __int32 *)(v48 + 8));
  *(_OWORD *)v89 = *(_OWORD *)a2;
  v49 = CMidi2KSAggregateMidiEndpointManager2::UpdateNameTableWithCustomProperties(a1, v89, v137);
  v50 = v49;
  if ( v49 >= 0 )
  {
    v140 = 0;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(v140) = 0;
    v138 = 0;
    v139 = si128;
    LOWORD(v138) = 0;
    v51 = (unsigned int *)*((_QWORD *)MidiKSAggregateTransportTelemetryProvider::Instance() + 1);
    v54 = *v51;
    if ( (_QWORD)v47 )
    {
      if ( v54 > 5 )
      {
        v93 = *(_DWORD *)(v47 + 56);
        v99 = *(_DWORD *)(v47 + 40);
        v55 = (_QWORD *)(*a2 + 96LL);
        if ( *(_QWORD *)(*a2 + 120LL) > 7u )
          v55 = (_QWORD *)*v55;
        *(_QWORD *)v89 = v55;
        *(_QWORD *)&v137[0] = L"Found custom properties cached for this endpoint";
        v98 = (const wchar_t *)a1;
        *(_QWORD *)v97 = "CMidi2KSAggregateMidiEndpointManager2::DeviceCreateMidiUmpEndpoint";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          (_DWORD)v51,
          (unsigned int)byte_18008AA31,
          v52,
          v53,
          (__int64)v97,
          (__int64)&v98,
          (__int64)v137,
          (__int64)v89,
          (__int64)&v99,
          (__int64)&v93);
      }
      if ( *(_QWORD *)v47 )
      {
        std::wstring::operator=<winrt::hstring,0>(&v140, v47);
        v56 = &v140;
        if ( si128.m128i_i64[1] > 7uLL )
          v56 = (__int128 *)v140;
        *((_QWORD *)&v130 + 1) = v56;
      }
      if ( *(_QWORD *)(v47 + 8) )
      {
        std::wstring::operator=<winrt::hstring,0>(&v138, v47 + 8);
        v57 = &v138;
        if ( v139.m128i_i64[1] > 7uLL )
          v57 = (__int128 *)v138;
        v131 = v57;
      }
      WindowsMidiServicesPluginConfigurationLib::MidiEndpointCustomProperties::WriteNonCommonProperties(v47, &v90);
    }
    else if ( v54 > 5 )
    {
      v58 = (_QWORD *)(*a2 + 96LL);
      if ( *(_QWORD *)(*a2 + 120LL) > 7u )
        v58 = (_QWORD *)*v58;
      *(_QWORD *)v89 = v58;
      *(_QWORD *)&v137[0] = L"No cached custom properties for this endpoint.";
      v98 = (const wchar_t *)a1;
      *(_QWORD *)v97 = "CMidi2KSAggregateMidiEndpointManager2::DeviceCreateMidiUmpEndpoint";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
        (_DWORD)v51,
        (unsigned int)byte_18008A9EB,
        v52,
        v53,
        (__int64)v97,
        (__int64)&v98,
        (__int64)v137,
        (__int64)v89);
    }
    if ( v46 )
      _InterlockedIncrement(v46 + 2);
    v137[0] = v47;
    v59 = a2[1];
    if ( v59 )
      _InterlockedIncrement((volatile signed __int32 *)(v59 + 8));
    *(_OWORD *)v89 = *(_OWORD *)a2;
    v60 = CMidi2KSAggregateMidiEndpointManager2::UpdateNameTableWithCustomProperties(a1, v89, v137);
    v50 = v60;
    if ( v60 >= 0 )
    {
      WindowsMidiServicesNamingLib::MidiEndpointNameTable::WriteProperties(*a2 + 176LL, &v90);
      v61 = *((_QWORD *)&v90 + 1);
      v94 = PKEY_MIDI_UsbVID;
      v95 = 0x36u;
      if ( *(_WORD *)v101[0] )
      {
        *(_QWORD *)&v96 = 0x200000005LL;
        *((_QWORD *)&v96 + 1) = v101[0];
      }
      else
      {
        v96 = 0u;
      }
      if ( *((_OWORD **)&v90 + 1) == v91 )
      {
        std::vector<_DEVPROPERTY>::_Emplace_reallocate<_DEVPROPERTY>(&v90, *((_QWORD *)&v90 + 1), &v94);
        v62 = (_OWORD *)*((_QWORD *)&v90 + 1);
      }
      else
      {
        **((_OWORD **)&v90 + 1) = PKEY_MIDI_UsbVID;
        *(_OWORD *)(v61 + 16) = v95;
        *(_OWORD *)(v61 + 32) = v96;
        v62 = (_OWORD *)(*((_QWORD *)&v90 + 1) + 48LL);
        *((_QWORD *)&v90 + 1) += 48LL;
      }
      v94 = PKEY_MIDI_UsbPID;
      v95 = 0x37u;
      if ( *v103 )
      {
        *(_QWORD *)&v96 = 0x200000005LL;
        *((_QWORD *)&v96 + 1) = v103;
      }
      else
      {
        v96 = 0u;
      }
      if ( v62 == v91 )
      {
        std::vector<_DEVPROPERTY>::_Emplace_reallocate<_DEVPROPERTY>(&v90, v62, &v94);
      }
      else
      {
        *v62 = PKEY_MIDI_UsbPID;
        v62[1] = v95;
        v62[2] = v96;
        *((_QWORD *)&v90 + 1) += 48LL;
      }
      v94 = PKEY_MIDI_EndpointDiscoveryProcessComplete;
      v95 = 0x8Cu;
      *(_QWORD *)&v96 = 0x100000011LL;
      *((_QWORD *)&v96 + 1) = &v92;
      v63 = *((_QWORD *)&v90 + 1);
      if ( *((_OWORD **)&v90 + 1) == v91 )
      {
        std::vector<_DEVPROPERTY>::_Emplace_reallocate<_DEVPROPERTY>(&v90, *((_QWORD *)&v90 + 1), &v94);
      }
      else
      {
        **((_OWORD **)&v90 + 1) = PKEY_MIDI_EndpointDiscoveryProcessComplete;
        *(_OWORD *)(v63 + 16) = v95;
        *(_OWORD *)(v63 + 32) = v96;
        *((_QWORD *)&v90 + 1) += 48LL;
      }
      memset_0(&v120, 0, 0x48u);
      v120 = 72;
      v64 = *a2;
      v65 = (_QWORD *)(*a2 + 96LL);
      if ( *(_QWORD *)(*a2 + 120LL) > 7u )
        v65 = (_QWORD *)*v65;
      v121 = v65;
      v122 = 0;
      v66 = (_QWORD *)(v64 + 64);
      if ( *(_QWORD *)(v64 + 88) > 7u )
        v66 = (_QWORD *)*v66;
      v123 = v66;
      pv = 0;
      v67 = (_DWORD *)*((_QWORD *)MidiKSAggregateTransportTelemetryProvider::Instance() + 1);
      if ( *v67 > 4u )
      {
        v70 = (_QWORD *)(*a2 + 64LL);
        if ( *(_QWORD *)(*a2 + 88LL) > 7u )
          v70 = (_QWORD *)*v70;
        *(_QWORD *)v89 = v70;
        *(_QWORD *)&v137[0] = L"Activating endpoint";
        v98 = (const wchar_t *)a1;
        *(_QWORD *)v97 = "CMidi2KSAggregateMidiEndpointManager2::DeviceCreateMidiUmpEndpoint";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
          (_DWORD)v67,
          (unsigned int)byte_18008A9B3,
          v68,
          v69,
          (__int64)v97,
          (__int64)&v98,
          (__int64)v137,
          (__int64)v89);
      }
      v71 = *(_QWORD *)(a1 + 32);
      *(_QWORD *)v89 = v71;
      v72 = *(__int64 (__fastcall **)(__int64, _QWORD *, _QWORD, __int64))(*(_QWORD *)v71 + 40LL);
      *(_QWORD *)&v137[0] = v72;
      v73 = pv;
      if ( pv )
      {
        LastError = GetLastError();
        CoTaskMemFree(v73);
        SetLastError(LastError);
        v71 = *(_QWORD *)v89;
        v72 = *(__int64 (__fastcall **)(__int64, _QWORD *, _QWORD, __int64))&v137[0];
      }
      pv = 0;
      v75 = (_QWORD *)(v102 + 32);
      if ( *(_QWORD *)(v102 + 56) > 7u )
        v75 = (_QWORD *)*v75;
      v76 = v72(v71, v75, 0, 2);
      v50 = v76;
      if ( v76 >= 0 )
      {
        EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 184));
        v103 = (_WORD *)(a1 + 184);
        v80 = (_DWORD *)*((_QWORD *)MidiKSAggregateTransportTelemetryProvider::Instance() + 1);
        if ( *v80 > 4u )
        {
          *(_QWORD *)v89 = pv;
          v83 = (_QWORD *)(*a2 + 64LL);
          if ( *(_QWORD *)(*a2 + 88LL) > 7u )
            v83 = (_QWORD *)*v83;
          *(_QWORD *)&v137[0] = v83;
          v98 = L"Aggregate UMP endpoint created";
          *(_QWORD *)v97 = a1;
          v101[0] = "CMidi2KSAggregateMidiEndpointManager2::DeviceCreateMidiUmpEndpoint";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
            (_DWORD)v80,
            (unsigned int)&byte_18008A957,
            v81,
            v82,
            (__int64)v101,
            (__int64)v97,
            (__int64)&v98,
            (__int64)v137,
            (__int64)v89);
        }
        memset(v137, 0, sizeof(v137));
        v84 = -1;
        do
          ++v84;
        while ( *((_WORD *)pv + v84) );
        std::wstring::_Construct<1,unsigned short const *>(v137);
        v85 = std::wstring::wstring(&v94, v137);
        WindowsMidiServicesInternal::ToLowerTrimmedWStringCopy(v145, v85);
        std::wstring::operator=(*a2 + 32LL, v145);
        std::wstring::~wstring(v145);
        std::wstring::~wstring(v137);
        v86 = std::wstring::wstring(&v94, *a2 + 96LL);
        WindowsMidiServicesInternal::ToUpperTrimmedWStringCopy(v145, v86);
        std::map<std::wstring,std::shared_ptr<KsAggregateEndpointDefinition2>>::_Insert_or_assign<std::wstring,std::shared_ptr<KsAggregateEndpointDefinition2> &>(
          a1 + 168,
          v89,
          v145,
          a2);
        std::wstring::~wstring(v145);
        if ( a1 != -184 )
          LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 184));
      }
      else
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x245,
          (unsigned int)"avcore\\midi2\\transport\\ksaggregatetransport\\midi2.ksaggregatemidiendpointmanager2.cpp",
          (const char *)(unsigned int)v76,
          (int)v124);
        v77 = (_DWORD *)*((_QWORD *)MidiKSAggregateTransportTelemetryProvider::Instance() + 1);
        if ( *v77 > 2u )
        {
          v93 = v50;
          v79 = (_QWORD *)(*a2 + 64LL);
          if ( *(_QWORD *)(*a2 + 88LL) > 7u )
            v79 = (_QWORD *)*v79;
          *(_QWORD *)v89 = v79;
          *(_QWORD *)&v137[0] = L"Aggregate UMP endpoint creation failed";
          v98 = (const wchar_t *)a1;
          *(_QWORD *)v97 = "CMidi2KSAggregateMidiEndpointManager2::DeviceCreateMidiUmpEndpoint";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
            (_DWORD)v77,
            (unsigned int)&dword_18008A914,
            (_DWORD)v77,
            v78,
            (__int64)v97,
            (__int64)&v98,
            (__int64)v137,
            (__int64)v89,
            (__int64)&v93);
        }
      }
      if ( pv )
        CoTaskMemFree(pv);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1FC,
        (unsigned int)"avcore\\midi2\\transport\\ksaggregatetransport\\midi2.ksaggregatemidiendpointmanager2.cpp",
        (const char *)(unsigned int)v60,
        v88);
    }
    std::wstring::~wstring(&v138);
    std::wstring::~wstring(&v140);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1CC,
      (unsigned int)"avcore\\midi2\\transport\\ksaggregatetransport\\midi2.ksaggregatemidiendpointmanager2.cpp",
      (const char *)(unsigned int)v49,
      v88);
  }
  if ( v46 )
  {
    if ( _InterlockedExchangeAdd(v46 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v46)(v46);
      if ( _InterlockedExchangeAdd(v46 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v46 + 8LL))(v46);
    }
  }
  WindowsMidiServicesPluginConfigurationLib::MidiEndpointMatchCriteria::~MidiEndpointMatchCriteria((WindowsMidiServicesPluginConfigurationLib::MidiEndpointMatchCriteria *)&v110);
  std::vector<enum std::byte>::~vector<enum std::byte>(&v106);
  std::vector<enum std::byte>::~vector<enum std::byte>(&v117);
  std::vector<PinMapEntryStagingEntry>::~vector<PinMapEntryStagingEntry>(&v108);
  std::vector<enum std::byte>::~vector<enum std::byte>(&v104);
  std::vector<_DEVPROPERTY>::~vector<_DEVPROPERTY>(&v90);
  if ( v24 )
  {
    if ( _InterlockedExchangeAdd(v24 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v24)(v24);
      if ( _InterlockedExchangeAdd(v24 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v24 + 8LL))(v24);
    }
  }
  v87 = (volatile signed __int32 *)a2[1];
  if ( v87 )
  {
    if ( _InterlockedExchangeAdd(v87 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v87)(v87);
      if ( _InterlockedExchangeAdd(v87 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v87 + 8LL))(v87);
    }
  }
  return v50;
}

```

## disassembly

```asm
0x180036d5c  mov     rax, rsp
0x180036d5f  mov     [rax+18h], rbx
0x180036d63  push    rbp
0x180036d64  push    rsi
0x180036d65  push    rdi
0x180036d66  push    r12
0x180036d68  push    r13
0x180036d6a  push    r14
0x180036d6c  push    r15
0x180036d6e  lea     rbp, [rax-278h]
0x180036d75  sub     rsp, 340h
0x180036d7c  movaps  xmmword ptr [rax-48h], xmm6
0x180036d80  mov     rax, cs:__security_cookie
0x180036d87  xor     rax, rsp
0x180036d8a  mov     [rbp+270h+var_50], rax
0x180036d91  mov     r15, rdx
0x180036d94  mov     r13, rcx
0x180036d97  mov     [rbp+270h+var_1B8], rdx
0x180036d9e  xor     r12d, r12d
0x180036da1  cmp     [rdx], r12
0x180036da4  jnz     short loc_180036E0E
0x180036da6  mov     rcx, [rbp+278h]; this
0x180036dad  mov     r9d, 80070057h; char *
0x180036db3  lea     r8, aAvcoreMidi2Tra_4; "avcore\\midi2\\transport\\ksaggregatetr"...
0x180036dba  mov     edx, 167h; void *
0x180036dbf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180036dc4  nop
0x180036dc5  mov     rbx, [r15+8]
0x180036dc9  test    rbx, rbx
0x180036dcc  jz      loc_180037165
0x180036dd2  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180036dd6  mov     eax, edi
0x180036dd8  lock xadd [rbx+8], eax
0x180036ddd  add     eax, edi
0x180036ddf  jnz     loc_180037165
0x180036de5  mov     rax, [rbx]
0x180036de8  mov     rcx, rbx
0x180036deb  mov     rax, [rax]
0x180036dee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036df3  mov     eax, edi
0x180036df5  lock xadd [rbx+0Ch], eax
0x180036dfa  add     eax, edi
0x180036dfc  jnz     loc_180037165
0x180036e02  mov     rax, [rbx]
0x180036e05  mov     rax, [rax+8]
0x180036e09  jmp     loc_18003715D
0x180036e0e  xorps   xmm0, xmm0
0x180036e11  movdqa  [rbp+270h+var_280], xmm0
0x180036e16  movdqu  xmmword ptr [rsp+370h+var_318+8], xmm0
0x180036e1c  mov     rax, [rdx+8]
0x180036e20  test    rax, rax
0x180036e23  jz      short loc_180036E29
0x180036e25  lock inc dword ptr [rax+8]
0x180036e29  mov     rax, [rdx]
0x180036e2c  mov     qword ptr [rsp+370h+var_318+8], rax
0x180036e31  mov     rax, [rdx+8]
0x180036e35  mov     qword ptr [rsp+370h+var_308], rax
0x180036e3a  lea     r8, [rbp+270h+var_280]
0x180036e3e  lea     rdx, [rsp+370h+var_318+8]
0x180036e43  call    ?FindExistingParentDeviceDefinitionForEndpoint@CMidi2KSAggregateMidiEndpointManager2@@AEAAJV?$shared_ptr@UKsAggregateEndpointDefinition2@@@std@@AEAV?$shared_ptr@VKsAggregateParentDeviceDefinition2@@@3@@Z; CMidi2KSAggregateMidiEndpointManager2::FindExistingParentDeviceDefinitionForEndpoint(std::shared_ptr<KsAggregateEndpointDefinition2>,std::shared_ptr<KsAggregateParentDeviceDefinition2> &)
0x180036e48  mov     esi, eax
0x180036e4a  test    eax, eax
0x180036e4c  jns     loc_180036EF2
0x180036e52  mov     edx, 16Ah; void *
0x180036e57  mov     r9d, esi; char *
0x180036e5a  lea     r8, aAvcoreMidi2Tra_4; "avcore\\midi2\\transport\\ksaggregatetr"...
0x180036e61  mov     rcx, [rbp+278h]; this
0x180036e68  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180036e6d  nop
0x180036e6e  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180036e72  mov     rbx, qword ptr [rbp+270h+var_280+8]
0x180036e76  test    rbx, rbx
0x180036e79  jz      short loc_180036EAF
0x180036e7b  mov     eax, edi
0x180036e7d  lock xadd [rbx+8], eax
0x180036e82  add     eax, edi
0x180036e84  jnz     short loc_180036EAF
0x180036e86  mov     rax, [rbx]
0x180036e89  mov     rcx, rbx
0x180036e8c  mov     rax, [rax]
0x180036e8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036e94  mov     eax, edi
0x180036e96  lock xadd [rbx+0Ch], eax
0x180036e9b  add     eax, edi
0x180036e9d  jnz     short loc_180036EAF
0x180036e9f  mov     rax, [rbx]
0x180036ea2  mov     rcx, rbx
0x180036ea5  mov     rax, [rax+8]
0x180036ea9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036eae  nop
0x180036eaf  mov     rbx, [r15+8]
0x180036eb3  test    rbx, rbx
0x180036eb6  jz      short loc_180036EEB
0x180036eb8  mov     eax, edi
0x180036eba  lock xadd [rbx+8], eax
0x180036ebf  add     eax, edi
0x180036ec1  jnz     short loc_180036EEB
0x180036ec3  mov     rax, [rbx]
0x180036ec6  mov     rcx, rbx
0x180036ec9  mov     rax, [rax]
0x180036ecc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036ed1  mov     eax, edi
0x180036ed3  lock xadd [rbx+0Ch], eax
0x180036ed8  add     eax, edi
0x180036eda  jnz     short loc_180036EEB
0x180036edc  mov     rax, [rbx]
0x180036edf  mov     rcx, rbx
0x180036ee2  mov     rax, [rax+8]
0x180036ee6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036eeb  mov     eax, esi
0x180036eed  jmp     loc_180037FB6
0x180036ef2  mov     rbx, qword ptr [rbp+270h+var_280]
0x180036ef6  test    rbx, rbx
0x180036ef9  jnz     short loc_180036F0A
0x180036efb  mov     esi, 8000FFFFh
0x180036f00  mov     edx, 16Bh
0x180036f05  jmp     loc_180036E57
0x180036f0a  call    ?Instance@MidiKSAggregateTransportTelemetryProvider@@KAPEAV1@XZ; MidiKSAggregateTransportTelemetryProvider::Instance(void)
0x180036f0f  mov     r8, [rax+8]
0x180036f13  mov     eax, [r8]
0x180036f16  lea     rdx, aCmidi2ksaggreg_3; "CMidi2KSAggregateMidiEndpointManager2::"...
0x180036f1d  cmp     eax, 4
0x180036f20  jbe     loc_180036FFC
0x180036f26  mov     rcx, [r15]
0x180036f29  mov     rax, [rcx+0A0h]
0x180036f30  sub     rax, [rcx+98h]
0x180036f37  sar     rax, 4
0x180036f3b  mov     [rbp+270h+var_2A0], eax
0x180036f3e  mov     rax, [rcx+88h]
0x180036f45  sub     rax, [rcx+80h]
0x180036f4c  sar     rax, 4
0x180036f50  mov     [rbp+270h+var_2E4], eax
0x180036f53  cmp     qword ptr [rbx+18h], 7
0x180036f58  jbe     short loc_180036F5F
0x180036f5a  mov     rax, [rbx]
0x180036f5d  jmp     short loc_180036F62
0x180036f5f  mov     rax, rbx
0x180036f62  mov     [rbp+270h+var_270], rax
0x180036f66  lea     rax, [rcx+40h]
0x180036f6a  cmp     qword ptr [rax+18h], 7
0x180036f6f  jbe     short loc_180036F74
0x180036f71  mov     rax, [rax]
0x180036f74  mov     [rbp+270h+var_290], rax
0x180036f78  add     rcx, 60h ; '`'
0x180036f7c  cmp     qword ptr [rcx+18h], 7
0x180036f81  jbe     short loc_180036F86
0x180036f83  mov     rcx, [rcx]
0x180036f86  mov     qword ptr [rbp+270h+var_2B0], rcx
0x180036f8a  lea     rax, aEnter_0; "Enter"
0x180036f91  mov     [rbp+270h+var_2A8], rax
0x180036f95  mov     qword ptr [rbp+270h+var_F0], r13
0x180036f9c  mov     qword ptr [rsp+370h+var_318+8], rdx
0x180036fa1  lea     rax, [rbp+270h+var_2A0]
0x180036fa5  mov     qword ptr [rsp+370h+var_318], rax
0x180036faa  lea     rax, [rbp+270h+var_2E4]
0x180036fae  mov     [rsp+370h+var_320], rax
0x180036fb3  lea     rax, [rbp+270h+var_270]
0x180036fb7  mov     [rsp+370h+var_328], rax
0x180036fbc  lea     rax, [rbp+270h+var_290]
0x180036fc0  mov     [rsp+370h+var_330], rax
0x180036fc5  lea     rax, [rbp+270h+var_2B0]
0x180036fc9  mov     [rsp+370h+var_338], rax
0x180036fce  lea     rax, [rbp+270h+var_2A8]
0x180036fd2  mov     [rsp+370h+var_340], rax
0x180036fd7  lea     rax, [rbp+270h+var_F0]
0x180036fde  mov     [rsp+370h+var_348], rax
0x180036fe3  lea     rax, [rsp+370h+var_318+8]
0x180036fe8  mov     qword ptr [rsp+370h+var_350], rax; int
0x180036fed  lea     rdx, word_18008AAA6
0x180036ff4  mov     rcx, r8
0x180036ff7  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U3@U3@U3@U?$_tlgWrapperByVal@$03@@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@555AEBU?$_tlgWrapperByVal@$03@@6@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180036ffc  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180037000  mov     [rbp+270h+var_2E8], dil
0x180037004  mov     rcx, [r15]
0x180037007  mov     rdx, [rcx+80h]
0x18003700e  mov     r8, [rcx+88h]
0x180037015  mov     rax, r8
0x180037018  sub     rax, rdx
0x18003701b  sar     rax, 4
0x18003701f  cmp     rax, 10h
0x180037023  jbe     short loc_180037093
0x180037025  mov     edx, 17Eh; void *
0x18003702a  mov     r9d, 80070057h; char *
0x180037030  lea     r8, aAvcoreMidi2Tra_4; "avcore\\midi2\\transport\\ksaggregatetr"...
0x180037037  mov     rcx, [rbp+278h]; this
0x18003703e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180037043  nop
0x180037044  mov     rbx, qword ptr [rbp+270h+var_280+8]
0x180037048  test    rbx, rbx
0x18003704b  jz      short loc_180037081
0x18003704d  mov     eax, edi
0x18003704f  lock xadd [rbx+8], eax
0x180037054  add     eax, edi
0x180037056  jnz     short loc_180037081
0x180037058  mov     rax, [rbx]
0x18003705b  mov     rcx, rbx
0x18003705e  mov     rax, [rax]
0x180037061  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037066  mov     eax, edi
0x180037068  lock xadd [rbx+0Ch], eax
0x18003706d  add     eax, edi
0x18003706f  jnz     short loc_180037081
0x180037071  mov     rax, [rbx]
0x180037074  mov     rcx, rbx
0x180037077  mov     rax, [rax+8]
0x18003707b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037080  nop
0x180037081  mov     rbx, [r15+8]
0x180037085  test    rbx, rbx
0x180037088  jz      loc_180037165
0x18003708e  jmp     loc_180036DD6
0x180037093  mov     r9, [rcx+98h]
0x18003709a  mov     r10, [rcx+0A0h]
0x1800370a1  mov     rax, r10
0x1800370a4  sub     rax, r9
0x1800370a7  sar     rax, 4
0x1800370ab  cmp     rax, 10h
0x1800370af  jbe     short loc_1800370BB
0x1800370b1  mov     edx, 17Fh
0x1800370b6  jmp     loc_18003702A
0x1800370bb  cmp     rdx, r8
0x1800370be  jnz     loc_18003716F
0x1800370c4  cmp     r9, r10
0x1800370c7  jnz     loc_18003716F
0x1800370cd  mov     rcx, [rbp+278h]; this
0x1800370d4  mov     r9d, 80070057h; char *
0x1800370da  lea     r8, aAvcoreMidi2Tra_4; "avcore\\midi2\\transport\\ksaggregatetr"...
0x1800370e1  mov     edx, 180h; void *
0x1800370e6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800370eb  nop
0x1800370ec  mov     rbx, qword ptr [rbp+270h+var_280+8]
0x1800370f0  test    rbx, rbx
0x1800370f3  jz      short loc_180037129
0x1800370f5  mov     eax, edi
0x1800370f7  lock xadd [rbx+8], eax
0x1800370fc  add     eax, edi
0x1800370fe  jnz     short loc_180037129
0x180037100  mov     rax, [rbx]
0x180037103  mov     rcx, rbx
0x180037106  mov     rax, [rax]
0x180037109  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003710e  mov     eax, edi
0x180037110  lock xadd [rbx+0Ch], eax
0x180037115  add     eax, edi
0x180037117  jnz     short loc_180037129
0x180037119  mov     rax, [rbx]
0x18003711c  mov     rcx, rbx
0x18003711f  mov     rax, [rax+8]
0x180037123  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037128  nop
0x180037129  mov     rbx, [r15+8]
0x18003712d  test    rbx, rbx
0x180037130  jz      short loc_180037165
0x180037132  mov     eax, edi
0x180037134  lock xadd [rbx+8], eax
0x180037139  add     eax, edi
0x18003713b  jnz     short loc_180037165
0x18003713d  mov     rax, [rbx]
0x180037140  mov     rcx, rbx
0x180037143  mov     rax, [rax]
0x180037146  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003714b  mov     edx, edi
0x18003714d  lock xadd [rbx+0Ch], edx
0x180037152  add     edx, edi
0x180037154  jnz     short loc_180037165
0x180037156  mov     rdx, [rbx]
0x180037159  mov     rax, [rdx+8]
0x18003715d  mov     rcx, rbx
0x180037160  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037165  mov     eax, 80070057h
0x18003716a  jmp     loc_180037FB6
0x18003716f  xorps   xmm0, xmm0
0x180037172  movdqa  [rbp+270h+var_F0], xmm0
0x18003717a  mov     rsi, qword ptr [rbp+270h+var_280+8]
0x18003717e  test    rsi, rsi
0x180037181  jz      short loc_180037187
0x180037183  lock inc dword ptr [rsi+8]
0x180037187  movaps  xmm0, [rbp+270h+var_280]
0x18003718b  movdqa  [rbp+270h+var_F0], xmm0
0x180037193  xorps   xmm0, xmm0
0x180037196  movdqu  xmmword ptr [rsp+370h+var_318+8], xmm0
0x18003719c  mov     rax, [r15+8]
0x1800371a0  test    rax, rax
0x1800371a3  jz      short loc_1800371A9
0x1800371a5  lock inc dword ptr [rax+8]
0x1800371a9  mov     rax, [r15]
0x1800371ac  mov     qword ptr [rsp+370h+var_318+8], rax
0x1800371b1  mov     rax, [r15+8]
0x1800371b5  mov     qword ptr [rsp+370h+var_308], rax
0x1800371ba  lea     r8, [rbp+270h+var_F0]
0x1800371c1  lea     rdx, [rsp+370h+var_318+8]
0x1800371c6  mov     rcx, r13
0x1800371c9  call    ?UpdateNewPinDefinitions@CMidi2KSAggregateMidiEndpointManager2@@AEAAJV?$shared_ptr@UKsAggregateEndpointDefinition2@@@std@@V?$shared_ptr@VKsAggregateParentDeviceDefinition2@@@3@@Z; CMidi2KSAggregateMidiEndpointManager2::UpdateNewPinDefinitions(std::shared_ptr<KsAggregateEndpointDefinition2>,std::shared_ptr<KsAggregateParentDeviceDefinition2>)
0x1800371ce  mov     r14d, eax
0x1800371d1  test    eax, eax
0x1800371d3  jns     loc_180037272
0x1800371d9  mov     rcx, [rbp+278h]; this
0x1800371e0  mov     r9d, eax; char *
0x1800371e3  lea     r8, aAvcoreMidi2Tra_4; "avcore\\midi2\\transport\\ksaggregatetr"...
0x1800371ea  mov     edx, 184h; void *
  ... truncated ...
```
