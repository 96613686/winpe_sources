# UsageAndQualityInsightsLogging::Instance(void)

- ea: `0x1800499c0`
- end: `0x180049a75`
- name: `?Instance@UsageAndQualityInsightsLogging@@KAPEAV1@XZ`
- size: `181`
- prototype: `struct UsageAndQualityInsightsLogging *(void)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18004a4b0`
- `0x18004c5ec`

## callees

- `0x180003850`
- `0x18000ff3c`
- `0x1800499c0`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180049a64`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180049a64`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1800499e8`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1800499e8`

## pseudocode

```c
struct UsageAndQualityInsightsLogging *UsageAndQualityInsightsLogging::Instance(void)
{
  void (*v0)(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, void *); // r8
  WINBOOL v2; // [rsp+30h] [rbp+8h] BYREF
  LPVOID v3; // [rsp+38h] [rbp+10h] BYREF

  v3 = 0;
  v2 = 0;
  if ( __std_init_once_begin_initialize(&`UsageAndQualityInsightsLogging::Instance'::`2'::wrapper, 0, &v2, &v3) && v2 )
  {
    qword_180159E68 = 0;
    v3 = &qword_180159E60;
    qword_180159E60 = &UsageAndQualityInsightsLogging::`vftable';
    byte_180159E70 = 0;
    dword_180159E74 = 0;
    qword_180159E78 = (struct _tlgProvider_t *)&`UsageAndQualityInsightsLogging::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(`UsageAndQualityInsightsLogging::Instance'::`2'::_lambda_1_::_lambda_invoker_cdecl_);
    wil::TraceLoggingProvider::Register((wil::TraceLoggingProvider *)&qword_180159E60, qword_180159E78, v0);
    InitOnceComplete(&`UsageAndQualityInsightsLogging::Instance'::`2'::wrapper, 0, &qword_180159E60);
  }
  return (struct UsageAndQualityInsightsLogging *)v3;
}

```

## disassembly

```asm
0x1800499c0  mov     rax, rsp
0x1800499c3  push    rbx
0x1800499c4  sub     rsp, 20h
0x1800499c8  lea     r9, [rax+10h]; lpContext
0x1800499cc  mov     qword ptr [rax+10h], 0
0x1800499d4  lea     r8, [rax+8]; fPending
0x1800499d8  mov     dword ptr [rax+8], 0
0x1800499df  xor     edx, edx; dwFlags
0x1800499e1  lea     rcx, ?wrapper@?1??Instance@UsageAndQualityInsightsLogging@@KAPEAV2@XZ@4V?$static_lazy@VUsageAndQualityInsightsLogging@@@details@wil@@A; lpInitOnce
0x1800499e8  call    cs:__imp___std_init_once_begin_initialize
0x1800499ee  test    eax, eax
0x1800499f0  jz      short loc_180049A6A
0x1800499f2  cmp     [rsp+28h+arg_0], 0
0x1800499f7  jz      short loc_180049A6A
0x1800499f9  lea     rbx, qword_180159E60
0x180049a00  mov     cs:qword_180159E68, 0
0x180049a0b  lea     rax, ??_7UsageAndQualityInsightsLogging@@6B@; const UsageAndQualityInsightsLogging::`vftable'
0x180049a12  mov     [rsp+28h+arg_8], rbx
0x180049a17  mov     cs:qword_180159E60, rax
0x180049a1e  mov     cs:byte_180159E70, 0
0x180049a25  mov     cs:dword_180159E74, 0
0x180049a2f  lea     rax, ?__hInner@?1???0StaticHandle@UsageAndQualityInsightsLogging@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `UsageAndQualityInsightsLogging::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x180049a36  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1_@?1??Instance@UsageAndQualityInsightsLogging@@KAPEAV3@XZ@SA@XZ; void (__cdecl *)()
0x180049a3d  mov     cs:qword_180159E78, rax
0x180049a44  call    atexit
0x180049a49  mov     rdx, cs:qword_180159E78; struct _tlgProvider_t *
0x180049a50  mov     rcx, rbx; this
0x180049a53  call    ?Register@TraceLoggingProvider@wil@@IEAAXQEBU_tlgProvider_t@@P6AXPEBU_GUID@@KE_K2PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z@Z; wil::TraceLoggingProvider::Register(_tlgProvider_t const * const,void (*)(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *))
0x180049a58  mov     r8, rbx; lpContext
0x180049a5b  lea     rcx, ?wrapper@?1??Instance@UsageAndQualityInsightsLogging@@KAPEAV2@XZ@4V?$static_lazy@VUsageAndQualityInsightsLogging@@@details@wil@@A; lpInitOnce
0x180049a62  xor     edx, edx; dwFlags
0x180049a64  call    cs:__imp_InitOnceComplete
0x180049a6a  mov     rax, [rsp+28h+arg_8]
0x180049a6f  add     rsp, 20h
0x180049a73  pop     rbx
0x180049a74  retn
```
