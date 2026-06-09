# wil::details::FeatureLogging::Instance(void)

- ea: `0x18002fa0c`
- end: `0x18002fac1`
- name: `?Instance@FeatureLogging@details@wil@@KAPEAV123@XZ`
- size: `181`
- prototype: `struct wil::details::FeatureLogging *(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18002f520`

## callees

- `0x180002978`
- `0x180009eb8`
- `0x18002fa0c`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18002fab0`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18002fab0`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18002fa34`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18002fa34`

## pseudocode

```c
struct wil::details::FeatureLogging *wil::details::FeatureLogging::Instance(void)
{
  void (*v0)(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, void *); // r8
  WINBOOL v2; // [rsp+30h] [rbp+8h] BYREF
  LPVOID v3; // [rsp+38h] [rbp+10h] BYREF

  v3 = 0;
  v2 = 0;
  if ( InitOnceBeginInitialize(&`wil::details::FeatureLogging::Instance'::`2'::wrapper, 0, &v2, &v3) && v2 )
  {
    qword_180042290 = 0;
    v3 = &qword_180042288;
    qword_180042288 = &wil::details::FeatureLogging::`vftable';
    byte_180042298 = 0;
    dword_18004229C = 0;
    qword_1800422A0 = (struct _tlgProvider_t *)&`wil::details::FeatureLogging::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(_lambda_120d0c6b51dc644cb63ed5c7fc62f6c3_::_lambda_invoker_cdecl_);
    wil::TraceLoggingProvider::Register((wil::TraceLoggingProvider *)&qword_180042288, qword_1800422A0, v0);
    InitOnceComplete(&`wil::details::FeatureLogging::Instance'::`2'::wrapper, 0, &qword_180042288);
  }
  return (struct wil::details::FeatureLogging *)v3;
}

```

## disassembly

```asm
0x18002fa0c  mov     rax, rsp
0x18002fa0f  push    rbx
0x18002fa10  sub     rsp, 20h
0x18002fa14  lea     r9, [rax+10h]; lpContext
0x18002fa18  mov     qword ptr [rax+10h], 0
0x18002fa20  lea     r8, [rax+8]; fPending
0x18002fa24  mov     dword ptr [rax+8], 0
0x18002fa2b  xor     edx, edx; dwFlags
0x18002fa2d  lea     rcx, ?wrapper@?1??Instance@FeatureLogging@details@wil@@KAPEAV234@XZ@4V?$static_lazy@VFeatureLogging@details@wil@@@34@A; lpInitOnce
0x18002fa34  call    cs:__imp_InitOnceBeginInitialize
0x18002fa3a  test    eax, eax
0x18002fa3c  jz      short loc_18002FAB6
0x18002fa3e  cmp     [rsp+28h+arg_0], 0
0x18002fa43  jz      short loc_18002FAB6
0x18002fa45  lea     rbx, qword_180042288
0x18002fa4c  mov     cs:qword_180042290, 0
0x18002fa57  lea     rax, ??_7FeatureLogging@details@wil@@6B@; const wil::details::FeatureLogging::`vftable'
0x18002fa5e  mov     [rsp+28h+arg_8], rbx
0x18002fa63  mov     cs:qword_180042288, rax
0x18002fa6a  mov     cs:byte_180042298, 0
0x18002fa71  mov     cs:dword_18004229C, 0
0x18002fa7b  lea     rax, ?__hInner@?1???0StaticHandle@FeatureLogging@details@wil@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `wil::details::FeatureLogging::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x18002fa82  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_120d0c6b51dc644cb63ed5c7fc62f6c3_@@CA@XZ; void (__cdecl *)()
0x18002fa89  mov     cs:qword_1800422A0, rax
0x18002fa90  call    atexit
0x18002fa95  mov     rdx, cs:qword_1800422A0; struct _tlgProvider_t *
0x18002fa9c  mov     rcx, rbx; this
0x18002fa9f  call    ?Register@TraceLoggingProvider@wil@@IEAAXQEBU_tlgProvider_t@@P6AXPEBU_GUID@@KE_K2PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z@Z; wil::TraceLoggingProvider::Register(_tlgProvider_t const * const,void (*)(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *))
0x18002faa4  mov     r8, rbx; lpContext
0x18002faa7  lea     rcx, ?wrapper@?1??Instance@FeatureLogging@details@wil@@KAPEAV234@XZ@4V?$static_lazy@VFeatureLogging@details@wil@@@34@A; lpInitOnce
0x18002faae  xor     edx, edx; dwFlags
0x18002fab0  call    cs:__imp_InitOnceComplete
0x18002fab6  mov     rax, [rsp+28h+arg_8]
0x18002fabb  add     rsp, 20h
0x18002fabf  pop     rbx
0x18002fac0  retn
```
