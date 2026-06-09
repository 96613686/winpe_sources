# Windows::Telemetry::Base::Provider(void)

- ea: `0x18003e044`
- end: `0x18003e11b`
- name: `?Provider@Base@Telemetry@Windows@@SAPEBU_tlgProvider_t@@XZ`
- size: `215`
- prototype: `const struct _tlgProvider_t *(void)`
- caller_count: `7`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18003e220`
- `0x18003e2a0`
- `0x18003e568`
- `0x18003e700`
- `0x18003ea9c`
- `0x1800430e8`
- `0x180043170`

## callees

- `0x180035c58`
- `0x18003e044`
- `0x180056500`
- `0x1800569e8`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18003e0f9`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18003e0f9`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18003e07d`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18003e07d`

## pseudocode

```c
const struct _tlgProvider_t *Windows::Telemetry::Base::Provider(void)
{
  void (*v0)(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, void *); // r8
  LPVOID Context; // [rsp+20h] [rbp-28h] BYREF
  BOOL fPending; // [rsp+28h] [rbp-20h] BYREF

  Context = 0;
  fPending = 0;
  if ( __std_init_once_begin_initialize(&`Windows::Telemetry::Base::Instance'::`2'::wrapper, 0, &fPending, &Context)
    && fPending )
  {
    qword_18009FB40 = 0;
    Context = &qword_18009FB38;
    qword_18009FB38 = &Windows::Telemetry::Base::`vftable';
    byte_18009FB48 = 0;
    dword_18009FB4C = 0;
    qword_18009FB50 = (struct _tlgProvider_t *)&`Windows::Telemetry::Base::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(`Windows::Telemetry::Base::Instance'::`2'::_lambda_1_::_lambda_invoker_cdecl_);
    wil::TraceLoggingProvider::Register((wil::TraceLoggingProvider *)&qword_18009FB38, qword_18009FB50, v0);
    InitOnceComplete(&`Windows::Telemetry::Base::Instance'::`2'::wrapper, 0, &qword_18009FB38);
  }
  return (const struct _tlgProvider_t *)*((_QWORD *)Context + 1);
}

```

## disassembly

```asm
0x18003e044  push    rbx
0x18003e046  sub     rsp, 40h
0x18003e04a  mov     rax, cs:__security_cookie
0x18003e051  xor     rax, rsp
0x18003e054  mov     [rsp+48h+var_18], rax
0x18003e059  lea     r9, [rsp+48h+Context]; lpContext
0x18003e05e  mov     [rsp+48h+Context], 0
0x18003e067  lea     r8, [rsp+48h+fPending]; fPending
0x18003e06c  mov     [rsp+48h+fPending], 0
0x18003e074  xor     edx, edx; dwFlags
0x18003e076  lea     rcx, ?wrapper@?1??Instance@Base@Telemetry@Windows@@KAPEAV234@XZ@4V?$static_lazy@VBase@Telemetry@Windows@@@details@wil@@A; lpInitOnce
0x18003e07d  call    cs:__imp___std_init_once_begin_initialize
0x18003e083  test    eax, eax
0x18003e085  jz      short loc_18003E0FF
0x18003e087  cmp     [rsp+48h+fPending], 0
0x18003e08c  jz      short loc_18003E0FF
0x18003e08e  lea     rbx, qword_18009FB38
0x18003e095  mov     cs:qword_18009FB40, 0
0x18003e0a0  lea     rax, ??_7Base@Telemetry@Windows@@6B@; const Windows::Telemetry::Base::`vftable'
0x18003e0a7  mov     [rsp+48h+Context], rbx
0x18003e0ac  mov     cs:qword_18009FB38, rax
0x18003e0b3  mov     cs:byte_18009FB48, 0
0x18003e0ba  mov     cs:dword_18009FB4C, 0
0x18003e0c4  lea     rax, ?__hInner@?1???0StaticHandle@Base@Telemetry@Windows@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `Windows::Telemetry::Base::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x18003e0cb  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1_@?1??Instance@Base@Telemetry@Windows@@KAPEAV345@XZ@SA@XZ; void (__cdecl *)()
0x18003e0d2  mov     cs:qword_18009FB50, rax
0x18003e0d9  call    atexit
0x18003e0de  mov     rdx, cs:qword_18009FB50; struct _tlgProvider_t *
0x18003e0e5  mov     rcx, rbx; this
0x18003e0e8  call    ?Register@TraceLoggingProvider@wil@@IEAAXQEBU_tlgProvider_t@@P6AXPEBU_GUID@@KE_K2PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z@Z; wil::TraceLoggingProvider::Register(_tlgProvider_t const * const,void (*)(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *))
0x18003e0ed  mov     r8, rbx; lpContext
0x18003e0f0  lea     rcx, ?wrapper@?1??Instance@Base@Telemetry@Windows@@KAPEAV234@XZ@4V?$static_lazy@VBase@Telemetry@Windows@@@details@wil@@A; lpInitOnce
0x18003e0f7  xor     edx, edx; dwFlags
0x18003e0f9  call    cs:__imp_InitOnceComplete
0x18003e0ff  mov     rax, [rsp+48h+Context]
0x18003e104  mov     rax, [rax+8]
0x18003e108  mov     rcx, [rsp+48h+var_18]
0x18003e10d  xor     rcx, rsp; StackCookie
0x18003e110  call    __security_check_cookie
0x18003e115  add     rsp, 40h
0x18003e119  pop     rbx
0x18003e11a  retn
```
