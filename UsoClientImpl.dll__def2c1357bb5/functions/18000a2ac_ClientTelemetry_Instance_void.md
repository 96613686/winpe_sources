# ClientTelemetry::Instance(void)

- ea: `0x18000a2ac`
- end: `0x18000a37f`
- name: `?Instance@ClientTelemetry@@KAPEAV1@XZ`
- size: `211`
- prototype: `struct ClientTelemetry *(void)`
- caller_count: `9`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000a270`
- `0x18000a410`
- `0x18000a844`
- `0x18000aa8c`
- `0x18000af08`
- `0x18000b494`
- `0x18000e654`
- `0x180018e90`
- `0x1800194f8`

## callees

- `0x18000a2ac`
- `0x180035c58`
- `0x180056500`
- `0x1800569e8`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000a361`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000a361`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18000a2e5`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18000a2e5`

## pseudocode

```c
struct ClientTelemetry *ClientTelemetry::Instance(void)
{
  void (*v0)(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, void *); // r8
  LPVOID Context; // [rsp+20h] [rbp-28h] BYREF
  BOOL fPending; // [rsp+28h] [rbp-20h] BYREF

  Context = 0;
  fPending = 0;
  if ( __std_init_once_begin_initialize(&`ClientTelemetry::Instance'::`2'::wrapper, 0, &fPending, &Context) && fPending )
  {
    qword_18009F8B8 = 0;
    Context = &qword_18009F8B0;
    qword_18009F8B0 = &Windows::Telemetry::Base::`vftable';
    byte_18009F8C0 = 0;
    dword_18009F8C4 = 0;
    qword_18009F8C8 = (struct _tlgProvider_t *)&`ClientTelemetry::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(`ClientTelemetry::Instance'::`2'::_lambda_1_::_lambda_invoker_cdecl_);
    wil::TraceLoggingProvider::Register((wil::TraceLoggingProvider *)&qword_18009F8B0, qword_18009F8C8, v0);
    InitOnceComplete(&`ClientTelemetry::Instance'::`2'::wrapper, 0, &qword_18009F8B0);
  }
  return (struct ClientTelemetry *)Context;
}

```

## disassembly

```asm
0x18000a2ac  push    rbx
0x18000a2ae  sub     rsp, 40h
0x18000a2b2  mov     rax, cs:__security_cookie
0x18000a2b9  xor     rax, rsp
0x18000a2bc  mov     [rsp+48h+var_18], rax
0x18000a2c1  lea     r9, [rsp+48h+Context]; lpContext
0x18000a2c6  mov     [rsp+48h+Context], 0
0x18000a2cf  lea     r8, [rsp+48h+fPending]; fPending
0x18000a2d4  mov     [rsp+48h+fPending], 0
0x18000a2dc  xor     edx, edx; dwFlags
0x18000a2de  lea     rcx, ?wrapper@?1??Instance@ClientTelemetry@@KAPEAV2@XZ@4V?$static_lazy@VClientTelemetry@@@details@wil@@A; lpInitOnce
0x18000a2e5  call    cs:__imp___std_init_once_begin_initialize
0x18000a2eb  test    eax, eax
0x18000a2ed  jz      short loc_18000A367
0x18000a2ef  cmp     [rsp+48h+fPending], 0
0x18000a2f4  jz      short loc_18000A367
0x18000a2f6  lea     rbx, qword_18009F8B0
0x18000a2fd  mov     cs:qword_18009F8B8, 0
0x18000a308  lea     rax, ??_7Base@Telemetry@Windows@@6B@; const Windows::Telemetry::Base::`vftable'
0x18000a30f  mov     [rsp+48h+Context], rbx
0x18000a314  mov     cs:qword_18009F8B0, rax
0x18000a31b  mov     cs:byte_18009F8C0, 0
0x18000a322  mov     cs:dword_18009F8C4, 0
0x18000a32c  lea     rax, ?__hInner@?1???0StaticHandle@ClientTelemetry@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `ClientTelemetry::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x18000a333  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1_@?1??Instance@ClientTelemetry@@KAPEAV3@XZ@SA@XZ; void (__cdecl *)()
0x18000a33a  mov     cs:qword_18009F8C8, rax
0x18000a341  call    atexit
0x18000a346  mov     rdx, cs:qword_18009F8C8; struct _tlgProvider_t *
0x18000a34d  mov     rcx, rbx; this
0x18000a350  call    ?Register@TraceLoggingProvider@wil@@IEAAXQEBU_tlgProvider_t@@P6AXPEBU_GUID@@KE_K2PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z@Z; wil::TraceLoggingProvider::Register(_tlgProvider_t const * const,void (*)(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *))
0x18000a355  mov     r8, rbx; lpContext
0x18000a358  lea     rcx, ?wrapper@?1??Instance@ClientTelemetry@@KAPEAV2@XZ@4V?$static_lazy@VClientTelemetry@@@details@wil@@A; lpInitOnce
0x18000a35f  xor     edx, edx; dwFlags
0x18000a361  call    cs:__imp_InitOnceComplete
0x18000a367  mov     rax, [rsp+48h+Context]
0x18000a36c  mov     rcx, [rsp+48h+var_18]
0x18000a371  xor     rcx, rsp; StackCookie
0x18000a374  call    __security_check_cookie
0x18000a379  add     rsp, 40h
0x18000a37d  pop     rbx
0x18000a37e  retn
```
