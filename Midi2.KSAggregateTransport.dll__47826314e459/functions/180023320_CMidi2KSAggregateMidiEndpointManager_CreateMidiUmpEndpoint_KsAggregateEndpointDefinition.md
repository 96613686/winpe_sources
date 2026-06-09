# CMidi2KSAggregateMidiEndpointManager::CreateMidiUmpEndpoint(KsAggregateEndpointDefinition &)

- ea: `0x180023320`
- end: `0x180024bf3`
- name: `?CreateMidiUmpEndpoint@CMidi2KSAggregateMidiEndpointManager@@EEAAJAEAUKsAggregateEndpointDefinition@@@Z`
- size: `6355`
- prototype: `int(CMidi2KSAggregateMidiEndpointManager *__hidden this, struct KsAggregateEndpointDefinition *)`
- caller_count: `0`
- callee_count: `52`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x18000163c`
- `0x1800017d0`
- `0x180001a94`
- `0x180002390`
- `0x1800024e0`
- `0x180002640`
- `0x180005020`
- `0x180005070`
- `0x180005e90`
- `0x180005e9c`
- `0x18000b394`
- `0x18000d430`
- `0x18000d778`
- `0x18000d920`
- `0x18000e37c`
- `0x1800105d8`
- `0x1800117d8`
- `0x180013118`
- `0x180013498`
- `0x180013638`
- `0x180014194`
- `0x1800196f4`
- `0x180019924`
- `0x180019954`
- `0x18001a844`
- `0x18001aa6c`
- `0x18001b160`
- `0x18001b258`
- `0x18001ca4c`
- `0x18001fa30`
- `0x180020104`
- `0x180020604`
- `0x180020b58`
- `0x180020d3c`
- `0x180021e68`
- `0x18002230c`
- `0x1800224f8`
- `0x180022648`
- `0x1800229bc`
- `0x180022df4`
- `0x180022f64`
- `0x180023320`
- `0x180029298`
- `0x180029460`
- `0x18004c470`
- `0x18004d024`
- `0x1800561e4`
- `0x180056268`
- `0x180056eb8`
- `0x180056fc4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180023d3c`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180023d3c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800249e4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800249e4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180024b26`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180024b26`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800247ac`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800247ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024799`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024799`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800247a4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180024b35`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800247a4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180024b35`

## string_xrefs

- `0x18002336e`: `CMidi2KSAggregateMidiEndpointManager::CreateMidiUmpEndpoint`
- `0x180023a2c`: `CMidi2KSAggregateMidiEndpointManager::CreateMidiUmpEndpoint`
- `0x180023cba`: `CMidi2KSAggregateMidiEndpointManager::CreateMidiUmpEndpoint`
- `0x180023d97`: `CMidi2KSAggregateMidiEndpointManager::CreateMidiUmpEndpoint`
- `0x18002424d`: `CMidi2KSAggregateMidiEndpointManager::CreateMidiUmpEndpoint`
- `0x1800242d1`: `CMidi2KSAggregateMidiEndpointManager::CreateMidiUmpEndpoint`
- `0x180024482`: `CMidi2KSAggregateMidiEndpointManager::CreateMidiUmpEndpoint`
- `0x1800245a9`: `CMidi2KSAggregateMidiEndpointManager::CreateMidiUmpEndpoint`
- `0x180024741`: `CMidi2KSAggregateMidiEndpointManager::CreateMidiUmpEndpoint`
- `0x180024894`: `CMidi2KSAggregateMidiEndpointManager::CreateMidiUmpEndpoint`
- `0x18002491f`: `CMidi2KSAggregateMidiEndpointManager::CreateMidiUmpEndpoint`
- `0x1800242bc`: `Found custom properties cached for this endpoint`
- `0x180024238`: `No cached custom properties for this endpoint.`
- `0x18002490e`: `Aggregate UMP endpoint created`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CMidi2KSAggregateMidiEndpointManager::CreateMidiUmpEndpoint(
        CMidi2KSAggregateMidiEndpointManager *this,
        struct KsAggregateEndpointDefinition *a2)
{
  CMidi2KSAggregateMidiEndpointManager *v3; // rbx
  _DWORD *v4; // rcx
  int v5; // r8d
  int v6; // r9d
  const wchar_t **v7; // rsi
  const char *v8; // rax
  __int64 v9; // r15
  __int64 v10; // r12
  __int64 v11; // r13
  unsigned int v12; // edi
  bool v14; // cc
  const wchar_t *v15; // rax
  const wchar_t *v16; // rax
  _QWORD *v17; // rax
  _QWORD *v18; // rax
  char v19; // cl
  __m128i si128; // xmm6
  int v21; // eax
  __int64 v22; // r8
  __int64 v23; // rax
  volatile signed __int32 *v24; // rbx
  __int64 v25; // r8
  __int64 v26; // rax
  __int64 v27; // rax
  wchar_t *v28; // xmm0_8
  __m128i v29; // xmm1
  wchar_t **v30; // r9
  __int64 v31; // rcx
  __int64 v32; // rdi
  __int128 *p_Src; // rbx
  __int64 v34; // rdx
  __int64 v35; // rdx
  _DWORD *v36; // rcx
  int v37; // r8d
  int v38; // r9d
  const wchar_t *v39; // rax
  __int64 v40; // r8
  __int64 i; // rdx
  size_t v42; // rdi
  size_t v43; // rcx
  _DWORD *v44; // rbx
  char *v45; // r13
  unsigned int *v46; // r12
  __int64 v47; // rbx
  __int64 v48; // r13
  unsigned int *v49; // r10
  unsigned int v50; // eax
  const wchar_t **v51; // rdi
  const char *v52; // rcx
  const wchar_t *v53; // rcx
  const wchar_t *v54; // rdx
  __int64 v55; // rax
  int v56; // eax
  __int64 v57; // rax
  int v58; // eax
  __int64 v59; // rdx
  _DWORD *v60; // rcx
  int v61; // r8d
  int v62; // r9d
  const wchar_t *v63; // rax
  __int64 v64; // rdx
  _OWORD *v65; // rdx
  _OWORD *v66; // rdx
  __int64 v67; // rdx
  char **v68; // r12
  __int64 v69; // rax
  wchar_t **v70; // rax
  char *v71; // rcx
  const wchar_t *v72; // rax
  struct TransportState *v73; // rax
  _QWORD *v74; // rdi
  __int64 v75; // rax
  volatile signed __int32 *v76; // rbx
  __int64 v77; // rdi
  unsigned int *v78; // rcx
  int v79; // r8d
  int v80; // r9d
  unsigned int v81; // eax
  char *v82; // rax
  char *v83; // rax
  __int128 *v84; // rax
  __int128 *v85; // rax
  __int64 v86; // rbx
  __int64 v87; // r13
  const char *v88; // r15
  __int64 v89; // rcx
  _BYTE *v90; // rax
  _BYTE *k; // rsi
  _DWORD *v92; // rcx
  int v93; // r8d
  int v94; // r9d
  const struct winrt::hstring *v95; // rsi
  const wchar_t *v96; // rax
  char *v97; // rax
  __int64 v98; // rcx
  _BYTE *v99; // rax
  _BYTE *j; // rsi
  _DWORD *v101; // rcx
  int v102; // r8d
  int v103; // r9d
  const struct winrt::hstring *v104; // rsi
  const wchar_t *v105; // rax
  char *v106; // rax
  __int64 v107; // rdx
  _QWORD *v108; // rax
  _QWORD *v109; // rax
  _DWORD *v110; // rcx
  int v111; // r8d
  int v112; // r9d
  _QWORD *v113; // rax
  const char *v114; // r13
  __int64 v115; // rsi
  __int64 (__fastcall *v116)(__int64, char *, _QWORD, __int64); // r12
  void *v117; // rdi
  DWORD LastError; // ebx
  char *v119; // rdx
  int v120; // eax
  unsigned int v121; // r12d
  _DWORD *v122; // r8
  int v123; // r9d
  _QWORD *v124; // r14
  _DWORD *v125; // rcx
  int v126; // r8d
  int v127; // r9d
  _QWORD *v128; // rax
  __int64 v129; // rax
  struct _RTL_CRITICAL_SECTION *v130; // r15
  __int64 *v131; // rsi
  __int64 v132; // rax
  __int64 v133; // r13
  const wchar_t *v134; // rdx
  unsigned __int64 v135; // rbx
  unsigned __int64 v136; // rdi
  const wchar_t *v137; // rcx
  size_t v138; // r8
  int v139; // eax
  __int64 v140; // rbx
  _OWORD *v141; // rdi
  int v142; // [rsp+28h] [rbp-E0h]
  __int64 v143; // [rsp+68h] [rbp-A0h] BYREF
  int v144[2]; // [rsp+70h] [rbp-98h] BYREF
  const char *v145; // [rsp+78h] [rbp-90h] BYREF
  const char *v146; // [rsp+80h] [rbp-88h] BYREF
  char v147; // [rsp+88h] [rbp-80h] BYREF
  __int128 v148; // [rsp+90h] [rbp-78h] BYREF
  _OWORD *v149; // [rsp+A0h] [rbp-68h]
  const char *v150; // [rsp+A8h] [rbp-60h] BYREF
  const char *v151; // [rsp+B0h] [rbp-58h] BYREF
  __int16 v152; // [rsp+B8h] [rbp-50h]
  LPVOID pv; // [rsp+C0h] [rbp-48h]
  __int128 v154; // [rsp+C8h] [rbp-40h] BYREF
  __int64 v155; // [rsp+D8h] [rbp-30h]
  _OWORD v156[2]; // [rsp+E8h] [rbp-20h] BYREF
  __int128 v157; // [rsp+108h] [rbp+0h] BYREF
  __int64 v158; // [rsp+118h] [rbp+10h]
  __int128 v159; // [rsp+120h] [rbp+18h] BYREF
  __int64 v160; // [rsp+130h] [rbp+28h]
  __int128 v161; // [rsp+138h] [rbp+30h] BYREF
  __int64 v162; // [rsp+148h] [rbp+40h]
  __int64 v163; // [rsp+150h] [rbp+48h] BYREF
  __int128 v164; // [rsp+158h] [rbp+50h]
  __int64 v165; // [rsp+168h] [rbp+60h]
  __int16 v166; // [rsp+170h] [rbp+68h]
  int v167; // [rsp+172h] [rbp+6Ah]
  __int16 v168; // [rsp+176h] [rbp+6Eh]
  __int128 v169; // [rsp+178h] [rbp+70h] BYREF
  __int128 v170; // [rsp+188h] [rbp+80h] BYREF
  __int64 v171; // [rsp+198h] [rbp+90h]
  _QWORD v172[5]; // [rsp+1A0h] [rbp+98h] BYREF
  int v173; // [rsp+1C8h] [rbp+C0h] BYREF
  _QWORD *v174; // [rsp+1D0h] [rbp+C8h]
  int v175; // [rsp+1F0h] [rbp+E8h]
  _QWORD *v176; // [rsp+1F8h] [rbp+F0h]
  char v177; // [rsp+218h] [rbp+110h] BYREF
  int v178; // [rsp+219h] [rbp+111h]
  int v179; // [rsp+21Eh] [rbp+116h]
  __int128 Src; // [rsp+228h] [rbp+120h] BYREF
  __int64 v181; // [rsp+238h] [rbp+130h]
  unsigned __int64 v182; // [rsp+240h] [rbp+138h]
  int v183[4]; // [rsp+248h] [rbp+140h] BYREF
  __int64 v184; // [rsp+258h] [rbp+150h]
  const wchar_t *v185; // [rsp+260h] [rbp+158h]
  const unsigned __int16 *v186; // [rsp+268h] [rbp+160h]
  const wchar_t *v187; // [rsp+270h] [rbp+168h]
  __int128 v188; // [rsp+278h] [rbp+170h]
  __int128 *v189; // [rsp+288h] [rbp+180h]
  _QWORD *v190; // [rsp+290h] [rbp+188h]
  _QWORD *v191; // [rsp+298h] [rbp+190h]
  int v192; // [rsp+2A0h] [rbp+198h]
  int v193; // [rsp+2A4h] [rbp+19Ch]
  int v194; // [rsp+2A8h] [rbp+1A0h]
  int v195; // [rsp+2ACh] [rbp+1A4h]
  wchar_t *S1[2]; // [rsp+2B8h] [rbp+1B0h] BYREF
  __int128 v197; // [rsp+2C8h] [rbp+1C0h]
  __int128 v198; // [rsp+2D8h] [rbp+1D0h]
  __int128 v199; // [rsp+2E8h] [rbp+1E0h] BYREF
  __int128 v200; // [rsp+2F8h] [rbp+1F0h] BYREF
  __m128i v201; // [rsp+308h] [rbp+200h]
  __int128 v202; // [rsp+318h] [rbp+210h] BYREF
  __int128 v203; // [rsp+328h] [rbp+220h]
  __int128 v204; // [rsp+338h] [rbp+230h] BYREF
  __m128i v205; // [rsp+348h] [rbp+240h]
  __int128 v206; // [rsp+358h] [rbp+250h] BYREF
  __m128i v207; // [rsp+368h] [rbp+260h]
  _QWORD v208[4]; // [rsp+378h] [rbp+270h] BYREF
  char v209[32]; // [rsp+398h] [rbp+290h] BYREF
  const char *v210; // [rsp+3B8h] [rbp+2B0h]
  __int64 v211; // [rsp+3C0h] [rbp+2B8h]
  int *v212; // [rsp+3C8h] [rbp+2C0h]
  __int64 v213; // [rsp+3D0h] [rbp+2C8h]
  const wchar_t *v214; // [rsp+3D8h] [rbp+2D0h]
  __int64 v215; // [rsp+3E0h] [rbp+2D8h]
  const wchar_t *v216; // [rsp+3E8h] [rbp+2E0h]
  int v217; // [rsp+3F0h] [rbp+2E8h]
  int v218; // [rsp+3F4h] [rbp+2ECh]
  const char **v219; // [rsp+3F8h] [rbp+2F0h]
  __int64 v220; // [rsp+400h] [rbp+2F8h]
  const wchar_t *v221; // [rsp+408h] [rbp+300h]
  int v222; // [rsp+410h] [rbp+308h]
  int v223; // [rsp+414h] [rbp+30Ch]
  wil::details::in1diag3 *retaddr; // [rsp+470h] [rbp+368h]

