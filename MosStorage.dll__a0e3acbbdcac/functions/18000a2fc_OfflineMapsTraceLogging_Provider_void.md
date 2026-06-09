# OfflineMapsTraceLogging::Provider(void)

- ea: `0x18000a2fc`
- end: `0x18000a3ae`
- name: `?Provider@OfflineMapsTraceLogging@@SAPEBU_tlgProvider_t@@XZ`
- size: `178`
- prototype: `const struct _tlgProvider_t *(void)`
- caller_count: `5`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000824c`
- `0x18000a684`
- `0x18000a750`
- `0x18000a87c`
- `0x18000a9c0`

## callees

- `0x180002030`
- `0x180006d8c`
- `0x18000a2fc`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18000a327`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18000a327`

## pseudocode

```c
const struct _tlgProvider_t *OfflineMapsTraceLogging::Provider(void)
{
  union _RTL_RUN_ONCE *v1; // [rsp+20h] [rbp-18h] BYREF
  int v2; // [rsp+28h] [rbp-10h]
  WINBOOL v3; // [rsp+40h] [rbp+8h] BYREF
  __int64 *v4; // [rsp+48h] [rbp+10h] BYREF

  v4 = 0;
  v3 = 0;
  if ( InitOnceBeginInitialize(&`OfflineMapsTraceLogging::Instance'::`2'::wrapper, 0, &v3, (LPVOID *)&v4) && v3 )
  {
    v1 = &`OfflineMapsTraceLogging::Instance'::`2'::wrapper;
    v4 = &qword_180018D78;
    qword_180018D78 = (__int64)&wil::TraceLoggingProvider::`vftable';
    qword_180018D80 = 0;
    byte_180018D88 = 0;
    dword_180018D8C = 0;
    qword_180018D90 = (__int64)&`OfflineMapsTraceLogging::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(_lambda_b1920e3fd6e26929e52072737012d5c8_::_lambda_invoker_cdecl_);
    v2 = 0;
    wil::details::static_lazy<OfflineMapsTraceLogging>::Completer::~Completer(&v1);
  }
  return (const struct _tlgProvider_t *)v4[1];
}

```

## disassembly

```asm
0x18000a2fc  mov     rax, rsp
0x18000a2ff  push    rdi
0x18000a300  sub     rsp, 30h
0x18000a304  lea     rdi, ?wrapper@?1??Instance@OfflineMapsTraceLogging@@KAPEAV2@XZ@4V?$static_lazy@VOfflineMapsTraceLogging@@@details@wil@@A; wil::details::static_lazy<OfflineMapsTraceLogging> `OfflineMapsTraceLogging::Instance(void)'::`2'::wrapper
0x18000a30b  mov     qword ptr [rax+10h], 0
0x18000a313  mov     rcx, rdi; lpInitOnce
0x18000a316  mov     dword ptr [rax+8], 0
0x18000a31d  lea     r9, [rax+10h]; lpContext
0x18000a321  xor     edx, edx; dwFlags
0x18000a323  lea     r8, [rax+8]; fPending
0x18000a327  call    cs:__imp_InitOnceBeginInitialize
0x18000a32d  test    eax, eax
0x18000a32f  jz      short loc_18000A39F
0x18000a331  cmp     [rsp+38h+arg_0], 0
0x18000a336  jz      short loc_18000A39F
0x18000a338  lea     rax, qword_180018D78
0x18000a33f  mov     [rsp+38h+var_18], rdi
0x18000a344  mov     [rsp+38h+arg_8], rax
0x18000a349  lea     rax, ??_7TraceLoggingProvider@wil@@6B@; const wil::TraceLoggingProvider::`vftable'
0x18000a350  mov     cs:qword_180018D78, rax
0x18000a357  mov     cs:qword_180018D80, 0
0x18000a362  mov     cs:byte_180018D88, 0
0x18000a369  mov     cs:dword_180018D8C, 0
0x18000a373  lea     rax, ?__hInner@?1???0StaticHandle@OfflineMapsTraceLogging@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `OfflineMapsTraceLogging::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x18000a37a  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_b1920e3fd6e26929e52072737012d5c8_@@CA@XZ; void (__cdecl *)()
0x18000a381  mov     cs:qword_180018D90, rax
0x18000a388  call    atexit
0x18000a38d  lea     rcx, [rsp+38h+var_18]
0x18000a392  mov     [rsp+38h+var_10], 0
0x18000a39a  call    ??1Completer@?$static_lazy@VOfflineMapsTraceLogging@@@details@wil@@QEAA@XZ; wil::details::static_lazy<OfflineMapsTraceLogging>::Completer::~Completer(void)
0x18000a39f  mov     rax, [rsp+38h+arg_8]
0x18000a3a4  mov     rax, [rax+8]
0x18000a3a8  add     rsp, 30h
0x18000a3ac  pop     rdi
0x18000a3ad  retn
```
