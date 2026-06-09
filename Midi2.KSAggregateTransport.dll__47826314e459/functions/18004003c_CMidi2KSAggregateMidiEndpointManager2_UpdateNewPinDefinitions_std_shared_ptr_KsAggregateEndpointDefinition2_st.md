# CMidi2KSAggregateMidiEndpointManager2::UpdateNewPinDefinitions(std::shared_ptr<KsAggregateEndpointDefinition2>,std::shared_ptr<KsAggregateParentDeviceDefinition2>)

- ea: `0x18004003c`
- end: `0x180040a6d`
- name: `?UpdateNewPinDefinitions@CMidi2KSAggregateMidiEndpointManager2@@AEAAJV?$shared_ptr@UKsAggregateEndpointDefinition2@@@std@@V?$shared_ptr@VKsAggregateParentDeviceDefinition2@@@3@@Z`
- size: `2609`
- prototype: ``
- caller_count: `2`
- callee_count: `17`
- tags: `service_task, installer_update`

## callers

- `0x180036d5c`
- `0x18003c890`

## callees

- `0x18000163c`
- `0x1800016dc`
- `0x180002918`
- `0x180005020`
- `0x18000b394`
- `0x18000d430`
- `0x18000d7d8`
- `0x1800117d8`
- `0x180013118`
- `0x18001a844`
- `0x18001aa6c`
- `0x1800229bc`
- `0x180033838`
- `0x18003b038`
- `0x18004003c`
- `0x1800562ec`
- `0x18005e010`

## string_xrefs

