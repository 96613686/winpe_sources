# CMidi2LoopbackMidiEndpointManager::CreateSingleEndpoint(std::shared_ptr<MidiLoopbackDeviceDefinition>)

- ea: `0x18001d454`
- end: `0x18001e442`
- name: `?CreateSingleEndpoint@CMidi2LoopbackMidiEndpointManager@@AEAAJV?$shared_ptr@UMidiLoopbackDeviceDefinition@@@std@@@Z`
- size: `4078`
- prototype: ``
- caller_count: `1`
- callee_count: `32`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001cd54`

## callees

- `0x1800018e8`
- `0x180001c34`
- `0x180001f74`
- `0x180002164`
- `0x180004180`
- `0x18000500c`
- `0x18000a024`
- `0x18000b740`
- `0x18000ccd8`
- `0x18000e178`
- `0x18000f0a4`
- `0x18000feb0`
- `0x180013294`
- `0x18001338c`
- `0x1800134cc`
- `0x18001393c`
- `0x1800164f0`
- `0x18001b624`
- `0x18001bd50`
- `0x18001c188`
- `0x18001c5d8`
- `0x18001c6b0`
- `0x18001c81c`
- `0x18001c95c`
- `0x18001c9e8`
- `0x18001cbc4`
- `0x18001d454`
- `0x180020d84`
- `0x1800210e4`
- `0x18002c91c`
- `0x18002d400`
- `0x180032010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001dfe7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001dfe7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001dfd4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001dfd4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001dfdf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001e0d4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001e37e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001dfdf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001e0d4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001e37e`

## string_xrefs

- `0x18001d657`: `CMidi2LoopbackMidiEndpointManager::CreateSingleEndpoint`
- `0x18001e1bf`: `CMidi2LoopbackMidiEndpointManager::CreateSingleEndpoint`
- `0x18001e213`: `CMidi2LoopbackMidiEndpointManager::CreateSingleEndpoint`

## pseudocode

```c
// Hidden C++ exception states: #wind=20
__int64 __fastcall CMidi2LoopbackMidiEndpointManager::CreateSingleEndpoint(__int64 a1, _QWORD *a2)
{
  unsigned int v4; // esi
  __int64 v5; // rdx
  volatile signed __int32 *v6; // rbx
  _QWORD *v8; // rax
  volatile signed __int32 *v9; // rbx
  const char *v10; // rax
  __int64 v11; // rdx
  _DWORD *v12; // r8
  int v13; // r9d
  _QWORD *v14; // rax
  _QWORD *v15; // rcx
  const wchar_t *v16; // rcx
  _QWORD *v17; // rcx
  _QWORD *v18; // rcx
  void *v19; // rax
  __int64 v20; // rbx
  __int128 *v21; // rdx
  void *v22; // rax
  __int64 v23; // rbx
  void *v24; // rax
  _DWORD *v25; // r8
  int v26; // r9d
  const char *v27; // rax
  const wchar_t *v28; // rax
  const wchar_t *v29; // rax
  const char *v30; // rax
  _QWORD *v31; // rax
  _QWORD *v32; // rcx
  _QWORD *v33; // rcx
  __int64 v34; // rdx
  __int64 v35; // rax
  _QWORD *v36; // rax
  _QWORD *v37; // rax
  _DWORD *v38; // r8
  int v39; // r9d
  const char *v40; // rax
  const wchar_t *v41; // rax
  const char *v42; // rcx
  _QWORD *v43; // rax
  __int128 *v44; // rax
  _QWORD *v45; // rax
  _QWORD *v46; // rax
  _QWORD *v47; // rax
  _QWORD *v48; // rax
  __int64 v49; // rdx
  __int64 v50; // rdx
  __int64 v51; // rdx
  int v52; // eax
  int v53; // eax
  __int64 v54; // r15
  __int64 (__fastcall *v55)(__int64, _QWORD *, _QWORD, __int64); // r12
  void *v56; // r14
  DWORD LastError; // ebx
  _QWORD *v58; // rdx
  int v59; // eax
  unsigned int v60; // r14d
  volatile signed __int32 *v61; // rbx
  _DWORD *v62; // r8
  int v63; // r9d
  const wchar_t *v64; // rax
  const char *v65; // rcx
  __int64 v66; // r8
  __int64 v67; // rax
  _DWORD *v68; // r8
  int v69; // r9d
  const char *v70; // rax
  const char *v71; // rcx
  volatile signed __int32 *v72; // rbx
  int v73; // [rsp+20h] [rbp-E0h]
  int v74; // [rsp+20h] [rbp-E0h]
  const char *v75; // [rsp+28h] [rbp-D8h]
  const char *v76; // [rsp+70h] [rbp-90h] BYREF
  const char *v77; // [rsp+78h] [rbp-88h] BYREF
  const wchar_t *v78; // [rsp+80h] [rbp-80h] BYREF
  const wchar_t *v79; // [rsp+88h] [rbp-78h] BYREF
  const char *v80; // [rsp+90h] [rbp-70h] BYREF
  LPVOID pv; // [rsp+98h] [rbp-68h]
  int v82[2]; // [rsp+A0h] [rbp-60h] BYREF
  __int128 v83; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v84; // [rsp+B8h] [rbp-48h]
  __int128 v85; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v86; // [rsp+D0h] [rbp-30h]
  _QWORD *v87; // [rsp+D8h] [rbp-28h] BYREF
  const wchar_t *v88; // [rsp+E0h] [rbp-20h] BYREF
  _QWORD *v89; // [rsp+E8h] [rbp-18h] BYREF
  __int128 v90; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v91; // [rsp+100h] [rbp+0h]
  _OWORD v92[3]; // [rsp+108h] [rbp+8h] BYREF
  __int64 v93; // [rsp+138h] [rbp+38h]
  _QWORD *v94; // [rsp+140h] [rbp+40h]
  int v95; // [rsp+150h] [rbp+50h] BYREF
  _QWORD *v96; // [rsp+158h] [rbp+58h]
  int v97; // [rsp+178h] [rbp+78h]
  _QWORD *v98; // [rsp+180h] [rbp+80h]
  int v99[4]; // [rsp+1A0h] [rbp+A0h] BYREF
  int v100; // [rsp+1B0h] [rbp+B0h]
  _QWORD *v101; // [rsp+1B8h] [rbp+B8h]
  __int128 *v102; // [rsp+1C0h] [rbp+C0h]
  _QWORD *v103; // [rsp+1C8h] [rbp+C8h]
  __int64 v104; // [rsp+1D0h] [rbp+D0h]
  _QWORD *v105; // [rsp+1D8h] [rbp+D8h]
  _QWORD *v106; // [rsp+1E0h] [rbp+E0h]
  _QWORD *v107; // [rsp+1E8h] [rbp+E8h]
  int v108; // [rsp+1F8h] [rbp+F8h]
  int v109; // [rsp+1FCh] [rbp+FCh]
  int v110; // [rsp+200h] [rbp+100h]
  __int128 Src; // [rsp+210h] [rbp+110h] BYREF
  __int128 v112; // [rsp+220h] [rbp+120h]
  __int128 v113; // [rsp+230h] [rbp+130h]
  _QWORD v114[3]; // [rsp+240h] [rbp+140h] BYREF
  unsigned __int64 v115; // [rsp+258h] [rbp+158h]
  __int128 v116; // [rsp+260h] [rbp+160h] BYREF
  __int128 v117; // [rsp+270h] [rbp+170h]
  int v118; // [rsp+280h] [rbp+180h] BYREF
  char v119; // [rsp+284h] [rbp+184h]
  int v120; // [rsp+286h] [rbp+186h]
  _OWORD v121[2]; // [rsp+290h] [rbp+190h] BYREF
  int v122; // [rsp+2B0h] [rbp+1B0h] BYREF
  char v123; // [rsp+2B4h] [rbp+1B4h]
  int v124; // [rsp+2B6h] [rbp+1B6h]
  _OWORD v125[2]; // [rsp+2C0h] [rbp+1C0h] BYREF
  __int128 v126; // [rsp+2E0h] [rbp+1E0h] BYREF
  __int128 v127; // [rsp+2F0h] [rbp+1F0h]
  _QWORD v128[3]; // [rsp+300h] [rbp+200h] BYREF
  unsigned __int64 v129; // [rsp+318h] [rbp+218h]
  _QWORD v130[3]; // [rsp+320h] [rbp+220h] BYREF
  unsigned __int64 v131; // [rsp+338h] [rbp+238h]
  _QWORD v132[3]; // [rsp+340h] [rbp+240h] BYREF
  unsigned __int64 v133; // [rsp+358h] [rbp+258h]
  _OWORD v134[2]; // [rsp+360h] [rbp+260h] BYREF
  _BYTE v135[32]; // [rsp+380h] [rbp+280h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+3E8h] [rbp+2E8h]

  v94 = a2;
  if ( !*(_BYTE *)(a1 + 16) )
  {
    v4 = -2147418113;
    v5 = 226;
    goto LABEL_3;
  }
  if ( !*(_QWORD *)(a1 + 88) )
  {
    v4 = -2147467261;
    v5 = 227;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v5,
      (unsigned int)"avcore\\midi2\\transport\\loopbackmiditransport\\midi2.loopbackmidiendpointmanager.cpp",
      (const char *)v4,
      v73);
    v6 = (volatile signed __int32 *)a2[1];
    if ( v6 && _InterlockedExchangeAdd(v6 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v6)(v6);
      if ( _InterlockedExchangeAdd(v6 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v6 + 8LL))(v6);
    }
    return v4;
  }
  v8 = (_QWORD *)*a2;
  if ( !*a2 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xE5,
      (unsigned int)"avcore\\midi2\\transport\\loopbackmiditransport\\midi2.loopbackmidiendpointmanager.cpp",
      (const char *)0x80070057LL,
      v73);
