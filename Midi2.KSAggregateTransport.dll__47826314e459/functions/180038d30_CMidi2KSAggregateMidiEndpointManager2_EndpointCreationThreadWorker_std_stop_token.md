# CMidi2KSAggregateMidiEndpointManager2::EndpointCreationThreadWorker(std::stop_token)

- ea: `0x180038d30`
- end: `0x18003936d`
- name: `?EndpointCreationThreadWorker@CMidi2KSAggregateMidiEndpointManager2@@AEAAXVstop_token@std@@@Z`
- size: `1597`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1800016dc`
- `0x180005044`
- `0x180008950`
- `0x18000c684`
- `0x1800117d8`
- `0x180019924`
- `0x180036d5c`
- `0x180038d30`
- `0x18005e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180038ff3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180038ff3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180039182`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180039182`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180039286`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180039286`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180038dd4`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180038f1f`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180038dd4`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180038f1f`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180038e5d`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180038ed4`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180038ef1`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800391f4`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180039215`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180038e5d`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180038ed4`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180038ef1`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800391f4`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180039215`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180038f12`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180038f12`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180038f7d`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180038f7d`

## string_xrefs

- `0x180038d5d`: `CMidi2KSAggregateMidiEndpointManager2::EndpointCreationThreadWorker`
- `0x180038f3a`: `CMidi2KSAggregateMidiEndpointManager2::EndpointCreationThreadWorker`
- `0x18003913b`: `CMidi2KSAggregateMidiEndpointManager2::EndpointCreationThreadWorker`
- `0x180038e14`: `Worker: Initial endpoint creation completed. Taking a nap`
- `0x180038faf`: `Worker: Endpoint ready to be created. Acquiring lock`
- `0x18003912c`: `Worker: Endpoint created`
- `0x1800391ab`: `Worker: No endpoints created`
- `0x180039241`: `Worker: Initial enumeration and endpoint creation complete. Signaling end of initial endpoint creation.`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall CMidi2KSAggregateMidiEndpointManager2::EndpointCreationThreadWorker(__int64 a1, const wchar_t *a2)
{
  const wchar_t *v2; // rsi
  _DWORD *v4; // rcx
  int v5; // r8d
  int v6; // r9d
  unsigned int v7; // r8d
  const char *v8; // r9
  _DWORD *v9; // rcx
  int v10; // r8d
  int v11; // r9d
  DWORD v12; // eax
  unsigned int v13; // r8d
  const char *v14; // r9
  _DWORD *v15; // rcx
  int v16; // r8d
  int v17; // r9d
  void *v18; // rbx
  DWORD v19; // eax
  unsigned int v20; // r8d
  const char *v21; // r9
  unsigned int v22; // r8d
  const char *v23; // r9
  DWORD LowPart; // r15d
  _QWORD *v25; // rbx
  _DWORD *v26; // rcx
  int v27; // r8d
  int v28; // r9d
  struct _RTL_CRITICAL_SECTION *v29; // r14
  __int64 v30; // rax
  int v31; // eax
  _QWORD *v32; // r15
  __int64 *v33; // r13
  __int64 *v34; // rsi
  __int64 v35; // rax
  __int64 v36; // rcx
  volatile signed __int32 *v37; // r14
  volatile signed __int32 *v38; // rsi
  _DWORD *v39; // rcx
  int v40; // r8d
  int v41; // r9d
  _DWORD *v42; // rcx
  int v43; // r8d
  int v44; // r9d
  void *v45; // rbx
  DWORD v46; // eax
  unsigned int v47; // r8d
  const char *v48; // r9
  _DWORD *v49; // rcx
  int v50; // r8d
  int v51; // r9d
  unsigned int v52; // r8d
  const char *v53; // r9
  _DWORD *v54; // rcx
  int v55; // r8d
  int v56; // r9d
  void *v57; // rcx
  int v58; // [rsp+20h] [rbp-40h]
  int v59[2]; // [rsp+40h] [rbp-20h] BYREF
  __int128 v60; // [rsp+48h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+38h]
  const wchar_t *v62; // [rsp+A8h] [rbp+48h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+B0h] [rbp+50h] BYREF
  const char *v64; // [rsp+B8h] [rbp+58h] BYREF

  v62 = a2;
  v2 = a2;
  v4 = (_DWORD *)*((_QWORD *)MidiKSAggregateTransportTelemetryProvider::Instance() + 1);
  if ( *v4 > 4u )
  {
    PerformanceCount.QuadPart = (LONGLONG)L"Worker: Enter.";
    v64 = (const char *)a1;
    *(_QWORD *)v59 = "CMidi2KSAggregateMidiEndpointManager2::EndpointCreationThreadWorker";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>>(
      (_DWORD)v4,
      (unsigned int)byte_18008A079,
      v5,
      v6,
      (__int64)v59,
      (__int64)&v64,
      (__int64)&PerformanceCount);
  }
  while ( !*(_QWORD *)v2 || (*(_DWORD *)(*(_QWORD *)v2 + 4LL) & 1) == 0 )
  {
    if ( *(_QWORD *)(a1 + 104) == *(_QWORD *)(a1 + 112) )
    {
      if ( !ResetEvent(*(HANDLE *)(a1 + 240)) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA06, v7, v8);
      if ( *(_QWORD *)(a1 + 232) && (!*(_QWORD *)v2 || (*(_DWORD *)(*(_QWORD *)v2 + 4LL) & 1) == 0) )
      {
        v9 = (_DWORD *)*((_QWORD *)MidiKSAggregateTransportTelemetryProvider::Instance() + 1);
        if ( *v9 > 4u )
        {
          PerformanceCount.QuadPart = (LONGLONG)L"Worker: Initial endpoint creation completed. Taking a nap";
          v64 = (const char *)a1;
          *(_QWORD *)v59 = "CMidi2KSAggregateMidiEndpointManager2::EndpointCreationThreadWorker";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>>(
            (_DWORD)v9,
            (unsigned int)&dword_18008A044,
            v10,
            v11,
            (__int64)v59,
            (__int64)&v64,
            (__int64)&PerformanceCount);
        }
        v12 = WaitForSingleObjectEx(*(HANDLE *)(a1 + 240), 0x2710u, 0);
        if ( v12 != 258 && v12 )
          wil::details::in1diag3::FailFast_Unexpected(retaddr, (void *)0xB0F, v13, v14);
      }
    }
    else
    {
      v15 = (_DWORD *)*((_QWORD *)MidiKSAggregateTransportTelemetryProvider::Instance() + 1);
      if ( *v15 > 4u )
      {
        PerformanceCount.QuadPart = (LONGLONG)L"Worker: Processing queue";
        v64 = (const char *)a1;
        *(_QWORD *)v59 = "CMidi2KSAggregateMidiEndpointManager2::EndpointCreationThreadWorker";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>>(
          (_DWORD)v15,
          (unsigned int)&byte_18008A00F,
          v16,
          v17,
          (__int64)v59,
          (__int64)&v64,
          (__int64)&PerformanceCount);
      }
      v18 = *(void **)(a1 + 240);
      v19 = WaitForSingleObjectEx(v18, 0, 0);
      if ( v19 != 258 )
      {
        if ( v19 || WaitForSingleObjectEx(v18, 0, 0) )
          wil::details::in1diag3::FailFast_Unexpected(retaddr, (void *)0xB07, v20, v21);
        if ( !*(_QWORD *)v2 || (*(_DWORD *)(*(_QWORD *)v2 + 4LL) & 1) == 0 )
        {
          Sleep(*(_DWORD *)(a1 + 24));
          if ( !ResetEvent(*(HANDLE *)(a1 + 240)) )
            wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA06, v22, v23);
        }
      }
      LowPart = 0;
      v25 = *(_QWORD **)(a1 + 104);
      while ( v25 != *(_QWORD **)(a1 + 112) && (!*(_QWORD *)v2 || (*(_DWORD *)(*(_QWORD *)v2 + 4LL) & 1) == 0) )
      {
        if ( *(_BYTE *)(*v25 + 248LL)
          || (PerformanceCount.QuadPart = 0,
              QueryPerformanceCounter(&PerformanceCount),
              PerformanceCount.QuadPart - *(_QWORD *)(*v25 + 240LL) < *(_QWORD *)(a1 + 16)) )
        {
          v25 += 2;
        }
        else
        {
          v26 = (_DWORD *)*((_QWORD *)MidiKSAggregateTransportTelemetryProvider::Instance() + 1);
          if ( *v26 > 4u )
          {
            PerformanceCount.QuadPart = (LONGLONG)L"Worker: Endpoint ready to be created. Acquiring lock";
            v64 = (const char *)a1;
            *(_QWORD *)v59 = "CMidi2KSAggregateMidiEndpointManager2::EndpointCreationThreadWorker";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>>(
              (_DWORD)v26,
              (unsigned int)word_180089FDA,
              v27,
              v28,
              (__int64)v59,
              (__int64)&v64,
              (__int64)&PerformanceCount);
          }
          v29 = (struct _RTL_CRITICAL_SECTION *)(a1 + 128);
          EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 128));
          PerformanceCount.QuadPart = a1 + 128;
          v60 = 0;
          v30 = v25[1];
          if ( v30 )
            _InterlockedIncrement((volatile signed __int32 *)(v30 + 8));
          v60 = *(_OWORD *)v25;
          v31 = CMidi2KSAggregateMidiEndpointManager2::DeviceCreateMidiUmpEndpoint(a1, &v60);
          if ( v31 < 0 )
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x6F0,
              (unsigned int)"avcore\\midi2\\transport\\ksaggregatetransport\\midi2.ksaggregatemidiendpointmanager2.cpp",
              (const char *)(unsigned int)v31,
              v58);
          PerformanceCount.LowPart = LowPart + 1;
          v32 = v25;
          v33 = *(__int64 **)(a1 + 112);
          v34 = v25 + 2;
          if ( v25 + 2 != v33 )
          {
            do
            {
              v35 = *v34;
              v36 = v34[1];
              *v34 = 0;
              v34[1] = 0;
              *v32 = v35;
              v37 = (volatile signed __int32 *)v32[1];
              v32[1] = v36;
              if ( v37 )
              {
                if ( _InterlockedExchangeAdd(v37 + 2, 0xFFFFFFFF) == 1 )
                {
                  (**(void (__fastcall ***)(volatile signed __int32 *))v37)(v37);
                  if ( _InterlockedExchangeAdd(v37 + 3, 0xFFFFFFFF) == 1 )
                    (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v37 + 8LL))(v37);
                }
              }
              v32 += 2;
              v34 += 2;
            }
            while ( v34 != v33 );
            v29 = (struct _RTL_CRITICAL_SECTION *)(a1 + 128);
          }
          v38 = *(volatile signed __int32 **)(*(_QWORD *)(a1 + 112) - 8LL);
          if ( v38 )
          {
            if ( _InterlockedExchangeAdd(v38 + 2, 0xFFFFFFFF) == 1 )
            {
              (**(void (__fastcall ***)(volatile signed __int32 *))v38)(v38);
              if ( _InterlockedExchangeAdd(v38 + 3, 0xFFFFFFFF) == 1 )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v38 + 8LL))(v38);
            }
          }
          *(_QWORD *)(a1 + 112) -= 16LL;
          v39 = (_DWORD *)*((_QWORD *)MidiKSAggregateTransportTelemetryProvider::Instance() + 1);
          if ( *v39 > 4u )
          {
            v64 = (const char *)L"Worker: Endpoint created";
            *(_QWORD *)v59 = a1;
            *(_QWORD *)&v60 = "CMidi2KSAggregateMidiEndpointManager2::EndpointCreationThreadWorker";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>>(
              (_DWORD)v39,
              (unsigned int)byte_180089FA5,
              v40,
              v41,
              (__int64)&v60,
              (__int64)v59,
              (__int64)&v64);
          }
          v2 = v62;
          LowPart = PerformanceCount.LowPart;
          if ( v29 )
            LeaveCriticalSection(v29);
        }
      }
      if ( !LowPart )
      {
        v42 = (_DWORD *)*((_QWORD *)MidiKSAggregateTransportTelemetryProvider::Instance() + 1);
        if ( *v42 > 4u )
        {
          PerformanceCount.QuadPart = (LONGLONG)L"Worker: No endpoints created";
          v64 = (const char *)a1;
          *(_QWORD *)&v60 = "CMidi2KSAggregateMidiEndpointManager2::EndpointCreationThreadWorker";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>>(
            (_DWORD)v42,
            (unsigned int)qword_180089F70,
            v43,
            v44,
            (__int64)&v60,
            (__int64)&v64,
            (__int64)&PerformanceCount);
        }
      }
    }
    v45 = *(void **)(a1 + 224);
    v46 = WaitForSingleObjectEx(v45, 0, 0);
    if ( v46 != 258 )
    {
      if ( v46 || WaitForSingleObjectEx(v45, 0, 0) )
        wil::details::in1diag3::FailFast_Unexpected(retaddr, (void *)0xB07, v47, v48);
      if ( *(_QWORD *)(a1 + 104) == *(_QWORD *)(a1 + 112) )
      {
        v49 = (_DWORD *)*((_QWORD *)MidiKSAggregateTransportTelemetryProvider::Instance() + 1);
        if ( *v49 > 4u )
        {
          PerformanceCount.QuadPart = (LONGLONG)L"Worker: Initial enumeration and endpoint creation complete. Signaling en"
                                                 "d of initial endpoint creation.";
          v64 = (const char *)a1;
          *(_QWORD *)&v60 = "CMidi2KSAggregateMidiEndpointManager2::EndpointCreationThreadWorker";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>>(
            (_DWORD)v49,
            (unsigned int)byte_180089F3B,
            v50,
            v51,
            (__int64)&v60,
            (__int64)&v64,
            (__int64)&PerformanceCount);
        }
        if ( !SetEvent(*(HANDLE *)(a1 + 232)) )
          wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA01, v52, v53);
      }
    }
  }
  v54 = (_DWORD *)*((_QWORD *)MidiKSAggregateTransportTelemetryProvider::Instance() + 1);
  if ( *v54 > 4u )
  {
    v62 = L"Worker: Exit";
    PerformanceCount.QuadPart = a1;
    v64 = "CMidi2KSAggregateMidiEndpointManager2::EndpointCreationThreadWorker";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>>(
      (_DWORD)v54,
      (unsigned int)byte_180089F09,
      v55,
      v56,
      (__int64)&v64,
      (__int64)&PerformanceCount,
      (__int64)&v62);
  }
  v57 = *(void **)v2;
  if ( *(_QWORD *)v2 && _InterlockedExchangeAdd((volatile signed __int32 *)v57, 0xFFFFFFFF) == 1 )
    operator delete(v57);
}