- `0x1800401ee`: `CMidi2KSAggregateMidiEndpointManager2::UpdateNewPinDefinitions`
- `0x180040467`: `CMidi2KSAggregateMidiEndpointManager2::UpdateNewPinDefinitions`
- `0x1800407f8`: `CMidi2KSAggregateMidiEndpointManager2::UpdateNewPinDefinitions`
- `0x1800408a2`: `CMidi2KSAggregateMidiEndpointManager2::UpdateNewPinDefinitions`
- `0x180040892`: `Name table updated`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall CMidi2KSAggregateMidiEndpointManager2::UpdateNewPinDefinitions(
        const char *a1,
        _QWORD *a2,
        _QWORD *a3)
{
  volatile signed __int32 *v6; // rdi
  volatile signed __int32 *v7; // rdi
  volatile signed __int32 *v8; // rdi
  _DWORD *v10; // r8
  int v11; // r9d
  _QWORD *v12; // rcx
  const char *v13; // rax
  const char *v14; // rcx
  __int64 v15; // r8
  __int64 v16; // rdx
  __int64 i; // rcx
  __int64 v18; // rcx
  __int64 j; // rdx
  __int64 *v20; // rdi
  __int64 *v21; // r12
  __m128i si128; // xmm6
  __int64 v23; // rdx
  unsigned __int8 v24; // al
  _DWORD *v25; // r10
  const wchar_t *v26; // rcx
  __int64 v27; // rax
  int v28; // ecx
  __int64 v29; // rax
  __int64 v30; // rax
  __int64 v31; // rax
  const wchar_t *v32; // rcx
  __int64 v33; // rax
  _DWORD *v34; // r10
  __int64 *v35; // rcx
  wchar_t *v36; // rdx
  wchar_t *v37; // r8
  const wchar_t *v38; // r9
  __int64 v39; // rax
  int v40; // eax
  __int64 v41; // rax
  int v42; // eax
  __int64 v43; // rax
  int v44; // eax
  __int64 v45; // rax
  __int64 v46; // rdx
  _DWORD *v47; // rcx
  int v48; // r8d
  int v49; // r9d
  volatile signed __int32 *v50; // rdi
  volatile signed __int32 *v51; // rdi
  volatile signed __int32 *v52; // rdi
  volatile signed __int32 *v53; // rdi
  int S2; // [rsp+28h] [rbp-E0h]
  char v55; // [rsp+68h] [rbp-A0h] BYREF
  char v56; // [rsp+69h] [rbp-9Fh] BYREF
  int v57; // [rsp+6Ch] [rbp-9Ch] BYREF
  __int64 v58; // [rsp+70h] [rbp-98h] BYREF
  const char *v59; // [rsp+78h] [rbp-90h] BYREF
  const char *v60; // [rsp+80h] [rbp-88h] BYREF
  const wchar_t *v61; // [rsp+88h] [rbp-80h] BYREF
  const char *v62; // [rsp+90h] [rbp-78h] BYREF
  const char *v63; // [rsp+98h] [rbp-70h] BYREF
  __int64 *v64; // [rsp+A0h] [rbp-68h] BYREF
  __int64 *v65; // [rsp+A8h] [rbp-60h]
  const wchar_t *v66; // [rsp+B8h] [rbp-50h]
  __int64 v67; // [rsp+C0h] [rbp-48h]
  const wchar_t *v68; // [rsp+C8h] [rbp-40h]
  __int64 v69; // [rsp+D0h] [rbp-38h]
  const wchar_t *v70; // [rsp+D8h] [rbp-30h]
  __int64 v71; // [rsp+E0h] [rbp-28h]
  _QWORD *v72; // [rsp+E8h] [rbp-20h]
  _QWORD *v73; // [rsp+F0h] [rbp-18h]
  wchar_t v74[8]; // [rsp+F8h] [rbp-10h] BYREF
  __m128i v75; // [rsp+108h] [rbp+0h]
  wchar_t v76[8]; // [rsp+118h] [rbp+10h] BYREF
  __m128i v77; // [rsp+128h] [rbp+20h]
  __int64 v78[2]; // [rsp+138h] [rbp+30h] BYREF
  __m128i v79; // [rsp+148h] [rbp+40h]
  int v80[4]; // [rsp+158h] [rbp+50h] BYREF
  __int128 v81; // [rsp+168h] [rbp+60h]
  _BYTE Src[32]; // [rsp+178h] [rbp+70h] BYREF
  _BYTE v83[32]; // [rsp+198h] [rbp+90h] BYREF
  _BYTE v84[32]; // [rsp+1B8h] [rbp+B0h] BYREF
  const char *v85; // [rsp+1D8h] [rbp+D0h]
  __int64 v86; // [rsp+1E0h] [rbp+D8h]
  const char **v87; // [rsp+1E8h] [rbp+E0h]
  __int64 v88; // [rsp+1F0h] [rbp+E8h]
  const wchar_t *v89; // [rsp+1F8h] [rbp+F0h]
  __int64 v90; // [rsp+200h] [rbp+F8h]
  char *v91; // [rsp+208h] [rbp+100h]
  __int64 v92; // [rsp+210h] [rbp+108h]
  const wchar_t *v93; // [rsp+218h] [rbp+110h]
  int v94; // [rsp+220h] [rbp+118h]
  int v95; // [rsp+224h] [rbp+11Ch]
  wchar_t *v96; // [rsp+228h] [rbp+120h]
  int v97; // [rsp+230h] [rbp+128h]
  int v98; // [rsp+234h] [rbp+12Ch]
  wchar_t *v99; // [rsp+238h] [rbp+130h]
  int v100; // [rsp+240h] [rbp+138h]
  int v101; // [rsp+244h] [rbp+13Ch]
  __int64 *v102; // [rsp+248h] [rbp+140h]
  int v103; // [rsp+250h] [rbp+148h]
  int v104; // [rsp+254h] [rbp+14Ch]
  __int128 v105; // [rsp+258h] [rbp+150h]
  __int128 v106; // [rsp+268h] [rbp+160h]
  wil::details::in1diag3 *retaddr; // [rsp+2D0h] [rbp+1C8h]

  v72 = a2;
  v73 = a3;
  if ( !*a2 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x80C,
      (unsigned int)"avcore\\midi2\\transport\\ksaggregatetransport\\midi2.ksaggregatemidiendpointmanager2.cpp",
      (const char *)0x80070057LL,
      S2);
    v6 = (volatile signed __int32 *)a2[1];
    if ( v6 )
    {
      if ( _InterlockedExchangeAdd(v6 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v6)(v6);
        if ( _InterlockedExchangeAdd(v6 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v6 + 8LL))(v6);
      }
    }
    v7 = (volatile signed __int32 *)a3[1];
    if ( !v7 )
      return 2147942487LL;
    if ( _InterlockedExchangeAdd(v7 + 2, 0xFFFFFFFF) != 1 )
      return 2147942487LL;
    (**(void (__fastcall ***)(volatile signed __int32 *))v7)(v7);
    if ( _InterlockedExchangeAdd(v7 + 3, 0xFFFFFFFF) != 1 )
      return 2147942487LL;
    goto LABEL_18;
  }
  if ( !*a3 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x80D,
      (unsigned int)"avcore\\midi2\\transport\\ksaggregatetransport\\midi2.ksaggregatemidiendpointmanager2.cpp",
      (const char *)0x80070057LL,
      S2);
    v8 = (volatile signed __int32 *)a2[1];
    if ( v8 )
    {
      if ( _InterlockedExchangeAdd(v8 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v8)(v8);
        if ( _InterlockedExchangeAdd(v8 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v8 + 8LL))(v8);
      }
    }
    v7 = (volatile signed __int32 *)a3[1];
    if ( !v7 )
      return 2147942487LL;
    if ( _InterlockedExchangeAdd(v7 + 2, 0xFFFFFFFF) != 1 )
      return 2147942487LL;
    (**(void (__fastcall ***)(volatile signed __int32 *))v7)(v7);
    if ( _InterlockedExchangeAdd(v7 + 3, 0xFFFFFFFF) != 1 )
      return 2147942487LL;