LABEL_12:
    v9 = (volatile signed __int32 *)a2[1];
    if ( !v9 )
      return 2147942487LL;
    if ( _InterlockedExchangeAdd(v9 + 2, 0xFFFFFFFF) != 1 )
      return 2147942487LL;
    (**(void (__fastcall ***)(volatile signed __int32 *))v9)(v9);
    if ( _InterlockedExchangeAdd(v9 + 3, 0xFFFFFFFF) != 1 )
      return 2147942487LL;
    goto LABEL_25;
  }
  if ( !v8[6] )
  {
    v10 = "Empty endpoint name";
    v11 = 231;
LABEL_18:
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)v11,
      (unsigned int)"avcore\\midi2\\transport\\loopbackmiditransport\\midi2.loopbackmidiendpointmanager.cpp",
      (const char *)0x80070057LL,
      (int)v10,
      v75);
    goto LABEL_12;
  }
  if ( !v8[18] )
  {
    v10 = "Empty endpoint prefix";
    v11 = 232;
    goto LABEL_18;
  }
  if ( !v8[14] )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0xE9,
      (unsigned int)"avcore\\midi2\\transport\\loopbackmiditransport\\midi2.loopbackmidiendpointmanager.cpp",
      (const char *)0x80070057LL,
      (int)"Empty endpoint unique id",
      v75);
    v9 = (volatile signed __int32 *)a2[1];
    if ( !v9 )
      return 2147942487LL;
    if ( _InterlockedExchangeAdd(v9 + 2, 0xFFFFFFFF) != 1 )
      return 2147942487LL;
    (**(void (__fastcall ***)(volatile signed __int32 *))v9)(v9);
    if ( _InterlockedExchangeAdd(v9 + 3, 0xFFFFFFFF) != 1 )
      return 2147942487LL;
