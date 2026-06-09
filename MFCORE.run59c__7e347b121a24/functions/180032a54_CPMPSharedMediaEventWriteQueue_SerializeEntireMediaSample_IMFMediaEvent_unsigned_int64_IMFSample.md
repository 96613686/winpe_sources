# CPMPSharedMediaEventWriteQueue::SerializeEntireMediaSample(IMFMediaEvent *,unsigned __int64,IMFSample *)

- ea: `0x180032a54`
- end: `0x180033676`
- name: `?SerializeEntireMediaSample@CPMPSharedMediaEventWriteQueue@@IEAAJPEAUIMFMediaEvent@@_KPEAUIMFSample@@@Z`
- size: `3106`
- prototype: `__int64 __fastcall(CPMPSharedMediaEventWriteQueue *__hidden this, struct IMFMediaEvent *, unsigned __int64, struct IMFSample *)`
- caller_count: `1`
- callee_count: `23`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800df588`

## callees

- `0x18001616c`
- `0x180032a54`
- `0x18003367c`
- `0x180033838`
- `0x1800338bc`
- `0x180033e20`
- `0x180033f78`
- `0x1800341dc`
- `0x180034a6c`
- `0x18003ecb0`
- `0x1800402c0`
- `0x180050d6c`
- `0x1800dfc90`
- `0x1800ec0e0`
- `0x18012cfd0`
- `0x18025839c`
- `0x1802583e8`
- `0x180258480`
- `0x1802592a0`
- `0x1802aaee8`
- `0x180344c60`
- `0x180344ce4`
- `0x180344d40`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180033059`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800330e4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003318f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800331d4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800332ef`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180033420`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003351f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180033059`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800330e4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003318f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800331d4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800332ef`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180033420`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003351f`

## string_xrefs

- `0x180032b0a`: `CPMPSharedMediaEventWriteQueue::SerializeEntireMediaSample`
- `0x18003339e`: `CPMPSharedMediaEventWriteQueue::SerializeEntireMediaSample`
- `0x1800333cc`: `CPMPSharedMediaEventWriteQueue::SerializeEntireMediaSample`
- `0x1800333fa`: `CPMPSharedMediaEventWriteQueue::SerializeEntireMediaSample`
- `0x180033499`: `CPMPSharedMediaEventWriteQueue::SerializeEntireMediaSample`
- `0x1800334c4`: `CPMPSharedMediaEventWriteQueue::SerializeEntireMediaSample`
- `0x1800334f2`: `CPMPSharedMediaEventWriteQueue::SerializeEntireMediaSample`
- `0x180033602`: `CPMPSharedMediaEventWriteQueue::SerializeEntireMediaSample`

## pseudocode

