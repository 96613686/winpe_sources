# CDShowWrapper::ConfigureDemux(IPin *)

- ea: `0x18007eb88`
- end: `0x18007f3ca`
- name: `?ConfigureDemux@CDShowWrapper@@IEAAJPEAUIPin@@@Z`
- size: `2114`
- prototype: `__int64 __fastcall(CDShowWrapper *__hidden this, struct IPin *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180030060`

## callees

- `0x180002820`
- `0x18000b8c0`
- `0x1800140b0`
- `0x1800227e0`
- `0x180032988`
- `0x180032a50`
- `0x180051ce4`
- `0x180074160`
- `0x18007d58c`
- `0x18007eb88`
- `0x180084e00`
- `0x1800c9010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18007efdc`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18007efdc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007ec83`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007ed2e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007eddf`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007ee97`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007ef3a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007effe`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007f0bf`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007f169`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007f218`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007f2c6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007ec83`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007ed2e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007eddf`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007ee97`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007ef3a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007effe`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007f0bf`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007f169`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007f218`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007f2c6`

## string_xrefs

- `0x18007ebb5`: `CDShowWrapper::ConfigureDemux`

## pseudocode

```c
__int64 __fastcall CDShowWrapper::ConfigureDemux(CDShowWrapper *this, struct IPin *a2)
{
  struct CallStackContext *ThreadRelativeContext; // rdi
  int v5; // ebx
  __int128 v6; // xmm0
  HRESULT v7; // edi
  CallStackTracing *v8; // rcx
  CallStackTracing *v9; // rax
  struct CallStackContext *v10; // rax
  __int64 v11; // rdx
  CallStackTracing *v12; // rcx
  CallStackTracing *v13; // rax
  struct CallStackContext *v14; // rax
  CallStackTracing *v15; // rcx
  CallStackTracing *v16; // rax
  struct CallStackContext *v17; // rax
  struct IBaseFilter *v18; // rbx
  CallStackTracing *v19; // rcx
  CallStackTracing *v20; // rax
  struct CallStackContext *v21; // rax
  CallStackTracing *v22; // rcx
  CallStackTracing *v23; // rax
  struct CallStackContext *v24; // rax
  CallStackTracing *v25; // rcx
  CallStackTracing *v26; // rax
  struct CallStackContext *v27; // rax
  CallStackTracing *v28; // rcx
  CallStackTracing *v29; // rax
  struct CallStackContext *v30; // rax
  CallStackTracing *v31; // rcx
  CallStackTracing *v32; // rax
  struct CallStackContext *v33; // rax
  CallStackTracing *v34; // rcx
  CallStackTracing *v35; // rax
  struct CallStackContext *v36; // rax
  CallStackTracing *v37; // rcx
  CallStackTracing *v38; // rax
  struct CallStackContext *v39; // rax
  _BYTE v41[8]; // [rsp+30h] [rbp-50h] BYREF
  void *v42; // [rsp+38h] [rbp-48h] BYREF
  LPVOID ppv; // [rsp+40h] [rbp-40h] BYREF
  __int64 v44; // [rsp+48h] [rbp-38h] BYREF
  __int64 v45; // [rsp+50h] [rbp-30h] BYREF
  struct IPin *v46; // [rsp+58h] [rbp-28h] BYREF
  struct IBaseFilter *v47; // [rsp+60h] [rbp-20h] BYREF
  _BYTE v48[16]; // [rsp+68h] [rbp-18h] BYREF

  v47 = 0;
  v46 = 0;
  v45 = 0;
  v44 = 0;
  ppv = 0;
  v42 = 0;
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v41, "CDShowWrapper::ConfigureDemux", 5273);
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) && *((_QWORD *)this + 60) )
  {
    ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
    v5 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 60) + 296LL))(*((_QWORD *)this + 60));
    v6 = *(_OWORD *)(*(__int64 (__fastcall **)(_QWORD, _BYTE *))(**((_QWORD **)this + 60) + 280LL))(
                      *((_QWORD *)this + 60),
                      v48);
    *((_DWORD *)ThreadRelativeContext + 504) = v5;
    *((_OWORD *)ThreadRelativeContext + 125) = v6;
  }
  v7 = (***((__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))this + 9))(
         *((_QWORD *)this + 9),
         &GUID_436eee9c_264f_4242_90e1_4e330c107512,
         &v44);
  if ( v7 >= 0 )
  {
    v7 = CDShowWrapper::AddPSIFilterToGraph(this, &v47, &v46);
    if ( v7 >= 0 )
    {
      v7 = ((__int64 (__fastcall *)(struct IPin *, struct IPin *, _QWORD))a2->lpVtbl->Connect)(a2, v46, 0);
      if ( v7 >= 0 )
      {
        v18 = v47;
        v7 = ((__int64 (__fastcall *)(struct IBaseFilter *, GUID *, __int64 *))v47->lpVtbl->QueryInterface)(
               v47,
               &GUID_c5d0dd45_05e2_4703_938f_4abbc6e3dee0,
               &v45);
        if ( v7 >= 0 )
        {
          v7 = CDShowWrapper::RunAndWaitForPSIGraph(this);
          if ( v7 >= 0 )
          {
            v7 = CoCreateInstance(&CLSID_DemuxRender, 0, 1u, &GUID_8f7c48e9_e418_456f_9265_a922135b0d49, &ppv);
            if ( v7 >= 0 )
            {
              v7 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, _QWORD, __int64, __int64))(*(_QWORD *)ppv + 24LL))(
                     ppv,
                     0,
                     *((_QWORD *)this + 9),
                     v44,
                     v45);
              if ( v7 >= 0 )
              {
                v7 = ((__int64 (__fastcall *)(struct IPin *))a2->lpVtbl->Disconnect)(a2);
                if ( v7 >= 0 )
                {
                  v7 = CGITPtr::Get(
                         (CDShowWrapper *)((char *)this + 48),
                         &GUID_56a868a9_0ad4_11ce_b03a_0020af0ba770,
                         &v42);
                  if ( v7 >= 0 )
                  {
                    v7 = (*(__int64 (__fastcall **)(void *, struct IBaseFilter *))(*(_QWORD *)v42 + 32LL))(v42, v18);
                    if ( v7 < 0 )
                    {
                      v37 = CallStackTracing::s_wpInstance;
                      if ( !CallStackTracing::s_wpInstance )
                      {
                        v38 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
                        CallStackTracing::s_wpInstance = v38;
                        if ( v38
                          && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v38 + 8LL))(
                               v38,
                               2032) )
                        {
                          v37 = CallStackTracing::s_wpInstance;
                        }
                        else
                        {
                          v37 = (CallStackTracing *)&qword_1800EB130;
                          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
                        }
                      }
                      if ( *((_BYTE *)v37 + 8) )
                      {
                        v39 = CallStackTracing::GetThreadRelativeContext(v37);
                        if ( *((_DWORD *)v39 + 499) != v7 )
                          CallStackContext::TraceFailure(v39, "CDShowWrapper::ConfigureDemux", 5295, v7);
                      }
                      if ( g_wppLevels )
                      {
                        v11 = 488;
                        goto LABEL_114;
                      }
                    }
                  }
                  else
                  {
                    v34 = CallStackTracing::s_wpInstance;
                    if ( !CallStackTracing::s_wpInstance )
                    {
                      v35 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
                      CallStackTracing::s_wpInstance = v35;
                      if ( v35
                        && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v35 + 8LL))(
                             v35,
                             2032) )
                      {
                        v34 = CallStackTracing::s_wpInstance;
                      }
                      else
                      {
                        v34 = (CallStackTracing *)&qword_1800EB130;
                        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
                      }
                    }
                    if ( *((_BYTE *)v34 + 8) )
                    {
                      v36 = CallStackTracing::GetThreadRelativeContext(v34);
                      if ( *((_DWORD *)v36 + 499) != v7 )
                        CallStackContext::TraceFailure(v36, "CDShowWrapper::ConfigureDemux", 5294, v7);
                    }
                    if ( g_wppLevels )
                    {
                      v11 = 487;
                      goto LABEL_114;
                    }
                  }
                }
                else
                {
                  v31 = CallStackTracing::s_wpInstance;
                  if ( !CallStackTracing::s_wpInstance )
                  {
                    v32 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
                    CallStackTracing::s_wpInstance = v32;
                    if ( v32
                      && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v32 + 8LL))(v32, 2032) )
                    {
                      v31 = CallStackTracing::s_wpInstance;
                    }
                    else
                    {
                      v31 = (CallStackTracing *)&qword_1800EB130;
                      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
                    }
                  }
                  if ( *((_BYTE *)v31 + 8) )
                  {
                    v33 = CallStackTracing::GetThreadRelativeContext(v31);
                    if ( *((_DWORD *)v33 + 499) != v7 )
                      CallStackContext::TraceFailure(v33, "CDShowWrapper::ConfigureDemux", 5293, v7);
                  }
                  if ( g_wppLevels )
                  {
                    v11 = 486;
                    goto LABEL_114;
                  }
                }
              }
              else
              {
                v28 = CallStackTracing::s_wpInstance;
                if ( !CallStackTracing::s_wpInstance )
                {
                  v29 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
                  CallStackTracing::s_wpInstance = v29;
                  if ( v29
                    && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v29 + 8LL))(v29, 2032) )
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
                  if ( *((_DWORD *)v30 + 499) != v7 )
                    CallStackContext::TraceFailure(v30, "CDShowWrapper::ConfigureDemux", 5288, v7);
                }
                if ( g_wppLevels )
                {
                  v11 = 485;
                  goto LABEL_114;
                }
              }
            }
            else
            {
              v25 = CallStackTracing::s_wpInstance;
              if ( !CallStackTracing::s_wpInstance )
              {
                v26 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
                CallStackTracing::s_wpInstance = v26;
                if ( v26
                  && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v26 + 8LL))(v26, 2032) )
                {
                  v25 = CallStackTracing::s_wpInstance;
                }
                else
                {
                  v25 = (CallStackTracing *)&qword_1800EB130;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
                }
              }
              if ( *((_BYTE *)v25 + 8) )
              {
                v27 = CallStackTracing::GetThreadRelativeContext(v25);
                if ( *((_DWORD *)v27 + 499) != v7 )
                  CallStackContext::TraceFailure(v27, "CDShowWrapper::ConfigureDemux", 5287, v7);
              }
              if ( g_wppLevels )
              {
                v11 = 484;
                goto LABEL_114;
              }
            }
          }
          else
          {
            v22 = CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v23 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
              CallStackTracing::s_wpInstance = v23;
              if ( v23
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v23 + 8LL))(v23, 2032) )
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
              if ( *((_DWORD *)v24 + 499) != v7 )
                CallStackContext::TraceFailure(v24, "CDShowWrapper::ConfigureDemux", 5284, v7);
            }
            if ( g_wppLevels )
            {
              v11 = 483;
              goto LABEL_114;
            }
          }
        }
        else
        {
          v19 = CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v20 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
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
            if ( *((_DWORD *)v21 + 499) != v7 )
              CallStackContext::TraceFailure(v21, "CDShowWrapper::ConfigureDemux", 5279, v7);
          }
          if ( g_wppLevels )
          {
            v11 = 482;
            goto LABEL_114;
          }
        }
      }
      else
      {
        v15 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v16 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
          CallStackTracing::s_wpInstance = v16;
          if ( v16 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v16 + 8LL))(v16, 2032) )
          {
            v15 = CallStackTracing::s_wpInstance;
          }
          else
          {
            v15 = (CallStackTracing *)&qword_1800EB130;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
          }
        }
        if ( *((_BYTE *)v15 + 8) )
        {
          v17 = CallStackTracing::GetThreadRelativeContext(v15);
          if ( *((_DWORD *)v17 + 499) != v7 )
            CallStackContext::TraceFailure(v17, "CDShowWrapper::ConfigureDemux", 5277, v7);
        }
        if ( g_wppLevels )
        {
          v11 = 481;
          goto LABEL_114;
        }
      }
    }
    else
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
        if ( *((_DWORD *)v14 + 499) != v7 )
          CallStackContext::TraceFailure(v14, "CDShowWrapper::ConfigureDemux", 5275, v7);
      }
      if ( g_wppLevels )
      {
        v11 = 480;
        goto LABEL_114;
      }
    }
  }
  else
  {
    v8 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v9 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
      CallStackTracing::s_wpInstance = v9;
      if ( v9 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v9 + 8LL))(v9, 2032) )
      {
        v8 = CallStackTracing::s_wpInstance;
      }
      else
      {
        v8 = (CallStackTracing *)&qword_1800EB130;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
      }
    }
    if ( *((_BYTE *)v8 + 8) )
    {
      v10 = CallStackTracing::GetThreadRelativeContext(v8);
      if ( *((_DWORD *)v10 + 499) != v7 )
        CallStackContext::TraceFailure(v10, "CDShowWrapper::ConfigureDemux", 5273, v7);
    }
    if ( g_wppLevels )
    {
      v11 = 479;
LABEL_114:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v11, &WPP_8e8a43b2e5013e25304950bf1ec57b49_Traceguids, this, v7);
    }
  }
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v41);
  ATL::CComPtrBase<IMediaSeeking>::~CComPtrBase<IMediaSeeking>(&v42);
  ATL::CComPtrBase<IMediaSeeking>::~CComPtrBase<IMediaSeeking>(&ppv);
  ATL::CComPtrBase<IMediaSeeking>::~CComPtrBase<IMediaSeeking>(&v44);
  ATL::CComPtrBase<IMediaSeeking>::~CComPtrBase<IMediaSeeking>(&v45);
  ATL::CComPtrBase<IMediaSeeking>::~CComPtrBase<IMediaSeeking>(&v46);
  ATL::CComPtrBase<IMediaSeeking>::~CComPtrBase<IMediaSeeking>(&v47);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18007eb88  mov     [rsp-28h+arg_10], rbx
