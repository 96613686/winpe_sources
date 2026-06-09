# CMidiXProc::SendMidiMessageInternal(__MIDL___MIDL_itf_windowsmidiservices_0000_0000_0004,void *,uint,__int64)

- ea: `0x18003d46c`
- end: `0x18003dd14`
- name: `?SendMidiMessageInternal@CMidiXProc@@AEAAJW4__MIDL___MIDL_itf_windowsmidiservices_0000_0000_0004@@PEAXI_J@Z`
- size: `2216`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x18003d298`

## callees

- `0x180002314`
- `0x180005254`
- `0x18000a7f4`
- `0x18000a814`
- `0x18000bb04`
- `0x18001fdb0`
- `0x18003d1d8`
- `0x18003d46c`
- `0x18003de34`
- `0x18003e2d0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18003d796`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18003dbfa`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18003d796`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18003dbfa`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003d7c2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003d8f7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003dade`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003d7c2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003d8f7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003dade`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18003d4e6`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18003d992`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18003d4e6`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18003d992`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003d4d4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003d980`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003d4d4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003d980`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18003d771`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18003dbd7`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18003d771`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18003dbd7`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x18003d562`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x18003da05`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x18003d562`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x18003da05`

## string_xrefs

- `0x18003d64b`: `MidiXProc stall detected during send, buffer dropped.`

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
  __int16 *v61; // rdx
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
  IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_MIDI2SendTimeout>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_MIDI2SendTimeout>::GetImpl'::`2'::impl);
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
        v61 = (__int16 *)&dword_180068F5C;
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
            v61 = &word_1800694C6;
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
        v61 = word_180068FF2;
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
              (unsigned int)&word_1800690F6,
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
      v26 = (__int16 *)&unk_180069430;
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
          v26 = (__int16 *)&dword_180069304;
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
      v26 = word_18006939A;
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
      v42 = &word_18006926E;
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
      v42 = (__int16 *)&unk_1800691D8;
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
0x18003d46c  mov     rax, rsp
0x18003d46f  mov     [rax+8], rbx
0x18003d473  mov     [rax+20h], r9d
0x18003d477  mov     [rax+18h], r8
0x18003d47b  mov     [rax+10h], edx
0x18003d47e  push    rbp
0x18003d47f  push    rsi
0x18003d480  push    rdi
0x18003d481  push    r12
0x18003d483  push    r13
0x18003d485  push    r14
0x18003d487  push    r15
0x18003d489  lea     rbp, [rax-57h]
0x18003d48d  sub     rsp, 0D0h
0x18003d494  mov     ebx, r9d
0x18003d497  mov     r14d, edx
0x18003d49a  mov     rdi, rcx
0x18003d49d  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_MIDI2SendTimeout@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_MIDI2SendTimeout@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_MIDI2SendTimeout> `wil::Feature<__WilFeatureTraits_Feature_Servicing_MIDI2SendTimeout>::GetImpl(void)'::`2'::impl
0x18003d4a4  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_MIDI2SendTimeout@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_MIDI2SendTimeout>::__private_IsEnabled(void)
0x18003d4a9  mov     r13, [rdi+70h]
0x18003d4ad  lea     ecx, [rbx+10h]
0x18003d4b0  mov     [rbp+4Fh+var_44], ecx
0x18003d4b3  lea     rbx, [rdi+8]
0x18003d4b7  mov     [rbp+4Fh+var_7C], 0
0x18003d4be  mov     rcx, rbx; lpCriticalSection
0x18003d4c1  mov     [rbp+4Fh+var_48], 0
0x18003d4c8  test    al, al
0x18003d4ca  jz      loc_18003D97D
0x18003d4d0  mov     [rbp+4Fh+var_80], 0
0x18003d4d4  call    cs:__imp_EnterCriticalSection
0x18003d4da  mov     rcx, [rdi+70h]
0x18003d4de  mov     rsi, [rbp+57h]
0x18003d4e2  mov     rcx, [rcx+40h]; hEvent
0x18003d4e6  call    cs:__imp_ResetEvent
0x18003d4ec  test    eax, eax
0x18003d4ee  jz      loc_18003DCF8
0x18003d4f4  mov     rcx, [r13+28h]
0x18003d4f8  xor     edx, edx
0x18003d4fa  xor     eax, eax
0x18003d4fc  lock cmpxchg [rcx], edx
0x18003d500  mov     rcx, [r13+30h]
0x18003d504  mov     r12d, eax
0x18003d507  xor     eax, eax
0x18003d509  lock cmpxchg [rcx], edx
0x18003d50d  mov     r15d, eax
0x18003d510  cmp     eax, r12d
0x18003d513  ja      short loc_18003D521
0x18003d515  mov     eax, [r13+20h]
0x18003d519  sub     eax, r12d
0x18003d51c  add     eax, r15d
0x18003d51f  jmp     short loc_18003D524
0x18003d521  sub     eax, r12d
0x18003d524  mov     ecx, [rbp+4Fh+var_44]
0x18003d527  dec     eax
0x18003d529  cmp     eax, ecx
0x18003d52b  jnb     loc_18003D72F
0x18003d531  lea     rsi, [rdi+30h]
0x18003d535  cmp     [rsi], dl
0x18003d537  jnz     loc_18003D6EF
0x18003d53d  mov     rax, [rdi+78h]
0x18003d541  lea     rdx, [rbp+4Fh+Handles]; lpHandles
0x18003d545  mov     [rbp+4Fh+Handles], rax
0x18003d549  xor     r8d, r8d; bWaitAll
0x18003d54c  mov     rax, [rdi+70h]
0x18003d550  mov     r9d, 3E8h; dwMilliseconds
0x18003d556  mov     rcx, [rax+40h]
0x18003d55a  mov     [rbp+4Fh+var_38], rcx
0x18003d55e  lea     ecx, [r8+2]; nCount
0x18003d562  call    cs:__imp_WaitForMultipleObjects
0x18003d568  cmp     eax, 1
0x18003d56b  jz      loc_18003D4DA
0x18003d571  inc     qword ptr [rdi+40h]
0x18003d575  test    eax, eax
0x18003d577  jnz     loc_18003D622
0x18003d57d  call    ?Provider@MidiXProcTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; MidiXProcTelemetryProvider::Provider(void)
0x18003d582  mov     r8, rax
0x18003d585  mov     ecx, [rax]
0x18003d587  cmp     ecx, 4
0x18003d58a  jbe     loc_18003D6E6
0x18003d590  mov     rcx, [rdi+40h]
0x18003d594  lea     rax, aMidixprocTermi; "MidiXProc terminated, buffer dropped."
0x18003d59b  mov     rdx, [rbp+4Fh+Src]
0x18003d59f  mov     [rbp+4Fh+var_60], rax
0x18003d5a3  lea     rax, aCmidixprocSend; "CMidiXProc::SendMidiMessageInternal"
0x18003d5aa  mov     [rbp+4Fh+var_50], rax
0x18003d5ae  lea     rax, [rbp+4Fh+var_78]
0x18003d5b2  mov     [rsp+60h], rax
0x18003d5b7  lea     rax, [rbp+4Fh+var_70]
0x18003d5bb  mov     [rsp+100h+var_A8], rax
0x18003d5c0  lea     rax, [rbp+4Fh+var_90]
0x18003d5c4  mov     [rsp+100h+var_B0], rax
0x18003d5c9  lea     rax, [rbp+4Fh+PerformanceCount]
0x18003d5cd  mov     [rsp+100h+var_B8], rax
0x18003d5d2  lea     rax, [rbp+4Fh+var_8C]
0x18003d5d6  mov     [rsp+100h+var_C0], rax
0x18003d5db  lea     rax, [rbp+4Fh+var_68]
0x18003d5df  mov     [rsp+100h+var_C8], rax
0x18003d5e4  lea     rax, [rbp+4Fh+var_60]
0x18003d5e8  mov     [rsp+100h+var_D0], rax
0x18003d5ed  lea     rax, [rbp+4Fh+var_58]
0x18003d5f1  mov     qword ptr [rbp+4Fh+var_78], rcx
0x18003d5f5  mov     rcx, [rdi+38h]
0x18003d5f9  mov     [rsp+100h+var_D8], rax
0x18003d5fe  lea     rax, [rbp+4Fh+var_50]
0x18003d602  mov     [rbp+4Fh+var_68], rdx
0x18003d606  lea     rdx, dword_180069304
0x18003d60d  mov     [rbp+4Fh+var_70], rcx
0x18003d611  mov     dword ptr [rbp+4Fh+PerformanceCount], r12d
0x18003d615  mov     [rbp+4Fh+var_8C], r15d
0x18003d619  mov     [rbp+4Fh+var_58], rdi
0x18003d61d  jmp     loc_18003D6D4
0x18003d622  cmp     eax, 102h
0x18003d627  jnz     loc_18003D6E6
0x18003d62d  mov     byte ptr [rsi], 1
0x18003d630  mov     [rdi+34h], r15d
0x18003d634  call    ?Provider@MidiXProcTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; MidiXProcTelemetryProvider::Provider(void)
0x18003d639  mov     r8, rax
0x18003d63c  mov     ecx, [rax]
0x18003d63e  cmp     ecx, 4
0x18003d641  jbe     loc_18003D6E6
0x18003d647  mov     rdx, [rbp+4Fh+Src]
0x18003d64b  lea     rax, aMidixprocStall_0; "MidiXProc stall detected during send, b"...
0x18003d652  mov     [rbp+4Fh+var_60], rdx
0x18003d656  lea     rdx, word_18006939A
0x18003d65d  mov     rcx, [rdi+40h]
0x18003d661  mov     [rbp+4Fh+var_68], rax
0x18003d665  lea     rax, aCmidixprocSend; "CMidiXProc::SendMidiMessageInternal"
0x18003d66c  mov     qword ptr [rbp+4Fh+var_78], rax
0x18003d670  lea     rax, [rbp+4Fh+var_50]
0x18003d674  mov     [rsp+60h], rax
0x18003d679  lea     rax, [rbp+4Fh+var_58]
0x18003d67d  mov     [rsp+100h+var_A8], rax
0x18003d682  lea     rax, [rbp+4Fh+var_90]
0x18003d686  mov     [rsp+100h+var_B0], rax
0x18003d68b  lea     rax, [rbp+4Fh+var_8C]
0x18003d68f  mov     [rsp+100h+var_B8], rax
0x18003d694  lea     rax, [rbp+4Fh+PerformanceCount]
0x18003d698  mov     [rsp+100h+var_C0], rax
0x18003d69d  lea     rax, [rbp+4Fh+var_60]
0x18003d6a1  mov     [rsp+100h+var_C8], rax
0x18003d6a6  lea     rax, [rbp+4Fh+var_68]
0x18003d6aa  mov     [rsp+100h+var_D0], rax
0x18003d6af  lea     rax, [rbp+4Fh+var_70]
0x18003d6b3  mov     [rbp+4Fh+var_50], rcx
0x18003d6b7  mov     rcx, [rdi+38h]
0x18003d6bb  mov     [rsp+100h+var_D8], rax
0x18003d6c0  lea     rax, [rbp+4Fh+var_78]
0x18003d6c4  mov     [rbp+4Fh+var_8C], r12d
0x18003d6c8  mov     [rbp+4Fh+var_58], rcx
0x18003d6cc  mov     [rbp+4Fh+var_70], rdi
0x18003d6d0  mov     dword ptr [rbp+4Fh+PerformanceCount], r15d
0x18003d6d4  mov     cl, [rsi]
0x18003d6d6  mov     [rbp+4Fh+var_90], cl
0x18003d6d9  mov     rcx, r8
0x18003d6dc  mov     qword ptr [rsp+100h+var_E0], rax
0x18003d6e1  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U2@U?$_tlgWrapperByVal@$03@@U4@U?$_tlgWrapperByVal@$00@@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@4AEBU?$_tlgWrapperByVal@$03@@6AEBU?$_tlgWrapperByVal@$00@@44@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &)
0x18003d6e6  mov     r13b, [rbp+4Fh+var_80]
0x18003d6ea  jmp     loc_18003D8EF
0x18003d6ef  movdqu  xmm0, xmmword ptr [rdi+38h]
0x18003d6f4  movdqa  xmm1, cs:__xmm@00000000000000010000000000000001
0x18003d6fc  paddq   xmm1, xmm0
0x18003d700  movdqu  xmmword ptr [rdi+38h], xmm1
0x18003d705  call    ?Provider@MidiXProcTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; MidiXProcTelemetryProvider::Provider(void)
0x18003d70a  mov     r8, rax
0x18003d70d  mov     ecx, [rax]
0x18003d70f  cmp     ecx, 4
0x18003d712  jbe     short loc_18003D6E6
0x18003d714  mov     rdx, [rbp+4Fh+Src]
0x18003d718  lea     rax, aMidixprocStall; "MidiXProc stalled, buffer dropped."
0x18003d71f  mov     [rbp+4Fh+var_60], rdx
0x18003d723  lea     rdx, unk_180069430
0x18003d72a  jmp     loc_18003D65D
0x18003d72f  mov     r14, [r13+18h]
0x18003d733  lea     eax, [r12+rcx]
0x18003d737  div     dword ptr [r13+20h]
0x18003d73b  mov     r9d, dword ptr [rbp+4Fh+Size]
0x18003d73f  lea     rcx, [r14+10h]
0x18003d743  mov     [rbp+4Fh+var_8C], edx
0x18003d746  mov     r8d, r9d; Size
0x18003d749  mov     rdx, [rbp+4Fh+Src]; Src
0x18003d74d  add     rcx, r12; void *
0x18003d750  mov     [r12+r14+8], r9d
0x18003d755  call    memcpy_0
0x18003d75a  mov     rax, [rbp+4Fh+arg_20]
0x18003d75e  xor     ecx, ecx
0x18003d760  test    rax, rax
0x18003d763  jnz     short loc_18003D77B
0x18003d765  cmp     [rdi], ecx
0x18003d767  jz      short loc_18003D781
0x18003d769  mov     qword ptr [rbp+4Fh+PerformanceCount], rcx
0x18003d76d  lea     rcx, [rbp+4Fh+PerformanceCount]; lpPerformanceCount
0x18003d771  call    cs:__imp_QueryPerformanceCounter
0x18003d777  mov     rax, qword ptr [rbp+4Fh+PerformanceCount]
0x18003d77b  mov     [r12+r14], rax
0x18003d77f  jmp     short loc_18003D785
0x18003d781  mov     [r12+r14], rcx
0x18003d785  mov     rax, [r13+28h]
0x18003d789  mov     ecx, [rbp+4Fh+var_8C]
0x18003d78c  xchg    ecx, [rax]
0x18003d78e  mov     rcx, [rdi+70h]
0x18003d792  mov     rcx, [rcx+38h]; hEvent
0x18003d796  call    cs:__imp_SetEvent
0x18003d79c  xor     r14d, r14d
0x18003d79f  test    eax, eax
0x18003d7a1  jnz     short loc_18003D7E5
0x18003d7a3  mov     edx, 2D4h; void *
0x18003d7a8  mov     rcx, [rbp+57h]; this
0x18003d7ac  lea     r8, aAvcoreMidi2Lib_3; "avcore\\midi2\\libs\\midixproc\\midixpr"...
0x18003d7b3  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18003d7b8  mov     edi, eax
0x18003d7ba  test    rbx, rbx
0x18003d7bd  jz      short loc_18003D7C8
0x18003d7bf  mov     rcx, rbx; lpCriticalSection
0x18003d7c2  call    cs:__imp_LeaveCriticalSection
0x18003d7c8  mov     eax, edi
0x18003d7ca  mov     rbx, [rsp+100h+arg_0]
0x18003d7d2  add     rsp, 0D0h
0x18003d7d9  pop     r15
0x18003d7db  pop     r14
0x18003d7dd  pop     r13
0x18003d7df  pop     r12
0x18003d7e1  pop     rdi
0x18003d7e2  pop     rsi
0x18003d7e3  pop     rbp
0x18003d7e4  retn
0x18003d7e5  lea     rsi, [rdi+30h]
0x18003d7e9  mov     [rbp+4Fh+var_7C], r12d
0x18003d7ed  mov     r13b, 1
0x18003d7f0  mov     [rbp+4Fh+var_48], r15d
0x18003d7f4  cmp     [rsi], r14b
0x18003d7f7  jz      loc_18003D8EB
0x18003d7fd  mov     [rdi+38h], r14
0x18003d801  cmp     r15d, [rdi+34h]
0x18003d805  jz      short loc_18003D839
0x18003d807  mov     [rsi], r14b
0x18003d80a  mov     [rdi+34h], r14d
0x18003d80e  call    ?Provider@MidiXProcTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; MidiXProcTelemetryProvider::Provider(void)
0x18003d813  mov     r8, rax
0x18003d816  mov     ecx, [rax]
0x18003d818  cmp     ecx, 4
0x18003d81b  jbe     loc_18003D8EB
0x18003d821  mov     rax, [rbp+4Fh+Src]
0x18003d825  lea     rdx, unk_1800691D8
0x18003d82c  mov     [rbp+4Fh+var_60], rax
0x18003d830  lea     rax, aMidixprocRecov; "MidiXProc recovered from stall."
0x18003d837  jmp     short loc_18003D862
0x18003d839  call    ?Provider@MidiXProcTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; MidiXProcTelemetryProvider::Provider(void)
0x18003d83e  mov     r8, rax
0x18003d841  mov     ecx, [rax]
0x18003d843  cmp     ecx, 4
0x18003d846  jbe     loc_18003D8EB
0x18003d84c  mov     rax, [rbp+4Fh+Src]
0x18003d850  lea     rdx, word_18006926E
0x18003d857  mov     [rbp+4Fh+var_60], rax
0x18003d85b  lea     rax, aMidixprocBuffe; "MidiXProc buffer added to queue will in"...
0x18003d862  mov     rcx, [rdi+40h]
0x18003d866  mov     [rbp+4Fh+var_68], rax
0x18003d86a  lea     rax, aCmidixprocSend; "CMidiXProc::SendMidiMessageInternal"
0x18003d871  mov     qword ptr [rbp+4Fh+var_78], rax
0x18003d875  lea     rax, [rbp+4Fh+var_50]
0x18003d879  mov     [rsp+60h], rax
0x18003d87e  lea     rax, [rbp+4Fh+var_58]
0x18003d882  mov     [rsp+100h+var_A8], rax
0x18003d887  lea     rax, [rbp+4Fh+var_90]
0x18003d88b  mov     [rsp+100h+var_B0], rax
0x18003d890  lea     rax, [rbp+4Fh+var_8C]
0x18003d894  mov     [rsp+100h+var_B8], rax
0x18003d899  lea     rax, [rbp+4Fh+PerformanceCount]
0x18003d89d  mov     [rsp+100h+var_C0], rax
0x18003d8a2  lea     rax, [rbp+4Fh+var_60]
0x18003d8a6  mov     [rsp+100h+var_C8], rax
0x18003d8ab  lea     rax, [rbp+4Fh+var_68]
0x18003d8af  mov     [rsp+100h+var_D0], rax
0x18003d8b4  lea     rax, [rbp+4Fh+var_70]
0x18003d8b8  mov     [rbp+4Fh+var_50], rcx
0x18003d8bc  mov     rcx, [rdi+38h]
0x18003d8c0  mov     [rbp+4Fh+var_58], rcx
0x18003d8c4  mov     cl, [rsi]
0x18003d8c6  mov     [rsp+100h+var_D8], rax
0x18003d8cb  lea     rax, [rbp+4Fh+var_78]
0x18003d8cf  mov     [rbp+4Fh+var_90], cl
0x18003d8d2  mov     rcx, r8
0x18003d8d5  mov     qword ptr [rsp+100h+var_E0], rax; int
0x18003d8da  mov     [rbp+4Fh+var_8C], r12d
0x18003d8de  mov     dword ptr [rbp+4Fh+PerformanceCount], r15d
0x18003d8e2  mov     [rbp+4Fh+var_70], rdi
0x18003d8e6  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U2@U?$_tlgWrapperByVal@$03@@U4@U?$_tlgWrapperByVal@$00@@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@4AEBU?$_tlgWrapperByVal@$03@@6AEBU?$_tlgWrapperByVal@$00@@44@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &)
0x18003d8eb  mov     r14d, [rbp+4Fh+arg_8]
0x18003d8ef  test    rbx, rbx
0x18003d8f2  jz      short loc_18003D8FD
0x18003d8f4  mov     rcx, rbx; lpCriticalSection
0x18003d8f7  call    cs:__imp_LeaveCriticalSection
0x18003d8fd  test    r13b, r13b
0x18003d900  jz      short loc_18003D948
0x18003d902  test    r14b, 1
0x18003d906  jz      loc_18003DCE7
0x18003d90c  mov     r9d, [rbp+4Fh+var_44]; unsigned int
0x18003d910  mov     rcx, rdi; this
0x18003d913  mov     r8d, [rbp+4Fh+var_7C]; unsigned int
0x18003d917  mov     edx, [rbp+4Fh+var_48]; unsigned int
  ... truncated ...
```
