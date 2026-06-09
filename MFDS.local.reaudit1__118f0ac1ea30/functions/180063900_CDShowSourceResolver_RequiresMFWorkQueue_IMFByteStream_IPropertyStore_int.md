# CDShowSourceResolver::RequiresMFWorkQueue(IMFByteStream *,IPropertyStore *,int *)

- ea: `0x180063900`
- end: `0x18006418f`
- name: `?RequiresMFWorkQueue@CDShowSourceResolver@@IEAAJPEAUIMFByteStream@@PEAUIPropertyStore@@PEAH@Z`
- size: `2191`
- prototype: `__int64 __fastcall(CDShowSourceResolver *__hidden this, struct IMFByteStream *, struct IPropertyStore *, int *)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180060c98`

## callees

- `0x180002820`
- `0x18000b8c0`
- `0x180010350`
- `0x1800140b0`
- `0x1800227e0`
- `0x18002329c`
- `0x180032a50`
- `0x180051ce4`
- `0x180063900`
- `0x1800c9010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180063984`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180063984`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800639a6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180063a6e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180063b27`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180063be0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180063c91`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180063d43`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180063df5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180063ea8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180063f5f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180064017`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800639a6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180063a6e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180063b27`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180063be0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180063c91`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180063d43`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180063df5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180063ea8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180063f5f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180064017`

## pseudocode

```c
__int64 __fastcall CDShowSourceResolver::RequiresMFWorkQueue(
        CDShowSourceResolver *this,
        struct IMFByteStream *a2,
        struct IPropertyStore *a3,
        int *a4)
{
  HRESULT v8; // ebx
  CallStackTracing *v9; // rcx
  CallStackTracing *v10; // rax
  struct CallStackContext *v11; // rax
  __int64 v12; // rdx
  CallStackTracing *v13; // rcx
  CallStackTracing *v14; // rax
  struct CallStackContext *v15; // rax
  CallStackTracing *v16; // rcx
  CallStackTracing *v17; // rax
  struct CallStackContext *v18; // rax
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
  struct CallStackContext *ThreadRelativeContext; // rax
  CallStackTracing *v37; // rcx
  CallStackTracing *v38; // rax
  struct CallStackContext *v39; // rax
  LPVOID ppv; // [rsp+30h] [rbp-40h] BYREF
  struct _AMMediaType *pv; // [rsp+38h] [rbp-38h] BYREF
  __int64 v43; // [rsp+40h] [rbp-30h] BYREF
  __int64 v44; // [rsp+48h] [rbp-28h] BYREF
  __int64 v45; // [rsp+50h] [rbp-20h] BYREF
  __int64 v46; // [rsp+58h] [rbp-18h] BYREF
  __int64 v47; // [rsp+60h] [rbp-10h] BYREF
  __int64 v48; // [rsp+68h] [rbp-8h] BYREF
  char v49; // [rsp+B0h] [rbp+40h] BYREF
  int v50; // [rsp+C8h] [rbp+58h] BYREF

  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)&v49,
    "CDShowSourceResolver::RequiresMFWorkQueue",
    428);
  ppv = 0;
  v48 = 0;
  v43 = 0;
  v47 = 0;
  v46 = 0;
  v45 = 0;
  v44 = 0;
  pv = 0;
  v50 = 0;
  *a4 = 0;
  v8 = CoCreateInstance(&CLSID_MFSourceFilter, 0, 1u, &GUID_00000000_0000_0000_c000_000000000046, &ppv);
  if ( v8 >= 0 )
  {
    v8 = (**(__int64 (__fastcall ***)(LPVOID, GUID *, __int64 *))ppv)(
           ppv,
           &GUID_56a86895_0ad4_11ce_b03a_0020af0ba770,
           &v48);
    if ( v8 >= 0 )
    {
      v8 = (**(__int64 (__fastcall ***)(LPVOID, GUID *, __int64 *))ppv)(
             ppv,
             &GUID_00f5e896_8813_44e3_8789_7e520e0de873,
             &v43);
      if ( v8 >= 0 )
      {
        v8 = (**(__int64 (__fastcall ***)(LPVOID, GUID *, __int64 *))ppv)(
               ppv,
               &GUID_7bb552d6_cbd8_42cc_bc1a_7b87a0a3a969,
               &v47);
        if ( v8 >= 0 )
        {
          v8 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v43 + 96LL))(v43, 0);
          if ( v8 >= 0 )
          {
            v8 = (*(__int64 (__fastcall **)(__int64, struct IPropertyStore *))(*(_QWORD *)v47 + 24LL))(v47, a3);
            if ( v8 >= 0 )
            {
              v8 = (*(__int64 (__fastcall **)(__int64, struct IMFByteStream *))(*(_QWORD *)v43 + 80LL))(v43, a2);
              if ( v8 >= 0 )
              {
                v8 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v48 + 80LL))(v48, &v46);
                if ( v8 >= 0 )
                {
                  if ( (*(unsigned int (__fastcall **)(__int64, __int64, __int64 *, _QWORD))(*(_QWORD *)v46 + 24LL))(
                         v46,
                         1,
                         &v45,
                         0) )
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
                    v8 = -2147418113;
                    if ( *((_BYTE *)v34 + 8) )
                    {
                      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(v34);
                      if ( *((_DWORD *)ThreadRelativeContext + 499) != -2147418113 )
                        CallStackContext::TraceFailure(
                          ThreadRelativeContext,
                          "CDShowSourceResolver::RequiresMFWorkQueue",
                          459,
                          -2147418113);
                    }
                    if ( g_wppLevels )
                    {
                      v12 = 54;
                      goto LABEL_12;
                    }
                  }
                  else
                  {
                    v8 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v45 + 96LL))(v45, &v44);
                    if ( v8 >= 0 )
                    {
                      if ( !(*(unsigned int (__fastcall **)(__int64, __int64, struct _AMMediaType **, int *))(*(_QWORD *)v44 + 24LL))(
                              v44,
                              1,
                              &pv,
                              &v50) )
                      {
                        if ( (unsigned __int8)_(&MEDIASUBTYPE_MPEG2_TRANSPORT, &pv->subtype)
                          || (unsigned __int8)_(&MEDIASUBTYPE_MPEG2_TRANSPORT_STRIDE, &pv->subtype) )
                        {
                          *a4 = 1;
                        }
                        DeleteMediaType(pv);
                      }
                      if ( (unsigned __int8)byte_1800EACCC >= 8u )
                        WPP_SF_qD(
                          *((_QWORD *)WPP_GLOBAL_Control + 22),
                          56,
                          WPP_4f2c49dc30393f4458000cee70747074_Traceguids,
                          this,
                          *a4);
                    }
                    else
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
                        if ( *((_DWORD *)v39 + 499) != v8 )
                          CallStackContext::TraceFailure(v39, "CDShowSourceResolver::RequiresMFWorkQueue", 464, v8);
                      }
                      if ( g_wppLevels )
                      {
                        v12 = 55;
                        goto LABEL_12;
                      }
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
                    if ( *((_DWORD *)v33 + 499) != v8 )
                      CallStackContext::TraceFailure(v33, "CDShowSourceResolver::RequiresMFWorkQueue", 454, v8);
                  }
                  if ( g_wppLevels )
                  {
                    v12 = 53;
                    goto LABEL_12;
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
                  if ( *((_DWORD *)v30 + 499) != v8 )
                    CallStackContext::TraceFailure(v30, "CDShowSourceResolver::RequiresMFWorkQueue", 452, v8);
                }
                if ( g_wppLevels )
                {
                  v12 = 52;
                  goto LABEL_12;
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
                if ( *((_DWORD *)v27 + 499) != v8 )
                  CallStackContext::TraceFailure(v27, "CDShowSourceResolver::RequiresMFWorkQueue", 451, v8);
              }
              if ( g_wppLevels )
              {
                v12 = 51;
                goto LABEL_12;
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
              if ( *((_DWORD *)v24 + 499) != v8 )
                CallStackContext::TraceFailure(v24, "CDShowSourceResolver::RequiresMFWorkQueue", 449, v8);
            }
            if ( g_wppLevels )
            {
              v12 = 50;
              goto LABEL_12;
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
            if ( *((_DWORD *)v21 + 499) != v8 )
              CallStackContext::TraceFailure(v21, "CDShowSourceResolver::RequiresMFWorkQueue", 446, v8);
          }
          if ( g_wppLevels )
          {
            v12 = 49;
            goto LABEL_12;
          }
        }
      }
      else
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
          if ( *((_DWORD *)v18 + 499) != v8 )
            CallStackContext::TraceFailure(v18, "CDShowSourceResolver::RequiresMFWorkQueue", 445, v8);
        }
        if ( g_wppLevels )
        {
          v12 = 48;
          goto LABEL_12;
        }
      }
    }
    else
    {
      v13 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v14 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
        CallStackTracing::s_wpInstance = v14;
        if ( v14 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v14 + 8LL))(v14, 2032) )
        {
          v13 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v13 = (CallStackTracing *)&qword_1800EB130;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
        }
      }
      if ( *((_BYTE *)v13 + 8) )
      {
        v15 = CallStackTracing::GetThreadRelativeContext(v13);
        if ( *((_DWORD *)v15 + 499) != v8 )
          CallStackContext::TraceFailure(v15, "CDShowSourceResolver::RequiresMFWorkQueue", 444, v8);
      }
      if ( g_wppLevels )
      {
        v12 = 47;
        goto LABEL_12;
      }
    }
  }
  else
  {
    v9 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v10 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
      CallStackTracing::s_wpInstance = v10;
      if ( v10 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v10 + 8LL))(v10, 2032) )
      {
        v9 = CallStackTracing::s_wpInstance;
      }
      else
      {
        v9 = (CallStackTracing *)&qword_1800EB130;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
      }
    }
    if ( *((_BYTE *)v9 + 8) )
    {
      v11 = CallStackTracing::GetThreadRelativeContext(v9);
      if ( *((_DWORD *)v11 + 499) != v8 )
        CallStackContext::TraceFailure(v11, "CDShowSourceResolver::RequiresMFWorkQueue", 443, v8);
    }
    if ( g_wppLevels )
    {
      v12 = 46;
LABEL_12:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v12, WPP_4f2c49dc30393f4458000cee70747074_Traceguids, this, v8);
    }
  }
  ATL::CComPtrBase<IMediaSeeking>::~CComPtrBase<IMediaSeeking>(&v44);
  ATL::CComPtrBase<IMediaSeeking>::~CComPtrBase<IMediaSeeking>(&v45);
  ATL::CComPtrBase<IMediaSeeking>::~CComPtrBase<IMediaSeeking>(&v46);
  ATL::CComPtrBase<IMediaSeeking>::~CComPtrBase<IMediaSeeking>(&v47);
  ATL::CComPtrBase<IMediaSeeking>::~CComPtrBase<IMediaSeeking>(&v43);
  ATL::CComPtrBase<IMediaSeeking>::~CComPtrBase<IMediaSeeking>(&v48);
  ATL::CComPtrBase<IMediaSeeking>::~CComPtrBase<IMediaSeeking>(&ppv);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v49);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180063900  mov     [rsp-38h+arg_8], rbx
