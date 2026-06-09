# CMidi2KSAggregateMidiEndpointManager2::BuildPinsAndGroupTerminalBlocksPropertyData(std::shared_ptr<KsAggregateEndpointDefinition2>,std::vector<std::byte,std::allocator<std::byte>> &,std::vector<WindowsMidiServicesInternal::GroupTerminalBlockInternal,std::allocator<WindowsMidiServicesInternal::GroupTerminalBlockInternal>> &)

- ea: `0x180035c78`
- end: `0x1800365df`
- name: `?BuildPinsAndGroupTerminalBlocksPropertyData@CMidi2KSAggregateMidiEndpointManager2@@AEAAJV?$shared_ptr@UKsAggregateEndpointDefinition2@@@std@@AEAV?$vector@W4byte@std@@V?$allocator@W4byte@std@@@2@@3@AEAV?$vector@UGroupTerminalBlockInternal@WindowsMidiServicesInternal@@V?$allocator@UGroupTerminalBlockInternal@WindowsMidiServicesInternal@@@std@@@3@@Z`
- size: `2407`
- prototype: ``
- caller_count: `2`
- callee_count: `25`
- tags: `service_task`

## callers

- `0x180036d5c`
- `0x180037fec`

## callees

- `0x18000163c`
- `0x1800017d0`
- `0x180005020`
- `0x180005e90`
- `0x180005e9c`
- `0x18000b394`
- `0x18000d430`
- `0x18000d7d8`
- `0x1800117d8`
- `0x180013118`
- `0x180013638`
- `0x180014194`
- `0x18001aa6c`
- `0x18001b258`
- `0x180020104`
- `0x180020604`
- `0x180020d3c`
- `0x1800224f8`
- `0x1800229bc`
- `0x18002fbd8`
- `0x180035c78`
- `0x18003b038`
- `0x1800561e4`
- `0x180056268`
- `0x18005e010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x1800364d4`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x1800364d4`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall CMidi2KSAggregateMidiEndpointManager2::BuildPinsAndGroupTerminalBlocksPropertyData(
        const char *a1,
        _QWORD *a2,
        __int64 a3,
        __int64 a4)
{
  __int64 v7; // rcx
  volatile signed __int32 *v8; // rbx
  char v9; // bl
  const char *v10; // r12
  const char *v11; // rdi
  __m128i si128; // xmm6
  __int64 v13; // rdx
  __int64 v14; // rcx
  int v15; // eax
  __int64 v16; // r8
  __int64 v17; // rax
  volatile signed __int32 *v18; // rbx
  __int64 v19; // r8
  __int64 v20; // rax
  __int64 v21; // rax
  __int128 *v22; // xmm0_8
  __m128i v23; // xmm1
  __int128 *v24; // r9
  __int64 v25; // rcx
  __int64 v26; // rdi
  __int128 *p_Src; // rbx
  __int64 v28; // rdx
  __int64 v29; // rdx
  _DWORD *v31; // rcx
  int v32; // r8d
  int v33; // r9d
  const char *v34; // rax
  __int64 v35; // r8
  __int64 i; // rdx
  unsigned __int64 v37; // rdi
  _DWORD *v38; // rdx
  unsigned __int64 v39; // rcx
  __int64 v40; // rbx
  _DWORD *v41; // rax
  unsigned int *v42; // rdi
  __int64 j; // rbx
  __int64 v44; // r13
  _DWORD *v45; // r10
  const wchar_t **v46; // r15
  const wchar_t *v47; // rcx
  const wchar_t *v48; // rax
  __int64 v49; // rdx
  int v50; // edx
  __int64 v51; // rcx
  int v52; // ecx
  __int64 v53; // rdx
  _DWORD *v54; // rcx
  int v55; // r8d
  int v56; // r9d
  const char *v57; // rax
  volatile signed __int32 *v58; // rbx
  int v59; // [rsp+28h] [rbp-E0h]
  __int64 v60; // [rsp+48h] [rbp-C0h] BYREF
  const char *v61; // [rsp+50h] [rbp-B8h] BYREF
  const char *v62; // [rsp+58h] [rbp-B0h] BYREF
  const wchar_t *v63; // [rsp+60h] [rbp-A8h] BYREF
  const char *v64; // [rsp+68h] [rbp-A0h] BYREF
  __int128 v65; // [rsp+70h] [rbp-98h] BYREF
  __int64 v66; // [rsp+80h] [rbp-88h]
  _QWORD v67[2]; // [rsp+88h] [rbp-80h] BYREF
  const char *v68; // [rsp+98h] [rbp-70h] BYREF
  const char *v69; // [rsp+A0h] [rbp-68h]
  _QWORD v70[3]; // [rsp+B0h] [rbp-58h] BYREF
  char v71; // [rsp+C8h] [rbp-40h] BYREF
  int v72; // [rsp+C9h] [rbp-3Fh]
  int v73; // [rsp+CEh] [rbp-3Ah]
  __int128 Src; // [rsp+D8h] [rbp-30h] BYREF
  __int64 v75; // [rsp+E8h] [rbp-20h]
  unsigned __int64 v76; // [rsp+F0h] [rbp-18h]
  __int128 v77; // [rsp+F8h] [rbp-10h] BYREF
  __int128 v78; // [rsp+108h] [rbp+0h]
  __int128 v79; // [rsp+118h] [rbp+10h] BYREF
  _OWORD v80[2]; // [rsp+128h] [rbp+20h] BYREF
  __int128 v81; // [rsp+148h] [rbp+40h] BYREF
  __m128i v82; // [rsp+158h] [rbp+50h]
  struct _EVENT_DATA_DESCRIPTOR v83; // [rsp+168h] [rbp+60h] BYREF
  const char *v84; // [rsp+188h] [rbp+80h]
  __int64 v85; // [rsp+190h] [rbp+88h]
  const char **v86; // [rsp+198h] [rbp+90h]
  __int64 v87; // [rsp+1A0h] [rbp+98h]
  const wchar_t *v88; // [rsp+1A8h] [rbp+A0h]
  __int64 v89; // [rsp+1B0h] [rbp+A8h]
  const wchar_t *v90; // [rsp+1B8h] [rbp+B0h]
  int v91; // [rsp+1C0h] [rbp+B8h]
  int v92; // [rsp+1C4h] [rbp+BCh]
  const char **v93; // [rsp+1C8h] [rbp+C0h]
  __int64 v94; // [rsp+1D0h] [rbp+C8h]
  __int64 *v95; // [rsp+1D8h] [rbp+D0h]
  __int64 v96; // [rsp+1E0h] [rbp+D8h]
  const wchar_t **v97; // [rsp+1E8h] [rbp+E0h]
  __int64 v98; // [rsp+1F0h] [rbp+E8h]
  const wchar_t *v99; // [rsp+1F8h] [rbp+F0h]
  int v100; // [rsp+200h] [rbp+F8h]
  int v101; // [rsp+204h] [rbp+FCh]
  wil::details::in1diag3 *retaddr; // [rsp+260h] [rbp+158h]

  v64 = a1;
  v70[2] = a2;
  v7 = *a2;
  if ( !*a2 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xCB,
      (unsigned int)"avcore\\midi2\\transport\\ksaggregatetransport\\midi2.ksaggregatemidiendpointmanager2.cpp",
      (const char *)0x80070057LL,
      v59);
    v8 = (volatile signed __int32 *)a2[1];
    if ( !v8 )
      return 2147942487LL;
LABEL_3:
    if ( _InterlockedExchangeAdd(v8 + 2, 0xFFFFFFFF) != 1 )
      return 2147942487LL;
    (**(void (__fastcall ***)(volatile signed __int32 *))v8)(v8);
    if ( _InterlockedExchangeAdd(v8 + 3, 0xFFFFFFFF) != 1 )
      return 2147942487LL;
LABEL_50:
    (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v8 + 8LL))(v8);
    return 2147942487LL;
  }
  v9 = 0;
  v65 = 0;
  v66 = 0;
  KsAggregateEndpointDefinition2::GetAllPins(v7, &v68);
  v10 = v68;
  v11 = v69;
  v61 = v69;
  if ( v68 != v69 )
  {
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    while ( 1 )
    {
      v13 = *(_QWORD *)v10;
      if ( !*(_QWORD *)(*(_QWORD *)v10 + 16LL) )
        break;
      v72 = 0x10000;
      v73 = 0;
      Src = 0;
      v75 = 0;
      v76 = 7;
      LOWORD(Src) = 0;
      LOBYTE(v60) = v9 + 1;
      v71 = v9 + 1;
      v79 = 0;
      v80[0] = 0;
      v80[1] = si128;
      LOWORD(v80[0]) = 0;
      DWORD1(v79) = *(_DWORD *)(v13 + 96);
      std::wstring::operator=(v80, v13);
      v14 = *(_QWORD *)v10;
      DWORD2(v79) = *(_DWORD *)(*(_QWORD *)v10 + 136LL);
      LOBYTE(v79) = *(_BYTE *)(v14 + 145);
      BYTE1(v72) = *(_BYTE *)(v14 + 145);
      v15 = *(_DWORD *)(v14 + 136);
      if ( v15 )
      {
        if ( v15 != 1 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xF9,
            (unsigned int)"avcore\\midi2\\transport\\ksaggregatetransport\\midi2.ksaggregatemidiendpointmanager2.cpp",
            (const char *)0x80070057LL,
            v59);
          std::wstring::~wstring(v80);
          std::wstring::~wstring(&Src);
          std::vector<std::shared_ptr<KsAggregateEndpointDefinition2>>::~vector<std::shared_ptr<KsAggregateEndpointDefinition2>>(&v68);
          std::vector<PinMapEntryStagingEntry>::~vector<PinMapEntryStagingEntry>(&v65);
          v8 = (volatile signed __int32 *)a2[1];
          if ( !v8 )
            return 2147942487LL;
          goto LABEL_3;
        }
        LOBYTE(v72) = 2;
        WindowsMidiServicesNamingLib::MidiEndpointNameTable::GetSourceEntry(*a2 + 176LL, v70);
        if ( v70[0] && *(_WORD *)(v70[0] + 136LL) )
        {
          v77 = 0;
          v78 = 0u;
          v19 = -1;
          do
            ++v19;
          while ( *(_WORD *)(v70[0] + 136LL + 2 * v19) );
          std::wstring::_Construct<1,unsigned short const *>(&v77);
          v20 = WindowsMidiServicesInternal::TrimmedWStringCopy(&v81, &v77);
          std::wstring::operator=(&Src, v20);
          std::wstring::~wstring(&v81);
        }
        v18 = (volatile signed __int32 *)v70[1];
      }
      else
      {
        LOBYTE(v72) = 1;
        WindowsMidiServicesNamingLib::MidiEndpointNameTable::GetDestinationEntry(*a2 + 176LL, v67);
        if ( v67[0] && *(_WORD *)(v67[0] + 136LL) )
        {
          v77 = 0;
          v78 = 0u;
          v16 = -1;
          do
            ++v16;
          while ( *(_WORD *)(v67[0] + 136LL + 2 * v16) );
          std::wstring::_Construct<1,unsigned short const *>(&v77);
          v17 = WindowsMidiServicesInternal::TrimmedWStringCopy(&v81, &v77);
          std::wstring::operator=(&Src, v17);
          std::wstring::~wstring(&v81);
        }
        v18 = (volatile signed __int32 *)v67[1];
      }
      if ( v18 )
      {
        if ( _InterlockedExchangeAdd(v18 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v18)(v18);
          if ( _InterlockedExchangeAdd(v18 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v18 + 8LL))(v18);
        }
      }
      if ( !v75 )
      {
        std::wstring::operator=(&Src, *a2 + 64LL);
        if ( BYTE1(v72) )
        {
          LOWORD(v63) = BYTE1(v72);
          v77 = 0;
          v78 = 0;
          std::wstring::_Construct<1,unsigned short const *>(&v77);
          v21 = std::wstring::_Insert<unsigned short>(&v77);
          v81 = *(_OWORD *)v21;
          v22 = (__int128 *)v81;
          v82 = *(__m128i *)(v21 + 16);
          v23 = v82;
          *(_WORD *)v21 = 0;
          *(_QWORD *)(v21 + 16) = 0;
          *(_QWORD *)(v21 + 24) = 7;
          v24 = &v81;
          if ( _mm_srli_si128(v23, 8).m128i_u64[0] > 7 )
            v24 = v22;
          v25 = v75;
          if ( v23.m128i_i64[0] > v76 - v75 )
          {
            ____Reallocate_grow_by_V_lambda_1___1_____Append_G___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV23_QEBG_K_Z_PEBG_K___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV01__KV_lambda_1___1_____Append_G_01_AEAAAEAV01_QEBG0_Z_PEBG_K_Z(
              &Src,
              v23.m128i_i64[0]);
          }
          else
          {
            v26 = v23.m128i_i64[0] + v75;
            v75 += v23.m128i_i64[0];
            p_Src = &Src;
            if ( v76 > 7 )
              p_Src = (__int128 *)Src;
            memmove_0((char *)p_Src + 2 * v25, v24, 2 * v23.m128i_i64[0]);
            *((_WORD *)p_Src + v26) = 0;
            v11 = v61;
          }
          std::wstring::~wstring(&v81);
          std::wstring::~wstring(&v77);
        }
      }
      HIBYTE(v72) = 1;
      v73 = 65537;
      v28 = *(_QWORD *)(a4 + 8);
      if ( v28 == *(_QWORD *)(a4 + 16) )
      {
        std::vector<WindowsMidiServicesInternal::GroupTerminalBlockInternal>::_Emplace_reallocate<WindowsMidiServicesInternal::GroupTerminalBlockInternal const &>(
          a4,
          v28,
          &v71);
      }
      else
      {
        *(_BYTE *)v28 = v71;
        *(_DWORD *)(v28 + 1) = v72;
        *(_DWORD *)(v28 + 6) = v73;
        std::wstring::wstring(v28 + 16, &Src);
        *(_QWORD *)(a4 + 8) += 48LL;
      }
      v29 = *((_QWORD *)&v65 + 1);
      if ( *((_QWORD *)&v65 + 1) == v66 )
      {
        std::vector<PinMapEntryStagingEntry>::_Emplace_reallocate<PinMapEntryStagingEntry const &>(
          &v65,
          *((_QWORD *)&v65 + 1),
          &v79);
      }
      else
      {
        **((_BYTE **)&v65 + 1) = v79;
        *(_QWORD *)(v29 + 4) = *(_QWORD *)((char *)&v79 + 4);
        std::wstring::wstring(v29 + 16, v80);
        *((_QWORD *)&v65 + 1) += 48LL;
      }
      std::wstring::~wstring(v80);
      std::wstring::~wstring(&Src);
      v10 += 16;
      if ( v10 == v11 )
        goto LABEL_52;
      v9 = v60;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD2,
      (unsigned int)"avcore\\midi2\\transport\\ksaggregatetransport\\midi2.ksaggregatemidiendpointmanager2.cpp",
      (const char *)0x80070057LL,
      v59);
    std::vector<std::shared_ptr<KsAggregateEndpointDefinition2>>::~vector<std::shared_ptr<KsAggregateEndpointDefinition2>>(&v68);
    std::vector<PinMapEntryStagingEntry>::~vector<PinMapEntryStagingEntry>(&v65);
    v8 = (volatile signed __int32 *)a2[1];
    if ( !v8 )
      return 2147942487LL;
    if ( _InterlockedExchangeAdd(v8 + 2, 0xFFFFFFFF) != 1 )
      return 2147942487LL;
    (**(void (__fastcall ***)(volatile signed __int32 *))v8)(v8);
    if ( _InterlockedExchangeAdd(v8 + 3, 0xFFFFFFFF) != 1 )
      return 2147942487LL;
    goto LABEL_50;
  }
LABEL_52:
  std::vector<std::shared_ptr<KsAggregateEndpointDefinition2>>::~vector<std::shared_ptr<KsAggregateEndpointDefinition2>>(&v68);
  v31 = (_DWORD *)*((_QWORD *)MidiKSAggregateTransportTelemetryProvider::Instance() + 1);
  if ( *v31 > 4u )
  {
    v34 = (const char *)(*a2 + 64LL);
    if ( *(_QWORD *)(*a2 + 88LL) > 7u )
      v34 = *(const char **)v34;
    v61 = v34;
    v63 = L"Building pin map property";
    v67[0] = v64;
    v62 = "CMidi2KSAggregateMidiEndpointManager2::BuildPinsAndGroupTerminalBlocksPropertyData";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
      (_DWORD)v31,
      (unsigned int)qword_18008ABD0,
      v32,
      v33,
      (__int64)&v62,
      (__int64)v67,
      (__int64)&v63,
      (__int64)&v61);
  }
  v35 = 0;
  for ( i = v65; i != *((_QWORD *)&v65 + 1); i += 48 )
    v35 += 2LL * *(_QWORD *)(i + 32) + 2;
  v37 = v35
      + 2
      * (0xAAAAAAAAAAAAAAABuLL * ((__int64)(*((_QWORD *)&v65 + 1) - v65) >> 4)
       + 0x5555555555555558LL * ((__int64)(*((_QWORD *)&v65 + 1) - v65) >> 4)
       + 2);
  v38 = *(_DWORD **)a3;
  v39 = *(_QWORD *)(a3 + 8) - *(_QWORD *)a3;
  if ( v37 >= v39 )
  {
    if ( v37 > v39 )
    {
      if ( v37 <= *(_QWORD *)(a3 + 16) - (_QWORD)v38 )
      {
        v40 = v37 - v39 + *(_QWORD *)(a3 + 8);
        memset_0(*(void **)(a3 + 8), 0, v37 - v39);
        *(_QWORD *)(a3 + 8) = v40;
      }
      else
      {
        std::vector<unsigned char>::_Resize_reallocate<std::_Value_init_tag>(a3, v37);
      }
    }
  }
  else
  {
    *(_QWORD *)(a3 + 8) = (char *)v38 + v37;
  }
  v41 = *(_DWORD **)a3;
  *v41 = v37;
  v42 = v41 + 1;
  v44 = *((_QWORD *)&v65 + 1);
  for ( j = v65; j != v44; j += 48 )
  {
    v45 = (_DWORD *)*((_QWORD *)MidiKSAggregateTransportTelemetryProvider::Instance() + 1);
    v46 = (const wchar_t **)(j + 16);
    if ( *v45 > 4u )
    {
      if ( *(_QWORD *)(j + 40) <= 7u )
        v47 = (const wchar_t *)(j + 16);
      else
        v47 = *v46;
      LODWORD(v63) = *(_DWORD *)(j + 8);
      LOBYTE(v60) = *(_BYTE *)j;
      LODWORD(v61) = *(_DWORD *)(j + 4);
      v48 = (const wchar_t *)(*a2 + 64LL);
      if ( *(_QWORD *)(*a2 + 88LL) > 7u )
        v48 = *(const wchar_t **)v48;
      v62 = v64;
      if ( v47 )
      {
        v49 = -1;
        do
          ++v49;
        while ( v47[v49] );
        v50 = 2 * v49 + 2;
      }
      else
      {
        v47 = &S1;
        v50 = 2;
      }
      v99 = v47;
      v100 = v50;
      v101 = 0;
      v97 = &v63;
      v98 = 4;
      v95 = &v60;
      v96 = 1;
      v93 = &v61;
      v94 = 4;
      if ( v48 )
      {
        v51 = -1;
        do
          ++v51;
        while ( v48[v51] );
        v52 = 2 * v51 + 2;
      }
      else
      {
        v48 = &S1;
        v52 = 2;
      }
      v90 = v48;
      v91 = v52;
      v92 = 0;
      v88 = L"Processing Pin Map entry";
      v89 = 50;
      v86 = &v62;
      v87 = 8;
      v84 = "CMidi2KSAggregateMidiEndpointManager2::BuildPinsAndGroupTerminalBlocksPropertyData";
      v85 = 83;
      tlgWriteTransfer_EventWriteTransfer((__int64)v45, (unsigned __int8 *)byte_18008AB69, 0, 0, 0xAu, &v83);
    }
    *v42 = 2 * *(_DWORD *)(j + 32) + 20;
    *((_BYTE *)v42 + 4) = *(_BYTE *)j;
    v42[3] = *(_DWORD *)(j + 8);
    v42[2] = *(_DWORD *)(j + 4);
    v53 = *(_QWORD *)(j + 32);
    if ( v53 )
    {
      if ( *(_QWORD *)(j + 40) > 7u )
        v46 = (const wchar_t **)*v46;
      _o_wcscpy_s(v42 + 4, v53 + 1, v46);
    }
    v42 = (unsigned int *)((char *)v42 + *v42);
  }
  v54 = (_DWORD *)*((_QWORD *)MidiKSAggregateTransportTelemetryProvider::Instance() + 1);
  if ( *v54 > 4u )
  {
    v57 = (const char *)(*a2 + 64LL);
    if ( *(_QWORD *)(*a2 + 88LL) > 7u )
      v57 = *(const char **)v57;
    v62 = v57;
    v67[0] = L"All pin map entries copied to property memory";
    v61 = "CMidi2KSAggregateMidiEndpointManager2::BuildPinsAndGroupTerminalBlocksPropertyData";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
      (_DWORD)v54,
      (unsigned int)byte_18008AB31,
      v55,
      v56,
      (__int64)&v61,
      (__int64)&v64,
      (__int64)v67,
      (__int64)&v62);
  }
  std::vector<PinMapEntryStagingEntry>::~vector<PinMapEntryStagingEntry>(&v65);
  v58 = (volatile signed __int32 *)a2[1];
  if ( v58 )
  {
    if ( _InterlockedExchangeAdd(v58 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v58)(v58);
      if ( _InterlockedExchangeAdd(v58 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v58 + 8LL))(v58);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180035c78  mov     rax, rsp
0x180035c7b  mov     [rax+8], rbx
0x180035c7f  push    rbp
0x180035c80  push    rsi
0x180035c81  push    rdi
0x180035c82  push    r12
0x180035c84  push    r13
0x180035c86  push    r14
0x180035c88  push    r15
0x180035c8a  lea     rbp, [rax-158h]
0x180035c91  sub     rsp, 220h
0x180035c98  movaps  xmmword ptr [rax-48h], xmm6
0x180035c9c  mov     rax, cs:__security_cookie
0x180035ca3  xor     rax, rsp
0x180035ca6  mov     [rbp+150h+var_50], rax
0x180035cad  mov     r13, r9
0x180035cb0  mov     r15, r8
0x180035cb3  mov     r14, rdx
0x180035cb6  mov     qword ptr [rsp+250h+var_1F0], rcx
0x180035cbb  mov     [rbp+150h+var_198], rdx
0x180035cbf  xor     edi, edi
0x180035cc1  mov     rcx, [rdx]
0x180035cc4  test    rcx, rcx
0x180035cc7  jnz     short loc_180035D31
0x180035cc9  mov     rcx, [rbp+158h]; this
0x180035cd0  mov     r9d, 80070057h; char *
0x180035cd6  lea     r8, aAvcoreMidi2Tra_4; "avcore\\midi2\\transport\\ksaggregatetr"...
0x180035cdd  mov     edx, 0CBh; void *
0x180035ce2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180035ce7  nop
0x180035ce8  mov     rbx, [r14+8]
0x180035cec  test    rbx, rbx
0x180035cef  jz      loc_1800361D9
0x180035cf5  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180035cf9  mov     eax, esi
0x180035cfb  lock xadd [rbx+8], eax
0x180035d00  add     eax, esi
0x180035d02  jnz     loc_1800361D9
0x180035d08  mov     rax, [rbx]
0x180035d0b  mov     rcx, rbx
0x180035d0e  mov     rax, [rax]
0x180035d11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035d16  mov     eax, esi
0x180035d18  lock xadd [rbx+0Ch], eax
0x180035d1d  add     eax, esi
0x180035d1f  jnz     loc_1800361D9
0x180035d25  mov     rax, [rbx]
0x180035d28  mov     rax, [rax+8]
0x180035d2c  jmp     loc_1800361D1
0x180035d31  mov     bl, dil
0x180035d34  xorps   xmm0, xmm0
0x180035d37  movdqu  [rsp+250h+var_1F0+8], xmm0
0x180035d3d  mov     [rsp+250h+var_1D8], rdi
0x180035d42  lea     rdx, [rbp+150h+var_1C0]
0x180035d46  call    ?GetAllPins@KsAggregateEndpointDefinition2@@QEAA?AV?$vector@V?$shared_ptr@UKsAggregateEndpointMidiPinDefinition2@@@std@@V?$allocator@V?$shared_ptr@UKsAggregateEndpointMidiPinDefinition2@@@std@@@2@@std@@XZ; KsAggregateEndpointDefinition2::GetAllPins(void)
0x180035d4b  nop
0x180035d4c  mov     r12, [rbp+150h+var_1C0]
0x180035d50  mov     rdi, [rbp+150h+var_1B8]
0x180035d54  mov     [rsp+250h+var_208], rdi
0x180035d59  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180035d5d  lea     r8d, [rsi+2]
0x180035d61  cmp     r12, rdi
0x180035d64  jz      loc_1800361E3
0x180035d6a  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x180035d72  mov     rdx, [r12]
0x180035d76  xor     ecx, ecx
0x180035d78  cmp     [rdx+10h], rcx
0x180035d7c  jz      loc_180036169
0x180035d82  mov     [rbp+150h+var_18F], 10000h
0x180035d89  mov     [rbp+150h+var_18A], ecx
0x180035d8c  xorps   xmm0, xmm0
0x180035d8f  movups  [rbp+150h+Src], xmm0
0x180035d93  mov     [rbp+150h+var_170], rcx
0x180035d97  mov     [rbp+150h+var_168], 7
0x180035d9f  mov     word ptr [rbp+150h+Src], cx
0x180035da3  add     bl, r8b
0x180035da6  mov     byte ptr [rsp+250h+var_210], bl
0x180035daa  mov     [rbp+150h+var_190], bl
0x180035dad  movups  [rbp+150h+var_140], xmm0
0x180035db1  xorps   xmm1, xmm1
0x180035db4  movups  [rbp+150h+var_130], xmm1
0x180035db8  movdqu  [rbp+150h+var_120], xmm6
0x180035dbd  xor     ebx, ebx
0x180035dbf  mov     word ptr [rbp+150h+var_130], bx
0x180035dc3  mov     eax, [rdx+60h]
0x180035dc6  mov     dword ptr [rbp+150h+var_140+4], eax
0x180035dc9  lea     rcx, [rbp+150h+var_130]
0x180035dcd  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x180035dd2  mov     rcx, [r12]
0x180035dd6  mov     eax, [rcx+88h]
0x180035ddc  mov     dword ptr [rbp+150h+var_140+8], eax
0x180035ddf  mov     al, [rcx+91h]
0x180035de5  mov     byte ptr [rbp+150h+var_140], al
0x180035de8  mov     r8b, [rcx+91h]
0x180035def  mov     byte ptr [rbp+150h+var_18F+1], r8b
0x180035df3  mov     eax, [rcx+88h]
0x180035df9  test    eax, eax
0x180035dfb  jnz     short loc_180035E7B
0x180035dfd  mov     byte ptr [rbp+150h+var_18F], 1
0x180035e01  mov     rcx, [r14]
0x180035e04  add     rcx, 0B0h
0x180035e0b  lea     rdx, [rbp+150h+var_1D0]
0x180035e0f  call    ?GetDestinationEntry@MidiEndpointNameTable@WindowsMidiServicesNamingLib@@QEBA?AV?$shared_ptr@UMidi1PortNameEntry@WindowsMidiServicesNamingLib@@@std@@E@Z; WindowsMidiServicesNamingLib::MidiEndpointNameTable::GetDestinationEntry(uchar)
0x180035e14  nop
0x180035e15  mov     rdx, [rbp+150h+var_1D0]
0x180035e19  test    rdx, rdx
0x180035e1c  jz      short loc_180035E72
0x180035e1e  add     rdx, 88h
0x180035e25  cmp     [rdx], bx
0x180035e28  jz      short loc_180035E72
0x180035e2a  xorps   xmm0, xmm0
0x180035e2d  movups  [rbp+150h+var_160], xmm0
0x180035e31  mov     qword ptr [rbp+150h+var_150], rbx
0x180035e35  mov     qword ptr [rbp+150h+var_150+8], rbx
0x180035e39  mov     r8, rsi
0x180035e3c  inc     r8
0x180035e3f  cmp     [rdx+r8*2], bx
0x180035e44  jnz     short loc_180035E3C
0x180035e46  lea     rcx, [rbp+150h+var_160]
0x180035e4a  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180035e4f  lea     rdx, [rbp+150h+var_160]; void *
0x180035e53  lea     rcx, [rbp+150h+var_110]; Src
0x180035e57  call    ?TrimmedWStringCopy@WindowsMidiServicesInternal@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V23@@Z; WindowsMidiServicesInternal::TrimmedWStringCopy(std::wstring)
0x180035e5c  mov     rdx, rax
0x180035e5f  lea     rcx, [rbp+150h+Src]
0x180035e63  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180035e68  lea     rcx, [rbp+150h+var_110]; void *
0x180035e6c  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180035e71  nop
0x180035e72  mov     rbx, [rbp+150h+var_1C8]
0x180035e76  jmp     loc_180035EFD
0x180035e7b  cmp     eax, 1
0x180035e7e  jnz     loc_180036113
0x180035e84  mov     byte ptr [rbp+150h+var_18F], 2
0x180035e88  mov     rcx, [r14]
0x180035e8b  add     rcx, 0B0h
0x180035e92  lea     rdx, [rbp+150h+var_1A8]
0x180035e96  call    ?GetSourceEntry@MidiEndpointNameTable@WindowsMidiServicesNamingLib@@QEBA?AV?$shared_ptr@UMidi1PortNameEntry@WindowsMidiServicesNamingLib@@@std@@E@Z; WindowsMidiServicesNamingLib::MidiEndpointNameTable::GetSourceEntry(uchar)
0x180035e9b  nop
0x180035e9c  mov     rdx, [rbp+150h+var_1A8]
0x180035ea0  test    rdx, rdx
0x180035ea3  jz      short loc_180035EF9
0x180035ea5  add     rdx, 88h
0x180035eac  cmp     [rdx], bx
0x180035eaf  jz      short loc_180035EF9
0x180035eb1  xorps   xmm0, xmm0
0x180035eb4  movups  [rbp+150h+var_160], xmm0
0x180035eb8  mov     qword ptr [rbp+150h+var_150], rbx
0x180035ebc  mov     qword ptr [rbp+150h+var_150+8], rbx
0x180035ec0  mov     r8, rsi
0x180035ec3  inc     r8
0x180035ec6  cmp     [rdx+r8*2], bx
0x180035ecb  jnz     short loc_180035EC3
0x180035ecd  lea     rcx, [rbp+150h+var_160]
0x180035ed1  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180035ed6  lea     rdx, [rbp+150h+var_160]; void *
0x180035eda  lea     rcx, [rbp+150h+var_110]; Src
0x180035ede  call    ?TrimmedWStringCopy@WindowsMidiServicesInternal@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V23@@Z; WindowsMidiServicesInternal::TrimmedWStringCopy(std::wstring)
0x180035ee3  mov     rdx, rax
0x180035ee6  lea     rcx, [rbp+150h+Src]
0x180035eea  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180035eef  lea     rcx, [rbp+150h+var_110]; void *
0x180035ef3  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180035ef8  nop
0x180035ef9  mov     rbx, [rbp+150h+var_1A0]
0x180035efd  test    rbx, rbx
0x180035f00  jz      short loc_180035F35
0x180035f02  mov     eax, esi
0x180035f04  lock xadd [rbx+8], eax
0x180035f09  add     eax, esi
0x180035f0b  jnz     short loc_180035F35
0x180035f0d  mov     rax, [rbx]
0x180035f10  mov     rcx, rbx
0x180035f13  mov     rax, [rax]
0x180035f16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035f1b  mov     eax, esi
0x180035f1d  lock xadd [rbx+0Ch], eax
0x180035f22  add     eax, esi
0x180035f24  jnz     short loc_180035F35
0x180035f26  mov     rax, [rbx]
0x180035f29  mov     rcx, rbx
0x180035f2c  mov     rax, [rax+8]
0x180035f30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035f35  xor     ebx, ebx
0x180035f37  cmp     [rbp+150h+var_170], rbx
0x180035f3b  jnz     loc_18003603D
0x180035f41  mov     rdx, [r14]
0x180035f44  add     rdx, 40h ; '@'
0x180035f48  lea     rcx, [rbp+150h+Src]
0x180035f4c  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x180035f51  movzx   eax, byte ptr [rbp+150h+var_18F+1]
0x180035f55  test    al, al
0x180035f57  jz      loc_18003603D
0x180035f5d  mov     word ptr [rsp+250h+var_1F8], ax
0x180035f62  xorps   xmm0, xmm0
0x180035f65  movups  [rbp+150h+var_160], xmm0
0x180035f69  xorps   xmm1, xmm1
0x180035f6c  movdqu  [rbp+150h+var_150], xmm1
0x180035f71  lea     r8d, [rbx+1]
0x180035f75  lea     rdx, [rsp+250h+var_1F8]
0x180035f7a  lea     rcx, [rbp+150h+var_160]
0x180035f7e  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180035f83  nop
0x180035f84  lea     r9d, [rbx+1]
0x180035f88  lea     r8, asc_180080F20; " "
0x180035f8f  xor     edx, edx
0x180035f91  lea     rcx, [rbp+150h+var_160]; Src
0x180035f95  call    ??$_Insert@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KQEBG0@Z; std::wstring::_Insert<ushort>(unsigned __int64,ushort const * const,unsigned __int64)
0x180035f9a  movups  xmm0, xmmword ptr [rax]
0x180035f9d  movups  [rbp+150h+var_110], xmm0
0x180035fa1  movups  xmm1, xmmword ptr [rax+10h]
0x180035fa5  movups  [rbp+150h+var_100], xmm1
0x180035fa9  mov     [rax], bx
0x180035fac  mov     [rax+10h], rbx
0x180035fb0  mov     qword ptr [rax+18h], 7
0x180035fb8  movq    rdx, xmm1
0x180035fbd  lea     r9, [rbp+150h+var_110]
0x180035fc1  movq    rcx, xmm0
0x180035fc6  psrldq  xmm1, 8
0x180035fcb  movq    rax, xmm1
0x180035fd0  cmp     rax, 7
0x180035fd4  cmova   r9, rcx
0x180035fd8  mov     rcx, [rbp+150h+var_170]
0x180035fdc  mov     rax, [rbp+150h+var_168]
0x180035fe0  sub     rax, rcx
0x180035fe3  cmp     rdx, rax
0x180035fe6  ja      short loc_18003601B
0x180035fe8  lea     rdi, [rdx+rcx]
0x180035fec  mov     [rbp+150h+var_170], rdi
0x180035ff0  lea     rbx, [rbp+150h+Src]
0x180035ff4  cmp     [rbp+150h+var_168], 7
0x180035ff9  cmova   rbx, qword ptr [rbp+150h+Src]
0x180035ffe  lea     r8, [rdx+rdx]; Size
0x180036002  lea     rcx, [rbx+rcx*2]; void *
0x180036006  mov     rdx, r9; Src
0x180036009  call    memmove_0
0x18003600e  xor     eax, eax
0x180036010  mov     [rbx+rdi*2], ax
0x180036014  mov     rdi, [rsp+250h+var_208]
0x180036019  jmp     short loc_18003602A
0x18003601b  mov     [rsp+250h+var_230], rdx; __int64
0x180036020  lea     rcx, [rbp+150h+Src]; Src
0x180036024  call    ??$_Reallocate_grow_by@V_lambda_1_@?1???$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV23@QEBG_K@Z@PEBG_K@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1???$_Append@G@01@AEAAAEAV01@QEBG0@Z@PEBG_K@Z; std::wstring::_Reallocate_grow_by<`std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)'::`2'::_lambda_1_,ushort const *,unsigned __int64>(unsigned __int64,`std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)'::`2'::_lambda_1_,ushort const *,unsigned __int64)
0x180036029  nop
0x18003602a  lea     rcx, [rbp+150h+var_110]; void *
0x18003602e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180036033  nop
0x180036034  lea     rcx, [rbp+150h+var_160]; void *
0x180036038  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003603d  mov     eax, 1
0x180036042  mov     byte ptr [rbp+150h+var_18F+3], al
0x180036045  mov     [rbp+150h+var_18A], 10001h
0x18003604c  mov     rdx, [r13+8]
0x180036050  cmp     rdx, [r13+10h]
0x180036054  jz      short loc_180036097
0x180036056  mov     al, [rbp+150h+var_190]
0x180036059  mov     [rdx], al
0x18003605b  mov     al, byte ptr [rbp+150h+var_18F]
0x18003605e  mov     [rdx+1], al
0x180036061  mov     al, byte ptr [rbp+150h+var_18F+1]
0x180036064  mov     [rdx+2], al
0x180036067  mov     al, byte ptr [rbp+150h+var_18F+2]
0x18003606a  mov     [rdx+3], al
0x18003606d  mov     al, byte ptr [rbp+150h+var_18F+3]
0x180036070  mov     [rdx+4], al
0x180036073  movzx   eax, word ptr [rbp+150h+var_18A]
0x180036077  mov     [rdx+6], ax
0x18003607b  movzx   eax, word ptr [rbp+150h+var_18A+2]
0x18003607f  mov     [rdx+8], ax
0x180036083  lea     rcx, [rdx+10h]
0x180036087  lea     rdx, [rbp+150h+Src]
0x18003608b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180036090  add     qword ptr [r13+8], 30h ; '0'
0x180036095  jmp     short loc_1800360A3
0x180036097  lea     r8, [rbp+150h+var_190]
0x18003609b  mov     rcx, r13
0x18003609e  call    ??$_Emplace_reallocate@AEBUGroupTerminalBlockInternal@WindowsMidiServicesInternal@@@?$vector@UGroupTerminalBlockInternal@WindowsMidiServicesInternal@@V?$allocator@UGroupTerminalBlockInternal@WindowsMidiServicesInternal@@@std@@@std@@AEAAPEAUGroupTerminalBlockInternal@WindowsMidiServicesInternal@@QEAU23@AEBU23@@Z; std::vector<WindowsMidiServicesInternal::GroupTerminalBlockInternal>::_Emplace_reallocate<WindowsMidiServicesInternal::GroupTerminalBlockInternal const &>(WindowsMidiServicesInternal::GroupTerminalBlockInternal * const,WindowsMidiServicesInternal::GroupTerminalBlockInternal const &)
0x1800360a3  mov     rdx, [rsp+250h+var_1E0]
0x1800360a8  cmp     rdx, [rsp+250h+var_1D8]
0x1800360ad  jz      short loc_1800360D5
0x1800360af  mov     al, byte ptr [rbp+150h+var_140]
0x1800360b2  mov     [rdx], al
0x1800360b4  mov     eax, dword ptr [rbp+150h+var_140+4]
0x1800360b7  mov     [rdx+4], eax
0x1800360ba  mov     eax, dword ptr [rbp+150h+var_140+8]
0x1800360bd  mov     [rdx+8], eax
0x1800360c0  lea     rcx, [rdx+10h]
0x1800360c4  lea     rdx, [rbp+150h+var_130]
0x1800360c8  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800360cd  add     [rsp+250h+var_1E0], 30h ; '0'
0x1800360d3  jmp     short loc_1800360E4
0x1800360d5  lea     r8, [rbp+150h+var_140]
0x1800360d9  lea     rcx, [rsp+250h+var_1F0+8]
0x1800360de  call    ??$_Emplace_reallocate@AEBUPinMapEntryStagingEntry@@@?$vector@UPinMapEntryStagingEntry@@V?$allocator@UPinMapEntryStagingEntry@@@std@@@std@@AEAAPEAUPinMapEntryStagingEntry@@QEAU2@AEBU2@@Z; std::vector<PinMapEntryStagingEntry>::_Emplace_reallocate<PinMapEntryStagingEntry const &>(PinMapEntryStagingEntry * const,PinMapEntryStagingEntry const &)
0x1800360e3  nop
0x1800360e4  lea     rcx, [rbp+150h+var_130]; void *
0x1800360e8  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800360ed  nop
0x1800360ee  lea     rcx, [rbp+150h+Src]; void *
0x1800360f2  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
  ... truncated ...
```
