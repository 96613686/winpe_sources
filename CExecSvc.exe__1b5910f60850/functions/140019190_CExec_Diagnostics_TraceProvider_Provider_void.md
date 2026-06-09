# CExec::Diagnostics::TraceProvider::Provider(void)

- ea: `0x140019190`
- end: `0x140019297`
- name: `?Provider@TraceProvider@Diagnostics@CExec@@SAPEBU_tlgProvider_t@@XZ`
- size: `263`
- prototype: `const struct _tlgProvider_t *(void)`
- caller_count: `10`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x14001565c`
- `0x140018e90`
- `0x1400196a0`
- `0x1400197f4`
- `0x140019948`
- `0x140019a9c`
- `0x140019bd0`
- `0x140019ea0`
- `0x14001a170`
- `0x14001ae44`

## callees

- `0x140001008`
- `0x140002310`
- `0x140002698`
- `0x140019190`
- `0x140024010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1400191c9`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1400191c9`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x140019275`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x140019275`

## pseudocode

```c
const struct _tlgProvider_t *CExec::Diagnostics::TraceProvider::Provider(void)
{
  LPVOID Context; // [rsp+20h] [rbp-28h] BYREF
  WINBOOL fPending; // [rsp+28h] [rbp-20h] BYREF

  Context = 0;
  fPending = 0;
  if ( InitOnceBeginInitialize(&`CExec::Diagnostics::TraceProvider::Instance'::`2'::wrapper, 0, &fPending, &Context)
    && fPending )
  {
    qword_14003A6E0 = 0;
    Context = &qword_14003A6D8;
    qword_14003A6D8 = (__int64)&CExec::Diagnostics::TraceProvider::`vftable';
    byte_14003A6E8 = 0;
    dword_14003A6EC = 0;
    CallbackContext = &`CExec::Diagnostics::TraceProvider::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(_lambda_cad52a63d25ea3a489c0b680e9f45eec_::_lambda_invoker_cdecl_);
    qword_14003A6E0 = (__int64)CallbackContext;
    byte_14003A6E8 = 1;
    TraceLoggingRegisterEx_EventRegister_EventSetInformation(CallbackContext);
    dword_14003A6EC = 1;
    (*(void (__fastcall **)(__int64 *))(qword_14003A6D8 + 8))(&qword_14003A6D8);
    InitOnceComplete(&`CExec::Diagnostics::TraceProvider::Instance'::`2'::wrapper, 0, &qword_14003A6D8);
  }
  return (const struct _tlgProvider_t *)*((_QWORD *)Context + 1);
}

```

## disassembly

```asm
0x140019190  push    rbx
0x140019192  sub     rsp, 40h
0x140019196  mov     rax, cs:__security_cookie
0x14001919d  xor     rax, rsp
0x1400191a0  mov     [rsp+48h+var_18], rax
0x1400191a5  lea     r9, [rsp+48h+Context]; lpContext
0x1400191aa  mov     [rsp+48h+Context], 0
0x1400191b3  lea     r8, [rsp+48h+fPending]; fPending
0x1400191b8  mov     [rsp+48h+fPending], 0
0x1400191c0  xor     edx, edx; dwFlags
0x1400191c2  lea     rcx, ?wrapper@?1??Instance@TraceProvider@Diagnostics@CExec@@KAPEAV234@XZ@4V?$static_lazy@VTraceProvider@Diagnostics@CExec@@@details@wil@@A; lpInitOnce
0x1400191c9  call    cs:__imp_InitOnceBeginInitialize
0x1400191cf  test    eax, eax
0x1400191d1  jz      loc_14001927B
0x1400191d7  cmp     [rsp+48h+fPending], 0
0x1400191dc  jz      loc_14001927B
0x1400191e2  lea     rbx, qword_14003A6D8
0x1400191e9  mov     cs:qword_14003A6E0, 0
0x1400191f4  lea     rax, ??_7TraceProvider@Diagnostics@CExec@@6B@; const CExec::Diagnostics::TraceProvider::`vftable'
0x1400191fb  mov     [rsp+48h+Context], rbx
0x140019200  mov     cs:qword_14003A6D8, rax
0x140019207  mov     cs:byte_14003A6E8, 0
0x14001920e  mov     cs:dword_14003A6EC, 0
0x140019218  lea     rax, ?__hInner@?1???0StaticHandle@TraceProvider@Diagnostics@CExec@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `CExec::Diagnostics::TraceProvider::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x14001921f  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_cad52a63d25ea3a489c0b680e9f45eec_@@CA@XZ; void (__cdecl *)()
0x140019226  mov     cs:CallbackContext, rax
0x14001922d  call    atexit
0x140019232  mov     rcx, cs:CallbackContext; CallbackContext
0x140019239  mov     cs:qword_14003A6E0, rcx
0x140019240  mov     cs:byte_14003A6E8, 1
0x140019247  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x14001924c  mov     rax, cs:qword_14003A6D8
0x140019253  mov     rcx, rbx
0x140019256  mov     cs:dword_14003A6EC, 1
0x140019260  mov     rax, [rax+8]
0x140019264  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140019269  mov     r8, rbx; lpContext
0x14001926c  lea     rcx, ?wrapper@?1??Instance@TraceProvider@Diagnostics@CExec@@KAPEAV234@XZ@4V?$static_lazy@VTraceProvider@Diagnostics@CExec@@@details@wil@@A; lpInitOnce
0x140019273  xor     edx, edx; dwFlags
0x140019275  call    cs:__imp_InitOnceComplete
0x14001927b  mov     rax, [rsp+48h+Context]
0x140019280  mov     rax, [rax+8]
0x140019284  mov     rcx, [rsp+48h+var_18]
0x140019289  xor     rcx, rsp; StackCookie
0x14001928c  call    __security_check_cookie
0x140019291  add     rsp, 40h
0x140019295  pop     rbx
0x140019296  retn
```
