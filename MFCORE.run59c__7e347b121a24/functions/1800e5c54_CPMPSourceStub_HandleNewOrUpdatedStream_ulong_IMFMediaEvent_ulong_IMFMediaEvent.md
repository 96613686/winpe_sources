# CPMPSourceStub::HandleNewOrUpdatedStream(ulong,IMFMediaEvent *,ulong *,IMFMediaEvent * *)

- ea: `0x1800e5c54`
- end: `0x1800e6509`
- name: `?HandleNewOrUpdatedStream@CPMPSourceStub@@IEAAJKPEAUIMFMediaEvent@@PEAKPEAPEAU2@@Z`
- size: `2229`
- prototype: `__int64 __usercall@<rax>(CPMPSourceStub *__hidden this@<rcx>, MediaEventType met@<edx>, struct IMFMediaEvent *@<r8>, unsigned int *@<r9>, struct IMFMediaEvent **)`
- caller_count: `1`
- callee_count: `15`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18015d9c8`

## callees

- `0x18002fee0`
- `0x18003ecb0`
- `0x1800402c0`
- `0x180050d6c`
- `0x180063f00`
- `0x180067eec`
- `0x18006b388`
- `0x1800717b4`
- `0x1800e5c54`
- `0x1800e6510`
- `0x1800e65b4`
- `0x1800ec0e0`
- `0x1802583a8`
- `0x1802ae5a4`
- `0x180344d40`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800e5ccf`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800e5d9f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800e5e57`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800e5fd0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800e615b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800e6251`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800e63bc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800e647f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800e5ccf`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800e5d9f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800e5e57`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800e5fd0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800e615b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800e6251`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800e63bc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800e647f`
- `MFPlat!MFCreateMediaEvent` at `0x1800e622f`
- `MFPlat!MFCreateMediaEvent` at `0x1800e6397`
- `MFPlat!MFCreateMediaEvent` at `0x1800e622f`
- `MFPlat!MFCreateMediaEvent` at `0x1800e6397`

## string_xrefs

- `0x1800e5c8c`: `CPMPSourceStub::HandleNewOrUpdatedStream`
- `0x1800e5d2d`: `CPMPSourceStub::HandleNewOrUpdatedStream`
- `0x1800e5dfd`: `CPMPSourceStub::HandleNewOrUpdatedStream`
- `0x1800e5eb5`: `CPMPSourceStub::HandleNewOrUpdatedStream`
- `0x1800e602e`: `CPMPSourceStub::HandleNewOrUpdatedStream`
- `0x1800e61b9`: `CPMPSourceStub::HandleNewOrUpdatedStream`
- `0x1800e62af`: `CPMPSourceStub::HandleNewOrUpdatedStream`
- `0x1800e641a`: `CPMPSourceStub::HandleNewOrUpdatedStream`
- `0x1800e64dd`: `CPMPSourceStub::HandleNewOrUpdatedStream`

## pseudocode

