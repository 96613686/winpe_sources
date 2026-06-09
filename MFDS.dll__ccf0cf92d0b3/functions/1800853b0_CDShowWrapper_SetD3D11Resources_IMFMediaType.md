# CDShowWrapper::SetD3D11Resources(IMFMediaType *)

- ea: `0x1800853b0`
- end: `0x180085dc2`
- name: `?SetD3D11Resources@CDShowWrapper@@QEAAJPEAUIMFMediaType@@@Z`
- size: `2578`
- prototype: `__int64 __fastcall(CDShowWrapper *__hidden this, struct IMFMediaType *)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x18006f980`

## callees

- `0x180002820`
- `0x18000b8c0`
- `0x1800140b0`
- `0x1800227e0`
- `0x180032a50`
- `0x180051ce4`
- `0x180074160`
- `0x1800853b0`
- `0x180089ab0`
- `0x1800c9010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180085491`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180085549`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18008561a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800856d0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180085780`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180085838`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800858f3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800859ae`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180085a6b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180085b20`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180085bd8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180085c87`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180085491`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180085549`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18008561a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800856d0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180085780`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180085838`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800858f3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800859ae`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180085a6b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180085b20`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180085bd8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180085c87`
- `MFPlat!MFCreateVideoSampleAllocatorEx` at `0x1800855f8`
- `MFPlat!MFCreateVideoSampleAllocatorEx` at `0x1800855f8`
- `MFPlat!MFCreateAttributes` at `0x18008575e`
- `MFPlat!MFCreateAttributes` at `0x18008575e`

## pseudocode

```c
__int64 __fastcall CDShowWrapper::SetD3D11Resources(CDShowWrapper *this, struct IMFMediaType *a2)
{
  CallStackTracing *v4; // rcx
  struct CallStackContext *ThreadRelativeContext; // rdi
  int v6; // ebx
  __int128 *v7; // rax
  __int128 v8; // xmm0
  HRESULT v9; // ebx
  CallStackTracing *v10; // rax
  struct CallStackContext *v11; // rax
  __int64 v12; // rdx
  CallStackTracing *v13; // rax
  struct CallStackContext *v14; // rax
  __int64 v15; // rcx
  CallStackTracing *v16; // rcx
  CallStackTracing *v17; // rax
  struct CallStackContext *v18; // rax
  __int64 v19; // rdx
  CallStackTracing *v20; // rcx
  CallStackTracing *v21; // rax
  struct CallStackContext *v22; // rax
  CallStackTracing *v23; // rcx
  CallStackTracing *v24; // rax
  struct CallStackContext *v25; // rax
  CallStackTracing *v26; // rcx
  CallStackTracing *v27; // rax
  struct CallStackContext *v28; // rax
  CallStackTracing *v29; // rcx
  CallStackTracing *v30; // rax
  struct CallStackContext *v31; // rax
  CallStackTracing *v32; // rcx
  CallStackTracing *v33; // rax
  struct CallStackContext *v34; // rax
  CallStackTracing *v35; // rcx
  CallStackTracing *v36; // rax
  struct CallStackContext *v37; // rax
  CallStackTracing *v38; // rcx
  CallStackTracing *v39; // rax
  struct CallStackContext *v40; // rax
  CDShowSource *v41; // rcx
  CallStackTracing *v42; // rcx
  CallStackTracing *v43; // rax
  struct CallStackContext *v44; // rax
  CallStackTracing *v45; // rcx
  CallStackTracing *v46; // rax
  struct CallStackContext *v47; // rax
  __int64 v48; // rcx
  __int64 v49; // rcx
  _BYTE v51[8]; // [rsp+30h] [rbp-50h] BYREF
  void *ppSampleAllocator; // [rsp+38h] [rbp-48h] BYREF
  IMFAttributes *ppMFAttributes; // [rsp+40h] [rbp-40h] BYREF
  void *v54; // [rsp+48h] [rbp-38h] BYREF
  __int64 v55; // [rsp+50h] [rbp-30h] BYREF
  __int64 v56; // [rsp+58h] [rbp-28h] BYREF
  _BYTE v57[16]; // [rsp+60h] [rbp-20h] BYREF

  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v51, "CDShowWrapper::SetD3D11Resources", 1779);
  v4 = CallStackTracing::s_wpInstance;
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) && *((_QWORD *)this + 60) )
  {
    ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
    v6 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 60) + 296LL))(*((_QWORD *)this + 60));
    v7 = (__int128 *)(*(__int64 (__fastcall **)(_QWORD, _BYTE *))(**((_QWORD **)this + 60) + 280LL))(
                       *((_QWORD *)this + 60),
                       v57);
    v4 = CallStackTracing::s_wpInstance;
    v8 = *v7;
    *((_DWORD *)ThreadRelativeContext + 504) = v6;
    *((_OWORD *)ThreadRelativeContext + 125) = v8;
  }
  v56 = 0;
  ppSampleAllocator = 0;
  ppMFAttributes = 0;
  v55 = 0;
  v54 = 0;
  if ( !*((_QWORD *)this + 41) )
  {
    v9 = -2147024809;
    if ( !v4 )
    {
      v10 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
      CallStackTracing::s_wpInstance = v10;
      if ( v10 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v10 + 8LL))(v10, 2032) )
      {
        v4 = CallStackTracing::s_wpInstance;
      }
      else
      {
        v4 = (CallStackTracing *)&qword_1800EB130;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
      }
    }
    if ( *((_BYTE *)v4 + 8) )
    {
      v11 = CallStackTracing::GetThreadRelativeContext(v4);
      if ( *((_DWORD *)v11 + 499) != -2147024809 )
        CallStackContext::TraceFailure(v11, "CDShowWrapper::SetD3D11Resources", 1788, -2147024809);
    }
    if ( g_wppLevels )
    {
      v12 = 129;
LABEL_15:
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v12,
        &WPP_8e8a43b2e5013e25304950bf1ec57b49_Traceguids,
        this,
        -2147024809);
      goto LABEL_148;
    }
    goto LABEL_148;
  }
  if ( a2 )
  {
    v15 = *((_QWORD *)this + 43);
    if ( v15 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
      *((_QWORD *)this + 43) = 0;
    }
    v9 = MFCreateVideoSampleAllocatorEx(&GUID_545b3a48_3283_4f62_866f_a62d8f598f9f, &ppSampleAllocator);
    if ( v9 < 0 )
    {
      v16 = CallStackTracing::s_wpInstance;
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
        v18 = CallStackTracing::GetThreadRelativeContext(v16);
        if ( *((_DWORD *)v18 + 499) != v9 )
          CallStackContext::TraceFailure(v18, "CDShowWrapper::SetD3D11Resources", 1796, v9);
      }
      if ( !g_wppLevels )
        goto LABEL_148;
      v19 = 131;
      goto LABEL_41;
    }
    v9 = (*(__int64 (__fastcall **)(void *, _QWORD))(*(_QWORD *)ppSampleAllocator + 24LL))(
           ppSampleAllocator,
           *((_QWORD *)this + 41));
    if ( v9 < 0 )
    {
      v20 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v21 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
        CallStackTracing::s_wpInstance = v21;
        if ( v21 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v21 + 8LL))(v21, 2032) )
        {
          v20 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v20 = (CallStackTracing *)&qword_1800EB130;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
        }
      }
      if ( *((_BYTE *)v20 + 8) )
      {
        v22 = CallStackTracing::GetThreadRelativeContext(v20);
        if ( *((_DWORD *)v22 + 499) != v9 )
          CallStackContext::TraceFailure(v22, "CDShowWrapper::SetD3D11Resources", 1798, v9);
      }
      if ( !g_wppLevels )
        goto LABEL_148;
      v19 = 132;
      goto LABEL_41;
    }
    v9 = MFCreateAttributes(&ppMFAttributes, 1u);
    if ( v9 < 0 )
    {
      v23 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v24 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
        CallStackTracing::s_wpInstance = v24;
        if ( v24 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v24 + 8LL))(v24, 2032) )
        {
          v23 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v23 = (CallStackTracing *)&qword_1800EB130;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
        }
      }
      if ( *((_BYTE *)v23 + 8) )
      {
        v25 = CallStackTracing::GetThreadRelativeContext(v23);
        if ( *((_DWORD *)v25 + 499) != v9 )
          CallStackContext::TraceFailure(v25, "CDShowWrapper::SetD3D11Resources", 1800, v9);
      }
      if ( !g_wppLevels )
        goto LABEL_148;
      v19 = 133;
      goto LABEL_41;
    }
    v9 = ((__int64 (__fastcall *)(IMFAttributes *, __int64 *, _QWORD))ppMFAttributes->lpVtbl->SetUINT32)(
           ppMFAttributes,
           MF_SA_D3D11_USAGE,
           0);
    if ( v9 < 0 )
    {
      v26 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v27 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
        CallStackTracing::s_wpInstance = v27;
        if ( v27 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v27 + 8LL))(v27, 2032) )
        {
          v26 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v26 = (CallStackTracing *)&qword_1800EB130;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
        }
      }
      if ( *((_BYTE *)v26 + 8) )
      {
        v28 = CallStackTracing::GetThreadRelativeContext(v26);
        if ( *((_DWORD *)v28 + 499) != v9 )
          CallStackContext::TraceFailure(v28, "CDShowWrapper::SetD3D11Resources", 1801, v9);
      }
      if ( !g_wppLevels )
        goto LABEL_148;
      v19 = 134;
      goto LABEL_41;
    }
    v9 = ((__int64 (__fastcall *)(IMFAttributes *, __int64 *, __int64))ppMFAttributes->lpVtbl->SetUINT32)(
           ppMFAttributes,
           MF_SA_D3D11_BINDFLAGS,
           32);
    if ( v9 < 0 )
    {
      v29 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v30 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
        CallStackTracing::s_wpInstance = v30;
        if ( v30 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v30 + 8LL))(v30, 2032) )
        {
          v29 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v29 = (CallStackTracing *)&qword_1800EB130;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
        }
      }
      if ( *((_BYTE *)v29 + 8) )
      {
        v31 = CallStackTracing::GetThreadRelativeContext(v29);
        if ( *((_DWORD *)v31 + 499) != v9 )
          CallStackContext::TraceFailure(v31, "CDShowWrapper::SetD3D11Resources", 1802, v9);
      }
      if ( !g_wppLevels )
        goto LABEL_148;
      v19 = 135;
      goto LABEL_41;
    }
    v9 = ((__int64 (__fastcall *)(IMFAttributes *, __int64 *, __int64))ppMFAttributes->lpVtbl->SetUINT32)(
           ppMFAttributes,
           MF_SA_BUFFERS_PER_SAMPLE,
           1);
    if ( v9 < 0 )
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
        if ( *((_DWORD *)v34 + 499) != v9 )
          CallStackContext::TraceFailure(v34, "CDShowWrapper::SetD3D11Resources", 1803, v9);
      }
      if ( !g_wppLevels )
        goto LABEL_148;
      v19 = 136;
      goto LABEL_41;
    }
    v9 = (*(__int64 (__fastcall **)(void *, __int64, __int64, IMFAttributes *, struct IMFMediaType *))(*(_QWORD *)ppSampleAllocator + 56LL))(
           ppSampleAllocator,
           1,
           10,
           ppMFAttributes,
           a2);
    if ( v9 < 0 )
    {
      v35 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v36 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
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
        if ( *((_DWORD *)v37 + 499) != v9 )
          CallStackContext::TraceFailure(v37, "CDShowWrapper::SetD3D11Resources", 1806, v9);
      }
      if ( !g_wppLevels )
        goto LABEL_148;
      v19 = 137;
      goto LABEL_41;
    }
    v9 = (**(__int64 (__fastcall ***)(void *, GUID *, __int64 *))ppSampleAllocator)(
           ppSampleAllocator,
           &GUID_992388b4_3372_4f67_8b6f_c84c071f4751,
           &v55);
    if ( v9 < 0 )
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
        if ( *((_DWORD *)v40 + 499) != v9 )
          CallStackContext::TraceFailure(v40, "CDShowWrapper::SetD3D11Resources", 1808, v9);
      }
      if ( !g_wppLevels )
        goto LABEL_148;
      v19 = 138;
      goto LABEL_41;
    }
    v41 = (CDShowSource *)*((_QWORD *)this + 1);
    if ( v41 )
    {
      v9 = CDShowSource::QueryInterface(v41, &GUID_a792cdbe_c374_4e89_8335_278e7b9956a4, &v54);
      if ( v9 < 0 )
      {
        v42 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v43 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
          CallStackTracing::s_wpInstance = v43;
          if ( v43 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v43 + 8LL))(v43, 2032) )
          {
            v42 = CallStackTracing::s_wpInstance;
          }
          else
          {
            v42 = (CallStackTracing *)&qword_1800EB130;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
          }
        }
        if ( *((_BYTE *)v42 + 8) )
        {
          v44 = CallStackTracing::GetThreadRelativeContext(v42);
          if ( *((_DWORD *)v44 + 499) != v9 )
            CallStackContext::TraceFailure(v44, "CDShowWrapper::SetD3D11Resources", 1812, v9);
        }
        if ( !g_wppLevels )
          goto LABEL_148;
        v19 = 139;
        goto LABEL_41;
      }
      v9 = (*(__int64 (__fastcall **)(__int64, void *))(*(_QWORD *)v55 + 24LL))(v55, v54);
      if ( v9 < 0 )
      {
        v45 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v46 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
          CallStackTracing::s_wpInstance = v46;
          if ( v46 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v46 + 8LL))(v46, 2032) )
          {
            v45 = CallStackTracing::s_wpInstance;
          }
          else
          {
            v45 = (CallStackTracing *)&qword_1800EB130;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
          }
        }
        if ( *((_BYTE *)v45 + 8) )
        {
          v47 = CallStackTracing::GetThreadRelativeContext(v45);
          if ( *((_DWORD *)v47 + 499) != v9 )
            CallStackContext::TraceFailure(v47, "CDShowWrapper::SetD3D11Resources", 1814, v9);
        }
        if ( !g_wppLevels )
          goto LABEL_148;
        v19 = 140;
