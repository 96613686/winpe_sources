# CASFTranscodeDestination::GetOutputActivate(ulong,IMFActivate * *)

- ea: `0x180044f40`
- end: `0x1800451e9`
- name: `?GetOutputActivate@CASFTranscodeDestination@@UEAAJKPEAPEAUIMFActivate@@@Z`
- size: `681`
- prototype: `__int64 __fastcall(CASFTranscodeDestination *__hidden this, unsigned int, struct IMFActivate **)`
- caller_count: `0`
- callee_count: `10`
- tags: ``

## callees

- `0x1800035c0`
- `0x180004a40`
- `0x180007000`
- `0x18000f05c`
- `0x18001a330`
- `0x18001c280`
- `0x180042bd0`
- `0x180044f40`
- `0x18004f410`
- `0x18005a010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180044fb1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180045061`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180045119`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180044fb1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180045061`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180045119`
- `mfasfsrcsnk!MFCreateASFMediaSinkActivate` at `0x180045045`
- `mfasfsrcsnk!MFCreateASFMediaSinkActivate` at `0x180045045`
- `mfasfsrcsnk!MFCreateASFMediaSinkActivateFromByteStream` at `0x180044f95`
- `mfasfsrcsnk!MFCreateASFMediaSinkActivateFromByteStream` at `0x180044f95`

## pseudocode

```c
__int64 __fastcall CASFTranscodeDestination::GetOutputActivate(
        CASFTranscodeDestination *this,
        unsigned int a2,
        struct IMFActivate **a3)
{
  bool v6; // zf
  __int64 v7; // rcx
  __int64 v8; // rdx
  __int64 v9; // rdx
  HRESULT OutputActivate; // ebx
  __int64 *v11; // rcx
  CallStackTracing *v12; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v14; // rdx
  const WCHAR *v15; // rax
  IMFASFContentInfo *v16; // rdx
  __int64 v17; // rdx
  __int64 *v18; // rcx
  CallStackTracing *v19; // rax
  struct CallStackContext *v20; // rax
  __int64 v21; // rdx
  __int64 *v22; // rcx
  CallStackTracing *v23; // rax
  struct CallStackContext *v24; // rax
  char v26; // [rsp+50h] [rbp+8h] BYREF
  IMFActivate *ppIActivate; // [rsp+68h] [rbp+20h] BYREF

  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)&v26,
    "CASFTranscodeDestination::GetOutputActivate",
    176);
  v6 = *((_QWORD *)this + 7) == 0;
  ppIActivate = 0;
  if ( !v6 )
    goto LABEL_26;
  v7 = *((_QWORD *)this + 5);
  v8 = *((_QWORD *)this + 9);
  if ( v7 )
  {
    OutputActivate = MFCreateASFMediaSinkActivateFromByteStream(v7, v8, &ppIActivate);
    if ( OutputActivate < 0 )
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
        ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v11);
        if ( *((_DWORD *)ThreadRelativeContext + 499) != OutputActivate )
          CallStackContext::TraceFailure(
            ThreadRelativeContext,
            "CASFTranscodeDestination::GetOutputActivate",
            187,
            OutputActivate);
      }
      if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      {
        v14 = 17;
LABEL_37:
        WPP_SF_qd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v14,
          &WPP_0a758c1def7e3974366218a1d0d46647_Traceguids,
          this,
          OutputActivate);
        goto LABEL_38;
      }
      goto LABEL_38;
    }
    goto LABEL_25;
  }
  v15 = (const WCHAR *)CMFBaseStringT<unsigned short>::PContents((char *)this + 16, v8);
  OutputActivate = MFCreateASFMediaSinkActivate(v15, v16, &ppIActivate);
  if ( OutputActivate >= 0 )
  {
LABEL_25:
    *((_QWORD *)this + 7) = ppIActivate;
    ppIActivate = 0;
LABEL_26:
    OutputActivate = CTranscodeDestination::GetOutputActivate(this, a2, a3);
    if ( OutputActivate < 0 )
    {
      v22 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v23 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v21);
        CallStackTracing::s_wpInstance = v23;
        if ( v23 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v23 + 8LL))(v23, 2032) )
        {
          v22 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v22 = &qword_180069A90;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
        }
      }
      if ( *((_BYTE *)v22 + 8) )
      {
        v24 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v22);
        if ( *((_DWORD *)v24 + 499) != OutputActivate )
          CallStackContext::TraceFailure(v24, "CASFTranscodeDestination::GetOutputActivate", 200, OutputActivate);
      }
      if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      {
        v14 = 19;
        goto LABEL_37;
      }
    }
    goto LABEL_38;
  }
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
    if ( *((_DWORD *)v20 + 499) != OutputActivate )
      CallStackContext::TraceFailure(v20, "CASFTranscodeDestination::GetOutputActivate", 193, OutputActivate);
  }
  if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
  {
    v14 = 18;
    goto LABEL_37;
  }
