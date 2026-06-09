# Windows::Telemetry::ServiceBase::Instance(void)

- ea: `0x1800857a8`
- end: `0x18008587b`
- name: `?Instance@ServiceBase@Telemetry@Windows@@KAPEAV123@XZ`
- size: `211`
- prototype: `struct Windows::Telemetry::ServiceBase *(void)`
- caller_count: `31`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x180085910`
- `0x180085c44`
- `0x180085e5c`
- `0x180085f5c`
- `0x180086260`
- `0x1800862e8`
- `0x1800865f0`
- `0x180087590`
- `0x180087618`
- `0x180087760`
- `0x1800877e8`
- `0x1800878bc`
- `0x1800879b4`
- `0x180087a6c`
- `0x180087bb0`
- `0x180087cb0`
- `0x180087d38`
- `0x180087de0`
- `0x180087e68`
- `0x180087f10`
- `0x180087fb8`
- `0x180088060`
- `0x18008832c`
- `0x180088740`
- `0x1800889d0`
- `0x180088cec`
- `0x1800896f0`
- `0x18008b700`
- `0x18008b8a0`
- `0x18008bb70`
- `0x18008bee8`

## callees

- `0x180039534`
- `0x1800857a8`
- `0x1800dd930`
- `0x1800dddd4`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1800857e1`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1800857e1`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18008585d`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18008585d`

## pseudocode

```c
struct Windows::Telemetry::ServiceBase *Windows::Telemetry::ServiceBase::Instance(void)
{
  void (*v0)(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, void *); // r8
  LPVOID Context; // [rsp+20h] [rbp-28h] BYREF
  WINBOOL fPending; // [rsp+28h] [rbp-20h] BYREF

  Context = 0;
  fPending = 0;
  if ( __std_init_once_begin_initialize(
         &`Windows::Telemetry::ServiceBase::Instance'::`2'::wrapper,
         0,
         &fPending,
         &Context)
    && fPending )
  {
    qword_1801503E8 = 0;
    Context = &qword_1801503E0;
    qword_1801503E0 = &Windows::Telemetry::ServiceBase::`vftable';
    byte_1801503F0 = 0;
    dword_1801503F4 = 0;
    qword_1801503F8 = (struct _tlgProvider_t *)&`Windows::Telemetry::ServiceBase::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(`Windows::Telemetry::ServiceBase::Instance'::`2'::_lambda_1_::_lambda_invoker_cdecl_);
    wil::TraceLoggingProvider::Register((wil::TraceLoggingProvider *)&qword_1801503E0, qword_1801503F8, v0);
    InitOnceComplete(&`Windows::Telemetry::ServiceBase::Instance'::`2'::wrapper, 0, &qword_1801503E0);
  }
  return (struct Windows::Telemetry::ServiceBase *)Context;
}

```

## disassembly

```asm
0x1800857a8  push    rbx
0x1800857aa  sub     rsp, 40h
0x1800857ae  mov     rax, cs:__security_cookie
0x1800857b5  xor     rax, rsp
0x1800857b8  mov     [rsp+48h+var_18], rax
0x1800857bd  lea     r9, [rsp+48h+Context]; lpContext
0x1800857c2  mov     [rsp+48h+Context], 0
0x1800857cb  lea     r8, [rsp+48h+fPending]; fPending
0x1800857d0  mov     [rsp+48h+fPending], 0
0x1800857d8  xor     edx, edx; dwFlags
0x1800857da  lea     rcx, ?wrapper@?1??Instance@ServiceBase@Telemetry@Windows@@KAPEAV234@XZ@4V?$static_lazy@VServiceBase@Telemetry@Windows@@@details@wil@@A; lpInitOnce
0x1800857e1  call    cs:__imp___std_init_once_begin_initialize
0x1800857e7  test    eax, eax
0x1800857e9  jz      short loc_180085863
0x1800857eb  cmp     [rsp+48h+fPending], 0
0x1800857f0  jz      short loc_180085863
0x1800857f2  lea     rbx, qword_1801503E0
0x1800857f9  mov     cs:qword_1801503E8, 0
0x180085804  lea     rax, ??_7ServiceBase@Telemetry@Windows@@6B@; const Windows::Telemetry::ServiceBase::`vftable'
0x18008580b  mov     [rsp+48h+Context], rbx
0x180085810  mov     cs:qword_1801503E0, rax
0x180085817  mov     cs:byte_1801503F0, 0
0x18008581e  mov     cs:dword_1801503F4, 0
0x180085828  lea     rax, ?__hInner@?1???0StaticHandle@ServiceBase@Telemetry@Windows@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `Windows::Telemetry::ServiceBase::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x18008582f  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1_@?1??Instance@ServiceBase@Telemetry@Windows@@KAPEAV345@XZ@SA@XZ; void (__cdecl *)()
0x180085836  mov     cs:qword_1801503F8, rax
0x18008583d  call    atexit
0x180085842  mov     rdx, cs:qword_1801503F8; struct _tlgProvider_t *
0x180085849  mov     rcx, rbx; this
0x18008584c  call    ?Register@TraceLoggingProvider@wil@@IEAAXQEBU_tlgProvider_t@@P6AXPEBU_GUID@@KE_K2PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z@Z; wil::TraceLoggingProvider::Register(_tlgProvider_t const * const,void (*)(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *))
0x180085851  mov     r8, rbx; lpContext
0x180085854  lea     rcx, ?wrapper@?1??Instance@ServiceBase@Telemetry@Windows@@KAPEAV234@XZ@4V?$static_lazy@VServiceBase@Telemetry@Windows@@@details@wil@@A; lpInitOnce
0x18008585b  xor     edx, edx; dwFlags
0x18008585d  call    cs:__imp_InitOnceComplete
0x180085863  mov     rax, [rsp+48h+Context]
0x180085868  mov     rcx, [rsp+48h+var_18]
0x18008586d  xor     rcx, rsp; StackCookie
0x180085870  call    __security_check_cookie
0x180085875  add     rsp, 40h
0x180085879  pop     rbx
0x18008587a  retn
```
