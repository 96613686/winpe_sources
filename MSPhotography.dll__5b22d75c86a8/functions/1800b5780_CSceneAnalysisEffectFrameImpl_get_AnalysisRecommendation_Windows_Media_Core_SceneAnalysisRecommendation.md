# CSceneAnalysisEffectFrameImpl::get_AnalysisRecommendation(Windows::Media::Core::SceneAnalysisRecommendation *)

- ea: `0x1800b5780`
- end: `0x1800b58d4`
- name: `?get_AnalysisRecommendation@CSceneAnalysisEffectFrameImpl@@UEAAJPEAW4SceneAnalysisRecommendation@Core@Media@Windows@@@Z`
- size: `340`
- prototype: `__int64 __fastcall(CSceneAnalysisEffectFrameImpl *__hidden this, enum Windows::Media::Core::SceneAnalysisRecommendation *)`
- caller_count: `0`
- callee_count: `11`
- tags: `broker_com_uri`

## callees

- `0x18000b480`
- `0x18000b490`
- `0x18000c0b8`
- `0x18000c0f8`
- `0x18002a9bc`
- `0x18002ae0c`
- `0x18002afd0`
- `0x1800a75a0`
- `0x1800b5780`
- `0x18012f850`
- `0x180142010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b57f6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b57f6`

## string_xrefs

- `0x1800b578f`: `CSceneAnalysisEffectFrameImpl::get_AnalysisRecommendation`
- `0x1800b5851`: `CSceneAnalysisEffectFrameImpl::get_AnalysisRecommendation`

## pseudocode

