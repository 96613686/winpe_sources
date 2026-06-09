# MidiEndpointTable::OnDeviceDisconnected(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>)

- ea: `0x180017670`
- end: `0x180017ed4`
- name: `?OnDeviceDisconnected@MidiEndpointTable@@QEAAJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `2148`
- prototype: `__int64 __fastcall(wchar_t *lpCriticalSection, _QWORD *)`
- caller_count: `1`
- callee_count: `18`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x18001b770`

## callees

- `0x180001878`
- `0x1800038f0`
- `0x180009784`
- `0x18000b5f8`
- `0x18000bf6c`
- `0x18000d1ac`
- `0x18000eae0`
- `0x18000ec98`
- `0x1800119f4`
- `0x1800136f0`
- `0x180014484`
- `0x180014830`
- `0x1800159c8`
- `0x180017670`
- `0x180019558`
- `0x180019850`
- `0x18001adc4`
- `0x180021010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001778e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001778e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180017b91`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180017c46`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180017c7b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180017d2d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180017b91`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180017c46`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180017c7b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180017d2d`

## string_xrefs

- `0x180017814`: `Unlinking from MidiDeviceBidi`
- `0x180017880`: `Unlinking MIDI Client BiDi`
- `0x180017bea`: `Endpoint teardown complete`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall MidiEndpointTable::OnDeviceDisconnected(wchar_t *lpCriticalSection, _QWORD *a2)
{
  _DWORD *v4; // rcx
  int v5; // r8d
  int v6; // r9d
  _QWORD *v7; // rax
  struct TransportState *v8; // rax
  __int64 v9; // rdi
  __int64 v10; // rax
  const struct MidiVirtualDeviceEndpointEntry *v11; // rax
  _DWORD *v12; // rcx
  int v13; // r8d
  int v14; // r9d
  const char *v15; // rax
  _DWORD *v16; // rcx
  int v17; // r8d
  int v18; // r9d
  const char *v19; // rax
  __int64 v20; // rcx
  __int64 v21; // rdi
  __int64 v22; // rdx
  __int64 v23; // rdx
  __int64 v24; // rdi
  __int64 v25; // rcx
  __int64 v26; // rcx
  __int64 v27; // rcx
  _DWORD *v28; // rcx
  int v29; // r8d
  int v30; // r9d
  const char *v31; // rax
  const char *v32; // rdi
  __int64 v33; // rax
  int v34; // eax
  _DWORD *v35; // rcx
  int v36; // r8d
  int v37; // r9d
  const char *v38; // rax
  const char *v39; // rdi
  __int64 v40; // rax
  int v41; // r14d
  _DWORD *v43; // rcx
  int v44; // r8d
  int v45; // r9d
  const char *v46; // rax
  _DWORD *v47; // rcx
  int v48; // r8d
  int v49; // r9d
  const char *v50; // rax
  _DWORD *v51; // rcx
  int v52; // r8d
  int v53; // r9d
  const char *v54; // rax
  _DWORD *v55; // rcx
  int v56; // r8d
  int v57; // r9d
  const char *v58; // rax
  int v59; // [rsp+20h] [rbp-208h]
  const char *v60; // [rsp+40h] [rbp-1E8h] BYREF
  const wchar_t *v61; // [rsp+48h] [rbp-1E0h] BYREF
  int v62[2]; // [rsp+50h] [rbp-1D8h] BYREF
  const wchar_t *v63; // [rsp+58h] [rbp-1D0h] BYREF
  _BYTE v64[32]; // [rsp+60h] [rbp-1C8h] BYREF
  LPCRITICAL_SECTION v65; // [rsp+80h] [rbp-1A8h]
  _QWORD *v66; // [rsp+88h] [rbp-1A0h]
  _BYTE v67[16]; // [rsp+90h] [rbp-198h] BYREF
  __int64 v68; // [rsp+A0h] [rbp-188h]
  _BYTE v69[192]; // [rsp+B0h] [rbp-178h] BYREF
  _BYTE v70[64]; // [rsp+170h] [rbp-B8h] BYREF
  _BYTE v71[40]; // [rsp+1B0h] [rbp-78h] BYREF
  __int64 v72; // [rsp+1D8h] [rbp-50h]
  __int64 v73; // [rsp+1E0h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+228h] [rbp+0h]

  v66 = a2;
  v4 = (_DWORD *)*((_QWORD *)MidiVirtualMidiTransportTelemetryProvider::Instance() + 1);
  if ( *v4 > 4u )
  {
    if ( a2[3] <= 7u )
      v7 = a2;
    else
      v7 = (_QWORD *)*a2;
    *(_QWORD *)v62 = v7;
    v63 = L"Enter";
    v61 = lpCriticalSection;
    v60 = "MidiEndpointTable::OnDeviceDisconnected";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
      (_DWORD)v4,
      (unsigned int)&byte_180026BCF,
      v5,
      v6,
      (__int64)&v60,
      (__int64)&v61,
      (__int64)&v63,
      (__int64)v62);
  }
  v8 = TransportState::Current();
  v9 = *((_QWORD *)v8 + 2);
  if ( v9 )
  {
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v9 + 8LL))(*((_QWORD *)v8 + 2));
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
    v10 = std::wstring::wstring(v64, a2);
    WindowsMidiServicesInternal::GetSwdPropertyVirtualEndpointAssociationId(v67, v10);
    if ( v68 )
    {
      EnterCriticalSection((LPCRITICAL_SECTION)lpCriticalSection);
      v65 = (LPCRITICAL_SECTION)lpCriticalSection;
      if ( *(_QWORD *)std::_Tree<std::_Tmap_traits<std::wstring,MidiVirtualDeviceEndpointEntry,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,MidiVirtualDeviceEndpointEntry>>,0>>::find(
                        lpCriticalSection + 20,
                        &v60,
                        v67) == *((_QWORD *)lpCriticalSection + 5) )
      {
        v47 = (_DWORD *)*((_QWORD *)MidiVirtualMidiTransportTelemetryProvider::Instance() + 1);
        if ( *v47 > 2u )
        {
          if ( a2[3] <= 7u )
            v50 = (const char *)a2;
          else
            v50 = (const char *)*a2;
          v60 = v50;
          v61 = L"Unexpected. There's no entry for associationId";
          v63 = lpCriticalSection;
          *(_QWORD *)v62 = "MidiEndpointTable::OnDeviceDisconnected";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
            (_DWORD)v47,
            (unsigned int)byte_1800269BB,
            v48,
            v49,
            (__int64)v62,
            (__int64)&v63,
            (__int64)&v61,
            (__int64)&v60);
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1CC,
          (unsigned int)"avcore\\midi2\\transport\\virtualmiditransport\\midiendpointtable.cpp",
          (const char *)0x80070057LL,
          v59);
        if ( lpCriticalSection )
          LeaveCriticalSection((LPCRITICAL_SECTION)lpCriticalSection);
        std::wstring::~wstring(v67);
        std::wstring::~wstring(a2);
        return 2147942487LL;
      }
      else
      {
        v11 = (const struct MidiVirtualDeviceEndpointEntry *)std::map<std::wstring,MidiVirtualDeviceEndpointEntry>::operator[](
                                                               lpCriticalSection + 20,
                                                               v67);
        MidiVirtualDeviceEndpointEntry::MidiVirtualDeviceEndpointEntry((MidiVirtualDeviceEndpointEntry *)v69, v11);
        if ( v72 )
        {
          v12 = (_DWORD *)*((_QWORD *)MidiVirtualMidiTransportTelemetryProvider::Instance() + 1);
          if ( *v12 > 5u )
          {
            v15 = (const char *)a2;
            if ( a2[3] > 7u )
              v15 = (const char *)*a2;
            v60 = v15;
            v61 = L"Unlinking from MidiDeviceBidi";
            v63 = lpCriticalSection;
            *(_QWORD *)v62 = "MidiEndpointTable::OnDeviceDisconnected";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
              (_DWORD)v12,
              (unsigned int)&word_180026B76,
              v13,
              v14,
              (__int64)v62,
              (__int64)&v63,
              (__int64)&v61,
              (__int64)&v60);
          }
          v16 = (_DWORD *)*((_QWORD *)MidiVirtualMidiTransportTelemetryProvider::Instance() + 1);
          if ( *v16 > 4u )
          {
            v19 = (const char *)a2;
            if ( a2[3] > 7u )
              v19 = (const char *)*a2;
            v60 = v19;
            v61 = L"Unlinking MIDI Client BiDi";
            v63 = lpCriticalSection;
            *(_QWORD *)v62 = "MidiEndpointTable::OnDeviceDisconnected";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
              (_DWORD)v16,
              (unsigned int)byte_180026B1D,
              v17,
              v18,
              (__int64)v62,
              (__int64)&v63,
              (__int64)&v61,
              (__int64)&v60);
          }
          v20 = v73;
          if ( v73 )
          {
            v21 = v73;
            v22 = *(_QWORD *)(v73 + 24);
            if ( v22 )
            {
              *(_QWORD *)(v73 + 24) = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
              v20 = v73;
            }
            v23 = *(_QWORD *)(v21 + 32);
            if ( v23 )
            {
              *(_QWORD *)(v21 + 32) = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
              v20 = v73;
            }
            v73 = 0;
            if ( v20 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
          }
          v24 = v72;
          v25 = *(_QWORD *)(v72 + 24);
          if ( v25 )
          {
            *(_QWORD *)(v72 + 24) = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
          }
          v26 = *(_QWORD *)(v24 + 32);
          if ( v26 )
          {
            *(_QWORD *)(v24 + 32) = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
          }
          v27 = v72;
          v72 = 0;
          if ( v27 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
          v28 = (_DWORD *)*((_QWORD *)MidiVirtualMidiTransportTelemetryProvider::Instance() + 1);
          if ( *v28 > 4u )
          {
            if ( a2[3] <= 7u )
              v31 = (const char *)a2;
            else
              v31 = (const char *)*a2;
            v60 = v31;
            v61 = L"Removing client visibile endpoint";
            v63 = lpCriticalSection;
            *(_QWORD *)v62 = "MidiEndpointTable::OnDeviceDisconnected";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
              (_DWORD)v28,
              (unsigned int)&dword_180026AC4,
              v29,
              v30,
              (__int64)v62,
              (__int64)&v63,
              (__int64)&v61,
              (__int64)&v60);
          }
          v32 = (const char *)*((_QWORD *)TransportState::Current() + 2);
          v60 = v32;
          if ( v32 )
            (*(void (__fastcall **)(const char *))(*(_QWORD *)v32 + 8LL))(v32);
          v33 = std::wstring::wstring(v64, v71);
          v34 = CMidi2VirtualMidiEndpointManager::DeleteClientEndpoint(v32, v33);
          if ( v34 < 0 )
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x1A2,
              (unsigned int)"avcore\\midi2\\transport\\virtualmiditransport\\midiendpointtable.cpp",
              (const char *)(unsigned int)v34,
              v59);
          if ( v32 )
            (*(void (__fastcall **)(const char *))(*(_QWORD *)v32 + 16LL))(v32);
          v35 = (_DWORD *)*((_QWORD *)MidiVirtualMidiTransportTelemetryProvider::Instance() + 1);
          if ( *v35 > 4u )
          {
            if ( a2[3] <= 7u )
              v38 = (const char *)a2;
            else
              v38 = (const char *)*a2;
            v60 = v38;
            v61 = L"Removing app host endpoint";
            v63 = lpCriticalSection;
            *(_QWORD *)v62 = "MidiEndpointTable::OnDeviceDisconnected";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
              (_DWORD)v35,
              (unsigned int)byte_180026A6B,
              v36,
              v37,
              (__int64)v62,
              (__int64)&v63,
              (__int64)&v61,
              (__int64)&v60);
          }
          v39 = (const char *)*((_QWORD *)TransportState::Current() + 2);
          v60 = v39;
          if ( v39 )
            (*(void (__fastcall **)(const char *))(*(_QWORD *)v39 + 8LL))(v39);
          v40 = std::wstring::wstring(v64, v70);
          v41 = CMidi2VirtualMidiEndpointManager::DeleteDeviceEndpoint(v39, v40);
          if ( v39 )
            (*(void (__fastcall **)(const char *))(*(_QWORD *)v39 + 16LL))(v39);
          if ( v41 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x1AF,
              (unsigned int)"avcore\\midi2\\transport\\virtualmiditransport\\midiendpointtable.cpp",
              (const char *)(unsigned int)v41,
              v59);
            MidiVirtualDeviceEndpointEntry::~MidiVirtualDeviceEndpointEntry((MidiVirtualDeviceEndpointEntry *)v69);
            LeaveCriticalSection((LPCRITICAL_SECTION)lpCriticalSection);
            std::wstring::~wstring(v67);
            std::wstring::~wstring(a2);
            return (unsigned int)v41;
          }
          std::_Tree<std::_Tmap_traits<std::wstring,MidiVirtualDeviceEndpointEntry,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,MidiVirtualDeviceEndpointEntry>>,0>>::erase(
            lpCriticalSection + 20,
            v69);
          v43 = (_DWORD *)*((_QWORD *)MidiVirtualMidiTransportTelemetryProvider::Instance() + 1);
          if ( *v43 > 5u )
          {
            if ( a2[3] <= 7u )
              v46 = (const char *)a2;
            else
              v46 = (const char *)*a2;
            v60 = v46;
            v61 = L"Endpoint teardown complete";
            v63 = lpCriticalSection;
            *(_QWORD *)v62 = "MidiEndpointTable::OnDeviceDisconnected";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
              (_DWORD)v43,
              (unsigned int)word_180026A12,
              v44,
              v45,
              (__int64)v62,
              (__int64)&v63,
              (__int64)&v61,
              (__int64)&v60);
          }
        }
        MidiVirtualDeviceEndpointEntry::~MidiVirtualDeviceEndpointEntry((MidiVirtualDeviceEndpointEntry *)v69);
        LeaveCriticalSection((LPCRITICAL_SECTION)lpCriticalSection);
        std::wstring::~wstring(v67);
        std::wstring::~wstring(a2);
        return 0;
      }
    }
    else
    {
      v51 = (_DWORD *)*((_QWORD *)MidiVirtualMidiTransportTelemetryProvider::Instance() + 1);
      if ( *v51 > 2u )
      {
        if ( a2[3] <= 7u )
          v54 = (const char *)a2;
        else
          v54 = (const char *)*a2;
        v60 = v54;
        v61 = L"Unable to get association id for this endpoint";
        v63 = lpCriticalSection;
        *(_QWORD *)v62 = "MidiEndpointTable::OnDeviceDisconnected";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
          (_DWORD)v51,
          (unsigned int)&dword_180026964,
          v52,
          v53,
          (__int64)v62,
          (__int64)&v63,
          (__int64)&v61,
          (__int64)&v60);
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1DB,
        (unsigned int)"avcore\\midi2\\transport\\virtualmiditransport\\midiendpointtable.cpp",
        (const char *)0x80070057LL,
        v59);
      std::wstring::~wstring(v67);
      std::wstring::~wstring(a2);
      return 2147942487LL;
    }
  }
  else
  {
    v55 = (_DWORD *)*((_QWORD *)MidiVirtualMidiTransportTelemetryProvider::Instance() + 1);
    if ( *v55 > 2u )
    {
      if ( a2[3] <= 7u )
        v58 = (const char *)a2;
      else
        v58 = (const char *)*a2;
      v60 = v58;
      v61 = L"Endpoint Manager is null";
      v63 = lpCriticalSection;
      *(_QWORD *)v62 = "MidiEndpointTable::OnDeviceDisconnected";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
        (_DWORD)v55,
        (unsigned int)byte_18002690D,
        v56,
        v57,
        (__int64)v62,
        (__int64)&v63,
        (__int64)&v61,
        (__int64)&v60);
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1EA,
      (unsigned int)"avcore\\midi2\\transport\\virtualmiditransport\\midiendpointtable.cpp",
      (const char *)0x80004003LL,
      v59);
    std::wstring::~wstring(a2);
    return 2147500035LL;
  }
}

