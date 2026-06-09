# ClientCoreTelemetry::Provider(void)

- ea: `0x18000b514`
- end: `0x18000b5eb`
- name: `?Provider@ClientCoreTelemetry@@SAPEBU_tlgProvider_t@@XZ`
- size: `215`
- prototype: `const struct _tlgProvider_t *(void)`
- caller_count: `5`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000b678`
- `0x18000b828`
- `0x18000b898`
- `0x18000ba08`
- `0x18000bbd0`

## callees

- `0x18000b514`
- `0x180035c58`
- `0x180056500`
- `0x1800569e8`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000b5c9`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000b5c9`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18000b54d`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18000b54d`

## pseudocode

```c
const struct _tlgProvider_t *ClientCoreTelemetry::Provider(void)
{
  void (*v0)(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, void *); // r8
  LPVOID Context; // [rsp+20h] [rbp-28h] BYREF
  BOOL fPending; // [rsp+28h] [rbp-20h] BYREF

  Context = 0;
  fPending = 0;
  if ( __std_init_once_begin_initialize(&`ClientCoreTelemetry::Instance'::`2'::wrapper, 0, &fPending, &Context)
    && fPending )
  {
    qword_18009F890 = 0;
    Context = &qword_18009F888;
    qword_18009F888 = &Windows::Telemetry::Base::`vftable';
    byte_18009F898 = 0;
    dword_18009F89C = 0;
    qword_18009F8A0 = (struct _tlgProvider_t *)&`ClientCoreTelemetry::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(`ClientCoreTelemetry::Instance'::`2'::_lambda_1_::_lambda_invoker_cdecl_);
    wil::TraceLoggingProvider::Register((wil::TraceLoggingProvider *)&qword_18009F888, qword_18009F8A0, v0);
    InitOnceComplete(&`ClientCoreTelemetry::Instance'::`2'::wrapper, 0, &qword_18009F888);
  }
  return (const struct _tlgProvider_t *)*((_QWORD *)Context + 1);
}

```

## disassembly

```asm
0x18000b514  push    rbx
0x18000b516  sub     rsp, 40h
0x18000b51a  mov     rax, cs:__security_cookie
0x18000b521  xor     rax, rsp
0x18000b524  mov     [rsp+48h+var_18], rax
0x18000b529  lea     r9, [rsp+48h+Context]; lpContext
0x18000b52e  mov     [rsp+48h+Context], 0
0x18000b537  lea     r8, [rsp+48h+fPending]; fPending
0x18000b53c  mov     [rsp+48h+fPending], 0
0x18000b544  xor     edx, edx; dwFlags
0x18000b546  lea     rcx, ?wrapper@?1??Instance@ClientCoreTelemetry@@KAPEAV2@XZ@4V?$static_lazy@VClientCoreTelemetry@@@details@wil@@A; lpInitOnce
0x18000b54d  call    cs:__imp___std_init_once_begin_initialize
0x18000b553  test    eax, eax
0x18000b555  jz      short loc_18000B5CF
0x18000b557  cmp     [rsp+48h+fPending], 0
0x18000b55c  jz      short loc_18000B5CF
0x18000b55e  lea     rbx, qword_18009F888
0x18000b565  mov     cs:qword_18009F890, 0
0x18000b570  lea     rax, ??_7Base@Telemetry@Windows@@6B@; const Windows::Telemetry::Base::`vftable'
0x18000b577  mov     [rsp+48h+Context], rbx
0x18000b57c  mov     cs:qword_18009F888, rax
0x18000b583  mov     cs:byte_18009F898, 0
0x18000b58a  mov     cs:dword_18009F89C, 0
0x18000b594  lea     rax, ?__hInner@?1???0StaticHandle@ClientCoreTelemetry@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `ClientCoreTelemetry::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x18000b59b  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1_@?1??Instance@ClientCoreTelemetry@@KAPEAV3@XZ@SA@XZ; void (__cdecl *)()
0x18000b5a2  mov     cs:qword_18009F8A0, rax
0x18000b5a9  call    atexit
0x18000b5ae  mov     rdx, cs:qword_18009F8A0; struct _tlgProvider_t *
0x18000b5b5  mov     rcx, rbx; this
0x18000b5b8  call    ?Register@TraceLoggingProvider@wil@@IEAAXQEBU_tlgProvider_t@@P6AXPEBU_GUID@@KE_K2PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z@Z; wil::TraceLoggingProvider::Register(_tlgProvider_t const * const,void (*)(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *))
0x18000b5bd  mov     r8, rbx; lpContext
0x18000b5c0  lea     rcx, ?wrapper@?1??Instance@ClientCoreTelemetry@@KAPEAV2@XZ@4V?$static_lazy@VClientCoreTelemetry@@@details@wil@@A; lpInitOnce
0x18000b5c7  xor     edx, edx; dwFlags
0x18000b5c9  call    cs:__imp_InitOnceComplete
0x18000b5cf  mov     rax, [rsp+48h+Context]
0x18000b5d4  mov     rax, [rax+8]
0x18000b5d8  mov     rcx, [rsp+48h+var_18]
0x18000b5dd  xor     rcx, rsp; StackCookie
0x18000b5e0  call    __security_check_cookie
0x18000b5e5  add     rsp, 40h
0x18000b5e9  pop     rbx
0x18000b5ea  retn
```
