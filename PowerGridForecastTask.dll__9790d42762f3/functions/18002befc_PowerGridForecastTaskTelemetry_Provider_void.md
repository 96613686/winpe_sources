# PowerGridForecastTaskTelemetry::Provider(void)

- ea: `0x18002befc`
- end: `0x18002bfb5`
- name: `?Provider@PowerGridForecastTaskTelemetry@@SAPEBU_tlgProvider_t@@XZ`
- size: `185`
- prototype: `const struct _tlgProvider_t *(void)`
- caller_count: `5`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180027d38`
- `0x18002b8a0`
- `0x18002e574`
- `0x18002e778`
- `0x18002e980`

## callees

- `0x180026710`
- `0x18002befc`
- `0x18002d360`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18002bf24`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18002bf24`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18002bfa0`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18002bfa0`

## pseudocode

```c
const struct _tlgProvider_t *PowerGridForecastTaskTelemetry::Provider(void)
{
  void (*v0)(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, void *); // r8
  BOOL v2; // [rsp+30h] [rbp+8h] BYREF
  _QWORD *v3; // [rsp+38h] [rbp+10h] BYREF

  v3 = 0;
  v2 = 0;
  if ( InitOnceBeginInitialize(&`PowerGridForecastTaskTelemetry::Instance'::`2'::wrapper, 0, &v2, (LPVOID *)&v3) && v2 )
  {
    qword_180047040 = 0;
    v3 = &qword_180047038;
    qword_180047038 = &PowerGridForecastTaskTelemetry::`vftable';
    byte_180047048 = 0;
    dword_18004704C = 0;
    qword_180047050 = (struct _tlgProvider_t *)&`PowerGridForecastTaskTelemetry::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(_lambda_8ee4ed33a54e690cca51678377337e7e_::_lambda_invoker_cdecl_);
    wil::TraceLoggingProvider::Register((wil::TraceLoggingProvider *)&qword_180047038, qword_180047050, v0);
    InitOnceComplete(&`PowerGridForecastTaskTelemetry::Instance'::`2'::wrapper, 0, &qword_180047038);
  }
  return (const struct _tlgProvider_t *)v3[1];
}

```

## disassembly

```asm
0x18002befc  mov     rax, rsp
0x18002beff  push    rbx
0x18002bf00  sub     rsp, 20h
0x18002bf04  lea     r9, [rax+10h]; lpContext
0x18002bf08  mov     qword ptr [rax+10h], 0
0x18002bf10  lea     r8, [rax+8]; fPending
0x18002bf14  mov     dword ptr [rax+8], 0
0x18002bf1b  xor     edx, edx; dwFlags
0x18002bf1d  lea     rcx, ?wrapper@?1??Instance@PowerGridForecastTaskTelemetry@@KAPEAV2@XZ@4V?$static_lazy@VPowerGridForecastTaskTelemetry@@@details@wil@@A; lpInitOnce
0x18002bf24  call    cs:__imp_InitOnceBeginInitialize
0x18002bf2a  test    eax, eax
0x18002bf2c  jz      short loc_18002BFA6
0x18002bf2e  cmp     [rsp+28h+arg_0], 0
0x18002bf33  jz      short loc_18002BFA6
0x18002bf35  lea     rbx, qword_180047038
0x18002bf3c  mov     cs:qword_180047040, 0
0x18002bf47  lea     rax, ??_7PowerGridForecastTaskTelemetry@@6B@; const PowerGridForecastTaskTelemetry::`vftable'
0x18002bf4e  mov     [rsp+28h+arg_8], rbx
0x18002bf53  mov     cs:qword_180047038, rax
0x18002bf5a  mov     cs:byte_180047048, 0
0x18002bf61  mov     cs:dword_18004704C, 0
0x18002bf6b  lea     rax, ?__hInner@?1???0StaticHandle@PowerGridForecastTaskTelemetry@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `PowerGridForecastTaskTelemetry::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x18002bf72  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_8ee4ed33a54e690cca51678377337e7e_@@CA@XZ; void (__cdecl *)()
0x18002bf79  mov     cs:qword_180047050, rax
0x18002bf80  call    atexit
0x18002bf85  mov     rdx, cs:qword_180047050; struct _tlgProvider_t *
0x18002bf8c  mov     rcx, rbx; this
0x18002bf8f  call    ?Register@TraceLoggingProvider@wil@@IEAAXQEBU_tlgProvider_t@@P6AXPEBU_GUID@@KE_K2PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z@Z; wil::TraceLoggingProvider::Register(_tlgProvider_t const * const,void (*)(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *))
0x18002bf94  mov     r8, rbx; lpContext
0x18002bf97  lea     rcx, ?wrapper@?1??Instance@PowerGridForecastTaskTelemetry@@KAPEAV2@XZ@4V?$static_lazy@VPowerGridForecastTaskTelemetry@@@details@wil@@A; lpInitOnce
0x18002bf9e  xor     edx, edx; dwFlags
0x18002bfa0  call    cs:__imp_InitOnceComplete
0x18002bfa6  mov     rax, [rsp+28h+arg_8]
0x18002bfab  mov     rax, [rax+8]
0x18002bfaf  add     rsp, 20h
0x18002bfb3  pop     rbx
0x18002bfb4  retn
```
