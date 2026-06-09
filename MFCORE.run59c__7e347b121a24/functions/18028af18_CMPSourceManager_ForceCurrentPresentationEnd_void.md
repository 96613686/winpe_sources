# CMPSourceManager::ForceCurrentPresentationEnd(void)

- ea: `0x18028af18`
- end: `0x18028ba6a`
- name: `?ForceCurrentPresentationEnd@CMPSourceManager@@AEAAJXZ`
- size: `2898`
- prototype: `__int64 __fastcall(CMPSourceManager *__hidden this)`
- caller_count: `2`
- callee_count: `12`
- tags: ``

## callers

- `0x18014902c`
- `0x1802037f4`

## callees

- `0x18002fee0`
- `0x18003ecb0`
- `0x1800402c0`
- `0x18004d118`
- `0x180050d6c`
- `0x18006b388`
- `0x18008b3a0`
- `0x1800a33c8`
- `0x1800ec0e0`
- `0x180162aec`
- `0x18028af18`
- `0x180344d40`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18028afb8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18028b106`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18028b198`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18028b253`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18028b468`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18028b4fa`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18028b58c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18028b61e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18028b6b0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18028b742`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18028b81f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18028b8d9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18028b982`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18028afb8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18028b106`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18028b198`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18028b253`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18028b468`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18028b4fa`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18028b58c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18028b61e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18028b6b0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18028b742`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18028b81f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18028b8d9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18028b982`
- `MFPlat!MFCreateMediaEvent` at `0x18028b3d6`
- `MFPlat!MFCreateMediaEvent` at `0x18028b7fd`
- `MFPlat!MFCreateMediaEvent` at `0x18028b3d6`
- `MFPlat!MFCreateMediaEvent` at `0x18028b7fd`

## pseudocode

