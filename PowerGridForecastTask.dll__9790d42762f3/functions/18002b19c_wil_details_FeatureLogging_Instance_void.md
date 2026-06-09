# wil::details::FeatureLogging::Instance(void)

- ea: `0x18002b19c`
- end: `0x18002b251`
- name: `?Instance@FeatureLogging@details@wil@@KAPEAV123@XZ`
- size: `181`
- prototype: `struct wil::details::FeatureLogging *(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180029c00`

## callees

- `0x180026710`
- `0x18002b19c`
- `0x18002d360`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18002b1c4`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18002b1c4`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18002b240`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18002b240`

## pseudocode

```c
struct wil::details::FeatureLogging *wil::details::FeatureLogging::Instance(void)
{
  void (*v0)(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, void *); // r8
  BOOL v2; // [rsp+30h] [rbp+8h] BYREF
  LPVOID v3; // [rsp+38h] [rbp+10h] BYREF

  v3 = 0;
  v2 = 0;
  if ( InitOnceBeginInitialize(&`wil::details::FeatureLogging::Instance'::`2'::wrapper, 0, &v2, &v3) && v2 )
  {
    qword_180047068 = 0;
    v3 = &qword_180047060;
    qword_180047060 = &PowerGridForecastTaskTelemetry::`vftable';
    byte_180047070 = 0;
    dword_180047074 = 0;
    qword_180047078 = (struct _tlgProvider_t *)&`wil::details::FeatureLogging::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(_lambda_120d0c6b51dc644cb63ed5c7fc62f6c3_::_lambda_invoker_cdecl_);
    wil::TraceLoggingProvider::Register((wil::TraceLoggingProvider *)&qword_180047060, qword_180047078, v0);
    InitOnceComplete(&`wil::details::FeatureLogging::Instance'::`2'::wrapper, 0, &qword_180047060);
  }
  return (struct wil::details::FeatureLogging *)v3;
}

```

## disassembly

```asm
0x18002b19c  mov     rax, rsp
0x18002b19f  push    rbx
0x18002b1a0  sub     rsp, 20h
0x18002b1a4  lea     r9, [rax+10h]; lpContext
0x18002b1a8  mov     qword ptr [rax+10h], 0
0x18002b1b0  lea     r8, [rax+8]; fPending
0x18002b1b4  mov     dword ptr [rax+8], 0
0x18002b1bb  xor     edx, edx; dwFlags
0x18002b1bd  lea     rcx, ?wrapper@?1??Instance@FeatureLogging@details@wil@@KAPEAV234@XZ@4V?$static_lazy@VFeatureLogging@details@wil@@@34@A; lpInitOnce
0x18002b1c4  call    cs:__imp_InitOnceBeginInitialize
0x18002b1ca  test    eax, eax
0x18002b1cc  jz      short loc_18002B246
0x18002b1ce  cmp     [rsp+28h+arg_0], 0
0x18002b1d3  jz      short loc_18002B246
0x18002b1d5  lea     rbx, qword_180047060
0x18002b1dc  mov     cs:qword_180047068, 0
0x18002b1e7  lea     rax, ??_7PowerGridForecastTaskTelemetry@@6B@; const PowerGridForecastTaskTelemetry::`vftable'
0x18002b1ee  mov     [rsp+28h+arg_8], rbx
0x18002b1f3  mov     cs:qword_180047060, rax
0x18002b1fa  mov     cs:byte_180047070, 0
0x18002b201  mov     cs:dword_180047074, 0
0x18002b20b  lea     rax, ?__hInner@?1???0StaticHandle@FeatureLogging@details@wil@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `wil::details::FeatureLogging::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x18002b212  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_120d0c6b51dc644cb63ed5c7fc62f6c3_@@CA@XZ; void (__cdecl *)()
0x18002b219  mov     cs:qword_180047078, rax
0x18002b220  call    atexit
0x18002b225  mov     rdx, cs:qword_180047078; struct _tlgProvider_t *
0x18002b22c  mov     rcx, rbx; this
0x18002b22f  call    ?Register@TraceLoggingProvider@wil@@IEAAXQEBU_tlgProvider_t@@P6AXPEBU_GUID@@KE_K2PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z@Z; wil::TraceLoggingProvider::Register(_tlgProvider_t const * const,void (*)(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *))
0x18002b234  mov     r8, rbx; lpContext
0x18002b237  lea     rcx, ?wrapper@?1??Instance@FeatureLogging@details@wil@@KAPEAV234@XZ@4V?$static_lazy@VFeatureLogging@details@wil@@@34@A; lpInitOnce
0x18002b23e  xor     edx, edx; dwFlags
0x18002b240  call    cs:__imp_InitOnceComplete
0x18002b246  mov     rax, [rsp+28h+arg_8]
0x18002b24b  add     rsp, 20h
0x18002b24f  pop     rbx
0x18002b250  retn
```
