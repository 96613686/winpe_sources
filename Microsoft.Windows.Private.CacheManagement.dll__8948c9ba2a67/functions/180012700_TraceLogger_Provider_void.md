# TraceLogger::Provider(void)

- ea: `0x180012700`
- end: `0x1800127da`
- name: `?Provider@TraceLogger@@SAPEBU_tlgProvider_t@@XZ`
- size: `218`
- prototype: `const struct _tlgProvider_t *(void)`
- caller_count: `3`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18001f896`
- `0x18001f91a`
- `0x18001fa07`

## callees

- `0x1800121d0`
- `0x180012700`
- `0x1800181b0`
- `0x180018598`

## import_xrefs

- `KERNEL32!InitOnceBeginInitialize` at `0x18001272f`
- `KERNEL32!InitOnceBeginInitialize` at `0x18001272f`
- `KERNEL32!InitOnceComplete` at `0x1800127b4`
- `KERNEL32!InitOnceComplete` at `0x1800127b4`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
const struct _tlgProvider_t *TraceLogger::Provider(void)
{
  void (*v0)(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, void *); // r8
  LPVOID Context; // [rsp+20h] [rbp-28h] BYREF
  BOOL fPending; // [rsp+28h] [rbp-20h] BYREF

  Context = 0;
  if ( InitOnceBeginInitialize(&`TraceLogger::Instance'::`2'::wrapper, 0, &fPending, &Context) && fPending )
  {
    qword_18002E720 = 0;
    Context = &qword_18002E718;
    byte_18002E728 = 0;
    dword_18002E72C = 0;
    qword_18002E718 = &TraceLogger::`vftable';
    qword_18002E730 = (struct _tlgProvider_t *)&`TraceLogger::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(_lambda_77df2b2445264ffccec9000ef713eb53_::_lambda_invoker_cdecl_);
    wil::TraceLoggingProvider::Register((wil::TraceLoggingProvider *)&qword_18002E718, qword_18002E730, v0);
    InitOnceComplete(&`TraceLogger::Instance'::`2'::wrapper, 0, &qword_18002E718);
  }
  return (const struct _tlgProvider_t *)*((_QWORD *)Context + 1);
}

```

## disassembly

```asm
0x180012700  sub     rsp, 48h
0x180012704  mov     rax, cs:__security_cookie
0x18001270b  xor     rax, rsp
0x18001270e  mov     [rsp+48h+var_18], rax
0x180012713  lea     r9, [rsp+48h+Context]; lpContext
0x180012718  mov     [rsp+48h+Context], 0
0x180012721  lea     r8, [rsp+48h+fPending]; fPending
0x180012726  xor     edx, edx; dwFlags
0x180012728  lea     rcx, ?wrapper@?1??Instance@TraceLogger@@KAPEAV2@XZ@4V?$static_lazy@VTraceLogger@@@details@wil@@A; lpInitOnce
0x18001272f  call    cs:__imp_InitOnceBeginInitialize
0x180012735  test    eax, eax
0x180012737  jz      loc_1800127BF
0x18001273d  cmp     [rsp+48h+fPending], 0
0x180012742  jz      short loc_1800127BF
0x180012744  mov     [rsp+48h+var_8], rbx
0x180012749  lea     rax, ??_7TraceLogger@@6B@; const TraceLogger::`vftable'
0x180012750  lea     rbx, qword_18002E718
0x180012757  mov     cs:qword_18002E720, 0
0x180012762  mov     [rsp+48h+Context], rbx
0x180012767  mov     cs:byte_18002E728, 0
0x18001276e  mov     cs:dword_18002E72C, 0
0x180012778  mov     cs:qword_18002E718, rax
0x18001277f  lea     rax, ?__hInner@?1???0StaticHandle@TraceLogger@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `TraceLogger::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x180012786  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_77df2b2445264ffccec9000ef713eb53_@@CA@XZ; void (__cdecl *)()
0x18001278d  mov     cs:qword_18002E730, rax
0x180012794  call    atexit
0x180012799  mov     rdx, cs:qword_18002E730; struct _tlgProvider_t *
0x1800127a0  mov     rcx, rbx; this
0x1800127a3  call    ?Register@TraceLoggingProvider@wil@@IEAAXQEBU_tlgProvider_t@@P6AXPEBU_GUID@@KE_K2PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z@Z; wil::TraceLoggingProvider::Register(_tlgProvider_t const * const,void (*)(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *))
0x1800127a8  mov     r8, rbx; lpContext
0x1800127ab  lea     rcx, ?wrapper@?1??Instance@TraceLogger@@KAPEAV2@XZ@4V?$static_lazy@VTraceLogger@@@details@wil@@A; lpInitOnce
0x1800127b2  xor     edx, edx; dwFlags
0x1800127b4  call    cs:__imp_InitOnceComplete
0x1800127ba  mov     rbx, [rsp+48h+var_8]
0x1800127bf  mov     rax, [rsp+48h+Context]
0x1800127c4  mov     rax, [rax+8]
0x1800127c8  mov     rcx, [rsp+48h+var_18]
0x1800127cd  xor     rcx, rsp; StackCookie
0x1800127d0  call    __security_check_cookie
0x1800127d5  add     rsp, 48h
0x1800127d9  retn
```
