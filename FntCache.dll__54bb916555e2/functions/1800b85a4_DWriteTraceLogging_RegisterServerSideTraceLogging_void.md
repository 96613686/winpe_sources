# DWriteTraceLogging::RegisterServerSideTraceLogging(void)

- ea: `0x1800b85a4`
- end: `0x1800b861e`
- name: `?RegisterServerSideTraceLogging@DWriteTraceLogging@@YAXXZ`
- size: `122`
- prototype: `void __fastcall(DWriteTraceLogging *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x1800aff28`

## callees

- `0x180001880`
- `0x1800aa650`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800b85ea`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800b85ea`
- `RPCRT4!UuidCreate` at `0x1800b85c9`
- `RPCRT4!UuidCreate` at `0x1800b85c9`

## pseudocode

```c
void __fastcall DWriteTraceLogging::RegisterServerSideTraceLogging(DWriteTraceLogging *this)
{
  UUID Uuid; // [rsp+20h] [rbp-28h] BYREF

  TraceLoggingRegisterEx_EventRegister_EventSetInformation(this);
  Uuid = 0;
  UuidCreate(&Uuid);
  DWriteTraceLogging::g_telemetryServerAggregator = (__int64)&g_hDWriteTraceLoggingProvider;
  xmmword_180142C2C = (__int128)Uuid;
  qword_180142C48 = GetTickCount64();
  qword_180142C40 = 20000;
  dword_180142C50 = 0;
}

```

## disassembly

```asm
0x1800b85a4  sub     rsp, 48h
0x1800b85a8  mov     rax, cs:__security_cookie
0x1800b85af  xor     rax, rsp
0x1800b85b2  mov     [rsp+48h+var_18], rax
0x1800b85b7  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x1800b85bc  xorps   xmm0, xmm0
0x1800b85bf  lea     rcx, [rsp+48h+Uuid]; Uuid
0x1800b85c4  movups  xmmword ptr [rsp+48h+Uuid.Data1], xmm0
0x1800b85c9  call    cs:__imp_UuidCreate
0x1800b85cf  movaps  xmm0, xmmword ptr [rsp+48h+Uuid.Data1]
0x1800b85d4  lea     rax, g_hDWriteTraceLoggingProvider
0x1800b85db  mov     cs:?g_telemetryServerAggregator@DWriteTraceLogging@@3V?$Aggregator@VTraceLoggingTimePolicy@DWriteTraceLogging@@V?$AggregationCircularArrayData@UDownloadManagerStats@DWriteTraceLogging@@$0BO@$00@2@UDownloadManagerStats@2@@1@A, rax; DWriteTraceLogging::Aggregator<DWriteTraceLogging::TraceLoggingTimePolicy,DWriteTraceLogging::AggregationCircularArrayData<DWriteTraceLogging::DownloadManagerStats,30,1>,DWriteTraceLogging::DownloadManagerStats> DWriteTraceLogging::g_telemetryServerAggregator
0x1800b85e2  movdqu  cs:xmmword_180142C2C, xmm0
0x1800b85ea  call    cs:__imp_GetTickCount64
0x1800b85f0  mov     cs:qword_180142C48, rax
0x1800b85f7  mov     cs:qword_180142C40, 4E20h
0x1800b8602  mov     cs:dword_180142C50, 0
0x1800b860c  mov     rcx, [rsp+48h+var_18]
0x1800b8611  xor     rcx, rsp; StackCookie
0x1800b8614  call    __security_check_cookie
0x1800b8619  add     rsp, 48h
0x1800b861d  retn
```
