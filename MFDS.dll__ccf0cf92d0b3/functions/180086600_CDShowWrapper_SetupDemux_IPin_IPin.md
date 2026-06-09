# CDShowWrapper::SetupDemux(IPin * *,IPin * *)

- ea: `0x180086600`
- end: `0x180086e5d`
- name: `?SetupDemux@CDShowWrapper@@IEAAJPEAPEAUIPin@@0@Z`
- size: `2141`
- prototype: `__int64 __fastcall(CDShowWrapper *__hidden this, struct IPin **, struct IPin **)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180030060`

## callees

- `0x180002820`
- `0x18000b8c0`
- `0x1800140b0`
- `0x1800227e0`
- `0x180032988`
- `0x180032a50`
- `0x180035b14`
- `0x180051ce4`
- `0x180074160`
- `0x180074a06`
- `0x180086600`
- `0x1800c9010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180086713`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180086713`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180086735`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180086809`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800868ea`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18008699d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180086a5d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180086b13`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180086bd0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180086c80`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180086d34`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180086735`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180086809`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800868ea`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18008699d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180086a5d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180086b13`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180086bd0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180086c80`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180086d34`

## pseudocode

```c
__int64 __fastcall CDShowWrapper::SetupDemux(CDShowWrapper *this, struct IPin **a2, struct IPin **a3)
{
  struct CallStackContext *ThreadRelativeContext; // rdi
  int v7; // ebx
  __int128 v8; // xmm0
  HRESULT v9; // ebx
  CallStackTracing *v10; // rcx
  CallStackTracing *v11; // rax
  struct CallStackContext *v12; // rax
  __int64 v13; // rdx
  CallStackTracing *v14; // rcx
  CallStackTracing *v15; // rax
  struct CallStackContext *v16; // rax
  CallStackTracing *v17; // rcx
  CallStackTracing *v18; // rax
  struct CallStackContext *v19; // rax
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
  _BYTE v39[8]; // [rsp+30h] [rbp-A9h] BYREF
  LPVOID ppv; // [rsp+38h] [rbp-A1h] BYREF
  struct IPin *v41; // [rsp+40h] [rbp-99h] BYREF
  struct IPin *v42; // [rsp+48h] [rbp-91h] BYREF
  int v43; // [rsp+50h] [rbp-89h] BYREF
  void *v44; // [rsp+58h] [rbp-81h] BYREF
  __int64 v45; // [rsp+60h] [rbp-79h] BYREF
  __int64 v46; // [rsp+68h] [rbp-71h] BYREF
  __int64 v47; // [rsp+70h] [rbp-69h] BYREF
  __int64 v48; // [rsp+78h] [rbp-61h] BYREF
  _BYTE v49[16]; // [rsp+80h] [rbp-59h] BYREF
  _OWORD v50[6]; // [rsp+90h] [rbp-49h] BYREF

  ppv = 0;
  v48 = 0;
  v42 = 0;
  v47 = 0;
  v41 = 0;
  v46 = 0;
  v45 = 0;
  memset_0(v50, 0, 0x58u);
  v44 = 0;
  v50[0] = MEDIATYPE_MPEG2_SECTIONS;
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v39, "CDShowWrapper::SetupDemux", 5214);
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) && *((_QWORD *)this + 60) )
  {
    ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
    v7 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 60) + 296LL))(*((_QWORD *)this + 60));
    v8 = *(_OWORD *)(*(__int64 (__fastcall **)(_QWORD, _BYTE *))(**((_QWORD **)this + 60) + 280LL))(
                      *((_QWORD *)this + 60),
                      v49);
    *((_DWORD *)ThreadRelativeContext + 504) = v7;
    *((_OWORD *)ThreadRelativeContext + 125) = v8;
  }
  v9 = CoCreateInstance(&CLSID_MFMPEG2Demultiplexer, 0, 1u, &GUID_56a86895_0ad4_11ce_b03a_0020af0ba770, &ppv);
  if ( v9 >= 0 )
  {
    v9 = (**(__int64 (__fastcall ***)(LPVOID, GUID *, __int64 *))ppv)(
           ppv,
           &GUID_436eee9c_264f_4242_90e1_4e330c107512,
           &v48);
    if ( v9 >= 0 )
    {
      if ( (**(int (__fastcall ***)(LPVOID, GUID *, __int64 *))ppv)(
             ppv,
             &GUID_3eb1ddcf_2265_4caa_b0cc_35ac60774f6f,
             &v45) >= 0 )
        (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v45 + 24LL))(v45, 1);
      v9 = (*(__int64 (__fastcall **)(LPVOID, __int64 *))(*(_QWORD *)ppv + 80LL))(ppv, &v47);
      if ( v9 >= 0 )
      {
        if ( (*(unsigned int (__fastcall **)(__int64, __int64, struct IPin **, _QWORD))(*(_QWORD *)v47 + 24LL))(
               v47,
               1,
               &v42,
               0) )
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
          v9 = -2147418113;
          if ( *((_BYTE *)v20 + 8) )
          {
            v22 = CallStackTracing::GetThreadRelativeContext(v20);
            if ( *((_DWORD *)v22 + 499) != -2147418113 )
              CallStackContext::TraceFailure(v22, "CDShowWrapper::SetupDemux", 5238, -2147418113);
          }
          if ( g_wppLevels )
          {
            v13 = 473;
            goto LABEL_15;
          }
        }
        else
        {
          v9 = (*(__int64 (__fastcall **)(__int64, _OWORD *, const wchar_t *, struct IPin **))(*(_QWORD *)v48 + 24LL))(
                 v48,
                 v50,
                 L"PSI",
                 &v41);
          if ( v9 >= 0 )
          {
            v9 = ((__int64 (__fastcall *)(struct IPin *, GUID *, __int64 *))v41->lpVtbl->QueryInterface)(
                   v41,
                   &GUID_afb6c2a1_2c41_11d3_8a60_0000f81e0e4a,
                   &v46);
            if ( v9 >= 0 )
            {
              v43 = 0;
              v9 = (*(__int64 (__fastcall **)(__int64, __int64, int *, __int64))(*(_QWORD *)v46 + 24LL))(
                     v46,
                     1,
                     &v43,
                     2);
              if ( v9 >= 0 )
              {
                v9 = CGITPtr::Get(
                       (CDShowWrapper *)((char *)this + 48),
                       &GUID_56a868a9_0ad4_11ce_b03a_0020af0ba770,
                       &v44);
                if ( v9 >= 0 )
                {
                  v9 = (*(__int64 (__fastcall **)(void *, LPVOID, _QWORD))(*(_QWORD *)v44 + 24LL))(v44, ppv, 0);
                  if ( v9 >= 0 )
                  {
                    *a2 = v42;
                    *a3 = v41;
                    v42 = 0;
                    v41 = 0;
                    ComSmartPtr<IBaseFilter>::operator=((char *)this + 72, &ppv);
                    goto LABEL_107;
                  }
                  v35 = CallStackTracing::s_wpInstance;
                  if ( !CallStackTracing::s_wpInstance )
                  {
                    v36 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
                    CallStackTracing::s_wpInstance = v36;
                    if ( v36
                      && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v36 + 8LL))(v36, 2032) )
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
                      CallStackContext::TraceFailure(v37, "CDShowWrapper::SetupDemux", 5251, v9);
                  }
                  if ( g_wppLevels )
                  {
                    v13 = 478;
                    goto LABEL_15;
                  }
                }
                else
                {
                  v32 = CallStackTracing::s_wpInstance;
                  if ( !CallStackTracing::s_wpInstance )
                  {
                    v33 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
                    CallStackTracing::s_wpInstance = v33;
                    if ( v33
                      && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v33 + 8LL))(v33, 2032) )
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
                      CallStackContext::TraceFailure(v34, "CDShowWrapper::SetupDemux", 5250, v9);
                  }
                  if ( g_wppLevels )
                  {
                    v13 = 477;
                    goto LABEL_15;
                  }
                }
              }
              else
              {
                v29 = CallStackTracing::s_wpInstance;
                if ( !CallStackTracing::s_wpInstance )
                {
                  v30 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
                  CallStackTracing::s_wpInstance = v30;
                  if ( v30
                    && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v30 + 8LL))(v30, 2032) )
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
                    CallStackContext::TraceFailure(v31, "CDShowWrapper::SetupDemux", 5248, v9);
                }
                if ( g_wppLevels )
                {
                  v13 = 476;
                  goto LABEL_15;
                }
              }
            }
            else
            {
              v26 = CallStackTracing::s_wpInstance;
              if ( !CallStackTracing::s_wpInstance )
              {
                v27 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
                CallStackTracing::s_wpInstance = v27;
                if ( v27
                  && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v27 + 8LL))(v27, 2032) )
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
                  CallStackContext::TraceFailure(v28, "CDShowWrapper::SetupDemux", 5245, v9);
              }
              if ( g_wppLevels )
              {
                v13 = 475;
                goto LABEL_15;
              }
            }
          }
          else
          {
            v23 = CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v24 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
              CallStackTracing::s_wpInstance = v24;
              if ( v24
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v24 + 8LL))(v24, 2032) )
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
                CallStackContext::TraceFailure(v25, "CDShowWrapper::SetupDemux", 5243, v9);
            }
            if ( g_wppLevels )
            {
              v13 = 474;
              goto LABEL_15;
            }
          }
        }
      }
      else
      {
        v17 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v18 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
          CallStackTracing::s_wpInstance = v18;
          if ( v18 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v18 + 8LL))(v18, 2032) )
          {
            v17 = CallStackTracing::s_wpInstance;
          }
          else
          {
            v17 = (CallStackTracing *)&qword_1800EB130;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
          }
        }
        if ( *((_BYTE *)v17 + 8) )
        {
          v19 = CallStackTracing::GetThreadRelativeContext(v17);
          if ( *((_DWORD *)v19 + 499) != v9 )
            CallStackContext::TraceFailure(v19, "CDShowWrapper::SetupDemux", 5232, v9);
        }
        if ( g_wppLevels )
        {
          v13 = 472;
          goto LABEL_15;
        }
      }
    }
    else
    {
      v14 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v15 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
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
        if ( *((_DWORD *)v16 + 499) != v9 )
          CallStackContext::TraceFailure(v16, "CDShowWrapper::SetupDemux", 5215, v9);
      }
      if ( g_wppLevels )
      {
        v13 = 471;
        goto LABEL_15;
      }
    }
  }
  else
  {
    v10 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v11 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
      CallStackTracing::s_wpInstance = v11;
      if ( v11 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v11 + 8LL))(v11, 2032) )
      {
        v10 = CallStackTracing::s_wpInstance;
      }
      else
      {
        v10 = (CallStackTracing *)&qword_1800EB130;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
      }
    }
    if ( *((_BYTE *)v10 + 8) )
    {
      v12 = CallStackTracing::GetThreadRelativeContext(v10);
      if ( *((_DWORD *)v12 + 499) != v9 )
        CallStackContext::TraceFailure(v12, "CDShowWrapper::SetupDemux", 5214, v9);
    }
    if ( g_wppLevels )
    {
      v13 = 470;
LABEL_15:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v13, &WPP_8e8a43b2e5013e25304950bf1ec57b49_Traceguids, this, v9);
    }
  }
