# CMidiDeviceManager::ActivateEndpointInternal(ushort const *,ushort const *,int,uint,__MIDL___MIDL_itf_windowsmidiservices_0000_0000_0002,ulong,ulong,_DEVPROPERTY const *,_DEVPROPERTY const *,_SW_DEVICE_CREATE_INFO const *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *,_MIDIPORT * *)

- ea: `0x14002b1a0`
- end: `0x14002c69c`
- name: `?ActivateEndpointInternal@CMidiDeviceManager@@AEAAJPEBG0HIW4__MIDL___MIDL_itf_windowsmidiservices_0000_0000_0002@@KKPEBU_DEVPROPERTY@@2PEBU_SW_DEVICE_CREATE_INFO@@PEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAPEAU_MIDIPORT@@@Z`
- size: `5372`
- prototype: `__int64 __fastcall(__int64, void *, const wchar_t *, int, unsigned int, unsigned int, unsigned int, unsigned int, __int64, __int64, __int128 *, char *, void **)`
- caller_count: `2`
- callee_count: `39`
- tags: `file_ops, registry_config, service_task, installer_update`

## callers

- `0x140029640`
- `0x140032ff4`

## callees

- `0x1400018e4`
- `0x140001f28`
- `0x140002adc`
- `0x140002ca8`
- `0x140002f48`
- `0x1400054c0`
- `0x1400054e4`
- `0x140005868`
- `0x1400060ec`
- `0x1400060f8`
- `0x1400072d4`
- `0x140007c20`
- `0x140008b34`
- `0x14000984c`
- `0x14000a6b4`
- `0x14000c55c`
- `0x14000e268`
- `0x140013a38`
- `0x14001440c`
- `0x14001487c`
- `0x14001dccc`
- `0x14001f95c`
- `0x14001fa84`
- `0x14002663c`
- `0x1400274d8`
- `0x140027b54`
- `0x140028c74`
- `0x140029064`
- `0x140029568`
- `0x14002b1a0`
- `0x14002ce1c`
- `0x140032dd0`
- `0x140034800`
- `0x14003481c`
- `0x1400357b8`
- `0x140035b6c`
- `0x140035c60`
- `0x140035d24`
- `0x14005a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x14002bb22`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x14002bb22`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x14002bcd7`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x14002bd0c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x14002bcd7`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x14002bd0c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14002bb65`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14002bb65`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002bb34`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002bb43`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002bb34`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002bb43`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14002bb4e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14002bd52`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14002bdbb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14002c0cb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14002c2d0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14002c37c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14002c3eb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14002c534`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14002bb4e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14002bd52`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14002bdbb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14002c0cb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14002c2d0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14002c37c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14002c3eb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14002c534`
- `api-ms-win-devices-swdevice-l1-1-0!SwDeviceCreate` at `0x14002bc1a`
- `api-ms-win-devices-swdevice-l1-1-0!SwDeviceCreate` at `0x14002bc88`
- `api-ms-win-devices-swdevice-l1-1-0!SwDeviceCreate` at `0x14002bc1a`
- `api-ms-win-devices-swdevice-l1-1-0!SwDeviceCreate` at `0x14002bc88`
- `api-ms-win-devices-swdevice-l1-1-0!SwDeviceInterfaceSetState` at `0x14002c3b6`
- `api-ms-win-devices-swdevice-l1-1-0!SwDeviceInterfaceSetState` at `0x14002c3b6`

## string_xrefs

- `0x14002c619`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x14002c65e`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x14002b23e`: `avcore\midi2\service\exe\mididevicemanager.cpp`
- `0x14002ba55`: `avcore\midi2\service\exe\mididevicemanager.cpp`
- `0x14002bd30`: `avcore\midi2\service\exe\mididevicemanager.cpp`
- `0x14002c0ac`: `avcore\midi2\service\exe\mididevicemanager.cpp`
- `0x14002c2b5`: `avcore\midi2\service\exe\mididevicemanager.cpp`
- `0x14002c35d`: `avcore\midi2\service\exe\mididevicemanager.cpp`
- `0x14002c3cc`: `avcore\midi2\service\exe\mididevicemanager.cpp`
- `0x14002c58f`: `avcore\midi2\service\exe\mididevicemanager.cpp`
- `0x14002c1cd`: `SwDeviceCreate failed`
- `0x14002bef6`: `Activating previously created endpoint.`
- `0x14002c033`: `SwDeviceCreate returned a failed HR`
- `0x14002c24d`: `SwDeviceState != SWDEVICESTATE::Created`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CMidiDeviceManager::ActivateEndpointInternal(
        __int64 a1,
        void *a2,
        const wchar_t *a3,
        int a4,
        unsigned int a5,
        unsigned int a6,
        unsigned int a7,
        unsigned int a8,
        __int64 a9,
        __int64 a10,
        __int128 *a11,
        char *a12,
        void **a13)
{
  __int64 v16; // rdx
  _DWORD *v17; // rcx
  __int64 v18; // r8
  __int64 v19; // r9
  void *v20; // rbx
  __int64 v21; // r8
  unsigned __int64 v22; // r14
  __int64 v23; // rcx
  __int64 v24; // rdx
  char **v25; // rcx
  unsigned __int64 v26; // rdx
  char *v27; // rsi
  __int64 v28; // rbx
  __int64 v29; // rdx
  __int64 v30; // rax
  __int64 v31; // rdx
  __int64 v32; // rdx
  __int64 v33; // rdx
  _WORD *v34; // rdx
  unsigned __int64 v35; // r8
  __int64 v36; // rax
  __int64 v37; // r8
  const wchar_t *v38; // r9
  int v39; // esi
  char **v40; // rcx
  unsigned __int64 v41; // rdx
  char *v42; // rdi
  __int64 v43; // rbx
  __int64 v44; // r8
  char **v45; // rcx
  unsigned __int64 v46; // rdx
  void *v47; // rsi
  char *v48; // rdi
  __int64 v49; // rbx
  __int64 v50; // r8
  _WORD *v51; // r9
  char **v52; // rcx
  unsigned __int64 v53; // rdx
  char *v54; // rdi
  __int64 v55; // rbx
  _OWORD *v56; // rax
  int v57; // r15d
  unsigned int v58; // ebx
  __int64 v59; // rdx
  __int64 *v60; // rcx
  _MIDIPORT *v61; // rdi
  char IsEnabled; // al
  const wchar_t *v63; // rcx
  _QWORD *v64; // rax
  void *v65; // rdx
  HANDLE Event; // rdi
  unsigned int v67; // r8d
  const char *v68; // r9
  HANDLE v69; // rbx
  DWORD LastError; // esi
  __int64 v71; // r8
  const char *v72; // r9
  char v73; // al
  _QWORD *v74; // rcx
  _QWORD *v75; // rcx
  _QWORD *v76; // rax
  int v77; // ecx
  DWORD v78; // eax
  const char *v79; // r9
  DWORD v80; // eax
  const char *v81; // r9
  int v82; // edi
  __int64 v83; // r8
  const char *v84; // r9
  __int64 v86; // r8
  const char *v87; // r9
  _MIDIPORT *v88; // rbx
  __int64 *v89; // rbx
  __int64 *i; // rdi
  const wchar_t *v91; // rdx
  const wchar_t *v92; // rcx
  size_t v93; // r8
  const wchar_t *v94; // rdx
  const wchar_t *v95; // rcx
  size_t v96; // r8
  _DWORD *v97; // r8
  __int64 v98; // r9
  _QWORD *v99; // rcx
  const wchar_t *v100; // rcx
  __int64 v101; // rdx
  void *v102; // r8
  __int64 v103; // rax
  __int64 v104; // rcx
  volatile signed __int32 *v105; // rbx
  struct HSWDEVICE__ **v106; // rcx
  struct HSWDEVICE__ *v107; // rcx
  _DWORD *v108; // rax
  _DWORD *v109; // r8
  __int64 v110; // r9
  __int64 v111; // r8
  const char *v112; // r9
  _DWORD *v113; // r8
  __int64 v114; // r9
  _QWORD *v115; // rcx
  const wchar_t *v116; // rcx
  _DWORD *v117; // rcx
  __int64 v118; // r8
  __int64 v119; // r9
  _DWORD *v120; // rcx
  __int64 v121; // r8
  __int64 v122; // r9
  __int64 v123; // r8
  const char *v124; // r9
  __int64 *v125; // rcx
  __int64 v126; // rdx
  int v127; // eax
  __int64 v128; // r8
  const char *v129; // r9
  __int64 *v130; // rcx
  __int64 v131; // rcx
  int v132; // eax
  __int64 v133; // r8
  const char *v134; // r9
  char *v135; // rbx
  _WORD *v136; // rdx
  __int64 v137; // rax
  _DWORD *v138; // rcx
  __int64 v139; // r8
  __int64 v140; // r9
  _MIDIPORT *v141; // rax
  _MIDIPORT **v142; // rdx
  __int64 v143; // r8
  const char *v144; // r9
  void *v145; // rbx
  int v146; // [rsp+20h] [rbp-E0h]
  __int64 v147; // [rsp+20h] [rbp-E0h]
  void *Block; // [rsp+60h] [rbp-A0h] BYREF
  int v149; // [rsp+68h] [rbp-98h]
  _BYTE v150[4]; // [rsp+6Ch] [rbp-94h] BYREF
  int v151[2]; // [rsp+70h] [rbp-90h] BYREF
  const wchar_t *v152; // [rsp+78h] [rbp-88h] BYREF
  __int128 v153; // [rsp+80h] [rbp-80h] BYREF
  __int64 v154; // [rsp+90h] [rbp-70h]
  int v155[2]; // [rsp+98h] [rbp-68h] BYREF
  const wchar_t *v156; // [rsp+A0h] [rbp-60h] BYREF
  unsigned int v157; // [rsp+A8h] [rbp-58h]
  int v158; // [rsp+ACh] [rbp-54h]
  unsigned int v159; // [rsp+B0h] [rbp-50h] BYREF
  unsigned int v160; // [rsp+B8h] [rbp-48h] BYREF
  void *Src; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v162; // [rsp+C8h] [rbp-38h] BYREF
  int v163[4]; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v164; // [rsp+E0h] [rbp-20h]
  const wchar_t *v165; // [rsp+E8h] [rbp-18h] BYREF
  char *v166; // [rsp+F0h] [rbp-10h] BYREF
  void *v167; // [rsp+F8h] [rbp-8h] BYREF
  HANDLE hObject[2]; // [rsp+100h] [rbp+0h] BYREF
  int v169; // [rsp+110h] [rbp+10h]
  unsigned int v170; // [rsp+118h] [rbp+18h]
  void **v171; // [rsp+120h] [rbp+20h]
  __int128 v172; // [rsp+130h] [rbp+30h] BYREF
  __int128 v173; // [rsp+140h] [rbp+40h]
  __int128 v174; // [rsp+150h] [rbp+50h]
  __int128 v175; // [rsp+160h] [rbp+60h]
  __int64 v176; // [rsp+170h] [rbp+70h]
  DEVPROPGUID fmtid; // [rsp+180h] [rbp+80h] BYREF
  __int128 pid; // [rsp+190h] [rbp+90h]
  __int128 v179; // [rsp+1A0h] [rbp+A0h]
  __int128 v180; // [rsp+1B0h] [rbp+B0h] BYREF
  __int64 v181; // [rsp+1C0h] [rbp+C0h]
  __int64 v182; // [rsp+1C8h] [rbp+C8h]
  char *v183[4]; // [rsp+1D0h] [rbp+D0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+238h] [rbp+138h]

  v158 = a4;
  Src = a2;
  v162 = a10;
  v159 = a5;
  v157 = a6;
  v166 = a12;
  v171 = a13;
  if ( !a9 )
  {
    v16 = 1258;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v16,
      (unsigned int)"avcore\\midi2\\service\\exe\\mididevicemanager.cpp",
      (const char *)0x80070057LL,
      v146);
    return 2147942487LL;
  }
  if ( !a7 )
  {
    v16 = 1259;
    goto LABEL_3;
  }
  v17 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
  if ( *v17 > 4u )
  {
    v170 = a8;
    v160 = a7;
    v149 = v158;
    v165 = a3;
    *(_QWORD *)v155 = a2;
    v156 = L"Enter";
    v152 = (const wchar_t *)a1;
    *(_QWORD *)v151 = "CMidiDeviceManager::ActivateEndpointInternal";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      (__int64)v17,
      (__int64)&unk_14008A110,
      v18,
      v19,
      v151,
      (__int64)&v152,
      &v156,
      v155,
      &v165);
  }
  v172 = *a11;
  v173 = a11[1];
  v174 = a11[2];
  v175 = a11[3];
  v176 = *((_QWORD *)a11 + 8);
  v20 = operator new(0xF8u);
  memset_0(v20, 0, 0xF8u);
  *((_DWORD *)v20 + 4) = 1;
  *((_QWORD *)v20 + 9) = 7;
  *((_QWORD *)v20 + 13) = 7;
  *((_QWORD *)v20 + 17) = 7;
  *((_QWORD *)v20 + 21) = 7;
  *((_DWORD *)v20 + 51) = -1;
  *((_QWORD *)v20 + 29) = 7;
  Block = v20;
  v153 = 0;
  v154 = 0;
  *(_OWORD *)v163 = 0;
  v164 = 0;
  std::vector<_DEVPROPERTY>::vector<_DEVPROPERTY>(&v180, a9, a9 + 48LL * a7);
  std::vector<_DEVPROPERTY>::operator=(&v153, &v180);
  std::vector<_DEVPROPERTY>::~vector<_DEVPROPERTY>((char **)&v180);
  v22 = -1;
  if ( !a3 )
    goto LABEL_23;
  v23 = -1;
  do
    ++v23;
  while ( a3[v23] );
  if ( v23 )
  {
    fmtid = (DEVPROPGUID)PKEY_MIDI_AssociatedUMP;
    pid = 0x34u;
    LODWORD(v179) = 18;
    DWORD1(v179) = 2 * v23 + 2;
    *((_QWORD *)&v179 + 1) = a3;
    v24 = *((_QWORD *)&v153 + 1);
    if ( *((_QWORD *)&v153 + 1) == v154 )
    {
      std::vector<_DEVPROPERTY>::_Emplace_reallocate<_DEVPROPERTY>(&v153, *((_QWORD *)&v153 + 1), &fmtid);
    }
    else
    {
      **((_OWORD **)&v153 + 1) = PKEY_MIDI_AssociatedUMP;
      *(_OWORD *)(v24 + 16) = pid;
      *(_OWORD *)(v24 + 32) = v179;
      *((_QWORD *)&v153 + 1) += 48LL;
    }
    v25 = (char **)((char *)Block + 208);
    v26 = -1;
    do
      ++v26;
    while ( a3[v26] );
    if ( v26 > *((_QWORD *)Block + 29) )
    {
      ____Reallocate_for_V_lambda_1___1_____Assign_G___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV23_QEBG_K_Z_PEBG___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV01__KV_lambda_1___1_____Assign_G_01_AEAAAEAV01_QEBG0_Z_PEBG_Z(
        v25,
        v26,
        v21,
        a3);
    }
    else
    {
      if ( *((_QWORD *)Block + 29) <= 7u )
        v27 = (char *)Block + 208;
      else
        v27 = *v25;
      *((_QWORD *)Block + 28) = v26;
      v28 = 2 * v26;
      memmove_0(v27, a3, 2 * v26);
      *(_WORD *)&v27[v28] = 0;
    }
  }
  else
  {
LABEL_23:
    fmtid = (DEVPROPGUID)PKEY_MIDI_AssociatedUMP;
    pid = 0x34u;
    v179 = 0u;
    v29 = *((_QWORD *)&v153 + 1);
    if ( *((_QWORD *)&v153 + 1) == v154 )
    {
      std::vector<_DEVPROPERTY>::_Emplace_reallocate<_DEVPROPERTY>(&v153, *((_QWORD *)&v153 + 1), &fmtid);
    }
    else
    {
      **((_OWORD **)&v153 + 1) = PKEY_MIDI_AssociatedUMP;
      *(_OWORD *)(v29 + 16) = pid;
      *(_OWORD *)(v29 + 32) = v179;
      *((_QWORD *)&v153 + 1) += 48LL;
    }
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_MIDI2ContainerIds>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_MIDI2ContainerIds>::GetImpl'::`2'::impl) )
  {
    if ( v162 && a8 )
    {
      std::vector<_DEVPROPERTY>::vector<_DEVPROPERTY>(&v180, v162, v162 + 48LL * a8);
      std::vector<_DEVPROPERTY>::operator=(v163, &v180);
      std::vector<_DEVPROPERTY>::~vector<_DEVPROPERTY>((char **)&v180);
    }
    fmtid = DEVPKEY_Device_FriendlyName.fmtid;
    pid = DEVPKEY_Device_FriendlyName.pid;
    LODWORD(v179) = 18;
    v30 = -1;
    do
      ++v30;
    while ( *(_WORD *)(v175 + 2 * v30) );
    DWORD1(v179) = 2 * v30 + 2;
    *((_QWORD *)&v179 + 1) = v175;
    v31 = *(_QWORD *)&v163[2];
    if ( *(_QWORD *)&v163[2] == v164 )
    {
      std::vector<_DEVPROPERTY>::_Emplace_reallocate<_DEVPROPERTY>(v163, *(_QWORD *)&v163[2], &fmtid);
    }
    else
    {
      **(_OWORD **)&v163[2] = DEVPKEY_Device_FriendlyName.fmtid;
      *(_OWORD *)(v31 + 16) = pid;
      *(_OWORD *)(v31 + 32) = v179;
      *(_QWORD *)&v163[2] += 48LL;
    }
  }
  v150[0] = -1;
  fmtid = DEVPKEY_Device_PresenceNotForDevice.fmtid;
  pid = DEVPKEY_Device_PresenceNotForDevice.pid;
  *(_QWORD *)&v179 = 0x100000011LL;
  *((_QWORD *)&v179 + 1) = v150;
  v32 = *((_QWORD *)&v153 + 1);
  if ( *((_QWORD *)&v153 + 1) == v154 )
  {
    std::vector<_DEVPROPERTY>::_Emplace_reallocate<_DEVPROPERTY>(&v153, *((_QWORD *)&v153 + 1), &fmtid);
    v33 = *((_QWORD *)&v153 + 1);
  }
  else
  {
    **((_OWORD **)&v153 + 1) = DEVPKEY_Device_PresenceNotForDevice.fmtid;
    *(_OWORD *)(v32 + 16) = pid;
    *(_OWORD *)(v32 + 32) = v179;
    v33 = *((_QWORD *)&v153 + 1) + 48LL;
    *((_QWORD *)&v153 + 1) += 48LL;
  }
  fmtid = DEVPKEY_Device_NoConnectSound.fmtid;
  pid = DEVPKEY_Device_NoConnectSound.pid;
  *(_QWORD *)&v179 = 0x100000011LL;
  *((_QWORD *)&v179 + 1) = v150;
  if ( v33 == v154 )
  {
    std::vector<_DEVPROPERTY>::_Emplace_reallocate<_DEVPROPERTY>(&v153, v33, &fmtid);
  }
  else
  {
    *(DEVPROPGUID *)v33 = DEVPKEY_Device_NoConnectSound.fmtid;
    *(_OWORD *)(v33 + 16) = pid;
    *(_OWORD *)(v33 + 32) = v179;
    *((_QWORD *)&v153 + 1) += 48LL;
  }
  v34 = (_WORD *)*((_QWORD *)a11 + 1);
  v180 = 0;
  v181 = 0;
  v182 = 0;
  v35 = -1;
  do
    ++v35;
  while ( v34[v35] );
  std::wstring::_Construct<1,unsigned short const *>((char **)&v180, v34, v35);
  v36 = std::wstring::wstring((__int64)&fmtid, (__int64)&v180);
  WindowsMidiServicesInternal::ToUpperTrimmedWStringCopy(v183, v36);
  std::wstring::operator=((char **)Block + 6, (__int64)v183);
  std::wstring::~wstring(v183);
  std::wstring::~wstring((char **)&v180);
  *(_DWORD *)Block = v157;
  v38 = L"MMDEVAPI";
  v39 = v158;
  if ( !v158 )
    v38 = L"MIDISRV";
  v40 = (char **)((char *)Block + 80);
  v41 = -1;
  do
    ++v41;
  while ( v38[v41] );
  if ( v41 > *((_QWORD *)Block + 13) )
  {
    ____Reallocate_for_V_lambda_1___1_____Assign_G___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV23_QEBG_K_Z_PEBG___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV01__KV_lambda_1___1_____Assign_G_01_AEAAAEAV01_QEBG0_Z_PEBG_Z(
      v40,
      v41,
      v37,
      v38);
  }
  else
  {
    if ( *((_QWORD *)Block + 13) <= 7u )
      v42 = (char *)Block + 80;
    else
      v42 = *v40;
    *((_QWORD *)Block + 12) = v41;
    v43 = 2 * v41;
    memmove_0(v42, v38, 2 * v41);
    *(_WORD *)&v42[v43] = 0;
  }
  *((_BYTE *)Block + 196) = v39 != 0;
  v45 = (char **)((char *)Block + 112);
  v46 = -1;
  v47 = Src;
  do
    ++v46;
  while ( *((_WORD *)Src + v46) );
  if ( v46 > *((_QWORD *)Block + 17) )
  {
    ____Reallocate_for_V_lambda_1___1_____Assign_G___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV23_QEBG_K_Z_PEBG___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV01__KV_lambda_1___1_____Assign_G_01_AEAAAEAV01_QEBG0_Z_PEBG_Z(
      v45,
      v46,
      v44,
      Src);
  }
  else
  {
    if ( *((_QWORD *)Block + 17) <= 7u )
      v48 = (char *)Block + 112;
    else
      v48 = *v45;
    *((_QWORD *)Block + 16) = v46;
    v49 = 2 * v46;
    memmove_0(v48, v47, 2 * v46);
    *(_WORD *)&v48[v49] = 0;
  }
  v51 = (_WORD *)*((_QWORD *)a11 + 6);
  v52 = (char **)((char *)Block + 144);
  v53 = -1;
  do
    ++v53;
  while ( v51[v53] );
  if ( v53 > *((_QWORD *)Block + 21) )
  {
    ____Reallocate_for_V_lambda_1___1_____Assign_G___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV23_QEBG_K_Z_PEBG___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV01__KV_lambda_1___1_____Assign_G_01_AEAAAEAV01_QEBG0_Z_PEBG_Z(
      v52,
      v53,
      v50,
      v51);
  }
  else
  {
    if ( *((_QWORD *)Block + 21) <= 7u )
      v54 = (char *)Block + 144;
    else
      v54 = *v52;
    *((_QWORD *)Block + 20) = v53;
    v55 = 2 * v53;
    memmove_0(v54, v51, 2 * v53);
    *(_WORD *)&v54[v55] = 0;
  }
  v56 = (_OWORD *)*((_QWORD *)a11 + 4);
  if ( v56 )
    *((_OWORD *)Block + 11) = *v56;
  v173 = 0u;
  v57 = v158;
  if ( v158 )
  {
    *((_DWORD *)Block + 50) = v159;
    std::wstring::operator+=((char *)Block + 48, L"_");
    v58 = v157;
    std::to_wstring(&fmtid, v157);
    std::wstring::operator+=((char *)Block + 48);
    std::wstring::~wstring((char **)&fmtid);
    std::wstring::operator+=((char *)Block + 48, L"_");
    std::to_wstring(&fmtid, v159);
    std::wstring::operator+=((char *)Block + 48);
    std::wstring::~wstring((char **)&fmtid);
    fmtid = (DEVPROPGUID)PKEY_MIDI_PortAssignedGroupIndex;
    pid = 0x12u;
    *(_QWORD *)&v179 = 0x400000007LL;
    *((_QWORD *)&v179 + 1) = &v159;
    v59 = *((_QWORD *)&v153 + 1);
    if ( *((_QWORD *)&v153 + 1) == v154 )
    {
      std::vector<_DEVPROPERTY>::_Emplace_reallocate<_DEVPROPERTY>(&v153, *((_QWORD *)&v153 + 1), &fmtid);
    }
    else
    {
      **((_OWORD **)&v153 + 1) = PKEY_MIDI_PortAssignedGroupIndex;
      *(_OWORD *)(v59 + 16) = pid;
      *(_OWORD *)(v59 + 32) = v179;
      *((_QWORD *)&v153 + 1) += 48LL;
    }
    if ( v58 == 1 )
    {
      v60 = DEVINTERFACE_MIDI_OUTPUT;
      goto LABEL_88;
    }
    if ( !v58 )
    {
      v60 = DEVINTERFACE_MIDI_INPUT;
      goto LABEL_88;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x558,
      (unsigned int)"avcore\\midi2\\service\\exe\\mididevicemanager.cpp",
      (const char *)0x80070057LL,
      v146);
    std::vector<_DEVPROPERTY>::~vector<_DEVPROPERTY>((char **)v163);
    std::vector<_DEVPROPERTY>::~vector<_DEVPROPERTY>((char **)&v153);
    v61 = (_MIDIPORT *)Block;
LABEL_215:
    if ( v61 )
    {
      _MIDIPORT::~_MIDIPORT(v61);
      operator delete(v61);
    }
    return 2147942487LL;
  }
  *((_QWORD *)&v173 + 1) = L"GenericMidiEndpoint";
  IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_MIDI2ContainerIds>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_MIDI2ContainerIds>::GetImpl'::`2'::impl);
  v63 = L"MIDISRV\\MidiEndpoints";
  if ( !IsEnabled )
    v63 = L"MIDISRV\\MidiEndpointsNonclass";
  *(_QWORD *)&v173 = v63;
  if ( v157 == 1 )
  {
    v60 = DEVINTERFACE_UNIVERSALMIDIPACKET_OUTPUT;
  }
  else if ( v157 )
  {
    if ( v157 != 2 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x576,
        (unsigned int)"avcore\\midi2\\service\\exe\\mididevicemanager.cpp",
        (const char *)0x80070057LL,
        v146);
      std::vector<_DEVPROPERTY>::~vector<_DEVPROPERTY>((char **)v163);
      std::vector<_DEVPROPERTY>::~vector<_DEVPROPERTY>((char **)&v153);
      v61 = (_MIDIPORT *)Block;
      if ( !Block )
        return 2147942487LL;
      goto LABEL_215;
    }
    v60 = DEVINTERFACE_UNIVERSALMIDIPACKET_BIDI;
  }
  else
  {
    v60 = DEVINTERFACE_UNIVERSALMIDIPACKET_INPUT;
  }