```c
__int64 __fastcall CMPSourceManager::ForceCurrentPresentationEnd(CMFMediaProcessor **this)
{
  CMFMediaProcessor *v2; // rax
  __int64 v3; // rdx
  HRESULT v4; // ebx
  __int64 v5; // r8
  __int64 *v6; // rcx
  CallStackTracing *v7; // rax
  struct CallStackContext *v8; // rax
  __int64 v9; // rdx
  unsigned __int16 i; // r14
  __int64 v11; // rdx
  __int64 v12; // r8
  __int64 v13; // rdx
  __int64 v14; // r8
  __int64 *v15; // rcx
  CallStackTracing *v16; // rax
  struct CallStackContext *v17; // rax
  __int64 *v18; // rcx
  CallStackTracing *v19; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v21; // rdx
  __int64 v22; // r8
  __int64 *v23; // rcx
  CallStackTracing *v24; // rax
  struct CallStackContext *v25; // rax
  unsigned __int16 j; // r14
  __int64 v27; // rdx
  __int64 v28; // r8
  __int64 v29; // rdx
  __int64 v30; // r8
  __int64 v31; // rdx
  __int64 v32; // r8
  __int64 v33; // rdx
  __int64 v34; // r8
  __int64 v35; // rdx
  __int64 v36; // r8
  __int64 v37; // rdx
  __int64 v38; // r8
  __int64 *v39; // rcx
  CallStackTracing *v40; // rax
  struct CallStackContext *v41; // rax
  __int64 *v42; // rcx
  CallStackTracing *v43; // rax
  struct CallStackContext *v44; // rax
  __int64 *v45; // rcx
  CallStackTracing *v46; // rax
  struct CallStackContext *v47; // rax
  __int64 *v48; // rcx
  CallStackTracing *v49; // rax
  struct CallStackContext *v50; // rax
  __int64 *v51; // rcx
  CallStackTracing *v52; // rax
  struct CallStackContext *v53; // rax
  __int64 *v54; // rcx
  CallStackTracing *v55; // rax
  struct CallStackContext *v56; // rax
  __int64 v57; // rdx
  __int64 v58; // r8
  __int64 *v59; // rcx
  CallStackTracing *v60; // rax
  struct CallStackContext *v61; // rax
  __int64 v62; // rdx
  __int64 v63; // r8
  __int64 *v64; // rcx
  CallStackTracing *v65; // rax
  struct CallStackContext *v66; // rax
  __int64 v67; // rdx
  __int64 v68; // r8
  __int64 *v69; // rcx
  CallStackTracing *v70; // rax
  struct CallStackContext *v71; // rax
  char v73; // [rsp+80h] [rbp+48h] BYREF
  unsigned __int16 v74; // [rsp+88h] [rbp+50h] BYREF
  struct IMFTopologyNode *v75; // [rsp+90h] [rbp+58h] BYREF
  IMFMediaEvent *ppEvent; // [rsp+98h] [rbp+60h] BYREF

  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)&v73,
    "CMPSourceManager::ForceCurrentPresentationEnd",
    2842);
  if ( (unsigned __int8)byte_1803CECE9 >= 4u )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 7), 243, &WPP_188564bb451e36b573e3a8eb23999d24_Traceguids, this);
  v2 = this[5];
  v74 = 0;
  v75 = 0;
  ppEvent = 0;
  v4 = (*(__int64 (__fastcall **)(_QWORD, unsigned __int16 *))(**((_QWORD **)v2 + 33) + 288LL))(
         *((_QWORD *)v2 + 33),
         &v74);
  if ( v4 >= 0 )
  {
    for ( i = 0; i < v74; ++i )
    {
      if ( v75 )
      {
        ((void (__fastcall *)(struct IMFTopologyNode *))v75->lpVtbl->Release)(v75);
        v75 = 0;
      }
      v4 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, struct IMFTopologyNode **))(**((_QWORD **)this[5] + 33) + 296LL))(
             *((_QWORD *)this[5] + 33),
             i,
             &v75);
      if ( v4 < 0 )
      {
        v18 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v19 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v11, v12);
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
          ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v18);
          if ( *((_DWORD *)ThreadRelativeContext + 499) != v4 )
            CallStackContext::TraceFailure(
              ThreadRelativeContext,
              "CMPSourceManager::ForceCurrentPresentationEnd",
              2860,
              v4);
        }
        if ( g_wppLevels )
        {
          v9 = 245;
          goto LABEL_165;
        }
        goto LABEL_166;
      }
      if ( (unsigned __int8)byte_1803CECE9 >= 0x10u )
        WPP_SF_qq(*((_QWORD *)WPP_GLOBAL_Control + 7), 246, &WPP_188564bb451e36b573e3a8eb23999d24_Traceguids, this, v75);
      v4 = ((__int64 (__fastcall *)(struct IMFTopologyNode *, const IID *, __int64))v75->lpVtbl->SetUINT32)(
             v75,
             &MF_TOPONODE_FLUSH,
             2);
      if ( v4 < 0 )
      {
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
          if ( *((_DWORD *)v17 + 499) != v4 )
            CallStackContext::TraceFailure(v17, "CMPSourceManager::ForceCurrentPresentationEnd", 2867, v4);
        }
        if ( g_wppLevels )
        {
          v9 = 247;
          goto LABEL_165;
        }
        goto LABEL_166;
      }
    }
    v4 = (*(__int64 (__fastcall **)(_QWORD, unsigned __int16 *))(**((_QWORD **)this[5] + 33) + 288LL))(
           *((_QWORD *)this[5] + 33),
           &v74);
    if ( v4 >= 0 )
    {
      for ( j = 0; j < v74; ++j )
      {
        if ( v75 )
        {
          ((void (__fastcall *)(struct IMFTopologyNode *))v75->lpVtbl->Release)(v75);
          v75 = 0;
        }
        v4 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, struct IMFTopologyNode **))(**((_QWORD **)this[5] + 33) + 296LL))(
               *((_QWORD *)this[5] + 33),
               j,
               &v75);
        if ( v4 < 0 )
        {
          v54 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v55 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v27, v28);
            CallStackTracing::s_wpInstance = v55;
            if ( v55 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v55 + 8LL))(v55, 2032) )
            {
              v54 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v54 = &qword_1803CE250;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
            }
          }
          if ( *((_BYTE *)v54 + 8) )
          {
            v56 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v54);
            if ( *((_DWORD *)v56 + 499) != v4 )
              CallStackContext::TraceFailure(v56, "CMPSourceManager::ForceCurrentPresentationEnd", 2881, v4);
          }
          if ( g_wppLevels )
          {
            v9 = 249;
            goto LABEL_165;
          }
          goto LABEL_166;
        }
        if ( (unsigned int)MFGetAttributeUINT32(v75, &unk_18037E640, 0) )
        {
          if ( (unsigned __int8)byte_1803CECE9 >= 0x10u )
            WPP_SF_qq(
              *((_QWORD *)WPP_GLOBAL_Control + 7),
              250,
              &WPP_188564bb451e36b573e3a8eb23999d24_Traceguids,
              this,
              v75);
          v4 = ((__int64 (__fastcall *)(struct IMFTopologyNode *, const IID *, __int64))v75->lpVtbl->SetUINT32)(
                 v75,
                 &MF_TOPONODE_FLUSH,
                 2);
          if ( v4 < 0 )
          {
            v51 = (__int64 *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v52 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v29, v30);
              CallStackTracing::s_wpInstance = v52;
              if ( v52
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v52 + 8LL))(v52, 2032) )
              {
                v51 = (__int64 *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v51 = &qword_1803CE250;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
              }
            }
            if ( *((_BYTE *)v51 + 8) )
            {
              v53 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v51);
              if ( *((_DWORD *)v53 + 499) != v4 )
                CallStackContext::TraceFailure(v53, "CMPSourceManager::ForceCurrentPresentationEnd", 2893, v4);
            }
            if ( g_wppLevels )
            {
              v9 = 251;
              goto LABEL_165;
            }
            goto LABEL_166;
          }
          if ( ppEvent )
          {
            ((void (__fastcall *)(IMFMediaEvent *))ppEvent->lpVtbl->Release)(ppEvent);
            ppEvent = 0;
          }
          v4 = MFCreateMediaEvent(0xD4u, &GUID_00000000_0000_0000_0000_000000000000, 0, 0, &ppEvent);
          if ( v4 < 0 )
          {
            v48 = (__int64 *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v49 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v31, v32);
              CallStackTracing::s_wpInstance = v49;
              if ( v49
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v49 + 8LL))(v49, 2032) )
              {
                v48 = (__int64 *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v48 = &qword_1803CE250;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
              }
            }
            if ( *((_BYTE *)v48 + 8) )
            {
              v50 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v48);
              if ( *((_DWORD *)v50 + 499) != v4 )
                CallStackContext::TraceFailure(v50, "CMPSourceManager::ForceCurrentPresentationEnd", 2898, v4);
            }
            if ( g_wppLevels )
            {
              v9 = 252;
              goto LABEL_165;
            }
            goto LABEL_166;
          }
          v4 = ((__int64 (__fastcall *)(IMFMediaEvent *, void *, __int64))ppEvent->lpVtbl->SetUINT32)(
                 ppEvent,
                 &unk_18037E630,
                 1);
          if ( v4 < 0 )
          {
            v45 = (__int64 *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v46 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v33, v34);
              CallStackTracing::s_wpInstance = v46;
              if ( v46
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v46 + 8LL))(v46, 2032) )
              {
                v45 = (__int64 *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v45 = &qword_1803CE250;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
              }
            }
            if ( *((_BYTE *)v45 + 8) )
            {
              v47 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v45);
              if ( *((_DWORD *)v47 + 499) != v4 )
                CallStackContext::TraceFailure(v47, "CMPSourceManager::ForceCurrentPresentationEnd", 2900, v4);
            }
            if ( g_wppLevels )
            {
              v9 = 253;
              goto LABEL_165;
            }
            goto LABEL_166;
          }
          v4 = CMFMediaProcessor::OnNodeEvent(this[4], v75, ppEvent);
          if ( v4 < 0 )
          {
            v42 = (__int64 *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v43 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v35, v36);
              CallStackTracing::s_wpInstance = v43;
              if ( v43
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v43 + 8LL))(v43, 2032) )
              {
                v42 = (__int64 *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v42 = &qword_1803CE250;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
              }
            }
            if ( *((_BYTE *)v42 + 8) )
            {
              v44 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v42);
              if ( *((_DWORD *)v44 + 499) != v4 )
                CallStackContext::TraceFailure(v44, "CMPSourceManager::ForceCurrentPresentationEnd", 2902, v4);
            }
            if ( g_wppLevels )
            {
              v9 = 254;
              goto LABEL_165;
            }
            goto LABEL_166;
          }
          v4 = ((__int64 (__fastcall *)(IMFMediaEvent *, void *, __int64))ppEvent->lpVtbl->SetUINT32)(
                 ppEvent,
                 &MF_EVENT_ENDOfSTREAM_FORCEPRESENTATIONEND,
                 1);
          if ( v4 < 0 )
          {
            v39 = (__int64 *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v40 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v37, v38);
              CallStackTracing::s_wpInstance = v40;
              if ( v40
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v40 + 8LL))(v40, 2032) )
              {
                v39 = (__int64 *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v39 = &qword_1803CE250;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
              }
            }
            if ( *((_BYTE *)v39 + 8) )
            {
              v41 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v39);
              if ( *((_DWORD *)v41 + 499) != v4 )
                CallStackContext::TraceFailure(v41, "CMPSourceManager::ForceCurrentPresentationEnd", 2904, v4);
            }
            if ( g_wppLevels )
            {
              v9 = 255;
              goto LABEL_165;
            }
            goto LABEL_166;
          }
        }
      }
      if ( ppEvent )
      {
        ((void (__fastcall *)(IMFMediaEvent *))ppEvent->lpVtbl->Release)(ppEvent);
        ppEvent = 0;
      }
      v4 = MFCreateMediaEvent(0xDAu, &GUID_00000000_0000_0000_0000_000000000000, 0, 0, &ppEvent);
      if ( v4 >= 0 )
      {
        v4 = ((__int64 (__fastcall *)(IMFMediaEvent *, void *, __int64))ppEvent->lpVtbl->SetUINT32)(
               ppEvent,
               &unk_18037E630,
               1);
        if ( v4 >= 0 )
        {
          v4 = CMFMediaProcessor::OnSourceEvent(this[4], ppEvent);
          if ( v4 < 0 )
          {
            v69 = (__int64 *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v70 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v67, v68);
              CallStackTracing::s_wpInstance = v70;
              if ( v70
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v70 + 8LL))(v70, 2032) )
              {
                v69 = (__int64 *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v69 = &qword_1803CE250;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
              }
            }
            if ( *((_BYTE *)v69 + 8) )
            {
              v71 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v69);
              if ( *((_DWORD *)v71 + 499) != v4 )
                CallStackContext::TraceFailure(v71, "CMPSourceManager::ForceCurrentPresentationEnd", 2916, v4);
            }
            if ( g_wppLevels )
            {
              v9 = 258;
              goto LABEL_165;
            }
          }
        }
        else
        {
          v64 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v65 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v62, v63);
            CallStackTracing::s_wpInstance = v65;
            if ( v65 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v65 + 8LL))(v65, 2032) )
            {
              v64 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v64 = &qword_1803CE250;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
            }
          }
          if ( *((_BYTE *)v64 + 8) )
          {
            v66 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v64);
            if ( *((_DWORD *)v66 + 499) != v4 )
              CallStackContext::TraceFailure(v66, "CMPSourceManager::ForceCurrentPresentationEnd", 2914, v4);
          }
          if ( g_wppLevels )
          {
            v9 = 257;
            goto LABEL_165;
          }
        }
      }
      else
      {
        v59 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v60 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v57, v58);
          CallStackTracing::s_wpInstance = v60;
          if ( v60 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v60 + 8LL))(v60, 2032) )
          {
            v59 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v59 = &qword_1803CE250;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
          }
        }
        if ( *((_BYTE *)v59 + 8) )
        {
          v61 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v59);
          if ( *((_DWORD *)v61 + 499) != v4 )
            CallStackContext::TraceFailure(v61, "CMPSourceManager::ForceCurrentPresentationEnd", 2913, v4);
        }
        if ( g_wppLevels )
        {
          v9 = 256;
          goto LABEL_165;
        }
      }
    }
    else
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
        v25 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v23);
        if ( *((_DWORD *)v25 + 499) != v4 )
          CallStackContext::TraceFailure(v25, "CMPSourceManager::ForceCurrentPresentationEnd", 2875, v4);
      }
      if ( g_wppLevels )
      {
        v9 = 248;
        goto LABEL_165;
      }
    }
  }
  else
  {
    v6 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v7 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v3, v5);
      CallStackTracing::s_wpInstance = v7;
      if ( v7 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v7 + 8LL))(v7, 2032) )
      {
        v6 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v6 = &qword_1803CE250;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
      }
    }
    if ( *((_BYTE *)v6 + 8) )
    {
      v8 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v6);
      if ( *((_DWORD *)v8 + 499) != v4 )
        CallStackContext::TraceFailure(v8, "CMPSourceManager::ForceCurrentPresentationEnd", 2854, v4);
    }
    if ( g_wppLevels )
    {
      v9 = 244;
LABEL_165:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v9, &WPP_188564bb451e36b573e3a8eb23999d24_Traceguids, this, v4);
    }
  }
LABEL_166:
  if ( v75 )
  {
    ((void (__fastcall *)(struct IMFTopologyNode *))v75->lpVtbl->Release)(v75);
    v75 = 0;
  }
  if ( ppEvent )
  {
    ((void (__fastcall *)(IMFMediaEvent *))ppEvent->lpVtbl->Release)(ppEvent);
    ppEvent = 0;
  }
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v73);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18028af18  push    rbp
0x18028af1a  push    rbx
0x18028af1b  push    rsi
0x18028af1c  push    rdi
0x18028af1d  push    r12
0x18028af1f  push    r13
0x18028af21  push    r14
0x18028af23  push    r15
0x18028af25  mov     rbp, rsp
0x18028af28  sub     rsp, 38h
0x18028af2c  mov     rsi, rcx
0x18028af2f  lea     r13, aCmpsourcemanag_11; "CMPSourceManager::ForceCurrentPresentat"...
0x18028af36  mov     rdx, r13; char *
0x18028af39  lea     rcx, [rbp+arg_0]; this
0x18028af3d  mov     r8d, 0B1Ah; int
0x18028af43  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18028af48  cmp     cs:byte_1803CECE9, 4
0x18028af4f  lea     r12, WPP_188564bb451e36b573e3a8eb23999d24_Traceguids
0x18028af56  jb      short loc_18028AF73
0x18028af58  mov     rcx, cs:WPP_GLOBAL_Control
0x18028af5f  mov     edx, 0F3h
0x18028af64  mov     r9, rsi
0x18028af67  mov     r8, r12
0x18028af6a  mov     rcx, [rcx+38h]
0x18028af6e  call    WPP_SF_q
0x18028af73  mov     rax, [rsi+28h]
0x18028af77  lea     rdx, [rbp+arg_8]
0x18028af7b  xor     r15d, r15d
0x18028af7e  mov     [rbp+arg_8], r15w
0x18028af83  mov     [rbp+arg_10], r15
0x18028af87  mov     [rbp+arg_18], r15
0x18028af8b  mov     rcx, [rax+108h]
0x18028af92  mov     rax, [rcx]
0x18028af95  mov     rax, [rax+120h]
0x18028af9c  call    cs:__guard_dispatch_icall_fptr
0x18028afa2  mov     ebx, eax
0x18028afa4  test    eax, eax
0x18028afa6  jns     loc_18028B043
0x18028afac  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18028afb3  test    rcx, rcx
0x18028afb6  jnz     short loc_18028B000
0x18028afb8  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18028afbf  nop     dword ptr [rax+rax+00h]
0x18028afc4  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18028afcb  mov     rcx, rax
0x18028afce  test    rax, rax
0x18028afd1  jz      short loc_18028AFF2
0x18028afd3  mov     rax, [rax]
0x18028afd6  mov     edx, 7F0h
0x18028afdb  mov     rax, [rax+8]
0x18028afdf  call    cs:__guard_dispatch_icall_fptr
0x18028afe5  test    eax, eax
0x18028afe7  jz      short loc_18028AFF2
0x18028afe9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18028aff0  jmp     short loc_18028B000
0x18028aff2  lea     rcx, qword_1803CE250; this
0x18028aff9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18028b000  cmp     [rcx+8], r15b
0x18028b004  jz      short loc_18028B027
0x18028b006  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18028b00b  cmp     [rax+7CCh], ebx
0x18028b011  jz      short loc_18028B027
0x18028b013  mov     r9d, ebx; int
0x18028b016  mov     r8d, 0B26h; int
0x18028b01c  mov     rdx, r13; char *
0x18028b01f  mov     rcx, rax; this
0x18028b022  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18028b027  mov     edi, 1
0x18028b02c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, dil; MFWppLevels g_wppLevels
0x18028b033  jb      loc_18028BA19
0x18028b039  mov     edx, 0F4h
0x18028b03e  jmp     loc_18028B9FF
0x18028b043  mov     r14d, r15d
0x18028b046  mov     edi, 1
0x18028b04b  cmp     r14w, [rbp+arg_8]
0x18028b050  jnb     loc_18028B21E
0x18028b056  mov     rcx, [rbp+arg_10]
0x18028b05a  test    rcx, rcx
0x18028b05d  jz      short loc_18028B070
0x18028b05f  mov     rax, [rcx]
0x18028b062  mov     rax, [rax+10h]
0x18028b066  call    cs:__guard_dispatch_icall_fptr
0x18028b06c  mov     [rbp+arg_10], r15
0x18028b070  mov     rax, [rsi+28h]
0x18028b074  lea     r8, [rbp+arg_10]
0x18028b078  movzx   edx, r14w
0x18028b07c  mov     rcx, [rax+108h]
0x18028b083  mov     rax, [rcx]
0x18028b086  mov     rax, [rax+128h]
0x18028b08d  call    cs:__guard_dispatch_icall_fptr
0x18028b093  mov     ebx, eax
0x18028b095  test    eax, eax
0x18028b097  js      loc_18028B18C
0x18028b09d  cmp     cs:byte_1803CECE9, 10h
0x18028b0a4  jb      short loc_18028B0CA
0x18028b0a6  mov     rcx, cs:WPP_GLOBAL_Control
0x18028b0ad  mov     edx, 0F6h
0x18028b0b2  mov     rax, [rbp+arg_10]
0x18028b0b6  mov     r9, rsi
0x18028b0b9  mov     r8, r12
0x18028b0bc  mov     [rsp+38h+ppEvent], rax
0x18028b0c1  mov     rcx, [rcx+38h]
0x18028b0c5  call    WPP_SF_qq
0x18028b0ca  mov     rcx, [rbp+arg_10]
0x18028b0ce  lea     rdx, MF_TOPONODE_FLUSH
0x18028b0d5  mov     r8d, 2
0x18028b0db  mov     rax, [rcx]
0x18028b0de  mov     rax, [rax+0A8h]
0x18028b0e5  call    cs:__guard_dispatch_icall_fptr
0x18028b0eb  mov     ebx, eax
0x18028b0ed  test    eax, eax
0x18028b0ef  js      short loc_18028B0FA
0x18028b0f1  add     r14w, di
0x18028b0f5  jmp     loc_18028B04B
0x18028b0fa  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18028b101  test    rcx, rcx
0x18028b104  jnz     short loc_18028B14E
0x18028b106  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18028b10d  nop     dword ptr [rax+rax+00h]
0x18028b112  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18028b119  mov     rcx, rax
0x18028b11c  test    rax, rax
0x18028b11f  jz      short loc_18028B140
0x18028b121  mov     rax, [rax]
0x18028b124  mov     edx, 7F0h
0x18028b129  mov     rax, [rax+8]
0x18028b12d  call    cs:__guard_dispatch_icall_fptr
0x18028b133  test    eax, eax
0x18028b135  jz      short loc_18028B140
0x18028b137  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18028b13e  jmp     short loc_18028B14E
0x18028b140  lea     rcx, qword_1803CE250; this
0x18028b147  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18028b14e  cmp     [rcx+8], r15b
0x18028b152  jz      short loc_18028B175
0x18028b154  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18028b159  cmp     [rax+7CCh], ebx
0x18028b15f  jz      short loc_18028B175
0x18028b161  mov     r9d, ebx; int
0x18028b164  mov     r8d, 0B33h; int
0x18028b16a  mov     rdx, r13; char *
0x18028b16d  mov     rcx, rax; this
0x18028b170  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18028b175  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, dil; MFWppLevels g_wppLevels
0x18028b17c  jb      loc_18028BA19
0x18028b182  mov     edx, 0F7h
0x18028b187  jmp     loc_18028B9FF
0x18028b18c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18028b193  test    rcx, rcx
0x18028b196  jnz     short loc_18028B1E0
0x18028b198  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18028b19f  nop     dword ptr [rax+rax+00h]
0x18028b1a4  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18028b1ab  mov     rcx, rax
0x18028b1ae  test    rax, rax
0x18028b1b1  jz      short loc_18028B1D2
0x18028b1b3  mov     rax, [rax]
0x18028b1b6  mov     edx, 7F0h
0x18028b1bb  mov     rax, [rax+8]
0x18028b1bf  call    cs:__guard_dispatch_icall_fptr
0x18028b1c5  test    eax, eax
0x18028b1c7  jz      short loc_18028B1D2
0x18028b1c9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18028b1d0  jmp     short loc_18028B1E0
0x18028b1d2  lea     rcx, qword_1803CE250; this
0x18028b1d9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18028b1e0  cmp     [rcx+8], r15b
0x18028b1e4  jz      short loc_18028B207
0x18028b1e6  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18028b1eb  cmp     [rax+7CCh], ebx
0x18028b1f1  jz      short loc_18028B207
0x18028b1f3  mov     r9d, ebx; int
0x18028b1f6  mov     r8d, 0B2Ch; int
0x18028b1fc  mov     rdx, r13; char *
0x18028b1ff  mov     rcx, rax; this
0x18028b202  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18028b207  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, dil; MFWppLevels g_wppLevels
0x18028b20e  jb      loc_18028BA19
0x18028b214  mov     edx, 0F5h
0x18028b219  jmp     loc_18028B9FF
0x18028b21e  mov     rax, [rsi+28h]
0x18028b222  lea     rdx, [rbp+arg_8]
0x18028b226  mov     rcx, [rax+108h]
0x18028b22d  mov     rax, [rcx]
0x18028b230  mov     rax, [rax+120h]
0x18028b237  call    cs:__guard_dispatch_icall_fptr
0x18028b23d  mov     ebx, eax
0x18028b23f  test    eax, eax
0x18028b241  jns     loc_18028B2D9
0x18028b247  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18028b24e  test    rcx, rcx
0x18028b251  jnz     short loc_18028B29B
0x18028b253  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18028b25a  nop     dword ptr [rax+rax+00h]
0x18028b25f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18028b266  mov     rcx, rax
0x18028b269  test    rax, rax
0x18028b26c  jz      short loc_18028B28D
0x18028b26e  mov     rax, [rax]
0x18028b271  mov     edx, 7F0h
0x18028b276  mov     rax, [rax+8]
0x18028b27a  call    cs:__guard_dispatch_icall_fptr
0x18028b280  test    eax, eax
0x18028b282  jz      short loc_18028B28D
0x18028b284  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18028b28b  jmp     short loc_18028B29B
0x18028b28d  lea     rcx, qword_1803CE250; this
0x18028b294  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18028b29b  cmp     [rcx+8], r15b
0x18028b29f  jz      short loc_18028B2C2
0x18028b2a1  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18028b2a6  cmp     [rax+7CCh], ebx
0x18028b2ac  jz      short loc_18028B2C2
0x18028b2ae  mov     r9d, ebx; int
0x18028b2b1  mov     r8d, 0B3Bh; int
0x18028b2b7  mov     rdx, r13; char *
0x18028b2ba  mov     rcx, rax; this
0x18028b2bd  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18028b2c2  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, dil; MFWppLevels g_wppLevels
0x18028b2c9  jb      loc_18028BA19
0x18028b2cf  mov     edx, 0F8h
0x18028b2d4  jmp     loc_18028B9FF
0x18028b2d9  mov     r14d, r15d
0x18028b2dc  cmp     r14w, [rbp+arg_8]
0x18028b2e1  jnb     loc_18028B7C8
0x18028b2e7  mov     rcx, [rbp+arg_10]
0x18028b2eb  test    rcx, rcx
0x18028b2ee  jz      short loc_18028B301
0x18028b2f0  mov     rax, [rcx]
0x18028b2f3  mov     rax, [rax+10h]
0x18028b2f7  call    cs:__guard_dispatch_icall_fptr
0x18028b2fd  mov     [rbp+arg_10], r15
0x18028b301  mov     rax, [rsi+28h]
0x18028b305  lea     r8, [rbp+arg_10]
0x18028b309  movzx   edx, r14w
0x18028b30d  mov     rcx, [rax+108h]
0x18028b314  mov     rax, [rcx]
0x18028b317  mov     rax, [rax+128h]
0x18028b31e  call    cs:__guard_dispatch_icall_fptr
0x18028b324  mov     ebx, eax
0x18028b326  test    eax, eax
0x18028b328  js      loc_18028B736
0x18028b32e  mov     rcx, [rbp+arg_10]
0x18028b332  lea     rdx, unk_18037E640
0x18028b339  xor     r8d, r8d
0x18028b33c  call    MFGetAttributeUINT32
0x18028b341  test    eax, eax
0x18028b343  jz      loc_18028B453
0x18028b349  cmp     cs:byte_1803CECE9, 10h
0x18028b350  jb      short loc_18028B376
0x18028b352  mov     rcx, cs:WPP_GLOBAL_Control
0x18028b359  mov     edx, 0FAh
0x18028b35e  mov     rax, [rbp+arg_10]
0x18028b362  mov     r9, rsi
0x18028b365  mov     r8, r12
0x18028b368  mov     [rsp+38h+ppEvent], rax
0x18028b36d  mov     rcx, [rcx+38h]
0x18028b371  call    WPP_SF_qq
0x18028b376  mov     rcx, [rbp+arg_10]
0x18028b37a  lea     rdx, MF_TOPONODE_FLUSH
0x18028b381  mov     r8d, 2
0x18028b387  mov     rax, [rcx]
0x18028b38a  mov     rax, [rax+0A8h]
0x18028b391  call    cs:__guard_dispatch_icall_fptr
0x18028b397  mov     ebx, eax
0x18028b399  test    eax, eax
0x18028b39b  js      loc_18028B6A4
0x18028b3a1  mov     rcx, [rbp+arg_18]
0x18028b3a5  test    rcx, rcx
0x18028b3a8  jz      short loc_18028B3BB
0x18028b3aa  mov     rax, [rcx]
0x18028b3ad  mov     rax, [rax+10h]
0x18028b3b1  call    cs:__guard_dispatch_icall_fptr
0x18028b3b7  mov     [rbp+arg_18], r15
0x18028b3bb  lea     rax, [rbp+arg_18]
0x18028b3bf  xor     r9d, r9d; pvValue
0x18028b3c2  xor     r8d, r8d; hrStatus
0x18028b3c5  mov     [rsp+38h+ppEvent], rax; ppEvent
0x18028b3ca  lea     rdx, _GUID_00000000_0000_0000_0000_000000000000; guidExtendedType
0x18028b3d1  mov     ecx, 0D4h; met
0x18028b3d6  call    cs:__imp_MFCreateMediaEvent
0x18028b3dd  nop     dword ptr [rax+rax+00h]
0x18028b3e2  mov     ebx, eax
0x18028b3e4  test    eax, eax
0x18028b3e6  js      loc_18028B612
0x18028b3ec  mov     rcx, [rbp+arg_18]
0x18028b3f0  lea     rdx, unk_18037E630
0x18028b3f7  mov     r8d, edi
0x18028b3fa  mov     rax, [rcx]
0x18028b3fd  mov     rax, [rax+0A8h]
0x18028b404  call    cs:__guard_dispatch_icall_fptr
0x18028b40a  mov     ebx, eax
0x18028b40c  test    eax, eax
0x18028b40e  js      loc_18028B580
0x18028b414  mov     r8, [rbp+arg_18]; struct IMFMediaEvent *
0x18028b418  mov     rdx, [rbp+arg_10]; struct IMFTopologyNode *
0x18028b41c  mov     rcx, [rsi+20h]; this
0x18028b420  call    ?OnNodeEvent@CMFMediaProcessor@@IEAAJPEAUIMFTopologyNode@@PEAUIMFMediaEvent@@@Z; CMFMediaProcessor::OnNodeEvent(IMFTopologyNode *,IMFMediaEvent *)
0x18028b425  mov     ebx, eax
0x18028b427  test    eax, eax
  ... truncated ...
```