LABEL_41:
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v19, &WPP_8e8a43b2e5013e25304950bf1ec57b49_Traceguids, this, v9);
        goto LABEL_148;
      }
    }
    if ( ppSampleAllocator )
    {
      (*(void (__fastcall **)(void *))(*(_QWORD *)ppSampleAllocator + 8LL))(ppSampleAllocator);
      v49 = *((_QWORD *)this + 43);
      if ( v49 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v49 + 16LL))(v49);
      *((_QWORD *)this + 43) = ppSampleAllocator;
    }
    else
    {
      v48 = *((_QWORD *)this + 43);
      if ( v48 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v48 + 16LL))(v48);
        *((_QWORD *)this + 43) = 0;
      }
    }
    goto LABEL_148;
  }
  v9 = -2147024809;
  if ( !v4 )
  {
    v13 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
    CallStackTracing::s_wpInstance = v13;
    if ( v13 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v13 + 8LL))(v13, 2032) )
    {
      v4 = CallStackTracing::s_wpInstance;
    }
    else
    {
      v4 = (CallStackTracing *)&qword_1800EB130;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
    }
  }
  if ( *((_BYTE *)v4 + 8) )
  {
    v14 = CallStackTracing::GetThreadRelativeContext(v4);
    if ( *((_DWORD *)v14 + 499) != -2147024809 )
      CallStackContext::TraceFailure(v14, "CDShowWrapper::SetD3D11Resources", 1789, -2147024809);
  }
  if ( g_wppLevels )
  {
    v12 = 130;
    goto LABEL_15;
  }
