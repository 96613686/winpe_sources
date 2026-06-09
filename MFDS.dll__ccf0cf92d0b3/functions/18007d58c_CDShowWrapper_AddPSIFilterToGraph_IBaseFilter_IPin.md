# CDShowWrapper::AddPSIFilterToGraph(IBaseFilter * *,IPin * *)

- ea: `0x18007d58c`
- end: `0x18007dc02`
- name: `?AddPSIFilterToGraph@CDShowWrapper@@IEAAJPEAPEAUIBaseFilter@@PEAPEAUIPin@@@Z`
- size: `1654`
- prototype: `__int64 __fastcall(CDShowWrapper *__hidden this, struct IBaseFilter **, struct IPin **)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18007eb88`

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
- `0x1800c9010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18007d745`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18007d745`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007d67c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007d767`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007d81c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007d8ea`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007d999`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007da4b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007db02`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007d67c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007d767`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007d81c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007d8ea`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007d999`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007da4b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007db02`

## pseudocode

```c
__int64 __fastcall CDShowWrapper::AddPSIFilterToGraph(CDShowWrapper *this, struct IBaseFilter **a2, struct IPin **a3)
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
  _BYTE v33[8]; // [rsp+30h] [rbp-50h] BYREF
  struct IBaseFilter *v34; // [rsp+38h] [rbp-48h] BYREF
  struct IPin *v35; // [rsp+40h] [rbp-40h] BYREF
  LPVOID ppv; // [rsp+48h] [rbp-38h] BYREF
  void *v37; // [rsp+50h] [rbp-30h] BYREF
  __int64 v38; // [rsp+58h] [rbp-28h] BYREF
  __int64 v39; // [rsp+60h] [rbp-20h] BYREF
  _BYTE v40[16]; // [rsp+68h] [rbp-18h] BYREF

  ppv = 0;
  v34 = 0;
  v35 = 0;
  v39 = 0;
  v38 = 0;
  v37 = 0;
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v33, "CDShowWrapper::AddPSIFilterToGraph", 5314);
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) && *((_QWORD *)this + 60) )
  {
    ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
    v7 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 60) + 296LL))(*((_QWORD *)this + 60));
    v8 = *(_OWORD *)(*(__int64 (__fastcall **)(_QWORD, _BYTE *))(**((_QWORD **)this + 60) + 280LL))(
                      *((_QWORD *)this + 60),
                      v40);
    *((_DWORD *)ThreadRelativeContext + 504) = v7;
    *((_OWORD *)ThreadRelativeContext + 125) = v8;
  }
  v9 = CGITPtr::Get((CDShowWrapper *)((char *)this + 48), &GUID_56a868a9_0ad4_11ce_b03a_0020af0ba770, &v37);
  if ( v9 >= 0 )
  {
    v9 = CoCreateInstance(&CLSID_PsiParserFilter, 0, 1u, &GUID_00000000_0000_0000_c000_000000000046, &ppv);
    if ( v9 >= 0 )
    {
      v9 = (**(__int64 (__fastcall ***)(LPVOID, GUID *, __int64 *))ppv)(
             ppv,
             &GUID_f6ea8518_63e9_4f2e_82bf_90057fc680d6,
             &v38);
      if ( v9 >= 0 )
      {
        (*(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v38 + 24LL))(v38, 32868, 32869);
        v9 = (**(__int64 (__fastcall ***)(LPVOID, GUID *, struct IBaseFilter **))ppv)(
               ppv,
               &GUID_56a86895_0ad4_11ce_b03a_0020af0ba770,
               &v34);
        if ( v9 >= 0 )
        {
          v9 = ((__int64 (__fastcall *)(struct IBaseFilter *, __int64 *))v34->lpVtbl->EnumPins)(v34, &v39);
          if ( v9 >= 0 )
          {
            if ( (*(unsigned int (__fastcall **)(__int64, __int64, struct IPin **, _QWORD))(*(_QWORD *)v39 + 24LL))(
                   v39,
                   1,
                   &v35,
                   0) )
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
              v9 = -2147418113;
              if ( *((_BYTE *)v26 + 8) )
              {
                v28 = CallStackTracing::GetThreadRelativeContext(v26);
                if ( *((_DWORD *)v28 + 499) != -2147418113 )
                  CallStackContext::TraceFailure(v28, "CDShowWrapper::AddPSIFilterToGraph", 5328, -2147418113);
              }
              if ( g_wppLevels )
              {
                v13 = 494;
                goto LABEL_15;
              }
            }
            else
            {
              v9 = (*(__int64 (__fastcall **)(void *, struct IBaseFilter *, _QWORD))(*(_QWORD *)v37 + 24LL))(
                     v37,
                     v34,
                     0);
              if ( v9 >= 0 )
              {
                *a2 = v34;
                *a3 = v35;
                v34 = 0;
                v35 = 0;
                goto LABEL_83;
              }
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
                  CallStackContext::TraceFailure(v31, "CDShowWrapper::AddPSIFilterToGraph", 5330, v9);
              }
              if ( g_wppLevels )
              {
                v13 = 495;
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
                CallStackContext::TraceFailure(v25, "CDShowWrapper::AddPSIFilterToGraph", 5322, v9);
            }
            if ( g_wppLevels )
            {
              v13 = 493;
              goto LABEL_15;
            }
          }
        }
        else
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
              CallStackContext::TraceFailure(v22, "CDShowWrapper::AddPSIFilterToGraph", 5320, v9);
          }
          if ( g_wppLevels )
          {
            v13 = 492;
            goto LABEL_15;
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
            CallStackContext::TraceFailure(v19, "CDShowWrapper::AddPSIFilterToGraph", 5318, v9);
        }
        if ( g_wppLevels )
        {
          v13 = 491;
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
          CallStackContext::TraceFailure(v16, "CDShowWrapper::AddPSIFilterToGraph", 5316, v9);
      }
      if ( g_wppLevels )
      {
        v13 = 490;
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
        CallStackContext::TraceFailure(v12, "CDShowWrapper::AddPSIFilterToGraph", 5314, v9);
    }
    if ( g_wppLevels )
    {
      v13 = 489;
LABEL_15:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v13, &WPP_8e8a43b2e5013e25304950bf1ec57b49_Traceguids, this, v9);
    }
  }
