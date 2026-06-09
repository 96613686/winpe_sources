# CMidiDeviceManager::ActivateEndpoint(ushort const *,int,__MIDL___MIDL_itf_windowsmidiservices_0000_0000_0002,__MIDL___MIDL_itf_windowsmidiservices_0000_0005_0003 * const,ulong,ulong,_DEVPROPERTY const *,_DEVPROPERTY const *,_SW_DEVICE_CREATE_INFO const *,ushort * *)

- ea: `0x140029640`
- end: `0x14002b197`
- name: `?ActivateEndpoint@CMidiDeviceManager@@UEAAJPEBGHW4__MIDL___MIDL_itf_windowsmidiservices_0000_0000_0002@@QEAU__MIDL___MIDL_itf_windowsmidiservices_0000_0005_0003@@KKPEBU_DEVPROPERTY@@3PEBU_SW_DEVICE_CREATE_INFO@@PEAPEAG@Z`
- size: `6999`
- prototype: `__int64 __fastcall(__int64, const char *, int, int, __int64, unsigned int, int, __int64, const char *, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `20`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x14000179c`
- `0x1400019d8`
- `0x140001ce8`
- `0x140001f28`
- `0x14000298c`
- `0x1400054c0`
- `0x140007c20`
- `0x14000984c`
- `0x14000a6b4`
- `0x14000c598`
- `0x14001f95c`
- `0x14002663c`
- `0x1400274d8`
- `0x140028c74`
- `0x140029064`
- `0x140029640`
- `0x14002b1a0`
- `0x140032ff4`
- `0x140035ae0`
- `0x14005a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1400298e0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14002a57c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14002b093`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14002b165`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1400298e0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14002a57c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14002b093`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14002b165`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1400297e6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1400297e6`

## string_xrefs

- `0x14002b04f`: `avcore\midi2\service\exe\mididevicemanager.cpp`
- `0x14002b0d0`: `avcore\midi2\service\exe\mididevicemanager.cpp`
- `0x14002b119`: `avcore\midi2\service\exe\mididevicemanager.cpp`
- `0x1400299f7`: `Common properties object supplied`
- `0x14002a51e`: `Common Properties: Friendly Name is null or empty`
- `0x140029883`: `Already Activated`
- `0x14002a4f2`: `Common Properties: Transport Code is null or empty`
- `0x14002a591`: `NO Common properties object supplied`

## pseudocode

