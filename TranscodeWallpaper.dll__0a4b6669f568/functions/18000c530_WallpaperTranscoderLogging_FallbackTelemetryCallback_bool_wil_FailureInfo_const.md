# WallpaperTranscoderLogging::FallbackTelemetryCallback(bool,wil::FailureInfo const &)

- ea: `0x18000c530`
- end: `0x18000c626`
- name: `?FallbackTelemetryCallback@WallpaperTranscoderLogging@@SAX_NAEBUFailureInfo@wil@@@Z`
- size: `246`
- prototype: `void __fastcall(char, const struct wil::FailureInfo *)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180002520`
- `0x180009b70`
- `0x180009dd4`
- `0x180009f3c`
- `0x18000c530`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000c5e2`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000c5e2`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18000c566`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18000c566`

## pseudocode

```c
void __fastcall WallpaperTranscoderLogging::FallbackTelemetryCallback(char a1, const struct wil::FailureInfo *a2)
{
  void (*v4)(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, void *); // r8
  BOOL v5; // [rsp+30h] [rbp+8h] BYREF
  wil::TraceLoggingProvider *v6; // [rsp+40h] [rbp+18h] BYREF

  v6 = 0;
  v5 = 0;
  if ( InitOnceBeginInitialize(&`WallpaperTranscoderLogging::Instance'::`2'::wrapper, 0, &v5, (LPVOID *)&v6) && v5 )
  {
    qword_1800166F8 = 0;
    v6 = (wil::TraceLoggingProvider *)&qword_1800166F0;
    qword_1800166F0 = &WallpaperTranscoderLogging::`vftable';
    byte_180016700 = 0;
    dword_180016704 = 0;
    qword_180016708 = (struct _tlgProvider_t *)&`WallpaperTranscoderLogging::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(_lambda_e8fea64e46132d3cb550827628f2707b_::_lambda_invoker_cdecl_);
    wil::TraceLoggingProvider::Register((wil::TraceLoggingProvider *)&qword_1800166F0, qword_180016708, v4);
    InitOnceComplete(&`WallpaperTranscoderLogging::Instance'::`2'::wrapper, 0, &qword_1800166F0);
  }
  if ( !a1 && (*((_BYTE *)a2 + 4) & 2) == 0 )
  {
    if ( *((_DWORD *)v6 + 5) == 1 )
    {
      wil::TraceLoggingProvider::ReportTelemetryFailure(v6, a2);
    }
    else if ( *((_DWORD *)v6 + 5) == 2 )
    {
      wil::TraceLoggingProvider::ReportTraceLoggingFailure(v6, a2);
    }
  }
}

```

## disassembly

```asm
0x18000c530  mov     rax, rsp
0x18000c533  mov     [rax+10h], rbx
0x18000c537  mov     [rax+20h], rsi
0x18000c53b  push    rdi
0x18000c53c  sub     rsp, 20h
0x18000c540  mov     rbx, rdx
0x18000c543  mov     qword ptr [rax+18h], 0
0x18000c54b  mov     dil, cl
0x18000c54e  mov     dword ptr [rax+8], 0
0x18000c555  xor     edx, edx; dwFlags
0x18000c557  lea     rcx, ?wrapper@?1??Instance@WallpaperTranscoderLogging@@KAPEAV2@XZ@4V?$static_lazy@VWallpaperTranscoderLogging@@@details@wil@@A; lpInitOnce
0x18000c55e  lea     r9, [rax+18h]; lpContext
0x18000c562  lea     r8, [rax+8]; fPending
0x18000c566  call    cs:__imp_InitOnceBeginInitialize
0x18000c56c  test    eax, eax
0x18000c56e  jz      short loc_18000C5E8
0x18000c570  cmp     [rsp+28h+arg_0], 0
0x18000c575  jz      short loc_18000C5E8
0x18000c577  lea     rsi, qword_1800166F0
0x18000c57e  mov     cs:qword_1800166F8, 0
0x18000c589  lea     rax, ??_7WallpaperTranscoderLogging@@6B@; const WallpaperTranscoderLogging::`vftable'
0x18000c590  mov     [rsp+28h+arg_10], rsi
0x18000c595  mov     cs:qword_1800166F0, rax
0x18000c59c  mov     cs:byte_180016700, 0
0x18000c5a3  mov     cs:dword_180016704, 0
0x18000c5ad  lea     rax, ?__hInner@?1???0StaticHandle@WallpaperTranscoderLogging@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `WallpaperTranscoderLogging::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x18000c5b4  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_e8fea64e46132d3cb550827628f2707b_@@CA@XZ; void (__cdecl *)()
0x18000c5bb  mov     cs:qword_180016708, rax
0x18000c5c2  call    atexit
0x18000c5c7  mov     rdx, cs:qword_180016708; struct _tlgProvider_t *
0x18000c5ce  mov     rcx, rsi; this
0x18000c5d1  call    ?Register@TraceLoggingProvider@wil@@IEAAXQEBU_tlgProvider_t@@P6AXPEBU_GUID@@KE_K2PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z@Z; wil::TraceLoggingProvider::Register(_tlgProvider_t const * const,void (*)(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *))
0x18000c5d6  mov     r8, rsi; lpContext
0x18000c5d9  lea     rcx, ?wrapper@?1??Instance@WallpaperTranscoderLogging@@KAPEAV2@XZ@4V?$static_lazy@VWallpaperTranscoderLogging@@@details@wil@@A; lpInitOnce
0x18000c5e0  xor     edx, edx; dwFlags
0x18000c5e2  call    cs:__imp_InitOnceComplete
0x18000c5e8  test    dil, dil
0x18000c5eb  jnz     short loc_18000C616
0x18000c5ed  test    byte ptr [rbx+4], 2
0x18000c5f1  jnz     short loc_18000C616
0x18000c5f3  mov     rcx, [rsp+28h+arg_10]; this
0x18000c5f8  cmp     dword ptr [rcx+14h], 1
0x18000c5fc  jnz     short loc_18000C608
0x18000c5fe  mov     rdx, rbx; struct wil::FailureInfo *
0x18000c601  call    ?ReportTelemetryFailure@TraceLoggingProvider@wil@@IEAAXAEBUFailureInfo@2@@Z; wil::TraceLoggingProvider::ReportTelemetryFailure(wil::FailureInfo const &)
0x18000c606  jmp     short loc_18000C616
0x18000c608  cmp     dword ptr [rcx+14h], 2
0x18000c60c  jnz     short loc_18000C616
0x18000c60e  mov     rdx, rbx; struct wil::FailureInfo *
0x18000c611  call    ?ReportTraceLoggingFailure@TraceLoggingProvider@wil@@IEAAXAEBUFailureInfo@2@@Z; wil::TraceLoggingProvider::ReportTraceLoggingFailure(wil::FailureInfo const &)
0x18000c616  mov     rbx, [rsp+28h+arg_8]
0x18000c61b  mov     rsi, [rsp+28h+arg_18]
0x18000c620  add     rsp, 20h
0x18000c624  pop     rdi
0x18000c625  retn
```
