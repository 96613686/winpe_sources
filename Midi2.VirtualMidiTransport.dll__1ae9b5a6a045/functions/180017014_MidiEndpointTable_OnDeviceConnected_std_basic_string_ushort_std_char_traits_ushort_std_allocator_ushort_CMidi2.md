# MidiEndpointTable::OnDeviceConnected(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,CMidi2VirtualMidiBidi *)

- ea: `0x180017014`
- end: `0x180017669`
- name: `?OnDeviceConnected@MidiEndpointTable@@QEAAJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCMidi2VirtualMidiBidi@@@Z`
- size: `1621`
- prototype: `__int64 __fastcall(wchar_t *lpCriticalSection, const char **, __int64)`
- caller_count: `1`
- callee_count: `17`
- tags: `authz_impersonation, service_task`

## callers

- `0x18001b1b0`

## callees

- `0x180001878`
- `0x1800038f0`
- `0x180009784`
- `0x18000b5f8`
- `0x18000bf6c`
- `0x18000d1ac`
- `0x18000d9b4`
- `0x1800119f4`
- `0x1800136f0`
- `0x180014484`
- `0x1800146f4`
- `0x180014830`
- `0x1800159c8`
- `0x180017014`
- `0x180019850`
- `0x18001adc4`
- `0x180021010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800170fb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800170fb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800172c4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001731b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800173e0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800174a5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180017561`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800172c4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001731b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800173e0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800174a5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180017561`

## string_xrefs

- `0x180017449`: `Device-side was already connected`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall MidiEndpointTable::OnDeviceConnected(wchar_t *lpCriticalSection, const char **a2, __int64 a3)
{
  struct MidiVirtualMidiTransportTelemetryProvider *v6; // rax
  int v7; // r8d
  int v8; // r9d
  _DWORD *v9; // rcx
  const char *v10; // rax
  __int64 v11; // rax
  const struct MidiVirtualDeviceEndpointEntry *v12; // rax
  __int64 v13; // rax
  struct TransportState *v14; // rax
  __int64 v15; // rdi
  _WORD *v16; // rcx
  _WORD *v17; // rcx
  __int64 v18; // rcx
  CMidi2VirtualMidiEndpointManager *v19; // rdi
  int ClientVisibleEndpoint; // r14d
  unsigned int v21; // r8d
  const char *v22; // r9
  __int64 result; // rax
  __int64 v24; // rax
  _DWORD *v25; // rcx
  int v26; // r8d
  int v27; // r9d
  const char *v28; // rax
  _DWORD *v29; // rcx
  int v30; // r8d
  int v31; // r9d
  const char *v32; // rax
  _DWORD *v33; // rcx
  int v34; // r8d
  int v35; // r9d
  const char *v36; // rax
  _DWORD *v37; // rcx
  int v38; // r8d
  int v39; // r9d
  const char *v40; // rax
  int v41; // [rsp+20h] [rbp-1F8h]
  const char *v42; // [rsp+40h] [rbp-1D8h] BYREF
  const wchar_t *v43; // [rsp+48h] [rbp-1D0h] BYREF
  const char *v44; // [rsp+50h] [rbp-1C8h] BYREF
  const wchar_t *v45; // [rsp+58h] [rbp-1C0h] BYREF
  _BYTE v46[32]; // [rsp+60h] [rbp-1B8h] BYREF
  const char **v47; // [rsp+80h] [rbp-198h]
  _BYTE v48[16]; // [rsp+88h] [rbp-190h] BYREF
  __int64 v49; // [rsp+98h] [rbp-180h]
  _BYTE v50[224]; // [rsp+B0h] [rbp-168h] BYREF
  _QWORD v51[4]; // [rsp+190h] [rbp-88h] BYREF
  _QWORD v52[5]; // [rsp+1B0h] [rbp-68h] BYREF
  __int64 v53; // [rsp+1D8h] [rbp-40h]
  __int64 v54; // [rsp+1E0h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+218h] [rbp+0h]

  v47 = a2;
  v6 = MidiVirtualMidiTransportTelemetryProvider::Instance();
  v9 = (_DWORD *)*((_QWORD *)v6 + 1);
  if ( *v9 > 4u )
  {
    if ( (unsigned __int64)a2[3] <= 7 )
      v10 = (const char *)a2;
    else
      v10 = *a2;
    v42 = v10;
    v45 = L"Enter";
    v43 = lpCriticalSection;
    v44 = "MidiEndpointTable::OnDeviceConnected";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
      (_DWORD)v9,
      (unsigned int)byte_180026D81,
      v7,
      v8,
      (__int64)&v44,
      (__int64)&v43,
      (__int64)&v45,
      (__int64)&v42);
  }
  try
  {
    v11 = std::wstring::wstring(v46, a2);
    WindowsMidiServicesInternal::GetSwdPropertyVirtualEndpointAssociationId(v48, v11);
    if ( v49 )
    {
      EnterCriticalSection((LPCRITICAL_SECTION)lpCriticalSection);
      v44 = (const char *)lpCriticalSection;
      if ( *(_QWORD *)std::_Tree<std::_Tmap_traits<std::wstring,MidiVirtualDeviceEndpointEntry,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,MidiVirtualDeviceEndpointEntry>>,0>>::find(
                        lpCriticalSection + 20,
                        &v43,
                        v48) != *((_QWORD *)lpCriticalSection + 5) )
      {
        v12 = (const struct MidiVirtualDeviceEndpointEntry *)std::map<std::wstring,MidiVirtualDeviceEndpointEntry>::operator[](
                                                               lpCriticalSection + 20,
                                                               v48);
        MidiVirtualDeviceEndpointEntry::MidiVirtualDeviceEndpointEntry((MidiVirtualDeviceEndpointEntry *)v50, v12);
        if ( v53 )
        {
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x105,
            (unsigned int)"avcore\\midi2\\transport\\virtualmiditransport\\midiendpointtable.cpp",
            (const char *)0x80004005LL,
            v41);
          v29 = (_DWORD *)*((_QWORD *)MidiVirtualMidiTransportTelemetryProvider::Instance() + 1);
          if ( *v29 > 2u )
          {
            if ( (unsigned __int64)a2[3] <= 7 )
              v32 = (const char *)a2;
            else
              v32 = *a2;
            v44 = v32;
            v43 = L"Device-side was already connected";
            v45 = lpCriticalSection;
            v42 = "MidiEndpointTable::OnDeviceConnected";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
              (_DWORD)v29,
              (unsigned int)word_180026D2A,
              v30,
              v31,
              (__int64)&v42,
              (__int64)&v45,
              (__int64)&v43,
              (__int64)&v44);
          }
        }
        else
        {
          v53 = a3;
          if ( a3 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)a3 + 8LL))(a3);
          v13 = std::map<std::wstring,MidiVirtualDeviceEndpointEntry>::operator[](lpCriticalSection + 20, v48);
          MidiVirtualDeviceEndpointEntry::operator=(v13, v50);
          v14 = TransportState::Current();
          v15 = *((_QWORD *)v14 + 2);
          if ( v15 )
          {
            (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v15 + 8LL))(*((_QWORD *)v14 + 2));
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
            v16 = v51;
            if ( v51[3] > 7u )
              v16 = (_WORD *)v51[0];
            v51[2] = 0;
            *v16 = 0;
            v17 = v52;
            if ( v52[3] > 7u )
              v17 = (_WORD *)v52[0];
            v52[2] = 0;
            *v17 = 0;
            v18 = v54;
            v54 = 0;
            if ( v18 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
            v19 = (CMidi2VirtualMidiEndpointManager *)*((_QWORD *)TransportState::Current() + 2);
            v43 = (const wchar_t *)v19;
            if ( v19 )
              (*(void (__fastcall **)(CMidi2VirtualMidiEndpointManager *))(*(_QWORD *)v19 + 8LL))(v19);
            ClientVisibleEndpoint = CMidi2VirtualMidiEndpointManager::CreateClientVisibleEndpoint(
                                      v19,
                                      (struct MidiVirtualDeviceEndpointEntry *)v50);
            if ( v19 )
              (*(void (__fastcall **)(CMidi2VirtualMidiEndpointManager *))(*(_QWORD *)v19 + 16LL))(v19);
            if ( ClientVisibleEndpoint >= 0 )
            {
              v24 = std::map<std::wstring,MidiVirtualDeviceEndpointEntry>::operator[](lpCriticalSection + 20, v48);
              MidiVirtualDeviceEndpointEntry::operator=(v24, v50);
              MidiVirtualDeviceEndpointEntry::~MidiVirtualDeviceEndpointEntry((MidiVirtualDeviceEndpointEntry *)v50);
              LeaveCriticalSection((LPCRITICAL_SECTION)lpCriticalSection);
              std::wstring::~wstring(v48);
              std::wstring::~wstring(a2);
              return 0;
            }
            else
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x11C,
                (unsigned int)"avcore\\midi2\\transport\\virtualmiditransport\\midiendpointtable.cpp",
                (const char *)(unsigned int)ClientVisibleEndpoint,
                v41);
              MidiVirtualDeviceEndpointEntry::~MidiVirtualDeviceEndpointEntry((MidiVirtualDeviceEndpointEntry *)v50);
              LeaveCriticalSection((LPCRITICAL_SECTION)lpCriticalSection);
              std::wstring::~wstring(v48);
              std::wstring::~wstring(a2);
              return (unsigned int)ClientVisibleEndpoint;
            }
          }
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x122,
            (unsigned int)"avcore\\midi2\\transport\\virtualmiditransport\\midiendpointtable.cpp",
            (const char *)0x80004005LL,
            v41);
          v25 = (_DWORD *)*((_QWORD *)MidiVirtualMidiTransportTelemetryProvider::Instance() + 1);
          if ( *v25 > 2u )
          {
            if ( (unsigned __int64)a2[3] <= 7 )
              v28 = (const char *)a2;
            else
              v28 = *a2;
            v44 = v28;
            v43 = L"Endpoint Manager is null";
            v45 = lpCriticalSection;
            v42 = "MidiEndpointTable::OnDeviceConnected";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
              (_DWORD)v25,
              (unsigned int)byte_180026CD3,
              v26,
              v27,
              (__int64)&v42,
              (__int64)&v45,
              (__int64)&v43,
              (__int64)&v44);
          }
        }
        MidiVirtualDeviceEndpointEntry::~MidiVirtualDeviceEndpointEntry((MidiVirtualDeviceEndpointEntry *)v50);
        LeaveCriticalSection((LPCRITICAL_SECTION)lpCriticalSection);
        std::wstring::~wstring(v48);
        std::wstring::~wstring(a2);
        return 2147500037LL;
      }
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x134,
        (unsigned int)"avcore\\midi2\\transport\\virtualmiditransport\\midiendpointtable.cpp",
        (const char *)0x80004005LL,
        v41);
      v33 = (_DWORD *)*((_QWORD *)MidiVirtualMidiTransportTelemetryProvider::Instance() + 1);
      if ( *v33 > 2u )
      {
        if ( (unsigned __int64)a2[3] <= 7 )
          v36 = (const char *)a2;
        else
          v36 = *a2;
        v44 = v36;
        v43 = L"Association id property was not present in device table";
        v45 = lpCriticalSection;
        v42 = "MidiEndpointTable::OnDeviceConnected";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
          (_DWORD)v33,
          (unsigned int)&dword_180026C7C,
          v34,
          v35,
          (__int64)&v42,
          (__int64)&v45,
          (__int64)&v43,
          (__int64)&v44);
      }
      if ( lpCriticalSection )
        LeaveCriticalSection((LPCRITICAL_SECTION)lpCriticalSection);
    }
    else
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x146,
        (unsigned int)"avcore\\midi2\\transport\\virtualmiditransport\\midiendpointtable.cpp",
        (const char *)0x80004005LL,
        v41);
      v37 = (_DWORD *)*((_QWORD *)MidiVirtualMidiTransportTelemetryProvider::Instance() + 1);
      if ( *v37 > 2u )
      {
        if ( (unsigned __int64)a2[3] <= 7 )
          v40 = (const char *)a2;
        else
          v40 = *a2;
        v44 = v40;
        v43 = L"Association id property was blank";
        v45 = lpCriticalSection;
        v42 = "MidiEndpointTable::OnDeviceConnected";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
          (_DWORD)v37,
          (unsigned int)byte_180026C25,
          v38,
          v39,
          (__int64)&v42,
          (__int64)&v45,
          (__int64)&v43,
          (__int64)&v44);
      }
    }
    std::wstring::~wstring(v48);
    std::wstring::~wstring(a2);
    result = 2147500037LL;
  }
  catch ( ... )
  {
    LODWORD(v42) = wil::details::in1diag3::Return_CaughtException(retaddr, (void *)0x155, v21, v22);
    std::wstring::~wstring(v47);
    return (unsigned int)v42;
  }
  return result;
}

```

