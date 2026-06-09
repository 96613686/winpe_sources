# UsageAndQualityInsightsCoreLogging::Instance(void)

- ea: `0x18001bb5c`
- end: `0x18001bc11`
- name: `?Instance@UsageAndQualityInsightsCoreLogging@@KAPEAV1@XZ`
- size: `181`
- prototype: `struct UsageAndQualityInsightsCoreLogging *(void)`
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18001bc20`
- `0x18001c3d0`
- `0x18004c634`

## callees

- `0x180003850`
- `0x18000ff3c`
- `0x18001bb5c`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18001bc00`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18001bc00`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18001bb84`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18001bb84`

## pseudocode

```c
struct UsageAndQualityInsightsCoreLogging *UsageAndQualityInsightsCoreLogging::Instance(void)
{
  void (*v0)(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, void *); // r8
  WINBOOL v2; // [rsp+30h] [rbp+8h] BYREF
  LPVOID v3; // [rsp+38h] [rbp+10h] BYREF

  v3 = 0;
  v2 = 0;
  if ( __std_init_once_begin_initialize(&`UsageAndQualityInsightsCoreLogging::Instance'::`2'::wrapper, 0, &v2, &v3)
    && v2 )
  {
    qword_180159E28 = 0;
    v3 = &qword_180159E20;
    qword_180159E20 = &UsageAndQualityInsightsCoreLogging::`vftable';
    byte_180159E30 = 0;
    dword_180159E34 = 0;
    qword_180159E38 = (struct _tlgProvider_t *)&`UsageAndQualityInsightsCoreLogging::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(`UsageAndQualityInsightsCoreLogging::Instance'::`2'::_lambda_1_::_lambda_invoker_cdecl_);
    wil::TraceLoggingProvider::Register((wil::TraceLoggingProvider *)&qword_180159E20, qword_180159E38, v0);
    InitOnceComplete(&`UsageAndQualityInsightsCoreLogging::Instance'::`2'::wrapper, 0, &qword_180159E20);
  }
  return (struct UsageAndQualityInsightsCoreLogging *)v3;
}

```

## disassembly

```asm
0x18001bb5c  mov     rax, rsp
0x18001bb5f  push    rbx
0x18001bb60  sub     rsp, 20h
0x18001bb64  lea     r9, [rax+10h]; lpContext
0x18001bb68  mov     qword ptr [rax+10h], 0
0x18001bb70  lea     r8, [rax+8]; fPending
0x18001bb74  mov     dword ptr [rax+8], 0
0x18001bb7b  xor     edx, edx; dwFlags
0x18001bb7d  lea     rcx, ?wrapper@?1??Instance@UsageAndQualityInsightsCoreLogging@@KAPEAV2@XZ@4V?$static_lazy@VUsageAndQualityInsightsCoreLogging@@@details@wil@@A; lpInitOnce
0x18001bb84  call    cs:__imp___std_init_once_begin_initialize
0x18001bb8a  test    eax, eax
0x18001bb8c  jz      short loc_18001BC06
0x18001bb8e  cmp     [rsp+28h+arg_0], 0
0x18001bb93  jz      short loc_18001BC06
0x18001bb95  lea     rbx, qword_180159E20
0x18001bb9c  mov     cs:qword_180159E28, 0
0x18001bba7  lea     rax, ??_7UsageAndQualityInsightsCoreLogging@@6B@; const UsageAndQualityInsightsCoreLogging::`vftable'
0x18001bbae  mov     [rsp+28h+arg_8], rbx
0x18001bbb3  mov     cs:qword_180159E20, rax
0x18001bbba  mov     cs:byte_180159E30, 0
0x18001bbc1  mov     cs:dword_180159E34, 0
0x18001bbcb  lea     rax, ?__hInner@?1???0StaticHandle@UsageAndQualityInsightsCoreLogging@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `UsageAndQualityInsightsCoreLogging::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x18001bbd2  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1_@?1??Instance@UsageAndQualityInsightsCoreLogging@@KAPEAV3@XZ@SA@XZ; void (__cdecl *)()
0x18001bbd9  mov     cs:qword_180159E38, rax
0x18001bbe0  call    atexit
0x18001bbe5  mov     rdx, cs:qword_180159E38; struct _tlgProvider_t *
0x18001bbec  mov     rcx, rbx; this
0x18001bbef  call    ?Register@TraceLoggingProvider@wil@@IEAAXQEBU_tlgProvider_t@@P6AXPEBU_GUID@@KE_K2PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z@Z; wil::TraceLoggingProvider::Register(_tlgProvider_t const * const,void (*)(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *))
0x18001bbf4  mov     r8, rbx; lpContext
0x18001bbf7  lea     rcx, ?wrapper@?1??Instance@UsageAndQualityInsightsCoreLogging@@KAPEAV2@XZ@4V?$static_lazy@VUsageAndQualityInsightsCoreLogging@@@details@wil@@A; lpInitOnce
0x18001bbfe  xor     edx, edx; dwFlags
0x18001bc00  call    cs:__imp_InitOnceComplete
0x18001bc06  mov     rax, [rsp+28h+arg_8]
0x18001bc0b  add     rsp, 20h
0x18001bc0f  pop     rbx
0x18001bc10  retn
```