```c
__int64 __fastcall CMidiDeviceManager::ActivateEndpoint(
        __int64 a1,
        const char *a2,
        int a3,
        int a4,
        __int64 a5,
        unsigned int a6,
        int a7,
        __int64 a8,
        const char *a9,
        __int64 a10,
        _QWORD *a11)
{
  _DWORD *v14; // r10
  __int64 v15; // r15
  __int64 v16; // r13
  const wchar_t *v17; // rcx
  __int64 v18; // rax
  int v19; // eax
  __int64 v20; // rbx
  __int64 v21; // rdi
  __int64 v22; // r13
  const wchar_t *v23; // rdx
  const wchar_t *v24; // rcx
  __int64 v25; // rax
  size_t v26; // r8
  _DWORD *v27; // rcx
  __int64 v28; // r8
  __int64 v29; // r9
  _DWORD *v31; // rcx
  __int64 v32; // r8
  __int64 v33; // r9
  const char *v34; // rbx
  unsigned int *v35; // rcx
  __int64 v36; // r8
  __int64 v37; // r9
  unsigned int v38; // eax
  const char *v39; // rbx
  __int64 v40; // rdx
  __int128 *v41; // rdx
  __int64 v42; // rdx
  __int64 v43; // r8
  __int64 v44; // rcx
  __int128 *v45; // rdx
  __int64 v46; // r8
  __int64 v47; // rcx
  __int128 *v48; // rdx
  __int64 v49; // r8
  __int64 v50; // rcx
  _DWORD *v51; // rcx
  __int64 v52; // r8
  __int64 v53; // r9
  __int64 v54; // rdx
  __int64 v55; // rcx
  _DWORD *v56; // rcx
  __int64 v57; // r8
  __int64 v58; // r9
  __int64 v59; // rdx
  __int64 v60; // rdx
  __int64 v61; // rcx
  _DWORD *v62; // rcx
  __int64 v63; // r8
  __int64 v64; // r9
  __int64 v65; // rdx
  __int64 v66; // rdx
  __int64 v67; // rcx
  _DWORD *v68; // rcx
  __int64 v69; // r8
  __int64 v70; // r9
  __int64 v71; // rdx
  __int64 v72; // rdx
  __int64 v73; // rcx
  _DWORD *v74; // rcx
  __int64 v75; // r8
  __int64 v76; // r9
  __int64 v77; // rdx
  __int64 v78; // rcx
  _DWORD *v79; // rcx
  __int64 v80; // r8
  __int64 v81; // r9
  __int64 v82; // rdx
  _DWORD *v83; // rcx
  __int64 v84; // r8
  __int64 v85; // r9
  __int64 v86; // rdx
  __int128 *v87; // rdx
  __int128 *v88; // rdx
  char *v89; // rax
  __int128 *v90; // rdx
  char *v91; // rax
  __int128 *v92; // rdx
  char *v93; // rax
  __int128 *v94; // rdx
  char *v95; // rax
  _DWORD *v96; // rcx
  __int64 v97; // r8
  __int64 v98; // r9
  char *v99; // rdx
  _DWORD *v100; // rcx
  __int64 v101; // r8
  __int64 v102; // r9
  const char *v103; // rdi
  __int64 v104; // rdx
  __int128 *v105; // rdx
  __int128 *v106; // rdx
  __int128 *v107; // rdx
  __int128 *v108; // rdx
  __int128 *v109; // rdx
  __int128 *v110; // rdx
  __int128 *v111; // rdx
  __int128 *v112; // rdx
  __int128 *v113; // rdx
  __int128 *v114; // rdx
  __int128 *v115; // rdx
  __int128 *v116; // rdx
  __int128 *v117; // rdx
  __int128 *v118; // rdx
  __int128 *v119; // rdx
  __int128 *v120; // rdx
  __int128 *v121; // rdx
  __int128 *v122; // rdx
  _DWORD *v123; // rcx
  __int64 v124; // r8
  __int64 v125; // r9
  int v126; // ebx
  __int128 v127; // xmm2
  __int128 v128; // xmm3
  __int64 v129; // rdx
  __int128 *v130; // rdx
  _DWORD *v131; // rcx
  __int64 v132; // r8
  __int64 v133; // r9
  _DWORD *v134; // rcx
  __int64 v135; // r8
  __int64 v136; // r9
  __int64 v137; // rsi
  int v138; // ebx
  unsigned __int64 v139; // r8
  _DWORD *v140; // r8
  __int64 v141; // r9
  int v142; // edx
  int v143; // eax
  _QWORD *v144; // rbx
  const unsigned __int16 *v145; // rdx
  int v146; // [rsp+20h] [rbp-E0h]
  __int128 v147; // [rsp+70h] [rbp-90h] BYREF
  __int128 *v148; // [rsp+80h] [rbp-80h]
  DEVPROPGUID fmtid; // [rsp+88h] [rbp-78h] BYREF
  __int128 pid; // [rsp+98h] [rbp-68h]
  __int128 v151; // [rsp+A8h] [rbp-58h]
  char v152; // [rsp+B8h] [rbp-48h] BYREF
  _BYTE v153[7]; // [rsp+B9h] [rbp-47h] BYREF
  const wchar_t *v154; // [rsp+C0h] [rbp-40h] BYREF
  const wchar_t *v155; // [rsp+C8h] [rbp-38h] BYREF
  const char *v156; // [rsp+D0h] [rbp-30h] BYREF
  const char *v157; // [rsp+D8h] [rbp-28h] BYREF
  const char *v158; // [rsp+E0h] [rbp-20h] BYREF
  int v159[2]; // [rsp+E8h] [rbp-18h] BYREF
  struct _MIDIPORT *v160; // [rsp+F0h] [rbp-10h] BYREF
  const char *v161; // [rsp+F8h] [rbp-8h] BYREF
  __int64 v162; // [rsp+100h] [rbp+0h] BYREF
  __int64 v163; // [rsp+108h] [rbp+8h] BYREF
  const char *v164; // [rsp+110h] [rbp+10h] BYREF
  _QWORD *v165; // [rsp+118h] [rbp+18h] BYREF
  unsigned __int16 *v166[2]; // [rsp+128h] [rbp+28h] BYREF
  __m128i si128; // [rsp+138h] [rbp+38h]
  const char *v168; // [rsp+170h] [rbp+70h]
  __int64 v169; // [rsp+178h] [rbp+78h]
  const wchar_t **v170; // [rsp+180h] [rbp+80h]
  __int64 v171; // [rsp+188h] [rbp+88h]
  const wchar_t *v172; // [rsp+190h] [rbp+90h]
  __int64 v173; // [rsp+198h] [rbp+98h]
  const wchar_t *v174; // [rsp+1A0h] [rbp+A0h]
  int v175; // [rsp+1A8h] [rbp+A8h]
  int v176; // [rsp+1ACh] [rbp+ACh]
  const char **v177; // [rsp+1B0h] [rbp+B0h]
  __int64 v178; // [rsp+1B8h] [rbp+B8h]
  const char **v179; // [rsp+1C0h] [rbp+C0h]
  __int64 v180; // [rsp+1C8h] [rbp+C8h]
  struct _MIDIPORT **v181; // [rsp+1D0h] [rbp+D0h]
  __int64 v182; // [rsp+1D8h] [rbp+D8h]
  __int64 *v183; // [rsp+1E0h] [rbp+E0h]
  __int64 v184; // [rsp+1E8h] [rbp+E8h]
  wil::details::in1diag3 *retaddr; // [rsp+238h] [rbp+138h]

  LODWORD(v161) = a4;
  LODWORD(v163) = a3;
  v157 = a2;
  v164 = a9;
  *(_QWORD *)v159 = a10;
  v165 = a11;
  v14 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
  v15 = -1;
  v16 = a5;
  if ( *v14 > 4u )
  {
    LODWORD(v162) = a3;
    LODWORD(v160) = a7;
    LODWORD(v158) = a6;
    LODWORD(v156) = a5 != 0;
    v154 = (const wchar_t *)a1;
    v183 = &v162;
    v184 = 4;
    v181 = &v160;
    v182 = 4;
    v179 = &v158;
    v180 = 4;
    v177 = &v156;
    v178 = 4;
    if ( a2 )
    {
      v17 = (const wchar_t *)a2;
      v18 = -1;
      do
        ++v18;
      while ( *(_WORD *)&a2[2 * v18] );
      v19 = 2 * v18 + 2;
    }
    else
    {
      v17 = &S2;
      v19 = 2;
    }
    v174 = v17;
    v175 = v19;
    v176 = 0;
    v172 = L"Enter";
    v173 = 12;
    v170 = &v154;
    v171 = 8;
    v168 = "CMidiDeviceManager::ActivateEndpoint";
    v169 = 37;
    tlgWriteTransfer_EventWriteTransfer(v14, word_140089FF2, 0, 0);
  }
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 96));
  v20 = *(_QWORD *)(a1 + 136);
  v21 = *(_QWORD *)(a1 + 144);
  if ( v20 != v21 )
  {
    v22 = *(_QWORD *)v159;
    do
    {
      v23 = *(const wchar_t **)(v22 + 8);
      v24 = (const wchar_t *)(*(_QWORD *)v20 + 48LL);
      v25 = -1;
      do
        ++v25;
      while ( v23[v25] );
      v26 = *(_QWORD *)(*(_QWORD *)v20 + 64LL);
      if ( *(_QWORD *)(*(_QWORD *)v20 + 72LL) > 7u )
        v24 = *(const wchar_t **)v24;
      if ( v26 == v25 && (!v26 || !wmemcmp(v24, v23, v26)) )
        break;
      v20 += 8;
    }
    while ( v20 != v21 );
    v16 = a5;
  }
  if ( v20 != *(_QWORD *)(a1 + 144) )
  {
    v27 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
    if ( *v27 > 4u )
    {
      v154 = *(const wchar_t **)(*(_QWORD *)v159 + 8LL);
      *(_QWORD *)v159 = v157;
      v157 = (const char *)L"Already Activated";
      v163 = a1;
      v161 = "CMidiDeviceManager::ActivateEndpoint";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
        (__int64)v27,
        (__int64)byte_140088D95,
        v28,
        v29,
        &v161,
        (__int64)&v163,
        &v157,
        v159,
        &v154);
    }
    if ( a1 != -96 )
      LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 96));
    return 1;
  }
  v147 = 0;
  v148 = 0;
  if ( a6 && a8 )
  {
    std::vector<_DEVPROPERTY>::vector<_DEVPROPERTY>(&fmtid, a8, a8 + 48LL * a6);
    std::vector<_DEVPROPERTY>::operator=(&v147, &fmtid);
    v31 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
    if ( *v31 <= 4u )
    {
      v34 = v157;
    }
    else
    {
      LODWORD(v156) = -1431655765 * ((__int64)(*((_QWORD *)&v147 + 1) - v147) >> 4);
      LODWORD(v158) = a6;
      v34 = v157;
      v154 = (const wchar_t *)v157;
      v162 = a1;
      v155 = (const wchar_t *)"CMidiDeviceManager::ActivateEndpoint";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        (__int64)v31,
        (__int64)&byte_1400896FF,
        v32,
        v33,
        &v155,
        (__int64)&v162,
        &v154);
    }
    std::vector<_DEVPROPERTY>::~vector<_DEVPROPERTY>((char **)&fmtid);
  }
  else
  {
    v34 = v157;
  }
  v152 = -1;
  v153[0] = 0;
  v35 = (unsigned int *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
  v38 = *v35;
  if ( !v16 )
  {
    if ( v38 > 3 )
    {
      v155 = L"NO Common properties object supplied";
      v154 = (const wchar_t *)v34;
      v156 = (const char *)a1;
      v158 = "CMidiDeviceManager::ActivateEndpoint";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
        (__int64)v35,
        (__int64)&byte_140088EA7,
        v36,
        v37,
        &v158,
        (__int64)&v156,
        &v154,
        &v155);
    }
    goto LABEL_159;
  }
  if ( v38 <= 4 )
  {
    v39 = v157;
  }
  else
  {
    v155 = L"Common properties object supplied";
    v39 = v157;
    v154 = (const wchar_t *)v157;
    v156 = (const char *)a1;
    v158 = "CMidiDeviceManager::ActivateEndpoint";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
      (__int64)v35,
      (__int64)byte_14008A48D,
      v36,
      v37,
      &v158,
      (__int64)&v156,
      &v154,
      &v155);
  }
  fmtid = (DEVPROPGUID)PKEY_MIDI_TransportLayer;
  pid = 1u;
  *(_QWORD *)&v151 = 0x100000000DLL;
  *((_QWORD *)&v151 + 1) = v16;
  v40 = *((_QWORD *)&v147 + 1);
  if ( *((__int128 **)&v147 + 1) == v148 )
  {
    std::vector<_DEVPROPERTY>::_Emplace_reallocate<_DEVPROPERTY>(&v147, *((_QWORD *)&v147 + 1), &fmtid);
    v41 = (__int128 *)*((_QWORD *)&v147 + 1);
  }
  else
  {
    **((_OWORD **)&v147 + 1) = PKEY_MIDI_TransportLayer;
    *(_OWORD *)(v40 + 16) = pid;
    *(_OWORD *)(v40 + 32) = v151;
    v41 = (__int128 *)(*((_QWORD *)&v147 + 1) + 48LL);
    *((_QWORD *)&v147 + 1) += 48LL;
  }
  fmtid = (DEVPROPGUID)PKEY_MIDI_EndpointDevicePurpose;
  pid = 0x64u;
  *(_QWORD *)&v151 = 0x400000007LL;
  *((_QWORD *)&v151 + 1) = v16 + 16;
  if ( v41 == v148 )
  {
    std::vector<_DEVPROPERTY>::_Emplace_reallocate<_DEVPROPERTY>(&v147, v41, &fmtid);
    v42 = *((_QWORD *)&v147 + 1);
  }
  else
  {
    *v41 = PKEY_MIDI_EndpointDevicePurpose;
    v41[1] = pid;
    v41[2] = v151;
    v42 = *((_QWORD *)&v147 + 1) + 48LL;
    *((_QWORD *)&v147 + 1) += 48LL;
  }
  v43 = *(_QWORD *)(v16 + 24);
  if ( !v43 )
    goto LABEL_151;
  v44 = -1;
  do
    ++v44;
  while ( *(_WORD *)(v43 + 2 * v44) );
  if ( !v44 )
  {
LABEL_151:
    v96 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
    if ( *v96 > 2u )
    {
      v155 = (const wchar_t *)v39;
      v154 = L"Common Properties: Friendly Name is null or empty";
      v99 = byte_140088F0D;
      goto LABEL_153;
    }
LABEL_154:
    std::vector<_DEVPROPERTY>::~vector<_DEVPROPERTY>((char **)&v147);
    if ( a1 != -96 )
      LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 96));
    return 2147942487LL;
  }
  fmtid = DEVPKEY_DeviceInterface_FriendlyName.fmtid;
  pid = DEVPKEY_DeviceInterface_FriendlyName.pid;
  LODWORD(v151) = 18;
  DWORD1(v151) = 2 * v44 + 2;
  *((_QWORD *)&v151 + 1) = v43;
  if ( (__int128 *)v42 == v148 )
  {
    std::vector<_DEVPROPERTY>::_Emplace_reallocate<_DEVPROPERTY>(&v147, v42, &fmtid);
    v45 = (__int128 *)*((_QWORD *)&v147 + 1);
  }
  else
  {
    *(DEVPROPGUID *)v42 = DEVPKEY_DeviceInterface_FriendlyName.fmtid;
    *(_OWORD *)(v42 + 16) = pid;
    *(_OWORD *)(v42 + 32) = v151;
    v45 = (__int128 *)(*((_QWORD *)&v147 + 1) + 48LL);
    *((_QWORD *)&v147 + 1) += 48LL;
  }
  v46 = *(_QWORD *)(v16 + 32);
  if ( !v46 )
    goto LABEL_149;
  v47 = -1;
  do
    ++v47;
  while ( *(_WORD *)(v46 + 2 * v47) );
  if ( !v47 )
  {
LABEL_149:
    v96 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
    if ( *v96 > 2u )
    {
      v155 = L"Common Properties: Transport Code is null or empty";
      v154 = (const wchar_t *)v39;
      v99 = byte_1400895A3;
LABEL_153:
      v157 = "CMidiDeviceManager::ActivateEndpoint";
      *(_QWORD *)v159 = a1;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
        (__int64)v96,
        (__int64)v99,
        v97,
        v98,
        &v157,
        (__int64)v159,
        &v154,
        &v155);
      goto LABEL_154;
    }
    goto LABEL_154;
  }
  fmtid = (DEVPROPGUID)PKEY_MIDI_TransportCode;
  pid = 2u;
  LODWORD(v151) = 18;
  DWORD1(v151) = 2 * v47 + 2;
  *((_QWORD *)&v151 + 1) = v46;
  if ( v45 == v148 )
  {
    std::vector<_DEVPROPERTY>::_Emplace_reallocate<_DEVPROPERTY>(&v147, v45, &fmtid);
    v48 = (__int128 *)*((_QWORD *)&v147 + 1);
  }
  else
  {
    *v45 = PKEY_MIDI_TransportCode;
    v45[1] = pid;
    v45[2] = v151;
    v48 = (__int128 *)(*((_QWORD *)&v147 + 1) + 48LL);
    *((_QWORD *)&v147 + 1) += 48LL;
  }
  v49 = *(_QWORD *)(v16 + 40);
  if ( !v49 )
    goto LABEL_61;
  v50 = -1;
  do
    ++v50;
  while ( *(_WORD *)(v49 + 2 * v50) );
  if ( v50 )
  {
    LODWORD(pid) = 14;
    LODWORD(v151) = 18;
    DWORD1(v151) = 2 * v50 + 2;
    *((_QWORD *)&v151 + 1) = v49;
  }
  else
  {
LABEL_61:
    v51 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
    if ( *v51 > 4u )
    {
      v155 = L"Clearing PKEY_MIDI_EndpointName";
      v154 = (const wchar_t *)v39;
      v156 = (const char *)a1;
      v158 = "CMidiDeviceManager::ActivateEndpoint";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
        (__int64)v51,
        (__int64)&byte_140089C5F,
        v52,
        v53,
        &v158,
        (__int64)&v156,
        &v154,
        &v155);
    }
    LODWORD(pid) = 14;
    v151 = 0u;
    v48 = (__int128 *)*((_QWORD *)&v147 + 1);
  }
  *((_QWORD *)&pid + 1) = 0;
  DWORD1(pid) = 0;
  fmtid = (DEVPROPGUID)PKEY_MIDI_EndpointName;
  if ( v48 == v148 )
  {
    std::vector<_DEVPROPERTY>::_Emplace_reallocate<_DEVPROPERTY>(&v147, v48, &fmtid);
  }
  else
  {
    *v48 = PKEY_MIDI_EndpointName;
    v48[1] = pid;
    v48[2] = v151;
    *((_QWORD *)&v147 + 1) += 48LL;
  }
  v54 = *(_QWORD *)(v16 + 48);
  if ( !v54 )
    goto LABEL_72;
  v55 = -1;
  do
    ++v55;
  while ( *(_WORD *)(v54 + 2 * v55) );
  if ( v55 )
  {
    LODWORD(pid) = 15;
    LODWORD(v151) = 18;
    DWORD1(v151) = 2 * v55 + 2;
    *((_QWORD *)&v151 + 1) = v54;
  }
  else
  {
LABEL_72:
    v56 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
    if ( *v56 > 4u )
    {
      v155 = L"Clearing PKEY_MIDI_Description";
      v154 = (const wchar_t *)v39;
      v156 = (const char *)a1;
      v158 = "CMidiDeviceManager::ActivateEndpoint";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
        (__int64)v56,
        (__int64)byte_140089929,
        v57,
        v58,
        &v158,
        (__int64)&v156,
        &v154,
        &v155);
    }
    LODWORD(pid) = 15;
    v151 = 0u;
  }
  v59 = *((_QWORD *)&v147 + 1);
  *((_QWORD *)&pid + 1) = 0;
  DWORD1(pid) = 0;
  fmtid = (DEVPROPGUID)PKEY_MIDI_Description;
  if ( *((__int128 **)&v147 + 1) == v148 )
  {
    std::vector<_DEVPROPERTY>::_Emplace_reallocate<_DEVPROPERTY>(&v147, *((_QWORD *)&v147 + 1), &fmtid);
  }
  else
  {
    **((_OWORD **)&v147 + 1) = PKEY_MIDI_Description;
    *(_OWORD *)(v59 + 16) = pid;
    *(_OWORD *)(v59 + 32) = v151;
    *((_QWORD *)&v147 + 1) += 48LL;
  }
  v60 = *(_QWORD *)(v16 + 72);
  if ( !v60 )
    goto LABEL_83;
  v61 = -1;
  do
    ++v61;
  while ( *(_WORD *)(v60 + 2 * v61) );
  if ( v61 )
  {
    LODWORD(pid) = 53;
    LODWORD(v151) = 18;
    DWORD1(v151) = 2 * v61 + 2;
    *((_QWORD *)&v151 + 1) = v60;
  }
  else
  {
LABEL_83:
    v62 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
    if ( *v62 > 4u )
    {
      v155 = L"Clearing PKEY_MIDI_SerialNumber";
      v154 = (const wchar_t *)v39;
      v156 = (const char *)a1;
      v158 = "CMidiDeviceManager::ActivateEndpoint";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
        (__int64)v62,
        (__int64)byte_140089865,
        v63,
        v64,
        &v158,
        (__int64)&v156,
        &v154,
        &v155);
    }
    LODWORD(pid) = 53;
    v151 = 0u;
  }
  v65 = *((_QWORD *)&v147 + 1);
  *((_QWORD *)&pid + 1) = 0;
  DWORD1(pid) = 0;
  fmtid = (DEVPROPGUID)PKEY_MIDI_SerialNumber;
  if ( *((__int128 **)&v147 + 1) == v148 )
  {
    std::vector<_DEVPROPERTY>::_Emplace_reallocate<_DEVPROPERTY>(&v147, *((_QWORD *)&v147 + 1), &fmtid);
  }
  else
  {
    **((_OWORD **)&v147 + 1) = PKEY_MIDI_SerialNumber;
    *(_OWORD *)(v65 + 16) = pid;
    *(_OWORD *)(v65 + 32) = v151;
    *((_QWORD *)&v147 + 1) += 48LL;
  }
  v66 = *(_QWORD *)(v16 + 80);
  if ( !v66 )
    goto LABEL_94;
  v67 = -1;
  do
    ++v67;
  while ( *(_WORD *)(v66 + 2 * v67) );
  if ( v67 )
  {
    LODWORD(pid) = 7;
    LODWORD(v151) = 18;
    DWORD1(v151) = 2 * v67 + 2;
    *((_QWORD *)&v151 + 1) = v66;
  }
  else
  {
LABEL_94:
    v68 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
    if ( *v68 > 4u )
    {
      v155 = L"Clearing PKEY_MIDI_ManufacturerName";
      v154 = (const wchar_t *)v39;
      v156 = (const char *)a1;
      v158 = "CMidiDeviceManager::ActivateEndpoint";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
        (__int64)v68,
        (__int64)byte_140089A2D,
        v69,
        v70,
        &v158,
        (__int64)&v156,
        &v154,
        &v155);
    }
    LODWORD(pid) = 7;
    v151 = 0u;
  }
  v71 = *((_QWORD *)&v147 + 1);
  *((_QWORD *)&pid + 1) = 0;
  DWORD1(pid) = 0;
  fmtid = (DEVPROPGUID)PKEY_MIDI_ManufacturerName;
  if ( *((__int128 **)&v147 + 1) == v148 )
  {
    std::vector<_DEVPROPERTY>::_Emplace_reallocate<_DEVPROPERTY>(&v147, *((_QWORD *)&v147 + 1), &fmtid);
  }
  else
  {
    **((_OWORD **)&v147 + 1) = PKEY_MIDI_ManufacturerName;
    *(_OWORD *)(v71 + 16) = pid;
    *(_OWORD *)(v71 + 32) = v151;
    *((_QWORD *)&v147 + 1) += 48LL;
  }
  v72 = *(_QWORD *)(v16 + 56);
  if ( !v72 )
    goto LABEL_105;
  v73 = -1;
  do
    ++v73;
  while ( *(_WORD *)(v72 + 2 * v73) );
  if ( v73 )
  {
    LODWORD(pid) = 500;
    LODWORD(v151) = 18;
    DWORD1(v151) = 2 * v73 + 2;
    *((_QWORD *)&v151 + 1) = v72;
  }
  else
  {
LABEL_105:
    v74 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
    if ( *v74 > 4u )
    {
      v155 = L"Clearing PKEY_MIDI_CustomEndpointName";
      v154 = (const wchar_t *)v39;
      v156 = (const char *)a1;
      v158 = "CMidiDeviceManager::ActivateEndpoint";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
        (__int64)v74,
        (__int64)byte_140089D41,
        v75,
        v76,
        &v158,
        (__int64)&v156,
        &v154,
        &v155);
    }
    LODWORD(pid) = 500;
    v151 = 0u;
  }
  v77 = *((_QWORD *)&v147 + 1);
  *((_QWORD *)&pid + 1) = 0;
  DWORD1(pid) = 0;
  fmtid = (DEVPROPGUID)PKEY_MIDI_CustomEndpointName;
  if ( *((__int128 **)&v147 + 1) == v148 )
  {
    std::vector<_DEVPROPERTY>::_Emplace_reallocate<_DEVPROPERTY>(&v147, *((_QWORD *)&v147 + 1), &fmtid);
  }
  else
  {
    **((_OWORD **)&v147 + 1) = PKEY_MIDI_CustomEndpointName;
    *(_OWORD *)(v77 + 16) = pid;
    *(_OWORD *)(v77 + 32) = v151;
    *((_QWORD *)&v147 + 1) += 48LL;
  }
  v78 = *(_QWORD *)(v16 + 64);
  if ( !v78 )
    goto LABEL_115;
  do
    ++v15;
  while ( *(_WORD *)(v78 + 2 * v15) );
  if ( v15 )
  {
    LODWORD(pid) = 503;
    LODWORD(v151) = 18;
    DWORD1(v151) = 2 * v15 + 2;
    *((_QWORD *)&v151 + 1) = v78;
  }
  else
  {
LABEL_115:
    v79 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
    if ( *v79 > 4u )
    {
      v155 = L"Clearing PKEY_MIDI_CustomDescription";
      v154 = (const wchar_t *)v39;
      v156 = (const char *)a1;
      v158 = "CMidiDeviceManager::ActivateEndpoint";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
        (__int64)v79,
        (__int64)&byte_14008A4C7,
        v80,
        v81,
        &v158,
        (__int64)&v156,
        &v154,
        &v155);
    }
    LODWORD(pid) = 503;
    v151 = 0u;
  }
  v82 = *((_QWORD *)&v147 + 1);
  *((_QWORD *)&pid + 1) = 0;
  DWORD1(pid) = 0;
  fmtid = (DEVPROPGUID)PKEY_MIDI_CustomDescription;
  if ( *((__int128 **)&v147 + 1) == v148 )
  {
    std::vector<_DEVPROPERTY>::_Emplace_reallocate<_DEVPROPERTY>(&v147, *((_QWORD *)&v147 + 1), &fmtid);
  }
  else
  {
    **((_OWORD **)&v147 + 1) = PKEY_MIDI_CustomDescription;
    *(_OWORD *)(v82 + 16) = pid;
    *(_OWORD *)(v82 + 32) = v151;
    *((_QWORD *)&v147 + 1) += 48LL;
  }
  v83 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
  if ( *v83 > 4u )
  {
    v155 = L"Adding other non-string properties";
    v154 = (const wchar_t *)v39;
    v156 = (const char *)a1;
    v158 = "CMidiDeviceManager::ActivateEndpoint";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
      (__int64)v83,
      (__int64)byte_1400896C5,
      v84,
      v85,
      &v158,
      (__int64)&v156,
      &v154,
      &v155);
  }
  fmtid = (DEVPROPGUID)PKEY_MIDI_NativeDataFormat;
  pid = 3u;
  *(_QWORD *)&v151 = 0x100000003LL;
  *((_QWORD *)&v151 + 1) = v16 + 92;
  v86 = *((_QWORD *)&v147 + 1);
  if ( *((__int128 **)&v147 + 1) == v148 )
  {
    std::vector<_DEVPROPERTY>::_Emplace_reallocate<_DEVPROPERTY>(&v147, *((_QWORD *)&v147 + 1), &fmtid);
    v87 = (__int128 *)*((_QWORD *)&v147 + 1);
  }
  else
  {
    **((_OWORD **)&v147 + 1) = PKEY_MIDI_NativeDataFormat;
    *(_OWORD *)(v86 + 16) = pid;
    *(_OWORD *)(v86 + 32) = v151;
    v87 = (__int128 *)(*((_QWORD *)&v147 + 1) + 48LL);
    *((_QWORD *)&v147 + 1) += 48LL;
  }
  fmtid = (DEVPROPGUID)PKEY_MIDI_SupportedDataFormats;
  pid = 6u;
  *(_QWORD *)&v151 = 0x100000003LL;
  *((_QWORD *)&v151 + 1) = v16 + 88;
  if ( v87 == v148 )
  {
    std::vector<_DEVPROPERTY>::_Emplace_reallocate<_DEVPROPERTY>(&v147, v87, &fmtid);
    v88 = (__int128 *)*((_QWORD *)&v147 + 1);
  }
  else
  {
    *v87 = PKEY_MIDI_SupportedDataFormats;
    v87[1] = pid;
    v87[2] = v151;
    v88 = (__int128 *)(*((_QWORD *)&v147 + 1) + 48LL);
    *((_QWORD *)&v147 + 1) += 48LL;
  }
  fmtid = (DEVPROPGUID)PKEY_MIDI_EndpointSupportsMidi1Protocol;
  pid = 0x97u;
  *(_QWORD *)&v151 = 0x100000011LL;
  v89 = &v152;
  if ( (*(_BYTE *)(v16 + 96) & 1) == 0 )
    v89 = v153;
  *((_QWORD *)&v151 + 1) = v89;
  if ( v88 == v148 )
  {
    std::vector<_DEVPROPERTY>::_Emplace_reallocate<_DEVPROPERTY>(&v147, v88, &fmtid);
    v90 = (__int128 *)*((_QWORD *)&v147 + 1);
  }
  else
  {
    *v88 = PKEY_MIDI_EndpointSupportsMidi1Protocol;
    v88[1] = pid;
    v88[2] = v151;
    v90 = (__int128 *)(*((_QWORD *)&v147 + 1) + 48LL);
    *((_QWORD *)&v147 + 1) += 48LL;
  }
  fmtid = (DEVPROPGUID)PKEY_MIDI_EndpointSupportsMidi2Protocol;
  pid = 0x96u;
  *(_QWORD *)&v151 = 0x100000011LL;
  v91 = &v152;
  if ( (*(_BYTE *)(v16 + 96) & 2) == 0 )
    v91 = v153;
  *((_QWORD *)&v151 + 1) = v91;
  if ( v90 == v148 )
  {
    std::vector<_DEVPROPERTY>::_Emplace_reallocate<_DEVPROPERTY>(&v147, v90, &fmtid);
    v92 = (__int128 *)*((_QWORD *)&v147 + 1);
  }
  else
  {
    *v90 = PKEY_MIDI_EndpointSupportsMidi2Protocol;
    v90[1] = pid;
    v90[2] = v151;
    v92 = (__int128 *)(*((_QWORD *)&v147 + 1) + 48LL);
    *((_QWORD *)&v147 + 1) += 48LL;
  }
  fmtid = (DEVPROPGUID)PKEY_MIDI_GenerateIncomingTimestamp;
  pid = 0xAu;
  *(_QWORD *)&v151 = 0x100000011LL;
  v93 = &v152;
  if ( (*(_BYTE *)(v16 + 96) & 8) == 0 )
    v93 = v153;
  *((_QWORD *)&v151 + 1) = v93;
  if ( v92 == v148 )
  {
    std::vector<_DEVPROPERTY>::_Emplace_reallocate<_DEVPROPERTY>(&v147, v92, &fmtid);
    v94 = (__int128 *)*((_QWORD *)&v147 + 1);
  }
  else
  {
    *v92 = PKEY_MIDI_GenerateIncomingTimestamp;
    v92[1] = pid;
    v92[2] = v151;
    v94 = (__int128 *)(*((_QWORD *)&v147 + 1) + 48LL);
    *((_QWORD *)&v147 + 1) += 48LL;
  }
  fmtid = (DEVPROPGUID)PKEY_MIDI_SupportsMulticlient;
  pid = 5u;
  *(_QWORD *)&v151 = 0x100000011LL;
  v95 = &v152;
  if ( (*(_BYTE *)(v16 + 96) & 4) == 0 )
    v95 = v153;
  *((_QWORD *)&v151 + 1) = v95;
  if ( v94 == v148 )
  {
    std::vector<_DEVPROPERTY>::_Emplace_reallocate<_DEVPROPERTY>(&v147, v94, &fmtid);
  }
  else
  {
    *v94 = PKEY_MIDI_SupportsMulticlient;
    v94[1] = pid;
    v94[2] = v151;
    *((_QWORD *)&v147 + 1) += 48LL;
  }
LABEL_159:
  v100 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
  if ( *v100 <= 4u )
  {
    v103 = v157;
  }
  else
  {
    v155 = L"Adding clearing properties";
    v103 = v157;
    v154 = (const wchar_t *)v157;
    v157 = (const char *)a1;
    v156 = "CMidiDeviceManager::ActivateEndpoint";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
      (__int64)v100,
      (__int64)qword_140089DC8,
      v101,
      v102,
      &v156,
      (__int64)&v157,
      &v154,
      &v155);
  }
  fmtid = (DEVPROPGUID)PKEY_MIDI_EndpointDiscoveryProcessComplete;
  pid = 0x8Cu;
  v151 = 0u;
  v104 = *((_QWORD *)&v147 + 1);
  if ( *((__int128 **)&v147 + 1) == v148 )
  {
    std::vector<_DEVPROPERTY>::_Emplace_reallocate<_DEVPROPERTY>(&v147, *((_QWORD *)&v147 + 1), &fmtid);
    v105 = (__int128 *)*((_QWORD *)&v147 + 1);
  }
  else
  {
    **((_OWORD **)&v147 + 1) = PKEY_MIDI_EndpointDiscoveryProcessComplete;
    *(_OWORD *)(v104 + 16) = pid;
    *(_OWORD *)(v104 + 32) = v151;
    v105 = (__int128 *)(*((_QWORD *)&v147 + 1) + 48LL);
    *((_QWORD *)&v147 + 1) += 48LL;
  }
  fmtid = (DEVPROPGUID)PKEY_MIDI_EndpointProvidedName;
  pid = 0xAAu;
  v151 = 0u;
  if ( v105 == v148 )
  {
    std::vector<_DEVPROPERTY>::_Emplace_reallocate<_DEVPROPERTY>(&v147, v105, &fmtid);
    v106 = (__int128 *)*((_QWORD *)&v147 + 1);
  }
  else
  {
    *v105 = PKEY_MIDI_EndpointProvidedName;
    v105[1] = pid;
    v105[2] = v151;
    v106 = (__int128 *)(*((_QWORD *)&v147 + 1) + 48LL);
    *((_QWORD *)&v147 + 1) += 48LL;
  }
  fmtid = (DEVPROPGUID)PKEY_MIDI_EndpointProvidedNameLastUpdateTime;
  pid = 0xACu;
  v151 = 0u;
  if ( v106 == v148 )
  {
    std::vector<_DEVPROPERTY>::_Emplace_reallocate<_DEVPROPERTY>(&v147, v106, &fmtid);
    v107 = (__int128 *)*((_QWORD *)&v147 + 1);
  }
  else
  {
    *v106 = PKEY_MIDI_EndpointProvidedNameLastUpdateTime;
    v106[1] = pid;
    v106[2] = v151;
    v107 = (__int128 *)(*((_QWORD *)&v147 + 1) + 48LL);
    *((_QWORD *)&v147 + 1) += 48LL;
  }
  fmtid = (DEVPROPGUID)PKEY_MIDI_EndpointProvidedProductInstanceId;
  pid = 0xABu;
  v151 = 0u;
  if ( v107 == v148 )
  {
    std::vector<_DEVPROPERTY>::_Emplace_reallocate<_DEVPROPERTY>(&v147, v107, &fmtid);
    v108 = (__int128 *)*((_QWORD *)&v147 + 1);
  }
  else
  {
    *v107 = PKEY_MIDI_EndpointProvidedProductInstanceId;
    v107[1] = pid;
    v107[2] = v151;
    v108 = (__int128 *)(*((_QWORD *)&v147 + 1) + 48LL);
    *((_QWORD *)&v147 + 1) += 48LL;
  }
  fmtid = (DEVPROPGUID)PKEY_MIDI_EndpointProvidedProductInstanceIdLastUpdateTime;
  pid = 0xADu;
  v151 = 0u;
  if ( v108 == v148 )
  {
    std::vector<_DEVPROPERTY>::_Emplace_reallocate<_DEVPROPERTY>(&v147, v108, &fmtid);
    v109 = (__int128 *)*((_QWORD *)&v147 + 1);
  }
  else
  {
    *v108 = PKEY_MIDI_EndpointProvidedProductInstanceIdLastUpdateTime;
    v108[1] = pid;
    v108[2] = v151;
    v109 = (__int128 *)(*((_QWORD *)&v147 + 1) + 48LL);
    *((_QWORD *)&v147 + 1) += 48LL;
  }
  fmtid = (DEVPROPGUID)PKEY_MIDI_EndpointConfiguredProtocol;
  pid = 0x190u;
  v151 = 0u;
  if ( v109 == v148 )
  {
    std::vector<_DEVPROPERTY>::_Emplace_reallocate<_DEVPROPERTY>(&v147, v109, &fmtid);
    v110 = (__int128 *)*((_QWORD *)&v147 + 1);
  }
  else
  {
    *v109 = PKEY_MIDI_EndpointConfiguredProtocol;
    v109[1] = pid;
    v109[2] = v151;
    v110 = (__int128 *)(*((_QWORD *)&v147 + 1) + 48LL);
    *((_QWORD *)&v147 + 1) += 48LL;
  }
  fmtid = (DEVPROPGUID)PKEY_MIDI_EndpointConfiguredToReceiveJRTimestamps;
  pid = 0x196u;
  v151 = 0u;
  if ( v110 == v148 )
  {
    std::vector<_DEVPROPERTY>::_Emplace_reallocate<_DEVPROPERTY>(&v147, v110, &fmtid);
    v111 = (__int128 *)*((_QWORD *)&v147 + 1);
  }
  else
  {
    *v110 = PKEY_MIDI_EndpointConfiguredToReceiveJRTimestamps;
    v110[1] = pid;
    v110[2] = v151;
    v111 = (__int128 *)(*((_QWORD *)&v147 + 1) + 48LL);
    *((_QWORD *)&v147 + 1) += 48LL;
  }
  fmtid = (DEVPROPGUID)PKEY_MIDI_EndpointConfiguredToSendJRTimestamps;
  pid = 0x195u;
  v151 = 0u;
  if ( v111 == v148 )
  {
    std::vector<_DEVPROPERTY>::_Emplace_reallocate<_DEVPROPERTY>(&v147, v111, &fmtid);
    v112 = (__int128 *)*((_QWORD *)&v147 + 1);
  }
  else
  {
    *v111 = PKEY_MIDI_EndpointConfiguredToSendJRTimestamps;
    v111[1] = pid;
    v111[2] = v151;
    v112 = (__int128 *)(*((_QWORD *)&v147 + 1) + 48LL);
    *((_QWORD *)&v147 + 1) += 48LL;
  }
  fmtid = (DEVPROPGUID)PKEY_MIDI_EndpointConfigurationLastUpdateTime;
  pid = 0x197u;
  v151 = 0u;
  if ( v112 == v148 )
  {
    std::vector<_DEVPROPERTY>::_Emplace_reallocate<_DEVPROPERTY>(&v147, v112, &fmtid);
    v113 = (__int128 *)*((_QWORD *)&v147 + 1);
  }
  else
  {
    *v112 = PKEY_MIDI_EndpointConfigurationLastUpdateTime;
    v112[1] = pid;
    v112[2] = v151;
    v113 = (__int128 *)(*((_QWORD *)&v147 + 1) + 48LL);
    *((_QWORD *)&v147 + 1) += 48LL;
  }
  fmtid = (DEVPROPGUID)PKEY_MIDI_EndpointSupportsReceivingJRTimestamps;
  pid = 0x98u;
  v151 = 0u;
  if ( v113 == v148 )
  {
    std::vector<_DEVPROPERTY>::_Emplace_reallocate<_DEVPROPERTY>(&v147, v113, &fmtid);
    v114 = (__int128 *)*((_QWORD *)&v147 + 1);
  }
  else
  {
    *v113 = PKEY_MIDI_EndpointSupportsReceivingJRTimestamps;
    v113[1] = pid;
    v113[2] = v151;
    v114 = (__int128 *)(*((_QWORD *)&v147 + 1) + 48LL);
    *((_QWORD *)&v147 + 1) += 48LL;
  }
  fmtid = (DEVPROPGUID)PKEY_MIDI_EndpointSupportsSendingJRTimestamps;
  pid = 0x99u;
  v151 = 0u;
  if ( v114 == v148 )
  {
    std::vector<_DEVPROPERTY>::_Emplace_reallocate<_DEVPROPERTY>(&v147, v114, &fmtid);
    v115 = (__int128 *)*((_QWORD *)&v147 + 1);
  }
  else
  {
    *v114 = PKEY_MIDI_EndpointSupportsSendingJRTimestamps;
    v114[1] = pid;
    v114[2] = v151;
    v115 = (__int128 *)(*((_QWORD *)&v147 + 1) + 48LL);
    *((_QWORD *)&v147 + 1) += 48LL;
  }
  fmtid = (DEVPROPGUID)PKEY_MIDI_EndpointUmpVersionMajor;
  pid = 0x9Au;
  v151 = 0u;
  if ( v115 == v148 )
  {
    std::vector<_DEVPROPERTY>::_Emplace_reallocate<_DEVPROPERTY>(&v147, v115, &fmtid);
    v116 = (__int128 *)*((_QWORD *)&v147 + 1);
  }
  else
  {
    *v115 = PKEY_MIDI_EndpointUmpVersionMajor;
    v115[1] = pid;
    v115[2] = v151;
    v116 = (__int128 *)(*((_QWORD *)&v147 + 1) + 48LL);
    *((_QWORD *)&v147 + 1) += 48LL;
  }
  fmtid = (DEVPROPGUID)PKEY_MIDI_EndpointUmpVersionMinor;
  pid = 0x9Bu;
  v151 = 0u;
  if ( v116 == v148 )
  {
    std::vector<_DEVPROPERTY>::_Emplace_reallocate<_DEVPROPERTY>(&v147, v116, &fmtid);
    v117 = (__int128 *)*((_QWORD *)&v147 + 1);
  }
  else
  {
    *v116 = PKEY_MIDI_EndpointUmpVersionMinor;
    v116[1] = pid;
    v116[2] = v151;
    v117 = (__int128 *)(*((_QWORD *)&v147 + 1) + 48LL);
    *((_QWORD *)&v147 + 1) += 48LL;
  }
  fmtid = (DEVPROPGUID)PKEY_MIDI_EndpointInformationLastUpdateTime;
  pid = 0x9Cu;
  v151 = 0u;
  if ( v117 == v148 )
  {
    std::vector<_DEVPROPERTY>::_Emplace_reallocate<_DEVPROPERTY>(&v147, v117, &fmtid);
    v118 = (__int128 *)*((_QWORD *)&v147 + 1);
  }
  else
  {
    *v117 = PKEY_MIDI_EndpointInformationLastUpdateTime;
    v117[1] = pid;
    v117[2] = v151;
    v118 = (__int128 *)(*((_QWORD *)&v147 + 1) + 48LL);
    *((_QWORD *)&v147 + 1) += 48LL;
  }
  fmtid = (DEVPROPGUID)PKEY_MIDI_DeviceIdentity;
  pid = 0xA0u;
  v151 = 0u;
  if ( v118 == v148 )
  {
    std::vector<_DEVPROPERTY>::_Emplace_reallocate<_DEVPROPERTY>(&v147, v118, &fmtid);
    v119 = (__int128 *)*((_QWORD *)&v147 + 1);
  }
  else
  {
    *v118 = PKEY_MIDI_DeviceIdentity;
    v118[1] = pid;
    v118[2] = v151;
    v119 = (__int128 *)(*((_QWORD *)&v147 + 1) + 48LL);
    *((_QWORD *)&v147 + 1) += 48LL;
  }
  fmtid = (DEVPROPGUID)PKEY_MIDI_DeviceIdentityLastUpdateTime;
  pid = 0xA1u;
  v151 = 0u;
  if ( v119 == v148 )
  {
    std::vector<_DEVPROPERTY>::_Emplace_reallocate<_DEVPROPERTY>(&v147, v119, &fmtid);
    v120 = (__int128 *)*((_QWORD *)&v147 + 1);
  }
  else
  {
    *v119 = PKEY_MIDI_DeviceIdentityLastUpdateTime;
    v119[1] = pid;
    v119[2] = v151;
    v120 = (__int128 *)(*((_QWORD *)&v147 + 1) + 48LL);
    *((_QWORD *)&v147 + 1) += 48LL;
  }
  fmtid = (DEVPROPGUID)PKEY_MIDI_FunctionBlocksAreStatic;
  pid = 0xB6u;
  v151 = 0u;
  if ( v120 == v148 )
  {
    std::vector<_DEVPROPERTY>::_Emplace_reallocate<_DEVPROPERTY>(&v147, v120, &fmtid);
    v121 = (__int128 *)*((_QWORD *)&v147 + 1);
  }
  else
  {
    *v120 = PKEY_MIDI_FunctionBlocksAreStatic;
    v120[1] = pid;
    v120[2] = v151;
    v121 = (__int128 *)(*((_QWORD *)&v147 + 1) + 48LL);
    *((_QWORD *)&v147 + 1) += 48LL;
  }
  fmtid = (DEVPROPGUID)PKEY_MIDI_FunctionBlockDeclaredCount;
  pid = 0xB4u;
  v151 = 0u;
  if ( v121 == v148 )
  {
    std::vector<_DEVPROPERTY>::_Emplace_reallocate<_DEVPROPERTY>(&v147, v121, &fmtid);
    v122 = (__int128 *)*((_QWORD *)&v147 + 1);
  }
  else
  {
    *v121 = PKEY_MIDI_FunctionBlockDeclaredCount;
    v121[1] = pid;
    v121[2] = v151;
    v122 = (__int128 *)(*((_QWORD *)&v147 + 1) + 48LL);
    *((_QWORD *)&v147 + 1) += 48LL;
  }
  fmtid = (DEVPROPGUID)PKEY_MIDI_FunctionBlocksLastUpdateTime;
  pid = 0xB7u;
  v151 = 0u;
  if ( v122 == v148 )
  {
    std::vector<_DEVPROPERTY>::_Emplace_reallocate<_DEVPROPERTY>(&v147, v122, &fmtid);
  }
  else
  {
    *v122 = PKEY_MIDI_FunctionBlocksLastUpdateTime;
    v122[1] = pid;
    v122[2] = v151;
    *((_QWORD *)&v147 + 1) += 48LL;
  }
  v123 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
  if ( *v123 > 4u )
  {
    v155 = (const wchar_t *)v103;
    v154 = L"Adding clearing properties for function blocks";
    v157 = (const char *)a1;
    v156 = "CMidiDeviceManager::ActivateEndpoint";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
      (__int64)v123,
      (__int64)byte_140089EF1,
      v124,
      v125,
      &v156,
      (__int64)&v157,
      &v154,
      &v155);
  }
  v126 = 0;
  v127 = PKEY_MIDI_FunctionBlock00;
  v128 = PKEY_MIDI_FunctionBlockName00;
  do
  {
    fmtid = (DEVPROPGUID)v127;
    pid = (unsigned int)(v126 + 200);
    v151 = 0u;
    v129 = *((_QWORD *)&v147 + 1);
    if ( *((__int128 **)&v147 + 1) == v148 )
    {
      std::vector<_DEVPROPERTY>::_Emplace_reallocate<_DEVPROPERTY>(&v147, *((_QWORD *)&v147 + 1), &fmtid);
      v130 = (__int128 *)*((_QWORD *)&v147 + 1);
      v127 = PKEY_MIDI_FunctionBlock00;
      v128 = PKEY_MIDI_FunctionBlockName00;
    }
    else
    {
      **((_OWORD **)&v147 + 1) = v127;
      *(_OWORD *)(v129 + 16) = pid;
      *(_OWORD *)(v129 + 32) = v151;
      v130 = (__int128 *)(*((_QWORD *)&v147 + 1) + 48LL);
      *((_QWORD *)&v147 + 1) += 48LL;
    }
    fmtid = (DEVPROPGUID)v128;
    pid = (unsigned int)(v126 + 300);
    v151 = 0u;
    if ( v130 == v148 )
    {
      std::vector<_DEVPROPERTY>::_Emplace_reallocate<_DEVPROPERTY>(&v147, v130, &fmtid);
      v127 = PKEY_MIDI_FunctionBlock00;
      v128 = PKEY_MIDI_FunctionBlockName00;
    }
    else
    {
      *v130 = v128;
      v130[1] = pid;
      v130[2] = v151;
      *((_QWORD *)&v147 + 1) += 48LL;
    }
    ++v126;
  }
  while ( v126 < 32 );
  v131 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
  if ( *v131 > 4u )
  {
    v155 = (const wchar_t *)v103;
    v154 = L"Registering cleanupOnFailure";
    v157 = (const char *)a1;
    v156 = "CMidiDeviceManager::ActivateEndpoint";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
      (__int64)v131,
      (__int64)word_140089BE2,
      v132,
      v133,
      &v156,
      (__int64)&v157,
      &v154,
      &v155);
  }
  *(_OWORD *)v166 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v166[0]) = 0;
  v160 = 0;
  v134 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
  if ( *v134 > 4u )
  {
    v155 = (const wchar_t *)v103;
    v154 = L"Activating UMP Endpoint";
    v157 = (const char *)a1;
    v156 = "CMidiDeviceManager::ActivateEndpoint";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
      (__int64)v134,
      (__int64)&byte_140089067,
      v135,
      v136,
      &v156,
      (__int64)&v157,
      &v154,
      &v155);
  }
  v137 = *(_QWORD *)v159;
  v146 = 0;
  v138 = CMidiDeviceManager::ActivateEndpointInternal(a1, v103, 0, 0);
  if ( v138 < 0 )
  {
    v140 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
    if ( *v140 > 2u )
    {
      LODWORD(v161) = v138;
      v164 = v103;
      v155 = L"Failed to activate UMP endpoint";
      v154 = (const wchar_t *)a1;
      *(_QWORD *)v159 = "CMidiDeviceManager::ActivateEndpoint";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
        (__int64)v140,
        (__int64)&byte_1400897CF,
        (__int64)v140,
        v141,
        v159,
        (__int64)&v154,
        &v155,
        &v164);
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4BE,
      (unsigned int)"avcore\\midi2\\service\\exe\\mididevicemanager.cpp",
      (const char *)(unsigned int)v138,
      v146);
    (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)a1 + 64LL))(a1, *(_QWORD *)(v137 + 8));
    goto LABEL_237;
  }
  v142 = v163;
  *((_BYTE *)v160 + 240) = (_DWORD)v163 != 0;
  if ( !v142 )
  {
    v143 = CMidiDeviceManager::SyncMidi1Ports((CMidiDeviceManager *)a1, v160);
    if ( v143 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x4C6,
        (int)"avcore\\midi2\\service\\exe\\mididevicemanager.cpp",
        (const char *)(unsigned int)v143);
  }
  v144 = v165;
  if ( v165 )
  {
    v145 = (const unsigned __int16 *)v166;
    if ( si128.m128i_i64[1] > 7uLL )
      v145 = v166[0];
    wil::make_cotaskmem_string_nothrow((wil *)&v165, v145, v139);
    if ( !v165 )
    {
      v138 = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x4CE,
        (unsigned int)"avcore\\midi2\\service\\exe\\mididevicemanager.cpp",
        (const char *)0x8007000ELL,
        0);
      (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)a1 + 64LL))(a1, *(_QWORD *)(v137 + 8));
LABEL_237:
      std::wstring::~wstring((char **)v166);
      std::vector<_DEVPROPERTY>::~vector<_DEVPROPERTY>((char **)&v147);
      if ( a1 != -96 )
        LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 96));
      return (unsigned int)v138;
    }
    *v144 = v165;
  }
  std::wstring::~wstring((char **)v166);
  std::vector<_DEVPROPERTY>::~vector<_DEVPROPERTY>((char **)&v147);
  if ( a1 != -96 )
    LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 96));
  return 0;
}

```

