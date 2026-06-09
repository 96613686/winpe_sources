# AIXTelemetryLogging::Provider(void)

- ea: `0x18000896c`
- end: `0x180008a25`
- name: `?Provider@AIXTelemetryLogging@@SAPEBU_tlgProvider_t@@XZ`
- size: `185`
- prototype: `const struct _tlgProvider_t *(void)`
- caller_count: `47`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000830c`
- `0x18000d724`
- `0x18000d7a4`
- `0x18000d870`
- `0x18000e148`
- `0x18000e210`
- `0x18000e2d8`
- `0x18000e3a0`
- `0x18000e4b4`
- `0x18000e5b4`
- `0x18000e634`
- `0x18000e718`
- `0x18000e7d4`
- `0x18000e854`
- `0x18000e8d4`
- `0x18000e980`
- `0x18000ea2c`
- `0x18000eadc`
- `0x18000f1a4`
- `0x180014884`
- `0x180014920`
- `0x180014dc4`
- `0x180014e60`
- `0x18001a3a0`
- `0x18001a848`
- `0x18001a8e4`
- `0x18001a980`
- `0x18001aa1c`
- `0x18001aab8`
- `0x18001ab54`
- `0x18001abf0`
- `0x18001ac8c`
- `0x18001d52c`
- `0x18001e794`
- `0x180025834`
- `0x1800258fc`
- `0x1800259c8`
- `0x18002a514`
- `0x18002a69c`
- `0x18002a7b4`
- `0x18002ac88`
- `0x18002ad24`
- `0x18002adc0`
- `0x18002ae5c`
- `0x18002aef8`
- `0x18002b864`
- `0x18002d050`

## callees

- `0x180002978`
- `0x18000896c`
- `0x180009eb8`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180008a10`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180008a10`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180008994`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180008994`

## pseudocode

```c
const struct _tlgProvider_t *AIXTelemetryLogging::Provider(void)
{
  void (*v0)(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, void *); // r8
  WINBOOL v2; // [rsp+30h] [rbp+8h] BYREF
  _QWORD *v3; // [rsp+38h] [rbp+10h] BYREF

  v3 = 0;
  v2 = 0;
  if ( InitOnceBeginInitialize(&`AIXTelemetryLogging::Instance'::`2'::wrapper, 0, &v2, (LPVOID *)&v3) && v2 )
  {
    qword_180041980 = 0;
    v3 = &qword_180041978;
    qword_180041978 = &wil::details::FeatureLogging::`vftable';
    byte_180041988 = 0;
    dword_18004198C = 0;
    qword_180041990 = (struct _tlgProvider_t *)&`AIXTelemetryLogging::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(_lambda_945080ad272e394bfcbba9388ab05f77_::_lambda_invoker_cdecl_);
    wil::TraceLoggingProvider::Register((wil::TraceLoggingProvider *)&qword_180041978, qword_180041990, v0);
    InitOnceComplete(&`AIXTelemetryLogging::Instance'::`2'::wrapper, 0, &qword_180041978);
  }
  return (const struct _tlgProvider_t *)v3[1];
}

```

## disassembly

```asm
0x18000896c  mov     rax, rsp
0x18000896f  push    rbx
0x180008970  sub     rsp, 20h
0x180008974  lea     r9, [rax+10h]; lpContext
0x180008978  mov     qword ptr [rax+10h], 0
0x180008980  lea     r8, [rax+8]; fPending
0x180008984  mov     dword ptr [rax+8], 0
0x18000898b  xor     edx, edx; dwFlags
0x18000898d  lea     rcx, ?wrapper@?1??Instance@AIXTelemetryLogging@@KAPEAV2@XZ@4V?$static_lazy@VAIXTelemetryLogging@@@details@wil@@A; lpInitOnce
0x180008994  call    cs:__imp_InitOnceBeginInitialize
0x18000899a  test    eax, eax
0x18000899c  jz      short loc_180008A16
0x18000899e  cmp     [rsp+28h+arg_0], 0
0x1800089a3  jz      short loc_180008A16
0x1800089a5  lea     rbx, qword_180041978
0x1800089ac  mov     cs:qword_180041980, 0
0x1800089b7  lea     rax, ??_7FeatureLogging@details@wil@@6B@; const wil::details::FeatureLogging::`vftable'
0x1800089be  mov     [rsp+28h+arg_8], rbx
0x1800089c3  mov     cs:qword_180041978, rax
0x1800089ca  mov     cs:byte_180041988, 0
0x1800089d1  mov     cs:dword_18004198C, 0
0x1800089db  lea     rax, ?__hInner@?1???0StaticHandle@AIXTelemetryLogging@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `AIXTelemetryLogging::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x1800089e2  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_945080ad272e394bfcbba9388ab05f77_@@CA@XZ; void (__cdecl *)()
0x1800089e9  mov     cs:qword_180041990, rax
0x1800089f0  call    atexit
0x1800089f5  mov     rdx, cs:qword_180041990; struct _tlgProvider_t *
0x1800089fc  mov     rcx, rbx; this
0x1800089ff  call    ?Register@TraceLoggingProvider@wil@@IEAAXQEBU_tlgProvider_t@@P6AXPEBU_GUID@@KE_K2PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z@Z; wil::TraceLoggingProvider::Register(_tlgProvider_t const * const,void (*)(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *))
0x180008a04  mov     r8, rbx; lpContext
0x180008a07  lea     rcx, ?wrapper@?1??Instance@AIXTelemetryLogging@@KAPEAV2@XZ@4V?$static_lazy@VAIXTelemetryLogging@@@details@wil@@A; lpInitOnce
0x180008a0e  xor     edx, edx; dwFlags
0x180008a10  call    cs:__imp_InitOnceComplete
0x180008a16  mov     rax, [rsp+28h+arg_8]
0x180008a1b  mov     rax, [rax+8]
0x180008a1f  add     rsp, 20h
0x180008a23  pop     rbx
0x180008a24  retn
```
