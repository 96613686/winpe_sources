# CDShowSourceResolver::BeginCreateObjectFromByteStream(IMFByteStream *,ushort const *,ulong,IPropertyStore *,IUnknown * *,IMFAsyncCallback *,IUnknown *)

- ea: `0x180071480`
- end: `0x180071a00`
- name: `?BeginCreateObjectFromByteStream@CDShowSourceResolver@@UEAAJPEAUIMFByteStream@@PEBGKPEAUIPropertyStore@@PEAPEAUIUnknown@@PEAUIMFAsyncCallback@@PEAU4@@Z`
- size: `1408`
- prototype: `int(CDShowSourceResolver *__hidden this, struct IMFByteStream *, const unsigned __int16 *, unsigned int, struct IPropertyStore *, struct IUnknown **, struct IMFAsyncCallback *, struct IUnknown *)`
- caller_count: `0`
- callee_count: `12`
- tags: `broker_com_uri`

## callees

- `0x180002820`
- `0x18000b8c0`
- `0x1800140b0`
- `0x1800227e0`
- `0x180032570`
- `0x180032a50`
- `0x18004840c`
- `0x180051ce4`
- `0x180071480`
- `0x180075b64`
- `0x1800765a0`
- `0x1800c9010`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!wcslen` at `0x18007167a`
- `api-ms-win-crt-string-l1-1-0!wcslen` at `0x18007167a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800719d0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800719d0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800714c9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800714c9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180071505`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800715d3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800716c6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180071789`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180071876`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180071925`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180071505`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800715d3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800716c6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180071789`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180071876`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180071925`
- `MFPlat!MFInvokeCallback` at `0x180071903`
- `MFPlat!MFInvokeCallback` at `0x180071903`
- `MFPlat!MFCreateAsyncResult` at `0x180071854`
- `MFPlat!MFCreateAsyncResult` at `0x180071854`

## string_xrefs

- `0x1800714a5`: `CDShowSourceResolver::BeginCreateObjectFromByteStream`
- `0x180071562`: `CDShowSourceResolver::BeginCreateObjectFromByteStream`
- `0x180071630`: `CDShowSourceResolver::BeginCreateObjectFromByteStream`
- `0x180071723`: `CDShowSourceResolver::BeginCreateObjectFromByteStream`
- `0x1800717e6`: `CDShowSourceResolver::BeginCreateObjectFromByteStream`
- `0x1800718d3`: `CDShowSourceResolver::BeginCreateObjectFromByteStream`
- `0x180071982`: `CDShowSourceResolver::BeginCreateObjectFromByteStream`

## pseudocode