```c
__int64 __fastcall CPMPSourceStub::HandleNewOrUpdatedStream(
        CPMPSourceStub *this,
        MediaEventType met,
        struct IMFMediaEvent *a3,
        unsigned int *a4,
        struct IMFMediaEvent **ppEvent)
{
  _DWORD *v9; // rsi
  __int64 v10; // rdx
  HRESULT Unknown; // ebx
  __int64 v12; // r8
  __int64 *v13; // rcx
  CallStackTracing *v14; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v16; // rdx
  __int64 v17; // rdx
  __int64 v18; // r8
  __int64 *v19; // rcx
  CallStackTracing *v20; // rax
  struct CallStackContext *v21; // rax
  __int64 v22; // rdx
  __int64 v23; // r8
  __int64 *v24; // rcx
  CallStackTracing *v25; // rax
  struct CallStackContext *v26; // rax
  struct CPMPStreamStub *v27; // rax
  CPMPStreamStub *v28; // rax
  CPMPStreamStub *v29; // rax
  __int64 v30; // rdx
  __int64 v31; // r8
  __int64 *v32; // rcx
  CallStackTracing *v33; // rax
  struct CallStackContext *v34; // rax
  _QWORD *v35; // rax
  __int64 v36; // rdx
  __int64 v37; // r8
  __int64 *v38; // rcx
  CallStackTracing *v39; // rax
  struct CallStackContext *v40; // rax
  __int64 v41; // rdx
  __int64 v42; // rdx
  __int64 v43; // r8
  __int64 *v44; // rcx
  CallStackTracing *v45; // rax
  struct CallStackContext *v46; // rax
  __int64 v48; // rdx
  __int64 v49; // r8
  __int64 *v50; // rcx
  CallStackTracing *v51; // rax
  struct CallStackContext *v52; // rax
  __int64 v53; // rdx
  __int64 v54; // r8
  __int64 *v55; // rcx
  CallStackTracing *v56; // rax
  struct CallStackContext *v57; // rax
  _BYTE v58[4]; // [rsp+30h] [rbp-48h] BYREF
  unsigned int v59; // [rsp+34h] [rbp-44h] BYREF
  struct IMFMediaStream *v60; // [rsp+38h] [rbp-40h] BYREF
  _DWORD *v61; // [rsp+40h] [rbp-38h] BYREF
  __int64 v62; // [rsp+48h] [rbp-30h] BYREF
  __int64 v63; // [rsp+50h] [rbp-28h] BYREF
  PROPVARIANT pvValue[2]; // [rsp+58h] [rbp-20h] BYREF
  __int64 v65; // [rsp+68h] [rbp-10h]

  v60 = 0;
  v63 = 0;
  v61 = 0;
  v62 = 0;
  v59 = 0;
  v9 = 0;
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v58, "CPMPSourceStub::HandleNewOrUpdatedStream", 777);
  Unknown = CMediaEventPtr::GetUnknown(a3, &IID_IMFMediaStream, (void **)&v60);
  if ( Unknown < 0 )
  {
    v13 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v14 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v10, v12);
      CallStackTracing::s_wpInstance = v14;
      if ( v14 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v14 + 8LL))(v14, 2032) )
      {
        v13 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v13 = &qword_1803CE250;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
      }
    }
    if ( *((_BYTE *)v13 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v13);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != Unknown )
        CallStackContext::TraceFailure(ThreadRelativeContext, "CPMPSourceStub::HandleNewOrUpdatedStream", 777, Unknown);
    }
    if ( g_wppLevels )
    {
      v16 = 54;
LABEL_12:
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v16,
        &WPP_bc4c13183d93354ba90b2bb655eeb28d_Traceguids,
        this,
        Unknown);
      goto LABEL_88;
    }
    goto LABEL_88;
  }
  Unknown = ((__int64 (__fastcall *)(struct IMFMediaStream *, __int64 *))v60->lpVtbl->GetStreamDescriptor)(v60, &v63);
  if ( Unknown >= 0 )
  {
    Unknown = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v63 + 264LL))(v63, &v59);
    if ( Unknown < 0 )
    {
      v24 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v25 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v22, v23);
        CallStackTracing::s_wpInstance = v25;
        if ( v25 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v25 + 8LL))(v25, 2032) )
        {
          v24 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v24 = &qword_1803CE250;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
        }
      }
      if ( *((_BYTE *)v24 + 8) )
      {
        v26 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v24);
        if ( *((_DWORD *)v26 + 499) != Unknown )
          CallStackContext::TraceFailure(v26, "CPMPSourceStub::HandleNewOrUpdatedStream", 781, Unknown);
      }
      if ( g_wppLevels )
      {
        v16 = 56;
        goto LABEL_12;
      }
      goto LABEL_88;
    }
    v27 = CPMPStreamStubList::FindById((CPMPSourceStub *)((char *)this + 64), v59);
    ComSmartPtr<CPMPStreamStub>::operator=(&v61, v27);
    v9 = v61;
    if ( v61 )
    {
      if ( v61[9] )
      {
        if ( (unsigned __int8)byte_1803CECE9 >= 0x10u )
          WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 7), 57, &WPP_bc4c13183d93354ba90b2bb655eeb28d_Traceguids, this);
        v9[9] = 0;
      }
      else
      {
        v61[8] = *((_DWORD *)this + 94);
        if ( (unsigned __int8)byte_1803CECE9 >= 0x10u )
          WPP_SF_qqD(
            *((_QWORD *)WPP_GLOBAL_Control + 7),
            58,
            &WPP_bc4c13183d93354ba90b2bb655eeb28d_Traceguids,
            this,
            v9,
            v59);
      }
    }
    else
    {
      v28 = (CPMPStreamStub *)operator new(0x60u);
      if ( v28 )
        v29 = CPMPStreamStub::CPMPStreamStub(v28, this, v60, v59);
      else
        v29 = 0;
      ComSmartPtr<CPMPStreamStub>::operator=(&v61, v29);
      v9 = v61;
      if ( !v61 )
      {
        v32 = (__int64 *)CallStackTracing::s_wpInstance;
        Unknown = -2147024882;
        if ( !CallStackTracing::s_wpInstance )
        {
          v33 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v30, v31);
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
          if ( *((_DWORD *)v34 + 499) != -2147024882 )
            CallStackContext::TraceFailure(v34, "CPMPSourceStub::HandleNewOrUpdatedStream", 808, -2147024882);
        }
        if ( g_wppLevels )
        {
          v16 = 59;
          goto LABEL_12;
        }
        goto LABEL_88;
      }
      if ( (unsigned __int8)byte_1803CECE9 >= 0x10u )
        WPP_SF_qqD(
          *((_QWORD *)WPP_GLOBAL_Control + 7),
          60,
          &WPP_bc4c13183d93354ba90b2bb655eeb28d_Traceguids,
          this,
          v61,
          v59);
      v35 = (_QWORD *)*((_QWORD *)this + 10);
      *((_QWORD *)v9 + 2) = (char *)this + 72;
      *((_QWORD *)v9 + 3) = v35;
      *v35 = v9 + 4;
      ++*((_DWORD *)this + 16);
      *((_QWORD *)this + 10) = v9 + 4;
      (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v9 + 8LL))(v9);
      v9[8] = *((_DWORD *)this + 94);
    }
    if ( ((__int64 (__fastcall *)(struct IMFMediaStream *, GUID *, __int64 *))v60->lpVtbl->QueryInterface)(
           v60,
           &IID_IMFRemoteProxy,
           &v62) < 0 )
    {
      v65 = 0;
      pvValue[0] = (PROPVARIANT)13;
      pvValue[1] = v60;
      Unknown = MFCreateMediaEvent(met, &GUID_00000000_0000_0000_0000_000000000000, 0, pvValue, ppEvent);
      if ( Unknown < 0 )
      {
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
          v52 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v50);
          if ( *((_DWORD *)v52 + 499) != Unknown )
            CallStackContext::TraceFailure(v52, "CPMPSourceStub::HandleNewOrUpdatedStream", 858, Unknown);
        }
        if ( g_wppLevels )
        {
          v16 = 64;
          goto LABEL_12;
        }
        goto LABEL_88;
      }
      Unknown = ((__int64 (__fastcall *)(_QWORD, void *, __int64))(*ppEvent)->lpVtbl->SetUINT32)(
                  *ppEvent,
                  &MF_PMP_REMOTE_STREAM,
                  1);
      if ( Unknown < 0 )
      {
        v55 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v56 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v53, v54);
          CallStackTracing::s_wpInstance = v56;
          if ( v56 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v56 + 8LL))(v56, 2032) )
          {
            v55 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v55 = &qword_1803CE250;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
          }
        }
        if ( *((_BYTE *)v55 + 8) )
        {
          v57 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v55);
          if ( *((_DWORD *)v57 + 499) != Unknown )
            CallStackContext::TraceFailure(v57, "CPMPSourceStub::HandleNewOrUpdatedStream", 859, Unknown);
        }
        if ( g_wppLevels )
        {
          v16 = 65;
          goto LABEL_12;
        }
        goto LABEL_88;
      }
    }
    else
    {
      if ( (unsigned __int8)byte_1803CECE9 >= 0x10u )
        WPP_SF_qqD(
          *((_QWORD *)WPP_GLOBAL_Control + 7),
          61,
          &WPP_bc4c13183d93354ba90b2bb655eeb28d_Traceguids,
          this,
          v9,
          v59);
      v61 = 0;
      v65 = 0;
      *(_OWORD *)pvValue = 0;
      Unknown = (*(__int64 (__fastcall **)(__int64, GUID *, _DWORD **))(*(_QWORD *)v62 + 24LL))(
                  v62,
                  &IID_IMFMediaStream,
                  &v61);
      if ( Unknown < 0 )
      {
        v38 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v39 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v36, v37);
          CallStackTracing::s_wpInstance = v39;
          if ( v39 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v39 + 8LL))(v39, 2032) )
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
          if ( *((_DWORD *)v40 + 499) != Unknown )
            CallStackContext::TraceFailure(v40, "CPMPSourceStub::HandleNewOrUpdatedStream", 844, Unknown);
        }
        if ( !g_wppLevels )
          goto LABEL_74;
        v41 = 62;
LABEL_73:
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v41,
          &WPP_bc4c13183d93354ba90b2bb655eeb28d_Traceguids,
          this,
          Unknown);
LABEL_74:
        ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&v61);
        goto LABEL_88;
      }
      LOWORD(pvValue[0]) = 13;
      pvValue[1] = v61;
      Unknown = MFCreateMediaEvent(met, &GUID_00000000_0000_0000_0000_000000000000, 0, pvValue, ppEvent);
      if ( Unknown < 0 )
      {
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
          v46 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v44);
          if ( *((_DWORD *)v46 + 499) != Unknown )
            CallStackContext::TraceFailure(v46, "CPMPSourceStub::HandleNewOrUpdatedStream", 848, Unknown);
        }
        if ( !g_wppLevels )
          goto LABEL_74;
        v41 = 63;
        goto LABEL_73;
      }
      ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&v61);
    }
    *a4 = v9[18];
    goto LABEL_88;
  }
  v19 = (__int64 *)CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    v20 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v17, v18);
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
    v21 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v19);
    if ( *((_DWORD *)v21 + 499) != Unknown )
      CallStackContext::TraceFailure(v21, "CPMPSourceStub::HandleNewOrUpdatedStream", 779, Unknown);
  }
  if ( g_wppLevels )
  {
    v16 = 55;
    goto LABEL_12;
  }
LABEL_88:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v58);
  if ( v62 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v62 + 16LL))(v62);
  if ( v9 )
    (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v9 + 16LL))(v9);
  if ( v63 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v63 + 16LL))(v63);
  if ( v60 )
    ((void (__fastcall *)(struct IMFMediaStream *))v60->lpVtbl->Release)(v60);
  return (unsigned int)Unknown;
}

```

