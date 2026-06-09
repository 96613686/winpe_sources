# CMidiXProc::SendMidiMessageInternal(__MIDL___MIDL_itf_windowsmidiservices_0000_0000_0004,void *,uint,__int64)

- ea: `0x140047258`
- end: `0x140047b00`
- name: `?SendMidiMessageInternal@CMidiXProc@@AEAAJW4__MIDL___MIDL_itf_windowsmidiservices_0000_0000_0004@@PEAXI_J@Z`
- size: `2216`
- prototype: `__int64 __fastcall(__int64, char, const wchar_t *, unsigned int, LARGE_INTEGER)`
- caller_count: `1`
- callee_count: `10`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x140047084`

## callees

- `0x140003500`
- `0x1400060e0`
- `0x14000a694`
- `0x14000a6b4`
- `0x14000c55c`
- `0x14000c598`
- `0x140046fc4`
- `0x140047258`
- `0x140047c20`
- `0x1400480bc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1400475ae`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1400476e3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1400478ca`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1400475ae`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1400476e3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1400478ca`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1400472d2`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x14004777e`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1400472d2`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x14004777e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1400472c0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14004776c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1400472c0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14004776c`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x140047582`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1400479e6`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x140047582`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1400479e6`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x14004755d`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1400479c3`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x14004755d`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1400479c3`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x14004734e`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x1400477f1`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x14004734e`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x1400477f1`

## string_xrefs

