# CStreamReader::CStreamReader(IStream *,long *)

- ea: `0x18004f5f8`
- end: `0x18004f710`
- name: `??0CStreamReader@@QEAA@PEAUIStream@@PEAJ@Z`
- size: `280`
- prototype: `CStreamReader *__fastcall(CStreamReader *__hidden this, struct IStream *, int *)`
- caller_count: `2`
- callee_count: `8`
- tags: ``

## callers

- `0x18001aaf0`
- `0x1800332d0`

## callees

- `0x1800035c0`
- `0x180004a40`
- `0x180007000`
- `0x18001a330`
- `0x18001c280`
- `0x18004f410`
- `0x18004f5f8`
- `0x18005a010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004f646`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004f646`

## string_xrefs

- `0x18004f61a`: `CStreamReader::CStreamReader`
- `0x18004f6a2`: `CStreamReader::CStreamReader`

## pseudocode

```c
CStreamReader *__fastcall CStreamReader::CStreamReader(CStreamReader *this, struct IStream *a2, int *a3)
{
  __int64 v5; // rdx
  __int64 *v6; // rcx
  CallStackTracing *v7; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  char v10; // [rsp+50h] [rbp+18h] BYREF

  *((_QWORD *)this + 1) = 0;
  *(_QWORD *)this = &CStreamReader::`vftable';
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v10, "CStreamReader::CStreamReader", 134);
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
        CallStackContext::TraceFailure(ThreadRelativeContext, "CStreamReader::CStreamReader", 134, -2147467261);
    }
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      WPP_SF_qd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        23,
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
0x18004f5f8  mov     [rsp+arg_0], rbx
0x18004f5fd  push    rdi
0x18004f5fe  sub     rsp, 30h
0x18004f602  lea     rax, ??_7CStreamReader@@6B@; const CStreamReader::`vftable'
0x18004f609  mov     qword ptr [rcx+8], 0
0x18004f611  mov     [rcx], rax
0x18004f614  mov     rdi, rdx
0x18004f617  mov     rbx, rcx
0x18004f61a  lea     rdx, aCstreamreaderC; "CStreamReader::CStreamReader"
0x18004f621  lea     rcx, [rsp+38h+arg_10]; this
0x18004f626  mov     r8d, 86h; int
0x18004f62c  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18004f631  test    rdi, rdi
0x18004f634  jnz     loc_18004F6E5
0x18004f63a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004f641  test    rcx, rcx
0x18004f644  jnz     short loc_18004F687
0x18004f646  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004f64c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004f653  mov     rcx, rax
0x18004f656  test    rax, rax
0x18004f659  jz      short loc_18004F679
0x18004f65b  mov     rax, [rax]
0x18004f65e  mov     edx, 7F0h
0x18004f663  mov     rax, [rax+8]
0x18004f667  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f66c  test    eax, eax
0x18004f66e  jz      short loc_18004F679
0x18004f670  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004f677  jmp     short loc_18004F687
0x18004f679  lea     rcx, qword_180069A90; this
0x18004f680  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004f687  cmp     byte ptr [rcx+8], 0
0x18004f68b  mov     edi, 80004003h
0x18004f690  jz      short loc_18004F6B7
0x18004f692  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004f697  cmp     [rax+7CCh], edi
0x18004f69d  jz      short loc_18004F6B7
0x18004f69f  mov     r9d, edi; int
0x18004f6a2  lea     rdx, aCstreamreaderC; "CStreamReader::CStreamReader"
0x18004f6a9  mov     r8d, 86h; int
0x18004f6af  mov     rcx, rax; this
0x18004f6b2  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004f6b7  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18004f6bc  cmp     al, 1
0x18004f6be  jb      short loc_18004F6F8
0x18004f6c0  mov     rcx, cs:WPP_GLOBAL_Control
0x18004f6c7  lea     r8, WPP_6dd5de0f919434228b32263d8b482734_Traceguids
0x18004f6ce  mov     edx, 17h
0x18004f6d3  mov     [rsp+38h+var_18], edi
0x18004f6d7  mov     r9, rbx
0x18004f6da  mov     rcx, [rcx+10h]
0x18004f6de  call    WPP_SF_qd
0x18004f6e3  jmp     short loc_18004F6F8
0x18004f6e5  mov     [rbx+8], rdi
0x18004f6e9  mov     rcx, rdi
0x18004f6ec  mov     rax, [rdi]
0x18004f6ef  mov     rax, [rax+8]
0x18004f6f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f6f8  lea     rcx, [rsp+38h+arg_10]; this
0x18004f6fd  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18004f702  mov     rax, rbx
0x18004f705  mov     rbx, [rsp+38h+arg_0]
0x18004f70a  add     rsp, 30h
0x18004f70e  pop     rdi
0x18004f70f  retn
```