## disassembly

```asm
0x1800e5c54  push    rbp
0x1800e5c56  push    rbx
0x1800e5c57  push    rsi
0x1800e5c58  push    rdi
0x1800e5c59  push    r12
0x1800e5c5b  push    r13
0x1800e5c5d  push    r14
0x1800e5c5f  push    r15
0x1800e5c61  mov     rbp, rsp
0x1800e5c64  sub     rsp, 78h
0x1800e5c68  xor     r15d, r15d
0x1800e5c6b  mov     rbx, r8
0x1800e5c6e  mov     r13d, edx
0x1800e5c71  mov     [rbp+var_40], r15
0x1800e5c75  mov     r14, rcx
0x1800e5c78  mov     [rbp+var_28], r15
0x1800e5c7c  mov     edi, 309h
0x1800e5c81  mov     [rbp+var_38], r15
0x1800e5c85  mov     r8d, edi; int
0x1800e5c88  mov     [rbp+var_30], r15
0x1800e5c8c  lea     rdx, aCpmpsourcestub_10; "CPMPSourceStub::HandleNewOrUpdatedStrea"...
0x1800e5c93  mov     [rbp+var_44], r15d
0x1800e5c97  lea     rcx, [rbp+var_48]; this
0x1800e5c9b  mov     r12, r9
0x1800e5c9e  mov     esi, r15d
0x1800e5ca1  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800e5ca6  lea     r8, [rbp+var_40]; void **
0x1800e5caa  mov     rcx, rbx; struct IMFMediaEvent *
0x1800e5cad  lea     rdx, IID_IMFMediaStream; struct _GUID *
0x1800e5cb4  call    ?GetUnknown@CMediaEventPtr@@SAJPEAUIMFMediaEvent@@AEBU_GUID@@PEAPEAX@Z; CMediaEventPtr::GetUnknown(IMFMediaEvent *,_GUID const &,void * *)
0x1800e5cb9  mov     ebx, eax
0x1800e5cbb  test    eax, eax
0x1800e5cbd  jns     loc_1800E5D74
0x1800e5cc3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800e5cca  test    rcx, rcx
0x1800e5ccd  jnz     short loc_1800E5D17
0x1800e5ccf  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800e5cd6  nop     dword ptr [rax+rax+00h]
0x1800e5cdb  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800e5ce2  mov     rcx, rax
0x1800e5ce5  test    rax, rax
0x1800e5ce8  jz      short loc_1800E5D09
0x1800e5cea  mov     rax, [rax]
0x1800e5ced  mov     edx, 7F0h
0x1800e5cf2  mov     rax, [rax+8]
0x1800e5cf6  call    cs:__guard_dispatch_icall_fptr
0x1800e5cfc  test    eax, eax
0x1800e5cfe  jz      short loc_1800E5D09
0x1800e5d00  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800e5d07  jmp     short loc_1800E5D17
0x1800e5d09  lea     rcx, qword_1803CE250; this
0x1800e5d10  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800e5d17  cmp     [rcx+8], r15b
0x1800e5d1b  jz      short loc_1800E5D3F
0x1800e5d1d  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800e5d22  cmp     [rax+7CCh], ebx
0x1800e5d28  jz      short loc_1800E5D3F
0x1800e5d2a  mov     r9d, ebx; int
0x1800e5d2d  lea     rdx, aCpmpsourcestub_10; "CPMPSourceStub::HandleNewOrUpdatedStrea"...
0x1800e5d34  mov     r8d, edi; int
0x1800e5d37  mov     rcx, rax; this
0x1800e5d3a  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800e5d3f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800e5d46  jb      loc_1800E62EB
0x1800e5d4c  mov     edx, 36h ; '6'
0x1800e5d51  lea     r8, WPP_bc4c13183d93354ba90b2bb655eeb28d_Traceguids
0x1800e5d58  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e5d5f  mov     r9, r14
0x1800e5d62  mov     dword ptr [rsp+78h+ppEvent], ebx
0x1800e5d66  mov     rcx, [rcx+10h]
0x1800e5d6a  call    WPP_SF_qD
0x1800e5d6f  jmp     loc_1800E62EB
0x1800e5d74  mov     rcx, [rbp+var_40]
0x1800e5d78  lea     rdx, [rbp+var_28]
0x1800e5d7c  mov     rax, [rcx]
0x1800e5d7f  mov     rax, [rax+40h]
0x1800e5d83  call    cs:__guard_dispatch_icall_fptr
0x1800e5d89  mov     ebx, eax
0x1800e5d8b  test    eax, eax
0x1800e5d8d  jns     loc_1800E5E29
0x1800e5d93  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800e5d9a  test    rcx, rcx
0x1800e5d9d  jnz     short loc_1800E5DE7
0x1800e5d9f  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800e5da6  nop     dword ptr [rax+rax+00h]
0x1800e5dab  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800e5db2  mov     rcx, rax
0x1800e5db5  test    rax, rax
0x1800e5db8  jz      short loc_1800E5DD9
0x1800e5dba  mov     rax, [rax]
0x1800e5dbd  mov     edx, 7F0h
0x1800e5dc2  mov     rax, [rax+8]
0x1800e5dc6  call    cs:__guard_dispatch_icall_fptr
0x1800e5dcc  test    eax, eax
0x1800e5dce  jz      short loc_1800E5DD9
0x1800e5dd0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800e5dd7  jmp     short loc_1800E5DE7
0x1800e5dd9  lea     rcx, qword_1803CE250; this
0x1800e5de0  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800e5de7  cmp     [rcx+8], r15b
0x1800e5deb  jz      short loc_1800E5E12
0x1800e5ded  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800e5df2  cmp     [rax+7CCh], ebx
0x1800e5df8  jz      short loc_1800E5E12
0x1800e5dfa  mov     r9d, ebx; int
0x1800e5dfd  lea     rdx, aCpmpsourcestub_10; "CPMPSourceStub::HandleNewOrUpdatedStrea"...
0x1800e5e04  mov     r8d, 30Bh; int
0x1800e5e0a  mov     rcx, rax; this
0x1800e5e0d  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800e5e12  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800e5e19  jb      loc_1800E62EB
0x1800e5e1f  mov     edx, 37h ; '7'
0x1800e5e24  jmp     loc_1800E5D51
0x1800e5e29  mov     rcx, [rbp+var_28]
0x1800e5e2d  lea     rdx, [rbp+var_44]
0x1800e5e31  mov     rax, [rcx]
0x1800e5e34  mov     rax, [rax+108h]
0x1800e5e3b  call    cs:__guard_dispatch_icall_fptr
0x1800e5e41  mov     ebx, eax
0x1800e5e43  test    eax, eax
0x1800e5e45  jns     loc_1800E5EE1
0x1800e5e4b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800e5e52  test    rcx, rcx
0x1800e5e55  jnz     short loc_1800E5E9F
0x1800e5e57  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800e5e5e  nop     dword ptr [rax+rax+00h]
0x1800e5e63  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800e5e6a  mov     rcx, rax
0x1800e5e6d  test    rax, rax
0x1800e5e70  jz      short loc_1800E5E91
0x1800e5e72  mov     rax, [rax]
0x1800e5e75  mov     edx, 7F0h
0x1800e5e7a  mov     rax, [rax+8]
0x1800e5e7e  call    cs:__guard_dispatch_icall_fptr
0x1800e5e84  test    eax, eax
0x1800e5e86  jz      short loc_1800E5E91
0x1800e5e88  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800e5e8f  jmp     short loc_1800E5E9F
0x1800e5e91  lea     rcx, qword_1803CE250; this
0x1800e5e98  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800e5e9f  cmp     [rcx+8], r15b
0x1800e5ea3  jz      short loc_1800E5ECA
0x1800e5ea5  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800e5eaa  cmp     [rax+7CCh], ebx
0x1800e5eb0  jz      short loc_1800E5ECA
0x1800e5eb2  mov     r9d, ebx; int
0x1800e5eb5  lea     rdx, aCpmpsourcestub_10; "CPMPSourceStub::HandleNewOrUpdatedStrea"...
0x1800e5ebc  mov     r8d, 30Dh; int
0x1800e5ec2  mov     rcx, rax; this
0x1800e5ec5  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800e5eca  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800e5ed1  jb      loc_1800E62EB
0x1800e5ed7  mov     edx, 38h ; '8'
0x1800e5edc  jmp     loc_1800E5D51
0x1800e5ee1  mov     edx, [rbp+var_44]; unsigned int
0x1800e5ee4  lea     rcx, [r14+40h]; this
0x1800e5ee8  call    ?FindById@CPMPStreamStubList@@QEAAPEAVCPMPStreamStub@@K@Z; CPMPStreamStubList::FindById(ulong)
0x1800e5eed  mov     rdx, rax
0x1800e5ef0  lea     rcx, [rbp+var_38]
0x1800e5ef4  call    ??4?$ComSmartPtr@VCPMPStreamStub@@@@QEAAPEAVCPMPStreamStub@@PEAV1@@Z; ComSmartPtr<CPMPStreamStub>::operator=(CPMPStreamStub *)
0x1800e5ef9  mov     rsi, [rbp+var_38]
0x1800e5efd  lea     rdi, WPP_bc4c13183d93354ba90b2bb655eeb28d_Traceguids
0x1800e5f04  test    rsi, rsi
0x1800e5f07  jz      short loc_1800E5F7F
0x1800e5f09  cmp     [rsi+24h], r15d
0x1800e5f0d  jz      short loc_1800E5F3C
0x1800e5f0f  cmp     cs:byte_1803CECE9, 10h
0x1800e5f16  jb      short loc_1800E5F33
0x1800e5f18  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e5f1f  mov     edx, 39h ; '9'
0x1800e5f24  mov     r9, r14
0x1800e5f27  mov     r8, rdi
0x1800e5f2a  mov     rcx, [rcx+38h]
0x1800e5f2e  call    WPP_SF_q
0x1800e5f33  mov     [rsi+24h], r15d
0x1800e5f37  jmp     loc_1800E60C5
0x1800e5f3c  mov     eax, [r14+178h]
0x1800e5f43  mov     [rsi+20h], eax
0x1800e5f46  cmp     cs:byte_1803CECE9, 10h
0x1800e5f4d  jb      loc_1800E60C5
0x1800e5f53  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e5f5a  mov     edx, 3Ah ; ':'
0x1800e5f5f  mov     eax, [rbp+var_44]
0x1800e5f62  mov     r9, r14
0x1800e5f65  mov     [rsp+78h+var_50], eax
0x1800e5f69  mov     r8, rdi
0x1800e5f6c  mov     [rsp+78h+ppEvent], rsi
0x1800e5f71  mov     rcx, [rcx+38h]
0x1800e5f75  call    WPP_SF_qqD
0x1800e5f7a  jmp     loc_1800E60C5
0x1800e5f7f  mov     ecx, 60h ; '`'; Size
0x1800e5f84  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800e5f89  test    rax, rax
0x1800e5f8c  jz      short loc_1800E5FA3
0x1800e5f8e  mov     r9d, [rbp+var_44]; unsigned int
0x1800e5f92  mov     rdx, r14; struct CPMPSourceStub *
0x1800e5f95  mov     r8, [rbp+var_40]; struct IMFMediaStream *
0x1800e5f99  mov     rcx, rax; this
0x1800e5f9c  call    ??0CPMPStreamStub@@QEAA@PEAVCPMPSourceStub@@PEAUIMFMediaStream@@K@Z; CPMPStreamStub::CPMPStreamStub(CPMPSourceStub *,IMFMediaStream *,ulong)
0x1800e5fa1  jmp     short loc_1800E5FA6
0x1800e5fa3  mov     rax, r15
0x1800e5fa6  mov     rdx, rax
0x1800e5fa9  lea     rcx, [rbp+var_38]
0x1800e5fad  call    ??4?$ComSmartPtr@VCPMPStreamStub@@@@QEAAPEAVCPMPStreamStub@@PEAV1@@Z; ComSmartPtr<CPMPStreamStub>::operator=(CPMPStreamStub *)
0x1800e5fb2  mov     rsi, [rbp+var_38]
0x1800e5fb6  test    rsi, rsi
0x1800e5fb9  jnz     loc_1800E605D
0x1800e5fbf  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800e5fc6  mov     ebx, 8007000Eh
0x1800e5fcb  test    rcx, rcx
0x1800e5fce  jnz     short loc_1800E6018
0x1800e5fd0  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800e5fd7  nop     dword ptr [rax+rax+00h]
0x1800e5fdc  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800e5fe3  mov     rcx, rax
0x1800e5fe6  test    rax, rax
0x1800e5fe9  jz      short loc_1800E600A
0x1800e5feb  mov     rax, [rax]
0x1800e5fee  mov     edx, 7F0h
0x1800e5ff3  mov     rax, [rax+8]
0x1800e5ff7  call    cs:__guard_dispatch_icall_fptr
0x1800e5ffd  test    eax, eax
0x1800e5fff  jz      short loc_1800E600A
0x1800e6001  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800e6008  jmp     short loc_1800E6018
0x1800e600a  lea     rcx, qword_1803CE250; this
0x1800e6011  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800e6018  cmp     [rcx+8], r15b
0x1800e601c  jz      short loc_1800E6043
0x1800e601e  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800e6023  cmp     [rax+7CCh], ebx
0x1800e6029  jz      short loc_1800E6043
0x1800e602b  mov     r9d, ebx; int
0x1800e602e  lea     rdx, aCpmpsourcestub_10; "CPMPSourceStub::HandleNewOrUpdatedStrea"...
0x1800e6035  mov     r8d, 328h; int
0x1800e603b  mov     rcx, rax; this
0x1800e603e  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800e6043  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800e604a  jb      loc_1800E62EB
0x1800e6050  mov     edx, 3Bh ; ';'
0x1800e6055  mov     r8, rdi
0x1800e6058  jmp     loc_1800E5D58
0x1800e605d  cmp     cs:byte_1803CECE9, 10h
0x1800e6064  jb      short loc_1800E608D
0x1800e6066  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e606d  mov     edx, 3Ch ; '<'
0x1800e6072  mov     eax, [rbp+var_44]
0x1800e6075  mov     r9, r14
0x1800e6078  mov     [rsp+78h+var_50], eax
0x1800e607c  mov     r8, rdi
0x1800e607f  mov     [rsp+78h+ppEvent], rsi
0x1800e6084  mov     rcx, [rcx+38h]
0x1800e6088  call    WPP_SF_qqD
0x1800e608d  lea     rdx, [rsi+10h]
0x1800e6091  lea     rcx, [r14+48h]
0x1800e6095  mov     rax, [rcx+8]
0x1800e6099  mov     [rdx], rcx
0x1800e609c  mov     [rdx+8], rax
0x1800e60a0  mov     [rax], rdx
0x1800e60a3  inc     dword ptr [r14+40h]
0x1800e60a7  mov     [rcx+8], rdx
0x1800e60ab  mov     rcx, rsi
0x1800e60ae  mov     rax, [rsi]
0x1800e60b1  mov     rax, [rax+8]
0x1800e60b5  call    cs:__guard_dispatch_icall_fptr
0x1800e60bb  mov     eax, [r14+178h]
0x1800e60c2  mov     [rsi+20h], eax
0x1800e60c5  mov     rcx, [rbp+var_40]
0x1800e60c9  lea     r8, [rbp+var_30]
0x1800e60cd  lea     rdx, IID_IMFRemoteProxy
0x1800e60d4  mov     rax, [rcx]
0x1800e60d7  mov     rax, [rax]
0x1800e60da  call    cs:__guard_dispatch_icall_fptr
0x1800e60e0  test    eax, eax
0x1800e60e2  js      loc_1800E635F
0x1800e60e8  cmp     cs:byte_1803CECE9, 10h
0x1800e60ef  jb      short loc_1800E6118
0x1800e60f1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e60f8  mov     edx, 3Dh ; '='
0x1800e60fd  mov     eax, [rbp+var_44]
0x1800e6100  mov     r9, r14
0x1800e6103  mov     [rsp+78h+var_50], eax
0x1800e6107  mov     r8, rdi
0x1800e610a  mov     [rsp+78h+ppEvent], rsi
0x1800e610f  mov     rcx, [rcx+38h]
0x1800e6113  call    WPP_SF_qqD
0x1800e6118  mov     rcx, [rbp+var_30]
0x1800e611c  lea     r8, [rbp+var_38]
0x1800e6120  xor     eax, eax
0x1800e6122  mov     [rbp+var_38], r15
0x1800e6126  mov     [rbp+var_10], rax
0x1800e612a  lea     rdx, IID_IMFMediaStream
0x1800e6131  xorps   xmm0, xmm0
0x1800e6134  movups  xmmword ptr [rbp+pvValue], xmm0
0x1800e6138  mov     rax, [rcx]
0x1800e613b  mov     rax, [rax+18h]
0x1800e613f  call    cs:__guard_dispatch_icall_fptr
0x1800e6145  mov     ebx, eax
0x1800e6147  test    eax, eax
0x1800e6149  jns     loc_1800E6204
  ... truncated ...
```