0x180063905  push    rbp
0x180063906  push    rsi
0x180063907  push    rdi
0x180063908  push    r12
0x18006390a  push    r13
0x18006390c  push    r14
0x18006390e  push    r15
0x180063910  mov     rbp, rsp
0x180063913  sub     rsp, 70h
0x180063917  mov     r14, r8
0x18006391a  mov     r15, rdx
0x18006391d  mov     rdi, rcx
0x180063920  lea     rdx, aCdshowsourcere; "CDShowSourceResolver::RequiresMFWorkQue"...
0x180063927  mov     r8d, 1ACh; int
0x18006392d  lea     rcx, [rbp+arg_0]; this
0x180063931  mov     rsi, r9
0x180063934  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180063939  xor     r12d, r12d
0x18006393c  lea     rax, [rbp+var_40]
0x180063940  lea     r9, _GUID_00000000_0000_0000_c000_000000000046; riid
0x180063947  mov     [rbp+var_40], r12
0x18006394b  xor     edx, edx; pUnkOuter
0x18006394d  mov     [rbp+var_8], r12
0x180063951  lea     rcx, CLSID_MFSourceFilter; rclsid
0x180063958  mov     [rbp+var_30], r12
0x18006395c  lea     r13d, [r12+1]
0x180063961  mov     [rbp+var_10], r12
0x180063965  mov     r8d, r13d; dwClsContext
0x180063968  mov     [rbp+var_18], r12
0x18006396c  mov     [rbp+var_20], r12
0x180063970  mov     [rbp+var_28], r12
0x180063974  mov     [rbp+pv], r12
0x180063978  mov     [rbp+arg_18], r12d
0x18006397c  mov     [rsi], r12d
0x18006397f  mov     [rsp+70h+ppv], rax; ppv
0x180063984  call    cs:__imp_CoCreateInstance
0x18006398b  nop     dword ptr [rax+rax+00h]
0x180063990  mov     ebx, eax
0x180063992  test    eax, eax
0x180063994  jns     loc_180063A3E
0x18006399a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800639a1  test    rcx, rcx
0x1800639a4  jnz     short loc_1800639ED
0x1800639a6  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800639ad  nop     dword ptr [rax+rax+00h]
0x1800639b2  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800639b9  mov     rcx, rax
0x1800639bc  test    rax, rax
0x1800639bf  jz      short loc_1800639DF
0x1800639c1  mov     rax, [rax]
0x1800639c4  mov     edx, 7F0h
0x1800639c9  mov     rax, [rax+8]
0x1800639cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800639d2  test    eax, eax
0x1800639d4  jz      short loc_1800639DF
0x1800639d6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800639dd  jmp     short loc_1800639ED
0x1800639df  lea     rcx, qword_1800EB130; this
0x1800639e6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800639ed  cmp     [rcx+8], r12b
0x1800639f1  jz      short loc_180063A18
0x1800639f3  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800639f8  cmp     [rax+7CCh], ebx
0x1800639fe  jz      short loc_180063A18
0x180063a00  mov     r9d, ebx; int
0x180063a03  lea     rdx, aCdshowsourcere; "CDShowSourceResolver::RequiresMFWorkQue"...
0x180063a0a  mov     r8d, 1BBh; int
0x180063a10  mov     rcx, rax; this
0x180063a13  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180063a18  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r13b; MFWppLevels g_wppLevels
0x180063a1f  jb      loc_18006412C
0x180063a25  mov     edx, 2Eh ; '.'
0x180063a2a  mov     rcx, cs:WPP_GLOBAL_Control
0x180063a31  mov     dword ptr [rsp+70h+ppv], ebx
0x180063a35  mov     rcx, [rcx+10h]
0x180063a39  jmp     loc_18006411D
0x180063a3e  mov     rcx, [rbp+var_40]
0x180063a42  lea     r8, [rbp+var_8]
0x180063a46  lea     rdx, _GUID_56a86895_0ad4_11ce_b03a_0020af0ba770
0x180063a4d  mov     rax, [rcx]
0x180063a50  mov     rax, [rax]
0x180063a53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063a58  mov     ebx, eax
0x180063a5a  test    eax, eax
0x180063a5c  jns     loc_180063AF7
0x180063a62  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180063a69  test    rcx, rcx
0x180063a6c  jnz     short loc_180063AB5
0x180063a6e  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180063a75  nop     dword ptr [rax+rax+00h]
0x180063a7a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180063a81  mov     rcx, rax
0x180063a84  test    rax, rax
0x180063a87  jz      short loc_180063AA7
0x180063a89  mov     rax, [rax]
0x180063a8c  mov     edx, 7F0h
0x180063a91  mov     rax, [rax+8]
0x180063a95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063a9a  test    eax, eax
0x180063a9c  jz      short loc_180063AA7
0x180063a9e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180063aa5  jmp     short loc_180063AB5
0x180063aa7  lea     rcx, qword_1800EB130; this
0x180063aae  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180063ab5  cmp     [rcx+8], r12b
0x180063ab9  jz      short loc_180063AE0
0x180063abb  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180063ac0  cmp     [rax+7CCh], ebx
0x180063ac6  jz      short loc_180063AE0
0x180063ac8  mov     r9d, ebx; int
0x180063acb  lea     rdx, aCdshowsourcere; "CDShowSourceResolver::RequiresMFWorkQue"...
0x180063ad2  mov     r8d, 1BCh; int
0x180063ad8  mov     rcx, rax; this
0x180063adb  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180063ae0  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r13b; MFWppLevels g_wppLevels
0x180063ae7  jb      loc_18006412C
0x180063aed  mov     edx, 2Fh ; '/'
0x180063af2  jmp     loc_180063A2A
0x180063af7  mov     rcx, [rbp+var_40]
0x180063afb  lea     r8, [rbp+var_30]
0x180063aff  lea     rdx, _GUID_00f5e896_8813_44e3_8789_7e520e0de873
0x180063b06  mov     rax, [rcx]
0x180063b09  mov     rax, [rax]
0x180063b0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063b11  mov     ebx, eax
0x180063b13  test    eax, eax
0x180063b15  jns     loc_180063BB0
0x180063b1b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180063b22  test    rcx, rcx
0x180063b25  jnz     short loc_180063B6E
0x180063b27  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180063b2e  nop     dword ptr [rax+rax+00h]
0x180063b33  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180063b3a  mov     rcx, rax
0x180063b3d  test    rax, rax
0x180063b40  jz      short loc_180063B60
0x180063b42  mov     rax, [rax]
0x180063b45  mov     edx, 7F0h
0x180063b4a  mov     rax, [rax+8]
0x180063b4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063b53  test    eax, eax
0x180063b55  jz      short loc_180063B60
0x180063b57  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180063b5e  jmp     short loc_180063B6E
0x180063b60  lea     rcx, qword_1800EB130; this
0x180063b67  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180063b6e  cmp     [rcx+8], r12b
0x180063b72  jz      short loc_180063B99
0x180063b74  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180063b79  cmp     [rax+7CCh], ebx
0x180063b7f  jz      short loc_180063B99
0x180063b81  mov     r9d, ebx; int
0x180063b84  lea     rdx, aCdshowsourcere; "CDShowSourceResolver::RequiresMFWorkQue"...
0x180063b8b  mov     r8d, 1BDh; int
0x180063b91  mov     rcx, rax; this
0x180063b94  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180063b99  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r13b; MFWppLevels g_wppLevels
0x180063ba0  jb      loc_18006412C
0x180063ba6  mov     edx, 30h ; '0'
0x180063bab  jmp     loc_180063A2A
0x180063bb0  mov     rcx, [rbp+var_40]
0x180063bb4  lea     r8, [rbp+var_10]
0x180063bb8  lea     rdx, _GUID_7bb552d6_cbd8_42cc_bc1a_7b87a0a3a969
0x180063bbf  mov     rax, [rcx]
0x180063bc2  mov     rax, [rax]
0x180063bc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063bca  mov     ebx, eax
0x180063bcc  test    eax, eax
0x180063bce  jns     loc_180063C69
0x180063bd4  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180063bdb  test    rcx, rcx
0x180063bde  jnz     short loc_180063C27
0x180063be0  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180063be7  nop     dword ptr [rax+rax+00h]
0x180063bec  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180063bf3  mov     rcx, rax
0x180063bf6  test    rax, rax
0x180063bf9  jz      short loc_180063C19
0x180063bfb  mov     rax, [rax]
0x180063bfe  mov     edx, 7F0h
0x180063c03  mov     rax, [rax+8]
0x180063c07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063c0c  test    eax, eax
0x180063c0e  jz      short loc_180063C19
0x180063c10  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180063c17  jmp     short loc_180063C27
0x180063c19  lea     rcx, qword_1800EB130; this
0x180063c20  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180063c27  cmp     [rcx+8], r12b
0x180063c2b  jz      short loc_180063C52
0x180063c2d  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180063c32  cmp     [rax+7CCh], ebx
0x180063c38  jz      short loc_180063C52
0x180063c3a  mov     r9d, ebx; int
0x180063c3d  lea     rdx, aCdshowsourcere; "CDShowSourceResolver::RequiresMFWorkQue"...
0x180063c44  mov     r8d, 1BEh; int
0x180063c4a  mov     rcx, rax; this
0x180063c4d  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180063c52  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r13b; MFWppLevels g_wppLevels
0x180063c59  jb      loc_18006412C
0x180063c5f  mov     edx, 31h ; '1'
0x180063c64  jmp     loc_180063A2A
0x180063c69  mov     rcx, [rbp+var_30]
0x180063c6d  xor     edx, edx
0x180063c6f  mov     rax, [rcx]
0x180063c72  mov     rax, [rax+60h]
0x180063c76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063c7b  mov     ebx, eax
0x180063c7d  test    eax, eax
0x180063c7f  jns     loc_180063D1A
0x180063c85  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180063c8c  test    rcx, rcx
0x180063c8f  jnz     short loc_180063CD8
0x180063c91  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180063c98  nop     dword ptr [rax+rax+00h]
0x180063c9d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180063ca4  mov     rcx, rax
0x180063ca7  test    rax, rax
0x180063caa  jz      short loc_180063CCA
0x180063cac  mov     rax, [rax]
0x180063caf  mov     edx, 7F0h
0x180063cb4  mov     rax, [rax+8]
0x180063cb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063cbd  test    eax, eax
0x180063cbf  jz      short loc_180063CCA
0x180063cc1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180063cc8  jmp     short loc_180063CD8
0x180063cca  lea     rcx, qword_1800EB130; this
0x180063cd1  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180063cd8  cmp     [rcx+8], r12b
0x180063cdc  jz      short loc_180063D03
0x180063cde  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180063ce3  cmp     [rax+7CCh], ebx
0x180063ce9  jz      short loc_180063D03
0x180063ceb  mov     r9d, ebx; int
0x180063cee  lea     rdx, aCdshowsourcere; "CDShowSourceResolver::RequiresMFWorkQue"...
0x180063cf5  mov     r8d, 1C1h; int
0x180063cfb  mov     rcx, rax; this
0x180063cfe  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180063d03  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r13b; MFWppLevels g_wppLevels
0x180063d0a  jb      loc_18006412C
0x180063d10  mov     edx, 32h ; '2'
0x180063d15  jmp     loc_180063A2A
0x180063d1a  mov     rcx, [rbp+var_10]
0x180063d1e  mov     rdx, r14
0x180063d21  mov     rax, [rcx]
0x180063d24  mov     rax, [rax+18h]
0x180063d28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063d2d  mov     ebx, eax
0x180063d2f  test    eax, eax
0x180063d31  jns     loc_180063DCC
0x180063d37  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180063d3e  test    rcx, rcx
0x180063d41  jnz     short loc_180063D8A
0x180063d43  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180063d4a  nop     dword ptr [rax+rax+00h]
0x180063d4f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180063d56  mov     rcx, rax
0x180063d59  test    rax, rax
0x180063d5c  jz      short loc_180063D7C
0x180063d5e  mov     rax, [rax]
0x180063d61  mov     edx, 7F0h
0x180063d66  mov     rax, [rax+8]
0x180063d6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063d6f  test    eax, eax
0x180063d71  jz      short loc_180063D7C
0x180063d73  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180063d7a  jmp     short loc_180063D8A
0x180063d7c  lea     rcx, qword_1800EB130; this
0x180063d83  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180063d8a  cmp     [rcx+8], r12b
0x180063d8e  jz      short loc_180063DB5
0x180063d90  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180063d95  cmp     [rax+7CCh], ebx
0x180063d9b  jz      short loc_180063DB5
0x180063d9d  mov     r9d, ebx; int
0x180063da0  lea     rdx, aCdshowsourcere; "CDShowSourceResolver::RequiresMFWorkQue"...
0x180063da7  mov     r8d, 1C3h; int
0x180063dad  mov     rcx, rax; this
0x180063db0  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180063db5  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r13b; MFWppLevels g_wppLevels
0x180063dbc  jb      loc_18006412C
0x180063dc2  mov     edx, 33h ; '3'
0x180063dc7  jmp     loc_180063A2A
0x180063dcc  mov     rcx, [rbp+var_30]
0x180063dd0  mov     rdx, r15
0x180063dd3  mov     rax, [rcx]
0x180063dd6  mov     rax, [rax+50h]
0x180063dda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063ddf  mov     ebx, eax
0x180063de1  test    eax, eax
0x180063de3  jns     loc_180063E7E
0x180063de9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180063df0  test    rcx, rcx
0x180063df3  jnz     short loc_180063E3C
0x180063df5  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180063dfc  nop     dword ptr [rax+rax+00h]
0x180063e01  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180063e08  mov     rcx, rax
  ... truncated ...
```
