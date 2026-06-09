# CSeqSourceStream::InitStream(IMFMediaStream *)

- ea: `0x1802b5e5c`
- end: `0x1802b6698`
- name: `?InitStream@CSeqSourceStream@@QEAAJPEAUIMFMediaStream@@@Z`
- size: `2108`
- prototype: `__int64 __fastcall(CSeqSourceStream *__hidden this, struct IMFMediaStream *)`
- caller_count: `2`
- callee_count: `12`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1801badbc`
- `0x180234a4c`

## callees

- `0x18002fee0`
- `0x18003ecb0`
- `0x1800402c0`
- `0x18004d118`
- `0x180050d6c`
- `0x180063f00`
- `0x180067eec`
- `0x1800ec0e0`
- `0x180106678`
- `0x1802540b8`
- `0x1802b5e5c`
- `0x180344d40`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x1802b6262`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x1802b6262`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x1802b6322`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x1802b63f2`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x1802b6322`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x1802b63f2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1802b5f04`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1802b5fcc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1802b6119`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1802b61d1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1802b6284`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1802b6344`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1802b6414`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1802b64d8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1802b65a7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1802b5f04`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1802b5fcc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1802b6119`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1802b61d1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1802b6284`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1802b6344`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1802b6414`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1802b64d8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1802b65a7`

## pseudocode

```c
__int64 __fastcall CSeqSourceStream::InitStream(GUID *this, struct IMFMediaStream *a2)
{
  __int64 v4; // rdx
  __int64 v5; // r8
  __int64 *v6; // rcx
  HRESULT v7; // edi
  CallStackTracing *v8; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v10; // rdx
  __int64 *v11; // rcx
  CallStackTracing *v12; // rax
  struct CallStackContext *v13; // rax
  int (__fastcall ***v14)(_QWORD, GUID *, _QWORD *); // rbx
  __int64 v15; // rdx
  __int64 v16; // r8
  __int64 *v17; // rcx
  CallStackTracing *v18; // rax
  struct CallStackContext *v19; // rax
  __int64 v20; // rdx
  __int64 v21; // rdx
  __int64 v22; // r8
  __int64 *v23; // rcx
  CallStackTracing *v24; // rax
  struct CallStackContext *v25; // rax
  __int64 v26; // rdx
  __int64 v27; // r8
  __int64 *v28; // rcx
  CallStackTracing *v29; // rax
  struct CallStackContext *v30; // rax
  __int64 v31; // rdx
  __int64 v32; // r8
  __int64 *v33; // rcx
  CallStackTracing *v34; // rax
  struct CallStackContext *v35; // rax
  __int64 v36; // rdx
  __int64 v37; // r8
  __int64 *v38; // rcx
  CallStackTracing *v39; // rax
  struct CallStackContext *v40; // rax
  __int64 v41; // rdx
  __int64 v42; // r8
  __int64 *v43; // rcx
  CallStackTracing *v44; // rax
  struct CallStackContext *v45; // rax
  __int64 v46; // rdx
  __int64 v47; // r8
  __int64 *v48; // rcx
  CallStackTracing *v49; // rax
  struct CallStackContext *v50; // rax
  __int64 v52; // [rsp+30h] [rbp-20h] BYREF
  struct IUnknown *v53; // [rsp+38h] [rbp-18h] BYREF
  LPUNKNOWN pUnk; // [rsp+40h] [rbp-10h] BYREF
  int (__fastcall ***v55)(_QWORD, GUID *, __int64 *); // [rsp+48h] [rbp-8h] BYREF
  __int64 v56; // [rsp+90h] [rbp+40h] BYREF
  LPSTREAM ppstm; // [rsp+A0h] [rbp+50h] BYREF
  __int64 v58; // [rsp+A8h] [rbp+58h] BYREF

  v55 = 0;
  v58 = 0;
  pUnk = 0;
  v53 = 0;
  v52 = 0;
  ppstm = 0;
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v56, "CSeqSourceStream::InitStream", 435);
  if ( (unsigned __int8)byte_1803CECE9 >= 8u )
    WPP_SF_qq(*((_QWORD *)WPP_GLOBAL_Control + 7), 21, &WPP_d90443cd628b30a662afd33318a02a36_Traceguids, this, a2);
  CAutoLockExclusiveT<IMFMultiReaderWriterLock>::CAutoLockExclusiveT<IMFMultiReaderWriterLock>(
    &v56,
    *(_QWORD *)this[2].Data4);
  if ( this[3].Data1 )
  {
    v6 = (__int64 *)CallStackTracing::s_wpInstance;
    v7 = -1072873851;
    if ( !CallStackTracing::s_wpInstance )
    {
      v8 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v4, v5);
      CallStackTracing::s_wpInstance = v8;
      if ( v8 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v8 + 8LL))(v8, 2032) )
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
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v6);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != -1072873851 )
        CallStackContext::TraceFailure(ThreadRelativeContext, "CSeqSourceStream::InitStream", 442, -1072873851);
    }
    if ( !g_wppLevels )
      goto LABEL_15;
    v10 = 22;
