# TraceLogger::Provider(void)

- ea: `0x1800119b0`
- end: `0x180011a8a`
- name: `?Provider@TraceLogger@@SAPEBU_tlgProvider_t@@XZ`
- size: `218`
- prototype: `const struct _tlgProvider_t *(void)`
- caller_count: `20`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180008a50`
- `0x18000a0f0`
- `0x18001cc10`
- `0x18001d320`
- `0x18001d8e0`
- `0x180021b10`
- `0x180022260`
- `0x1800229c0`
- `0x180022dd0`
- `0x180023860`
- `0x180023c50`
- `0x180024120`
- `0x180024580`
- `0x180024d50`
- `0x180024e40`
- `0x180024f30`
- `0x180025020`
- `0x180025170`
- `0x180026050`
- `0x18003aec0`

## callees

- `0x1800114a0`
- `0x1800119b0`
- `0x180034ef0`
- `0x1800353fc`

## import_xrefs

- `KERNEL32!InitOnceBeginInitialize` at `0x1800119df`
- `KERNEL32!InitOnceBeginInitialize` at `0x1800119df`
- `KERNEL32!InitOnceComplete` at `0x180011a64`
- `KERNEL32!InitOnceComplete` at `0x180011a64`

## pseudocode

```c
const struct _tlgProvider_t *TraceLogger::Provider(void)
{
  void (*v0)(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, void *); // r8
  LPVOID Context; // [rsp+20h] [rbp-28h] BYREF
  BOOL fPending; // [rsp+28h] [rbp-20h] BYREF

  Context = 0;
  if ( InitOnceBeginInitialize(&`TraceLogger::Instance'::`2'::wrapper, 0, &fPending, &Context) && fPending )
  {
    qword_180059E20 = 0;
    Context = &qword_180059E18;
    byte_180059E28 = 0;
    dword_180059E2C = 0;
    qword_180059E18 = &TraceLogger::`vftable';
    qword_180059E30 = (struct _tlgProvider_t *)&`TraceLogger::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(_lambda_77df2b2445264ffccec9000ef713eb53_::_lambda_invoker_cdecl_);
    wil::TraceLoggingProvider::Register((wil::TraceLoggingProvider *)&qword_180059E18, qword_180059E30, v0);
    InitOnceComplete(&`TraceLogger::Instance'::`2'::wrapper, 0, &qword_180059E18);
  }
  return (const struct _tlgProvider_t *)*((_QWORD *)Context + 1);
}

```

## disassembly

```asm
0x1800119b0  sub     rsp, 48h
0x1800119b4  mov     rax, cs:__security_cookie
0x1800119bb  xor     rax, rsp
0x1800119be  mov     [rsp+48h+var_18], rax
0x1800119c3  lea     r9, [rsp+48h+Context]; lpContext
0x1800119c8  mov     [rsp+48h+Context], 0
0x1800119d1  lea     r8, [rsp+48h+fPending]; fPending
0x1800119d6  xor     edx, edx; dwFlags
0x1800119d8  lea     rcx, ?wrapper@?1??Instance@TraceLogger@@KAPEAV2@XZ@4V?$static_lazy@VTraceLogger@@@details@wil@@A; lpInitOnce
0x1800119df  call    cs:__imp_InitOnceBeginInitialize
0x1800119e5  test    eax, eax
0x1800119e7  jz      loc_180011A6F
0x1800119ed  cmp     [rsp+48h+fPending], 0
0x1800119f2  jz      short loc_180011A6F
0x1800119f4  mov     [rsp+48h+var_8], rbx
0x1800119f9  lea     rax, ??_7TraceLogger@@6B@; const TraceLogger::`vftable'
0x180011a00  lea     rbx, qword_180059E18
0x180011a07  mov     cs:qword_180059E20, 0
0x180011a12  mov     [rsp+48h+Context], rbx
0x180011a17  mov     cs:byte_180059E28, 0
0x180011a1e  mov     cs:dword_180059E2C, 0
0x180011a28  mov     cs:qword_180059E18, rax
0x180011a2f  lea     rax, ?__hInner@?1???0StaticHandle@TraceLogger@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `TraceLogger::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x180011a36  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_77df2b2445264ffccec9000ef713eb53_@@CA@XZ; void (__cdecl *)()
0x180011a3d  mov     cs:qword_180059E30, rax
0x180011a44  call    atexit
0x180011a49  mov     rdx, cs:qword_180059E30; struct _tlgProvider_t *
0x180011a50  mov     rcx, rbx; this
0x180011a53  call    ?Register@TraceLoggingProvider@wil@@IEAAXQEBU_tlgProvider_t@@P6AXPEBU_GUID@@KE_K2PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z@Z; wil::TraceLoggingProvider::Register(_tlgProvider_t const * const,void (*)(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *))
0x180011a58  mov     r8, rbx; lpContext
0x180011a5b  lea     rcx, ?wrapper@?1??Instance@TraceLogger@@KAPEAV2@XZ@4V?$static_lazy@VTraceLogger@@@details@wil@@A; lpInitOnce
0x180011a62  xor     edx, edx; dwFlags
0x180011a64  call    cs:__imp_InitOnceComplete
0x180011a6a  mov     rbx, [rsp+48h+var_8]
0x180011a6f  mov     rax, [rsp+48h+Context]
0x180011a74  mov     rax, [rax+8]
0x180011a78  mov     rcx, [rsp+48h+var_18]
0x180011a7d  xor     rcx, rsp; StackCookie
0x180011a80  call    __security_check_cookie
0x180011a85  add     rsp, 48h
0x180011a89  retn
```
