# wil::details::FeatureLogging::Instance(void)

- ea: `0x180019500`
- end: `0x1800195e5`
- name: `?Instance@FeatureLogging@details@wil@@KAPEAV123@XZ`
- size: `229`
- prototype: `struct wil::details::FeatureLogging *(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180018d40`

## callees

- `0x180001674`
- `0x180004098`
- `0x180019500`
- `0x180064010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800195d4`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800195d4`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180019528`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180019528`

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
    qword_180098A28 = 0;
    v2 = &qword_180098A20;
    qword_180098A20 = (__int64)&wil::details::FeatureLogging::`vftable';
    byte_180098A30 = 0;
    dword_180098A34 = 0;
    qword_180098A38 = &`wil::details::FeatureLogging::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(_lambda_120d0c6b51dc644cb63ed5c7fc62f6c3_::_lambda_invoker_cdecl_);
    qword_180098A28 = (__int64)qword_180098A38;
    byte_180098A30 = 1;
    TraceLoggingRegisterEx_EventRegister_EventSetInformation(qword_180098A38);
    dword_180098A34 = 1;
    (*(void (__fastcall **)(__int64 *))(qword_180098A20 + 8))(&qword_180098A20);
    InitOnceComplete(&`wil::details::FeatureLogging::Instance'::`2'::wrapper, 0, &qword_180098A20);
  }
  return (struct wil::details::FeatureLogging *)v2;
}

```

## disassembly

```asm
0x180019500  mov     rax, rsp
0x180019503  push    rbx
0x180019504  sub     rsp, 20h
0x180019508  lea     r9, [rax+10h]; lpContext
0x18001950c  mov     qword ptr [rax+10h], 0
0x180019514  lea     r8, [rax+8]; fPending
0x180019518  mov     dword ptr [rax+8], 0
0x18001951f  xor     edx, edx; dwFlags
0x180019521  lea     rcx, ?wrapper@?1??Instance@FeatureLogging@details@wil@@KAPEAV234@XZ@4V?$static_lazy@VFeatureLogging@details@wil@@@34@A; lpInitOnce
0x180019528  call    cs:__imp_InitOnceBeginInitialize
0x18001952e  test    eax, eax
0x180019530  jz      loc_1800195DA
0x180019536  cmp     [rsp+28h+arg_0], 0
0x18001953b  jz      loc_1800195DA
0x180019541  lea     rbx, qword_180098A20
0x180019548  mov     cs:qword_180098A28, 0
0x180019553  lea     rax, ??_7FeatureLogging@details@wil@@6B@; const wil::details::FeatureLogging::`vftable'
0x18001955a  mov     [rsp+28h+arg_8], rbx
0x18001955f  mov     cs:qword_180098A20, rax
0x180019566  mov     cs:byte_180098A30, 0
0x18001956d  mov     cs:dword_180098A34, 0
0x180019577  lea     rax, ?__hInner@?1???0StaticHandle@FeatureLogging@details@wil@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `wil::details::FeatureLogging::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x18001957e  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_120d0c6b51dc644cb63ed5c7fc62f6c3_@@CA@XZ; void (__cdecl *)()
0x180019585  mov     cs:qword_180098A38, rax
0x18001958c  call    atexit
0x180019591  mov     rcx, cs:qword_180098A38; CallbackContext
0x180019598  mov     cs:qword_180098A28, rcx
0x18001959f  mov     cs:byte_180098A30, 1
0x1800195a6  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x1800195ab  mov     rax, cs:qword_180098A20
0x1800195b2  mov     rcx, rbx
0x1800195b5  mov     cs:dword_180098A34, 1
0x1800195bf  mov     rax, [rax+8]
0x1800195c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800195c8  mov     r8, rbx; lpContext
0x1800195cb  lea     rcx, ?wrapper@?1??Instance@FeatureLogging@details@wil@@KAPEAV234@XZ@4V?$static_lazy@VFeatureLogging@details@wil@@@34@A; lpInitOnce
0x1800195d2  xor     edx, edx; dwFlags
0x1800195d4  call    cs:__imp_InitOnceComplete
0x1800195da  mov     rax, [rsp+28h+arg_8]
0x1800195df  add     rsp, 20h
0x1800195e3  pop     rbx
0x1800195e4  retn
```
