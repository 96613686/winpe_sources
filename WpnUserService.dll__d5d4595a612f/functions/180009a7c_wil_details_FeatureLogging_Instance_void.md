# wil::details::FeatureLogging::Instance(void)

- ea: `0x180009a7c`
- end: `0x180009b31`
- name: `?Instance@FeatureLogging@details@wil@@KAPEAV123@XZ`
- size: `181`
- prototype: `struct wil::details::FeatureLogging *(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180009040`

## callees

- `0x180002f70`
- `0x180009a7c`
- `0x18000b644`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180009b20`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180009b20`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180009aa4`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180009aa4`

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
    qword_1800196D0 = 0;
    v3 = &qword_1800196C8;
    qword_1800196C8 = &wil::details::FeatureLogging::`vftable';
    byte_1800196D8 = 0;
    dword_1800196DC = 0;
    qword_1800196E0 = (struct _tlgProvider_t *)&`wil::details::FeatureLogging::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(_lambda_120d0c6b51dc644cb63ed5c7fc62f6c3_::_lambda_invoker_cdecl_);
    wil::TraceLoggingProvider::Register((wil::TraceLoggingProvider *)&qword_1800196C8, qword_1800196E0, v0);
    InitOnceComplete(&`wil::details::FeatureLogging::Instance'::`2'::wrapper, 0, &qword_1800196C8);
  }
  return (struct wil::details::FeatureLogging *)v3;
}

```

## disassembly

```asm
0x180009a7c  mov     rax, rsp
0x180009a7f  push    rbx
0x180009a80  sub     rsp, 20h
0x180009a84  lea     r9, [rax+10h]; lpContext
0x180009a88  mov     qword ptr [rax+10h], 0
0x180009a90  lea     r8, [rax+8]; fPending
0x180009a94  mov     dword ptr [rax+8], 0
0x180009a9b  xor     edx, edx; dwFlags
0x180009a9d  lea     rcx, ?wrapper@?1??Instance@FeatureLogging@details@wil@@KAPEAV234@XZ@4V?$static_lazy@VFeatureLogging@details@wil@@@34@A; lpInitOnce
0x180009aa4  call    cs:__imp_InitOnceBeginInitialize
0x180009aaa  test    eax, eax
0x180009aac  jz      short loc_180009B26
0x180009aae  cmp     [rsp+28h+arg_0], 0
0x180009ab3  jz      short loc_180009B26
0x180009ab5  lea     rbx, qword_1800196C8
0x180009abc  mov     cs:qword_1800196D0, 0
0x180009ac7  lea     rax, ??_7FeatureLogging@details@wil@@6B@; const wil::details::FeatureLogging::`vftable'
0x180009ace  mov     [rsp+28h+arg_8], rbx
0x180009ad3  mov     cs:qword_1800196C8, rax
0x180009ada  mov     cs:byte_1800196D8, 0
0x180009ae1  mov     cs:dword_1800196DC, 0
0x180009aeb  lea     rax, ?__hInner@?1???0StaticHandle@FeatureLogging@details@wil@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `wil::details::FeatureLogging::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x180009af2  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_120d0c6b51dc644cb63ed5c7fc62f6c3_@@CA@XZ; void (__cdecl *)()
0x180009af9  mov     cs:qword_1800196E0, rax
0x180009b00  call    atexit
0x180009b05  mov     rdx, cs:qword_1800196E0; struct _tlgProvider_t *
0x180009b0c  mov     rcx, rbx; this
0x180009b0f  call    ?Register@TraceLoggingProvider@wil@@IEAAXQEBU_tlgProvider_t@@P6AXPEBU_GUID@@KE_K2PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z@Z; wil::TraceLoggingProvider::Register(_tlgProvider_t const * const,void (*)(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *))
0x180009b14  mov     r8, rbx; lpContext
0x180009b17  lea     rcx, ?wrapper@?1??Instance@FeatureLogging@details@wil@@KAPEAV234@XZ@4V?$static_lazy@VFeatureLogging@details@wil@@@34@A; lpInitOnce
0x180009b1e  xor     edx, edx; dwFlags
0x180009b20  call    cs:__imp_InitOnceComplete
0x180009b26  mov     rax, [rsp+28h+arg_8]
0x180009b2b  add     rsp, 20h
0x180009b2f  pop     rbx
0x180009b30  retn
```
