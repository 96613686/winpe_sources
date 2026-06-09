# PrintUtilLogging::Provider(void)

- ea: `0x180036454`
- end: `0x18003653d`
- name: `?Provider@PrintUtilLogging@@SAPEBU_tlgProvider_t@@XZ`
- size: `233`
- prototype: `const struct _tlgProvider_t *(void)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18003488c`
- `0x180035824`

## callees

- `0x180001008`
- `0x1800022c8`
- `0x180036454`
- `0x18005d010`

## import_xrefs

- `KERNEL32!InitOnceComplete` at `0x180036528`
- `KERNEL32!InitOnceComplete` at `0x180036528`
- `KERNEL32!InitOnceBeginInitialize` at `0x18003647c`
- `KERNEL32!InitOnceBeginInitialize` at `0x18003647c`

## pseudocode

```c
const struct _tlgProvider_t *PrintUtilLogging::Provider(void)
{
  BOOL v1; // [rsp+30h] [rbp+8h] BYREF
  __int64 *v2; // [rsp+38h] [rbp+10h] BYREF

  v2 = 0;
  v1 = 0;
  if ( InitOnceBeginInitialize(&`PrintUtilLogging::Instance'::`2'::wrapper, 0, &v1, (LPVOID *)&v2) && v1 )
  {
    qword_180074628 = 0;
    v2 = &qword_180074620;
    qword_180074620 = (__int64)&wil::TraceLoggingProvider::`vftable';
    byte_180074630 = 0;
    dword_180074634 = 0;
    CallbackContext = &`PrintUtilLogging::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(_lambda_2452e651ee40cf7f91dae90d69019a22_::_lambda_invoker_cdecl_);
    qword_180074628 = (__int64)CallbackContext;
    byte_180074630 = 1;
    TraceLoggingRegisterEx_EventRegister_2U(CallbackContext);
    dword_180074634 = 1;
    (*(void (__fastcall **)(__int64 *))(qword_180074620 + 8))(&qword_180074620);
    InitOnceComplete(&`PrintUtilLogging::Instance'::`2'::wrapper, 0, &qword_180074620);
  }
  return (const struct _tlgProvider_t *)v2[1];
}

```

## disassembly

```asm
0x180036454  mov     rax, rsp
0x180036457  push    rbx
0x180036458  sub     rsp, 20h
0x18003645c  lea     r9, [rax+10h]; lpContext
0x180036460  mov     qword ptr [rax+10h], 0
0x180036468  lea     r8, [rax+8]; fPending
0x18003646c  mov     dword ptr [rax+8], 0
0x180036473  xor     edx, edx; dwFlags
0x180036475  lea     rcx, ?wrapper@?1??Instance@PrintUtilLogging@@KAPEAV2@XZ@4V?$static_lazy@VPrintUtilLogging@@@details@wil@@A; lpInitOnce
0x18003647c  call    cs:__imp_InitOnceBeginInitialize
0x180036482  test    eax, eax
0x180036484  jz      loc_18003652E
0x18003648a  cmp     [rsp+28h+arg_0], 0
0x18003648f  jz      loc_18003652E
0x180036495  lea     rbx, qword_180074620
0x18003649c  mov     cs:qword_180074628, 0
0x1800364a7  lea     rax, ??_7TraceLoggingProvider@wil@@6B@; const wil::TraceLoggingProvider::`vftable'
0x1800364ae  mov     [rsp+28h+arg_8], rbx
0x1800364b3  mov     cs:qword_180074620, rax
0x1800364ba  mov     cs:byte_180074630, 0
0x1800364c1  mov     cs:dword_180074634, 0
0x1800364cb  lea     rax, ?__hInner@?1???0StaticHandle@PrintUtilLogging@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `PrintUtilLogging::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x1800364d2  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_2452e651ee40cf7f91dae90d69019a22_@@CA@XZ; void (__cdecl *)()
0x1800364d9  mov     cs:CallbackContext, rax
0x1800364e0  call    atexit
0x1800364e5  mov     rcx, cs:CallbackContext; CallbackContext
0x1800364ec  mov     cs:qword_180074628, rcx
0x1800364f3  mov     cs:byte_180074630, 1
0x1800364fa  call    TraceLoggingRegisterEx_EventRegister_2U
0x1800364ff  mov     rax, cs:qword_180074620
0x180036506  mov     rcx, rbx
0x180036509  mov     cs:dword_180074634, 1
0x180036513  mov     rax, [rax+8]
0x180036517  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003651c  mov     r8, rbx; lpContext
0x18003651f  lea     rcx, ?wrapper@?1??Instance@PrintUtilLogging@@KAPEAV2@XZ@4V?$static_lazy@VPrintUtilLogging@@@details@wil@@A; lpInitOnce
0x180036526  xor     edx, edx; dwFlags
0x180036528  call    cs:__imp_InitOnceComplete
0x18003652e  mov     rax, [rsp+28h+arg_8]
0x180036533  mov     rax, [rax+8]
0x180036537  add     rsp, 20h
0x18003653b  pop     rbx
0x18003653c  retn
```
