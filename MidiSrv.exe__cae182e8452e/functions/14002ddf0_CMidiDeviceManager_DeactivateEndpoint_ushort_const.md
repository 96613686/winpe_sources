# CMidiDeviceManager::DeactivateEndpoint(ushort const *)

- ea: `0x14002ddf0`
- end: `0x14002e713`
- name: `?DeactivateEndpoint@CMidiDeviceManager@@UEAAJPEBG@Z`
- size: `2339`
- prototype: `__int64 __fastcall(CMidiDeviceManager *__hidden this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `20`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x1400018e4`
- `0x140001bc0`
- `0x140001ce8`
- `0x14000298c`
- `0x1400054c0`
- `0x1400072d4`
- `0x140007c20`
- `0x14000984c`
- `0x14000a6b4`
- `0x140013a38`
- `0x14001bf60`
- `0x14001dccc`
- `0x14001e990`
- `0x14001f95c`
- `0x140027660`
- `0x140028d00`
- `0x14002d640`
- `0x14002ddf0`
- `0x14003481c`
- `0x1400358d0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14002e1b6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14002e244`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14002e1b6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14002e244`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14002df71`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14002df71`

## string_xrefs

- `0x14002de9e`: `avcore\midi2\service\exe\mididevicemanager.cpp`
- `0x14002df11`: `avcore\midi2\service\exe\mididevicemanager.cpp`
- `0x14002e63a`: `avcore\midi2\service\exe\mididevicemanager.cpp`

## pseudocode

```c
__int64 __fastcall CMidiDeviceManager::DeactivateEndpoint(CMidiDeviceManager *this, const char *a2)
{
  unsigned int v3; // ebx
  _DWORD *v5; // rcx
  __int64 v6; // r8
  __int64 v7; // r9
  unsigned int v8; // ebx
  unsigned __int64 v9; // r8
  __int64 v10; // rax
  __int64 v11; // rdx
  char IsEnabled; // al
  __m128i si128; // xmm6
  __int64 **v14; // r13
  __int64 *v15; // rsi
  __int64 *v16; // r12
  int v17; // ebx
  __int64 v18; // rax
  const wchar_t *v19; // rdx
  const wchar_t *v20; // rcx
  __int64 v21; // rax
  const wchar_t *v22; // rdx
  const wchar_t *v23; // rcx
  char v24; // r15
  _DWORD *v25; // r8
  __int64 v26; // r9
  __int64 v27; // rax
  __int64 v28; // rcx
  wchar_t **v29; // rax
  __int64 v30; // rax
  unsigned __int64 v31; // r8
  _WORD *v32; // rdx
  __int64 v33; // rax
  __int64 v34; // rdx
  _DWORD *v35; // rcx
  __int64 v36; // r8
  __int64 v37; // r9
  wchar_t **v38; // rax
  __int64 **v39; // r12
  __int64 *v40; // rsi
  __int64 *v41; // r15
  int v42; // ebx
  __int64 v43; // rax
  const wchar_t *v44; // rdx
  const wchar_t *v45; // rcx
  __int64 v46; // rax
  const wchar_t *v47; // rdx
  const wchar_t *v48; // rcx
  char v49; // r14
  _DWORD *v50; // r8
  __int64 v51; // r9
  __int64 v52; // rax
  const char *v53; // rcx
  wchar_t **v54; // rax
  __int64 v55; // rax
  unsigned __int64 v56; // r8
  _WORD *v57; // rdx
  __int64 v58; // rax
  __int64 v59; // rdx
  _DWORD *v60; // rcx
  __int64 v61; // r8
  __int64 v62; // r9
  wchar_t **v63; // rax
  _DWORD *v64; // r8
  __int64 v65; // r9
  const wchar_t *v66; // rdx
  __int64 v67; // rcx
  _DWORD *v68; // rcx
  __int64 v69; // r8
  __int64 v70; // r9
  int v71; // eax
  _DWORD *v72; // rcx
  __int64 v73; // r8
  __int64 v74; // r9
  wchar_t **v75; // rax
  int v77; // [rsp+28h] [rbp-E0h]
  char v78; // [rsp+58h] [rbp-B0h]
  int v79[2]; // [rsp+60h] [rbp-A8h] BYREF
  int v80[2]; // [rsp+68h] [rbp-A0h] BYREF
  const wchar_t *v81; // [rsp+70h] [rbp-98h] BYREF
  const char *v82; // [rsp+78h] [rbp-90h] BYREF
  const char *v83; // [rsp+80h] [rbp-88h] BYREF
  __int128 v84; // [rsp+88h] [rbp-80h] BYREF
  __int64 v85; // [rsp+98h] [rbp-70h]
  _BYTE v86[8]; // [rsp+A0h] [rbp-68h] BYREF
  _BYTE v87[32]; // [rsp+A8h] [rbp-60h] BYREF
  wchar_t *S2[2]; // [rsp+C8h] [rbp-40h] BYREF
  size_t N; // [rsp+D8h] [rbp-30h]
  unsigned __int64 v90; // [rsp+E0h] [rbp-28h]
  wchar_t *v91[2]; // [rsp+E8h] [rbp-20h] BYREF
  __m128i v92; // [rsp+F8h] [rbp-10h]
  wchar_t *S1[2]; // [rsp+108h] [rbp+0h] BYREF
  __int128 v94; // [rsp+118h] [rbp+10h]
  wil::details::in1diag3 *retaddr; // [rsp+180h] [rbp+78h]

  v3 = 0;
  LODWORD(v83) = 0;
  v5 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
  if ( *v5 > 4u )
  {
    *(_QWORD *)v80 = "CMidiDeviceManager::DeactivateEndpoint";
    v81 = L"Enter";
    v83 = a2;
    *(_QWORD *)v79 = this;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
      (__int64)v5,
      (__int64)byte_1400890A1,
      v6,
      v7,
      v80,
      (__int64)v79,
      &v81,
      &v83);
  }
  if ( a2 )
  {
    *(_OWORD *)S1 = 0;
    v9 = -1;
    v94 = 0;
    do
      ++v9;
    while ( *(_WORD *)&a2[2 * v9] );
    std::wstring::_Construct<1,unsigned short const *>((char **)S1, a2, v9);
    v10 = std::wstring::wstring((__int64)v91, (__int64)S1);
    WindowsMidiServicesInternal::ToUpperTrimmedWStringCopy(S2, v10);
    std::wstring::~wstring((char **)S1);
    if ( N )
    {
      v78 = 0;
      v84 = 0;
      v85 = 0;
      IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_MIDI2DeviceRemoval>::__private_IsEnabled(
                    `wil::Feature<__WilFeatureTraits_Feature_Servicing_MIDI2DeviceRemoval>::GetImpl'::`2'::impl,
                    v11);
      si128 = _mm_load_si128((const __m128i *)&_xmm);
      if ( IsEnabled )
      {
        v14 = (__int64 **)((char *)this + 136);
        while ( 1 )
        {
          EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 96));
          v15 = *v14;
          v16 = (__int64 *)*((_QWORD *)this + 18);
          if ( *v14 != v16 )
          {
            do
            {
              v17 = v3 | 1;
              v18 = std::wstring::wstring((__int64)v87, *v15 + 48);
              WindowsMidiServicesInternal::ToUpperTrimmedWStringCopy(S1, v18);
              v19 = (const wchar_t *)S2;
              v20 = (const wchar_t *)S1;
              if ( v90 > 7 )
                v19 = S2[0];
              if ( *((_QWORD *)&v94 + 1) > 7u )
                v20 = S1[0];
              if ( (unsigned __int64)v94 >= N && !wmemcmp(v20, v19, N) )
                goto LABEL_24;
              v17 |= 2u;
              v21 = std::wstring::wstring((__int64)v87, *v15 + 112);
              WindowsMidiServicesInternal::ToUpperTrimmedWStringCopy(v91, v21);
              v22 = (const wchar_t *)S2;
              v23 = (const wchar_t *)v91;
              if ( v90 > 7 )
                v22 = S2[0];
              if ( v92.m128i_i64[1] > 7uLL )
                v23 = v91[0];
              if ( v92.m128i_i64[0] >= N && !wmemcmp(v23, v22, N) )
LABEL_24:
                v24 = 1;
              else
                v24 = 0;
              if ( (v17 & 2) != 0 )
              {
                v17 &= ~2u;
                std::wstring::~wstring((char **)v91);
              }
              v3 = v17 & 0xFFFFFFFE;
              std::wstring::~wstring((char **)S1);
              if ( v24 )
                break;
              ++v15;
            }
            while ( v15 != v16 );
          }
          if ( v15 == *((__int64 **)this + 18) )
            break;
          v25 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
          if ( *v25 > 4u )
          {
            v27 = *v15;
            v81 = L"Found instance id in ports list. Erasing";
            v28 = *(_QWORD *)(v27 + 40);
            v29 = S2;
            if ( v90 > 7 )
              v29 = (wchar_t **)S2[0];
            *(_QWORD *)v79 = v29;
            v82 = "CMidiDeviceManager::DeactivateEndpoint";
            *(_QWORD *)v80 = v28;
            v83 = (const char *)this;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
              (__int64)v25,
              (__int64)byte_1400899C3,
              (__int64)v25,
              v26,
              &v82,
              (__int64)&v83,
              &v81,
              v79,
              v80);
          }
          v30 = *v15;
          v31 = -1;
          *(_OWORD *)S1 = 0;
          v32 = *(_WORD **)(v30 + 40);
          v94 = 0;
          do
            ++v31;
          while ( v32[v31] );
          std::wstring::_Construct<1,unsigned short const *>((char **)S1, v32, v31);
          v33 = std::wstring::wstring((__int64)v87, (__int64)S1);
          WindowsMidiServicesInternal::ToLowerTrimmedWStringCopy(v91, v33);
          v34 = *((_QWORD *)&v84 + 1);
          if ( *((_QWORD *)&v84 + 1) == v85 )
          {
            std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(&v84, *((_QWORD *)&v84 + 1), v91);
          }
          else
          {
            **((_OWORD **)&v84 + 1) = 0;
            *(_QWORD *)(v34 + 16) = 0;
            *(_QWORD *)(v34 + 24) = 0;
            *(_OWORD *)v34 = *(_OWORD *)v91;
            *(__m128i *)(v34 + 16) = v92;
            *((_QWORD *)&v84 + 1) += 32LL;
            v92 = si128;
            LOWORD(v91[0]) = 0;
          }
          std::wstring::~wstring((char **)v91);
          std::wstring::~wstring((char **)S1);
          std::vector<std::unique_ptr<_MIDIPORT>>::erase((char *)this + 136, v86, v15);
          v78 = 1;
          if ( this != (CMidiDeviceManager *)-96LL )
            LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 96));
        }
        v35 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
        if ( *v35 > 4u )
        {
          v38 = S2;
          *(_QWORD *)v79 = this;
          if ( v90 > 7 )
            v38 = (wchar_t **)S2[0];
          v82 = (const char *)v38;
          *(_QWORD *)v80 = L"Found no more matches in list. Breaking out of loop";
          v81 = (const wchar_t *)"CMidiDeviceManager::DeactivateEndpoint";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
            (__int64)v35,
            (__int64)&dword_140089B9C,
            v36,
            v37,
            &v81,
            (__int64)v79,
            v80,
            &v82);
        }
        if ( this != (CMidiDeviceManager *)-96LL )
          LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 96));
      }
      else
      {
        v39 = (__int64 **)((char *)this + 136);
        while ( 1 )
        {
          v40 = *v39;
          v41 = (__int64 *)*((_QWORD *)this + 18);
          if ( *v39 != v41 )
          {
            do
            {
              v42 = v3 | 4;
              v43 = std::wstring::wstring((__int64)v87, *v40 + 48);
              WindowsMidiServicesInternal::ToUpperTrimmedWStringCopy(v91, v43);
              v44 = (const wchar_t *)S2;
              v45 = (const wchar_t *)v91;
              if ( v90 > 7 )
                v44 = S2[0];
              if ( v92.m128i_i64[1] > 7uLL )
                v45 = v91[0];
              if ( v92.m128i_i64[0] >= N && !wmemcmp(v45, v44, N) )
                goto LABEL_62;
              v42 |= 8u;
              v46 = std::wstring::wstring((__int64)v87, *v40 + 112);
              WindowsMidiServicesInternal::ToUpperTrimmedWStringCopy(S1, v46);
              v47 = (const wchar_t *)S2;
              v48 = (const wchar_t *)S1;
              if ( v90 > 7 )
                v47 = S2[0];
              if ( *((_QWORD *)&v94 + 1) > 7u )
                v48 = S1[0];
              if ( (unsigned __int64)v94 >= N && !wmemcmp(v48, v47, N) )
LABEL_62:
                v49 = 1;
              else
                v49 = 0;
              if ( (v42 & 8) != 0 )
              {
                v42 &= ~8u;
                std::wstring::~wstring((char **)S1);
              }
              v3 = v42 & 0xFFFFFFFB;
              std::wstring::~wstring((char **)v91);
              if ( v49 )
                break;
              ++v40;
            }
            while ( v40 != v41 );
          }
          if ( v40 == *((__int64 **)this + 18) )
            break;
          v50 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
          if ( *v50 > 4u )
          {
            v52 = *v40;
            *(_QWORD *)v79 = L"Found instance id in ports list. Erasing";
            v53 = *(const char **)(v52 + 40);
            v54 = S2;
            if ( v90 > 7 )
              v54 = (wchar_t **)S2[0];
            *(_QWORD *)v80 = v54;
            v83 = "CMidiDeviceManager::DeactivateEndpoint";
            v82 = v53;
            v81 = (const wchar_t *)this;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
              (__int64)v50,
              (__int64)byte_140089539,
              (__int64)v50,
              v51,
              &v83,
              (__int64)&v81,
              v79,
              v80,
              &v82);
          }
          v55 = *v40;
          v56 = -1;
          *(_OWORD *)S1 = 0;
          v57 = *(_WORD **)(v55 + 40);
          v94 = 0;
          do
            ++v56;
          while ( v57[v56] );
          std::wstring::_Construct<1,unsigned short const *>((char **)S1, v57, v56);
          v58 = std::wstring::wstring((__int64)v87, (__int64)S1);
          WindowsMidiServicesInternal::ToLowerTrimmedWStringCopy(v91, v58);
          v59 = *((_QWORD *)&v84 + 1);
          if ( *((_QWORD *)&v84 + 1) == v85 )
          {
            std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(&v84, *((_QWORD *)&v84 + 1), v91);
          }
          else
          {
            **((_OWORD **)&v84 + 1) = 0;
            *(_QWORD *)(v59 + 16) = 0;
            *(_QWORD *)(v59 + 24) = 0;
            *(_OWORD *)v59 = *(_OWORD *)v91;
            *(__m128i *)(v59 + 16) = v92;
            *((_QWORD *)&v84 + 1) += 32LL;
            v92 = si128;
            LOWORD(v91[0]) = 0;
          }
          std::wstring::~wstring((char **)v91);
          std::wstring::~wstring((char **)S1);
          std::vector<std::unique_ptr<_MIDIPORT>>::erase((char *)this + 136, v86, v40);
          v78 = 1;
        }
        v60 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
        if ( *v60 > 4u )
        {
          v63 = S2;
          *(_QWORD *)v79 = this;
          if ( v90 > 7 )
            v63 = (wchar_t **)S2[0];
          v82 = (const char *)v63;
          *(_QWORD *)v80 = L"Found no more matches in list. Breaking out of loop";
          v81 = (const wchar_t *)"CMidiDeviceManager::DeactivateEndpoint";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
            (__int64)v60,
            (__int64)byte_140089EAB,
            v61,
            v62,
            &v81,
            (__int64)v79,
            v80,
            &v82);
        }
      }
      if ( !v78 )
        goto LABEL_97;
      v64 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
      if ( *v64 > 4u )
      {
        if ( (_QWORD)v84 == *((_QWORD *)&v84 + 1) )
        {
          v66 = L"<none>";
        }
        else if ( *(_QWORD *)(v84 + 24) <= 7u )
        {
          v66 = (const wchar_t *)v84;
        }
        else
        {
          v66 = *(const wchar_t **)v84;
        }
        v82 = (const char *)v66;
        *(_QWORD *)v79 = L"Notifying client manager of device removal";
        *(_QWORD *)v80 = (__int64)(*((_QWORD *)&v84 + 1) - v84) >> 5;
        v81 = (const wchar_t *)this;
        v83 = "CMidiDeviceManager::DeactivateEndpoint";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>>(
          (__int64)v64,
          (__int64)&word_140088F9E,
          (__int64)v64,
          v65,
          &v83,
          (__int64)&v81,
          v79,
          (__int64)v80,
          &v82);
      }
      v67 = *((_QWORD *)this + 2);
      if ( v67 )
      {
        CMidiClientManager::OnDeviceRemoved(v67, (const wchar_t **)&v84);
      }
      else
      {
        v68 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
        if ( *v68 > 3u )
        {
          *(_QWORD *)v80 = this;
          v82 = (const char *)L"No client manager set for device removal";
          *(_QWORD *)v79 = "CMidiDeviceManager::DeactivateEndpoint";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>>(
            (__int64)v68,
            (__int64)byte_14008A2C1,
            v69,
            v70,
            v79,
            (__int64)v80,
            &v82);
        }
      }
      v71 = CMidiDeviceManager::CompactPortNumbers(this);
      v8 = v71;
      if ( v71 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x7B8,
          (unsigned int)"avcore\\midi2\\service\\exe\\mididevicemanager.cpp",
          (const char *)(unsigned int)v71,
          v77);
        std::vector<std::wstring>::~vector<std::wstring>(&v84);
      }
      else
      {
LABEL_97:
        v72 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
        if ( *v72 > 4u )
        {
          v75 = S2;
          *(_QWORD *)v79 = this;
          if ( v90 > 7 )
            v75 = (wchar_t **)S2[0];
          v82 = (const char *)v75;
          *(_QWORD *)v80 = L"Exit success";
          v81 = (const wchar_t *)"CMidiDeviceManager::DeactivateEndpoint";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
            (__int64)v72,
            (__int64)qword_1400895E8,
            v73,
            v74,
            &v81,
            (__int64)v79,
            v80,
            &v82);
        }
        std::vector<std::wstring>::~vector<std::wstring>(&v84);
        v8 = 0;
      }
    }
    else
    {
      v8 = -2147024809;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x717,
        (unsigned int)"avcore\\midi2\\service\\exe\\mididevicemanager.cpp",
        (const char *)0x80070057LL,
        v77);
    }
    std::wstring::~wstring((char **)S2);
  }
  else
  {
    v8 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x712,
      (unsigned int)"avcore\\midi2\\service\\exe\\mididevicemanager.cpp",
      (const char *)0x80070057LL,
      v77);
  }
  return v8;
}

