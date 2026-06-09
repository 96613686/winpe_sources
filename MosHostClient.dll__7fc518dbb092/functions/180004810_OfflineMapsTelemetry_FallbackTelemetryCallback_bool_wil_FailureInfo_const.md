# OfflineMapsTelemetry::FallbackTelemetryCallback(bool,wil::FailureInfo const &)

- ea: `0x180004810`
- end: `0x18000492b`
- name: `?FallbackTelemetryCallback@OfflineMapsTelemetry@@SAX_NAEBUFailureInfo@wil@@@Z`
- size: `283`
- prototype: `void __fastcall(char, const struct wil::FailureInfo *)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x180002900`
- `0x180004810`
- `0x180005c50`
- `0x180005f08`
- `0x180006070`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180004846`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180004846`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800048e7`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800048e7`

## pseudocode

```c
void __fastcall OfflineMapsTelemetry::FallbackTelemetryCallback(char a1, const struct wil::FailureInfo *a2)
{
  BOOL v4; // [rsp+30h] [rbp+8h] BYREF
  wil::TraceLoggingProvider *v5; // [rsp+40h] [rbp+18h] BYREF

  v5 = 0;
  v4 = 0;
  if ( InitOnceBeginInitialize(&`OfflineMapsTelemetry::Instance'::`2'::wrapper, 0, &v4, (LPVOID *)&v5) && v4 )
  {
    qword_18001C748 = 0;
    qword_18001C740 = (__int64)&OfflineMapsTelemetry::`vftable';
    v5 = (wil::TraceLoggingProvider *)&qword_18001C740;
    byte_18001C750 = 0;
    dword_18001C754 = 0;
    dword_18001C768 = -1;
    atexit(_lambda_76ceee9f57f0a306d53fba4fb93de71e_::_lambda_invoker_cdecl_);
    qword_18001C748 = (__int64)OfflineMapsTraceLogging::Provider();
    byte_18001C750 = 0;
    dword_18001C754 = 1;
    (*(void (__fastcall **)(__int64 *))(qword_18001C740 + 8))(&qword_18001C740);
    InitOnceComplete(&`OfflineMapsTelemetry::Instance'::`2'::wrapper, 0, &qword_18001C740);
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
0x180004810  mov     rax, rsp
0x180004813  mov     [rax+10h], rbx
0x180004817  mov     [rax+20h], rsi
0x18000481b  push    rdi
0x18000481c  sub     rsp, 20h
0x180004820  mov     rbx, rdx
0x180004823  mov     qword ptr [rax+18h], 0
0x18000482b  mov     dil, cl
0x18000482e  mov     dword ptr [rax+8], 0
0x180004835  xor     edx, edx; dwFlags
0x180004837  lea     rcx, ?wrapper@?1??Instance@OfflineMapsTelemetry@@KAPEAV2@XZ@4V?$static_lazy@VOfflineMapsTelemetry@@@details@wil@@A; lpInitOnce
0x18000483e  lea     r9, [rax+18h]; lpContext
0x180004842  lea     r8, [rax+8]; fPending
0x180004846  call    cs:__imp_InitOnceBeginInitialize
0x18000484c  test    eax, eax
0x18000484e  jz      loc_1800048ED
0x180004854  cmp     [rsp+28h+arg_0], 0
0x180004859  jz      loc_1800048ED
0x18000485f  lea     rax, ??_7OfflineMapsTelemetry@@6B@; const OfflineMapsTelemetry::`vftable'
0x180004866  mov     cs:qword_18001C748, 0
0x180004871  lea     rsi, qword_18001C740
0x180004878  mov     cs:qword_18001C740, rax
0x18000487f  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_76ceee9f57f0a306d53fba4fb93de71e_@@CA@XZ; void (__cdecl *)()
0x180004886  mov     [rsp+28h+arg_10], rsi
0x18000488b  mov     cs:byte_18001C750, 0
0x180004892  mov     cs:dword_18001C754, 0
0x18000489c  mov     cs:dword_18001C768, 0FFFFFFFFh
0x1800048a6  call    atexit
0x1800048ab  call    ?Provider@OfflineMapsTraceLogging@@SAPEBU_tlgProvider_t@@XZ; OfflineMapsTraceLogging::Provider(void)
0x1800048b0  mov     cs:qword_18001C748, rax
0x1800048b7  mov     rcx, rsi
0x1800048ba  mov     rax, cs:qword_18001C740
0x1800048c1  mov     cs:byte_18001C750, 0
0x1800048c8  mov     cs:dword_18001C754, 1
0x1800048d2  mov     rax, [rax+8]
0x1800048d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800048db  mov     r8, rsi; lpContext
0x1800048de  lea     rcx, ?wrapper@?1??Instance@OfflineMapsTelemetry@@KAPEAV2@XZ@4V?$static_lazy@VOfflineMapsTelemetry@@@details@wil@@A; lpInitOnce
0x1800048e5  xor     edx, edx; dwFlags
0x1800048e7  call    cs:__imp_InitOnceComplete
0x1800048ed  test    dil, dil
0x1800048f0  jnz     short loc_18000491B
0x1800048f2  test    byte ptr [rbx+4], 2
0x1800048f6  jnz     short loc_18000491B
0x1800048f8  mov     rcx, [rsp+28h+arg_10]; this
0x1800048fd  cmp     dword ptr [rcx+14h], 1
0x180004901  jnz     short loc_18000490D
0x180004903  mov     rdx, rbx; struct wil::FailureInfo *
0x180004906  call    ?ReportTelemetryFailure@TraceLoggingProvider@wil@@IEAAXAEBUFailureInfo@2@@Z; wil::TraceLoggingProvider::ReportTelemetryFailure(wil::FailureInfo const &)
0x18000490b  jmp     short loc_18000491B
0x18000490d  cmp     dword ptr [rcx+14h], 2
0x180004911  jnz     short loc_18000491B
0x180004913  mov     rdx, rbx; struct wil::FailureInfo *
0x180004916  call    ?ReportTraceLoggingFailure@TraceLoggingProvider@wil@@IEAAXAEBUFailureInfo@2@@Z; wil::TraceLoggingProvider::ReportTraceLoggingFailure(wil::FailureInfo const &)
0x18000491b  mov     rbx, [rsp+28h+arg_8]
0x180004920  mov     rsi, [rsp+28h+arg_18]
0x180004925  add     rsp, 20h
0x180004929  pop     rdi
0x18000492a  retn
```