LABEL_88:
  *((_QWORD *)Block + 1) = v60;
  v64 = (char *)Block + 48;
  if ( *((_QWORD *)Block + 9) > 7u )
    v64 = (_QWORD *)*v64;
  *((_QWORD *)&v172 + 1) = v64;
  v167 = 0;
  *(_QWORD *)v151 = hObject;
  hObject[0] = 0;
  Event = CreateEventExW(0, 0, 0, 0x1F0003u);
  if ( !Event )
    wil::details::in1diag3::Throw_GetLastError(retaddr, v65, v67, v68);
  GetLastError();
  v69 = hObject[0];
  if ( hObject[0] )
  {
    LastError = GetLastError();
    if ( !CloseHandle(v69) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v71, v72);
    SetLastError(LastError);
    v47 = Src;
  }
  hObject[0] = Event;
  v167 = Block;
  hObject[1] = (HANDLE)v153;
  v169 = -1431655765 * ((__int64)(*((_QWORD *)&v153 + 1) - v153) >> 4);
  v73 = wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_MIDI2ContainerIds>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_MIDI2ContainerIds>::GetImpl'::`2'::impl);
  LOBYTE(v181) = 1;
  *(_QWORD *)&v180 = (char *)Block + 24;
  if ( v73 )
  {
    *((_QWORD *)&v180 + 1) = 0;
    v75 = (char *)Block + 80;
    if ( *((_QWORD *)Block + 13) > 7u )
      v75 = (_QWORD *)*v75;
    LODWORD(v147) = v163[0];
    *((_DWORD *)Block + 48) = SwDeviceCreate(
                                v75,
                                v47,
                                &v172,
                                0xAAAAAAAAAAAAAAABuLL * ((__int64)(*(_QWORD *)&v163[2] - *(_QWORD *)v163) >> 4));
  }
  else
  {
    *((_QWORD *)&v180 + 1) = 0;
    v74 = (char *)Block + 80;
    if ( *((_QWORD *)Block + 13) > 7u )
      v74 = (_QWORD *)*v74;
    v147 = v162 & -(__int64)(a8 != 0);
    *((_DWORD *)Block + 48) = SwDeviceCreate(v74, v47, &v172, a8);
  }
  if ( (_BYTE)v181 )
    wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSWDEVICE__ *,void (*)(HSWDEVICE__ *),&void SwDeviceClose(HSWDEVICE__ *),wistd::integral_constant<unsigned __int64,0>,HSWDEVICE__ *,HSWDEVICE__ *,0,std::nullptr_t>>>>::reset(
      v180,
      *((_QWORD *)&v180 + 1));
  v76 = Block;
  v77 = *((_DWORD *)Block + 48);
  if ( v77 >= 0 )
  {
    v78 = WaitForSingleObjectEx(hObject[0], 0x2710u, 0);
    if ( v78 != 258 )
    {
      if ( v78 )
        wil::details::in1diag3::FailFast_Unexpected(
          retaddr,
          (void *)0xB0F,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
          v79);
      goto LABEL_155;
    }
    wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSWDEVICE__ *,void (*)(HSWDEVICE__ *),&void SwDeviceClose(HSWDEVICE__ *),wistd::integral_constant<unsigned __int64,0>,HSWDEVICE__ *,HSWDEVICE__ *,0,std::nullptr_t>>>>::reset(
      (char *)Block + 24,
      0);
    v80 = WaitForSingleObjectEx(hObject[0], 0x2710u, 0);
    if ( v80 != 258 && v80 )
      wil::details::in1diag3::FailFast_Unexpected(
        retaddr,
        (void *)0xB0F,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v81);
    v82 = *((_DWORD *)Block + 48);
    if ( v82 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x5AD,
        (unsigned int)"avcore\\midi2\\service\\exe\\mididevicemanager.cpp",
        (const char *)(unsigned int)v82,
        v147);
      if ( hObject[0] && !CloseHandle(hObject[0]) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v83, v84);
      goto LABEL_112;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5AE,
      (unsigned int)"avcore\\midi2\\service\\exe\\mididevicemanager.cpp",
      (const char *)0x80004005LL,
      v147);
    if ( hObject[0] && !CloseHandle(hObject[0]) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v86, v87);
    std::vector<_DEVPROPERTY>::~vector<_DEVPROPERTY>((char **)v163);
    std::vector<_DEVPROPERTY>::~vector<_DEVPROPERTY>((char **)&v153);
    v88 = (_MIDIPORT *)Block;
