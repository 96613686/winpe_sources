# CSceneAnalysisEffectFrameImpl::RuntimeClassInitialize(Windows::Foundation::TimeSpan *,Windows::Foundation::TimeSpan *,Windows::Media::Capture::ICapturedFrameControlValues *,float *,float *,ushort,float *,Windows::Media::Core::SceneAnalysisRecommendation)

- ea: `0x1800b52b0`
- end: `0x1800b5634`
- name: `?RuntimeClassInitialize@CSceneAnalysisEffectFrameImpl@@QEAAJPEAUTimeSpan@Foundation@Windows@@0PEAUICapturedFrameControlValues@Capture@Media@4@PEAM2G2W4SceneAnalysisRecommendation@Core@74@@Z`
- size: `900`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `broker_com_uri`

## callers

- `0x1800b37d8`

## callees

- `0x18000b490`
- `0x18000c0f8`
- `0x1800280e4`
- `0x18002a9bc`
- `0x18002ae0c`
- `0x18002afd0`
- `0x18002bb98`
- `0x1800a75a0`
- `0x1800ae020`
- `0x1800b3614`
- `0x1800b3700`
- `0x1800b47d0`
- `0x1800b52b0`
- `0x18012f850`
- `0x180130614`
- `0x180142010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b5309`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b53ce`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b5498`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b5558`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b5309`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b53ce`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b5498`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b5558`

## pseudocode

```c
__int64 __fastcall CSceneAnalysisEffectFrameImpl::RuntimeClassInitialize(
        __int64 a1,
        struct Windows::Foundation::TimeSpan *a2,
        struct Windows::Foundation::TimeSpan *a3,
        __int64 a4,
        __int64 a5,
        char a6,
        char a7,
        __int64 a8,
        int a9)
{
  int v13; // edx
  int v14; // eax
  __int64 *v15; // rcx
  int v16; // ebx
  CallStackTracing *v17; // rax
  struct CallStackContext *v18; // rax
  __int64 v19; // rdx
  __int64 *v20; // rcx
  CallStackTracing *v21; // rax
  struct CallStackContext *v22; // rax
  __int64 v23; // rbp
  __int64 *v24; // rcx
  CallStackTracing *v25; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v27; // rbp
  __int64 *v28; // rcx
  CallStackTracing *v29; // rax
  struct CallStackContext *v30; // rax
  __int64 v32; // [rsp+50h] [rbp+8h] BYREF

  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)&v32,
    "CSceneAnalysisEffectFrameImpl::RuntimeClassInitialize",
    121);
  if ( a2 )
  {
    v16 = CResultFrameBase::InitializeBase((CResultFrameBase *)a1, a2, a3);
    if ( v16 >= 0 )
    {
      v23 = a5;
      if ( a5
        && (Microsoft::WRL::ComPtr<HighDynamicRangeControlImpl>::InternalRelease(a1 + 144),
            v16 = Microsoft::WRL::Details::MakeAndInitialize<CHighDynamicRangeOutputImpl,CHighDynamicRangeOutputImpl,float &,float * &,unsigned short &>(
                    a1 + 144,
                    v23,
                    &a6,
                    &a7),
            v16 < 0) )
      {
        v24 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v25 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
          CallStackTracing::s_wpInstance = v25;
          if ( v25 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v25 + 8LL))(v25, 2032) )
          {
            v24 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v24 = &qword_18015FF10;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18015FF10;
          }
        }
        if ( *((_BYTE *)v24 + 8) )
        {
          ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v24);
          if ( *((_DWORD *)ThreadRelativeContext + 499) != v16 )
            CallStackContext::TraceFailure(
              ThreadRelativeContext,
              "CSceneAnalysisEffectFrameImpl::RuntimeClassInitialize",
              135,
              v16);
        }
        if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        {
          v19 = 23;
          goto LABEL_13;
        }
      }
      else
      {
        v27 = a8;
        if ( a8
          && (Microsoft::WRL::ComPtr<CLowLightOutputImpl>::InternalRelease(a1 + 152),
              v16 = Microsoft::WRL::Details::MakeAndInitialize<CLowLightOutputImpl,CLowLightOutputImpl,float &>(
                      a1 + 152,
                      v27),
              v16 < 0) )
        {
          v28 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v29 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
            CallStackTracing::s_wpInstance = v29;
            if ( v29 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v29 + 8LL))(v29, 2032) )
            {
              v28 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v28 = &qword_18015FF10;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18015FF10;
            }
          }
          if ( *((_BYTE *)v28 + 8) )
          {
            v30 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v28);
            if ( *((_DWORD *)v30 + 499) != v16 )
              CallStackContext::TraceFailure(v30, "CSceneAnalysisEffectFrameImpl::RuntimeClassInitialize", 143, v16);
          }
          if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
          {
            v19 = 24;
            goto LABEL_13;
          }
        }
        else
        {
          if ( *(_QWORD *)(a1 + 136) != a4 )
          {
            v32 = a4;
            Microsoft::WRL::ComPtr<IAsyncInfo>::InternalAddRef(&v32);
            v32 = *(_QWORD *)(a1 + 136);
            *(_QWORD *)(a1 + 136) = a4;
            Microsoft::WRL::ComPtr<IMFVideoProcessorControl>::InternalRelease(&v32);
          }
          *(_DWORD *)(a1 + 160) = a9;
        }
      }
    }
    else
    {
      v20 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v21 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
        CallStackTracing::s_wpInstance = v21;
        if ( v21 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v21 + 8LL))(v21, 2032) )
        {
          v20 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v20 = &qword_18015FF10;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18015FF10;
        }
      }
      if ( *((_BYTE *)v20 + 8) )
      {
        v22 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v20);
        if ( *((_DWORD *)v22 + 499) != v16 )
          CallStackContext::TraceFailure(v22, "CSceneAnalysisEffectFrameImpl::RuntimeClassInitialize", 126, v16);
      }
      if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      {
        v19 = 22;
        goto LABEL_13;
      }
    }
  }
  else
  {
    v14 = Windows::Media::Report((Windows::Media *)0x80004003LL, v13);
    v15 = (__int64 *)CallStackTracing::s_wpInstance;
    v16 = v14;
    if ( !CallStackTracing::s_wpInstance )
    {
      v17 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
      CallStackTracing::s_wpInstance = v17;
      if ( v17 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v17 + 8LL))(v17, 2032) )
      {
        v15 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v15 = &qword_18015FF10;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18015FF10;
      }
    }
    if ( *((_BYTE *)v15 + 8) )
    {
      v18 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v15);
      if ( v16 < 0 && *((_DWORD *)v18 + 499) != v16 )
        CallStackContext::TraceFailure(v18, "CSceneAnalysisEffectFrameImpl::RuntimeClassInitialize", 124, v16);
    }
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
    {
      v19 = 21;
LABEL_13:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v19, &WPP_2cb6b193ea5b3f7c59b28ba1ce3630e6_Traceguids, a1, v16);
    }
  }
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v32);
  return (unsigned int)v16;
}