LABEL_107:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v39);
  ATL::CComPtrBase<IMediaSeeking>::~CComPtrBase<IMediaSeeking>(&v44);
  ATL::CComPtrBase<IMediaSeeking>::~CComPtrBase<IMediaSeeking>(&v45);
  ATL::CComPtrBase<IMediaSeeking>::~CComPtrBase<IMediaSeeking>(&v46);
  ATL::CComPtrBase<IMediaSeeking>::~CComPtrBase<IMediaSeeking>(&v41);
  ATL::CComPtrBase<IMediaSeeking>::~CComPtrBase<IMediaSeeking>(&v47);
  ATL::CComPtrBase<IMediaSeeking>::~CComPtrBase<IMediaSeeking>(&v42);
  ATL::CComPtrBase<IMediaSeeking>::~CComPtrBase<IMediaSeeking>(&v48);
  ATL::CComPtrBase<IMediaSeeking>::~CComPtrBase<IMediaSeeking>(&ppv);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180086600  mov     [rsp-8+arg_18], rbx
0x180086605  push    rbp
0x180086606  push    rsi
0x180086607  push    rdi
0x180086608  push    r12
0x18008660a  push    r13
0x18008660c  push    r14
0x18008660e  push    r15
0x180086610  lea     rbp, [rsp-27h]
0x180086615  sub     rsp, 100h
0x18008661c  mov     rax, cs:__security_cookie
0x180086623  xor     rax, rsp
0x180086626  mov     [rbp+57h+var_40], rax
0x18008662a  xor     r12d, r12d
0x18008662d  mov     r15, r8
0x180086630  mov     r14, rdx
0x180086633  mov     [rsp+130h+var_F8], r12
0x180086638  mov     rsi, rcx
0x18008663b  mov     [rbp+57h+var_B8], r12
0x18008663f  xor     edx, edx; Val
0x180086641  mov     [rsp+130h+var_E8], r12
0x180086646  lea     r8d, [r12+58h]; Size
0x18008664b  mov     [rbp+57h+var_C0], r12
0x18008664f  lea     rcx, [rbp+57h+var_A0]; void *
0x180086653  mov     [rsp+130h+var_F0], r12
0x180086658  mov     [rbp+57h+var_C8], r12
0x18008665c  mov     [rbp+57h+var_D0], r12
0x180086660  call    memset_0
0x180086665  movups  xmm0, xmmword ptr cs:MEDIATYPE_MPEG2_SECTIONS.Data1
0x18008666c  lea     r13, aCdshowwrapperS_2; "CDShowWrapper::SetupDemux"
0x180086673  mov     [rsp+130h+var_D8], r12
0x180086678  mov     r8d, 145Eh; int
0x18008667e  lea     rcx, [rsp+130h+var_100]; this
0x180086683  mov     rdx, r13; char *
0x180086686  movdqu  [rbp+57h+var_A0], xmm0
0x18008668b  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180086690  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180086697  cmp     [rcx+8], r12b
0x18008669b  jz      short loc_1800866F1
0x18008669d  cmp     [rsi+1E0h], r12
0x1800866a4  jz      short loc_1800866F1
0x1800866a6  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800866ab  mov     rcx, [rsi+1E0h]
0x1800866b2  mov     rdi, rax
0x1800866b5  mov     rdx, [rcx]
0x1800866b8  mov     rax, [rdx+128h]
0x1800866bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800866c4  mov     rcx, [rsi+1E0h]
0x1800866cb  mov     ebx, eax
0x1800866cd  mov     rdx, [rcx]
0x1800866d0  mov     rax, [rdx+118h]
0x1800866d7  lea     rdx, [rbp+57h+var_B0]
0x1800866db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800866e0  movups  xmm0, xmmword ptr [rax]
0x1800866e3  mov     [rdi+7E0h], ebx
0x1800866e9  movdqu  xmmword ptr [rdi+7D0h], xmm0
0x1800866f1  lea     rax, [rsp+130h+var_F8]
0x1800866f6  mov     edi, 1
0x1800866fb  mov     r8d, edi; dwClsContext
0x1800866fe  mov     [rsp+130h+ppv], rax; ppv
0x180086703  lea     r9, _GUID_56a86895_0ad4_11ce_b03a_0020af0ba770; riid
0x18008670a  xor     edx, edx; pUnkOuter
0x18008670c  lea     rcx, CLSID_MFMPEG2Demultiplexer; rclsid
0x180086713  call    cs:__imp_CoCreateInstance
0x18008671a  nop     dword ptr [rax+rax+00h]
0x18008671f  mov     ebx, eax
0x180086721  test    eax, eax
0x180086723  jns     loc_1800867D8
0x180086729  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180086730  test    rcx, rcx
0x180086733  jnz     short loc_18008677C
0x180086735  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18008673c  nop     dword ptr [rax+rax+00h]
0x180086741  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180086748  mov     rcx, rax
0x18008674b  test    rax, rax
0x18008674e  jz      short loc_18008676E
0x180086750  mov     rax, [rax]
0x180086753  mov     edx, 7F0h
0x180086758  mov     rax, [rax+8]
0x18008675c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180086761  test    eax, eax
0x180086763  jz      short loc_18008676E
0x180086765  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18008676c  jmp     short loc_18008677C
0x18008676e  lea     rcx, qword_1800EB130; this
0x180086775  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18008677c  cmp     [rcx+8], r12b
0x180086780  jz      short loc_1800867A3
0x180086782  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180086787  cmp     [rax+7CCh], ebx
0x18008678d  jz      short loc_1800867A3
0x18008678f  mov     r9d, ebx; int
0x180086792  mov     r8d, 145Eh; int
0x180086798  mov     rdx, r13; char *
0x18008679b  mov     rcx, rax; this
0x18008679e  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800867a3  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, dil; MFWppLevels g_wppLevels
0x1800867aa  jb      loc_180086DDD
0x1800867b0  mov     edx, 1D6h
0x1800867b5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800867bc  lea     r8, WPP_8e8a43b2e5013e25304950bf1ec57b49_Traceguids
0x1800867c3  mov     r9, rsi
0x1800867c6  mov     dword ptr [rsp+130h+ppv], ebx
0x1800867ca  mov     rcx, [rcx+10h]
0x1800867ce  call    WPP_SF_qD
0x1800867d3  jmp     loc_180086DDD
0x1800867d8  mov     rcx, [rsp+130h+var_F8]
0x1800867dd  lea     r8, [rbp+57h+var_B8]
0x1800867e1  lea     rdx, _GUID_436eee9c_264f_4242_90e1_4e330c107512
0x1800867e8  mov     rax, [rcx]
0x1800867eb  mov     rax, [rax]
0x1800867ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800867f3  mov     ebx, eax
0x1800867f5  test    eax, eax
0x1800867f7  jns     loc_18008688E
0x1800867fd  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180086804  test    rcx, rcx
0x180086807  jnz     short loc_180086850
0x180086809  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180086810  nop     dword ptr [rax+rax+00h]
0x180086815  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18008681c  mov     rcx, rax
0x18008681f  test    rax, rax
0x180086822  jz      short loc_180086842
0x180086824  mov     rax, [rax]
0x180086827  mov     edx, 7F0h
0x18008682c  mov     rax, [rax+8]
0x180086830  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180086835  test    eax, eax
0x180086837  jz      short loc_180086842
0x180086839  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180086840  jmp     short loc_180086850
0x180086842  lea     rcx, qword_1800EB130; this
0x180086849  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180086850  cmp     [rcx+8], r12b
0x180086854  jz      short loc_180086877
0x180086856  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18008685b  cmp     [rax+7CCh], ebx
0x180086861  jz      short loc_180086877
0x180086863  mov     r9d, ebx; int
0x180086866  mov     r8d, 145Fh; int
0x18008686c  mov     rdx, r13; char *
0x18008686f  mov     rcx, rax; this
0x180086872  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180086877  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, dil; MFWppLevels g_wppLevels
0x18008687e  jb      loc_180086DDD
0x180086884  mov     edx, 1D7h
0x180086889  jmp     loc_1800867B5
0x18008688e  mov     rcx, [rsp+130h+var_F8]
0x180086893  lea     r8, [rbp+57h+var_D0]
0x180086897  lea     rdx, _GUID_3eb1ddcf_2265_4caa_b0cc_35ac60774f6f
0x18008689e  mov     rax, [rcx]
0x1800868a1  mov     rax, [rax]
0x1800868a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800868a9  test    eax, eax
0x1800868ab  js      short loc_1800868BF
0x1800868ad  mov     rcx, [rbp+57h+var_D0]
0x1800868b1  mov     edx, edi
0x1800868b3  mov     rax, [rcx]
0x1800868b6  mov     rax, [rax+18h]
0x1800868ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800868bf  mov     rcx, [rsp+130h+var_F8]
0x1800868c4  lea     rdx, [rbp+57h+var_C0]
0x1800868c8  mov     rax, [rcx]
0x1800868cb  mov     rax, [rax+50h]
0x1800868cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800868d4  mov     ebx, eax
0x1800868d6  test    eax, eax
0x1800868d8  jns     loc_18008696F
0x1800868de  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800868e5  test    rcx, rcx
0x1800868e8  jnz     short loc_180086931
0x1800868ea  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800868f1  nop     dword ptr [rax+rax+00h]
0x1800868f6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800868fd  mov     rcx, rax
0x180086900  test    rax, rax
0x180086903  jz      short loc_180086923
0x180086905  mov     rax, [rax]
0x180086908  mov     edx, 7F0h
0x18008690d  mov     rax, [rax+8]
0x180086911  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180086916  test    eax, eax
0x180086918  jz      short loc_180086923
0x18008691a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180086921  jmp     short loc_180086931
0x180086923  lea     rcx, qword_1800EB130; this
0x18008692a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180086931  cmp     [rcx+8], r12b
0x180086935  jz      short loc_180086958
0x180086937  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18008693c  cmp     [rax+7CCh], ebx
0x180086942  jz      short loc_180086958
0x180086944  mov     r9d, ebx; int
0x180086947  mov     r8d, 1470h; int
0x18008694d  mov     rdx, r13; char *
0x180086950  mov     rcx, rax; this
0x180086953  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180086958  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, dil; MFWppLevels g_wppLevels
0x18008695f  jb      loc_180086DDD
0x180086965  mov     edx, 1D8h
0x18008696a  jmp     loc_1800867B5
0x18008696f  mov     rcx, [rbp+57h+var_C0]
0x180086973  lea     r8, [rsp+130h+var_E8]
0x180086978  xor     r9d, r9d
0x18008697b  mov     edx, edi
0x18008697d  mov     rax, [rcx]
0x180086980  mov     rax, [rax+18h]
0x180086984  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180086989  test    eax, eax
0x18008698b  jz      loc_180086A27
0x180086991  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180086998  test    rcx, rcx
0x18008699b  jnz     short loc_1800869E4
0x18008699d  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800869a4  nop     dword ptr [rax+rax+00h]
0x1800869a9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800869b0  mov     rcx, rax
0x1800869b3  test    rax, rax
0x1800869b6  jz      short loc_1800869D6
0x1800869b8  mov     rax, [rax]
0x1800869bb  mov     edx, 7F0h
0x1800869c0  mov     rax, [rax+8]
0x1800869c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800869c9  test    eax, eax
0x1800869cb  jz      short loc_1800869D6
0x1800869cd  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800869d4  jmp     short loc_1800869E4
0x1800869d6  lea     rcx, qword_1800EB130; this
0x1800869dd  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800869e4  mov     ebx, 8000FFFFh
0x1800869e9  cmp     [rcx+8], r12b
0x1800869ed  jz      short loc_180086A10
0x1800869ef  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800869f4  cmp     [rax+7CCh], ebx
0x1800869fa  jz      short loc_180086A10
0x1800869fc  mov     r9d, ebx; int
0x1800869ff  mov     r8d, 1476h; int
0x180086a05  mov     rdx, r13; char *
0x180086a08  mov     rcx, rax; this
0x180086a0b  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180086a10  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, dil; MFWppLevels g_wppLevels
0x180086a17  jb      loc_180086DDD
0x180086a1d  mov     edx, 1D9h
0x180086a22  jmp     loc_1800867B5
0x180086a27  mov     rcx, [rbp+57h+var_B8]
0x180086a2b  lea     r9, [rsp+130h+var_F0]
0x180086a30  lea     r8, aPsi; "PSI"
0x180086a37  lea     rdx, [rbp+57h+var_A0]
0x180086a3b  mov     rax, [rcx]
0x180086a3e  mov     rax, [rax+18h]
0x180086a42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180086a47  mov     ebx, eax
0x180086a49  test    eax, eax
0x180086a4b  jns     loc_180086AE2
0x180086a51  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180086a58  test    rcx, rcx
0x180086a5b  jnz     short loc_180086AA4
0x180086a5d  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180086a64  nop     dword ptr [rax+rax+00h]
0x180086a69  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180086a70  mov     rcx, rax
0x180086a73  test    rax, rax
0x180086a76  jz      short loc_180086A96
0x180086a78  mov     rax, [rax]
0x180086a7b  mov     edx, 7F0h
0x180086a80  mov     rax, [rax+8]
0x180086a84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180086a89  test    eax, eax
0x180086a8b  jz      short loc_180086A96
0x180086a8d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180086a94  jmp     short loc_180086AA4
0x180086a96  lea     rcx, qword_1800EB130; this
0x180086a9d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180086aa4  cmp     [rcx+8], r12b
0x180086aa8  jz      short loc_180086ACB
0x180086aaa  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180086aaf  cmp     [rax+7CCh], ebx
0x180086ab5  jz      short loc_180086ACB
0x180086ab7  mov     r9d, ebx; int
0x180086aba  mov     r8d, 147Bh; int
0x180086ac0  mov     rdx, r13; char *
0x180086ac3  mov     rcx, rax; this
0x180086ac6  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180086acb  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, dil; MFWppLevels g_wppLevels
0x180086ad2  jb      loc_180086DDD
0x180086ad8  mov     edx, 1DAh
0x180086add  jmp     loc_1800867B5
0x180086ae2  mov     rcx, [rsp+130h+var_F0]
0x180086ae7  lea     r8, [rbp+57h+var_C8]
0x180086aeb  lea     rdx, _GUID_afb6c2a1_2c41_11d3_8a60_0000f81e0e4a
0x180086af2  mov     rax, [rcx]
0x180086af5  mov     rax, [rax]
0x180086af8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180086afd  mov     ebx, eax
0x180086aff  test    eax, eax
0x180086b01  jns     loc_180086B98
0x180086b07  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180086b0e  test    rcx, rcx
  ... truncated ...
```