```

## disassembly

```asm
0x180017670  mov     [rsp+arg_10], rbx
0x180017675  push    rsi
0x180017676  push    rdi
0x180017677  push    r12
0x180017679  push    r14
0x18001767b  push    r15
0x18001767d  sub     rsp, 200h
0x180017684  mov     rax, cs:__security_cookie
0x18001768b  xor     rax, rsp
0x18001768e  mov     [rsp+228h+var_38], rax
0x180017696  mov     rbx, rdx
0x180017699  mov     rsi, rcx
0x18001769c  mov     [rsp+228h+var_1A0], rdx
0x1800176a4  call    ?Instance@MidiVirtualMidiTransportTelemetryProvider@@KAPEAV1@XZ; MidiVirtualMidiTransportTelemetryProvider::Instance(void)
0x1800176a9  mov     rcx, [rax+8]
0x1800176ad  mov     eax, [rcx]
0x1800176af  cmp     eax, 4
0x1800176b2  jbe     short loc_18001771B
0x1800176b4  cmp     qword ptr [rbx+18h], 7
0x1800176b9  jbe     short loc_1800176C0
0x1800176bb  mov     rax, [rbx]
0x1800176be  jmp     short loc_1800176C3
0x1800176c0  mov     rax, rbx
0x1800176c3  mov     qword ptr [rsp+228h+var_1D8], rax
0x1800176c8  lea     rax, aEnter; "Enter"
0x1800176cf  mov     [rsp+228h+var_1D0], rax
0x1800176d4  mov     [rsp+228h+var_1E0], rsi
0x1800176d9  lea     r15, aMidiendpointta_0; "MidiEndpointTable::OnDeviceDisconnected"
0x1800176e0  mov     [rsp+228h+var_1E8], r15
0x1800176e5  lea     rax, [rsp+228h+var_1D8]
0x1800176ea  mov     [rsp+228h+var_1F0], rax
0x1800176ef  lea     rax, [rsp+228h+var_1D0]
0x1800176f4  mov     [rsp+228h+var_1F8], rax
0x1800176f9  lea     rax, [rsp+228h+var_1E0]
0x1800176fe  mov     [rsp+228h+var_200], rax
0x180017703  lea     rax, [rsp+228h+var_1E8]
0x180017708  mov     qword ptr [rsp+228h+var_208], rax
0x18001770d  lea     rdx, byte_180026BCF
0x180017714  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x180017719  jmp     short loc_180017722
0x18001771b  lea     r15, aMidiendpointta_0; "MidiEndpointTable::OnDeviceDisconnected"
0x180017722  call    ?Current@TransportState@@SAAEAV1@XZ; TransportState::Current(void)
0x180017727  mov     rdi, [rax+10h]
0x18001772b  test    rdi, rdi
0x18001772e  jz      short loc_180017740
0x180017730  mov     rax, [rdi]
0x180017733  mov     rcx, rdi
0x180017736  mov     rax, [rax+8]
0x18001773a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001773f  nop
0x180017740  test    rdi, rdi
0x180017743  jz      short loc_180017755
0x180017745  mov     rax, [rdi]
0x180017748  mov     rcx, rdi
0x18001774b  mov     rax, [rax+10h]
0x18001774f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017754  nop
0x180017755  test    rdi, rdi
0x180017758  jz      loc_180017DFE
0x18001775e  mov     rdx, rbx
0x180017761  lea     rcx, [rsp+228h+var_1C8]
0x180017766  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18001776b  mov     rdx, rax
0x18001776e  lea     rcx, [rsp+228h+var_198]
0x180017776  call    ?GetSwdPropertyVirtualEndpointAssociationId@WindowsMidiServicesInternal@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V23@@Z; WindowsMidiServicesInternal::GetSwdPropertyVirtualEndpointAssociationId(std::wstring)
0x18001777b  nop
0x18001777c  cmp     [rsp+228h+var_188], 0
0x180017785  jz      loc_180017D51
0x18001778b  mov     rcx, rsi; lpCriticalSection
0x18001778e  call    cs:__imp_EnterCriticalSection
0x180017794  mov     [rsp+228h+var_1A8], rsi
0x18001779c  lea     r12, [rsi+28h]
0x1800177a0  lea     r8, [rsp+228h+var_198]
0x1800177a8  lea     rdx, [rsp+228h+var_1E8]
0x1800177ad  mov     rcx, r12
0x1800177b0  call    ?find@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UMidiVirtualDeviceEndpointEntry@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UMidiVirtualDeviceEndpointEntry@@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UMidiVirtualDeviceEndpointEntry@@@std@@@std@@@std@@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Tree<std::_Tmap_traits<std::wstring,MidiVirtualDeviceEndpointEntry,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,MidiVirtualDeviceEndpointEntry>>,0>>::find(std::wstring const &)
0x1800177b5  mov     rcx, [r12]
0x1800177b9  cmp     [rax], rcx
0x1800177bc  jz      loc_180017C95
0x1800177c2  lea     rdx, [rsp+228h+var_198]
0x1800177ca  mov     rcx, r12
0x1800177cd  call    ??A?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UMidiVirtualDeviceEndpointEntry@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UMidiVirtualDeviceEndpointEntry@@@std@@@2@@std@@QEAAAEAUMidiVirtualDeviceEndpointEntry@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::map<std::wstring,MidiVirtualDeviceEndpointEntry>::operator[](std::wstring const &)
0x1800177d2  mov     rdx, rax; struct MidiVirtualDeviceEndpointEntry *
0x1800177d5  lea     rcx, [rsp+228h+var_178]; this
0x1800177dd  call    ??0MidiVirtualDeviceEndpointEntry@@QEAA@AEBU0@@Z; MidiVirtualDeviceEndpointEntry::MidiVirtualDeviceEndpointEntry(MidiVirtualDeviceEndpointEntry const &)
0x1800177e2  nop
0x1800177e3  cmp     [rsp+228h+var_50], 0
0x1800177ec  jz      loc_180017C6A
0x1800177f2  call    ?Instance@MidiVirtualMidiTransportTelemetryProvider@@KAPEAV1@XZ; MidiVirtualMidiTransportTelemetryProvider::Instance(void)
0x1800177f7  mov     rcx, [rax+8]
0x1800177fb  mov     eax, [rcx]
0x1800177fd  cmp     eax, 5
0x180017800  jbe     short loc_18001785E
0x180017802  mov     rax, rbx
0x180017805  cmp     qword ptr [rbx+18h], 7
0x18001780a  jbe     short loc_18001780F
0x18001780c  mov     rax, [rbx]
0x18001780f  mov     [rsp+228h+var_1E8], rax
0x180017814  lea     rax, aUnlinkingFromM; "Unlinking from MidiDeviceBidi"
0x18001781b  mov     [rsp+228h+var_1E0], rax
0x180017820  mov     [rsp+228h+var_1D0], rsi
0x180017825  mov     qword ptr [rsp+228h+var_1D8], r15
0x18001782a  lea     rax, [rsp+228h+var_1E8]
0x18001782f  mov     [rsp+228h+var_1F0], rax
0x180017834  lea     rax, [rsp+228h+var_1E0]
0x180017839  mov     [rsp+228h+var_1F8], rax
0x18001783e  lea     rax, [rsp+228h+var_1D0]
0x180017843  mov     [rsp+228h+var_200], rax
0x180017848  lea     rax, [rsp+228h+var_1D8]
0x18001784d  mov     qword ptr [rsp+228h+var_208], rax
0x180017852  lea     rdx, word_180026B76
0x180017859  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x18001785e  call    ?Instance@MidiVirtualMidiTransportTelemetryProvider@@KAPEAV1@XZ; MidiVirtualMidiTransportTelemetryProvider::Instance(void)
0x180017863  mov     rcx, [rax+8]
0x180017867  mov     eax, [rcx]
0x180017869  cmp     eax, 4
0x18001786c  jbe     short loc_1800178CA
0x18001786e  mov     rax, rbx
0x180017871  cmp     qword ptr [rbx+18h], 7
0x180017876  jbe     short loc_18001787B
0x180017878  mov     rax, [rbx]
0x18001787b  mov     [rsp+228h+var_1E8], rax
0x180017880  lea     rax, aUnlinkingMidiC; "Unlinking MIDI Client BiDi"
0x180017887  mov     [rsp+228h+var_1E0], rax
0x18001788c  mov     [rsp+228h+var_1D0], rsi
0x180017891  mov     qword ptr [rsp+228h+var_1D8], r15
0x180017896  lea     rax, [rsp+228h+var_1E8]
0x18001789b  mov     [rsp+228h+var_1F0], rax
0x1800178a0  lea     rax, [rsp+228h+var_1E0]
0x1800178a5  mov     [rsp+228h+var_1F8], rax
0x1800178aa  lea     rax, [rsp+228h+var_1D0]
0x1800178af  mov     [rsp+228h+var_200], rax
0x1800178b4  lea     rax, [rsp+228h+var_1D8]
0x1800178b9  mov     qword ptr [rsp+228h+var_208], rax
0x1800178be  lea     rdx, byte_180026B1D
0x1800178c5  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x1800178ca  mov     rcx, [rsp+228h+var_48]
0x1800178d2  test    rcx, rcx
0x1800178d5  jz      short loc_18001794A
0x1800178d7  mov     rdi, rcx
0x1800178da  mov     rdx, [rcx+18h]
0x1800178de  test    rdx, rdx
0x1800178e1  jz      short loc_180017903
0x1800178e3  mov     qword ptr [rcx+18h], 0
0x1800178eb  mov     rax, [rdx]
0x1800178ee  mov     rcx, rdx
0x1800178f1  mov     rax, [rax+10h]
0x1800178f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800178fa  nop
0x1800178fb  mov     rcx, [rsp+228h+var_48]
0x180017903  mov     rdx, [rdi+20h]
0x180017907  test    rdx, rdx
0x18001790a  jz      short loc_18001792C
0x18001790c  mov     qword ptr [rdi+20h], 0
0x180017914  mov     rax, [rdx]
0x180017917  mov     rcx, rdx
0x18001791a  mov     rax, [rax+10h]
0x18001791e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017923  nop
0x180017924  mov     rcx, [rsp+228h+var_48]
0x18001792c  mov     [rsp+228h+var_48], 0
0x180017938  test    rcx, rcx
0x18001793b  jz      short loc_18001794A
0x18001793d  mov     rax, [rcx]
0x180017940  mov     rax, [rax+10h]
0x180017944  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017949  nop
0x18001794a  mov     rdi, [rsp+228h+var_50]
0x180017952  mov     rcx, [rdi+18h]
0x180017956  test    rcx, rcx
0x180017959  jz      short loc_180017970
0x18001795b  mov     qword ptr [rdi+18h], 0
0x180017963  mov     rax, [rcx]
0x180017966  mov     rax, [rax+10h]
0x18001796a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001796f  nop
0x180017970  mov     rcx, [rdi+20h]
0x180017974  test    rcx, rcx
0x180017977  jz      short loc_18001798E
0x180017979  mov     qword ptr [rdi+20h], 0
0x180017981  mov     rax, [rcx]
0x180017984  mov     rax, [rax+10h]
0x180017988  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001798d  nop
0x18001798e  mov     rcx, [rsp+228h+var_50]
0x180017996  mov     [rsp+228h+var_50], 0
0x1800179a2  test    rcx, rcx
0x1800179a5  jz      short loc_1800179B4
0x1800179a7  mov     rax, [rcx]
0x1800179aa  mov     rax, [rax+10h]
0x1800179ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800179b3  nop
0x1800179b4  call    ?Instance@MidiVirtualMidiTransportTelemetryProvider@@KAPEAV1@XZ; MidiVirtualMidiTransportTelemetryProvider::Instance(void)
0x1800179b9  mov     rcx, [rax+8]
0x1800179bd  mov     eax, [rcx]
0x1800179bf  cmp     eax, 4
0x1800179c2  jbe     short loc_180017A22
0x1800179c4  cmp     qword ptr [rbx+18h], 7
0x1800179c9  jbe     short loc_1800179D0
0x1800179cb  mov     rax, [rbx]
0x1800179ce  jmp     short loc_1800179D3
0x1800179d0  mov     rax, rbx
0x1800179d3  mov     [rsp+228h+var_1E8], rax
0x1800179d8  lea     rax, aRemovingClient; "Removing client visibile endpoint"
0x1800179df  mov     [rsp+228h+var_1E0], rax
0x1800179e4  mov     [rsp+228h+var_1D0], rsi
0x1800179e9  mov     qword ptr [rsp+228h+var_1D8], r15
0x1800179ee  lea     rax, [rsp+228h+var_1E8]
0x1800179f3  mov     [rsp+228h+var_1F0], rax
0x1800179f8  lea     rax, [rsp+228h+var_1E0]
0x1800179fd  mov     [rsp+228h+var_1F8], rax
0x180017a02  lea     rax, [rsp+228h+var_1D0]
0x180017a07  mov     [rsp+228h+var_200], rax
0x180017a0c  lea     rax, [rsp+228h+var_1D8]
0x180017a11  mov     qword ptr [rsp+228h+var_208], rax; int
0x180017a16  lea     rdx, dword_180026AC4
0x180017a1d  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x180017a22  call    ?Current@TransportState@@SAAEAV1@XZ; TransportState::Current(void)
0x180017a27  mov     rdi, [rax+10h]
0x180017a2b  mov     [rsp+228h+var_1E8], rdi
0x180017a30  test    rdi, rdi
0x180017a33  jz      short loc_180017A45
0x180017a35  mov     rax, [rdi]
0x180017a38  mov     rcx, rdi
0x180017a3b  mov     rax, [rax+8]
0x180017a3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017a44  nop
0x180017a45  lea     rdx, [rsp+228h+var_78]
0x180017a4d  lea     rcx, [rsp+228h+var_1C8]
0x180017a52  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180017a57  mov     rdx, rax
0x180017a5a  mov     rcx, rdi
0x180017a5d  call    ?DeleteClientEndpoint@CMidi2VirtualMidiEndpointManager@@QEAAJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; CMidi2VirtualMidiEndpointManager::DeleteClientEndpoint(std::wstring)
0x180017a62  mov     rcx, [rsp+228h]; this
0x180017a6a  test    eax, eax
0x180017a6c  jns     short loc_180017A83
0x180017a6e  mov     r9d, eax; char *
0x180017a71  lea     r8, aAvcoreMidi2Tra_3; "avcore\\midi2\\transport\\virtualmiditr"...
0x180017a78  mov     edx, 1A2h; void *
0x180017a7d  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180017a82  nop
0x180017a83  test    rdi, rdi
0x180017a86  jz      short loc_180017A98
0x180017a88  mov     rax, [rdi]
0x180017a8b  mov     rcx, rdi
0x180017a8e  mov     rax, [rax+10h]
0x180017a92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017a97  nop
0x180017a98  call    ?Instance@MidiVirtualMidiTransportTelemetryProvider@@KAPEAV1@XZ; MidiVirtualMidiTransportTelemetryProvider::Instance(void)
0x180017a9d  mov     rcx, [rax+8]
0x180017aa1  mov     eax, [rcx]
0x180017aa3  cmp     eax, 4
0x180017aa6  jbe     short loc_180017B06
0x180017aa8  cmp     qword ptr [rbx+18h], 7
0x180017aad  jbe     short loc_180017AB4
0x180017aaf  mov     rax, [rbx]
0x180017ab2  jmp     short loc_180017AB7
0x180017ab4  mov     rax, rbx
0x180017ab7  mov     [rsp+228h+var_1E8], rax
0x180017abc  lea     rax, aRemovingAppHos; "Removing app host endpoint"
0x180017ac3  mov     [rsp+228h+var_1E0], rax
0x180017ac8  mov     [rsp+228h+var_1D0], rsi
0x180017acd  mov     qword ptr [rsp+228h+var_1D8], r15
0x180017ad2  lea     rax, [rsp+228h+var_1E8]
0x180017ad7  mov     [rsp+228h+var_1F0], rax
0x180017adc  lea     rax, [rsp+228h+var_1E0]
0x180017ae1  mov     [rsp+228h+var_1F8], rax
0x180017ae6  lea     rax, [rsp+228h+var_1D0]
0x180017aeb  mov     [rsp+228h+var_200], rax
0x180017af0  lea     rax, [rsp+228h+var_1D8]
0x180017af5  mov     qword ptr [rsp+228h+var_208], rax; int
0x180017afa  lea     rdx, byte_180026A6B
0x180017b01  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x180017b06  call    ?Current@TransportState@@SAAEAV1@XZ; TransportState::Current(void)
0x180017b0b  mov     rdi, [rax+10h]
0x180017b0f  mov     [rsp+228h+var_1E8], rdi
0x180017b14  test    rdi, rdi
0x180017b17  jz      short loc_180017B29
0x180017b19  mov     rax, [rdi]
0x180017b1c  mov     rcx, rdi
0x180017b1f  mov     rax, [rax+8]
0x180017b23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017b28  nop
0x180017b29  lea     rdx, [rsp+228h+var_B8]
0x180017b31  lea     rcx, [rsp+228h+var_1C8]
0x180017b36  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180017b3b  mov     rdx, rax
0x180017b3e  mov     rcx, rdi
0x180017b41  call    ?DeleteDeviceEndpoint@CMidi2VirtualMidiEndpointManager@@QEAAJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; CMidi2VirtualMidiEndpointManager::DeleteDeviceEndpoint(std::wstring)
0x180017b46  mov     r14d, eax
0x180017b49  test    rdi, rdi
0x180017b4c  jz      short loc_180017B5E
0x180017b4e  mov     rcx, [rdi]
0x180017b51  mov     rax, [rcx+10h]
0x180017b55  mov     rcx, rdi
0x180017b58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017b5d  nop
0x180017b5e  test    r14d, r14d
0x180017b61  jns     short loc_180017BB6
0x180017b63  mov     rcx, [rsp+228h]; this
  ... truncated ...
```