## disassembly

```asm
0x140029640  mov     [rsp-8+arg_10], rbx
0x140029645  push    rbp
0x140029646  push    rsi
0x140029647  push    rdi
0x140029648  push    r12
0x14002964a  push    r13
0x14002964c  push    r14
0x14002964e  push    r15
0x140029650  lea     rbp, [rsp-100h]
0x140029658  sub     rsp, 200h
0x14002965f  mov     rax, cs:__security_cookie
0x140029666  xor     rax, rsp
0x140029669  mov     [rbp+130h+var_40], rax
0x140029670  mov     dword ptr [rbp+130h+var_138], r9d
0x140029674  mov     edi, r8d
0x140029677  mov     dword ptr [rbp+130h+var_128], r8d
0x14002967b  mov     rbx, rdx
0x14002967e  mov     [rbp+130h+var_158], rdx
0x140029682  mov     r12, rcx
0x140029685  mov     esi, [rbp+130h+arg_28]
0x14002968b  mov     r14, [rbp+130h+arg_38]
0x140029692  mov     rax, [rbp+130h+arg_40]
0x140029699  mov     [rbp+130h+var_120], rax
0x14002969d  mov     rax, [rbp+130h+arg_48]
0x1400296a4  mov     qword ptr [rbp+130h+var_148], rax
0x1400296a8  mov     rax, [rbp+130h+arg_50]
0x1400296af  mov     [rbp+130h+var_118], rax
0x1400296b3  call    ?Instance@MidiSrvTelemetryProvider@@KAPEAV1@XZ; MidiSrvTelemetryProvider::Instance(void)
0x1400296b8  mov     r10, [rax+8]
0x1400296bc  mov     eax, [r10]
0x1400296bf  xor     edx, edx
0x1400296c1  or      r15, 0FFFFFFFFFFFFFFFFh
0x1400296c5  lea     r8, aCmidideviceman; "CMidiDeviceManager::ActivateEndpoint"
0x1400296cc  mov     r13, [rbp+130h+arg_20]
0x1400296d3  lea     ecx, [rdx+4]
0x1400296d6  cmp     eax, ecx
0x1400296d8  jbe     loc_1400297E1
0x1400296de  mov     dword ptr [rbp+130h+var_130], edi
0x1400296e1  mov     eax, [rbp+130h+arg_30]
0x1400296e7  mov     dword ptr [rbp+130h+var_140], eax
0x1400296ea  mov     dword ptr [rbp+130h+var_150], esi
0x1400296ed  mov     eax, edx
0x1400296ef  test    r13, r13
0x1400296f2  setnz   al
0x1400296f5  mov     dword ptr [rbp+130h+var_160], eax
0x1400296f8  mov     [rbp+130h+var_170], r12
0x1400296fc  lea     rax, [rbp+130h+var_130]
0x140029700  mov     [rbp+130h+var_50], rax
0x140029707  mov     [rbp+130h+var_48], rcx
0x14002970e  lea     rax, [rbp+130h+var_140]
0x140029712  mov     [rbp+130h+var_60], rax
0x140029719  mov     [rbp+130h+var_58], rcx
0x140029720  lea     rax, [rbp+130h+var_150]
0x140029724  mov     [rbp+130h+var_70], rax
0x14002972b  mov     [rbp+130h+var_68], rcx
0x140029732  lea     rax, [rbp+130h+var_160]
0x140029736  mov     [rbp+130h+var_80], rax
0x14002973d  mov     [rbp+130h+var_78], rcx
0x140029744  test    rbx, rbx
0x140029747  jz      short loc_140029761
0x140029749  mov     rcx, rbx
0x14002974c  mov     rax, r15
0x14002974f  inc     rax
0x140029752  cmp     [rbx+rax*2], dx
0x140029756  jnz     short loc_14002974F
0x140029758  lea     eax, ds:2[rax*2]
0x14002975f  jmp     short loc_14002976D
0x140029761  lea     rcx, S2
0x140029768  mov     eax, 2
0x14002976d  mov     [rbp+130h+var_90], rcx
0x140029774  mov     [rbp+130h+var_88], eax
0x14002977a  mov     [rbp+130h+var_84], edx
0x140029780  lea     rax, aEnter; "Enter"
0x140029787  mov     [rbp+130h+var_A0], rax
0x14002978e  mov     [rbp+130h+var_98], 0Ch
0x140029799  lea     rax, [rbp+130h+var_170]
0x14002979d  mov     [rbp+130h+var_B0], rax
0x1400297a4  mov     [rbp+130h+var_A8], 8
0x1400297af  mov     [rbp+130h+var_C0], r8
0x1400297b3  mov     [rbp+130h+var_B8], 25h ; '%'
0x1400297bb  lea     rax, [rbp+130h+var_E0]
0x1400297bf  mov     [rsp+230h+var_208], rax
0x1400297c4  mov     [rsp+230h+var_210], 0Ah
0x1400297cc  xor     r9d, r9d
0x1400297cf  xor     r8d, r8d
0x1400297d2  lea     rdx, word_140089FF2
0x1400297d9  mov     rcx, r10
0x1400297dc  call    _tlgWriteTransfer_EventWriteTransfer
0x1400297e1  lea     rcx, [r12+60h]; lpCriticalSection
0x1400297e6  call    cs:__imp_EnterCriticalSection
0x1400297ec  mov     rbx, [r12+88h]
0x1400297f4  mov     rdi, [r12+90h]
0x1400297fc  cmp     rbx, rdi
0x1400297ff  jz      short loc_140029851
0x140029801  mov     r13, qword ptr [rbp+130h+var_148]
0x140029805  mov     rdx, [r13+8]; S2
0x140029809  mov     rcx, [rbx]
0x14002980c  add     rcx, 30h ; '0'
0x140029810  mov     rax, r15
0x140029813  xor     r9d, r9d
0x140029816  inc     rax
0x140029819  cmp     [rdx+rax*2], r9w
0x14002981e  jnz     short loc_140029816
0x140029820  mov     r8, [rcx+10h]; N
0x140029824  cmp     qword ptr [rcx+18h], 7
0x140029829  jbe     short loc_14002982E
0x14002982b  mov     rcx, [rcx]; S1
0x14002982e  cmp     r8, rax
0x140029831  jnz     short loc_140029841
0x140029833  test    r8, r8
0x140029836  jz      short loc_14002984A
0x140029838  call    wmemcmp
0x14002983d  test    eax, eax
0x14002983f  jz      short loc_14002984A
0x140029841  add     rbx, 8
0x140029845  cmp     rbx, rdi
0x140029848  jnz     short loc_140029805
0x14002984a  mov     r13, [rbp+130h+arg_20]
0x140029851  cmp     rbx, [r12+90h]
0x140029859  jz      loc_1400298F0
0x14002985f  call    ?Instance@MidiSrvTelemetryProvider@@KAPEAV1@XZ; MidiSrvTelemetryProvider::Instance(void)
0x140029864  mov     rcx, [rax+8]
0x140029868  mov     eax, [rcx]
0x14002986a  cmp     eax, 4
0x14002986d  jbe     short loc_1400298D6
0x14002986f  mov     rax, qword ptr [rbp+130h+var_148]
0x140029873  mov     rax, [rax+8]
0x140029877  mov     [rbp+130h+var_170], rax
0x14002987b  mov     rbx, [rbp+130h+var_158]
0x14002987f  mov     qword ptr [rbp+130h+var_148], rbx
0x140029883  lea     rax, aAlreadyActivat; "Already Activated"
0x14002988a  mov     [rbp+130h+var_158], rax
0x14002988e  mov     [rbp+130h+var_128], r12
0x140029892  lea     rax, aCmidideviceman; "CMidiDeviceManager::ActivateEndpoint"
0x140029899  mov     [rbp+130h+var_138], rax
0x14002989d  lea     rax, [rbp+130h+var_170]
0x1400298a1  mov     [rsp+230h+var_1F0], rax
0x1400298a6  lea     rax, [rbp+130h+var_148]
0x1400298aa  mov     [rsp+230h+var_1F8], rax
0x1400298af  lea     rax, [rbp+130h+var_158]
0x1400298b3  mov     [rsp+230h+var_200], rax
0x1400298b8  lea     rax, [rbp+130h+var_128]
0x1400298bc  mov     [rsp+230h+var_208], rax
0x1400298c1  lea     rax, [rbp+130h+var_138]
0x1400298c5  mov     qword ptr [rsp+230h+var_210], rax
0x1400298ca  lea     rdx, byte_140088D95
0x1400298d1  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U3@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@55@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x1400298d6  lea     rcx, [r12+60h]; lpCriticalSection
0x1400298db  test    rcx, rcx
0x1400298de  jz      short loc_1400298E6
0x1400298e0  call    cs:__imp_LeaveCriticalSection
0x1400298e6  mov     eax, 1
0x1400298eb  jmp     loc_14002B16D
0x1400298f0  xorps   xmm0, xmm0
0x1400298f3  movdqu  [rsp+230h+var_1C0], xmm0
0x1400298f9  xor     eax, eax
0x1400298fb  mov     [rbp+130h+var_1B0], rax
0x1400298ff  mov     rbx, 0AAAAAAAAAAAAAAABh
0x140029909  test    esi, esi
0x14002990b  jz      loc_1400299C8
0x140029911  test    r14, r14
0x140029914  jz      loc_1400299C8
0x14002991a  lea     r8, [rsi+rsi*2]
0x14002991e  shl     r8, 4
0x140029922  add     r8, r14
0x140029925  mov     rdx, r14
0x140029928  lea     rcx, [rbp+130h+var_1A8]
0x14002992c  call    ??$?0PEBU_DEVPROPERTY@@$0A@@?$vector@U_DEVPROPERTY@@V?$allocator@U_DEVPROPERTY@@@std@@@std@@QEAA@PEBU_DEVPROPERTY@@0AEBV?$allocator@U_DEVPROPERTY@@@1@@Z; std::vector<_DEVPROPERTY>::vector<_DEVPROPERTY>(_DEVPROPERTY const *,_DEVPROPERTY const *,std::allocator<_DEVPROPERTY> const &)
0x140029931  lea     rdx, [rbp+130h+var_1A8]
0x140029935  lea     rcx, [rsp+230h+var_1C0]
0x14002993a  call    ??4?$vector@U_DEVPROPERTY@@V?$allocator@U_DEVPROPERTY@@@std@@@std@@QEAAAEAV01@AEBV01@@Z; std::vector<_DEVPROPERTY>::operator=(std::vector<_DEVPROPERTY> const &)
0x14002993f  call    ?Instance@MidiSrvTelemetryProvider@@KAPEAV1@XZ; MidiSrvTelemetryProvider::Instance(void)
0x140029944  mov     rcx, [rax+8]
0x140029948  mov     eax, [rcx]
0x14002994a  cmp     eax, 4
0x14002994d  jbe     short loc_1400299B9
0x14002994f  mov     rax, qword ptr [rsp+230h+var_1C0+8]
0x140029954  sub     rax, qword ptr [rsp+230h+var_1C0]
0x140029959  sar     rax, 4
0x14002995d  imul    rax, rbx
0x140029961  mov     dword ptr [rbp+130h+var_160], eax
0x140029964  mov     dword ptr [rbp+130h+var_150], esi
0x140029967  mov     rbx, [rbp+130h+var_158]
0x14002996b  mov     [rbp+130h+var_170], rbx
0x14002996f  mov     [rbp+130h+var_130], r12
0x140029973  lea     rax, aCmidideviceman; "CMidiDeviceManager::ActivateEndpoint"
0x14002997a  mov     [rbp+130h+var_168], rax
0x14002997e  lea     rax, [rbp+130h+var_160]
0x140029982  mov     [rsp+230h+var_1F0], rax
0x140029987  lea     rax, [rbp+130h+var_150]
0x14002998b  mov     [rsp+230h+var_1F8], rax
0x140029990  lea     rax, [rbp+130h+var_170]
0x140029994  mov     [rsp+230h+var_200], rax
0x140029999  lea     rax, [rbp+130h+var_130]
0x14002999d  mov     [rsp+230h+var_208], rax
0x1400299a2  lea     rax, [rbp+130h+var_168]
0x1400299a6  mov     qword ptr [rsp+230h+var_210], rax
0x1400299ab  lea     rdx, byte_1400896FF
0x1400299b2  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@6@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1400299b7  jmp     short loc_1400299BD
0x1400299b9  mov     rbx, [rbp+130h+var_158]
0x1400299bd  lea     rcx, [rbp+130h+var_1A8]
0x1400299c1  call    ??1?$vector@U_DEVPROPERTY@@V?$allocator@U_DEVPROPERTY@@@std@@@std@@QEAA@XZ; std::vector<_DEVPROPERTY>::~vector<_DEVPROPERTY>(void)
0x1400299c6  jmp     short loc_1400299CC
0x1400299c8  mov     rbx, [rbp+130h+var_158]
0x1400299cc  mov     [rbp+130h+var_178], r15b
0x1400299d0  xor     r14d, r14d
0x1400299d3  mov     [rbp+130h+var_177], r14b
0x1400299d7  lea     esi, [r14+1]
0x1400299db  lea     edi, [rsi+2Fh]
0x1400299de  call    ?Instance@MidiSrvTelemetryProvider@@KAPEAV1@XZ; MidiSrvTelemetryProvider::Instance(void)
0x1400299e3  mov     rcx, [rax+8]
0x1400299e7  mov     eax, [rcx]
0x1400299e9  test    r13, r13
0x1400299ec  jz      loc_14002A58C
0x1400299f2  cmp     eax, 4
0x1400299f5  jbe     short loc_140029A4B
0x1400299f7  lea     rax, aCommonProperti_1; "Common properties object supplied"
0x1400299fe  mov     [rbp+130h+var_168], rax
0x140029a02  mov     rbx, [rbp+130h+var_158]
0x140029a06  mov     [rbp+130h+var_170], rbx
0x140029a0a  mov     [rbp+130h+var_160], r12
0x140029a0e  lea     rax, aCmidideviceman; "CMidiDeviceManager::ActivateEndpoint"
0x140029a15  mov     [rbp+130h+var_150], rax
0x140029a19  lea     rax, [rbp+130h+var_168]
0x140029a1d  mov     [rsp+230h+var_1F8], rax
0x140029a22  lea     rax, [rbp+130h+var_170]
0x140029a26  mov     [rsp+230h+var_200], rax
0x140029a2b  lea     rax, [rbp+130h+var_160]
0x140029a2f  mov     [rsp+230h+var_208], rax
0x140029a34  lea     rax, [rbp+130h+var_150]
0x140029a38  mov     qword ptr [rsp+230h+var_210], rax
0x140029a3d  lea     rdx, byte_14008A48D
0x140029a44  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x140029a49  jmp     short loc_140029A4F
0x140029a4b  mov     rbx, [rbp+130h+var_158]
0x140029a4f  movups  xmm0, cs:PKEY_MIDI_TransportLayer
0x140029a56  movups  [rbp+130h+var_1A8], xmm0
0x140029a5a  mov     eax, cs:dword_14007A7F8
0x140029a60  mov     dword ptr [rbp+130h+var_198], eax
0x140029a63  mov     dword ptr [rbp+130h+var_198+4], r14d
0x140029a67  mov     qword ptr [rbp+130h+var_198+8], r14
0x140029a6b  mov     dword ptr [rbp+130h+var_188], 0Dh
0x140029a72  mov     dword ptr [rbp+130h+var_188+4], 10h
0x140029a79  mov     qword ptr [rbp+130h+var_188+8], r13
0x140029a7d  mov     rdx, qword ptr [rsp+230h+var_1C0+8]
0x140029a82  cmp     rdx, [rbp+130h+var_1B0]
0x140029a86  jz      short loc_140029AAA
0x140029a88  movups  xmmword ptr [rdx], xmm0
0x140029a8b  movups  xmm0, [rbp+130h+var_198]
0x140029a8f  movups  xmmword ptr [rdx+10h], xmm0
0x140029a93  movups  xmm1, [rbp+130h+var_188]
0x140029a97  movups  xmmword ptr [rdx+20h], xmm1
0x140029a9b  mov     rdx, qword ptr [rsp+230h+var_1C0+8]
0x140029aa0  add     rdx, rdi
0x140029aa3  mov     qword ptr [rsp+230h+var_1C0+8], rdx
0x140029aa8  jmp     short loc_140029ABD
0x140029aaa  lea     r8, [rbp+130h+var_1A8]
0x140029aae  lea     rcx, [rsp+230h+var_1C0]
0x140029ab3  call    ??$_Emplace_reallocate@U_DEVPROPERTY@@@?$vector@U_DEVPROPERTY@@V?$allocator@U_DEVPROPERTY@@@std@@@std@@AEAAPEAU_DEVPROPERTY@@QEAU2@$$QEAU2@@Z; std::vector<_DEVPROPERTY>::_Emplace_reallocate<_DEVPROPERTY>(_DEVPROPERTY * const,_DEVPROPERTY &&)
0x140029ab8  mov     rdx, qword ptr [rsp+230h+var_1C0+8]
0x140029abd  movups  xmm0, cs:PKEY_MIDI_EndpointDevicePurpose
0x140029ac4  movups  [rbp+130h+var_1A8], xmm0
0x140029ac8  mov     eax, cs:dword_14007A3C0
0x140029ace  mov     dword ptr [rbp+130h+var_198], eax
0x140029ad1  mov     dword ptr [rbp+130h+var_198+4], r14d
0x140029ad5  mov     qword ptr [rbp+130h+var_198+8], r14
0x140029ad9  mov     dword ptr [rbp+130h+var_188], 7
0x140029ae0  mov     dword ptr [rbp+130h+var_188+4], 4
0x140029ae7  lea     rax, [r13+10h]
0x140029aeb  mov     qword ptr [rbp+130h+var_188+8], rax
0x140029aef  cmp     rdx, [rbp+130h+var_1B0]
0x140029af3  jz      short loc_140029B17
0x140029af5  movups  xmmword ptr [rdx], xmm0
0x140029af8  movups  xmm0, [rbp+130h+var_198]
0x140029afc  movups  xmmword ptr [rdx+10h], xmm0
0x140029b00  movups  xmm1, [rbp+130h+var_188]
0x140029b04  movups  xmmword ptr [rdx+20h], xmm1
0x140029b08  mov     rdx, qword ptr [rsp+230h+var_1C0+8]
0x140029b0d  add     rdx, rdi
0x140029b10  mov     qword ptr [rsp+230h+var_1C0+8], rdx
0x140029b15  jmp     short loc_140029B2A
0x140029b17  lea     r8, [rbp+130h+var_1A8]
0x140029b1b  lea     rcx, [rsp+230h+var_1C0]
0x140029b20  call    ??$_Emplace_reallocate@U_DEVPROPERTY@@@?$vector@U_DEVPROPERTY@@V?$allocator@U_DEVPROPERTY@@@std@@@std@@AEAAPEAU_DEVPROPERTY@@QEAU2@$$QEAU2@@Z; std::vector<_DEVPROPERTY>::_Emplace_reallocate<_DEVPROPERTY>(_DEVPROPERTY * const,_DEVPROPERTY &&)
0x140029b25  mov     rdx, qword ptr [rsp+230h+var_1C0+8]
0x140029b2a  mov     r8, [r13+18h]
0x140029b2e  test    r8, r8
0x140029b31  jz      loc_14002A50A
0x140029b37  mov     rcx, r15
0x140029b3a  inc     rcx
0x140029b3d  cmp     [r8+rcx*2], r14w
0x140029b42  jnz     short loc_140029B3A
0x140029b44  test    rcx, rcx
0x140029b47  jz      loc_14002A50A
0x140029b4d  movups  xmm0, xmmword ptr cs:DEVPKEY_DeviceInterface_FriendlyName.fmtid.Data1
0x140029b54  movups  [rbp+130h+var_1A8], xmm0
0x140029b58  mov     eax, cs:DEVPKEY_DeviceInterface_FriendlyName.pid
0x140029b5e  mov     dword ptr [rbp+130h+var_198], eax
0x140029b61  mov     dword ptr [rbp+130h+var_198+4], r14d
  ... truncated ...
```