LABEL_25:
    (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v9 + 8LL))(v9);
    return 2147942487LL;
  }
  v12 = (_DWORD *)*((_QWORD *)MidiLoopbackMidiTransportTelemetryProvider::Instance() + 1);
  if ( *v12 > 4u )
  {
    v14 = (_QWORD *)*a2;
    v15 = (_QWORD *)(*a2 + 64LL);
    if ( *(_QWORD *)(*a2 + 88LL) > 7u )
      v15 = (_QWORD *)*v15;
    v87 = v15;
    v16 = (const wchar_t *)(v14 + 4);
    if ( v14[7] > 7u )
      v16 = *(const wchar_t **)v16;
    v88 = v16;
    v17 = v14 + 12;
    if ( v14[15] > 7u )
      v17 = (_QWORD *)*v17;
    v89 = v17;
    v18 = v14 + 16;
    if ( v14[19] > 7u )
      v18 = (_QWORD *)*v18;
    *(_QWORD *)v82 = v18;
    if ( v14[3] > 7u )
      v14 = (_QWORD *)*v14;
    v77 = (const char *)v14;
    v78 = L"Enter";
    v79 = (const wchar_t *)a1;
    v80 = "CMidi2LoopbackMidiEndpointManager::CreateSingleEndpoint";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
      (_DWORD)v12,
      (unsigned int)byte_180058661,
      (_DWORD)v12,
      v13,
      (__int64)&v80,
      (__int64)&v79,
      (__int64)&v78,
      (__int64)&v77,
      (__int64)v82,
      (__int64)&v89,
      (__int64)&v88,
      (__int64)&v87);
  }
  v126 = 0;
  v127 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v126, L"LOOP");
  std::wstring::wstring(v132, *a2 + 32LL);
  std::wstring::wstring(v130, *a2 + 64LL);
  v83 = 0;
  v84 = 0;
  v116 = 0;
  v117 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v116, &S2);
  memset(v134, 0, sizeof(v134));
  std::wstring::_Construct<1,unsigned short const *>(v134, &S2);
  v19 = (void *)std::wstring::wstring(v135, v134);
  v20 = *(_QWORD *)(WindowsMidiServicesInternal::TrimmedWStringCopy(&Src, v19) + 16);
  std::wstring::~wstring(&Src);
  if ( v20 )
  {
    v21 = v134;
  }
  else
  {
    v22 = (void *)std::wstring::wstring(&Src, &v116);
    v23 = *(_QWORD *)(WindowsMidiServicesInternal::TrimmedWStringCopy(v135, v22) + 16);
    std::wstring::~wstring(v135);
    v21 = &v116;
    if ( !v23 )
      v21 = (__int128 *)v132;
  }
  v24 = (void *)std::wstring::wstring(&Src, v21);
  WindowsMidiServicesInternal::TrimmedWStringCopy(v114, v24);
  std::wstring::~wstring(v134);
  std::wstring::~wstring(&v116);
  v25 = (_DWORD *)*((_QWORD *)MidiLoopbackMidiTransportTelemetryProvider::Instance() + 1);
  if ( *v25 > 4u )
  {
    v27 = (const char *)v130;
    if ( v131 > 7 )
      v27 = (const char *)v130[0];
    v80 = v27;
    v28 = (const wchar_t *)v132;
    if ( v133 > 7 )
      v28 = (const wchar_t *)v132[0];
    v79 = v28;
    v29 = (const wchar_t *)&v126;
    if ( *((_QWORD *)&v127 + 1) > 7u )
      v29 = (const wchar_t *)v126;
    v78 = v29;
    v30 = (const char *)v114;
    if ( v115 > 7 )
      v30 = (const char *)v114[0];
    v77 = v30;
    v31 = (_QWORD *)*a2;
    v32 = (_QWORD *)(*a2 + 96LL);
    if ( *(_QWORD *)(*a2 + 120LL) > 7u )
      v32 = (_QWORD *)*v32;
    *(_QWORD *)v82 = v32;
    if ( v31[3] > 7u )
      v31 = (_QWORD *)*v31;
    v89 = v31;
    v88 = L"Adding endpoint properties";
    v87 = (_QWORD *)a1;
    v76 = "CMidi2LoopbackMidiEndpointManager::CreateSingleEndpoint";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
      (_DWORD)v25,
      (unsigned int)byte_1800585CB,
      (_DWORD)v25,
      v26,
      (__int64)&v76,
      (__int64)&v87,
      (__int64)&v88,
      (__int64)&v89,
      (__int64)v82,
      (__int64)&v77,
      (__int64)&v78,
      (__int64)&v79,
      (__int64)&v80);
  }
  Src = PKEY_MIDI_VirtualMidiEndpointAssociator;
  v112 = 0x389u;
  LODWORD(v113) = 18;
  v33 = (_QWORD *)*a2;
  DWORD1(v113) = 2 * *(_DWORD *)(*a2 + 16LL) + 2;
  if ( v33[3] > 7u )
    v33 = (_QWORD *)*v33;
  *((_QWORD *)&v113 + 1) = v33;
  v34 = *((_QWORD *)&v83 + 1);
  if ( *((_QWORD *)&v83 + 1) == v84 )
  {
    std::vector<_DEVPROPERTY>::_Emplace_reallocate<_DEVPROPERTY>(&v83, *((_QWORD *)&v83 + 1), &Src);
  }
  else
  {
    **((_OWORD **)&v83 + 1) = PKEY_MIDI_VirtualMidiEndpointAssociator;
    *(_OWORD *)(v34 + 16) = v112;
    *(_OWORD *)(v34 + 32) = v113;
    *((_QWORD *)&v83 + 1) += 48LL;
  }
  memset_0(&v95, 0, 0x48u);
  v95 = 72;
  if ( (unsigned __int64)(0x7FFFFFFFFFFFFFFELL - *(_QWORD *)(*a2 + 144LL)) < *(_QWORD *)(*a2 + 112LL) )
    std::_Xlen_string();
  v74 = *(_QWORD *)(*a2 + 144LL);
  std::wstring::wstring(&v116);
  v35 = std::wstring::wstring(&Src, &v116);
  WindowsMidiServicesInternal::ToUpperTrimmedWStringCopy(v128, v35);
  std::wstring::~wstring(&v116);
  v36 = v128;
  if ( v129 > 7 )
    v36 = (_QWORD *)v128[0];
  v96 = v36;
  v97 = 0;
  v37 = v114;
  if ( v115 > 7 )
    v37 = (_QWORD *)v114[0];
  v98 = v37;
  pv = 0;
  v38 = (_DWORD *)*((_QWORD *)MidiLoopbackMidiTransportTelemetryProvider::Instance() + 1);
  if ( *v38 > 4u )
  {
    v40 = (const char *)v128;
    if ( v129 > 7 )
      v40 = (const char *)v128[0];
    v76 = v40;
    v41 = (const wchar_t *)*a2;
    v42 = (const char *)(*a2 + 96LL);
    if ( *(_QWORD *)(*a2 + 120LL) > 7u )
      v42 = *(const char **)v42;
    v80 = v42;
    if ( *((_QWORD *)v41 + 3) > 7u )
      v41 = *(const wchar_t **)v41;
    v79 = v41;
    v78 = L"Activating endpoint";
    v77 = (const char *)a1;
    *(_QWORD *)v82 = "CMidi2LoopbackMidiEndpointManager::CreateSingleEndpoint";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
      (_DWORD)v38,
      (unsigned int)byte_180058569,
      (_DWORD)v38,
      v39,
      (__int64)v82,
      (__int64)&v77,
      (__int64)&v78,
      (__int64)&v79,
      (__int64)&v80,
      (__int64)&v76);
  }
  memset_0(v99, 0, 0x68u);
  *(_OWORD *)v99 = *(_OWORD *)(a1 + 36);
  v100 = 0;
  v43 = v114;
  if ( v115 > 7 )
    v43 = (_QWORD *)v114[0];
  v101 = v43;
  v44 = &v126;
  if ( *((_QWORD *)&v127 + 1) > 7u )
    v44 = (__int128 *)v126;
  v102 = v44;
  v45 = v132;
  if ( v133 > 7 )
    v45 = (_QWORD *)v132[0];
  v103 = v45;
  v104 = 0;
  v46 = v114;
  if ( v115 > 7 )
    v46 = (_QWORD *)v114[0];
  v105 = v46;
  if ( v130[2] )
  {
    v47 = v130;
    if ( v131 > 7 )
      v47 = (_QWORD *)v130[0];
    v106 = v47;
  }
  else
  {
    v106 = 0;
  }
  v48 = (_QWORD *)(*a2 + 96LL);
  if ( *(_QWORD *)(*a2 + 120LL) > 7u )
    v48 = (_QWORD *)*v48;
  v107 = v48;
  v108 = 2;
  v109 = 2;
  v110 = 15;
  v85 = 0;
  v86 = 0;
  v124 = 0;
  v125[0] = 0;
  v125[1] = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v125[0]) = 0;
  v122 = 16777473;
  v123 = 17;
  std::wstring::operator=(v125, v114);
  v49 = *((_QWORD *)&v85 + 1);
  if ( *((_QWORD *)&v85 + 1) == v86 )
  {
    std::vector<WindowsMidiServicesInternal::GroupTerminalBlockInternal>::_Emplace_reallocate<WindowsMidiServicesInternal::GroupTerminalBlockInternal const &>(
      &v85,
      *((_QWORD *)&v85 + 1),
      &v122);
  }
  else
  {
    **((_DWORD **)&v85 + 1) = v122;
    *(_BYTE *)(v49 + 4) = v123;
    *(_DWORD *)(v49 + 6) = v124;
    std::wstring::wstring(v49 + 16, v125);
    *((_QWORD *)&v85 + 1) += 48LL;
  }
  v120 = 0;
  v121[0] = 0;
  v121[1] = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v121[0]) = 0;
  v118 = 16777729;
  v119 = 17;
  std::wstring::operator=(v121, v114);
  v50 = *((_QWORD *)&v85 + 1);
  if ( *((_QWORD *)&v85 + 1) == v86 )
  {
    std::vector<WindowsMidiServicesInternal::GroupTerminalBlockInternal>::_Emplace_reallocate<WindowsMidiServicesInternal::GroupTerminalBlockInternal const &>(
      &v85,
      *((_QWORD *)&v85 + 1),
      &v118);
  }
  else
  {
    **((_DWORD **)&v85 + 1) = v118;
    *(_BYTE *)(v50 + 4) = v119;
    *(_DWORD *)(v50 + 6) = v120;
    std::wstring::wstring(v50 + 16, v121);
    *((_QWORD *)&v85 + 1) += 48LL;
  }
  v90 = 0;
  v91 = 0;
  if ( (unsigned __int8)WindowsMidiServicesInternal::WriteGroupTerminalBlocksToPropertyDataPointer(&v85, &v90) )
  {
    Src = PKEY_MIDI_GroupTerminalBlocks;
    v112 = 0x32u;
    LODWORD(v113) = 4099;
    DWORD1(v113) = DWORD2(v90) - v90;
    *((_QWORD *)&v113 + 1) = v90;
    v51 = *((_QWORD *)&v83 + 1);
    if ( *((_QWORD *)&v83 + 1) == v84 )
    {
      std::vector<_DEVPROPERTY>::_Emplace_reallocate<_DEVPROPERTY>(&v83, *((_QWORD *)&v83 + 1), &Src);
    }
    else
    {
      **((_OWORD **)&v83 + 1) = PKEY_MIDI_GroupTerminalBlocks;
      *(_OWORD *)(v51 + 16) = v112;
      *(_OWORD *)(v51 + 32) = v113;
      *((_QWORD *)&v83 + 1) += 48LL;
    }
  }
  memset(v92, 0, sizeof(v92));
  v93 = 0;
  WindowsMidiServicesNamingLib::MidiEndpointNameTable::MidiEndpointNameTable((WindowsMidiServicesNamingLib::MidiEndpointNameTable *)v92);
  if ( !*(_BYTE *)(*a2 + 224LL) )
  {
    v116 = 0;
    v117 = 0;
    std::wstring::_Construct<1,unsigned short const *>(&v116, &S2);
    v52 = WindowsMidiServicesNamingLib::MidiEndpointNameTable::PopulateAllEntriesForNativeUmpDevice(v92, &v116, &v85);
    if ( v52 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x178,
        (unsigned int)"avcore\\midi2\\transport\\loopbackmiditransport\\midi2.loopbackmidiendpointmanager.cpp",
        (const char *)(unsigned int)v52,
        v74);
    std::wstring::~wstring(&v116);
    v53 = WindowsMidiServicesNamingLib::MidiEndpointNameTable::WriteProperties(v92, &v83);
    if ( v53 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x179,
        (unsigned int)"avcore\\midi2\\transport\\loopbackmiditransport\\midi2.loopbackmidiendpointmanager.cpp",
        (const char *)(unsigned int)v53,
        v74);
  }
  v54 = *(_QWORD *)(a1 + 88);
  v55 = *(__int64 (__fastcall **)(__int64, _QWORD *, _QWORD, __int64))(*(_QWORD *)v54 + 40LL);
  v56 = pv;
  if ( pv )
  {
    LastError = GetLastError();
    CoTaskMemFree(v56);
    SetLastError(LastError);
  }
  pv = 0;
  v58 = (_QWORD *)(a1 + 56);
  if ( *(_QWORD *)(a1 + 80) > 7u )
    v58 = (_QWORD *)*v58;
  v59 = v55(v54, v58, *(unsigned __int8 *)(*a2 + 224LL), 2);
  v60 = v59;
  if ( v59 >= 0 )
  {
    v62 = (_DWORD *)*((_QWORD *)MidiLoopbackMidiTransportTelemetryProvider::Instance() + 1);
    if ( *v62 > 4u )
    {
      v76 = (const char *)pv;
      v64 = (const wchar_t *)*a2;
      v65 = (const char *)(*a2 + 96LL);
      if ( *(_QWORD *)(*a2 + 120LL) > 7u )
        v65 = *(const char **)v65;
      v80 = v65;
      if ( *((_QWORD *)v64 + 3) > 7u )
        v64 = *(const wchar_t **)v64;
      v79 = v64;
      v78 = L"Endpoint activated";
      v77 = (const char *)a1;
      *(_QWORD *)v82 = "CMidi2LoopbackMidiEndpointManager::CreateSingleEndpoint";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
        (_DWORD)v62,
        (unsigned int)byte_1800584FB,
        (_DWORD)v62,
        v63,
        (__int64)v82,
        (__int64)&v77,
        (__int64)&v78,
        (__int64)&v79,
        (__int64)&v80,
        (__int64)&v76);
    }
    std::wstring::operator=(*a2 + 160LL, v128);
    v116 = 0;
    v117 = 0;
    v66 = -1;
    do
      ++v66;
    while ( *((_WORD *)pv + v66) );
    std::wstring::_Construct<1,unsigned short const *>(&v116, pv);
    v67 = std::wstring::wstring(&Src, &v116);
    WindowsMidiServicesInternal::ToLowerTrimmedWStringCopy(v134, v67);
    std::wstring::operator=(*a2 + 192LL, v134);
    std::wstring::~wstring(v134);
    std::wstring::~wstring(&v116);
    v68 = (_DWORD *)*((_QWORD *)MidiLoopbackMidiTransportTelemetryProvider::Instance() + 1);
    if ( *v68 > 4u )
    {
      v70 = (const char *)*a2;
      v71 = (const char *)(*a2 + 96LL);
      if ( *(_QWORD *)(*a2 + 120LL) > 7u )
        v71 = *(const char **)v71;
      v76 = v71;
      if ( *((_QWORD *)v70 + 3) > 7u )
        v70 = *(const char **)v70;
      v80 = v70;
      v79 = L"Done";
      v78 = (const wchar_t *)a1;
      v77 = "CMidi2LoopbackMidiEndpointManager::CreateSingleEndpoint";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
        (_DWORD)v68,
        (unsigned int)&word_1800584A6,
        (_DWORD)v68,
        v69,
        (__int64)&v77,
        (__int64)&v78,
        (__int64)&v79,
        (__int64)&v80,
        (__int64)&v76);
    }
    WindowsMidiServicesNamingLib::MidiEndpointNameTable::~MidiEndpointNameTable((WindowsMidiServicesNamingLib::MidiEndpointNameTable *)v92);
    std::vector<enum std::byte>::~vector<enum std::byte>(&v90);
    std::wstring::~wstring(v121);
    std::wstring::~wstring(v125);
    std::vector<WindowsMidiServicesInternal::GroupTerminalBlockInternal>::~vector<WindowsMidiServicesInternal::GroupTerminalBlockInternal>(&v85);
    if ( pv )
      CoTaskMemFree(pv);
    std::wstring::~wstring(v128);
    std::wstring::~wstring(v114);
    std::vector<_DEVPROPERTY>::~vector<_DEVPROPERTY>(&v83);
    std::wstring::~wstring(v130);
    std::wstring::~wstring(v132);
    std::wstring::~wstring(&v126);
    v72 = (volatile signed __int32 *)a2[1];
    if ( v72 )
    {
      if ( _InterlockedExchangeAdd(v72 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v72)(v72);
        if ( _InterlockedExchangeAdd(v72 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v72 + 8LL))(v72);
      }
    }
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x187,
      (unsigned int)"avcore\\midi2\\transport\\loopbackmiditransport\\midi2.loopbackmidiendpointmanager.cpp",
      (const char *)(unsigned int)v59,
      (int)v99);
    WindowsMidiServicesNamingLib::MidiEndpointNameTable::~MidiEndpointNameTable((WindowsMidiServicesNamingLib::MidiEndpointNameTable *)v92);
    std::vector<enum std::byte>::~vector<enum std::byte>(&v90);
    std::wstring::~wstring(v121);
    std::wstring::~wstring(v125);
    std::vector<WindowsMidiServicesInternal::GroupTerminalBlockInternal>::~vector<WindowsMidiServicesInternal::GroupTerminalBlockInternal>(&v85);
    if ( pv )
      CoTaskMemFree(pv);
    std::wstring::~wstring(v128);
    std::wstring::~wstring(v114);
    std::vector<_DEVPROPERTY>::~vector<_DEVPROPERTY>(&v83);
    std::wstring::~wstring(v130);
    std::wstring::~wstring(v132);
    std::wstring::~wstring(&v126);
    v61 = (volatile signed __int32 *)a2[1];
    if ( v61 )
    {
      if ( _InterlockedExchangeAdd(v61 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v61)(v61);
        if ( _InterlockedExchangeAdd(v61 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v61 + 8LL))(v61);
      }
    }
    return v60;
  }
}