LABEL_18:
    (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v7 + 8LL))(v7);
    return 2147942487LL;
  }
  v10 = (_DWORD *)*((_QWORD *)MidiKSAggregateTransportTelemetryProvider::Instance() + 1);
  if ( *v10 > 4u )
  {
    v12 = (_QWORD *)*a2;
    LODWORD(v58) = (__int64)(*(_QWORD *)(*a2 + 160LL) - *(_QWORD *)(*a2 + 152LL)) >> 4;
    v57 = (__int64)(v12[17] - v12[16]) >> 4;
    v13 = (const char *)(v12 + 8);
    if ( v12[11] > 7u )
      v13 = *(const char **)v13;
    v59 = v13;
    v14 = (const char *)(v12 + 12);
    if ( *((_QWORD *)v14 + 3) > 7u )
      v14 = *(const char **)v14;
    v60 = v14;
    v61 = L"Enter";
    v62 = a1;
    v63 = "CMidi2KSAggregateMidiEndpointManager2::UpdateNewPinDefinitions";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      (_DWORD)v10,
      (unsigned int)byte_180089D95,
      (_DWORD)v10,
      v11,
      (__int64)&v63,
      (__int64)&v62,
      (__int64)&v61,
      (__int64)&v60,
      (__int64)&v59,
      (__int64)&v57,
      (__int64)&v58);
  }
  v105 = 0;
  v106 = 0;
  v15 = *a2;
  v16 = *(_QWORD *)(*a2 + 136LL);
  for ( i = *(_QWORD *)(*a2 + 128LL); i != v16; i += 16 )
  {
    if ( !*(_BYTE *)(*(_QWORD *)i + 144LL) )
      *((_BYTE *)&v105 + *(unsigned __int8 *)(*(_QWORD *)i + 145LL)) = 1;
  }
  v18 = *(_QWORD *)(v15 + 160);
  for ( j = *(_QWORD *)(v15 + 152); j != v18; j += 16 )
  {
    if ( !*(_BYTE *)(*(_QWORD *)j + 144LL) )
      *((_BYTE *)&v106 + *(unsigned __int8 *)(*(_QWORD *)j + 145LL)) = 1;
  }
  KsAggregateEndpointDefinition2::GetAllPins(v15, &v64);
  v20 = v64;
  v21 = v65;
  if ( v64 == v65 )
  {
LABEL_97:
    std::vector<std::shared_ptr<KsAggregateEndpointDefinition2>>::~vector<std::shared_ptr<KsAggregateEndpointDefinition2>>(&v64);
    v50 = (volatile signed __int32 *)a2[1];
    if ( v50 )
    {
      if ( _InterlockedExchangeAdd(v50 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v50)(v50);
        if ( _InterlockedExchangeAdd(v50 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v50 + 8LL))(v50);
      }
    }
    v51 = (volatile signed __int32 *)a3[1];
    if ( v51 )
    {
      if ( _InterlockedExchangeAdd(v51 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v51)(v51);
        if ( _InterlockedExchangeAdd(v51 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v51 + 8LL))(v51);
      }
    }
    return 0;
  }
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  while ( 2 )
  {
    v23 = *v20;
    if ( !*(_BYTE *)(*v20 + 144) )
      goto LABEL_48;
    v24 = 0;
    while ( !*(_DWORD *)(v23 + 140) )
    {
      if ( !*((_BYTE *)&v105 + v24) )
      {
        *((_BYTE *)&v105 + v24) = 1;
        goto LABEL_47;
      }
LABEL_44:
      if ( ++v24 >= 0x10u )
        goto LABEL_48;
    }
    if ( *((_BYTE *)&v106 + v24) )
      goto LABEL_44;
    *((_BYTE *)&v106 + v24) = 1;
LABEL_47:
    *(_BYTE *)(v23 + 145) = v24;
    *(_BYTE *)(*v20 + 144) = 0;
LABEL_48:
    v25 = (_DWORD *)*((_QWORD *)MidiKSAggregateTransportTelemetryProvider::Instance() + 1);
    if ( *v25 > 4u )
    {
      v26 = L"MidiFlowOut";
      if ( *(_DWORD *)(*v20 + 140) != 1 )
        v26 = L"MidiFlowIn";
      v55 = *(_BYTE *)(*v20 + 145);
      v63 = a1;
      v27 = -1;
      do
        ++v27;
      while ( v26[v27] );
      v93 = v26;
      v94 = 2 * v27 + 2;
      v95 = 0;
      v91 = &v55;
      v92 = 1;
      v89 = L"Assigned Group Index to pin";
      v90 = 56;
      v87 = &v63;
      v88 = 8;
      v85 = "CMidi2KSAggregateMidiEndpointManager2::UpdateNewPinDefinitions";
      v86 = 63;
      tlgWriteTransfer_EventWriteTransfer(v25, qword_180089D30, 0, 0, 7, v84);
    }
    if ( *(_BYTE *)(*v20 + 145) <= 0xFu )
    {
      *(_OWORD *)v80 = 0;
      v81 = 0;
      std::wstring::_Construct<1,unsigned short const *>(v80);
      *(_OWORD *)v78 = 0;
      v79 = si128;
      LOWORD(v78[0]) = 0;
      *(_OWORD *)v76 = 0;
      v77 = si128;
      v76[0] = 0;
      *(_OWORD *)v74 = 0;
      v75 = si128;
      v74[0] = 0;
      v28 = *(_DWORD *)(*a3 + 64LL);
      if ( v28 )
      {
        if ( *(_QWORD *)(*v20 + 80) )
        {
          v57 = v28 + 1;
          v66 = L"{1} - {0}";
          v67 = 9;
          v29 = std::format<std::wstring &,unsigned int>(Src);
          std::wstring::operator=(v76, v29);
          std::wstring::~wstring(Src);
        }
        if ( *(_QWORD *)(*v20 + 48) )
        {
          v57 = *(_DWORD *)(*a3 + 64LL) + 1;
          v68 = L"{1} - {0}";
          v69 = 9;
          v30 = std::format<std::wstring &,unsigned int>(Src);
          std::wstring::operator=(v74, v30);
          std::wstring::~wstring(Src);
        }
        v31 = *(_QWORD *)(*v20 + 120);
        if ( v31 )
        {
          v32 = (const wchar_t *)(*v20 + 104);
          if ( *(_QWORD *)(*v20 + 128) > 7u )
            v32 = *(const wchar_t **)v32;
          if ( v31 != 4 || wmemcmp(v32, L"MIDI", 4u) )
          {
            v57 = *(_DWORD *)(*a3 + 64LL) + 1;
            v70 = L"{1} - {0}";
            v71 = 9;
            v33 = std::format<std::wstring &,unsigned int>(v83);
            std::wstring::operator=(v78, v33);
            std::wstring::~wstring(v83);
          }
        }
      }
      else
      {
        std::wstring::operator=(v76, *v20 + 64);
        std::wstring::operator=(v74, *v20 + 32);
        std::wstring::operator=(v78, *v20 + 104);
      }
      v34 = (_DWORD *)*((_QWORD *)MidiKSAggregateTransportTelemetryProvider::Instance() + 1);
      if ( *v34 > 4u )
      {
        v35 = v78;
        if ( v79.m128i_i64[1] > 7uLL )
          v35 = (__int64 *)v78[0];
        v36 = v74;
        if ( v75.m128i_i64[1] > 7uLL )
          v36 = *(wchar_t **)v74;
        v37 = v76;
        if ( v77.m128i_i64[1] > 7uLL )
          v37 = *(wchar_t **)v76;
        v38 = L"MidiFlowOut";
        if ( *(_DWORD *)(*v20 + 140) != 1 )
          v38 = L"MidiFlowIn";
        v56 = *(_BYTE *)(*v20 + 145);
        v62 = a1;
        if ( v35 )
        {
          v39 = -1;
          do
            ++v39;
          while ( *((_WORD *)v35 + v39) );
          v40 = 2 * v39 + 2;
        }
        else
        {
          v35 = (__int64 *)&S1;
          v40 = 2;
        }
        v102 = v35;
        v103 = v40;
        v104 = 0;
        if ( v36 )
        {
          v41 = -1;
          do
            ++v41;
          while ( v36[v41] );
          v42 = 2 * v41 + 2;
        }
        else
        {
          v36 = (wchar_t *)&S1;
          v42 = 2;
        }
        v99 = v36;
        v100 = v42;
        v101 = 0;
        if ( v37 )
        {
          v43 = -1;
          do
            ++v43;
          while ( v37[v43] );
          v44 = 2 * v43 + 2;
        }
        else
        {
          v37 = (wchar_t *)&S1;
          v44 = 2;
        }
        v96 = v37;
        v97 = v44;
        v98 = 0;
        v45 = -1;
        do
          ++v45;
        while ( v38[v45] );
        v93 = v38;
        v94 = 2 * v45 + 2;
        v95 = 0;
        v91 = &v56;
        v92 = 1;
        v89 = L"Setting names";
        v90 = 28;
        v87 = &v62;
        v88 = 8;
        v85 = "CMidi2KSAggregateMidiEndpointManager2::UpdateNewPinDefinitions";
        v86 = 63;
        tlgWriteTransfer_EventWriteTransfer(v34, &word_180089C9E, 0, 0, 10, v84);
      }
      v46 = *v20;
      LOBYTE(v46) = *(_BYTE *)(*v20 + 145);
      WindowsMidiServicesNamingLib::MidiEndpointNameTable::PopulateEntryForMidi1DeviceUsingMidi1Driver(
        *(_DWORD *)a2 + 176,
        v46,
        *(_DWORD *)(*v20 + 140),
        (int)v80,
        v76,
        v74,
        (__int64)v78,
        *(_BYTE *)(*v20 + 146));
      v47 = (_DWORD *)*((_QWORD *)MidiKSAggregateTransportTelemetryProvider::Instance() + 1);
      if ( *v47 > 4u )
      {
        v61 = L"Name table updated";
        v60 = a1;
        v59 = "CMidi2KSAggregateMidiEndpointManager2::UpdateNewPinDefinitions";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>>(
          (_DWORD)v47,
          (unsigned int)byte_180089C69,
          v48,
          v49,
          (__int64)&v59,
          (__int64)&v60,
          (__int64)&v61);
      }
      std::wstring::~wstring(v74);
      std::wstring::~wstring(v76);
      std::wstring::~wstring(v78);
      std::wstring::~wstring(v80);
      v20 += 2;
      if ( v20 == v21 )
        goto LABEL_97;
      continue;
    }
    break;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x862,
    (unsigned int)"avcore\\midi2\\transport\\ksaggregatetransport\\midi2.ksaggregatemidiendpointmanager2.cpp",
    (const char *)0x8000FFFFLL,
    S2);
  std::vector<std::shared_ptr<KsAggregateEndpointDefinition2>>::~vector<std::shared_ptr<KsAggregateEndpointDefinition2>>(&v64);
  v52 = (volatile signed __int32 *)a2[1];
  if ( v52 )
  {
    if ( _InterlockedExchangeAdd(v52 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v52)(v52);
      if ( _InterlockedExchangeAdd(v52 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v52 + 8LL))(v52);
    }
  }
  v53 = (volatile signed __int32 *)a3[1];
  if ( v53 )
  {
    if ( _InterlockedExchangeAdd(v53 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v53)(v53);
      if ( _InterlockedExchangeAdd(v53 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v53 + 8LL))(v53);
    }
  }
  return 2147549183LL;
}

