# TelemetryLogger::Instance(void)

- ea: `0x1800116f0`
- end: `0x1800117f3`
- name: `?Instance@TelemetryLogger@@KAPEAV1@XZ`
- size: `259`
- prototype: `struct TelemetryLogger *(void)`
- caller_count: `13`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180007ef0`
- `0x18000e830`
- `0x18000f240`
- `0x18000f840`
- `0x180010480`
- `0x180010950`
- `0x180010e20`
- `0x180010ee0`
- `0x180010f10`
- `0x180010fe0`
- `0x1800112f0`
- `0x1800115f0`
- `0x1800153b0`

## callees

- `0x1800116f0`
- `0x1800121d0`
- `0x1800181b0`
- `0x180018598`

## import_xrefs

- `KERNEL32!InitOnceBeginInitialize` at `0x18001171f`
- `KERNEL32!InitOnceBeginInitialize` at `0x18001171f`
- `KERNEL32!InitOnceComplete` at `0x1800117d0`
- `KERNEL32!InitOnceComplete` at `0x1800117d0`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
struct TelemetryLogger *TelemetryLogger::Instance(void)
{
  void (*v0)(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, void *); // r8
  LPVOID Context; // [rsp+20h] [rbp-28h] BYREF
  BOOL fPending; // [rsp+28h] [rbp-20h] BYREF

  Context = 0;
  if ( InitOnceBeginInitialize(&`TelemetryLogger::Instance'::`2'::wrapper, 0, &fPending, &Context) && fPending )
  {
    qword_18002E6A0 = 0;
    Context = &qword_18002E698;
    byte_18002E6A8 = 0;
    dword_18002E6AC = 0;
    qword_18002E698 = &TelemetryLogger::`vftable';
    qword_18002E6D8 = 0;
    qword_18002E6B0 = (struct _tlgProvider_t *)&`TelemetryLogger::StaticHandle::StaticHandle'::`2'::__hInner;
    dword_18002E6E0 = 5;
    dword_18002E6E4 = 600;
    xmmword_18002E6B8 = 0;
    xmmword_18002E6C8 = 0;
    atexit(_lambda_d0de0aea0d9e121ad3b76698eff7e035_::_lambda_invoker_cdecl_);
    wil::TraceLoggingProvider::Register((wil::TraceLoggingProvider *)&qword_18002E698, qword_18002E6B0, v0);
    InitOnceComplete(&`TelemetryLogger::Instance'::`2'::wrapper, 0, &qword_18002E698);
  }
  return (struct TelemetryLogger *)Context;
}

```

## disassembly

```asm
0x1800116f0  push    rdi
0x1800116f2  sub     rsp, 40h
0x1800116f6  mov     rax, cs:__security_cookie
0x1800116fd  xor     rax, rsp
0x180011700  mov     [rsp+48h+var_18], rax
0x180011705  xor     edi, edi
0x180011707  lea     r9, [rsp+48h+Context]; lpContext
0x18001170c  lea     r8, [rsp+48h+fPending]; fPending
0x180011711  mov     [rsp+48h+Context], rdi
0x180011716  xor     edx, edx; dwFlags
0x180011718  lea     rcx, ?wrapper@?1??Instance@TelemetryLogger@@KAPEAV2@XZ@4V?$static_lazy@VTelemetryLogger@@@details@wil@@A; lpInitOnce
0x18001171f  call    cs:__imp_InitOnceBeginInitialize
0x180011725  test    eax, eax
0x180011727  jz      loc_1800117DB
0x18001172d  cmp     [rsp+48h+fPending], edi
0x180011731  jz      loc_1800117DB
0x180011737  mov     [rsp+48h+arg_0], rbx
0x18001173c  lea     rax, ??_7TelemetryLogger@@6B@; const TelemetryLogger::`vftable'
0x180011743  lea     rbx, qword_18002E698
0x18001174a  mov     cs:qword_18002E6A0, rdi
0x180011751  mov     [rsp+48h+Context], rbx
0x180011756  mov     cs:byte_18002E6A8, dil
0x18001175d  mov     cs:dword_18002E6AC, edi
0x180011763  mov     cs:qword_18002E698, rax
0x18001176a  lea     rax, ?__hInner@?1???0StaticHandle@TelemetryLogger@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `TelemetryLogger::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x180011771  mov     cs:qword_18002E6D8, rdi
0x180011778  xorps   xmm0, xmm0
0x18001177b  mov     cs:qword_18002E6B0, rax
0x180011782  xorps   xmm1, xmm1
0x180011785  mov     cs:dword_18002E6E0, 5
0x18001178f  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d0de0aea0d9e121ad3b76698eff7e035_@@CA@XZ; void (__cdecl *)()
0x180011796  mov     cs:dword_18002E6E4, 258h
0x1800117a0  movdqu  cs:xmmword_18002E6B8, xmm0
0x1800117a8  movdqu  cs:xmmword_18002E6C8, xmm1
0x1800117b0  call    atexit
0x1800117b5  mov     rdx, cs:qword_18002E6B0; struct _tlgProvider_t *
0x1800117bc  mov     rcx, rbx; this
0x1800117bf  call    ?Register@TraceLoggingProvider@wil@@IEAAXQEBU_tlgProvider_t@@P6AXPEBU_GUID@@KE_K2PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z@Z; wil::TraceLoggingProvider::Register(_tlgProvider_t const * const,void (*)(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *))
0x1800117c4  mov     r8, rbx; lpContext
0x1800117c7  lea     rcx, ?wrapper@?1??Instance@TelemetryLogger@@KAPEAV2@XZ@4V?$static_lazy@VTelemetryLogger@@@details@wil@@A; lpInitOnce
0x1800117ce  xor     edx, edx; dwFlags
0x1800117d0  call    cs:__imp_InitOnceComplete
0x1800117d6  mov     rbx, [rsp+48h+arg_0]
0x1800117db  mov     rax, [rsp+48h+Context]
0x1800117e0  mov     rcx, [rsp+48h+var_18]
0x1800117e5  xor     rcx, rsp; StackCookie
0x1800117e8  call    __security_check_cookie
0x1800117ed  add     rsp, 40h
0x1800117f1  pop     rdi
0x1800117f2  retn
```
