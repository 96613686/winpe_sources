# CAudStreamSink::PlaceMarker(_MFSTREAMSINK_MARKER_TYPE,tagPROPVARIANT const *,tagPROPVARIANT const *)

- ea: `0x180084a10`
- end: `0x1800856a4`
- name: `?PlaceMarker@CAudStreamSink@@UEAAJW4_MFSTREAMSINK_MARKER_TYPE@@PEBUtagPROPVARIANT@@1@Z`
- size: `3220`
- prototype: `__int64 __fastcall(CAudStreamSink *__hidden this, enum _MFSTREAMSINK_MARKER_TYPE, const struct tagPROPVARIANT *, const struct tagPROPVARIANT *)`
- caller_count: `1`
- callee_count: `29`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1801fb65c`

## callees

- `0x18001616c`
- `0x18002fee0`
- `0x180035170`
- `0x18003ecb0`
- `0x1800402c0`
- `0x180045dbc`
- `0x18004d118`
- `0x180050d6c`
- `0x180063f00`
- `0x18006b388`
- `0x1800840e0`
- `0x1800845d0`
- `0x180084a10`
- `0x1800856ac`
- `0x1800856d0`
- `0x1800858b0`
- `0x1800859b0`
- `0x1800ec0e0`
- `0x180184530`
- `0x1801851b4`
- `0x180189368`
- `0x180204654`
- `0x1802583a8`
- `0x180258480`
- `0x180318e88`
- `0x18031d290`
- `0x18031d6f4`
- `0x18031edbc`
- `0x180344d40`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18008515f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180085675`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18008515f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180085675`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180084a6a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180084e21`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180084a6a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180084e21`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180084cca`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180084d23`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18008518b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800852b6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180085377`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180085465`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18008554e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180084cca`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180084d23`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18008518b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800852b6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180085377`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180085465`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18008554e`

## string_xrefs

- `0x180084a7c`: `CAudStreamSink::PlaceMarker`
- `0x180084b57`: `CAudStreamSink::PlaceMarker`
- `0x180084d80`: `CAudStreamSink::PlaceMarker`
- `0x180084dd3`: `CAudStreamSink::PlaceMarker`
- `0x1800851e9`: `CAudStreamSink::PlaceMarker`
- `0x180085314`: `CAudStreamSink::PlaceMarker`
- `0x1800853d5`: `CAudStreamSink::PlaceMarker`
- `0x1800854c3`: `CAudStreamSink::PlaceMarker`
- `0x1800855ac`: `CAudStreamSink::PlaceMarker`
- `0x180085606`: `CAudStreamSink::PlaceMarker`

## pseudocode

