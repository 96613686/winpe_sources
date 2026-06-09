# CAudStreamSink::GetService(_GUID const &,_GUID const &,void * *)

- ea: `0x1800e2590`
- end: `0x1800e32bb`
- name: `?GetService@CAudStreamSink@@UEAAJAEBU_GUID@@0PEAPEAX@Z`
- size: `3371`
- prototype: `int(CAudStreamSink *__hidden this, const struct _GUID *, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800e0ea0`

## callees

- `0x18002fee0`
- `0x18003ecb0`
- `0x1800402c0`
- `0x180050d6c`
- `0x180063f00`
- `0x18006b388`
- `0x1800e2590`
- `0x1800e32d0`
- `0x1800ec0e0`
- `0x180176760`
- `0x18023e1a0`
- `0x180258480`
- `0x18031941c`
- `0x180344cd8`
- `0x180344d40`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800e2ec5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800e2ec5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800e2d57`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800e2d57`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800e2657`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800e2709`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800e27ea`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800e28c6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800e29ab`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800e2a44`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800e2b2d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800e2bc4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800e2c98`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800e2e16`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800e2f23`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800e302f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800e3157`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800e31ee`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800e2657`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800e2709`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800e27ea`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800e28c6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800e29ab`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800e2a44`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800e2b2d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800e2bc4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800e2c98`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800e2e16`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800e2f23`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800e302f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800e3157`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800e31ee`

## string_xrefs

- `0x1800e25b9`: `CAudStreamSink::GetService`
- `0x1800e26b8`: `CAudStreamSink::GetService`
- `0x1800e276a`: `CAudStreamSink::GetService`
- `0x1800e284b`: `CAudStreamSink::GetService`
- `0x1800e2927`: `CAudStreamSink::GetService`
- `0x1800e2a0c`: `CAudStreamSink::GetService`
- `0x1800e2aa5`: `CAudStreamSink::GetService`
- `0x1800e2b8e`: `CAudStreamSink::GetService`
- `0x1800e2c25`: `CAudStreamSink::GetService`
- `0x1800e2cf9`: `CAudStreamSink::GetService`
- `0x1800e2e77`: `CAudStreamSink::GetService`
- `0x1800e2f84`: `CAudStreamSink::GetService`
- `0x1800e3090`: `CAudStreamSink::GetService`
- `0x1800e31b8`: `CAudStreamSink::GetService`
- `0x1800e324f`: `CAudStreamSink::GetService`

## pseudocode