LABEL_83:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v33);
  ATL::CComPtrBase<IMediaSeeking>::~CComPtrBase<IMediaSeeking>(&v37);
  ATL::CComPtrBase<IMediaSeeking>::~CComPtrBase<IMediaSeeking>(&v38);
  ATL::CComPtrBase<IMediaSeeking>::~CComPtrBase<IMediaSeeking>(&v39);
  ATL::CComPtrBase<IMediaSeeking>::~CComPtrBase<IMediaSeeking>(&v35);
  ATL::CComPtrBase<IMediaSeeking>::~CComPtrBase<IMediaSeeking>(&v34);
  ATL::CComPtrBase<IMediaSeeking>::~CComPtrBase<IMediaSeeking>(&ppv);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18007d58c  mov     [rsp-38h+arg_18], rbx
0x18007d591  push    rbp
0x18007d592  push    rsi
0x18007d593  push    rdi
0x18007d594  push    r12
0x18007d596  push    r13
0x18007d598  push    r14
0x18007d59a  push    r15
0x18007d59c  mov     rbp, rsp
0x18007d59f  sub     rsp, 80h
0x18007d5a6  mov     rax, cs:__security_cookie
0x18007d5ad  xor     rax, rsp
0x18007d5b0  mov     [rbp+var_8], rax
0x18007d5b4  xor     r12d, r12d
0x18007d5b7  lea     r13, aCdshowwrapperA
0x18007d5be  mov     r15, r8
0x18007d5c1  mov     [rbp+var_38], r12
0x18007d5c5  mov     r14, rdx
0x18007d5c8  mov     [rbp+var_48], r12
0x18007d5cc  mov     rsi, rcx
0x18007d5cf  mov     [rbp+var_40], r12
0x18007d5d3  mov     rdx, r13; char *
0x18007d5d6  mov     [rbp+var_20], r12
0x18007d5da  mov     r8d, 14C2h; int
0x18007d5e0  mov     [rbp+var_28], r12
0x18007d5e4  lea     rcx, [rbp+var_50]; this
0x18007d5e8  mov     [rbp+var_30], r12
0x18007d5ec  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z
0x18007d5f1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18007d5f8  cmp     [rcx+8], r12b
0x18007d5fc  jz      short loc_18007D652
0x18007d5fe  cmp     [rsi+1E0h], r12
0x18007d605  jz      short loc_18007D652
0x18007d607  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ
0x18007d60c  mov     rcx, [rsi+1E0h]
0x18007d613  mov     rdi, rax
0x18007d616  mov     rdx, [rcx]
0x18007d619  mov     rax, [rdx+128h]
0x18007d620  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007d625  mov     rcx, [rsi+1E0h]
0x18007d62c  mov     ebx, eax
0x18007d62e  mov     rdx, [rcx]
0x18007d631  mov     rax, [rdx+118h]
0x18007d638  lea     rdx, [rbp+var_18]
0x18007d63c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007d641  movups  xmm0, xmmword ptr [rax]
0x18007d644  mov     [rdi+7E0h], ebx
0x18007d64a  movdqu  xmmword ptr [rdi+7D0h], xmm0
0x18007d652  lea     rcx, [rsi+30h]; this
0x18007d656  lea     r8, [rbp+var_30]; void **
0x18007d65a  lea     rdx, _GUID_56a868a9_0ad4_11ce_b03a_0020af0ba770; struct _GUID *
0x18007d661  call    ?Get@CGITPtr@@QEAAJAEBU_GUID@@PEAPEAX@Z
0x18007d666  mov     ebx, eax
0x18007d668  test    eax, eax
0x18007d66a  jns     loc_18007D724
0x18007d670  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA
0x18007d677  test    rcx, rcx
0x18007d67a  jnz     short loc_18007D6C3
0x18007d67c  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18007d683  nop     dword ptr [rax+rax+00h]
0x18007d688  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax
0x18007d68f  mov     rcx, rax
0x18007d692  test    rax, rax
0x18007d695  jz      short loc_18007D6B5
0x18007d697  mov     rax, [rax]
0x18007d69a  mov     edx, 7F0h
0x18007d69f  mov     rax, [rax+8]
0x18007d6a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007d6a8  test    eax, eax
0x18007d6aa  jz      short loc_18007D6B5
0x18007d6ac  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA
0x18007d6b3  jmp     short loc_18007D6C3
0x18007d6b5  lea     rcx, qword_1800EB130; this
0x18007d6bc  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx
0x18007d6c3  cmp     [rcx+8], r12b
0x18007d6c7  jz      short loc_18007D6EA
0x18007d6c9  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ
0x18007d6ce  cmp     [rax+7CCh], ebx
0x18007d6d4  jz      short loc_18007D6EA
0x18007d6d6  mov     r9d, ebx; int
0x18007d6d9  mov     r8d, 14C2h; int
0x18007d6df  mov     rdx, r13; char *
0x18007d6e2  mov     rcx, rax; this
0x18007d6e5  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z
0x18007d6ea  mov     edi, 1
0x18007d6ef  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, dil
0x18007d6f6  jb      loc_18007DB99
0x18007d6fc  mov     edx, 1E9h
0x18007d701  mov     rcx, cs:WPP_GLOBAL_Control
0x18007d708  lea     r8, WPP_8e8a43b2e5013e25304950bf1ec57b49_Traceguids
0x18007d70f  mov     r9, rsi
0x18007d712  mov     dword ptr [rsp+80h+ppv], ebx
0x18007d716  mov     rcx, [rcx+10h]
0x18007d71a  call    WPP_SF_qD
0x18007d71f  jmp     loc_18007DB99
0x18007d724  lea     rax, [rbp+var_38]
0x18007d728  mov     edi, 1
0x18007d72d  mov     r8d, edi; dwClsContext
0x18007d730  mov     [rsp+80h+ppv], rax; ppv
0x18007d735  lea     r9, _GUID_00000000_0000_0000_c000_000000000046; riid
0x18007d73c  xor     edx, edx; pUnkOuter
0x18007d73e  lea     rcx, CLSID_PsiParserFilter; rclsid
0x18007d745  call    cs:__imp_CoCreateInstance
0x18007d74c  nop     dword ptr [rax+rax+00h]
0x18007d751  mov     ebx, eax
0x18007d753  test    eax, eax
0x18007d755  jns     loc_18007D7EC
0x18007d75b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA
0x18007d762  test    rcx, rcx
0x18007d765  jnz     short loc_18007D7AE
0x18007d767  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18007d76e  nop     dword ptr [rax+rax+00h]
0x18007d773  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax
0x18007d77a  mov     rcx, rax
0x18007d77d  test    rax, rax
0x18007d780  jz      short loc_18007D7A0
0x18007d782  mov     rax, [rax]
0x18007d785  mov     edx, 7F0h
0x18007d78a  mov     rax, [rax+8]
0x18007d78e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007d793  test    eax, eax
0x18007d795  jz      short loc_18007D7A0
0x18007d797  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA
0x18007d79e  jmp     short loc_18007D7AE
0x18007d7a0  lea     rcx, qword_1800EB130; this
0x18007d7a7  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx
0x18007d7ae  cmp     [rcx+8], r12b
0x18007d7b2  jz      short loc_18007D7D5
0x18007d7b4  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ
0x18007d7b9  cmp     [rax+7CCh], ebx
0x18007d7bf  jz      short loc_18007D7D5
0x18007d7c1  mov     r9d, ebx; int
0x18007d7c4  mov     r8d, 14C4h; int
0x18007d7ca  mov     rdx, r13; char *
0x18007d7cd  mov     rcx, rax; this
0x18007d7d0  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z
0x18007d7d5  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, dil
0x18007d7dc  jb      loc_18007DB99
0x18007d7e2  mov     edx, 1EAh
0x18007d7e7  jmp     loc_18007D701
0x18007d7ec  mov     rcx, [rbp+var_38]
0x18007d7f0  lea     r8, [rbp+var_28]
0x18007d7f4  lea     rdx, _GUID_f6ea8518_63e9_4f2e_82bf_90057fc680d6
0x18007d7fb  mov     rax, [rcx]
0x18007d7fe  mov     rax, [rax]
0x18007d801  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007d806  mov     ebx, eax
0x18007d808  test    eax, eax
0x18007d80a  jns     loc_18007D8A1
0x18007d810  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA
0x18007d817  test    rcx, rcx
0x18007d81a  jnz     short loc_18007D863
0x18007d81c  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18007d823  nop     dword ptr [rax+rax+00h]
0x18007d828  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax
0x18007d82f  mov     rcx, rax
0x18007d832  test    rax, rax
0x18007d835  jz      short loc_18007D855
0x18007d837  mov     rax, [rax]
0x18007d83a  mov     edx, 7F0h
0x18007d83f  mov     rax, [rax+8]
0x18007d843  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007d848  test    eax, eax
0x18007d84a  jz      short loc_18007D855
0x18007d84c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA
0x18007d853  jmp     short loc_18007D863
0x18007d855  lea     rcx, qword_1800EB130; this
0x18007d85c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx
0x18007d863  cmp     [rcx+8], r12b
0x18007d867  jz      short loc_18007D88A
0x18007d869  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ
0x18007d86e  cmp     [rax+7CCh], ebx
0x18007d874  jz      short loc_18007D88A
0x18007d876  mov     r9d, ebx; int
0x18007d879  mov     r8d, 14C6h; int
0x18007d87f  mov     rdx, r13; char *
0x18007d882  mov     rcx, rax; this
0x18007d885  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z
0x18007d88a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, dil
0x18007d891  jb      loc_18007DB99
0x18007d897  mov     edx, 1EBh
0x18007d89c  jmp     loc_18007D701
0x18007d8a1  mov     rcx, [rbp+var_28]
0x18007d8a5  mov     edx, 8064h
0x18007d8aa  mov     rax, [rcx]
0x18007d8ad  lea     r8d, [rdx+1]
0x18007d8b1  mov     rax, [rax+18h]
0x18007d8b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007d8ba  mov     rcx, [rbp+var_38]
0x18007d8be  lea     r8, [rbp+var_48]
0x18007d8c2  lea     rdx, _GUID_56a86895_0ad4_11ce_b03a_0020af0ba770
0x18007d8c9  mov     rax, [rcx]
0x18007d8cc  mov     rax, [rax]
0x18007d8cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007d8d4  mov     ebx, eax
0x18007d8d6  test    eax, eax
0x18007d8d8  jns     loc_18007D96F
0x18007d8de  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA
0x18007d8e5  test    rcx, rcx
0x18007d8e8  jnz     short loc_18007D931
0x18007d8ea  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18007d8f1  nop     dword ptr [rax+rax+00h]
0x18007d8f6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax
0x18007d8fd  mov     rcx, rax
0x18007d900  test    rax, rax
0x18007d903  jz      short loc_18007D923
0x18007d905  mov     rax, [rax]
0x18007d908  mov     edx, 7F0h
0x18007d90d  mov     rax, [rax+8]
0x18007d911  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007d916  test    eax, eax
0x18007d918  jz      short loc_18007D923
0x18007d91a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA
0x18007d921  jmp     short loc_18007D931
0x18007d923  lea     rcx, qword_1800EB130; this
0x18007d92a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx
0x18007d931  cmp     [rcx+8], r12b
0x18007d935  jz      short loc_18007D958
0x18007d937  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ
0x18007d93c  cmp     [rax+7CCh], ebx
0x18007d942  jz      short loc_18007D958
0x18007d944  mov     r9d, ebx; int
0x18007d947  mov     r8d, 14C8h; int
0x18007d94d  mov     rdx, r13; char *
0x18007d950  mov     rcx, rax; this
0x18007d953  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z
0x18007d958  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, dil
0x18007d95f  jb      loc_18007DB99
0x18007d965  mov     edx, 1ECh
0x18007d96a  jmp     loc_18007D701
0x18007d96f  mov     rcx, [rbp+var_48]
0x18007d973  lea     rdx, [rbp+var_20]
0x18007d977  mov     rax, [rcx]
0x18007d97a  mov     rax, [rax+50h]
0x18007d97e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007d983  mov     ebx, eax
0x18007d985  test    eax, eax
0x18007d987  jns     loc_18007DA1E
0x18007d98d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA
0x18007d994  test    rcx, rcx
0x18007d997  jnz     short loc_18007D9E0
0x18007d999  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18007d9a0  nop     dword ptr [rax+rax+00h]
0x18007d9a5  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax
0x18007d9ac  mov     rcx, rax
0x18007d9af  test    rax, rax
0x18007d9b2  jz      short loc_18007D9D2
0x18007d9b4  mov     rax, [rax]
0x18007d9b7  mov     edx, 7F0h
0x18007d9bc  mov     rax, [rax+8]
0x18007d9c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007d9c5  test    eax, eax
0x18007d9c7  jz      short loc_18007D9D2
0x18007d9c9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA
0x18007d9d0  jmp     short loc_18007D9E0
0x18007d9d2  lea     rcx, qword_1800EB130; this
0x18007d9d9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx
0x18007d9e0  cmp     [rcx+8], r12b
0x18007d9e4  jz      short loc_18007DA07
0x18007d9e6  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ
0x18007d9eb  cmp     [rax+7CCh], ebx
0x18007d9f1  jz      short loc_18007DA07
0x18007d9f3  mov     r9d, ebx; int
0x18007d9f6  mov     r8d, 14CAh; int
0x18007d9fc  mov     rdx, r13; char *
0x18007d9ff  mov     rcx, rax; this
0x18007da02  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z
0x18007da07  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, dil
0x18007da0e  jb      loc_18007DB99
0x18007da14  mov     edx, 1EDh
0x18007da19  jmp     loc_18007D701
0x18007da1e  mov     rcx, [rbp+var_20]
0x18007da22  lea     r8, [rbp+var_40]
0x18007da26  xor     r9d, r9d
0x18007da29  mov     edx, edi
0x18007da2b  mov     rax, [rcx]
0x18007da2e  mov     rax, [rax+18h]
0x18007da32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007da37  test    eax, eax
0x18007da39  jz      loc_18007DAD5
0x18007da3f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA
0x18007da46  test    rcx, rcx
0x18007da49  jnz     short loc_18007DA92
0x18007da4b  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18007da52  nop     dword ptr [rax+rax+00h]
0x18007da57  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax
0x18007da5e  mov     rcx, rax
0x18007da61  test    rax, rax
0x18007da64  jz      short loc_18007DA84
0x18007da66  mov     rax, [rax]
0x18007da69  mov     edx, 7F0h
0x18007da6e  mov     rax, [rax+8]
0x18007da72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007da77  test    eax, eax
0x18007da79  jz      short loc_18007DA84
0x18007da7b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA
0x18007da82  jmp     short loc_18007DA92
0x18007da84  lea     rcx, qword_1800EB130; this
0x18007da8b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx
0x18007da92  mov     ebx, 8000FFFFh
  ... truncated ...
```