LABEL_178:
    if ( v88 )
    {
      _MIDIPORT::~_MIDIPORT(v88);
      operator delete(v88);
    }
    return 2147500037LL;
  }
  if ( v77 == -2147024713 )
  {
    v89 = *(__int64 **)(a1 + 144);
    for ( i = *(__int64 **)(a1 + 136); ; ++i )
    {
      if ( i == v89 )
      {
LABEL_138:
        if ( i == *(__int64 **)(a1 + 144) )
        {
          v113 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
          if ( *v113 > 4u )
          {
            v149 = v57;
            v115 = (char *)Block + 80;
            if ( *((_QWORD *)Block + 13) > 7u )
              v115 = (_QWORD *)*v115;
            *(_QWORD *)v151 = v115;
            v116 = (const wchar_t *)((char *)Block + 48);
            if ( *((_QWORD *)Block + 9) > 7u )
              v116 = *(const wchar_t **)v116;
            v152 = v116;
            v156 = (const wchar_t *)*((_QWORD *)Block + 5);
            *(_QWORD *)v155 = v47;
            v165 = L"Endpoint exists, but it is not in the MidiDeviceManager store. Is something else creating endpoints?";
            v162 = a1;
            Src = "CMidiDeviceManager::ActivateEndpointInternal";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
              (__int64)v113,
              (__int64)&byte_140088A9F,
              (__int64)v113,
              v114,
              &Src,
              (__int64)&v162,
              &v165,
              v155,
              &v156,
              &v152,
              v151);
          }
        }
        else
        {
          v97 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
          if ( *v97 > 4u )
          {
            v149 = v57;
            v99 = (char *)Block + 80;
            if ( *((_QWORD *)Block + 13) > 7u )
              v99 = (_QWORD *)*v99;
            *(_QWORD *)v151 = v99;
            v100 = (const wchar_t *)((char *)Block + 48);
            if ( *((_QWORD *)Block + 9) > 7u )
              v100 = *(const wchar_t **)v100;
            v152 = v100;
            v156 = (const wchar_t *)*((_QWORD *)Block + 5);
            *(_QWORD *)v155 = v47;
            v165 = L"Activating previously created endpoint.";
            v162 = a1;
            Src = "CMidiDeviceManager::ActivateEndpointInternal";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
              (__int64)v97,
              (__int64)word_140089E02,
              (__int64)v97,
              v98,
              &Src,
              (__int64)&v162,
              &v165,
              v155,
              &v156,
              &v152,
              v151);
          }
          v101 = *i;
          v102 = Block;
          v103 = *(_QWORD *)(*i + 32);
          if ( v103 )
            _InterlockedIncrement((volatile signed __int32 *)(v103 + 8));
          v104 = *(_QWORD *)(v101 + 32);
          *((_QWORD *)Block + 3) = *(_QWORD *)(v101 + 24);
          v105 = (volatile signed __int32 *)*((_QWORD *)v102 + 4);
          *((_QWORD *)v102 + 4) = v104;
          if ( v105 )
          {
            if ( _InterlockedExchangeAdd(v105 + 2, 0xFFFFFFFF) == 1 )
            {
              (**(void (__fastcall ***)(volatile signed __int32 *))v105)(v105);
              if ( _InterlockedExchangeAdd(v105 + 3, 0xFFFFFFFF) == 1 )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v105 + 8LL))(v105);
            }
          }
          v106 = *(struct HSWDEVICE__ ***)(*i + 24);
          if ( v106 )
            v107 = *v106;
          else
            v107 = 0;
          SwMidiPortCreateCallback(v107, 0, &v167, 0);
        }
        goto LABEL_155;
      }
      v91 = (const wchar_t *)(*i + 48);
      v92 = (const wchar_t *)(v76 + 6);
      if ( *(_QWORD *)(*i + 72) > 7u )
        v91 = *(const wchar_t **)v91;
      v93 = v76[8];
      if ( v76[9] > 7u )
        v92 = *(const wchar_t **)v92;
      if ( v93 == *(_QWORD *)(*i + 64) )
      {
        if ( v93 )
        {
          if ( wmemcmp(v92, v91, v93) )
            goto LABEL_135;
          v76 = Block;
        }
        v94 = (const wchar_t *)(*i + 80);
        v95 = (const wchar_t *)(v76 + 10);
        if ( *(_QWORD *)(*i + 104) > 7u )
          v94 = *(const wchar_t **)v94;
        v96 = v76[12];
        if ( v76[13] > 7u )
          v95 = *(const wchar_t **)v95;
        if ( v96 == *(_QWORD *)(*i + 96) )
        {
          if ( !v96 || !wmemcmp(v95, v94, v96) )
            goto LABEL_138;
LABEL_135:
          v76 = Block;
          continue;
        }
      }
    }
  }
  v117 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
  if ( *v117 > 2u )
  {
    v149 = v57;
    *(_QWORD *)v151 = v47;
    v152 = L"SwDeviceCreate failed";
    v156 = (const wchar_t *)a1;
    *(_QWORD *)v155 = "CMidiDeviceManager::ActivateEndpointInternal";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
      (__int64)v117,
      (__int64)&word_14008A616,
      v118,
      v119,
      v155,
      (__int64)&v156,
      &v152,
      v151);
  }