```c
__int64 __fastcall CSceneAnalysisEffectFrameImpl::get_AnalysisRecommendation(
        CSceneAnalysisEffectFrameImpl *this,
        enum Windows::Media::Core::SceneAnalysisRecommendation *a2)
{
  int v4; // edx
  int v5; // eax
  __int64 *v6; // rcx
  int v7; // ebx
  CallStackTracing *v8; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  char v11; // [rsp+68h] [rbp+10h] BYREF

  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)&v11,
    "CSceneAnalysisEffectFrameImpl::get_AnalysisRecommendation",
    211);
  if ( _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel() >= 0x20u )
    WPP_SF_q(
      *((_QWORD *)WPP_GLOBAL_Control + 27),
      35,
      &WPP_2cb6b193ea5b3f7c59b28ba1ce3630e6_Traceguids,
      (char *)this - 104);
  if ( a2 )
  {
    v7 = 0;
    *(_DWORD *)a2 = *((_DWORD *)this + 14);
    if ( _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel() >= 0x20u )
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 27),
        37,
        &WPP_2cb6b193ea5b3f7c59b28ba1ce3630e6_Traceguids,
        (char *)this - 104,
        *((_DWORD *)this + 14));
  }
  else
  {
    v5 = Windows::Media::Report((Windows::Media *)0x80004003LL, v4);
    v6 = (__int64 *)CallStackTracing::s_wpInstance;
    v7 = v5;
    if ( !CallStackTracing::s_wpInstance )
    {
      v8 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
      CallStackTracing::s_wpInstance = v8;
      if ( v8 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v8 + 8LL))(v8, 2032) )
      {
        v6 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v6 = &qword_18015FF10;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18015FF10;
      }
    }
    if ( *((_BYTE *)v6 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v6);
      if ( v7 < 0 && *((_DWORD *)ThreadRelativeContext + 499) != v7 )
        CallStackContext::TraceFailure(
          ThreadRelativeContext,
          "CSceneAnalysisEffectFrameImpl::get_AnalysisRecommendation",
          213,
          v7);
    }
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        36,
        &WPP_2cb6b193ea5b3f7c59b28ba1ce3630e6_Traceguids,
        (char *)this - 104,
        v7);
  }
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v11);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800b5780  push    rbx
0x1800b5782  push    rbp
0x1800b5783  push    rsi
0x1800b5784  push    rdi
0x1800b5785  sub     rsp, 38h
0x1800b5789  mov     rsi, rdx
0x1800b578c  mov     rbp, rcx
0x1800b578f  lea     rdx, aCsceneanalysis_13; "CSceneAnalysisEffectFrameImpl::get_Anal"...
0x1800b5796  mov     r8d, 0D3h; int
0x1800b579c  lea     rcx, [rsp+58h+arg_8]; this
0x1800b57a1  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800b57a6  lea     rdi, [rbp-68h]
0x1800b57aa  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_CORE_MFTS@@SAEXZ; _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel(void)
0x1800b57af  cmp     al, 20h ; ' '
0x1800b57b1  jb      short loc_1800B57D5
0x1800b57b3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b57ba  lea     r8, WPP_2cb6b193ea5b3f7c59b28ba1ce3630e6_Traceguids
0x1800b57c1  mov     edx, 23h ; '#'
0x1800b57c6  mov     r9, rdi
0x1800b57c9  mov     rcx, [rcx+0D8h]
0x1800b57d0  call    WPP_SF_q
0x1800b57d5  test    rsi, rsi
0x1800b57d8  jnz     loc_1800B5885
0x1800b57de  mov     ecx, 80004003h; this
0x1800b57e3  call    ?Report@Media@Windows@@YAJJ@Z; Windows::Media::Report(long)
0x1800b57e8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b57ef  mov     ebx, eax
0x1800b57f1  test    rcx, rcx
0x1800b57f4  jnz     short loc_1800B5837
0x1800b57f6  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800b57fc  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b5803  mov     rcx, rax
0x1800b5806  test    rax, rax
0x1800b5809  jz      short loc_1800B5829
0x1800b580b  mov     rdx, [rax]
0x1800b580e  mov     rax, [rdx+8]
0x1800b5812  mov     edx, 7F0h
0x1800b5817  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b581c  test    eax, eax
0x1800b581e  jz      short loc_1800B5829
0x1800b5820  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b5827  jmp     short loc_1800B5837
0x1800b5829  lea     rcx, qword_18015FF10; this
0x1800b5830  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b5837  cmp     byte ptr [rcx+8], 0
0x1800b583b  jz      short loc_1800B5866
0x1800b583d  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800b5842  test    ebx, ebx
0x1800b5844  jns     short loc_1800B5866
0x1800b5846  cmp     [rax+7CCh], ebx
0x1800b584c  jz      short loc_1800B5866
0x1800b584e  mov     r9d, ebx; int
0x1800b5851  lea     rdx, aCsceneanalysis_13; "CSceneAnalysisEffectFrameImpl::get_Anal"...
0x1800b5858  mov     r8d, 0D5h; int
0x1800b585e  mov     rcx, rax; this
0x1800b5861  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800b5866  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1800b586b  cmp     al, 1
0x1800b586d  jb      short loc_1800B58BF
0x1800b586f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b5876  mov     edx, 24h ; '$'
0x1800b587b  mov     [rsp+58h+var_38], ebx
0x1800b587f  mov     rcx, [rcx+10h]
0x1800b5883  jmp     short loc_1800B58B0
0x1800b5885  mov     eax, [rdi+0A0h]
0x1800b588b  xor     ebx, ebx
0x1800b588d  mov     [rsi], eax
0x1800b588f  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_CORE_MFTS@@SAEXZ; _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel(void)
0x1800b5894  cmp     al, 20h ; ' '
0x1800b5896  jb      short loc_1800B58BF
0x1800b5898  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b589f  lea     edx, [rbx+25h]
0x1800b58a2  mov     eax, [rbp+38h]
0x1800b58a5  mov     [rsp+58h+var_38], eax
0x1800b58a9  mov     rcx, [rcx+0D8h]
0x1800b58b0  mov     r9, rdi
0x1800b58b3  lea     r8, WPP_2cb6b193ea5b3f7c59b28ba1ce3630e6_Traceguids
0x1800b58ba  call    WPP_SF_qD
0x1800b58bf  lea     rcx, [rsp+58h+arg_8]; this
0x1800b58c4  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800b58c9  mov     eax, ebx
0x1800b58cb  add     rsp, 38h
0x1800b58cf  pop     rdi
0x1800b58d0  pop     rsi
0x1800b58d1  pop     rbp
0x1800b58d2  pop     rbx
0x1800b58d3  retn
```
