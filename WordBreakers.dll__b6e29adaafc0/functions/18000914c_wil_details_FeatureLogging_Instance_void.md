# wil::details::FeatureLogging::Instance(void)

- ea: `0x18000914c`
- end: `0x180009231`
- name: `?Instance@FeatureLogging@details@wil@@KAPEAV123@XZ`
- size: `229`
- prototype: `struct wil::details::FeatureLogging *(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180008340`

## callees

- `0x180001950`
- `0x180002718`
- `0x18000914c`
- `0x18000c010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180009174`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180009174`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180009220`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180009220`

## pseudocode

```c
struct wil::details::FeatureLogging *wil::details::FeatureLogging::Instance(void)
{
  BOOL v1; // [rsp+30h] [rbp+8h] BYREF
  __int64 *v2; // [rsp+38h] [rbp+10h] BYREF

  v2 = 0;
  v1 = 0;
  if ( InitOnceBeginInitialize(&`wil::details::FeatureLogging::Instance'::`2'::wrapper, 0, &v1, (LPVOID *)&v2) && v1 )
  {
    qword_180012C80 = 0;
    v2 = &qword_180012C78;
    qword_180012C78 = (__int64)&wil::details::FeatureLogging::`vftable';
    byte_180012C88 = 0;
    dword_180012C8C = 0;
    CallbackContext = &`wil::details::FeatureLogging::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(_lambda_120d0c6b51dc644cb63ed5c7fc62f6c3_::_lambda_invoker_cdecl_);
    qword_180012C80 = (__int64)CallbackContext;
    byte_180012C88 = 1;
    TraceLoggingRegisterEx_EventRegister_EventSetInformation(CallbackContext);
    dword_180012C8C = 1;
    (*(void (__fastcall **)(__int64 *))(qword_180012C78 + 8))(&qword_180012C78);
    InitOnceComplete(&`wil::details::FeatureLogging::Instance'::`2'::wrapper, 0, &qword_180012C78);
  }
  return (struct wil::details::FeatureLogging *)v2;
}

```

## disassembly

```asm
0x18000914c  mov     rax, rsp
0x18000914f  push    rbx
0x180009150  sub     rsp, 20h
0x180009154  lea     r9, [rax+10h]; lpContext
0x180009158  mov     qword ptr [rax+10h], 0
0x180009160  lea     r8, [rax+8]; fPending
0x180009164  mov     dword ptr [rax+8], 0
0x18000916b  xor     edx, edx; dwFlags
0x18000916d  lea     rcx, ?wrapper@?1??Instance@FeatureLogging@details@wil@@KAPEAV234@XZ@4V?$static_lazy@VFeatureLogging@details@wil@@@34@A; lpInitOnce
0x180009174  call    cs:__imp_InitOnceBeginInitialize
0x18000917a  test    eax, eax
0x18000917c  jz      loc_180009226
0x180009182  cmp     [rsp+28h+arg_0], 0
0x180009187  jz      loc_180009226
0x18000918d  lea     rbx, qword_180012C78
0x180009194  mov     cs:qword_180012C80, 0
0x18000919f  lea     rax, ??_7FeatureLogging@details@wil@@6B@; const wil::details::FeatureLogging::`vftable'
0x1800091a6  mov     [rsp+28h+arg_8], rbx
0x1800091ab  mov     cs:qword_180012C78, rax
0x1800091b2  mov     cs:byte_180012C88, 0
0x1800091b9  mov     cs:dword_180012C8C, 0
0x1800091c3  lea     rax, ?__hInner@?1???0StaticHandle@FeatureLogging@details@wil@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `wil::details::FeatureLogging::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x1800091ca  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_120d0c6b51dc644cb63ed5c7fc62f6c3_@@CA@XZ; void (__cdecl *)()
0x1800091d1  mov     cs:CallbackContext, rax
0x1800091d8  call    atexit
0x1800091dd  mov     rcx, cs:CallbackContext; CallbackContext
0x1800091e4  mov     cs:qword_180012C80, rcx
0x1800091eb  mov     cs:byte_180012C88, 1
0x1800091f2  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x1800091f7  mov     rax, cs:qword_180012C78
0x1800091fe  mov     rcx, rbx
0x180009201  mov     cs:dword_180012C8C, 1
0x18000920b  mov     rax, [rax+8]
0x18000920f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009214  mov     r8, rbx; lpContext
0x180009217  lea     rcx, ?wrapper@?1??Instance@FeatureLogging@details@wil@@KAPEAV234@XZ@4V?$static_lazy@VFeatureLogging@details@wil@@@34@A; lpInitOnce
0x18000921e  xor     edx, edx; dwFlags
0x180009220  call    cs:__imp_InitOnceComplete
0x180009226  mov     rax, [rsp+28h+arg_8]
0x18000922b  add     rsp, 20h
0x18000922f  pop     rbx
0x180009230  retn
```