- `0x140047437`: `MidiXProc stall detected during send, buffer dropped.`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
        v61 = (__int16 *)byte_14008C695;
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
            v61 = &word_14008CC36;
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
        v61 = word_14008C762;
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
              (unsigned int)&word_14008C866,
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
      v26 = (__int16 *)&unk_14008CBA0;
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
          v26 = (__int16 *)&dword_14008CA74;
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
      v26 = word_14008CB0A;
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
      v42 = &word_14008C9DE;
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
      v42 = (__int16 *)&unk_14008C948;
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
0x140047258  mov     rax, rsp
0x14004725b  mov     [rax+8], rbx
0x14004725f  mov     [rax+20h], r9d
0x140047263  mov     [rax+18h], r8
0x140047267  mov     [rax+10h], edx
0x14004726a  push    rbp
0x14004726b  push    rsi
0x14004726c  push    rdi
0x14004726d  push    r12
0x14004726f  push    r13
0x140047271  push    r14
0x140047273  push    r15
0x140047275  lea     rbp, [rax-57h]
0x140047279  sub     rsp, 0D0h
0x140047280  mov     ebx, r9d
0x140047283  mov     r14d, edx
0x140047286  mov     rdi, rcx
0x140047289  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_MIDI2SendTimeout@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_MIDI2SendTimeout@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_MIDI2SendTimeout> `wil::Feature<__WilFeatureTraits_Feature_Servicing_MIDI2SendTimeout>::GetImpl(void)'::`2'::impl
0x140047290  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_MIDI2SendTimeout@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_MIDI2SendTimeout>::__private_IsEnabled(void)
0x140047295  mov     r13, [rdi+70h]
0x140047299  lea     ecx, [rbx+10h]
0x14004729c  mov     [rbp+4Fh+var_44], ecx
0x14004729f  lea     rbx, [rdi+8]
0x1400472a3  mov     [rbp+4Fh+var_7C], 0
0x1400472aa  mov     rcx, rbx; lpCriticalSection
0x1400472ad  mov     [rbp+4Fh+var_48], 0
0x1400472b4  test    al, al
0x1400472b6  jz      loc_140047769
0x1400472bc  mov     [rbp+4Fh+var_80], 0
0x1400472c0  call    cs:__imp_EnterCriticalSection
0x1400472c6  mov     rcx, [rdi+70h]
0x1400472ca  mov     rsi, [rbp+57h]
0x1400472ce  mov     rcx, [rcx+40h]; hEvent
0x1400472d2  call    cs:__imp_ResetEvent
0x1400472d8  test    eax, eax
0x1400472da  jz      loc_140047AE4
0x1400472e0  mov     rcx, [r13+28h]
0x1400472e4  xor     edx, edx
0x1400472e6  xor     eax, eax
0x1400472e8  lock cmpxchg [rcx], edx
0x1400472ec  mov     rcx, [r13+30h]
0x1400472f0  mov     r12d, eax
0x1400472f3  xor     eax, eax
0x1400472f5  lock cmpxchg [rcx], edx
0x1400472f9  mov     r15d, eax
0x1400472fc  cmp     eax, r12d
0x1400472ff  ja      short loc_14004730D
0x140047301  mov     eax, [r13+20h]
0x140047305  sub     eax, r12d
0x140047308  add     eax, r15d
0x14004730b  jmp     short loc_140047310
0x14004730d  sub     eax, r12d
0x140047310  mov     ecx, [rbp+4Fh+var_44]
0x140047313  dec     eax
0x140047315  cmp     eax, ecx
0x140047317  jnb     loc_14004751B
0x14004731d  lea     rsi, [rdi+30h]
0x140047321  cmp     [rsi], dl
0x140047323  jnz     loc_1400474DB
0x140047329  mov     rax, [rdi+78h]
0x14004732d  lea     rdx, [rbp+4Fh+Handles]; lpHandles
0x140047331  mov     [rbp+4Fh+Handles], rax
0x140047335  xor     r8d, r8d; bWaitAll
0x140047338  mov     rax, [rdi+70h]
0x14004733c  mov     r9d, 3E8h; dwMilliseconds
0x140047342  mov     rcx, [rax+40h]
0x140047346  mov     [rbp+4Fh+var_38], rcx
0x14004734a  lea     ecx, [r8+2]; nCount
0x14004734e  call    cs:__imp_WaitForMultipleObjects
0x140047354  cmp     eax, 1
0x140047357  jz      loc_1400472C6
0x14004735d  inc     qword ptr [rdi+40h]
0x140047361  test    eax, eax
0x140047363  jnz     loc_14004740E
0x140047369  call    ?Provider@MidiXProcTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; MidiXProcTelemetryProvider::Provider(void)
0x14004736e  mov     r8, rax
0x140047371  mov     ecx, [rax]
0x140047373  cmp     ecx, 4
0x140047376  jbe     loc_1400474D2
0x14004737c  mov     rcx, [rdi+40h]
0x140047380  lea     rax, aMidixprocTermi; "MidiXProc terminated, buffer dropped."
0x140047387  mov     rdx, [rbp+4Fh+Src]
0x14004738b  mov     [rbp+4Fh+var_60], rax
0x14004738f  lea     rax, aCmidixprocSend; "CMidiXProc::SendMidiMessageInternal"
0x140047396  mov     [rbp+4Fh+var_50], rax
0x14004739a  lea     rax, [rbp+4Fh+var_78]
0x14004739e  mov     [rsp+60h], rax
0x1400473a3  lea     rax, [rbp+4Fh+var_70]
0x1400473a7  mov     [rsp+100h+var_A8], rax
0x1400473ac  lea     rax, [rbp+4Fh+var_90]
0x1400473b0  mov     [rsp+100h+var_B0], rax
0x1400473b5  lea     rax, [rbp+4Fh+PerformanceCount]
0x1400473b9  mov     [rsp+100h+var_B8], rax
0x1400473be  lea     rax, [rbp+4Fh+var_8C]
0x1400473c2  mov     [rsp+100h+var_C0], rax
0x1400473c7  lea     rax, [rbp+4Fh+var_68]
0x1400473cb  mov     [rsp+100h+var_C8], rax
0x1400473d0  lea     rax, [rbp+4Fh+var_60]
0x1400473d4  mov     [rsp+100h+var_D0], rax
0x1400473d9  lea     rax, [rbp+4Fh+var_58]
0x1400473dd  mov     qword ptr [rbp+4Fh+var_78], rcx
0x1400473e1  mov     rcx, [rdi+38h]
0x1400473e5  mov     [rsp+100h+var_D8], rax
0x1400473ea  lea     rax, [rbp+4Fh+var_50]
0x1400473ee  mov     [rbp+4Fh+var_68], rdx
0x1400473f2  lea     rdx, dword_14008CA74
0x1400473f9  mov     [rbp+4Fh+var_70], rcx
0x1400473fd  mov     dword ptr [rbp+4Fh+PerformanceCount], r12d
0x140047401  mov     [rbp+4Fh+var_8C], r15d
0x140047405  mov     [rbp+4Fh+var_58], rdi
0x140047409  jmp     loc_1400474C0
0x14004740e  cmp     eax, 102h
0x140047413  jnz     loc_1400474D2
0x140047419  mov     byte ptr [rsi], 1
0x14004741c  mov     [rdi+34h], r15d
0x140047420  call    ?Provider@MidiXProcTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; MidiXProcTelemetryProvider::Provider(void)
0x140047425  mov     r8, rax
0x140047428  mov     ecx, [rax]
0x14004742a  cmp     ecx, 4
0x14004742d  jbe     loc_1400474D2
0x140047433  mov     rdx, [rbp+4Fh+Src]
0x140047437  lea     rax, aMidixprocStall_0; "MidiXProc stall detected during send, b"...
0x14004743e  mov     [rbp+4Fh+var_60], rdx
0x140047442  lea     rdx, word_14008CB0A
0x140047449  mov     rcx, [rdi+40h]
0x14004744d  mov     [rbp+4Fh+var_68], rax
0x140047451  lea     rax, aCmidixprocSend; "CMidiXProc::SendMidiMessageInternal"
0x140047458  mov     qword ptr [rbp+4Fh+var_78], rax
0x14004745c  lea     rax, [rbp+4Fh+var_50]
0x140047460  mov     [rsp+60h], rax
0x140047465  lea     rax, [rbp+4Fh+var_58]
0x140047469  mov     [rsp+100h+var_A8], rax
0x14004746e  lea     rax, [rbp+4Fh+var_90]
0x140047472  mov     [rsp+100h+var_B0], rax
0x140047477  lea     rax, [rbp+4Fh+var_8C]
0x14004747b  mov     [rsp+100h+var_B8], rax
0x140047480  lea     rax, [rbp+4Fh+PerformanceCount]
0x140047484  mov     [rsp+100h+var_C0], rax
0x140047489  lea     rax, [rbp+4Fh+var_60]
0x14004748d  mov     [rsp+100h+var_C8], rax
0x140047492  lea     rax, [rbp+4Fh+var_68]
0x140047496  mov     [rsp+100h+var_D0], rax
0x14004749b  lea     rax, [rbp+4Fh+var_70]
0x14004749f  mov     [rbp+4Fh+var_50], rcx
0x1400474a3  mov     rcx, [rdi+38h]
0x1400474a7  mov     [rsp+100h+var_D8], rax
0x1400474ac  lea     rax, [rbp+4Fh+var_78]
0x1400474b0  mov     [rbp+4Fh+var_8C], r12d
0x1400474b4  mov     [rbp+4Fh+var_58], rcx
0x1400474b8  mov     [rbp+4Fh+var_70], rdi
0x1400474bc  mov     dword ptr [rbp+4Fh+PerformanceCount], r15d
0x1400474c0  mov     cl, [rsi]
0x1400474c2  mov     [rbp+4Fh+var_90], cl
0x1400474c5  mov     rcx, r8
0x1400474c8  mov     qword ptr [rsp+100h+var_E0], rax
0x1400474cd  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U2@U?$_tlgWrapperByVal@$03@@U4@U?$_tlgWrapperByVal@$00@@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@4AEBU?$_tlgWrapperByVal@$03@@6AEBU?$_tlgWrapperByVal@$00@@44@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &)
0x1400474d2  mov     r13b, [rbp+4Fh+var_80]
0x1400474d6  jmp     loc_1400476DB
0x1400474db  movdqu  xmm0, xmmword ptr [rdi+38h]
0x1400474e0  movdqa  xmm1, cs:__xmm@00000000000000010000000000000001
0x1400474e8  paddq   xmm1, xmm0
0x1400474ec  movdqu  xmmword ptr [rdi+38h], xmm1
0x1400474f1  call    ?Provider@MidiXProcTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; MidiXProcTelemetryProvider::Provider(void)
0x1400474f6  mov     r8, rax
0x1400474f9  mov     ecx, [rax]
0x1400474fb  cmp     ecx, 4
0x1400474fe  jbe     short loc_1400474D2
0x140047500  mov     rdx, [rbp+4Fh+Src]
0x140047504  lea     rax, aMidixprocStall; "MidiXProc stalled, buffer dropped."
0x14004750b  mov     [rbp+4Fh+var_60], rdx
0x14004750f  lea     rdx, unk_14008CBA0
0x140047516  jmp     loc_140047449
0x14004751b  mov     r14, [r13+18h]
0x14004751f  lea     eax, [r12+rcx]
0x140047523  div     dword ptr [r13+20h]
0x140047527  mov     r9d, dword ptr [rbp+4Fh+Size]
0x14004752b  lea     rcx, [r14+10h]
0x14004752f  mov     [rbp+4Fh+var_8C], edx
0x140047532  mov     r8d, r9d; Size
0x140047535  mov     rdx, [rbp+4Fh+Src]; Src
0x140047539  add     rcx, r12; void *
0x14004753c  mov     [r12+r14+8], r9d
0x140047541  call    memcpy_0
0x140047546  mov     rax, [rbp+4Fh+arg_20]
0x14004754a  xor     ecx, ecx
0x14004754c  test    rax, rax
0x14004754f  jnz     short loc_140047567
0x140047551  cmp     [rdi], ecx
0x140047553  jz      short loc_14004756D
0x140047555  mov     qword ptr [rbp+4Fh+PerformanceCount], rcx
0x140047559  lea     rcx, [rbp+4Fh+PerformanceCount]; lpPerformanceCount
0x14004755d  call    cs:__imp_QueryPerformanceCounter
0x140047563  mov     rax, qword ptr [rbp+4Fh+PerformanceCount]
0x140047567  mov     [r12+r14], rax
0x14004756b  jmp     short loc_140047571
0x14004756d  mov     [r12+r14], rcx
0x140047571  mov     rax, [r13+28h]
0x140047575  mov     ecx, [rbp+4Fh+var_8C]
0x140047578  xchg    ecx, [rax]
0x14004757a  mov     rcx, [rdi+70h]
0x14004757e  mov     rcx, [rcx+38h]; hEvent
0x140047582  call    cs:__imp_SetEvent
0x140047588  xor     r14d, r14d
0x14004758b  test    eax, eax
0x14004758d  jnz     short loc_1400475D1
0x14004758f  mov     edx, 2D4h; void *
0x140047594  mov     rcx, [rbp+57h]; this
0x140047598  lea     r8, aAvcoreMidi2Lib_0; "avcore\\midi2\\libs\\midixproc\\midixpr"...
0x14004759f  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1400475a4  mov     edi, eax
0x1400475a6  test    rbx, rbx
0x1400475a9  jz      short loc_1400475B4
0x1400475ab  mov     rcx, rbx; lpCriticalSection
0x1400475ae  call    cs:__imp_LeaveCriticalSection
0x1400475b4  mov     eax, edi
0x1400475b6  mov     rbx, [rsp+100h+arg_0]
0x1400475be  add     rsp, 0D0h
0x1400475c5  pop     r15
0x1400475c7  pop     r14
0x1400475c9  pop     r13
0x1400475cb  pop     r12
0x1400475cd  pop     rdi
0x1400475ce  pop     rsi
0x1400475cf  pop     rbp
0x1400475d0  retn
0x1400475d1  lea     rsi, [rdi+30h]
0x1400475d5  mov     [rbp+4Fh+var_7C], r12d
0x1400475d9  mov     r13b, 1
0x1400475dc  mov     [rbp+4Fh+var_48], r15d
0x1400475e0  cmp     [rsi], r14b
0x1400475e3  jz      loc_1400476D7
0x1400475e9  mov     [rdi+38h], r14
0x1400475ed  cmp     r15d, [rdi+34h]
0x1400475f1  jz      short loc_140047625
0x1400475f3  mov     [rsi], r14b
0x1400475f6  mov     [rdi+34h], r14d
0x1400475fa  call    ?Provider@MidiXProcTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; MidiXProcTelemetryProvider::Provider(void)
0x1400475ff  mov     r8, rax
0x140047602  mov     ecx, [rax]
0x140047604  cmp     ecx, 4
0x140047607  jbe     loc_1400476D7
0x14004760d  mov     rax, [rbp+4Fh+Src]
0x140047611  lea     rdx, unk_14008C948
0x140047618  mov     [rbp+4Fh+var_60], rax
0x14004761c  lea     rax, aMidixprocRecov; "MidiXProc recovered from stall."
0x140047623  jmp     short loc_14004764E
0x140047625  call    ?Provider@MidiXProcTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; MidiXProcTelemetryProvider::Provider(void)
0x14004762a  mov     r8, rax
0x14004762d  mov     ecx, [rax]
0x14004762f  cmp     ecx, 4
0x140047632  jbe     loc_1400476D7
0x140047638  mov     rax, [rbp+4Fh+Src]
0x14004763c  lea     rdx, word_14008C9DE
0x140047643  mov     [rbp+4Fh+var_60], rax
0x140047647  lea     rax, aMidixprocBuffe; "MidiXProc buffer added to queue will in"...
0x14004764e  mov     rcx, [rdi+40h]
0x140047652  mov     [rbp+4Fh+var_68], rax
0x140047656  lea     rax, aCmidixprocSend; "CMidiXProc::SendMidiMessageInternal"
0x14004765d  mov     qword ptr [rbp+4Fh+var_78], rax
0x140047661  lea     rax, [rbp+4Fh+var_50]
0x140047665  mov     [rsp+60h], rax
0x14004766a  lea     rax, [rbp+4Fh+var_58]
0x14004766e  mov     [rsp+100h+var_A8], rax
0x140047673  lea     rax, [rbp+4Fh+var_90]
0x140047677  mov     [rsp+100h+var_B0], rax
0x14004767c  lea     rax, [rbp+4Fh+var_8C]
0x140047680  mov     [rsp+100h+var_B8], rax
0x140047685  lea     rax, [rbp+4Fh+PerformanceCount]
0x140047689  mov     [rsp+100h+var_C0], rax
0x14004768e  lea     rax, [rbp+4Fh+var_60]
0x140047692  mov     [rsp+100h+var_C8], rax
0x140047697  lea     rax, [rbp+4Fh+var_68]
0x14004769b  mov     [rsp+100h+var_D0], rax
0x1400476a0  lea     rax, [rbp+4Fh+var_70]
0x1400476a4  mov     [rbp+4Fh+var_50], rcx
0x1400476a8  mov     rcx, [rdi+38h]
0x1400476ac  mov     [rbp+4Fh+var_58], rcx
0x1400476b0  mov     cl, [rsi]
0x1400476b2  mov     [rsp+100h+var_D8], rax
0x1400476b7  lea     rax, [rbp+4Fh+var_78]
0x1400476bb  mov     [rbp+4Fh+var_90], cl
0x1400476be  mov     rcx, r8
0x1400476c1  mov     qword ptr [rsp+100h+var_E0], rax; int
0x1400476c6  mov     [rbp+4Fh+var_8C], r12d
0x1400476ca  mov     dword ptr [rbp+4Fh+PerformanceCount], r15d
0x1400476ce  mov     [rbp+4Fh+var_70], rdi
0x1400476d2  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U2@U?$_tlgWrapperByVal@$03@@U4@U?$_tlgWrapperByVal@$00@@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@4AEBU?$_tlgWrapperByVal@$03@@6AEBU?$_tlgWrapperByVal@$00@@44@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &)
0x1400476d7  mov     r14d, [rbp+4Fh+arg_8]
0x1400476db  test    rbx, rbx
0x1400476de  jz      short loc_1400476E9
0x1400476e0  mov     rcx, rbx; lpCriticalSection
0x1400476e3  call    cs:__imp_LeaveCriticalSection
0x1400476e9  test    r13b, r13b
0x1400476ec  jz      short loc_140047734
0x1400476ee  test    r14b, 1
0x1400476f2  jz      loc_140047AD3
0x1400476f8  mov     r9d, [rbp+4Fh+var_44]; unsigned int
0x1400476fc  mov     rcx, rdi; this
0x1400476ff  mov     r8d, [rbp+4Fh+var_7C]; unsigned int
0x140047703  mov     edx, [rbp+4Fh+var_48]; unsigned int
  ... truncated ...
```