LABEL_14:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v10, &WPP_d90443cd628b30a662afd33318a02a36_Traceguids, this, v7);
LABEL_15:
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v56 + 32LL))(v56);
    goto LABEL_112;
  }
  if ( *(_QWORD *)this[4].Data4 )
  {
    v11 = (__int64 *)CallStackTracing::s_wpInstance;
    v7 = -1072875845;
    if ( !CallStackTracing::s_wpInstance )
    {
      v12 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v4, v5);
      CallStackTracing::s_wpInstance = v12;
      if ( v12 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v12 + 8LL))(v12, 2032) )
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
      v13 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v11);
      if ( *((_DWORD *)v13 + 499) != -1072875845 )
        CallStackContext::TraceFailure(v13, "CSeqSourceStream::InitStream", 448, -1072875845);
    }
    if ( !g_wppLevels )
      goto LABEL_15;
    v10 = 23;
    goto LABEL_14;
  }
  *(_QWORD *)this[4].Data4 = a2;
  v7 = 0;
  if ( a2 )
    ((void (__fastcall *)(struct IMFMediaStream *))a2->lpVtbl->AddRef)(a2);
  ComSmartPtr<CPMPStreamStub>::operator=(&v55, *(_QWORD *)this[4].Data4);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v56 + 32LL))(v56);
  v14 = v55;
  if ( v55 )
  {
    if ( (**v55)(v55, &IID_IMFRemoteProxy, &v58) < 0 )
    {
      v7 = (*v14)[4](v14, this + 14, 0);
      if ( v7 < 0 )
      {
        v48 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v49 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v46, v47);
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
          if ( *((_DWORD *)v50 + 499) != v7 )
            CallStackContext::TraceFailure(v50, "CSeqSourceStream::InitStream", 503, v7);
        }
        if ( g_wppLevels )
        {
          v20 = 31;
          goto LABEL_111;
        }
      }
    }
    else
    {
      if ( (unsigned __int8)byte_1803CECE9 >= 8u )
        WPP_SF_qq(*((_QWORD *)WPP_GLOBAL_Control + 7), 24, &WPP_d90443cd628b30a662afd33318a02a36_Traceguids, this, a2);
      v7 = (*(__int64 (__fastcall **)(__int64, GUID *, LPUNKNOWN *))(*(_QWORD *)v58 + 24LL))(
             v58,
             &IID_IMFMediaStream,
             &pUnk);
      if ( v7 >= 0 )
      {
        v7 = (*(__int64 (__fastcall **)(__int64, GUID *, __int64 *))(*(_QWORD *)v58 + 32LL))(v58, &IID_IMFPMPHost, &v52);
        if ( v7 >= 0 )
        {
          v7 = CreateStreamOnHGlobal(0, 1, &ppstm);
          if ( v7 >= 0 )
          {
            v7 = CoMarshalInterface(ppstm, &IID_IMFMediaStream, pUnk, 0, 0, 0);
            if ( v7 >= 0 )
            {
              v7 = CoMarshalInterface(
                     ppstm,
                     &IID_IMFSequencerRemoteStreamCallback,
                     (LPUNKNOWN)((unsigned __int64)&this[1] & -(__int64)(this != 0)),
                     0,
                     0,
                     0);
              if ( v7 >= 0 )
              {
                v7 = (*(__int64 (__fastcall **)(__int64, GUID *, LPSTREAM, GUID *, struct IUnknown **))(*(_QWORD *)v52 + 40LL))(
                       v52,
                       &CLSID_SequencerSourceRemoteStream,
                       ppstm,
                       &IID_IMFMediaStream,
                       &v53);
                if ( v7 >= 0 )
                {
                  CGITPtr::Set((CGITPtr *)&this[5], &GUID_d182108f_4ec6_443f_aa42_a71106ec825f, v53);
                  goto LABEL_112;
                }
                v43 = (__int64 *)CallStackTracing::s_wpInstance;
                if ( !CallStackTracing::s_wpInstance )
                {
                  v44 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v41, v42);
                  CallStackTracing::s_wpInstance = v44;
                  if ( v44
                    && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v44 + 8LL))(v44, 2032) )
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
                  if ( *((_DWORD *)v45 + 499) != v7 )
                    CallStackContext::TraceFailure(v45, "CSeqSourceStream::InitStream", 494, v7);
                }
                if ( g_wppLevels )
                {
                  v20 = 30;
                  goto LABEL_111;
                }
              }
              else
              {
                v38 = (__int64 *)CallStackTracing::s_wpInstance;
                if ( !CallStackTracing::s_wpInstance )
                {
                  v39 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v36, v37);
                  CallStackTracing::s_wpInstance = v39;
                  if ( v39
                    && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v39 + 8LL))(v39, 2032) )
                  {
                    v38 = (__int64 *)CallStackTracing::s_wpInstance;
                  }
                  else
                  {
                    v38 = &qword_1803CE250;
                    CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
                  }
                }
                if ( *((_BYTE *)v38 + 8) )
                {
                  v40 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v38);
                  if ( *((_DWORD *)v40 + 499) != v7 )
                    CallStackContext::TraceFailure(v40, "CSeqSourceStream::InitStream", 489, v7);
                }
                if ( g_wppLevels )
                {
                  v20 = 29;
                  goto LABEL_111;
                }
              }
            }
            else
            {
              v33 = (__int64 *)CallStackTracing::s_wpInstance;
              if ( !CallStackTracing::s_wpInstance )
              {
                v34 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v31, v32);
                CallStackTracing::s_wpInstance = v34;
                if ( v34
                  && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v34 + 8LL))(v34, 2032) )
                {
                  v33 = (__int64 *)CallStackTracing::s_wpInstance;
                }
                else
                {
                  v33 = &qword_1803CE250;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
                }
              }
              if ( *((_BYTE *)v33 + 8) )
              {
                v35 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v33);
                if ( *((_DWORD *)v35 + 499) != v7 )
                  CallStackContext::TraceFailure(v35, "CSeqSourceStream::InitStream", 482, v7);
              }
              if ( g_wppLevels )
              {
                v20 = 28;
                goto LABEL_111;
              }
            }
          }
          else
          {
            v28 = (__int64 *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v29 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v26, v27);
              CallStackTracing::s_wpInstance = v29;
              if ( v29
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v29 + 8LL))(v29, 2032) )
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
              v30 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v28);
              if ( *((_DWORD *)v30 + 499) != v7 )
                CallStackContext::TraceFailure(v30, "CSeqSourceStream::InitStream", 475, v7);
            }
            if ( g_wppLevels )
            {
              v20 = 27;
              goto LABEL_111;
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
            if ( *((_DWORD *)v25 + 499) != v7 )
              CallStackContext::TraceFailure(v25, "CSeqSourceStream::InitStream", 470, v7);
          }
          if ( g_wppLevels )
          {
            v20 = 26;
            goto LABEL_111;
          }
        }
      }
      else
      {
        v17 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v18 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v15, v16);
          CallStackTracing::s_wpInstance = v18;
          if ( v18 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v18 + 8LL))(v18, 2032) )
          {
            v17 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v17 = &qword_1803CE250;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
          }
        }
        if ( *((_BYTE *)v17 + 8) )
        {
          v19 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v17);
          if ( *((_DWORD *)v19 + 499) != v7 )
            CallStackContext::TraceFailure(v19, "CSeqSourceStream::InitStream", 467, v7);
        }
        if ( g_wppLevels )
        {
          v20 = 25;
LABEL_111:
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v20,
            &WPP_d90443cd628b30a662afd33318a02a36_Traceguids,
            this,
            v7);
        }
      }
    }
  }
