# CMFSampleGrabberStreamSink::ScheduleTimerForNextSample(void)

- ea: `0x18009f2f0`
- end: `0x18009fc65`
- name: `?ScheduleTimerForNextSample@CMFSampleGrabberStreamSink@@IEAAJXZ`
- size: `2421`
- prototype: `__int64 __fastcall(CMFSampleGrabberStreamSink *__hidden this)`
- caller_count: `2`
- callee_count: `14`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18009e0a0`
- `0x18009f020`

## callees

- `0x18001616c`
- `0x18002c9ac`
- `0x18002fee0`
- `0x18003ecb0`
- `0x1800402c0`
- `0x180050d6c`
- `0x180063f00`
- `0x18006b388`
- `0x180082b48`
- `0x18009b9e0`
- `0x18009d1e0`
- `0x18009f2f0`
- `0x1800ec0e0`
- `0x180344d40`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009f505`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009f5b7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009f64f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009f706`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009f7c2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009f8bf`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009f95e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009f9f6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009fa99`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009f505`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009f5b7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009f64f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009f706`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009f7c2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009f8bf`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009f95e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009f9f6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009fa99`

## string_xrefs

- `0x18009f305`: `CMFSampleGrabberStreamSink::ScheduleTimerForNextSample`
- `0x18009f594`: `CMFSampleGrabberStreamSink::ScheduleTimerForNextSample`
- `0x18009f62c`: `CMFSampleGrabberStreamSink::ScheduleTimerForNextSample`
- `0x18009f6e3`: `CMFSampleGrabberStreamSink::ScheduleTimerForNextSample`
- `0x18009f79a`: `CMFSampleGrabberStreamSink::ScheduleTimerForNextSample`
- `0x18009f869`: `CMFSampleGrabberStreamSink::ScheduleTimerForNextSample`
- `0x18009f894`: `CMFSampleGrabberStreamSink::ScheduleTimerForNextSample`
- `0x18009f934`: `CMFSampleGrabberStreamSink::ScheduleTimerForNextSample`
- `0x18009f9d3`: `CMFSampleGrabberStreamSink::ScheduleTimerForNextSample`
- `0x18009fa6f`: `CMFSampleGrabberStreamSink::ScheduleTimerForNextSample`
- `0x18009fb2d`: `CMFSampleGrabberStreamSink::ScheduleTimerForNextSample`

## pseudocode

```c
__int64 __fastcall CMFSampleGrabberStreamSink::ScheduleTimerForNextSample(CMFSampleGrabberStreamSink *this)
{
  int v2; // edi
  void (__fastcall ****v3)(_QWORD, GUID *, __int64 *); // rbx
  void (__fastcall ***v4)(_QWORD, GUID *, __int64 *); // rbx
  __int64 v5; // rdx
  __int64 v6; // r8
  signed __int64 v7; // rax
  unsigned __int64 v8; // r8
  __int64 v9; // rdx
  __int64 v10; // r8
  CallStackTracing *v12; // rcx
  __int64 v13; // rdx
  __int64 v14; // r8
  __int64 *v15; // rcx
  CallStackTracing *v16; // rax
  struct CallStackContext *v17; // rax
  __int64 *v18; // rcx
  CallStackTracing *v19; // rax
  __int64 v20; // rdx
  struct CallStackContext *v21; // rax
  __int64 *v22; // rcx
  CallStackTracing *v23; // rax
  struct CallStackContext *v24; // rax
  __int64 *v25; // rcx
  CallStackTracing *v26; // rax
  struct CallStackContext *v27; // rax
  __int64 *v28; // rcx
  CallStackTracing *v29; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  struct CallStackContext *v31; // rax
  __int64 *v32; // rcx
  CallStackTracing *v33; // rax
  __int64 v34; // rdx
  struct CallStackContext *v35; // rax
  __int64 *v36; // rcx
  CallStackTracing *v37; // rax
  __int64 v38; // rdx
  struct CallStackContext *v39; // rax
  __int64 *v40; // rcx
  CallStackTracing *v41; // rax
  struct CallStackContext *v42; // rax
  __int64 *v43; // rcx
  CallStackTracing *v44; // rax
  struct CallStackContext *v45; // rax
  __int64 v46; // rdx
  __int64 v47; // r8
  __int64 v48; // rdx
  __int64 v49; // r8
  __int64 v50; // rdx
  __int64 v51; // r8
  __int64 v52; // rdx
  __int64 v53; // r8
  __int64 v54; // [rsp+40h] [rbp-30h] BYREF
  unsigned __int64 v55; // [rsp+48h] [rbp-28h] BYREF
  PROPVARIANT pvar[2]; // [rsp+50h] [rbp-20h] BYREF
  __int64 v57; // [rsp+60h] [rbp-10h]
  int v58; // [rsp+B0h] [rbp+40h] BYREF
  __int64 v59; // [rsp+B8h] [rbp+48h] BYREF
  __int64 v60; // [rsp+C0h] [rbp+50h] BYREF
  void *v61; // [rsp+C8h] [rbp+58h] BYREF

  v2 = 0;
  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)&v58,
    "CMFSampleGrabberStreamSink::ScheduleTimerForNextSample",
    801);
  if ( *((_QWORD *)this + 63) || !*((_DWORD *)this + 262) )
    goto LABEL_15;
  if ( *((_QWORD *)this + 62) )
  {
    v59 = 0;
    while ( 1 )
    {
      while ( 1 )
      {
        v3 = (void (__fastcall ****)(_QWORD, GUID *, __int64 *))*((_QWORD *)this + 129);
        v60 = 0;
        if ( !v3 )
          goto LABEL_77;
        v4 = *v3;
        (**v4)(v4, &GUID_c40a00f2_b93a_4d80_ae8c_5a1c634f58e4, &v59);
        (**v4)(v4, &GUID_df598932_f10c_4e39_bba2_c308f101daa3, &v60);
        if ( v60 )
          break;
        if ( v59 )
          goto LABEL_8;
        v61 = 0;
        if ( !(unsigned int)CVPtrList::RemoveHead((CMFSampleGrabberStreamSink *)((char *)this + 608), &v61) )
        {
          v28 = (__int64 *)CallStackTracing::s_wpInstance;
          v2 = -2147418113;
          if ( !CallStackTracing::s_wpInstance )
          {
            v29 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v46, v47);
            CallStackTracing::s_wpInstance = v29;
            if ( v29 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v29 + 8LL))(v29, 2032) )
            {
              v28 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v28 = &qword_1803CE250;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
            }
          }
          if ( *((_BYTE *)v28 + 8) )
          {
            ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v28);
            if ( *((_DWORD *)ThreadRelativeContext + 499) != -2147418113 )
              CallStackContext::TraceFailure(
                ThreadRelativeContext,
                "CMFSampleGrabberStreamSink::ScheduleTimerForNextSample",
                860,
                -2147418113);
          }
          if ( g_wppLevels )
            WPP_SF_qD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              76,
              &WPP_9e0691ee672e3c34414a5076d2e5426e_Traceguids,
              this,
              -2147418113);
          goto LABEL_76;
        }
        v54 = 0;
        v2 = (**(__int64 (__fastcall ***)(void *, GUID *, __int64 *))v61)(
               v61,
               &GUID_a6fdf644_50ab_4cb8_b4d8_656cb597b6ca,
               &v54);
        if ( v2 < 0 )
        {
          v25 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v26 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v48, v49);
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
            if ( *((_DWORD *)v27 + 499) != v2 )
              CallStackContext::TraceFailure(v27, "CMFSampleGrabberStreamSink::ScheduleTimerForNextSample", 864, v2);
          }
          if ( g_wppLevels )
            WPP_SF_qD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              77,
              &WPP_9e0691ee672e3c34414a5076d2e5426e_Traceguids,
              this,
              v2);
          goto LABEL_65;
        }
        v58 = 0;
        v57 = 0;
        *(_OWORD *)pvar = 0;
        v2 = (*(__int64 (__fastcall **)(__int64, int *, PROPVARIANT *))(*(_QWORD *)v54 + 24LL))(v54, &v58, pvar);
        if ( v2 < 0 )
        {
          v22 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v23 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v50, v51);
            CallStackTracing::s_wpInstance = v23;
            if ( v23 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v23 + 8LL))(v23, 2032) )
            {
              v22 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v22 = &qword_1803CE250;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
            }
          }
          if ( *((_BYTE *)v22 + 8) )
          {
            v24 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v22);
            if ( *((_DWORD *)v24 + 499) != v2 )
              CallStackContext::TraceFailure(v24, "CMFSampleGrabberStreamSink::ScheduleTimerForNextSample", 872, v2);
          }
          if ( g_wppLevels )
          {
            v20 = 78;
LABEL_53:
            WPP_SF_qD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              v20,
              &WPP_9e0691ee672e3c34414a5076d2e5426e_Traceguids,
              this,
              v2);
          }