```c
__int64 __fastcall CAudStreamSink::GetService(
        CAudStreamSink *this,
        const struct _GUID *a2,
        const struct _GUID *a3,
        void **a4)
{
  __int64 v8; // rdx
  __int64 v9; // rcx
  __int64 v10; // r8
  __int64 *v11; // rbx
  struct CallStackContext *ThreadRelativeContext; // rdi
  int v13; // ebx
  __int128 v14; // xmm0
  int Interface; // edi
  CallStackTracing *v16; // rax
  struct CallStackContext *v17; // rax
  char *v18; // r9
  __int64 v19; // rdx
  char *v20; // rsi
  CallStackTracing *v21; // rax
  struct CallStackContext *v22; // rax
  __int64 v23; // rdx
  __int64 v24; // rcx
  __int64 v25; // r8
  unsigned __int64 v26; // rcx
  CallStackTracing *v27; // rax
  struct CallStackContext *v28; // rax
  __int64 v29; // rdx
  __int64 v30; // rdx
  __int64 v31; // rcx
  __int64 v32; // r8
  CallStackTracing *v33; // rax
  struct CallStackContext *v34; // rax
  __int64 v35; // rdx
  __int64 v36; // rcx
  __int64 v37; // r8
  __int64 v38; // rdx
  __int64 v39; // rcx
  __int64 v40; // r8
  __int64 *v41; // rbx
  CallStackTracing *v42; // rax
  struct CallStackContext *v43; // rax
  CallStackTracing *v44; // rax
  struct CallStackContext *v45; // rax
  __int64 v46; // rdx
  __int64 v47; // r8
  __int64 v48; // rcx
  __int64 v49; // rdx
  __int64 v50; // rcx
  __int64 v51; // r8
  __int64 *v52; // rbx
  CallStackTracing *v53; // rax
  struct CallStackContext *v54; // rax
  CallStackTracing *v55; // rax
  struct CallStackContext *v56; // rax
  __int64 v57; // rdx
  __int64 v58; // rcx
  __int64 v59; // r8
  CallStackTracing *v60; // rax
  struct CallStackContext *v61; // rax
  __int64 v62; // rdx
  int v63; // ebx
  struct IMFAttributes *v64; // rbx
  __int64 v65; // rdx
  __int64 v66; // rcx
  __int64 v67; // r8
  __int64 *v68; // rbx
  CallStackTracing *v69; // rax
  struct CallStackContext *v70; // rax
  __int64 v71; // rdx
  __int64 v72; // rdx
  __int64 v73; // rcx
  __int64 v74; // r8
  __int64 *v75; // rbx
  CallStackTracing *v76; // rax
  struct CallStackContext *v77; // rax
  __int64 v78; // rdx
  __int64 v79; // rcx
  __int64 v80; // r8
  __int64 *v81; // rbx
  CallStackTracing *v82; // rax
  struct CallStackContext *v83; // rax
  __int64 v84; // rdx
  __int64 v85; // r8
  __int64 v86; // rcx
  __int64 v87; // rdx
  __int64 v88; // rcx
  __int64 v89; // r8
  __int64 *v90; // rbx
  CallStackTracing *v91; // rax
  struct CallStackContext *v92; // rax
  CallStackTracing *v93; // rax
  struct CallStackContext *v94; // rax
  _BYTE v96[8]; // [rsp+30h] [rbp-68h] BYREF
  _QWORD v97[2]; // [rsp+38h] [rbp-60h] BYREF

  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v96, "CAudStreamSink::GetService", 608);
  v11 = (__int64 *)CallStackTracing::s_wpInstance;
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) && *((_QWORD *)this + 748) )
  {
    ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
    v13 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 748) + 296LL))(*((_QWORD *)this + 748));
    v14 = *(_OWORD *)(*(__int64 (__fastcall **)(_QWORD, _QWORD *))(**((_QWORD **)this + 748) + 280LL))(
                       *((_QWORD *)this + 748),
                       v97);
    *((_DWORD *)ThreadRelativeContext + 504) = v13;
    v11 = (__int64 *)CallStackTracing::s_wpInstance;
    *((_OWORD *)ThreadRelativeContext + 125) = v14;
  }
  if ( a4 )
  {
    v20 = (char *)this - 616;
    if ( *((_DWORD *)this - 68) == 7 )
    {
      Interface = -1072870856;
      if ( !v11 )
      {
        v21 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v9, v8, v10);
        CallStackTracing::s_wpInstance = v21;
        if ( v21 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v21 + 8LL))(v21, 2032) )
        {
          v11 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v11 = &qword_1803CE250;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
        }
      }
      if ( *((_BYTE *)v11 + 8) )
      {
        v22 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v11);
        if ( *((_DWORD *)v22 + 499) != -1072870856 )
          CallStackContext::TraceFailure(v22, "CAudStreamSink::GetService", 616, -1072870856);
      }
      if ( !g_wppLevels )
        goto LABEL_189;
      v19 = 47;
      goto LABEL_187;
    }
    *a4 = 0;
    Interface = 0;
    if ( !memcmp_0(&MR_POLICY_VOLUME_SERVICE, a2, 0x10u) )
    {
      if ( !memcmp_0(&IID_IMFSimpleAudioVolume, a3, 0x10u) )
      {
        v26 = (unsigned __int64)this - 256;
LABEL_164:
        *a4 = (void *)(v26 & -(__int64)(this != (CAudStreamSink *)616));
        _InterlockedIncrement((volatile signed __int32 *)this - 152);
        goto LABEL_189;
      }
      Interface = -2147467262;
      if ( !v11 )
      {
        v27 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v24, v23, v25);
        CallStackTracing::s_wpInstance = v27;
        if ( v27 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v27 + 8LL))(v27, 2032) )
        {
          v11 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v11 = &qword_1803CE250;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
        }
      }
      if ( *((_BYTE *)v11 + 8) )
      {
        v28 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v11);
        if ( *((_DWORD *)v28 + 499) != -2147467262 )
          CallStackContext::TraceFailure(v28, "CAudStreamSink::GetService", 632, -2147467262);
      }
      if ( !g_wppLevels )
        goto LABEL_189;
      v29 = 48;
      goto LABEL_39;
    }
    if ( !memcmp_0(&MR_STREAM_VOLUME_SERVICE, a2, 0x10u) )
    {
      if ( !memcmp_0(&IID_IMFAudioStreamVolume, a3, 0x10u) )
      {
        v26 = (unsigned __int64)this - 248;
        goto LABEL_164;
      }
      Interface = -2147467262;
      if ( !v11 )
      {
        v33 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v31, v30, v32);
        CallStackTracing::s_wpInstance = v33;
        if ( v33 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v33 + 8LL))(v33, 2032) )
        {
          v11 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v11 = &qword_1803CE250;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
        }
      }
      if ( *((_BYTE *)v11 + 8) )
      {
        v34 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v11);
        if ( *((_DWORD *)v34 + 499) != -2147467262 )
          CallStackContext::TraceFailure(v34, "CAudStreamSink::GetService", 644, -2147467262);
      }
      if ( !g_wppLevels )
        goto LABEL_189;
      v29 = 49;
LABEL_39:
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v29,
        &WPP_8e6dbb68bb473dec012b49037e0fe992_Traceguids,
        v20,
        -2147467262);
      goto LABEL_189;
    }
    if ( !memcmp_0(&MF_RATE_CONTROL_SERVICE, a2, 0x10u) )
    {
      if ( memcmp_0(&IID_IMFRateSupport, a3, 0x10u) )
      {
        Interface = -2147467262;
        if ( !v11 )
        {
          v44 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v36, v35, v37);
          CallStackTracing::s_wpInstance = v44;
          if ( v44 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v44 + 8LL))(v44, 2032) )
          {
            v11 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v11 = &qword_1803CE250;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
          }
        }
        if ( *((_BYTE *)v11 + 8) )
        {
          v45 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v11);
          if ( *((_DWORD *)v45 + 499) != -2147467262 )
            CallStackContext::TraceFailure(v45, "CAudStreamSink::GetService", 656, -2147467262);
        }
        if ( !g_wppLevels )
          goto LABEL_189;
        v29 = 51;
        goto LABEL_39;
      }
      Interface = CAudStreamSink::QueryInterface((CAudStreamSink *)((char *)this - 616), a3, a4);
      if ( Interface >= 0 )
        goto LABEL_189;
      v41 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v42 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v39, v38, v40);
        CallStackTracing::s_wpInstance = v42;
        if ( v42 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v42 + 8LL))(v42, 2032) )
        {
          v41 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v41 = &qword_1803CE250;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
        }
      }
      if ( *((_BYTE *)v41 + 8) )
      {
        v43 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v41);
        if ( *((_DWORD *)v43 + 499) != Interface )
          CallStackContext::TraceFailure(v43, "CAudStreamSink::GetService", 652, Interface);
      }
      if ( !g_wppLevels )
        goto LABEL_189;
      v19 = 50;
LABEL_187:
      v18 = (char *)this - 616;
      goto LABEL_188;
    }
    if ( !memcmp_0(&IID_IMFAudioPolicy, a3, 0x10u) )
    {
      v48 = *(_QWORD *)&v20[*(int *)(*((_QWORD *)this - 30) + 4LL) + 384];
      if ( v48 )
      {
        Interface = (*(__int64 (__fastcall **)(__int64, const struct _GUID *, const struct _GUID *, void **))(*(_QWORD *)v48 + 48LL))(
                      v48,
                      a2,
                      a3,
                      a4);
        if ( Interface >= 0 )
          goto LABEL_189;
        v52 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v53 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v50, v49, v51);
          CallStackTracing::s_wpInstance = v53;
          if ( v53 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v53 + 8LL))(v53, 2032) )
          {
            v52 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v52 = &qword_1803CE250;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
          }
        }
        if ( *((_BYTE *)v52 + 8) )
        {
          v54 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v52);
          if ( *((_DWORD *)v54 + 499) != Interface )
            CallStackContext::TraceFailure(v54, "CAudStreamSink::GetService", 664, Interface);
        }
        if ( !g_wppLevels )
          goto LABEL_189;
        v19 = 52;
      }
      else
      {
        Interface = -1072875850;
        if ( !v11 )
        {
          v55 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v46, v47);
          CallStackTracing::s_wpInstance = v55;
          if ( v55 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v55 + 8LL))(v55, 2032) )
          {
            v11 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v11 = &qword_1803CE250;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
          }
        }
        if ( *((_BYTE *)v11 + 8) )
        {
          v56 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v11);
          if ( *((_DWORD *)v56 + 499) != -1072875850 )
            CallStackContext::TraceFailure(v56, "CAudStreamSink::GetService", 668, -1072875850);
        }
        if ( !g_wppLevels )
          goto LABEL_189;
        v19 = 53;
      }
      goto LABEL_187;
    }
    if ( memcmp_0(&MF_CLOCK_RATE_MATCH_SERVICE, a2, 0x10u) )
    {
      if ( !memcmp_0(&MR_AUDIO_RENDER_SERVICE, a2, 0x10u) )
      {
        v26 = (unsigned __int64)this + 64;
        goto LABEL_164;
      }
      v86 = *(_QWORD *)&v20[*(int *)(*((_QWORD *)this - 30) + 4LL) + 384];
      if ( v86 )
      {
        Interface = (*(__int64 (__fastcall **)(__int64, const struct _GUID *, const struct _GUID *, void **))(*(_QWORD *)v86 + 48LL))(
                      v86,
                      a2,
                      a3,
                      a4);
        if ( Interface >= 0 )
          goto LABEL_189;
        v90 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v91 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v88, v87, v89);
          CallStackTracing::s_wpInstance = v91;
          if ( v91 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v91 + 8LL))(v91, 2032) )
          {
            v90 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v90 = &qword_1803CE250;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
          }
        }
        if ( *((_BYTE *)v90 + 8) )
        {
          v92 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v90);
          if ( *((_DWORD *)v92 + 499) != Interface )
            CallStackContext::TraceFailure(v92, "CAudStreamSink::GetService", 739, Interface);
        }
        if ( !g_wppLevels )
          goto LABEL_189;
        v19 = 62;
      }
      else
      {
        Interface = -1072875846;
        if ( !v11 )
        {
          v93 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v84, v85);
          CallStackTracing::s_wpInstance = v93;
          if ( v93 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v93 + 8LL))(v93, 2032) )
          {
            v11 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v11 = &qword_1803CE250;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
          }
        }
        if ( *((_BYTE *)v11 + 8) )
        {
          v94 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v11);
          if ( *((_DWORD *)v94 + 499) != -1072875846 )
            CallStackContext::TraceFailure(v94, "CAudStreamSink::GetService", 743, -1072875846);
        }
        if ( !g_wppLevels )
          goto LABEL_189;
        v19 = 63;
      }
      goto LABEL_187;
    }
    if ( memcmp_0(&IID_IMFClockRateMatch, a3, 0x10u) )
    {
      Interface = -2147467262;
      if ( !v11 )
      {
        v60 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v58, v57, v59);
        CallStackTracing::s_wpInstance = v60;
        if ( v60 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v60 + 8LL))(v60, 2032) )
        {
          v11 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v11 = &qword_1803CE250;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
        }
      }
      if ( *((_BYTE *)v11 + 8) )
      {
        v61 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v11);
        if ( *((_DWORD *)v61 + 499) != -2147467262 )
          CallStackContext::TraceFailure(v61, "CAudStreamSink::GetService", 675, -2147467262);
      }
      if ( !g_wppLevels )
        goto LABEL_189;
      v29 = 54;
      goto LABEL_39;
    }
    if ( (unsigned __int8)byte_1803CECE9 >= 0x10u )
      WPP_SF_q(
        *((_QWORD *)WPP_GLOBAL_Control + 7),
        55,
        &WPP_8e6dbb68bb473dec012b49037e0fe992_Traceguids,
        (char *)this - 616);
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this - 352));
    if ( !*((_DWORD *)v20 + 210) )
    {
      v63 = *((_DWORD *)this + 1659);
      *((_DWORD *)this + 1659) = 1;
      *((_DWORD *)this + 56) = 1;
      if ( *((_QWORD *)this + 23) )
      {
        if ( *((_DWORD *)this + 1645) )
        {
          if ( (unsigned __int8)byte_1803CECE9 >= 0x10u )
            WPP_SF_q(
              *((_QWORD *)WPP_GLOBAL_Control + 7),
              60,
              &WPP_8e6dbb68bb473dec012b49037e0fe992_Traceguids,
              (char *)this - 616);
          Interface = CAudStreamSink::QueueAudioSessionChangedEvent((char *)this - 616, v62, 8, 1);
          if ( Interface < 0 )
          {
            *((_DWORD *)this + 1659) = v63;
            v81 = (__int64 *)CallStackTracing::s_wpInstance;
            *((_DWORD *)this + 56) = 0;
            if ( !v81 )
            {
              v82 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v79, v78, v80);
              CallStackTracing::s_wpInstance = v82;
              if ( v82
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v82 + 8LL))(v82, 2032) )
              {
                v81 = (__int64 *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v81 = &qword_1803CE250;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
              }
            }
            if ( *((_BYTE *)v81 + 8) )
            {
              v83 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v81);
              if ( *((_DWORD *)v83 + 499) != Interface )
                CallStackContext::TraceFailure(v83, "CAudStreamSink::GetService", 717, Interface);
            }
            if ( g_wppLevels )
              WPP_SF_qD(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                61,
                &WPP_8e6dbb68bb473dec012b49037e0fe992_Traceguids,
                (char *)this - 616,
                Interface);
            goto LABEL_133;
          }
        }
        else
        {
          v64 = (struct IMFAttributes *)*((_QWORD *)this - 72);
          v97[0] = v64;
          if ( v64 )
            ((void (__fastcall *)(struct IMFAttributes *))v64->lpVtbl->AddRef)(v64);
          if ( (unsigned __int8)byte_1803CECE9 >= 0x10u )
            WPP_SF_q(
              *((_QWORD *)WPP_GLOBAL_Control + 7),
              56,
              &WPP_8e6dbb68bb473dec012b49037e0fe992_Traceguids,
              (char *)this - 616);
          Interface = CAudStreamSink::DoInvalidateAudEngineStream((CAudStreamSink *)((char *)this - 616), 0xFFFFFFu, 1);
          if ( Interface < 0 )
          {
            v68 = (__int64 *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v69 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v66, v65, v67);
              CallStackTracing::s_wpInstance = v69;
              if ( v69
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v69 + 8LL))(v69, 2032) )
              {
                v68 = (__int64 *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v68 = &qword_1803CE250;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
              }
            }
            if ( *((_BYTE *)v68 + 8) )
            {
              v70 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v68);
              if ( *((_DWORD *)v70 + 499) != Interface )
                CallStackContext::TraceFailure(v70, "CAudStreamSink::GetService", 701, Interface);
            }
            if ( !g_wppLevels )
              goto LABEL_132;
            v71 = 57;
LABEL_131:
            WPP_SF_qD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              v71,
              &WPP_8e6dbb68bb473dec012b49037e0fe992_Traceguids,
              (char *)this - 616,
              Interface);
LABEL_132:
            ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(v97);
LABEL_133:
            LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this - 352));
            goto LABEL_189;
          }
          if ( (unsigned __int8)byte_1803CECE9 >= 0x10u )
            WPP_SF_q(
              *((_QWORD *)WPP_GLOBAL_Control + 7),
              58,
              &WPP_8e6dbb68bb473dec012b49037e0fe992_Traceguids,
              (char *)this - 616);
          Interface = CAudStreamSink::SetMediaType((CAudStreamSink *)((char *)this - 584), v64);
          if ( Interface < 0 )
          {
            v75 = (__int64 *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v76 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v73, v72, v74);
              CallStackTracing::s_wpInstance = v76;
              if ( v76
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v76 + 8LL))(v76, 2032) )
              {
                v75 = (__int64 *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v75 = &qword_1803CE250;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
              }
            }
            if ( *((_BYTE *)v75 + 8) )
            {
              v77 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v75);
              if ( *((_DWORD *)v77 + 499) != Interface )
                CallStackContext::TraceFailure(v77, "CAudStreamSink::GetService", 704, Interface);
            }
            if ( !g_wppLevels )
              goto LABEL_132;
            v71 = 59;
            goto LABEL_131;
          }
          ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(v97);
        }
      }
    }
    *a4 = (void *)(((unsigned __int64)this + 32) & ((unsigned __int128)-(__int128)(unsigned __int64)v20 >> 64));
    _InterlockedIncrement((volatile signed __int32 *)v20 + 2);
    goto LABEL_133;
  }
  Interface = -2147467261;
  if ( !v11 )
  {
    v16 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v9, v8, v10);
    CallStackTracing::s_wpInstance = v16;
    if ( v16 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v16 + 8LL))(v16, 2032) )
    {
      v11 = (__int64 *)CallStackTracing::s_wpInstance;
    }
    else
    {
      v11 = &qword_1803CE250;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
    }
  }
  if ( *((_BYTE *)v11 + 8) )
  {
    v17 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v11);
    if ( *((_DWORD *)v17 + 499) != -2147467261 )
      CallStackContext::TraceFailure(v17, "CAudStreamSink::GetService", 612, -2147467261);
  }
  if ( g_wppLevels )
  {
    v18 = (char *)this - 616;
    v19 = 46;
LABEL_188:
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v19,
      &WPP_8e6dbb68bb473dec012b49037e0fe992_Traceguids,
      v18,
      Interface);
  }
LABEL_189:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v96);
  return (unsigned int)Interface;
}

```