  v3 = this;
  v150 = (const char *)this;
  v4 = (_DWORD *)*((_QWORD *)MidiKSAggregateTransportTelemetryProvider::Instance() + 1);
  v7 = (const wchar_t **)((char *)a2 + 104);
  if ( *v4 > 4u )
  {
    if ( *((_QWORD *)a2 + 16) <= 7u )
      v8 = (char *)a2 + 104;
    else
      v8 = (const char *)*v7;
    v146 = v8;
    v151 = (const char *)L"Enter";
    v145 = (const char *)v3;
    *(_QWORD *)v144 = "CMidi2KSAggregateMidiEndpointManager::CreateMidiUmpEndpoint";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
      (_DWORD)v4,
      (unsigned int)byte_1800896D3,
      v5,
      v6,
      (__int64)v144,
      (__int64)&v145,
      (__int64)&v151,
      (__int64)&v146);
  }
  v9 = -1;
  v147 = -1;
  v10 = *((_QWORD *)a2 + 30);
  v11 = *((_QWORD *)a2 + 29);
  if ( !(0xEEEEEEEEEEEEEEEFuLL * ((v10 - v11) >> 3)) )
  {
    v12 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x6F,
      (unsigned int)"avcore\\midi2\\transport\\ksaggregatetransport\\midi2.ksaggregatemidiendpointmanager.cpp",
      (const char *)0x80070057LL,
      v142);
    return v12;
  }
  v148 = 0;
  v149 = 0;
  v184 = 0;
  v195 = 0;
  *(GUID *)v183 = GUID_0f273b18_e372_4d95_87ac_c31c3d22e937;
  v14 = *((_QWORD *)a2 + 16) <= 7u;
  if ( *((_QWORD *)a2 + 16) <= 7u )
    v15 = (const wchar_t *)((char *)a2 + 104);
  else
    v15 = *v7;
  v185 = v15;
  v186 = L"KSA";
  if ( v14 )
    v16 = (const wchar_t *)((char *)a2 + 104);
  else
    v16 = *v7;
  v187 = v16;
  v188 = 0;
  v189 = 0;
  if ( *((_QWORD *)a2 + 7) )
  {
    v17 = (_QWORD *)((char *)a2 + 40);
    if ( *((_QWORD *)a2 + 8) > 7u )
      v17 = (_QWORD *)*v17;
    v190 = v17;
  }
  else
  {
    v190 = 0;
  }
  if ( *((_QWORD *)a2 + 11) )
  {
    v18 = (_QWORD *)((char *)a2 + 72);
    if ( *((_QWORD *)a2 + 12) > 7u )
      v18 = (_QWORD *)*v18;
    v191 = v18;
  }
  else
  {
    v191 = 0;
  }
  v192 = 2;
  v193 = 1;
  v194 = 13;
  v19 = 0;
  v159 = 0;
  v160 = 0;
  v157 = 0;
  v158 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  if ( v11 != v10 )
  {
    while ( 1 )
    {
      if ( !*(_QWORD *)(v11 + 16) )
      {
        v12 = -2147024809;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x8E,
          (unsigned int)"avcore\\midi2\\transport\\ksaggregatetransport\\midi2.ksaggregatemidiendpointmanager.cpp",
          (const char *)0x80070057LL,
          v142);
        goto LABEL_65;
      }
      v178 = 0x10000;
      v179 = 0;
      Src = 0;
      v181 = 0;
      v182 = 7;
      LOWORD(Src) = 0;
      LOBYTE(v143) = v19 + 1;
      v177 = v19 + 1;
      v199 = 0;
      v200 = 0;
      v201 = si128;
      LOWORD(v200) = 0;
      DWORD1(v199) = *(_DWORD *)(v11 + 64);
      std::wstring::operator=(&v200, v11);
      v21 = *(_DWORD *)(v11 + 104);
      DWORD2(v199) = v21;
      LOBYTE(v199) = *(_BYTE *)(v11 + 112);
      BYTE1(v178) = v199;
      if ( v21 )
      {
        if ( v21 != 1 )
        {
          v12 = -2147024809;
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xB5,
            (unsigned int)"avcore\\midi2\\transport\\ksaggregatetransport\\midi2.ksaggregatemidiendpointmanager.cpp",
            (const char *)0x80070057LL,
            v142);
          std::wstring::~wstring(&v200);
          std::wstring::~wstring(&Src);
          goto LABEL_65;
        }
        LOBYTE(v178) = 2;
        WindowsMidiServicesNamingLib::MidiEndpointNameTable::GetSourceEntry((char *)a2 + 256, &v154);
        if ( (_QWORD)v154 && *(_WORD *)(v154 + 136) )
        {
          *(_OWORD *)S1 = 0;
          v197 = 0;
          v25 = -1;
          do
            ++v25;
          while ( *(_WORD *)(v154 + 136 + 2 * v25) );
          std::wstring::_Construct<1,unsigned short const *>(S1);
          v26 = WindowsMidiServicesInternal::TrimmedWStringCopy(v208, S1);
          std::wstring::operator=(&Src, v26);
          std::wstring::~wstring(v208);
        }
        v24 = (volatile signed __int32 *)*((_QWORD *)&v154 + 1);
      }
      else
      {
        LOBYTE(v178) = 1;
        WindowsMidiServicesNamingLib::MidiEndpointNameTable::GetDestinationEntry((char *)a2 + 256, v156);
        if ( *(_QWORD *)&v156[0] && *(_WORD *)(*(_QWORD *)&v156[0] + 136LL) )
        {
          *(_OWORD *)S1 = 0;
          v197 = 0;
          v22 = -1;
          do
            ++v22;
          while ( *(_WORD *)(*(_QWORD *)&v156[0] + 136LL + 2 * v22) );
          std::wstring::_Construct<1,unsigned short const *>(S1);
          v23 = WindowsMidiServicesInternal::TrimmedWStringCopy(v208, S1);
          std::wstring::operator=(&Src, v23);
          std::wstring::~wstring(v208);
        }
        v24 = (volatile signed __int32 *)*((_QWORD *)&v156[0] + 1);
      }
      if ( v24 )
      {
        if ( !_InterlockedDecrement(v24 + 2) )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v24)(v24);
          if ( !_InterlockedDecrement(v24 + 3) )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v24 + 8LL))(v24);
        }
      }
      if ( !v181 )
      {
        std::wstring::operator=(&Src, (char *)a2 + 104);
        if ( BYTE1(v178) )
        {
          v152 = BYTE1(v178);
          v202 = 0;
          v203 = 0;
          std::wstring::_Construct<1,unsigned short const *>(&v202);
          v27 = std::wstring::_Insert<unsigned short>(&v202);
          *(_OWORD *)S1 = *(_OWORD *)v27;
          v28 = S1[0];
          v197 = *(_OWORD *)(v27 + 16);
          v29 = (__m128i)v197;
          *(_WORD *)v27 = 0;
          *(_QWORD *)(v27 + 16) = 0;
          *(_QWORD *)(v27 + 24) = 7;
          v30 = S1;
          if ( _mm_srli_si128(v29, 8).m128i_u64[0] > 7 )
            v30 = (wchar_t **)v28;
          v31 = v181;
          if ( v29.m128i_i64[0] > v182 - v181 )
          {
            ____Reallocate_grow_by_V_lambda_1___1_____Append_G___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV23_QEBG_K_Z_PEBG_K___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV01__KV_lambda_1___1_____Append_G_01_AEAAAEAV01_QEBG0_Z_PEBG_K_Z(
              &Src,
              v29.m128i_i64[0]);
          }
          else
          {
            v32 = v29.m128i_i64[0] + v181;
            v181 += v29.m128i_i64[0];
            p_Src = &Src;
            if ( v182 > 7 )
              p_Src = (__int128 *)Src;
            memmove_0((char *)p_Src + 2 * v31, v30, 2 * v29.m128i_i64[0]);
            *((_WORD *)p_Src + v32) = 0;
          }
          std::wstring::~wstring(S1);
          std::wstring::~wstring(&v202);
        }
      }
      HIBYTE(v178) = 1;
      v179 = 65537;
      v34 = *((_QWORD *)&v159 + 1);
      if ( *((_QWORD *)&v159 + 1) == v160 )
      {
        std::vector<WindowsMidiServicesInternal::GroupTerminalBlockInternal>::_Emplace_reallocate<WindowsMidiServicesInternal::GroupTerminalBlockInternal const &>(
          &v159,
          *((_QWORD *)&v159 + 1),
          &v177);
      }
      else
      {
        **((_BYTE **)&v159 + 1) = v177;
        *(_DWORD *)(v34 + 1) = v178;
        *(_DWORD *)(v34 + 6) = v179;
        std::wstring::wstring(v34 + 16, &Src);
        *((_QWORD *)&v159 + 1) += 48LL;
      }
      v35 = *((_QWORD *)&v157 + 1);
      if ( *((_QWORD *)&v157 + 1) == v158 )
      {
        std::vector<PinMapEntryStagingEntry>::_Emplace_reallocate<PinMapEntryStagingEntry const &>(
          &v157,
          *((_QWORD *)&v157 + 1),
          &v199);
      }
      else
      {
        **((_BYTE **)&v157 + 1) = v199;
        *(_QWORD *)(v35 + 4) = *(_QWORD *)((char *)&v199 + 4);
        std::wstring::wstring(v35 + 16, &v200);
        *((_QWORD *)&v157 + 1) += 48LL;
      }
      std::wstring::~wstring(&v200);
      std::wstring::~wstring(&Src);
      v11 += 120;
      if ( v11 == v10 )
        break;
      v19 = v143;
    }
    v3 = (CMidi2KSAggregateMidiEndpointManager *)v150;
  }
  v36 = (_DWORD *)*((_QWORD *)MidiKSAggregateTransportTelemetryProvider::Instance() + 1);
  if ( *v36 > 4u )
  {
    if ( *((_QWORD *)a2 + 16) <= 7u )
      v39 = (const wchar_t *)((char *)a2 + 104);
    else
      v39 = *v7;
    *(_QWORD *)v144 = v39;
    v145 = (const char *)L"Building pin map property";
    v146 = (const char *)v3;
    v151 = "CMidi2KSAggregateMidiEndpointManager::CreateMidiUmpEndpoint";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
      (_DWORD)v36,
      (unsigned int)byte_18008969B,
      v37,
      v38,
      (__int64)&v151,
      (__int64)&v146,
      (__int64)&v145,
      (__int64)v144);
  }
  v40 = 0;
  for ( i = v157; i != *((_QWORD *)&v157 + 1); i += 48 )
    v40 += 2LL * *(_QWORD *)(i + 32) + 2;
  v42 = v40
      + 2
      * (0xAAAAAAAAAAAAAAABuLL * ((__int64)(*((_QWORD *)&v157 + 1) - v157) >> 4)
       + 0x5555555555555558LL * ((__int64)(*((_QWORD *)&v157 + 1) - v157) >> 4)
       + 2);
  *(_QWORD *)&v154 = v42;
  v43 = 24;
  if ( v42 > 1 )
  {
    if ( v42 - 1 > 0xFFFFFFFFFFFFFFE0uLL )
      __scrt_throw_std_bad_array_new_length();
    v43 = (v42 - 1 + 31) & 0xFFFFFFFFFFFFFFF8uLL;
  }
  v44 = operator new(v43);
  v44[2] = 1;
  v44[3] = 1;
  *(_QWORD *)v44 = &std::_Ref_count_unbounded_array<unsigned char [0],1>::`vftable';
  v45 = (char *)(v44 + 4);
  v146 = (const char *)(v44 + 4);
  memset_0(v44 + 4, 0, v42);
  v208[0] = v44 + 4;
  v208[1] = v44;
  if ( v44 == (_DWORD *)-16LL )
  {
    v12 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xE9,
      (unsigned int)"avcore\\midi2\\transport\\ksaggregatetransport\\midi2.ksaggregatemidiendpointmanager.cpp",
      (const char *)0x8007000ELL,
      v142);
    if ( !_InterlockedDecrement((volatile signed __int32 *)0xFFFFFFFFFFFFFFF8LL) )
    {
      ((void (__fastcall *)(__int64))*MEMORY[0xFFFFFFFFFFFFFFF0])(-16);
      if ( !_InterlockedDecrement((volatile signed __int32 *)0xFFFFFFFFFFFFFFFCLL) )
        (*(void (__fastcall **)(__int64))(MEMORY[0xFFFFFFFFFFFFFFF0] + 8LL))(-16);
    }
LABEL_65:
    std::vector<PinMapEntryStagingEntry>::~vector<PinMapEntryStagingEntry>(&v157);
    std::vector<PinMapEntryStagingEntry>::~vector<PinMapEntryStagingEntry>(&v159);
    std::vector<_DEVPROPERTY>::~vector<_DEVPROPERTY>(&v148);
    return v12;
  }
  memset_0(v44 + 4, 0, v42);
  *(_DWORD *)v45 = v42;
  v46 = v44 + 5;
  v47 = v157;
  if ( (_QWORD)v157 != *((_QWORD *)&v157 + 1) )
  {
    v48 = *((_QWORD *)&v157 + 1);
    do
    {
      v49 = (unsigned int *)*((_QWORD *)MidiKSAggregateTransportTelemetryProvider::Instance() + 1);
      v50 = *v49;
      v51 = (const wchar_t **)(v47 + 16);
      v52 = (const char *)(v47 + 40);
      v145 = (const char *)(v47 + 40);
      if ( v50 > 4 )
      {
        if ( *(_QWORD *)v52 <= 7u )
          v53 = (const wchar_t *)(v47 + 16);
        else
          v53 = *v51;
        LODWORD(v151) = *(_DWORD *)(v47 + 4);
        if ( *((_QWORD *)a2 + 16) <= 7u )
          v54 = (const wchar_t *)((char *)a2 + 104);
        else
          v54 = *v7;
        *(_QWORD *)v144 = v150;
        if ( v53 )
        {
          v55 = -1;
          do
            ++v55;
          while ( v53[v55] );
          v56 = 2 * v55 + 2;
        }
        else
        {
          v53 = &::S1;
          v56 = 2;
        }
        v221 = v53;
        v222 = v56;
        v223 = 0;
        v219 = &v151;
        v220 = 4;
        if ( v54 )
        {
          v57 = -1;
          do
            ++v57;
          while ( v54[v57] );
          v58 = 2 * v57 + 2;
        }
        else
        {
          v54 = &::S1;
          v58 = 2;
        }
        v216 = v54;
        v217 = v58;
        v218 = 0;
        v214 = L"Processing Pin Map entry";
        v215 = 50;
        v212 = v144;
        v213 = 8;
        v210 = "CMidi2KSAggregateMidiEndpointManager::CreateMidiUmpEndpoint";
        v211 = 60;
        tlgWriteTransfer_EventWriteTransfer(v49, qword_180089650, 0, 0, 8, v209);
        v52 = v145;
      }
      *v46 = 2 * *(_DWORD *)(v47 + 32) + 20;
      *((_BYTE *)v46 + 4) = *(_BYTE *)v47;
      v46[3] = *(_DWORD *)(v47 + 8);
      v46[2] = *(_DWORD *)(v47 + 4);
      v59 = *(_QWORD *)(v47 + 32);
      if ( v59 )
      {
        if ( *(_QWORD *)v52 > 7u )
          v51 = (const wchar_t **)*v51;
        _o_wcscpy_s(v46 + 4, v59 + 1, v51);
      }
      v46 = (unsigned int *)((char *)v46 + *v46);
      v47 += 48;
    }
    while ( v47 != v48 );
    v45 = (char *)v146;
    LODWORD(v42) = v154;
  }
  v60 = (_DWORD *)*((_QWORD *)MidiKSAggregateTransportTelemetryProvider::Instance() + 1);
  if ( *v60 > 4u )
  {
    if ( *((_QWORD *)a2 + 16) <= 7u )
      v63 = (const wchar_t *)((char *)a2 + 104);
    else
      v63 = *v7;
    *(_QWORD *)&v154 = v63;
    *(_QWORD *)v144 = L"All pin map entries copied to property memory";
    v145 = v150;
    v146 = "CMidi2KSAggregateMidiEndpointManager::CreateMidiUmpEndpoint";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
      (_DWORD)v60,
      (unsigned int)qword_180089618,
      v61,
      v62,
      (__int64)&v146,
      (__int64)&v145,
      (__int64)v144,
      (__int64)&v154);
  }
  *(_OWORD *)S1 = DEVPKEY_KsAggMidiGroupPinMap;
  v197 = 0x10u;
  LODWORD(v198) = 4099;
  DWORD1(v198) = v42;
  *((_QWORD *)&v198 + 1) = v45;
  v64 = *((_QWORD *)&v148 + 1);
  if ( *((_OWORD **)&v148 + 1) == v149 )
  {
    std::vector<_DEVPROPERTY>::_Emplace_reallocate<_DEVPROPERTY>(&v148, *((_QWORD *)&v148 + 1), S1);
    v65 = (_OWORD *)*((_QWORD *)&v148 + 1);
  }
  else
  {
    **((_OWORD **)&v148 + 1) = DEVPKEY_KsAggMidiGroupPinMap;
    *(_OWORD *)(v64 + 16) = v197;
    *(_OWORD *)(v64 + 32) = v198;
    v65 = (_OWORD *)(*((_QWORD *)&v148 + 1) + 48LL);
    *((_QWORD *)&v148 + 1) += 48LL;
  }
  *(_OWORD *)S1 = PKEY_MIDI_UsbVID;
  v197 = 0x36u;
  if ( *((_WORD *)a2 + 16) )
  {
    *(_QWORD *)&v198 = 0x200000005LL;
    *((_QWORD *)&v198 + 1) = (char *)a2 + 32;
  }
  else
  {
    v198 = 0u;
  }
  if ( v65 == v149 )
  {
    std::vector<_DEVPROPERTY>::_Emplace_reallocate<_DEVPROPERTY>(&v148, v65, S1);
    v66 = (_OWORD *)*((_QWORD *)&v148 + 1);
  }
  else
  {
    *v65 = PKEY_MIDI_UsbVID;
    v65[1] = v197;
    v65[2] = v198;
    v66 = (_OWORD *)(*((_QWORD *)&v148 + 1) + 48LL);
    *((_QWORD *)&v148 + 1) += 48LL;
  }
  *(_OWORD *)S1 = PKEY_MIDI_UsbPID;
  v197 = 0x37u;
  if ( *((_WORD *)a2 + 17) )
  {
    *(_QWORD *)&v198 = 0x200000005LL;
    *((_QWORD *)&v198 + 1) = (char *)a2 + 34;
  }
  else
  {
    v198 = 0u;
  }
  if ( v66 == v149 )
  {
    std::vector<_DEVPROPERTY>::_Emplace_reallocate<_DEVPROPERTY>(&v148, v66, S1);
  }
  else
  {
    *v66 = PKEY_MIDI_UsbPID;
    v66[1] = v197;
    v66[2] = v198;
    *((_QWORD *)&v148 + 1) += 48LL;
  }
  v170 = 0;
  v171 = 0;
  if ( (unsigned __int8)WindowsMidiServicesInternal::WriteGroupTerminalBlocksToPropertyDataPointer(&v159, &v170) )
  {
    *(_OWORD *)S1 = PKEY_MIDI_GroupTerminalBlocks;
    v197 = 0x32u;
    LODWORD(v198) = 4099;
    DWORD1(v198) = DWORD2(v170) - v170;
    *((_QWORD *)&v198 + 1) = v170;
    v67 = *((_QWORD *)&v148 + 1);
    if ( *((_OWORD **)&v148 + 1) == v149 )
    {
      std::vector<_DEVPROPERTY>::_Emplace_reallocate<_DEVPROPERTY>(&v148, *((_QWORD *)&v148 + 1), S1);
    }
    else
    {
      **((_OWORD **)&v148 + 1) = PKEY_MIDI_GroupTerminalBlocks;
      *(_OWORD *)(v67 + 16) = v197;
      *(_OWORD *)(v67 + 32) = v198;
      *((_QWORD *)&v148 + 1) += 48LL;
    }
  }
  v162 = 0;
  v167 = 0;
  v168 = 0;
  v161 = 0u;
  v163 = 0;
  v164 = 0u;
  v165 = 0;
  v166 = 0;
  v169 = 0u;
  v68 = (char **)((char *)a2 + 136);
  v69 = std::wstring::wstring(v172, (char *)a2 + 136);
  WindowsMidiServicesInternal::ToUpperTrimmedWStringCopy(S1, v69);
  v70 = S1;
  if ( *((_QWORD *)&v197 + 1) > 7u )
    v70 = (wchar_t **)S1[0];
  *(_QWORD *)&v156[0] = v70;
  *((_QWORD *)&v156[0] + 1) = v197;
  winrt::hstring::operator=((char *)&v161 + 8, v156);
  std::wstring::~wstring(S1);
  LODWORD(v162) = *((_DWORD *)a2 + 8);
  if ( *((_QWORD *)a2 + 8) <= 7u )
    v71 = (char *)a2 + 40;
  else
    v71 = (char *)*((_QWORD *)a2 + 5);
  *(_QWORD *)&v156[0] = v71;
  *((_QWORD *)&v156[0] + 1) = *((_QWORD *)a2 + 7);
  winrt::hstring::operator=(&v163, v156);
  if ( *((_QWORD *)a2 + 16) <= 7u )
    v72 = (const wchar_t *)((char *)a2 + 104);
  else
    v72 = *v7;
  *(_QWORD *)&v156[0] = v72;
  *((_QWORD *)&v156[0] + 1) = *((_QWORD *)a2 + 15);
  winrt::hstring::operator=(&v169, v156);
  v73 = TransportState::Current();
  v74 = (_QWORD *)*((_QWORD *)v73 + 2);
  if ( v74 )
    (*(void (__fastcall **)(_QWORD))(*v74 + 8LL))(*((_QWORD *)v73 + 2));
  v75 = v74[3];
  if ( v75 )
    _InterlockedIncrement((volatile signed __int32 *)(v75 + 8));
  v76 = (volatile signed __int32 *)v74[3];
  WindowsMidiServicesPluginConfigurationLib::MidiEndpointCustomPropertiesCache::GetProperties(v74[2], v172, &v161);
  if ( v76 )
  {
    if ( _InterlockedExchangeAdd(v76 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v76)(v76);
      if ( _InterlockedExchangeAdd(v76 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v76 + 8LL))(v76);
    }
  }
  if ( v74 )
    (*(void (__fastcall **)(_QWORD *))(*v74 + 16LL))(v74);
  v206 = 0;
  v207 = si128;
  LOWORD(v206) = 0;
  v204 = 0;
  v205 = si128;
  LOWORD(v204) = 0;
  v77 = v172[0];
  v78 = (unsigned int *)*((_QWORD *)MidiKSAggregateTransportTelemetryProvider::Instance() + 1);
  v81 = *v78;
  if ( v77 )
  {
    if ( v81 > 5 )
    {
      LODWORD(v151) = *(_DWORD *)(v77 + 56);
      LODWORD(v146) = *(_DWORD *)(v77 + 40);
      if ( *((_QWORD *)a2 + 20) <= 7u )
        v83 = (char *)a2 + 136;
      else
        v83 = *v68;
      *(_QWORD *)&v154 = v83;
      *(_QWORD *)v144 = L"Found custom properties cached for this endpoint";
      v145 = v150;
      *(_QWORD *)&v156[0] = "CMidi2KSAggregateMidiEndpointManager::CreateMidiUmpEndpoint";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        (_DWORD)v78,
        (unsigned int)byte_1800895A3,
        v79,
        v80,
        (__int64)v156,
        (__int64)&v145,
        (__int64)v144,
        (__int64)&v154,
        (__int64)&v146,
        (__int64)&v151);
    }
    if ( *(_QWORD *)v77 )
    {
      std::wstring::operator=<winrt::hstring,0>(&v206, v77);
      v84 = &v206;
      if ( v207.m128i_i64[1] > 7uLL )
        v84 = (__int128 *)v206;
      *((_QWORD *)&v188 + 1) = v84;
    }
    if ( *(_QWORD *)(v77 + 8) )
    {
      std::wstring::operator=<winrt::hstring,0>(&v204, v77 + 8);
      v85 = &v204;
      if ( v205.m128i_i64[1] > 7uLL )
        v85 = (__int128 *)v204;
      v189 = v85;
    }
    WindowsMidiServicesPluginConfigurationLib::MidiEndpointCustomProperties::WriteNonCommonProperties(v77, &v148);
  }
  else if ( v81 > 5 )
  {
    if ( *((_QWORD *)a2 + 20) <= 7u )
      v82 = (char *)a2 + 136;
    else
      v82 = *v68;
    *(_QWORD *)&v154 = v82;
    *(_QWORD *)v144 = L"No cached custom properties for this endpoint.";
    v145 = v150;
    v146 = "CMidi2KSAggregateMidiEndpointManager::CreateMidiUmpEndpoint";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
      (_DWORD)v78,
      (unsigned int)byte_18008955D,
      v79,
      v80,
      (__int64)&v146,
      (__int64)&v145,
      (__int64)v144,
      (__int64)&v154);
  }
  v86 = *((_QWORD *)a2 + 29);
  v87 = *((_QWORD *)a2 + 30);
  if ( v86 != v87 )
  {
    v88 = v150;
    do
    {
      if ( v77 && (*(_QWORD *)(v77 + 56) || *(_QWORD *)(v77 + 40)) )
      {
        if ( *(_DWORD *)(v86 + 104) )
        {
          if ( *(_DWORD *)(v86 + 104) == 1 )
          {
            v98 = *(_QWORD *)(v77 + 32);
            v99 = *(_BYTE **)(v98 + 8);
            HIDWORD(v156[0]) = 0;
            for ( j = (_BYTE *)v98; !v99[25]; v99 = *(_BYTE **)v99 )
            {
              if ( v99[32] >= *(_BYTE *)(v86 + 112) )
                j = v99;
              else
                v99 += 16;
            }
            if ( !j[25] && *(_BYTE *)(v86 + 112) >= j[32] && j != (_BYTE *)v98 )
            {
              v101 = (_DWORD *)*((_QWORD *)MidiKSAggregateTransportTelemetryProvider::Instance() + 1);
              if ( *v101 <= 5u )
              {
                v104 = (const struct winrt::hstring *)(j + 48);
              }
              else
              {
                LOBYTE(v143) = *(_BYTE *)(v86 + 112);
                v104 = (const struct winrt::hstring *)(j + 48);
                if ( *(_QWORD *)v104 )
                  v105 = *(const wchar_t **)(*(_QWORD *)v104 + 16LL);
                else
                  v105 = &::S1;
                *(_QWORD *)&v156[0] = v105;
                if ( *((_QWORD *)a2 + 20) <= 7u )
                  v106 = (char *)a2 + 136;
                else
                  v106 = *v68;
                *(_QWORD *)&v154 = v106;
                *(_QWORD *)v144 = L"Found custom name for a Midi 1 source.";
                v151 = v88;
                v146 = "CMidi2KSAggregateMidiEndpointManager::CreateMidiUmpEndpoint";
                _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<1>>(
                  (_DWORD)v101,
                  (unsigned int)byte_18008949D,
                  v102,
                  v103,
                  (__int64)&v146,
                  (__int64)&v151,
                  (__int64)v144,
                  (__int64)&v154,
                  (__int64)v156,
                  (__int64)&v143);
              }
              WindowsMidiServicesNamingLib::MidiEndpointNameTable::UpdateSourceEntryCustomName(
                (struct KsAggregateEndpointDefinition *)((char *)a2 + 256),
                *(_BYTE *)(v86 + 112),
                v104);
            }
          }
        }
        else
        {
          v89 = *(_QWORD *)(v77 + 48);
          v90 = *(_BYTE **)(v89 + 8);
          HIDWORD(v156[0]) = 0;
          for ( k = (_BYTE *)v89; !v90[25]; v90 = *(_BYTE **)v90 )
          {
            if ( v90[32] >= *(_BYTE *)(v86 + 112) )
              k = v90;
            else
              v90 += 16;
          }
          if ( !k[25] && *(_BYTE *)(v86 + 112) >= k[32] && k != (_BYTE *)v89 )
          {
            v92 = (_DWORD *)*((_QWORD *)MidiKSAggregateTransportTelemetryProvider::Instance() + 1);
            if ( *v92 <= 5u )
            {
              v95 = (const struct winrt::hstring *)(k + 48);
            }
            else
            {
              LOBYTE(v143) = *(_BYTE *)(v86 + 112);
              v95 = (const struct winrt::hstring *)(k + 48);
              if ( *(_QWORD *)v95 )
                v96 = *(const wchar_t **)(*(_QWORD *)v95 + 16LL);
              else
                v96 = &::S1;
              *(_QWORD *)&v156[0] = v96;
              if ( *((_QWORD *)a2 + 20) <= 7u )
                v97 = (char *)a2 + 136;
              else
                v97 = *v68;
              *(_QWORD *)&v154 = v97;
              *(_QWORD *)v144 = L"Found custom name for a Midi 1 destination.";
              v145 = v88;
              v146 = "CMidi2KSAggregateMidiEndpointManager::CreateMidiUmpEndpoint";
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<1>>(
                (_DWORD)v92,
                (unsigned int)byte_1800894FD,
                v93,
                v94,
                (__int64)&v146,
                (__int64)&v145,
                (__int64)v144,
                (__int64)&v154,
                (__int64)v156,
                (__int64)&v143);
            }
            WindowsMidiServicesNamingLib::MidiEndpointNameTable::UpdateDestinationEntryCustomName(
              (struct KsAggregateEndpointDefinition *)((char *)a2 + 256),
              *(_BYTE *)(v86 + 112),
              v95);
          }
        }
      }
      v86 += 120;
    }
    while ( v86 != v87 );
    v9 = -1;
  }
  WindowsMidiServicesNamingLib::MidiEndpointNameTable::WriteProperties((char *)a2 + 256, &v148);
  v199 = PKEY_MIDI_EndpointDiscoveryProcessComplete;
  v200 = 0x8Cu;
  v201.m128i_i64[0] = 0x100000011LL;
  v201.m128i_i64[1] = (__int64)&v147;
  v107 = *((_QWORD *)&v148 + 1);
  if ( *((_OWORD **)&v148 + 1) == v149 )
  {
    std::vector<_DEVPROPERTY>::_Emplace_reallocate<_DEVPROPERTY>(&v148, *((_QWORD *)&v148 + 1), &v199);
  }
  else
  {
    **((_OWORD **)&v148 + 1) = PKEY_MIDI_EndpointDiscoveryProcessComplete;
    *(_OWORD *)(v107 + 16) = v200;
    *(__m128i *)(v107 + 32) = v201;
    *((_QWORD *)&v148 + 1) += 48LL;
  }
  memset_0(&v173, 0, 0x48u);
  v173 = 72;
  v108 = (_QWORD *)((char *)a2 + 136);
  if ( *((_QWORD *)a2 + 20) > 7u )
    v108 = (_QWORD *)*v108;
  v174 = v108;
  v175 = 0;
  v109 = (_QWORD *)((char *)a2 + 104);
  if ( *((_QWORD *)a2 + 16) > 7u )
    v109 = (_QWORD *)*v109;
  v176 = v109;
  pv = 0;
  v110 = (_DWORD *)*((_QWORD *)MidiKSAggregateTransportTelemetryProvider::Instance() + 1);
  if ( *v110 <= 4u )
  {
    v114 = v150;
  }
  else
  {
    v113 = (_QWORD *)((char *)a2 + 104);
    if ( *((_QWORD *)a2 + 16) > 7u )
      v113 = (_QWORD *)*v113;
    *(_QWORD *)&v156[0] = v113;
    *(_QWORD *)&v154 = L"Activating endpoint";
    v114 = v150;
    *(_QWORD *)v144 = v150;
    v145 = "CMidi2KSAggregateMidiEndpointManager::CreateMidiUmpEndpoint";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
      (_DWORD)v110,
      (unsigned int)byte_180089465,
      v111,
      v112,
      (__int64)&v145,
      (__int64)v144,
      (__int64)&v154,
      (__int64)v156);
  }
  v115 = *((_QWORD *)v114 + 2);
  v116 = *(__int64 (__fastcall **)(__int64, char *, _QWORD, __int64))(*(_QWORD *)v115 + 40LL);
  v117 = pv;
  if ( pv )
  {
    LastError = GetLastError();
    CoTaskMemFree(v117);
    SetLastError(LastError);
  }
  pv = 0;
  if ( *((_QWORD *)a2 + 28) <= 7u )
    v119 = (char *)a2 + 200;
  else
    v119 = (char *)*((_QWORD *)a2 + 25);
  v120 = v116(v115, v119, 0, 2);
  v121 = v120;
  if ( v120 >= 0 )
  {
    v125 = (_DWORD *)*((_QWORD *)MidiKSAggregateTransportTelemetryProvider::Instance() + 1);
    if ( *v125 > 4u )
    {
      *(_QWORD *)&v156[0] = pv;
      v128 = (_QWORD *)((char *)a2 + 104);
      if ( *((_QWORD *)a2 + 16) > 7u )
        v128 = (_QWORD *)*v128;
      *(_QWORD *)&v154 = v128;
      *(_QWORD *)v144 = L"Aggregate UMP endpoint created";
      v145 = v114;
      v150 = "CMidi2KSAggregateMidiEndpointManager::CreateMidiUmpEndpoint";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
        (_DWORD)v125,
        (unsigned int)byte_180089409,
        v126,
        v127,
        (__int64)&v150,
        (__int64)&v145,
        (__int64)v144,
        (__int64)&v154,
        (__int64)v156);
    }
    v202 = 0;
    v203 = 0;
    do
      ++v9;
    while ( *((_WORD *)pv + v9) );
    std::wstring::_Construct<1,unsigned short const *>(&v202);
    v129 = std::wstring::wstring(v156, &v202);
    WindowsMidiServicesInternal::ToLowerTrimmedWStringCopy(S1, v129);
    std::wstring::operator=(a2, S1);
    std::wstring::~wstring(S1);
    std::wstring::~wstring(&v202);
    v130 = (struct _RTL_CRITICAL_SECTION *)(v114 + 32);
    EnterCriticalSection((LPCRITICAL_SECTION)(v114 + 32));
    v131 = (__int64 *)(v114 + 72);
    v132 = std::wstring::wstring(&v202, (char *)a2 + 200);
    WindowsMidiServicesInternal::ToUpperTrimmedWStringCopy(S1, v132);
    std::_Tree<std::_Tmap_traits<std::wstring,std::shared_ptr<KsAggregateParentDeviceDefinition2>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::shared_ptr<KsAggregateParentDeviceDefinition2>>>,0>>::_Find_lower_bound<std::wstring>(
      v114 + 72,
      &v154,
      S1);
    v133 = v155;
    if ( *(_BYTE *)(v155 + 25) )
      goto LABEL_252;
    v134 = (const wchar_t *)(v155 + 32);
    v135 = *(_QWORD *)(v155 + 48);
    if ( *(_QWORD *)(v155 + 56) > 7u )
      v134 = *(const wchar_t **)v134;
    v136 = v197;
    v137 = (const wchar_t *)S1;
    if ( *((_QWORD *)&v197 + 1) > 7u )
      v137 = S1[0];
    v138 = v197;
    if ( v135 < (unsigned __int64)v197 )
      v138 = *(_QWORD *)(v155 + 48);
    v139 = wmemcmp(v137, v134, v138);
    if ( v139 )
    {
      if ( v139 < 0 )
      {
LABEL_252:
        if ( v131[1] == 0xAE4C415C9882B9LL )
          std::_Throw_tree_length_error();
        v140 = *v131;
        *(_QWORD *)&v156[0] = v131;
        v141 = operator new(0x178u);
        v141[2] = *(_OWORD *)S1;
        v141[3] = v197;
        *(_QWORD *)&v197 = 0;
        *((_QWORD *)&v197 + 1) = 7;
        LOWORD(S1[0]) = 0;
        KsAggregateEndpointDefinition::KsAggregateEndpointDefinition((KsAggregateEndpointDefinition *)(v141 + 4), a2);
        *(_QWORD *)v141 = v140;
        *((_QWORD *)v141 + 1) = v140;
        *((_QWORD *)v141 + 2) = v140;
        *((_WORD *)v141 + 12) = 0;
        *((_QWORD *)&v156[0] + 1) = 0;
        std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<std::wstring const,KsAggregateEndpointDefinition>,void *>>>::~_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<std::wstring const,KsAggregateEndpointDefinition>,void *>>>(v156);
        v156[0] = v154;
        std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::shared_ptr<KsAggregateParentDeviceDefinition2>>>>::_Insert_node(
          v131,
          v156,
          v141);
        goto LABEL_254;
      }
    }
    else if ( v136 < v135 )
    {
      goto LABEL_252;
    }
    KsAggregateEndpointDefinition::operator=(v133 + 64, a2);
LABEL_254:
    std::wstring::~wstring(S1);
    if ( v130 )
      LeaveCriticalSection(v130);
    goto LABEL_256;
  }
  wil::details::in1diag3::_Log_Hr(
    retaddr,
    (void *)0x1E8,
    (unsigned int)"avcore\\midi2\\transport\\ksaggregatetransport\\midi2.ksaggregatemidiendpointmanager.cpp",
    (const char *)(unsigned int)v120,
    (int)v183);
  v122 = (_DWORD *)*((_QWORD *)MidiKSAggregateTransportTelemetryProvider::Instance() + 1);
  if ( *v122 > 2u )
  {
    LODWORD(v146) = v121;
    v124 = (_QWORD *)((char *)a2 + 104);
    if ( v124[3] > 7u )
      v124 = (_QWORD *)*v124;
    *(_QWORD *)&v156[0] = v124;
    *(_QWORD *)&v154 = L"Aggregate UMP endpoint creation failed";
    *(_QWORD *)v144 = v114;
    v145 = "CMidi2KSAggregateMidiEndpointManager::CreateMidiUmpEndpoint";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
      (_DWORD)v122,
      (unsigned int)&word_1800893C6,
      (_DWORD)v122,
      v123,
      (__int64)&v145,
      (__int64)v144,
      (__int64)&v154,
      (__int64)v156,
      (__int64)&v146);
  }
LABEL_256:
  if ( pv )
    CoTaskMemFree(pv);
  std::wstring::~wstring(&v204);
  std::wstring::~wstring(&v206);
  std::shared_ptr<WindowsMidiServicesPluginConfigurationLib::MidiEndpointMatchCriteria>::~shared_ptr<WindowsMidiServicesPluginConfigurationLib::MidiEndpointMatchCriteria>(v172);
  WindowsMidiServicesPluginConfigurationLib::MidiEndpointMatchCriteria::~MidiEndpointMatchCriteria((WindowsMidiServicesPluginConfigurationLib::MidiEndpointMatchCriteria *)&v161);
  std::vector<enum std::byte>::~vector<enum std::byte>(&v170);
  std::shared_ptr<WindowsMidiServicesPluginConfigurationLib::MidiEndpointMatchCriteria>::~shared_ptr<WindowsMidiServicesPluginConfigurationLib::MidiEndpointMatchCriteria>(v208);
  std::vector<PinMapEntryStagingEntry>::~vector<PinMapEntryStagingEntry>(&v157);
  std::vector<PinMapEntryStagingEntry>::~vector<PinMapEntryStagingEntry>(&v159);
  std::vector<_DEVPROPERTY>::~vector<_DEVPROPERTY>(&v148);
  return v121;
}

```