LABEL_54:
          CMFPropVariant::Clear(pvar);
LABEL_65:
          ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&v54);
LABEL_76:
          ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&v61);
          goto LABEL_77;
        }
        v2 = CMFMediaEventGenerator::QueueEvent(
               (CMFSampleGrabberStreamSink *)((char *)this + 104),
               0x132u,
               &GUID_00000000_0000_0000_0000_000000000000,
               0,
               (PROPVARIANT *)((unsigned __int64)pvar & -(__int64)(v58 != 0)));
        if ( v2 < 0 )
        {
          v18 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v19 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v52, v53);
            CallStackTracing::s_wpInstance = v19;
            if ( v19 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v19 + 8LL))(v19, 2032) )
            {
              v18 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v18 = &qword_1803CE250;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
            }
          }
          if ( *((_BYTE *)v18 + 8) )
          {
            v21 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v18);
            if ( *((_DWORD *)v21 + 499) != v2 )
              CallStackContext::TraceFailure(v21, "CMFSampleGrabberStreamSink::ScheduleTimerForNextSample", 875, v2);
          }
          if ( g_wppLevels )
          {
            v20 = 79;
            goto LABEL_53;
          }
          goto LABEL_54;
        }
        CMFPropVariant::Clear(pvar);
        ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&v54);
        ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&v61);
        ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&v60);
      }
      v2 = CMFSampleGrabberStreamSink::FinishProcessSample(this);
      if ( v2 < 0 )
        break;
      if ( v60 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v60 + 16LL))(v60);
    }
    v15 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v16 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v13, v14);
      CallStackTracing::s_wpInstance = v16;
      if ( v16 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v16 + 8LL))(v16, 2032) )
      {
        v15 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v15 = &qword_1803CE250;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
      }
    }
    if ( *((_BYTE *)v15 + 8) )
    {
      v17 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v15);
      if ( *((_DWORD *)v17 + 499) != v2 )
        CallStackContext::TraceFailure(v17, "CMFSampleGrabberStreamSink::ScheduleTimerForNextSample", 849, v2);
    }
    if ( g_wppLevels )
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 75, &WPP_9e0691ee672e3c34414a5076d2e5426e_Traceguids, this, v2);
LABEL_77:
    ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&v60);
    if ( !v59 )
      goto LABEL_123;
