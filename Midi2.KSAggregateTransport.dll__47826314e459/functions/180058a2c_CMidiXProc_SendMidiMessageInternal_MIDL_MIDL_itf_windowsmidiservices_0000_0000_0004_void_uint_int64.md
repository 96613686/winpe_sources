# CMidiXProc::SendMidiMessageInternal(__MIDL___MIDL_itf_windowsmidiservices_0000_0000_0004,void *,uint,__int64)

- ea: `0x180058a2c`
- end: `0x1800592d4`
- name: `?SendMidiMessageInternal@CMidiXProc@@AEAAJW4__MIDL___MIDL_itf_windowsmidiservices_0000_0000_0004@@PEAXI_J@Z`
- size: `2216`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180058858`

## callees

- `0x180002df0`
- `0x180005e84`
- `0x18000b374`
- `0x18000b394`
- `0x18000c684`
- `0x180019924`
- `0x180058798`
- `0x180058a2c`
- `0x1800593f4`
- `0x180059890`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180058a94`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180058f40`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180058a94`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180058f40`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180058d82`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180058eb7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005909e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180058d82`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180058eb7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005909e`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180058d56`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800591ba`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180058d56`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800591ba`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180058aa6`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180058f52`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180058aa6`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180058f52`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180058d31`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180059197`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180058d31`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180059197`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x180058b22`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x180058fc5`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x180058b22`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x180058fc5`

## string_xrefs

- `0x180058c0b`: `MidiXProc stall detected during send, buffer dropped.`

## pseudocode

