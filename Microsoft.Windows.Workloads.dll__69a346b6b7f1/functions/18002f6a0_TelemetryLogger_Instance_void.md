# TelemetryLogger::Instance(void)

- ea: `0x18002f6a0`
- end: `0x18002f7a3`
- name: `?Instance@TelemetryLogger@@KAPEAV1@XZ`
- size: `259`
- prototype: `struct TelemetryLogger *(void)`
- caller_count: `6`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18002f640`
- `0x18002f7b0`
- `0x18002fa90`
- `0x18002fd20`
- `0x18002fd50`
- `0x18002fd80`

## callees

- `0x1800114a0`
- `0x18002f6a0`
- `0x180034ef0`
- `0x1800353fc`

## import_xrefs

- `KERNEL32!InitOnceBeginInitialize` at `0x18002f6cf`
- `KERNEL32!InitOnceBeginInitialize` at `0x18002f6cf`
- `KERNEL32!InitOnceComplete` at `0x18002f780`
- `KERNEL32!InitOnceComplete` at `0x18002f780`

## pseudocode

```c
struct TelemetryLogger *TelemetryLogger::Instance(void)
{
  void (*v0)(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, void *); // r8
  LPVOID Context; // [rsp+20h] [rbp-28h] BYREF
  BOOL fPending; // [rsp+28h] [rbp-20h] BYREF

  Context = 0;
  if ( InitOnceBeginInitialize(&`TelemetryLogger::Instance'::`2'::wrapper, 0, &fPending, &Context) && fPending )
  {
    qword_18005A0B0 = 0;
    Context = &qword_18005A0A8;
    byte_18005A0B8 = 0;
    dword_18005A0BC = 0;
    qword_18005A0A8 = &TelemetryLogger::`vftable';
    qword_18005A0E8 = 0;
    qword_18005A0C0 = (struct _tlgProvider_t *)&`TelemetryLogger::StaticHandle::StaticHandle'::`2'::__hInner;
    dword_18005A0F0 = 5;
    dword_18005A0F4 = 600;
    xmmword_18005A0C8 = 0;
    xmmword_18005A0D8 = 0;
    atexit(_lambda_d0de0aea0d9e121ad3b76698eff7e035_::_lambda_invoker_cdecl_);
    wil::TraceLoggingProvider::Register((wil::TraceLoggingProvider *)&qword_18005A0A8, qword_18005A0C0, v0);
    InitOnceComplete(&`TelemetryLogger::Instance'::`2'::wrapper, 0, &qword_18005A0A8);
  }
  return (struct TelemetryLogger *)Context;
}

```

## disassembly

```asm
0x18002f6a0  push    rdi
0x18002f6a2  sub     rsp, 40h
0x18002f6a6  mov     rax, cs:__security_cookie
0x18002f6ad  xor     rax, rsp
0x18002f6b0  mov     [rsp+48h+var_18], rax
0x18002f6b5  xor     edi, edi
0x18002f6b7  lea     r9, [rsp+48h+Context]; lpContext
0x18002f6bc  lea     r8, [rsp+48h+fPending]; fPending
0x18002f6c1  mov     [rsp+48h+Context], rdi
0x18002f6c6  xor     edx, edx; dwFlags
0x18002f6c8  lea     rcx, ?wrapper@?1??Instance@TelemetryLogger@@KAPEAV2@XZ@4V?$static_lazy@VTelemetryLogger@@@details@wil@@A; lpInitOnce
0x18002f6cf  call    cs:__imp_InitOnceBeginInitialize
0x18002f6d5  test    eax, eax
0x18002f6d7  jz      loc_18002F78B
0x18002f6dd  cmp     [rsp+48h+fPending], edi
0x18002f6e1  jz      loc_18002F78B
0x18002f6e7  mov     [rsp+48h+arg_0], rbx
0x18002f6ec  lea     rax, ??_7TelemetryLogger@@6B@; const TelemetryLogger::`vftable'
0x18002f6f3  lea     rbx, qword_18005A0A8
0x18002f6fa  mov     cs:qword_18005A0B0, rdi
0x18002f701  mov     [rsp+48h+Context], rbx
0x18002f706  mov     cs:byte_18005A0B8, dil
0x18002f70d  mov     cs:dword_18005A0BC, edi
0x18002f713  mov     cs:qword_18005A0A8, rax
0x18002f71a  lea     rax, ?__hInner@?1???0StaticHandle@TelemetryLogger@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `TelemetryLogger::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x18002f721  mov     cs:qword_18005A0E8, rdi
0x18002f728  xorps   xmm0, xmm0
0x18002f72b  mov     cs:qword_18005A0C0, rax
0x18002f732  xorps   xmm1, xmm1
0x18002f735  mov     cs:dword_18005A0F0, 5
0x18002f73f  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d0de0aea0d9e121ad3b76698eff7e035_@@CA@XZ; void (__cdecl *)()
0x18002f746  mov     cs:dword_18005A0F4, 258h
0x18002f750  movdqu  cs:xmmword_18005A0C8, xmm0
0x18002f758  movdqu  cs:xmmword_18005A0D8, xmm1
0x18002f760  call    atexit
0x18002f765  mov     rdx, cs:qword_18005A0C0; struct _tlgProvider_t *
0x18002f76c  mov     rcx, rbx; this
0x18002f76f  call    ?Register@TraceLoggingProvider@wil@@IEAAXQEBU_tlgProvider_t@@P6AXPEBU_GUID@@KE_K2PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z@Z; wil::TraceLoggingProvider::Register(_tlgProvider_t const * const,void (*)(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *))
0x18002f774  mov     r8, rbx; lpContext
0x18002f777  lea     rcx, ?wrapper@?1??Instance@TelemetryLogger@@KAPEAV2@XZ@4V?$static_lazy@VTelemetryLogger@@@details@wil@@A; lpInitOnce
0x18002f77e  xor     edx, edx; dwFlags
0x18002f780  call    cs:__imp_InitOnceComplete
0x18002f786  mov     rbx, [rsp+48h+arg_0]
0x18002f78b  mov     rax, [rsp+48h+Context]
0x18002f790  mov     rcx, [rsp+48h+var_18]
0x18002f795  xor     rcx, rsp; StackCookie
0x18002f798  call    __security_check_cookie
0x18002f79d  add     rsp, 40h
0x18002f7a1  pop     rdi
0x18002f7a2  retn
```
