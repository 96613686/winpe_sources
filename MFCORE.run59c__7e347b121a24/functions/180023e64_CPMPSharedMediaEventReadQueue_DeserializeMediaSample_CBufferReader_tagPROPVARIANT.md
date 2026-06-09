# CPMPSharedMediaEventReadQueue::DeserializeMediaSample(CBufferReader &,tagPROPVARIANT *)

- ea: `0x180023e64`
- end: `0x1800249e6`
- name: `?DeserializeMediaSample@CPMPSharedMediaEventReadQueue@@IEAAJAEAVCBufferReader@@PEAUtagPROPVARIANT@@@Z`
- size: `2946`
- prototype: `int(CPMPSharedMediaEventReadQueue *__hidden this, struct CBufferReader *, struct tagPROPVARIANT *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config`

## callers

- `0x180023860`

## callees

- `0x18001616c`
- `0x180023e64`
- `0x1800249ec`
- `0x180024c3c`
- `0x18003ecb0`
- `0x1800402c0`
- `0x180050d6c`
- `0x1800ec0e0`
- `0x1801854f4`
- `0x180258480`
- `0x180344d40`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002431c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800243b0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180024444`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800244fa`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180024592`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002462a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800246c2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002475a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002487c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180024914`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002431c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800243b0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180024444`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800244fa`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180024592`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002462a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800246c2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002475a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002487c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180024914`
- `MFPlat!MFCreateSample` at `0x180023ef6`
- `MFPlat!MFCreateSample` at `0x180023ef6`

## string_xrefs

- `0x180023eba`: `CPMPSharedMediaEventReadQueue::DeserializeMediaSample`
- `0x1800244d7`: `CPMPSharedMediaEventReadQueue::DeserializeMediaSample`
- `0x18002456f`: `CPMPSharedMediaEventReadQueue::DeserializeMediaSample`
- `0x180024607`: `CPMPSharedMediaEventReadQueue::DeserializeMediaSample`
- `0x18002469f`: `CPMPSharedMediaEventReadQueue::DeserializeMediaSample`
- `0x180024737`: `CPMPSharedMediaEventReadQueue::DeserializeMediaSample`
- `0x1800247cf`: `CPMPSharedMediaEventReadQueue::DeserializeMediaSample`
- `0x1800247fa`: `CPMPSharedMediaEventReadQueue::DeserializeMediaSample`
- `0x180024828`: `CPMPSharedMediaEventReadQueue::DeserializeMediaSample`
- `0x180024856`: `CPMPSharedMediaEventReadQueue::DeserializeMediaSample`
- `0x1800248f1`: `CPMPSharedMediaEventReadQueue::DeserializeMediaSample`
- `0x180024989`: `CPMPSharedMediaEventReadQueue::DeserializeMediaSample`

## pseudocode

