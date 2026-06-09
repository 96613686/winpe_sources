# OfflineMapsTelemetry::Instance(void)

- ea: `0x18000824c`
- end: `0x180008326`
- name: `?Instance@OfflineMapsTelemetry@@KAPEAV1@XZ`
- size: `218`
- prototype: `struct OfflineMapsTelemetry *(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180009cc0`

## callees

- `0x180002030`
- `0x18000824c`
- `0x18000a2fc`
- `0x180010010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180008315`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180008315`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180008274`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180008274`

## pseudocode

```c
struct OfflineMapsTelemetry *OfflineMapsTelemetry::Instance(void)
{
  WINBOOL v1; // [rsp+30h] [rbp+8h] BYREF
  __int64 *v2; // [rsp+38h] [rbp+10h] BYREF

  v2 = 0;
  v1 = 0;
  if ( InitOnceBeginInitialize(&`OfflineMapsTelemetry::Instance'::`2'::wrapper, 0, &v1, (LPVOID *)&v2) && v1 )
  {
    qword_180018DA8 = 0;
    qword_180018DA0 = (__int64)&OfflineMapsTelemetry::`vftable';
    v2 = &qword_180018DA0;
    byte_180018DB0 = 0;
    dword_180018DB4 = 0;
    dword_180018DC8 = -1;
    atexit(_lambda_76ceee9f57f0a306d53fba4fb93de71e_::_lambda_invoker_cdecl_);
    qword_180018DA8 = (__int64)OfflineMapsTraceLogging::Provider();
    byte_180018DB0 = 0;
    dword_180018DB4 = 1;
    (*(void (__fastcall **)(__int64 *))(qword_180018DA0 + 8))(&qword_180018DA0);
    InitOnceComplete(&`OfflineMapsTelemetry::Instance'::`2'::wrapper, 0, &qword_180018DA0);
  }
  return (struct OfflineMapsTelemetry *)v2;
}

```

## disassembly

```asm
0x18000824c  mov     rax, rsp
0x18000824f  push    rbx
0x180008250  sub     rsp, 20h
0x180008254  lea     r9, [rax+10h]; lpContext
0x180008258  mov     qword ptr [rax+10h], 0
0x180008260  lea     r8, [rax+8]; fPending
0x180008264  mov     dword ptr [rax+8], 0
0x18000826b  xor     edx, edx; dwFlags
0x18000826d  lea     rcx, ?wrapper@?1??Instance@OfflineMapsTelemetry@@KAPEAV2@XZ@4V?$static_lazy@VOfflineMapsTelemetry@@@details@wil@@A; lpInitOnce
0x180008274  call    cs:__imp_InitOnceBeginInitialize
0x18000827a  test    eax, eax
0x18000827c  jz      loc_18000831B
0x180008282  cmp     [rsp+28h+arg_0], 0
0x180008287  jz      loc_18000831B
0x18000828d  lea     rax, ??_7OfflineMapsTelemetry@@6B@; const OfflineMapsTelemetry::`vftable'
0x180008294  mov     cs:qword_180018DA8, 0
0x18000829f  lea     rbx, qword_180018DA0
0x1800082a6  mov     cs:qword_180018DA0, rax
0x1800082ad  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_76ceee9f57f0a306d53fba4fb93de71e_@@CA@XZ; void (__cdecl *)()
0x1800082b4  mov     [rsp+28h+arg_8], rbx
0x1800082b9  mov     cs:byte_180018DB0, 0
0x1800082c0  mov     cs:dword_180018DB4, 0
0x1800082ca  mov     cs:dword_180018DC8, 0FFFFFFFFh
0x1800082d4  call    atexit
0x1800082d9  call    ?Provider@OfflineMapsTraceLogging@@SAPEBU_tlgProvider_t@@XZ; OfflineMapsTraceLogging::Provider(void)
0x1800082de  mov     cs:qword_180018DA8, rax
0x1800082e5  mov     rcx, rbx
0x1800082e8  mov     rax, cs:qword_180018DA0
0x1800082ef  mov     cs:byte_180018DB0, 0
0x1800082f6  mov     cs:dword_180018DB4, 1
0x180008300  mov     rax, [rax+8]
0x180008304  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008309  mov     r8, rbx; lpContext
0x18000830c  lea     rcx, ?wrapper@?1??Instance@OfflineMapsTelemetry@@KAPEAV2@XZ@4V?$static_lazy@VOfflineMapsTelemetry@@@details@wil@@A; lpInitOnce
0x180008313  xor     edx, edx; dwFlags
0x180008315  call    cs:__imp_InitOnceComplete
0x18000831b  mov     rax, [rsp+28h+arg_8]
0x180008320  add     rsp, 20h
0x180008324  pop     rbx
0x180008325  retn
```
