# CPMPSharedMediaEventReadQueue::DeserializeFragmentedSampleHeader(CBufferReader &)

- ea: `0x1801cb850`
- end: `0x1801cc1b8`
- name: `?DeserializeFragmentedSampleHeader@CPMPSharedMediaEventReadQueue@@IEAAJAEAVCBufferReader@@@Z`
- size: `2408`
- prototype: `__int64 __fastcall(CPMPSharedMediaEventReadQueue *__hidden this, struct CBufferReader *pStm)`
- caller_count: `1`
- callee_count: `18`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180023860`

## callees

- `0x1800249ec`
- `0x180024c3c`
- `0x18002fee0`
- `0x18003ecb0`
- `0x1800402c0`
- `0x180050d6c`
- `0x180063f00`
- `0x1800bb904`
- `0x1800ec0e0`
- `0x18018d0a0`
- `0x1801aef24`
- `0x1801cb850`
- `0x1802583a8`
- `0x180258480`
- `0x18029ee74`
- `0x1802aa428`
- `0x1802aae70`
- `0x180344d40`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801cb8ed`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801cb9b4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801cba5c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801cbb1e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801cbc4c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801cbd01`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801cbdb5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801cbe71`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801cbf29`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801cc08a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801cb8ed`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801cb9b4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801cba5c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801cbb1e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801cbc4c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801cbd01`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801cbdb5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801cbe71`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801cbf29`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801cc08a`
- `MFPlat!MFCreateSample` at `0x1801cb992`
- `MFPlat!MFCreateSample` at `0x1801cb992`

## string_xrefs

- `0x1801cb8bd`: `CPMPSharedMediaEventReadQueue::DeserializeFragmentedSampleHeader`
- `0x1801cbcaa`: `CPMPSharedMediaEventReadQueue::DeserializeFragmentedSampleHeader`
- `0x1801cbd5f`: `CPMPSharedMediaEventReadQueue::DeserializeFragmentedSampleHeader`
- `0x1801cbe13`: `CPMPSharedMediaEventReadQueue::DeserializeFragmentedSampleHeader`
- `0x1801cbecf`: `CPMPSharedMediaEventReadQueue::DeserializeFragmentedSampleHeader`
- `0x1801cbf87`: `CPMPSharedMediaEventReadQueue::DeserializeFragmentedSampleHeader`
- `0x1801cc0e8`: `CPMPSharedMediaEventReadQueue::DeserializeFragmentedSampleHeader`

## pseudocode