```c
__int64 __fastcall CMidiXProc::SendMidiMessageInternal(
        __int64 a1,
        char a2,
        const wchar_t *a3,
        unsigned int a4,
        LARGE_INTEGER a5)
{
  char v6; // r14
  char IsEnabled; // al
  __int64 v9; // r13
  struct _RTL_CRITICAL_SECTION *v10; // rbx
  struct _RTL_CRITICAL_SECTION *v11; // rcx
  unsigned int v12; // r8d
  const char *v13; // r9
  __int64 v14; // r12
  unsigned int v15; // eax
  DWORD v16; // r15d
  int v17; // eax
  _BYTE *v18; // rsi
  DWORD v19; // eax
  const struct _tlgProvider_t *v20; // rax
  int v21; // r9d
  int v22; // r8d
  __int64 v23; // rcx
  __int64 v24; // rcx
  int *v25; // rax
  __int16 *v26; // rdx
  const struct _tlgProvider_t *v27; // rax
  const wchar_t *v28; // rax
  const char *v29; // rcx
  __int64 v30; // rcx
  char v31; // r13
  const struct _tlgProvider_t *v32; // rax
  __int64 v33; // r14
  LARGE_INTEGER v34; // rax
  const char *v35; // r9
  __int64 v36; // rdx
  unsigned int LastError; // edi
  const struct _tlgProvider_t *v39; // rax
  int v40; // r9d
  int v41; // r8d
  __int16 *v42; // rdx
  const wchar_t *v43; // rax
  const struct _tlgProvider_t *v44; // rax
  const char *v45; // rcx
  int v46; // ebx
  __int64 v47; // rdx
  __int64 v48; // rdx
  char v49; // r12
  unsigned int v50; // r8d
  const char *v51; // r9
  __int64 v52; // r15
  signed __int32 v53; // eax
  unsigned int v54; // ecx
  DWORD v55; // esi
  int v56; // eax
  DWORD v57; // eax
  const struct _tlgProvider_t *v58; // rax
  int v59; // r9d
  int v60; // r8d
  int *v61; // rdx
  const wchar_t *v62; // rax
  const char *v63; // rcx
  unsigned int v64; // r13d
  const struct _tlgProvider_t *v65; // rax
  const struct _tlgProvider_t *v66; // rax
  __int64 v67; // r14
  unsigned int v68; // r12d
  LARGE_INTEGER v69; // rax
  const struct _tlgProvider_t *v70; // rax
  int v71; // r9d
  const char *v72; // rcx
  int v73; // [rsp+28h] [rbp-91h]
  __int64 *v74; // [rsp+30h] [rbp-89h]
  const wchar_t **v75; // [rsp+38h] [rbp-81h]
  const wchar_t **v76; // [rsp+40h] [rbp-79h]
  LARGE_INTEGER *v77; // [rsp+48h] [rbp-71h]
  LARGE_INTEGER *p_PerformanceCount; // [rsp+50h] [rbp-69h]
  __int64 *v79; // [rsp+60h] [rbp-59h]
  int *v80; // [rsp+68h] [rbp-51h]
  _BYTE v81[4]; // [rsp+78h] [rbp-41h] BYREF
  unsigned int v82; // [rsp+7Ch] [rbp-3Dh] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+80h] [rbp-39h] BYREF
  char v84; // [rsp+88h] [rbp-31h]
  unsigned int v85; // [rsp+8Ch] [rbp-2Dh]
  int v86[2]; // [rsp+90h] [rbp-29h] BYREF
  __int64 v87; // [rsp+98h] [rbp-21h] BYREF
  const wchar_t *v88; // [rsp+A0h] [rbp-19h] BYREF
  const wchar_t *v89; // [rsp+A8h] [rbp-11h] BYREF
  __int64 v90; // [rsp+B0h] [rbp-9h] BYREF
  const char *v91; // [rsp+B8h] [rbp-1h] BYREF
  unsigned int v92; // [rsp+C0h] [rbp+7h]
  unsigned int v93; // [rsp+C4h] [rbp+Bh]
  HANDLE Handles; // [rsp+C8h] [rbp+Fh] BYREF
  __int64 v95; // [rsp+D0h] [rbp+17h]
  wil::details::in1diag3 *retaddr; // [rsp+110h] [rbp+57h]

  v6 = a2;
  IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_MIDI2SendTimeout>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_Servicing_MIDI2SendTimeout>::GetImpl'::`2'::impl);
  v9 = *(_QWORD *)(a1 + 112);
  v93 = a4 + 16;
  v10 = (struct _RTL_CRITICAL_SECTION *)(a1 + 8);
  v85 = 0;
  v11 = (struct _RTL_CRITICAL_SECTION *)(a1 + 8);
  v92 = 0;
  if ( !IsEnabled )
  {
    v49 = 0;
    EnterCriticalSection(v11);
    while ( 1 )
    {
      if ( !ResetEvent(*(HANDLE *)(*(_QWORD *)(a1 + 112) + 64LL)) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA06, v50, v51);
      v52 = (unsigned int)_InterlockedCompareExchange(*(volatile signed __int32 **)(v9 + 40), 0, 0);
      v53 = _InterlockedCompareExchange(*(volatile signed __int32 **)(v9 + 48), 0, 0);
      v54 = *(_DWORD *)(v9 + 32);
      v55 = v53;
      v56 = v53 - v52;
      if ( v55 <= (unsigned int)v52 )
        v56 += v54;
      if ( v56 - 1 >= v93 )
        break;
      if ( *(_BYTE *)(a1 + 48) )
      {
        *(__m128i *)(a1 + 56) = _mm_add_epi64(
                                  _mm_load_si128((const __m128i *)&_xmm),
                                  _mm_loadu_si128((const __m128i *)(a1 + 56)));
        v66 = MidiXProcTelemetryProvider::Provider();
        v60 = (int)v66;
        if ( *(_DWORD *)v66 <= 4u )
          goto LABEL_63;
        v61 = (int *)&byte_18008B51F;
        v89 = a3;
        v62 = L"MidiXProc stalled, buffer dropped.";
        goto LABEL_62;
      }
      Handles = *(HANDLE *)(a1 + 120);
      v95 = *(_QWORD *)(*(_QWORD *)(a1 + 112) + 64LL);
      v57 = WaitForMultipleObjects(2u, &Handles, 0, 0x1388u);
      if ( v57 != 1 )
      {
        ++*(_QWORD *)(a1 + 64);
        if ( !v57 )
        {
          v58 = MidiXProcTelemetryProvider::Provider();
          v60 = (int)v58;
          if ( *(_DWORD *)v58 > 4u )
          {
            v61 = (int *)&unk_18008BAC0;
            v89 = a3;
            v62 = L"MidiXProc terminated, buffer dropped.";
            goto LABEL_62;
          }
LABEL_63:
          v64 = v85;
          goto LABEL_64;
        }
        if ( v57 != 258 )
          goto LABEL_63;
        *(_BYTE *)(a1 + 48) = 1;
        v65 = MidiXProcTelemetryProvider::Provider();
        v60 = (int)v65;
        if ( *(_DWORD *)v65 <= 4u )
          goto LABEL_63;
        v61 = &dword_18008B5EC;
        v89 = a3;
        v62 = L"MidiXProc stall detected, buffer dropped.";
LABEL_62:
        v63 = *(const char **)(a1 + 64);
        v88 = v62;
        *(_QWORD *)v86 = "CMidiXProc::SendMidiMessageInternal";
        v91 = v63;
        v90 = *(_QWORD *)(a1 + 56);
        v81[0] = *(_BYTE *)(a1 + 48);
        v82 = v52;
        PerformanceCount.LowPart = v55;
        v87 = a1;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
          v60,
          (_DWORD)v61,
          v60,
          v59,
          (__int64)v86,
          (__int64)&v87,
          (__int64)&v88,
          (__int64)&v89,
          (__int64)&PerformanceCount,
          (__int64)&v82,
          (__int64)v81,
          (__int64)&v90,
          (__int64)&v91);
        goto LABEL_63;
      }
    }
    v67 = *(_QWORD *)(v9 + 24);
    v68 = ((unsigned int)v52 + v93) % v54;
    *(_DWORD *)(v52 + v67 + 8) = a4;
    memcpy_0((void *)(v52 + v67 + 16), a3, a4);
    v69 = a5;
    if ( !a5.QuadPart )
    {
      if ( !*(_DWORD *)a1 )
      {
        *(_QWORD *)(v52 + v67) = 0;
LABEL_80:
        _InterlockedExchange(*(volatile __int32 **)(v9 + 40), v68);
        if ( !SetEvent(*(HANDLE *)(*(_QWORD *)(a1 + 112) + 56LL)) )
        {
          v36 = 968;
LABEL_28:
          LastError = wil::details::in1diag3::Return_GetLastError(
                        retaddr,
                        (void *)v36,
                        (unsigned int)"avcore\\midi2\\libs\\midixproc\\midixproc.cpp",
                        v35);
          if ( v10 )
            LeaveCriticalSection(v10);
          return LastError;
        }
        v49 = 1;
        v64 = v52;
        v92 = v55;
        if ( *(_BYTE *)(a1 + 48) )
        {
          *(_BYTE *)(a1 + 48) = 0;
          *(_QWORD *)(a1 + 56) = 0;
          v70 = MidiXProcTelemetryProvider::Provider();
          if ( *(_DWORD *)v70 > 4u )
          {
            v72 = *(const char **)(a1 + 64);
            v89 = a3;
            v88 = L"MidiXProc recovered from stall.";
            *(_QWORD *)v86 = "CMidiXProc::SendMidiMessageInternal";
            v91 = v72;
            v90 = *(_QWORD *)(a1 + 56);
            v81[0] = *(_BYTE *)(a1 + 48);
            v82 = v52;
            PerformanceCount.LowPart = v55;
            v87 = a1;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
              (_DWORD)v70,
              (unsigned int)&unk_18008B6F0,
              (_DWORD)v70,
              v71,
              (__int64)v86,
              (__int64)&v87,
              (__int64)&v88,
              (__int64)&v89,
              (__int64)&PerformanceCount,
              (__int64)&v82,
              (__int64)v81,
              (__int64)&v90,
              (__int64)&v91);
          }
        }
        v6 = a2;
LABEL_64:
        if ( a1 != -8 )
          LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 8));
        if ( !v49 )
        {
          v48 = 1095;
          goto LABEL_51;
        }
        if ( (v6 & 1) != 0 )
        {
          v46 = CMidiXProc::WaitForSendComplete((CMidiXProc *)a1, v92, v64, a4);
          if ( v46 < 0 )
          {
            v47 = 1088;
            goto LABEL_45;
          }
        }
        return 0;
      }
      PerformanceCount.QuadPart = 0;
      QueryPerformanceCounter(&PerformanceCount);
      v69 = PerformanceCount;
    }
    *(LARGE_INTEGER *)(v52 + v67) = v69;
    goto LABEL_80;
  }
  v84 = 0;
  EnterCriticalSection(v11);
  while ( 1 )
  {
    if ( !ResetEvent(*(HANDLE *)(*(_QWORD *)(a1 + 112) + 64LL)) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA06, v12, v13);
    v14 = (unsigned int)_InterlockedCompareExchange(*(volatile signed __int32 **)(v9 + 40), 0, 0);
    v15 = _InterlockedCompareExchange(*(volatile signed __int32 **)(v9 + 48), 0, 0);
    v16 = v15;
    v17 = v15 > (unsigned int)v14 ? v15 - v14 : v15 + *(_DWORD *)(v9 + 32) - v14;
    if ( v17 - 1 >= v93 )
      break;
    v18 = (_BYTE *)(a1 + 48);
    if ( *(_BYTE *)(a1 + 48) )
    {
      *(__m128i *)(a1 + 56) = _mm_add_epi64(
                                _mm_load_si128((const __m128i *)&_xmm),
                                _mm_loadu_si128((const __m128i *)(a1 + 56)));
      v32 = MidiXProcTelemetryProvider::Provider();
      v22 = (int)v32;
      if ( *(_DWORD *)v32 <= 4u )
        goto LABEL_18;
      v28 = L"MidiXProc stalled, buffer dropped.";
      v89 = a3;
      v26 = word_18008BA2A;
      goto LABEL_16;
    }
    Handles = *(HANDLE *)(a1 + 120);
    v95 = *(_QWORD *)(*(_QWORD *)(a1 + 112) + 64LL);
    v19 = WaitForMultipleObjects(2u, &Handles, 0, 0x3E8u);
    if ( v19 != 1 )
    {
      ++*(_QWORD *)(a1 + 64);
      if ( !v19 )
      {
        v20 = MidiXProcTelemetryProvider::Provider();
        v22 = (int)v20;
        if ( *(_DWORD *)v20 > 4u )
        {
          v23 = *(_QWORD *)(a1 + 64);
          v89 = L"MidiXProc terminated, buffer dropped.";
          v91 = "CMidiXProc::SendMidiMessageInternal";
          v80 = v86;
          v79 = &v87;
          p_PerformanceCount = &PerformanceCount;
          v77 = (LARGE_INTEGER *)&v82;
          v76 = &v88;
          v75 = &v89;
          *(_QWORD *)v86 = v23;
          v24 = *(_QWORD *)(a1 + 56);
          v74 = &v90;
          v25 = (int *)&v91;
          v88 = a3;
          v26 = &word_18008B8FE;
          v87 = v24;
          PerformanceCount.LowPart = v14;
          v82 = v16;
          v90 = a1;
          goto LABEL_17;
        }
        goto LABEL_18;
      }
      if ( v19 != 258 )
        goto LABEL_18;
      *v18 = 1;
      *(_DWORD *)(a1 + 52) = v16;
      v27 = MidiXProcTelemetryProvider::Provider();
      v22 = (int)v27;
      if ( *(_DWORD *)v27 <= 4u )
        goto LABEL_18;
      v28 = L"MidiXProc stall detected during send, buffer dropped.";
      v89 = a3;
      v26 = (__int16 *)&dword_18008B994;
LABEL_16:
      v29 = *(const char **)(a1 + 64);
      v88 = v28;
      *(_QWORD *)v86 = "CMidiXProc::SendMidiMessageInternal";
      v80 = (int *)&v91;
      v79 = &v90;
      p_PerformanceCount = (LARGE_INTEGER *)&v82;
      v77 = &PerformanceCount;
      v76 = &v89;
      v75 = &v88;
      v91 = v29;
      v30 = *(_QWORD *)(a1 + 56);
      v74 = &v87;
      v25 = v86;
      v82 = v14;
      v90 = v30;
      v87 = a1;
      PerformanceCount.LowPart = v16;
LABEL_17:
      v81[0] = *v18;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
        v22,
        (_DWORD)v26,
        v22,
        v21,
        (__int64)v25,
        (__int64)v74,
        (__int64)v75,
        (__int64)v76,
        (__int64)v77,
        (__int64)p_PerformanceCount,
        (__int64)v81,
        (__int64)v79,
        (__int64)v80);
LABEL_18:
      v31 = v84;
      goto LABEL_39;
    }
  }
  v33 = *(_QWORD *)(v9 + 24);
  v82 = ((unsigned int)v14 + v93) % *(_DWORD *)(v9 + 32);
  *(_DWORD *)(v14 + v33 + 8) = a4;
  memcpy_0((void *)(v14 + v33 + 16), a3, a4);
  v34 = a5;
  if ( a5.QuadPart )
    goto LABEL_24;
  if ( *(_DWORD *)a1 )
  {
    PerformanceCount.QuadPart = 0;
    QueryPerformanceCounter(&PerformanceCount);
    v34 = PerformanceCount;
LABEL_24:
    *(LARGE_INTEGER *)(v14 + v33) = v34;
    goto LABEL_26;
  }
  *(_QWORD *)(v14 + v33) = 0;
