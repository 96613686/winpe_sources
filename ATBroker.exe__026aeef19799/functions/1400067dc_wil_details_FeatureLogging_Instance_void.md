# wil::details::FeatureLogging::Instance(void)

- ea: `0x1400067dc`
- end: `0x1400068c1`
- name: `?Instance@FeatureLogging@details@wil@@KAPEAV123@XZ`
- size: `229`
- prototype: `struct wil::details::FeatureLogging *(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140004ee0`

## callees

- `0x140001950`
- `0x1400023e4`
- `0x1400067dc`
- `0x140017010`

## import_xrefs

- `KERNEL32!InitOnceComplete` at `0x1400068b0`
- `KERNEL32!InitOnceComplete` at `0x1400068b0`
- `KERNEL32!InitOnceBeginInitialize` at `0x140006804`
- `KERNEL32!InitOnceBeginInitialize` at `0x140006804`

## pseudocode

```c
struct wil::details::FeatureLogging *wil::details::FeatureLogging::Instance(void)
{
  WINBOOL v1; // [rsp+30h] [rbp+8h] BYREF
  __int64 *v2; // [rsp+38h] [rbp+10h] BYREF

  v2 = 0;
  v1 = 0;
  if ( InitOnceBeginInitialize(&`wil::details::FeatureLogging::Instance'::`2'::wrapper, 0, &v1, (LPVOID *)&v2) && v1 )
  {
    qword_140021250 = 0;
    v2 = &qword_140021248;
    qword_140021248 = (__int64)&wil::details::FeatureLogging::`vftable';
    byte_140021258 = 0;
    dword_14002125C = 0;
    CallbackContext = &`wil::details::FeatureLogging::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(_lambda_120d0c6b51dc644cb63ed5c7fc62f6c3_::_lambda_invoker_cdecl_);
    qword_140021250 = (__int64)CallbackContext;
    byte_140021258 = 1;
    TraceLoggingRegisterEx_EventRegister_EventSetInformation(CallbackContext);
    dword_14002125C = 1;
    (*(void (__fastcall **)(__int64 *))(qword_140021248 + 8))(&qword_140021248);
    InitOnceComplete(&`wil::details::FeatureLogging::Instance'::`2'::wrapper, 0, &qword_140021248);
  }
  return (struct wil::details::FeatureLogging *)v2;
}

```

## disassembly

```asm
0x1400067dc  mov     rax, rsp
0x1400067df  push    rbx
0x1400067e0  sub     rsp, 20h
0x1400067e4  lea     r9, [rax+10h]; lpContext
0x1400067e8  mov     qword ptr [rax+10h], 0
0x1400067f0  lea     r8, [rax+8]; fPending
0x1400067f4  mov     dword ptr [rax+8], 0
0x1400067fb  xor     edx, edx; dwFlags
0x1400067fd  lea     rcx, ?wrapper@?1??Instance@FeatureLogging@details@wil@@KAPEAV234@XZ@4V?$static_lazy@VFeatureLogging@details@wil@@@34@A; lpInitOnce
0x140006804  call    cs:__imp_InitOnceBeginInitialize
0x14000680a  test    eax, eax
0x14000680c  jz      loc_1400068B6
0x140006812  cmp     [rsp+28h+arg_0], 0
0x140006817  jz      loc_1400068B6
0x14000681d  lea     rbx, qword_140021248
0x140006824  mov     cs:qword_140021250, 0
0x14000682f  lea     rax, ??_7FeatureLogging@details@wil@@6B@; const wil::details::FeatureLogging::`vftable'
0x140006836  mov     [rsp+28h+arg_8], rbx
0x14000683b  mov     cs:qword_140021248, rax
0x140006842  mov     cs:byte_140021258, 0
0x140006849  mov     cs:dword_14002125C, 0
0x140006853  lea     rax, ?__hInner@?1???0StaticHandle@FeatureLogging@details@wil@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `wil::details::FeatureLogging::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x14000685a  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_120d0c6b51dc644cb63ed5c7fc62f6c3_@@CA@XZ; void (__cdecl *)()
0x140006861  mov     cs:CallbackContext, rax
0x140006868  call    atexit
0x14000686d  mov     rcx, cs:CallbackContext; CallbackContext
0x140006874  mov     cs:qword_140021250, rcx
0x14000687b  mov     cs:byte_140021258, 1
0x140006882  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x140006887  mov     rax, cs:qword_140021248
0x14000688e  mov     rcx, rbx
0x140006891  mov     cs:dword_14002125C, 1
0x14000689b  mov     rax, [rax+8]
0x14000689f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400068a4  mov     r8, rbx; lpContext
0x1400068a7  lea     rcx, ?wrapper@?1??Instance@FeatureLogging@details@wil@@KAPEAV234@XZ@4V?$static_lazy@VFeatureLogging@details@wil@@@34@A; lpInitOnce
0x1400068ae  xor     edx, edx; dwFlags
0x1400068b0  call    cs:__imp_InitOnceComplete
0x1400068b6  mov     rax, [rsp+28h+arg_8]
0x1400068bb  add     rsp, 20h
0x1400068bf  pop     rbx
0x1400068c0  retn
```