```c
__int64 __fastcall CPMPSharedMediaEventWriteQueue::SerializeEntireMediaSample(
        CPMPSharedMediaEventWriteQueue *this,
        struct IMFMediaEvent *a2,
        unsigned __int64 a3,
        IMFAttributes *a4)
{
  unsigned int v6; // r12d
  CallStackTracing *v9; // rcx
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v11; // rcx
  __int64 v12; // rcx
  int v13; // ebx
  __int64 v14; // rdx
  __int64 v15; // r8
  __int64 v16; // r8
  unsigned int v17; // edi
  unsigned __int64 v18; // rbx
  unsigned __int128 v19; // rax
  int v20; // edi
  struct IMFSampleVtbl *lpVtbl; // rax
  __int64 v22; // r8
  unsigned int v23; // edx
  int v24; // r15d
  __int64 v25; // rbx
  __int64 v26; // rdx
  unsigned int v27; // edi
  unsigned int v28; // eax
  unsigned int v29; // eax
  __int64 v30; // r8
  int v31; // ebx
  void **v32; // rax
  unsigned int i; // edi
  __int64 v34; // rbx
  unsigned int v35; // r14d
  __int64 v36; // rdx
  __int64 v37; // r8
  unsigned int j; // edi
  __int64 v39; // rcx
  __int64 *v41; // rcx
  __int64 v42; // rdx
  __int64 *v43; // rcx
  CallStackTracing *v44; // rcx
  __int64 v45; // rdx
  CallStackTracing *v46; // rcx
  CallStackTracing *v47; // rcx
  __int64 v48; // rdx
  __int64 v49; // r8
  __int64 *v50; // rcx
  CallStackTracing *v51; // rax
  __int64 *v52; // rcx
  CallStackTracing *v53; // rax
  CallStackTracing *v54; // rax
  CallStackTracing *v55; // rax
  struct CallStackContext *v56; // rax
  struct CallStackContext *v57; // rax
  __int64 *v58; // rcx
  CallStackTracing *v59; // rax
  struct CallStackContext *v60; // rax
  struct CallStackContext *v61; // rax
  struct CallStackContext *v62; // rax
  struct CallStackContext *v63; // rax
  __int64 *v64; // rcx
  CallStackTracing *v65; // rax
  struct CallStackContext *v66; // rax
  struct CallStackContext *v67; // rax
  struct CallStackContext *v68; // rax
  __int64 *v69; // rcx
  CallStackTracing *v70; // rax
  struct CallStackContext *v71; // rax
  void *v72; // r15
  unsigned int v73; // [rsp+30h] [rbp-D0h] BYREF
  char v74[4]; // [rsp+34h] [rbp-CCh] BYREF
  int v75; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int8 *v76; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int64 v77; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int64 v78; // [rsp+50h] [rbp-B0h]
  void **v79; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD v80[64]; // [rsp+68h] [rbp-98h] BYREF
  void **v81; // [rsp+268h] [rbp+168h] BYREF
  unsigned __int8 *v82; // [rsp+270h] [rbp+170h]
  unsigned int v83; // [rsp+278h] [rbp+178h]
  unsigned int v84; // [rsp+27Ch] [rbp+17Ch]
  _QWORD v85[65]; // [rsp+280h] [rbp+180h] BYREF
  _QWORD v86[2]; // [rsp+488h] [rbp+388h] BYREF
  _DWORD Size[3]; // [rsp+49Ch] [rbp+39Ch] BYREF
  unsigned int v88; // [rsp+4A8h] [rbp+3A8h]
  _BYTE v89[6144]; // [rsp+4B0h] [rbp+3B0h] BYREF
  unsigned int v90; // [rsp+1CB0h] [rbp+1BB0h]
  _DWORD v91[4]; // [rsp+1CC0h] [rbp+1BC0h] BYREF
  _OWORD v92[2]; // [rsp+1CD0h] [rbp+1BD0h] BYREF

  v6 = 0;
  v78 = a3;
  v76 = 0;
  v73 = 0;
  CBufferWriter::CBufferWriter((CBufferWriter *)v85);
  v9 = CallStackTracing::s_wpInstance;
  v85[0] = &CDynamicBufferWriter::`vftable'{for `CDefaultIStreamImpl'};
  v85[1] = &CBufferWriter::`vftable'{for `CPersistStreamMap'};
  v86[0] = &CDynamicBufferWriterWithReferenceStore::`vftable'{for `CBinaryWriter'};
  *(_QWORD *)&Size[1] = v89;
  v88 = 0;
  v90 = 256;
  if ( !CallStackTracing::s_wpInstance )
  {
    CallStackTracing::InitInstance();
    v9 = CallStackTracing::s_wpInstance;
  }
  if ( *((_BYTE *)v9 + 8) )
  {
    ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(v9);
    v11 = *((unsigned int *)ThreadRelativeContext + 497);
    if ( (unsigned int)v11 < *((_DWORD *)ThreadRelativeContext + 498) )
    {
      v12 = 2 * v11;
      *((_QWORD *)ThreadRelativeContext + v12) = "CPMPSharedMediaEventWriteQueue::SerializeEntireMediaSample";
      *((_DWORD *)ThreadRelativeContext + 2 * v12 + 2) = 255;
    }
    ++*((_DWORD *)ThreadRelativeContext + 497);
  }
  v77 = a3;
  v13 = (*(__int64 (__fastcall **)(_QWORD *, unsigned __int64 *, __int64))v86[0])(v86, &v77, 8);
  if ( v13 < 0 )
  {
    v46 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::InitInstance();
      v46 = CallStackTracing::s_wpInstance;
    }
    if ( *((_BYTE *)v46 + 8) )
    {
      v56 = CallStackTracing::GetThreadRelativeContext(v46);
      if ( *((_DWORD *)v56 + 499) != v13 )
        CallStackContext::TraceFailure(v56, "CPMPSharedMediaEventWriteQueue::SerializeEntireMediaSample", 255, v13);
    }
    if ( !g_wppLevels )
      goto LABEL_37;
    v45 = 18;