LABEL_155:
  v108 = Block;
  if ( *((int *)Block + 48) < 0 )
  {
    v109 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
    if ( *v109 > 2u )
    {
      v149 = v57;
      *(_QWORD *)v151 = v47;
      v160 = *((_DWORD *)Block + 48);
      v152 = L"SwDeviceCreate returned a failed HR";
      v156 = (const wchar_t *)a1;
      *(_QWORD *)v155 = "CMidiDeviceManager::ActivateEndpointInternal";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
        (__int64)v109,
        (__int64)&byte_140089677,
        (__int64)v109,
        v110,
        v155,
        (__int64)&v156,
        &v152,
        (__int64)&v160,
        v151);
    }
    v108 = Block;
  }
  v82 = v108[48];
  if ( v82 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x60E,
      (unsigned int)"avcore\\midi2\\service\\exe\\mididevicemanager.cpp",
      (const char *)(unsigned int)v82,
      v147);
    if ( hObject[0] && !CloseHandle(hObject[0]) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v111, v112);
LABEL_112:
    std::vector<_DEVPROPERTY>::~vector<_DEVPROPERTY>((char **)v163);
    std::vector<_DEVPROPERTY>::~vector<_DEVPROPERTY>((char **)&v153);
    if ( Block )
    {
      _MIDIPORT::~_MIDIPORT((_MIDIPORT *)Block);
      operator delete(Block);
    }
    return (unsigned int)v82;
  }
  if ( v108[4] != 2 )
  {
    v120 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
    if ( *v120 > 2u )
    {
      v149 = v57;
      *(_QWORD *)v151 = v47;
      v152 = L"SwDeviceState != SWDEVICESTATE::Created";
      v156 = (const wchar_t *)a1;
      *(_QWORD *)v155 = "CMidiDeviceManager::ActivateEndpointInternal";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
        (__int64)v120,
        (__int64)&dword_14008A0CC,
        v121,
        v122,
        v155,
        (__int64)&v156,
        &v152,
        v151);
    }
    v108 = Block;
    if ( *((_DWORD *)Block + 4) != 2 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x61D,
        (unsigned int)"avcore\\midi2\\service\\exe\\mididevicemanager.cpp",
        (const char *)0x80004005LL,
        v147);
      if ( hObject[0] && !CloseHandle(hObject[0]) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v123, v124);
      std::vector<_DEVPROPERTY>::~vector<_DEVPROPERTY>((char **)v163);
      std::vector<_DEVPROPERTY>::~vector<_DEVPROPERTY>((char **)&v153);
      v88 = (_MIDIPORT *)Block;
      if ( !Block )
        return 2147500037LL;
      goto LABEL_178;
    }
  }
  if ( v57 )
  {
    v125 = (__int64 *)*((_QWORD *)v108 + 3);
    if ( v125 )
      v126 = *v125;
    else
      v126 = 0;
    v127 = CMidiDeviceManager::AssignPortNumber(a1, v126, *((_QWORD *)v108 + 5), v157);
    v82 = v127;
    if ( v127 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x622,
        (unsigned int)"avcore\\midi2\\service\\exe\\mididevicemanager.cpp",
        (const char *)(unsigned int)v127,
        v147);
      if ( hObject[0] && !CloseHandle(hObject[0]) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v128, v129);
      goto LABEL_112;
    }
    v108 = Block;
  }
  v130 = (__int64 *)*((_QWORD *)v108 + 3);
  if ( v130 )
    v131 = *v130;
  else
    v131 = 0;
  v132 = SwDeviceInterfaceSetState(v131, *((_QWORD *)v108 + 5), 1);
  v82 = v132;
  if ( v132 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x62A,
      (unsigned int)"avcore\\midi2\\service\\exe\\mididevicemanager.cpp",
      (const char *)(unsigned int)v132,
      v147);
    if ( hObject[0] && !CloseHandle(hObject[0]) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v133, v134);
    goto LABEL_112;
  }
  v135 = v166;
  if ( v166 )
  {
    v136 = (_WORD *)*((_QWORD *)Block + 5);
    v180 = 0;
    v181 = 0;
    v182 = 0;
    do
      ++v22;
    while ( v136[v22] );
    std::wstring::_Construct<1,unsigned short const *>((char **)&v180, v136, v22);
    v137 = std::wstring::wstring((__int64)&fmtid, (__int64)&v180);
    WindowsMidiServicesInternal::ToLowerTrimmedWStringCopy(v183, v137);
    std::wstring::operator=((char **)v135, (__int64)v183);
    std::wstring::~wstring(v183);
    std::wstring::~wstring((char **)&v180);
    v138 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
    if ( *v138 > 4u )
    {
      if ( *((_QWORD *)v135 + 3) > 7u )
        v135 = *(char **)v135;
      v166 = v135;
      *(_QWORD *)v151 = a1;
      v152 = (const wchar_t *)"CMidiDeviceManager::ActivateEndpointInternal";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>>(
        (__int64)v138,
        (__int64)&dword_140089FAC,
        v139,
        v140,
        &v152,
        (__int64)v151,
        &v166);
    }
  }
  v141 = (_MIDIPORT *)Block;
  if ( v171 )
    *v171 = Block;
  v142 = *(_MIDIPORT ***)(a1 + 144);
  if ( v142 == *(_MIDIPORT ***)(a1 + 152) )
  {
    std::vector<std::unique_ptr<_MIDIPORT>>::_Emplace_reallocate<std::unique_ptr<_MIDIPORT>>(
      (_MIDIPORT ***)(a1 + 136),
      v142,
      (__int64 *)&Block);
  }
  else
  {
    Block = 0;
    *v142 = v141;
    *(_QWORD *)(a1 + 144) += 8LL;
  }
  if ( hObject[0] && !CloseHandle(hObject[0]) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v143, v144);
  std::vector<_DEVPROPERTY>::~vector<_DEVPROPERTY>((char **)v163);
  std::vector<_DEVPROPERTY>::~vector<_DEVPROPERTY>((char **)&v153);
  v145 = Block;
  if ( Block )
  {
    _MIDIPORT::~_MIDIPORT((_MIDIPORT *)Block);
    operator delete(v145);
  }
  return 0;
}

