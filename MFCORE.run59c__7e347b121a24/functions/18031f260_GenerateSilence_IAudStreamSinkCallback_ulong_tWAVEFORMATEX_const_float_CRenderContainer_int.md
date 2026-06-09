# GenerateSilence(IAudStreamSinkCallback *,ulong,tWAVEFORMATEX const *,float,CRenderContainer * *,int)

- ea: `0x18031f260`
- end: `0x18031fbc7`
- name: `?GenerateSilence@@YAJPEAUIAudStreamSinkCallback@@KPEBUtWAVEFORMATEX@@MPEAPEAVCRenderContainer@@H@Z`
- size: `2407`
- prototype: `__int64 __usercall@<rax>(struct IAudStreamSinkCallback *@<rcx>, unsigned int@<edx>, const struct tWAVEFORMATEX *@<r8>, float@<xmm3>, struct CRenderContainer **, int)`
- caller_count: `2`
- callee_count: `14`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x180175290`
- `0x1801c4fd0`

## callees

- `0x18002fee0`
- `0x18003ecb0`
- `0x1800402c0`
- `0x180050d6c`
- `0x180063f00`
- `0x18007dff8`
- `0x18007f670`
- `0x1800c9ea8`
- `0x1800ec0e0`
- `0x1800f2254`
- `0x18025839c`
- `0x1802583e8`
- `0x18031f260`
- `0x180344d40`

## import_xrefs

- `MFPlat!MFCreateMemoryBuffer` at `0x18031f425`
- `MFPlat!MFCreateMemoryBuffer` at `0x18031f425`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18031f2e3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18031f399`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18031f447`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18031f51c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18031f5d4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18031f67e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18031f72d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18031f7dc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18031f8f4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18031f99d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18031fa4e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18031fb0d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18031f2e3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18031f399`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18031f447`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18031f51c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18031f5d4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18031f67e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18031f72d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18031f7dc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18031f8f4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18031f99d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18031fa4e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18031fb0d`
- `MFPlat!MFCreateSample` at `0x18031f377`
- `MFPlat!MFCreateSample` at `0x18031f377`

## pseudocode