LABEL_112:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v56);
  ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&ppstm);
  ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&v52);
  ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&v53);
  ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&pUnk);
  ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&v58);
  ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&v55);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1802b5e5c  mov     [rsp-38h+arg_8], rbx
0x1802b5e61  push    rbp
0x1802b5e62  push    rsi
0x1802b5e63  push    rdi
0x1802b5e64  push    r12
0x1802b5e66  push    r13
0x1802b5e68  push    r14
0x1802b5e6a  push    r15
0x1802b5e6c  mov     rbp, rsp
0x1802b5e6f  sub     rsp, 50h
0x1802b5e73  xor     r15d, r15d
0x1802b5e76  lea     r13, aCseqsourcestre_2; "CSeqSourceStream::InitStream"
0x1802b5e7d  mov     r14, rdx
0x1802b5e80  mov     [rbp+var_8], r15
0x1802b5e84  mov     rsi, rcx
0x1802b5e87  mov     [rbp+arg_18], r15
0x1802b5e8b  mov     rdx, r13; char *
0x1802b5e8e  mov     [rbp+pUnk], r15
0x1802b5e92  mov     r8d, 1B3h; int
0x1802b5e98  mov     [rbp+var_18], r15
0x1802b5e9c  lea     rcx, [rbp+arg_0]; this
0x1802b5ea0  mov     [rbp+var_20], r15
0x1802b5ea4  mov     [rbp+ppstm], r15
0x1802b5ea8  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1802b5ead  cmp     cs:byte_1803CECE9, 8
0x1802b5eb4  lea     r12, WPP_d90443cd628b30a662afd33318a02a36_Traceguids
0x1802b5ebb  jb      short loc_1802B5EDC
0x1802b5ebd  mov     rcx, cs:WPP_GLOBAL_Control
0x1802b5ec4  lea     edx, [r15+15h]
0x1802b5ec8  mov     r9, rsi
0x1802b5ecb  mov     [rsp+50h+pvDestContext], r14
0x1802b5ed0  mov     r8, r12
0x1802b5ed3  mov     rcx, [rcx+38h]
0x1802b5ed7  call    WPP_SF_qq
0x1802b5edc  mov     rdx, [rsi+28h]
0x1802b5ee0  lea     rcx, [rbp+arg_0]
0x1802b5ee4  call    ??0?$CAutoLockExclusiveT@UIMFMultiReaderWriterLock@@@@QEAA@PEAUIMFMultiReaderWriterLock@@@Z; CAutoLockExclusiveT<IMFMultiReaderWriterLock>::CAutoLockExclusiveT<IMFMultiReaderWriterLock>(IMFMultiReaderWriterLock *)
0x1802b5ee9  cmp     [rsi+30h], r15d
0x1802b5eed  jz      loc_1802B5FB1
0x1802b5ef3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1802b5efa  mov     edi, 0C00D3E85h
0x1802b5eff  test    rcx, rcx
0x1802b5f02  jnz     short loc_1802B5F4C
0x1802b5f04  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1802b5f0b  nop     dword ptr [rax+rax+00h]
0x1802b5f10  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1802b5f17  mov     rcx, rax
0x1802b5f1a  test    rax, rax
0x1802b5f1d  jz      short loc_1802B5F3E
0x1802b5f1f  mov     rax, [rax]
0x1802b5f22  mov     edx, 7F0h
0x1802b5f27  mov     rax, [rax+8]
0x1802b5f2b  call    cs:__guard_dispatch_icall_fptr
0x1802b5f31  test    eax, eax
0x1802b5f33  jz      short loc_1802B5F3E
0x1802b5f35  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1802b5f3c  jmp     short loc_1802B5F4C
0x1802b5f3e  lea     rcx, qword_1803CE250; this
0x1802b5f45  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1802b5f4c  cmp     [rcx+8], r15b
0x1802b5f50  jz      short loc_1802B5F73
0x1802b5f52  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1802b5f57  cmp     [rax+7CCh], edi
0x1802b5f5d  jz      short loc_1802B5F73
0x1802b5f5f  mov     r9d, edi; int
0x1802b5f62  mov     r8d, 1BAh; int
0x1802b5f68  mov     rdx, r13; char *
0x1802b5f6b  mov     rcx, rax; this
0x1802b5f6e  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1802b5f73  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1802b5f7a  jb      short loc_1802B5F9B
0x1802b5f7c  mov     edx, 16h
0x1802b5f81  mov     rcx, cs:WPP_GLOBAL_Control
0x1802b5f88  mov     r9, rsi
0x1802b5f8b  mov     r8, r12
0x1802b5f8e  mov     dword ptr [rsp+50h+pvDestContext], edi
0x1802b5f92  mov     rcx, [rcx+10h]
0x1802b5f96  call    WPP_SF_qD
0x1802b5f9b  mov     rcx, [rbp+arg_0]
0x1802b5f9f  mov     rax, [rcx]
0x1802b5fa2  mov     rax, [rax+20h]
0x1802b5fa6  call    cs:__guard_dispatch_icall_fptr
0x1802b5fac  jmp     loc_1802B663E
0x1802b5fb1  cmp     [rsi+48h], r15
0x1802b5fb5  jz      loc_1802B6052
0x1802b5fbb  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1802b5fc2  mov     edi, 0C00D36BBh
0x1802b5fc7  test    rcx, rcx
0x1802b5fca  jnz     short loc_1802B6014
0x1802b5fcc  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1802b5fd3  nop     dword ptr [rax+rax+00h]
0x1802b5fd8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1802b5fdf  mov     rcx, rax
0x1802b5fe2  test    rax, rax
0x1802b5fe5  jz      short loc_1802B6006
0x1802b5fe7  mov     rax, [rax]
0x1802b5fea  mov     edx, 7F0h
0x1802b5fef  mov     rax, [rax+8]
0x1802b5ff3  call    cs:__guard_dispatch_icall_fptr
0x1802b5ff9  test    eax, eax
0x1802b5ffb  jz      short loc_1802B6006
0x1802b5ffd  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1802b6004  jmp     short loc_1802B6014
0x1802b6006  lea     rcx, qword_1803CE250; this
0x1802b600d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1802b6014  cmp     [rcx+8], r15b
0x1802b6018  jz      short loc_1802B603B
0x1802b601a  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1802b601f  cmp     [rax+7CCh], edi
0x1802b6025  jz      short loc_1802B603B
0x1802b6027  mov     r9d, edi; int
0x1802b602a  mov     r8d, 1C0h; int
0x1802b6030  mov     rdx, r13; char *
0x1802b6033  mov     rcx, rax; this
0x1802b6036  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1802b603b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1802b6042  jb      loc_1802B5F9B
0x1802b6048  mov     edx, 17h
0x1802b604d  jmp     loc_1802B5F81
0x1802b6052  mov     [rsi+48h], r14
0x1802b6056  mov     edi, r15d
0x1802b6059  test    r14, r14
0x1802b605c  jz      short loc_1802B606E
0x1802b605e  mov     rax, [r14]
0x1802b6061  mov     rcx, r14
0x1802b6064  mov     rax, [rax+8]
0x1802b6068  call    cs:__guard_dispatch_icall_fptr
0x1802b606e  mov     rdx, [rsi+48h]
0x1802b6072  lea     rcx, [rbp+var_8]
0x1802b6076  call    ??4?$ComSmartPtr@VCPMPStreamStub@@@@QEAAPEAVCPMPStreamStub@@PEAV1@@Z; ComSmartPtr<CPMPStreamStub>::operator=(CPMPStreamStub *)
0x1802b607b  mov     rcx, [rbp+arg_0]
0x1802b607f  mov     rax, [rcx]
0x1802b6082  mov     rax, [rax+20h]
0x1802b6086  call    cs:__guard_dispatch_icall_fptr
0x1802b608c  mov     rbx, [rbp+var_8]
0x1802b6090  test    rbx, rbx
0x1802b6093  jz      loc_1802B663E
0x1802b6099  mov     rax, [rbx]
0x1802b609c  lea     r8, [rbp+arg_18]
0x1802b60a0  lea     rdx, IID_IMFRemoteProxy
0x1802b60a7  mov     rcx, rbx
0x1802b60aa  mov     rax, [rax]
0x1802b60ad  call    cs:__guard_dispatch_icall_fptr
0x1802b60b3  test    eax, eax
0x1802b60b5  js      loc_1802B6577
0x1802b60bb  cmp     cs:byte_1803CECE9, 8
0x1802b60c2  jb      short loc_1802B60E4
0x1802b60c4  mov     rcx, cs:WPP_GLOBAL_Control
0x1802b60cb  mov     edx, 18h
0x1802b60d0  mov     r9, rsi
0x1802b60d3  mov     [rsp+50h+pvDestContext], r14
0x1802b60d8  mov     r8, r12
0x1802b60db  mov     rcx, [rcx+38h]
0x1802b60df  call    WPP_SF_qq
0x1802b60e4  mov     rcx, [rbp+arg_18]
0x1802b60e8  lea     rbx, IID_IMFMediaStream
0x1802b60ef  lea     r8, [rbp+pUnk]
0x1802b60f3  mov     rdx, rbx
0x1802b60f6  mov     rax, [rcx]
0x1802b60f9  mov     rax, [rax+18h]
0x1802b60fd  call    cs:__guard_dispatch_icall_fptr
0x1802b6103  mov     edi, eax
0x1802b6105  test    eax, eax
0x1802b6107  jns     loc_1802B619F
0x1802b610d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1802b6114  test    rcx, rcx
0x1802b6117  jnz     short loc_1802B6161
0x1802b6119  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1802b6120  nop     dword ptr [rax+rax+00h]
0x1802b6125  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1802b612c  mov     rcx, rax
0x1802b612f  test    rax, rax
0x1802b6132  jz      short loc_1802B6153
0x1802b6134  mov     rax, [rax]
0x1802b6137  mov     edx, 7F0h
0x1802b613c  mov     rax, [rax+8]
0x1802b6140  call    cs:__guard_dispatch_icall_fptr
0x1802b6146  test    eax, eax
0x1802b6148  jz      short loc_1802B6153
0x1802b614a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1802b6151  jmp     short loc_1802B6161
0x1802b6153  lea     rcx, qword_1803CE250; this
0x1802b615a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1802b6161  cmp     [rcx+8], r15b
0x1802b6165  jz      short loc_1802B6188
0x1802b6167  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1802b616c  cmp     [rax+7CCh], edi
0x1802b6172  jz      short loc_1802B6188
0x1802b6174  mov     r9d, edi; int
0x1802b6177  mov     r8d, 1D3h; int
0x1802b617d  mov     rdx, r13; char *
0x1802b6180  mov     rcx, rax; this
0x1802b6183  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1802b6188  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1802b618f  jb      loc_1802B663E
0x1802b6195  mov     edx, 19h
0x1802b619a  jmp     loc_1802B6624
0x1802b619f  mov     rcx, [rbp+arg_18]
0x1802b61a3  lea     r8, [rbp+var_20]
0x1802b61a7  lea     rdx, IID_IMFPMPHost
0x1802b61ae  mov     rax, [rcx]
0x1802b61b1  mov     rax, [rax+20h]
0x1802b61b5  call    cs:__guard_dispatch_icall_fptr
0x1802b61bb  mov     edi, eax
0x1802b61bd  test    eax, eax
0x1802b61bf  jns     loc_1802B6257
0x1802b61c5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1802b61cc  test    rcx, rcx
0x1802b61cf  jnz     short loc_1802B6219
0x1802b61d1  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1802b61d8  nop     dword ptr [rax+rax+00h]
0x1802b61dd  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1802b61e4  mov     rcx, rax
0x1802b61e7  test    rax, rax
0x1802b61ea  jz      short loc_1802B620B
0x1802b61ec  mov     rax, [rax]
0x1802b61ef  mov     edx, 7F0h
0x1802b61f4  mov     rax, [rax+8]
0x1802b61f8  call    cs:__guard_dispatch_icall_fptr
0x1802b61fe  test    eax, eax
0x1802b6200  jz      short loc_1802B620B
0x1802b6202  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1802b6209  jmp     short loc_1802B6219
0x1802b620b  lea     rcx, qword_1803CE250; this
0x1802b6212  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1802b6219  cmp     [rcx+8], r15b
0x1802b621d  jz      short loc_1802B6240
0x1802b621f  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1802b6224  cmp     [rax+7CCh], edi
0x1802b622a  jz      short loc_1802B6240
0x1802b622c  mov     r9d, edi; int
0x1802b622f  mov     r8d, 1D6h; int
0x1802b6235  mov     rdx, r13; char *
0x1802b6238  mov     rcx, rax; this
0x1802b623b  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1802b6240  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1802b6247  jb      loc_1802B663E
0x1802b624d  mov     edx, 1Ah
0x1802b6252  jmp     loc_1802B6624
0x1802b6257  lea     r8, [rbp+ppstm]; ppstm
0x1802b625b  mov     edx, 1; fDeleteOnRelease
0x1802b6260  xor     ecx, ecx; hGlobal
0x1802b6262  call    cs:__imp_CreateStreamOnHGlobal
0x1802b6269  nop     dword ptr [rax+rax+00h]
0x1802b626e  mov     edi, eax
0x1802b6270  test    eax, eax
0x1802b6272  jns     loc_1802B630A
0x1802b6278  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1802b627f  test    rcx, rcx
0x1802b6282  jnz     short loc_1802B62CC
0x1802b6284  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1802b628b  nop     dword ptr [rax+rax+00h]
0x1802b6290  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1802b6297  mov     rcx, rax
0x1802b629a  test    rax, rax
0x1802b629d  jz      short loc_1802B62BE
0x1802b629f  mov     rax, [rax]
0x1802b62a2  mov     edx, 7F0h
0x1802b62a7  mov     rax, [rax+8]
0x1802b62ab  call    cs:__guard_dispatch_icall_fptr
0x1802b62b1  test    eax, eax
0x1802b62b3  jz      short loc_1802B62BE
0x1802b62b5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1802b62bc  jmp     short loc_1802B62CC
0x1802b62be  lea     rcx, qword_1803CE250; this
0x1802b62c5  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1802b62cc  cmp     [rcx+8], r15b
0x1802b62d0  jz      short loc_1802B62F3
0x1802b62d2  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1802b62d7  cmp     [rax+7CCh], edi
0x1802b62dd  jz      short loc_1802B62F3
0x1802b62df  mov     r9d, edi; int
0x1802b62e2  mov     r8d, 1DBh; int
0x1802b62e8  mov     rdx, r13; char *
0x1802b62eb  mov     rcx, rax; this
0x1802b62ee  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1802b62f3  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1802b62fa  jb      loc_1802B663E
0x1802b6300  mov     edx, 1Bh
0x1802b6305  jmp     loc_1802B6624
0x1802b630a  mov     r8, [rbp+pUnk]; pUnk
0x1802b630e  xor     r9d, r9d; dwDestContext
0x1802b6311  mov     rcx, [rbp+ppstm]; pStm
0x1802b6315  mov     rdx, rbx; riid
0x1802b6318  mov     [rsp+50h+mshlflags], r15d; mshlflags
0x1802b631d  mov     [rsp+50h+pvDestContext], r15; pvDestContext
0x1802b6322  call    cs:__imp_CoMarshalInterface
0x1802b6329  nop     dword ptr [rax+rax+00h]
0x1802b632e  mov     edi, eax
0x1802b6330  test    eax, eax
0x1802b6332  jns     loc_1802B63CA
0x1802b6338  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1802b633f  test    rcx, rcx
0x1802b6342  jnz     short loc_1802B638C
0x1802b6344  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1802b634b  nop     dword ptr [rax+rax+00h]
0x1802b6350  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1802b6357  mov     rcx, rax
0x1802b635a  test    rax, rax
0x1802b635d  jz      short loc_1802B637E
  ... truncated ...
```
