# wil::details::FeatureLogging::Instance(void)

- ea: `0x18000e014`
- end: `0x18000e0c9`
- name: `?Instance@FeatureLogging@details@wil@@KAPEAV123@XZ`
- size: `181`
- prototype: `struct wil::details::FeatureLogging *(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000d5c0`

## callees

- `0x180003e80`
- `0x180008a1c`
- `0x18000e014`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000e0b8`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000e0b8`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18000e03c`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18000e03c`

## pseudocode

```c
struct wil::details::FeatureLogging *wil::details::FeatureLogging::Instance(void)
{
  void (*v0)(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, void *); // r8
  WINBOOL v2; // [rsp+30h] [rbp+8h] BYREF
  LPVOID v3; // [rsp+38h] [rbp+10h] BYREF

  v3 = 0;
  v2 = 0;
  if ( InitOnceBeginInitialize(&`wil::details::FeatureLogging::Instance'::`2'::wrapper, 0, &v2, &v3) && v2 )
  {
    qword_18008A268 = 0;
    v3 = &qword_18008A260;
    qword_18008A260 = &wil::details::FeatureLogging::`vftable';
    byte_18008A270 = 0;
    dword_18008A274 = 0;
    qword_18008A278 = (struct _tlgProvider_t *)&`wil::details::FeatureLogging::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(_lambda_120d0c6b51dc644cb63ed5c7fc62f6c3_::_lambda_invoker_cdecl_);
    wil::TraceLoggingProvider::Register((wil::TraceLoggingProvider *)&qword_18008A260, qword_18008A278, v0);
    InitOnceComplete(&`wil::details::FeatureLogging::Instance'::`2'::wrapper, 0, &qword_18008A260);
  }
  return (struct wil::details::FeatureLogging *)v3;
}

```

## disassembly

```asm
0x18000e014  mov     rax, rsp
0x18000e017  push    rbx
0x18000e018  sub     rsp, 20h
0x18000e01c  lea     r9, [rax+10h]; lpContext
0x18000e020  mov     qword ptr [rax+10h], 0
0x18000e028  lea     r8, [rax+8]; fPending
0x18000e02c  mov     dword ptr [rax+8], 0
0x18000e033  xor     edx, edx; dwFlags
0x18000e035  lea     rcx, ?wrapper@?1??Instance@FeatureLogging@details@wil@@KAPEAV234@XZ@4V?$static_lazy@VFeatureLogging@details@wil@@@34@A; lpInitOnce
0x18000e03c  call    cs:__imp_InitOnceBeginInitialize
0x18000e042  test    eax, eax
0x18000e044  jz      short loc_18000E0BE
0x18000e046  cmp     [rsp+28h+arg_0], 0
0x18000e04b  jz      short loc_18000E0BE
0x18000e04d  lea     rbx, qword_18008A260
0x18000e054  mov     cs:qword_18008A268, 0
0x18000e05f  lea     rax, ??_7FeatureLogging@details@wil@@6B@; const wil::details::FeatureLogging::`vftable'
0x18000e066  mov     [rsp+28h+arg_8], rbx
0x18000e06b  mov     cs:qword_18008A260, rax
0x18000e072  mov     cs:byte_18008A270, 0
0x18000e079  mov     cs:dword_18008A274, 0
0x18000e083  lea     rax, ?__hInner@?1???0StaticHandle@FeatureLogging@details@wil@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `wil::details::FeatureLogging::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x18000e08a  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_120d0c6b51dc644cb63ed5c7fc62f6c3_@@CA@XZ; void (__cdecl *)()
0x18000e091  mov     cs:qword_18008A278, rax
0x18000e098  call    atexit
0x18000e09d  mov     rdx, cs:qword_18008A278; struct _tlgProvider_t *
0x18000e0a4  mov     rcx, rbx; this
0x18000e0a7  call    ?Register@TraceLoggingProvider@wil@@IEAAXQEBU_tlgProvider_t@@P6AXPEBU_GUID@@KE_K2PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z@Z; wil::TraceLoggingProvider::Register(_tlgProvider_t const * const,void (*)(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *))
0x18000e0ac  mov     r8, rbx; lpContext
0x18000e0af  lea     rcx, ?wrapper@?1??Instance@FeatureLogging@details@wil@@KAPEAV234@XZ@4V?$static_lazy@VFeatureLogging@details@wil@@@34@A; lpInitOnce
0x18000e0b6  xor     edx, edx; dwFlags
0x18000e0b8  call    cs:__imp_InitOnceComplete
0x18000e0be  mov     rax, [rsp+28h+arg_8]
0x18000e0c3  add     rsp, 20h
0x18000e0c7  pop     rbx
0x18000e0c8  retn
```