## disassembly

```asm
0x180017014  mov     [rsp+arg_10], rbx
0x180017019  mov     [rsp+arg_18], rsi
0x18001701e  push    rdi
0x18001701f  push    r14
0x180017021  push    r15
0x180017023  sub     rsp, 200h
0x18001702a  mov     rax, cs:__security_cookie
0x180017031  xor     rax, rsp
0x180017034  mov     [rsp+218h+var_28], rax
0x18001703c  mov     rdi, r8
0x18001703f  mov     rbx, rdx
0x180017042  mov     rsi, rcx
0x180017045  mov     [rsp+218h+var_198], rdx
0x18001704d  call    ?Instance@MidiVirtualMidiTransportTelemetryProvider@@KAPEAV1@XZ; MidiVirtualMidiTransportTelemetryProvider::Instance(void)
0x180017052  mov     rcx, [rax+8]
0x180017056  mov     eax, [rcx]
0x180017058  cmp     eax, 4
0x18001705b  jbe     short loc_1800170C4
0x18001705d  cmp     qword ptr [rbx+18h], 7
0x180017062  jbe     short loc_180017069
0x180017064  mov     rax, [rbx]
0x180017067  jmp     short loc_18001706C
0x180017069  mov     rax, rbx
0x18001706c  mov     [rsp+218h+var_1D8], rax
0x180017071  lea     rax, aEnter; "Enter"
0x180017078  mov     [rsp+218h+var_1C0], rax
0x18001707d  mov     [rsp+218h+var_1D0], rsi
0x180017082  lea     r14, aMidiendpointta_4; "MidiEndpointTable::OnDeviceConnected"
0x180017089  mov     [rsp+218h+var_1C8], r14
0x18001708e  lea     rax, [rsp+218h+var_1D8]
0x180017093  mov     [rsp+218h+var_1E0], rax
0x180017098  lea     rax, [rsp+218h+var_1C0]
0x18001709d  mov     [rsp+218h+var_1E8], rax
0x1800170a2  lea     rax, [rsp+218h+var_1D0]
0x1800170a7  mov     [rsp+218h+var_1F0], rax
0x1800170ac  lea     rax, [rsp+218h+var_1C8]
0x1800170b1  mov     [rsp+218h+var_1F8], rax
0x1800170b6  lea     rdx, byte_180026D81
0x1800170bd  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x1800170c2  jmp     short loc_1800170CB
0x1800170c4  lea     r14, aMidiendpointta_4; "MidiEndpointTable::OnDeviceConnected"
0x1800170cb  mov     rdx, rbx
0x1800170ce  lea     rcx, [rsp+218h+var_1B8]
0x1800170d3  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800170d8  mov     rdx, rax
0x1800170db  lea     rcx, [rsp+218h+var_190]
0x1800170e3  call    ?GetSwdPropertyVirtualEndpointAssociationId@WindowsMidiServicesInternal@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V23@@Z; WindowsMidiServicesInternal::GetSwdPropertyVirtualEndpointAssociationId(std::wstring)
0x1800170e8  nop
0x1800170e9  cmp     [rsp+218h+var_180], 0
0x1800170f2  jz      loc_180017585
0x1800170f8  mov     rcx, rsi; lpCriticalSection
0x1800170fb  call    cs:__imp_EnterCriticalSection
0x180017101  mov     [rsp+218h+var_1C8], rsi
0x180017106  lea     r15, [rsi+28h]
0x18001710a  lea     r8, [rsp+218h+var_190]
0x180017112  lea     rdx, [rsp+218h+var_1D0]
0x180017117  mov     rcx, r15
0x18001711a  call    ?find@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UMidiVirtualDeviceEndpointEntry@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UMidiVirtualDeviceEndpointEntry@@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UMidiVirtualDeviceEndpointEntry@@@std@@@std@@@std@@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Tree<std::_Tmap_traits<std::wstring,MidiVirtualDeviceEndpointEntry,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,MidiVirtualDeviceEndpointEntry>>,0>>::find(std::wstring const &)
0x18001711f  mov     rcx, [r15]
0x180017122  cmp     [rax], rcx
0x180017125  jz      loc_1800174C9
0x18001712b  lea     rdx, [rsp+218h+var_190]
0x180017133  mov     rcx, r15
0x180017136  call    ??A?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UMidiVirtualDeviceEndpointEntry@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UMidiVirtualDeviceEndpointEntry@@@std@@@2@@std@@QEAAAEAUMidiVirtualDeviceEndpointEntry@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::map<std::wstring,MidiVirtualDeviceEndpointEntry>::operator[](std::wstring const &)
0x18001713b  mov     rdx, rax; struct MidiVirtualDeviceEndpointEntry *
0x18001713e  lea     rcx, [rsp+218h+var_168]; this
0x180017146  call    ??0MidiVirtualDeviceEndpointEntry@@QEAA@AEBU0@@Z; MidiVirtualDeviceEndpointEntry::MidiVirtualDeviceEndpointEntry(MidiVirtualDeviceEndpointEntry const &)
0x18001714b  nop
0x18001714c  cmp     [rsp+218h+var_40], 0
0x180017155  jnz     loc_180017404
0x18001715b  mov     [rsp+218h+var_40], rdi
0x180017163  test    rdi, rdi
0x180017166  jz      short loc_180017178
0x180017168  mov     rax, [rdi]
0x18001716b  mov     rcx, rdi
0x18001716e  mov     rax, [rax+8]
0x180017172  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017177  nop
0x180017178  lea     rdx, [rsp+218h+var_190]
0x180017180  mov     rcx, r15
0x180017183  call    ??A?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UMidiVirtualDeviceEndpointEntry@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UMidiVirtualDeviceEndpointEntry@@@std@@@2@@std@@QEAAAEAUMidiVirtualDeviceEndpointEntry@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::map<std::wstring,MidiVirtualDeviceEndpointEntry>::operator[](std::wstring const &)
0x180017188  lea     rdx, [rsp+218h+var_168]
0x180017190  mov     rcx, rax
0x180017193  call    ??4MidiVirtualDeviceEndpointEntry@@QEAAAEAU0@AEBU0@@Z; MidiVirtualDeviceEndpointEntry::operator=(MidiVirtualDeviceEndpointEntry const &)
0x180017198  call    ?Current@TransportState@@SAAEAV1@XZ; TransportState::Current(void)
0x18001719d  mov     rdi, [rax+10h]
0x1800171a1  test    rdi, rdi
0x1800171a4  jz      short loc_1800171B6
0x1800171a6  mov     rax, [rdi]
0x1800171a9  mov     rcx, rdi
0x1800171ac  mov     rax, [rax+8]
0x1800171b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800171b5  nop
0x1800171b6  test    rdi, rdi
0x1800171b9  jz      short loc_1800171CB
0x1800171bb  mov     rax, [rdi]
0x1800171be  mov     rcx, rdi
0x1800171c1  mov     rax, [rax+10h]
0x1800171c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800171ca  nop
0x1800171cb  test    rdi, rdi
0x1800171ce  jz      loc_18001733F
0x1800171d4  lea     rcx, [rsp+218h+var_88]
0x1800171dc  cmp     [rsp+218h+var_70], 7
0x1800171e5  cmova   rcx, [rsp+218h+var_88]
0x1800171ee  mov     [rsp+218h+var_78], 0
0x1800171fa  xor     eax, eax
0x1800171fc  mov     [rcx], ax
0x1800171ff  lea     rcx, [rsp+218h+var_68]
0x180017207  cmp     [rsp+218h+var_50], 7
0x180017210  cmova   rcx, [rsp+218h+var_68]
0x180017219  mov     [rsp+218h+var_58], rax
0x180017221  mov     [rcx], ax
0x180017224  mov     rcx, [rsp+218h+var_38]
0x18001722c  mov     [rsp+218h+var_38], rax
0x180017234  test    rcx, rcx
0x180017237  jz      short loc_180017246
0x180017239  mov     rax, [rcx]
0x18001723c  mov     rax, [rax+10h]
0x180017240  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017245  nop
0x180017246  call    ?Current@TransportState@@SAAEAV1@XZ; TransportState::Current(void)
0x18001724b  mov     rdi, [rax+10h]
0x18001724f  mov     [rsp+218h+var_1D0], rdi
0x180017254  test    rdi, rdi
0x180017257  jz      short loc_180017269
0x180017259  mov     rax, [rdi]
0x18001725c  mov     rcx, rdi
0x18001725f  mov     rax, [rax+8]
0x180017263  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017268  nop
0x180017269  lea     rdx, [rsp+218h+var_168]; struct MidiVirtualDeviceEndpointEntry *
0x180017271  mov     rcx, rdi; this
0x180017274  call    ?CreateClientVisibleEndpoint@CMidi2VirtualMidiEndpointManager@@QEAAJAEAUMidiVirtualDeviceEndpointEntry@@@Z; CMidi2VirtualMidiEndpointManager::CreateClientVisibleEndpoint(MidiVirtualDeviceEndpointEntry &)
0x180017279  mov     r14d, eax
0x18001727c  test    rdi, rdi
0x18001727f  jz      short loc_180017291
0x180017281  mov     rcx, [rdi]
0x180017284  mov     rax, [rcx+10h]
0x180017288  mov     rcx, rdi
0x18001728b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017290  nop
0x180017291  test    r14d, r14d
0x180017294  jns     short loc_1800172E9
0x180017296  mov     rcx, [rsp+218h]; this
0x18001729e  mov     r9d, r14d; char *
0x1800172a1  lea     r8, aAvcoreMidi2Tra_3; "avcore\\midi2\\transport\\virtualmiditr"...
0x1800172a8  mov     edx, 11Ch; void *
0x1800172ad  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800172b2  nop
0x1800172b3  lea     rcx, [rsp+218h+var_168]; this
0x1800172bb  call    ??1MidiVirtualDeviceEndpointEntry@@QEAA@XZ; MidiVirtualDeviceEndpointEntry::~MidiVirtualDeviceEndpointEntry(void)
0x1800172c0  nop
0x1800172c1  mov     rcx, rsi; lpCriticalSection
0x1800172c4  call    cs:__imp_LeaveCriticalSection
0x1800172ca  nop
0x1800172cb  lea     rcx, [rsp+218h+var_190]
0x1800172d3  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800172d8  nop
0x1800172d9  mov     rcx, rbx
0x1800172dc  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800172e1  mov     eax, r14d
0x1800172e4  jmp     loc_180017640
0x1800172e9  lea     rdx, [rsp+218h+var_190]
0x1800172f1  mov     rcx, r15
0x1800172f4  call    ??A?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UMidiVirtualDeviceEndpointEntry@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UMidiVirtualDeviceEndpointEntry@@@std@@@2@@std@@QEAAAEAUMidiVirtualDeviceEndpointEntry@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::map<std::wstring,MidiVirtualDeviceEndpointEntry>::operator[](std::wstring const &)
0x1800172f9  lea     rdx, [rsp+218h+var_168]
0x180017301  mov     rcx, rax
0x180017304  call    ??4MidiVirtualDeviceEndpointEntry@@QEAAAEAU0@AEBU0@@Z; MidiVirtualDeviceEndpointEntry::operator=(MidiVirtualDeviceEndpointEntry const &)
0x180017309  nop
0x18001730a  lea     rcx, [rsp+218h+var_168]; this
0x180017312  call    ??1MidiVirtualDeviceEndpointEntry@@QEAA@XZ; MidiVirtualDeviceEndpointEntry::~MidiVirtualDeviceEndpointEntry(void)
0x180017317  nop
0x180017318  mov     rcx, rsi; lpCriticalSection
0x18001731b  call    cs:__imp_LeaveCriticalSection
0x180017321  nop
0x180017322  lea     rcx, [rsp+218h+var_190]
0x18001732a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001732f  nop
0x180017330  mov     rcx, rbx
0x180017333  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180017338  xor     eax, eax
0x18001733a  jmp     loc_180017640
0x18001733f  mov     rcx, [rsp+218h]; this
0x180017347  mov     edi, 80004005h
0x18001734c  mov     r9d, edi; char *
0x18001734f  lea     r8, aAvcoreMidi2Tra_3; "avcore\\midi2\\transport\\virtualmiditr"...
0x180017356  mov     edx, 122h; void *
0x18001735b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180017360  call    ?Instance@MidiVirtualMidiTransportTelemetryProvider@@KAPEAV1@XZ; MidiVirtualMidiTransportTelemetryProvider::Instance(void)
0x180017365  mov     rcx, [rax+8]
0x180017369  mov     eax, [rcx]
0x18001736b  cmp     eax, 2
0x18001736e  jbe     short loc_1800173CF
0x180017370  cmp     qword ptr [rbx+18h], 7
0x180017375  jbe     short loc_18001737C
0x180017377  mov     rax, [rbx]
0x18001737a  jmp     short loc_18001737F
0x18001737c  mov     rax, rbx
0x18001737f  mov     [rsp+218h+var_1C8], rax
0x180017384  lea     rax, aEndpointManage; "Endpoint Manager is null"
0x18001738b  mov     [rsp+218h+var_1D0], rax
0x180017390  mov     [rsp+218h+var_1C0], rsi
0x180017395  mov     [rsp+218h+var_1D8], r14
0x18001739a  lea     rax, [rsp+218h+var_1C8]
0x18001739f  mov     [rsp+218h+var_1E0], rax
0x1800173a4  lea     rax, [rsp+218h+var_1D0]
0x1800173a9  mov     [rsp+218h+var_1E8], rax
0x1800173ae  lea     rax, [rsp+218h+var_1C0]
0x1800173b3  mov     [rsp+218h+var_1F0], rax
0x1800173b8  lea     rax, [rsp+218h+var_1D8]
0x1800173bd  mov     [rsp+218h+var_1F8], rax
0x1800173c2  lea     rdx, byte_180026CD3
0x1800173c9  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x1800173ce  nop
0x1800173cf  lea     rcx, [rsp+218h+var_168]; this
0x1800173d7  call    ??1MidiVirtualDeviceEndpointEntry@@QEAA@XZ; MidiVirtualDeviceEndpointEntry::~MidiVirtualDeviceEndpointEntry(void)
0x1800173dc  nop
0x1800173dd  mov     rcx, rsi; lpCriticalSection
0x1800173e0  call    cs:__imp_LeaveCriticalSection
0x1800173e6  nop
0x1800173e7  lea     rcx, [rsp+218h+var_190]
0x1800173ef  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800173f4  nop
0x1800173f5  mov     rcx, rbx
0x1800173f8  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800173fd  mov     eax, edi
0x1800173ff  jmp     loc_180017640
0x180017404  mov     rcx, [rsp+218h]; this
0x18001740c  mov     edi, 80004005h
0x180017411  mov     r9d, edi; char *
0x180017414  lea     r8, aAvcoreMidi2Tra_3; "avcore\\midi2\\transport\\virtualmiditr"...
0x18001741b  mov     edx, 105h; void *
0x180017420  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180017425  call    ?Instance@MidiVirtualMidiTransportTelemetryProvider@@KAPEAV1@XZ; MidiVirtualMidiTransportTelemetryProvider::Instance(void)
0x18001742a  mov     rcx, [rax+8]
0x18001742e  mov     eax, [rcx]
0x180017430  cmp     eax, 2
0x180017433  jbe     short loc_180017494
0x180017435  cmp     qword ptr [rbx+18h], 7
0x18001743a  jbe     short loc_180017441
0x18001743c  mov     rax, [rbx]
0x18001743f  jmp     short loc_180017444
0x180017441  mov     rax, rbx
0x180017444  mov     [rsp+218h+var_1C8], rax
0x180017449  lea     rax, aDeviceSideWasA; "Device-side was already connected"
0x180017450  mov     [rsp+218h+var_1D0], rax
0x180017455  mov     [rsp+218h+var_1C0], rsi
0x18001745a  mov     [rsp+218h+var_1D8], r14
0x18001745f  lea     rax, [rsp+218h+var_1C8]
0x180017464  mov     [rsp+218h+var_1E0], rax
0x180017469  lea     rax, [rsp+218h+var_1D0]
0x18001746e  mov     [rsp+218h+var_1E8], rax
0x180017473  lea     rax, [rsp+218h+var_1C0]
0x180017478  mov     [rsp+218h+var_1F0], rax
0x18001747d  lea     rax, [rsp+218h+var_1D8]
0x180017482  mov     [rsp+218h+var_1F8], rax
0x180017487  lea     rdx, word_180026D2A
0x18001748e  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x180017493  nop
0x180017494  lea     rcx, [rsp+218h+var_168]; this
0x18001749c  call    ??1MidiVirtualDeviceEndpointEntry@@QEAA@XZ; MidiVirtualDeviceEndpointEntry::~MidiVirtualDeviceEndpointEntry(void)
0x1800174a1  nop
0x1800174a2  mov     rcx, rsi; lpCriticalSection
0x1800174a5  call    cs:__imp_LeaveCriticalSection
0x1800174ab  nop
0x1800174ac  lea     rcx, [rsp+218h+var_190]
0x1800174b4  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800174b9  nop
0x1800174ba  mov     rcx, rbx
0x1800174bd  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800174c2  mov     eax, edi
0x1800174c4  jmp     loc_180017640
0x1800174c9  mov     rcx, [rsp+218h]; this
0x1800174d1  mov     edi, 80004005h
0x1800174d6  mov     r9d, edi; char *
0x1800174d9  lea     r8, aAvcoreMidi2Tra_3; "avcore\\midi2\\transport\\virtualmiditr"...
0x1800174e0  mov     edx, 134h; void *
0x1800174e5  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800174ea  call    ?Instance@MidiVirtualMidiTransportTelemetryProvider@@KAPEAV1@XZ; MidiVirtualMidiTransportTelemetryProvider::Instance(void)
0x1800174ef  mov     rcx, [rax+8]
0x1800174f3  mov     eax, [rcx]
0x1800174f5  cmp     eax, 2
0x1800174f8  jbe     short loc_180017559
0x1800174fa  cmp     qword ptr [rbx+18h], 7
0x1800174ff  jbe     short loc_180017506
0x180017501  mov     rax, [rbx]
0x180017504  jmp     short loc_180017509
0x180017506  mov     rax, rbx
0x180017509  mov     [rsp+218h+var_1C8], rax
0x18001750e  lea     rax, aAssociationIdP; "Association id property was not present"...
0x180017515  mov     [rsp+218h+var_1D0], rax
0x18001751a  mov     [rsp+218h+var_1C0], rsi
0x18001751f  mov     [rsp+218h+var_1D8], r14
0x180017524  lea     rax, [rsp+218h+var_1C8]
0x180017529  mov     [rsp+218h+var_1E0], rax
0x18001752e  lea     rax, [rsp+218h+var_1D0]
0x180017533  mov     [rsp+218h+var_1E8], rax
0x180017538  lea     rax, [rsp+218h+var_1C0]
0x18001753d  mov     [rsp+218h+var_1F0], rax
  ... truncated ...
```
