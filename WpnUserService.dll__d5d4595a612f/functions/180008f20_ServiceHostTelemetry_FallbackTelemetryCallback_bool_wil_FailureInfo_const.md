# ServiceHostTelemetry::FallbackTelemetryCallback(bool,wil::FailureInfo const &)

- ea: `0x180008f20`
- end: `0x180009031`
- name: `?FallbackTelemetryCallback@ServiceHostTelemetry@@SAX_NAEBUFailureInfo@wil@@@Z`
- size: `273`
- prototype: `void __fastcall(char, const struct wil::FailureInfo *)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x180002f70`
- `0x180008f20`
- `0x18000a648`
- `0x18000bc14`
- `0x18000bd7c`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180008fed`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180008fed`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180008f56`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180008f56`

## pseudocode

```c
void __fastcall ServiceHostTelemetry::FallbackTelemetryCallback(char a1, const struct wil::FailureInfo *a2)
{
  WINBOOL v4; // [rsp+30h] [rbp+8h] BYREF
  wil::TraceLoggingProvider *v5; // [rsp+40h] [rbp+18h] BYREF

  v5 = 0;
  v4 = 0;
  if ( InitOnceBeginInitialize(&`ServiceHostTelemetry::Instance'::`2'::wrapper, 0, &v4, (LPVOID *)&v5) && v4 )
  {
    qword_180019688 = 0;
    qword_180019680 = (__int64)&ServiceHostTelemetry::`vftable';
    v5 = (wil::TraceLoggingProvider *)&qword_180019680;
    byte_180019690 = 0;
    dword_180019694 = 0;
    atexit(_lambda_ef7f6407c7d6d1282504bab1440f4cfe_::_lambda_invoker_cdecl_);
    qword_180019688 = (__int64)ServiceHostLogging::Provider();
    byte_180019690 = 0;
    dword_180019694 = 1;
    (*(void (__fastcall **)(__int64 *))(qword_180019680 + 8))(&qword_180019680);
    InitOnceComplete(&`ServiceHostTelemetry::Instance'::`2'::wrapper, 0, &qword_180019680);
  }
  if ( !a1 && (*((_BYTE *)a2 + 4) & 2) == 0 )
  {
    if ( *((_DWORD *)v5 + 5) == 1 )
    {
      wil::TraceLoggingProvider::ReportTelemetryFailure(v5, a2);
    }
    else if ( *((_DWORD *)v5 + 5) == 2 )
    {
      wil::TraceLoggingProvider::ReportTraceLoggingFailure(v5, a2);
    }
  }
}

```

## disassembly

```asm
0x180008f20  mov     rax, rsp
0x180008f23  mov     [rax+10h], rbx
0x180008f27  mov     [rax+20h], rsi
0x180008f2b  push    rdi
0x180008f2c  sub     rsp, 20h
0x180008f30  mov     rbx, rdx
0x180008f33  mov     qword ptr [rax+18h], 0
0x180008f3b  mov     dil, cl
0x180008f3e  mov     dword ptr [rax+8], 0
0x180008f45  xor     edx, edx; dwFlags
0x180008f47  lea     rcx, ?wrapper@?1??Instance@ServiceHostTelemetry@@KAPEAV2@XZ@4V?$static_lazy@VServiceHostTelemetry@@@details@wil@@A; lpInitOnce
0x180008f4e  lea     r9, [rax+18h]; lpContext
0x180008f52  lea     r8, [rax+8]; fPending
0x180008f56  call    cs:__imp_InitOnceBeginInitialize
0x180008f5c  test    eax, eax
0x180008f5e  jz      loc_180008FF3
0x180008f64  cmp     [rsp+28h+arg_0], 0
0x180008f69  jz      loc_180008FF3
0x180008f6f  lea     rax, ??_7ServiceHostTelemetry@@6B@; const ServiceHostTelemetry::`vftable'
0x180008f76  mov     cs:qword_180019688, 0
0x180008f81  lea     rsi, qword_180019680
0x180008f88  mov     cs:qword_180019680, rax
0x180008f8f  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_ef7f6407c7d6d1282504bab1440f4cfe_@@CA@XZ; void (__cdecl *)()
0x180008f96  mov     [rsp+28h+arg_10], rsi
0x180008f9b  mov     cs:byte_180019690, 0
0x180008fa2  mov     cs:dword_180019694, 0
0x180008fac  call    atexit
0x180008fb1  call    ?Provider@ServiceHostLogging@@SAPEBU_tlgProvider_t@@XZ; ServiceHostLogging::Provider(void)
0x180008fb6  mov     cs:qword_180019688, rax
0x180008fbd  mov     rcx, rsi
0x180008fc0  mov     rax, cs:qword_180019680
0x180008fc7  mov     cs:byte_180019690, 0
0x180008fce  mov     cs:dword_180019694, 1
0x180008fd8  mov     rax, [rax+8]
0x180008fdc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008fe1  mov     r8, rsi; lpContext
0x180008fe4  lea     rcx, ?wrapper@?1??Instance@ServiceHostTelemetry@@KAPEAV2@XZ@4V?$static_lazy@VServiceHostTelemetry@@@details@wil@@A; lpInitOnce
0x180008feb  xor     edx, edx; dwFlags
0x180008fed  call    cs:__imp_InitOnceComplete
0x180008ff3  test    dil, dil
0x180008ff6  jnz     short loc_180009021
0x180008ff8  test    byte ptr [rbx+4], 2
0x180008ffc  jnz     short loc_180009021
0x180008ffe  mov     rcx, [rsp+28h+arg_10]; this
0x180009003  cmp     dword ptr [rcx+14h], 1
0x180009007  jnz     short loc_180009013
0x180009009  mov     rdx, rbx; struct wil::FailureInfo *
0x18000900c  call    ?ReportTelemetryFailure@TraceLoggingProvider@wil@@IEAAXAEBUFailureInfo@2@@Z; wil::TraceLoggingProvider::ReportTelemetryFailure(wil::FailureInfo const &)
0x180009011  jmp     short loc_180009021
0x180009013  cmp     dword ptr [rcx+14h], 2
0x180009017  jnz     short loc_180009021
0x180009019  mov     rdx, rbx; struct wil::FailureInfo *
0x18000901c  call    ?ReportTraceLoggingFailure@TraceLoggingProvider@wil@@IEAAXAEBUFailureInfo@2@@Z; wil::TraceLoggingProvider::ReportTraceLoggingFailure(wil::FailureInfo const &)
0x180009021  mov     rbx, [rsp+28h+arg_8]
0x180009026  mov     rsi, [rsp+28h+arg_18]
0x18000902b  add     rsp, 20h
0x18000902f  pop     rdi
0x180009030  retn
```
