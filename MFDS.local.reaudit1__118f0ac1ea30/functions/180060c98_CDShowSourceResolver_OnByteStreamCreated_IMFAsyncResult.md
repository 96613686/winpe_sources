# CDShowSourceResolver::OnByteStreamCreated(IMFAsyncResult *)

- ea: `0x180060c98`
- end: `0x18006153f`
- name: `?OnByteStreamCreated@CDShowSourceResolver@@IEAAXPEAUIMFAsyncResult@@@Z`
- size: `2215`
- prototype: `void __fastcall(CDShowSourceResolver *__hidden this, struct IMFAsyncResult *)`
- caller_count: `1`
- callee_count: `17`
- tags: `broker_com_uri`

## callers

- `0x180079010`

## callees

- `0x180002820`
- `0x18000b8c0`
- `0x1800140b0`
- `0x1800227e0`
- `0x180023f20`
- `0x18002d514`
- `0x180032988`
- `0x180032a50`
- `0x180051ce4`
- `0x180053638`
- `0x180053934`
- `0x180060c98`
- `0x180063900`
- `0x1800760fc`
- `0x180076738`
- `0x18007bd8c`
- `0x1800c9010`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!memset` at `0x180060d20`
- `api-ms-win-crt-string-l1-1-0!memset` at `0x180060d20`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180061515`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180061515`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180060cd1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180060cd1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180060d4a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180060dfc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180060ed9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180060f29`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180061055`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800611a9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180061217`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800613ab`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180060d4a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180060dfc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180060ed9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180060f29`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180061055`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800611a9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180061217`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800613ab`
- `MFPlat!MFInvokeCallback` at `0x1800614cf`
- `MFPlat!MFInvokeCallback` at `0x1800614cf`

## string_xrefs

- `0x180060cb7`: `CDShowSourceResolver::OnByteStreamCreated`
- `0x180060da7`: `CDShowSourceResolver::OnByteStreamCreated`
- `0x180060e59`: `CDShowSourceResolver::OnByteStreamCreated`
- `0x180060f86`: `CDShowSourceResolver::OnByteStreamCreated`
- `0x180060fd6`: `CDShowSourceResolver::OnByteStreamCreated`
- `0x1800610b2`: `CDShowSourceResolver::OnByteStreamCreated`
- `0x180061274`: `CDShowSourceResolver::OnByteStreamCreated`
- `0x180061302`: `CDShowSourceResolver::OnByteStreamCreated`
- `0x180061408`: `CDShowSourceResolver::OnByteStreamCreated`

## pseudocode

```c
void __fastcall CDShowSourceResolver::OnByteStreamCreated(
        struct _RTL_CRITICAL_SECTION *this,
        struct IMFAsyncResult *a2)
{
  int v4; // r12d
  IMFAsyncResult *v5; // rdi
  int v6; // r15d
  CallStackTracing *v7; // rcx
  int v8; // ebx
  CallStackTracing *v9; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v11; // rdx
  CallStackTracing *v12; // rcx
  CallStackTracing *v13; // rax
  struct CallStackContext *v14; // rax
  int v15; // eax
  CallStackTracing *v16; // rcx
  CallStackTracing *v17; // rax
  CallStackTracing *v18; // rcx
  CallStackTracing *v19; // rax
  struct CallStackContext *v20; // rax
  struct CallStackContext *v21; // rax
  CallStackTracing *v22; // rcx
  CallStackTracing *v23; // rax
  struct CallStackContext *v24; // rax
  const unsigned __int16 *v25; // rax
  int v26; // r8d
  int v27; // eax
  __int64 v28; // rax
  __int64 v29; // r8
  CallStackTracing *v30; // rcx
  CallStackTracing *v31; // rax
  CallStackTracing *v32; // rcx
  CallStackTracing *v33; // rax
  struct CallStackContext *v34; // rax
  struct IMFByteStream *v35; // rcx
  struct CallStackContext *v36; // rax
  const unsigned __int16 *v37; // rax
  CallStackTracing *v38; // rcx
  CallStackTracing *v39; // rax
  struct CallStackContext *v40; // rax
  struct IMFAsyncResultVtbl *v41; // rcx
  struct IMFAsyncResultVtbl *lpVtbl; // rcx
  struct IUnknown *v43; // [rsp+40h] [rbp-69h] BYREF
  __int64 (__fastcall ***v44)(_QWORD, GUID *, struct IMFByteStream **); // [rsp+48h] [rbp-61h] BYREF
  _QWORD v45[2]; // [rsp+50h] [rbp-59h] BYREF
  int v46; // [rsp+60h] [rbp-49h] BYREF
  __int64 v47; // [rsp+64h] [rbp-45h]
  int v48; // [rsp+6Ch] [rbp-3Dh]
  __int64 v49; // [rsp+70h] [rbp-39h]
  _BYTE v50[64]; // [rsp+78h] [rbp-31h] BYREF
  int v51; // [rsp+B8h] [rbp+Fh]
  int v52; // [rsp+110h] [rbp+67h] BYREF
  MF_OBJECT_TYPE v53; // [rsp+118h] [rbp+6Fh] BYREF
  struct IMFByteStream *v54; // [rsp+120h] [rbp+77h] BYREF
  struct IPropertyStore *v55; // [rsp+128h] [rbp+7Fh] BYREF

  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)&v52,
    "CDShowSourceResolver::OnByteStreamCreated",
    489);
  EnterCriticalSection(this + 2);
  v46 &= 0xFFFFFFF8;
  v4 = 0;
  v51 = 1;
  v45[0] = 0;
  v44 = 0;
  v5 = 0;
  v54 = 0;
  v6 = 0;
  v43 = 0;
  v53 = MF_OBJECT_MEDIASOURCE;
  v52 = 0;
  v47 = 0;
  v49 = 0;
  v48 = 0;
  memset(v50, 0, sizeof(v50));
  v55 = 0;
  if ( !a2 )
  {
    v7 = CallStackTracing::s_wpInstance;
    v8 = -2147418113;
    if ( !CallStackTracing::s_wpInstance )
    {
      v9 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
      CallStackTracing::s_wpInstance = v9;
      if ( v9 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v9 + 8LL))(v9, 2032) )
      {
        v7 = CallStackTracing::s_wpInstance;
      }
      else
      {
        v7 = (CallStackTracing *)&qword_1800EB130;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
      }
    }
    if ( *((_BYTE *)v7 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(v7);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != -2147418113 )
        CallStackContext::TraceFailure(
          ThreadRelativeContext,
          "CDShowSourceResolver::OnByteStreamCreated",
          507,
          -2147418113);
    }
    if ( !g_wppLevels )
      goto LABEL_103;
    v11 = 58;