## disassembly

```asm
0x1800e2590  push    rbx
0x1800e2592  push    rbp
0x1800e2593  push    rsi
0x1800e2594  push    rdi
0x1800e2595  push    r12
0x1800e2597  push    r13
0x1800e2599  push    r14
0x1800e259b  push    r15
0x1800e259d  sub     rsp, 58h
0x1800e25a1  mov     rax, cs:__security_cookie
0x1800e25a8  xor     rax, rsp
0x1800e25ab  mov     [rsp+98h+var_50], rax
0x1800e25b0  mov     r15, r8
0x1800e25b3  mov     r12, rdx
0x1800e25b6  mov     rbp, rcx
0x1800e25b9  lea     rdx, aCaudstreamsink_49; "CAudStreamSink::GetService"
0x1800e25c0  mov     r8d, 260h; int
0x1800e25c6  lea     rcx, [rsp+98h+var_68]; this
0x1800e25cb  mov     r14, r9
0x1800e25ce  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800e25d3  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800e25da  xor     r13d, r13d
0x1800e25dd  cmp     [rbx+8], r13b
0x1800e25e1  jz      short loc_1800E2644
0x1800e25e3  cmp     [rbp+1760h], r13
0x1800e25ea  jz      short loc_1800E2644
0x1800e25ec  mov     rcx, rbx; this
0x1800e25ef  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800e25f4  mov     rcx, [rbp+1760h]
0x1800e25fb  mov     rdi, rax
0x1800e25fe  mov     rdx, [rcx]
0x1800e2601  mov     rax, [rdx+128h]
0x1800e2608  call    cs:__guard_dispatch_icall_fptr
0x1800e260e  mov     rcx, [rbp+1760h]
0x1800e2615  mov     ebx, eax
0x1800e2617  mov     rdx, [rcx]
0x1800e261a  mov     rax, [rdx+118h]
0x1800e2621  lea     rdx, [rsp+98h+var_60]
0x1800e2626  call    cs:__guard_dispatch_icall_fptr
0x1800e262c  movups  xmm0, xmmword ptr [rax]
0x1800e262f  mov     [rdi+7E0h], ebx
0x1800e2635  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800e263c  movdqu  xmmword ptr [rdi+7D0h], xmm0
0x1800e2644  test    r14, r14
0x1800e2647  jnz     loc_1800E26EB
0x1800e264d  mov     edi, 80004003h
0x1800e2652  test    rbx, rbx
0x1800e2655  jnz     short loc_1800E269F
0x1800e2657  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800e265e  nop     dword ptr [rax+rax+00h]
0x1800e2663  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800e266a  mov     rcx, rax
0x1800e266d  test    rax, rax
0x1800e2670  jz      short loc_1800E2691
0x1800e2672  mov     rax, [rax]
0x1800e2675  mov     edx, 7F0h
0x1800e267a  mov     rax, [rax+8]
0x1800e267e  call    cs:__guard_dispatch_icall_fptr
0x1800e2684  test    eax, eax
0x1800e2686  jz      short loc_1800E2691
0x1800e2688  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800e268f  jmp     short loc_1800E269F
0x1800e2691  lea     rbx, qword_1803CE250
0x1800e2698  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rbx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800e269f  cmp     [rbx+8], r13b
0x1800e26a3  jz      short loc_1800E26CD
0x1800e26a5  mov     rcx, rbx; this
0x1800e26a8  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800e26ad  cmp     [rax+7CCh], edi
0x1800e26b3  jz      short loc_1800E26CD
0x1800e26b5  mov     r9d, edi; int
0x1800e26b8  lea     rdx, aCaudstreamsink_49; "CAudStreamSink::GetService"
0x1800e26bf  mov     r8d, 264h; int
0x1800e26c5  mov     rcx, rax; this
0x1800e26c8  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800e26cd  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800e26d4  jb      loc_1800E3290
0x1800e26da  lea     r9, [rbp-268h]
0x1800e26e1  mov     edx, 2Eh ; '.'
0x1800e26e6  jmp     loc_1800E3275
0x1800e26eb  lea     rsi, [rbp-268h]
0x1800e26f2  cmp     dword ptr [rsi+158h], 7
0x1800e26f9  jnz     loc_1800E2796
0x1800e26ff  mov     edi, 0C00D4A38h
0x1800e2704  test    rbx, rbx
0x1800e2707  jnz     short loc_1800E2751
0x1800e2709  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800e2710  nop     dword ptr [rax+rax+00h]
0x1800e2715  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800e271c  mov     rcx, rax
0x1800e271f  test    rax, rax
0x1800e2722  jz      short loc_1800E2743
0x1800e2724  mov     rax, [rax]
0x1800e2727  mov     edx, 7F0h
0x1800e272c  mov     rax, [rax+8]
0x1800e2730  call    cs:__guard_dispatch_icall_fptr
0x1800e2736  test    eax, eax
0x1800e2738  jz      short loc_1800E2743
0x1800e273a  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800e2741  jmp     short loc_1800E2751
0x1800e2743  lea     rbx, qword_1803CE250
0x1800e274a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rbx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800e2751  cmp     [rbx+8], r13b
0x1800e2755  jz      short loc_1800E277F
0x1800e2757  mov     rcx, rbx; this
0x1800e275a  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800e275f  cmp     [rax+7CCh], edi
0x1800e2765  jz      short loc_1800E277F
0x1800e2767  mov     r9d, edi; int
0x1800e276a  lea     rdx, aCaudstreamsink_49; "CAudStreamSink::GetService"
0x1800e2771  mov     r8d, 268h; int
0x1800e2777  mov     rcx, rax; this
0x1800e277a  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800e277f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800e2786  jb      loc_1800E3290
0x1800e278c  mov     edx, 2Fh ; '/'
0x1800e2791  jmp     loc_1800E3272
0x1800e2796  mov     r8d, 10h; Size
0x1800e279c  mov     [r14], r13
0x1800e279f  mov     rdx, r12; Buf2
0x1800e27a2  lea     rcx, MR_POLICY_VOLUME_SERVICE; Buf1
0x1800e27a9  mov     edi, r13d
0x1800e27ac  call    memcmp_0
0x1800e27b1  mov     r8d, 10h; Size
0x1800e27b7  test    eax, eax
0x1800e27b9  jnz     loc_1800E287E
0x1800e27bf  mov     rdx, r15; Buf2
0x1800e27c2  lea     rcx, IID_IMFSimpleAudioVolume; Buf1
0x1800e27c9  call    memcmp_0
0x1800e27ce  test    eax, eax
0x1800e27d0  jnz     short loc_1800E27DE
0x1800e27d2  lea     rcx, [rbp-100h]
0x1800e27d9  jmp     loc_1800E30F7
0x1800e27de  mov     ebp, 80004002h
0x1800e27e3  mov     edi, ebp
0x1800e27e5  test    rbx, rbx
0x1800e27e8  jnz     short loc_1800E2832
0x1800e27ea  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800e27f1  nop     dword ptr [rax+rax+00h]
0x1800e27f6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800e27fd  mov     rcx, rax
0x1800e2800  test    rax, rax
0x1800e2803  jz      short loc_1800E2824
0x1800e2805  mov     rax, [rax]
0x1800e2808  mov     edx, 7F0h
0x1800e280d  mov     rax, [rax+8]
0x1800e2811  call    cs:__guard_dispatch_icall_fptr
0x1800e2817  test    eax, eax
0x1800e2819  jz      short loc_1800E2824
0x1800e281b  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800e2822  jmp     short loc_1800E2832
0x1800e2824  lea     rbx, qword_1803CE250
0x1800e282b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rbx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800e2832  cmp     [rbx+8], r13b
0x1800e2836  jz      short loc_1800E2860
0x1800e2838  mov     rcx, rbx; this
0x1800e283b  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800e2840  cmp     [rax+7CCh], ebp
0x1800e2846  jz      short loc_1800E2860
0x1800e2848  mov     r9d, ebp; int
0x1800e284b  lea     rdx, aCaudstreamsink_49; "CAudStreamSink::GetService"
0x1800e2852  mov     r8d, 278h; int
0x1800e2858  mov     rcx, rax; this
0x1800e285b  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800e2860  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800e2867  jb      loc_1800E3290
0x1800e286d  mov     edx, 30h ; '0'
0x1800e2872  mov     [rsp+98h+var_78], ebp
0x1800e2876  mov     r9, rsi
0x1800e2879  jmp     loc_1800E3279
0x1800e287e  mov     rdx, r12; Buf2
0x1800e2881  lea     rcx, MR_STREAM_VOLUME_SERVICE; Buf1
0x1800e2888  call    memcmp_0
0x1800e288d  mov     r8d, 10h; Size
0x1800e2893  test    eax, eax
0x1800e2895  jnz     loc_1800E2953
0x1800e289b  mov     rdx, r15; Buf2
0x1800e289e  lea     rcx, IID_IMFAudioStreamVolume; Buf1
0x1800e28a5  call    memcmp_0
0x1800e28aa  test    eax, eax
0x1800e28ac  jnz     short loc_1800E28BA
0x1800e28ae  lea     rcx, [rbp-0F8h]
0x1800e28b5  jmp     loc_1800E30F7
0x1800e28ba  mov     ebp, 80004002h
0x1800e28bf  mov     edi, ebp
0x1800e28c1  test    rbx, rbx
0x1800e28c4  jnz     short loc_1800E290E
0x1800e28c6  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800e28cd  nop     dword ptr [rax+rax+00h]
0x1800e28d2  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800e28d9  mov     rcx, rax
0x1800e28dc  test    rax, rax
0x1800e28df  jz      short loc_1800E2900
0x1800e28e1  mov     rax, [rax]
0x1800e28e4  mov     edx, 7F0h
0x1800e28e9  mov     rax, [rax+8]
0x1800e28ed  call    cs:__guard_dispatch_icall_fptr
0x1800e28f3  test    eax, eax
0x1800e28f5  jz      short loc_1800E2900
0x1800e28f7  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800e28fe  jmp     short loc_1800E290E
0x1800e2900  lea     rbx, qword_1803CE250
0x1800e2907  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rbx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800e290e  cmp     [rbx+8], r13b
0x1800e2912  jz      short loc_1800E293C
0x1800e2914  mov     rcx, rbx; this
0x1800e2917  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800e291c  cmp     [rax+7CCh], ebp
0x1800e2922  jz      short loc_1800E293C
0x1800e2924  mov     r9d, ebp; int
0x1800e2927  lea     rdx, aCaudstreamsink_49; "CAudStreamSink::GetService"
0x1800e292e  mov     r8d, 284h; int
0x1800e2934  mov     rcx, rax; this
0x1800e2937  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800e293c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800e2943  jb      loc_1800E3290
0x1800e2949  mov     edx, 31h ; '1'
0x1800e294e  jmp     loc_1800E2872
0x1800e2953  mov     rdx, r12; Buf2
0x1800e2956  lea     rcx, MF_RATE_CONTROL_SERVICE; Buf1
0x1800e295d  call    memcmp_0
0x1800e2962  mov     r8d, 10h; Size
0x1800e2968  mov     rdx, r15; Buf2
0x1800e296b  test    eax, eax
0x1800e296d  jnz     loc_1800E2AD1
0x1800e2973  lea     rcx, IID_IMFRateSupport; Buf1
0x1800e297a  call    memcmp_0
0x1800e297f  test    eax, eax
0x1800e2981  jnz     loc_1800E2A38
0x1800e2987  mov     r8, r14; void **
0x1800e298a  mov     rdx, r15; struct _GUID *
0x1800e298d  mov     rcx, rsi; this
0x1800e2990  call    ?QueryInterface@CAudStreamSink@@UEAAJAEBU_GUID@@PEAPEAX@Z; CAudStreamSink::QueryInterface(_GUID const &,void * *)
0x1800e2995  mov     edi, eax
0x1800e2997  test    eax, eax
0x1800e2999  jns     loc_1800E3290
0x1800e299f  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800e29a6  test    rbx, rbx
0x1800e29a9  jnz     short loc_1800E29F3
0x1800e29ab  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800e29b2  nop     dword ptr [rax+rax+00h]
0x1800e29b7  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800e29be  mov     rcx, rax
0x1800e29c1  test    rax, rax
0x1800e29c4  jz      short loc_1800E29E5
0x1800e29c6  mov     rax, [rax]
0x1800e29c9  mov     edx, 7F0h
0x1800e29ce  mov     rax, [rax+8]
0x1800e29d2  call    cs:__guard_dispatch_icall_fptr
0x1800e29d8  test    eax, eax
0x1800e29da  jz      short loc_1800E29E5
0x1800e29dc  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800e29e3  jmp     short loc_1800E29F3
0x1800e29e5  lea     rbx, qword_1803CE250
0x1800e29ec  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rbx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800e29f3  cmp     [rbx+8], r13b
0x1800e29f7  jz      short loc_1800E2A21
0x1800e29f9  mov     rcx, rbx; this
0x1800e29fc  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800e2a01  cmp     [rax+7CCh], edi
0x1800e2a07  jz      short loc_1800E2A21
0x1800e2a09  mov     r9d, edi; int
0x1800e2a0c  lea     rdx, aCaudstreamsink_49; "CAudStreamSink::GetService"
0x1800e2a13  mov     r8d, 28Ch; int
0x1800e2a19  mov     rcx, rax; this
0x1800e2a1c  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800e2a21  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800e2a28  jb      loc_1800E3290
0x1800e2a2e  mov     edx, 32h ; '2'
0x1800e2a33  jmp     loc_1800E3272
0x1800e2a38  mov     ebp, 80004002h
0x1800e2a3d  mov     edi, ebp
0x1800e2a3f  test    rbx, rbx
0x1800e2a42  jnz     short loc_1800E2A8C
0x1800e2a44  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800e2a4b  nop     dword ptr [rax+rax+00h]
0x1800e2a50  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800e2a57  mov     rcx, rax
0x1800e2a5a  test    rax, rax
0x1800e2a5d  jz      short loc_1800E2A7E
0x1800e2a5f  mov     rax, [rax]
0x1800e2a62  mov     edx, 7F0h
0x1800e2a67  mov     rax, [rax+8]
0x1800e2a6b  call    cs:__guard_dispatch_icall_fptr
0x1800e2a71  test    eax, eax
0x1800e2a73  jz      short loc_1800E2A7E
0x1800e2a75  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800e2a7c  jmp     short loc_1800E2A8C
0x1800e2a7e  lea     rbx, qword_1803CE250
0x1800e2a85  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rbx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800e2a8c  cmp     [rbx+8], r13b
0x1800e2a90  jz      short loc_1800E2ABA
0x1800e2a92  mov     rcx, rbx; this
0x1800e2a95  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800e2a9a  cmp     [rax+7CCh], ebp
0x1800e2aa0  jz      short loc_1800E2ABA
0x1800e2aa2  mov     r9d, ebp; int
0x1800e2aa5  lea     rdx, aCaudstreamsink_49; "CAudStreamSink::GetService"
0x1800e2aac  mov     r8d, 290h; int
0x1800e2ab2  mov     rcx, rax; this
  ... truncated ...
```