LABEL_8:
    v55 = 0x7FFFFFFFFFFFFFFFLL;
    v2 = (*(__int64 (__fastcall **)(__int64, unsigned __int64 *))(*(_QWORD *)v59 + 280LL))(v59, &v55);
    if ( v2 < 0 )
    {
      v12 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::InitInstance();
        v12 = CallStackTracing::s_wpInstance;
      }
      if ( *((_BYTE *)v12 + 8) )
      {
        v31 = CallStackTracing::GetThreadRelativeContext(v12);
        if ( *((_DWORD *)v31 + 499) != v2 )
          CallStackContext::TraceFailure(v31, "CMFSampleGrabberStreamSink::ScheduleTimerForNextSample", 901, v2);
      }
      if ( g_wppLevels )
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 80, &WPP_9e0691ee672e3c34414a5076d2e5426e_Traceguids, this, v2);
      goto LABEL_13;
    }
    if ( v55 == 0x7FFFFFFFFFFFFFFFLL )
    {
      v32 = (__int64 *)CallStackTracing::s_wpInstance;
      v2 = -2147418113;
      if ( !CallStackTracing::s_wpInstance )
      {
        v33 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v5, v6);
        CallStackTracing::s_wpInstance = v33;
        if ( v33 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v33 + 8LL))(v33, 2032) )
        {
          v32 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v32 = &qword_1803CE250;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
        }
      }
      if ( *((_BYTE *)v32 + 8) )
      {
        v35 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v32);
        if ( *((_DWORD *)v35 + 499) != -2147418113 )
          CallStackContext::TraceFailure(
            v35,
            "CMFSampleGrabberStreamSink::ScheduleTimerForNextSample",
            905,
            -2147418113);
      }
      if ( !g_wppLevels )
        goto LABEL_123;
      v34 = 81;
      goto LABEL_111;
    }
    if ( *((_DWORD *)this + 267) )
    {
      v7 = *((_QWORD *)this + 60);
      v8 = 0;
      if ( (__int64)v55 <= v7 )
        goto LABEL_12;
      if ( v55 >= v7 )
      {
        v8 = v55 - v7;
        goto LABEL_12;
      }
      v36 = (__int64 *)CallStackTracing::s_wpInstance;
      v2 = -2147024362;
      if ( !CallStackTracing::s_wpInstance )
      {
        v37 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v5, 0);
        CallStackTracing::s_wpInstance = v37;
        if ( v37 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v37 + 8LL))(v37, 2032) )
        {
          v36 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v36 = &qword_1803CE250;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
        }
      }
      if ( *((_BYTE *)v36 + 8) )
      {
        v39 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v36);
        if ( *((_DWORD *)v39 + 499) != -2147024362 )
          CallStackContext::TraceFailure(
            v39,
            "CMFSampleGrabberStreamSink::ScheduleTimerForNextSample",
            920,
            -2147024362);
      }
      if ( !g_wppLevels )
        goto LABEL_123;
      v38 = 82;
    }
    else
    {
      v8 = v55 + *((_QWORD *)this + 60);
      if ( v8 >= v55 )
      {
LABEL_12:
        v2 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, unsigned __int64, char *, _QWORD, char *))(**((_QWORD **)this + 62)
                                                                                                 + 24LL))(
               *((_QWORD *)this + 62),
               0,
               v8,
               (char *)this + 600,
               0,
               (char *)this + 504);
        if ( v2 >= 0 )
        {
LABEL_13:
          if ( v59 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v59 + 16LL))(v59);
          goto LABEL_15;
        }
        v40 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v41 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v9, v10);
          CallStackTracing::s_wpInstance = v41;
          if ( v41 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v41 + 8LL))(v41, 2032) )
          {
            v40 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v40 = &qword_1803CE250;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
          }
        }
        if ( *((_BYTE *)v40 + 8) )
        {
          v42 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v40);
          if ( *((_DWORD *)v42 + 499) != v2 )
            CallStackContext::TraceFailure(v42, "CMFSampleGrabberStreamSink::ScheduleTimerForNextSample", 929, v2);
        }
        if ( g_wppLevels )
        {
          v34 = 84;
LABEL_111:
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v34,
            &WPP_9e0691ee672e3c34414a5076d2e5426e_Traceguids,
            this,
            v2);
        }