LABEL_26:
  _InterlockedExchange(*(volatile __int32 **)(v9 + 40), v82);
  if ( !SetEvent(*(HANDLE *)(*(_QWORD *)(a1 + 112) + 56LL)) )
  {
    v36 = 724;
    goto LABEL_28;
  }
  v18 = (_BYTE *)(a1 + 48);
  v85 = v14;
  v31 = 1;
  v92 = v16;
  if ( !*(_BYTE *)(a1 + 48) )
    goto LABEL_38;
  *(_QWORD *)(a1 + 56) = 0;
  if ( v16 == *(_DWORD *)(a1 + 52) )
  {
    v44 = MidiXProcTelemetryProvider::Provider();
    v41 = (int)v44;
    if ( *(_DWORD *)v44 > 4u )
    {
      v42 = (__int16 *)&unk_18008B868;
      v89 = a3;
      v43 = L"MidiXProc buffer added to queue will in stalled state.";
      goto LABEL_37;
    }
  }
  else
  {
    *v18 = 0;
    *(_DWORD *)(a1 + 52) = 0;
    v39 = MidiXProcTelemetryProvider::Provider();
    v41 = (int)v39;
    if ( *(_DWORD *)v39 > 4u )
    {
      v42 = word_18008B7D2;
      v89 = a3;
      v43 = L"MidiXProc recovered from stall.";
LABEL_37:
      v45 = *(const char **)(a1 + 64);
      v88 = v43;
      *(_QWORD *)v86 = "CMidiXProc::SendMidiMessageInternal";
      v91 = v45;
      v90 = *(_QWORD *)(a1 + 56);
      v81[0] = *v18;
      v82 = v14;
      PerformanceCount.LowPart = v16;
      v87 = a1;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
        v41,
        (_DWORD)v42,
        v41,
        v40,
        (__int64)v86,
        (__int64)&v87,
        (__int64)&v88,
        (__int64)&v89,
        (__int64)&PerformanceCount,
        (__int64)&v82,
        (__int64)v81,
        (__int64)&v90,
        (__int64)&v91);
    }
  }
