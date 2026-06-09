# CAudCaptureStream::ReadCaptureBuffer(int)

- ea: `0x180035264`
- end: `0x1800360af`
- name: `?ReadCaptureBuffer@CAudCaptureStream@@QEAAJH@Z`
- size: `3659`
- prototype: `__int64 __fastcall(CAudCaptureStream *__hidden this, int)`
- caller_count: `2`
- callee_count: `19`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180036d6c`
- `0x1802dddb0`

## callees

- `0x18001616c`
- `0x18002fee0`
- `0x180035264`
- `0x1800360b8`
- `0x180036114`
- `0x180036304`
- `0x18003a4a0`
- `0x18003ecb0`
- `0x1800402c0`
- `0x180045dbc`
- `0x180050d6c`
- `0x1800caaac`
- `0x1800ec0e0`
- `0x180153d20`
- `0x1801859e8`
- `0x180189368`
- `0x1802dea5c`
- `0x180344ce4`
- `0x180344d40`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800352d6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800352d6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800352c0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800352c0`
- `MFPlat!MFCreateMemoryBuffer` at `0x18003536b`
- `MFPlat!MFCreateMemoryBuffer` at `0x18003536b`
- `MFPlat!MFllMulDiv` at `0x180035584`
- `MFPlat!MFllMulDiv` at `0x180035584`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180035489`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800356be`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003585b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003590d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800359e9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180035a84`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180035b4d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180035be8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180035c83`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180035d5f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180035dfa`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180035e92`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180035489`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800356be`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003585b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003590d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800359e9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180035a84`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180035b4d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180035be8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180035c83`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180035d5f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180035dfa`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180035e92`

## string_xrefs

- `0x180035284`: `CAudCaptureStream::ReadCaptureBuffer`
- `0x180035835`: `CAudCaptureStream::ReadCaptureBuffer`
- `0x1800358ea`: `CAudCaptureStream::ReadCaptureBuffer`
- `0x180035982`: `CAudCaptureStream::ReadCaptureBuffer`
- `0x1800359c0`: `CAudCaptureStream::ReadCaptureBuffer`
- `0x180035a5e`: `CAudCaptureStream::ReadCaptureBuffer`
- `0x180035af9`: `CAudCaptureStream::ReadCaptureBuffer`
- `0x180035b24`: `CAudCaptureStream::ReadCaptureBuffer`
- `0x180035bc2`: `CAudCaptureStream::ReadCaptureBuffer`
- `0x180035c5d`: `CAudCaptureStream::ReadCaptureBuffer`
- `0x180035cf8`: `CAudCaptureStream::ReadCaptureBuffer`
- `0x180035d36`: `CAudCaptureStream::ReadCaptureBuffer`
- `0x180035dd4`: `CAudCaptureStream::ReadCaptureBuffer`
- `0x180035e6f`: `CAudCaptureStream::ReadCaptureBuffer`
- `0x180035f20`: `CAudCaptureStream::ReadCaptureBuffer`

## pseudocode

