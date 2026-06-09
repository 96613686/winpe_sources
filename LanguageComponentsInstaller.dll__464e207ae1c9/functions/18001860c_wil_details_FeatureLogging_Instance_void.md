# wil::details::FeatureLogging::Instance(void)

- ea: `0x18001860c`
- end: `0x1800186df`
- name: `?Instance@FeatureLogging@details@wil@@KAPEAV123@XZ`
- size: `211`
- prototype: `struct wil::details::FeatureLogging *(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180016320`

## callees

- `0x180003520`
- `0x180003a08`
- `0x18001860c`
- `0x18001a9c0`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800186c1`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800186c1`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180018645`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180018645`

## pseudocode

```c
struct wil::details::FeatureLogging *wil::details::FeatureLogging::Instance(void)
{
  void (*v0)(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, void *); // r8
  LPVOID Context; // [rsp+20h] [rbp-28h] BYREF
  WINBOOL fPending; // [rsp+28h] [rbp-20h] BYREF

  Context = 0;
  fPending = 0;
  if ( InitOnceBeginInitialize(&`wil::details::FeatureLogging::Instance'::`2'::wrapper, 0, &fPending, &Context)
    && fPending )
  {
    qword_180037810 = 0;
    Context = &qword_180037808;
    qword_180037808 = &wil::details::FeatureLogging::`vftable';
    byte_180037818 = 0;
    dword_18003781C = 0;
    qword_180037820 = (struct _tlgProvider_t *)&`wil::details::FeatureLogging::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(_lambda_120d0c6b51dc644cb63ed5c7fc62f6c3_::_lambda_invoker_cdecl_);
    wil::TraceLoggingProvider::Register((wil::TraceLoggingProvider *)&qword_180037808, qword_180037820, v0);
    InitOnceComplete(&`wil::details::FeatureLogging::Instance'::`2'::wrapper, 0, &qword_180037808);
  }
  return (struct wil::details::FeatureLogging *)Context;
}

```

## disassembly

```asm
0x18001860c  push    rbx
0x18001860e  sub     rsp, 40h
0x180018612  mov     rax, cs:__security_cookie
0x180018619  xor     rax, rsp
0x18001861c  mov     [rsp+48h+var_18], rax
0x180018621  lea     r9, [rsp+48h+Context]; lpContext
0x180018626  mov     [rsp+48h+Context], 0
0x18001862f  lea     r8, [rsp+48h+fPending]; fPending
0x180018634  mov     [rsp+48h+fPending], 0
0x18001863c  xor     edx, edx; dwFlags
0x18001863e  lea     rcx, ?wrapper@?1??Instance@FeatureLogging@details@wil@@KAPEAV234@XZ@4V?$static_lazy@VFeatureLogging@details@wil@@@34@A; lpInitOnce
0x180018645  call    cs:__imp_InitOnceBeginInitialize
0x18001864b  test    eax, eax
0x18001864d  jz      short loc_1800186C7
0x18001864f  cmp     [rsp+48h+fPending], 0
0x180018654  jz      short loc_1800186C7
0x180018656  lea     rbx, qword_180037808
0x18001865d  mov     cs:qword_180037810, 0
0x180018668  lea     rax, ??_7FeatureLogging@details@wil@@6B@; const wil::details::FeatureLogging::`vftable'
0x18001866f  mov     [rsp+48h+Context], rbx
0x180018674  mov     cs:qword_180037808, rax
0x18001867b  mov     cs:byte_180037818, 0
0x180018682  mov     cs:dword_18003781C, 0
0x18001868c  lea     rax, ?__hInner@?1???0StaticHandle@FeatureLogging@details@wil@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `wil::details::FeatureLogging::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x180018693  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_120d0c6b51dc644cb63ed5c7fc62f6c3_@@CA@XZ; void (__cdecl *)()
0x18001869a  mov     cs:qword_180037820, rax
0x1800186a1  call    atexit
0x1800186a6  mov     rdx, cs:qword_180037820; struct _tlgProvider_t *
0x1800186ad  mov     rcx, rbx; this
0x1800186b0  call    ?Register@TraceLoggingProvider@wil@@IEAAXQEBU_tlgProvider_t@@P6AXPEBU_GUID@@KE_K2PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z@Z; wil::TraceLoggingProvider::Register(_tlgProvider_t const * const,void (*)(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *))
0x1800186b5  mov     r8, rbx; lpContext
0x1800186b8  lea     rcx, ?wrapper@?1??Instance@FeatureLogging@details@wil@@KAPEAV234@XZ@4V?$static_lazy@VFeatureLogging@details@wil@@@34@A; lpInitOnce
0x1800186bf  xor     edx, edx; dwFlags
0x1800186c1  call    cs:__imp_InitOnceComplete
0x1800186c7  mov     rax, [rsp+48h+Context]
0x1800186cc  mov     rcx, [rsp+48h+var_18]
0x1800186d1  xor     rcx, rsp; StackCookie
0x1800186d4  call    __security_check_cookie
0x1800186d9  add     rsp, 40h
0x1800186dd  pop     rbx
0x1800186de  retn
```
