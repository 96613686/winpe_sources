# CTranscodeEngine::_BeginPrepareTranscode(void)

- ea: `0x180010bcc`
- end: `0x180010fc6`
- name: `?_BeginPrepareTranscode@CTranscodeEngine@@IEAAJXZ`
- size: `1018`
- prototype: `__int64 __fastcall(CTranscodeEngine *__hidden this)`
- caller_count: `2`
- callee_count: `12`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18002d210`
- `0x18002d5d0`

## callees

- `0x1800035c0`
- `0x180004a40`
- `0x180007000`
- `0x18000a3f4`
- `0x18000b41c`
- `0x180010bcc`
- `0x180010fcc`
- `0x18001a330`
- `0x18001c280`
- `0x18002e75c`
- `0x18004f410`
- `0x18005a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180010edb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180010edb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180010eed`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180010eed`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180010fa4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180010fa4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180010c34`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180010d7f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180010e3a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180010f20`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180010c34`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180010d7f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180010e3a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180010f20`
- `MFPlat!MFCreateSourceResolver` at `0x180010c18`
- `MFPlat!MFCreateSourceResolver` at `0x180010c18`

## pseudocode

```c
__int64 __fastcall CTranscodeEngine::_BeginPrepareTranscode(CTranscodeEngine *this)
{
  __int64 v2; // rdx
  int TopologyAndSetOnSession; // edi
  __int64 *v4; // rcx
  CallStackTracing *v5; // rax
  struct CallStackContext *v6; // rax
  __int64 v7; // rdx
  __int64 v8; // rdx
  __int64 *v9; // rcx
  CallStackTracing *v10; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v12; // rdx
  __int64 *v13; // rcx
  CallStackTracing *v14; // rax
  struct CallStackContext *v15; // rax
  __int64 v16; // rdx
  __int64 v17; // rdx
  __int64 *v18; // rcx
  CallStackTracing *v19; // rax
  struct CallStackContext *v20; // rax
  int v22; // [rsp+90h] [rbp+38h] BYREF
  IMFSourceResolver *ppISourceResolver; // [rsp+98h] [rbp+40h] BYREF
  __int64 v24; // [rsp+A0h] [rbp+48h] BYREF
  LPVOID pv; // [rsp+A8h] [rbp+50h] BYREF

  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v22, "CTranscodeEngine::_BeginPrepareTranscode", 403);
  pv = 0;
  if ( *((_QWORD *)this + 16) )
  {
    v24 = 0;
    ppISourceResolver = 0;
    TopologyAndSetOnSession = MFCreateSourceResolver(&ppISourceResolver);
    if ( TopologyAndSetOnSession >= 0 )
    {
      *((_DWORD *)this + 169) = 1;
      if ( (***((int (__fastcall ****)(_QWORD, GUID *, __int64 *))this + 16))(
             *((_QWORD *)this + 16),
             &GUID_2cd2d921_c447_44a7_a13c_4adabfc247e3,
             &v24) >= 0 )
      {
        v22 = 0;
        (*(void (__fastcall **)(__int64, const IID *, LPVOID *, int *))(*(_QWORD *)v24 + 104LL))(
          v24,
          &MF_BYTESTREAM_ORIGIN_NAME,
          &pv,
          &v22);
      }
      TopologyAndSetOnSession = ((__int64 (__fastcall *)(IMFSourceResolver *, _QWORD, LPVOID, __int64, _QWORD, _QWORD, char *, IMFSourceResolver *))ppISourceResolver->lpVtbl->BeginCreateObjectFromByteStream)(
                                  ppISourceResolver,
                                  *((_QWORD *)this + 16),
                                  pv,
                                  65553,
                                  0,
                                  0,
                                  (char *)this + 680,
                                  ppISourceResolver);
      if ( TopologyAndSetOnSession >= 0 )
        goto LABEL_14;
      v9 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v10 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v8);
        CallStackTracing::s_wpInstance = v10;
        if ( v10 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v10 + 8LL))(v10, 2032) )
        {
          v9 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v9 = &qword_180069A90;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
        }
      }
      if ( *((_BYTE *)v9 + 8) )
      {
        ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v9);
        if ( *((_DWORD *)ThreadRelativeContext + 499) != TopologyAndSetOnSession )
          CallStackContext::TraceFailure(
            ThreadRelativeContext,
            "CTranscodeEngine::_BeginPrepareTranscode",
            438,
            TopologyAndSetOnSession);
      }
      if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        goto LABEL_14;
      v7 = 55;
    }
    else
    {
      v4 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v5 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v2);
        CallStackTracing::s_wpInstance = v5;
        if ( v5 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v5 + 8LL))(v5, 2032) )
        {
          v4 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v4 = &qword_180069A90;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
        }
      }
      if ( *((_BYTE *)v4 + 8) )
      {
        v6 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v4);
        if ( *((_DWORD *)v6 + 499) != TopologyAndSetOnSession )
          CallStackContext::TraceFailure(v6, "CTranscodeEngine::_BeginPrepareTranscode", 410, TopologyAndSetOnSession);
      }
      if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        goto LABEL_14;
      v7 = 54;
    }
    WPP_SF_qd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v7,
      &WPP_e568207c201a3850f272ae9c45155cdf_Traceguids,
      this,
      TopologyAndSetOnSession);
LABEL_14:
    ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&ppISourceResolver);
    ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&v24);
    goto LABEL_56;
  }
  if ( !*((_QWORD *)this + 22) )
  {
    TopologyAndSetOnSession = -2147418113;
    goto LABEL_56;
  }
  if ( *((int *)this + 168) >= 5 )
  {
    TopologyAndSetOnSession = 0;
    goto LABEL_56;
  }
  TopologyAndSetOnSession = CTranscodeEngine::_ConfigureSourceAndProfile(this);
  if ( TopologyAndSetOnSession >= 0 )
  {
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
    CTranscodeEngine::_SetPropertyStore(this);
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
    if ( *((int *)this + 168) < 5 )
    {
      TopologyAndSetOnSession = CTranscodeEngine::_CreateTopologyAndSetOnSession(this, 0);
      if ( TopologyAndSetOnSession < 0 )
      {
        v18 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v19 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v17);
          CallStackTracing::s_wpInstance = v19;
          if ( v19 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v19 + 8LL))(v19, 2032) )
          {
            v18 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v18 = &qword_180069A90;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
          }
        }
        if ( *((_BYTE *)v18 + 8) )
        {
          v20 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v18);
          if ( *((_DWORD *)v20 + 499) != TopologyAndSetOnSession )
            CallStackContext::TraceFailure(
              v20,
              "CTranscodeEngine::_BeginPrepareTranscode",
              467,
              TopologyAndSetOnSession);
        }
        if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        {
          v16 = 57;
          goto LABEL_42;
        }
      }
    }
  }
  else
  {
    v13 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v14 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v12);
      CallStackTracing::s_wpInstance = v14;
      if ( v14 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v14 + 8LL))(v14, 2032) )
      {
        v13 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v13 = &qword_180069A90;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
      }
    }
    if ( *((_BYTE *)v13 + 8) )
    {
      v15 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v13);
      if ( *((_DWORD *)v15 + 499) != TopologyAndSetOnSession )
        CallStackContext::TraceFailure(v15, "CTranscodeEngine::_BeginPrepareTranscode", 450, TopologyAndSetOnSession);
    }
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
    {
      v16 = 56;
LABEL_42:
      WPP_SF_qd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v16,
        &WPP_e568207c201a3850f272ae9c45155cdf_Traceguids,
        this,
        TopologyAndSetOnSession);
    }
  }
LABEL_56:
  CoTaskMemFree(pv);
  pv = 0;
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v22);
  return (unsigned int)TopologyAndSetOnSession;
}

```