LABEL_148:
  ATL::CComPtrBase<IMediaSeeking>::~CComPtrBase<IMediaSeeking>(&v54);
  ATL::CComPtrBase<IMediaSeeking>::~CComPtrBase<IMediaSeeking>(&v55);
  ATL::CComPtrBase<IMediaSeeking>::~CComPtrBase<IMediaSeeking>(&ppMFAttributes);
  ATL::CComPtrBase<IMediaSeeking>::~CComPtrBase<IMediaSeeking>(&ppSampleAllocator);
  ATL::CComPtrBase<IMediaSeeking>::~CComPtrBase<IMediaSeeking>(&v56);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v51);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800853b0  mov     [rsp-28h+arg_10], rbx
0x1800853b5  mov     [rsp-28h+arg_18], rsi
0x1800853ba  push    rbp
0x1800853bb  push    rdi
0x1800853bc  push    r12
0x1800853be  push    r14
0x1800853c0  push    r15
0x1800853c2  mov     rbp, rsp
0x1800853c5  sub     rsp, 80h
0x1800853cc  mov     rax, cs:__security_cookie
0x1800853d3  xor     rax, rsp
0x1800853d6  mov     [rbp+var_10], rax
0x1800853da  mov     r14, rdx
0x1800853dd  lea     r12, aCdshowwrapperS_0; "CDShowWrapper::SetD3D11Resources"
0x1800853e4  mov     rsi, rcx
0x1800853e7  mov     rdx, r12; char *
0x1800853ea  mov     r8d, 6F3h; int
0x1800853f0  lea     rcx, [rbp+var_50]; this
0x1800853f4  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800853f9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180085400  xor     r15d, r15d
0x180085403  cmp     [rcx+8], r15b
0x180085407  jz      short loc_180085464
0x180085409  cmp     [rsi+1E0h], r15
0x180085410  jz      short loc_180085464
0x180085412  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180085417  mov     rcx, [rsi+1E0h]
0x18008541e  mov     rdi, rax
0x180085421  mov     rdx, [rcx]
0x180085424  mov     rax, [rdx+128h]
0x18008542b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180085430  mov     rcx, [rsi+1E0h]
0x180085437  mov     ebx, eax
0x180085439  mov     rdx, [rcx]
0x18008543c  mov     rax, [rdx+118h]
0x180085443  lea     rdx, [rbp+var_20]
0x180085447  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008544c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180085453  movups  xmm0, xmmword ptr [rax]
0x180085456  mov     [rdi+7E0h], ebx
0x18008545c  movdqu  xmmword ptr [rdi+7D0h], xmm0
0x180085464  mov     [rbp+var_28], r15
0x180085468  mov     [rbp+ppSampleAllocator], r15
0x18008546c  mov     [rbp+ppMFAttributes], r15
0x180085470  mov     [rbp+var_30], r15
0x180085474  mov     [rbp+var_38], r15
0x180085478  cmp     [rsi+148h], r15
0x18008547f  jnz     loc_180085534
0x180085485  mov     edi, 80070057h
0x18008548a  mov     ebx, edi
0x18008548c  test    rcx, rcx
0x18008548f  jnz     short loc_1800854D8
0x180085491  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180085498  nop     dword ptr [rax+rax+00h]
0x18008549d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800854a4  mov     rcx, rax
0x1800854a7  test    rax, rax
0x1800854aa  jz      short loc_1800854CA
0x1800854ac  mov     rax, [rax]
0x1800854af  mov     edx, 7F0h
0x1800854b4  mov     rax, [rax+8]
0x1800854b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800854bd  test    eax, eax
0x1800854bf  jz      short loc_1800854CA
0x1800854c1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800854c8  jmp     short loc_1800854D8
0x1800854ca  lea     rcx, qword_1800EB130; this
0x1800854d1  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800854d8  cmp     [rcx+8], r15b
0x1800854dc  jz      short loc_1800854FF
0x1800854de  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800854e3  cmp     [rax+7CCh], edi
0x1800854e9  jz      short loc_1800854FF
0x1800854eb  mov     r9d, edi; int
0x1800854ee  mov     r8d, 6FCh; int
0x1800854f4  mov     rdx, r12; char *
0x1800854f7  mov     rcx, rax; this
0x1800854fa  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800854ff  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180085506  jb      loc_180085D61
0x18008550c  mov     edx, 81h
0x180085511  mov     dword ptr [rsp+80h+var_60], edi
0x180085515  mov     rcx, cs:WPP_GLOBAL_Control
0x18008551c  lea     r8, WPP_8e8a43b2e5013e25304950bf1ec57b49_Traceguids
0x180085523  mov     r9, rsi
0x180085526  mov     rcx, [rcx+10h]
0x18008552a  call    WPP_SF_qD
0x18008552f  jmp     loc_180085D61
0x180085534  test    r14, r14
0x180085537  jnz     loc_1800855CE
0x18008553d  mov     edi, 80070057h
0x180085542  mov     ebx, edi
0x180085544  test    rcx, rcx
0x180085547  jnz     short loc_180085590
0x180085549  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180085550  nop     dword ptr [rax+rax+00h]
0x180085555  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18008555c  mov     rcx, rax
0x18008555f  test    rax, rax
0x180085562  jz      short loc_180085582
0x180085564  mov     rax, [rax]
0x180085567  mov     edx, 7F0h
0x18008556c  mov     rax, [rax+8]
0x180085570  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180085575  test    eax, eax
0x180085577  jz      short loc_180085582
0x180085579  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180085580  jmp     short loc_180085590
0x180085582  lea     rcx, qword_1800EB130; this
0x180085589  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180085590  cmp     [rcx+8], r15b
0x180085594  jz      short loc_1800855B7
0x180085596  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18008559b  cmp     [rax+7CCh], edi
0x1800855a1  jz      short loc_1800855B7
0x1800855a3  mov     r9d, edi; int
0x1800855a6  mov     r8d, 6FDh; int
0x1800855ac  mov     rdx, r12; char *
0x1800855af  mov     rcx, rax; this
0x1800855b2  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800855b7  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800855be  jb      loc_180085D61
0x1800855c4  mov     edx, 82h
0x1800855c9  jmp     loc_180085511
0x1800855ce  mov     rcx, [rsi+158h]
0x1800855d5  test    rcx, rcx
0x1800855d8  jz      short loc_1800855ED
0x1800855da  mov     rax, [rcx]
0x1800855dd  mov     rax, [rax+10h]
0x1800855e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800855e6  mov     [rsi+158h], r15
0x1800855ed  lea     rdx, [rbp+ppSampleAllocator]; ppSampleAllocator
0x1800855f1  lea     rcx, _GUID_545b3a48_3283_4f62_866f_a62d8f598f9f; riid
0x1800855f8  call    cs:__imp_MFCreateVideoSampleAllocatorEx
0x1800855ff  nop     dword ptr [rax+rax+00h]
0x180085604  mov     ebx, eax
0x180085606  test    eax, eax
0x180085608  jns     loc_1800856A3
0x18008560e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180085615  test    rcx, rcx
0x180085618  jnz     short loc_180085661
0x18008561a  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180085621  nop     dword ptr [rax+rax+00h]
0x180085626  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18008562d  mov     rcx, rax
0x180085630  test    rax, rax
0x180085633  jz      short loc_180085653
0x180085635  mov     rax, [rax]
0x180085638  mov     edx, 7F0h
0x18008563d  mov     rax, [rax+8]
0x180085641  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180085646  test    eax, eax
0x180085648  jz      short loc_180085653
0x18008564a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180085651  jmp     short loc_180085661
0x180085653  lea     rcx, qword_1800EB130; this
0x18008565a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180085661  cmp     [rcx+8], r15b
0x180085665  jz      short loc_180085688
0x180085667  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18008566c  cmp     [rax+7CCh], ebx
0x180085672  jz      short loc_180085688
0x180085674  mov     r9d, ebx; int
0x180085677  mov     r8d, 704h; int
0x18008567d  mov     rdx, r12; char *
0x180085680  mov     rcx, rax; this
0x180085683  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180085688  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18008568f  jb      loc_180085D61
0x180085695  mov     edx, 83h
0x18008569a  mov     dword ptr [rsp+80h+var_60], ebx
0x18008569e  jmp     loc_180085515
0x1800856a3  mov     rcx, [rbp+ppSampleAllocator]
0x1800856a7  mov     rdx, [rsi+148h]
0x1800856ae  mov     rax, [rcx]
0x1800856b1  mov     rax, [rax+18h]
0x1800856b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800856ba  mov     ebx, eax
0x1800856bc  test    eax, eax
0x1800856be  jns     loc_180085755
0x1800856c4  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800856cb  test    rcx, rcx
0x1800856ce  jnz     short loc_180085717
0x1800856d0  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800856d7  nop     dword ptr [rax+rax+00h]
0x1800856dc  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800856e3  mov     rcx, rax
0x1800856e6  test    rax, rax
0x1800856e9  jz      short loc_180085709
0x1800856eb  mov     rax, [rax]
0x1800856ee  mov     edx, 7F0h
0x1800856f3  mov     rax, [rax+8]
0x1800856f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800856fc  test    eax, eax
0x1800856fe  jz      short loc_180085709
0x180085700  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180085707  jmp     short loc_180085717
0x180085709  lea     rcx, qword_1800EB130; this
0x180085710  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180085717  cmp     [rcx+8], r15b
0x18008571b  jz      short loc_18008573E
0x18008571d  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180085722  cmp     [rax+7CCh], ebx
0x180085728  jz      short loc_18008573E
0x18008572a  mov     r9d, ebx; int
0x18008572d  mov     r8d, 706h; int
0x180085733  mov     rdx, r12; char *
0x180085736  mov     rcx, rax; this
0x180085739  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18008573e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180085745  jb      loc_180085D61
0x18008574b  mov     edx, 84h
0x180085750  jmp     loc_18008569A
0x180085755  mov     edx, 1; cInitialSize
0x18008575a  lea     rcx, [rbp+ppMFAttributes]; ppMFAttributes
0x18008575e  call    cs:__imp_MFCreateAttributes
0x180085765  nop     dword ptr [rax+rax+00h]
0x18008576a  mov     ebx, eax
0x18008576c  test    eax, eax
0x18008576e  jns     loc_180085805
0x180085774  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18008577b  test    rcx, rcx
0x18008577e  jnz     short loc_1800857C7
0x180085780  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180085787  nop     dword ptr [rax+rax+00h]
0x18008578c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180085793  mov     rcx, rax
0x180085796  test    rax, rax
0x180085799  jz      short loc_1800857B9
0x18008579b  mov     rax, [rax]
0x18008579e  mov     edx, 7F0h
0x1800857a3  mov     rax, [rax+8]
0x1800857a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800857ac  test    eax, eax
0x1800857ae  jz      short loc_1800857B9
0x1800857b0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800857b7  jmp     short loc_1800857C7
0x1800857b9  lea     rcx, qword_1800EB130; this
0x1800857c0  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800857c7  cmp     [rcx+8], r15b
0x1800857cb  jz      short loc_1800857EE
0x1800857cd  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800857d2  cmp     [rax+7CCh], ebx
0x1800857d8  jz      short loc_1800857EE
0x1800857da  mov     r9d, ebx; int
0x1800857dd  mov     r8d, 708h; int
0x1800857e3  mov     rdx, r12; char *
0x1800857e6  mov     rcx, rax; this
0x1800857e9  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800857ee  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800857f5  jb      loc_180085D61
0x1800857fb  mov     edx, 85h
0x180085800  jmp     loc_18008569A
0x180085805  mov     rcx, [rbp+ppMFAttributes]
0x180085809  lea     rdx, MF_SA_D3D11_USAGE
0x180085810  xor     r8d, r8d
0x180085813  mov     rax, [rcx]
0x180085816  mov     rax, [rax+0A8h]
0x18008581d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180085822  mov     ebx, eax
0x180085824  test    eax, eax
0x180085826  jns     loc_1800858BD
0x18008582c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180085833  test    rcx, rcx
0x180085836  jnz     short loc_18008587F
0x180085838  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18008583f  nop     dword ptr [rax+rax+00h]
0x180085844  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18008584b  mov     rcx, rax
0x18008584e  test    rax, rax
0x180085851  jz      short loc_180085871
0x180085853  mov     rax, [rax]
0x180085856  mov     edx, 7F0h
0x18008585b  mov     rax, [rax+8]
0x18008585f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180085864  test    eax, eax
0x180085866  jz      short loc_180085871
0x180085868  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18008586f  jmp     short loc_18008587F
0x180085871  lea     rcx, qword_1800EB130; this
0x180085878  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18008587f  cmp     [rcx+8], r15b
0x180085883  jz      short loc_1800858A6
0x180085885  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18008588a  cmp     [rax+7CCh], ebx
0x180085890  jz      short loc_1800858A6
0x180085892  mov     r9d, ebx; int
0x180085895  mov     r8d, 709h; int
0x18008589b  mov     rdx, r12; char *
0x18008589e  mov     rcx, rax; this
0x1800858a1  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800858a6  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800858ad  jb      loc_180085D61
0x1800858b3  mov     edx, 86h
0x1800858b8  jmp     loc_18008569A
0x1800858bd  mov     rcx, [rbp+ppMFAttributes]
0x1800858c1  lea     rdx, MF_SA_D3D11_BINDFLAGS
0x1800858c8  mov     r8d, 20h ; ' '
0x1800858ce  mov     rax, [rcx]
0x1800858d1  mov     rax, [rax+0A8h]
  ... truncated ...
```
