# CStreamWriter::CStreamWriter(IStream *,long *)

- ea: `0x18004f718`
- end: `0x18004f830`
- name: `??0CStreamWriter@@QEAA@PEAUIStream@@PEAJ@Z`
- size: `280`
- prototype: `CStreamWriter *__fastcall(CStreamWriter *__hidden this, struct IStream *, int *)`
- caller_count: `2`
- callee_count: `8`
- tags: ``

## callers

- `0x18001b5c0`
- `0x180033df0`

## callees

- `0x1800035c0`
- `0x180004a40`
- `0x180007000`
- `0x18001a330`
- `0x18001c280`
- `0x18004f410`
- `0x18004f718`
- `0x18005a010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004f766`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004f766`

## string_xrefs

- `0x18004f73a`: `CStreamWriter::CStreamWriter`
- `0x18004f7c2`: `CStreamWriter::CStreamWriter`

## pseudocode

```c
CStreamWriter *__fastcall CStreamWriter::CStreamWriter(CStreamWriter *this, struct IStream *a2, int *a3)
{
  __int64 v5; // rdx
  __int64 *v6; // rcx
  CallStackTracing *v7; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  char v10; // [rsp+50h] [rbp+18h] BYREF

  *((_QWORD *)this + 1) = 0;
  *(_QWORD *)this = &CStreamWriter::`vftable';
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v10, "CStreamWriter::CStreamWriter", 25);
  if ( a2 )
  {
    *((_QWORD *)this + 1) = a2;
    ((void (__fastcall *)(struct IStream *))a2->lpVtbl->AddRef)(a2);
  }
  else
  {
    v6 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v7 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v5);
      CallStackTracing::s_wpInstance = v7;
      if ( v7 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v7 + 8LL))(v7, 2032) )
      {
        v6 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v6 = &qword_180069A90;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
      }
    }
    if ( *((_BYTE *)v6 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v6);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != -2147467261 )
        CallStackContext::TraceFailure(ThreadRelativeContext, "CStreamWriter::CStreamWriter", 25, -2147467261);
    }
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      WPP_SF_qd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        10,
        WPP_6dd5de0f919434228b32263d8b482734_Traceguids,
        this,
        -2147467261);
  }
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v10);
  return this;
}

```

## disassembly

```asm
0x18004f718  mov     [rsp+arg_0], rbx
0x18004f71d  push    rdi
0x18004f71e  sub     rsp, 30h
0x18004f722  lea     rax, ??_7CStreamWriter@@6B@; const CStreamWriter::`vftable'
0x18004f729  mov     qword ptr [rcx+8], 0
0x18004f731  mov     [rcx], rax
0x18004f734  mov     rdi, rdx
0x18004f737  mov     rbx, rcx
0x18004f73a  lea     rdx, aCstreamwriterC; "CStreamWriter::CStreamWriter"
0x18004f741  lea     rcx, [rsp+38h+arg_10]; this
0x18004f746  mov     r8d, 19h; int
0x18004f74c  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18004f751  test    rdi, rdi
0x18004f754  jnz     loc_18004F805
0x18004f75a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004f761  test    rcx, rcx
0x18004f764  jnz     short loc_18004F7A7
0x18004f766  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004f76c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004f773  mov     rcx, rax
0x18004f776  test    rax, rax
0x18004f779  jz      short loc_18004F799
0x18004f77b  mov     rax, [rax]
0x18004f77e  mov     edx, 7F0h
0x18004f783  mov     rax, [rax+8]
0x18004f787  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f78c  test    eax, eax
0x18004f78e  jz      short loc_18004F799
0x18004f790  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004f797  jmp     short loc_18004F7A7
0x18004f799  lea     rcx, qword_180069A90; this
0x18004f7a0  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004f7a7  cmp     byte ptr [rcx+8], 0
0x18004f7ab  mov     edi, 80004003h
0x18004f7b0  jz      short loc_18004F7D7
0x18004f7b2  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004f7b7  cmp     [rax+7CCh], edi
0x18004f7bd  jz      short loc_18004F7D7
0x18004f7bf  mov     r9d, edi; int
0x18004f7c2  lea     rdx, aCstreamwriterC; "CStreamWriter::CStreamWriter"
0x18004f7c9  mov     r8d, 19h; int
0x18004f7cf  mov     rcx, rax; this
0x18004f7d2  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004f7d7  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18004f7dc  cmp     al, 1
0x18004f7de  jb      short loc_18004F818
0x18004f7e0  mov     rcx, cs:WPP_GLOBAL_Control
0x18004f7e7  lea     r8, WPP_6dd5de0f919434228b32263d8b482734_Traceguids
0x18004f7ee  mov     edx, 0Ah
0x18004f7f3  mov     [rsp+38h+var_18], edi
0x18004f7f7  mov     r9, rbx
0x18004f7fa  mov     rcx, [rcx+10h]
0x18004f7fe  call    WPP_SF_qd
0x18004f803  jmp     short loc_18004F818
0x18004f805  mov     [rbx+8], rdi
0x18004f809  mov     rcx, rdi
0x18004f80c  mov     rax, [rdi]
0x18004f80f  mov     rax, [rax+8]
0x18004f813  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f818  lea     rcx, [rsp+38h+arg_10]; this
0x18004f81d  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18004f822  mov     rax, rbx
0x18004f825  mov     rbx, [rsp+38h+arg_0]
0x18004f82a  add     rsp, 30h
0x18004f82e  pop     rdi
0x18004f82f  retn
```