```c
__int64 __fastcall GenerateSilence(
        struct IAudStreamSinkCallback *a1,
        unsigned int a2,
        const struct tWAVEFORMATEX *a3,
        float a4,
        struct CRenderContainer **a5,
        int a6)
{
  unsigned __int64 v6; // rdi
  unsigned __int8 *v9; // rsi
  __int64 v10; // rdx
  HRESULT Silence; // ebx
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
  __int64 v27; // rdx
  __int64 v28; // r8
  __int64 *v29; // rcx
  CallStackTracing *v30; // rax
  struct CallStackContext *v31; // rax
  __int64 v32; // rdx
  __int64 v33; // r8
  __int64 *v34; // rcx
  CallStackTracing *v35; // rax
  struct CallStackContext *v36; // rax
  __int64 v37; // rdx
  __int64 v38; // r8
  __int64 *v39; // rcx
  CallStackTracing *v40; // rax
  struct CallStackContext *v41; // rax
  __int64 v42; // rdx
  __int64 v43; // rdx
  __int64 v44; // r8
  __int64 *v45; // rcx
  CallStackTracing *v46; // rax
  struct CallStackContext *v47; // rax
  __int64 v48; // rdx
  __int64 v49; // r8
  __int64 *v50; // rcx
  CallStackTracing *v51; // rax
  struct CallStackContext *v52; // rax
  unsigned __int8 *v54; // rax
  __int64 v55; // rdx
  __int64 v56; // r8
  __int64 *v57; // rcx
  CallStackTracing *v58; // rax
  struct CallStackContext *v59; // rax
  __int64 v60; // rdx
  __int64 v61; // r8
  __int64 *v62; // rcx
  CallStackTracing *v63; // rax
  struct CallStackContext *v64; // rax
  __int64 v65; // rdx
  __int64 v66; // r8
  __int64 *v67; // rcx
  CallStackTracing *v68; // rax
  struct CallStackContext *v69; // rax
  __int64 v70; // rdx
  __int64 v71; // r8
  __int64 *v72; // rcx
  CallStackTracing *v73; // rax
  struct CallStackContext *v74; // rax
  int v75; // [rsp+30h] [rbp-48h] BYREF
  CPooledObject *v76; // [rsp+38h] [rbp-40h] BYREF
  IMFMediaBuffer *ppBuffer; // [rsp+40h] [rbp-38h] BYREF
  IMFSample *ppIMFSample; // [rsp+48h] [rbp-30h] BYREF
  unsigned __int8 *v79; // [rsp+50h] [rbp-28h] BYREF
  char v80; // [rsp+C0h] [rbp+48h] BYREF

  v6 = a2;
  v76 = 0;
  v79 = 0;
  v75 = 0;
  ppIMFSample = 0;
  ppBuffer = 0;
  v9 = 0;
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v80, "GenerateSilence", 120);
  Silence = (*(__int64 (__fastcall **)(struct IAudStreamSinkCallback *, CPooledObject **))(*(_QWORD *)a1 + 152LL))(
              a1,
              &v76);
  if ( Silence < 0 )
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
      if ( *((_DWORD *)ThreadRelativeContext + 499) != Silence )
        CallStackContext::TraceFailure(ThreadRelativeContext, "GenerateSilence", 120, Silence);
    }
    if ( !g_wppLevels )
      goto LABEL_139;
    v16 = 15;
    goto LABEL_138;
  }
  if ( !a6 )
  {
    Silence = MFCreateSample(&ppIMFSample);
    if ( Silence < 0 )
    {
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
        if ( *((_DWORD *)v21 + 499) != Silence )
          CallStackContext::TraceFailure(v21, "GenerateSilence", 125, Silence);
      }
      if ( !g_wppLevels )
        goto LABEL_139;
      v16 = 16;
      goto LABEL_138;
    }
    Silence = MFCreateMemoryBuffer(v6, &ppBuffer);
    if ( Silence < 0 )
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
        if ( *((_DWORD *)v26 + 499) != Silence )
          CallStackContext::TraceFailure(v26, "GenerateSilence", 126, Silence);
      }
      if ( !g_wppLevels )
        goto LABEL_139;
      v16 = 17;
      goto LABEL_138;
    }
    ((void (__fastcall *)(IMFSample *, IMFMediaBuffer *))ppIMFSample->lpVtbl->AddBuffer)(ppIMFSample, ppBuffer);
    Silence = CRenderContainer::Initialize(v76, a1, ppIMFSample, 1, a4, 0);
    if ( Silence < 0 )
    {
      v29 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v30 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v27, v28);
        CallStackTracing::s_wpInstance = v30;
        if ( v30 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v30 + 8LL))(v30, 2032) )
        {
          v29 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v29 = &qword_1803CE250;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
        }
      }
      if ( *((_BYTE *)v29 + 8) )
      {
        v31 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v29);
        if ( *((_DWORD *)v31 + 499) != Silence )
          CallStackContext::TraceFailure(v31, "GenerateSilence", 131, Silence);
      }
      if ( !g_wppLevels )
        goto LABEL_139;
      v16 = 18;
      goto LABEL_138;
    }
    Silence = ((__int64 (__fastcall *)(IMFMediaBuffer *, unsigned __int8 **, int *, _QWORD))ppBuffer->lpVtbl->Lock)(
                ppBuffer,
                &v79,
                &v75,
                0);
    if ( Silence < 0 )
    {
      v34 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v35 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v32, v33);
        CallStackTracing::s_wpInstance = v35;
        if ( v35 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v35 + 8LL))(v35, 2032) )
        {
          v34 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v34 = &qword_1803CE250;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
        }
      }
      if ( *((_BYTE *)v34 + 8) )
      {
        v36 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v34);
        if ( *((_DWORD *)v36 + 499) != Silence )
          CallStackContext::TraceFailure(v36, "GenerateSilence", 133, Silence);
      }
      if ( !g_wppLevels )
        goto LABEL_139;
      v16 = 19;
      goto LABEL_138;
    }
    Silence = GenerateSilence(v79, v6, a3);
    if ( Silence >= 0 )
    {
      Silence = ((__int64 (__fastcall *)(IMFMediaBuffer *, _QWORD))ppBuffer->lpVtbl->SetCurrentLength)(
                  ppBuffer,
                  (unsigned int)v6);
      if ( Silence >= 0 )
      {
        Silence = CRenderContainer::AddData(v76, v79, v6, 0);
        if ( Silence < 0 )
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
            if ( *((_DWORD *)v52 + 499) != Silence )
              CallStackContext::TraceFailure(v52, "GenerateSilence", 143, Silence);
          }
          if ( g_wppLevels )
          {
            v42 = 22;
            goto LABEL_90;
          }
        }
      }
      else
      {
        v45 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v46 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v43, v44);
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
          if ( *((_DWORD *)v47 + 499) != Silence )
            CallStackContext::TraceFailure(v47, "GenerateSilence", 139, Silence);
        }
        if ( g_wppLevels )
        {
          v42 = 21;
          goto LABEL_90;
        }
      }
    }
    else
    {
      v39 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v40 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v37, v38);
        CallStackTracing::s_wpInstance = v40;
        if ( v40 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v40 + 8LL))(v40, 2032) )
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
        if ( *((_DWORD *)v41 + 499) != Silence )
          CallStackContext::TraceFailure(v41, "GenerateSilence", 137, Silence);
      }
      if ( g_wppLevels )
      {
        v42 = 20;
LABEL_90:
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v42,
          &WPP_5d18bf9a50ae3015af6399046348c38b_Traceguids,
          0,
          Silence);
      }
    }
    ((void (__fastcall *)(IMFMediaBuffer *))ppBuffer->lpVtbl->Unlock)(ppBuffer);
    if ( Silence < 0 )
      goto LABEL_139;
LABEL_92:
    *a5 = v76;
    goto LABEL_93;
  }
  v54 = (unsigned __int8 *)operator new[](v6);
  v9 = v54;
  if ( v54 )
  {
    Silence = GenerateSilence(v54, v6, a3);
    if ( Silence >= 0 )
    {
      Silence = CRenderContainer::AddData(v76, v9, v6, 1);
      if ( Silence >= 0 )
      {
        Silence = CRenderContainer::Initialize(v76, a1, 0, 1, a4, 0);
        if ( Silence >= 0 )
          goto LABEL_92;
        v72 = (__int64 *)CallStackTracing::s_wpInstance;
        v9 = 0;
        if ( !CallStackTracing::s_wpInstance )
        {
          v73 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v70, v71);
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
          if ( *((_DWORD *)v74 + 499) != Silence )
            CallStackContext::TraceFailure(v74, "GenerateSilence", 157, Silence);
        }
        if ( !g_wppLevels )
          goto LABEL_139;
        v16 = 26;
      }
      else
      {
        v67 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v68 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v65, v66);
          CallStackTracing::s_wpInstance = v68;
          if ( v68 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v68 + 8LL))(v68, 2032) )
          {
            v67 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v67 = &qword_1803CE250;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
          }
        }
        if ( *((_BYTE *)v67 + 8) )
        {
          v69 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v67);
          if ( *((_DWORD *)v69 + 499) != Silence )
            CallStackContext::TraceFailure(v69, "GenerateSilence", 152, Silence);
        }
        if ( !g_wppLevels )
          goto LABEL_139;
        v16 = 25;
      }
    }
    else
    {
      v62 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v63 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v60, v61);
        CallStackTracing::s_wpInstance = v63;
        if ( v63 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v63 + 8LL))(v63, 2032) )
        {
          v62 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v62 = &qword_1803CE250;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
        }
      }
      if ( *((_BYTE *)v62 + 8) )
      {
        v64 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v62);
        if ( *((_DWORD *)v64 + 499) != Silence )
          CallStackContext::TraceFailure(v64, "GenerateSilence", 150, Silence);
      }
      if ( !g_wppLevels )
        goto LABEL_139;
      v16 = 24;
    }
  }
  else
  {
    v57 = (__int64 *)CallStackTracing::s_wpInstance;
    Silence = -2147024882;
    if ( !CallStackTracing::s_wpInstance )
    {
      v58 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v55, v56);
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
      if ( *((_DWORD *)v59 + 499) != -2147024882 )
        CallStackContext::TraceFailure(v59, "GenerateSilence", 148, -2147024882);
    }
    if ( !g_wppLevels )
      goto LABEL_139;
    v16 = 23;
  }
LABEL_138:
  WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v16, &WPP_5d18bf9a50ae3015af6399046348c38b_Traceguids, 0, Silence);
LABEL_139:
  operator delete(v9);
  if ( v76 )
    CPooledObject::_FinalRelease(v76);
LABEL_93:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v80);
  ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&ppBuffer);
  ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&ppIMFSample);
  return (unsigned int)Silence;
}

```

