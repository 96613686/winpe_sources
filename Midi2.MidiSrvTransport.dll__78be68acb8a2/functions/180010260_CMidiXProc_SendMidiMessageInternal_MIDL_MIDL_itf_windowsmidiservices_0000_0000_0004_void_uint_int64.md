# CMidiXProc::SendMidiMessageInternal(__MIDL___MIDL_itf_windowsmidiservices_0000_0000_0004,void *,uint,__int64)

- ea: `0x180010260`
- end: `0x180010b08`
- name: `?SendMidiMessageInternal@CMidiXProc@@AEAAJW4__MIDL___MIDL_itf_windowsmidiservices_0000_0000_0004@@PEAXI_J@Z`
- size: `2216`
- prototype: `__int64 __fastcall(__int64, char, const wchar_t *, unsigned int, LARGE_INTEGER)`
- caller_count: `1`
- callee_count: `10`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180010094`

## callees

- `0x180001abc`
- `0x180007e04`
- `0x180007e24`
- `0x180009014`
- `0x18000bc80`
- `0x18000f984`
- `0x180010260`
- `0x180010cc0`
- `0x18001131c`
- `0x180014080`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001058a`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800109ee`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001058a`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800109ee`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800105b6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800106eb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800108d2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800105b6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800106eb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800108d2`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800102da`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180010786`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800102da`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180010786`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800102c8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180010774`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800102c8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180010774`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180010565`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800109cb`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180010565`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800109cb`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x180010356`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x1800107f9`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x180010356`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x1800107f9`

## string_xrefs