```c
__int64 __fastcall CDShowSourceResolver::BeginCreateObjectFromByteStream(
        CDShowSourceResolver *this,
        struct IUnknownVtbl *a2,
        const unsigned __int16 *a3,
        int a4,
        struct IUnknown *a5,
        struct IUnknown **a6,
        struct IMFAsyncCallback *a7,
        struct IUnknown *a8)
{
  int v11; // r15d
  struct IUnknown *v12; // rcx
  struct IUnknown **v13; // rsi
  CallStackTracing *v14; // rcx
  HRESULT Instance; // ebx
  CallStackTracing *v16; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v18; // rdx
  CallStackTracing *v19; // rcx
  CallStackTracing *v20; // rax
  struct CallStackContext *v21; // rax
  IUnknown *v22; // rdi
  size_t v23; // rax
  CallStackTracing *v24; // rcx
  CallStackTracing *v25; // rax
  struct CallStackContext *v26; // rax
  CallStackTracing *v27; // rcx
  CallStackTracing *v28; // rax
  struct CallStackContext *v29; // rax
  struct IUnknownVtbl *lpVtbl; // rcx
  CallStackTracing *v31; // rcx
  CallStackTracing *v32; // rax
  struct CallStackContext *v33; // rax
  CallStackTracing *v34; // rcx
  CallStackTracing *v35; // rax
  struct CallStackContext *v36; // rax
  IUnknown *punkState; // [rsp+80h] [rbp+40h] BYREF
  IMFAsyncResult *ppAsyncResult; // [rsp+88h] [rbp+48h] BYREF
  int v40; // [rsp+98h] [rbp+58h]

  v40 = a4;
  v11 = a4;
  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)&punkState,
    "CDShowSourceResolver::BeginCreateObjectFromByteStream",
    221);
  EnterCriticalSection((LPCRITICAL_SECTION)this + 2);
  v13 = a6;
  punkState = 0;
  ppAsyncResult = 0;
  if ( a6 )
    *a6 = 0;
  if ( !a2 )
  {
    v14 = CallStackTracing::s_wpInstance;
    Instance = -2147467261;
    if ( !CallStackTracing::s_wpInstance )
    {
      v16 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
      CallStackTracing::s_wpInstance = v16;
      if ( v16 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v16 + 8LL))(v16, 2032) )
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
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(v14);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != -2147467261 )
        CallStackContext::TraceFailure(
          ThreadRelativeContext,
          "CDShowSourceResolver::BeginCreateObjectFromByteStream",
          232,
          -2147467261);
    }
    if ( g_wppLevels )
    {
      v18 = 28;
LABEL_14:
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v18,
        WPP_4f2c49dc30393f4458000cee70747074_Traceguids,
        this,
        Instance);
      goto LABEL_79;
    }
    goto LABEL_79;
  }
  Instance = CDShowSourceResolver::CResolverResult::CreateInstance(
               v12,
               a7,
               a8,
               (struct CDShowSourceResolver::CResolverResult **)&punkState);
  if ( Instance >= 0 )
  {
    v22 = punkState;
    LODWORD(a6) = -1;
    if ( a3 )
    {
      v23 = wcslen(a3);
      if ( (int)UIntPtrToLong(v23, (int *)&a6) < 0 )
      {
        Instance = -2147024785;
        HIDWORD(v22[17].lpVtbl) = -2147024785;
        goto LABEL_30;
      }
      Instance = CMFBaseStringT<unsigned short>::_Append(&v22[17], a3, (unsigned int)a6);
      if ( Instance < 0 )
      {
LABEL_30:
        v24 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v25 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
          CallStackTracing::s_wpInstance = v25;
          if ( v25 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v25 + 8LL))(v25, 2032) )
          {
            v24 = CallStackTracing::s_wpInstance;
          }
          else
          {
            v24 = (CallStackTracing *)&qword_1800EB130;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
          }
        }
        if ( *((_BYTE *)v24 + 8) )
        {
          v26 = CallStackTracing::GetThreadRelativeContext(v24);
          if ( *((_DWORD *)v26 + 499) != Instance )
            CallStackContext::TraceFailure(v26, "CDShowSourceResolver::BeginCreateObjectFromByteStream", 246, Instance);
        }
        if ( g_wppLevels )
        {
          v18 = 30;
          goto LABEL_14;
        }
        goto LABEL_79;
      }
      v11 = v40;
    }
    if ( a5
      && (Instance = CGITPtr::Set(
                       (CGITPtr *)((char *)&v22[20].lpVtbl + 4),
                       &GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99,
                       a5),
          Instance < 0) )
    {
      v27 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v28 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
        CallStackTracing::s_wpInstance = v28;
        if ( v28 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v28 + 8LL))(v28, 2032) )
        {
          v27 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v27 = (CallStackTracing *)&qword_1800EB130;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
        }
      }
      if ( *((_BYTE *)v27 + 8) )
      {
        v29 = CallStackTracing::GetThreadRelativeContext(v27);
        if ( *((_DWORD *)v29 + 499) != Instance )
          CallStackContext::TraceFailure(v29, "CDShowSourceResolver::BeginCreateObjectFromByteStream", 249, Instance);
      }
      if ( g_wppLevels )
      {
        v18 = 31;
        goto LABEL_14;
      }
    }
    else
    {
      LODWORD(v22[20].lpVtbl) = v11;
      (*((void (__fastcall **)(struct IUnknownVtbl *))a2->QueryInterface + 1))(a2);
      lpVtbl = v22[16].lpVtbl;
      if ( lpVtbl )
        (*((void (__fastcall **)(struct IUnknownVtbl *))lpVtbl->QueryInterface + 2))(lpVtbl);
      v22[16].lpVtbl = a2;
      Instance = MFCreateAsyncResult(0, (IMFAsyncCallback *)this + 9, v22, &ppAsyncResult);
      if ( Instance >= 0 )
      {
        Instance = MFInvokeCallback(ppAsyncResult);
        if ( Instance >= 0 )
        {
          if ( v13 )
          {
            punkState = 0;
            *v13 = v22;
          }
        }
        else
        {
          v34 = CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v35 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
            CallStackTracing::s_wpInstance = v35;
            if ( v35 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v35 + 8LL))(v35, 2032) )
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
            if ( *((_DWORD *)v36 + 499) != Instance )
              CallStackContext::TraceFailure(
                v36,
                "CDShowSourceResolver::BeginCreateObjectFromByteStream",
                258,
                Instance);
          }
          if ( g_wppLevels )
          {
            v18 = 33;
            goto LABEL_14;
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
          if ( v32 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v32 + 8LL))(v32, 2032) )
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
          if ( *((_DWORD *)v33 + 499) != Instance )
            CallStackContext::TraceFailure(v33, "CDShowSourceResolver::BeginCreateObjectFromByteStream", 257, Instance);
        }
        if ( g_wppLevels )
        {
          v18 = 32;
          goto LABEL_14;
        }
      }
    }
    goto LABEL_79;
  }
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
    if ( *((_DWORD *)v21 + 499) != Instance )
      CallStackContext::TraceFailure(v21, "CDShowSourceResolver::BeginCreateObjectFromByteStream", 244, Instance);
  }
  if ( g_wppLevels )
  {
    v18 = 29;
    goto LABEL_14;
  }
LABEL_79:
  ATL::CComPtrBase<IMediaSeeking>::~CComPtrBase<IMediaSeeking>(&ppAsyncResult);
  ATL::CComPtrBase<IMediaSeeking>::~CComPtrBase<IMediaSeeking>(&punkState);
  LeaveCriticalSection((LPCRITICAL_SECTION)this + 2);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&punkState);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x180071480  mov     [rsp-38h+arg_10], rbx
0x180071485  mov     [rsp-38h+arg_18], r9d
0x18007148a  push    rbp
0x18007148b  push    rsi
0x18007148c  push    rdi
0x18007148d  push    r12
0x18007148f  push    r13
0x180071491  push    r14
0x180071493  push    r15
0x180071495  mov     rbp, rsp
0x180071498  sub     rsp, 40h
0x18007149c  mov     r12, r8
0x18007149f  mov     r14, rdx
0x1800714a2  mov     r13, rcx
0x1800714a5  lea     rdx, aCdshowsourcere_5; "CDShowSourceResolver::BeginCreateObject"...
0x1800714ac  mov     r8d, 0DDh; int
0x1800714b2  lea     rcx, [rbp+punkState]; this
0x1800714b6  mov     r15d, r9d
0x1800714b9  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800714be  lea     rax, [r13+50h]
0x1800714c2  mov     rcx, rax; lpCriticalSection
0x1800714c5  mov     [rbp+lpCriticalSection], rax
0x1800714c9  call    cs:__imp_EnterCriticalSection
0x1800714d0  nop     dword ptr [rax+rax+00h]
0x1800714d5  mov     rsi, [rbp+arg_28]
0x1800714d9  xor     edi, edi
0x1800714db  mov     [rbp+punkState], rdi
0x1800714df  mov     [rbp+ppAsyncResult], rdi
0x1800714e3  test    rsi, rsi
0x1800714e6  jz      short loc_1800714EB
0x1800714e8  mov     [rsi], rdi
0x1800714eb  test    r14, r14
0x1800714ee  jnz     loc_1800715AC
0x1800714f4  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800714fb  mov     ebx, 80004003h
0x180071500  test    rcx, rcx
0x180071503  jnz     short loc_18007154C
0x180071505  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18007150c  nop     dword ptr [rax+rax+00h]
0x180071511  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180071518  mov     rcx, rax
0x18007151b  test    rax, rax
0x18007151e  jz      short loc_18007153E
0x180071520  mov     rax, [rax]
0x180071523  mov     edx, 7F0h
0x180071528  mov     rax, [rax+8]
0x18007152c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071531  test    eax, eax
0x180071533  jz      short loc_18007153E
0x180071535  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007153c  jmp     short loc_18007154C
0x18007153e  lea     rcx, qword_1800EB130; this
0x180071545  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18007154c  cmp     [rcx+8], dil
0x180071550  jz      short loc_180071577
0x180071552  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180071557  cmp     [rax+7CCh], ebx
0x18007155d  jz      short loc_180071577
0x18007155f  mov     r9d, ebx; int
0x180071562  lea     rdx, aCdshowsourcere_5; "CDShowSourceResolver::BeginCreateObject"...
0x180071569  mov     r8d, 0E8h; int
0x18007156f  mov     rcx, rax; this
0x180071572  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180071577  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18007157e  jb      loc_1800719BA
0x180071584  mov     edx, 1Ch
0x180071589  mov     rcx, cs:WPP_GLOBAL_Control
0x180071590  lea     r8, WPP_4f2c49dc30393f4458000cee70747074_Traceguids
0x180071597  mov     r9, r13
0x18007159a  mov     [rsp+40h+var_20], ebx
0x18007159e  mov     rcx, [rcx+10h]
0x1800715a2  call    WPP_SF_qD
0x1800715a7  jmp     loc_1800719BA
0x1800715ac  mov     r8, [rbp+arg_38]; struct IUnknown *
0x1800715b0  lea     r9, [rbp+punkState]; struct CDShowSourceResolver::CResolverResult **
0x1800715b4  mov     rdx, [rbp+arg_30]; struct IMFAsyncCallback *
0x1800715b8  call    ?CreateInstance@CResolverResult@CDShowSourceResolver@@SAJPEAUIUnknown@@PEAUIMFAsyncCallback@@0PEAPEAV12@@Z; CDShowSourceResolver::CResolverResult::CreateInstance(IUnknown *,IMFAsyncCallback *,IUnknown *,CDShowSourceResolver::CResolverResult * *)
0x1800715bd  mov     ebx, eax
0x1800715bf  test    eax, eax
0x1800715c1  jns     loc_18007165C
0x1800715c7  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800715ce  test    rcx, rcx
0x1800715d1  jnz     short loc_18007161A
0x1800715d3  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800715da  nop     dword ptr [rax+rax+00h]
0x1800715df  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800715e6  mov     rcx, rax
0x1800715e9  test    rax, rax
0x1800715ec  jz      short loc_18007160C
0x1800715ee  mov     rax, [rax]
0x1800715f1  mov     edx, 7F0h
0x1800715f6  mov     rax, [rax+8]
0x1800715fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800715ff  test    eax, eax
0x180071601  jz      short loc_18007160C
0x180071603  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007160a  jmp     short loc_18007161A
0x18007160c  lea     rcx, qword_1800EB130; this
0x180071613  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18007161a  cmp     [rcx+8], dil
0x18007161e  jz      short loc_180071645
0x180071620  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180071625  cmp     [rax+7CCh], ebx
0x18007162b  jz      short loc_180071645
0x18007162d  mov     r9d, ebx; int
0x180071630  lea     rdx, aCdshowsourcere_5; "CDShowSourceResolver::BeginCreateObject"...
0x180071637  mov     r8d, 0F4h; int
0x18007163d  mov     rcx, rax; this
0x180071640  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180071645  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18007164c  jb      loc_1800719BA
0x180071652  mov     edx, 1Dh
0x180071657  jmp     loc_180071589
0x18007165c  mov     rdi, [rbp+punkState]
0x180071660  mov     dword ptr [rbp+arg_28], 0FFFFFFFFh
0x180071667  test    r12, r12
0x18007166a  jz      loc_180071753
0x180071670  mov     rcx, r12; String
0x180071673  lea     r15, [rdi+88h]
0x18007167a  call    cs:__imp_wcslen
0x180071681  nop     dword ptr [rax+rax+00h]
0x180071686  mov     rcx, rax; unsigned __int64
0x180071689  lea     rdx, [rbp+arg_28]; int *
0x18007168d  call    ?UIntPtrToLong@@YAJ_KPEAJ@Z; UIntPtrToLong(unsigned __int64,long *)
0x180071692  test    eax, eax
0x180071694  jns     short loc_1800716A1
0x180071696  mov     ebx, 8007006Fh
0x18007169b  mov     [r15+4], ebx
0x18007169f  jmp     short loc_1800716BA
0x1800716a1  mov     r8d, dword ptr [rbp+arg_28]
0x1800716a5  mov     rdx, r12
0x1800716a8  mov     rcx, r15
0x1800716ab  call    ?_Append@?$CMFBaseStringT@G@@IEAAJPEBGJ@Z; CMFBaseStringT<ushort>::_Append(ushort const *,long)
0x1800716b0  mov     ebx, eax
0x1800716b2  test    eax, eax
0x1800716b4  jns     loc_18007174F
0x1800716ba  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800716c1  test    rcx, rcx
0x1800716c4  jnz     short loc_18007170D
0x1800716c6  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800716cd  nop     dword ptr [rax+rax+00h]
0x1800716d2  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800716d9  mov     rcx, rax
0x1800716dc  test    rax, rax
0x1800716df  jz      short loc_1800716FF
0x1800716e1  mov     rax, [rax]
0x1800716e4  mov     edx, 7F0h
0x1800716e9  mov     rax, [rax+8]
0x1800716ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800716f2  test    eax, eax
0x1800716f4  jz      short loc_1800716FF
0x1800716f6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800716fd  jmp     short loc_18007170D
0x1800716ff  lea     rcx, qword_1800EB130; this
0x180071706  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18007170d  cmp     byte ptr [rcx+8], 0
0x180071711  jz      short loc_180071738
0x180071713  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180071718  cmp     [rax+7CCh], ebx
0x18007171e  jz      short loc_180071738
0x180071720  mov     r9d, ebx; int
0x180071723  lea     rdx, aCdshowsourcere_5; "CDShowSourceResolver::BeginCreateObject"...
0x18007172a  mov     r8d, 0F6h; int
0x180071730  mov     rcx, rax; this
0x180071733  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180071738  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18007173f  jb      loc_1800719BA
0x180071745  mov     edx, 1Eh
0x18007174a  jmp     loc_180071589
0x18007174f  mov     r15d, [rbp+arg_18]
0x180071753  mov     r8, [rbp+arg_20]; struct IUnknown *
0x180071757  test    r8, r8
0x18007175a  jz      loc_180071812
0x180071760  lea     rcx, [rdi+0A4h]; this
0x180071767  lea     rdx, _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99; struct _GUID *
0x18007176e  call    ?Set@CGITPtr@@QEAAJAEBU_GUID@@PEAUIUnknown@@@Z; CGITPtr::Set(_GUID const &,IUnknown *)
0x180071773  mov     ebx, eax
0x180071775  test    eax, eax
0x180071777  jns     loc_180071812
0x18007177d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180071784  test    rcx, rcx
0x180071787  jnz     short loc_1800717D0
0x180071789  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180071790  nop     dword ptr [rax+rax+00h]
0x180071795  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18007179c  mov     rcx, rax
0x18007179f  test    rax, rax
0x1800717a2  jz      short loc_1800717C2
0x1800717a4  mov     rax, [rax]
0x1800717a7  mov     edx, 7F0h
0x1800717ac  mov     rax, [rax+8]
0x1800717b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800717b5  test    eax, eax
0x1800717b7  jz      short loc_1800717C2
0x1800717b9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800717c0  jmp     short loc_1800717D0
0x1800717c2  lea     rcx, qword_1800EB130; this
0x1800717c9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800717d0  cmp     byte ptr [rcx+8], 0
0x1800717d4  jz      short loc_1800717FB
0x1800717d6  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800717db  cmp     [rax+7CCh], ebx
0x1800717e1  jz      short loc_1800717FB
0x1800717e3  mov     r9d, ebx; int
0x1800717e6  lea     rdx, aCdshowsourcere_5; "CDShowSourceResolver::BeginCreateObject"...
0x1800717ed  mov     r8d, 0F9h; int
0x1800717f3  mov     rcx, rax; this
0x1800717f6  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800717fb  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180071802  jb      loc_1800719BA
0x180071808  mov     edx, 1Fh
0x18007180d  jmp     loc_180071589
0x180071812  mov     [rdi+0A0h], r15d
0x180071819  mov     rcx, r14
0x18007181c  mov     rax, [r14]
0x18007181f  mov     rax, [rax+8]
0x180071823  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071828  mov     rcx, [rdi+80h]
0x18007182f  test    rcx, rcx
0x180071832  jz      short loc_180071840
0x180071834  mov     rax, [rcx]
0x180071837  mov     rax, [rax+10h]
0x18007183b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071840  lea     rdx, [r13+48h]; pCallback
0x180071844  mov     [rdi+80h], r14
0x18007184b  lea     r9, [rbp+ppAsyncResult]; ppAsyncResult
0x18007184f  mov     r8, rdi; punkState
0x180071852  xor     ecx, ecx; punkObject
0x180071854  call    cs:__imp_MFCreateAsyncResult
0x18007185b  nop     dword ptr [rax+rax+00h]
0x180071860  mov     ebx, eax
0x180071862  test    eax, eax
0x180071864  jns     loc_1800718FF
0x18007186a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180071871  test    rcx, rcx
0x180071874  jnz     short loc_1800718BD
0x180071876  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18007187d  nop     dword ptr [rax+rax+00h]
0x180071882  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180071889  mov     rcx, rax
0x18007188c  test    rax, rax
0x18007188f  jz      short loc_1800718AF
0x180071891  mov     rax, [rax]
0x180071894  mov     edx, 7F0h
0x180071899  mov     rax, [rax+8]
0x18007189d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800718a2  test    eax, eax
0x1800718a4  jz      short loc_1800718AF
0x1800718a6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800718ad  jmp     short loc_1800718BD
0x1800718af  lea     rcx, qword_1800EB130; this
0x1800718b6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800718bd  cmp     byte ptr [rcx+8], 0
0x1800718c1  jz      short loc_1800718E8
0x1800718c3  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800718c8  cmp     [rax+7CCh], ebx
0x1800718ce  jz      short loc_1800718E8
0x1800718d0  mov     r9d, ebx; int
0x1800718d3  lea     rdx, aCdshowsourcere_5; "CDShowSourceResolver::BeginCreateObject"...
0x1800718da  mov     r8d, 101h; int
0x1800718e0  mov     rcx, rax; this
0x1800718e3  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800718e8  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800718ef  jb      loc_1800719BA
0x1800718f5  mov     edx, 20h ; ' '
0x1800718fa  jmp     loc_180071589
0x1800718ff  mov     rcx, [rbp+ppAsyncResult]; pAsyncResult
0x180071903  call    cs:__imp_MFInvokeCallback
0x18007190a  nop     dword ptr [rax+rax+00h]
0x18007190f  mov     ebx, eax
0x180071911  test    eax, eax
0x180071913  jns     loc_1800719AA
0x180071919  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180071920  test    rcx, rcx
0x180071923  jnz     short loc_18007196C
0x180071925  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18007192c  nop     dword ptr [rax+rax+00h]
0x180071931  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180071938  mov     rcx, rax
0x18007193b  test    rax, rax
0x18007193e  jz      short loc_18007195E
0x180071940  mov     rax, [rax]
0x180071943  mov     edx, 7F0h
0x180071948  mov     rax, [rax+8]
0x18007194c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071951  test    eax, eax
0x180071953  jz      short loc_18007195E
0x180071955  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007195c  jmp     short loc_18007196C
0x18007195e  lea     rcx, qword_1800EB130; this
0x180071965  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18007196c  cmp     byte ptr [rcx+8], 0
0x180071970  jz      short loc_180071997
0x180071972  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180071977  cmp     [rax+7CCh], ebx
0x18007197d  jz      short loc_180071997
0x18007197f  mov     r9d, ebx; int
0x180071982  lea     rdx, aCdshowsourcere_5; "CDShowSourceResolver::BeginCreateObject"...
0x180071989  mov     r8d, 102h; int
0x18007198f  mov     rcx, rax; this
  ... truncated ...
```