LABEL_102:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v11, WPP_4f2c49dc30393f4458000cee70747074_Traceguids, this, v8);
LABEL_103:
    if ( v54 )
      ((void (__fastcall *)(struct IMFByteStream *))v54->lpVtbl->Close)(v54);
    goto LABEL_112;
  }
  v8 = ((__int64 (__fastcall *)(struct IMFAsyncResult *, _QWORD *))a2->lpVtbl->GetState)(a2, v45);
  if ( v8 < 0 )
  {
    v12 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v13 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
      CallStackTracing::s_wpInstance = v13;
      if ( v13 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v13 + 8LL))(v13, 2032) )
      {
        v12 = CallStackTracing::s_wpInstance;
      }
      else
      {
        v12 = (CallStackTracing *)&qword_1800EB130;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
      }
    }
    if ( *((_BYTE *)v12 + 8) )
    {
      v14 = CallStackTracing::GetThreadRelativeContext(v12);
      if ( *((_DWORD *)v14 + 499) != v8 )
        CallStackContext::TraceFailure(v14, "CDShowSourceResolver::OnByteStreamCreated", 508, v8);
    }
    if ( !g_wppLevels )
      goto LABEL_103;
    v11 = 59;
    goto LABEL_102;
  }
  v5 = (IMFAsyncResult *)v45[0];
  v15 = (*(__int64 (__fastcall **)(_QWORD, struct IMFAsyncResult *, MF_OBJECT_TYPE *, __int64 (__fastcall ****)(_QWORD, GUID *, struct IMFByteStream **)))(**(_QWORD **)(v45[0] + 104LL) + 48LL))(
          *(_QWORD *)(v45[0] + 104LL),
          a2,
          &v53,
          &v44);
  v8 = v15;
  if ( v15 < 0 )
  {
    if ( v15 != -2147024809 )
    {
      v18 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v19 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
        CallStackTracing::s_wpInstance = v19;
        if ( v19 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v19 + 8LL))(v19, 2032) )
        {
          v18 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v18 = (CallStackTracing *)&qword_1800EB130;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
        }
      }
      if ( *((_BYTE *)v18 + 8) )
      {
        v20 = CallStackTracing::GetThreadRelativeContext(v18);
        if ( *((_DWORD *)v20 + 499) != v8 )
          CallStackContext::TraceFailure(v20, "CDShowSourceResolver::OnByteStreamCreated", 530, v8);
      }
      if ( !g_wppLevels )
        goto LABEL_103;
      v11 = 60;
      goto LABEL_102;
    }
    v4 = 1;
  }
  if ( LODWORD(v5[12].lpVtbl) )
  {
    v16 = CallStackTracing::s_wpInstance;
    v8 = -2147467260;
    if ( !CallStackTracing::s_wpInstance )
    {
      v17 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
      CallStackTracing::s_wpInstance = v17;
      if ( v17 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v17 + 8LL))(v17, 2032) )
      {
        v16 = CallStackTracing::s_wpInstance;
      }
      else
      {
        v16 = (CallStackTracing *)&qword_1800EB130;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
      }
    }
    if ( *((_BYTE *)v16 + 8) )
    {
      v21 = CallStackTracing::GetThreadRelativeContext(v16);
      if ( *((_DWORD *)v21 + 499) != -2147467260 )
        CallStackContext::TraceFailure(v21, "CDShowSourceResolver::OnByteStreamCreated", 539, -2147467260);
    }
    if ( !g_wppLevels )
      goto LABEL_103;
    v11 = 61;
    goto LABEL_102;
  }
  CGITPtr::Get((CGITPtr *)((char *)&v5[20].lpVtbl + 4), &GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99, (void **)&v55);
  if ( !v4 )
  {
    v8 = (**v44)(v44, &GUID_ad4c1b00_4bf7_422f_9175_756693d9130d, &v54);
    if ( v8 < 0 )
    {
      v22 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v23 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
        CallStackTracing::s_wpInstance = v23;
        if ( v23 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v23 + 8LL))(v23, 2032) )
        {
          v22 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v22 = (CallStackTracing *)&qword_1800EB130;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
        }
      }
      if ( *((_BYTE *)v22 + 8) )
      {
        v24 = CallStackTracing::GetThreadRelativeContext(v22);
        if ( *((_DWORD *)v24 + 499) != v8 )
          CallStackContext::TraceFailure(v24, "CDShowSourceResolver::OnByteStreamCreated", 550, v8);
      }
      if ( !g_wppLevels )
        goto LABEL_103;
      v11 = 62;
      goto LABEL_102;
    }
    v25 = (const unsigned __int16 *)CMFBaseStringT<unsigned short>::PContents(&v5[17]);
    if ( (int)CUri::Parse((CUri *)&v46, v25, v26) < 0 || (unsigned int)CUri::GetKnownScheme(&v46) == 1 )
    {
      v8 = CDShowSourceResolver::RequiresMFWorkQueue((CDShowSourceResolver *)this, v54, v55, &v52);
      if ( v8 < 0 )
      {
        v32 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v33 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
          CallStackTracing::s_wpInstance = v33;
          if ( v33 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v33 + 8LL))(v33, 2032) )
          {
            v32 = CallStackTracing::s_wpInstance;
          }
          else
          {
            v32 = (CallStackTracing *)&qword_1800EB130;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
          }
        }
        if ( *((_BYTE *)v32 + 8) )
        {
          v34 = CallStackTracing::GetThreadRelativeContext(v32);
          if ( *((_DWORD *)v34 + 499) != v8 )
            CallStackContext::TraceFailure(v34, "CDShowSourceResolver::OnByteStreamCreated", 569, v8);
        }
        if ( !g_wppLevels )
          goto LABEL_103;
        v11 = 63;
        goto LABEL_102;
      }
      v6 = v52;
      v27 = 0;
      if ( !v52 )
      {
        ((void (__fastcall *)(struct IMFByteStream *))v54->lpVtbl->Close)(v54);
        v35 = v54;
        if ( v54 )
        {
          v54 = 0;
          ((void (__fastcall *)(struct IMFByteStream *))v35->lpVtbl->Release)(v35);
        }
        goto LABEL_89;
      }
    }
    else
    {
      v27 = 1;
    }
    if ( (unsigned __int8)byte_1800EACCC >= 8u )
      WPP_SF_qDD(
        *((_QWORD *)WPP_GLOBAL_Control + 22),
        64,
        WPP_4f2c49dc30393f4458000cee70747074_Traceguids,
        this,
        v27,
        v6);
    v28 = CMFBaseStringT<unsigned short>::PContents(&v5[17]);
    v8 = (*(__int64 (__fastcall **)(struct _RTL_CRITICAL_SECTION *, struct IMFByteStream *, __int64, _QWORD, __int64, MF_OBJECT_TYPE *, struct IUnknown **))&this->DebugInfo->EntryCount)(
           this,
           v54,
           v28,
           LODWORD(v5[20].lpVtbl),
           v29,
           &v53,
           &v43);
    if ( v8 < 0 )
    {
      v30 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v31 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
        CallStackTracing::s_wpInstance = v31;
        if ( v31 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v31 + 8LL))(v31, 2032) )
        {
          v30 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v30 = (CallStackTracing *)&qword_1800EB130;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
        }
      }
      if ( *((_BYTE *)v30 + 8) )
      {
        v36 = CallStackTracing::GetThreadRelativeContext(v30);
        if ( *((_DWORD *)v36 + 499) != v8 )
          CallStackContext::TraceFailure(v36, "CDShowSourceResolver::OnByteStreamCreated", 583, v8);
      }
      if ( !g_wppLevels )
        goto LABEL_103;
      v11 = 65;
      goto LABEL_102;
    }
  }
