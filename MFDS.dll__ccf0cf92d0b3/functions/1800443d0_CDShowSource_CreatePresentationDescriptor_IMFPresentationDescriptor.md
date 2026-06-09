# CDShowSource::CreatePresentationDescriptor(IMFPresentationDescriptor * *)

- ea: `0x1800443d0`
- end: `0x1800453bc`
- name: `?CreatePresentationDescriptor@CDShowSource@@UEAAJPEAPEAUIMFPresentationDescriptor@@@Z`
- size: `4076`
- prototype: `__int64 __fastcall(CDShowSource *__hidden this, struct IMFPresentationDescriptor **)`
- caller_count: `0`
- callee_count: `17`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x180002820`
- `0x1800052c0`
- `0x18000b8c0`
- `0x180010350`
- `0x1800140b0`
- `0x1800227e0`
- `0x180032a50`
- `0x180041d8c`
- `0x1800443d0`
- `0x1800453c4`
- `0x18004d7cc`
- `0x180051ce4`
- `0x180073d4c`
- `0x180073d58`
- `0x180074160`
- `0x180089860`
- `0x1800c9010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004537d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004537d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180044482`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180044482`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800444c6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004458b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180044655`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180044729`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800447fb`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180044971`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180044a73`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180044b58`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180044bed`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180044c82`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180044d17`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180044dac`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180044e41`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180044ed6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180044fde`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800450cb`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004519b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180045250`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800444c6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004458b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180044655`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180044729`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800447fb`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180044971`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180044a73`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180044b58`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180044bed`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180044c82`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180044d17`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180044dac`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180044e41`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180044ed6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180044fde`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800450cb`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004519b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180045250`
- `MFPlat!MFCreatePresentationDescriptor` at `0x1800447d9`
- `MFPlat!MFCreatePresentationDescriptor` at `0x1800447d9`

## string_xrefs

- `0x1800443fd`: `CDShowSource::CreatePresentationDescriptor`
- `0x180044786`: `CDShowSource::CreatePresentationDescriptor`
- `0x180044858`: `CDShowSource::CreatePresentationDescriptor`
- `0x180044ad0`: `CDShowSource::CreatePresentationDescriptor`
- `0x180044b20`: `CDShowSource::CreatePresentationDescriptor`
- `0x180044bb5`: `CDShowSource::CreatePresentationDescriptor`
- `0x180044c4a`: `CDShowSource::CreatePresentationDescriptor`
- `0x180044cdf`: `CDShowSource::CreatePresentationDescriptor`
- `0x180044d74`: `CDShowSource::CreatePresentationDescriptor`
- `0x180044e09`: `CDShowSource::CreatePresentationDescriptor`
- `0x180044e9e`: `CDShowSource::CreatePresentationDescriptor`
- `0x180044f33`: `CDShowSource::CreatePresentationDescriptor`
- `0x18004503b`: `CDShowSource::CreatePresentationDescriptor`
- `0x180045128`: `CDShowSource::CreatePresentationDescriptor`
- `0x1800451f8`: `CDShowSource::CreatePresentationDescriptor`
- `0x1800452ad`: `CDShowSource::CreatePresentationDescriptor`

## pseudocode