```c
__int64 __fastcall CPMPSharedMediaEventReadQueue::DeserializeFragmentedSampleHeader(
        CPMPSharedMediaEventReadQueue *this,
        struct CBufferReader *pStm)
{
  _DWORD *v4; // rax
  _DWORD *v5; // rdi
  __int64 v6; // rdx
  __int64 v7; // r8
  __int64 *v8; // rcx
  HRESULT appended; // ebx
  CallStackTracing *v10; // rax
  struct CallStackContext *v11; // rax
  __int64 v12; // rdx
  __int64 v13; // r8
  __int64 *v14; // rcx
  CallStackTracing *v15; // rax
  struct CallStackContext *v16; // rax
  __int64 v17; // rdx
  __int64 v18; // r8
  __int64 *v19; // rcx
  CallStackTracing *v20; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v22; // r8
  __int64 *v23; // rcx
  CallStackTracing *v24; // rax
  struct CallStackContext *v25; // rax
  unsigned int v26; // ecx
  unsigned int v27; // r12d
  unsigned int v28; // edx
  int v29; // r15d
  __int64 v30; // r8
  int v31; // r9d
  __int64 *v32; // rcx
  CallStackTracing *v33; // rax
  struct CallStackContext *v34; // rax
  __int64 v35; // r8
  __int64 *v36; // rcx
  CallStackTracing *v37; // rax
  struct CallStackContext *v38; // rax
  __int64 v39; // r8
  __int64 *v40; // rcx
  CallStackTracing *v41; // rax
  struct CallStackContext *v42; // rax
  __int64 v43; // r8
  __int64 *v44; // rcx
  CallStackTracing *v45; // rax
  struct CallStackContext *v46; // rax
  __int64 v47; // r8
  __int64 *v48; // rcx
  CallStackTracing *v49; // rax
  struct CallStackContext *v50; // rax
  __int64 v51; // r8
  __int64 *v52; // rcx
  CallStackTracing *v53; // rax
  struct CallStackContext *v54; // rax
  IMFSample *v55; // rdx
  struct IMFMediaBuffer *v56; // rdx
  __int64 v57; // rax
  _BYTE v59[8]; // [rsp+40h] [rbp-40h] BYREF
  struct IMFMediaBuffer *v60; // [rsp+48h] [rbp-38h] BYREF
  IMFSample *ppIMFSample; // [rsp+50h] [rbp-30h] BYREF
  int v62; // [rsp+58h] [rbp-28h] BYREF
  unsigned int v63[2]; // [rsp+60h] [rbp-20h] BYREF
  unsigned int v64; // [rsp+68h] [rbp-18h]

  ppIMFSample = 0;
  v60 = 0;
  v4 = operator new(0x40u);
  v5 = v4;
  if ( v4 )
  {
    v4[4] = 0;
    *((_QWORD *)v4 + 3) = 0;
    *((_QWORD *)v4 + 4) = 0;
    *((_QWORD *)v4 + 5) = 0;
    *((_QWORD *)v4 + 6) = 0;
    *((_QWORD *)v4 + 7) = 0;
  }
  else
  {
    v5 = 0;
  }
  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)v59,
    "CPMPSharedMediaEventReadQueue::DeserializeFragmentedSampleHeader",
    977);
  if ( v5 )
  {
    appended = MFCreateSample(&ppIMFSample);
    if ( appended >= 0 )
    {
      appended = CSamplePropBinaryReader::Deserialize(pStm, (IMFAttributes *)ppIMFSample);
      if ( appended < 0 )
      {
        v19 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v20 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v12, v18);
          CallStackTracing::s_wpInstance = v20;
          if ( v20 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v20 + 8LL))(v20, 2032) )
          {
            v19 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v19 = &qword_1803CE250;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
          }
        }
        if ( *((_BYTE *)v19 + 8) )
        {
          ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v19);
          if ( *((_DWORD *)ThreadRelativeContext + 499) != appended )
            CallStackContext::TraceFailure(
              ThreadRelativeContext,
              "CPMPSharedMediaEventReadQueue::DeserializeFragmentedSampleHeader",
              982,
              appended);
        }
        if ( !g_wppLevels )
          goto LABEL_127;
        v17 = 105;
        goto LABEL_126;
      }
      *(_QWORD *)v63 = 0;
      v64 = 0;
      appended = (**((__int64 (__fastcall ***)(char *, unsigned int *, __int64))pStm + 65))((char *)pStm + 520, v63, 12);
      if ( appended < 0 )
      {
        v23 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v24 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v12, v22);
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
          if ( *((_DWORD *)v25 + 499) != appended )
            CallStackContext::TraceFailure(
              v25,
              "CPMPSharedMediaEventReadQueue::DeserializeFragmentedSampleHeader",
              987,
              appended);
        }
        if ( !g_wppLevels )
          goto LABEL_127;
        v17 = 106;
        goto LABEL_126;
      }
      v62 = 0;
      ((void (__fastcall *)(IMFSample *, int *))ppIMFSample->lpVtbl->GetSampleFlags)(ppIMFSample, &v62);
      v26 = v63[1];
      v27 = v63[0];
      v5[4] = v64;
      v28 = v64;
      if ( v26 > 1 && (v62 & 0x100) != 0 )
      {
        v29 = 30;
      }
      else
      {
        v29 = 0;
        v26 = 1;
      }
      v5[14] = v26;
      if ( (unsigned int)CPMPSharedMediaEventReadQueue::LookupSampleState(this, v28, 0, 0) != -1072875819 )
      {
        if ( byte_1803CECEC )
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 22),
            (unsigned int)(v31 + 107),
            &WPP_be5c5516ab2437f8fba11fde691f58f8_Traceguids,
            this,
            v5[4]);
        v32 = (__int64 *)CallStackTracing::s_wpInstance;
        appended = -1072875845;
        if ( !CallStackTracing::s_wpInstance )
        {
          v33 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v12, v30);
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
          v34 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v32);
          if ( *((_DWORD *)v34 + 499) != -1072875845 )
            CallStackContext::TraceFailure(
              v34,
              "CPMPSharedMediaEventReadQueue::DeserializeFragmentedSampleHeader",
              1009,
              -1072875845);
        }
        if ( !g_wppLevels )
          goto LABEL_127;
        v17 = 108;
        goto LABEL_126;
      }
      if ( v29 )
      {
        if ( (unsigned __int8)byte_1803CECEC >= 0x10u )
          WPP_SF_qDDDd(
            *((_QWORD *)WPP_GLOBAL_Control + 22),
            114,
            &WPP_be5c5516ab2437f8fba11fde691f58f8_Traceguids,
            this,
            v5[4],
            v27,
            *((_DWORD *)pStm + 134) - *((_DWORD *)pStm + 135),
            v63[1]);
      }
      else
      {
        appended = CMFMemoryBuffer::CreateInstance(v27, v12, &v60);
        if ( appended < 0 )
        {
          v36 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v37 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v12, v35);
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
            v38 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v36);
            if ( *((_DWORD *)v38 + 499) != appended )
              CallStackContext::TraceFailure(
                v38,
                "CPMPSharedMediaEventReadQueue::DeserializeFragmentedSampleHeader",
                1015,
                appended);
          }
          if ( !g_wppLevels )
            goto LABEL_127;
          v17 = 109;
          goto LABEL_126;
        }
        appended = ((__int64 (__fastcall *)(struct IMFMediaBuffer *, _QWORD))v60->lpVtbl->SetCurrentLength)(v60, v27);
        if ( appended < 0 )
        {
          v40 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v41 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v12, v39);
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
            if ( *((_DWORD *)v42 + 499) != appended )
              CallStackContext::TraceFailure(
                v42,
                "CPMPSharedMediaEventReadQueue::DeserializeFragmentedSampleHeader",
                1016,
                appended);
          }
          if ( !g_wppLevels )
            goto LABEL_127;
          v17 = 110;
          goto LABEL_126;
        }
        appended = ((__int64 (__fastcall *)(struct IMFMediaBuffer *, _DWORD *, _QWORD, _DWORD *))v60->lpVtbl->Lock)(
                     v60,
                     v5 + 10,
                     0,
                     v5 + 12);
        if ( appended < 0 )
        {
          v44 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v45 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v12, v43);
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
            if ( *((_DWORD *)v46 + 499) != appended )
              CallStackContext::TraceFailure(
                v46,
                "CPMPSharedMediaEventReadQueue::DeserializeFragmentedSampleHeader",
                1018,
                appended);
          }
          if ( !g_wppLevels )
            goto LABEL_127;
          v17 = 111;
          goto LABEL_126;
        }
        appended = ((__int64 (__fastcall *)(IMFSample *, struct IMFMediaBuffer *))ppIMFSample->lpVtbl->AddBuffer)(
                     ppIMFSample,
                     v60);
        if ( appended < 0 )
        {
          v48 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v49 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v12, v47);
            CallStackTracing::s_wpInstance = v49;
            if ( v49 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v49 + 8LL))(v49, 2032) )
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
            if ( *((_DWORD *)v50 + 499) != appended )
              CallStackContext::TraceFailure(
                v50,
                "CPMPSharedMediaEventReadQueue::DeserializeFragmentedSampleHeader",
                1020,
                appended);
          }
          if ( !g_wppLevels )
            goto LABEL_127;
          v17 = 112;
          goto LABEL_126;
        }
        if ( (unsigned __int8)byte_1803CECEC >= 0x10u )
          WPP_SF_qddd(
            *((_QWORD *)WPP_GLOBAL_Control + 22),
            113,
            &WPP_be5c5516ab2437f8fba11fde691f58f8_Traceguids,
            this,
            v5[4],
            v27,
            *((_DWORD *)pStm + 134) - *((_DWORD *)pStm + 135));
      }
      if ( *((_DWORD *)pStm + 134) == *((_DWORD *)pStm + 135)
        || (appended = CPMPSharedMediaEventReadQueue::AppendSampleFragment(
                         this,
                         pStm,
                         (struct CPMPSharedMediaEventReadQueue::SAMPLE_STATE *)v5),
            appended >= 0) )
      {
        v55 = ppIMFSample;
        ppIMFSample = 0;
        ComSmartPtr<IMFMediaBuffer>::Attach(v5 + 6, v55);
        v56 = v60;
        v60 = 0;
        ComSmartPtr<IMFMediaBuffer>::Attach(v5 + 8, v56);
        v57 = *((_QWORD *)this + 35);
        *(_QWORD *)v5 = v57;
        *((_QWORD *)v5 + 1) = (char *)this + 280;
        *(_QWORD *)(v57 + 8) = v5;
        ++*((_DWORD *)this + 68);
        *((_QWORD *)this + 35) = v5;
        goto LABEL_129;
      }
      v52 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v53 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v12, v51);
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
        if ( *((_DWORD *)v54 + 499) != appended )
          CallStackContext::TraceFailure(
            v54,
            "CPMPSharedMediaEventReadQueue::DeserializeFragmentedSampleHeader",
            1033,
            appended);
      }
      if ( !g_wppLevels )
        goto LABEL_127;
      v17 = 115;
    }
    else
    {
      v14 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v15 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v12, v13);
        CallStackTracing::s_wpInstance = v15;
        if ( v15 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v15 + 8LL))(v15, 2032) )
        {
          v14 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v14 = &qword_1803CE250;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
        }
      }
      if ( *((_BYTE *)v14 + 8) )
      {
        v16 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v14);
        if ( *((_DWORD *)v16 + 499) != appended )
          CallStackContext::TraceFailure(
            v16,
            "CPMPSharedMediaEventReadQueue::DeserializeFragmentedSampleHeader",
            979,
            appended);
      }
      if ( !g_wppLevels )
        goto LABEL_127;
      v17 = 104;
    }
LABEL_126:
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v17,
      &WPP_be5c5516ab2437f8fba11fde691f58f8_Traceguids,
      this,
      appended);
LABEL_127:
    CPMPSharedMediaEventReadQueue::SAMPLE_STATE::`scalar deleting destructor'(
      (CPMPSharedMediaEventReadQueue::SAMPLE_STATE *)v5,
      v12);
    goto LABEL_129;
  }
  v8 = (__int64 *)CallStackTracing::s_wpInstance;
  appended = -2147024882;
  if ( !CallStackTracing::s_wpInstance )
  {
    v10 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v6, v7);
    CallStackTracing::s_wpInstance = v10;
    if ( v10 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v10 + 8LL))(v10, 2032) )
    {
      v8 = (__int64 *)CallStackTracing::s_wpInstance;
    }
    else
    {
      v8 = &qword_1803CE250;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
    }
  }
  if ( *((_BYTE *)v8 + 8) )
  {
    v11 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v8);
    if ( *((_DWORD *)v11 + 499) != -2147024882 )
      CallStackContext::TraceFailure(
        v11,
        "CPMPSharedMediaEventReadQueue::DeserializeFragmentedSampleHeader",
        977,
        -2147024882);
  }
  if ( g_wppLevels )
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      103,
      &WPP_be5c5516ab2437f8fba11fde691f58f8_Traceguids,
      this,
      -2147024882);