```

## disassembly

```asm
0x14002b1a0  mov     [rsp-8+arg_18], rbx
0x14002b1a5  push    rbp
0x14002b1a6  push    rsi
0x14002b1a7  push    rdi
0x14002b1a8  push    r12
0x14002b1aa  push    r13
0x14002b1ac  push    r14
0x14002b1ae  push    r15
0x14002b1b0  lea     rbp, [rsp-100h]
0x14002b1b8  sub     rsp, 200h
0x14002b1bf  mov     rax, cs:__security_cookie
0x14002b1c6  xor     rax, rsp
0x14002b1c9  mov     [rbp+130h+var_40], rax
0x14002b1d0  mov     [rbp+130h+var_184], r9d
0x14002b1d4  mov     rdi, r8
0x14002b1d7  mov     rbx, rdx
0x14002b1da  mov     [rbp+130h+Src], rdx
0x14002b1de  mov     r13, rcx
0x14002b1e1  mov     rax, [rbp+130h+arg_48]
0x14002b1e8  mov     [rbp+130h+var_168], rax
0x14002b1ec  mov     eax, [rbp+130h+arg_20]
0x14002b1f2  mov     [rbp+130h+var_180], eax
0x14002b1f5  mov     eax, [rbp+130h+arg_28]
0x14002b1fb  mov     [rbp+130h+var_188], eax
0x14002b1fe  mov     esi, [rbp+130h+arg_30]
0x14002b204  mov     r12d, [rbp+130h+arg_38]
0x14002b20b  mov     r14, [rbp+130h+arg_40]
0x14002b212  mov     r15, [rbp+130h+arg_50]
0x14002b219  mov     rax, [rbp+130h+arg_58]
0x14002b220  mov     [rbp+130h+var_140], rax
0x14002b224  mov     rax, [rbp+130h+arg_60]
0x14002b22b  mov     [rbp+130h+var_110], rax
0x14002b22f  test    r14, r14
0x14002b232  jnz     short loc_14002B259
0x14002b234  mov     edx, 4EAh; void *
0x14002b239  mov     ebx, 80070057h
0x14002b23e  lea     r8, aAvcoreMidi2Ser_9; "avcore\\midi2\\service\\exe\\mididevice"...
0x14002b245  mov     r9d, ebx; char *
0x14002b248  mov     rcx, [rbp+138h]; this
0x14002b24f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14002b254  jmp     loc_14002C5D9
0x14002b259  test    esi, esi
0x14002b25b  jnz     short loc_14002B264
0x14002b25d  mov     edx, 4EBh
0x14002b262  jmp     short loc_14002B239
0x14002b264  call    ?Instance@MidiSrvTelemetryProvider@@KAPEAV1@XZ; MidiSrvTelemetryProvider::Instance(void)
0x14002b269  mov     rcx, [rax+8]
0x14002b26d  mov     eax, [rcx]
0x14002b26f  lea     rdx, aCmidideviceman_0; "CMidiDeviceManager::ActivateEndpointInt"...
0x14002b276  cmp     eax, 4
0x14002b279  jbe     loc_14002B301
0x14002b27f  mov     [rbp+130h+var_118], r12d
0x14002b283  mov     [rbp+130h+var_178], esi
0x14002b286  mov     eax, [rbp+130h+var_184]
0x14002b289  mov     [rsp+230h+var_1C8], eax
0x14002b28d  mov     [rbp+130h+var_148], rdi
0x14002b291  mov     qword ptr [rbp+130h+var_198], rbx
0x14002b295  lea     rax, aEnter; "Enter"
0x14002b29c  mov     [rbp+130h+var_190], rax
0x14002b2a0  mov     [rsp+230h+var_1B8], r13
0x14002b2a5  mov     qword ptr [rsp+230h+var_1C0], rdx
0x14002b2aa  lea     rax, [rbp+130h+var_118]
0x14002b2ae  mov     [rsp+230h+var_1D8], rax
0x14002b2b3  lea     rax, [rbp+130h+var_178]
0x14002b2b7  mov     [rsp+230h+var_1E0], rax
0x14002b2bc  lea     rax, [rsp+230h+var_1C8]
0x14002b2c1  mov     [rsp+230h+var_1E8], rax
0x14002b2c6  lea     rax, [rbp+130h+var_148]
0x14002b2ca  mov     [rsp+230h+var_1F0], rax
0x14002b2cf  lea     rax, [rbp+130h+var_198]
0x14002b2d3  mov     [rsp+230h+var_1F8], rax
0x14002b2d8  lea     rax, [rbp+130h+var_190]
0x14002b2dc  mov     [rsp+230h+var_200], rax
0x14002b2e1  lea     rax, [rsp+230h+var_1B8]
0x14002b2e6  mov     [rsp+230h+var_208], rax
0x14002b2eb  lea     rax, [rsp+230h+var_1C0]
0x14002b2f0  mov     qword ptr [rsp+230h+var_210], rax; int
0x14002b2f5  lea     rdx, unk_14008A110
0x14002b2fc  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U3@U3@U?$_tlgWrapperByVal@$03@@U4@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@55AEBU?$_tlgWrapperByVal@$03@@66@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x14002b301  movups  xmm0, xmmword ptr [r15]
0x14002b305  movaps  [rbp+130h+var_100], xmm0
0x14002b309  movups  xmm1, xmmword ptr [r15+10h]
0x14002b30e  movaps  [rbp+130h+var_F0], xmm1
0x14002b312  movups  xmm0, xmmword ptr [r15+20h]
0x14002b317  movaps  [rbp+130h+var_E0], xmm0
0x14002b31b  movups  xmm1, xmmword ptr [r15+30h]
0x14002b320  movaps  [rbp+130h+var_D0], xmm1
0x14002b324  movsd   xmm0, qword ptr [r15+40h]
0x14002b32a  movsd   [rbp+130h+var_C0], xmm0
0x14002b32f  mov     ecx, 0F8h; Size
0x14002b334  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14002b339  mov     rbx, rax
0x14002b33c  xor     edx, edx; Val
0x14002b33e  mov     r8d, 0F8h; Size
0x14002b344  mov     rcx, rax; void *
0x14002b347  call    memset_0
0x14002b34c  mov     dword ptr [rbx+10h], 1
0x14002b353  mov     eax, 7
0x14002b358  mov     [rbx+48h], rax
0x14002b35c  mov     [rbx+68h], rax
0x14002b360  mov     [rbx+88h], rax
0x14002b367  mov     [rbx+0A8h], rax
0x14002b36e  mov     dword ptr [rbx+0CCh], 0FFFFFFFFh
0x14002b378  mov     [rbx+0E8h], rax
0x14002b37f  mov     [rsp+230h+Block], rbx
0x14002b384  xorps   xmm0, xmm0
0x14002b387  movdqu  [rbp+130h+var_1B0], xmm0
0x14002b38c  xor     ebx, ebx
0x14002b38e  mov     [rbp+130h+var_1A0], rbx
0x14002b392  movdqu  xmmword ptr [rbp+130h+var_160], xmm0
0x14002b397  mov     [rbp+130h+var_150], rbx
0x14002b39b  lea     r8, [rsi+rsi*2]
0x14002b39f  shl     r8, 4
0x14002b3a3  add     r8, r14
0x14002b3a6  mov     rdx, r14
0x14002b3a9  lea     rcx, [rbp+130h+var_80]
0x14002b3b0  call    ??$?0PEBU_DEVPROPERTY@@$0A@@?$vector@U_DEVPROPERTY@@V?$allocator@U_DEVPROPERTY@@@std@@@std@@QEAA@PEBU_DEVPROPERTY@@0AEBV?$allocator@U_DEVPROPERTY@@@1@@Z; std::vector<_DEVPROPERTY>::vector<_DEVPROPERTY>(_DEVPROPERTY const *,_DEVPROPERTY const *,std::allocator<_DEVPROPERTY> const &)
0x14002b3b5  nop
0x14002b3b6  lea     rdx, [rbp+130h+var_80]
0x14002b3bd  lea     rcx, [rbp+130h+var_1B0]
0x14002b3c1  call    ??4?$vector@U_DEVPROPERTY@@V?$allocator@U_DEVPROPERTY@@@std@@@std@@QEAAAEAV01@AEBV01@@Z; std::vector<_DEVPROPERTY>::operator=(std::vector<_DEVPROPERTY> const &)
0x14002b3c6  nop
0x14002b3c7  lea     rcx, [rbp+130h+var_80]
0x14002b3ce  call    ??1?$vector@U_DEVPROPERTY@@V?$allocator@U_DEVPROPERTY@@@std@@@std@@QEAA@XZ; std::vector<_DEVPROPERTY>::~vector<_DEVPROPERTY>(void)
0x14002b3d3  or      r14, 0FFFFFFFFFFFFFFFFh
0x14002b3d7  test    rdi, rdi
0x14002b3da  jz      loc_14002B4CB
0x14002b3e0  mov     rcx, r14
0x14002b3e3  inc     rcx
0x14002b3e6  cmp     [rdi+rcx*2], bx
0x14002b3ea  jnz     short loc_14002B3E3
0x14002b3ec  test    rcx, rcx
0x14002b3ef  jz      loc_14002B4CB
0x14002b3f5  movups  xmm0, cs:PKEY_MIDI_AssociatedUMP
0x14002b3fc  movups  [rbp+130h+var_B0], xmm0
0x14002b403  mov     eax, cs:dword_14007A450
0x14002b409  mov     dword ptr [rbp+130h+var_A0], eax
0x14002b40f  mov     dword ptr [rbp+130h+var_A0+4], ebx
0x14002b415  mov     qword ptr [rbp+130h+var_A0+8], rbx
0x14002b41c  mov     dword ptr [rbp+130h+var_90], 12h
0x14002b426  lea     eax, ds:2[rcx*2]
0x14002b42d  mov     dword ptr [rbp+130h+var_90+4], eax
0x14002b433  mov     qword ptr [rbp+130h+var_90+8], rdi
0x14002b43a  mov     rdx, qword ptr [rbp+130h+var_1B0+8]
0x14002b43e  cmp     rdx, [rbp+130h+var_1A0]
0x14002b442  jz      short loc_14002B464
0x14002b444  movups  xmmword ptr [rdx], xmm0
0x14002b447  movups  xmm0, [rbp+130h+var_A0]
0x14002b44e  movups  xmmword ptr [rdx+10h], xmm0
0x14002b452  movups  xmm1, [rbp+130h+var_90]
0x14002b459  movups  xmmword ptr [rdx+20h], xmm1
0x14002b45d  add     qword ptr [rbp+130h+var_1B0+8], 30h ; '0'
0x14002b462  jmp     short loc_14002B474
0x14002b464  lea     r8, [rbp+130h+var_B0]
0x14002b46b  lea     rcx, [rbp+130h+var_1B0]
0x14002b46f  call    ??$_Emplace_reallocate@U_DEVPROPERTY@@@?$vector@U_DEVPROPERTY@@V?$allocator@U_DEVPROPERTY@@@std@@@std@@AEAAPEAU_DEVPROPERTY@@QEAU2@$$QEAU2@@Z; std::vector<_DEVPROPERTY>::_Emplace_reallocate<_DEVPROPERTY>(_DEVPROPERTY * const,_DEVPROPERTY &&)
0x14002b474  mov     rcx, [rsp+230h+Block]
0x14002b479  add     rcx, 0D0h
0x14002b480  mov     rdx, r14
0x14002b483  inc     rdx
0x14002b486  cmp     [rdi+rdx*2], bx
0x14002b48a  jnz     short loc_14002B483
0x14002b48c  cmp     rdx, [rcx+18h]
0x14002b490  ja      short loc_14002B4C1
0x14002b492  cmp     qword ptr [rcx+18h], 7
0x14002b497  jbe     short loc_14002B49E
0x14002b499  mov     rsi, [rcx]
0x14002b49c  jmp     short loc_14002B4A1
0x14002b49e  mov     rsi, rcx
0x14002b4a1  mov     [rcx+10h], rdx
0x14002b4a5  lea     rbx, [rdx+rdx]
0x14002b4a9  mov     r8, rbx; Size
0x14002b4ac  mov     rdx, rdi; Src
0x14002b4af  mov     rcx, rsi; void *
0x14002b4b2  call    memmove_0
0x14002b4b7  xor     eax, eax
0x14002b4b9  mov     [rsi+rbx], ax
0x14002b4bd  xor     ebx, ebx
0x14002b4bf  jmp     short loc_14002B53A
0x14002b4c1  mov     r9, rdi
0x14002b4c4  call    ??$_Reallocate_for@V_lambda_1_@?1???$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV23@QEBG_K@Z@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1???$_Assign@G@01@AEAAAEAV01@QEBG0@Z@PEBG@Z; std::wstring::_Reallocate_for<`std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)'::`2'::_lambda_1_,ushort const *>(unsigned __int64,`std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)'::`2'::_lambda_1_,ushort const *)
0x14002b4c9  jmp     short loc_14002B53A
0x14002b4cb  movups  xmm0, cs:PKEY_MIDI_AssociatedUMP
0x14002b4d2  movups  [rbp+130h+var_B0], xmm0
0x14002b4d9  mov     eax, cs:dword_14007A450
0x14002b4df  mov     dword ptr [rbp+130h+var_A0], eax
0x14002b4e5  mov     dword ptr [rbp+130h+var_A0+4], ebx
0x14002b4eb  mov     qword ptr [rbp+130h+var_A0+8], rbx
0x14002b4f2  mov     qword ptr [rbp+130h+var_90], rbx
0x14002b4f9  mov     qword ptr [rbp+130h+var_90+8], rbx
0x14002b500  mov     rdx, qword ptr [rbp+130h+var_1B0+8]
0x14002b504  cmp     rdx, [rbp+130h+var_1A0]
0x14002b508  jz      short loc_14002B52A
0x14002b50a  movups  xmmword ptr [rdx], xmm0
0x14002b50d  movups  xmm0, [rbp+130h+var_A0]
0x14002b514  movups  xmmword ptr [rdx+10h], xmm0
0x14002b518  movups  xmm1, [rbp+130h+var_90]
0x14002b51f  movups  xmmword ptr [rdx+20h], xmm1
0x14002b523  add     qword ptr [rbp+130h+var_1B0+8], 30h ; '0'
0x14002b528  jmp     short loc_14002B53A
0x14002b52a  lea     r8, [rbp+130h+var_B0]
0x14002b531  lea     rcx, [rbp+130h+var_1B0]
0x14002b535  call    ??$_Emplace_reallocate@U_DEVPROPERTY@@@?$vector@U_DEVPROPERTY@@V?$allocator@U_DEVPROPERTY@@@std@@@std@@AEAAPEAU_DEVPROPERTY@@QEAU2@$$QEAU2@@Z; std::vector<_DEVPROPERTY>::_Emplace_reallocate<_DEVPROPERTY>(_DEVPROPERTY * const,_DEVPROPERTY &&)
0x14002b53a  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_MIDI2ContainerIds@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_MIDI2ContainerIds@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_MIDI2ContainerIds> `wil::Feature<__WilFeatureTraits_Feature_Servicing_MIDI2ContainerIds>::GetImpl(void)'::`2'::impl
0x14002b541  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_MIDI2ContainerIds@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_MIDI2ContainerIds>::__private_IsEnabled(void)
0x14002b546  test    al, al
0x14002b548  jz      loc_14002B623
0x14002b54e  mov     rcx, [rbp+130h+var_168]
0x14002b552  test    rcx, rcx
0x14002b555  jz      short loc_14002B594
0x14002b557  test    r12d, r12d
0x14002b55a  jz      short loc_14002B594
0x14002b55c  lea     r8, [r12+r12*2]
0x14002b560  shl     r8, 4
0x14002b564  add     r8, rcx
0x14002b567  mov     rdx, rcx
0x14002b56a  lea     rcx, [rbp+130h+var_80]
0x14002b571  call    ??$?0PEBU_DEVPROPERTY@@$0A@@?$vector@U_DEVPROPERTY@@V?$allocator@U_DEVPROPERTY@@@std@@@std@@QEAA@PEBU_DEVPROPERTY@@0AEBV?$allocator@U_DEVPROPERTY@@@1@@Z; std::vector<_DEVPROPERTY>::vector<_DEVPROPERTY>(_DEVPROPERTY const *,_DEVPROPERTY const *,std::allocator<_DEVPROPERTY> const &)
0x14002b576  nop
0x14002b577  lea     rdx, [rbp+130h+var_80]
0x14002b57e  lea     rcx, [rbp+130h+var_160]
0x14002b582  call    ??4?$vector@U_DEVPROPERTY@@V?$allocator@U_DEVPROPERTY@@@std@@@std@@QEAAAEAV01@AEBV01@@Z; std::vector<_DEVPROPERTY>::operator=(std::vector<_DEVPROPERTY> const &)
0x14002b587  nop
0x14002b588  lea     rcx, [rbp+130h+var_80]
0x14002b58f  call    ??1?$vector@U_DEVPROPERTY@@V?$allocator@U_DEVPROPERTY@@@std@@@std@@QEAA@XZ; std::vector<_DEVPROPERTY>::~vector<_DEVPROPERTY>(void)
0x14002b594  movups  xmm0, xmmword ptr cs:DEVPKEY_Device_FriendlyName.fmtid.Data1
0x14002b59b  movups  [rbp+130h+var_B0], xmm0
0x14002b5a2  mov     eax, cs:DEVPKEY_Device_FriendlyName.pid
0x14002b5a8  mov     dword ptr [rbp+130h+var_A0], eax
0x14002b5ae  mov     dword ptr [rbp+130h+var_A0+4], ebx
0x14002b5b4  mov     qword ptr [rbp+130h+var_A0+8], rbx
0x14002b5bb  mov     dword ptr [rbp+130h+var_90], 12h
0x14002b5c5  mov     rcx, qword ptr [rbp+130h+var_D0]
0x14002b5c9  mov     rax, r14
0x14002b5cc  inc     rax
0x14002b5cf  cmp     [rcx+rax*2], bx
0x14002b5d3  jnz     short loc_14002B5CC
0x14002b5d5  lea     eax, ds:2[rax*2]
0x14002b5dc  mov     dword ptr [rbp+130h+var_90+4], eax
0x14002b5e2  mov     qword ptr [rbp+130h+var_90+8], rcx
0x14002b5e9  mov     rdx, qword ptr [rbp+130h+var_160+8]
0x14002b5ed  cmp     rdx, [rbp+130h+var_150]
0x14002b5f1  jz      short loc_14002B613
0x14002b5f3  movups  xmmword ptr [rdx], xmm0
0x14002b5f6  movups  xmm0, [rbp+130h+var_A0]
0x14002b5fd  movups  xmmword ptr [rdx+10h], xmm0
0x14002b601  movups  xmm1, [rbp+130h+var_90]
0x14002b608  movups  xmmword ptr [rdx+20h], xmm1
0x14002b60c  add     qword ptr [rbp+130h+var_160+8], 30h ; '0'
0x14002b611  jmp     short loc_14002B623
0x14002b613  lea     r8, [rbp+130h+var_B0]
0x14002b61a  lea     rcx, [rbp+130h+var_160]
0x14002b61e  call    ??$_Emplace_reallocate@U_DEVPROPERTY@@@?$vector@U_DEVPROPERTY@@V?$allocator@U_DEVPROPERTY@@@std@@@std@@AEAAPEAU_DEVPROPERTY@@QEAU2@$$QEAU2@@Z; std::vector<_DEVPROPERTY>::_Emplace_reallocate<_DEVPROPERTY>(_DEVPROPERTY * const,_DEVPROPERTY &&)
0x14002b623  mov     [rsp+230h+var_1C4], r14b
0x14002b628  movups  xmm0, xmmword ptr cs:DEVPKEY_Device_PresenceNotForDevice.fmtid.Data1
0x14002b62f  movups  [rbp+130h+var_B0], xmm0
0x14002b636  mov     eax, cs:DEVPKEY_Device_PresenceNotForDevice.pid
0x14002b63c  mov     dword ptr [rbp+130h+var_A0], eax
0x14002b642  mov     dword ptr [rbp+130h+var_A0+4], ebx
0x14002b648  mov     qword ptr [rbp+130h+var_A0+8], rbx
0x14002b64f  mov     edi, 11h
0x14002b654  mov     dword ptr [rbp+130h+var_90], edi
0x14002b65a  lea     esi, [rdi-10h]
0x14002b65d  mov     dword ptr [rbp+130h+var_90+4], esi
0x14002b663  lea     rax, [rsp+230h+var_1C4]
0x14002b668  mov     qword ptr [rbp+130h+var_90+8], rax
0x14002b66f  mov     rdx, qword ptr [rbp+130h+var_1B0+8]
0x14002b673  cmp     rdx, [rbp+130h+var_1A0]
0x14002b677  jz      short loc_14002B6A0
0x14002b679  movups  xmmword ptr [rdx], xmm0
0x14002b67c  movups  xmm0, [rbp+130h+var_A0]
0x14002b683  movups  xmmword ptr [rdx+10h], xmm0
0x14002b687  movups  xmm1, [rbp+130h+var_90]
0x14002b68e  movups  xmmword ptr [rdx+20h], xmm1
0x14002b692  mov     rdx, qword ptr [rbp+130h+var_1B0+8]
0x14002b696  add     rdx, 30h ; '0'
0x14002b69a  mov     qword ptr [rbp+130h+var_1B0+8], rdx
0x14002b69e  jmp     short loc_14002B6B4
0x14002b6a0  lea     r8, [rbp+130h+var_B0]
0x14002b6a7  lea     rcx, [rbp+130h+var_1B0]
0x14002b6ab  call    ??$_Emplace_reallocate@U_DEVPROPERTY@@@?$vector@U_DEVPROPERTY@@V?$allocator@U_DEVPROPERTY@@@std@@@std@@AEAAPEAU_DEVPROPERTY@@QEAU2@$$QEAU2@@Z; std::vector<_DEVPROPERTY>::_Emplace_reallocate<_DEVPROPERTY>(_DEVPROPERTY * const,_DEVPROPERTY &&)
0x14002b6b0  mov     rdx, qword ptr [rbp+130h+var_1B0+8]
0x14002b6b4  movups  xmm0, xmmword ptr cs:DEVPKEY_Device_NoConnectSound.fmtid.Data1
0x14002b6bb  movups  [rbp+130h+var_B0], xmm0
0x14002b6c2  mov     eax, cs:DEVPKEY_Device_NoConnectSound.pid
0x14002b6c8  mov     dword ptr [rbp+130h+var_A0], eax
0x14002b6ce  mov     dword ptr [rbp+130h+var_A0+4], ebx
0x14002b6d4  mov     qword ptr [rbp+130h+var_A0+8], rbx
0x14002b6db  mov     dword ptr [rbp+130h+var_90], edi
0x14002b6e1  mov     dword ptr [rbp+130h+var_90+4], esi
0x14002b6e7  lea     rax, [rsp+230h+var_1C4]
0x14002b6ec  mov     qword ptr [rbp+130h+var_90+8], rax
0x14002b6f3  cmp     rdx, [rbp+130h+var_1A0]
0x14002b6f7  jz      short loc_14002B719
0x14002b6f9  movups  xmmword ptr [rdx], xmm0
0x14002b6fc  movups  xmm0, [rbp+130h+var_A0]
0x14002b703  movups  xmmword ptr [rdx+10h], xmm0
0x14002b707  movups  xmm1, [rbp+130h+var_90]
0x14002b70e  movups  xmmword ptr [rdx+20h], xmm1
0x14002b712  add     qword ptr [rbp+130h+var_1B0+8], 30h ; '0'
  ... truncated ...
```
