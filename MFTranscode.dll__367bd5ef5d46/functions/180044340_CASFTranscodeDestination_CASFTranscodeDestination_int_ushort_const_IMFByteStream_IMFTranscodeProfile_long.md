# CASFTranscodeDestination::CASFTranscodeDestination(int,ushort const *,IMFByteStream *,IMFTranscodeProfile *,long *)

- ea: `0x180044340`
- end: `0x1800445fa`
- name: `??0CASFTranscodeDestination@@QEAA@HPEBGPEAUIMFByteStream@@PEAUIMFTranscodeProfile@@PEAJ@Z`
- size: `698`
- prototype: `CASFTranscodeDestination *__usercall@<rax>(CASFTranscodeDestination *__hidden this@<rcx>, int@<edx>, const unsigned __int16 *@<r8>, struct IMFByteStream *@<r9>, struct IMFTranscodeProfile *, int *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config`

## callers

- `0x180002f50`

## callees

- `0x1800035c0`
- `0x180004a40`
- `0x180007000`
- `0x180016bf0`
- `0x18001a330`
- `0x18001c280`
- `0x180044340`
- `0x1800446a8`
- `0x180045710`
- `0x18004f410`
- `0x18005a010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800443c6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004446c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004451f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800443c6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004446c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004451f`
- `mfasfsrcsnk!MFCreateASFContentInfo` at `0x1800443aa`
- `mfasfsrcsnk!MFCreateASFContentInfo` at `0x1800443aa`

## pseudocode

```c
CASFTranscodeDestination *__fastcall CASFTranscodeDestination::CASFTranscodeDestination(
        CASFTranscodeDestination *this,
        int a2,
        const unsigned __int16 *a3,
        struct IMFByteStream *a4,
        struct IMFTranscodeProfile *a5,
        int *a6)
{
  int *v7; // rsi
  bool v8; // sf
  __int64 v9; // rdx
  HRESULT inited; // ebx
  __int64 *v11; // rcx
  CallStackTracing *v12; // rax
  struct CallStackContext *v13; // rax
  __int64 v14; // rdx
  __int64 v15; // rdx
  __int64 *v16; // rcx
  CallStackTracing *v17; // rax
  struct CallStackContext *v18; // rax
  __int64 v19; // rdx
  __int64 *v20; // rcx
  CallStackTracing *v21; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  IMFASFContentInfo *ppIContentInfo; // [rsp+40h] [rbp+8h] BYREF

  v7 = a6;
  CTranscodeDestination::CTranscodeDestination(this, a2, a3, a4, a5, a6);
  *(_QWORD *)this = &CASFTranscodeDestination::`vftable';
  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)&a6,
    "CASFTranscodeDestination::CASFTranscodeDestination",
    33);
  v8 = *v7 < 0;
  ppIContentInfo = 0;
  *((_QWORD *)this + 9) = 0;
  if ( v8 )
    goto LABEL_40;
  inited = MFCreateASFContentInfo(&ppIContentInfo);
  if ( inited >= 0 )
  {
    inited = CASFTranscodeDestination::ConfigContentInfo(this, ppIContentInfo);
    if ( inited >= 0 )
    {
      *((_QWORD *)this + 9) = ppIContentInfo;
      ppIContentInfo = 0;
      inited = CASFTranscodeDestination::InitSinkInfo(this);
      if ( inited >= 0 )
        goto LABEL_36;
      v20 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v21 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v19);
        CallStackTracing::s_wpInstance = v21;
        if ( v21 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v21 + 8LL))(v21, 2032) )
        {
          v20 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v20 = &qword_180069A90;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
        }
      }
      if ( *((_BYTE *)v20 + 8) )
      {
        ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v20);
        if ( *((_DWORD *)ThreadRelativeContext + 499) != inited )
          CallStackContext::TraceFailure(
            ThreadRelativeContext,
            "CASFTranscodeDestination::CASFTranscodeDestination",
            50,
            inited);
      }
      if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        goto LABEL_36;
      v14 = 13;
    }
    else
    {
      v16 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v17 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v15);
        CallStackTracing::s_wpInstance = v17;
        if ( v17 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v17 + 8LL))(v17, 2032) )
        {
          v16 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v16 = &qword_180069A90;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
        }
      }
      if ( *((_BYTE *)v16 + 8) )
      {
        v18 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v16);
        if ( *((_DWORD *)v18 + 499) != inited )
          CallStackContext::TraceFailure(v18, "CASFTranscodeDestination::CASFTranscodeDestination", 45, inited);
      }
      if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        goto LABEL_36;
      v14 = 12;
    }
  }
  else
  {
    v11 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v12 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v9);
      CallStackTracing::s_wpInstance = v12;
      if ( v12 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v12 + 8LL))(v12, 2032) )
      {
        v11 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v11 = &qword_180069A90;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
      }
    }
    if ( *((_BYTE *)v11 + 8) )
    {
      v13 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v11);
      if ( *((_DWORD *)v13 + 499) != inited )
        CallStackContext::TraceFailure(v13, "CASFTranscodeDestination::CASFTranscodeDestination", 44, inited);
    }
    if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      goto LABEL_36;
    v14 = 11;
  }
  WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), v14, &WPP_0a758c1def7e3974366218a1d0d46647_Traceguids, this, inited);
