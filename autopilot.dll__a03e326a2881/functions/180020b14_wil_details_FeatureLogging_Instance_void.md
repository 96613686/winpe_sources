# wil::details::FeatureLogging::Instance(void)

- ea: `0x180020b14`
- end: `0x180020bc9`
- name: `?Instance@FeatureLogging@details@wil@@KAPEAV123@XZ`
- size: `181`
- prototype: `struct wil::details::FeatureLogging *(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18001fed0`

## callees

- `0x1800049c8`
- `0x18000fca8`
- `0x180020b14`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180020b3c`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180020b3c`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180020bb8`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180020bb8`

## pseudocode

```c
struct wil::details::FeatureLogging *wil::details::FeatureLogging::Instance(void)
{
  void (*v0)(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, void *); // r8
  WINBOOL v2; // [rsp+30h] [rbp+8h] BYREF
  LPVOID v3; // [rsp+38h] [rbp+10h] BYREF

  v3 = 0;
  v2 = 0;
  if ( __std_init_once_begin_initialize(&`wil::details::FeatureLogging::Instance'::`2'::wrapper, 0, &v2, &v3) && v2 )
  {
    qword_180043AE8 = 0;
    v3 = &qword_180043AE0;
    qword_180043AE0 = &AutoPilotTelemProvider::`vftable';
    byte_180043AF0 = 0;
    dword_180043AF4 = 0;
    qword_180043AF8 = (struct _tlgProvider_t *)&`wil::details::FeatureLogging::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(_lambda_120d0c6b51dc644cb63ed5c7fc62f6c3_::_lambda_invoker_cdecl_);
    wil::TraceLoggingProvider::Register((wil::TraceLoggingProvider *)&qword_180043AE0, qword_180043AF8, v0);
    InitOnceComplete(&`wil::details::FeatureLogging::Instance'::`2'::wrapper, 0, &qword_180043AE0);
  }
  return (struct wil::details::FeatureLogging *)v3;
}

```

## disassembly

```asm
0x180020b14  mov     rax, rsp
0x180020b17  push    rbx
0x180020b18  sub     rsp, 20h
0x180020b1c  lea     r9, [rax+10h]; lpContext
0x180020b20  mov     qword ptr [rax+10h], 0
0x180020b28  lea     r8, [rax+8]; fPending
0x180020b2c  mov     dword ptr [rax+8], 0
0x180020b33  xor     edx, edx; dwFlags
0x180020b35  lea     rcx, ?wrapper@?1??Instance@FeatureLogging@details@wil@@KAPEAV234@XZ@4V?$static_lazy@VFeatureLogging@details@wil@@@34@A; lpInitOnce
0x180020b3c  call    cs:__imp___std_init_once_begin_initialize
0x180020b42  test    eax, eax
0x180020b44  jz      short loc_180020BBE
0x180020b46  cmp     [rsp+28h+arg_0], 0
0x180020b4b  jz      short loc_180020BBE
0x180020b4d  lea     rbx, qword_180043AE0
0x180020b54  mov     cs:qword_180043AE8, 0
0x180020b5f  lea     rax, ??_7AutoPilotTelemProvider@@6B@; const AutoPilotTelemProvider::`vftable'
0x180020b66  mov     [rsp+28h+arg_8], rbx
0x180020b6b  mov     cs:qword_180043AE0, rax
0x180020b72  mov     cs:byte_180043AF0, 0
0x180020b79  mov     cs:dword_180043AF4, 0
0x180020b83  lea     rax, ?__hInner@?1???0StaticHandle@FeatureLogging@details@wil@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `wil::details::FeatureLogging::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x180020b8a  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_120d0c6b51dc644cb63ed5c7fc62f6c3_@@CA@XZ; void (__cdecl *)()
0x180020b91  mov     cs:qword_180043AF8, rax
0x180020b98  call    atexit
0x180020b9d  mov     rdx, cs:qword_180043AF8; struct _tlgProvider_t *
0x180020ba4  mov     rcx, rbx; this
0x180020ba7  call    ?Register@TraceLoggingProvider@wil@@IEAAXQEBU_tlgProvider_t@@P6AXPEBU_GUID@@KE_K2PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z@Z; wil::TraceLoggingProvider::Register(_tlgProvider_t const * const,void (*)(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *))
0x180020bac  mov     r8, rbx; lpContext
0x180020baf  lea     rcx, ?wrapper@?1??Instance@FeatureLogging@details@wil@@KAPEAV234@XZ@4V?$static_lazy@VFeatureLogging@details@wil@@@34@A; lpInitOnce
0x180020bb6  xor     edx, edx; dwFlags
0x180020bb8  call    cs:__imp_InitOnceComplete
0x180020bbe  mov     rax, [rsp+28h+arg_8]
0x180020bc3  add     rsp, 20h
0x180020bc7  pop     rbx
0x180020bc8  retn
```
