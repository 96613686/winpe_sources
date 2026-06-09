# CSceneAnalysisMFT::SetupSampleAnalysis(IMFSample *)

- ea: `0x1800b00f0`
- end: `0x1800b0514`
- name: `?SetupSampleAnalysis@CSceneAnalysisMFT@@AEAAJPEAUIMFSample@@@Z`
- size: `1060`
- prototype: `__int64 __fastcall(CSceneAnalysisMFT *__hidden this, struct IMFSample *)`
- caller_count: `1`
- callee_count: `19`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800ae510`

## callees

- `0x1800016b0`
- `0x180001784`
- `0x180005660`
- `0x180009784`
- `0x18000c0f8`
- `0x18000fcdc`
- `0x180015fb8`
- `0x18002a9bc`
- `0x18002ae0c`
- `0x18002afd0`
- `0x1800ada38`
- `0x1800aece4`
- `0x1800b00f0`
- `0x18012f808`
- `0x18012f850`
- `0x180132010`
- `0x180134abc`
- `0x1801357e0`
- `0x1801358a8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800b0145`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800b0145`
- `MFPlat!MFCreateAsyncResult` at `0x1800b036a`
- `MFPlat!MFCreateAsyncResult` at `0x1800b036a`

## pseudocode

```c
__int64 __fastcall CSceneAnalysisMFT::SetupSampleAnalysis(CSceneAnalysisMFT *this, struct IMFSample *a2)
{
  RTL_SRWLOCK *v4; // rcx
  int NecessaryAttributes; // ebx
  CallStackTracing *v6; // rcx
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v8; // rdx
  CallStackTracing *v9; // rcx
  struct CallStackContext *v10; // rax
  CallStackTracing *v11; // rcx
  struct CallStackContext *v12; // rax
  __int64 v13; // rdx
  RTL_SRWLOCK *v14; // r10
  int v15; // eax
  RTL_SRWLOCK *v16; // r10
  PSRWLOCK v17; // rcx
  CallStackTracing *v18; // rcx
  struct CallStackContext *v19; // rax
  CallStackTracing *v20; // rcx
  struct CallStackContext *v21; // rax
  CallStackTracing *v22; // rcx
  struct CallStackContext *v23; // rax
  CAggregatePhotographyTelemetry *v24; // rcx
  int v25; // ecx
  int v26; // r8d
  int v27; // r9d
  char *v29; // [rsp+50h] [rbp-20h] BYREF
  const char *v30; // [rsp+58h] [rbp-18h] BYREF
  __int64 v31; // [rsp+60h] [rbp-10h] BYREF
  PSRWLOCK SRWLock; // [rsp+A0h] [rbp+30h] BYREF
  int v33; // [rsp+B0h] [rbp+40h] BYREF
  IMFAsyncResult *ppAsyncResult; // [rsp+B8h] [rbp+48h] BYREF

  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)&SRWLock,
    "CSceneAnalysisMFT::SetupSampleAnalysis",
    294);
  ppAsyncResult = 0;
  Microsoft::WRL::Wrappers::SRWLock::LockExclusive(&SRWLock, (char *)this + 368);
  v4 = SRWLock;
  *((_BYTE *)this + 433) = 1;
  if ( v4 )
    ReleaseSRWLockExclusive(v4);
  NecessaryAttributes = CSceneAnalysisMFT::ExtractNecessaryAttributes(this, a2);
  if ( NecessaryAttributes < 0 )
  {
    v6 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::InitInstance();
      v6 = CallStackTracing::s_wpInstance;
    }
    if ( *((_BYTE *)v6 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(v6);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != NecessaryAttributes )
        CallStackContext::TraceFailure(
          ThreadRelativeContext,
          "CSceneAnalysisMFT::SetupSampleAnalysis",
          303,
          NecessaryAttributes);
    }
    if ( !g_wppLevels )
      goto LABEL_58;
    v8 = 46;
    goto LABEL_57;
  }
  if ( *((_BYTE *)this + 432) )
  {
    NecessaryAttributes = CCoreMFT::ConfigureXVP(
                            this,
                            *((struct IMFMediaType **)this + 14),
                            *((struct IMFMediaType **)this + 14),
                            a2);
    if ( NecessaryAttributes < 0 )
    {
      v9 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::InitInstance();
        v9 = CallStackTracing::s_wpInstance;
      }
      if ( *((_BYTE *)v9 + 8) )
      {
        v10 = CallStackTracing::GetThreadRelativeContext(v9);
        if ( *((_DWORD *)v10 + 499) != NecessaryAttributes )
          CallStackContext::TraceFailure(v10, "CSceneAnalysisMFT::SetupSampleAnalysis", 309, NecessaryAttributes);
      }
      if ( !g_wppLevels )
        goto LABEL_58;
      v8 = 47;
      goto LABEL_57;
    }
    *((_BYTE *)this + 432) = 0;
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 440);
  NecessaryAttributes = CCoreMFT::XVPConvertSample(this, a2, (struct IMFSample **)this + 55, 0);
  if ( NecessaryAttributes < 0 )
  {
    v11 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::InitInstance();
      v11 = CallStackTracing::s_wpInstance;
    }
    if ( *((_BYTE *)v11 + 8) )
    {
      v12 = CallStackTracing::GetThreadRelativeContext(v11);
      if ( *((_DWORD *)v12 + 499) != NecessaryAttributes )
        CallStackContext::TraceFailure(v12, "CSceneAnalysisMFT::SetupSampleAnalysis", 315, NecessaryAttributes);
    }
    if ( !g_wppLevels )
      goto LABEL_58;
    v8 = 48;
    goto LABEL_57;
  }
  v13 = *((_QWORD *)this + 47);
  v14 = (RTL_SRWLOCK *)*((_QWORD *)this + 93);
  SRWLock = v14;
  if ( v13 > *((_QWORD *)this + 12) )
  {
    v15 = LongLongAdd((__int64)v14, v13 - *((_QWORD *)this + 12), (__int64 *)&SRWLock);
    v17 = SRWLock;
    if ( v15 < 0 )
      v17 = v16;
    v14 = v17;
  }
  NecessaryAttributes = CCoreMFT::UpdateDeadline(this, (__int64)v14);
  if ( NecessaryAttributes < 0 )
  {
    v18 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::InitInstance();
      v18 = CallStackTracing::s_wpInstance;
    }
    if ( *((_BYTE *)v18 + 8) )
    {
      v19 = CallStackTracing::GetThreadRelativeContext(v18);
      if ( *((_DWORD *)v19 + 499) != NecessaryAttributes )
        CallStackContext::TraceFailure(v19, "CSceneAnalysisMFT::SetupSampleAnalysis", 329, NecessaryAttributes);
    }
    if ( !g_wppLevels )
      goto LABEL_58;
    v8 = 49;
    goto LABEL_57;
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppAsyncResult);
  NecessaryAttributes = MFCreateAsyncResult(0, (IMFAsyncCallback *)this + 44, 0, &ppAsyncResult);
  if ( NecessaryAttributes < 0 )
  {
    v20 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::InitInstance();
      v20 = CallStackTracing::s_wpInstance;
    }
    if ( *((_BYTE *)v20 + 8) )
    {
      v21 = CallStackTracing::GetThreadRelativeContext(v20);
      if ( *((_DWORD *)v21 + 499) != NecessaryAttributes )
        CallStackContext::TraceFailure(v21, "CSceneAnalysisMFT::SetupSampleAnalysis", 332, NecessaryAttributes);
    }
    if ( !g_wppLevels )
      goto LABEL_58;
    v8 = 50;
    goto LABEL_57;
  }
  NecessaryAttributes = CCoreMFT::PutWorkItem(this, ppAsyncResult);
  if ( NecessaryAttributes >= 0 )
    goto LABEL_63;
  v22 = CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    CallStackTracing::InitInstance();
    v22 = CallStackTracing::s_wpInstance;
  }
  if ( *((_BYTE *)v22 + 8) )
  {
    v23 = CallStackTracing::GetThreadRelativeContext(v22);
    if ( *((_DWORD *)v23 + 499) != NecessaryAttributes )
      CallStackContext::TraceFailure(v23, "CSceneAnalysisMFT::SetupSampleAnalysis", 333, NecessaryAttributes);
  }
  if ( g_wppLevels )
  {
    v8 = 51;
LABEL_57:
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v8,
      &WPP_a042ef2f2a7a38ff6a18b622801eb737_Traceguids,
      this,
      NecessaryAttributes);
  }
LABEL_58:
  v24 = (CAggregatePhotographyTelemetry *)*((_QWORD *)this + 92);
  if ( v24 )
  {
    CAggregatePhotographyTelemetry::AddData(v24, 4u, 0.0);
    if ( (unsigned int)dword_18015F0D0 > 5 )
    {
      if ( (unsigned __int8)tlgKeywordOn(&dword_18015F0D0, 0x400000000000LL) )
      {
        LODWORD(SRWLock) = NecessaryAttributes;
        v29 = (char *)this + 752;
        v33 = 1;
        v30 = "SceneAnalysis";
        v31 = 0x1000000;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(
          v25,
          (unsigned int)byte_180152B8B,
          v26,
          v27,
          (__int64)&v31,
          (__int64)&v30,
          (__int64)&v33,
          (__int64)&v29,
          (__int64)&SRWLock);
      }
    }
  }
  CSceneAnalysisMFT::ResetAnalysisState(this);
LABEL_63:
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppAsyncResult);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&SRWLock);
  return (unsigned int)NecessaryAttributes;
}

```

