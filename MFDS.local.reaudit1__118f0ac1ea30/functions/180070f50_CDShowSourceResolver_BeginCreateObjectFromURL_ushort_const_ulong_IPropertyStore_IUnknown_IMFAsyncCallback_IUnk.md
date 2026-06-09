# CDShowSourceResolver::BeginCreateObjectFromURL(ushort const *,ulong,IPropertyStore *,IUnknown * *,IMFAsyncCallback *,IUnknown *)

- ea: `0x180070f50`
- end: `0x180071479`
- name: `?BeginCreateObjectFromURL@CDShowSourceResolver@@UEAAJPEBGKPEAUIPropertyStore@@PEAPEAUIUnknown@@PEAUIMFAsyncCallback@@PEAU3@@Z`
- size: `1321`
- prototype: `int(CDShowSourceResolver *__hidden this, const unsigned __int16 *, unsigned int, struct IPropertyStore *, struct IUnknown **, struct IMFAsyncCallback *, struct IUnknown *)`
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
- `0x180070f50`
- `0x180075b64`
- `0x1800765a0`
- `0x1800c9010`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!wcslen` at `0x18007115a`
- `api-ms-win-crt-string-l1-1-0!wcslen` at `0x18007115a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180071449`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180071449`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180070f99`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180070f99`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180070fe5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800710b3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800711a6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800712b9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180071395`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180070fe5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800710b3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800711a6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800712b9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180071395`
- `MFPlat!MFCreateSourceResolver` at `0x180070fc3`
- `MFPlat!MFCreateSourceResolver` at `0x180070fc3`

## string_xrefs

- `0x180070f75`: `CDShowSourceResolver::BeginCreateObjectFromURL`
- `0x180071042`: `CDShowSourceResolver::BeginCreateObjectFromURL`
- `0x180071110`: `CDShowSourceResolver::BeginCreateObjectFromURL`
- `0x180071203`: `CDShowSourceResolver::BeginCreateObjectFromURL`
- `0x180071316`: `CDShowSourceResolver::BeginCreateObjectFromURL`
- `0x1800713f2`: `CDShowSourceResolver::BeginCreateObjectFromURL`

## pseudocode