```c
__int64 __fastcall CAudStreamSink::PlaceMarker(
        CAudStreamSink *this,
        unsigned int a2,
        const struct tagPROPVARIANT *a3,
        struct tagPROPVARIANT *a4)
{
  struct tagPROPVARIANT *v4; // rbx
  struct _RTL_CRITICAL_SECTION *v8; // r15
  CallStackTracing *v9; // rcx
  struct CallStackContext *ThreadRelativeContext; // rdi
  int v11; // ebx
  __int128 *v12; // rax
  __int128 v13; // xmm0
  int v14; // edi
  struct CallStackContext *v15; // rax
  __int64 v16; // rdx
  __int64 v17; // r8
  unsigned __int8 v18; // al
  BOOL v19; // ebx
  int CanProcessEvent; // eax
  __int64 v21; // rdx
  __int64 v22; // r8
  __int64 *v23; // rcx
  CallStackTracing *v24; // rax
  __int64 *v25; // rcx
  CallStackTracing *v26; // rax
  struct CallStackContext *v27; // rax
  __int64 v28; // rdx
  struct CallStackContext *v29; // rax
  int v30; // edx
  __int64 v31; // rax
  LARGE_INTEGER hVal; // rbx
  LARGE_INTEGER v33; // rbx
  int v34; // ebx
  __int64 v35; // rax
  int v36; // eax
  CMarkerData *v37; // rax
  CMarkerData *v38; // rbx
  bool v39; // zf
  __int64 v40; // rcx
  unsigned int v41; // edx
  __int64 v42; // rdx
  __int64 v43; // r8
  __int64 *v44; // rcx
  CallStackTracing *v45; // rax
  struct CallStackContext *v46; // rax
  __int64 v47; // rcx
  __int64 v48; // rdx
  __int64 v49; // r8
  __int64 *v50; // rcx
  CallStackTracing *v51; // rax
  struct CallStackContext *v52; // rax
  __int64 v53; // rdx
  __int64 v54; // r8
  __int64 *v55; // rcx
  CallStackTracing *v56; // rax
  struct CallStackContext *v57; // rax
  CMarkerData *v58; // rax
  __int64 v59; // rdx
  __int64 v60; // r8
  CMarkerData *v61; // rax
  CMarkerData *v62; // rbx
  unsigned int v63; // edx
  int v64; // ecx
  __int64 v65; // rdx
  __int64 v66; // r8
  __int64 *v67; // rcx
  CallStackTracing *v68; // rax
  struct CallStackContext *v69; // rax
  __int64 v70; // rdx
  __int64 *v71; // rcx
  CallStackTracing *v72; // rax
  struct CallStackContext *v73; // rax
  CallStackTracing *v74; // rcx
  struct CallStackContext *v75; // rax
  BOOL v77; // [rsp+38h] [rbp-41h]
  _BYTE v78[4]; // [rsp+3Ch] [rbp-3Dh] BYREF
  int v79; // [rsp+40h] [rbp-39h] BYREF
  int v80; // [rsp+44h] [rbp-35h]
  struct tagPROPVARIANT *v81; // [rsp+48h] [rbp-31h]
  __int64 v82; // [rsp+50h] [rbp-29h] BYREF
  int v83; // [rsp+58h] [rbp-21h] BYREF
  BOOL v84; // [rsp+5Ch] [rbp-1Dh]
  int v85; // [rsp+60h] [rbp-19h]
  struct CRenderContainer *v86; // [rsp+68h] [rbp-11h] BYREF
  __int64 MarkerTimestamp; // [rsp+70h] [rbp-9h]
  _QWORD v88[2]; // [rsp+78h] [rbp-1h] BYREF

  v4 = a4;
  v81 = a4;
  v8 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 736);
  MarkerTimestamp = GetMarkerTimestamp(a3);
  v79 = 0;
  v86 = 0;
  EnterCriticalSection(v8);
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v78, "CAudStreamSink::PlaceMarker", 1743);
  v9 = CallStackTracing::s_wpInstance;
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) && *((_QWORD *)this + 823) )
  {
    ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
    v11 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 823) + 296LL))(*((_QWORD *)this + 823));
    v12 = (__int128 *)(*(__int64 (__fastcall **)(_QWORD, _QWORD *))(**((_QWORD **)this + 823) + 280LL))(
                        *((_QWORD *)this + 823),
                        v88);
    v9 = CallStackTracing::s_wpInstance;
    v13 = *v12;
    *((_DWORD *)ThreadRelativeContext + 504) = v11;
    v4 = v81;
    *((_OWORD *)ThreadRelativeContext + 125) = v13;
  }
  if ( (Microsoft_Windows_MediaFoundation_Performance_CoreEnableBits & 1) != 0 )
  {
    McTemplateU0pd_EventWriteTransfer(v9, &AudStreamSink_PlaceMarker_Enter, (char *)this - 16, a2);
    v9 = CallStackTracing::s_wpInstance;
  }
  if ( *((_DWORD *)this + 82) == 7 )
  {
    v14 = -1072870856;
    if ( !v9 )
    {
      CallStackTracing::InitInstance();
      v9 = CallStackTracing::s_wpInstance;
    }
    if ( *((_BYTE *)v9 + 8) )
    {
      v15 = CallStackTracing::GetThreadRelativeContext(v9);
      if ( *((_DWORD *)v15 + 499) != -1072870856 )
        CallStackContext::TraceFailure(v15, "CAudStreamSink::PlaceMarker", 1747, -1072870856);
    }
    if ( g_wppLevels )
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        138,
        &WPP_8e6dbb68bb473dec012b49037e0fe992_Traceguids,
        (char *)this - 16,
        -1072870856);
    goto LABEL_179;
  }
  v14 = CBaseStreamSink::PlaceMarker(this, (enum _MFSTREAMSINK_MARKER_TYPE)a2, a3, v4);
  v18 = (unsigned __int8)byte_1803CECE9;
  if ( (unsigned __int8)byte_1803CECE9 >= 0x10u )
  {
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 7),
      139,
      &WPP_8e6dbb68bb473dec012b49037e0fe992_Traceguids,
      (char *)this - 16,
      a2);
    v18 = (unsigned __int8)byte_1803CECE9;
  }
  v19 = 0;
  if ( a3 )
  {
    if ( v18 >= 0x10u )
    {
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 7),
        140,
        &WPP_8e6dbb68bb473dec012b49037e0fe992_Traceguids,
        (char *)this - 16,
        a3->vt);
      v18 = (unsigned __int8)byte_1803CECE9;
    }
    if ( a3->vt == 20 && v18 >= 0x10u )
      ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD))WPP_SF_qq)(
        *((_QWORD *)WPP_GLOBAL_Control + 7),
        141,
        &WPP_8e6dbb68bb473dec012b49037e0fe992_Traceguids,
        (char *)this - 16,
        (LARGE_INTEGER)a3->hVal.QuadPart);
  }
  if ( (*((_DWORD *)this + 60) || *((_DWORD *)this + 1350)) && v14 == -1072875850 )
  {
    v14 = 0;
LABEL_26:
    if ( a2 == 3 )
    {
      CanProcessEvent = CAudStreamSink::CanProcessEvent((CAudStreamSink *)((char *)this - 16), a3);
      v14 = CanProcessEvent;
      if ( (unsigned __int8)byte_1803CECE9 >= 0x10u )
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 7),
          143,
          &WPP_8e6dbb68bb473dec012b49037e0fe992_Traceguids,
          (char *)this - 16,
          CanProcessEvent);
      if ( v14 < 0 )
      {
        v23 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v24 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v21, v22);
          CallStackTracing::s_wpInstance = v24;
          if ( v24 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v24 + 8LL))(v24, 2032) )
          {
            v23 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v23 = &qword_1803CE250;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
          }
        }
        if ( *((_BYTE *)v23 + 8) )
        {
          v29 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v23);
          if ( *((_DWORD *)v29 + 499) != v14 )
            CallStackContext::TraceFailure(v29, "CAudStreamSink::PlaceMarker", 1779, v14);
        }
        if ( g_wppLevels )
        {
          v28 = 144;
          goto LABEL_45;
        }
        goto LABEL_179;
      }
    }
    v85 = *((_DWORD *)this + 83);
    v77 = 0;
    v84 = 0;
    v80 = 0;
    CAudStreamSink::LockAudioSamplePump((CAudStreamSink *)((char *)this + 640));
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 5176));
    if ( *((_DWORD *)this + 83) == 1 && a2 - 1 <= 1 )
    {
      if ( (unsigned __int8)byte_1803CECE9 >= 8u )
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 7),
          145,
          &WPP_8e6dbb68bb473dec012b49037e0fe992_Traceguids,
          (char *)this - 16,
          a2);
      if ( (Microsoft_Windows_MediaFoundation_Performance_CoreEnableBits & 1) != 0 )
        McTemplateU0pddi_EventWriteTransfer(1, v30, (_DWORD)this - 16, 1, a2, MarkerTimestamp);
      CAudStreamSink::SignalStreamPrerolled((CAudStreamSink *)((char *)this - 16));
      v31 = *((_QWORD *)this + 646);
      *((_DWORD *)this + 1280) = 0;
      *((_QWORD *)this + 641) = 0;
      *(_DWORD *)(v31 + 1612) = 1;
    }
    if ( a2 == 3 )
    {
      if ( a3->vt == 13 )
      {
        hVal = a3->hVal;
        v88[0] = hVal.QuadPart;
        if ( hVal.QuadPart )
          (*(void (__fastcall **)(LARGE_INTEGER))(*(_QWORD *)hVal.QuadPart + 8LL))(hVal);
        v82 = 0;
        v83 = 0;
        if ( (**(int (__fastcall ***)(LARGE_INTEGER, GUID *, __int64 *))hVal.QuadPart)(
               hVal,
               &GUID_df598932_f10c_4e39_bba2_c308f101daa3,
               &v82) < 0 )
        {
          v19 = 0;
        }
        else
        {
          v19 = 0;
          if ( (*(int (__fastcall **)(__int64, int *))(*(_QWORD *)v82 + 264LL))(v82, &v83) >= 0 )
          {
            v19 = v83 == 401;
            v77 = v19;
          }
        }
        ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&v82);
        ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(v88);
      }
    }
    else if ( !a2 && v81->vt == 13 )
    {
      v33 = v81->hVal;
      v88[0] = v33.QuadPart;
      if ( v33.QuadPart )
        (*(void (__fastcall **)(LARGE_INTEGER))(*(_QWORD *)v33.QuadPart + 8LL))(v33);
      v82 = 0;
      v34 = (**(__int64 (__fastcall ***)(LARGE_INTEGER, GUID *, __int64 *))v33.QuadPart)(
              v33,
              &GUID_a427b9fe_2ced_4b41_9529_5f53608bcbd2,
              &v82);
      ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&v82);
      ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(v88);
      v84 = v34 >= 0;
      v19 = 0;
    }
    if ( !*((_DWORD *)this + 1662) )
      goto LABEL_80;
    v35 = *((_QWORD *)this + 834);
    if ( *((_DWORD *)this + 1661) == 2 )
      v35 *= 2;
    if ( *(_QWORD *)(*((_QWORD *)this + 646) + 1496LL) < v35 )
    {
      if ( (unsigned __int8)byte_1803CECE9 >= 0x10u )
        WPP_SF_q(
          *((_QWORD *)WPP_GLOBAL_Control + 7),
          146,
          &WPP_8e6dbb68bb473dec012b49037e0fe992_Traceguids,
          (char *)this - 16);
      v36 = 1;
    }
    else
    {
LABEL_80:
      v36 = v80;
    }
    if ( v19 && (v36 || v85 == 1) )
    {
      if ( (unsigned __int8)byte_1803CECE9 >= 0x10u )
        WPP_SF_q(
          *((_QWORD *)WPP_GLOBAL_Control + 7),
          147,
          &WPP_8e6dbb68bb473dec012b49037e0fe992_Traceguids,
          (char *)this - 16);
      goto LABEL_102;
    }
    v37 = (CMarkerData *)operator new(0x28u);
    if ( !v37 || (v38 = CMarkerData::CMarkerData(v37, (enum _MFSTREAMSINK_MARKER_TYPE)a2, a3, v81)) == 0 )
    {
      v74 = CallStackTracing::s_wpInstance;
      v14 = -2147024882;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::InitInstance();
        v74 = CallStackTracing::s_wpInstance;
      }
      if ( *((_BYTE *)v74 + 8) )
      {
        v75 = CallStackTracing::GetThreadRelativeContext(v74);
        if ( *((_DWORD *)v75 + 499) != -2147024882 )
          CallStackContext::TraceFailure(v75, "CAudStreamSink::PlaceMarker", 1854, -2147024882);
      }
      if ( !g_wppLevels )
        goto LABEL_179;
      v70 = 148;
      goto LABEL_178;
    }
    v39 = !v84;
    *((_DWORD *)v38 + 8) = v77;
    if ( !v39 )
    {
      if ( (unsigned __int8)byte_1803CECE9 >= 0x10u )
        WPP_SF_q(
          *((_QWORD *)WPP_GLOBAL_Control + 7),
          149,
          &WPP_8e6dbb68bb473dec012b49037e0fe992_Traceguids,
          (char *)this - 16);
      CSampleQueue::AddDelayedMarker(*((CSampleQueue **)this + 646), v38);
      goto LABEL_92;
    }
    v40 = *(_QWORD *)((char *)this + *(int *)(*((_QWORD *)this + 45) + 4LL) + 368);
    if ( v40 )
    {
      v14 = (*(__int64 (__fastcall **)(__int64, CMarkerData *, int *))(*(_QWORD *)v40 + 72LL))(v40, v38, &v79);
    }
    else
    {
      if ( (unsigned int)CSampleQueue::GetLast(*((CSampleQueue **)this + 646), &v86) )
      {
        v14 = CRenderContainer::AddMarker(v86, v38);
LABEL_92:
        v79 = 1;
        goto LABEL_99;
      }
      CMarkerData::`scalar deleting destructor'(v38, v41);
    }
    if ( !v79 )
    {
      v19 = v77;
LABEL_102:
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 5176));
      CAudStreamSink::UnlockAudioSamplePump((CAudStreamSink *)((char *)this + 640));
      if ( v14 < 0 )
      {
        v44 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v45 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v42, v43);
          CallStackTracing::s_wpInstance = v45;
          if ( v45 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v45 + 8LL))(v45, 2032) )
          {
            v44 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v44 = &qword_1803CE250;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
          }
        }
        if ( *((_BYTE *)v44 + 8) )
        {
          v46 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v44);
          if ( *((_DWORD *)v46 + 499) != v14 )
            CallStackContext::TraceFailure(v46, "CAudStreamSink::PlaceMarker", 1890, v14);
        }
        if ( g_wppLevels )
        {
          v28 = 150;
          goto LABEL_45;
        }
        goto LABEL_179;
      }
      if ( v79 )
        goto LABEL_179;
      if ( (unsigned __int8)byte_1803CECE9 >= 0x10u )
        WPP_SF_q(
          *((_QWORD *)WPP_GLOBAL_Control + 7),
          151,
          &WPP_8e6dbb68bb473dec012b49037e0fe992_Traceguids,
          (char *)this - 16);
      if ( v85 != 1 && *((_DWORD *)this + 82) != 1 )
      {
        if ( a2 == 1 )
        {
          v47 = *(_QWORD *)((char *)this + *(int *)(*((_QWORD *)this + 45) + 4LL) + 368);
          if ( v47 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v47 + 64LL))(v47);
        }
        v14 = CAudStreamSink::DispatchMarker(
                (CAudStreamSink *)((char *)this - 16),
                0,
                (enum _MFSTREAMSINK_MARKER_TYPE)a2,
                a3,
                v81);
        if ( v14 < 0 )
        {
          v50 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v51 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v48, v49);
            CallStackTracing::s_wpInstance = v51;
            if ( v51 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v51 + 8LL))(v51, 2032) )
            {
              v50 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v50 = &qword_1803CE250;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
            }
          }
          if ( *((_BYTE *)v50 + 8) )
          {
            v52 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v50);
            if ( *((_DWORD *)v52 + 499) != v14 )
              CallStackContext::TraceFailure(v52, "CAudStreamSink::PlaceMarker", 1908, v14);
          }
          if ( g_wppLevels )
          {
            v28 = 152;
            goto LABEL_45;
          }
        }
        goto LABEL_179;
      }
      if ( v19 )
      {
        v14 = CAudStreamSink::DispatchMarker(
                (CAudStreamSink *)((char *)this - 16),
                0,
                (enum _MFSTREAMSINK_MARKER_TYPE)a2,
                a3,
                v81);
        if ( v14 < 0 )
        {
          v55 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v56 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v53, v54);
            CallStackTracing::s_wpInstance = v56;
            if ( v56 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v56 + 8LL))(v56, 2032) )
            {
              v55 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v55 = &qword_1803CE250;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
            }
          }
          if ( *((_BYTE *)v55 + 8) )
          {
            v57 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v55);
            if ( *((_DWORD *)v57 + 499) != v14 )
              CallStackContext::TraceFailure(v57, "CAudStreamSink::PlaceMarker", 1917, v14);
          }
          if ( g_wppLevels )
          {
            v28 = 153;
            goto LABEL_45;
          }
        }
        goto LABEL_179;
      }
      v58 = (CMarkerData *)operator new(0x28u);
      if ( v58 && (v61 = CMarkerData::CMarkerData(v58, (enum _MFSTREAMSINK_MARKER_TYPE)a2, a3, v81), (v62 = v61) != 0) )
      {
        if ( CVPtrList::AddTail((CAudStreamSink *)((char *)this + 5968), v61) )
        {
          if ( (Microsoft_Windows_MediaFoundation_Performance_CoreEnableBits & 1) != 0 )
            McTemplateU0pddi_EventWriteTransfer(v64, v63, (_DWORD)this - 16, 2, a2, MarkerTimestamp);
          if ( (unsigned __int8)byte_1803CECE9 >= 8u )
            WPP_SF_qD(
              *((_QWORD *)WPP_GLOBAL_Control + 7),
              156,
              &WPP_8e6dbb68bb473dec012b49037e0fe992_Traceguids,
              (char *)this - 16,
              a2);
          goto LABEL_179;
        }
        CMarkerData::`scalar deleting destructor'(v62, v63);
        v67 = (__int64 *)CallStackTracing::s_wpInstance;
        v14 = -2147024882;
        if ( !CallStackTracing::s_wpInstance )
        {
          v68 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v65, v66);
          CallStackTracing::s_wpInstance = v68;
          if ( v68 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v68 + 8LL))(v68, 2032) )
          {
            v67 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v67 = &qword_1803CE250;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
          }
        }
        if ( *((_BYTE *)v67 + 8) )
        {
          v69 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v67);
          if ( *((_DWORD *)v69 + 499) != -2147024882 )
            CallStackContext::TraceFailure(v69, "CAudStreamSink::PlaceMarker", 1927, -2147024882);
        }
        if ( !g_wppLevels )
          goto LABEL_179;
        v70 = 155;
      }
      else
      {
        v71 = (__int64 *)CallStackTracing::s_wpInstance;
        v14 = -2147024882;
        if ( !CallStackTracing::s_wpInstance )
        {
          v72 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v59, v60);
          CallStackTracing::s_wpInstance = v72;
          if ( v72 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v72 + 8LL))(v72, 2032) )
          {
            v71 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v71 = &qword_1803CE250;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
          }
        }
        if ( *((_BYTE *)v71 + 8) )
        {
          v73 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v71);
          if ( *((_DWORD *)v73 + 499) != -2147024882 )
            CallStackContext::TraceFailure(v73, "CAudStreamSink::PlaceMarker", 1922, -2147024882);
        }
        if ( !g_wppLevels )
          goto LABEL_179;
        v70 = 154;
      }
LABEL_178:
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v70,
        &WPP_8e6dbb68bb473dec012b49037e0fe992_Traceguids,
        (char *)this - 16,
        -2147024882);
      goto LABEL_179;
    }
LABEL_99:
    v19 = v77;
    if ( a2 == 1 )
      *((_DWORD *)this + 1330) = 1;
    goto LABEL_102;
  }
  if ( v14 >= 0 )
    goto LABEL_26;
  v25 = (__int64 *)CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    v26 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v16, v17);
    CallStackTracing::s_wpInstance = v26;
    if ( v26 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v26 + 8LL))(v26, 2032) )
    {
      v25 = (__int64 *)CallStackTracing::s_wpInstance;
    }
    else
    {
      v25 = &qword_1803CE250;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
    }
  }
  if ( *((_BYTE *)v25 + 8) )
  {
    v27 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v25);
    if ( *((_DWORD *)v27 + 499) != v14 )
      CallStackContext::TraceFailure(v27, "CAudStreamSink::PlaceMarker", 1769, v14);
  }
  if ( g_wppLevels )
  {
    v28 = 142;
LABEL_45:
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v28,
      &WPP_8e6dbb68bb473dec012b49037e0fe992_Traceguids,
      (char *)this - 16,
      v14);
  }
LABEL_179:
  if ( (Microsoft_Windows_MediaFoundation_Performance_CoreEnableBits & 1) != 0 )
    McTemplateU0pq_EventWriteTransfer(
      &Microsoft_Windows_MediaFoundation_Performance_Core_Context,
      &AudStreamSink_PlaceMarker_Exit,
      (char *)this - 16,
      (unsigned int)v14);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v78);
  LeaveCriticalSection(v8);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x180084a10  push    rbp
0x180084a12  push    rbx
0x180084a13  push    rsi
0x180084a14  push    rdi
0x180084a15  push    r12
0x180084a17  push    r13
0x180084a19  push    r14
0x180084a1b  push    r15
0x180084a1d  lea     rbp, [rsp-1Fh]
0x180084a22  sub     rsp, 98h
0x180084a29  mov     rax, cs:__security_cookie
0x180084a30  xor     rax, rsp
0x180084a33  mov     [rbp+57h+var_48], rax
0x180084a37  mov     rbx, r9
0x180084a3a  mov     rsi, rcx
0x180084a3d  mov     rcx, r8; struct tagPROPVARIANT *
0x180084a40  mov     [rbp+57h+var_88], rbx
0x180084a44  mov     r12, r8
0x180084a47  mov     r13d, edx
0x180084a4a  call    ?GetMarkerTimestamp@@YA_JPEBUtagPROPVARIANT@@@Z; GetMarkerTimestamp(tagPROPVARIANT const *)
0x180084a4f  lea     r15, [rsi+2E0h]
0x180084a56  mov     [rbp+57h+var_60], rax
0x180084a5a  xor     edi, edi
0x180084a5c  mov     [rbp+57h+var_A0], r15
0x180084a60  mov     rcx, r15; lpCriticalSection
0x180084a63  mov     [rbp+57h+var_90], edi
0x180084a66  mov     [rbp+57h+var_68], rdi
0x180084a6a  call    cs:__imp_EnterCriticalSection
0x180084a71  nop     dword ptr [rax+rax+00h]
0x180084a76  mov     r8d, 6CFh; int
0x180084a7c  lea     rdx, aCaudstreamsink_86; "CAudStreamSink::PlaceMarker"
0x180084a83  lea     rcx, [rbp+57h+var_94]; this
0x180084a87  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180084a8c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180084a93  cmp     [rcx+8], dil
0x180084a97  jz      short loc_180084AFA
0x180084a99  cmp     [rsi+19B8h], rdi
0x180084aa0  jz      short loc_180084AFA
0x180084aa2  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180084aa7  mov     rcx, [rsi+19B8h]
0x180084aae  mov     rdi, rax
0x180084ab1  mov     rdx, [rcx]
0x180084ab4  mov     rax, [rdx+128h]
0x180084abb  call    cs:__guard_dispatch_icall_fptr
0x180084ac1  mov     rcx, [rsi+19B8h]
0x180084ac8  mov     ebx, eax
0x180084aca  mov     rdx, [rcx]
0x180084acd  mov     rax, [rdx+118h]
0x180084ad4  lea     rdx, [rbp+57h+var_58]
0x180084ad8  call    cs:__guard_dispatch_icall_fptr
0x180084ade  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180084ae5  movups  xmm0, xmmword ptr [rax]
0x180084ae8  mov     [rdi+7E0h], ebx
0x180084aee  mov     rbx, [rbp+57h+var_88]
0x180084af2  movdqu  xmmword ptr [rdi+7D0h], xmm0
0x180084afa  test    cs:Microsoft_Windows_MediaFoundation_Performance_CoreEnableBits, 1
0x180084b01  jz      short loc_180084B1D
0x180084b03  lea     r8, [rsi-10h]
0x180084b07  mov     r9d, r13d
0x180084b0a  lea     rdx, AudStreamSink_PlaceMarker_Enter
0x180084b11  call    McTemplateU0pd_EventWriteTransfer
0x180084b16  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180084b1d  lea     r14, [rsi-10h]
0x180084b21  cmp     dword ptr [r14+158h], 7
0x180084b29  jnz     short loc_180084BA1
0x180084b2b  mov     edi, 0C00D4A38h
0x180084b30  test    rcx, rcx
0x180084b33  jnz     short loc_180084B41
0x180084b35  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x180084b3a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180084b41  cmp     byte ptr [rcx+8], 0
0x180084b45  jz      short loc_180084B6C
0x180084b47  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180084b4c  cmp     [rax+7CCh], edi
0x180084b52  jz      short loc_180084B6C
0x180084b54  mov     r9d, edi; int
0x180084b57  lea     rdx, aCaudstreamsink_86; "CAudStreamSink::PlaceMarker"
0x180084b5e  mov     r8d, 6D3h; int
0x180084b64  mov     rcx, rax; this
0x180084b67  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180084b6c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180084b73  jb      loc_180085647
0x180084b79  mov     rcx, cs:WPP_GLOBAL_Control
0x180084b80  lea     r8, WPP_8e6dbb68bb473dec012b49037e0fe992_Traceguids
0x180084b87  mov     edx, 8Ah
0x180084b8c  mov     dword ptr [rsp+0D0h+var_B0], edi
0x180084b90  mov     r9, r14
0x180084b93  mov     rcx, [rcx+10h]
0x180084b97  call    WPP_SF_qD
0x180084b9c  jmp     loc_180085647
0x180084ba1  mov     r9, rbx; struct tagPROPVARIANT *
0x180084ba4  mov     r8, r12; struct tagPROPVARIANT *
0x180084ba7  mov     edx, r13d; enum _MFSTREAMSINK_MARKER_TYPE
0x180084baa  mov     rcx, rsi; this
0x180084bad  call    ?PlaceMarker@CBaseStreamSink@@UEAAJW4_MFSTREAMSINK_MARKER_TYPE@@PEBUtagPROPVARIANT@@1@Z; CBaseStreamSink::PlaceMarker(_MFSTREAMSINK_MARKER_TYPE,tagPROPVARIANT const *,tagPROPVARIANT const *)
0x180084bb2  mov     edi, eax
0x180084bb4  mov     al, cs:byte_1803CECE9
0x180084bba  lea     r15, WPP_8e6dbb68bb473dec012b49037e0fe992_Traceguids
0x180084bc1  cmp     al, 10h
0x180084bc3  jb      short loc_180084BEB
0x180084bc5  mov     rcx, cs:WPP_GLOBAL_Control
0x180084bcc  mov     edx, 8Bh
0x180084bd1  mov     r9, r14
0x180084bd4  mov     dword ptr [rsp+0D0h+var_B0], r13d
0x180084bd9  mov     r8, r15
0x180084bdc  mov     rcx, [rcx+38h]
0x180084be0  call    WPP_SF_qD
0x180084be5  mov     al, cs:byte_1803CECE9
0x180084beb  xor     ebx, ebx
0x180084bed  test    r12, r12
0x180084bf0  jz      short loc_180084C51
0x180084bf2  cmp     al, 10h
0x180084bf4  jb      short loc_180084C20
0x180084bf6  mov     rcx, cs:WPP_GLOBAL_Control
0x180084bfd  mov     edx, 8Ch
0x180084c02  movzx   eax, word ptr [r12]
0x180084c07  mov     r9, r14
0x180084c0a  mov     r8, r15
0x180084c0d  mov     dword ptr [rsp+0D0h+var_B0], eax
0x180084c11  mov     rcx, [rcx+38h]
0x180084c15  call    WPP_SF_qD
0x180084c1a  mov     al, cs:byte_1803CECE9
0x180084c20  cmp     word ptr [r12], 14h
0x180084c26  jnz     short loc_180084C51
0x180084c28  cmp     al, 10h
0x180084c2a  jb      short loc_180084C51
0x180084c2c  mov     rcx, cs:WPP_GLOBAL_Control
0x180084c33  mov     edx, 8Dh
0x180084c38  mov     rax, [r12+8]
0x180084c3d  mov     r9, r14
0x180084c40  mov     r8, r15
0x180084c43  mov     [rsp+0D0h+var_B0], rax
0x180084c48  mov     rcx, [rcx+38h]
0x180084c4c  call    WPP_SF_qq
0x180084c51  cmp     [rsi+0F0h], ebx
0x180084c57  jnz     short loc_180084C65
0x180084c59  cmp     [rsi+1518h], ebx
0x180084c5f  jz      loc_180084D0F
0x180084c65  cmp     edi, 0C00D36B6h
0x180084c6b  jnz     loc_180084D0F
0x180084c71  mov     edi, ebx
0x180084c73  cmp     r13d, 3
0x180084c77  jnz     loc_180084DFC
0x180084c7d  mov     rdx, r12; struct tagPROPVARIANT *
0x180084c80  mov     rcx, r14; this
0x180084c83  call    ?CanProcessEvent@CAudStreamSink@@IEAAJPEBUtagPROPVARIANT@@@Z; CAudStreamSink::CanProcessEvent(tagPROPVARIANT const *)
0x180084c88  mov     edi, eax
0x180084c8a  cmp     cs:byte_1803CECE9, 10h
0x180084c91  jb      short loc_180084CB2
0x180084c93  mov     rcx, cs:WPP_GLOBAL_Control
0x180084c9a  mov     edx, 8Fh
0x180084c9f  mov     r9, r14
0x180084ca2  mov     dword ptr [rsp+0D0h+var_B0], eax
0x180084ca6  mov     r8, r15
0x180084ca9  mov     rcx, [rcx+38h]
0x180084cad  call    WPP_SF_qD
0x180084cb2  test    edi, edi
0x180084cb4  jns     loc_180084DFC
0x180084cba  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180084cc1  test    rcx, rcx
0x180084cc4  jnz     loc_180084DBE
0x180084cca  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180084cd1  nop     dword ptr [rax+rax+00h]
0x180084cd6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180084cdd  mov     rcx, rax
0x180084ce0  test    rax, rax
0x180084ce3  jz      loc_180084DB0
0x180084ce9  mov     rax, [rax]
0x180084cec  mov     edx, 7F0h
0x180084cf1  mov     rax, [rax+8]
0x180084cf5  call    cs:__guard_dispatch_icall_fptr
0x180084cfb  test    eax, eax
0x180084cfd  jz      loc_180084DB0
0x180084d03  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180084d0a  jmp     loc_180084DBE
0x180084d0f  test    edi, edi
0x180084d11  jns     loc_180084C73
0x180084d17  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180084d1e  test    rcx, rcx
0x180084d21  jnz     short loc_180084D6B
0x180084d23  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180084d2a  nop     dword ptr [rax+rax+00h]
0x180084d2f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180084d36  mov     rcx, rax
0x180084d39  test    rax, rax
0x180084d3c  jz      short loc_180084D5D
0x180084d3e  mov     rax, [rax]
0x180084d41  mov     edx, 7F0h
0x180084d46  mov     rax, [rax+8]
0x180084d4a  call    cs:__guard_dispatch_icall_fptr
0x180084d50  test    eax, eax
0x180084d52  jz      short loc_180084D5D
0x180084d54  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180084d5b  jmp     short loc_180084D6B
0x180084d5d  lea     rcx, qword_1803CE250; this
0x180084d64  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180084d6b  cmp     [rcx+8], bl
0x180084d6e  jz      short loc_180084D95
0x180084d70  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180084d75  cmp     [rax+7CCh], edi
0x180084d7b  jz      short loc_180084D95
0x180084d7d  mov     r9d, edi; int
0x180084d80  lea     rdx, aCaudstreamsink_86; "CAudStreamSink::PlaceMarker"
0x180084d87  mov     r8d, 6E9h; int
0x180084d8d  mov     rcx, rax; this
0x180084d90  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180084d95  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180084d9c  jb      loc_180085643
0x180084da2  mov     edx, 8Eh
0x180084da7  mov     dword ptr [rsp+0D0h+var_B0], edi
0x180084dab  jmp     loc_18008562D
0x180084db0  lea     rcx, qword_1803CE250; this
0x180084db7  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180084dbe  cmp     [rcx+8], bl
0x180084dc1  jz      short loc_180084DE8
0x180084dc3  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180084dc8  cmp     [rax+7CCh], edi
0x180084dce  jz      short loc_180084DE8
0x180084dd0  mov     r9d, edi; int
0x180084dd3  lea     rdx, aCaudstreamsink_86; "CAudStreamSink::PlaceMarker"
0x180084dda  mov     r8d, 6F3h; int
0x180084de0  mov     rcx, rax; this
0x180084de3  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180084de8  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180084def  jb      loc_180085643
0x180084df5  mov     edx, 90h
0x180084dfa  jmp     short loc_180084DA7
0x180084dfc  mov     eax, [rsi+14Ch]
0x180084e02  lea     rcx, [rsi+280h]; this
0x180084e09  mov     [rbp+57h+var_70], eax
0x180084e0c  mov     [rbp+57h+var_98], ebx
0x180084e0f  mov     [rbp+57h+var_74], ebx
0x180084e12  mov     [rbp+57h+var_8C], ebx
0x180084e15  call    ?LockAudioSamplePump@CAudStreamSink@@UEAAJXZ; CAudStreamSink::LockAudioSamplePump(void)
0x180084e1a  lea     rcx, [rsi+1438h]; lpCriticalSection
0x180084e21  call    cs:__imp_EnterCriticalSection
0x180084e28  nop     dword ptr [rax+rax+00h]
0x180084e2d  mov     ecx, 1
0x180084e32  cmp     [rsi+14Ch], ecx
0x180084e38  jnz     short loc_180084EB7
0x180084e3a  lea     eax, [r13-1]
0x180084e3e  cmp     eax, ecx
0x180084e40  ja      short loc_180084EB7
0x180084e42  cmp     cs:byte_1803CECE9, 8
0x180084e49  jb      short loc_180084E70
0x180084e4b  mov     rcx, cs:WPP_GLOBAL_Control
0x180084e52  mov     edx, 91h
0x180084e57  mov     r9, r14
0x180084e5a  mov     dword ptr [rsp+0D0h+var_B0], r13d
0x180084e5f  mov     r8, r15
0x180084e62  mov     rcx, [rcx+38h]
0x180084e66  call    WPP_SF_qD
0x180084e6b  mov     ecx, 1
0x180084e70  test    cs:Microsoft_Windows_MediaFoundation_Performance_CoreEnableBits, cl
0x180084e76  jz      short loc_180084E91
0x180084e78  mov     rax, [rbp+57h+var_60]
0x180084e7c  mov     r9d, ecx
0x180084e7f  mov     [rsp+0D0h+var_A8], rax
0x180084e84  mov     r8, r14
0x180084e87  mov     dword ptr [rsp+0D0h+var_B0], r13d
0x180084e8c  call    McTemplateU0pddi_EventWriteTransfer
0x180084e91  mov     rcx, r14; this
0x180084e94  call    ?SignalStreamPrerolled@CAudStreamSink@@UEAAJXZ; CAudStreamSink::SignalStreamPrerolled(void)
0x180084e99  mov     rax, [rsi+1430h]
0x180084ea0  mov     [rsi+1400h], ebx
0x180084ea6  mov     [rsi+1408h], rbx
0x180084ead  mov     dword ptr [rax+64Ch], 1
0x180084eb7  cmp     r13d, 3
0x180084ebb  jnz     loc_180084F62
0x180084ec1  cmp     word ptr [r12], 0Dh
0x180084ec7  jnz     loc_180084FCF
0x180084ecd  mov     rbx, [r12+8]
0x180084ed2  mov     [rbp+57h+var_58], rbx
0x180084ed6  test    rbx, rbx
0x180084ed9  jz      short loc_180084EEB
0x180084edb  mov     rax, [rbx]
0x180084ede  mov     rcx, rbx
0x180084ee1  mov     rax, [rax+8]
0x180084ee5  call    cs:__guard_dispatch_icall_fptr
0x180084eeb  mov     [rbp+57h+var_80], 0
0x180084ef3  lea     r8, [rbp+57h+var_80]
0x180084ef7  mov     [rbp+57h+var_78], 0
0x180084efe  lea     rdx, _GUID_df598932_f10c_4e39_bba2_c308f101daa3
0x180084f05  mov     rax, [rbx]
0x180084f08  mov     rcx, rbx
0x180084f0b  mov     rax, [rax]
0x180084f0e  call    cs:__guard_dispatch_icall_fptr
0x180084f14  test    eax, eax
0x180084f16  js      short loc_180084F4B
0x180084f18  mov     rcx, [rbp+57h+var_80]
0x180084f1c  lea     rdx, [rbp+57h+var_78]
0x180084f20  mov     rax, [rcx]
0x180084f23  mov     rax, [rax+108h]
0x180084f2a  call    cs:__guard_dispatch_icall_fptr
0x180084f30  mov     ebx, [rbp+57h+var_98]
0x180084f33  test    eax, eax
0x180084f35  js      short loc_180084F4E
0x180084f37  cmp     [rbp+57h+var_78], 191h
0x180084f3e  mov     eax, 1
0x180084f43  cmovz   ebx, eax
  ... truncated ...
```
