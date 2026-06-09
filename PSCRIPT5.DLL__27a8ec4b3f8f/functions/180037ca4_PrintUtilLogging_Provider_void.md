# PrintUtilLogging::Provider(void)

- ea: `0x180037ca4`
- end: `0x180037d9a`
- name: `?Provider@PrintUtilLogging@@SAPEBU_tlgProvider_t@@XZ`
- size: `246`
- prototype: `const struct _tlgProvider_t *(void)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180035fb4`
- `0x180036fb0`

## callees

- `0x180001008`
- `0x180002308`
- `0x180037ca4`
- `0x18005f010`

## import_xrefs

- `KERNEL32!InitOnceComplete` at `0x180037d7e`
- `KERNEL32!InitOnceComplete` at `0x180037d7e`
- `KERNEL32!InitOnceBeginInitialize` at `0x180037ccc`
- `KERNEL32!InitOnceBeginInitialize` at `0x180037ccc`

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
    qword_180076618 = 0;
    v2 = &qword_180076610;
    qword_180076610 = (__int64)&wil::TraceLoggingProvider::`vftable';
    byte_180076620 = 0;
    dword_180076624 = 0;
    CallbackContext = &`PrintUtilLogging::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(_lambda_2452e651ee40cf7f91dae90d69019a22_::_lambda_invoker_cdecl_);
    qword_180076618 = (__int64)CallbackContext;
    byte_180076620 = 1;
    TraceLoggingRegisterEx_EventRegister_2U(CallbackContext);
    dword_180076624 = 1;
    (*(void (__fastcall **)(__int64 *))(qword_180076610 + 8))(&qword_180076610);
    InitOnceComplete(&`PrintUtilLogging::Instance'::`2'::wrapper, 0, &qword_180076610);
  }
  return (const struct _tlgProvider_t *)v2[1];
}

```

## disassembly

```asm
0x180037ca4  mov     rax, rsp
0x180037ca7  push    rbx
0x180037ca8  sub     rsp, 20h
0x180037cac  lea     r9, [rax+10h]; lpContext
0x180037cb0  mov     qword ptr [rax+10h], 0
0x180037cb8  lea     r8, [rax+8]; fPending
0x180037cbc  mov     dword ptr [rax+8], 0
0x180037cc3  xor     edx, edx; dwFlags
0x180037cc5  lea     rcx, ?wrapper@?1??Instance@PrintUtilLogging@@KAPEAV2@XZ@4V?$static_lazy@VPrintUtilLogging@@@details@wil@@A; lpInitOnce
0x180037ccc  call    cs:__imp_InitOnceBeginInitialize
0x180037cd3  nop     dword ptr [rax+rax+00h]
0x180037cd8  test    eax, eax
0x180037cda  jz      loc_180037D8A
0x180037ce0  cmp     [rsp+28h+arg_0], 0
0x180037ce5  jz      loc_180037D8A
0x180037ceb  lea     rbx, qword_180076610
0x180037cf2  mov     cs:qword_180076618, 0
0x180037cfd  lea     rax, ??_7TraceLoggingProvider@wil@@6B@; const wil::TraceLoggingProvider::`vftable'
0x180037d04  mov     [rsp+28h+arg_8], rbx
0x180037d09  mov     cs:qword_180076610, rax
0x180037d10  mov     cs:byte_180076620, 0
0x180037d17  mov     cs:dword_180076624, 0
0x180037d21  lea     rax, ?__hInner@?1???0StaticHandle@PrintUtilLogging@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `PrintUtilLogging::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x180037d28  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_2452e651ee40cf7f91dae90d69019a22_@@CA@XZ; void (__cdecl *)()
0x180037d2f  mov     cs:CallbackContext, rax
0x180037d36  call    atexit
0x180037d3b  mov     rcx, cs:CallbackContext; CallbackContext
0x180037d42  mov     cs:qword_180076618, rcx
0x180037d49  mov     cs:byte_180076620, 1
0x180037d50  call    TraceLoggingRegisterEx_EventRegister_2U
0x180037d55  mov     rax, cs:qword_180076610
0x180037d5c  mov     rcx, rbx
0x180037d5f  mov     cs:dword_180076624, 1
0x180037d69  mov     rax, [rax+8]
0x180037d6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037d72  mov     r8, rbx; lpContext
0x180037d75  lea     rcx, ?wrapper@?1??Instance@PrintUtilLogging@@KAPEAV2@XZ@4V?$static_lazy@VPrintUtilLogging@@@details@wil@@A; lpInitOnce
0x180037d7c  xor     edx, edx; dwFlags
0x180037d7e  call    cs:__imp_InitOnceComplete
0x180037d85  nop     dword ptr [rax+rax+00h]
0x180037d8a  mov     rax, [rsp+28h+arg_8]
0x180037d8f  mov     rax, [rax+8]
0x180037d93  add     rsp, 20h
0x180037d97  pop     rbx
0x180037d98  retn
```