LABEL_126:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v45, &WPP_be5c5516ab2437f8fba11fde691f58f8_Traceguids, this, v13);
    goto LABEL_37;
  }
  v13 = CEventBinaryWriter::Serialize(v85, a2, 1);
  if ( v13 < 0 )
  {
    v47 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::InitInstance();
      v47 = CallStackTracing::s_wpInstance;
    }
    if ( *((_BYTE *)v47 + 8) )
    {
      v57 = CallStackTracing::GetThreadRelativeContext(v47);
      if ( *((_DWORD *)v57 + 499) != v13 )
        CallStackContext::TraceFailure(v57, "CPMPSharedMediaEventWriteQueue::SerializeEntireMediaSample", 257, v13);
    }
    if ( !g_wppLevels )
      goto LABEL_37;
    v45 = 19;
    goto LABEL_126;
  }
  v13 = CSamplePropBinaryWriter::Serialize(a4, (struct CBufferWriter *)v85);
  if ( v13 < 0 )
  {
    v58 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v59 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v14, v15);
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
      if ( *((_DWORD *)v60 + 499) != v13 )
        CallStackContext::TraceFailure(v60, "CPMPSharedMediaEventWriteQueue::SerializeEntireMediaSample", 262, v13);
    }
    if ( !g_wppLevels )
      goto LABEL_37;
    v45 = 20;
    goto LABEL_126;
  }
  ((void (__fastcall *)(IMFAttributes *, unsigned int *))a4->lpVtbl[1].Compare)(a4, &v73);
  v17 = v73;
  v18 = v73;
  if ( v73 > v90 )
  {
    v72 = operator new[](saturated_mul(v73, 0x18u));
    if ( !v72 )
      goto LABEL_70;
    CStackAllocT<CPMPSharedMediaEventWriteQueue::BufRef,256>::FreeHeapAllocation(&Size[1]);
    *(_QWORD *)&Size[1] = v72;
    v90 = v17;
  }
  v88 = v17;
  if ( !*(_QWORD *)&Size[1] )
  {
LABEL_70:
    v13 = -2147024882;
    goto LABEL_37;
  }
  v19 = 0x18 * (unsigned __int128)v18;
  if ( !is_mul_ok(0x18u, v18) )
  {
    v69 = (__int64 *)CallStackTracing::s_wpInstance;
    v13 = -2147024362;
    if ( !CallStackTracing::s_wpInstance )
    {
      v70 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, *((_QWORD *)&v19 + 1), v16);
      CallStackTracing::s_wpInstance = v70;
      if ( v70 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v70 + 8LL))(v70, 2032) )
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
      if ( *((_DWORD *)v71 + 499) != -2147024362 )
        CallStackContext::TraceFailure(
          v71,
          "CPMPSharedMediaEventWriteQueue::SerializeEntireMediaSample",
          276,
          -2147024362);
    }
    if ( !g_wppLevels )
      goto LABEL_37;
    v42 = 21;