```c
__int64 __fastcall CAudCaptureStream::ReadCaptureBuffer(CAudCaptureStream *this, unsigned int a2)
{
  __int64 v4; // rcx
  __int64 v5; // r12
  unsigned int v6; // r14d
  int v7; // r15d
  int v8; // eax
  HRESULT v9; // ebx
  DWORD v10; // ecx
  __int64 v11; // rdx
  __int64 v12; // r8
  __int64 v13; // rdx
  __int64 v14; // r8
  char v15; // r15
  unsigned int v16; // r14d
  __int64 v17; // rdx
  __int64 v18; // r8
  __int64 v19; // rdx
  __int64 v20; // r8
  __int64 *v21; // rcx
  CallStackTracing *v22; // rax
  __int64 v23; // rdx
  __int64 v24; // rdx
  __int64 v25; // r8
  __int64 v26; // rdx
  __int64 v27; // r8
  __int64 v28; // rdx
  __int64 v29; // r8
  __int64 v30; // rdx
  __int64 v31; // r8
  LONGLONG v32; // r12
  __int64 v33; // rdx
  int v34; // ecx
  __int64 v35; // r8
  __int64 v36; // rdx
  __int64 v37; // r8
  __int64 v38; // rcx
  HRESULT v39; // eax
  IMFMediaBuffer *v40; // rcx
  __int64 v42; // rdx
  __int64 v43; // r8
  __int64 *v44; // rcx
  CallStackTracing *v45; // rax
  __int64 v46; // rdx
  CallStackTracing *v47; // rcx
  CallStackTracing *v48; // rcx
  __int64 v49; // rdx
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 *v51; // rcx
  CallStackTracing *v52; // rax
  struct CallStackContext *v53; // rax
  __int64 *v54; // rcx
  CallStackTracing *v55; // rax
  struct CallStackContext *v56; // rax
  struct CallStackContext *v57; // rax
  __int64 *v58; // rcx
  CallStackTracing *v59; // rax
  struct CallStackContext *v60; // rax
  __int64 *v61; // rcx
  CallStackTracing *v62; // rax
  struct CallStackContext *v63; // rax
  struct CallStackContext *v64; // rax
  __int64 *v65; // rcx
  CallStackTracing *v66; // rax
  struct CallStackContext *v67; // rax
  __int64 *v68; // rcx
  CallStackTracing *v69; // rax
  struct CallStackContext *v70; // rax
  __int64 *v71; // rcx
  CallStackTracing *v72; // rax
  struct CallStackContext *v73; // rax
  struct CallStackContext *v74; // rax
  __int64 *v75; // rcx
  CallStackTracing *v76; // rax
  struct CallStackContext *v77; // rax
  __int64 *v78; // rcx
  CallStackTracing *v79; // rax
  struct CallStackContext *v80; // rax
  __int64 *v81; // rcx
  CallStackTracing *v82; // rax
  struct CallStackContext *v83; // rax
  __int64 v84; // r8
  int v85; // [rsp+40h] [rbp-40h] BYREF
  int v86; // [rsp+44h] [rbp-3Ch] BYREF
  IMFMediaBuffer *ppBuffer; // [rsp+48h] [rbp-38h] BYREF
  struct IMFSample *v88; // [rsp+50h] [rbp-30h] BYREF
  __int64 v89; // [rsp+58h] [rbp-28h] BYREF
  __int64 v90; // [rsp+60h] [rbp-20h] BYREF
  void *Src; // [rsp+68h] [rbp-18h] BYREF
  __int64 v92; // [rsp+70h] [rbp-10h] BYREF
  int v93; // [rsp+C0h] [rbp+40h] BYREF
  unsigned int v94; // [rsp+D0h] [rbp+50h] BYREF
  int v95; // [rsp+D8h] [rbp+58h] BYREF

  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v93, "CAudCaptureStream::ReadCaptureBuffer", 1097);
  v5 = 0;
  ppBuffer = 0;
  v88 = 0;
  v94 = 0;
  if ( (Microsoft_Windows_MediaFoundation_Performance_CoreEnableBits & 1) != 0 )
    McTemplateU0pd_EventWriteTransfer(v4, &AudCaptureStream_ReadCaptureBuffer_Enter, this, a2);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 656));
  v6 = *((_DWORD *)this + 174);
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 656));
  if ( v6 > 0x14 )
  {
    v9 = 0;
    if ( (unsigned __int8)byte_1803CECED >= 0x20u )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 27), 88, &WPP_a3161aeae109384f3fa1a92793044c0c_Traceguids, v6);
    goto LABEL_187;
  }
  v7 = 1;
  v8 = (*(__int64 (__fastcall **)(_QWORD, unsigned int *))(**((_QWORD **)this + 8) + 48LL))(*((_QWORD *)this + 8), &v94);
  v9 = TranslateError_WASAPIToMFCapture(v8);
  if ( v9 < 0 )
  {
    v48 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::InitInstance();
      v48 = CallStackTracing::s_wpInstance;
    }
    if ( *((_BYTE *)v48 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(v48);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != v9 )
        CallStackContext::TraceFailure(ThreadRelativeContext, "CAudCaptureStream::ReadCaptureBuffer", 1122, v9);
    }
    if ( !g_wppLevels )
      goto LABEL_62;
    v49 = 89;
LABEL_81:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v49, &WPP_a3161aeae109384f3fa1a92793044c0c_Traceguids, this, v9);
    goto LABEL_62;
  }
  if ( (unsigned __int8)byte_1803CECED >= 0x20u )
    WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 27), 90, &WPP_a3161aeae109384f3fa1a92793044c0c_Traceguids, v94, v6);
  if ( (Microsoft_Windows_MediaFoundation_Performance_CoreEnableBits & 1) != 0 )
    McTemplateU0pqq_EventWriteTransfer(
      (unsigned int)&Microsoft_Windows_MediaFoundation_Performance_Core_Context,
      (unsigned int)&AudCaptureStream_ReadCaptureBuffer_CurrentPadding,
      (_DWORD)this,
      v94,
      v6);
  if ( !v94 )
    goto LABEL_187;
  v10 = *((_DWORD *)this + 43) * v94;
  v90 = 0;
  Src = 0;
  v86 = 0;
  v95 = 0;
  v85 = 0;
  v92 = 0;
  v89 = 0;
  v9 = MFCreateMemoryBuffer(v10, &ppBuffer);
  if ( v9 < 0 )
  {
    v51 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v52 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v11, v12);
      CallStackTracing::s_wpInstance = v52;
      if ( v52 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v52 + 8LL))(v52, 2032) )
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
      if ( *((_DWORD *)v53 + 499) != v9 )
        CallStackContext::TraceFailure(v53, "CAudCaptureStream::ReadCaptureBuffer", 1143, v9);
    }
    if ( !g_wppLevels )
      goto LABEL_62;
    v49 = 91;
    goto LABEL_81;
  }
  v9 = ((__int64 (__fastcall *)(IMFMediaBuffer *, __int64 *, _QWORD, _QWORD))ppBuffer->lpVtbl->Lock)(
         ppBuffer,
         &v90,
         0,
         0);
  if ( v9 < 0 )
  {
    v54 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v55 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v13, v14);
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
      if ( *((_DWORD *)v56 + 499) != v9 )
        CallStackContext::TraceFailure(v56, "CAudCaptureStream::ReadCaptureBuffer", 1144, v9);
    }
    if ( !g_wppLevels )
      goto LABEL_62;
    v49 = 92;
    goto LABEL_81;
  }
  v15 = 0;
  v93 = 1;
  v16 = 0;
  while ( 1 )
  {
    if ( v16 >= v94 )
      goto LABEL_29;
    v9 = (*(__int64 (__fastcall **)(_QWORD, int *))(**((_QWORD **)this + 7) + 40LL))(*((_QWORD *)this + 7), &v86);
    if ( v9 < 0 )
    {
      v47 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::InitInstance();
        v47 = CallStackTracing::s_wpInstance;
      }
      if ( *((_BYTE *)v47 + 8) )
      {
        v64 = CallStackTracing::GetThreadRelativeContext(v47);
        if ( *((_DWORD *)v64 + 499) != v9 )
          CallStackContext::TraceFailure(v64, "CAudCaptureStream::ReadCaptureBuffer", 1148, v9);
      }
      if ( !g_wppLevels )
        goto LABEL_61;
      v23 = 93;
      goto LABEL_190;
    }
    v9 = (*(__int64 (__fastcall **)(_QWORD, void **, int *, int *, __int64 *, __int64 *))(**((_QWORD **)this + 7) + 24LL))(
           *((_QWORD *)this + 7),
           &Src,
           &v95,
           &v85,
           &v92,
           &v89);
    if ( v9 < 0 )
    {
      v61 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v62 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v17, v18);
        CallStackTracing::s_wpInstance = v62;
        if ( v62 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v62 + 8LL))(v62, 2032) )
        {
          v61 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v61 = &qword_1803CE250;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
        }
      }
      if ( *((_BYTE *)v61 + 8) )
      {
        v63 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v61);
        if ( *((_DWORD *)v63 + 499) != v9 )
          CallStackContext::TraceFailure(v63, "CAudCaptureStream::ReadCaptureBuffer", 1151, v9);
      }
      if ( !g_wppLevels )
        goto LABEL_61;
      v23 = 94;
      goto LABEL_190;
    }
    if ( (Microsoft_Windows_MediaFoundation_Performance_CoreEnableBits & 1) != 0 )
      McTemplateU0pqqq_EventWriteTransfer(
        (unsigned int)&Microsoft_Windows_MediaFoundation_Performance_Core_Context,
        (unsigned int)&AudCaptureStream_ReadCaptureBuffer_GetBuffer,
        (_DWORD)this,
        v16,
        v95,
        v85);
    if ( !v16 )
    {
      v15 = v85;
      if ( (v85 & 4) != 0 )
      {
        v5 = *((_QWORD *)this + 22);
      }
      else
      {
        v5 = v89;
        *((_QWORD *)this + 22) = v89;
      }
    }
    if ( v16 + v95 > v94 )
      break;
    memcpy_0((void *)(v90 + v16 * *((_DWORD *)this + 43)), Src, (unsigned int)(v95 * *((_DWORD *)this + 43)));
    v16 += v95;
    v9 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 7) + 32LL))(*((_QWORD *)this + 7));
    if ( v9 < 0 )
    {
      v21 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v22 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v19, v20);
        CallStackTracing::s_wpInstance = v22;
        if ( v22 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v22 + 8LL))(v22, 2032) )
        {
          v21 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v21 = &qword_1803CE250;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
        }
      }
      if ( *((_BYTE *)v21 + 8) )
      {
        v57 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v21);
        if ( *((_DWORD *)v57 + 499) != v9 )
          CallStackContext::TraceFailure(v57, "CAudCaptureStream::ReadCaptureBuffer", 1172, v9);
      }
      if ( !g_wppLevels )
        goto LABEL_61;
      v23 = 95;
LABEL_190:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v23, &WPP_a3161aeae109384f3fa1a92793044c0c_Traceguids, this, v9);
LABEL_61:
      v7 = v93;
      goto LABEL_62;
    }
  }
  v9 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 7) + 32LL))(*((_QWORD *)this + 7), 0);
  if ( v9 < 0 )
  {
    v58 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v59 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v24, v25);
      CallStackTracing::s_wpInstance = v59;
      if ( v59 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v59 + 8LL))(v59, 2032) )
      {
        v58 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v58 = &qword_1803CE250;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
      }
    }
    if ( *((_BYTE *)v58 + 8) )
    {
      v60 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v58);
      if ( *((_DWORD *)v60 + 499) != v9 )
        CallStackContext::TraceFailure(v60, "CAudCaptureStream::ReadCaptureBuffer", 1176, v9);
    }
    if ( !g_wppLevels )
      goto LABEL_61;
    v23 = 96;
    goto LABEL_190;
  }
LABEL_29:
  v93 = 0;
  v9 = ((__int64 (__fastcall *)(IMFMediaBuffer *))ppBuffer->lpVtbl->Unlock)(ppBuffer);
  if ( v9 < 0 )
  {
    v65 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v66 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v26, v27);
      CallStackTracing::s_wpInstance = v66;
      if ( v66 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v66 + 8LL))(v66, 2032) )
      {
        v65 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v65 = &qword_1803CE250;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
      }
    }
    if ( *((_BYTE *)v65 + 8) )
    {
      v67 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v65);
      if ( *((_DWORD *)v67 + 499) != v9 )
        CallStackContext::TraceFailure(v67, "CAudCaptureStream::ReadCaptureBuffer", 1181, v9);
    }
    if ( !g_wppLevels )
      goto LABEL_181;
    v46 = 97;
    goto LABEL_180;
  }
  v9 = ((__int64 (__fastcall *)(IMFMediaBuffer *, _QWORD))ppBuffer->lpVtbl->SetCurrentLength)(
         ppBuffer,
         *((_DWORD *)this + 43) * v16);
  if ( v9 < 0 )
  {
    v68 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v69 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v28, v29);
      CallStackTracing::s_wpInstance = v69;
      if ( v69 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v69 + 8LL))(v69, 2032) )
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
      if ( *((_DWORD *)v70 + 499) != v9 )
        CallStackContext::TraceFailure(v70, "CAudCaptureStream::ReadCaptureBuffer", 1183, v9);
    }
    if ( !g_wppLevels )
      goto LABEL_181;
    v46 = 98;
    goto LABEL_180;
  }
  v9 = CAudCaptureStream::CreateSampleForBuffer(this, &v88, ppBuffer);
  if ( v9 < 0 )
  {
    v71 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v72 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v30, v31);
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
      if ( *((_DWORD *)v73 + 499) != v9 )
        CallStackContext::TraceFailure(v73, "CAudCaptureStream::ReadCaptureBuffer", 1184, v9);
    }
    if ( !g_wppLevels )
      goto LABEL_181;
    v46 = 99;
    goto LABEL_180;
  }
  if ( (v15 & 4) != 0
    || (v9 = ((__int64 (__fastcall *)(struct IMFSample *, __int64))v88->lpVtbl->SetSampleTime)(v88, v5), v9 >= 0) )
  {
    v32 = MFllMulDiv(v16, 10000000, *((unsigned int *)this + 39), 0);
    v9 = ((__int64 (__fastcall *)(struct IMFSample *, LONGLONG))v88->lpVtbl->SetSampleDuration)(v88, v32);
    if ( v9 < 0 )
    {
      v75 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v76 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v33, v35);
        CallStackTracing::s_wpInstance = v76;
        if ( v76 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v76 + 8LL))(v76, 2032) )
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
        if ( *((_DWORD *)v77 + 499) != v9 )
          CallStackContext::TraceFailure(v77, "CAudCaptureStream::ReadCaptureBuffer", 1191, v9);
      }
      if ( !g_wppLevels )
        goto LABEL_181;
      v46 = 101;
    }
    else if ( (a2 || (v15 & 5) != 0)
           && (v9 = ((__int64 (__fastcall *)(struct IMFSample *, const GUID *, __int64))v88->lpVtbl->SetUINT32)(
                      v88,
                      &MFSampleExtension_Discontinuity,
                      1),
               v9 < 0) )
    {
      v78 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v79 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v33, v84);
        CallStackTracing::s_wpInstance = v79;
        if ( v79 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v79 + 8LL))(v79, 2032) )
        {
          v78 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v78 = &qword_1803CE250;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
        }
      }
      if ( *((_BYTE *)v78 + 8) )
      {
        v80 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v78);
        if ( *((_DWORD *)v80 + 499) != v9 )
          CallStackContext::TraceFailure(v80, "CAudCaptureStream::ReadCaptureBuffer", 1196, v9);
      }
      if ( !g_wppLevels )
        goto LABEL_181;
      v46 = 102;
    }
    else
    {
      if ( (Microsoft_Windows_MediaFoundation_Performance_CoreEnableBits & 1) != 0 )
        McTemplateU0pqxxq_EventWriteTransfer(v34, v33, (_DWORD)this, v16, *((_QWORD *)this + 22), v32, v15);
      v9 = CAudCaptureStream::AddSample(this, v88);
      if ( v9 >= 0 )
      {
        v38 = *((_QWORD *)this + 25) + 112LL;
        v88 = 0;
        v39 = (*(__int64 (__fastcall **)(__int64, __int64, GUID *, _QWORD, _QWORD))(*(_QWORD *)v38 + 48LL))(
                v38,
                602,
                &GUID_00000000_0000_0000_0000_000000000000,
                0,
                0);
        v40 = ppBuffer;
        v9 = v39;
        if ( ppBuffer )
        {
          ((void (__fastcall *)(IMFMediaBuffer *))ppBuffer->lpVtbl->Release)(ppBuffer);
          v40 = 0;
          ppBuffer = 0;
        }
        if ( v9 < 0 )
          goto LABEL_181;
LABEL_42:
        if ( v40 )
        {
          ((void (__fastcall *)(IMFMediaBuffer *))v40->lpVtbl->Release)(v40);
          ppBuffer = 0;
        }
        goto LABEL_44;
      }
      v81 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v82 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v36, v37);
        CallStackTracing::s_wpInstance = v82;
        if ( v82 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v82 + 8LL))(v82, 2032) )
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
        if ( *((_DWORD *)v83 + 499) != v9 )
          CallStackContext::TraceFailure(v83, "CAudCaptureStream::ReadCaptureBuffer", 1209, v9);
      }
      if ( !g_wppLevels )
        goto LABEL_181;
      v46 = 104;
    }
LABEL_180:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v46, &WPP_a3161aeae109384f3fa1a92793044c0c_Traceguids, this, v9);
    goto LABEL_181;
  }
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
    v74 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v44);
    if ( *((_DWORD *)v74 + 499) != v9 )
      CallStackContext::TraceFailure(v74, "CAudCaptureStream::ReadCaptureBuffer", 1188, v9);
  }
  if ( g_wppLevels )
  {
    v46 = 100;
    goto LABEL_180;
  }
LABEL_181:
  v7 = 0;
LABEL_62:
  (*(void (__fastcall **)(__int64, __int64, GUID *, _QWORD, _QWORD))(*(_QWORD *)(*((_QWORD *)this + 25) + 112LL) + 48LL))(
    *((_QWORD *)this + 25) + 112LL,
    1,
    &GUID_00000000_0000_0000_0000_000000000000,
    (unsigned int)v9,
    0);
  if ( !v7 )
  {
LABEL_63:
    v40 = ppBuffer;
    goto LABEL_42;
  }
LABEL_187:
  if ( ppBuffer )
  {
    ((void (__fastcall *)(IMFMediaBuffer *))ppBuffer->lpVtbl->Unlock)(ppBuffer);
    goto LABEL_63;
  }
LABEL_44:
  if ( v88 )
  {
    ((void (__fastcall *)(struct IMFSample *))v88->lpVtbl->Release)(v88);
    v88 = 0;
  }
  if ( (Microsoft_Windows_MediaFoundation_Performance_CoreEnableBits & 1) != 0 )
    McTemplateU0pq_EventWriteTransfer(
      &Microsoft_Windows_MediaFoundation_Performance_Core_Context,
      &AudCaptureStream_ReadCaptureBuffer_Exit,
      this,
      (unsigned int)v9);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v93);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180035264  mov     [rsp-38h+arg_8], rbx
0x180035269  push    rbp
0x18003526a  push    rsi
0x18003526b  push    rdi
0x18003526c  push    r12
0x18003526e  push    r13
0x180035270  push    r14
0x180035272  push    r15
0x180035274  mov     rbp, rsp
0x180035277  sub     rsp, 80h
0x18003527e  mov     r13d, edx
0x180035281  mov     rdi, rcx
0x180035284  lea     rdx, aCaudcapturestr_28; "CAudCaptureStream::ReadCaptureBuffer"
0x18003528b  mov     r8d, 449h; int
0x180035291  lea     rcx, [rbp+arg_0]; this
0x180035295  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18003529a  xor     r12d, r12d
0x18003529d  test    cs:Microsoft_Windows_MediaFoundation_Performance_CoreEnableBits, 1
0x1800352a4  mov     [rbp+ppBuffer], r12
0x1800352a8  mov     [rbp+var_30], r12
0x1800352ac  mov     [rbp+arg_10], r12d
0x1800352b0  jnz     loc_180035F37
0x1800352b6  lea     rbx, [rdi+290h]
0x1800352bd  mov     rcx, rbx; lpCriticalSection
0x1800352c0  call    cs:__imp_EnterCriticalSection
0x1800352c7  nop     dword ptr [rax+rax+00h]
0x1800352cc  mov     r14d, [rdi+2B8h]
0x1800352d3  mov     rcx, rbx; lpCriticalSection
0x1800352d6  call    cs:__imp_LeaveCriticalSection
0x1800352dd  nop     dword ptr [rax+rax+00h]
0x1800352e2  cmp     r14d, 14h
0x1800352e6  ja      loc_180035F4E
0x1800352ec  mov     rcx, [rdi+40h]
0x1800352f0  lea     rdx, [rbp+arg_10]
0x1800352f4  mov     r15d, 1
0x1800352fa  mov     rax, [rcx]
0x1800352fd  mov     rax, [rax+30h]
0x180035301  call    cs:__guard_dispatch_icall_fptr
0x180035307  mov     ecx, eax; int
0x180035309  call    ?TranslateError_WASAPIToMFCapture@@YAJJ@Z; TranslateError_WASAPIToMFCapture(long)
0x18003530e  mov     ebx, eax
0x180035310  test    eax, eax
0x180035312  js      loc_1800357A5
0x180035318  cmp     cs:byte_1803CECED, 20h ; ' '
0x18003531f  lea     rsi, WPP_a3161aeae109384f3fa1a92793044c0c_Traceguids
0x180035326  jnb     loc_1800357D1
0x18003532c  test    cs:Microsoft_Windows_MediaFoundation_Performance_CoreEnableBits, r15b
0x180035333  jnz     loc_180035F9B
0x180035339  mov     ecx, [rbp+arg_10]
0x18003533c  test    ecx, ecx
0x18003533e  jz      loc_180035F7C
0x180035344  imul    ecx, [rdi+0ACh]; cbMaxLength
0x18003534b  lea     rdx, [rbp+ppBuffer]; ppBuffer
0x18003534f  mov     [rbp+var_20], r12
0x180035353  mov     [rbp+Src], r12
0x180035357  mov     [rbp+var_3C], r12d
0x18003535b  mov     [rbp+arg_18], r12d
0x18003535f  mov     [rbp+var_40], r12d
0x180035363  mov     [rbp+var_10], r12
0x180035367  mov     [rbp+var_28], r12
0x18003536b  call    cs:__imp_MFCreateMemoryBuffer
0x180035372  nop     dword ptr [rax+rax+00h]
0x180035377  mov     ebx, eax
0x180035379  test    eax, eax
0x18003537b  js      loc_18003584F
0x180035381  mov     rcx, [rbp+ppBuffer]
0x180035385  lea     rdx, [rbp+var_20]
0x180035389  xor     r9d, r9d
0x18003538c  xor     r8d, r8d
0x18003538f  mov     rax, [rcx]
0x180035392  mov     rax, [rax+18h]
0x180035396  call    cs:__guard_dispatch_icall_fptr
0x18003539c  mov     ebx, eax
0x18003539e  test    eax, eax
0x1800353a0  js      loc_180035901
0x1800353a6  mov     r15d, r12d
0x1800353a9  mov     [rbp+arg_0], 1
0x1800353b0  mov     r14d, r12d
0x1800353b3  cmp     r14d, [rbp+arg_10]
0x1800353b7  jnb     loc_180035507
0x1800353bd  mov     rcx, [rdi+38h]
0x1800353c1  lea     rdx, [rbp+var_3C]
0x1800353c5  mov     rax, [rcx]
0x1800353c8  mov     rax, [rax+28h]
0x1800353cc  call    cs:__guard_dispatch_icall_fptr
0x1800353d2  mov     ebx, eax
0x1800353d4  test    eax, eax
0x1800353d6  js      loc_18003571F
0x1800353dc  mov     rcx, [rdi+38h]
0x1800353e0  lea     rdx, [rbp+var_28]
0x1800353e4  mov     [rsp+80h+var_58], rdx
0x1800353e9  lea     r9, [rbp+var_40]
0x1800353ed  lea     rdx, [rbp+var_10]
0x1800353f1  mov     [rsp+80h+var_60], rdx
0x1800353f6  lea     r8, [rbp+arg_18]
0x1800353fa  mov     rax, [rcx]
0x1800353fd  lea     rdx, [rbp+Src]
0x180035401  mov     rax, [rax+18h]
0x180035405  call    cs:__guard_dispatch_icall_fptr
0x18003540b  mov     ebx, eax
0x18003540d  test    eax, eax
0x18003540f  js      loc_180035A75
0x180035415  test    cs:Microsoft_Windows_MediaFoundation_Performance_CoreEnableBits, 1
0x18003541c  jnz     loc_180035FBF
0x180035422  test    r14d, r14d
0x180035425  jz      loc_18003578B
0x18003542b  mov     edx, [rbp+arg_18]
0x18003542e  lea     eax, [r14+rdx]
0x180035432  cmp     eax, [rbp+arg_10]
0x180035435  ja      loc_1800354EA
0x18003543b  mov     ecx, [rdi+0ACh]
0x180035441  mov     r8d, ecx
0x180035444  imul    ecx, r14d
0x180035448  imul    r8d, edx; Size
0x18003544c  mov     rdx, [rbp+Src]; Src
0x180035450  add     rcx, [rbp+var_20]; void *
0x180035454  call    memcpy_0
0x180035459  mov     rcx, [rdi+38h]
0x18003545d  mov     edx, [rbp+arg_18]
0x180035460  add     r14d, edx
0x180035463  mov     rax, [rcx]
0x180035466  mov     rax, [rax+20h]
0x18003546a  call    cs:__guard_dispatch_icall_fptr
0x180035470  mov     ebx, eax
0x180035472  test    eax, eax
0x180035474  jns     loc_1800353B3
0x18003547a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180035481  xor     r12d, r12d
0x180035484  test    rcx, rcx
0x180035487  jnz     short loc_1800354C9
0x180035489  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180035490  nop     dword ptr [rax+rax+00h]
0x180035495  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18003549c  mov     rcx, rax
0x18003549f  test    rax, rax
0x1800354a2  jz      loc_180035999
0x1800354a8  mov     rax, [rax]
0x1800354ab  mov     edx, 7F0h
0x1800354b0  mov     rax, [rax+8]
0x1800354b4  call    cs:__guard_dispatch_icall_fptr
0x1800354ba  test    eax, eax
0x1800354bc  jz      loc_180035999
0x1800354c2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800354c9  cmp     [rcx+8], r12b
0x1800354cd  jnz     loc_1800359AC
0x1800354d3  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800354da  jb      loc_180035749
0x1800354e0  mov     edx, 5Fh ; '_'
0x1800354e5  jmp     loc_180035FF0
0x1800354ea  mov     rcx, [rdi+38h]
0x1800354ee  xor     edx, edx
0x1800354f0  mov     rax, [rcx]
0x1800354f3  mov     rax, [rax+20h]
0x1800354f7  call    cs:__guard_dispatch_icall_fptr
0x1800354fd  mov     ebx, eax
0x1800354ff  test    eax, eax
0x180035501  js      loc_1800359DA
0x180035507  mov     rcx, [rbp+ppBuffer]
0x18003550b  mov     [rbp+arg_0], 0
0x180035512  mov     rax, [rcx]
0x180035515  mov     rax, [rax+20h]
0x180035519  call    cs:__guard_dispatch_icall_fptr
0x18003551f  mov     ebx, eax
0x180035521  test    eax, eax
0x180035523  js      loc_180035B3E
0x180035529  mov     rcx, [rbp+ppBuffer]
0x18003552d  mov     edx, r14d
0x180035530  imul    edx, [rdi+0ACh]
0x180035537  mov     rax, [rcx]
0x18003553a  mov     rax, [rax+30h]
0x18003553e  call    cs:__guard_dispatch_icall_fptr
0x180035544  mov     ebx, eax
0x180035546  test    eax, eax
0x180035548  js      loc_180035BD9
0x18003554e  mov     r8, [rbp+ppBuffer]; struct IMFMediaBuffer *
0x180035552  lea     rdx, [rbp+var_30]; struct IMFSample **
0x180035556  mov     rcx, rdi; this
0x180035559  call    ?CreateSampleForBuffer@CAudCaptureStream@@IEAAJPEAPEAUIMFSample@@PEAUIMFMediaBuffer@@@Z; CAudCaptureStream::CreateSampleForBuffer(IMFSample * *,IMFMediaBuffer *)
0x18003555e  mov     ebx, eax
0x180035560  test    eax, eax
0x180035562  js      loc_180035C74
0x180035568  test    r15b, 4
0x18003556c  jz      loc_18003568E
0x180035572  mov     r8d, [rdi+9Ch]; c
0x180035579  xor     r9d, r9d; d
0x18003557c  mov     ecx, r14d; a
0x18003557f  mov     edx, 989680h; b
0x180035584  call    cs:__imp_MFllMulDiv
0x18003558b  nop     dword ptr [rax+rax+00h]
0x180035590  mov     rcx, [rbp+var_30]
0x180035594  mov     r12, rax
0x180035597  mov     rdx, [rcx]
0x18003559a  mov     rax, [rdx+130h]
0x1800355a1  mov     rdx, r12
0x1800355a4  call    cs:__guard_dispatch_icall_fptr
0x1800355aa  mov     ebx, eax
0x1800355ac  test    eax, eax
0x1800355ae  js      loc_180035D50
0x1800355b4  test    r13d, r13d
0x1800355b7  jnz     loc_18003600F
0x1800355bd  test    r15b, 5
0x1800355c1  jnz     loc_18003600F
0x1800355c7  test    cs:Microsoft_Windows_MediaFoundation_Performance_CoreEnableBits, 1
0x1800355ce  jnz     loc_18003603F
0x1800355d4  mov     rdx, [rbp+var_30]; struct IMFSample *
0x1800355d8  mov     rcx, rdi; this
0x1800355db  call    ?AddSample@CAudCaptureStream@@IEAAJPEAUIMFSample@@@Z; CAudCaptureStream::AddSample(IMFSample *)
0x1800355e0  xor     r12d, r12d
0x1800355e3  mov     ebx, eax
0x1800355e5  test    eax, eax
0x1800355e7  js      loc_180035E86
0x1800355ed  mov     rcx, [rdi+0C8h]
0x1800355f4  lea     r8, _GUID_00000000_0000_0000_0000_000000000000
0x1800355fb  add     rcx, 70h ; 'p'
0x1800355ff  mov     [rbp+var_30], r12
0x180035603  xor     r9d, r9d
0x180035606  mov     [rsp+80h+var_60], r12
0x18003560b  mov     edx, 25Ah
0x180035610  mov     rax, [rcx]
0x180035613  mov     rax, [rax+30h]
0x180035617  call    cs:__guard_dispatch_icall_fptr
0x18003561d  mov     rcx, [rbp+ppBuffer]
0x180035621  mov     ebx, eax
0x180035623  test    rcx, rcx
0x180035626  jz      short loc_18003563C
0x180035628  mov     rax, [rcx]
0x18003562b  mov     rax, [rax+10h]
0x18003562f  call    cs:__guard_dispatch_icall_fptr
0x180035635  mov     ecx, r12d
0x180035638  mov     [rbp+ppBuffer], rcx
0x18003563c  test    ebx, ebx
0x18003563e  js      loc_180035EF8
0x180035644  test    rcx, rcx
0x180035647  jnz     loc_180036065
0x18003564d  mov     rcx, [rbp+var_30]
0x180035651  test    rcx, rcx
0x180035654  jnz     loc_18003607B
0x18003565a  test    cs:Microsoft_Windows_MediaFoundation_Performance_CoreEnableBits, 1
0x180035661  jnz     loc_180036091
0x180035667  lea     rcx, [rbp+arg_0]; this
0x18003566b  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180035670  mov     eax, ebx
0x180035672  mov     rbx, [rsp+80h+arg_8]
0x18003567a  add     rsp, 80h
0x180035681  pop     r15
0x180035683  pop     r14
0x180035685  pop     r13
0x180035687  pop     r12
0x180035689  pop     rdi
0x18003568a  pop     rsi
0x18003568b  pop     rbp
0x18003568c  retn
0x18003568e  mov     rcx, [rbp+var_30]
0x180035692  mov     rdx, r12
0x180035695  mov     rax, [rcx]
0x180035698  mov     rax, [rax+120h]
0x18003569f  call    cs:__guard_dispatch_icall_fptr
0x1800356a5  xor     r12d, r12d
0x1800356a8  mov     ebx, eax
0x1800356aa  test    eax, eax
0x1800356ac  jns     loc_180035572
0x1800356b2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800356b9  test    rcx, rcx
0x1800356bc  jnz     short loc_1800356FE
0x1800356be  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800356c5  nop     dword ptr [rax+rax+00h]
0x1800356ca  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800356d1  mov     rcx, rax
0x1800356d4  test    rax, rax
0x1800356d7  jz      loc_180035D0F
0x1800356dd  mov     rax, [rax]
0x1800356e0  mov     edx, 7F0h
0x1800356e5  mov     rax, [rax+8]
0x1800356e9  call    cs:__guard_dispatch_icall_fptr
0x1800356ef  test    eax, eax
0x1800356f1  jz      loc_180035D0F
0x1800356f7  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800356fe  cmp     [rcx+8], r12b
0x180035702  jnz     loc_180035D22
0x180035708  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003570f  jb      loc_180035EF8
0x180035715  mov     edx, 64h ; 'd'
0x18003571a  jmp     loc_180035EDE
0x18003571f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180035726  xor     r12d, r12d
0x180035729  test    rcx, rcx
0x18003572c  jz      loc_180035814
0x180035732  cmp     [rcx+8], r12b
0x180035736  jnz     loc_180035B10
0x18003573c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180035743  jnb     loc_180035FEB
0x180035749  mov     r15d, [rbp+arg_0]
0x18003574d  mov     rcx, [rdi+0C8h]
0x180035754  lea     r8, _GUID_00000000_0000_0000_0000_000000000000
0x18003575b  add     rcx, 70h ; 'p'
0x18003575f  mov     [rsp+80h+var_60], r12
0x180035764  mov     r9d, ebx
0x180035767  mov     edx, 1
0x18003576c  mov     rax, [rcx]
0x18003576f  mov     rax, [rax+30h]
  ... truncated ...
```