## disassembly

```asm
0x180023320  mov     rax, rsp
0x180023323  mov     [rax+18h], rbx
0x180023327  push    rbp
0x180023328  push    rsi
0x180023329  push    rdi
0x18002332a  push    r12
0x18002332c  push    r13
0x18002332e  push    r14
0x180023330  push    r15
0x180023332  lea     rbp, [rax-368h]
0x180023339  sub     rsp, 430h
0x180023340  movaps  xmmword ptr [rax-48h], xmm6
0x180023344  mov     rax, cs:__security_cookie
0x18002334b  xor     rax, rsp
0x18002334e  mov     [rbp+360h+var_50], rax
0x180023355  mov     r14, rdx
0x180023358  mov     rbx, rcx
0x18002335b  mov     [rbp+360h+var_3C0], rcx
0x18002335f  call    ?Instance@MidiKSAggregateTransportTelemetryProvider@@KAPEAV1@XZ; MidiKSAggregateTransportTelemetryProvider::Instance(void)
0x180023364  mov     rcx, [rax+8]
0x180023368  mov     eax, [rcx]
0x18002336a  lea     rsi, [r14+68h]
0x18002336e  lea     rdx, aCmidi2ksaggreg_1; "CMidi2KSAggregateMidiEndpointManager::C"...
0x180023375  cmp     eax, 4
0x180023378  jbe     short loc_1800233D6
0x18002337a  cmp     qword ptr [rsi+18h], 7
0x18002337f  jbe     short loc_180023386
0x180023381  mov     rax, [rsi]
0x180023384  jmp     short loc_180023389
0x180023386  mov     rax, rsi
0x180023389  mov     [rsp+460h+var_3E8], rax
0x18002338e  lea     rax, aEnter_0; "Enter"
0x180023395  mov     [rbp+360h+var_3B8], rax
0x180023399  mov     [rsp+460h+var_3F0], rbx
0x18002339e  mov     qword ptr [rsp+460h+var_3F8], rdx
0x1800233a3  lea     rax, [rsp+460h+var_3E8]
0x1800233a8  mov     [rsp+460h+var_428], rax
0x1800233ad  lea     rax, [rbp+360h+var_3B8]
0x1800233b1  mov     [rsp+460h+var_430], rax
0x1800233b6  lea     rax, [rsp+460h+var_3F0]
0x1800233bb  mov     [rsp+460h+var_438], rax
0x1800233c0  lea     rax, [rsp+460h+var_3F8]
0x1800233c5  mov     [rsp+460h+var_440], rax; int
0x1800233ca  lea     rdx, byte_1800896D3
0x1800233d1  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x1800233d6  or      r15, 0FFFFFFFFFFFFFFFFh
0x1800233da  mov     [rbp+360h+var_3E0], r15b
0x1800233de  mov     r12, [r14+0F0h]
0x1800233e5  mov     r13, [r14+0E8h]
0x1800233ec  mov     rax, r12
0x1800233ef  sub     rax, r13
0x1800233f2  sar     rax, 3
0x1800233f6  mov     rcx, 0EEEEEEEEEEEEEEEFh
0x180023400  imul    rax, rcx
0x180023404  lea     edx, [r15+2]
0x180023408  cmp     rax, rdx
0x18002340b  jnb     short loc_180023433
0x18002340d  mov     rcx, [rbp+368h]; this
0x180023414  mov     edi, 80070057h
0x180023419  mov     r9d, edi; char *
0x18002341c  lea     r8, aAvcoreMidi2Tra_0; "avcore\\midi2\\transport\\ksaggregatetr"...
0x180023423  lea     edx, [r15+70h]; void *
0x180023427  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002342c  mov     eax, edi
0x18002342e  jmp     loc_180024B9E
0x180023433  xorps   xmm0, xmm0
0x180023436  movdqu  [rbp+360h+var_3D8], xmm0
0x18002343b  xor     edi, edi
0x18002343d  mov     [rbp+360h+var_3C8], rdi
0x180023441  xor     eax, eax
0x180023443  mov     [rbp+360h+var_210], rax
0x18002344a  mov     [rbp+360h+var_1BC], eax
0x180023450  movups  xmm0, xmmword ptr cs:_GUID_0f273b18_e372_4d95_87ac_c31c3d22e937.Data1
0x180023457  movdqu  xmmword ptr [rbp+360h+var_220], xmm0
0x18002345f  cmp     qword ptr [rsi+18h], 7
0x180023464  jbe     short loc_18002346B
0x180023466  mov     rax, [rsi]
0x180023469  jmp     short loc_18002346E
0x18002346b  mov     rax, rsi
0x18002346e  mov     [rbp+360h+var_208], rax
0x180023475  lea     rax, aKsa; "KSA"
0x18002347c  mov     [rbp+360h+var_200], rax
0x180023483  jbe     short loc_18002348A
0x180023485  mov     rax, [rsi]
0x180023488  jmp     short loc_18002348D
0x18002348a  mov     rax, rsi
0x18002348d  mov     [rbp+360h+var_1F8], rax
0x180023494  xorps   xmm0, xmm0
0x180023497  movdqa  [rbp+360h+var_1F0], xmm0
0x18002349f  mov     [rbp+360h+var_1E0], rdi
0x1800234a6  cmp     [r14+38h], rdi
0x1800234aa  jnz     short loc_1800234B5
0x1800234ac  mov     [rbp+360h+var_1D8], rdi
0x1800234b3  jmp     short loc_1800234CA
0x1800234b5  lea     rax, [r14+28h]
0x1800234b9  cmp     qword ptr [rax+18h], 7
0x1800234be  jbe     short loc_1800234C3
0x1800234c0  mov     rax, [rax]
0x1800234c3  mov     [rbp+360h+var_1D8], rax
0x1800234ca  cmp     [r14+58h], rdi
0x1800234ce  jnz     short loc_1800234D9
0x1800234d0  mov     [rbp+360h+var_1D0], rdi
0x1800234d7  jmp     short loc_1800234EE
0x1800234d9  lea     rax, [r14+48h]
0x1800234dd  cmp     qword ptr [rax+18h], 7
0x1800234e2  jbe     short loc_1800234E7
0x1800234e4  mov     rax, [rax]
0x1800234e7  mov     [rbp+360h+var_1D0], rax
0x1800234ee  mov     [rbp+360h+var_1C8], 2
0x1800234f8  mov     [rbp+360h+var_1C4], edx
0x1800234fe  mov     [rbp+360h+var_1C0], 0Dh
0x180023508  mov     cl, dil
0x18002350b  movdqu  [rbp+360h+var_348], xmm0
0x180023510  mov     [rbp+360h+var_338], rdi
0x180023514  xorps   xmm1, xmm1
0x180023517  movdqu  [rbp+360h+var_360], xmm1
0x18002351c  mov     [rbp+360h+var_350], rdi
0x180023520  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x180023528  cmp     r13, r12
0x18002352b  jz      loc_1800239F7
0x180023531  cmp     [r13+10h], rdi
0x180023535  jz      loc_1800239B3
0x18002353b  mov     [rbp+360h+var_24F], 10000h
0x180023545  mov     [rbp+360h+var_24A], 0
0x18002354f  xorps   xmm0, xmm0
0x180023552  movups  [rbp+360h+Src], xmm0
0x180023559  mov     [rbp+360h+var_230], rdi
0x180023560  mov     [rbp+360h+var_228], 7
0x18002356b  mov     word ptr [rbp+360h+Src], di
0x180023572  add     cl, dl
0x180023574  mov     byte ptr [rsp+460h+var_400], cl
0x180023578  mov     [rbp+360h+var_250], cl
0x18002357e  movups  [rbp+360h+var_180], xmm0
0x180023585  xorps   xmm1, xmm1
0x180023588  movups  [rbp+360h+var_170], xmm1
0x18002358f  movdqu  [rbp+360h+var_160], xmm6
0x180023597  mov     word ptr [rbp+360h+var_170], di
0x18002359e  mov     eax, [r13+40h]
0x1800235a2  mov     dword ptr [rbp+360h+var_180+4], eax
0x1800235a8  mov     rdx, r13
0x1800235ab  lea     rcx, [rbp+360h+var_170]
0x1800235b2  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x1800235b7  mov     eax, [r13+68h]
0x1800235bb  mov     dword ptr [rbp+360h+var_180+8], eax
0x1800235c1  mov     r8b, [r13+70h]
0x1800235c5  mov     byte ptr [rbp+360h+var_180], r8b
0x1800235cc  mov     byte ptr [rbp+360h+var_24F+1], r8b
0x1800235d3  test    eax, eax
0x1800235d5  jnz     loc_18002366C
0x1800235db  mov     byte ptr [rbp+360h+var_24F], 1
0x1800235e2  lea     rcx, [r14+100h]
0x1800235e9  lea     rdx, [rbp+360h+var_380]
0x1800235ed  call    ?GetDestinationEntry@MidiEndpointNameTable@WindowsMidiServicesNamingLib@@QEBA?AV?$shared_ptr@UMidi1PortNameEntry@WindowsMidiServicesNamingLib@@@std@@E@Z; WindowsMidiServicesNamingLib::MidiEndpointNameTable::GetDestinationEntry(uchar)
0x1800235f2  mov     rdx, qword ptr [rbp+360h+var_380]
0x1800235f6  test    rdx, rdx
0x1800235f9  jz      short loc_180023663
0x1800235fb  add     rdx, 88h
0x180023602  cmp     [rdx], di
0x180023605  jz      short loc_180023663
0x180023607  xorps   xmm0, xmm0
0x18002360a  movups  xmmword ptr [rbp+360h+S1], xmm0
0x180023611  xorps   xmm1, xmm1
0x180023614  movdqu  [rbp+360h+var_1A0], xmm1
0x18002361c  mov     r8, r15
0x18002361f  inc     r8
0x180023622  cmp     [rdx+r8*2], di
0x180023627  jnz     short loc_18002361F
0x180023629  lea     rcx, [rbp+360h+S1]
0x180023630  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180023635  lea     rdx, [rbp+360h+S1]; void *
0x18002363c  lea     rcx, [rbp+360h+var_F0]; Src
0x180023643  call    ?TrimmedWStringCopy@WindowsMidiServicesInternal@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V23@@Z; WindowsMidiServicesInternal::TrimmedWStringCopy(std::wstring)
0x180023648  mov     rdx, rax
0x18002364b  lea     rcx, [rbp+360h+Src]
0x180023652  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180023657  lea     rcx, [rbp+360h+var_F0]; void *
0x18002365e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180023663  mov     rbx, qword ptr [rbp+360h+var_380+8]
0x180023667  jmp     loc_180023701
0x18002366c  cmp     eax, 1
0x18002366f  jnz     loc_180023979
0x180023675  mov     byte ptr [rbp+360h+var_24F], 2
0x18002367c  lea     rcx, [r14+100h]
0x180023683  lea     rdx, [rbp+360h+var_3A0]
0x180023687  call    ?GetSourceEntry@MidiEndpointNameTable@WindowsMidiServicesNamingLib@@QEBA?AV?$shared_ptr@UMidi1PortNameEntry@WindowsMidiServicesNamingLib@@@std@@E@Z; WindowsMidiServicesNamingLib::MidiEndpointNameTable::GetSourceEntry(uchar)
0x18002368c  mov     rdx, qword ptr [rbp+360h+var_3A0]
0x180023690  test    rdx, rdx
0x180023693  jz      short loc_1800236FD
0x180023695  add     rdx, 88h
0x18002369c  cmp     [rdx], di
0x18002369f  jz      short loc_1800236FD
0x1800236a1  xorps   xmm0, xmm0
0x1800236a4  movups  xmmword ptr [rbp+360h+S1], xmm0
0x1800236ab  xorps   xmm1, xmm1
0x1800236ae  movdqu  [rbp+360h+var_1A0], xmm1
0x1800236b6  mov     r8, r15
0x1800236b9  inc     r8
0x1800236bc  cmp     [rdx+r8*2], di
0x1800236c1  jnz     short loc_1800236B9
0x1800236c3  lea     rcx, [rbp+360h+S1]
0x1800236ca  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800236cf  lea     rdx, [rbp+360h+S1]; void *
0x1800236d6  lea     rcx, [rbp+360h+var_F0]; Src
0x1800236dd  call    ?TrimmedWStringCopy@WindowsMidiServicesInternal@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V23@@Z; WindowsMidiServicesInternal::TrimmedWStringCopy(std::wstring)
0x1800236e2  mov     rdx, rax
0x1800236e5  lea     rcx, [rbp+360h+Src]
0x1800236ec  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800236f1  lea     rcx, [rbp+360h+var_F0]; void *
0x1800236f8  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800236fd  mov     rbx, qword ptr [rbp+360h+var_3A0+8]
0x180023701  test    rbx, rbx
0x180023704  jz      short loc_18002373D
0x180023706  mov     eax, r15d
0x180023709  lock xadd [rbx+8], eax
0x18002370e  add     eax, r15d
0x180023711  jnz     short loc_18002373D
0x180023713  mov     rax, [rbx]
0x180023716  mov     rcx, rbx
0x180023719  mov     rax, [rax]
0x18002371c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023721  mov     eax, r15d
0x180023724  lock xadd [rbx+0Ch], eax
0x180023729  add     eax, r15d
0x18002372c  jnz     short loc_18002373D
0x18002372e  mov     rax, [rbx]
0x180023731  mov     rcx, rbx
0x180023734  mov     rax, [rax+8]
0x180023738  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002373d  cmp     [rbp+360h+var_230], rdi
0x180023744  jnz     loc_180023873
0x18002374a  mov     rdx, rsi
0x18002374d  lea     rcx, [rbp+360h+Src]
0x180023754  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x180023759  movzx   eax, byte ptr [rbp+360h+var_24F+1]
0x180023760  test    al, al
0x180023762  jz      loc_180023873
0x180023768  mov     [rbp+360h+var_3B0], ax
0x18002376c  xorps   xmm0, xmm0
0x18002376f  movups  [rbp+360h+var_150], xmm0
0x180023776  xorps   xmm1, xmm1
0x180023779  movdqu  [rbp+360h+var_140], xmm1
0x180023781  mov     ebx, 1
0x180023786  mov     r8d, ebx
0x180023789  lea     rdx, [rbp+360h+var_3B0]
0x18002378d  lea     rcx, [rbp+360h+var_150]
0x180023794  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180023799  mov     r9d, ebx
0x18002379c  lea     r8, asc_180080F20; " "
0x1800237a3  xor     edx, edx
0x1800237a5  lea     rcx, [rbp+360h+var_150]; Src
0x1800237ac  call    ??$_Insert@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KQEBG0@Z; std::wstring::_Insert<ushort>(unsigned __int64,ushort const * const,unsigned __int64)
0x1800237b1  movups  xmm0, xmmword ptr [rax]
0x1800237b4  movups  xmmword ptr [rbp+360h+S1], xmm0
0x1800237bb  movups  xmm1, xmmword ptr [rax+10h]
0x1800237bf  movups  [rbp+360h+var_1A0], xmm1
0x1800237c6  mov     [rax], di
0x1800237c9  mov     [rax+10h], rdi
0x1800237cd  mov     qword ptr [rax+18h], 7
0x1800237d5  movq    rdx, xmm1
0x1800237da  lea     r9, [rbp+360h+S1]
0x1800237e1  movq    rcx, xmm0
0x1800237e6  psrldq  xmm1, 8
0x1800237eb  movq    rax, xmm1
0x1800237f0  cmp     rax, 7
0x1800237f4  cmova   r9, rcx
0x1800237f8  mov     rcx, [rbp+360h+var_230]
0x1800237ff  mov     rax, [rbp+360h+var_228]
0x180023806  sub     rax, rcx
0x180023809  cmp     rdx, rax
0x18002380c  ja      short loc_18002384A
0x18002380e  lea     rdi, [rdx+rcx]
0x180023812  mov     [rbp+360h+var_230], rdi
0x180023819  lea     rbx, [rbp+360h+Src]
0x180023820  cmp     [rbp+360h+var_228], 7
0x180023828  cmova   rbx, qword ptr [rbp+360h+Src]
0x180023830  lea     r8, [rdx+rdx]; Size
0x180023834  lea     rcx, [rbx+rcx*2]; void *
0x180023838  mov     rdx, r9; Src
0x18002383b  call    memmove_0
0x180023840  xor     eax, eax
0x180023842  mov     [rbx+rdi*2], ax
0x180023846  xor     edi, edi
0x180023848  jmp     short loc_18002385B
0x18002384a  mov     [rsp+460h+var_440], rdx; __int64
0x18002384f  lea     rcx, [rbp+360h+Src]; Src
0x180023856  call    ??$_Reallocate_grow_by@V_lambda_1_@?1???$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV23@QEBG_K@Z@PEBG_K@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1???$_Append@G@01@AEAAAEAV01@QEBG0@Z@PEBG_K@Z; std::wstring::_Reallocate_grow_by<`std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)'::`2'::_lambda_1_,ushort const *,unsigned __int64>(unsigned __int64,`std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)'::`2'::_lambda_1_,ushort const *,unsigned __int64)
0x18002385b  lea     rcx, [rbp+360h+S1]; void *
0x180023862  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180023867  lea     rcx, [rbp+360h+var_150]; void *
0x18002386e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180023873  mov     eax, 1
0x180023878  mov     byte ptr [rbp+360h+var_24F+3], al
0x18002387e  mov     [rbp+360h+var_24A], 10001h
0x180023888  mov     rdx, qword ptr [rbp+360h+var_348+8]
0x18002388c  cmp     rdx, [rbp+360h+var_338]
0x180023890  jz      short loc_1800238EB
0x180023892  mov     al, [rbp+360h+var_250]
0x180023898  mov     [rdx], al
0x18002389a  mov     al, byte ptr [rbp+360h+var_24F]
0x1800238a0  mov     [rdx+1], al
  ... truncated ...
```