```

## disassembly

```asm
0x1800b52b0  mov     [rsp+arg_8], rbx
0x1800b52b5  mov     [rsp+arg_10], rbp
0x1800b52ba  push    rsi
0x1800b52bb  push    rdi
0x1800b52bc  push    r15
0x1800b52be  sub     rsp, 30h
0x1800b52c2  mov     rbp, r8
0x1800b52c5  lea     r15, aCsceneanalysis_1; "CSceneAnalysisEffectFrameImpl::RuntimeC"...
0x1800b52cc  mov     rbx, rdx
0x1800b52cf  mov     rdi, rcx
0x1800b52d2  mov     rdx, r15; char *
0x1800b52d5  lea     rcx, [rsp+48h+arg_0]; this
0x1800b52da  mov     r8d, 79h ; 'y'; int
0x1800b52e0  mov     rsi, r9
0x1800b52e3  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800b52e8  test    rbx, rbx
0x1800b52eb  jnz     loc_1800B53AA
0x1800b52f1  mov     ecx, 80004003h; this
0x1800b52f6  call    ?Report@Media@Windows@@YAJJ@Z; Windows::Media::Report(long)
0x1800b52fb  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b5302  mov     ebx, eax
0x1800b5304  test    rcx, rcx
0x1800b5307  jnz     short loc_1800B534A
0x1800b5309  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800b530f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b5316  mov     rcx, rax
0x1800b5319  test    rax, rax
0x1800b531c  jz      short loc_1800B533C
0x1800b531e  mov     rax, [rax]
0x1800b5321  mov     edx, 7F0h
0x1800b5326  mov     rax, [rax+8]
0x1800b532a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b532f  test    eax, eax
0x1800b5331  jz      short loc_1800B533C
0x1800b5333  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b533a  jmp     short loc_1800B534A
0x1800b533c  lea     rcx, qword_18015FF10; this
0x1800b5343  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b534a  cmp     byte ptr [rcx+8], 0
0x1800b534e  jz      short loc_1800B5375
0x1800b5350  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800b5355  test    ebx, ebx
0x1800b5357  jns     short loc_1800B5375
0x1800b5359  cmp     [rax+7CCh], ebx
0x1800b535f  jz      short loc_1800B5375
0x1800b5361  mov     r9d, ebx; int
0x1800b5364  mov     r8d, 7Ch ; '|'; int
0x1800b536a  mov     rdx, r15; char *
0x1800b536d  mov     rcx, rax; this
0x1800b5370  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800b5375  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1800b537a  cmp     al, 1
0x1800b537c  jb      loc_1800B5615
0x1800b5382  mov     edx, 15h
0x1800b5387  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b538e  lea     r8, WPP_2cb6b193ea5b3f7c59b28ba1ce3630e6_Traceguids
0x1800b5395  mov     r9, rdi
0x1800b5398  mov     [rsp+48h+var_28], ebx
0x1800b539c  mov     rcx, [rcx+10h]
0x1800b53a0  call    WPP_SF_qD
0x1800b53a5  jmp     loc_1800B5615
0x1800b53aa  mov     r8, rbp; struct Windows::Foundation::TimeSpan *
0x1800b53ad  mov     rdx, rbx; struct Windows::Foundation::TimeSpan *
0x1800b53b0  mov     rcx, rdi; this
0x1800b53b3  call    ?InitializeBase@CResultFrameBase@@IEAAJPEAUTimeSpan@Foundation@Windows@@0@Z; CResultFrameBase::InitializeBase(Windows::Foundation::TimeSpan *,Windows::Foundation::TimeSpan *)
0x1800b53b8  mov     ebx, eax
0x1800b53ba  test    eax, eax
0x1800b53bc  jns     loc_1800B544D
0x1800b53c2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b53c9  test    rcx, rcx
0x1800b53cc  jnz     short loc_1800B540F
0x1800b53ce  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800b53d4  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b53db  mov     rcx, rax
0x1800b53de  test    rax, rax
0x1800b53e1  jz      short loc_1800B5401
0x1800b53e3  mov     rax, [rax]
0x1800b53e6  mov     edx, 7F0h
0x1800b53eb  mov     rax, [rax+8]
0x1800b53ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b53f4  test    eax, eax
0x1800b53f6  jz      short loc_1800B5401
0x1800b53f8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b53ff  jmp     short loc_1800B540F
0x1800b5401  lea     rcx, qword_18015FF10; this
0x1800b5408  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b540f  cmp     byte ptr [rcx+8], 0
0x1800b5413  jz      short loc_1800B5436
0x1800b5415  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800b541a  cmp     [rax+7CCh], ebx
0x1800b5420  jz      short loc_1800B5436
0x1800b5422  mov     r9d, ebx; int
0x1800b5425  mov     r8d, 7Eh ; '~'; int
0x1800b542b  mov     rdx, r15; char *
0x1800b542e  mov     rcx, rax; this
0x1800b5431  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800b5436  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1800b543b  cmp     al, 1
0x1800b543d  jb      loc_1800B5615
0x1800b5443  mov     edx, 16h
0x1800b5448  jmp     loc_1800B5387
0x1800b544d  mov     rbp, [rsp+48h+arg_20]
0x1800b5452  test    rbp, rbp
0x1800b5455  jz      loc_1800B5517
0x1800b545b  lea     rbx, [rdi+90h]
0x1800b5462  mov     rcx, rbx
0x1800b5465  call    ?InternalRelease@?$ComPtr@VHighDynamicRangeControlImpl@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<HighDynamicRangeControlImpl>::InternalRelease(void)
0x1800b546a  lea     r9, [rsp+48h+arg_30]
0x1800b5472  mov     rdx, rbp
0x1800b5475  lea     r8, [rsp+48h+arg_28]
0x1800b547a  mov     rcx, rbx
0x1800b547d  call    ??$MakeAndInitialize@VCHighDynamicRangeOutputImpl@@V1@AEAMAEAPEAMAEAG@Details@WRL@Microsoft@@YAJPEAPEAVCHighDynamicRangeOutputImpl@@AEAMAEAPEAMAEAG@Z; Microsoft::WRL::Details::MakeAndInitialize<CHighDynamicRangeOutputImpl,CHighDynamicRangeOutputImpl,float &,float * &,ushort &>(CHighDynamicRangeOutputImpl * *,float &,float * &,ushort &)
0x1800b5482  mov     ebx, eax
0x1800b5484  test    eax, eax
0x1800b5486  jns     loc_1800B5517
0x1800b548c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b5493  test    rcx, rcx
0x1800b5496  jnz     short loc_1800B54D9
0x1800b5498  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800b549e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b54a5  mov     rcx, rax
0x1800b54a8  test    rax, rax
0x1800b54ab  jz      short loc_1800B54CB
0x1800b54ad  mov     rax, [rax]
0x1800b54b0  mov     edx, 7F0h
0x1800b54b5  mov     rax, [rax+8]
0x1800b54b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b54be  test    eax, eax
0x1800b54c0  jz      short loc_1800B54CB
0x1800b54c2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b54c9  jmp     short loc_1800B54D9
0x1800b54cb  lea     rcx, qword_18015FF10; this
0x1800b54d2  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b54d9  cmp     byte ptr [rcx+8], 0
0x1800b54dd  jz      short loc_1800B5500
0x1800b54df  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800b54e4  cmp     [rax+7CCh], ebx
0x1800b54ea  jz      short loc_1800B5500
0x1800b54ec  mov     r9d, ebx; int
0x1800b54ef  mov     r8d, 87h; int
0x1800b54f5  mov     rdx, r15; char *
0x1800b54f8  mov     rcx, rax; this
0x1800b54fb  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800b5500  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1800b5505  cmp     al, 1
0x1800b5507  jb      loc_1800B5615
0x1800b550d  mov     edx, 17h
0x1800b5512  jmp     loc_1800B5387
0x1800b5517  mov     rbp, [rsp+48h+arg_38]
0x1800b551f  test    rbp, rbp
0x1800b5522  jz      loc_1800B55D3
0x1800b5528  lea     rbx, [rdi+98h]
0x1800b552f  mov     rcx, rbx
0x1800b5532  call    ?InternalRelease@?$ComPtr@VCLowLightOutputImpl@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<CLowLightOutputImpl>::InternalRelease(void)
0x1800b5537  mov     rdx, rbp
0x1800b553a  mov     rcx, rbx
0x1800b553d  call    ??$MakeAndInitialize@VCLowLightOutputImpl@@V1@AEAM@Details@WRL@Microsoft@@YAJPEAPEAVCLowLightOutputImpl@@AEAM@Z; Microsoft::WRL::Details::MakeAndInitialize<CLowLightOutputImpl,CLowLightOutputImpl,float &>(CLowLightOutputImpl * *,float &)
0x1800b5542  mov     ebx, eax
0x1800b5544  test    eax, eax
0x1800b5546  jns     loc_1800B55D3
0x1800b554c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b5553  test    rcx, rcx
0x1800b5556  jnz     short loc_1800B5599
0x1800b5558  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800b555e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b5565  mov     rcx, rax
0x1800b5568  test    rax, rax
0x1800b556b  jz      short loc_1800B558B
0x1800b556d  mov     rax, [rax]
0x1800b5570  mov     edx, 7F0h
0x1800b5575  mov     rax, [rax+8]
0x1800b5579  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b557e  test    eax, eax
0x1800b5580  jz      short loc_1800B558B
0x1800b5582  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b5589  jmp     short loc_1800B5599
0x1800b558b  lea     rcx, qword_18015FF10; this
0x1800b5592  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b5599  cmp     byte ptr [rcx+8], 0
0x1800b559d  jz      short loc_1800B55C0
0x1800b559f  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800b55a4  cmp     [rax+7CCh], ebx
0x1800b55aa  jz      short loc_1800B55C0
0x1800b55ac  mov     r9d, ebx; int
0x1800b55af  mov     r8d, 8Fh; int
0x1800b55b5  mov     rdx, r15; char *
0x1800b55b8  mov     rcx, rax; this
0x1800b55bb  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800b55c0  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1800b55c5  cmp     al, 1
0x1800b55c7  jb      short loc_1800B5615
0x1800b55c9  mov     edx, 18h
0x1800b55ce  jmp     loc_1800B5387
0x1800b55d3  cmp     [rdi+88h], rsi
0x1800b55da  jz      short loc_1800B5608
0x1800b55dc  lea     rcx, [rsp+48h+arg_0]
0x1800b55e1  mov     [rsp+48h+arg_0], rsi
0x1800b55e6  call    ?InternalAddRef@?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IAsyncInfo>::InternalAddRef(void)
0x1800b55eb  mov     rcx, [rdi+88h]
0x1800b55f2  mov     [rsp+48h+arg_0], rcx
0x1800b55f7  lea     rcx, [rsp+48h+arg_0]
0x1800b55fc  mov     [rdi+88h], rsi
0x1800b5603  call    ?InternalRelease@?$ComPtr@UIMFVideoProcessorControl@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IMFVideoProcessorControl>::InternalRelease(void)
0x1800b5608  mov     ecx, [rsp+48h+arg_40]
0x1800b560f  mov     [rdi+0A0h], ecx
0x1800b5615  lea     rcx, [rsp+48h+arg_0]; this
0x1800b561a  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800b561f  mov     rbp, [rsp+48h+arg_10]
0x1800b5624  mov     eax, ebx
0x1800b5626  mov     rbx, [rsp+48h+arg_8]
0x1800b562b  add     rsp, 30h
0x1800b562f  pop     r15
0x1800b5631  pop     rdi
0x1800b5632  pop     rsi
0x1800b5633  retn
```