LABEL_89:
  if ( (unsigned __int8)byte_1800EACCC >= 8u )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 22), 66, WPP_4f2c49dc30393f4458000cee70747074_Traceguids, this);
  v37 = (const unsigned __int16 *)CMFBaseStringT<unsigned short>::PContents(&v5[17]);
  v8 = CDShowSourceResolver::InternalCreateObjectFromURL(
         (CDShowSourceResolver *)this,
         v37,
         (unsigned int)v5[20].lpVtbl,
         v55,
         &v53,
         0,
         &v43);
  if ( v8 < 0 )
  {
    v38 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v39 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
      CallStackTracing::s_wpInstance = v39;
      if ( v39 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v39 + 8LL))(v39, 2032) )
      {
        v38 = CallStackTracing::s_wpInstance;
      }
      else
      {
        v38 = (CallStackTracing *)&qword_1800EB130;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
      }
    }
    if ( *((_BYTE *)v38 + 8) )
    {
      v40 = CallStackTracing::GetThreadRelativeContext(v38);
      if ( *((_DWORD *)v40 + 499) != v8 )
        CallStackContext::TraceFailure(v40, "CDShowSourceResolver::OnByteStreamCreated", 604, v8);
    }
    if ( !g_wppLevels )
      goto LABEL_103;
    v11 = 67;
    goto LABEL_102;
  }
  if ( v43 )
  {
    ((void (__fastcall *)(struct IUnknown *))v43->lpVtbl->AddRef)(v43);
    lpVtbl = v5[15].lpVtbl;
    if ( lpVtbl )
      (*((void (__fastcall **)(struct IMFAsyncResultVtbl *))lpVtbl->QueryInterface + 2))(lpVtbl);
    v5[15].lpVtbl = (struct IMFAsyncResultVtbl *)v43;
  }
  else
  {
    v41 = v5[15].lpVtbl;
    if ( v41 )
    {
      (*((void (__fastcall **)(struct IMFAsyncResultVtbl *))v41->QueryInterface + 2))(v41);
      v5[15].lpVtbl = 0;
    }
  }
  LODWORD(v5[14].lpVtbl) = v53;
