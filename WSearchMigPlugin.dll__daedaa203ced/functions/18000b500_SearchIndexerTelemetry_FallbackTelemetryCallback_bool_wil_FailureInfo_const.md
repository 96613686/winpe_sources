# SearchIndexerTelemetry::FallbackTelemetryCallback(bool,wil::FailureInfo const &)

- ea: `0x18000b500`
- end: `0x18000b5f3`
- name: `?FallbackTelemetryCallback@SearchIndexerTelemetry@@SAX_NAEBUFailureInfo@wil@@@Z`
- size: `243`
- prototype: `void __fastcall(bool, const struct wil::FailureInfo *)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180002b7c`
- `0x18000b500`
- `0x18000b730`
- `0x18000b93c`
- `0x180018010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000b5cd`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000b5cd`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18000b536`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18000b536`

## pseudocode

```c
void __fastcall SearchIndexerTelemetry::FallbackTelemetryCallback(bool a1, const struct wil::FailureInfo *a2)
{
  WINBOOL v4; // [rsp+40h] [rbp+18h] BYREF
  SearchIndexerTelemetry *v5; // [rsp+48h] [rbp+20h] BYREF

  v5 = 0;
  v4 = 0;
  if ( InitOnceBeginInitialize(&`SearchIndexerTelemetry::Instance'::`2'::wrapper, 0, &v4, (LPVOID *)&v5) && v4 )
  {
    qword_180025FB8 = 0;
    qword_180025FB0 = (__int64)&SearchIndexerTelemetry::`vftable';
    v5 = (SearchIndexerTelemetry *)&qword_180025FB0;
    byte_180025FC0 = 0;
    dword_180025FC4 = 0;
    atexit(_lambda_fb7600e3a88af5fe7cde97f26e161ee5_::_lambda_invoker_cdecl_);
    qword_180025FB8 = (__int64)SearchIndexerLogging::Provider();
    byte_180025FC0 = 0;
    dword_180025FC4 = 1;
    (*(void (__fastcall **)(__int64 *))(qword_180025FB0 + 8))(&qword_180025FB0);
    InitOnceComplete(&`SearchIndexerTelemetry::Instance'::`2'::wrapper, 0, &qword_180025FB0);
  }
  SearchIndexerTelemetry::OnErrorReported(v5, a1, a2);
}

```

## disassembly

```asm
0x18000b500  mov     rax, rsp
0x18000b503  mov     [rax+8], rbx
0x18000b507  mov     [rax+10h], rsi
0x18000b50b  push    rdi
0x18000b50c  sub     rsp, 20h
0x18000b510  mov     rbx, rdx
0x18000b513  mov     qword ptr [rax+20h], 0
0x18000b51b  mov     dil, cl
0x18000b51e  mov     dword ptr [rax+18h], 0
0x18000b525  xor     edx, edx; dwFlags
0x18000b527  lea     rcx, ?wrapper@?1??Instance@SearchIndexerTelemetry@@KAPEAV2@XZ@4V?$static_lazy@VSearchIndexerTelemetry@@@details@wil@@A; lpInitOnce
0x18000b52e  lea     r9, [rax+20h]; lpContext
0x18000b532  lea     r8, [rax+18h]; fPending
0x18000b536  call    cs:__imp_InitOnceBeginInitialize
0x18000b53c  test    eax, eax
0x18000b53e  jz      loc_18000B5D3
0x18000b544  cmp     [rsp+28h+arg_10], 0
0x18000b549  jz      loc_18000B5D3
0x18000b54f  lea     rax, ??_7SearchIndexerTelemetry@@6B@; const SearchIndexerTelemetry::`vftable'
0x18000b556  mov     cs:qword_180025FB8, 0
0x18000b561  lea     rsi, qword_180025FB0
0x18000b568  mov     cs:qword_180025FB0, rax
0x18000b56f  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_fb7600e3a88af5fe7cde97f26e161ee5_@@CA@XZ; void (__cdecl *)()
0x18000b576  mov     [rsp+28h+arg_18], rsi
0x18000b57b  mov     cs:byte_180025FC0, 0
0x18000b582  mov     cs:dword_180025FC4, 0
0x18000b58c  call    atexit
0x18000b591  call    ?Provider@SearchIndexerLogging@@SAPEBU_tlgProvider_t@@XZ; SearchIndexerLogging::Provider(void)
0x18000b596  mov     cs:qword_180025FB8, rax
0x18000b59d  mov     rcx, rsi
0x18000b5a0  mov     rax, cs:qword_180025FB0
0x18000b5a7  mov     cs:byte_180025FC0, 0
0x18000b5ae  mov     cs:dword_180025FC4, 1
0x18000b5b8  mov     rax, [rax+8]
0x18000b5bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b5c1  mov     r8, rsi; lpContext
0x18000b5c4  lea     rcx, ?wrapper@?1??Instance@SearchIndexerTelemetry@@KAPEAV2@XZ@4V?$static_lazy@VSearchIndexerTelemetry@@@details@wil@@A; lpInitOnce
0x18000b5cb  xor     edx, edx; dwFlags
0x18000b5cd  call    cs:__imp_InitOnceComplete
0x18000b5d3  mov     rcx, [rsp+28h+arg_18]; this
0x18000b5d8  mov     r8, rbx; struct wil::FailureInfo *
0x18000b5db  mov     dl, dil; bool
0x18000b5de  call    ?OnErrorReported@SearchIndexerTelemetry@@UEAAX_NAEBUFailureInfo@wil@@@Z; SearchIndexerTelemetry::OnErrorReported(bool,wil::FailureInfo const &)
0x18000b5e3  mov     rbx, [rsp+28h+arg_0]
0x18000b5e8  mov     rsi, [rsp+28h+arg_8]
0x18000b5ed  add     rsp, 20h
0x18000b5f1  pop     rdi
0x18000b5f2  retn
```