```

## disassembly

```asm
0x18004003c  mov     rax, rsp
0x18004003f  mov     [rax+8], rbx
0x180040043  push    rbp
0x180040044  push    rsi
0x180040045  push    rdi
0x180040046  push    r12
0x180040048  push    r13
0x18004004a  push    r14
0x18004004c  push    r15
0x18004004e  lea     rbp, [rax-1C8h]
0x180040055  sub     rsp, 290h
0x18004005c  movaps  xmmword ptr [rax-48h], xmm6
0x180040060  mov     rax, cs:__security_cookie
0x180040067  xor     rax, rsp
0x18004006a  mov     [rbp+1C0h+var_50], rax
0x180040071  mov     r14, r8
0x180040074  mov     rsi, rdx
0x180040077  mov     r15, rcx
0x18004007a  mov     [rbp+1C0h+var_1E0], rdx
0x18004007e  mov     [rbp+1C0h+var_1D8], r8
0x180040082  xor     r13d, r13d
0x180040085  cmp     [rdx], r13
0x180040088  jnz     loc_180040133
0x18004008e  mov     rcx, [rbp+1C8h]; this
0x180040095  mov     r9d, 80070057h; char *
0x18004009b  lea     r8, aAvcoreMidi2Tra_4; "avcore\\midi2\\transport\\ksaggregatetr"...
0x1800400a2  mov     edx, 80Ch; void *
0x1800400a7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800400ac  nop
0x1800400ad  mov     rdi, [rsi+8]
0x1800400b1  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800400b5  test    rdi, rdi
0x1800400b8  jz      short loc_1800400EE
0x1800400ba  mov     eax, ebx
0x1800400bc  lock xadd [rdi+8], eax
0x1800400c1  add     eax, ebx
0x1800400c3  jnz     short loc_1800400EE
0x1800400c5  mov     rax, [rdi]
0x1800400c8  mov     rcx, rdi
0x1800400cb  mov     rax, [rax]
0x1800400ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800400d3  mov     eax, ebx
0x1800400d5  lock xadd [rdi+0Ch], eax
0x1800400da  add     eax, ebx
0x1800400dc  jnz     short loc_1800400EE
0x1800400de  mov     rax, [rdi]
0x1800400e1  mov     rcx, rdi
0x1800400e4  mov     rax, [rax+8]
0x1800400e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800400ed  nop
0x1800400ee  mov     rdi, [r14+8]
0x1800400f2  test    rdi, rdi
0x1800400f5  jz      loc_1800401D8
0x1800400fb  mov     eax, ebx
0x1800400fd  lock xadd [rdi+8], eax
0x180040102  add     eax, ebx
0x180040104  jnz     loc_1800401D8
0x18004010a  mov     rax, [rdi]
0x18004010d  mov     rcx, rdi
0x180040110  mov     rax, [rax]
0x180040113  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040118  mov     eax, ebx
0x18004011a  lock xadd [rdi+0Ch], eax
0x18004011f  add     eax, ebx
0x180040121  jnz     loc_1800401D8
0x180040127  mov     rax, [rdi]
0x18004012a  mov     rax, [rax+8]
0x18004012e  jmp     loc_1800401D0
0x180040133  cmp     [r8], r13
0x180040136  jnz     loc_1800401E2
0x18004013c  mov     rcx, [rbp+1C8h]; this
0x180040143  mov     r9d, 80070057h; char *
0x180040149  lea     r8, aAvcoreMidi2Tra_4; "avcore\\midi2\\transport\\ksaggregatetr"...
0x180040150  mov     edx, 80Dh; void *
0x180040155  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004015a  nop
0x18004015b  mov     rdi, [rsi+8]
0x18004015f  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180040163  test    rdi, rdi
0x180040166  jz      short loc_18004019C
0x180040168  mov     eax, ebx
0x18004016a  lock xadd [rdi+8], eax
0x18004016f  add     eax, ebx
0x180040171  jnz     short loc_18004019C
0x180040173  mov     rax, [rdi]
0x180040176  mov     rcx, rdi
0x180040179  mov     rax, [rax]
0x18004017c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040181  mov     eax, ebx
0x180040183  lock xadd [rdi+0Ch], eax
0x180040188  add     eax, ebx
0x18004018a  jnz     short loc_18004019C
0x18004018c  mov     rax, [rdi]
0x18004018f  mov     rcx, rdi
0x180040192  mov     rax, [rax+8]
0x180040196  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004019b  nop
0x18004019c  mov     rdi, [r14+8]
0x1800401a0  test    rdi, rdi
0x1800401a3  jz      short loc_1800401D8
0x1800401a5  mov     eax, ebx
0x1800401a7  lock xadd [rdi+8], eax
0x1800401ac  add     eax, ebx
0x1800401ae  jnz     short loc_1800401D8
0x1800401b0  mov     rax, [rdi]
0x1800401b3  mov     rcx, rdi
0x1800401b6  mov     rax, [rax]
0x1800401b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800401be  mov     edx, ebx
0x1800401c0  lock xadd [rdi+0Ch], edx
0x1800401c5  add     edx, ebx
0x1800401c7  jnz     short loc_1800401D8
0x1800401c9  mov     rdx, [rdi]
0x1800401cc  mov     rax, [rdx+8]
0x1800401d0  mov     rcx, rdi
0x1800401d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800401d8  mov     eax, 80070057h
0x1800401dd  jmp     loc_180040991
0x1800401e2  call    ?Instance@MidiKSAggregateTransportTelemetryProvider@@KAPEAV1@XZ; MidiKSAggregateTransportTelemetryProvider::Instance(void)
0x1800401e7  mov     r8, [rax+8]
0x1800401eb  mov     eax, [r8]
0x1800401ee  lea     rdx, aCmidi2ksaggreg_42; "CMidi2KSAggregateMidiEndpointManager2::"...
0x1800401f5  cmp     eax, 4
0x1800401f8  jbe     loc_1800402B8
0x1800401fe  mov     rcx, [rsi]
0x180040201  mov     rax, [rcx+0A0h]
0x180040208  sub     rax, [rcx+98h]
0x18004020f  sar     rax, 4
0x180040213  mov     dword ptr [rsp+2C0h+var_258], eax
0x180040217  mov     rax, [rcx+88h]
0x18004021e  sub     rax, [rcx+80h]
0x180040225  sar     rax, 4
0x180040229  mov     [rsp+2C0h+var_25C], eax
0x18004022d  lea     rax, [rcx+40h]
0x180040231  cmp     qword ptr [rax+18h], 7
0x180040236  jbe     short loc_18004023B
0x180040238  mov     rax, [rax]
0x18004023b  mov     [rsp+2C0h+var_250], rax
0x180040240  add     rcx, 60h ; '`'
0x180040244  cmp     qword ptr [rcx+18h], 7
0x180040249  jbe     short loc_18004024E
0x18004024b  mov     rcx, [rcx]
0x18004024e  mov     [rsp+2C0h+var_248], rcx
0x180040253  lea     rax, aEnter_0; "Enter"
0x18004025a  mov     [rbp+1C0h+var_240], rax
0x18004025e  mov     [rbp+1C0h+var_238], r15
0x180040262  mov     [rbp+1C0h+var_230], rdx
0x180040266  lea     rax, [rsp+2C0h+var_258]
0x18004026b  mov     [rsp+2C0h+var_270], rax
0x180040270  lea     rax, [rsp+2C0h+var_25C]
0x180040275  mov     [rsp+2C0h+var_278], rax
0x18004027a  lea     rax, [rsp+2C0h+var_250]
0x18004027f  mov     [rsp+2C0h+var_280], rax
0x180040284  lea     rax, [rsp+2C0h+var_248]
0x180040289  mov     qword ptr [rsp+2C0h+var_288], rax
0x18004028e  lea     rax, [rbp+1C0h+var_240]
0x180040292  mov     [rsp+2C0h+var_290], rax
0x180040297  lea     rax, [rbp+1C0h+var_238]
0x18004029b  mov     [rsp+2C0h+var_298], rax
0x1800402a0  lea     rax, [rbp+1C0h+var_230]
0x1800402a4  mov     [rsp+2C0h+S2], rax
0x1800402a9  lea     rdx, byte_180089D95
0x1800402b0  mov     rcx, r8
0x1800402b3  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U3@U3@U?$_tlgWrapperByVal@$03@@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@55AEBU?$_tlgWrapperByVal@$03@@6@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800402b8  xorps   xmm0, xmm0
0x1800402bb  movups  [rbp+1C0h+var_70], xmm0
0x1800402c2  xorps   xmm1, xmm1
0x1800402c5  movups  [rbp+1C0h+var_60], xmm1
0x1800402cc  mov     r8, [rsi]
0x1800402cf  mov     rdx, [r8+88h]
0x1800402d6  mov     rcx, [r8+80h]
0x1800402dd  jmp     short loc_1800402FE
0x1800402df  mov     rax, [rcx]
0x1800402e2  cmp     [rax+90h], r13b
0x1800402e9  jnz     short loc_1800402FA
0x1800402eb  movzx   eax, byte ptr [rax+91h]
0x1800402f2  mov     byte ptr [rbp+rax+1C0h+var_70], 1
0x1800402fa  add     rcx, 10h
0x1800402fe  cmp     rcx, rdx
0x180040301  jnz     short loc_1800402DF
0x180040303  mov     rcx, [r8+0A0h]
0x18004030a  mov     rdx, [r8+98h]
0x180040311  jmp     short loc_180040332
0x180040313  mov     rax, [rdx]
0x180040316  cmp     [rax+90h], r13b
0x18004031d  jnz     short loc_18004032E
0x18004031f  movzx   eax, byte ptr [rax+91h]
0x180040326  mov     byte ptr [rbp+rax+1C0h+var_60], 1
0x18004032e  add     rdx, 10h
0x180040332  cmp     rdx, rcx
0x180040335  jnz     short loc_180040313
0x180040337  lea     rdx, [rbp+1C0h+var_228]
0x18004033b  mov     rcx, r8
0x18004033e  call    ?GetAllPins@KsAggregateEndpointDefinition2@@QEAA?AV?$vector@V?$shared_ptr@UKsAggregateEndpointMidiPinDefinition2@@@std@@V?$allocator@V?$shared_ptr@UKsAggregateEndpointMidiPinDefinition2@@@std@@@2@@std@@XZ; KsAggregateEndpointDefinition2::GetAllPins(void)
0x180040343  nop
0x180040344  mov     rdi, [rbp+1C0h+var_228]
0x180040348  mov     r12, [rbp+1C0h+var_220]
0x18004034c  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180040350  cmp     rdi, r12
0x180040353  jz      loc_18004090C
0x180040359  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x180040361  mov     rdx, [rdi]
0x180040364  cmp     [rdx+90h], r13b
0x18004036b  jz      short loc_1800403BA
0x18004036d  mov     al, r13b
0x180040370  movzx   ecx, al
0x180040373  cmp     [rdx+8Ch], r13d
0x18004037a  jnz     short loc_180040390
0x18004037c  cmp     byte ptr [rbp+rcx+1C0h+var_70], r13b
0x180040384  jnz     short loc_18004039A
0x180040386  mov     byte ptr [rbp+rcx+1C0h+var_70], 1
0x18004038e  jmp     short loc_1800403AA
0x180040390  cmp     byte ptr [rbp+rcx+1C0h+var_60], r13b
0x180040398  jz      short loc_1800403A2
0x18004039a  inc     al
0x18004039c  cmp     al, 10h
0x18004039e  jb      short loc_180040370
0x1800403a0  jmp     short loc_1800403BA
0x1800403a2  mov     byte ptr [rbp+rcx+1C0h+var_60], 1
0x1800403aa  mov     [rdx+91h], al
0x1800403b0  mov     rax, [rdi]
0x1800403b3  mov     [rax+90h], r13b
0x1800403ba  call    ?Instance@MidiKSAggregateTransportTelemetryProvider@@KAPEAV1@XZ; MidiKSAggregateTransportTelemetryProvider::Instance(void)
0x1800403bf  mov     r10, [rax+8]
0x1800403c3  mov     eax, [r10]
0x1800403c6  cmp     eax, 4
0x1800403c9  jbe     loc_1800404A9
0x1800403cf  mov     rax, [rdi]
0x1800403d2  lea     rcx, aMidiflowout; "MidiFlowOut"
0x1800403d9  cmp     dword ptr [rax+8Ch], 1
0x1800403e0  lea     rdx, aMidiflowin; "MidiFlowIn"
0x1800403e7  cmovnz  rcx, rdx
0x1800403eb  mov     al, [rax+91h]
0x1800403f1  mov     byte ptr [rsp+2C0h+var_260], al
0x1800403f5  mov     [rbp+1C0h+var_230], r15
0x1800403f9  mov     rax, rbx
0x1800403fc  inc     rax
0x1800403ff  cmp     [rcx+rax*2], r13w
0x180040404  jnz     short loc_1800403FC
0x180040406  mov     [rbp+1C0h+var_B0], rcx
0x18004040d  lea     eax, ds:2[rax*2]
0x180040414  mov     [rbp+1C0h+var_A8], eax
0x18004041a  mov     [rbp+1C0h+var_A4], r13d
0x180040421  lea     rax, [rsp+2C0h+var_260]
0x180040426  mov     [rbp+1C0h+var_C0], rax
0x18004042d  mov     [rbp+1C0h+var_B8], 1
0x180040438  lea     rax, aAssignedGroupI; "Assigned Group Index to pin"
0x18004043f  mov     [rbp+1C0h+var_D0], rax
0x180040446  mov     [rbp+1C0h+var_C8], 38h ; '8'
0x180040451  lea     rax, [rbp+1C0h+var_230]
0x180040455  mov     [rbp+1C0h+var_E0], rax
0x18004045c  mov     [rbp+1C0h+var_D8], 8
0x180040467  lea     rax, aCmidi2ksaggreg_42; "CMidi2KSAggregateMidiEndpointManager2::"...
0x18004046e  mov     [rbp+1C0h+var_F0], rax
0x180040475  mov     [rbp+1C0h+var_E8], 3Fh ; '?'
0x180040480  lea     rax, [rbp+1C0h+var_110]
0x180040487  mov     [rsp+2C0h+var_298], rax
0x18004048c  mov     dword ptr [rsp+2C0h+S2], 7; int
0x180040494  xor     r9d, r9d
0x180040497  xor     r8d, r8d
0x18004049a  lea     rdx, qword_180089D30
0x1800404a1  mov     rcx, r10
0x1800404a4  call    _tlgWriteTransfer_EventWriteTransfer
0x1800404a9  mov     rax, [rdi]
0x1800404ac  cmp     byte ptr [rax+91h], 0Fh
0x1800404b3  ja      loc_1800409C0
0x1800404b9  xorps   xmm0, xmm0
0x1800404bc  movups  xmmword ptr [rbp+1C0h+var_170], xmm0
0x1800404c0  xorps   xmm1, xmm1
0x1800404c3  movdqu  [rbp+1C0h+var_160], xmm1
0x1800404c8  xor     r8d, r8d
0x1800404cb  lea     rdx, S1
0x1800404d2  lea     rcx, [rbp+1C0h+var_170]
0x1800404d6  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800404db  nop
0x1800404dc  xorps   xmm0, xmm0
0x1800404df  movups  xmmword ptr [rbp+1C0h+var_190], xmm0
0x1800404e3  movdqu  [rbp+1C0h+var_180], xmm6
0x1800404e8  mov     word ptr [rbp+1C0h+var_190], r13w
0x1800404ed  movups  xmmword ptr [rbp+1C0h+var_1B0], xmm0
0x1800404f1  movdqu  [rbp+1C0h+var_1A0], xmm6
0x1800404f6  mov     [rbp+1C0h+var_1B0], r13w
0x1800404fb  movups  xmmword ptr [rbp+1C0h+var_1D0], xmm0
0x1800404ff  movdqu  [rbp+1C0h+var_1C0], xmm6
0x180040504  mov     [rbp+1C0h+var_1D0], r13w
0x180040509  mov     rax, [r14]
0x18004050c  mov     ecx, [rax+40h]
0x18004050f  mov     rdx, [rdi]
0x180040512  add     rdx, 40h ; '@'
0x180040516  test    ecx, ecx
0x180040518  jz      loc_180040647
0x18004051e  cmp     [rdx+10h], r13
0x180040522  jz      short loc_180040568
0x180040524  lea     eax, [rcx+1]
0x180040527  mov     [rsp+2C0h+var_25C], eax
0x18004052b  lea     rax, a10; "{1} - {0}"
0x180040532  mov     [rbp+1C0h+var_210], rax
0x180040536  mov     [rbp+1C0h+var_208], 9
0x18004053e  lea     r9, [rsp+2C0h+var_25C]
0x180040543  mov     r8, rdx
  ... truncated ...
```