LABEL_141:
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v42,
      &WPP_be5c5516ab2437f8fba11fde691f58f8_Traceguids,
      this,
      -2147024362);
    goto LABEL_37;
  }
  v20 = 0;
  memset_0(*(void **)&Size[1], SDWORD2(v19), v19);
  lpVtbl = (struct IMFSampleVtbl *)a4->lpVtbl;
  v75 = 0;
  ((void (__fastcall *)(IMFAttributes *, int *))lpVtbl->GetSampleFlags)(a4, &v75);
  v23 = v73;
  if ( v73 <= 1 || (v24 = 30, (v75 & 0x100) == 0) )
    v24 = 0;
  if ( v88 )
  {
    do
    {
      v25 = 3LL * v6;
      ((void (__fastcall *)(IMFAttributes *, _QWORD, __int64))a4->lpVtbl[1].GetUINT32)(
        a4,
        v6,
        *(_QWORD *)&Size[1] + 24LL * v6);
      (*(void (__fastcall **)(_QWORD, __int64, _QWORD, __int64))(**(_QWORD **)(*(_QWORD *)&Size[1] + 24LL * v6) + 24LL))(
        *(_QWORD *)(*(_QWORD *)&Size[1] + 24LL * v6),
        *(_QWORD *)&Size[1] + 24LL * v6 + 8,
        0,
        *(_QWORD *)&Size[1] + 16LL + 24LL * v6);
      ++v6;
      v20 += *(_DWORD *)(*(_QWORD *)&Size[1] + 8 * v25 + 16);
    }
    while ( v6 < v88 );
    v23 = v73;
  }
  v91[1] = v23;
  v91[0] = v20;
  v91[2] = 0;
  v26 = v23 * v24 + Size[0] + 12;
  if ( (unsigned int)v26 < Size[0] )
  {
    v43 = (__int64 *)CallStackTracing::s_wpInstance;
    v13 = -2147024362;
    if ( !CallStackTracing::s_wpInstance )
    {
      v55 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v26, v22);
      CallStackTracing::s_wpInstance = v55;
      if ( v55 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v55 + 8LL))(v55, 2032) )
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
      v68 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v43);
      if ( *((_DWORD *)v68 + 499) != -2147024362 )
        CallStackContext::TraceFailure(
          v68,
          "CPMPSharedMediaEventWriteQueue::SerializeEntireMediaSample",
          305,
          -2147024362);
    }
    if ( !g_wppLevels )
      goto LABEL_37;
    v42 = 22;
    goto LABEL_141;
  }
  v27 = v26 + v20;
  if ( v27 < (unsigned int)v26 )
  {
    v41 = (__int64 *)CallStackTracing::s_wpInstance;
    v13 = -2147024362;
    if ( !CallStackTracing::s_wpInstance )
    {
      v54 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v26, v22);
      CallStackTracing::s_wpInstance = v54;
      if ( v54 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v54 + 8LL))(v54, 2032) )
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
      v67 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v41);
      if ( *((_DWORD *)v67 + 499) != -2147024362 )
        CallStackContext::TraceFailure(
          v67,
          "CPMPSharedMediaEventWriteQueue::SerializeEntireMediaSample",
          306,
          -2147024362);
    }
    if ( !g_wppLevels )
      goto LABEL_37;
    v42 = 23;
    goto LABEL_141;
  }
  v28 = *((_DWORD *)this + 4);
  if ( v28 <= 0x28 )
    v29 = 2097148;
  else
    v29 = v28 - 40;
  if ( v27 > v29 )
  {
    v13 = CPMPSharedMediaEventWriteQueue::SerializeMediaSampleInFragments(this, a2, v78, a4);
    if ( v13 >= 0 )
      goto LABEL_37;
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
      v61 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v50);
      if ( *((_DWORD *)v61 + 499) != v13 )
        CallStackContext::TraceFailure(v61, "CPMPSharedMediaEventWriteQueue::SerializeEntireMediaSample", 318, v13);
    }
    if ( !g_wppLevels )
      goto LABEL_37;
    v45 = 24;
    goto LABEL_126;
  }
  v13 = CSharedMsgWriteQueue::AllocData(this, v27, &v76);
  if ( v13 < 0 )
  {
    v44 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::InitInstance();
      v44 = CallStackTracing::s_wpInstance;
    }
    if ( *((_BYTE *)v44 + 8) )
    {
      v62 = CallStackTracing::GetThreadRelativeContext(v44);
      if ( *((_DWORD *)v62 + 499) != v13 )
        CallStackContext::TraceFailure(v62, "CPMPSharedMediaEventWriteQueue::SerializeEntireMediaSample", 322, v13);
    }
    if ( !g_wppLevels )
      goto LABEL_37;
    v45 = 25;
    goto LABEL_126;
  }
  CBufferWriter::CBufferWriter((CBufferWriter *)&v79);
  v31 = Size[0];
  v79 = &CBufferWriter::`vftable'{for `CDefaultIStreamImpl'};
  v80[0] = &CBufferWriter::`vftable'{for `CPersistStreamMap'};
  v32 = &CFixedBufferWriter::`vftable'{for `CBinaryWriter'};
  v81 = &CFixedBufferWriter::`vftable'{for `CBinaryWriter'};
  v82 = v76;
  v83 = v27;
  if ( Size[0] )
  {
    if ( Size[0] + v84 > v27 || v84 > Size[0] + v84 )
    {
      v52 = (__int64 *)CallStackTracing::s_wpInstance;
      v13 = -2147024882;
      if ( !CallStackTracing::s_wpInstance )
      {
        v53 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v76, v30);
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
        v63 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v52);
        if ( *((_DWORD *)v63 + 499) != -2147024882 )
          CallStackContext::TraceFailure(
            v63,
            "CPMPSharedMediaEventWriteQueue::SerializeEntireMediaSample",
            327,
            -2147024882);
      }
      if ( g_wppLevels )
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          26,
          &WPP_be5c5516ab2437f8fba11fde691f58f8_Traceguids,
          this,
          -2147024882);
      v79 = &CBufferWriter::`vftable'{for `CDefaultIStreamImpl'};
      v80[0] = &CBufferWriter::`vftable'{for `CPersistStreamMap'};
      v81 = &CBufferWriter::`vftable'{for `CBinaryWriter'};
      CPersistStreamMap::~CPersistStreamMap((CPersistStreamMap *)v80);
      goto LABEL_37;
    }
    memcpy_0(&v76[v84], (const void *)v86[1], Size[0]);
    v84 += v31;
    v32 = v81;
  }
  ((void (__fastcall *)(void ***, _DWORD *, __int64))*v32)(&v81, v91, 12);
  for ( i = 0; i < v88; ++i )
  {
    v34 = 24LL * i;
    if ( v24 )
    {
      memset(v92, 0, 30);
      MultiSampleHeader::Serialize((MultiSampleHeader *)v92, *(struct IMFMediaBuffer **)(v34 + *(_QWORD *)&Size[1]));
      ((void (__fastcall *)(void ***, _OWORD *, __int64))*v81)(&v81, v92, 30);
    }
    v35 = *(_DWORD *)(v34 + *(_QWORD *)&Size[1] + 16);
    if ( v35 && v84 + v35 <= v83 && v84 <= v84 + v35 )
    {
      memcpy_0(&v82[v84], *(const void **)(v34 + *(_QWORD *)&Size[1] + 8), v35);
      v84 += v35;
    }
  }
  v79 = &CBufferWriter::`vftable'{for `CDefaultIStreamImpl'};
  v80[0] = &CBufferWriter::`vftable'{for `CPersistStreamMap'};
  v81 = &CBufferWriter::`vftable'{for `CBinaryWriter'};
  CPersistStreamMap::~CPersistStreamMap((CPersistStreamMap *)v80);
  v13 = CSharedMsgWriteQueue::WriteMsg(this);
  if ( v13 < 0 )
  {
    v64 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v65 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v36, v37);
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
      if ( *((_DWORD *)v66 + 499) != v13 )
        CallStackContext::TraceFailure(v66, "CPMPSharedMediaEventWriteQueue::SerializeEntireMediaSample", 345, v13);
    }
    if ( g_wppLevels )
    {
      v45 = 27;
      goto LABEL_126;
    }
  }