LABEL_129:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v59);
  ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&v60);
  ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&ppIMFSample);
  return (unsigned int)appended;
}

```

## disassembly

```asm
0x1801cb850  mov     [rsp-38h+arg_10], rbx
0x1801cb855  push    rbp
0x1801cb856  push    rsi
0x1801cb857  push    rdi
0x1801cb858  push    r12
0x1801cb85a  push    r13
0x1801cb85c  push    r14
0x1801cb85e  push    r15
0x1801cb860  mov     rbp, rsp
0x1801cb863  sub     rsp, 80h
0x1801cb86a  mov     rax, cs:__security_cookie
0x1801cb871  xor     rax, rsp
0x1801cb874  mov     [rbp+var_10], rax
0x1801cb878  xor     r13d, r13d
0x1801cb87b  mov     rsi, rcx
0x1801cb87e  mov     r14, rdx
0x1801cb881  mov     [rbp+ppIMFSample], r13
0x1801cb885  mov     [rbp+var_38], r13
0x1801cb889  lea     ecx, [r13+40h]; Size
0x1801cb88d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1801cb892  mov     rdi, rax
0x1801cb895  test    rax, rax
0x1801cb898  jz      short loc_1801CB8B4
0x1801cb89a  mov     [rax+10h], r13d
0x1801cb89e  mov     [rax+18h], r13
0x1801cb8a2  mov     [rax+20h], r13
0x1801cb8a6  mov     [rax+28h], r13
0x1801cb8aa  mov     [rax+30h], r13
0x1801cb8ae  mov     [rax+38h], r13
0x1801cb8b2  jmp     short loc_1801CB8B7
0x1801cb8b4  mov     rdi, r13
0x1801cb8b7  mov     r12d, 3D1h
0x1801cb8bd  lea     r15, aCpmpsharedmedi_12; "CPMPSharedMediaEventReadQueue::Deserial"...
0x1801cb8c4  mov     r8d, r12d; int
0x1801cb8c7  lea     rcx, [rbp+var_40]; this
0x1801cb8cb  mov     rdx, r15; char *
0x1801cb8ce  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1801cb8d3  test    rdi, rdi
0x1801cb8d6  jnz     loc_1801CB98E
0x1801cb8dc  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801cb8e3  mov     ebx, 8007000Eh
0x1801cb8e8  test    rcx, rcx
0x1801cb8eb  jnz     short loc_1801CB935
0x1801cb8ed  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1801cb8f4  nop     dword ptr [rax+rax+00h]
0x1801cb8f9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1801cb900  mov     rcx, rax
0x1801cb903  test    rax, rax
0x1801cb906  jz      short loc_1801CB927
0x1801cb908  mov     rax, [rax]
0x1801cb90b  mov     edx, 7F0h
0x1801cb910  mov     rax, [rax+8]
0x1801cb914  call    cs:__guard_dispatch_icall_fptr
0x1801cb91a  test    eax, eax
0x1801cb91c  jz      short loc_1801CB927
0x1801cb91e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801cb925  jmp     short loc_1801CB935
0x1801cb927  lea     rcx, qword_1803CE250; this
0x1801cb92e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1801cb935  cmp     [rcx+8], r13b
0x1801cb939  jz      short loc_1801CB959
0x1801cb93b  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1801cb940  cmp     [rax+7CCh], ebx
0x1801cb946  jz      short loc_1801CB959
0x1801cb948  mov     r9d, ebx; int
0x1801cb94b  mov     r8d, r12d; int
0x1801cb94e  mov     rdx, r15; char *
0x1801cb951  mov     rcx, rax; this
0x1801cb954  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1801cb959  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1801cb960  jb      loc_1801CC173
0x1801cb966  mov     rcx, cs:WPP_GLOBAL_Control
0x1801cb96d  lea     r8, WPP_be5c5516ab2437f8fba11fde691f58f8_Traceguids
0x1801cb974  mov     edx, 67h ; 'g'
0x1801cb979  mov     [rsp+80h+var_60], ebx
0x1801cb97d  mov     r9, rsi
0x1801cb980  mov     rcx, [rcx+10h]
0x1801cb984  call    WPP_SF_qD
0x1801cb989  jmp     loc_1801CC173
0x1801cb98e  lea     rcx, [rbp+ppIMFSample]; ppIMFSample
0x1801cb992  call    cs:__imp_MFCreateSample
0x1801cb999  nop     dword ptr [rax+rax+00h]
0x1801cb99e  mov     ebx, eax
0x1801cb9a0  test    eax, eax
0x1801cb9a2  jns     loc_1801CBA3A
0x1801cb9a8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801cb9af  test    rcx, rcx
0x1801cb9b2  jnz     short loc_1801CB9FC
0x1801cb9b4  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1801cb9bb  nop     dword ptr [rax+rax+00h]
0x1801cb9c0  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1801cb9c7  mov     rcx, rax
0x1801cb9ca  test    rax, rax
0x1801cb9cd  jz      short loc_1801CB9EE
0x1801cb9cf  mov     rax, [rax]
0x1801cb9d2  mov     edx, 7F0h
0x1801cb9d7  mov     rax, [rax+8]
0x1801cb9db  call    cs:__guard_dispatch_icall_fptr
0x1801cb9e1  test    eax, eax
0x1801cb9e3  jz      short loc_1801CB9EE
0x1801cb9e5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801cb9ec  jmp     short loc_1801CB9FC
0x1801cb9ee  lea     rcx, qword_1803CE250; this
0x1801cb9f5  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1801cb9fc  cmp     [rcx+8], r13b
0x1801cba00  jz      short loc_1801CBA23
0x1801cba02  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1801cba07  cmp     [rax+7CCh], ebx
0x1801cba0d  jz      short loc_1801CBA23
0x1801cba0f  mov     r9d, ebx; int
0x1801cba12  mov     r8d, 3D3h; int
0x1801cba18  mov     rdx, r15; char *
0x1801cba1b  mov     rcx, rax; this
0x1801cba1e  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1801cba23  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1801cba2a  jb      loc_1801CC129
0x1801cba30  mov     edx, 68h ; 'h'
0x1801cba35  jmp     loc_1801CC10B
0x1801cba3a  mov     rdx, [rbp+ppIMFSample]; pAttr
0x1801cba3e  mov     rcx, r14; pStm
0x1801cba41  call    ?Deserialize@CSamplePropBinaryReader@@SAJAEAVCBufferReader@@PEAUIMFSample@@@Z; CSamplePropBinaryReader::Deserialize(CBufferReader &,IMFSample *)
0x1801cba46  mov     ebx, eax
0x1801cba48  test    eax, eax
0x1801cba4a  jns     loc_1801CBAE2
0x1801cba50  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801cba57  test    rcx, rcx
0x1801cba5a  jnz     short loc_1801CBAA4
0x1801cba5c  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1801cba63  nop     dword ptr [rax+rax+00h]
0x1801cba68  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1801cba6f  mov     rcx, rax
0x1801cba72  test    rax, rax
0x1801cba75  jz      short loc_1801CBA96
0x1801cba77  mov     rax, [rax]
0x1801cba7a  mov     edx, 7F0h
0x1801cba7f  mov     rax, [rax+8]
0x1801cba83  call    cs:__guard_dispatch_icall_fptr
0x1801cba89  test    eax, eax
0x1801cba8b  jz      short loc_1801CBA96
0x1801cba8d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801cba94  jmp     short loc_1801CBAA4
0x1801cba96  lea     rcx, qword_1803CE250; this
0x1801cba9d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1801cbaa4  cmp     [rcx+8], r13b
0x1801cbaa8  jz      short loc_1801CBACB
0x1801cbaaa  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1801cbaaf  cmp     [rax+7CCh], ebx
0x1801cbab5  jz      short loc_1801CBACB
0x1801cbab7  mov     r9d, ebx; int
0x1801cbaba  mov     r8d, 3D6h; int
0x1801cbac0  mov     rdx, r15; char *
0x1801cbac3  mov     rcx, rax; this
0x1801cbac6  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1801cbacb  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1801cbad2  jb      loc_1801CC129
0x1801cbad8  mov     edx, 69h ; 'i'
0x1801cbadd  jmp     loc_1801CC10B
0x1801cbae2  xor     eax, eax
0x1801cbae4  lea     rcx, [r14+208h]
0x1801cbaeb  mov     qword ptr [rbp+var_20], rax
0x1801cbaef  lea     rdx, [rbp+var_20]
0x1801cbaf3  mov     [rbp+var_18], eax
0x1801cbaf6  mov     r8d, 0Ch
0x1801cbafc  mov     rax, [rcx]
0x1801cbaff  mov     rax, [rax]
0x1801cbb02  call    cs:__guard_dispatch_icall_fptr
0x1801cbb08  mov     ebx, eax
0x1801cbb0a  test    eax, eax
0x1801cbb0c  jns     loc_1801CBBA4
0x1801cbb12  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801cbb19  test    rcx, rcx
0x1801cbb1c  jnz     short loc_1801CBB66
0x1801cbb1e  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1801cbb25  nop     dword ptr [rax+rax+00h]
0x1801cbb2a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1801cbb31  mov     rcx, rax
0x1801cbb34  test    rax, rax
0x1801cbb37  jz      short loc_1801CBB58
0x1801cbb39  mov     rax, [rax]
0x1801cbb3c  mov     edx, 7F0h
0x1801cbb41  mov     rax, [rax+8]
0x1801cbb45  call    cs:__guard_dispatch_icall_fptr
0x1801cbb4b  test    eax, eax
0x1801cbb4d  jz      short loc_1801CBB58
0x1801cbb4f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801cbb56  jmp     short loc_1801CBB66
0x1801cbb58  lea     rcx, qword_1803CE250; this
0x1801cbb5f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1801cbb66  cmp     [rcx+8], r13b
0x1801cbb6a  jz      short loc_1801CBB8D
0x1801cbb6c  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1801cbb71  cmp     [rax+7CCh], ebx
0x1801cbb77  jz      short loc_1801CBB8D
0x1801cbb79  mov     r9d, ebx; int
0x1801cbb7c  mov     r8d, 3DBh; int
0x1801cbb82  mov     rdx, r15; char *
0x1801cbb85  mov     rcx, rax; this
0x1801cbb88  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1801cbb8d  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1801cbb94  jb      loc_1801CC129
0x1801cbb9a  mov     edx, 6Ah ; 'j'
0x1801cbb9f  jmp     loc_1801CC10B
0x1801cbba4  mov     rcx, [rbp+ppIMFSample]
0x1801cbba8  lea     rdx, [rbp+var_28]
0x1801cbbac  mov     [rbp+var_28], r13d
0x1801cbbb0  mov     rax, [rcx]
0x1801cbbb3  mov     rax, [rax+108h]
0x1801cbbba  call    cs:__guard_dispatch_icall_fptr
0x1801cbbc0  mov     ecx, [rbp+var_20+4]
0x1801cbbc3  mov     eax, [rbp+var_18]
0x1801cbbc6  mov     r12d, [rbp+var_20]
0x1801cbbca  mov     [rdi+10h], eax
0x1801cbbcd  mov     edx, [rbp+var_18]; unsigned int
0x1801cbbd0  cmp     ecx, 1
0x1801cbbd3  jbe     short loc_1801CBBE6
0x1801cbbd5  test    [rbp+var_28], 100h
0x1801cbbdc  jz      short loc_1801CBBE6
0x1801cbbde  mov     r15d, 1Eh
0x1801cbbe4  jmp     short loc_1801CBBEE
0x1801cbbe6  mov     r15d, r13d
0x1801cbbe9  mov     ecx, 1
0x1801cbbee  mov     [rdi+38h], ecx
0x1801cbbf1  xor     r9d, r9d; struct _LIST_ENTRY **
0x1801cbbf4  mov     rcx, rsi; this
0x1801cbbf7  xor     r8d, r8d; struct CPMPSharedMediaEventReadQueue::SAMPLE_STATE **
0x1801cbbfa  call    ?LookupSampleState@CPMPSharedMediaEventReadQueue@@IEAAJKPEAPEAUSAMPLE_STATE@1@PEAPEAU_LIST_ENTRY@@@Z; CPMPSharedMediaEventReadQueue::LookupSampleState(ulong,CPMPSharedMediaEventReadQueue::SAMPLE_STATE * *,_LIST_ENTRY * *)
0x1801cbbff  cmp     eax, 0C00D36D5h
0x1801cbc04  jz      loc_1801CBCD6
0x1801cbc0a  cmp     cs:byte_1803CECEC, 1
0x1801cbc11  jb      short loc_1801CBC3B
0x1801cbc13  mov     rcx, cs:WPP_GLOBAL_Control
0x1801cbc1a  lea     edx, [r9+6Bh]
0x1801cbc1e  mov     eax, [rdi+10h]
0x1801cbc21  lea     r8, WPP_be5c5516ab2437f8fba11fde691f58f8_Traceguids
0x1801cbc28  mov     r9, rsi
0x1801cbc2b  mov     [rsp+80h+var_60], eax
0x1801cbc2f  mov     rcx, [rcx+0B0h]
0x1801cbc36  call    WPP_SF_qD
0x1801cbc3b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801cbc42  mov     ebx, 0C00D36BBh
0x1801cbc47  test    rcx, rcx
0x1801cbc4a  jnz     short loc_1801CBC94
0x1801cbc4c  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1801cbc53  nop     dword ptr [rax+rax+00h]
0x1801cbc58  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1801cbc5f  mov     rcx, rax
0x1801cbc62  test    rax, rax
0x1801cbc65  jz      short loc_1801CBC86
0x1801cbc67  mov     rax, [rax]
0x1801cbc6a  mov     edx, 7F0h
0x1801cbc6f  mov     rax, [rax+8]
0x1801cbc73  call    cs:__guard_dispatch_icall_fptr
0x1801cbc79  test    eax, eax
0x1801cbc7b  jz      short loc_1801CBC86
0x1801cbc7d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801cbc84  jmp     short loc_1801CBC94
0x1801cbc86  lea     rcx, qword_1803CE250; this
0x1801cbc8d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1801cbc94  cmp     [rcx+8], r13b
0x1801cbc98  jz      short loc_1801CBCBF
0x1801cbc9a  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1801cbc9f  cmp     [rax+7CCh], ebx
0x1801cbca5  jz      short loc_1801CBCBF
0x1801cbca7  mov     r9d, ebx; int
0x1801cbcaa  lea     rdx, aCpmpsharedmedi_12; "CPMPSharedMediaEventReadQueue::Deserial"...
0x1801cbcb1  mov     r8d, 3F1h; int
0x1801cbcb7  mov     rcx, rax; this
0x1801cbcba  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1801cbcbf  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1801cbcc6  jb      loc_1801CC129
0x1801cbccc  mov     edx, 6Ch ; 'l'
0x1801cbcd1  jmp     loc_1801CC10B
0x1801cbcd6  test    r15d, r15d
0x1801cbcd9  jnz     loc_1801CC002
0x1801cbcdf  lea     r8, [rbp+var_38]; struct IMFMediaBuffer **
0x1801cbce3  mov     ecx, r12d; unsigned int
0x1801cbce6  call    ?CreateInstance@CMFMemoryBuffer@@SAJKKPEAPEAUIMFMediaBuffer@@@Z; CMFMemoryBuffer::CreateInstance(ulong,ulong,IMFMediaBuffer * *)
0x1801cbceb  mov     ebx, eax
0x1801cbced  test    eax, eax
0x1801cbcef  jns     loc_1801CBD8B
0x1801cbcf5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801cbcfc  test    rcx, rcx
0x1801cbcff  jnz     short loc_1801CBD49
0x1801cbd01  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1801cbd08  nop     dword ptr [rax+rax+00h]
0x1801cbd0d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1801cbd14  mov     rcx, rax
0x1801cbd17  test    rax, rax
0x1801cbd1a  jz      short loc_1801CBD3B
0x1801cbd1c  mov     rax, [rax]
0x1801cbd1f  mov     edx, 7F0h
0x1801cbd24  mov     rax, [rax+8]
0x1801cbd28  call    cs:__guard_dispatch_icall_fptr
0x1801cbd2e  test    eax, eax
0x1801cbd30  jz      short loc_1801CBD3B
0x1801cbd32  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801cbd39  jmp     short loc_1801CBD49
0x1801cbd3b  lea     rcx, qword_1803CE250; this
0x1801cbd42  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1801cbd49  cmp     [rcx+8], r13b
  ... truncated ...
```
