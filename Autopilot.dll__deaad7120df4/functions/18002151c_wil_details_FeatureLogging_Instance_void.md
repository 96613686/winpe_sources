# wil::details::FeatureLogging::Instance(void)

- ea: `0x18002151c`
- end: `0x1800215de`
- name: `?Instance@FeatureLogging@details@wil@@KAPEAV123@XZ`
- size: `194`
- prototype: `struct wil::details::FeatureLogging *(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180020830`

## callees

- `0x1800049e8`
- `0x18000fd60`
- `0x18002151c`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180021544`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180021544`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800215c6`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800215c6`

## pseudocode

```c
struct wil::details::FeatureLogging *wil::details::FeatureLogging::Instance(void)
{
  void (*v0)(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, void *); // r8
  WINBOOL v2; // [rsp+30h] [rbp+8h] BYREF
  LPVOID v3; // [rsp+38h] [rbp+10h] BYREF

  v3 = 0;
  v2 = 0;
  if ( __std_init_once_begin_initialize(&`wil::details::FeatureLogging::Instance'::`2'::wrapper, 0, &v2, &v3) && v2 )
  {
    qword_180044AE8 = 0;
    v3 = &qword_180044AE0;
    qword_180044AE0 = &AutoPilotTelemProvider::`vftable';
    byte_180044AF0 = 0;
    dword_180044AF4 = 0;
    qword_180044AF8 = (struct _tlgProvider_t *)&`wil::details::FeatureLogging::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(_lambda_120d0c6b51dc644cb63ed5c7fc62f6c3_::_lambda_invoker_cdecl_);
    wil::TraceLoggingProvider::Register((wil::TraceLoggingProvider *)&qword_180044AE0, qword_180044AF8, v0);
    InitOnceComplete(&`wil::details::FeatureLogging::Instance'::`2'::wrapper, 0, &qword_180044AE0);
  }
  return (struct wil::details::FeatureLogging *)v3;
}

```

## disassembly

```asm
0x18002151c  mov     rax, rsp
0x18002151f  push    rbx
0x180021520  sub     rsp, 20h
0x180021524  lea     r9, [rax+10h]; lpContext
0x180021528  mov     qword ptr [rax+10h], 0
0x180021530  lea     r8, [rax+8]; fPending
0x180021534  mov     dword ptr [rax+8], 0
0x18002153b  xor     edx, edx; dwFlags
0x18002153d  lea     rcx, ?wrapper@?1??Instance@FeatureLogging@details@wil@@KAPEAV234@XZ@4V?$static_lazy@VFeatureLogging@details@wil@@@34@A; lpInitOnce
0x180021544  call    cs:__imp___std_init_once_begin_initialize
0x18002154b  nop     dword ptr [rax+rax+00h]
0x180021550  test    eax, eax
0x180021552  jz      short loc_1800215D2
0x180021554  cmp     [rsp+28h+arg_0], 0
0x180021559  jz      short loc_1800215D2
0x18002155b  lea     rbx, qword_180044AE0
0x180021562  mov     cs:qword_180044AE8, 0
0x18002156d  lea     rax, ??_7AutoPilotTelemProvider@@6B@; const AutoPilotTelemProvider::`vftable'
0x180021574  mov     [rsp+28h+arg_8], rbx
0x180021579  mov     cs:qword_180044AE0, rax
0x180021580  mov     cs:byte_180044AF0, 0
0x180021587  mov     cs:dword_180044AF4, 0
0x180021591  lea     rax, ?__hInner@?1???0StaticHandle@FeatureLogging@details@wil@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `wil::details::FeatureLogging::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x180021598  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_120d0c6b51dc644cb63ed5c7fc62f6c3_@@CA@XZ; void (__cdecl *)()
0x18002159f  mov     cs:qword_180044AF8, rax
0x1800215a6  call    atexit
0x1800215ab  mov     rdx, cs:qword_180044AF8; struct _tlgProvider_t *
0x1800215b2  mov     rcx, rbx; this
0x1800215b5  call    ?Register@TraceLoggingProvider@wil@@IEAAXQEBU_tlgProvider_t@@P6AXPEBU_GUID@@KE_K2PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z@Z; wil::TraceLoggingProvider::Register(_tlgProvider_t const * const,void (*)(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *))
0x1800215ba  mov     r8, rbx; lpContext
0x1800215bd  lea     rcx, ?wrapper@?1??Instance@FeatureLogging@details@wil@@KAPEAV234@XZ@4V?$static_lazy@VFeatureLogging@details@wil@@@34@A; lpInitOnce
0x1800215c4  xor     edx, edx; dwFlags
0x1800215c6  call    cs:__imp_InitOnceComplete
0x1800215cd  nop     dword ptr [rax+rax+00h]
0x1800215d2  mov     rax, [rsp+28h+arg_8]
0x1800215d7  add     rsp, 20h
0x1800215db  pop     rbx
0x1800215dc  retn
```
