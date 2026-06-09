# UsageAndQualityInsightsTraceLogging::TraceLoggingInfo(char const *,...)

- ea: `0x1800107b0`
- end: `0x180010890`
- name: `?TraceLoggingInfo@UsageAndQualityInsightsTraceLogging@@SAXPEBDZZ`
- size: `224`
- prototype: `void(const char *, ...)`
- caller_count: `27`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000d360`
- `0x180010740`
- `0x180010760`
- `0x180010d9c`
- `0x18001573c`
- `0x180015930`
- `0x18001b234`
- `0x18001e18c`
- `0x1800366f4`
- `0x180046cf0`
- `0x180047688`
- `0x180047aec`
- `0x180048234`
- `0x1800485a0`
- `0x180048b20`
- `0x180048d8c`
- `0x180049850`
- `0x18004a66c`
- `0x18004aec4`
- `0x18004c184`
- `0x18004f0b8`
- `0x18004f64c`
- `0x1800e4154`
- `0x1800e5324`
- `0x1800e75bc`
- `0x1800f58d4`
- `0x1800f5a1c`

## callees

- `0x180003850`
- `0x18000ff3c`
- `0x1800102d0`
- `0x1800107b0`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180010871`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180010871`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1800107f5`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1800107f5`

## pseudocode

```c
void UsageAndQualityInsightsTraceLogging::TraceLoggingInfo(const char *a1, ...)
{
  void (*v1)(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, void *); // r8
  WINBOOL v2; // [rsp+20h] [rbp-28h] BYREF
  wil::TraceLoggingProvider *v3; // [rsp+28h] [rbp-20h] BYREF
  va_list va; // [rsp+58h] [rbp+10h] BYREF

  va_start(va, a1);
  v3 = 0;
  v2 = 0;
  if ( __std_init_once_begin_initialize(
         &`UsageAndQualityInsightsTraceLogging::Instance'::`2'::wrapper,
         0,
         &v2,
         (LPVOID *)&v3)
    && v2 )
  {
    qword_180159DB8 = 0;
    v3 = (wil::TraceLoggingProvider *)&qword_180159DB0;
    qword_180159DB0 = &UsageAndQualityInsightsTraceLogging::`vftable';
    byte_180159DC0 = 0;
    dword_180159DC4 = 0;
    qword_180159DC8 = (struct _tlgProvider_t *)&`UsageAndQualityInsightsTraceLogging::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(`UsageAndQualityInsightsTraceLogging::Instance'::`2'::_lambda_1_::_lambda_invoker_cdecl_);
    wil::TraceLoggingProvider::Register((wil::TraceLoggingProvider *)&qword_180159DB0, qword_180159DC8, v1);
    InitOnceComplete(&`UsageAndQualityInsightsTraceLogging::Instance'::`2'::wrapper, 0, &qword_180159DB0);
  }
  wil::TraceLoggingProvider::ReportTraceLoggingMessage(v3, a1, va);
}

```

## disassembly

```asm
0x1800107b0  mov     rax, rsp
0x1800107b3  mov     [rax+8], rcx
0x1800107b7  mov     [rax+10h], rdx
0x1800107bb  mov     [rax+18h], r8
0x1800107bf  mov     [rax+20h], r9
0x1800107c3  push    rbx
0x1800107c4  push    rsi
0x1800107c5  sub     rsp, 38h
0x1800107c9  mov     qword ptr [rax-20h], 0
0x1800107d1  lea     r9, [rax-20h]; lpContext
0x1800107d5  lea     r8, [rax-28h]; fPending
0x1800107d9  mov     qword ptr [rax-20h], 0
0x1800107e1  xor     edx, edx; dwFlags
0x1800107e3  mov     dword ptr [rax-28h], 0
0x1800107ea  lea     rcx, ?wrapper@?1??Instance@UsageAndQualityInsightsTraceLogging@@KAPEAV2@XZ@4V?$static_lazy@VUsageAndQualityInsightsTraceLogging@@@details@wil@@A; lpInitOnce
0x1800107f1  lea     rsi, [rax+10h]
0x1800107f5  call    cs:__imp___std_init_once_begin_initialize
0x1800107fb  test    eax, eax
0x1800107fd  jz      short loc_180010877
0x1800107ff  cmp     [rsp+48h+var_28], 0
0x180010804  jz      short loc_180010877
0x180010806  lea     rbx, qword_180159DB0
0x18001080d  mov     cs:qword_180159DB8, 0
0x180010818  lea     rax, ??_7UsageAndQualityInsightsTraceLogging@@6B@; const UsageAndQualityInsightsTraceLogging::`vftable'
0x18001081f  mov     [rsp+48h+var_20], rbx
0x180010824  mov     cs:qword_180159DB0, rax
0x18001082b  mov     cs:byte_180159DC0, 0
0x180010832  mov     cs:dword_180159DC4, 0
0x18001083c  lea     rax, ?__hInner@?1???0StaticHandle@UsageAndQualityInsightsTraceLogging@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `UsageAndQualityInsightsTraceLogging::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x180010843  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1_@?1??Instance@UsageAndQualityInsightsTraceLogging@@KAPEAV3@XZ@SA@XZ; void (__cdecl *)()
0x18001084a  mov     cs:qword_180159DC8, rax
0x180010851  call    atexit
0x180010856  mov     rdx, cs:qword_180159DC8; struct _tlgProvider_t *
0x18001085d  mov     rcx, rbx; this
0x180010860  call    ?Register@TraceLoggingProvider@wil@@IEAAXQEBU_tlgProvider_t@@P6AXPEBU_GUID@@KE_K2PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z@Z; wil::TraceLoggingProvider::Register(_tlgProvider_t const * const,void (*)(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *))
0x180010865  mov     r8, rbx; lpContext
0x180010868  lea     rcx, ?wrapper@?1??Instance@UsageAndQualityInsightsTraceLogging@@KAPEAV2@XZ@4V?$static_lazy@VUsageAndQualityInsightsTraceLogging@@@details@wil@@A; lpInitOnce
0x18001086f  xor     edx, edx; dwFlags
0x180010871  call    cs:__imp_InitOnceComplete
0x180010877  mov     rdx, [rsp+48h+arg_0]; char *
0x18001087c  mov     r8, rsi; char *
0x18001087f  mov     rcx, [rsp+48h+var_20]; this
0x180010884  call    ?ReportTraceLoggingMessage@TraceLoggingProvider@wil@@IEAAXPEBDPEAD@Z; wil::TraceLoggingProvider::ReportTraceLoggingMessage(char const *,char *)
0x180010889  add     rsp, 38h
0x18001088d  pop     rsi
0x18001088e  pop     rbx
0x18001088f  retn
```