```c
__int64 __fastcall CDShowSourceResolver::BeginCreateObjectFromURL(
        struct _RTL_CRITICAL_SECTION *this,
        const unsigned __int16 *a2,
        int a3,
        struct IUnknown *a4,
        struct IUnknown **a5,
        struct IMFAsyncCallback *a6,
        struct IUnknown *a7)
{
  int v7; // r14d
  struct IUnknown **v11; // rsi
  struct IUnknown *v12; // rcx
  HRESULT v13; // ebx
  CallStackTracing *v14; // rcx
  CallStackTracing *v15; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v17; // rdx
  CallStackTracing *v18; // rcx
  CallStackTracing *v19; // rax
  struct CallStackContext *v20; // rax
  struct CDShowSourceResolver::CResolverResult *v21; // rdi
  size_t v22; // rax
  CallStackTracing *v23; // rcx
  CallStackTracing *v24; // rax
  struct CallStackContext *v25; // rax
  __int64 v26; // rcx
  __int64 v27; // rcx
  CallStackTracing *v28; // rcx
  CallStackTracing *v29; // rax
  struct CallStackContext *v30; // rax
  CallStackTracing *v31; // rcx
  CallStackTracing *v32; // rax
  struct CallStackContext *v33; // rax
  IMFSourceResolver *ppISourceResolver; // [rsp+40h] [rbp-20h] BYREF
  __int64 v36; // [rsp+48h] [rbp-18h] BYREF
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+50h] [rbp-10h]
  struct CDShowSourceResolver::CResolverResult *v38; // [rsp+A0h] [rbp+40h] BYREF
  int v39; // [rsp+B0h] [rbp+50h]

  v39 = a3;
  v7 = a3;
  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)&v38,
    "CDShowSourceResolver::BeginCreateObjectFromURL",
    98);
  lpCriticalSection = this + 2;
  EnterCriticalSection(this + 2);
  v11 = a5;
  v36 = 0;
  ppISourceResolver = 0;
  v38 = 0;
  if ( a5 )
    *a5 = 0;
  v13 = MFCreateSourceResolver(&ppISourceResolver);
  if ( v13 < 0 )
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
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(v14);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != v13 )
        CallStackContext::TraceFailure(
          ThreadRelativeContext,
          "CDShowSourceResolver::BeginCreateObjectFromURL",
          119,
          v13);
    }
    if ( g_wppLevels )
    {
      v17 = 17;
LABEL_14:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v17, WPP_4f2c49dc30393f4458000cee70747074_Traceguids, this, v13);
      goto LABEL_72;
    }
    goto LABEL_72;
  }
  v13 = CDShowSourceResolver::CResolverResult::CreateInstance(v12, a6, a7, &v38);
  if ( v13 >= 0 )
  {
    v21 = v38;
    LODWORD(a5) = -1;
    if ( a2 )
    {
      v22 = wcslen(a2);
      if ( (int)UIntPtrToLong(v22, (int *)&a5) < 0 )
      {
        v13 = -2147024785;
        *((_DWORD *)v21 + 35) = -2147024785;
        goto LABEL_30;
      }
      v13 = CMFBaseStringT<unsigned short>::_Append((char *)v21 + 136, a2, (unsigned int)a5);
      if ( v13 < 0 )
      {
LABEL_30:
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
          if ( *((_DWORD *)v25 + 499) != v13 )
            CallStackContext::TraceFailure(v25, "CDShowSourceResolver::BeginCreateObjectFromURL", 125, v13);
        }
        if ( g_wppLevels )
        {
          v17 = 19;
          goto LABEL_14;
        }
        goto LABEL_72;
      }
      v7 = v39;
    }
    if ( ppISourceResolver )
    {
      ((void (__fastcall *)(IMFSourceResolver *))ppISourceResolver->lpVtbl->AddRef)(ppISourceResolver);
      v27 = *((_QWORD *)v21 + 13);
      if ( v27 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
      *((_QWORD *)v21 + 13) = ppISourceResolver;
    }
    else
    {
      v26 = *((_QWORD *)v21 + 13);
      if ( v26 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
        *((_QWORD *)v21 + 13) = 0;
      }
    }
    if ( a4
      && (v13 = CGITPtr::Set(
                  (struct CDShowSourceResolver::CResolverResult *)((char *)v21 + 164),
                  &GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99,
                  a4),
          v13 < 0) )
    {
      v28 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v29 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
        CallStackTracing::s_wpInstance = v29;
        if ( v29 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v29 + 8LL))(v29, 2032) )
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
        if ( *((_DWORD *)v30 + 499) != v13 )
          CallStackContext::TraceFailure(v30, "CDShowSourceResolver::BeginCreateObjectFromURL", 129, v13);
      }
      if ( g_wppLevels )
      {
        v17 = 20;
        goto LABEL_14;
      }
    }
    else
    {
      *((_DWORD *)v21 + 40) = v7;
      v13 = ((__int64 (__fastcall *)(IMFSourceResolver *, const unsigned __int16 *, __int64, struct IUnknown *, char *, HANDLE *, struct CDShowSourceResolver::CResolverResult *))ppISourceResolver->lpVtbl->BeginCreateObjectFromURL)(
              ppISourceResolver,
              a2,
              65538,
              a4,
              (char *)v21 + 168,
              &this[1].LockSemaphore,
              v21);
      if ( v13 >= 0 )
      {
        if ( v11 )
        {
          v38 = 0;
          *v11 = (struct IUnknown *)v21;
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
          if ( *((_DWORD *)v33 + 499) != v13 )
            CallStackContext::TraceFailure(v33, "CDShowSourceResolver::BeginCreateObjectFromURL", 142, v13);
        }
        if ( g_wppLevels )
        {
          v17 = 21;
          goto LABEL_14;
        }
      }
    }
    goto LABEL_72;
  }
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
    if ( *((_DWORD *)v20 + 499) != v13 )
      CallStackContext::TraceFailure(v20, "CDShowSourceResolver::BeginCreateObjectFromURL", 124, v13);
  }
  if ( g_wppLevels )
  {
    v17 = 18;
    goto LABEL_14;
  }
LABEL_72:
  ATL::CComPtrBase<IMediaSeeking>::~CComPtrBase<IMediaSeeking>(&v38);
  ATL::CComPtrBase<IMediaSeeking>::~CComPtrBase<IMediaSeeking>(&ppISourceResolver);
  ATL::CComPtrBase<IMediaSeeking>::~CComPtrBase<IMediaSeeking>(&v36);
  LeaveCriticalSection(lpCriticalSection);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v38);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x180070f50  mov     [rsp-38h+arg_8], rbx
0x180070f55  mov     [rsp-38h+arg_10], r8d
0x180070f5a  push    rbp
0x180070f5b  push    rsi
0x180070f5c  push    rdi
0x180070f5d  push    r12
0x180070f5f  push    r13
0x180070f61  push    r14
0x180070f63  push    r15
0x180070f65  mov     rbp, rsp
0x180070f68  sub     rsp, 60h
0x180070f6c  mov     r14d, r8d
0x180070f6f  mov     r12, rdx
0x180070f72  mov     r15, rcx
0x180070f75  lea     rdx, aCdshowsourcere_2; "CDShowSourceResolver::BeginCreateObject"...
0x180070f7c  mov     r8d, 62h ; 'b'; int
0x180070f82  lea     rcx, [rbp+arg_0]; this
0x180070f86  mov     r13, r9
0x180070f89  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180070f8e  lea     rax, [r15+50h]
0x180070f92  mov     rcx, rax; lpCriticalSection
0x180070f95  mov     [rbp+lpCriticalSection], rax
0x180070f99  call    cs:__imp_EnterCriticalSection
0x180070fa0  nop     dword ptr [rax+rax+00h]
0x180070fa5  mov     rsi, [rbp+arg_20]
0x180070fa9  xor     edi, edi
0x180070fab  mov     [rbp+var_18], rdi
0x180070faf  mov     [rbp+ppISourceResolver], rdi
0x180070fb3  mov     [rbp+arg_0], rdi
0x180070fb7  test    rsi, rsi
0x180070fba  jz      short loc_180070FBF
0x180070fbc  mov     [rsi], rdi
0x180070fbf  lea     rcx, [rbp+ppISourceResolver]; ppISourceResolver
0x180070fc3  call    cs:__imp_MFCreateSourceResolver
0x180070fca  nop     dword ptr [rax+rax+00h]
0x180070fcf  mov     ebx, eax
0x180070fd1  test    eax, eax
0x180070fd3  jns     loc_18007108C
0x180070fd9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180070fe0  test    rcx, rcx
0x180070fe3  jnz     short loc_18007102C
0x180070fe5  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180070fec  nop     dword ptr [rax+rax+00h]
0x180070ff1  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180070ff8  mov     rcx, rax
0x180070ffb  test    rax, rax
0x180070ffe  jz      short loc_18007101E
0x180071000  mov     rax, [rax]
0x180071003  mov     edx, 7F0h
0x180071008  mov     rax, [rax+8]
0x18007100c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071011  test    eax, eax
0x180071013  jz      short loc_18007101E
0x180071015  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007101c  jmp     short loc_18007102C
0x18007101e  lea     rcx, qword_1800EB130; this
0x180071025  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18007102c  cmp     [rcx+8], dil
0x180071030  jz      short loc_180071057
0x180071032  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180071037  cmp     [rax+7CCh], ebx
0x18007103d  jz      short loc_180071057
0x18007103f  mov     r9d, ebx; int
0x180071042  lea     rdx, aCdshowsourcere_2; "CDShowSourceResolver::BeginCreateObject"...
0x180071049  mov     r8d, 77h ; 'w'; int
0x18007104f  mov     rcx, rax; this
0x180071052  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180071057  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18007105e  jb      loc_18007142A
0x180071064  mov     edx, 11h
0x180071069  mov     rcx, cs:WPP_GLOBAL_Control
0x180071070  lea     r8, WPP_4f2c49dc30393f4458000cee70747074_Traceguids
0x180071077  mov     r9, r15
0x18007107a  mov     dword ptr [rsp+60h+var_40], ebx
0x18007107e  mov     rcx, [rcx+10h]
0x180071082  call    WPP_SF_qD
0x180071087  jmp     loc_18007142A
0x18007108c  mov     r8, [rbp+arg_30]; struct IUnknown *
0x180071090  lea     r9, [rbp+arg_0]; struct CDShowSourceResolver::CResolverResult **
0x180071094  mov     rdx, [rbp+arg_28]; struct IMFAsyncCallback *
0x180071098  call    ?CreateInstance@CResolverResult@CDShowSourceResolver@@SAJPEAUIUnknown@@PEAUIMFAsyncCallback@@0PEAPEAV12@@Z; CDShowSourceResolver::CResolverResult::CreateInstance(IUnknown *,IMFAsyncCallback *,IUnknown *,CDShowSourceResolver::CResolverResult * *)
0x18007109d  mov     ebx, eax
0x18007109f  test    eax, eax
0x1800710a1  jns     loc_18007113C
0x1800710a7  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800710ae  test    rcx, rcx
0x1800710b1  jnz     short loc_1800710FA
0x1800710b3  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800710ba  nop     dword ptr [rax+rax+00h]
0x1800710bf  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800710c6  mov     rcx, rax
0x1800710c9  test    rax, rax
0x1800710cc  jz      short loc_1800710EC
0x1800710ce  mov     rax, [rax]
0x1800710d1  mov     edx, 7F0h
0x1800710d6  mov     rax, [rax+8]
0x1800710da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800710df  test    eax, eax
0x1800710e1  jz      short loc_1800710EC
0x1800710e3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800710ea  jmp     short loc_1800710FA
0x1800710ec  lea     rcx, qword_1800EB130; this
0x1800710f3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800710fa  cmp     [rcx+8], dil
0x1800710fe  jz      short loc_180071125
0x180071100  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180071105  cmp     [rax+7CCh], ebx
0x18007110b  jz      short loc_180071125
0x18007110d  mov     r9d, ebx; int
0x180071110  lea     rdx, aCdshowsourcere_2; "CDShowSourceResolver::BeginCreateObject"...
0x180071117  mov     r8d, 7Ch ; '|'; int
0x18007111d  mov     rcx, rax; this
0x180071120  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180071125  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18007112c  jb      loc_18007142A
0x180071132  mov     edx, 12h
0x180071137  jmp     loc_180071069
0x18007113c  mov     rdi, [rbp+arg_0]
0x180071140  mov     dword ptr [rbp+arg_20], 0FFFFFFFFh
0x180071147  test    r12, r12
0x18007114a  jz      loc_180071233
0x180071150  mov     rcx, r12; String
0x180071153  lea     r14, [rdi+88h]
0x18007115a  call    cs:__imp_wcslen
0x180071161  nop     dword ptr [rax+rax+00h]
0x180071166  mov     rcx, rax; unsigned __int64
0x180071169  lea     rdx, [rbp+arg_20]; int *
0x18007116d  call    ?UIntPtrToLong@@YAJ_KPEAJ@Z; UIntPtrToLong(unsigned __int64,long *)
0x180071172  test    eax, eax
0x180071174  jns     short loc_180071181
0x180071176  mov     ebx, 8007006Fh
0x18007117b  mov     [r14+4], ebx
0x18007117f  jmp     short loc_18007119A
0x180071181  mov     r8d, dword ptr [rbp+arg_20]
0x180071185  mov     rdx, r12
0x180071188  mov     rcx, r14
0x18007118b  call    ?_Append@?$CMFBaseStringT@G@@IEAAJPEBGJ@Z; CMFBaseStringT<ushort>::_Append(ushort const *,long)
0x180071190  mov     ebx, eax
0x180071192  test    eax, eax
0x180071194  jns     loc_18007122F
0x18007119a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800711a1  test    rcx, rcx
0x1800711a4  jnz     short loc_1800711ED
0x1800711a6  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800711ad  nop     dword ptr [rax+rax+00h]
0x1800711b2  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800711b9  mov     rcx, rax
0x1800711bc  test    rax, rax
0x1800711bf  jz      short loc_1800711DF
0x1800711c1  mov     rax, [rax]
0x1800711c4  mov     edx, 7F0h
0x1800711c9  mov     rax, [rax+8]
0x1800711cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800711d2  test    eax, eax
0x1800711d4  jz      short loc_1800711DF
0x1800711d6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800711dd  jmp     short loc_1800711ED
0x1800711df  lea     rcx, qword_1800EB130; this
0x1800711e6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800711ed  cmp     byte ptr [rcx+8], 0
0x1800711f1  jz      short loc_180071218
0x1800711f3  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800711f8  cmp     [rax+7CCh], ebx
0x1800711fe  jz      short loc_180071218
0x180071200  mov     r9d, ebx; int
0x180071203  lea     rdx, aCdshowsourcere_2; "CDShowSourceResolver::BeginCreateObject"...
0x18007120a  mov     r8d, 7Dh ; '}'; int
0x180071210  mov     rcx, rax; this
0x180071213  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180071218  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18007121f  jb      loc_18007142A
0x180071225  mov     edx, 13h
0x18007122a  jmp     loc_180071069
0x18007122f  mov     r14d, [rbp+arg_10]
0x180071233  mov     rcx, [rbp+ppISourceResolver]
0x180071237  test    rcx, rcx
0x18007123a  jnz     short loc_18007125B
0x18007123c  mov     rcx, [rdi+68h]
0x180071240  test    rcx, rcx
0x180071243  jz      short loc_180071284
0x180071245  mov     rax, [rcx]
0x180071248  mov     rax, [rax+10h]
0x18007124c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071251  mov     qword ptr [rdi+68h], 0
0x180071259  jmp     short loc_180071284
0x18007125b  mov     rax, [rcx]
0x18007125e  mov     rax, [rax+8]
0x180071262  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071267  mov     rcx, [rdi+68h]
0x18007126b  test    rcx, rcx
0x18007126e  jz      short loc_18007127C
0x180071270  mov     rax, [rcx]
0x180071273  mov     rax, [rax+10h]
0x180071277  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007127c  mov     rax, [rbp+ppISourceResolver]
0x180071280  mov     [rdi+68h], rax
0x180071284  test    r13, r13
0x180071287  jz      loc_180071342
0x18007128d  lea     rcx, [rdi+0A4h]; this
0x180071294  mov     r8, r13; struct IUnknown *
0x180071297  lea     rdx, _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99; struct _GUID *
0x18007129e  call    ?Set@CGITPtr@@QEAAJAEBU_GUID@@PEAUIUnknown@@@Z; CGITPtr::Set(_GUID const &,IUnknown *)
0x1800712a3  mov     ebx, eax
0x1800712a5  test    eax, eax
0x1800712a7  jns     loc_180071342
0x1800712ad  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800712b4  test    rcx, rcx
0x1800712b7  jnz     short loc_180071300
0x1800712b9  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800712c0  nop     dword ptr [rax+rax+00h]
0x1800712c5  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800712cc  mov     rcx, rax
0x1800712cf  test    rax, rax
0x1800712d2  jz      short loc_1800712F2
0x1800712d4  mov     rax, [rax]
0x1800712d7  mov     edx, 7F0h
0x1800712dc  mov     rax, [rax+8]
0x1800712e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800712e5  test    eax, eax
0x1800712e7  jz      short loc_1800712F2
0x1800712e9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800712f0  jmp     short loc_180071300
0x1800712f2  lea     rcx, qword_1800EB130; this
0x1800712f9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180071300  cmp     byte ptr [rcx+8], 0
0x180071304  jz      short loc_18007132B
0x180071306  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18007130b  cmp     [rax+7CCh], ebx
0x180071311  jz      short loc_18007132B
0x180071313  mov     r9d, ebx; int
0x180071316  lea     rdx, aCdshowsourcere_2; "CDShowSourceResolver::BeginCreateObject"...
0x18007131d  mov     r8d, 81h; int
0x180071323  mov     rcx, rax; this
0x180071326  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18007132b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180071332  jb      loc_18007142A
0x180071338  mov     edx, 14h
0x18007133d  jmp     loc_180071069
0x180071342  mov     [rdi+0A0h], r14d
0x180071349  lea     r8, [rdi+0A8h]
0x180071350  mov     rcx, [rbp+ppISourceResolver]
0x180071354  lea     rdx, [r15+40h]
0x180071358  mov     [rsp+60h+var_30], rdi
0x18007135d  mov     r9, r13
0x180071360  mov     [rsp+60h+var_38], rdx
0x180071365  mov     rdx, r12
0x180071368  mov     [rsp+60h+var_40], r8
0x18007136d  mov     r8d, 10002h
0x180071373  mov     rax, [rcx]
0x180071376  mov     rax, [rax+28h]
0x18007137a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007137f  mov     ebx, eax
0x180071381  test    eax, eax
0x180071383  jns     loc_18007141A
0x180071389  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180071390  test    rcx, rcx
0x180071393  jnz     short loc_1800713DC
0x180071395  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18007139c  nop     dword ptr [rax+rax+00h]
0x1800713a1  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800713a8  mov     rcx, rax
0x1800713ab  test    rax, rax
0x1800713ae  jz      short loc_1800713CE
0x1800713b0  mov     rax, [rax]
0x1800713b3  mov     edx, 7F0h
0x1800713b8  mov     rax, [rax+8]
0x1800713bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800713c1  test    eax, eax
0x1800713c3  jz      short loc_1800713CE
0x1800713c5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800713cc  jmp     short loc_1800713DC
0x1800713ce  lea     rcx, qword_1800EB130; this
0x1800713d5  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800713dc  cmp     byte ptr [rcx+8], 0
0x1800713e0  jz      short loc_180071407
0x1800713e2  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800713e7  cmp     [rax+7CCh], ebx
0x1800713ed  jz      short loc_180071407
0x1800713ef  mov     r9d, ebx; int
0x1800713f2  lea     rdx, aCdshowsourcere_2; "CDShowSourceResolver::BeginCreateObject"...
0x1800713f9  mov     r8d, 8Eh; int
0x1800713ff  mov     rcx, rax; this
0x180071402  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180071407  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18007140e  jb      short loc_18007142A
0x180071410  mov     edx, 15h
0x180071415  jmp     loc_180071069
0x18007141a  test    rsi, rsi
0x18007141d  jz      short loc_18007142A
0x18007141f  mov     [rbp+arg_0], 0
0x180071427  mov     [rsi], rdi
0x18007142a  lea     rcx, [rbp+arg_0]; void *
0x18007142e  call    ??1?$CComPtrBase@UIMediaSeeking@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IMediaSeeking>::~CComPtrBase<IMediaSeeking>(void)
0x180071433  lea     rcx, [rbp+ppISourceResolver]; void *
0x180071437  call    ??1?$CComPtrBase@UIMediaSeeking@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IMediaSeeking>::~CComPtrBase<IMediaSeeking>(void)
0x18007143c  lea     rcx, [rbp+var_18]; void *
0x180071440  call    ??1?$CComPtrBase@UIMediaSeeking@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IMediaSeeking>::~CComPtrBase<IMediaSeeking>(void)
0x180071445  mov     rcx, [rbp+lpCriticalSection]; lpCriticalSection
0x180071449  call    cs:__imp_LeaveCriticalSection
0x180071450  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