## disassembly

```asm
0x180010bcc  push    rbp
0x180010bce  push    rbx
0x180010bcf  push    rsi
0x180010bd0  push    rdi
0x180010bd1  push    r14
0x180010bd3  push    r15
0x180010bd5  mov     rbp, rsp
0x180010bd8  sub     rsp, 58h
0x180010bdc  mov     rsi, rcx
0x180010bdf  lea     r15, aCtranscodeengi_15; "CTranscodeEngine::_BeginPrepareTranscod"...
0x180010be6  mov     rdx, r15; char *
0x180010be9  lea     rcx, [rbp+arg_0]; this
0x180010bed  mov     r8d, 193h; int
0x180010bf3  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180010bf8  xor     r14d, r14d
0x180010bfb  mov     [rbp+pv], r14
0x180010bff  cmp     [rsi+80h], r14
0x180010c06  jz      loc_180010DFE
0x180010c0c  lea     rcx, [rbp+ppISourceResolver]; ppISourceResolver
0x180010c10  mov     [rbp+arg_10], r14
0x180010c14  mov     [rbp+ppISourceResolver], r14
0x180010c18  call    cs:__imp_MFCreateSourceResolver
0x180010c1e  mov     edi, eax
0x180010c20  test    eax, eax
0x180010c22  jns     loc_180010CDF
0x180010c28  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180010c2f  test    rcx, rcx
0x180010c32  jnz     short loc_180010C75
0x180010c34  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180010c3a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180010c41  mov     rcx, rax
0x180010c44  test    rax, rax
0x180010c47  jz      short loc_180010C67
0x180010c49  mov     rax, [rax]
0x180010c4c  mov     edx, 7F0h
0x180010c51  mov     rax, [rax+8]
0x180010c55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010c5a  test    eax, eax
0x180010c5c  jz      short loc_180010C67
0x180010c5e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180010c65  jmp     short loc_180010C75
0x180010c67  lea     rcx, qword_180069A90; this
0x180010c6e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180010c75  cmp     [rcx+8], r14b
0x180010c79  jz      short loc_180010C9C
0x180010c7b  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180010c80  cmp     [rax+7CCh], edi
0x180010c86  jz      short loc_180010C9C
0x180010c88  mov     r9d, edi; int
0x180010c8b  mov     r8d, 19Ah; int
0x180010c91  mov     rdx, r15; char *
0x180010c94  mov     rcx, rax; this
0x180010c97  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180010c9c  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180010ca1  cmp     al, 1
0x180010ca3  jb      short loc_180010CC8
0x180010ca5  mov     edx, 36h ; '6'
0x180010caa  mov     rcx, cs:WPP_GLOBAL_Control
0x180010cb1  lea     r8, WPP_e568207c201a3850f272ae9c45155cdf_Traceguids
0x180010cb8  mov     r9, rsi
0x180010cbb  mov     dword ptr [rsp+58h+var_38], edi
0x180010cbf  mov     rcx, [rcx+10h]
0x180010cc3  call    WPP_SF_qd
0x180010cc8  lea     rcx, [rbp+ppISourceResolver]
0x180010ccc  call    ??1?$ComSmartPtr@UIMFTransform@@@@QEAA@XZ; ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(void)
0x180010cd1  lea     rcx, [rbp+arg_10]
0x180010cd5  call    ??1?$ComSmartPtr@UIMFTransform@@@@QEAA@XZ; ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(void)
0x180010cda  jmp     loc_180010FA0
0x180010cdf  mov     dword ptr [rsi+2A4h], 1
0x180010ce9  lea     r8, [rbp+arg_10]
0x180010ced  mov     rcx, [rsi+80h]
0x180010cf4  lea     rdx, _GUID_2cd2d921_c447_44a7_a13c_4adabfc247e3
0x180010cfb  mov     rax, [rcx]
0x180010cfe  mov     rax, [rax]
0x180010d01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010d06  test    eax, eax
0x180010d08  js      short loc_180010D2D
0x180010d0a  mov     rcx, [rbp+arg_10]
0x180010d0e  lea     r9, [rbp+arg_0]
0x180010d12  mov     [rbp+arg_0], r14d
0x180010d16  lea     r8, [rbp+pv]
0x180010d1a  lea     rdx, MF_BYTESTREAM_ORIGIN_NAME
0x180010d21  mov     rax, [rcx]
0x180010d24  mov     rax, [rax+68h]
0x180010d28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010d2d  mov     rcx, [rbp+ppISourceResolver]
0x180010d31  lea     rdx, [rsi+2A8h]
0x180010d38  mov     r8, [rbp+pv]
0x180010d3c  mov     r9d, 10011h
0x180010d42  mov     [rsp+58h+var_20], rcx
0x180010d47  mov     [rsp+58h+var_28], rdx
0x180010d4c  mov     rax, [rcx]
0x180010d4f  mov     rdx, [rsi+80h]
0x180010d56  mov     [rsp+58h+var_30], r14
0x180010d5b  mov     [rsp+58h+var_38], r14
0x180010d60  mov     rax, [rax+38h]
0x180010d64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010d69  mov     edi, eax
0x180010d6b  test    eax, eax
0x180010d6d  jns     loc_180010CC8
0x180010d73  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180010d7a  test    rcx, rcx
0x180010d7d  jnz     short loc_180010DC0
0x180010d7f  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180010d85  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180010d8c  mov     rcx, rax
0x180010d8f  test    rax, rax
0x180010d92  jz      short loc_180010DB2
0x180010d94  mov     rax, [rax]
0x180010d97  mov     edx, 7F0h
0x180010d9c  mov     rax, [rax+8]
0x180010da0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010da5  test    eax, eax
0x180010da7  jz      short loc_180010DB2
0x180010da9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180010db0  jmp     short loc_180010DC0
0x180010db2  lea     rcx, qword_180069A90; this
0x180010db9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180010dc0  cmp     [rcx+8], r14b
0x180010dc4  jz      short loc_180010DE7
0x180010dc6  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180010dcb  cmp     [rax+7CCh], edi
0x180010dd1  jz      short loc_180010DE7
0x180010dd3  mov     r9d, edi; int
0x180010dd6  mov     r8d, 1B6h; int
0x180010ddc  mov     rdx, r15; char *
0x180010ddf  mov     rcx, rax; this
0x180010de2  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180010de7  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180010dec  cmp     al, 1
0x180010dee  jb      loc_180010CC8
0x180010df4  mov     edx, 37h ; '7'
0x180010df9  jmp     loc_180010CAA
0x180010dfe  cmp     [rsi+0B0h], r14
0x180010e05  jz      loc_180010F9B
0x180010e0b  cmp     dword ptr [rsi+2A0h], 5
0x180010e12  jl      short loc_180010E1C
0x180010e14  mov     edi, r14d
0x180010e17  jmp     loc_180010FA0
0x180010e1c  mov     rcx, rsi; this
0x180010e1f  call    ?_ConfigureSourceAndProfile@CTranscodeEngine@@IEAAJXZ; CTranscodeEngine::_ConfigureSourceAndProfile(void)
0x180010e24  mov     edi, eax
0x180010e26  test    eax, eax
0x180010e28  jns     loc_180010ED7
0x180010e2e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180010e35  test    rcx, rcx
0x180010e38  jnz     short loc_180010E7B
0x180010e3a  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180010e40  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180010e47  mov     rcx, rax
0x180010e4a  test    rax, rax
0x180010e4d  jz      short loc_180010E6D
0x180010e4f  mov     rax, [rax]
0x180010e52  mov     edx, 7F0h
0x180010e57  mov     rax, [rax+8]
0x180010e5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010e60  test    eax, eax
0x180010e62  jz      short loc_180010E6D
0x180010e64  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180010e6b  jmp     short loc_180010E7B
0x180010e6d  lea     rcx, qword_180069A90; this
0x180010e74  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180010e7b  cmp     [rcx+8], r14b
0x180010e7f  jz      short loc_180010EA2
0x180010e81  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180010e86  cmp     [rax+7CCh], edi
0x180010e8c  jz      short loc_180010EA2
0x180010e8e  mov     r9d, edi; int
0x180010e91  mov     r8d, 1C2h; int
0x180010e97  mov     rdx, r15; char *
0x180010e9a  mov     rcx, rax; this
0x180010e9d  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180010ea2  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180010ea7  cmp     al, 1
0x180010ea9  jb      loc_180010FA0
0x180010eaf  mov     edx, 38h ; '8'
0x180010eb4  mov     rcx, cs:WPP_GLOBAL_Control
0x180010ebb  lea     r8, WPP_e568207c201a3850f272ae9c45155cdf_Traceguids
0x180010ec2  mov     r9, rsi
0x180010ec5  mov     dword ptr [rsp+58h+var_38], edi
0x180010ec9  mov     rcx, [rcx+10h]
0x180010ecd  call    WPP_SF_qd
0x180010ed2  jmp     loc_180010FA0
0x180010ed7  lea     rcx, [rsi+8]; lpCriticalSection
0x180010edb  call    cs:__imp_LeaveCriticalSection
0x180010ee1  mov     rcx, rsi; this
0x180010ee4  call    ?_SetPropertyStore@CTranscodeEngine@@IEAAXXZ; CTranscodeEngine::_SetPropertyStore(void)
0x180010ee9  lea     rcx, [rsi+8]; lpCriticalSection
0x180010eed  call    cs:__imp_EnterCriticalSection
0x180010ef3  cmp     dword ptr [rsi+2A0h], 5
0x180010efa  jge     loc_180010FA0
0x180010f00  xor     edx, edx; bool
0x180010f02  mov     rcx, rsi; this
0x180010f05  call    ?_CreateTopologyAndSetOnSession@CTranscodeEngine@@IEAAJ_N@Z; CTranscodeEngine::_CreateTopologyAndSetOnSession(bool)
0x180010f0a  mov     edi, eax
0x180010f0c  test    eax, eax
0x180010f0e  jns     loc_180010FA0
0x180010f14  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180010f1b  test    rcx, rcx
0x180010f1e  jnz     short loc_180010F61
0x180010f20  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180010f26  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180010f2d  mov     rcx, rax
0x180010f30  test    rax, rax
0x180010f33  jz      short loc_180010F53
0x180010f35  mov     rax, [rax]
0x180010f38  mov     edx, 7F0h
0x180010f3d  mov     rax, [rax+8]
0x180010f41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010f46  test    eax, eax
0x180010f48  jz      short loc_180010F53
0x180010f4a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180010f51  jmp     short loc_180010F61
0x180010f53  lea     rcx, qword_180069A90; this
0x180010f5a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180010f61  cmp     [rcx+8], r14b
0x180010f65  jz      short loc_180010F88
0x180010f67  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180010f6c  cmp     [rax+7CCh], edi
0x180010f72  jz      short loc_180010F88
0x180010f74  mov     r9d, edi; int
0x180010f77  mov     r8d, 1D3h; int
0x180010f7d  mov     rdx, r15; char *
0x180010f80  mov     rcx, rax; this
0x180010f83  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180010f88  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180010f8d  cmp     al, 1
0x180010f8f  jb      short loc_180010FA0
0x180010f91  mov     edx, 39h ; '9'
0x180010f96  jmp     loc_180010EB4
0x180010f9b  mov     edi, 8000FFFFh
0x180010fa0  mov     rcx, [rbp+pv]; pv
0x180010fa4  call    cs:__imp_CoTaskMemFree
0x180010faa  mov     [rbp+pv], r14
0x180010fae  lea     rcx, [rbp+arg_0]; this
0x180010fb2  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180010fb7  mov     eax, edi
0x180010fb9  add     rsp, 58h
0x180010fbd  pop     r15
0x180010fbf  pop     r14
0x180010fc1  pop     rdi
0x180010fc2  pop     rsi
0x180010fc3  pop     rbx
0x180010fc4  pop     rbp
0x180010fc5  retn
```
