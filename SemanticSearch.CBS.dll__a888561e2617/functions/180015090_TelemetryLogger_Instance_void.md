# TelemetryLogger::Instance(void)

- ea: `0x180015090`
- end: `0x180015193`
- name: `?Instance@TelemetryLogger@@KAPEAV1@XZ`
- size: `259`
- prototype: `struct TelemetryLogger *(void)`
- caller_count: `49`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000a0d0`
- `0x18000a440`
- `0x18000a5b0`
- `0x18000ae40`
- `0x18000b2a0`
- `0x18000ba70`
- `0x18000bba0`
- `0x18000bdd0`
- `0x180014880`
- `0x1800148b0`
- `0x180014980`
- `0x180014c90`
- `0x180014f90`
- `0x1800151a0`
- `0x180017080`
- `0x180017600`
- `0x180017760`
- `0x180018550`
- `0x18001b880`
- `0x18001bb90`
- `0x18001bfc0`
- `0x18001c120`
- `0x18001cc80`
- `0x180033980`
- `0x180033af0`
- `0x180033e10`
- `0x180034290`
- `0x180034b20`
- `0x180034c70`
- `0x180034f70`
- `0x18003f9f0`
- `0x18003fb50`
- `0x1800406a0`
- `0x180042ff0`
- `0x180051770`
- `0x180051d80`
- `0x180052120`
- `0x1800524e0`
- `0x1800528b0`
- `0x180052c90`
- `0x180053610`
- `0x180053fa0`
- `0x180054370`
- `0x1800583b0`
- `0x180058d60`
- `0x180059130`
- `0x180059520`
- `0x180059980`
- `0x18005bc90`

## callees

- `0x180015090`
- `0x180015560`
- `0x18004c070`
- `0x18004c8ac`

## import_xrefs

- `KERNEL32!InitOnceBeginInitialize` at `0x1800150bf`
- `KERNEL32!InitOnceBeginInitialize` at `0x1800150bf`
- `KERNEL32!InitOnceComplete` at `0x180015170`
- `KERNEL32!InitOnceComplete` at `0x180015170`

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
    qword_1800866B0 = 0;
    Context = &qword_1800866A8;
    byte_1800866B8 = 0;
    dword_1800866BC = 0;
    qword_1800866A8 = &TelemetryLogger::`vftable';
    qword_1800866E8 = 0;
    qword_1800866C0 = (struct _tlgProvider_t *)&`TelemetryLogger::StaticHandle::StaticHandle'::`2'::__hInner;
    dword_1800866F0 = 5;
    dword_1800866F4 = 600;
    xmmword_1800866C8 = 0;
    xmmword_1800866D8 = 0;
    atexit(`TelemetryLogger::Instance'::`2'::_lambda_1_::_lambda_invoker_cdecl_);
    wil::TraceLoggingProvider::Register((wil::TraceLoggingProvider *)&qword_1800866A8, qword_1800866C0, v0);
    InitOnceComplete(&`TelemetryLogger::Instance'::`2'::wrapper, 0, &qword_1800866A8);
  }
  return (struct TelemetryLogger *)Context;
}

```

## disassembly

```asm
0x180015090  push    rdi
0x180015092  sub     rsp, 40h
0x180015096  mov     rax, cs:__security_cookie
0x18001509d  xor     rax, rsp
0x1800150a0  mov     [rsp+48h+var_18], rax
0x1800150a5  xor     edi, edi
0x1800150a7  lea     r9, [rsp+48h+Context]; lpContext
0x1800150ac  lea     r8, [rsp+48h+fPending]; fPending
0x1800150b1  mov     [rsp+48h+Context], rdi
0x1800150b6  xor     edx, edx; dwFlags
0x1800150b8  lea     rcx, ?wrapper@?1??Instance@TelemetryLogger@@KAPEAV2@XZ@4V?$static_lazy@VTelemetryLogger@@@details@wil@@A; lpInitOnce
0x1800150bf  call    cs:__imp_InitOnceBeginInitialize
0x1800150c5  test    eax, eax
0x1800150c7  jz      loc_18001517B
0x1800150cd  cmp     [rsp+48h+fPending], edi
0x1800150d1  jz      loc_18001517B
0x1800150d7  mov     [rsp+48h+arg_0], rbx
0x1800150dc  lea     rax, ??_7TelemetryLogger@@6B@; const TelemetryLogger::`vftable'
0x1800150e3  lea     rbx, qword_1800866A8
0x1800150ea  mov     cs:qword_1800866B0, rdi
0x1800150f1  mov     [rsp+48h+Context], rbx
0x1800150f6  mov     cs:byte_1800866B8, dil
0x1800150fd  mov     cs:dword_1800866BC, edi
0x180015103  mov     cs:qword_1800866A8, rax
0x18001510a  lea     rax, ?__hInner@?1???0StaticHandle@TelemetryLogger@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `TelemetryLogger::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x180015111  mov     cs:qword_1800866E8, rdi
0x180015118  xorps   xmm0, xmm0
0x18001511b  mov     cs:qword_1800866C0, rax
0x180015122  xorps   xmm1, xmm1
0x180015125  mov     cs:dword_1800866F0, 5
0x18001512f  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1_@?1??Instance@TelemetryLogger@@KAPEAV3@XZ@SA@XZ; void (__cdecl *)()
0x180015136  mov     cs:dword_1800866F4, 258h
0x180015140  movdqu  cs:xmmword_1800866C8, xmm0
0x180015148  movdqu  cs:xmmword_1800866D8, xmm1
0x180015150  call    atexit
0x180015155  mov     rdx, cs:qword_1800866C0; struct _tlgProvider_t *
0x18001515c  mov     rcx, rbx; this
0x18001515f  call    ?Register@TraceLoggingProvider@wil@@IEAAXQEBU_tlgProvider_t@@P6AXPEBU_GUID@@KE_K2PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z@Z; wil::TraceLoggingProvider::Register(_tlgProvider_t const * const,void (*)(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *))
0x180015164  mov     r8, rbx; lpContext
0x180015167  lea     rcx, ?wrapper@?1??Instance@TelemetryLogger@@KAPEAV2@XZ@4V?$static_lazy@VTelemetryLogger@@@details@wil@@A; lpInitOnce
0x18001516e  xor     edx, edx; dwFlags
0x180015170  call    cs:__imp_InitOnceComplete
0x180015176  mov     rbx, [rsp+48h+arg_0]
0x18001517b  mov     rax, [rsp+48h+Context]
0x180015180  mov     rcx, [rsp+48h+var_18]
0x180015185  xor     rcx, rsp; StackCookie
0x180015188  call    __security_check_cookie
0x18001518d  add     rsp, 40h
0x180015191  pop     rdi
0x180015192  retn
```