```c
__int64 __fastcall CDShowSource::CreatePresentationDescriptor(
        CDShowSource *this,
        struct IMFPresentationDescriptor **a2)
{
  struct CallStackContext *ThreadRelativeContext; // rdi
  int v5; // ebx
  __int128 v6; // xmm0
  struct _RTL_CRITICAL_SECTION *v7; // rbx
  bool v8; // zf
  CallStackTracing *v9; // rcx
  HRESULT v10; // edi
  CallStackTracing *v11; // rax
  struct CallStackContext *v12; // rax
  __int64 v13; // rdx
  CallStackTracing *v14; // rcx
  CallStackTracing *v15; // rax
  struct CallStackContext *v16; // rax
  DWORD v17; // edi
  IMFStreamDescriptor **v18; // r12
  CallStackTracing *v19; // rcx
  CallStackTracing *v20; // rax
  struct CallStackContext *v21; // rax
  __int64 i; // r15
  __int64 v23; // rax
  CallStackTracing *v24; // rcx
  CallStackTracing *v25; // rax
  struct CallStackContext *v26; // rax
  __int64 v27; // rdx
  CallStackTracing *v28; // rcx
  CallStackTracing *v29; // rax
  struct CallStackContext *v30; // rax
  __int64 j; // r15
  IMFStreamDescriptor *v32; // rcx
  CallStackTracing *v33; // rcx
  CallStackTracing *v34; // rax
  CallStackTracing *v35; // rcx
  CallStackTracing *v36; // rax
  struct CallStackContext *v37; // rax
  __int64 v38; // rdx
  struct CallStackContext *v39; // rax
  CallStackTracing *v40; // rcx
  CallStackTracing *v41; // rax
  struct CallStackContext *v42; // rax
  CallStackTracing *v43; // rcx
  CallStackTracing *v44; // rax
  struct CallStackContext *v45; // rax
  CallStackTracing *v46; // rcx
  CallStackTracing *v47; // rax
  struct CallStackContext *v48; // rax
  CallStackTracing *v49; // rcx
  CallStackTracing *v50; // rax
  struct CallStackContext *v51; // rax
  CallStackTracing *v52; // rcx
  CallStackTracing *v53; // rax
  struct CallStackContext *v54; // rax
  CallStackTracing *v55; // rcx
  CallStackTracing *v56; // rax
  struct CallStackContext *v57; // rax
  CallStackTracing *v58; // rcx
  CallStackTracing *v59; // rax
  struct CallStackContext *v60; // rax
  CallStackTracing *v61; // rcx
  CallStackTracing *v62; // rax
  struct CallStackContext *v63; // rax
  CallStackTracing *v64; // rcx
  CallStackTracing *v65; // rax
  struct CallStackContext *v66; // rax
  CallStackTracing *v67; // rcx
  CallStackTracing *v68; // rax
  struct CallStackContext *v69; // rax
  CallStackTracing *v70; // rcx
  CallStackTracing *v71; // rax
  struct CallStackContext *v72; // rax
  unsigned int v73; // r13d
  __int64 k; // r14
  IMFStreamDescriptor *v75; // rcx
  struct IMFMediaType *v77; // [rsp+38h] [rbp-31h] BYREF
  _BYTE v78[4]; // [rsp+40h] [rbp-29h] BYREF
  unsigned int v79; // [rsp+44h] [rbp-25h]
  IMFPresentationDescriptor *ppPresentationDescriptor; // [rsp+48h] [rbp-21h] BYREF
  int v81; // [rsp+50h] [rbp-19h] BYREF
  __int64 v82; // [rsp+58h] [rbp-11h] BYREF
  _QWORD v83[2]; // [rsp+60h] [rbp-9h] BYREF
  struct _GUID v84; // [rsp+70h] [rbp+7h] BYREF

  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)v78,
    "CDShowSource::CreatePresentationDescriptor",
    732);
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) && *((_QWORD *)this + 137) )
  {
    ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
    v5 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 137) + 296LL))(*((_QWORD *)this + 137));
    v6 = *(_OWORD *)(*(__int64 (__fastcall **)(_QWORD, _QWORD *))(**((_QWORD **)this + 137) + 280LL))(
                      *((_QWORD *)this + 137),
                      v83);
    *((_DWORD *)ThreadRelativeContext + 504) = v5;
    *((_OWORD *)ThreadRelativeContext + 125) = v6;
  }
  v7 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 48);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
  v8 = *((_DWORD *)this + 22) == 0;
  ppPresentationDescriptor = 0;
  v82 = 0;
  v84 = GUID_00000000_0000_0000_0000_000000000000;
  if ( !v8 )
  {
    v9 = CallStackTracing::s_wpInstance;
    v10 = -1072873851;
    if ( !CallStackTracing::s_wpInstance )
    {
      v11 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
      CallStackTracing::s_wpInstance = v11;
      if ( v11 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v11 + 8LL))(v11, 2032) )
      {
        v9 = CallStackTracing::s_wpInstance;
      }
      else
      {
        v9 = (CallStackTracing *)&qword_1800EB130;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
      }
    }
    if ( *((_BYTE *)v9 + 8) )
    {
      v12 = CallStackTracing::GetThreadRelativeContext(v9);
      if ( *((_DWORD *)v12 + 499) != -1072873851 )
        CallStackContext::TraceFailure(v12, "CDShowSource::CreatePresentationDescriptor", 742, -1072873851);
    }
    if ( !g_wppLevels )
      goto LABEL_228;
    v13 = 72;
    goto LABEL_15;
  }
  if ( !*((_QWORD *)this + 92) )
  {
    v14 = CallStackTracing::s_wpInstance;
    v10 = -2147467261;
    if ( !CallStackTracing::s_wpInstance )
    {
      v15 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
      CallStackTracing::s_wpInstance = v15;
      if ( v15 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v15 + 8LL))(v15, 2032) )
      {
        v14 = CallStackTracing::s_wpInstance;
      }
      else
      {
        v14 = (CallStackTracing *)&qword_1800EB130;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
      }
    }
    if ( *((_BYTE *)v14 + 8) )
    {
      v16 = CallStackTracing::GetThreadRelativeContext(v14);
      if ( *((_DWORD *)v16 + 499) != -2147467261 )
        CallStackContext::TraceFailure(v16, "CDShowSource::CreatePresentationDescriptor", 744, -2147467261);
    }
    if ( !g_wppLevels )
      goto LABEL_228;
    v13 = 73;
    goto LABEL_15;
  }
  v79 = *((_DWORD *)this + 252);
  v17 = v79;
  v18 = (IMFStreamDescriptor **)operator new[](saturated_mul(v79, 8u));
  if ( !v18 )
  {
    v19 = CallStackTracing::s_wpInstance;
    v10 = -2147024882;
    if ( !CallStackTracing::s_wpInstance )
    {
      v20 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
      CallStackTracing::s_wpInstance = v20;
      if ( v20 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v20 + 8LL))(v20, 2032) )
      {
        v19 = CallStackTracing::s_wpInstance;
      }
      else
      {
        v19 = (CallStackTracing *)&qword_1800EB130;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
      }
    }
    if ( *((_BYTE *)v19 + 8) )
    {
      v21 = CallStackTracing::GetThreadRelativeContext(v19);
      if ( *((_DWORD *)v21 + 499) != -2147024882 )
        CallStackContext::TraceFailure(v21, "CDShowSource::CreatePresentationDescriptor", 748, -2147024882);
    }
    if ( !g_wppLevels )
      goto LABEL_228;
    v13 = 74;
LABEL_15:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v13, &WPP_fc9d812e38f834ce3857a60a35cbba0e_Traceguids, this, v10);
    goto LABEL_228;
  }
  for ( i = 0; (unsigned int)i < v17; i = (unsigned int)(i + 1) )
  {
    v23 = CTPtrArray<CDShowStream,20>::operator[]((char *)this + 808, (unsigned int)i);
    v10 = (*(__int64 (__fastcall **)(__int64, IMFStreamDescriptor **))(*(_QWORD *)v23 + 64LL))(v23, &v18[i]);
    if ( v10 < 0 )
    {
      v24 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v25 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
        CallStackTracing::s_wpInstance = v25;
        if ( v25 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v25 + 8LL))(v25, 2032) )
        {
          v24 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v24 = (CallStackTracing *)&qword_1800EB130;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
        }
      }
      if ( *((_BYTE *)v24 + 8) )
      {
        v26 = CallStackTracing::GetThreadRelativeContext(v24);
        if ( *((_DWORD *)v26 + 499) != v10 )
          CallStackContext::TraceFailure(v26, "CDShowSource::CreatePresentationDescriptor", 752, v10);
      }
      if ( g_wppLevels )
      {
        v27 = 75;
        goto LABEL_52;
      }
      goto LABEL_223;
    }
    v17 = v79;
  }
  v10 = MFCreatePresentationDescriptor(v17, v18, &ppPresentationDescriptor);
  if ( v10 < 0 )
  {
    v28 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v29 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
      CallStackTracing::s_wpInstance = v29;
      if ( v29 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v29 + 8LL))(v29, 2032) )
      {
        v28 = CallStackTracing::s_wpInstance;
      }
      else
      {
        v28 = (CallStackTracing *)&qword_1800EB130;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
      }
    }
    if ( *((_BYTE *)v28 + 8) )
    {
      v30 = CallStackTracing::GetThreadRelativeContext(v28);
      if ( *((_DWORD *)v30 + 499) != v10 )
        CallStackContext::TraceFailure(v30, "CDShowSource::CreatePresentationDescriptor", 758, v10);
    }
    if ( g_wppLevels )
    {
      v27 = 76;
      goto LABEL_52;
    }
    goto LABEL_223;
  }
  for ( j = 0; (unsigned int)j < v79; j = (unsigned int)(j + 1) )
  {
    v32 = v18[j];
    v83[0] = 0;
    v77 = 0;
    v10 = ((__int64 (__fastcall *)(IMFStreamDescriptor *, _QWORD *))v32->lpVtbl->GetMediaTypeHandler)(v32, v83);
    if ( v10 < 0 )
    {
      v58 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v59 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
        CallStackTracing::s_wpInstance = v59;
        if ( v59 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v59 + 8LL))(v59, 2032) )
        {
          v58 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v58 = (CallStackTracing *)&qword_1800EB130;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
        }
      }
      if ( *((_BYTE *)v58 + 8) )
      {
        v60 = CallStackTracing::GetThreadRelativeContext(v58);
        if ( *((_DWORD *)v60 + 499) != v10 )
          CallStackContext::TraceFailure(v60, "CDShowSource::CreatePresentationDescriptor", 765, v10);
      }
      if ( !g_wppLevels )
        goto LABEL_172;
      v38 = 77;
LABEL_171:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v38, &WPP_fc9d812e38f834ce3857a60a35cbba0e_Traceguids, this, v10);
      goto LABEL_172;
    }
    if ( (*(int (__fastcall **)(_QWORD, struct IMFMediaType **))(*(_QWORD *)v83[0] + 56LL))(v83[0], &v77) >= 0 )
    {
      if ( *((int *)this + 54) <= 0 )
        goto LABEL_83;
      v10 = MediaSubTypeTransform(v77);
      if ( v10 < 0 )
      {
        v49 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v50 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
          CallStackTracing::s_wpInstance = v50;
          if ( v50 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v50 + 8LL))(v50, 2032) )
          {
            v49 = CallStackTracing::s_wpInstance;
          }
          else
          {
            v49 = (CallStackTracing *)&qword_1800EB130;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
          }
        }
        if ( *((_BYTE *)v49 + 8) )
        {
          v51 = CallStackTracing::GetThreadRelativeContext(v49);
          if ( *((_DWORD *)v51 + 499) != v10 )
            CallStackContext::TraceFailure(v51, "CDShowSource::CreatePresentationDescriptor", 791, v10);
        }
        if ( !g_wppLevels )
          goto LABEL_172;
        v38 = 82;
        goto LABEL_171;
      }
      v10 = (*(__int64 (__fastcall **)(_QWORD, struct IMFMediaType *))(*(_QWORD *)v83[0] + 48LL))(v83[0], v77);
      if ( v10 < 0 )
      {
        v46 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v47 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
          CallStackTracing::s_wpInstance = v47;
          if ( v47 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v47 + 8LL))(v47, 2032) )
          {
            v46 = CallStackTracing::s_wpInstance;
          }
          else
          {
            v46 = (CallStackTracing *)&qword_1800EB130;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
          }
        }
        if ( *((_BYTE *)v46 + 8) )
        {
          v48 = CallStackTracing::GetThreadRelativeContext(v46);
          if ( *((_DWORD *)v48 + 499) != v10 )
            CallStackContext::TraceFailure(v48, "CDShowSource::CreatePresentationDescriptor", 792, v10);
        }
        if ( !g_wppLevels )
          goto LABEL_172;
        v38 = 83;
        goto LABEL_171;
      }
    }
    else
    {
      v81 = 0;
      v10 = (*(__int64 (__fastcall **)(_QWORD, int *))(*(_QWORD *)v83[0] + 32LL))(v83[0], &v81);
      if ( v10 < 0 )
      {
        v43 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v44 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
          CallStackTracing::s_wpInstance = v44;
          if ( v44 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v44 + 8LL))(v44, 2032) )
          {
            v43 = CallStackTracing::s_wpInstance;
          }
          else
          {
            v43 = (CallStackTracing *)&qword_1800EB130;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
          }
        }
        if ( *((_BYTE *)v43 + 8) )
        {
          v45 = CallStackTracing::GetThreadRelativeContext(v43);
          if ( *((_DWORD *)v45 + 499) != v10 )
            CallStackContext::TraceFailure(v45, "CDShowSource::CreatePresentationDescriptor", 779, v10);
        }
        if ( !g_wppLevels )
          goto LABEL_172;
        v38 = 78;
        goto LABEL_171;
      }
      v10 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, struct IMFMediaType **))(*(_QWORD *)v83[0] + 40LL))(
              v83[0],
              (unsigned int)(v81 - 1),
              &v77);
      if ( v10 < 0 )
      {
        v40 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v41 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
          CallStackTracing::s_wpInstance = v41;
          if ( v41 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v41 + 8LL))(v41, 2032) )
          {
            v40 = CallStackTracing::s_wpInstance;
          }
          else
          {
            v40 = (CallStackTracing *)&qword_1800EB130;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
          }
        }
        if ( *((_BYTE *)v40 + 8) )
        {
          v42 = CallStackTracing::GetThreadRelativeContext(v40);
          if ( *((_DWORD *)v42 + 499) != v10 )
            CallStackContext::TraceFailure(v42, "CDShowSource::CreatePresentationDescriptor", 781, v10);
        }
        if ( !g_wppLevels )
          goto LABEL_172;
        v38 = 79;
        goto LABEL_171;
      }
      if ( *((int *)this + 54) > 0 )
      {
        v10 = MediaSubTypeTransform(v77);
        if ( v10 < 0 )
        {
          v35 = CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v36 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
            CallStackTracing::s_wpInstance = v36;
            if ( v36 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v36 + 8LL))(v36, 2032) )
            {
              v35 = CallStackTracing::s_wpInstance;
            }
            else
            {
              v35 = (CallStackTracing *)&qword_1800EB130;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
            }
          }
          if ( *((_BYTE *)v35 + 8) )
          {
            v37 = CallStackTracing::GetThreadRelativeContext(v35);
            if ( *((_DWORD *)v37 + 499) != v10 )
              CallStackContext::TraceFailure(v37, "CDShowSource::CreatePresentationDescriptor", 785, v10);
          }
          if ( g_wppLevels )
          {
            v38 = 80;
            goto LABEL_171;
          }
LABEL_172:
          ATL::CComPtrBase<IMediaSeeking>::~CComPtrBase<IMediaSeeking>(&v77);
          ATL::CComPtrBase<IMediaSeeking>::~CComPtrBase<IMediaSeeking>(v83);
          goto LABEL_223;
        }
      }
      v10 = (*(__int64 (__fastcall **)(_QWORD, struct IMFMediaType *))(*(_QWORD *)v83[0] + 48LL))(v83[0], v77);
      if ( v10 < 0 )
      {
        v33 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v34 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
          CallStackTracing::s_wpInstance = v34;
          if ( v34 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v34 + 8LL))(v34, 2032) )
          {
            v33 = CallStackTracing::s_wpInstance;
          }
          else
          {
            v33 = (CallStackTracing *)&qword_1800EB130;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
          }
        }
        if ( *((_BYTE *)v33 + 8) )
        {
          v39 = CallStackTracing::GetThreadRelativeContext(v33);
          if ( *((_DWORD *)v39 + 499) != v10 )
            CallStackContext::TraceFailure(v39, "CDShowSource::CreatePresentationDescriptor", 787, v10);
        }
        if ( !g_wppLevels )
          goto LABEL_172;
        v38 = 81;
        goto LABEL_171;
      }
    }
    if ( *((int *)this + 54) > 0 )
    {
      if ( (unsigned int)CDShowSource::IsCPEnabled(this) )
      {
        v10 = ((__int64 (__fastcall *)(IMFStreamDescriptor *, const IID *, __int64))v18[j]->lpVtbl->SetUINT32)(
                v18[j],
                &MF_SD_PROTECTED,
                1);
        if ( v10 < 0 )
        {
          v52 = CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v53 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
            CallStackTracing::s_wpInstance = v53;
            if ( v53 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v53 + 8LL))(v53, 2032) )
            {
              v52 = CallStackTracing::s_wpInstance;
            }
            else
            {
              v52 = (CallStackTracing *)&qword_1800EB130;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
            }
          }
          if ( *((_BYTE *)v52 + 8) )
          {
            v54 = CallStackTracing::GetThreadRelativeContext(v52);
            if ( *((_DWORD *)v54 + 499) != v10 )
              CallStackContext::TraceFailure(v54, "CDShowSource::CreatePresentationDescriptor", 800, v10);
          }
          if ( !g_wppLevels )
            goto LABEL_172;
          v38 = 84;
          goto LABEL_171;
        }
      }
    }
LABEL_83:
    v10 = ((__int64 (__fastcall *)(IMFPresentationDescriptor *, _QWORD))ppPresentationDescriptor->lpVtbl->SelectStream)(
            ppPresentationDescriptor,
            (unsigned int)j);
    if ( v10 < 0 )
    {
      v55 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v56 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
        CallStackTracing::s_wpInstance = v56;
        if ( v56 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v56 + 8LL))(v56, 2032) )
        {
          v55 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v55 = (CallStackTracing *)&qword_1800EB130;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
        }
      }
      if ( *((_BYTE *)v55 + 8) )
      {
        v57 = CallStackTracing::GetThreadRelativeContext(v55);
        if ( *((_DWORD *)v57 + 499) != v10 )
          CallStackContext::TraceFailure(v57, "CDShowSource::CreatePresentationDescriptor", 803, v10);
      }
      if ( !g_wppLevels )
        goto LABEL_172;
      v38 = 85;
      goto LABEL_171;
    }
    ATL::CComPtrBase<IMediaSeeking>::~CComPtrBase<IMediaSeeking>(&v77);
    ATL::CComPtrBase<IMediaSeeking>::~CComPtrBase<IMediaSeeking>(v83);
  }
  if ( (*(int (__fastcall **)(_QWORD, __int64 *))(**((_QWORD **)this + 92) + 48LL))(*((_QWORD *)this + 92), &v82) < 0
    || (v10 = ((__int64 (__fastcall *)(IMFPresentationDescriptor *, const IID *, __int64))ppPresentationDescriptor->lpVtbl->SetUINT64)(
                ppPresentationDescriptor,
                &MF_PD_DURATION,
                v82),
        v10 >= 0) )
  {
    if ( (int)CDShowWrapper::GetContainerFormat(*((CDShowWrapper **)this + 92), &v84) < 0
      || (unsigned __int8)_(&GUID_00000000_0000_0000_0000_000000000000, &v84)
      || (v10 = ((__int64 (__fastcall *)(IMFPresentationDescriptor *, __int64 *, struct _GUID *))ppPresentationDescriptor->lpVtbl->SetGUID)(
                  ppPresentationDescriptor,
                  MF_PD_CONTAINER_FORMAT,
                  &v84),
          v10 >= 0) )
    {
      if ( *(_DWORD *)(*((_QWORD *)this + 92) + 472LL)
        && (v10 = ((__int64 (__fastcall *)(IMFPresentationDescriptor *, __int64 *, __int64))ppPresentationDescriptor->lpVtbl->SetUINT32)(
                    ppPresentationDescriptor,
                    MF_PD_AUDIOGAPS_EXPECTED,
                    1),
            v10 < 0) )
      {
        v67 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v68 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
          CallStackTracing::s_wpInstance = v68;
          if ( v68 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v68 + 8LL))(v68, 2032) )
          {
            v67 = CallStackTracing::s_wpInstance;
          }
          else
          {
            v67 = (CallStackTracing *)&qword_1800EB130;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
          }
        }
        if ( *((_BYTE *)v67 + 8) )
        {
          v69 = CallStackTracing::GetThreadRelativeContext(v67);
          if ( *((_DWORD *)v69 + 499) != v10 )
            CallStackContext::TraceFailure(v69, "CDShowSource::CreatePresentationDescriptor", 832, v10);
        }
        if ( !g_wppLevels )
          goto LABEL_223;
        v27 = 88;
      }
      else
      {
        v10 = ((__int64 (__fastcall *)(IMFPresentationDescriptor *, struct IMFPresentationDescriptor **))ppPresentationDescriptor->lpVtbl->Clone)(
                ppPresentationDescriptor,
                a2);
        if ( v10 >= 0 )
        {
          if ( (unsigned __int8)byte_1800EACCB >= 4u )
            WPP_SF_qqD(
              *((_QWORD *)WPP_GLOBAL_Control + 17),
              90,
              &WPP_fc9d812e38f834ce3857a60a35cbba0e_Traceguids,
              this,
              *a2,
              (int)v82 / 10000);
          goto LABEL_223;
        }
        v70 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v71 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
          CallStackTracing::s_wpInstance = v71;
          if ( v71 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v71 + 8LL))(v71, 2032) )
          {
            v70 = CallStackTracing::s_wpInstance;
          }
          else
          {
            v70 = (CallStackTracing *)&qword_1800EB130;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
          }
        }
        if ( *((_BYTE *)v70 + 8) )
        {
          v72 = CallStackTracing::GetThreadRelativeContext(v70);
          if ( *((_DWORD *)v72 + 499) != v10 )
            CallStackContext::TraceFailure(v72, "CDShowSource::CreatePresentationDescriptor", 835, v10);
        }
        if ( !g_wppLevels )
          goto LABEL_223;
        v27 = 89;
      }
    }
    else
    {
      v64 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v65 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
        CallStackTracing::s_wpInstance = v65;
        if ( v65 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v65 + 8LL))(v65, 2032) )
        {
          v64 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v64 = (CallStackTracing *)&qword_1800EB130;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
        }
      }
      if ( *((_BYTE *)v64 + 8) )
      {
        v66 = CallStackTracing::GetThreadRelativeContext(v64);
        if ( *((_DWORD *)v66 + 499) != v10 )
          CallStackContext::TraceFailure(v66, "CDShowSource::CreatePresentationDescriptor", 824, v10);
      }
      if ( !g_wppLevels )
        goto LABEL_223;
      v27 = 87;
    }
LABEL_52:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v27, &WPP_fc9d812e38f834ce3857a60a35cbba0e_Traceguids, this, v10);
    goto LABEL_223;
  }
  v61 = CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    v62 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
    CallStackTracing::s_wpInstance = v62;
    if ( v62 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v62 + 8LL))(v62, 2032) )
    {
      v61 = CallStackTracing::s_wpInstance;
    }
    else
    {
      v61 = (CallStackTracing *)&qword_1800EB130;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
    }
  }
  if ( *((_BYTE *)v61 + 8) )
  {
    v63 = CallStackTracing::GetThreadRelativeContext(v61);
    if ( *((_DWORD *)v63 + 499) != v10 )
      CallStackContext::TraceFailure(v63, "CDShowSource::CreatePresentationDescriptor", 809, v10);
  }
  if ( g_wppLevels )
  {
    v27 = 86;
    goto LABEL_52;
  }
LABEL_223:
  v73 = v79;
  for ( k = 0; (unsigned int)k < v73; k = (unsigned int)(k + 1) )
  {
    v75 = v18[k];
    if ( v75 )
    {
      ((void (__fastcall *)(IMFStreamDescriptor *))v75->lpVtbl->Release)(v75);
      v18[k] = 0;
    }
  }
  operator delete(v18);
LABEL_228:
  if ( ppPresentationDescriptor )
    ((void (__fastcall *)(IMFPresentationDescriptor *))ppPresentationDescriptor->lpVtbl->Release)(ppPresentationDescriptor);
  LeaveCriticalSection(v7);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v78);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1800443d0  mov     [rsp-8+arg_10], rbx
0x1800443d5  push    rbp
0x1800443d6  push    rsi
0x1800443d7  push    rdi
0x1800443d8  push    r12
0x1800443da  push    r13
0x1800443dc  push    r14
0x1800443de  push    r15
0x1800443e0  lea     rbp, [rsp-27h]
0x1800443e5  sub     rsp, 90h
0x1800443ec  mov     rax, cs:__security_cookie
0x1800443f3  xor     rax, rsp
0x1800443f6  mov     [rbp+57h+var_40], rax
0x1800443fa  mov     r13, rdx
0x1800443fd  lea     rsi, aCdshowsourceCr; "CDShowSource::CreatePresentationDescrip"...
0x180044404  mov     r14, rcx
0x180044407  mov     rdx, rsi; char *
0x18004440a  mov     r8d, 2DCh; int
0x180044410  lea     rcx, [rbp+57h+var_80]; this
0x180044414  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180044419  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180044420  cmp     byte ptr [rcx+8], 0
0x180044424  jz      short loc_18004447B
0x180044426  cmp     qword ptr [r14+448h], 0
0x18004442e  jz      short loc_18004447B
0x180044430  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180044435  mov     rcx, [r14+448h]
0x18004443c  mov     rdi, rax
0x18004443f  mov     rdx, [rcx]
0x180044442  mov     rax, [rdx+128h]
0x180044449  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004444e  mov     rcx, [r14+448h]
0x180044455  mov     ebx, eax
0x180044457  mov     rdx, [rcx]
0x18004445a  mov     rax, [rdx+118h]
0x180044461  lea     rdx, [rbp+57h+var_60]
0x180044465  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004446a  movups  xmm0, xmmword ptr [rax]
0x18004446d  mov     [rdi+7E0h], ebx
0x180044473  movdqu  xmmword ptr [rdi+7D0h], xmm0
0x18004447b  lea     rbx, [r14+30h]
0x18004447f  mov     rcx, rbx; lpCriticalSection
0x180044482  call    cs:__imp_EnterCriticalSection
0x180044489  nop     dword ptr [rax+rax+00h]
0x18004448e  cmp     dword ptr [r14+58h], 0
0x180044493  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x18004449a  mov     [rbp+57h+ppPresentationDescriptor], 0
0x1800444a2  mov     [rbp+57h+var_68], 0
0x1800444aa  movdqu  xmmword ptr [rbp+57h+var_50.Data1], xmm0
0x1800444af  jz      loc_18004456C
0x1800444b5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800444bc  mov     edi, 0C00D3E85h
0x1800444c1  test    rcx, rcx
0x1800444c4  jnz     short loc_18004450D
0x1800444c6  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800444cd  nop     dword ptr [rax+rax+00h]
0x1800444d2  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800444d9  mov     rcx, rax
0x1800444dc  test    rax, rax
0x1800444df  jz      short loc_1800444FF
0x1800444e1  mov     rax, [rax]
0x1800444e4  mov     edx, 7F0h
0x1800444e9  mov     rax, [rax+8]
0x1800444ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800444f2  test    eax, eax
0x1800444f4  jz      short loc_1800444FF
0x1800444f6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800444fd  jmp     short loc_18004450D
0x1800444ff  lea     rcx, qword_1800EB130; this
0x180044506  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004450d  cmp     byte ptr [rcx+8], 0
0x180044511  jz      short loc_180044534
0x180044513  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180044518  cmp     [rax+7CCh], edi
0x18004451e  jz      short loc_180044534
0x180044520  mov     r9d, edi; int
0x180044523  mov     r8d, 2E6h; int
0x180044529  mov     rdx, rsi; char *
0x18004452c  mov     rcx, rax; this
0x18004452f  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180044534  mov     esi, 1
0x180044539  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, sil; MFWppLevels g_wppLevels
0x180044540  jb      loc_180045365
0x180044546  lea     edx, [rsi+47h]
0x180044549  mov     rcx, cs:WPP_GLOBAL_Control
0x180044550  lea     r8, WPP_fc9d812e38f834ce3857a60a35cbba0e_Traceguids
0x180044557  mov     r9, r14
0x18004455a  mov     dword ptr [rsp+0C0h+var_A0], edi
0x18004455e  mov     rcx, [rcx+10h]
0x180044562  call    WPP_SF_qD
0x180044567  jmp     loc_180045365
0x18004456c  cmp     qword ptr [r14+2E0h], 0
0x180044574  jnz     loc_180044613
0x18004457a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180044581  mov     edi, 80004003h
0x180044586  test    rcx, rcx
0x180044589  jnz     short loc_1800445D2
0x18004458b  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180044592  nop     dword ptr [rax+rax+00h]
0x180044597  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004459e  mov     rcx, rax
0x1800445a1  test    rax, rax
0x1800445a4  jz      short loc_1800445C4
0x1800445a6  mov     rax, [rax]
0x1800445a9  mov     edx, 7F0h
0x1800445ae  mov     rax, [rax+8]
0x1800445b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800445b7  test    eax, eax
0x1800445b9  jz      short loc_1800445C4
0x1800445bb  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800445c2  jmp     short loc_1800445D2
0x1800445c4  lea     rcx, qword_1800EB130; this
0x1800445cb  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800445d2  cmp     byte ptr [rcx+8], 0
0x1800445d6  jz      short loc_1800445F9
0x1800445d8  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800445dd  cmp     [rax+7CCh], edi
0x1800445e3  jz      short loc_1800445F9
0x1800445e5  mov     r9d, edi; int
0x1800445e8  mov     r8d, 2E8h; int
0x1800445ee  mov     rdx, rsi; char *
0x1800445f1  mov     rcx, rax; this
0x1800445f4  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800445f9  mov     esi, 1
0x1800445fe  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, sil; MFWppLevels g_wppLevels
0x180044605  jb      loc_180045365
0x18004460b  lea     edx, [rsi+48h]
0x18004460e  jmp     loc_180044549
0x180044613  mov     edi, [r14+3F0h]
0x18004461a  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180044621  mov     eax, 8
0x180044626  mov     [rbp+57h+var_7C], edi
0x180044629  mul     rdi
0x18004462c  cmovb   rax, rcx
0x180044630  mov     rcx, rax; unsigned __int64
0x180044633  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180044638  mov     r12, rax
0x18004463b  test    rax, rax
0x18004463e  jnz     loc_1800446DD
0x180044644  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004464b  mov     edi, 8007000Eh
0x180044650  test    rcx, rcx
0x180044653  jnz     short loc_18004469C
0x180044655  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004465c  nop     dword ptr [rax+rax+00h]
0x180044661  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180044668  mov     rcx, rax
0x18004466b  test    rax, rax
0x18004466e  jz      short loc_18004468E
0x180044670  mov     rax, [rax]
0x180044673  mov     edx, 7F0h
0x180044678  mov     rax, [rax+8]
0x18004467c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044681  test    eax, eax
0x180044683  jz      short loc_18004468E
0x180044685  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004468c  jmp     short loc_18004469C
0x18004468e  lea     rcx, qword_1800EB130; this
0x180044695  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004469c  cmp     byte ptr [rcx+8], 0
0x1800446a0  jz      short loc_1800446C3
0x1800446a2  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800446a7  cmp     [rax+7CCh], edi
0x1800446ad  jz      short loc_1800446C3
0x1800446af  mov     r9d, edi; int
0x1800446b2  mov     r8d, 2ECh; int
0x1800446b8  mov     rdx, rsi; char *
0x1800446bb  mov     rcx, rax; this
0x1800446be  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800446c3  mov     esi, 1
0x1800446c8  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, sil; MFWppLevels g_wppLevels
0x1800446cf  jb      loc_180045365
0x1800446d5  lea     edx, [rsi+49h]
0x1800446d8  jmp     loc_180044549
0x1800446dd  xor     r15d, r15d
0x1800446e0  lea     esi, [r15+1]
0x1800446e4  cmp     r15d, edi
0x1800446e7  jnb     loc_1800447D0
0x1800446ed  lea     rcx, [r14+328h]
0x1800446f4  mov     edx, r15d
0x1800446f7  call    ??A?$CTPtrArray@VCDShowStream@@$0BE@@@QEBAPEAVCDShowStream@@K@Z; CTPtrArray<CDShowStream,20>::operator[](ulong)
0x1800446fc  mov     rcx, rax
0x1800446ff  lea     rdx, [r12+r15*8]
0x180044703  mov     r8, [rax]
0x180044706  mov     rax, [r8+40h]
0x18004470a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004470f  mov     edi, eax
0x180044711  test    eax, eax
0x180044713  js      short loc_18004471D
0x180044715  mov     edi, [rbp+57h+var_7C]
0x180044718  add     r15d, esi
0x18004471b  jmp     short loc_1800446E4
0x18004471d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180044724  test    rcx, rcx
0x180044727  jnz     short loc_180044770
0x180044729  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180044730  nop     dword ptr [rax+rax+00h]
0x180044735  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004473c  mov     rcx, rax
0x18004473f  test    rax, rax
0x180044742  jz      short loc_180044762
0x180044744  mov     rax, [rax]
0x180044747  mov     edx, 7F0h
0x18004474c  mov     rax, [rax+8]
0x180044750  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044755  test    eax, eax
0x180044757  jz      short loc_180044762
0x180044759  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180044760  jmp     short loc_180044770
0x180044762  lea     rcx, qword_1800EB130; this
0x180044769  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180044770  cmp     byte ptr [rcx+8], 0
0x180044774  jz      short loc_18004479B
0x180044776  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004477b  cmp     [rax+7CCh], edi
0x180044781  jz      short loc_18004479B
0x180044783  mov     r9d, edi; int
0x180044786  lea     rdx, aCdshowsourceCr; "CDShowSource::CreatePresentationDescrip"...
0x18004478d  mov     r8d, 2F0h; int
0x180044793  mov     rcx, rax; this
0x180044796  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004479b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, sil; MFWppLevels g_wppLevels
0x1800447a2  jb      loc_18004532C
0x1800447a8  mov     edx, 4Bh ; 'K'
0x1800447ad  mov     rcx, cs:WPP_GLOBAL_Control
0x1800447b4  lea     r8, WPP_fc9d812e38f834ce3857a60a35cbba0e_Traceguids
0x1800447bb  mov     r9, r14
0x1800447be  mov     dword ptr [rsp+0C0h+var_A0], edi
0x1800447c2  mov     rcx, [rcx+10h]
0x1800447c6  call    WPP_SF_qD
0x1800447cb  jmp     loc_18004532C
0x1800447d0  lea     r8, [rbp+57h+ppPresentationDescriptor]; ppPresentationDescriptor
0x1800447d4  mov     rdx, r12; apStreamDescriptors
0x1800447d7  mov     ecx, edi; cStreamDescriptors
0x1800447d9  call    cs:__imp_MFCreatePresentationDescriptor
0x1800447e0  nop     dword ptr [rax+rax+00h]
0x1800447e5  mov     edi, eax
0x1800447e7  test    eax, eax
0x1800447e9  jns     loc_180044884
0x1800447ef  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800447f6  test    rcx, rcx
0x1800447f9  jnz     short loc_180044842
0x1800447fb  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180044802  nop     dword ptr [rax+rax+00h]
0x180044807  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004480e  mov     rcx, rax
0x180044811  test    rax, rax
0x180044814  jz      short loc_180044834
0x180044816  mov     rax, [rax]
0x180044819  mov     edx, 7F0h
0x18004481e  mov     rax, [rax+8]
0x180044822  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044827  test    eax, eax
0x180044829  jz      short loc_180044834
0x18004482b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180044832  jmp     short loc_180044842
0x180044834  lea     rcx, qword_1800EB130; this
0x18004483b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180044842  cmp     byte ptr [rcx+8], 0
0x180044846  jz      short loc_18004486D
0x180044848  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004484d  cmp     [rax+7CCh], edi
0x180044853  jz      short loc_18004486D
0x180044855  mov     r9d, edi; int
0x180044858  lea     rdx, aCdshowsourceCr; "CDShowSource::CreatePresentationDescrip"...
0x18004485f  mov     r8d, 2F6h; int
0x180044865  mov     rcx, rax; this
0x180044868  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004486d  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, sil; MFWppLevels g_wppLevels
0x180044874  jb      loc_18004532C
0x18004487a  mov     edx, 4Ch ; 'L'
0x18004487f  jmp     loc_1800447AD
0x180044884  xor     r15d, r15d
0x180044887  cmp     r15d, [rbp+57h+var_7C]
0x18004488b  jnb     loc_180044F8B
0x180044891  mov     rcx, [r12+r15*8]
0x180044895  lea     rdx, [rbp+57h+var_60]
0x180044899  mov     [rbp+57h+var_60], 0
0x1800448a1  mov     [rbp+57h+var_88], 0
0x1800448a9  mov     rax, [rcx]
0x1800448ac  mov     rax, [rax+110h]
0x1800448b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800448b8  mov     edi, eax
0x1800448ba  test    eax, eax
0x1800448bc  js      loc_180044ECA
0x1800448c2  mov     rcx, [rbp+57h+var_60]
0x1800448c6  lea     rdx, [rbp+57h+var_88]
0x1800448ca  mov     rax, [rcx]
0x1800448cd  mov     rax, [rax+38h]
0x1800448d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800448d6  test    eax, eax
0x1800448d8  jns     loc_1800449B5
0x1800448de  mov     rcx, [rbp+57h+var_60]
0x1800448e2  lea     rdx, [rbp+57h+var_70]
0x1800448e6  mov     [rbp+57h+var_70], 0
0x1800448ed  mov     rax, [rcx]
0x1800448f0  mov     rax, [rax+20h]
0x1800448f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800448f9  mov     edi, eax
0x1800448fb  test    eax, eax
  ... truncated ...
```