## disassembly

```asm
0x18031f260  push    rbp
0x18031f262  push    rbx
0x18031f263  push    rsi
0x18031f264  push    rdi
0x18031f265  push    r12
0x18031f267  push    r13
0x18031f269  push    r14
0x18031f26b  push    r15
0x18031f26d  mov     rbp, rsp
0x18031f270  sub     rsp, 78h
0x18031f274  xor     r12d, r12d
0x18031f277  mov     edi, edx
0x18031f279  mov     r14, r8
0x18031f27c  movaps  [rsp+78h+var_18], xmm6
0x18031f281  mov     r15, rcx
0x18031f284  mov     [rbp+var_40], r12
0x18031f288  lea     r13, aGeneratesilenc_0; "GenerateSilence"
0x18031f28f  mov     [rbp+var_28], r12
0x18031f293  lea     r8d, [r12+78h]; int
0x18031f298  mov     [rbp+var_48], r12d
0x18031f29c  mov     rdx, r13; char *
0x18031f29f  mov     [rbp+ppIMFSample], r12
0x18031f2a3  lea     rcx, [rbp+arg_0]; this
0x18031f2a7  mov     [rbp+ppBuffer], r12
0x18031f2ab  movaps  xmm6, xmm3
0x18031f2ae  mov     esi, r12d
0x18031f2b1  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18031f2b6  mov     rax, [r15]
0x18031f2b9  lea     rdx, [rbp+var_40]
0x18031f2bd  mov     rcx, r15
0x18031f2c0  mov     rax, [rax+98h]
0x18031f2c7  call    cs:__guard_dispatch_icall_fptr
0x18031f2cd  mov     ebx, eax
0x18031f2cf  test    eax, eax
0x18031f2d1  jns     loc_18031F369
0x18031f2d7  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18031f2de  test    rcx, rcx
0x18031f2e1  jnz     short loc_18031F32B
0x18031f2e3  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18031f2ea  nop     dword ptr [rax+rax+00h]
0x18031f2ef  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18031f2f6  mov     rcx, rax
0x18031f2f9  test    rax, rax
0x18031f2fc  jz      short loc_18031F31D
0x18031f2fe  mov     rax, [rax]
0x18031f301  mov     edx, 7F0h
0x18031f306  mov     rax, [rax+8]
0x18031f30a  call    cs:__guard_dispatch_icall_fptr
0x18031f310  test    eax, eax
0x18031f312  jz      short loc_18031F31D
0x18031f314  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18031f31b  jmp     short loc_18031F32B
0x18031f31d  lea     rcx, qword_1803CE250; this
0x18031f324  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18031f32b  cmp     [rcx+8], r12b
0x18031f32f  jz      short loc_18031F352
0x18031f331  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18031f336  cmp     [rax+7CCh], ebx
0x18031f33c  jz      short loc_18031F352
0x18031f33e  mov     r9d, ebx; int
0x18031f341  mov     r8d, 78h ; 'x'; int
0x18031f347  mov     rdx, r13; char *
0x18031f34a  mov     rcx, rax; this
0x18031f34d  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18031f352  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18031f359  jb      loc_18031FBA8
0x18031f35f  mov     edx, 0Fh
0x18031f364  jmp     loc_18031FB8A
0x18031f369  cmp     [rbp+arg_28], r12d
0x18031f36d  jnz     loc_18031F8CF
0x18031f373  lea     rcx, [rbp+ppIMFSample]; ppIMFSample
0x18031f377  call    cs:__imp_MFCreateSample
0x18031f37e  nop     dword ptr [rax+rax+00h]
0x18031f383  mov     ebx, eax
0x18031f385  test    eax, eax
0x18031f387  jns     loc_18031F41F
0x18031f38d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18031f394  test    rcx, rcx
0x18031f397  jnz     short loc_18031F3E1
0x18031f399  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18031f3a0  nop     dword ptr [rax+rax+00h]
0x18031f3a5  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18031f3ac  mov     rcx, rax
0x18031f3af  test    rax, rax
0x18031f3b2  jz      short loc_18031F3D3
0x18031f3b4  mov     rax, [rax]
0x18031f3b7  mov     edx, 7F0h
0x18031f3bc  mov     rax, [rax+8]
0x18031f3c0  call    cs:__guard_dispatch_icall_fptr
0x18031f3c6  test    eax, eax
0x18031f3c8  jz      short loc_18031F3D3
0x18031f3ca  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18031f3d1  jmp     short loc_18031F3E1
0x18031f3d3  lea     rcx, qword_1803CE250; this
0x18031f3da  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18031f3e1  cmp     [rcx+8], r12b
0x18031f3e5  jz      short loc_18031F408
0x18031f3e7  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18031f3ec  cmp     [rax+7CCh], ebx
0x18031f3f2  jz      short loc_18031F408
0x18031f3f4  mov     r9d, ebx; int
0x18031f3f7  mov     r8d, 7Dh ; '}'; int
0x18031f3fd  mov     rdx, r13; char *
0x18031f400  mov     rcx, rax; this
0x18031f403  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18031f408  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18031f40f  jb      loc_18031FBA8
0x18031f415  mov     edx, 10h
0x18031f41a  jmp     loc_18031FB8A
0x18031f41f  lea     rdx, [rbp+ppBuffer]; ppBuffer
0x18031f423  mov     ecx, edi; cbMaxLength
0x18031f425  call    cs:__imp_MFCreateMemoryBuffer
0x18031f42c  nop     dword ptr [rax+rax+00h]
0x18031f431  mov     ebx, eax
0x18031f433  test    eax, eax
0x18031f435  jns     loc_18031F4CD
0x18031f43b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18031f442  test    rcx, rcx
0x18031f445  jnz     short loc_18031F48F
0x18031f447  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18031f44e  nop     dword ptr [rax+rax+00h]
0x18031f453  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18031f45a  mov     rcx, rax
0x18031f45d  test    rax, rax
0x18031f460  jz      short loc_18031F481
0x18031f462  mov     rax, [rax]
0x18031f465  mov     edx, 7F0h
0x18031f46a  mov     rax, [rax+8]
0x18031f46e  call    cs:__guard_dispatch_icall_fptr
0x18031f474  test    eax, eax
0x18031f476  jz      short loc_18031F481
0x18031f478  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18031f47f  jmp     short loc_18031F48F
0x18031f481  lea     rcx, qword_1803CE250; this
0x18031f488  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18031f48f  cmp     [rcx+8], r12b
0x18031f493  jz      short loc_18031F4B6
0x18031f495  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18031f49a  cmp     [rax+7CCh], ebx
0x18031f4a0  jz      short loc_18031F4B6
0x18031f4a2  mov     r9d, ebx; int
0x18031f4a5  mov     r8d, 7Eh ; '~'; int
0x18031f4ab  mov     rdx, r13; char *
0x18031f4ae  mov     rcx, rax; this
0x18031f4b1  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18031f4b6  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18031f4bd  jb      loc_18031FBA8
0x18031f4c3  mov     edx, 11h
0x18031f4c8  jmp     loc_18031FB8A
0x18031f4cd  mov     rcx, [rbp+ppIMFSample]
0x18031f4d1  mov     rdx, [rbp+ppBuffer]
0x18031f4d5  mov     rax, [rcx]
0x18031f4d8  mov     rax, [rax+150h]
0x18031f4df  call    cs:__guard_dispatch_icall_fptr
0x18031f4e5  mov     r8, [rbp+ppIMFSample]; struct IMFSample *
0x18031f4e9  mov     r9d, 1; int
0x18031f4ef  mov     rcx, [rbp+var_40]; this
0x18031f4f3  mov     rdx, r15; struct IAudStreamSinkCallback *
0x18031f4f6  mov     [rsp+78h+var_50], r12d; int
0x18031f4fb  movss   [rsp+78h+var_58], xmm6; float
0x18031f501  call    ?Initialize@CRenderContainer@@QEAAJPEAUIAudStreamSinkCallback@@PEAUIMFSample@@HMH@Z; CRenderContainer::Initialize(IAudStreamSinkCallback *,IMFSample *,int,float,int)
0x18031f506  mov     ebx, eax
0x18031f508  test    eax, eax
0x18031f50a  jns     loc_18031F5A2
0x18031f510  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18031f517  test    rcx, rcx
0x18031f51a  jnz     short loc_18031F564
0x18031f51c  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18031f523  nop     dword ptr [rax+rax+00h]
0x18031f528  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18031f52f  mov     rcx, rax
0x18031f532  test    rax, rax
0x18031f535  jz      short loc_18031F556
0x18031f537  mov     rax, [rax]
0x18031f53a  mov     edx, 7F0h
0x18031f53f  mov     rax, [rax+8]
0x18031f543  call    cs:__guard_dispatch_icall_fptr
0x18031f549  test    eax, eax
0x18031f54b  jz      short loc_18031F556
0x18031f54d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18031f554  jmp     short loc_18031F564
0x18031f556  lea     rcx, qword_1803CE250; this
0x18031f55d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18031f564  cmp     [rcx+8], r12b
0x18031f568  jz      short loc_18031F58B
0x18031f56a  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18031f56f  cmp     [rax+7CCh], ebx
0x18031f575  jz      short loc_18031F58B
0x18031f577  mov     r9d, ebx; int
0x18031f57a  mov     r8d, 83h; int
0x18031f580  mov     rdx, r13; char *
0x18031f583  mov     rcx, rax; this
0x18031f586  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18031f58b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18031f592  jb      loc_18031FBA8
0x18031f598  mov     edx, 12h
0x18031f59d  jmp     loc_18031FB8A
0x18031f5a2  mov     rcx, [rbp+ppBuffer]
0x18031f5a6  lea     r8, [rbp+var_48]
0x18031f5aa  xor     r9d, r9d
0x18031f5ad  lea     rdx, [rbp+var_28]
0x18031f5b1  mov     rax, [rcx]
0x18031f5b4  mov     rax, [rax+18h]
0x18031f5b8  call    cs:__guard_dispatch_icall_fptr
0x18031f5be  mov     ebx, eax
0x18031f5c0  test    eax, eax
0x18031f5c2  jns     loc_18031F65A
0x18031f5c8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18031f5cf  test    rcx, rcx
0x18031f5d2  jnz     short loc_18031F61C
0x18031f5d4  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18031f5db  nop     dword ptr [rax+rax+00h]
0x18031f5e0  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18031f5e7  mov     rcx, rax
0x18031f5ea  test    rax, rax
0x18031f5ed  jz      short loc_18031F60E
0x18031f5ef  mov     rax, [rax]
0x18031f5f2  mov     edx, 7F0h
0x18031f5f7  mov     rax, [rax+8]
0x18031f5fb  call    cs:__guard_dispatch_icall_fptr
0x18031f601  test    eax, eax
0x18031f603  jz      short loc_18031F60E
0x18031f605  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18031f60c  jmp     short loc_18031F61C
0x18031f60e  lea     rcx, qword_1803CE250; this
0x18031f615  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18031f61c  cmp     [rcx+8], r12b
0x18031f620  jz      short loc_18031F643
0x18031f622  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18031f627  cmp     [rax+7CCh], ebx
0x18031f62d  jz      short loc_18031F643
0x18031f62f  mov     r9d, ebx; int
0x18031f632  mov     r8d, 85h; int
0x18031f638  mov     rdx, r13; char *
0x18031f63b  mov     rcx, rax; this
0x18031f63e  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18031f643  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18031f64a  jb      loc_18031FBA8
0x18031f650  mov     edx, 13h
0x18031f655  jmp     loc_18031FB8A
0x18031f65a  mov     rcx, [rbp+var_28]; unsigned __int8 *
0x18031f65e  mov     r8, r14; struct tWAVEFORMATEX *
0x18031f661  mov     edx, edi; unsigned int
0x18031f663  call    ?GenerateSilence@@YAJPEAEKPEBUtWAVEFORMATEX@@@Z; GenerateSilence(uchar *,ulong,tWAVEFORMATEX const *)
0x18031f668  mov     ebx, eax
0x18031f66a  test    eax, eax
0x18031f66c  jns     loc_18031F704
0x18031f672  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18031f679  test    rcx, rcx
0x18031f67c  jnz     short loc_18031F6C6
0x18031f67e  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18031f685  nop     dword ptr [rax+rax+00h]
0x18031f68a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18031f691  mov     rcx, rax
0x18031f694  test    rax, rax
0x18031f697  jz      short loc_18031F6B8
0x18031f699  mov     rax, [rax]
0x18031f69c  mov     edx, 7F0h
0x18031f6a1  mov     rax, [rax+8]
0x18031f6a5  call    cs:__guard_dispatch_icall_fptr
0x18031f6ab  test    eax, eax
0x18031f6ad  jz      short loc_18031F6B8
0x18031f6af  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18031f6b6  jmp     short loc_18031F6C6
0x18031f6b8  lea     rcx, qword_1803CE250; this
0x18031f6bf  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18031f6c6  cmp     [rcx+8], r12b
0x18031f6ca  jz      short loc_18031F6ED
0x18031f6cc  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18031f6d1  cmp     [rax+7CCh], ebx
0x18031f6d7  jz      short loc_18031F6ED
0x18031f6d9  mov     r9d, ebx; int
0x18031f6dc  mov     r8d, 89h; int
0x18031f6e2  mov     rdx, r13; char *
0x18031f6e5  mov     rcx, rax; this
0x18031f6e8  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18031f6ed  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18031f6f4  jb      loc_18031F877
0x18031f6fa  mov     edx, 14h
0x18031f6ff  jmp     loc_18031F859
0x18031f704  mov     rcx, [rbp+ppBuffer]
0x18031f708  mov     edx, edi
0x18031f70a  mov     rax, [rcx]
0x18031f70d  mov     rax, [rax+30h]
0x18031f711  call    cs:__guard_dispatch_icall_fptr
0x18031f717  mov     ebx, eax
0x18031f719  test    eax, eax
0x18031f71b  jns     loc_18031F7B3
0x18031f721  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18031f728  test    rcx, rcx
0x18031f72b  jnz     short loc_18031F775
0x18031f72d  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18031f734  nop     dword ptr [rax+rax+00h]
0x18031f739  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18031f740  mov     rcx, rax
0x18031f743  test    rax, rax
0x18031f746  jz      short loc_18031F767
0x18031f748  mov     rax, [rax]
0x18031f74b  mov     edx, 7F0h
0x18031f750  mov     rax, [rax+8]
  ... truncated ...
```