```

## disassembly

```asm
0x14002ddf0  mov     rax, rsp
0x14002ddf3  mov     [rax+18h], rbx
0x14002ddf7  push    rbp
0x14002ddf8  push    rsi
0x14002ddf9  push    rdi
0x14002ddfa  push    r12
0x14002ddfc  push    r13
0x14002ddfe  push    r14
0x14002de00  push    r15
0x14002de02  lea     rbp, [rax-78h]
0x14002de06  sub     rsp, 140h
0x14002de0d  movaps  xmmword ptr [rax-48h], xmm6
0x14002de11  mov     rax, cs:__security_cookie
0x14002de18  xor     rax, rsp
0x14002de1b  mov     [rbp+70h+var_50], rax
0x14002de1f  xor     r13d, r13d
0x14002de22  mov     rsi, rdx
0x14002de25  mov     ebx, r13d
0x14002de28  mov     rdi, rcx
0x14002de2b  mov     dword ptr [rsp+170h+var_F8], ebx
0x14002de2f  call    ?Instance@MidiSrvTelemetryProvider@@KAPEAV1@XZ; MidiSrvTelemetryProvider::Instance(void)
0x14002de34  lea     rdx, aCmidideviceman_17; "CMidiDeviceManager::DeactivateEndpoint"
0x14002de3b  mov     rcx, [rax+8]
0x14002de3f  mov     eax, [rcx]
0x14002de41  cmp     eax, 4
0x14002de44  jbe     short loc_14002DE95
0x14002de46  lea     rax, aEnter; "Enter"
0x14002de4d  mov     qword ptr [rsp+170h+var_110], rdx
0x14002de52  mov     [rsp+170h+var_108], rax
0x14002de57  lea     rdx, byte_1400890A1
0x14002de5e  lea     rax, [rsp+170h+var_F8]
0x14002de63  mov     [rsp+170h+var_F8], rsi
0x14002de68  mov     [rsp+170h+var_138], rax
0x14002de6d  lea     rax, [rsp+170h+var_108]
0x14002de72  mov     [rsp+170h+var_140], rax
0x14002de77  lea     rax, [rsp+170h+var_118]
0x14002de7c  mov     [rsp+170h+var_148], rax
0x14002de81  lea     rax, [rsp+170h+var_110]
0x14002de86  mov     qword ptr [rsp+170h+var_150], rax; int
0x14002de8b  mov     qword ptr [rsp+170h+var_118], rdi
0x14002de90  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x14002de95  test    rsi, rsi
0x14002de98  jnz     short loc_14002DEBC
0x14002de9a  mov     rcx, [rbp+78h]; this
0x14002de9e  lea     r8, aAvcoreMidi2Ser_9; "avcore\\midi2\\service\\exe\\mididevice"...
0x14002dea5  mov     ebx, 80070057h
0x14002deaa  mov     edx, 712h; void *
0x14002deaf  mov     r9d, ebx; char *
0x14002deb2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14002deb7  jmp     loc_14002E6E5
0x14002debc  xorps   xmm0, xmm0
0x14002debf  xorps   xmm1, xmm1
0x14002dec2  movups  xmmword ptr [rbp+70h+S1], xmm0
0x14002dec6  or      r8, 0FFFFFFFFFFFFFFFFh
0x14002deca  movdqu  [rbp+70h+var_60], xmm1
0x14002decf  inc     r8
0x14002ded2  cmp     [rsi+r8*2], r13w
0x14002ded7  jnz     short loc_14002DECF
0x14002ded9  mov     rdx, rsi
0x14002dedc  lea     rcx, [rbp+70h+S1]
0x14002dee0  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x14002dee5  lea     rdx, [rbp+70h+S1]
0x14002dee9  lea     rcx, [rbp+70h+var_90]
0x14002deed  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x14002def2  mov     rdx, rax
0x14002def5  lea     rcx, [rbp+70h+S2]
0x14002def9  call    ?ToUpperTrimmedWStringCopy@WindowsMidiServicesInternal@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V23@@Z; WindowsMidiServicesInternal::ToUpperTrimmedWStringCopy(std::wstring)
0x14002defe  lea     rcx, [rbp+70h+S1]; void *
0x14002df02  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14002df07  cmp     [rbp+70h+N], r13
0x14002df0b  jnz     short loc_14002DF2F
0x14002df0d  mov     rcx, [rbp+78h]; this
0x14002df11  lea     r8, aAvcoreMidi2Ser_9; "avcore\\midi2\\service\\exe\\mididevice"...
0x14002df18  mov     ebx, 80070057h
0x14002df1d  mov     edx, 717h; void *
0x14002df22  mov     r9d, ebx; char *
0x14002df25  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14002df2a  jmp     loc_14002E6DC
0x14002df2f  xorps   xmm0, xmm0
0x14002df32  mov     byte ptr [rsp+170h+var_120], r13b
0x14002df37  movdqu  [rbp+70h+var_F0], xmm0
0x14002df3c  mov     [rbp+70h+var_E0], r13
0x14002df40  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_MIDI2DeviceRemoval@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_MIDI2DeviceRemoval@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_MIDI2DeviceRemoval> `wil::Feature<__WilFeatureTraits_Feature_Servicing_MIDI2DeviceRemoval>::GetImpl(void)'::`2'::impl
0x14002df47  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_MIDI2DeviceRemoval@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_MIDI2DeviceRemoval>::__private_IsEnabled(void)
0x14002df4c  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x14002df54  test    al, al
0x14002df56  jz      loc_14002E24F
0x14002df5c  lea     r14, [rdi+60h]
0x14002df60  lea     r13, [rdi+88h]
0x14002df67  lea     r15, aFoundInstanceI; "Found instance id in ports list. Erasin"...
0x14002df6e  mov     rcx, r14; lpCriticalSection
0x14002df71  call    cs:__imp_EnterCriticalSection
0x14002df77  mov     rsi, [r13+0]
0x14002df7b  mov     r12, [r13+8]
0x14002df7f  cmp     rsi, r12
0x14002df82  jz      loc_14002E062
0x14002df88  mov     rdx, [rsi]
0x14002df8b  lea     rcx, [rbp+70h+var_D0]
0x14002df8f  add     rdx, 30h ; '0'
0x14002df93  or      ebx, 1
0x14002df96  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x14002df9b  mov     rdx, rax
0x14002df9e  lea     rcx, [rbp+70h+S1]
0x14002dfa2  call    ?ToUpperTrimmedWStringCopy@WindowsMidiServicesInternal@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V23@@Z; WindowsMidiServicesInternal::ToUpperTrimmedWStringCopy(std::wstring)
0x14002dfa7  cmp     [rbp+70h+var_98], 7
0x14002dfac  lea     rdx, [rbp+70h+S2]
0x14002dfb0  mov     r8, [rbp+70h+N]; N
0x14002dfb4  lea     rcx, [rbp+70h+S1]
0x14002dfb8  cmova   rdx, [rbp+70h+S2]; S2
0x14002dfbd  cmp     qword ptr [rbp+70h+var_60+8], 7
0x14002dfc2  cmova   rcx, [rbp+70h+S1]; S1
0x14002dfc7  cmp     qword ptr [rbp+70h+var_60], r8
0x14002dfcb  jb      short loc_14002DFD6
0x14002dfcd  call    wmemcmp
0x14002dfd2  test    eax, eax
0x14002dfd4  jz      short loc_14002E024
0x14002dfd6  mov     rdx, [rsi]
0x14002dfd9  lea     rcx, [rbp+70h+var_D0]
0x14002dfdd  add     rdx, 70h ; 'p'
0x14002dfe1  or      ebx, 2
0x14002dfe4  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x14002dfe9  mov     rdx, rax
0x14002dfec  lea     rcx, [rbp+70h+var_90]
0x14002dff0  call    ?ToUpperTrimmedWStringCopy@WindowsMidiServicesInternal@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V23@@Z; WindowsMidiServicesInternal::ToUpperTrimmedWStringCopy(std::wstring)
0x14002dff5  cmp     [rbp+70h+var_98], 7
0x14002dffa  lea     rdx, [rbp+70h+S2]
0x14002dffe  mov     r8, [rbp+70h+N]; N
0x14002e002  lea     rcx, [rbp+70h+var_90]
0x14002e006  cmova   rdx, [rbp+70h+S2]; S2
0x14002e00b  cmp     qword ptr [rbp+70h+var_80+8], 7
0x14002e010  cmova   rcx, [rbp+70h+var_90]; S1
0x14002e015  cmp     qword ptr [rbp+70h+var_80], r8
0x14002e019  jb      short loc_14002E029
0x14002e01b  call    wmemcmp
0x14002e020  test    eax, eax
0x14002e022  jnz     short loc_14002E029
0x14002e024  mov     r15b, 1
0x14002e027  jmp     short loc_14002E02C
0x14002e029  xor     r15b, r15b
0x14002e02c  test    bl, 2
0x14002e02f  jz      short loc_14002E03D
0x14002e031  and     ebx, 0FFFFFFFDh
0x14002e034  lea     rcx, [rbp+70h+var_90]; void *
0x14002e038  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14002e03d  lea     rcx, [rbp+70h+S1]; void *
0x14002e041  and     ebx, 0FFFFFFFEh
0x14002e044  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14002e049  test    r15b, r15b
0x14002e04c  jnz     short loc_14002E05B
0x14002e04e  add     rsi, 8
0x14002e052  cmp     rsi, r12
0x14002e055  jnz     loc_14002DF88
0x14002e05b  lea     r15, aFoundInstanceI; "Found instance id in ports list. Erasin"...
0x14002e062  cmp     rsi, [rdi+90h]
0x14002e069  jz      loc_14002E1C1
0x14002e06f  call    ?Instance@MidiSrvTelemetryProvider@@KAPEAV1@XZ; MidiSrvTelemetryProvider::Instance(void)
0x14002e074  mov     r8, [rax+8]
0x14002e078  mov     eax, [r8]
0x14002e07b  cmp     eax, 4
0x14002e07e  jbe     short loc_14002E0F6
0x14002e080  mov     rax, [rsi]
0x14002e083  lea     rdx, byte_1400899C3
0x14002e08a  cmp     [rbp+70h+var_98], 7
0x14002e08f  mov     [rsp+170h+var_108], r15
0x14002e094  mov     rcx, [rax+28h]
0x14002e098  lea     rax, [rbp+70h+S2]
0x14002e09c  cmova   rax, [rbp+70h+S2]
0x14002e0a1  mov     qword ptr [rsp+170h+var_118], rax
0x14002e0a6  lea     rax, aCmidideviceman_17; "CMidiDeviceManager::DeactivateEndpoint"
0x14002e0ad  mov     [rsp+170h+var_100], rax
0x14002e0b2  lea     rax, [rsp+170h+var_110]
0x14002e0b7  mov     [rsp+170h+var_130], rax
0x14002e0bc  lea     rax, [rsp+170h+var_118]
0x14002e0c1  mov     [rsp+170h+var_138], rax
0x14002e0c6  lea     rax, [rsp+170h+var_108]
0x14002e0cb  mov     [rsp+170h+var_140], rax
0x14002e0d0  lea     rax, [rsp+170h+var_F8]
0x14002e0d5  mov     [rsp+170h+var_148], rax
0x14002e0da  lea     rax, [rsp+170h+var_100]
0x14002e0df  mov     qword ptr [rsp+170h+var_110], rcx
0x14002e0e4  mov     rcx, r8
0x14002e0e7  mov     qword ptr [rsp+170h+var_150], rax
0x14002e0ec  mov     [rsp+170h+var_F8], rdi
0x14002e0f1  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U3@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@55@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x14002e0f6  mov     rax, [rsi]
0x14002e0f9  xorps   xmm0, xmm0
0x14002e0fc  xorps   xmm1, xmm1
0x14002e0ff  or      r8, 0FFFFFFFFFFFFFFFFh
0x14002e103  movups  xmmword ptr [rbp+70h+S1], xmm0
0x14002e107  xor     r12d, r12d
0x14002e10a  mov     rdx, [rax+28h]
0x14002e10e  movdqu  [rbp+70h+var_60], xmm1
0x14002e113  inc     r8
0x14002e116  cmp     [rdx+r8*2], r12w
0x14002e11b  jnz     short loc_14002E113
0x14002e11d  lea     rcx, [rbp+70h+S1]
0x14002e121  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x14002e126  lea     rdx, [rbp+70h+S1]
0x14002e12a  lea     rcx, [rbp+70h+var_D0]
0x14002e12e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x14002e133  mov     rdx, rax
0x14002e136  lea     rcx, [rbp+70h+var_90]
0x14002e13a  call    ?ToLowerTrimmedWStringCopy@WindowsMidiServicesInternal@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V23@@Z; WindowsMidiServicesInternal::ToLowerTrimmedWStringCopy(std::wstring)
0x14002e13f  mov     rdx, qword ptr [rbp+70h+var_F0+8]
0x14002e143  cmp     rdx, [rbp+70h+var_E0]
0x14002e147  jz      short loc_14002E177
0x14002e149  xorps   xmm0, xmm0
0x14002e14c  movups  xmmword ptr [rdx], xmm0
0x14002e14f  mov     [rdx+10h], r12
0x14002e153  mov     [rdx+18h], r12
0x14002e157  movups  xmm0, xmmword ptr [rbp+70h+var_90]
0x14002e15b  movups  xmmword ptr [rdx], xmm0
0x14002e15e  movups  xmm1, [rbp+70h+var_80]
0x14002e162  movups  xmmword ptr [rdx+10h], xmm1
0x14002e166  add     qword ptr [rbp+70h+var_F0+8], 20h ; ' '
0x14002e16b  movdqu  [rbp+70h+var_80], xmm6
0x14002e170  mov     word ptr [rbp+70h+var_90], r12w
0x14002e175  jmp     short loc_14002E184
0x14002e177  lea     r8, [rbp+70h+var_90]
0x14002e17b  lea     rcx, [rbp+70h+var_F0]
0x14002e17f  call    ??$_Emplace_reallocate@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@QEAV21@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(std::wstring * const,std::wstring &&)
0x14002e184  lea     rcx, [rbp+70h+var_90]; void *
0x14002e188  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14002e18d  lea     rcx, [rbp+70h+S1]; void *
0x14002e191  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14002e196  mov     r8, rsi
0x14002e199  lea     rdx, [rbp+70h+var_D8]
0x14002e19d  mov     rcx, r13
0x14002e1a0  call    ?erase@?$vector@V?$unique_ptr@U_MIDIPORT@@U?$default_delete@U_MIDIPORT@@@std@@@std@@V?$allocator@V?$unique_ptr@U_MIDIPORT@@U?$default_delete@U_MIDIPORT@@@std@@@std@@@2@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@V?$unique_ptr@U_MIDIPORT@@U?$default_delete@U_MIDIPORT@@@std@@@std@@@std@@@std@@@2@V?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@V?$unique_ptr@U_MIDIPORT@@U?$default_delete@U_MIDIPORT@@@std@@@std@@@std@@@std@@@2@@Z; std::vector<std::unique_ptr<_MIDIPORT>>::erase(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<std::unique_ptr<_MIDIPORT>>>>)
0x14002e1a5  mov     byte ptr [rsp+170h+var_120], 1
0x14002e1aa  test    r14, r14
0x14002e1ad  jz      loc_14002DF6E
0x14002e1b3  mov     rcx, r14; lpCriticalSection
0x14002e1b6  call    cs:__imp_LeaveCriticalSection
0x14002e1bc  jmp     loc_14002DF6E
0x14002e1c1  call    ?Instance@MidiSrvTelemetryProvider@@KAPEAV1@XZ; MidiSrvTelemetryProvider::Instance(void)
0x14002e1c6  mov     rcx, [rax+8]
0x14002e1ca  mov     eax, [rcx]
0x14002e1cc  cmp     eax, 4
0x14002e1cf  jbe     short loc_14002E235
0x14002e1d1  cmp     [rbp+70h+var_98], 7
0x14002e1d6  lea     rax, [rbp+70h+S2]
0x14002e1da  lea     rdx, dword_140089B9C
0x14002e1e1  mov     qword ptr [rsp+170h+var_118], rdi
0x14002e1e6  cmova   rax, [rbp+70h+S2]
0x14002e1eb  mov     [rsp+170h+var_100], rax
0x14002e1f0  lea     rax, aFoundNoMoreMat; "Found no more matches in list. Breaking"...
0x14002e1f7  mov     qword ptr [rsp+170h+var_110], rax
0x14002e1fc  lea     rax, aCmidideviceman_17; "CMidiDeviceManager::DeactivateEndpoint"
0x14002e203  mov     [rsp+170h+var_108], rax
0x14002e208  lea     rax, [rsp+170h+var_100]
0x14002e20d  mov     [rsp+170h+var_138], rax
0x14002e212  lea     rax, [rsp+170h+var_110]
0x14002e217  mov     [rsp+170h+var_140], rax
0x14002e21c  lea     rax, [rsp+170h+var_118]
0x14002e221  mov     [rsp+170h+var_148], rax
0x14002e226  lea     rax, [rsp+170h+var_108]
0x14002e22b  mov     qword ptr [rsp+170h+var_150], rax
0x14002e230  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x14002e235  xor     r13d, r13d
0x14002e238  test    r14, r14
0x14002e23b  jz      loc_14002E507
0x14002e241  mov     rcx, r14; lpCriticalSection
0x14002e244  call    cs:__imp_LeaveCriticalSection
0x14002e24a  jmp     loc_14002E507
0x14002e24f  lea     r12, [rdi+88h]
0x14002e256  lea     r14, aFoundInstanceI; "Found instance id in ports list. Erasin"...
0x14002e25d  mov     rsi, [r12]
0x14002e261  mov     r15, [r12+8]
0x14002e266  cmp     rsi, r15
0x14002e269  jz      loc_14002E349
0x14002e26f  mov     rdx, [rsi]
0x14002e272  lea     rcx, [rbp+70h+var_D0]
0x14002e276  add     rdx, 30h ; '0'
0x14002e27a  or      ebx, 4
0x14002e27d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x14002e282  mov     rdx, rax
0x14002e285  lea     rcx, [rbp+70h+var_90]
0x14002e289  call    ?ToUpperTrimmedWStringCopy@WindowsMidiServicesInternal@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V23@@Z; WindowsMidiServicesInternal::ToUpperTrimmedWStringCopy(std::wstring)
0x14002e28e  cmp     [rbp+70h+var_98], 7
0x14002e293  lea     rdx, [rbp+70h+S2]
0x14002e297  mov     r8, [rbp+70h+N]; N
0x14002e29b  lea     rcx, [rbp+70h+var_90]
0x14002e29f  cmova   rdx, [rbp+70h+S2]; S2
0x14002e2a4  cmp     qword ptr [rbp+70h+var_80+8], 7
0x14002e2a9  cmova   rcx, [rbp+70h+var_90]; S1
0x14002e2ae  cmp     qword ptr [rbp+70h+var_80], r8
0x14002e2b2  jb      short loc_14002E2BD
0x14002e2b4  call    wmemcmp
0x14002e2b9  test    eax, eax
0x14002e2bb  jz      short loc_14002E30B
0x14002e2bd  mov     rdx, [rsi]
0x14002e2c0  lea     rcx, [rbp+70h+var_D0]
0x14002e2c4  add     rdx, 70h ; 'p'
0x14002e2c8  or      ebx, 8
0x14002e2cb  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x14002e2d0  mov     rdx, rax
0x14002e2d3  lea     rcx, [rbp+70h+S1]
0x14002e2d7  call    ?ToUpperTrimmedWStringCopy@WindowsMidiServicesInternal@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V23@@Z; WindowsMidiServicesInternal::ToUpperTrimmedWStringCopy(std::wstring)
0x14002e2dc  cmp     [rbp+70h+var_98], 7
  ... truncated ...
```