LABEL_37:
  if ( *(_QWORD *)&Size[1] )
  {
    for ( j = 0; j < v88; ++j )
    {
      v39 = *(_QWORD *)(*(_QWORD *)&Size[1] + 24LL * j);
      if ( v39 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 32LL))(v39);
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(*(_QWORD *)&Size[1] + 24LL * j) + 16LL))(*(_QWORD *)(*(_QWORD *)&Size[1] + 24LL * j));
      }
    }
  }
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v74);
  if ( *(_QWORD *)&Size[1] && *(_BYTE **)&Size[1] != v89 )
  {
    operator delete(*(void **)&Size[1]);
    *(_QWORD *)&Size[1] = 0;
  }
  CDynamicBufferWriter::~CDynamicBufferWriter((CDynamicBufferWriter *)v85);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x180032a54  push    rbp
0x180032a56  push    rbx
0x180032a57  push    rsi
0x180032a58  push    rdi
0x180032a59  push    r12
0x180032a5b  push    r13
0x180032a5d  push    r14
0x180032a5f  push    r15
0x180032a61  lea     rbp, [rsp-1C08h]
0x180032a69  mov     eax, 1D08h
0x180032a6e  call    _alloca_probe
0x180032a73  sub     rsp, rax
0x180032a76  mov     rax, cs:__security_cookie
0x180032a7d  xor     rax, rsp
0x180032a80  mov     [rbp+1C40h+var_50], rax
0x180032a87  mov     rbx, r8
0x180032a8a  mov     rsi, rcx
0x180032a8d  xor     r12d, r12d
0x180032a90  mov     [rsp+1D40h+var_1CF0], rbx
0x180032a95  lea     rcx, [rbp+1C40h+var_1AC0]; this
0x180032a9c  mov     [rsp+1D40h+var_1D00], r12
0x180032aa1  mov     [rsp+1D40h+var_1D10], r12d
0x180032aa6  mov     r14, r9
0x180032aa9  mov     r13, rdx
0x180032aac  call    ??0CBufferWriter@@QEAA@XZ; CBufferWriter::CBufferWriter(void)
0x180032ab1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180032ab8  lea     rax, ??_7CDynamicBufferWriter@@6BCDefaultIStreamImpl@@@; const CDynamicBufferWriter::`vftable'{for `CDefaultIStreamImpl'}
0x180032abf  mov     [rbp+1C40h+var_1AC0], rax
0x180032ac6  lea     rax, ??_7CBufferWriter@@6BCPersistStreamMap@@@; const CBufferWriter::`vftable'{for `CPersistStreamMap'}
0x180032acd  mov     [rbp+1C40h+var_1AB8], rax
0x180032ad4  lea     rax, ??_7CDynamicBufferWriterWithReferenceStore@@6BCBinaryWriter@@@; const CDynamicBufferWriterWithReferenceStore::`vftable'{for `CBinaryWriter'}
0x180032adb  mov     [rbp+1C40h+var_18B8], rax
0x180032ae2  lea     rax, [rbp+1C40h+var_1890]
0x180032ae9  mov     qword ptr [rbp+1C40h+Size+4], rax
0x180032af0  mov     [rbp+1C40h+var_1898], r12d
0x180032af7  mov     [rbp+1C40h+var_90], 100h
0x180032b01  test    rcx, rcx
0x180032b04  jz      loc_180033215
0x180032b0a  lea     r15, aCpmpsharedmedi_8; "CPMPSharedMediaEventWriteQueue::Seriali"...
0x180032b11  mov     edi, 0FFh
0x180032b16  cmp     [rcx+8], r12b
0x180032b1a  jz      short loc_180032B40
0x180032b1c  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180032b21  mov     ecx, [rax+7C4h]
0x180032b27  cmp     ecx, [rax+7C8h]
0x180032b2d  jnb     short loc_180032B3A
0x180032b2f  add     rcx, rcx
0x180032b32  mov     [rax+rcx*8], r15
0x180032b36  mov     [rax+rcx*8+8], edi
0x180032b3a  inc     dword ptr [rax+7C4h]
0x180032b40  mov     rax, [rbp+1C40h+var_18B8]
0x180032b47  lea     rdx, [rsp+1D40h+var_1CF8]
0x180032b4c  mov     r8d, 8
0x180032b52  mov     [rsp+1D40h+var_1CF8], rbx
0x180032b57  lea     rcx, [rbp+1C40h+var_18B8]
0x180032b5e  mov     rax, [rax]
0x180032b61  call    cs:__guard_dispatch_icall_fptr
0x180032b67  mov     ebx, eax
0x180032b69  test    eax, eax
0x180032b6b  js      loc_180032FC7
0x180032b71  mov     r8d, 1
0x180032b77  lea     rcx, [rbp+1C40h+var_1AC0]
0x180032b7e  mov     rdx, r13
0x180032b81  call    ?Serialize@CEventBinaryWriter@@QEAAJPEAUIMFMediaEvent@@W4VALUE_SERIALIZATION_TYPE@CEventBinaryTypes@@@Z; CEventBinaryWriter::Serialize(IMFMediaEvent *,CEventBinaryTypes::VALUE_SERIALIZATION_TYPE)
0x180032b86  mov     ebx, eax
0x180032b88  test    eax, eax
0x180032b8a  js      loc_180032FF8
0x180032b90  lea     rdx, [rbp+1C40h+var_1AC0]; pStm
0x180032b97  mov     rcx, r14; pAttr
0x180032b9a  call    ?Serialize@CSamplePropBinaryWriter@@SAJPEAUIMFSample@@AEAVCBufferWriter@@@Z; CSamplePropBinaryWriter::Serialize(IMFSample *,CBufferWriter &)
0x180032b9f  mov     ebx, eax
0x180032ba1  test    eax, eax
0x180032ba3  js      loc_1800332E3
0x180032ba9  mov     rax, [r14]
0x180032bac  lea     rdx, [rsp+1D40h+var_1D10]
0x180032bb1  mov     rcx, r14
0x180032bb4  mov     rax, [rax+138h]
0x180032bbb  call    cs:__guard_dispatch_icall_fptr
0x180032bc1  mov     edi, [rsp+1D40h+var_1D10]
0x180032bc5  mov     edx, 18h; Val
0x180032bca  mov     ebx, edi
0x180032bcc  cmp     edi, [rbp+1C40h+var_90]
0x180032bd2  ja      loc_1800335C5
0x180032bd8  mov     rcx, qword ptr [rbp+1C40h+Size+4]; void *
0x180032bdf  mov     [rbp+1C40h+var_1898], edi
0x180032be5  test    rcx, rcx
0x180032be8  jz      loc_180033029
0x180032bee  mov     rax, rbx
0x180032bf1  mul     rdx
0x180032bf4  test    rdx, rdx
0x180032bf7  jnz     loc_18003350C
0x180032bfd  mov     r8, rax; Size
0x180032c00  mov     edi, r12d
0x180032c03  call    memset_0
0x180032c08  mov     rax, [r14]
0x180032c0b  lea     rdx, [rsp+1D40h+var_1D08]
0x180032c10  mov     rcx, r14
0x180032c13  mov     [rsp+1D40h+var_1D08], r12d
0x180032c18  mov     rax, [rax+108h]
0x180032c1f  call    cs:__guard_dispatch_icall_fptr
0x180032c25  mov     edx, [rsp+1D40h+var_1D10]
0x180032c29  cmp     edx, 1
0x180032c2c  ja      loc_1800330BA
0x180032c32  mov     r15d, r12d
0x180032c35  cmp     [rbp+1C40h+var_1898], r12d
0x180032c3c  jbe     short loc_180032CAC
0x180032c3e  mov     rcx, [r14]
0x180032c41  mov     edx, r12d
0x180032c44  mov     eax, r12d
0x180032c47  lea     rbx, [rax+rax*2]
0x180032c4b  mov     rax, qword ptr [rbp+1C40h+Size+4]
0x180032c52  lea     r8, [rax+rbx*8]
0x180032c56  mov     rax, [rcx+140h]
0x180032c5d  mov     rcx, r14
0x180032c60  call    cs:__guard_dispatch_icall_fptr
0x180032c66  mov     rdx, qword ptr [rbp+1C40h+Size+4]
0x180032c6d  xor     r8d, r8d
0x180032c70  mov     rcx, [rdx+rbx*8]
0x180032c74  lea     r9, [rdx+10h]
0x180032c78  lea     rdx, [rdx+rbx*8]
0x180032c7c  lea     r9, [r9+rbx*8]
0x180032c80  add     rdx, 8
0x180032c84  mov     rax, [rcx]
0x180032c87  mov     rax, [rax+18h]
0x180032c8b  call    cs:__guard_dispatch_icall_fptr
0x180032c91  mov     rax, qword ptr [rbp+1C40h+Size+4]
0x180032c98  inc     r12d
0x180032c9b  add     edi, [rax+rbx*8+10h]
0x180032c9f  cmp     r12d, [rbp+1C40h+var_1898]
0x180032ca6  jb      short loc_180032C3E
0x180032ca8  mov     edx, [rsp+1D40h+var_1D10]
0x180032cac  mov     ecx, dword ptr [rbp+1C40h+Size]
0x180032cb2  xor     r12d, r12d
0x180032cb5  mov     [rbp+1C40h+var_7C], edx
0x180032cbb  mov     eax, r15d
0x180032cbe  imul    eax, edx
0x180032cc1  mov     [rbp+1C40h+var_80], edi
0x180032cc7  lea     edx, [rcx+0Ch]
0x180032cca  mov     [rbp+1C40h+var_78], r12d
0x180032cd1  add     edx, eax
0x180032cd3  cmp     edx, ecx
0x180032cd5  jb      loc_180032F54
0x180032cdb  add     edi, edx
0x180032cdd  cmp     edi, edx
0x180032cdf  jb      loc_180032F1C
0x180032ce5  mov     eax, [rsi+10h]
0x180032ce8  cmp     eax, 28h ; '('
0x180032ceb  jbe     loc_180032F8C
0x180032cf1  add     eax, 0FFFFFFD8h
0x180032cf4  mov     rcx, rsi; this
0x180032cf7  cmp     edi, eax
0x180032cf9  ja      loc_180033033
0x180032cff  lea     r8, [rsp+1D40h+var_1D00]; unsigned __int8 **
0x180032d04  mov     edx, edi; unsigned int
0x180032d06  call    ?AllocData@CSharedMsgWriteQueue@@QEAAJKPEAPEAE@Z; CSharedMsgWriteQueue::AllocData(ulong,uchar * *)
0x180032d0b  mov     ebx, eax
0x180032d0d  test    eax, eax
0x180032d0f  js      loc_180032F96
0x180032d15  lea     rcx, [rsp+1D40h+var_1CE0]; this
0x180032d1a  call    ??0CBufferWriter@@QEAA@XZ; CBufferWriter::CBufferWriter(void)
0x180032d1f  mov     ebx, dword ptr [rbp+1C40h+Size]
0x180032d25  lea     rax, ??_7CBufferWriter@@6BCDefaultIStreamImpl@@@; const CBufferWriter::`vftable'{for `CDefaultIStreamImpl'}
0x180032d2c  mov     rdx, [rsp+1D40h+var_1D00]
0x180032d31  mov     [rsp+1D40h+var_1CE0], rax
0x180032d36  lea     rax, ??_7CBufferWriter@@6BCPersistStreamMap@@@; const CBufferWriter::`vftable'{for `CPersistStreamMap'}
0x180032d3d  mov     [rsp+1D40h+var_1CD8], rax
0x180032d42  lea     rax, ??_7CFixedBufferWriter@@6BCBinaryWriter@@@; const CFixedBufferWriter::`vftable'{for `CBinaryWriter'}
0x180032d49  mov     [rbp+1C40h+var_1AD8], rax
0x180032d50  mov     [rbp+1C40h+var_1AD0], rdx
0x180032d57  mov     [rbp+1C40h+var_1AC8], edi
0x180032d5d  test    ebx, ebx
0x180032d5f  jz      short loc_180032D9A
0x180032d61  mov     eax, [rbp+1C40h+var_1AC4]
0x180032d67  lea     ecx, [rbx+rax]
0x180032d6a  cmp     ecx, edi
0x180032d6c  ja      loc_1800330D3
0x180032d72  cmp     eax, ecx
0x180032d74  ja      loc_1800330D3
0x180032d7a  lea     rcx, [rdx+rax]; void *
0x180032d7e  mov     r8d, ebx; Size
0x180032d81  mov     rdx, [rbp+1C40h+Src]; Src
0x180032d88  call    memcpy_0
0x180032d8d  add     [rbp+1C40h+var_1AC4], ebx
0x180032d93  mov     rax, [rbp+1C40h+var_1AD8]
0x180032d9a  mov     rax, [rax]
0x180032d9d  lea     rdx, [rbp+1C40h+var_80]
0x180032da4  mov     r8d, 0Ch
0x180032daa  lea     rcx, [rbp+1C40h+var_1AD8]
0x180032db1  call    cs:__guard_dispatch_icall_fptr
0x180032db7  mov     edi, r12d
0x180032dba  cmp     [rbp+1C40h+var_1898], r12d
0x180032dc1  jbe     short loc_180032E28
0x180032dc3  mov     eax, edi
0x180032dc5  lea     rcx, [rax+rax*2]
0x180032dc9  lea     rbx, ds:0[rcx*8]
0x180032dd1  test    r15d, r15d
0x180032dd4  jnz     loc_180033614
0x180032dda  mov     rdx, qword ptr [rbp+1C40h+Size+4]
0x180032de1  mov     r14d, [rbx+rdx+10h]
0x180032de6  test    r14d, r14d
0x180032de9  jz      short loc_180032E1E
0x180032deb  mov     eax, [rbp+1C40h+var_1AC4]
0x180032df1  lea     ecx, [rax+r14]
0x180032df5  cmp     ecx, [rbp+1C40h+var_1AC8]
0x180032dfb  ja      short loc_180032E1E
0x180032dfd  cmp     eax, ecx
0x180032dff  ja      short loc_180032E1E
0x180032e01  mov     rdx, [rbx+rdx+8]; Src
0x180032e06  mov     ecx, eax
0x180032e08  add     rcx, [rbp+1C40h+var_1AD0]; void *
0x180032e0f  mov     r8d, r14d; Size
0x180032e12  call    memcpy_0
0x180032e17  add     [rbp+1C40h+var_1AC4], r14d
0x180032e1e  inc     edi
0x180032e20  cmp     edi, [rbp+1C40h+var_1898]
0x180032e26  jb      short loc_180032DC3
0x180032e28  lea     rax, ??_7CBufferWriter@@6BCDefaultIStreamImpl@@@; const CBufferWriter::`vftable'{for `CDefaultIStreamImpl'}
0x180032e2f  mov     [rsp+1D40h+var_1CE0], rax
0x180032e34  lea     rcx, [rsp+1D40h+var_1CD8]; this
0x180032e39  lea     rax, ??_7CBufferWriter@@6BCPersistStreamMap@@@; const CBufferWriter::`vftable'{for `CPersistStreamMap'}
0x180032e40  mov     [rsp+1D40h+var_1CD8], rax
0x180032e45  lea     rax, ??_7CBufferWriter@@6BCBinaryWriter@@@; const CBufferWriter::`vftable'{for `CBinaryWriter'}
0x180032e4c  mov     [rbp+1C40h+var_1AD8], rax
0x180032e53  call    ??1CPersistStreamMap@@QEAA@XZ; CPersistStreamMap::~CPersistStreamMap(void)
0x180032e58  mov     rcx, rsi; this
0x180032e5b  call    ?WriteMsg@CSharedMsgWriteQueue@@QEAAJXZ; CSharedMsgWriteQueue::WriteMsg(void)
0x180032e60  mov     ebx, eax
0x180032e62  test    eax, eax
0x180032e64  js      loc_180033414
0x180032e6a  cmp     qword ptr [rbp+1C40h+Size+4], r12
0x180032e71  jz      short loc_180032EC4
0x180032e73  mov     edi, r12d
0x180032e76  cmp     [rbp+1C40h+var_1898], r12d
0x180032e7d  jbe     short loc_180032EC4
0x180032e7f  mov     eax, edi
0x180032e81  lea     rsi, [rax+rax*2]
0x180032e85  mov     rax, qword ptr [rbp+1C40h+Size+4]
0x180032e8c  mov     rcx, [rax+rsi*8]
0x180032e90  test    rcx, rcx
0x180032e93  jz      short loc_180032EBA
0x180032e95  mov     rax, [rcx]
0x180032e98  mov     rax, [rax+20h]
0x180032e9c  call    cs:__guard_dispatch_icall_fptr
0x180032ea2  mov     rax, qword ptr [rbp+1C40h+Size+4]
0x180032ea9  mov     rcx, [rax+rsi*8]
0x180032ead  mov     rax, [rcx]
0x180032eb0  mov     rax, [rax+10h]
0x180032eb4  call    cs:__guard_dispatch_icall_fptr
0x180032eba  inc     edi
0x180032ebc  cmp     edi, [rbp+1C40h+var_1898]
0x180032ec2  jb      short loc_180032E7F
0x180032ec4  lea     rcx, [rsp+1D40h+var_1D0C]; this
0x180032ec9  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180032ece  mov     rcx, qword ptr [rbp+1C40h+Size+4]; Block
0x180032ed5  test    rcx, rcx
0x180032ed8  jz      short loc_180032EEA
0x180032eda  lea     rax, [rbp+1C40h+var_1890]
0x180032ee1  cmp     rcx, rax
0x180032ee4  jnz     loc_180033665
0x180032eea  lea     rcx, [rbp+1C40h+var_1AC0]; this
0x180032ef1  call    ??1CDynamicBufferWriter@@UEAA@XZ; CDynamicBufferWriter::~CDynamicBufferWriter(void)
0x180032ef6  mov     eax, ebx
0x180032ef8  mov     rcx, [rbp+1C40h+var_50]
0x180032eff  xor     rcx, rsp; StackCookie
0x180032f02  call    __security_check_cookie
0x180032f07  add     rsp, 1D08h
0x180032f0e  pop     r15
0x180032f10  pop     r14
0x180032f12  pop     r13
0x180032f14  pop     r12
0x180032f16  pop     rdi
0x180032f17  pop     rsi
0x180032f18  pop     rbx
0x180032f19  pop     rbp
0x180032f1a  retn
0x180032f1c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180032f23  mov     edi, 80070216h
0x180032f28  mov     ebx, edi
0x180032f2a  test    rcx, rcx
0x180032f2d  jz      loc_18003318F
0x180032f33  cmp     [rcx+8], r12b
0x180032f37  jnz     loc_1800334B0
0x180032f3d  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180032f44  jb      loc_180032E6A
0x180032f4a  mov     edx, 17h
0x180032f4f  jmp     loc_18003356F
0x180032f54  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180032f5b  mov     edi, 80070216h
0x180032f60  mov     ebx, edi
0x180032f62  test    rcx, rcx
0x180032f65  jz      loc_1800331D4
0x180032f6b  cmp     [rcx+8], r12b
0x180032f6f  jnz     loc_1800334DE
0x180032f75  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180032f7c  jb      loc_180032E6A
0x180032f82  mov     edx, 16h
0x180032f87  jmp     loc_18003356F
0x180032f8c  mov     eax, 1FFFFCh
0x180032f91  jmp     loc_180032CF4
0x180032f96  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
  ... truncated ...
```