LABEL_123:
        ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&v59);
        goto LABEL_15;
      }
      v43 = (__int64 *)CallStackTracing::s_wpInstance;
      v2 = -2147024362;
      if ( !CallStackTracing::s_wpInstance )
      {
        v44 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v5, v8);
        CallStackTracing::s_wpInstance = v44;
        if ( v44 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v44 + 8LL))(v44, 2032) )
        {
          v43 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v43 = &qword_1803CE250;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
        }
      }
      if ( *((_BYTE *)v43 + 8) )
      {
        v45 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v43);
        if ( *((_DWORD *)v45 + 499) != -2147024362 )
          CallStackContext::TraceFailure(
            v45,
            "CMFSampleGrabberStreamSink::ScheduleTimerForNextSample",
            926,
            -2147024362);
      }
      if ( !g_wppLevels )
        goto LABEL_123;
      v38 = 83;
    }
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v38,
      &WPP_9e0691ee672e3c34414a5076d2e5426e_Traceguids,
      this,
      -2147024362);
    goto LABEL_123;
  }
  if ( (unsigned __int8)byte_1803CECEA >= 8u )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 12), 74, &WPP_9e0691ee672e3c34414a5076d2e5426e_Traceguids, this);
LABEL_15:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v58);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18009f2f0  push    rbp
0x18009f2f2  push    rbx
0x18009f2f3  push    rsi
0x18009f2f4  push    rdi
0x18009f2f5  push    r12
0x18009f2f7  push    r14
0x18009f2f9  push    r15
0x18009f2fb  mov     rbp, rsp
0x18009f2fe  sub     rsp, 70h
0x18009f302  mov     rsi, rcx
0x18009f305  lea     rdx, aCmfsamplegrabb_28; "CMFSampleGrabberStreamSink::ScheduleTim"...
0x18009f30c  xor     r12d, r12d
0x18009f30f  lea     rcx, [rbp+arg_0]; this
0x18009f313  mov     r8d, 321h; int
0x18009f319  mov     edi, r12d
0x18009f31c  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18009f321  lea     r15, [rsi+1F8h]
0x18009f328  cmp     [r15], r12
0x18009f32b  jnz     loc_18009F455
0x18009f331  cmp     [rsi+418h], r12d
0x18009f338  jz      loc_18009F455
0x18009f33e  cmp     [rsi+1F0h], r12
0x18009f345  jz      loc_18009FB44
0x18009f34b  mov     [rbp+arg_8], r12
0x18009f34f  mov     rbx, [rsi+408h]
0x18009f356  lea     r14, WPP_9e0691ee672e3c34414a5076d2e5426e_Traceguids
0x18009f35d  mov     [rbp+arg_10], r12
0x18009f361  test    rbx, rbx
0x18009f364  jz      loc_18009F831
0x18009f36a  mov     rbx, [rbx]
0x18009f36d  lea     r8, [rbp+arg_8]
0x18009f371  lea     rdx, _GUID_c40a00f2_b93a_4d80_ae8c_5a1c634f58e4
0x18009f378  mov     rcx, rbx
0x18009f37b  mov     rax, [rbx]
0x18009f37e  mov     rax, [rax]
0x18009f381  call    cs:__guard_dispatch_icall_fptr
0x18009f387  mov     rax, [rbx]
0x18009f38a  lea     r8, [rbp+arg_10]
0x18009f38e  lea     rdx, _GUID_df598932_f10c_4e39_bba2_c308f101daa3
0x18009f395  mov     rcx, rbx
0x18009f398  mov     rax, [rax]
0x18009f39b  call    cs:__guard_dispatch_icall_fptr
0x18009f3a1  cmp     [rbp+arg_10], r12
0x18009f3a5  jnz     loc_18009F4BE
0x18009f3ab  cmp     [rbp+arg_8], r12
0x18009f3af  jz      loc_18009FB75
0x18009f3b5  mov     rcx, [rbp+arg_8]
0x18009f3b9  lea     rdx, [rbp+var_28]
0x18009f3bd  mov     rbx, 7FFFFFFFFFFFFFFFh
0x18009f3c7  mov     [rbp+var_28], rbx
0x18009f3cb  mov     rax, [rcx]
0x18009f3ce  mov     rax, [rax+118h]
0x18009f3d5  call    cs:__guard_dispatch_icall_fptr
0x18009f3db  mov     edi, eax
0x18009f3dd  test    eax, eax
0x18009f3df  js      loc_18009F47E
0x18009f3e5  mov     rcx, [rbp+var_28]
0x18009f3e9  cmp     rcx, rbx
0x18009f3ec  jz      loc_18009F8AE
0x18009f3f2  cmp     [rsi+42Ch], r12d
0x18009f3f9  jz      loc_18009FC4D
0x18009f3ff  mov     rax, [rsi+1E0h]
0x18009f406  mov     r8, r12
0x18009f409  cmp     rcx, rax
0x18009f40c  jg      short loc_18009F470
0x18009f40e  mov     rcx, [rsi+1F0h]
0x18009f415  lea     r9, [rsi+258h]
0x18009f41c  mov     [rsp+70h+var_48], r15
0x18009f421  xor     edx, edx
0x18009f423  mov     [rsp+70h+pvValue], r12
0x18009f428  mov     rax, [rcx]
0x18009f42b  mov     rax, [rax+18h]
0x18009f42f  call    cs:__guard_dispatch_icall_fptr
0x18009f435  mov     edi, eax
0x18009f437  test    eax, eax
0x18009f439  js      loc_18009F9EA
0x18009f43f  mov     rcx, [rbp+arg_8]
0x18009f443  test    rcx, rcx
0x18009f446  jz      short loc_18009F455
0x18009f448  mov     rax, [rcx]
0x18009f44b  mov     rax, [rax+10h]
0x18009f44f  call    cs:__guard_dispatch_icall_fptr
0x18009f455  lea     rcx, [rbp+arg_0]; this
0x18009f459  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18009f45e  mov     eax, edi
0x18009f460  add     rsp, 70h
0x18009f464  pop     r15
0x18009f466  pop     r14
0x18009f468  pop     r12
0x18009f46a  pop     rdi
0x18009f46b  pop     rsi
0x18009f46c  pop     rbx
0x18009f46d  pop     rbp
0x18009f46e  retn
0x18009f470  jb      loc_18009F94B
0x18009f476  mov     r8, rcx
0x18009f479  sub     r8, rax
0x18009f47c  jmp     short loc_18009F40E
0x18009f47e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18009f485  test    rcx, rcx
0x18009f488  jz      short loc_18009F4EB
0x18009f48a  cmp     [rcx+8], r12b
0x18009f48e  jnz     loc_18009F880
0x18009f494  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18009f49b  jb      short loc_18009F43F
0x18009f49d  mov     rcx, cs:WPP_GLOBAL_Control
0x18009f4a4  mov     edx, 50h ; 'P'
0x18009f4a9  mov     r9, rsi
0x18009f4ac  mov     dword ptr [rsp+70h+pvValue], edi
0x18009f4b0  mov     r8, r14
0x18009f4b3  mov     rcx, [rcx+10h]
0x18009f4b7  call    WPP_SF_qD
0x18009f4bc  jmp     short loc_18009F43F
0x18009f4be  mov     rcx, rsi; this
0x18009f4c1  call    ?FinishProcessSample@CMFSampleGrabberStreamSink@@IEAAJXZ; CMFSampleGrabberStreamSink::FinishProcessSample(void)
0x18009f4c6  mov     edi, eax
0x18009f4c8  test    eax, eax
0x18009f4ca  js      short loc_18009F4F9
0x18009f4cc  mov     rcx, [rbp+arg_10]
0x18009f4d0  test    rcx, rcx
0x18009f4d3  jz      loc_18009F34F
0x18009f4d9  mov     rax, [rcx]
0x18009f4dc  mov     rax, [rax+10h]
0x18009f4e0  call    cs:__guard_dispatch_icall_fptr
0x18009f4e6  jmp     loc_18009F34F
0x18009f4eb  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x18009f4f0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18009f4f7  jmp     short loc_18009F48A
0x18009f4f9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18009f500  test    rcx, rcx
0x18009f503  jnz     short loc_18009F53D
0x18009f505  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18009f50c  nop     dword ptr [rax+rax+00h]
0x18009f511  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18009f518  mov     rcx, rax
0x18009f51b  test    rax, rax
0x18009f51e  jz      short loc_18009F574
0x18009f520  mov     rax, [rax]
0x18009f523  mov     edx, 7F0h
0x18009f528  mov     rax, [rax+8]
0x18009f52c  call    cs:__guard_dispatch_icall_fptr
0x18009f532  test    eax, eax
0x18009f534  jz      short loc_18009F574
0x18009f536  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18009f53d  cmp     [rcx+8], r12b
0x18009f541  jnz     short loc_18009F584
0x18009f543  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18009f54a  jb      loc_18009F831
0x18009f550  mov     rcx, cs:WPP_GLOBAL_Control
0x18009f557  mov     edx, 4Bh ; 'K'
0x18009f55c  mov     r9, rsi
0x18009f55f  mov     dword ptr [rsp+70h+pvValue], edi
0x18009f563  mov     r8, r14
0x18009f566  mov     rcx, [rcx+10h]
0x18009f56a  call    WPP_SF_qD
0x18009f56f  jmp     loc_18009F831
0x18009f574  lea     rcx, qword_1803CE250
0x18009f57b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18009f582  jmp     short loc_18009F53D
0x18009f584  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18009f589  cmp     [rax+7CCh], edi
0x18009f58f  jz      short loc_18009F543
0x18009f591  mov     r9d, edi; int
0x18009f594  lea     rdx, aCmfsamplegrabb_28; "CMFSampleGrabberStreamSink::ScheduleTim"...
0x18009f59b  mov     r8d, 351h; int
0x18009f5a1  mov     rcx, rax; this
0x18009f5a4  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18009f5a9  jmp     short loc_18009F543
0x18009f5ab  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18009f5b2  test    rcx, rcx
0x18009f5b5  jnz     short loc_18009F5EF
0x18009f5b7  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18009f5be  nop     dword ptr [rax+rax+00h]
0x18009f5c3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18009f5ca  mov     rcx, rax
0x18009f5cd  test    rax, rax
0x18009f5d0  jz      short loc_18009F60C
0x18009f5d2  mov     rax, [rax]
0x18009f5d5  mov     edx, 7F0h
0x18009f5da  mov     rax, [rax+8]
0x18009f5de  call    cs:__guard_dispatch_icall_fptr
0x18009f5e4  test    eax, eax
0x18009f5e6  jz      short loc_18009F60C
0x18009f5e8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18009f5ef  cmp     [rcx+8], r12b
0x18009f5f3  jnz     short loc_18009F61C
0x18009f5f5  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18009f5fc  jb      loc_18009F6B5
0x18009f602  mov     edx, 4Fh ; 'O'
0x18009f607  jmp     loc_18009F69B
0x18009f60c  lea     rcx, qword_1803CE250
0x18009f613  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18009f61a  jmp     short loc_18009F5EF
0x18009f61c  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18009f621  cmp     [rax+7CCh], edi
0x18009f627  jz      short loc_18009F5F5
0x18009f629  mov     r9d, edi; int
0x18009f62c  lea     rdx, aCmfsamplegrabb_28; "CMFSampleGrabberStreamSink::ScheduleTim"...
0x18009f633  mov     r8d, 36Bh; int
0x18009f639  mov     rcx, rax; this
0x18009f63c  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18009f641  jmp     short loc_18009F5F5
0x18009f643  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18009f64a  test    rcx, rcx
0x18009f64d  jnz     short loc_18009F687
0x18009f64f  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18009f656  nop     dword ptr [rax+rax+00h]
0x18009f65b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18009f662  mov     rcx, rax
0x18009f665  test    rax, rax
0x18009f668  jz      short loc_18009F6C3
0x18009f66a  mov     rax, [rax]
0x18009f66d  mov     edx, 7F0h
0x18009f672  mov     rax, [rax+8]
0x18009f676  call    cs:__guard_dispatch_icall_fptr
0x18009f67c  test    eax, eax
0x18009f67e  jz      short loc_18009F6C3
0x18009f680  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18009f687  cmp     [rcx+8], r12b
0x18009f68b  jnz     short loc_18009F6D3
0x18009f68d  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18009f694  jb      short loc_18009F6B5
0x18009f696  mov     edx, 4Eh ; 'N'
0x18009f69b  mov     rcx, cs:WPP_GLOBAL_Control
0x18009f6a2  mov     r9, rsi
0x18009f6a5  mov     r8, r14
0x18009f6a8  mov     dword ptr [rsp+70h+pvValue], edi
0x18009f6ac  mov     rcx, [rcx+10h]
0x18009f6b0  call    WPP_SF_qD
0x18009f6b5  lea     rcx, [rbp+pvar]; pvar
0x18009f6b9  call    ?Clear@CMFPropVariant@@QEAAJXZ; CMFPropVariant::Clear(void)
0x18009f6be  jmp     loc_18009F76C
0x18009f6c3  lea     rcx, qword_1803CE250
0x18009f6ca  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18009f6d1  jmp     short loc_18009F687
0x18009f6d3  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18009f6d8  cmp     [rax+7CCh], edi
0x18009f6de  jz      short loc_18009F68D
0x18009f6e0  mov     r9d, edi; int
0x18009f6e3  lea     rdx, aCmfsamplegrabb_28; "CMFSampleGrabberStreamSink::ScheduleTim"...
0x18009f6ea  mov     r8d, 368h; int
0x18009f6f0  mov     rcx, rax; this
0x18009f6f3  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18009f6f8  jmp     short loc_18009F68D
0x18009f6fa  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18009f701  test    rcx, rcx
0x18009f704  jnz     short loc_18009F73E
0x18009f706  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18009f70d  nop     dword ptr [rax+rax+00h]
0x18009f712  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18009f719  mov     rcx, rax
0x18009f71c  test    rax, rax
0x18009f71f  jz      short loc_18009F77A
0x18009f721  mov     rax, [rax]
0x18009f724  mov     edx, 7F0h
0x18009f729  mov     rax, [rax+8]
0x18009f72d  call    cs:__guard_dispatch_icall_fptr
0x18009f733  test    eax, eax
0x18009f735  jz      short loc_18009F77A
0x18009f737  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18009f73e  cmp     [rcx+8], r12b
0x18009f742  jnz     short loc_18009F78A
0x18009f744  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18009f74b  jb      short loc_18009F76C
0x18009f74d  mov     rcx, cs:WPP_GLOBAL_Control
0x18009f754  mov     edx, 4Dh ; 'M'
0x18009f759  mov     r9, rsi
0x18009f75c  mov     dword ptr [rsp+70h+pvValue], edi
0x18009f760  mov     r8, r14
0x18009f763  mov     rcx, [rcx+10h]
0x18009f767  call    WPP_SF_qD
0x18009f76c  lea     rcx, [rbp+var_30]
0x18009f770  call    ??1?$ComSmartPtr@UIMFTransform@@@@QEAA@XZ; ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(void)
0x18009f775  jmp     loc_18009F828
0x18009f77a  lea     rcx, qword_1803CE250
0x18009f781  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18009f788  jmp     short loc_18009F73E
0x18009f78a  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18009f78f  cmp     [rax+7CCh], edi
0x18009f795  jz      short loc_18009F744
0x18009f797  mov     r9d, edi; int
0x18009f79a  lea     rdx, aCmfsamplegrabb_28; "CMFSampleGrabberStreamSink::ScheduleTim"...
0x18009f7a1  mov     r8d, 360h; int
0x18009f7a7  mov     rcx, rax; this
0x18009f7aa  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18009f7af  jmp     short loc_18009F744
0x18009f7b1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18009f7b8  mov     edi, 8000FFFFh
0x18009f7bd  test    rcx, rcx
0x18009f7c0  jnz     short loc_18009F7FA
0x18009f7c2  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18009f7c9  nop     dword ptr [rax+rax+00h]
0x18009f7ce  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18009f7d5  mov     rcx, rax
0x18009f7d8  test    rax, rax
0x18009f7db  jz      short loc_18009F849
0x18009f7dd  mov     rax, [rax]
0x18009f7e0  mov     edx, 7F0h
0x18009f7e5  mov     rax, [rax+8]
0x18009f7e9  call    cs:__guard_dispatch_icall_fptr
  ... truncated ...
```
