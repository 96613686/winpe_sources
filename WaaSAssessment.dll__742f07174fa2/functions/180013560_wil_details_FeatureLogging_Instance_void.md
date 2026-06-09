# wil::details::FeatureLogging::Instance(void)

- ea: `0x180013560`
- end: `0x180013645`
- name: `?Instance@FeatureLogging@details@wil@@KAPEAV123@XZ`
- size: `229`
- prototype: `struct wil::details::FeatureLogging *(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180011b50`

## callees

- `0x180001950`
- `0x180002b08`
- `0x180013560`
- `0x18001b010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180013588`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180013588`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180013634`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180013634`

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
    qword_180027D68 = 0;
    v2 = &qword_180027D60;
    qword_180027D60 = (__int64)&wil::details::FeatureLogging::`vftable';
    byte_180027D70 = 0;
    dword_180027D74 = 0;
    CallbackContext = &`wil::details::FeatureLogging::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(_lambda_120d0c6b51dc644cb63ed5c7fc62f6c3_::_lambda_invoker_cdecl_);
    qword_180027D68 = (__int64)CallbackContext;
    byte_180027D70 = 1;
    TraceLoggingRegisterEx_EventRegister_EventSetInformation(CallbackContext);
    dword_180027D74 = 1;
    (*(void (__fastcall **)(__int64 *))(qword_180027D60 + 8))(&qword_180027D60);
    InitOnceComplete(&`wil::details::FeatureLogging::Instance'::`2'::wrapper, 0, &qword_180027D60);
  }
  return (struct wil::details::FeatureLogging *)v2;
}

```

## disassembly

```asm
0x180013560  mov     rax, rsp
0x180013563  push    rbx
0x180013564  sub     rsp, 20h
0x180013568  lea     r9, [rax+10h]; lpContext
0x18001356c  mov     qword ptr [rax+10h], 0
0x180013574  lea     r8, [rax+8]; fPending
0x180013578  mov     dword ptr [rax+8], 0
0x18001357f  xor     edx, edx; dwFlags
0x180013581  lea     rcx, ?wrapper@?1??Instance@FeatureLogging@details@wil@@KAPEAV234@XZ@4V?$static_lazy@VFeatureLogging@details@wil@@@34@A; lpInitOnce
0x180013588  call    cs:__imp_InitOnceBeginInitialize
0x18001358e  test    eax, eax
0x180013590  jz      loc_18001363A
0x180013596  cmp     [rsp+28h+arg_0], 0
0x18001359b  jz      loc_18001363A
0x1800135a1  lea     rbx, qword_180027D60
0x1800135a8  mov     cs:qword_180027D68, 0
0x1800135b3  lea     rax, ??_7FeatureLogging@details@wil@@6B@; const wil::details::FeatureLogging::`vftable'
0x1800135ba  mov     [rsp+28h+arg_8], rbx
0x1800135bf  mov     cs:qword_180027D60, rax
0x1800135c6  mov     cs:byte_180027D70, 0
0x1800135cd  mov     cs:dword_180027D74, 0
0x1800135d7  lea     rax, ?__hInner@?1???0StaticHandle@FeatureLogging@details@wil@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `wil::details::FeatureLogging::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x1800135de  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_120d0c6b51dc644cb63ed5c7fc62f6c3_@@CA@XZ; void (__cdecl *)()
0x1800135e5  mov     cs:CallbackContext, rax
0x1800135ec  call    atexit
0x1800135f1  mov     rcx, cs:CallbackContext; CallbackContext
0x1800135f8  mov     cs:qword_180027D68, rcx
0x1800135ff  mov     cs:byte_180027D70, 1
0x180013606  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x18001360b  mov     rax, cs:qword_180027D60
0x180013612  mov     rcx, rbx
0x180013615  mov     cs:dword_180027D74, 1
0x18001361f  mov     rax, [rax+8]
0x180013623  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013628  mov     r8, rbx; lpContext
0x18001362b  lea     rcx, ?wrapper@?1??Instance@FeatureLogging@details@wil@@KAPEAV234@XZ@4V?$static_lazy@VFeatureLogging@details@wil@@@34@A; lpInitOnce
0x180013632  xor     edx, edx; dwFlags
0x180013634  call    cs:__imp_InitOnceComplete
0x18001363a  mov     rax, [rsp+28h+arg_8]
0x18001363f  add     rsp, 20h
0x180013643  pop     rbx
0x180013644  retn
```