LABEL_36:
  if ( *v7 >= 0 )
    *v7 = inited;
  if ( ppIContentInfo )
  {
    ((void (__fastcall *)(IMFASFContentInfo *))ppIContentInfo->lpVtbl->Release)(ppIContentInfo);
    ppIContentInfo = 0;
  }
LABEL_40:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&a6);
  return this;
}

```

## disassembly

```asm
0x180044340  mov     r11, rsp
0x180044343  mov     [r11+10h], rbx
0x180044347  mov     [r11+18h], rsi
0x18004434b  push    rdi
0x18004434c  sub     rsp, 30h
0x180044350  mov     rax, [rsp+38h+arg_20]
0x180044355  mov     rdi, rcx
0x180044358  mov     rsi, [rsp+38h+arg_28]
0x18004435d  mov     [r11-10h], rsi
0x180044361  mov     [r11-18h], rax
0x180044365  call    ??0CTranscodeDestination@@QEAA@HPEBGPEAUIMFByteStream@@PEAUIMFTranscodeProfile@@PEAJ@Z; CTranscodeDestination::CTranscodeDestination(int,ushort const *,IMFByteStream *,IMFTranscodeProfile *,long *)
0x18004436a  lea     rax, ??_7CASFTranscodeDestination@@6B@; const CASFTranscodeDestination::`vftable'
0x180044371  mov     r8d, 21h ; '!'; int
0x180044377  lea     rdx, aCasftranscoded_5; "CASFTranscodeDestination::CASFTranscode"...
0x18004437e  mov     [rdi], rax
0x180044381  lea     rcx, [rsp+38h+arg_28]; this
0x180044386  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18004438b  cmp     dword ptr [rsi], 0
0x18004438e  mov     [rsp+38h+ppIContentInfo], 0
0x180044397  mov     qword ptr [rdi+48h], 0
0x18004439f  jl      loc_1800445DD
0x1800443a5  lea     rcx, [rsp+38h+ppIContentInfo]; ppIContentInfo
0x1800443aa  call    cs:__imp_MFCreateASFContentInfo
0x1800443b0  mov     ebx, eax
0x1800443b2  test    eax, eax
0x1800443b4  jns     loc_180044449
0x1800443ba  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800443c1  test    rcx, rcx
0x1800443c4  jnz     short loc_180044407
0x1800443c6  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800443cc  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800443d3  mov     rcx, rax
0x1800443d6  test    rax, rax
0x1800443d9  jz      short loc_1800443F9
0x1800443db  mov     rax, [rax]
0x1800443de  mov     edx, 7F0h
0x1800443e3  mov     rax, [rax+8]
0x1800443e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800443ec  test    eax, eax
0x1800443ee  jz      short loc_1800443F9
0x1800443f0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800443f7  jmp     short loc_180044407
0x1800443f9  lea     rcx, qword_180069A90; this
0x180044400  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180044407  cmp     byte ptr [rcx+8], 0
0x18004440b  jz      short loc_180044432
0x18004440d  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180044412  cmp     [rax+7CCh], ebx
0x180044418  jz      short loc_180044432
0x18004441a  mov     r9d, ebx; int
0x18004441d  lea     rdx, aCasftranscoded_5; "CASFTranscodeDestination::CASFTranscode"...
0x180044424  mov     r8d, 2Ch ; ','; int
0x18004442a  mov     rcx, rax; this
0x18004442d  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180044432  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180044437  cmp     al, 1
0x180044439  jb      loc_1800445B7
0x18004443f  mov     edx, 0Bh
0x180044444  jmp     loc_180044599
0x180044449  mov     rdx, [rsp+38h+ppIContentInfo]; struct IMFASFContentInfo *
0x18004444e  mov     rcx, rdi; this
0x180044451  call    ?ConfigContentInfo@CASFTranscodeDestination@@IEAAJPEAUIMFASFContentInfo@@@Z; CASFTranscodeDestination::ConfigContentInfo(IMFASFContentInfo *)
0x180044456  mov     ebx, eax
0x180044458  test    eax, eax
0x18004445a  jns     loc_1800444EF
0x180044460  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180044467  test    rcx, rcx
0x18004446a  jnz     short loc_1800444AD
0x18004446c  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180044472  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180044479  mov     rcx, rax
0x18004447c  test    rax, rax
0x18004447f  jz      short loc_18004449F
0x180044481  mov     rax, [rax]
0x180044484  mov     edx, 7F0h
0x180044489  mov     rax, [rax+8]
0x18004448d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044492  test    eax, eax
0x180044494  jz      short loc_18004449F
0x180044496  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004449d  jmp     short loc_1800444AD
0x18004449f  lea     rcx, qword_180069A90; this
0x1800444a6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800444ad  cmp     byte ptr [rcx+8], 0
0x1800444b1  jz      short loc_1800444D8
0x1800444b3  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800444b8  cmp     [rax+7CCh], ebx
0x1800444be  jz      short loc_1800444D8
0x1800444c0  mov     r9d, ebx; int
0x1800444c3  lea     rdx, aCasftranscoded_5; "CASFTranscodeDestination::CASFTranscode"...
0x1800444ca  mov     r8d, 2Dh ; '-'; int
0x1800444d0  mov     rcx, rax; this
0x1800444d3  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800444d8  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1800444dd  cmp     al, 1
0x1800444df  jb      loc_1800445B7
0x1800444e5  mov     edx, 0Ch
0x1800444ea  jmp     loc_180044599
0x1800444ef  mov     rax, [rsp+38h+ppIContentInfo]
0x1800444f4  mov     rcx, rdi; this
0x1800444f7  mov     [rdi+48h], rax
0x1800444fb  mov     [rsp+38h+ppIContentInfo], 0
0x180044504  call    ?InitSinkInfo@CASFTranscodeDestination@@MEAAJXZ; CASFTranscodeDestination::InitSinkInfo(void)
0x180044509  mov     ebx, eax
0x18004450b  test    eax, eax
0x18004450d  jns     loc_1800445B7
0x180044513  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004451a  test    rcx, rcx
0x18004451d  jnz     short loc_180044560
0x18004451f  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180044525  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004452c  mov     rcx, rax
0x18004452f  test    rax, rax
0x180044532  jz      short loc_180044552
0x180044534  mov     rax, [rax]
0x180044537  mov     edx, 7F0h
0x18004453c  mov     rax, [rax+8]
0x180044540  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044545  test    eax, eax
0x180044547  jz      short loc_180044552
0x180044549  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180044550  jmp     short loc_180044560
0x180044552  lea     rcx, qword_180069A90; this
0x180044559  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180044560  cmp     byte ptr [rcx+8], 0
0x180044564  jz      short loc_18004458B
0x180044566  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004456b  cmp     [rax+7CCh], ebx
0x180044571  jz      short loc_18004458B
0x180044573  mov     r9d, ebx; int
0x180044576  lea     rdx, aCasftranscoded_5; "CASFTranscodeDestination::CASFTranscode"...
0x18004457d  mov     r8d, 32h ; '2'; int
0x180044583  mov     rcx, rax; this
0x180044586  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004458b  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180044590  cmp     al, 1
0x180044592  jb      short loc_1800445B7
0x180044594  mov     edx, 0Dh
0x180044599  mov     rcx, cs:WPP_GLOBAL_Control
0x1800445a0  lea     r8, WPP_0a758c1def7e3974366218a1d0d46647_Traceguids
0x1800445a7  mov     r9, rdi
0x1800445aa  mov     [rsp+38h+var_18], ebx
0x1800445ae  mov     rcx, [rcx+10h]
0x1800445b2  call    WPP_SF_qd
0x1800445b7  cmp     dword ptr [rsi], 0
0x1800445ba  jl      short loc_1800445BE
0x1800445bc  mov     [rsi], ebx
0x1800445be  mov     rcx, [rsp+38h+ppIContentInfo]
0x1800445c3  test    rcx, rcx
0x1800445c6  jz      short loc_1800445DD
0x1800445c8  mov     rax, [rcx]
0x1800445cb  mov     rax, [rax+10h]
0x1800445cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800445d4  mov     [rsp+38h+ppIContentInfo], 0
0x1800445dd  lea     rcx, [rsp+38h+arg_28]; this
0x1800445e2  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800445e7  mov     rbx, [rsp+38h+arg_8]
0x1800445ec  mov     rax, rdi
0x1800445ef  mov     rsi, [rsp+38h+arg_10]
0x1800445f4  add     rsp, 30h
0x1800445f8  pop     rdi
0x1800445f9  retn
```