```c
__int64 __fastcall CPMPSharedMediaEventReadQueue::DeserializeMediaSample(
        CPMPSharedMediaEventReadQueue *this,
        struct CBufferReader *a2,
        struct tagPROPVARIANT *a3)
{
  unsigned int v3; // r14d
  CallStackTracing *v5; // rcx
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v9; // rcx
  __int64 v10; // rcx
  HRESULT v11; // ebx
  __int64 v12; // rdx
  __int64 v13; // r8
  char *v14; // rsi
  __int64 v15; // rdx
  __int64 v16; // r8
  unsigned int v17; // edx
  unsigned int v18; // r12d
  unsigned int v19; // r15d
  __int64 v20; // rdx
  __int64 v21; // r8
  __int64 v22; // rdx
  __int64 v23; // r8
  IMFSample *v24; // rcx
  CallStackTracing *v26; // rcx
  __int64 v27; // rdx
  __int64 (__fastcall **v28)(char *, _OWORD *, __int64); // rax
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
  __int64 v39; // rdx
  __int64 v40; // r8
  CallStackTracing *v41; // rcx
  CallStackTracing *v42; // rcx
  CallStackTracing *v43; // rcx
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
  __int64 *v57; // rcx
  CallStackTracing *v58; // rax
  struct CallStackContext *v59; // rax
  __int64 *v60; // rcx
  CallStackTracing *v61; // rax
  struct CallStackContext *v62; // rax
  __int64 *v63; // rcx
  CallStackTracing *v64; // rax
  struct CallStackContext *v65; // rax
  __int64 *v66; // rcx
  CallStackTracing *v67; // rax
  struct CallStackContext *v68; // rax
  struct CallStackContext *v69; // rax
  struct CallStackContext *v70; // rax
  struct CallStackContext *v71; // rax
  __int64 *v72; // rcx
  CallStackTracing *v73; // rax
  struct CallStackContext *v74; // rax
  __int64 *v75; // rcx
  CallStackTracing *v76; // rax
  struct CallStackContext *v77; // rax
  struct IMFMediaBuffer *v78; // [rsp+30h] [rbp-39h] BYREF
  IMFSample *ppIMFSample; // [rsp+38h] [rbp-31h] BYREF
  _BYTE v80[8]; // [rsp+40h] [rbp-29h] BYREF
  __int64 v81; // [rsp+48h] [rbp-21h] BYREF
  int v82; // [rsp+50h] [rbp-19h] BYREF
  int v83; // [rsp+54h] [rbp-15h] BYREF
  unsigned int v84[2]; // [rsp+58h] [rbp-11h] BYREF
  int v85; // [rsp+60h] [rbp-9h]
  _OWORD v86[2]; // [rsp+68h] [rbp-1h] BYREF

  v3 = 0;
  v5 = CallStackTracing::s_wpInstance;
  ppIMFSample = 0;
  v78 = 0;
  v81 = 0;
  v83 = 0;
  if ( !CallStackTracing::s_wpInstance )
  {
    CallStackTracing::InitInstance();
    v5 = CallStackTracing::s_wpInstance;
  }
  if ( *((_BYTE *)v5 + 8) )
  {
    ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(v5);
    v9 = *((unsigned int *)ThreadRelativeContext + 497);
    if ( (unsigned int)v9 < *((_DWORD *)ThreadRelativeContext + 498) )
    {
      v10 = 2 * v9;
      *((_QWORD *)ThreadRelativeContext + v10) = "CPMPSharedMediaEventReadQueue::DeserializeMediaSample";
      *((_DWORD *)ThreadRelativeContext + 2 * v10 + 2) = 893;
    }
    ++*((_DWORD *)ThreadRelativeContext + 497);
  }
  v11 = MFCreateSample(&ppIMFSample);
  if ( v11 < 0 )
  {
    v26 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::InitInstance();
      v26 = CallStackTracing::s_wpInstance;
    }
    if ( *((_BYTE *)v26 + 8) )
    {
      v44 = CallStackTracing::GetThreadRelativeContext(v26);
      if ( *((_DWORD *)v44 + 499) != v11 )
        CallStackContext::TraceFailure(v44, "CPMPSharedMediaEventReadQueue::DeserializeMediaSample", 893, v11);
    }
    if ( !g_wppLevels )
      goto LABEL_19;
    v27 = 88;
LABEL_87:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v27, &WPP_be5c5516ab2437f8fba11fde691f58f8_Traceguids, this, v11);
    goto LABEL_19;
  }
  v11 = CSamplePropBinaryReader::Deserialize(a2, (IMFAttributes *)ppIMFSample);
  if ( v11 < 0 )
  {
    v45 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v46 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v12, v13);
      CallStackTracing::s_wpInstance = v46;
      if ( v46 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v46 + 8LL))(v46, 2032) )
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
      if ( *((_DWORD *)v47 + 499) != v11 )
        CallStackContext::TraceFailure(v47, "CPMPSharedMediaEventReadQueue::DeserializeMediaSample", 896, v11);
    }
    if ( !g_wppLevels )
      goto LABEL_19;
    v27 = 89;
    goto LABEL_87;
  }
  *(_QWORD *)v84 = 0;
  v14 = (char *)a2 + 520;
  v85 = 0;
  v11 = (**(__int64 (__fastcall ***)(char *, unsigned int *, __int64))v14)(v14, v84, 12);
  if ( v11 < 0 )
  {
    v48 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v49 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v15, v16);
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
      if ( *((_DWORD *)v50 + 499) != v11 )
        CallStackContext::TraceFailure(v50, "CPMPSharedMediaEventReadQueue::DeserializeMediaSample", 901, v11);
    }
    if ( !g_wppLevels )
      goto LABEL_19;
    v27 = 90;
    goto LABEL_87;
  }
  v82 = 0;
  ((void (__fastcall *)(IMFSample *, int *))ppIMFSample->lpVtbl->GetSampleFlags)(ppIMFSample, &v82);
  v18 = v84[1];
  v19 = v84[0];
  if ( v84[1] > 1 && (v82 & 0x100) != 0 )
  {
    while ( v3 < v18 )
    {
      v28 = *(__int64 (__fastcall ***)(char *, _OWORD *, __int64))v14;
      memset(v86, 0, 30);
      v11 = (*v28)(v14, v86, 30);
      if ( v11 < 0 )
      {
        v66 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v67 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v29, v30);
          CallStackTracing::s_wpInstance = v67;
          if ( v67 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v67 + 8LL))(v67, 2032) )
          {
            v66 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v66 = &qword_1803CE250;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
          }
        }
        if ( *((_BYTE *)v66 + 8) )
        {
          v68 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v66);
          if ( *((_DWORD *)v68 + 499) != v11 )
            CallStackContext::TraceFailure(v68, "CPMPSharedMediaEventReadQueue::DeserializeMediaSample", 927, v11);
        }
        if ( g_wppLevels )
        {
          v27 = 96;
          goto LABEL_87;
        }
        goto LABEL_19;
      }
      v11 = CMFMemoryBuffer::CreateInstance(DWORD1(v86[1]), v29, &v78);
      if ( v11 < 0 )
      {
        v63 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v64 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v31, v32);
          CallStackTracing::s_wpInstance = v64;
          if ( v64 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v64 + 8LL))(v64, 2032) )
          {
            v63 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v63 = &qword_1803CE250;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
          }
        }
        if ( *((_BYTE *)v63 + 8) )
        {
          v65 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v63);
          if ( *((_DWORD *)v65 + 499) != v11 )
            CallStackContext::TraceFailure(v65, "CPMPSharedMediaEventReadQueue::DeserializeMediaSample", 929, v11);
        }
        if ( g_wppLevels )
        {
          v27 = 97;
          goto LABEL_87;
        }
        goto LABEL_19;
      }
      v11 = MultiSampleHeader::Deserialize((MultiSampleHeader *)v86, v78);
      if ( v11 < 0 )
      {
        v60 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v61 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v33, v34);
          CallStackTracing::s_wpInstance = v61;
          if ( v61 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v61 + 8LL))(v61, 2032) )
          {
            v60 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v60 = &qword_1803CE250;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
          }
        }
        if ( *((_BYTE *)v60 + 8) )
        {
          v62 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v60);
          if ( *((_DWORD *)v62 + 499) != v11 )
            CallStackContext::TraceFailure(v62, "CPMPSharedMediaEventReadQueue::DeserializeMediaSample", 932, v11);
        }
        if ( g_wppLevels )
        {
          v27 = 98;
          goto LABEL_87;
        }
        goto LABEL_19;
      }
      v11 = ((__int64 (__fastcall *)(struct IMFMediaBuffer *, __int64 *, _QWORD, int *))v78->lpVtbl->Lock)(
              v78,
              &v81,
              0,
              &v83);
      if ( v11 < 0 )
      {
        v57 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v58 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v35, v36);
          CallStackTracing::s_wpInstance = v58;
          if ( v58 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v58 + 8LL))(v58, 2032) )
          {
            v57 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v57 = &qword_1803CE250;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
          }
        }
        if ( *((_BYTE *)v57 + 8) )
        {
          v59 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v57);
          if ( *((_DWORD *)v59 + 499) != v11 )
            CallStackContext::TraceFailure(v59, "CPMPSharedMediaEventReadQueue::DeserializeMediaSample", 934, v11);
        }
        if ( g_wppLevels )
        {
          v27 = 99;
          goto LABEL_87;
        }
        goto LABEL_19;
      }
      v11 = (**(__int64 (__fastcall ***)(char *, __int64, _QWORD))v14)(v14, v81, DWORD1(v86[1]));
      if ( v11 < 0 )
      {
        v54 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v55 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v37, v38);
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
          if ( *((_DWORD *)v56 + 499) != v11 )
            CallStackContext::TraceFailure(v56, "CPMPSharedMediaEventReadQueue::DeserializeMediaSample", 935, v11);
        }
        if ( g_wppLevels )
        {
          v27 = 100;
          goto LABEL_87;
        }
        goto LABEL_19;
      }
      ((void (__fastcall *)(struct IMFMediaBuffer *))v78->lpVtbl->Unlock)(v78);
      v81 = 0;
      v11 = ((__int64 (__fastcall *)(IMFSample *, struct IMFMediaBuffer *))ppIMFSample->lpVtbl->AddBuffer)(
              ppIMFSample,
              v78);
      if ( v11 < 0 )
      {
        v51 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v52 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v39, v40);
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
          if ( *((_DWORD *)v53 + 499) != v11 )
            CallStackContext::TraceFailure(v53, "CPMPSharedMediaEventReadQueue::DeserializeMediaSample", 939, v11);
        }
        if ( g_wppLevels )
        {
          v27 = 101;
          goto LABEL_87;
        }
        goto LABEL_19;
      }
      if ( v78 )
      {
        ((void (__fastcall *)(struct IMFMediaBuffer *))v78->lpVtbl->Release)(v78);
        v78 = 0;
      }
      ++v3;
    }
    goto LABEL_16;
  }
  v11 = CMFMemoryBuffer::CreateInstance(v84[0], v17, &v78);
  if ( v11 < 0 )
  {
    v41 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::InitInstance();
      v41 = CallStackTracing::s_wpInstance;
    }
    if ( *((_BYTE *)v41 + 8) )
    {
      v69 = CallStackTracing::GetThreadRelativeContext(v41);
      if ( *((_DWORD *)v69 + 499) != v11 )
        CallStackContext::TraceFailure(v69, "CPMPSharedMediaEventReadQueue::DeserializeMediaSample", 915, v11);
    }
    if ( !g_wppLevels )
      goto LABEL_19;
    v27 = 91;
    goto LABEL_87;
  }
  v11 = ((__int64 (__fastcall *)(struct IMFMediaBuffer *, __int64 *, _QWORD, int *))v78->lpVtbl->Lock)(
          v78,
          &v81,
          0,
          &v83);
  if ( v11 < 0 )
  {
    v42 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::InitInstance();
      v42 = CallStackTracing::s_wpInstance;
    }
    if ( *((_BYTE *)v42 + 8) )
    {
      v70 = CallStackTracing::GetThreadRelativeContext(v42);
      if ( *((_DWORD *)v70 + 499) != v11 )
        CallStackContext::TraceFailure(v70, "CPMPSharedMediaEventReadQueue::DeserializeMediaSample", 916, v11);
    }
    if ( !g_wppLevels )
      goto LABEL_19;
    v27 = 92;
    goto LABEL_87;
  }
  v11 = (**(__int64 (__fastcall ***)(char *, __int64, _QWORD))v14)(v14, v81, v19);
  if ( v11 < 0 )
  {
    v43 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::InitInstance();
      v43 = CallStackTracing::s_wpInstance;
    }
    if ( *((_BYTE *)v43 + 8) )
    {
      v71 = CallStackTracing::GetThreadRelativeContext(v43);
      if ( *((_DWORD *)v71 + 499) != v11 )
        CallStackContext::TraceFailure(v71, "CPMPSharedMediaEventReadQueue::DeserializeMediaSample", 917, v11);
    }
    if ( !g_wppLevels )
      goto LABEL_19;
    v27 = 93;
    goto LABEL_87;
  }
  v11 = ((__int64 (__fastcall *)(struct IMFMediaBuffer *, _QWORD))v78->lpVtbl->SetCurrentLength)(v78, v19);
  if ( v11 < 0 )
  {
    v72 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v73 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v20, v21);
      CallStackTracing::s_wpInstance = v73;
      if ( v73 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v73 + 8LL))(v73, 2032) )
      {
        v72 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v72 = &qword_1803CE250;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
      }
    }
    if ( *((_BYTE *)v72 + 8) )
    {
      v74 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v72);
      if ( *((_DWORD *)v74 + 499) != v11 )
        CallStackContext::TraceFailure(v74, "CPMPSharedMediaEventReadQueue::DeserializeMediaSample", 918, v11);
    }
    if ( !g_wppLevels )
      goto LABEL_19;
    v27 = 94;
    goto LABEL_87;
  }
  v11 = ((__int64 (__fastcall *)(IMFSample *, struct IMFMediaBuffer *))ppIMFSample->lpVtbl->AddBuffer)(ppIMFSample, v78);
  if ( v11 >= 0 )
  {
LABEL_16:
    if ( (unsigned __int8)byte_1803CECEC >= 0x10u )
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 22), 102, &WPP_be5c5516ab2437f8fba11fde691f58f8_Traceguids, this, v19);
    v24 = ppIMFSample;
    a3->vt = 13;
    a3->hVal.QuadPart = (LONGLONG)v24;
    ((void (__fastcall *)(IMFSample *))v24->lpVtbl->AddRef)(v24);
    goto LABEL_19;
  }
  v75 = (__int64 *)CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    v76 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v22, v23);
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
    if ( *((_DWORD *)v77 + 499) != v11 )
      CallStackContext::TraceFailure(v77, "CPMPSharedMediaEventReadQueue::DeserializeMediaSample", 919, v11);
  }
  if ( g_wppLevels )
  {
    v27 = 95;
    goto LABEL_87;
  }
LABEL_19:
  if ( v81 )
  {
    if ( !v78 )
      goto LABEL_22;
    ((void (__fastcall *)(struct IMFMediaBuffer *))v78->lpVtbl->Unlock)(v78);
  }
  if ( v78 )
  {
    ((void (__fastcall *)(struct IMFMediaBuffer *))v78->lpVtbl->Release)(v78);
    v78 = 0;
  }
LABEL_22:
  if ( ppIMFSample )
  {
    ((void (__fastcall *)(IMFSample *))ppIMFSample->lpVtbl->Release)(ppIMFSample);
    ppIMFSample = 0;
  }
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v80);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180023e64  mov     [rsp-8+arg_18], rbx
0x180023e69  push    rbp
0x180023e6a  push    rsi
0x180023e6b  push    rdi
0x180023e6c  push    r12
0x180023e6e  push    r13
0x180023e70  push    r14
0x180023e72  push    r15
0x180023e74  lea     rbp, [rsp-27h]
0x180023e79  sub     rsp, 90h
0x180023e80  mov     rax, cs:__security_cookie
0x180023e87  xor     rax, rsp
0x180023e8a  mov     [rbp+57h+var_38], rax
0x180023e8e  xor     r14d, r14d
0x180023e91  mov     rdi, rcx
0x180023e94  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180023e9b  mov     r13, r8
0x180023e9e  mov     [rbp+57h+ppIMFSample], r14
0x180023ea2  mov     rsi, rdx
0x180023ea5  mov     [rbp+57h+var_90], r14
0x180023ea9  mov     [rbp+57h+var_78], r14
0x180023ead  mov     [rbp+57h+var_6C], r14d
0x180023eb1  test    rcx, rcx
0x180023eb4  jz      loc_180024297
0x180023eba  lea     r15, aCpmpsharedmedi_11; "CPMPSharedMediaEventReadQueue::Deserial"...
0x180023ec1  mov     r12d, 37Dh
0x180023ec7  cmp     [rcx+8], r14b
0x180023ecb  jz      short loc_180023EF2
0x180023ecd  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180023ed2  mov     ecx, [rax+7C4h]
0x180023ed8  cmp     ecx, [rax+7C8h]
0x180023ede  jnb     short loc_180023EEC
0x180023ee0  add     rcx, rcx
0x180023ee3  mov     [rax+rcx*8], r15
0x180023ee7  mov     [rax+rcx*8+8], r12d
0x180023eec  inc     dword ptr [rax+7C4h]
0x180023ef2  lea     rcx, [rbp+57h+ppIMFSample]; ppIMFSample
0x180023ef6  call    cs:__imp_MFCreateSample
0x180023efd  nop     dword ptr [rax+rax+00h]
0x180023f02  mov     ebx, eax
0x180023f04  test    eax, eax
0x180023f06  js      loc_1800240CF
0x180023f0c  mov     rdx, [rbp+57h+ppIMFSample]; pAttr
0x180023f10  mov     rcx, rsi; pStm
0x180023f13  call    ?Deserialize@CSamplePropBinaryReader@@SAJAEAVCBufferReader@@PEAUIMFSample@@@Z; CSamplePropBinaryReader::Deserialize(CBufferReader &,IMFSample *)
0x180023f18  mov     ebx, eax
0x180023f1a  test    eax, eax
0x180023f1c  js      loc_180024310
0x180023f22  xor     eax, eax
0x180023f24  lea     rdx, [rbp+57h+var_68]
0x180023f28  mov     qword ptr [rbp+57h+var_68], rax
0x180023f2c  add     rsi, 208h
0x180023f33  mov     [rbp+57h+var_60], eax
0x180023f36  mov     r8d, 0Ch
0x180023f3c  mov     rcx, rsi
0x180023f3f  mov     rax, [rsi]
0x180023f42  mov     rax, [rax]
0x180023f45  call    cs:__guard_dispatch_icall_fptr
0x180023f4b  mov     ebx, eax
0x180023f4d  test    eax, eax
0x180023f4f  js      loc_1800243A4
0x180023f55  mov     rcx, [rbp+57h+ppIMFSample]
0x180023f59  lea     rdx, [rbp+57h+var_70]
0x180023f5d  mov     [rbp+57h+var_70], r14d
0x180023f61  mov     rax, [rcx]
0x180023f64  mov     rax, [rax+108h]
0x180023f6b  call    cs:__guard_dispatch_icall_fptr
0x180023f71  mov     r12d, [rbp+57h+var_68+4]
0x180023f75  mov     r15d, [rbp+57h+var_68]
0x180023f79  cmp     r12d, 1
0x180023f7d  ja      loc_180024100
0x180023f83  lea     r8, [rbp+57h+var_90]; struct IMFMediaBuffer **
0x180023f87  mov     ecx, r15d; unsigned int
0x180023f8a  call    ?CreateInstance@CMFMemoryBuffer@@SAJKKPEAPEAUIMFMediaBuffer@@@Z; CMFMemoryBuffer::CreateInstance(ulong,ulong,IMFMediaBuffer * *)
0x180023f8f  mov     ebx, eax
0x180023f91  test    eax, eax
0x180023f93  js      loc_180024208
0x180023f99  mov     rcx, [rbp+57h+var_90]
0x180023f9d  lea     r9, [rbp+57h+var_6C]
0x180023fa1  xor     r8d, r8d
0x180023fa4  lea     rdx, [rbp+57h+var_78]
0x180023fa8  mov     rax, [rcx]
0x180023fab  mov     rax, [rax+18h]
0x180023faf  call    cs:__guard_dispatch_icall_fptr
0x180023fb5  mov     ebx, eax
0x180023fb7  test    eax, eax
0x180023fb9  js      loc_180024239
0x180023fbf  mov     rax, [rsi]
0x180023fc2  mov     r8d, r15d
0x180023fc5  mov     rdx, [rbp+57h+var_78]
0x180023fc9  mov     rcx, rsi
0x180023fcc  mov     rax, [rax]
0x180023fcf  call    cs:__guard_dispatch_icall_fptr
0x180023fd5  mov     ebx, eax
0x180023fd7  test    eax, eax
0x180023fd9  js      loc_18002426A
0x180023fdf  mov     rcx, [rbp+57h+var_90]
0x180023fe3  mov     edx, r15d
0x180023fe6  mov     rax, [rcx]
0x180023fe9  mov     rax, [rax+30h]
0x180023fed  call    cs:__guard_dispatch_icall_fptr
0x180023ff3  mov     ebx, eax
0x180023ff5  test    eax, eax
0x180023ff7  js      loc_180024870
0x180023ffd  mov     rcx, [rbp+57h+ppIMFSample]
0x180024001  mov     rdx, [rbp+57h+var_90]
0x180024005  mov     rax, [rcx]
0x180024008  mov     rax, [rax+150h]
0x18002400f  call    cs:__guard_dispatch_icall_fptr
0x180024015  mov     ebx, eax
0x180024017  test    eax, eax
0x180024019  js      loc_180024908
0x18002401f  cmp     cs:byte_1803CECEC, 10h
0x180024026  jnb     loc_1800249BA
0x18002402c  mov     rcx, [rbp+57h+ppIMFSample]
0x180024030  mov     word ptr [r13+0], 0Dh
0x180024037  mov     [r13+8], rcx
0x18002403b  mov     rax, [rcx]
0x18002403e  mov     rax, [rax+8]
0x180024042  call    cs:__guard_dispatch_icall_fptr
0x180024048  xor     edi, edi
0x18002404a  cmp     [rbp+57h+var_78], rdi
0x18002404e  jnz     short loc_1800240B7
0x180024050  mov     rcx, [rbp+57h+var_90]
0x180024054  test    rcx, rcx
0x180024057  jz      short loc_18002406A
0x180024059  mov     rax, [rcx]
0x18002405c  mov     rax, [rax+10h]
0x180024060  call    cs:__guard_dispatch_icall_fptr
0x180024066  mov     [rbp+57h+var_90], rdi
0x18002406a  mov     rcx, [rbp+57h+ppIMFSample]
0x18002406e  test    rcx, rcx
0x180024071  jz      short loc_180024084
0x180024073  mov     rax, [rcx]
0x180024076  mov     rax, [rax+10h]
0x18002407a  call    cs:__guard_dispatch_icall_fptr
0x180024080  mov     [rbp+57h+ppIMFSample], rdi
0x180024084  lea     rcx, [rbp+57h+var_80]; this
0x180024088  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18002408d  mov     eax, ebx
0x18002408f  mov     rcx, [rbp+57h+var_38]
0x180024093  xor     rcx, rsp; StackCookie
0x180024096  call    __security_check_cookie
0x18002409b  mov     rbx, [rsp+0C0h+arg_18]
0x1800240a3  add     rsp, 90h
0x1800240aa  pop     r15
0x1800240ac  pop     r14
0x1800240ae  pop     r13
0x1800240b0  pop     r12
0x1800240b2  pop     rdi
0x1800240b3  pop     rsi
0x1800240b4  pop     rbp
0x1800240b5  retn
0x1800240b7  mov     rcx, [rbp+57h+var_90]
0x1800240bb  test    rcx, rcx
0x1800240be  jz      short loc_18002406A
0x1800240c0  mov     rax, [rcx]
0x1800240c3  mov     rax, [rax+20h]
0x1800240c7  call    cs:__guard_dispatch_icall_fptr
0x1800240cd  jmp     short loc_180024050
0x1800240cf  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800240d6  test    rcx, rcx
0x1800240d9  jz      loc_1800242A8
0x1800240df  cmp     [rcx+8], r14b
0x1800240e3  jnz     loc_1800242E9
0x1800240e9  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800240f0  jb      loc_180024048
0x1800240f6  mov     edx, 58h ; 'X'
0x1800240fb  jmp     loc_180024494
0x180024100  test    [rbp+57h+var_70], 100h
0x180024107  jz      loc_180023F83
0x18002410d  cmp     r14d, r12d
0x180024110  jnb     loc_18002401F
0x180024116  mov     rax, [rsi]
0x180024119  lea     rdx, [rbp+57h+var_58]
0x18002411d  xorps   xmm0, xmm0
0x180024120  mov     r8d, 1Eh
0x180024126  movups  [rbp+57h+var_58], xmm0
0x18002412a  mov     rcx, rsi
0x18002412d  mov     rax, [rax]
0x180024130  movups  [rbp+57h+var_58+0Eh], xmm0
0x180024134  call    cs:__guard_dispatch_icall_fptr
0x18002413a  mov     ebx, eax
0x18002413c  test    eax, eax
0x18002413e  js      loc_18002474E
0x180024144  mov     ecx, [rbp+57h+var_44]; unsigned int
0x180024147  lea     r8, [rbp+57h+var_90]; struct IMFMediaBuffer **
0x18002414b  call    ?CreateInstance@CMFMemoryBuffer@@SAJKKPEAPEAUIMFMediaBuffer@@@Z; CMFMemoryBuffer::CreateInstance(ulong,ulong,IMFMediaBuffer * *)
0x180024150  mov     ebx, eax
0x180024152  test    eax, eax
0x180024154  js      loc_1800246B6
0x18002415a  mov     rdx, [rbp+57h+var_90]; struct IMFMediaBuffer *
0x18002415e  lea     rcx, [rbp+57h+var_58]; this
0x180024162  call    ?Deserialize@MultiSampleHeader@@QEAAJPEAUIMFMediaBuffer@@@Z; MultiSampleHeader::Deserialize(IMFMediaBuffer *)
0x180024167  mov     ebx, eax
0x180024169  test    eax, eax
0x18002416b  js      loc_18002461E
0x180024171  mov     rcx, [rbp+57h+var_90]
0x180024175  lea     r9, [rbp+57h+var_6C]
0x180024179  xor     r8d, r8d
0x18002417c  lea     rdx, [rbp+57h+var_78]
0x180024180  mov     rax, [rcx]
0x180024183  mov     rax, [rax+18h]
0x180024187  call    cs:__guard_dispatch_icall_fptr
0x18002418d  mov     ebx, eax
0x18002418f  test    eax, eax
0x180024191  js      loc_180024586
0x180024197  mov     rax, [rsi]
0x18002419a  mov     rcx, rsi
0x18002419d  mov     r8d, [rbp+57h+var_44]
0x1800241a1  mov     rdx, [rbp+57h+var_78]
0x1800241a5  mov     rax, [rax]
0x1800241a8  call    cs:__guard_dispatch_icall_fptr
0x1800241ae  mov     ebx, eax
0x1800241b0  test    eax, eax
0x1800241b2  js      loc_1800244EE
0x1800241b8  mov     rcx, [rbp+57h+var_90]
0x1800241bc  mov     rax, [rcx]
0x1800241bf  mov     rax, [rax+20h]
0x1800241c3  call    cs:__guard_dispatch_icall_fptr
0x1800241c9  mov     rcx, [rbp+57h+ppIMFSample]
0x1800241cd  mov     rdx, [rbp+57h+var_90]
0x1800241d1  mov     [rbp+57h+var_78], 0
0x1800241d9  mov     rax, [rcx]
0x1800241dc  mov     rax, [rax+150h]
0x1800241e3  call    cs:__guard_dispatch_icall_fptr
0x1800241e9  mov     ebx, eax
0x1800241eb  test    eax, eax
0x1800241ed  js      loc_180024438
0x1800241f3  mov     rcx, [rbp+57h+var_90]
0x1800241f7  test    rcx, rcx
0x1800241fa  jnz     loc_1800249A0
0x180024200  inc     r14d
0x180024203  jmp     loc_18002410D
0x180024208  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18002420f  test    rcx, rcx
0x180024212  jz      loc_1800242B9
0x180024218  cmp     [rcx+8], r14b
0x18002421c  jnz     loc_1800247E6
0x180024222  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180024229  jb      loc_180024048
0x18002422f  mov     edx, 5Bh ; '['
0x180024234  jmp     loc_180024494
0x180024239  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180024240  test    rcx, rcx
0x180024243  jz      loc_1800242CA
0x180024249  cmp     [rcx+8], r14b
0x18002424d  jnz     loc_180024814
0x180024253  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18002425a  jb      loc_180024048
0x180024260  mov     edx, 5Ch ; '\'
0x180024265  jmp     loc_180024494
0x18002426a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180024271  test    rcx, rcx
0x180024274  jz      short loc_1800242DB
0x180024276  cmp     [rcx+8], r14b
0x18002427a  jnz     loc_180024842
0x180024280  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180024287  jb      loc_180024048
0x18002428d  mov     edx, 5Dh ; ']'
0x180024292  jmp     loc_180024494
0x180024297  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x18002429c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800242a3  jmp     loc_180023EBA
0x1800242a8  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x1800242ad  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800242b4  jmp     loc_1800240DF
0x1800242b9  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x1800242be  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800242c5  jmp     loc_180024218
0x1800242ca  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x1800242cf  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800242d6  jmp     loc_180024249
0x1800242db  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x1800242e0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800242e7  jmp     short loc_180024276
0x1800242e9  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800242ee  cmp     [rax+7CCh], ebx
0x1800242f4  jz      loc_1800240E9
0x1800242fa  mov     r9d, ebx; int
0x1800242fd  mov     r8d, r12d; int
0x180024300  mov     rdx, r15; char *
0x180024303  mov     rcx, rax; this
0x180024306  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18002430b  jmp     loc_1800240E9
0x180024310  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180024317  test    rcx, rcx
0x18002431a  jnz     short loc_180024354
0x18002431c  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180024323  nop     dword ptr [rax+rax+00h]
0x180024328  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18002432f  mov     rcx, rax
0x180024332  test    rax, rax
0x180024335  jz      short loc_180024371
0x180024337  mov     rax, [rax]
0x18002433a  mov     edx, 7F0h
0x18002433f  mov     rax, [rax+8]
0x180024343  call    cs:__guard_dispatch_icall_fptr
0x180024349  test    eax, eax
0x18002434b  jz      short loc_180024371
  ... truncated ...
```