0x18007eb8d  mov     [rsp-28h+arg_18], rsi
0x18007eb92  push    rbp
0x18007eb93  push    rdi
0x18007eb94  push    r12
0x18007eb96  push    r14
0x18007eb98  push    r15
0x18007eb9a  mov     rbp, rsp
0x18007eb9d  sub     rsp, 80h
0x18007eba4  mov     rax, cs:__security_cookie
0x18007ebab  xor     rax, rsp
0x18007ebae  mov     [rbp+var_8], rax
0x18007ebb2  xor     r15d, r15d
0x18007ebb5  lea     r12, aCdshowwrapperC_14; "CDShowWrapper::ConfigureDemux"
0x18007ebbc  mov     r14, rdx
0x18007ebbf  mov     [rbp+var_20], r15
0x18007ebc3  mov     rsi, rcx
0x18007ebc6  mov     [rbp+var_28], r15
0x18007ebca  mov     rdx, r12; char *
0x18007ebcd  mov     [rbp+var_30], r15
0x18007ebd1  mov     r8d, 1499h; int
0x18007ebd7  mov     [rbp+var_38], r15
0x18007ebdb  lea     rcx, [rbp+var_50]; this
0x18007ebdf  mov     [rbp+var_40], r15
0x18007ebe3  mov     [rbp+var_48], r15
0x18007ebe7  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18007ebec  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18007ebf3  cmp     [rcx+8], r15b
0x18007ebf7  jz      short loc_18007EC53
0x18007ebf9  cmp     [rsi+1E0h], r15
0x18007ec00  jz      short loc_18007EC53
0x18007ec02  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18007ec07  mov     rdx, [rsi+1E0h]
0x18007ec0e  mov     rdi, rax
0x18007ec11  mov     rcx, [rdx]
0x18007ec14  mov     rax, [rcx+128h]
0x18007ec1b  mov     rcx, rdx
0x18007ec1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007ec23  mov     r8, [rsi+1E0h]
0x18007ec2a  lea     rdx, [rbp+var_18]
0x18007ec2e  mov     ebx, eax
0x18007ec30  mov     rcx, [r8]
0x18007ec33  mov     rax, [rcx+118h]
0x18007ec3a  mov     rcx, r8
0x18007ec3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007ec42  movups  xmm0, xmmword ptr [rax]
0x18007ec45  mov     [rdi+7E0h], ebx
0x18007ec4b  movdqu  xmmword ptr [rdi+7D0h], xmm0
0x18007ec53  mov     rcx, [rsi+48h]
0x18007ec57  lea     r8, [rbp+var_38]
0x18007ec5b  lea     rdx, _GUID_436eee9c_264f_4242_90e1_4e330c107512
0x18007ec62  mov     rax, [rcx]
0x18007ec65  mov     rax, [rax]
0x18007ec68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007ec6d  mov     edi, eax
0x18007ec6f  test    eax, eax
0x18007ec71  jns     loc_18007ED08
0x18007ec77  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007ec7e  test    rcx, rcx
0x18007ec81  jnz     short loc_18007ECCA
0x18007ec83  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18007ec8a  nop     dword ptr [rax+rax+00h]
0x18007ec8f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18007ec96  mov     rcx, rax
0x18007ec99  test    rax, rax
0x18007ec9c  jz      short loc_18007ECBC
0x18007ec9e  mov     rax, [rax]
0x18007eca1  mov     edx, 7F0h
0x18007eca6  mov     rax, [rax+8]
0x18007ecaa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007ecaf  test    eax, eax
0x18007ecb1  jz      short loc_18007ECBC
0x18007ecb3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007ecba  jmp     short loc_18007ECCA
0x18007ecbc  lea     rcx, qword_1800EB130; this
0x18007ecc3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18007ecca  cmp     [rcx+8], r15b
0x18007ecce  jz      short loc_18007ECF1
0x18007ecd0  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18007ecd5  cmp     [rax+7CCh], edi
0x18007ecdb  jz      short loc_18007ECF1
0x18007ecdd  mov     r9d, edi; int
0x18007ece0  mov     r8d, 1499h; int
0x18007ece6  mov     rdx, r12; char *
0x18007ece9  mov     rcx, rax; this
0x18007ecec  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18007ecf1  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18007ecf8  jb      loc_18007F360
0x18007ecfe  mov     edx, 1DFh
0x18007ed03  jmp     loc_18007F342
0x18007ed08  lea     r8, [rbp+var_28]; struct IPin **
0x18007ed0c  mov     rcx, rsi; this
0x18007ed0f  lea     rdx, [rbp+var_20]; struct IBaseFilter **
0x18007ed13  call    ?AddPSIFilterToGraph@CDShowWrapper@@IEAAJPEAPEAUIBaseFilter@@PEAPEAUIPin@@@Z; CDShowWrapper::AddPSIFilterToGraph(IBaseFilter * *,IPin * *)
0x18007ed18  mov     edi, eax
0x18007ed1a  test    eax, eax
0x18007ed1c  jns     loc_18007EDB3
0x18007ed22  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007ed29  test    rcx, rcx
0x18007ed2c  jnz     short loc_18007ED75
0x18007ed2e  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18007ed35  nop     dword ptr [rax+rax+00h]
0x18007ed3a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18007ed41  mov     rcx, rax
0x18007ed44  test    rax, rax
0x18007ed47  jz      short loc_18007ED67
0x18007ed49  mov     rax, [rax]
0x18007ed4c  mov     edx, 7F0h
0x18007ed51  mov     rax, [rax+8]
0x18007ed55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007ed5a  test    eax, eax
0x18007ed5c  jz      short loc_18007ED67
0x18007ed5e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007ed65  jmp     short loc_18007ED75
0x18007ed67  lea     rcx, qword_1800EB130; this
0x18007ed6e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18007ed75  cmp     [rcx+8], r15b
0x18007ed79  jz      short loc_18007ED9C
0x18007ed7b  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18007ed80  cmp     [rax+7CCh], edi
0x18007ed86  jz      short loc_18007ED9C
0x18007ed88  mov     r9d, edi; int
0x18007ed8b  mov     r8d, 149Bh; int
0x18007ed91  mov     rdx, r12; char *
0x18007ed94  mov     rcx, rax; this
0x18007ed97  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18007ed9c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18007eda3  jb      loc_18007F360
0x18007eda9  mov     edx, 1E0h
0x18007edae  jmp     loc_18007F342
0x18007edb3  mov     rax, [r14]
0x18007edb6  xor     r8d, r8d
0x18007edb9  mov     rdx, [rbp+var_28]
0x18007edbd  mov     rcx, r14
0x18007edc0  mov     rax, [rax+18h]
0x18007edc4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007edc9  mov     edi, eax
0x18007edcb  test    eax, eax
0x18007edcd  jns     loc_18007EE64
0x18007edd3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007edda  test    rcx, rcx
0x18007eddd  jnz     short loc_18007EE26
0x18007eddf  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18007ede6  nop     dword ptr [rax+rax+00h]
0x18007edeb  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18007edf2  mov     rcx, rax
0x18007edf5  test    rax, rax
0x18007edf8  jz      short loc_18007EE18
0x18007edfa  mov     rax, [rax]
0x18007edfd  mov     edx, 7F0h
0x18007ee02  mov     rax, [rax+8]
0x18007ee06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007ee0b  test    eax, eax
0x18007ee0d  jz      short loc_18007EE18
0x18007ee0f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007ee16  jmp     short loc_18007EE26
0x18007ee18  lea     rcx, qword_1800EB130; this
0x18007ee1f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18007ee26  cmp     [rcx+8], r15b
0x18007ee2a  jz      short loc_18007EE4D
0x18007ee2c  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18007ee31  cmp     [rax+7CCh], edi
0x18007ee37  jz      short loc_18007EE4D
0x18007ee39  mov     r9d, edi; int
0x18007ee3c  mov     r8d, 149Dh; int
0x18007ee42  mov     rdx, r12; char *
0x18007ee45  mov     rcx, rax; this
0x18007ee48  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18007ee4d  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18007ee54  jb      loc_18007F360
0x18007ee5a  mov     edx, 1E1h
0x18007ee5f  jmp     loc_18007F342
0x18007ee64  mov     rbx, [rbp+var_20]
0x18007ee68  lea     r8, [rbp+var_30]
0x18007ee6c  lea     rdx, _GUID_c5d0dd45_05e2_4703_938f_4abbc6e3dee0
0x18007ee73  mov     rcx, rbx
0x18007ee76  mov     rax, [rbx]
0x18007ee79  mov     rax, [rax]
0x18007ee7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007ee81  mov     edi, eax
0x18007ee83  test    eax, eax
0x18007ee85  jns     loc_18007EF1C
0x18007ee8b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007ee92  test    rcx, rcx
0x18007ee95  jnz     short loc_18007EEDE
0x18007ee97  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18007ee9e  nop     dword ptr [rax+rax+00h]
0x18007eea3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18007eeaa  mov     rcx, rax
0x18007eead  test    rax, rax
0x18007eeb0  jz      short loc_18007EED0
0x18007eeb2  mov     rax, [rax]
0x18007eeb5  mov     edx, 7F0h
0x18007eeba  mov     rax, [rax+8]
0x18007eebe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007eec3  test    eax, eax
0x18007eec5  jz      short loc_18007EED0
0x18007eec7  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007eece  jmp     short loc_18007EEDE
0x18007eed0  lea     rcx, qword_1800EB130; this
0x18007eed7  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18007eede  cmp     [rcx+8], r15b
0x18007eee2  jz      short loc_18007EF05
0x18007eee4  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18007eee9  cmp     [rax+7CCh], edi
0x18007eeef  jz      short loc_18007EF05
0x18007eef1  mov     r9d, edi; int
0x18007eef4  mov     r8d, 149Fh; int
0x18007eefa  mov     rdx, r12; char *
0x18007eefd  mov     rcx, rax; this
0x18007ef00  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18007ef05  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18007ef0c  jb      loc_18007F360
0x18007ef12  mov     edx, 1E2h
0x18007ef17  jmp     loc_18007F342
0x18007ef1c  mov     rcx, rsi; this
0x18007ef1f  call    ?RunAndWaitForPSIGraph@CDShowWrapper@@IEAAJXZ; CDShowWrapper::RunAndWaitForPSIGraph(void)
0x18007ef24  mov     edi, eax
0x18007ef26  test    eax, eax
0x18007ef28  jns     loc_18007EFBF
0x18007ef2e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007ef35  test    rcx, rcx
0x18007ef38  jnz     short loc_18007EF81
0x18007ef3a  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18007ef41  nop     dword ptr [rax+rax+00h]
0x18007ef46  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18007ef4d  mov     rcx, rax
0x18007ef50  test    rax, rax
0x18007ef53  jz      short loc_18007EF73
0x18007ef55  mov     rax, [rax]
0x18007ef58  mov     edx, 7F0h
0x18007ef5d  mov     rax, [rax+8]
0x18007ef61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007ef66  test    eax, eax
0x18007ef68  jz      short loc_18007EF73
0x18007ef6a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007ef71  jmp     short loc_18007EF81
0x18007ef73  lea     rcx, qword_1800EB130; this
0x18007ef7a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18007ef81  cmp     [rcx+8], r15b
0x18007ef85  jz      short loc_18007EFA8
0x18007ef87  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18007ef8c  cmp     [rax+7CCh], edi
0x18007ef92  jz      short loc_18007EFA8
0x18007ef94  mov     r9d, edi; int
0x18007ef97  mov     r8d, 14A4h; int
0x18007ef9d  mov     rdx, r12; char *
0x18007efa0  mov     rcx, rax; this
0x18007efa3  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18007efa8  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18007efaf  jb      loc_18007F360
0x18007efb5  mov     edx, 1E3h
0x18007efba  jmp     loc_18007F342
0x18007efbf  xor     edx, edx; pUnkOuter
0x18007efc1  lea     rax, [rbp+var_40]
0x18007efc5  lea     r9, _GUID_8f7c48e9_e418_456f_9265_a922135b0d49; riid
0x18007efcc  mov     [rsp+80h+ppv], rax; ppv
0x18007efd1  lea     rcx, CLSID_DemuxRender; rclsid
0x18007efd8  lea     r8d, [rdx+1]; dwClsContext
0x18007efdc  call    cs:__imp_CoCreateInstance
0x18007efe3  nop     dword ptr [rax+rax+00h]
0x18007efe8  mov     edi, eax
0x18007efea  test    eax, eax
0x18007efec  jns     loc_18007F083
0x18007eff2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007eff9  test    rcx, rcx
0x18007effc  jnz     short loc_18007F045
0x18007effe  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18007f005  nop     dword ptr [rax+rax+00h]
0x18007f00a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18007f011  mov     rcx, rax
0x18007f014  test    rax, rax
0x18007f017  jz      short loc_18007F037
0x18007f019  mov     rax, [rax]
0x18007f01c  mov     edx, 7F0h
0x18007f021  mov     rax, [rax+8]
0x18007f025  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007f02a  test    eax, eax
0x18007f02c  jz      short loc_18007F037
0x18007f02e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007f035  jmp     short loc_18007F045
0x18007f037  lea     rcx, qword_1800EB130; this
0x18007f03e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18007f045  cmp     [rcx+8], r15b
0x18007f049  jz      short loc_18007F06C
0x18007f04b  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18007f050  cmp     [rax+7CCh], edi
0x18007f056  jz      short loc_18007F06C
0x18007f058  mov     r9d, edi; int
0x18007f05b  mov     r8d, 14A7h; int
0x18007f061  mov     rdx, r12; char *
0x18007f064  mov     rcx, rax; this
0x18007f067  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18007f06c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18007f073  jb      loc_18007F360
0x18007f079  mov     edx, 1E4h
0x18007f07e  jmp     loc_18007F342
0x18007f083  mov     r10, [rbp+var_40]
0x18007f087  xor     edx, edx
0x18007f089  mov     rcx, [rbp+var_30]
  ... truncated ...
```