LABEL_38:
  v6 = a2;
LABEL_39:
  if ( a1 != -8 )
    LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 8));
  if ( v31 )
  {
    if ( (v6 & 1) != 0 )
    {
      v46 = CMidiXProc::WaitForSendComplete((CMidiXProc *)a1, v92, v85, v93);
      if ( v46 < 0 )
      {
        v47 = 872;
LABEL_45:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v47,
          (unsigned int)"avcore\\midi2\\libs\\midixproc\\midixproc.cpp",
          (const char *)(unsigned int)v46,
          v73);
        return (unsigned int)v46;
      }
    }
    return 0;
  }
  if ( !*v18 || !*(_QWORD *)(a1 + 56) )
  {
    v48 = 888;
LABEL_51:
    v46 = -2147024774;
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)v48,
      (unsigned int)"avcore\\midi2\\libs\\midixproc\\midixproc.cpp",
      (const char *)0x8007007ALL,
      v73);
    return (unsigned int)v46;
  }
  return 2147500036LL;
}

```

## disassembly

```asm
0x180058a2c  mov     rax, rsp
0x180058a2f  mov     [rax+8], rbx
0x180058a33  mov     [rax+20h], r9d
0x180058a37  mov     [rax+18h], r8
0x180058a3b  mov     [rax+10h], edx
0x180058a3e  push    rbp
0x180058a3f  push    rsi
0x180058a40  push    rdi
0x180058a41  push    r12
0x180058a43  push    r13
0x180058a45  push    r14
0x180058a47  push    r15
0x180058a49  lea     rbp, [rax-57h]
0x180058a4d  sub     rsp, 0D0h
0x180058a54  mov     ebx, r9d
0x180058a57  mov     r14d, edx
0x180058a5a  mov     rdi, rcx
0x180058a5d  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_MIDI2SendTimeout@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_MIDI2SendTimeout@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_MIDI2SendTimeout> `wil::Feature<__WilFeatureTraits_Feature_Servicing_MIDI2SendTimeout>::GetImpl(void)'::`2'::impl
0x180058a64  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_MIDI2SendTimeout@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_MIDI2SendTimeout>::__private_IsEnabled(void)
0x180058a69  mov     r13, [rdi+70h]
0x180058a6d  lea     ecx, [rbx+10h]
0x180058a70  mov     [rbp+4Fh+var_44], ecx
0x180058a73  lea     rbx, [rdi+8]
0x180058a77  mov     [rbp+4Fh+var_7C], 0
0x180058a7e  mov     rcx, rbx; lpCriticalSection
0x180058a81  mov     [rbp+4Fh+var_48], 0
0x180058a88  test    al, al
0x180058a8a  jz      loc_180058F3D
0x180058a90  mov     [rbp+4Fh+var_80], 0
0x180058a94  call    cs:__imp_EnterCriticalSection
0x180058a9a  mov     rcx, [rdi+70h]
0x180058a9e  mov     rsi, [rbp+57h]
0x180058aa2  mov     rcx, [rcx+40h]; hEvent
0x180058aa6  call    cs:__imp_ResetEvent
0x180058aac  test    eax, eax
0x180058aae  jz      loc_1800592B8
0x180058ab4  mov     rcx, [r13+28h]
0x180058ab8  xor     edx, edx
0x180058aba  xor     eax, eax
0x180058abc  lock cmpxchg [rcx], edx
0x180058ac0  mov     rcx, [r13+30h]
0x180058ac4  mov     r12d, eax
0x180058ac7  xor     eax, eax
0x180058ac9  lock cmpxchg [rcx], edx
0x180058acd  mov     r15d, eax
0x180058ad0  cmp     eax, r12d
0x180058ad3  ja      short loc_180058AE1
0x180058ad5  mov     eax, [r13+20h]
0x180058ad9  sub     eax, r12d
0x180058adc  add     eax, r15d
0x180058adf  jmp     short loc_180058AE4
0x180058ae1  sub     eax, r12d
0x180058ae4  mov     ecx, [rbp+4Fh+var_44]
0x180058ae7  dec     eax
0x180058ae9  cmp     eax, ecx
0x180058aeb  jnb     loc_180058CEF
0x180058af1  lea     rsi, [rdi+30h]
0x180058af5  cmp     [rsi], dl
0x180058af7  jnz     loc_180058CAF
0x180058afd  mov     rax, [rdi+78h]
0x180058b01  lea     rdx, [rbp+4Fh+Handles]; lpHandles
0x180058b05  mov     [rbp+4Fh+Handles], rax
0x180058b09  xor     r8d, r8d; bWaitAll
0x180058b0c  mov     rax, [rdi+70h]
0x180058b10  mov     r9d, 3E8h; dwMilliseconds
0x180058b16  mov     rcx, [rax+40h]
0x180058b1a  mov     [rbp+4Fh+var_38], rcx
0x180058b1e  lea     ecx, [r8+2]; nCount
0x180058b22  call    cs:__imp_WaitForMultipleObjects
0x180058b28  cmp     eax, 1
0x180058b2b  jz      loc_180058A9A
0x180058b31  inc     qword ptr [rdi+40h]
0x180058b35  test    eax, eax
0x180058b37  jnz     loc_180058BE2
0x180058b3d  call    ?Provider@MidiXProcTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; MidiXProcTelemetryProvider::Provider(void)
0x180058b42  mov     r8, rax
0x180058b45  mov     ecx, [rax]
0x180058b47  cmp     ecx, 4
0x180058b4a  jbe     loc_180058CA6
0x180058b50  mov     rcx, [rdi+40h]
0x180058b54  lea     rax, aMidixprocTermi; "MidiXProc terminated, buffer dropped."
0x180058b5b  mov     rdx, [rbp+4Fh+Src]
0x180058b5f  mov     [rbp+4Fh+var_60], rax
0x180058b63  lea     rax, aCmidixprocSend; "CMidiXProc::SendMidiMessageInternal"
0x180058b6a  mov     [rbp+4Fh+var_50], rax
0x180058b6e  lea     rax, [rbp+4Fh+var_78]
0x180058b72  mov     [rsp+60h], rax
0x180058b77  lea     rax, [rbp+4Fh+var_70]
0x180058b7b  mov     [rsp+100h+var_A8], rax
0x180058b80  lea     rax, [rbp+4Fh+var_90]
0x180058b84  mov     [rsp+100h+var_B0], rax
0x180058b89  lea     rax, [rbp+4Fh+PerformanceCount]
0x180058b8d  mov     [rsp+100h+var_B8], rax
0x180058b92  lea     rax, [rbp+4Fh+var_8C]
0x180058b96  mov     [rsp+100h+var_C0], rax
0x180058b9b  lea     rax, [rbp+4Fh+var_68]
0x180058b9f  mov     [rsp+100h+var_C8], rax
0x180058ba4  lea     rax, [rbp+4Fh+var_60]
0x180058ba8  mov     [rsp+100h+var_D0], rax
0x180058bad  lea     rax, [rbp+4Fh+var_58]
0x180058bb1  mov     qword ptr [rbp+4Fh+var_78], rcx
0x180058bb5  mov     rcx, [rdi+38h]
0x180058bb9  mov     [rsp+100h+var_D8], rax
0x180058bbe  lea     rax, [rbp+4Fh+var_50]
0x180058bc2  mov     [rbp+4Fh+var_68], rdx
0x180058bc6  lea     rdx, word_18008B8FE
0x180058bcd  mov     [rbp+4Fh+var_70], rcx
0x180058bd1  mov     dword ptr [rbp+4Fh+PerformanceCount], r12d
0x180058bd5  mov     [rbp+4Fh+var_8C], r15d
0x180058bd9  mov     [rbp+4Fh+var_58], rdi
0x180058bdd  jmp     loc_180058C94
0x180058be2  cmp     eax, 102h
0x180058be7  jnz     loc_180058CA6
0x180058bed  mov     byte ptr [rsi], 1
0x180058bf0  mov     [rdi+34h], r15d
0x180058bf4  call    ?Provider@MidiXProcTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; MidiXProcTelemetryProvider::Provider(void)
0x180058bf9  mov     r8, rax
0x180058bfc  mov     ecx, [rax]
0x180058bfe  cmp     ecx, 4
0x180058c01  jbe     loc_180058CA6
0x180058c07  mov     rdx, [rbp+4Fh+Src]
0x180058c0b  lea     rax, aMidixprocStall_0; "MidiXProc stall detected during send, b"...
0x180058c12  mov     [rbp+4Fh+var_60], rdx
0x180058c16  lea     rdx, dword_18008B994
0x180058c1d  mov     rcx, [rdi+40h]
0x180058c21  mov     [rbp+4Fh+var_68], rax
0x180058c25  lea     rax, aCmidixprocSend; "CMidiXProc::SendMidiMessageInternal"
0x180058c2c  mov     qword ptr [rbp+4Fh+var_78], rax
0x180058c30  lea     rax, [rbp+4Fh+var_50]
0x180058c34  mov     [rsp+60h], rax
0x180058c39  lea     rax, [rbp+4Fh+var_58]
0x180058c3d  mov     [rsp+100h+var_A8], rax
0x180058c42  lea     rax, [rbp+4Fh+var_90]
0x180058c46  mov     [rsp+100h+var_B0], rax
0x180058c4b  lea     rax, [rbp+4Fh+var_8C]
0x180058c4f  mov     [rsp+100h+var_B8], rax
0x180058c54  lea     rax, [rbp+4Fh+PerformanceCount]
0x180058c58  mov     [rsp+100h+var_C0], rax
0x180058c5d  lea     rax, [rbp+4Fh+var_60]
0x180058c61  mov     [rsp+100h+var_C8], rax
0x180058c66  lea     rax, [rbp+4Fh+var_68]
0x180058c6a  mov     [rsp+100h+var_D0], rax
0x180058c6f  lea     rax, [rbp+4Fh+var_70]
0x180058c73  mov     [rbp+4Fh+var_50], rcx
0x180058c77  mov     rcx, [rdi+38h]
0x180058c7b  mov     [rsp+100h+var_D8], rax
0x180058c80  lea     rax, [rbp+4Fh+var_78]
0x180058c84  mov     [rbp+4Fh+var_8C], r12d
0x180058c88  mov     [rbp+4Fh+var_58], rcx
0x180058c8c  mov     [rbp+4Fh+var_70], rdi
0x180058c90  mov     dword ptr [rbp+4Fh+PerformanceCount], r15d
0x180058c94  mov     cl, [rsi]
0x180058c96  mov     [rbp+4Fh+var_90], cl
0x180058c99  mov     rcx, r8
0x180058c9c  mov     qword ptr [rsp+100h+var_E0], rax
0x180058ca1  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U2@U?$_tlgWrapperByVal@$03@@U4@U?$_tlgWrapperByVal@$00@@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@4AEBU?$_tlgWrapperByVal@$03@@6AEBU?$_tlgWrapperByVal@$00@@44@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &)
0x180058ca6  mov     r13b, [rbp+4Fh+var_80]
0x180058caa  jmp     loc_180058EAF
0x180058caf  movdqu  xmm0, xmmword ptr [rdi+38h]
0x180058cb4  movdqa  xmm1, cs:__xmm@00000000000000010000000000000001
0x180058cbc  paddq   xmm1, xmm0
0x180058cc0  movdqu  xmmword ptr [rdi+38h], xmm1
0x180058cc5  call    ?Provider@MidiXProcTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; MidiXProcTelemetryProvider::Provider(void)
0x180058cca  mov     r8, rax
0x180058ccd  mov     ecx, [rax]
0x180058ccf  cmp     ecx, 4
0x180058cd2  jbe     short loc_180058CA6
0x180058cd4  mov     rdx, [rbp+4Fh+Src]
0x180058cd8  lea     rax, aMidixprocStall; "MidiXProc stalled, buffer dropped."
0x180058cdf  mov     [rbp+4Fh+var_60], rdx
0x180058ce3  lea     rdx, word_18008BA2A
0x180058cea  jmp     loc_180058C1D
0x180058cef  mov     r14, [r13+18h]
0x180058cf3  lea     eax, [r12+rcx]
0x180058cf7  div     dword ptr [r13+20h]
0x180058cfb  mov     r9d, dword ptr [rbp+4Fh+Size]
0x180058cff  lea     rcx, [r14+10h]
0x180058d03  mov     [rbp+4Fh+var_8C], edx
0x180058d06  mov     r8d, r9d; Size
0x180058d09  mov     rdx, [rbp+4Fh+Src]; Src
0x180058d0d  add     rcx, r12; void *
0x180058d10  mov     [r12+r14+8], r9d
0x180058d15  call    memcpy_0
0x180058d1a  mov     rax, [rbp+4Fh+arg_20]
0x180058d1e  xor     ecx, ecx
0x180058d20  test    rax, rax
0x180058d23  jnz     short loc_180058D3B
0x180058d25  cmp     [rdi], ecx
0x180058d27  jz      short loc_180058D41
0x180058d29  mov     qword ptr [rbp+4Fh+PerformanceCount], rcx
0x180058d2d  lea     rcx, [rbp+4Fh+PerformanceCount]; lpPerformanceCount
0x180058d31  call    cs:__imp_QueryPerformanceCounter
0x180058d37  mov     rax, qword ptr [rbp+4Fh+PerformanceCount]
0x180058d3b  mov     [r12+r14], rax
0x180058d3f  jmp     short loc_180058D45
0x180058d41  mov     [r12+r14], rcx
0x180058d45  mov     rax, [r13+28h]
0x180058d49  mov     ecx, [rbp+4Fh+var_8C]
0x180058d4c  xchg    ecx, [rax]
0x180058d4e  mov     rcx, [rdi+70h]
0x180058d52  mov     rcx, [rcx+38h]; hEvent
0x180058d56  call    cs:__imp_SetEvent
0x180058d5c  xor     r14d, r14d
0x180058d5f  test    eax, eax
0x180058d61  jnz     short loc_180058DA5
0x180058d63  mov     edx, 2D4h; void *
0x180058d68  mov     rcx, [rbp+57h]; this
0x180058d6c  lea     r8, aAvcoreMidi2Lib_3; "avcore\\midi2\\libs\\midixproc\\midixpr"...
0x180058d73  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180058d78  mov     edi, eax
0x180058d7a  test    rbx, rbx
0x180058d7d  jz      short loc_180058D88
0x180058d7f  mov     rcx, rbx; lpCriticalSection
0x180058d82  call    cs:__imp_LeaveCriticalSection
0x180058d88  mov     eax, edi
0x180058d8a  mov     rbx, [rsp+100h+arg_0]
0x180058d92  add     rsp, 0D0h
0x180058d99  pop     r15
0x180058d9b  pop     r14
0x180058d9d  pop     r13
0x180058d9f  pop     r12
0x180058da1  pop     rdi
0x180058da2  pop     rsi
0x180058da3  pop     rbp
0x180058da4  retn
0x180058da5  lea     rsi, [rdi+30h]
0x180058da9  mov     [rbp+4Fh+var_7C], r12d
0x180058dad  mov     r13b, 1
0x180058db0  mov     [rbp+4Fh+var_48], r15d
0x180058db4  cmp     [rsi], r14b
0x180058db7  jz      loc_180058EAB
0x180058dbd  mov     [rdi+38h], r14
0x180058dc1  cmp     r15d, [rdi+34h]
0x180058dc5  jz      short loc_180058DF9
0x180058dc7  mov     [rsi], r14b
0x180058dca  mov     [rdi+34h], r14d
0x180058dce  call    ?Provider@MidiXProcTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; MidiXProcTelemetryProvider::Provider(void)
0x180058dd3  mov     r8, rax
0x180058dd6  mov     ecx, [rax]
0x180058dd8  cmp     ecx, 4
0x180058ddb  jbe     loc_180058EAB
0x180058de1  mov     rax, [rbp+4Fh+Src]
0x180058de5  lea     rdx, word_18008B7D2
0x180058dec  mov     [rbp+4Fh+var_60], rax
0x180058df0  lea     rax, aMidixprocRecov; "MidiXProc recovered from stall."
0x180058df7  jmp     short loc_180058E22
0x180058df9  call    ?Provider@MidiXProcTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; MidiXProcTelemetryProvider::Provider(void)
0x180058dfe  mov     r8, rax
0x180058e01  mov     ecx, [rax]
0x180058e03  cmp     ecx, 4
0x180058e06  jbe     loc_180058EAB
0x180058e0c  mov     rax, [rbp+4Fh+Src]
0x180058e10  lea     rdx, unk_18008B868
0x180058e17  mov     [rbp+4Fh+var_60], rax
0x180058e1b  lea     rax, aMidixprocBuffe; "MidiXProc buffer added to queue will in"...
0x180058e22  mov     rcx, [rdi+40h]
0x180058e26  mov     [rbp+4Fh+var_68], rax
0x180058e2a  lea     rax, aCmidixprocSend; "CMidiXProc::SendMidiMessageInternal"
0x180058e31  mov     qword ptr [rbp+4Fh+var_78], rax
0x180058e35  lea     rax, [rbp+4Fh+var_50]
0x180058e39  mov     [rsp+60h], rax
0x180058e3e  lea     rax, [rbp+4Fh+var_58]
0x180058e42  mov     [rsp+100h+var_A8], rax
0x180058e47  lea     rax, [rbp+4Fh+var_90]
0x180058e4b  mov     [rsp+100h+var_B0], rax
0x180058e50  lea     rax, [rbp+4Fh+var_8C]
0x180058e54  mov     [rsp+100h+var_B8], rax
0x180058e59  lea     rax, [rbp+4Fh+PerformanceCount]
0x180058e5d  mov     [rsp+100h+var_C0], rax
0x180058e62  lea     rax, [rbp+4Fh+var_60]
0x180058e66  mov     [rsp+100h+var_C8], rax
0x180058e6b  lea     rax, [rbp+4Fh+var_68]
0x180058e6f  mov     [rsp+100h+var_D0], rax
0x180058e74  lea     rax, [rbp+4Fh+var_70]
0x180058e78  mov     [rbp+4Fh+var_50], rcx
0x180058e7c  mov     rcx, [rdi+38h]
0x180058e80  mov     [rbp+4Fh+var_58], rcx
0x180058e84  mov     cl, [rsi]
0x180058e86  mov     [rsp+100h+var_D8], rax
0x180058e8b  lea     rax, [rbp+4Fh+var_78]
0x180058e8f  mov     [rbp+4Fh+var_90], cl
0x180058e92  mov     rcx, r8
0x180058e95  mov     qword ptr [rsp+100h+var_E0], rax; int
0x180058e9a  mov     [rbp+4Fh+var_8C], r12d
0x180058e9e  mov     dword ptr [rbp+4Fh+PerformanceCount], r15d
0x180058ea2  mov     [rbp+4Fh+var_70], rdi
0x180058ea6  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U2@U?$_tlgWrapperByVal@$03@@U4@U?$_tlgWrapperByVal@$00@@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@4AEBU?$_tlgWrapperByVal@$03@@6AEBU?$_tlgWrapperByVal@$00@@44@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &)
0x180058eab  mov     r14d, [rbp+4Fh+arg_8]
0x180058eaf  test    rbx, rbx
0x180058eb2  jz      short loc_180058EBD
0x180058eb4  mov     rcx, rbx; lpCriticalSection
0x180058eb7  call    cs:__imp_LeaveCriticalSection
0x180058ebd  test    r13b, r13b
0x180058ec0  jz      short loc_180058F08
0x180058ec2  test    r14b, 1
0x180058ec6  jz      loc_1800592A7
0x180058ecc  mov     r9d, [rbp+4Fh+var_44]; unsigned int
0x180058ed0  mov     rcx, rdi; this
0x180058ed3  mov     r8d, [rbp+4Fh+var_7C]; unsigned int
0x180058ed7  mov     edx, [rbp+4Fh+var_48]; unsigned int
  ... truncated ...
```
