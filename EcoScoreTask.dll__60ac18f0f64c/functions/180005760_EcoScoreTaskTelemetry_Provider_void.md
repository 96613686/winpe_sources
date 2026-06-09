# EcoScoreTaskTelemetry::Provider(void)

- ea: `0x180005760`
- end: `0x180005812`
- name: `?Provider@EcoScoreTaskTelemetry@@SAPEBU_tlgProvider_t@@XZ`
- size: `178`
- prototype: `const struct _tlgProvider_t *(void)`
- caller_count: `6`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800024d8`
- `0x180003048`
- `0x1800052b0`
- `0x180006654`
- `0x180006858`
- `0x180006a60`

## callees

- `0x180002020`
- `0x1800031fc`
- `0x180005760`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18000578b`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18000578b`

## pseudocode

```c
const struct _tlgProvider_t *EcoScoreTaskTelemetry::Provider(void)
{
  union _RTL_RUN_ONCE *v1; // [rsp+20h] [rbp-18h] BYREF
  int v2; // [rsp+28h] [rbp-10h]
  BOOL v3; // [rsp+40h] [rbp+8h] BYREF
  __int64 *v4; // [rsp+48h] [rbp+10h] BYREF

  v4 = 0;
  v3 = 0;
  if ( InitOnceBeginInitialize(&`EcoScoreTaskTelemetry::Instance'::`2'::wrapper, 0, &v3, (LPVOID *)&v4) && v3 )
  {
    v1 = &`EcoScoreTaskTelemetry::Instance'::`2'::wrapper;
    v4 = &qword_18000D870;
    qword_18000D870 = (__int64)&wil::TraceLoggingProvider::`vftable';
    qword_18000D878 = 0;
    byte_18000D880 = 0;
    dword_18000D884 = 0;
    qword_18000D888 = (__int64)&`EcoScoreTaskTelemetry::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(_lambda_3f7e6be3839dcef3c8b7fe8ed819d62b_::_lambda_invoker_cdecl_);
    v2 = 0;
    wil::details::static_lazy<EcoScoreTaskTelemetry>::Completer::~Completer(&v1);
  }
  return (const struct _tlgProvider_t *)v4[1];
}

```

## disassembly

```asm
0x180005760  mov     rax, rsp
0x180005763  push    rdi
0x180005764  sub     rsp, 30h
0x180005768  lea     rdi, ?wrapper@?1??Instance@EcoScoreTaskTelemetry@@KAPEAV2@XZ@4V?$static_lazy@VEcoScoreTaskTelemetry@@@details@wil@@A; wil::details::static_lazy<EcoScoreTaskTelemetry> `EcoScoreTaskTelemetry::Instance(void)'::`2'::wrapper
0x18000576f  mov     qword ptr [rax+10h], 0
0x180005777  mov     rcx, rdi; lpInitOnce
0x18000577a  mov     dword ptr [rax+8], 0
0x180005781  lea     r9, [rax+10h]; lpContext
0x180005785  xor     edx, edx; dwFlags
0x180005787  lea     r8, [rax+8]; fPending
0x18000578b  call    cs:__imp_InitOnceBeginInitialize
0x180005791  test    eax, eax
0x180005793  jz      short loc_180005803
0x180005795  cmp     [rsp+38h+arg_0], 0
0x18000579a  jz      short loc_180005803
0x18000579c  lea     rax, qword_18000D870
0x1800057a3  mov     [rsp+38h+var_18], rdi
0x1800057a8  mov     [rsp+38h+arg_8], rax
0x1800057ad  lea     rax, ??_7TraceLoggingProvider@wil@@6B@; const wil::TraceLoggingProvider::`vftable'
0x1800057b4  mov     cs:qword_18000D870, rax
0x1800057bb  mov     cs:qword_18000D878, 0
0x1800057c6  mov     cs:byte_18000D880, 0
0x1800057cd  mov     cs:dword_18000D884, 0
0x1800057d7  lea     rax, ?__hInner@?1???0StaticHandle@EcoScoreTaskTelemetry@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `EcoScoreTaskTelemetry::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x1800057de  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_3f7e6be3839dcef3c8b7fe8ed819d62b_@@CA@XZ; void (__cdecl *)()
0x1800057e5  mov     cs:qword_18000D888, rax
0x1800057ec  call    atexit
0x1800057f1  lea     rcx, [rsp+38h+var_18]
0x1800057f6  mov     [rsp+38h+var_10], 0
0x1800057fe  call    ??1Completer@?$static_lazy@VEcoScoreTaskTelemetry@@@details@wil@@QEAA@XZ; wil::details::static_lazy<EcoScoreTaskTelemetry>::Completer::~Completer(void)
0x180005803  mov     rax, [rsp+38h+arg_8]
0x180005808  mov     rax, [rax+8]
0x18000580c  add     rsp, 30h
0x180005810  pop     rdi
0x180005811  retn
```