- `0x18001043f`: `MidiXProc stall detected during send, buffer dropped.`

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
        v61 = (__int16 *)&unk_18001A2F8;
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
            v61 = word_18001A862;
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
        v61 = &word_18001A38E;
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
              (unsigned int)word_18001A492,
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
      v26 = (__int16 *)&dword_18001A7CC;
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
          v26 = (__int16 *)&unk_18001A6A0;
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
      v26 = &word_18001A736;
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
      v42 = word_18001A60A;
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
      v42 = (__int16 *)&dword_18001A574;
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
0x180010260  mov     rax, rsp
0x180010263  mov     [rax+8], rbx
0x180010267  mov     [rax+20h], r9d
0x18001026b  mov     [rax+18h], r8
0x18001026f  mov     [rax+10h], edx
0x180010272  push    rbp
0x180010273  push    rsi
0x180010274  push    rdi
0x180010275  push    r12
0x180010277  push    r13
0x180010279  push    r14
0x18001027b  push    r15
0x18001027d  lea     rbp, [rax-57h]
0x180010281  sub     rsp, 0D0h
0x180010288  mov     ebx, r9d
0x18001028b  mov     r14d, edx
0x18001028e  mov     rdi, rcx
0x180010291  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_MIDI2SendTimeout@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_MIDI2SendTimeout@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_MIDI2SendTimeout> `wil::Feature<__WilFeatureTraits_Feature_Servicing_MIDI2SendTimeout>::GetImpl(void)'::`2'::impl
0x180010298  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_MIDI2SendTimeout@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_MIDI2SendTimeout>::__private_IsEnabled(void)
0x18001029d  mov     r13, [rdi+70h]
0x1800102a1  lea     ecx, [rbx+10h]
0x1800102a4  mov     [rbp+4Fh+var_44], ecx
0x1800102a7  lea     rbx, [rdi+8]
0x1800102ab  mov     [rbp+4Fh+var_7C], 0
0x1800102b2  mov     rcx, rbx; lpCriticalSection
0x1800102b5  mov     [rbp+4Fh+var_48], 0
0x1800102bc  test    al, al
0x1800102be  jz      loc_180010771
0x1800102c4  mov     [rbp+4Fh+var_80], 0
0x1800102c8  call    cs:__imp_EnterCriticalSection
0x1800102ce  mov     rcx, [rdi+70h]
0x1800102d2  mov     rsi, [rbp+57h]
0x1800102d6  mov     rcx, [rcx+40h]; hEvent
0x1800102da  call    cs:__imp_ResetEvent
0x1800102e0  test    eax, eax
0x1800102e2  jz      loc_180010AEC
0x1800102e8  mov     rcx, [r13+28h]
0x1800102ec  xor     edx, edx
0x1800102ee  xor     eax, eax
0x1800102f0  lock cmpxchg [rcx], edx
0x1800102f4  mov     rcx, [r13+30h]
0x1800102f8  mov     r12d, eax
0x1800102fb  xor     eax, eax
0x1800102fd  lock cmpxchg [rcx], edx
0x180010301  mov     r15d, eax
0x180010304  cmp     eax, r12d
0x180010307  ja      short loc_180010315
0x180010309  mov     eax, [r13+20h]
0x18001030d  sub     eax, r12d
0x180010310  add     eax, r15d
0x180010313  jmp     short loc_180010318
0x180010315  sub     eax, r12d
0x180010318  mov     ecx, [rbp+4Fh+var_44]
0x18001031b  dec     eax
0x18001031d  cmp     eax, ecx
0x18001031f  jnb     loc_180010523
0x180010325  lea     rsi, [rdi+30h]
0x180010329  cmp     [rsi], dl
0x18001032b  jnz     loc_1800104E3
0x180010331  mov     rax, [rdi+78h]
0x180010335  lea     rdx, [rbp+4Fh+Handles]; lpHandles
0x180010339  mov     [rbp+4Fh+Handles], rax
0x18001033d  xor     r8d, r8d; bWaitAll
0x180010340  mov     rax, [rdi+70h]
0x180010344  mov     r9d, 3E8h; dwMilliseconds
0x18001034a  mov     rcx, [rax+40h]
0x18001034e  mov     [rbp+4Fh+var_38], rcx
0x180010352  lea     ecx, [r8+2]; nCount
0x180010356  call    cs:__imp_WaitForMultipleObjects
0x18001035c  cmp     eax, 1
0x18001035f  jz      loc_1800102CE
0x180010365  inc     qword ptr [rdi+40h]
0x180010369  test    eax, eax
0x18001036b  jnz     loc_180010416
0x180010371  call    ?Provider@MidiXProcTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; MidiXProcTelemetryProvider::Provider(void)
0x180010376  mov     r8, rax
0x180010379  mov     ecx, [rax]
0x18001037b  cmp     ecx, 4
0x18001037e  jbe     loc_1800104DA
0x180010384  mov     rcx, [rdi+40h]
0x180010388  lea     rax, aMidixprocTermi; "MidiXProc terminated, buffer dropped."
0x18001038f  mov     rdx, [rbp+4Fh+Src]
0x180010393  mov     [rbp+4Fh+var_60], rax
0x180010397  lea     rax, aCmidixprocSend; "CMidiXProc::SendMidiMessageInternal"
0x18001039e  mov     [rbp+4Fh+var_50], rax
0x1800103a2  lea     rax, [rbp+4Fh+var_78]
0x1800103a6  mov     [rsp+60h], rax
0x1800103ab  lea     rax, [rbp+4Fh+var_70]
0x1800103af  mov     [rsp+100h+var_A8], rax
0x1800103b4  lea     rax, [rbp+4Fh+var_90]
0x1800103b8  mov     [rsp+100h+var_B0], rax
0x1800103bd  lea     rax, [rbp+4Fh+PerformanceCount]
0x1800103c1  mov     [rsp+100h+var_B8], rax
0x1800103c6  lea     rax, [rbp+4Fh+var_8C]
0x1800103ca  mov     [rsp+100h+var_C0], rax
0x1800103cf  lea     rax, [rbp+4Fh+var_68]
0x1800103d3  mov     [rsp+100h+var_C8], rax
0x1800103d8  lea     rax, [rbp+4Fh+var_60]
0x1800103dc  mov     [rsp+100h+var_D0], rax
0x1800103e1  lea     rax, [rbp+4Fh+var_58]
0x1800103e5  mov     qword ptr [rbp+4Fh+var_78], rcx
0x1800103e9  mov     rcx, [rdi+38h]
0x1800103ed  mov     [rsp+100h+var_D8], rax
0x1800103f2  lea     rax, [rbp+4Fh+var_50]
0x1800103f6  mov     [rbp+4Fh+var_68], rdx
0x1800103fa  lea     rdx, unk_18001A6A0
0x180010401  mov     [rbp+4Fh+var_70], rcx
0x180010405  mov     dword ptr [rbp+4Fh+PerformanceCount], r12d
0x180010409  mov     [rbp+4Fh+var_8C], r15d
0x18001040d  mov     [rbp+4Fh+var_58], rdi
0x180010411  jmp     loc_1800104C8
0x180010416  cmp     eax, 102h
0x18001041b  jnz     loc_1800104DA
0x180010421  mov     byte ptr [rsi], 1
0x180010424  mov     [rdi+34h], r15d
0x180010428  call    ?Provider@MidiXProcTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; MidiXProcTelemetryProvider::Provider(void)
0x18001042d  mov     r8, rax
0x180010430  mov     ecx, [rax]
0x180010432  cmp     ecx, 4
0x180010435  jbe     loc_1800104DA
0x18001043b  mov     rdx, [rbp+4Fh+Src]
0x18001043f  lea     rax, aMidixprocStall_0; "MidiXProc stall detected during send, b"...
0x180010446  mov     [rbp+4Fh+var_60], rdx
0x18001044a  lea     rdx, word_18001A736
0x180010451  mov     rcx, [rdi+40h]
0x180010455  mov     [rbp+4Fh+var_68], rax
0x180010459  lea     rax, aCmidixprocSend; "CMidiXProc::SendMidiMessageInternal"
0x180010460  mov     qword ptr [rbp+4Fh+var_78], rax
0x180010464  lea     rax, [rbp+4Fh+var_50]
0x180010468  mov     [rsp+60h], rax
0x18001046d  lea     rax, [rbp+4Fh+var_58]
0x180010471  mov     [rsp+100h+var_A8], rax
0x180010476  lea     rax, [rbp+4Fh+var_90]
0x18001047a  mov     [rsp+100h+var_B0], rax
0x18001047f  lea     rax, [rbp+4Fh+var_8C]
0x180010483  mov     [rsp+100h+var_B8], rax
0x180010488  lea     rax, [rbp+4Fh+PerformanceCount]
0x18001048c  mov     [rsp+100h+var_C0], rax
0x180010491  lea     rax, [rbp+4Fh+var_60]
0x180010495  mov     [rsp+100h+var_C8], rax
0x18001049a  lea     rax, [rbp+4Fh+var_68]
0x18001049e  mov     [rsp+100h+var_D0], rax
0x1800104a3  lea     rax, [rbp+4Fh+var_70]
0x1800104a7  mov     [rbp+4Fh+var_50], rcx
0x1800104ab  mov     rcx, [rdi+38h]
0x1800104af  mov     [rsp+100h+var_D8], rax
0x1800104b4  lea     rax, [rbp+4Fh+var_78]
0x1800104b8  mov     [rbp+4Fh+var_8C], r12d
0x1800104bc  mov     [rbp+4Fh+var_58], rcx
0x1800104c0  mov     [rbp+4Fh+var_70], rdi
0x1800104c4  mov     dword ptr [rbp+4Fh+PerformanceCount], r15d
0x1800104c8  mov     cl, [rsi]
0x1800104ca  mov     [rbp+4Fh+var_90], cl
0x1800104cd  mov     rcx, r8
0x1800104d0  mov     qword ptr [rsp+100h+var_E0], rax
0x1800104d5  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U2@U?$_tlgWrapperByVal@$03@@U4@U?$_tlgWrapperByVal@$00@@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@4AEBU?$_tlgWrapperByVal@$03@@6AEBU?$_tlgWrapperByVal@$00@@44@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &)
0x1800104da  mov     r13b, [rbp+4Fh+var_80]
0x1800104de  jmp     loc_1800106E3
0x1800104e3  movdqu  xmm0, xmmword ptr [rdi+38h]
0x1800104e8  movdqa  xmm1, cs:__xmm@00000000000000010000000000000001
0x1800104f0  paddq   xmm1, xmm0
0x1800104f4  movdqu  xmmword ptr [rdi+38h], xmm1
0x1800104f9  call    ?Provider@MidiXProcTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; MidiXProcTelemetryProvider::Provider(void)
0x1800104fe  mov     r8, rax
0x180010501  mov     ecx, [rax]
0x180010503  cmp     ecx, 4
0x180010506  jbe     short loc_1800104DA
0x180010508  mov     rdx, [rbp+4Fh+Src]
0x18001050c  lea     rax, aMidixprocStall; "MidiXProc stalled, buffer dropped."
0x180010513  mov     [rbp+4Fh+var_60], rdx
0x180010517  lea     rdx, dword_18001A7CC
0x18001051e  jmp     loc_180010451
0x180010523  mov     r14, [r13+18h]
0x180010527  lea     eax, [r12+rcx]
0x18001052b  div     dword ptr [r13+20h]
0x18001052f  mov     r9d, dword ptr [rbp+4Fh+Size]
0x180010533  lea     rcx, [r14+10h]
0x180010537  mov     [rbp+4Fh+var_8C], edx
0x18001053a  mov     r8d, r9d; Size
0x18001053d  mov     rdx, [rbp+4Fh+Src]; Src
0x180010541  add     rcx, r12; void *
0x180010544  mov     [r12+r14+8], r9d
0x180010549  call    memcpy_0
0x18001054e  mov     rax, [rbp+4Fh+arg_20]
0x180010552  xor     ecx, ecx
0x180010554  test    rax, rax
0x180010557  jnz     short loc_18001056F
0x180010559  cmp     [rdi], ecx
0x18001055b  jz      short loc_180010575
0x18001055d  mov     qword ptr [rbp+4Fh+PerformanceCount], rcx
0x180010561  lea     rcx, [rbp+4Fh+PerformanceCount]; lpPerformanceCount
0x180010565  call    cs:__imp_QueryPerformanceCounter
0x18001056b  mov     rax, qword ptr [rbp+4Fh+PerformanceCount]
0x18001056f  mov     [r12+r14], rax
0x180010573  jmp     short loc_180010579
0x180010575  mov     [r12+r14], rcx
0x180010579  mov     rax, [r13+28h]
0x18001057d  mov     ecx, [rbp+4Fh+var_8C]
0x180010580  xchg    ecx, [rax]
0x180010582  mov     rcx, [rdi+70h]
0x180010586  mov     rcx, [rcx+38h]; hEvent
0x18001058a  call    cs:__imp_SetEvent
0x180010590  xor     r14d, r14d
0x180010593  test    eax, eax
0x180010595  jnz     short loc_1800105D9
0x180010597  mov     edx, 2D4h; void *
0x18001059c  mov     rcx, [rbp+57h]; this
0x1800105a0  lea     r8, aAvcoreMidi2Lib_0; "avcore\\midi2\\libs\\midixproc\\midixpr"...
0x1800105a7  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800105ac  mov     edi, eax
0x1800105ae  test    rbx, rbx
0x1800105b1  jz      short loc_1800105BC
0x1800105b3  mov     rcx, rbx; lpCriticalSection
0x1800105b6  call    cs:__imp_LeaveCriticalSection
0x1800105bc  mov     eax, edi
0x1800105be  mov     rbx, [rsp+100h+arg_0]
0x1800105c6  add     rsp, 0D0h
0x1800105cd  pop     r15
0x1800105cf  pop     r14
0x1800105d1  pop     r13
0x1800105d3  pop     r12
0x1800105d5  pop     rdi
0x1800105d6  pop     rsi
0x1800105d7  pop     rbp
0x1800105d8  retn
0x1800105d9  lea     rsi, [rdi+30h]
0x1800105dd  mov     [rbp+4Fh+var_7C], r12d
0x1800105e1  mov     r13b, 1
0x1800105e4  mov     [rbp+4Fh+var_48], r15d
0x1800105e8  cmp     [rsi], r14b
0x1800105eb  jz      loc_1800106DF
0x1800105f1  mov     [rdi+38h], r14
0x1800105f5  cmp     r15d, [rdi+34h]
0x1800105f9  jz      short loc_18001062D
0x1800105fb  mov     [rsi], r14b
0x1800105fe  mov     [rdi+34h], r14d
0x180010602  call    ?Provider@MidiXProcTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; MidiXProcTelemetryProvider::Provider(void)
0x180010607  mov     r8, rax
0x18001060a  mov     ecx, [rax]
0x18001060c  cmp     ecx, 4
0x18001060f  jbe     loc_1800106DF
0x180010615  mov     rax, [rbp+4Fh+Src]
0x180010619  lea     rdx, dword_18001A574
0x180010620  mov     [rbp+4Fh+var_60], rax
0x180010624  lea     rax, aMidixprocRecov; "MidiXProc recovered from stall."
0x18001062b  jmp     short loc_180010656
0x18001062d  call    ?Provider@MidiXProcTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; MidiXProcTelemetryProvider::Provider(void)
0x180010632  mov     r8, rax
0x180010635  mov     ecx, [rax]
0x180010637  cmp     ecx, 4
0x18001063a  jbe     loc_1800106DF
0x180010640  mov     rax, [rbp+4Fh+Src]
0x180010644  lea     rdx, word_18001A60A
0x18001064b  mov     [rbp+4Fh+var_60], rax
0x18001064f  lea     rax, aMidixprocBuffe; "MidiXProc buffer added to queue will in"...
0x180010656  mov     rcx, [rdi+40h]
0x18001065a  mov     [rbp+4Fh+var_68], rax
0x18001065e  lea     rax, aCmidixprocSend; "CMidiXProc::SendMidiMessageInternal"
0x180010665  mov     qword ptr [rbp+4Fh+var_78], rax
0x180010669  lea     rax, [rbp+4Fh+var_50]
0x18001066d  mov     [rsp+60h], rax
0x180010672  lea     rax, [rbp+4Fh+var_58]
0x180010676  mov     [rsp+100h+var_A8], rax
0x18001067b  lea     rax, [rbp+4Fh+var_90]
0x18001067f  mov     [rsp+100h+var_B0], rax
0x180010684  lea     rax, [rbp+4Fh+var_8C]
0x180010688  mov     [rsp+100h+var_B8], rax
0x18001068d  lea     rax, [rbp+4Fh+PerformanceCount]
0x180010691  mov     [rsp+100h+var_C0], rax
0x180010696  lea     rax, [rbp+4Fh+var_60]
0x18001069a  mov     [rsp+100h+var_C8], rax
0x18001069f  lea     rax, [rbp+4Fh+var_68]
0x1800106a3  mov     [rsp+100h+var_D0], rax
0x1800106a8  lea     rax, [rbp+4Fh+var_70]
0x1800106ac  mov     [rbp+4Fh+var_50], rcx
0x1800106b0  mov     rcx, [rdi+38h]
0x1800106b4  mov     [rbp+4Fh+var_58], rcx
0x1800106b8  mov     cl, [rsi]
0x1800106ba  mov     [rsp+100h+var_D8], rax
0x1800106bf  lea     rax, [rbp+4Fh+var_78]
0x1800106c3  mov     [rbp+4Fh+var_90], cl
0x1800106c6  mov     rcx, r8
0x1800106c9  mov     qword ptr [rsp+100h+var_E0], rax; int
0x1800106ce  mov     [rbp+4Fh+var_8C], r12d
0x1800106d2  mov     dword ptr [rbp+4Fh+PerformanceCount], r15d
0x1800106d6  mov     [rbp+4Fh+var_70], rdi
0x1800106da  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U2@U?$_tlgWrapperByVal@$03@@U4@U?$_tlgWrapperByVal@$00@@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@4AEBU?$_tlgWrapperByVal@$03@@6AEBU?$_tlgWrapperByVal@$00@@44@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &)
0x1800106df  mov     r14d, [rbp+4Fh+arg_8]
0x1800106e3  test    rbx, rbx
0x1800106e6  jz      short loc_1800106F1
0x1800106e8  mov     rcx, rbx; lpCriticalSection
0x1800106eb  call    cs:__imp_LeaveCriticalSection
0x1800106f1  test    r13b, r13b
0x1800106f4  jz      short loc_18001073C
0x1800106f6  test    r14b, 1
0x1800106fa  jz      loc_180010ADB
0x180010700  mov     r9d, [rbp+4Fh+var_44]; unsigned int
0x180010704  mov     rcx, rdi; this
0x180010707  mov     r8d, [rbp+4Fh+var_7C]; unsigned int
0x18001070b  mov     edx, [rbp+4Fh+var_48]; unsigned int
  ... truncated ...
```
