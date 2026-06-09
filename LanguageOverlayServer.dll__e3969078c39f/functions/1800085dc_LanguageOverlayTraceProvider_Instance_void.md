# LanguageOverlayTraceProvider::Instance(void)

- ea: `0x1800085dc`
- end: `0x180008691`
- name: `?Instance@LanguageOverlayTraceProvider@@KAPEAV1@XZ`
- size: `181`
- prototype: `struct LanguageOverlayTraceProvider *(void)`
- caller_count: `64`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180007870`
- `0x18000be14`
- `0x18000e2d0`
- `0x18001046c`
- `0x180010598`
- `0x180010738`
- `0x180010890`
- `0x180010b30`
- `0x1800130b0`
- `0x180014d20`
- `0x180015b20`
- `0x180015ea0`
- `0x180016210`
- `0x1800168e8`
- `0x180016a64`
- `0x180016b98`
- `0x180016cc4`
- `0x180016e1c`
- `0x180016f74`
- `0x1800170d0`
- `0x180017370`
- `0x180017610`
- `0x18001a4e8`
- `0x18002e5fc`
- `0x18002fb74`
- `0x18002fc5c`
- `0x18002fd44`
- `0x18002fee0`
- `0x180030180`
- `0x180030420`
- `0x1800346fc`
- `0x1800382f4`
- `0x1800383e0`
- `0x18003b1a4`
- `0x18003b2d8`
- `0x18003b470`
- `0x18003b780`
- `0x18003ba20`
- `0x180040060`
- `0x1800401e8`
- `0x1800407dc`
- `0x180040c4c`
- `0x180040e24`
- `0x180040e60`
- `0x180041038`
- `0x180041a78`
- `0x1800464dc`
- `0x180046668`
- `0x180046750`
- `0x180046a90`

## callees

- `0x180003e80`
- `0x1800085dc`
- `0x180008a1c`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180008680`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180008680`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180008604`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180008604`

## pseudocode

```c
struct LanguageOverlayTraceProvider *LanguageOverlayTraceProvider::Instance(void)
{
  void (*v0)(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, void *); // r8
  WINBOOL v2; // [rsp+30h] [rbp+8h] BYREF
  LPVOID v3; // [rsp+38h] [rbp+10h] BYREF

  v3 = 0;
  v2 = 0;
  if ( InitOnceBeginInitialize(&`LanguageOverlayTraceProvider::Instance'::`2'::wrapper, 0, &v2, &v3) && v2 )
  {
    qword_18008A1C8 = 0;
    v3 = &qword_18008A1C0;
    qword_18008A1C0 = &wil::details::FeatureLogging::`vftable';
    byte_18008A1D0 = 0;
    dword_18008A1D4 = 0;
    qword_18008A1D8 = (struct _tlgProvider_t *)&`LanguageOverlayTraceProvider::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(_lambda_d44f55dc24bcb5ef14112b4d240a5cc8_::_lambda_invoker_cdecl_);
    wil::TraceLoggingProvider::Register((wil::TraceLoggingProvider *)&qword_18008A1C0, qword_18008A1D8, v0);
    InitOnceComplete(&`LanguageOverlayTraceProvider::Instance'::`2'::wrapper, 0, &qword_18008A1C0);
  }
  return (struct LanguageOverlayTraceProvider *)v3;
}

```

## disassembly

```asm
0x1800085dc  mov     rax, rsp
0x1800085df  push    rbx
0x1800085e0  sub     rsp, 20h
0x1800085e4  lea     r9, [rax+10h]; lpContext
0x1800085e8  mov     qword ptr [rax+10h], 0
0x1800085f0  lea     r8, [rax+8]; fPending
0x1800085f4  mov     dword ptr [rax+8], 0
0x1800085fb  xor     edx, edx; dwFlags
0x1800085fd  lea     rcx, ?wrapper@?1??Instance@LanguageOverlayTraceProvider@@KAPEAV2@XZ@4V?$static_lazy@VLanguageOverlayTraceProvider@@@details@wil@@A; lpInitOnce
0x180008604  call    cs:__imp_InitOnceBeginInitialize
0x18000860a  test    eax, eax
0x18000860c  jz      short loc_180008686
0x18000860e  cmp     [rsp+28h+arg_0], 0
0x180008613  jz      short loc_180008686
0x180008615  lea     rbx, qword_18008A1C0
0x18000861c  mov     cs:qword_18008A1C8, 0
0x180008627  lea     rax, ??_7FeatureLogging@details@wil@@6B@; const wil::details::FeatureLogging::`vftable'
0x18000862e  mov     [rsp+28h+arg_8], rbx
0x180008633  mov     cs:qword_18008A1C0, rax
0x18000863a  mov     cs:byte_18008A1D0, 0
0x180008641  mov     cs:dword_18008A1D4, 0
0x18000864b  lea     rax, ?__hInner@?1???0StaticHandle@LanguageOverlayTraceProvider@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `LanguageOverlayTraceProvider::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x180008652  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d44f55dc24bcb5ef14112b4d240a5cc8_@@CA@XZ; void (__cdecl *)()
0x180008659  mov     cs:qword_18008A1D8, rax
0x180008660  call    atexit
0x180008665  mov     rdx, cs:qword_18008A1D8; struct _tlgProvider_t *
0x18000866c  mov     rcx, rbx; this
0x18000866f  call    ?Register@TraceLoggingProvider@wil@@IEAAXQEBU_tlgProvider_t@@P6AXPEBU_GUID@@KE_K2PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z@Z; wil::TraceLoggingProvider::Register(_tlgProvider_t const * const,void (*)(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *))
0x180008674  mov     r8, rbx; lpContext
0x180008677  lea     rcx, ?wrapper@?1??Instance@LanguageOverlayTraceProvider@@KAPEAV2@XZ@4V?$static_lazy@VLanguageOverlayTraceProvider@@@details@wil@@A; lpInitOnce
0x18000867e  xor     edx, edx; dwFlags
0x180008680  call    cs:__imp_InitOnceComplete
0x180008686  mov     rax, [rsp+28h+arg_8]
0x18000868b  add     rsp, 20h
0x18000868f  pop     rbx
0x180008690  retn
```