```

## disassembly

```asm
0x18001d454  mov     [rsp-8+arg_10], rbx
0x18001d459  push    rbp
0x18001d45a  push    rsi
0x18001d45b  push    rdi
0x18001d45c  push    r12
0x18001d45e  push    r13
0x18001d460  push    r14
0x18001d462  push    r15
0x18001d464  lea     rbp, [rsp-2B0h]
0x18001d46c  sub     rsp, 3B0h
0x18001d473  mov     rax, cs:__security_cookie
0x18001d47a  xor     rax, rsp
0x18001d47d  mov     [rbp+2E0h+var_40], rax
0x18001d484  mov     rdi, rdx
0x18001d487  mov     rsi, rcx
0x18001d48a  mov     [rbp+2E0h+var_2A0], rdx
0x18001d48e  xor     r13d, r13d
0x18001d491  cmp     [rcx+10h], r13b
0x18001d495  jnz     short loc_18001D4FF
0x18001d497  mov     esi, 8000FFFFh
0x18001d49c  mov     edx, 0E2h; void *
0x18001d4a1  lea     r8, aAvcoreMidi2Tra; "avcore\\midi2\\transport\\loopbackmidit"...
0x18001d4a8  mov     r9d, esi; char *
0x18001d4ab  mov     rcx, [rbp+2E8h]; this
0x18001d4b2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001d4b7  nop
0x18001d4b8  mov     rbx, [rdi+8]
0x18001d4bc  test    rbx, rbx
0x18001d4bf  jz      short loc_18001D4F8
0x18001d4c1  or      eax, 0FFFFFFFFh
0x18001d4c4  lock xadd [rbx+8], eax
0x18001d4c9  cmp     eax, 1
0x18001d4cc  jnz     short loc_18001D4F8
0x18001d4ce  mov     rax, [rbx]
0x18001d4d1  mov     rcx, rbx
0x18001d4d4  mov     rax, [rax]
0x18001d4d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d4dc  or      edx, 0FFFFFFFFh
0x18001d4df  lock xadd [rbx+0Ch], edx
0x18001d4e4  cmp     edx, 1
0x18001d4e7  jnz     short loc_18001D4F8
0x18001d4e9  mov     rdx, [rbx]
0x18001d4ec  mov     rcx, rbx
0x18001d4ef  mov     rax, [rdx+8]
0x18001d4f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d4f8  mov     eax, esi
0x18001d4fa  jmp     loc_18001E412
0x18001d4ff  cmp     [rcx+58h], r13
0x18001d503  jnz     short loc_18001D511
0x18001d505  mov     esi, 80004003h
0x18001d50a  mov     edx, 0E3h
0x18001d50f  jmp     short loc_18001D4A1
0x18001d511  mov     rax, [rdx]
0x18001d514  test    rax, rax
0x18001d517  jnz     short loc_18001D581
0x18001d519  mov     rcx, [rbp+2E8h]; this
0x18001d520  mov     r9d, 80070057h; char *
0x18001d526  lea     r8, aAvcoreMidi2Tra; "avcore\\midi2\\transport\\loopbackmidit"...
0x18001d52d  mov     edx, 0E5h; void *
0x18001d532  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001d537  nop
0x18001d538  mov     rbx, [rdi+8]
0x18001d53c  test    rbx, rbx
0x18001d53f  jz      loc_18001D63B
0x18001d545  or      eax, 0FFFFFFFFh
0x18001d548  lock xadd [rbx+8], eax
0x18001d54d  cmp     eax, 1
0x18001d550  jnz     loc_18001D63B
0x18001d556  mov     rax, [rbx]
0x18001d559  mov     rcx, rbx
0x18001d55c  mov     rax, [rax]
0x18001d55f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d564  or      eax, 0FFFFFFFFh
0x18001d567  lock xadd [rbx+0Ch], eax
0x18001d56c  cmp     eax, 1
0x18001d56f  jnz     loc_18001D63B
0x18001d575  mov     rax, [rbx]
0x18001d578  mov     rax, [rax+8]
0x18001d57c  jmp     loc_18001D633
0x18001d581  cmp     [rax+30h], r13
0x18001d585  jnz     short loc_18001D5B3
0x18001d587  lea     rax, aEmptyEndpointN; "Empty endpoint name"
0x18001d58e  mov     edx, 0E7h; void *
0x18001d593  lea     r8, aAvcoreMidi2Tra; "avcore\\midi2\\transport\\loopbackmidit"...
0x18001d59a  mov     r9d, 80070057h; char *
0x18001d5a0  mov     qword ptr [rsp+3E0h+var_3C0], rax; int
0x18001d5a5  mov     rcx, [rbp+2E8h]; this
0x18001d5ac  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18001d5b1  jmp     short loc_18001D538
0x18001d5b3  cmp     [rax+90h], r13
0x18001d5ba  jnz     short loc_18001D5CA
0x18001d5bc  lea     rax, aEmptyEndpointP; "Empty endpoint prefix"
0x18001d5c3  mov     edx, 0E8h
0x18001d5c8  jmp     short loc_18001D593
0x18001d5ca  cmp     [rax+70h], r13
0x18001d5ce  jnz     short loc_18001D645
0x18001d5d0  mov     rcx, [rbp+2E8h]; this
0x18001d5d7  lea     rax, aEmptyEndpointU; "Empty endpoint unique id"
0x18001d5de  mov     qword ptr [rsp+3E0h+var_3C0], rax; int
0x18001d5e3  mov     r9d, 80070057h; char *
0x18001d5e9  lea     r8, aAvcoreMidi2Tra; "avcore\\midi2\\transport\\loopbackmidit"...
0x18001d5f0  mov     edx, 0E9h; void *
0x18001d5f5  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18001d5fa  nop
0x18001d5fb  mov     rbx, [rdi+8]
0x18001d5ff  test    rbx, rbx
0x18001d602  jz      short loc_18001D63B
0x18001d604  or      eax, 0FFFFFFFFh
0x18001d607  lock xadd [rbx+8], eax
0x18001d60c  cmp     eax, 1
0x18001d60f  jnz     short loc_18001D63B
0x18001d611  mov     rax, [rbx]
0x18001d614  mov     rcx, rbx
0x18001d617  mov     rax, [rax]
0x18001d61a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d61f  or      edx, 0FFFFFFFFh
0x18001d622  lock xadd [rbx+0Ch], edx
0x18001d627  cmp     edx, 1
0x18001d62a  jnz     short loc_18001D63B
0x18001d62c  mov     rdx, [rbx]
0x18001d62f  mov     rax, [rdx+8]
0x18001d633  mov     rcx, rbx
0x18001d636  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d63b  mov     eax, 80070057h
0x18001d640  jmp     loc_18001E412
0x18001d645  call    ?Instance@MidiLoopbackMidiTransportTelemetryProvider@@KAPEAV1@XZ; MidiLoopbackMidiTransportTelemetryProvider::Instance(void)
0x18001d64a  mov     r8, [rax+8]
0x18001d64e  mov     eax, [r8]
0x18001d651  mov     r14d, 7
0x18001d657  lea     r12, aCmidi2loopback_2; "CMidi2LoopbackMidiEndpointManager::Crea"...
0x18001d65e  lea     r15d, [r14-3]
0x18001d662  cmp     eax, r15d
0x18001d665  jbe     loc_18001D72E
0x18001d66b  mov     rax, [rdi]
0x18001d66e  lea     rcx, [rax+40h]
0x18001d672  cmp     [rcx+18h], r14
0x18001d676  jbe     short loc_18001D67B
0x18001d678  mov     rcx, [rcx]
0x18001d67b  mov     [rbp+2E0h+var_308], rcx
0x18001d67f  lea     rcx, [rax+20h]
0x18001d683  cmp     [rcx+18h], r14
0x18001d687  jbe     short loc_18001D68C
0x18001d689  mov     rcx, [rcx]
0x18001d68c  mov     [rbp+2E0h+var_300], rcx
0x18001d690  lea     rcx, [rax+60h]
0x18001d694  cmp     [rcx+18h], r14
0x18001d698  jbe     short loc_18001D69D
0x18001d69a  mov     rcx, [rcx]
0x18001d69d  mov     [rbp+2E0h+var_2F8], rcx
0x18001d6a1  lea     rcx, [rax+80h]
0x18001d6a8  cmp     [rcx+18h], r14
0x18001d6ac  jbe     short loc_18001D6B1
0x18001d6ae  mov     rcx, [rcx]
0x18001d6b1  mov     qword ptr [rbp+2E0h+var_340], rcx
0x18001d6b5  cmp     [rax+18h], r14
0x18001d6b9  jbe     short loc_18001D6BE
0x18001d6bb  mov     rax, [rax]
0x18001d6be  mov     [rsp+3E0h+var_368], rax
0x18001d6c3  lea     rax, aEnter; "Enter"
0x18001d6ca  mov     [rbp+2E0h+var_360], rax
0x18001d6ce  mov     [rbp+2E0h+var_358], rsi
0x18001d6d2  mov     [rbp+2E0h+var_350], r12
0x18001d6d6  lea     rax, [rbp+2E0h+var_308]
0x18001d6da  mov     [rsp+3E0h+var_388], rax
0x18001d6df  lea     rax, [rbp+2E0h+var_300]
0x18001d6e3  mov     [rsp+3E0h+var_390], rax
0x18001d6e8  lea     rax, [rbp+2E0h+var_2F8]
0x18001d6ec  mov     [rsp+3E0h+var_398], rax
0x18001d6f1  lea     rax, [rbp+2E0h+var_340]
0x18001d6f5  mov     [rsp+3E0h+var_3A0], rax
0x18001d6fa  lea     rax, [rsp+3E0h+var_368]
0x18001d6ff  mov     [rsp+3E0h+var_3A8], rax
0x18001d704  lea     rax, [rbp+2E0h+var_360]
0x18001d708  mov     [rsp+3E0h+var_3B0], rax
0x18001d70d  lea     rax, [rbp+2E0h+var_358]
0x18001d711  mov     [rsp+3E0h+var_3B8], rax
0x18001d716  lea     rax, [rbp+2E0h+var_350]
0x18001d71a  mov     qword ptr [rsp+3E0h+var_3C0], rax
0x18001d71f  lea     rdx, byte_180058661
0x18001d726  mov     rcx, r8
0x18001d729  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U3@U3@U3@U3@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@55555@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x18001d72e  xorps   xmm0, xmm0
0x18001d731  movups  [rbp+2E0h+var_100], xmm0
0x18001d738  xorps   xmm1, xmm1
0x18001d73b  movdqu  [rbp+2E0h+var_F0], xmm1
0x18001d743  mov     r8, r15
0x18001d746  lea     rdx, aLoop; "LOOP"
0x18001d74d  lea     rcx, [rbp+2E0h+var_100]
0x18001d754  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18001d759  nop
0x18001d75a  mov     rdx, [rdi]
0x18001d75d  add     rdx, 20h ; ' '
0x18001d761  lea     rcx, [rbp+2E0h+var_A0]
0x18001d768  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18001d76d  nop
0x18001d76e  mov     rdx, [rdi]
0x18001d771  add     rdx, 40h ; '@'
0x18001d775  lea     rcx, [rbp+2E0h+var_C0]
0x18001d77c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18001d781  nop
0x18001d782  xorps   xmm0, xmm0
0x18001d785  movdqu  [rbp+2E0h+var_338], xmm0
0x18001d78a  mov     [rbp+2E0h+var_328], r13
0x18001d78e  movups  [rbp+2E0h+var_180], xmm0
0x18001d795  xorps   xmm1, xmm1
0x18001d798  movdqu  [rbp+2E0h+var_170], xmm1
0x18001d7a0  xor     r8d, r8d
0x18001d7a3  lea     rdx, S2
0x18001d7aa  lea     rcx, [rbp+2E0h+var_180]
0x18001d7b1  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18001d7b6  nop
0x18001d7b7  xorps   xmm0, xmm0
0x18001d7ba  movups  [rbp+2E0h+var_80], xmm0
0x18001d7c1  xorps   xmm1, xmm1
0x18001d7c4  movdqu  [rbp+2E0h+var_70], xmm1
0x18001d7cc  xor     r8d, r8d
0x18001d7cf  lea     rdx, S2
0x18001d7d6  lea     rcx, [rbp+2E0h+var_80]
0x18001d7dd  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18001d7e2  nop
0x18001d7e3  lea     rdx, [rbp+2E0h+var_80]
0x18001d7ea  lea     rcx, [rbp+2E0h+var_60]
0x18001d7f1  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18001d7f6  mov     rdx, rax; void *
0x18001d7f9  lea     rcx, [rbp+2E0h+Src]; Src
0x18001d800  call    ?TrimmedWStringCopy@WindowsMidiServicesInternal@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V23@@Z; WindowsMidiServicesInternal::TrimmedWStringCopy(std::wstring)
0x18001d805  mov     rbx, [rax+10h]
0x18001d809  lea     rcx, [rbp+2E0h+Src]; void *
0x18001d810  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001d815  lea     rcx, [rbp+2E0h+Src]
0x18001d81c  test    rbx, rbx
0x18001d81f  jz      short loc_18001D82A
0x18001d821  lea     rdx, [rbp+2E0h+var_80]
0x18001d828  jmp     short loc_18001D86F
0x18001d82a  lea     rdx, [rbp+2E0h+var_180]
0x18001d831  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18001d836  mov     rdx, rax; void *
0x18001d839  lea     rcx, [rbp+2E0h+var_60]; Src
0x18001d840  call    ?TrimmedWStringCopy@WindowsMidiServicesInternal@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V23@@Z; WindowsMidiServicesInternal::TrimmedWStringCopy(std::wstring)
0x18001d845  mov     rbx, [rax+10h]
0x18001d849  lea     rcx, [rbp+2E0h+var_60]; void *
0x18001d850  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001d855  lea     rcx, [rbp+2E0h+Src]
0x18001d85c  test    rbx, rbx
0x18001d85f  lea     rdx, [rbp+2E0h+var_180]
0x18001d866  jnz     short loc_18001D86F
0x18001d868  lea     rdx, [rbp+2E0h+var_A0]
0x18001d86f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18001d874  mov     rdx, rax; void *
0x18001d877  lea     rcx, [rbp+2E0h+var_1A0]; Src
0x18001d87e  call    ?TrimmedWStringCopy@WindowsMidiServicesInternal@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V23@@Z; WindowsMidiServicesInternal::TrimmedWStringCopy(std::wstring)
0x18001d883  nop
0x18001d884  lea     rcx, [rbp+2E0h+var_80]; void *
0x18001d88b  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001d890  nop
0x18001d891  lea     rcx, [rbp+2E0h+var_180]; void *
0x18001d898  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001d89d  call    ?Instance@MidiLoopbackMidiTransportTelemetryProvider@@KAPEAV1@XZ; MidiLoopbackMidiTransportTelemetryProvider::Instance(void)
0x18001d8a2  mov     r8, [rax+8]
0x18001d8a6  mov     eax, [r8]
0x18001d8a9  cmp     eax, r15d
0x18001d8ac  jbe     loc_18001D9B2
0x18001d8b2  lea     rax, [rbp+2E0h+var_C0]
0x18001d8b9  cmp     [rbp+2E0h+var_A8], r14
0x18001d8c0  cmova   rax, [rbp+2E0h+var_C0]
0x18001d8c8  mov     [rbp+2E0h+var_350], rax
0x18001d8cc  lea     rax, [rbp+2E0h+var_A0]
0x18001d8d3  cmp     [rbp+2E0h+var_88], r14
0x18001d8da  cmova   rax, [rbp+2E0h+var_A0]
0x18001d8e2  mov     [rbp+2E0h+var_358], rax
0x18001d8e6  lea     rax, [rbp+2E0h+var_100]
0x18001d8ed  cmp     qword ptr [rbp+2E0h+var_F0+8], r14
0x18001d8f4  cmova   rax, qword ptr [rbp+2E0h+var_100]
0x18001d8fc  mov     [rbp+2E0h+var_360], rax
0x18001d900  lea     rax, [rbp+2E0h+var_1A0]
0x18001d907  cmp     [rbp+2E0h+var_188], r14
0x18001d90e  cmova   rax, [rbp+2E0h+var_1A0]
0x18001d916  mov     [rsp+3E0h+var_368], rax
0x18001d91b  mov     rax, [rdi]
0x18001d91e  lea     rcx, [rax+60h]
0x18001d922  cmp     [rcx+18h], r14
0x18001d926  jbe     short loc_18001D92B
0x18001d928  mov     rcx, [rcx]
0x18001d92b  mov     qword ptr [rbp+2E0h+var_340], rcx
0x18001d92f  cmp     [rax+18h], r14
0x18001d933  jbe     short loc_18001D938
0x18001d935  mov     rax, [rax]
0x18001d938  mov     [rbp+2E0h+var_2F8], rax
0x18001d93c  lea     rax, aAddingEndpoint; "Adding endpoint properties"
0x18001d943  mov     [rbp+2E0h+var_300], rax
0x18001d947  mov     [rbp+2E0h+var_308], rsi
0x18001d94b  mov     [rsp+3E0h+var_370], r12
0x18001d950  lea     rax, [rbp+2E0h+var_350]
0x18001d954  mov     [rsp+3E0h+var_380], rax
0x18001d959  lea     rax, [rbp+2E0h+var_358]
0x18001d95d  mov     [rsp+3E0h+var_388], rax
0x18001d962  lea     rax, [rbp+2E0h+var_360]
0x18001d966  mov     [rsp+3E0h+var_390], rax
0x18001d96b  lea     rax, [rsp+3E0h+var_368]
0x18001d970  mov     [rsp+3E0h+var_398], rax
  ... truncated ...
```