```

## disassembly

```asm
0x180038d30  mov     [rsp-38h+arg_0], rbx
0x180038d35  mov     [rsp-38h+arg_8], rdx
0x180038d3a  push    rbp
0x180038d3b  push    rsi
0x180038d3c  push    rdi
0x180038d3d  push    r12
0x180038d3f  push    r13
0x180038d41  push    r14
0x180038d43  push    r15
0x180038d45  mov     rbp, rsp
0x180038d48  sub     rsp, 60h
0x180038d4c  mov     rsi, rdx
0x180038d4f  mov     rdi, rcx
0x180038d52  call    ?Instance@MidiKSAggregateTransportTelemetryProvider@@KAPEAV1@XZ; MidiKSAggregateTransportTelemetryProvider::Instance(void)
0x180038d57  mov     rcx, [rax+8]
0x180038d5b  mov     eax, [rcx]
0x180038d5d  lea     r14, aCmidi2ksaggreg_31; "CMidi2KSAggregateMidiEndpointManager2::"...
0x180038d64  cmp     eax, 4
0x180038d67  jbe     short loc_180038DA3
0x180038d69  lea     rax, aWorkerEnter; "Worker: Enter."
0x180038d70  mov     qword ptr [rbp+PerformanceCount], rax
0x180038d74  mov     [rbp+arg_18], rdi
0x180038d78  mov     qword ptr [rbp+var_20], r14
0x180038d7c  lea     rax, [rbp+PerformanceCount]
0x180038d80  mov     [rsp+60h+var_30], rax
0x180038d85  lea     rax, [rbp+arg_18]
0x180038d89  mov     [rsp+60h+var_38], rax
0x180038d8e  lea     rax, [rbp+var_20]
0x180038d92  mov     qword ptr [rsp+60h+var_40], rax
0x180038d97  lea     rdx, byte_18008A079
0x180038d9e  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &)
0x180038da3  or      r12d, 0FFFFFFFFh
0x180038da7  mov     rax, [rsi]
0x180038daa  test    rax, rax
0x180038dad  jz      short loc_180038DBB
0x180038daf  mov     eax, [rax+4]
0x180038db2  nop
0x180038db3  test    al, 1
0x180038db5  jnz     loc_180039299
0x180038dbb  mov     rax, [rdi+70h]
0x180038dbf  cmp     [rdi+68h], rax
0x180038dc3  jnz     loc_180038E7B
0x180038dc9  mov     rbx, [rbp+38h]
0x180038dcd  mov     rcx, [rdi+0F0h]; hEvent
0x180038dd4  call    cs:__imp_ResetEvent
0x180038dda  test    eax, eax
0x180038ddc  jz      loc_180039354
0x180038de2  cmp     qword ptr [rdi+0E8h], 0
0x180038dea  jz      loc_1800391E5
0x180038df0  mov     rax, [rsi]
0x180038df3  test    rax, rax
0x180038df6  jz      short loc_180038E04
0x180038df8  mov     eax, [rax+4]
0x180038dfb  nop
0x180038dfc  test    al, 1
0x180038dfe  jnz     loc_1800391E5
0x180038e04  call    ?Instance@MidiKSAggregateTransportTelemetryProvider@@KAPEAV1@XZ; MidiKSAggregateTransportTelemetryProvider::Instance(void)
0x180038e09  mov     rcx, [rax+8]
0x180038e0d  mov     eax, [rcx]
0x180038e0f  cmp     eax, 4
0x180038e12  jbe     short loc_180038E4E
0x180038e14  lea     rax, aWorkerInitialE_0; "Worker: Initial endpoint creation compl"...
0x180038e1b  mov     qword ptr [rbp+PerformanceCount], rax
0x180038e1f  mov     [rbp+arg_18], rdi
0x180038e23  mov     qword ptr [rbp+var_20], r14
0x180038e27  lea     rax, [rbp+PerformanceCount]
0x180038e2b  mov     [rsp+60h+var_30], rax
0x180038e30  lea     rax, [rbp+arg_18]
0x180038e34  mov     [rsp+60h+var_38], rax
0x180038e39  lea     rax, [rbp+var_20]
0x180038e3d  mov     qword ptr [rsp+60h+var_40], rax
0x180038e42  lea     rdx, dword_18008A044
0x180038e49  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &)
0x180038e4e  xor     r8d, r8d; bAlertable
0x180038e51  mov     edx, 2710h; dwMilliseconds
0x180038e56  mov     rcx, [rdi+0F0h]; hHandle
0x180038e5d  call    cs:__imp_WaitForSingleObjectEx
0x180038e63  cmp     eax, 102h
0x180038e68  jz      loc_1800391E5
0x180038e6e  test    eax, eax
0x180038e70  jnz     loc_180039328
0x180038e76  jmp     loc_1800391E5
0x180038e7b  call    ?Instance@MidiKSAggregateTransportTelemetryProvider@@KAPEAV1@XZ; MidiKSAggregateTransportTelemetryProvider::Instance(void)
0x180038e80  mov     rcx, [rax+8]
0x180038e84  mov     eax, [rcx]
0x180038e86  cmp     eax, 4
0x180038e89  jbe     short loc_180038EC5
0x180038e8b  lea     rax, aWorkerProcessi; "Worker: Processing queue"
0x180038e92  mov     qword ptr [rbp+PerformanceCount], rax
0x180038e96  mov     [rbp+arg_18], rdi
0x180038e9a  mov     qword ptr [rbp+var_20], r14
0x180038e9e  lea     rax, [rbp+PerformanceCount]
0x180038ea2  mov     [rsp+60h+var_30], rax
0x180038ea7  lea     rax, [rbp+arg_18]
0x180038eab  mov     [rsp+60h+var_38], rax
0x180038eb0  lea     rax, [rbp+var_20]
0x180038eb4  mov     qword ptr [rsp+60h+var_40], rax
0x180038eb9  lea     rdx, byte_18008A00F
0x180038ec0  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &)
0x180038ec5  mov     rbx, [rdi+0F0h]
0x180038ecc  xor     r8d, r8d; bAlertable
0x180038ecf  xor     edx, edx; dwMilliseconds
0x180038ed1  mov     rcx, rbx; hHandle
0x180038ed4  call    cs:__imp_WaitForSingleObjectEx
0x180038eda  cmp     eax, 102h
0x180038edf  jz      short loc_180038F31
0x180038ee1  test    eax, eax
0x180038ee3  jnz     loc_180039319
0x180038ee9  xor     r8d, r8d; bAlertable
0x180038eec  xor     edx, edx; dwMilliseconds
0x180038eee  mov     rcx, rbx; hHandle
0x180038ef1  call    cs:__imp_WaitForSingleObjectEx
0x180038ef7  test    eax, eax
0x180038ef9  jnz     loc_180039319
0x180038eff  mov     rax, [rsi]
0x180038f02  test    rax, rax
0x180038f05  jz      short loc_180038F0F
0x180038f07  mov     eax, [rax+4]
0x180038f0a  nop
0x180038f0b  test    al, 1
0x180038f0d  jnz     short loc_180038F31
0x180038f0f  mov     ecx, [rdi+18h]; dwMilliseconds
0x180038f12  call    cs:__imp_Sleep
0x180038f18  mov     rcx, [rdi+0F0h]; hEvent
0x180038f1f  call    cs:__imp_ResetEvent
0x180038f25  mov     rcx, [rbp+38h]; this
0x180038f29  test    eax, eax
0x180038f2b  jz      loc_180039362
0x180038f31  xor     r15d, r15d
0x180038f34  mov     rbx, [rdi+68h]
0x180038f38  jmp     short loc_180038F41
0x180038f3a  lea     r14, aCmidi2ksaggreg_31; "CMidi2KSAggregateMidiEndpointManager2::"...
0x180038f41  cmp     rbx, [rdi+70h]
0x180038f45  jz      loc_180039196
0x180038f4b  mov     rax, [rsi]
0x180038f4e  test    rax, rax
0x180038f51  jz      short loc_180038F5F
0x180038f53  mov     eax, [rax+4]
0x180038f56  nop
0x180038f57  test    al, 1
0x180038f59  jnz     loc_180039196
0x180038f5f  mov     rax, [rbx]
0x180038f62  mov     cl, [rax+0F8h]
0x180038f68  nop
0x180038f69  test    cl, cl
0x180038f6b  jnz     loc_18003918D
0x180038f71  mov     qword ptr [rbp+PerformanceCount], 0
0x180038f79  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180038f7d  call    cs:__imp_QueryPerformanceCounter
0x180038f83  mov     rdx, qword ptr [rbp+PerformanceCount]
0x180038f87  mov     rax, [rbx]
0x180038f8a  mov     rcx, [rax+0F0h]
0x180038f91  nop
0x180038f92  sub     rdx, rcx
0x180038f95  cmp     rdx, [rdi+10h]
0x180038f99  jb      loc_18003918D
0x180038f9f  call    ?Instance@MidiKSAggregateTransportTelemetryProvider@@KAPEAV1@XZ; MidiKSAggregateTransportTelemetryProvider::Instance(void)
0x180038fa4  mov     rcx, [rax+8]
0x180038fa8  mov     eax, [rcx]
0x180038faa  cmp     eax, 4
0x180038fad  jbe     short loc_180038FE9
0x180038faf  lea     rax, aWorkerEndpoint_0; "Worker: Endpoint ready to be created. A"...
0x180038fb6  mov     qword ptr [rbp+PerformanceCount], rax
0x180038fba  mov     [rbp+arg_18], rdi
0x180038fbe  mov     qword ptr [rbp+var_20], r14
0x180038fc2  lea     rax, [rbp+PerformanceCount]
0x180038fc6  mov     [rsp+60h+var_30], rax
0x180038fcb  lea     rax, [rbp+arg_18]
0x180038fcf  mov     [rsp+60h+var_38], rax
0x180038fd4  lea     rax, [rbp+var_20]
0x180038fd8  mov     qword ptr [rsp+60h+var_40], rax; int
0x180038fdd  lea     rdx, word_180089FDA
0x180038fe4  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &)
0x180038fe9  lea     r14, [rdi+80h]
0x180038ff0  mov     rcx, r14; lpCriticalSection
0x180038ff3  call    cs:__imp_EnterCriticalSection
0x180038ff9  mov     qword ptr [rbp+PerformanceCount], r14
0x180038ffd  xorps   xmm0, xmm0
0x180039000  movdqu  [rbp+var_18], xmm0
0x180039005  mov     rax, [rbx+8]
0x180039009  test    rax, rax
0x18003900c  jz      short loc_180039012
0x18003900e  lock inc dword ptr [rax+8]
0x180039012  mov     rax, [rbx]
0x180039015  mov     qword ptr [rbp+var_18], rax
0x180039019  mov     rax, [rbx+8]
0x18003901d  mov     qword ptr [rbp+var_18+8], rax
0x180039021  lea     rdx, [rbp+var_18]
0x180039025  mov     rcx, rdi
0x180039028  call    ?DeviceCreateMidiUmpEndpoint@CMidi2KSAggregateMidiEndpointManager2@@AEAAJV?$shared_ptr@UKsAggregateEndpointDefinition2@@@std@@@Z; CMidi2KSAggregateMidiEndpointManager2::DeviceCreateMidiUmpEndpoint(std::shared_ptr<KsAggregateEndpointDefinition2>)
0x18003902d  mov     rcx, [rbp+38h]; this
0x180039031  test    eax, eax
0x180039033  jns     short loc_180039049
0x180039035  mov     r9d, eax; char *
0x180039038  lea     r8, aAvcoreMidi2Tra_4; "avcore\\midi2\\transport\\ksaggregatetr"...
0x18003903f  mov     edx, 6F0h; void *
0x180039044  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180039049  inc     r15d
0x18003904c  mov     dword ptr [rbp+PerformanceCount], r15d
0x180039050  mov     r15, rbx
0x180039053  mov     r13, [rdi+70h]
0x180039057  lea     rsi, [rbx+10h]
0x18003905b  cmp     rsi, r13
0x18003905e  jz      short loc_1800390D3
0x180039060  mov     rax, [rsi]
0x180039063  mov     rcx, [rsi+8]
0x180039067  mov     qword ptr [rsi], 0
0x18003906e  mov     qword ptr [rsi+8], 0
0x180039076  mov     [r15], rax
0x180039079  mov     r14, [r15+8]
0x18003907d  mov     [r15+8], rcx
0x180039081  test    r14, r14
0x180039084  jz      short loc_1800390BF
0x180039086  mov     eax, r12d
0x180039089  lock xadd [r14+8], eax
0x18003908f  add     eax, r12d
0x180039092  jnz     short loc_1800390BF
0x180039094  mov     rax, [r14]
0x180039097  mov     rcx, r14
0x18003909a  mov     rax, [rax]
0x18003909d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800390a2  mov     eax, r12d
0x1800390a5  lock xadd [r14+0Ch], eax
0x1800390ab  add     eax, r12d
0x1800390ae  jnz     short loc_1800390BF
0x1800390b0  mov     rax, [r14]
0x1800390b3  mov     rcx, r14
0x1800390b6  mov     rax, [rax+8]
0x1800390ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800390bf  add     r15, 10h
0x1800390c3  add     rsi, 10h
0x1800390c7  cmp     rsi, r13
0x1800390ca  jnz     short loc_180039060
0x1800390cc  lea     r14, [rdi+80h]
0x1800390d3  mov     rax, [rdi+70h]
0x1800390d7  mov     rsi, [rax-8]
0x1800390db  test    rsi, rsi
0x1800390de  jz      short loc_180039117
0x1800390e0  mov     eax, r12d
0x1800390e3  lock xadd [rsi+8], eax
0x1800390e8  add     eax, r12d
0x1800390eb  jnz     short loc_180039117
0x1800390ed  mov     rax, [rsi]
0x1800390f0  mov     rcx, rsi
0x1800390f3  mov     rax, [rax]
0x1800390f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800390fb  mov     eax, r12d
0x1800390fe  lock xadd [rsi+0Ch], eax
0x180039103  add     eax, r12d
0x180039106  jnz     short loc_180039117
0x180039108  mov     rax, [rsi]
0x18003910b  mov     rcx, rsi
0x18003910e  mov     rax, [rax+8]
0x180039112  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039117  add     qword ptr [rdi+70h], 0FFFFFFFFFFFFFFF0h
0x18003911c  call    ?Instance@MidiKSAggregateTransportTelemetryProvider@@KAPEAV1@XZ; MidiKSAggregateTransportTelemetryProvider::Instance(void)
0x180039121  mov     rcx, [rax+8]
0x180039125  mov     eax, [rcx]
0x180039127  cmp     eax, 4
0x18003912a  jbe     short loc_18003916E
0x18003912c  lea     rax, aWorkerEndpoint; "Worker: Endpoint created"
0x180039133  mov     [rbp+arg_18], rax
0x180039137  mov     qword ptr [rbp+var_20], rdi
0x18003913b  lea     rax, aCmidi2ksaggreg_31; "CMidi2KSAggregateMidiEndpointManager2::"...
0x180039142  mov     qword ptr [rbp+var_18], rax
0x180039146  lea     rax, [rbp+arg_18]
0x18003914a  mov     [rsp+60h+var_30], rax
0x18003914f  lea     rax, [rbp+var_20]
0x180039153  mov     [rsp+60h+var_38], rax
0x180039158  lea     rax, [rbp+var_18]
0x18003915c  mov     qword ptr [rsp+60h+var_40], rax
0x180039161  lea     rdx, byte_180089FA5
0x180039168  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &)
0x18003916d  nop
0x18003916e  test    r14, r14
0x180039171  mov     rsi, [rbp+arg_8]
0x180039175  mov     r15d, dword ptr [rbp+PerformanceCount]
0x180039179  jz      loc_180038F3A
0x18003917f  mov     rcx, r14; lpCriticalSection
0x180039182  call    cs:__imp_LeaveCriticalSection
0x180039188  jmp     loc_180038F3A
0x18003918d  add     rbx, 10h
0x180039191  jmp     loc_180038F41
0x180039196  test    r15d, r15d
0x180039199  jnz     short loc_1800391E5
0x18003919b  call    ?Instance@MidiKSAggregateTransportTelemetryProvider@@KAPEAV1@XZ; MidiKSAggregateTransportTelemetryProvider::Instance(void)
0x1800391a0  mov     rcx, [rax+8]
0x1800391a4  mov     eax, [rcx]
0x1800391a6  cmp     eax, 4
0x1800391a9  jbe     short loc_1800391E5
0x1800391ab  lea     rax, aWorkerNoEndpoi; "Worker: No endpoints created"
0x1800391b2  mov     qword ptr [rbp+PerformanceCount], rax
0x1800391b6  mov     [rbp+arg_18], rdi
0x1800391ba  mov     qword ptr [rbp+var_18], r14
0x1800391be  lea     rax, [rbp+PerformanceCount]
0x1800391c2  mov     [rsp+60h+var_30], rax
0x1800391c7  lea     rax, [rbp+arg_18]
0x1800391cb  mov     [rsp+60h+var_38], rax
0x1800391d0  lea     rax, [rbp+var_18]
0x1800391d4  mov     qword ptr [rsp+60h+var_40], rax
  ... truncated ...
```