## disassembly

```asm
0x1800b00f0  push    rbp
0x1800b00f2  push    rbx
0x1800b00f3  push    rsi
0x1800b00f4  push    rdi
0x1800b00f5  push    r12
0x1800b00f7  mov     rbp, rsp
0x1800b00fa  sub     rsp, 70h
0x1800b00fe  mov     rsi, rdx
0x1800b0101  lea     r12, aCsceneanalysis_17; "CSceneAnalysisMFT::SetupSampleAnalysis"
0x1800b0108  mov     rdi, rcx
0x1800b010b  mov     rdx, r12; char *
0x1800b010e  mov     r8d, 126h; int
0x1800b0114  lea     rcx, [rbp+SRWLock]; this
0x1800b0118  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800b011d  lea     rdx, [rdi+170h]
0x1800b0124  mov     [rbp+ppAsyncResult], 0
0x1800b012c  lea     rcx, [rbp+SRWLock]
0x1800b0130  call    ?LockExclusive@SRWLock@Wrappers@WRL@Microsoft@@SA?AVSyncLockExclusive@Details@234@PEAU_RTL_SRWLOCK@@@Z; Microsoft::WRL::Wrappers::SRWLock::LockExclusive(_RTL_SRWLOCK *)
0x1800b0135  mov     rcx, [rbp+SRWLock]; SRWLock
0x1800b0139  mov     byte ptr [rdi+1B1h], 1
0x1800b0140  test    rcx, rcx
0x1800b0143  jz      short loc_1800B014B
0x1800b0145  call    cs:__imp_ReleaseSRWLockExclusive
0x1800b014b  mov     rdx, rsi; struct IMFSample *
0x1800b014e  mov     rcx, rdi; this
0x1800b0151  call    ?ExtractNecessaryAttributes@CSceneAnalysisMFT@@AEAAJPEAUIMFSample@@@Z; CSceneAnalysisMFT::ExtractNecessaryAttributes(IMFSample *)
0x1800b0156  mov     ebx, eax
0x1800b0158  test    eax, eax
0x1800b015a  jns     short loc_1800B01B2
0x1800b015c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b0163  test    rcx, rcx
0x1800b0166  jnz     short loc_1800B0174
0x1800b0168  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x1800b016d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800b0174  cmp     byte ptr [rcx+8], 0
0x1800b0178  jz      short loc_1800B019B
0x1800b017a  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800b017f  cmp     [rax+7CCh], ebx
0x1800b0185  jz      short loc_1800B019B
0x1800b0187  mov     r9d, ebx; int
0x1800b018a  mov     r8d, 12Fh; int
0x1800b0190  mov     rdx, r12; char *
0x1800b0193  mov     rcx, rax; this
0x1800b0196  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800b019b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800b01a2  jb      loc_1800B044A
0x1800b01a8  mov     edx, 2Eh ; '.'
0x1800b01ad  jmp     loc_1800B042C
0x1800b01b2  cmp     byte ptr [rdi+1B0h], 0
0x1800b01b9  jz      short loc_1800B0230
0x1800b01bb  mov     rdx, [rdi+70h]; struct IMFMediaType *
0x1800b01bf  mov     r9, rsi; struct IMFSample *
0x1800b01c2  mov     r8, rdx; struct IMFMediaType *
0x1800b01c5  mov     rcx, rdi; this
0x1800b01c8  call    ?ConfigureXVP@CCoreMFT@@IEAAJPEAUIMFMediaType@@0PEAUIMFSample@@@Z; CCoreMFT::ConfigureXVP(IMFMediaType *,IMFMediaType *,IMFSample *)
0x1800b01cd  mov     ebx, eax
0x1800b01cf  test    eax, eax
0x1800b01d1  jns     short loc_1800B0229
0x1800b01d3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b01da  test    rcx, rcx
0x1800b01dd  jnz     short loc_1800B01EB
0x1800b01df  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x1800b01e4  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800b01eb  cmp     byte ptr [rcx+8], 0
0x1800b01ef  jz      short loc_1800B0212
0x1800b01f1  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800b01f6  cmp     [rax+7CCh], ebx
0x1800b01fc  jz      short loc_1800B0212
0x1800b01fe  mov     r9d, ebx; int
0x1800b0201  mov     r8d, 135h; int
0x1800b0207  mov     rdx, r12; char *
0x1800b020a  mov     rcx, rax; this
0x1800b020d  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800b0212  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800b0219  jb      loc_1800B044A
0x1800b021f  mov     edx, 2Fh ; '/'
0x1800b0224  jmp     loc_1800B042C
0x1800b0229  mov     byte ptr [rdi+1B0h], 0
0x1800b0230  lea     rbx, [rdi+1B8h]
0x1800b0237  mov     rcx, rbx
0x1800b023a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800b023f  xor     r9d, r9d; struct tagRECT *
0x1800b0242  mov     [rsp+70h+var_50], 0; struct tagRECT *
0x1800b024b  mov     r8, rbx; struct IMFSample **
0x1800b024e  mov     rdx, rsi; struct IMFSample *
0x1800b0251  mov     rcx, rdi; this
0x1800b0254  call    ?XVPConvertSample@CCoreMFT@@IEAAJPEAUIMFSample@@PEAPEAU2@PEAUtagRECT@@2@Z; CCoreMFT::XVPConvertSample(IMFSample *,IMFSample * *,tagRECT *,tagRECT *)
0x1800b0259  mov     ebx, eax
0x1800b025b  test    eax, eax
0x1800b025d  jns     short loc_1800B02B5
0x1800b025f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b0266  test    rcx, rcx
0x1800b0269  jnz     short loc_1800B0277
0x1800b026b  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x1800b0270  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800b0277  cmp     byte ptr [rcx+8], 0
0x1800b027b  jz      short loc_1800B029E
0x1800b027d  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800b0282  cmp     [rax+7CCh], ebx
0x1800b0288  jz      short loc_1800B029E
0x1800b028a  mov     r9d, ebx; int
0x1800b028d  mov     r8d, 13Bh; int
0x1800b0293  mov     rdx, r12; char *
0x1800b0296  mov     rcx, rax; this
0x1800b0299  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800b029e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800b02a5  jb      loc_1800B044A
0x1800b02ab  mov     edx, 30h ; '0'
0x1800b02b0  jmp     loc_1800B042C
0x1800b02b5  mov     rdx, [rdi+178h]
0x1800b02bc  mov     r10, [rdi+2E8h]
0x1800b02c3  mov     [rbp+SRWLock], r10
0x1800b02c7  cmp     rdx, [rdi+60h]
0x1800b02cb  jle     short loc_1800B02EA
0x1800b02cd  sub     rdx, [rdi+60h]; __int64
0x1800b02d1  lea     r8, [rbp+SRWLock]; __int64 *
0x1800b02d5  mov     rcx, r10; __int64
0x1800b02d8  call    ?LongLongAdd@@YAJ_J0PEA_J@Z; LongLongAdd(__int64,__int64,__int64 *)
0x1800b02dd  mov     rcx, [rbp+SRWLock]
0x1800b02e1  test    eax, eax
0x1800b02e3  cmovs   rcx, r10
0x1800b02e7  mov     r10, rcx
0x1800b02ea  mov     rdx, r10; __int64
0x1800b02ed  mov     rcx, rdi; this
0x1800b02f0  call    ?UpdateDeadline@CCoreMFT@@IEAAJ_J@Z; CCoreMFT::UpdateDeadline(__int64)
0x1800b02f5  mov     ebx, eax
0x1800b02f7  test    eax, eax
0x1800b02f9  jns     short loc_1800B0351
0x1800b02fb  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b0302  test    rcx, rcx
0x1800b0305  jnz     short loc_1800B0313
0x1800b0307  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x1800b030c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800b0313  cmp     byte ptr [rcx+8], 0
0x1800b0317  jz      short loc_1800B033A
0x1800b0319  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800b031e  cmp     [rax+7CCh], ebx
0x1800b0324  jz      short loc_1800B033A
0x1800b0326  mov     r9d, ebx; int
0x1800b0329  mov     r8d, 149h; int
0x1800b032f  mov     rdx, r12; char *
0x1800b0332  mov     rcx, rax; this
0x1800b0335  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800b033a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800b0341  jb      loc_1800B044A
0x1800b0347  mov     edx, 31h ; '1'
0x1800b034c  jmp     loc_1800B042C
0x1800b0351  lea     rcx, [rbp+ppAsyncResult]
0x1800b0355  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800b035a  lea     rdx, [rdi+160h]; pCallback
0x1800b0361  xor     r8d, r8d; punkState
0x1800b0364  lea     r9, [rbp+ppAsyncResult]; ppAsyncResult
0x1800b0368  xor     ecx, ecx; punkObject
0x1800b036a  call    cs:__imp_MFCreateAsyncResult
0x1800b0370  mov     ebx, eax
0x1800b0372  test    eax, eax
0x1800b0374  jns     short loc_1800B03C9
0x1800b0376  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b037d  test    rcx, rcx
0x1800b0380  jnz     short loc_1800B038E
0x1800b0382  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x1800b0387  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800b038e  cmp     byte ptr [rcx+8], 0
0x1800b0392  jz      short loc_1800B03B5
0x1800b0394  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800b0399  cmp     [rax+7CCh], ebx
0x1800b039f  jz      short loc_1800B03B5
0x1800b03a1  mov     r9d, ebx; int
0x1800b03a4  mov     r8d, 14Ch; int
0x1800b03aa  mov     rdx, r12; char *
0x1800b03ad  mov     rcx, rax; this
0x1800b03b0  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800b03b5  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800b03bc  jb      loc_1800B044A
0x1800b03c2  mov     edx, 32h ; '2'
0x1800b03c7  jmp     short loc_1800B042C
0x1800b03c9  mov     rdx, [rbp+ppAsyncResult]; struct IMFAsyncResult *
0x1800b03cd  mov     rcx, rdi; this
0x1800b03d0  call    ?PutWorkItem@CCoreMFT@@IEAAJPEAUIMFAsyncResult@@@Z; CCoreMFT::PutWorkItem(IMFAsyncResult *)
0x1800b03d5  mov     ebx, eax
0x1800b03d7  test    eax, eax
0x1800b03d9  jns     loc_1800B04F5
0x1800b03df  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b03e6  test    rcx, rcx
0x1800b03e9  jnz     short loc_1800B03F7
0x1800b03eb  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x1800b03f0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800b03f7  cmp     byte ptr [rcx+8], 0
0x1800b03fb  jz      short loc_1800B041E
0x1800b03fd  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800b0402  cmp     [rax+7CCh], ebx
0x1800b0408  jz      short loc_1800B041E
0x1800b040a  mov     r9d, ebx; int
0x1800b040d  mov     r8d, 14Dh; int
0x1800b0413  mov     rdx, r12; char *
0x1800b0416  mov     rcx, rax; this
0x1800b0419  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800b041e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800b0425  jb      short loc_1800B044A
0x1800b0427  mov     edx, 33h ; '3'
0x1800b042c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b0433  lea     r8, WPP_a042ef2f2a7a38ff6a18b622801eb737_Traceguids
0x1800b043a  mov     r9, rdi
0x1800b043d  mov     dword ptr [rsp+70h+var_50], ebx
0x1800b0441  mov     rcx, [rcx+10h]
0x1800b0445  call    WPP_SF_qD
0x1800b044a  mov     rcx, [rdi+2E0h]; this
0x1800b0451  test    rcx, rcx
0x1800b0454  jz      loc_1800B04ED
0x1800b045a  xorps   xmm2, xmm2; double
0x1800b045d  mov     edx, 4; unsigned int
0x1800b0462  call    ?AddData@CAggregatePhotographyTelemetry@@QEAAXKN@Z; CAggregatePhotographyTelemetry::AddData(ulong,double)
0x1800b0467  mov     eax, cs:dword_18015F0D0
0x1800b046d  cmp     eax, 5
0x1800b0470  jbe     short loc_1800B04ED
0x1800b0472  mov     rdx, 400000000000h
0x1800b047c  lea     rcx, dword_18015F0D0
0x1800b0483  call    _tlgKeywordOn
0x1800b0488  test    al, al
0x1800b048a  jz      short loc_1800B04ED
0x1800b048c  lea     rax, [rdi+2F0h]
0x1800b0493  mov     dword ptr [rbp+SRWLock], ebx
0x1800b0496  mov     [rbp+var_20], rax
0x1800b049a  lea     rdx, byte_180152B8B
0x1800b04a1  lea     rax, Str2; "SceneAnalysis"
0x1800b04a8  mov     [rbp+arg_10], 1
0x1800b04af  mov     [rbp+var_18], rax
0x1800b04b3  lea     rax, [rbp+SRWLock]
0x1800b04b7  mov     [rsp+70h+var_30], rax
0x1800b04bc  lea     rax, [rbp+var_20]
0x1800b04c0  mov     [rsp+70h+var_38], rax
0x1800b04c5  lea     rax, [rbp+arg_10]
0x1800b04c9  mov     [rsp+70h+var_40], rax
0x1800b04ce  lea     rax, [rbp+var_18]
0x1800b04d2  mov     [rsp+70h+var_48], rax
0x1800b04d7  lea     rax, [rbp+var_10]
0x1800b04db  mov     [rsp+70h+var_50], rax
0x1800b04e0  mov     [rbp+var_10], 1000000h
0x1800b04e8  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByRef@$0BA@@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByRef@$0BA@@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &)
0x1800b04ed  mov     rcx, rdi; this
0x1800b04f0  call    ?ResetAnalysisState@CSceneAnalysisMFT@@AEAAXXZ; CSceneAnalysisMFT::ResetAnalysisState(void)
0x1800b04f5  lea     rcx, [rbp+ppAsyncResult]
0x1800b04f9  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800b04fe  lea     rcx, [rbp+SRWLock]; this
0x1800b0502  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800b0507  mov     eax, ebx
0x1800b0509  add     rsp, 70h
0x1800b050d  pop     r12
0x1800b050f  pop     rdi
0x1800b0510  pop     rsi
0x1800b0511  pop     rbx
0x1800b0512  pop     rbp
0x1800b0513  retn
```