LABEL_112:
  if ( v5 )
  {
    ((void (__fastcall *)(IMFAsyncResult *, _QWORD))v5->lpVtbl->SetStatus)(v5, (unsigned int)v8);
    MFInvokeCallback(v5);
  }
  ATL::CComPtrBase<IMediaSeeking>::~CComPtrBase<IMediaSeeking>(&v55);
  CMFBaseStringT<char>::~CMFBaseStringT<char>(&v46);
  ATL::CComPtrBase<IMediaSeeking>::~CComPtrBase<IMediaSeeking>(&v43);
  ATL::CComPtrBase<IMediaSeeking>::~CComPtrBase<IMediaSeeking>(&v54);
  ATL::CComPtrBase<IMediaSeeking>::~CComPtrBase<IMediaSeeking>(&v44);
  ATL::CComPtrBase<IMediaSeeking>::~CComPtrBase<IMediaSeeking>(v45);
  LeaveCriticalSection(this + 2);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v52);
}

```

## disassembly

```asm
0x180060c98  push    rbp
0x180060c9a  push    rbx
0x180060c9b  push    rsi
0x180060c9c  push    rdi
0x180060c9d  push    r12
0x180060c9f  push    r13
0x180060ca1  push    r14
0x180060ca3  push    r15
0x180060ca5  lea     rbp, [rsp-1Fh]
0x180060caa  sub     rsp, 0C8h
0x180060cb1  mov     r14, rdx
0x180060cb4  mov     rsi, rcx
0x180060cb7  lea     rdx, aCdshowsourcere_3; "CDShowSourceResolver::OnByteStreamCreat"...
0x180060cbe  mov     r8d, 1E9h; int
0x180060cc4  lea     rcx, [rbp+57h+arg_0]; this
0x180060cc8  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180060ccd  lea     rcx, [rsi+50h]; lpCriticalSection
0x180060cd1  call    cs:__imp_EnterCriticalSection
0x180060cd8  nop     dword ptr [rax+rax+00h]
0x180060cdd  and     [rbp+57h+var_A0], 0FFFFFFF8h
0x180060ce1  lea     rcx, [rbp+57h+var_88]; void *
0x180060ce5  xor     r12d, r12d
0x180060ce8  mov     [rbp+57h+var_48], 1
0x180060cef  xor     edx, edx; Val
0x180060cf1  mov     [rbp+57h+var_B0], r12
0x180060cf5  mov     [rbp+57h+var_B8], r12
0x180060cf9  mov     edi, r12d
0x180060cfc  mov     [rbp+57h+arg_10], r12
0x180060d00  mov     r15d, r12d
0x180060d03  lea     r8d, [r12+40h]; Size
0x180060d08  mov     [rbp+57h+var_C0], r12
0x180060d0c  mov     [rbp+57h+arg_8], r12d
0x180060d10  mov     [rbp+57h+arg_0], r12d
0x180060d14  mov     [rbp+57h+var_9C], r12
0x180060d18  mov     [rbp+57h+var_90], r12
0x180060d1c  mov     [rbp+57h+var_94], r12d
0x180060d20  call    cs:__imp_memset
0x180060d27  nop     dword ptr [rax+rax+00h]
0x180060d2c  mov     [rbp+57h+arg_18], r12
0x180060d30  test    r14, r14
0x180060d33  jnz     loc_180060DD3
0x180060d39  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180060d40  mov     ebx, 8000FFFFh
0x180060d45  test    rcx, rcx
0x180060d48  jnz     short loc_180060D91
0x180060d4a  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180060d51  nop     dword ptr [rax+rax+00h]
0x180060d56  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180060d5d  mov     rcx, rax
0x180060d60  test    rax, rax
0x180060d63  jz      short loc_180060D83
0x180060d65  mov     rax, [rax]
0x180060d68  mov     edx, 7F0h
0x180060d6d  mov     rax, [rax+8]
0x180060d71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060d76  test    eax, eax
0x180060d78  jz      short loc_180060D83
0x180060d7a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180060d81  jmp     short loc_180060D91
0x180060d83  lea     rcx, qword_1800EB130; this
0x180060d8a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180060d91  cmp     [rcx+8], r12b
0x180060d95  jz      short loc_180060DBC
0x180060d97  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180060d9c  cmp     [rax+7CCh], ebx
0x180060da2  jz      short loc_180060DBC
0x180060da4  mov     r9d, ebx; int
0x180060da7  lea     rdx, aCdshowsourcere_3; "CDShowSourceResolver::OnByteStreamCreat"...
0x180060dae  mov     r8d, 1FBh; int
0x180060db4  mov     rcx, rax; this
0x180060db7  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180060dbc  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180060dc3  jb      loc_180061449
0x180060dc9  mov     edx, 3Ah ; ':'
0x180060dce  jmp     loc_18006142B
0x180060dd3  mov     rax, [r14]
0x180060dd6  lea     rdx, [rbp+57h+var_B0]
0x180060dda  mov     rcx, r14
0x180060ddd  mov     rax, [rax+18h]
0x180060de1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060de6  mov     ebx, eax
0x180060de8  test    eax, eax
0x180060dea  jns     loc_180060E85
0x180060df0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180060df7  test    rcx, rcx
0x180060dfa  jnz     short loc_180060E43
0x180060dfc  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180060e03  nop     dword ptr [rax+rax+00h]
0x180060e08  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180060e0f  mov     rcx, rax
0x180060e12  test    rax, rax
0x180060e15  jz      short loc_180060E35
0x180060e17  mov     rax, [rax]
0x180060e1a  mov     edx, 7F0h
0x180060e1f  mov     rax, [rax+8]
0x180060e23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060e28  test    eax, eax
0x180060e2a  jz      short loc_180060E35
0x180060e2c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180060e33  jmp     short loc_180060E43
0x180060e35  lea     rcx, qword_1800EB130; this
0x180060e3c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180060e43  cmp     [rcx+8], r12b
0x180060e47  jz      short loc_180060E6E
0x180060e49  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180060e4e  cmp     [rax+7CCh], ebx
0x180060e54  jz      short loc_180060E6E
0x180060e56  mov     r9d, ebx; int
0x180060e59  lea     rdx, aCdshowsourcere_3; "CDShowSourceResolver::OnByteStreamCreat"...
0x180060e60  mov     r8d, 1FCh; int
0x180060e66  mov     rcx, rax; this
0x180060e69  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180060e6e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180060e75  jb      loc_180061449
0x180060e7b  mov     edx, 3Bh ; ';'
0x180060e80  jmp     loc_18006142B
0x180060e85  mov     rdi, [rbp+57h+var_B0]
0x180060e89  lea     r9, [rbp+57h+var_B8]
0x180060e8d  lea     r8, [rbp+57h+arg_8]
0x180060e91  mov     rdx, r14
0x180060e94  mov     rcx, [rdi+68h]
0x180060e98  mov     rax, [rcx]
0x180060e9b  mov     rax, [rax+30h]
0x180060e9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060ea4  mov     ebx, eax
0x180060ea6  test    eax, eax
0x180060ea8  jns     short loc_180060EB7
0x180060eaa  cmp     eax, 80070057h
0x180060eaf  jnz     short loc_180060F1D
0x180060eb1  mov     r12d, 1
0x180060eb7  cmp     [rdi+60h], r15d
0x180060ebb  jz      loc_180061002
0x180060ec1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180060ec8  xor     r12d, r12d
0x180060ecb  mov     ebx, 80004004h
0x180060ed0  test    rcx, rcx
0x180060ed3  jnz     loc_180060FC0
0x180060ed9  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180060ee0  nop     dword ptr [rax+rax+00h]
0x180060ee5  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180060eec  mov     rcx, rax
0x180060eef  test    rax, rax
0x180060ef2  jz      loc_180060FB2
0x180060ef8  mov     rax, [rax]
0x180060efb  mov     edx, 7F0h
0x180060f00  mov     rax, [rax+8]
0x180060f04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060f09  test    eax, eax
0x180060f0b  jz      loc_180060FB2
0x180060f11  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180060f18  jmp     loc_180060FC0
0x180060f1d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180060f24  test    rcx, rcx
0x180060f27  jnz     short loc_180060F70
0x180060f29  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180060f30  nop     dword ptr [rax+rax+00h]
0x180060f35  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180060f3c  mov     rcx, rax
0x180060f3f  test    rax, rax
0x180060f42  jz      short loc_180060F62
0x180060f44  mov     rax, [rax]
0x180060f47  mov     edx, 7F0h
0x180060f4c  mov     rax, [rax+8]
0x180060f50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060f55  test    eax, eax
0x180060f57  jz      short loc_180060F62
0x180060f59  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180060f60  jmp     short loc_180060F70
0x180060f62  lea     rcx, qword_1800EB130; this
0x180060f69  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180060f70  cmp     [rcx+8], r12b
0x180060f74  jz      short loc_180060F9B
0x180060f76  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180060f7b  cmp     [rax+7CCh], ebx
0x180060f81  jz      short loc_180060F9B
0x180060f83  mov     r9d, ebx; int
0x180060f86  lea     rdx, aCdshowsourcere_3; "CDShowSourceResolver::OnByteStreamCreat"...
0x180060f8d  mov     r8d, 212h; int
0x180060f93  mov     rcx, rax; this
0x180060f96  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180060f9b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180060fa2  jb      loc_180061449
0x180060fa8  mov     edx, 3Ch ; '<'
0x180060fad  jmp     loc_18006142B
0x180060fb2  lea     rcx, qword_1800EB130; this
0x180060fb9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180060fc0  cmp     [rcx+8], r12b
0x180060fc4  jz      short loc_180060FEB
0x180060fc6  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180060fcb  cmp     [rax+7CCh], ebx
0x180060fd1  jz      short loc_180060FEB
0x180060fd3  mov     r9d, ebx; int
0x180060fd6  lea     rdx, aCdshowsourcere_3; "CDShowSourceResolver::OnByteStreamCreat"...
0x180060fdd  mov     r8d, 21Bh; int
0x180060fe3  mov     rcx, rax; this
0x180060fe6  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180060feb  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180060ff2  jb      loc_180061449
0x180060ff8  mov     edx, 3Dh ; '='
0x180060ffd  jmp     loc_18006142B
0x180061002  lea     rcx, [rdi+0A4h]; this
0x180061009  lea     r8, [rbp+57h+arg_18]; void **
0x18006100d  lea     rdx, _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99; struct _GUID *
0x180061014  call    ?Get@CGITPtr@@QEAAJAEBU_GUID@@PEAPEAX@Z; CGITPtr::Get(_GUID const &,void * *)
0x180061019  test    r12d, r12d
0x18006101c  jnz     loc_18006132E
0x180061022  mov     rcx, [rbp+57h+var_B8]
0x180061026  lea     r8, [rbp+57h+arg_10]
0x18006102a  lea     rdx, _GUID_ad4c1b00_4bf7_422f_9175_756693d9130d
0x180061031  mov     rax, [rcx]
0x180061034  mov     rax, [rax]
0x180061037  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006103c  xor     r12d, r12d
0x18006103f  mov     ebx, eax
0x180061041  test    eax, eax
0x180061043  jns     loc_1800610DE
0x180061049  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180061050  test    rcx, rcx
0x180061053  jnz     short loc_18006109C
0x180061055  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18006105c  nop     dword ptr [rax+rax+00h]
0x180061061  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180061068  mov     rcx, rax
0x18006106b  test    rax, rax
0x18006106e  jz      short loc_18006108E
0x180061070  mov     rax, [rax]
0x180061073  mov     edx, 7F0h
0x180061078  mov     rax, [rax+8]
0x18006107c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061081  test    eax, eax
0x180061083  jz      short loc_18006108E
0x180061085  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006108c  jmp     short loc_18006109C
0x18006108e  lea     rcx, qword_1800EB130; this
0x180061095  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18006109c  cmp     [rcx+8], r12b
0x1800610a0  jz      short loc_1800610C7
0x1800610a2  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800610a7  cmp     [rax+7CCh], ebx
0x1800610ad  jz      short loc_1800610C7
0x1800610af  mov     r9d, ebx; int
0x1800610b2  lea     rdx, aCdshowsourcere_3; "CDShowSourceResolver::OnByteStreamCreat"...
0x1800610b9  mov     r8d, 226h; int
0x1800610bf  mov     rcx, rax; this
0x1800610c2  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800610c7  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800610ce  jb      loc_180061449
0x1800610d4  mov     edx, 3Eh ; '>'
0x1800610d9  jmp     loc_18006142B
0x1800610de  lea     r14, [rdi+88h]
0x1800610e5  mov     rcx, r14
0x1800610e8  call    ?PContents@?$CMFBaseStringT@G@@QEBAPEBGXZ; CMFBaseStringT<ushort>::PContents(void)
0x1800610ed  mov     rdx, rax; unsigned __int16 *
0x1800610f0  lea     rcx, [rbp+57h+var_A0]; this
0x1800610f4  call    ?Parse@CUri@@QEAAJPEBGJ@Z; CUri::Parse(ushort const *,long)
0x1800610f9  test    eax, eax
0x1800610fb  js      loc_1800611ED
0x180061101  lea     rcx, [rbp+57h+var_A0]
0x180061105  call    ?GetKnownScheme@CUri@@QEBA?AW4SCHEME@1@XZ; CUri::GetKnownScheme(void)
0x18006110a  cmp     eax, 1
0x18006110d  jz      loc_1800611ED
0x180061113  mov     eax, 1
0x180061118  cmp     cs:byte_1800EACCC, 8
0x18006111f  jb      short loc_18006114C
0x180061121  mov     rcx, cs:WPP_GLOBAL_Control
0x180061128  lea     r8, WPP_4f2c49dc30393f4458000cee70747074_Traceguids
0x18006112f  mov     edx, 40h ; '@'
0x180061134  mov     [rsp+100h+var_D8], r15d
0x180061139  mov     r9, rsi
0x18006113c  mov     dword ptr [rsp+100h+var_E0], eax
0x180061140  mov     rcx, [rcx+0B0h]
0x180061147  call    WPP_SF_qDD
0x18006114c  mov     r8, [rbp+57h+arg_18]
0x180061150  mov     rcx, r14
0x180061153  call    ?PContents@?$CMFBaseStringT@G@@QEBAPEBGXZ; CMFBaseStringT<ushort>::PContents(void)
0x180061158  mov     rcx, [rsi]
0x18006115b  mov     r9d, [rdi+0A0h]
0x180061162  mov     rdx, [rbp+57h+arg_10]
0x180061166  mov     r10, [rcx+20h]
0x18006116a  lea     rcx, [rbp+57h+var_C0]
0x18006116e  mov     [rsp+100h+var_D0], rcx
0x180061173  lea     rcx, [rbp+57h+arg_8]
0x180061177  mov     qword ptr [rsp+100h+var_D8], rcx
0x18006117c  mov     rcx, rsi
0x18006117f  mov     [rsp+100h+var_E0], r8
0x180061184  mov     r8, rax
0x180061187  mov     rax, r10
0x18006118a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006118f  mov     ebx, eax
0x180061191  test    eax, eax
0x180061193  jns     loc_180061331
0x180061199  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800611a0  test    rcx, rcx
0x1800611a3  jnz     loc_1800612EC
0x1800611a9  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800611b0  nop     dword ptr [rax+rax+00h]
0x1800611b5  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800611bc  mov     rcx, rax
0x1800611bf  test    rax, rax
0x1800611c2  jz      loc_1800612DE
  ... truncated ...
```