LABEL_38:
  if ( ppIActivate )
  {
    ((void (__fastcall *)(IMFActivate *))ppIActivate->lpVtbl->Release)(ppIActivate);
    ppIActivate = 0;
  }
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v26);
  return (unsigned int)OutputActivate;
}

```

## disassembly

```asm
0x180044f40  mov     [rsp+arg_8], rbx
0x180044f45  push    rbp
0x180044f46  push    rsi
0x180044f47  push    rdi
0x180044f48  sub     rsp, 30h
0x180044f4c  mov     rsi, r8
0x180044f4f  mov     ebp, edx
0x180044f51  mov     rdi, rcx
0x180044f54  lea     rdx, aCasftranscoded_2; "CASFTranscodeDestination::GetOutputActi"...
0x180044f5b  mov     r8d, 0B0h; int
0x180044f61  lea     rcx, [rsp+48h+arg_0]; this
0x180044f66  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180044f6b  cmp     qword ptr [rdi+38h], 0
0x180044f70  mov     [rsp+48h+ppIActivate], 0
0x180044f79  jnz     loc_1800450F6
0x180044f7f  mov     rcx, [rdi+28h]
0x180044f83  mov     rdx, [rdi+48h]
0x180044f87  test    rcx, rcx
0x180044f8a  jz      loc_180045034
0x180044f90  lea     r8, [rsp+48h+ppIActivate]
0x180044f95  call    cs:__imp_MFCreateASFMediaSinkActivateFromByteStream
0x180044f9b  mov     ebx, eax
0x180044f9d  test    eax, eax
0x180044f9f  jns     loc_1800450E4
0x180044fa5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180044fac  test    rcx, rcx
0x180044faf  jnz     short loc_180044FF2
0x180044fb1  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180044fb7  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180044fbe  mov     rcx, rax
0x180044fc1  test    rax, rax
0x180044fc4  jz      short loc_180044FE4
0x180044fc6  mov     rax, [rax]
0x180044fc9  mov     edx, 7F0h
0x180044fce  mov     rax, [rax+8]
0x180044fd2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044fd7  test    eax, eax
0x180044fd9  jz      short loc_180044FE4
0x180044fdb  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180044fe2  jmp     short loc_180044FF2
0x180044fe4  lea     rcx, qword_180069A90; this
0x180044feb  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180044ff2  cmp     byte ptr [rcx+8], 0
0x180044ff6  jz      short loc_18004501D
0x180044ff8  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180044ffd  cmp     [rax+7CCh], ebx
0x180045003  jz      short loc_18004501D
0x180045005  mov     r9d, ebx; int
0x180045008  lea     rdx, aCasftranscoded_2; "CASFTranscodeDestination::GetOutputActi"...
0x18004500f  mov     r8d, 0BBh; int
0x180045015  mov     rcx, rax; this
0x180045018  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004501d  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180045022  cmp     al, 1
0x180045024  jb      loc_1800451B1
0x18004502a  mov     edx, 11h
0x18004502f  jmp     loc_180045193
0x180045034  lea     rcx, [rdi+10h]
0x180045038  call    ?PContents@?$CMFBaseStringT@G@@QEBAPEBGXZ; CMFBaseStringT<ushort>::PContents(void)
0x18004503d  mov     rcx, rax; pwszFileName
0x180045040  lea     r8, [rsp+48h+ppIActivate]; ppIActivate
0x180045045  call    cs:__imp_MFCreateASFMediaSinkActivate
0x18004504b  mov     ebx, eax
0x18004504d  test    eax, eax
0x18004504f  jns     loc_1800450E4
0x180045055  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004505c  test    rcx, rcx
0x18004505f  jnz     short loc_1800450A2
0x180045061  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180045067  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004506e  mov     rcx, rax
0x180045071  test    rax, rax
0x180045074  jz      short loc_180045094
0x180045076  mov     rax, [rax]
0x180045079  mov     edx, 7F0h
0x18004507e  mov     rax, [rax+8]
0x180045082  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045087  test    eax, eax
0x180045089  jz      short loc_180045094
0x18004508b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180045092  jmp     short loc_1800450A2
0x180045094  lea     rcx, qword_180069A90; this
0x18004509b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800450a2  cmp     byte ptr [rcx+8], 0
0x1800450a6  jz      short loc_1800450CD
0x1800450a8  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800450ad  cmp     [rax+7CCh], ebx
0x1800450b3  jz      short loc_1800450CD
0x1800450b5  mov     r9d, ebx; int
0x1800450b8  lea     rdx, aCasftranscoded_2; "CASFTranscodeDestination::GetOutputActi"...
0x1800450bf  mov     r8d, 0C1h; int
0x1800450c5  mov     rcx, rax; this
0x1800450c8  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800450cd  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1800450d2  cmp     al, 1
0x1800450d4  jb      loc_1800451B1
0x1800450da  mov     edx, 12h
0x1800450df  jmp     loc_180045193
0x1800450e4  mov     rax, [rsp+48h+ppIActivate]
0x1800450e9  mov     [rdi+38h], rax
0x1800450ed  mov     [rsp+48h+ppIActivate], 0
0x1800450f6  mov     r8, rsi; struct IMFActivate **
0x1800450f9  mov     edx, ebp; unsigned int
0x1800450fb  mov     rcx, rdi; this
0x1800450fe  call    ?GetOutputActivate@CTranscodeDestination@@UEAAJKPEAPEAUIMFActivate@@@Z; CTranscodeDestination::GetOutputActivate(ulong,IMFActivate * *)
0x180045103  mov     ebx, eax
0x180045105  test    eax, eax
0x180045107  jns     loc_1800451B1
0x18004510d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180045114  test    rcx, rcx
0x180045117  jnz     short loc_18004515A
0x180045119  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004511f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180045126  mov     rcx, rax
0x180045129  test    rax, rax
0x18004512c  jz      short loc_18004514C
0x18004512e  mov     rax, [rax]
0x180045131  mov     edx, 7F0h
0x180045136  mov     rax, [rax+8]
0x18004513a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004513f  test    eax, eax
0x180045141  jz      short loc_18004514C
0x180045143  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004514a  jmp     short loc_18004515A
0x18004514c  lea     rcx, qword_180069A90; this
0x180045153  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004515a  cmp     byte ptr [rcx+8], 0
0x18004515e  jz      short loc_180045185
0x180045160  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180045165  cmp     [rax+7CCh], ebx
0x18004516b  jz      short loc_180045185
0x18004516d  mov     r9d, ebx; int
0x180045170  lea     rdx, aCasftranscoded_2; "CASFTranscodeDestination::GetOutputActi"...
0x180045177  mov     r8d, 0C8h; int
0x18004517d  mov     rcx, rax; this
0x180045180  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180045185  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18004518a  cmp     al, 1
0x18004518c  jb      short loc_1800451B1
0x18004518e  mov     edx, 13h
0x180045193  mov     rcx, cs:WPP_GLOBAL_Control
0x18004519a  lea     r8, WPP_0a758c1def7e3974366218a1d0d46647_Traceguids
0x1800451a1  mov     r9, rdi
0x1800451a4  mov     [rsp+48h+var_28], ebx
0x1800451a8  mov     rcx, [rcx+10h]
0x1800451ac  call    WPP_SF_qd
0x1800451b1  mov     rcx, [rsp+48h+ppIActivate]
0x1800451b6  test    rcx, rcx
0x1800451b9  jz      short loc_1800451D0
0x1800451bb  mov     rax, [rcx]
0x1800451be  mov     rax, [rax+10h]
0x1800451c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800451c7  mov     [rsp+48h+ppIActivate], 0
0x1800451d0  lea     rcx, [rsp+48h+arg_0]; this
0x1800451d5  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800451da  mov     eax, ebx
0x1800451dc  mov     rbx, [rsp+48h+arg_8]
0x1800451e1  add     rsp, 30h
0x1800451e5  pop     rdi
0x1800451e6  pop     rsi
0x1800451e7  pop     rbp
0x1800451e8  retn
```
