# uus::UUSTracing::Instance(void)

- ea: `0x18003c6b8`
- end: `0x18003c78b`
- name: `?Instance@UUSTracing@uus@@KAPEAV12@XZ`
- size: `211`
- prototype: `struct uus::UUSTracing *(void)`
- caller_count: `3`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18003c114`
- `0x18003c480`
- `0x18003c794`

## callees

- `0x180008520`
- `0x18003c6b8`
- `0x1800427d0`
- `0x180042ba4`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18003c76d`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18003c76d`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18003c6f1`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18003c6f1`

## pseudocode

```c
struct uus::UUSTracing *uus::UUSTracing::Instance(void)
{
  void (*v0)(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, void *); // r8
  LPVOID Context; // [rsp+20h] [rbp-28h] BYREF
  WINBOOL fPending; // [rsp+28h] [rbp-20h] BYREF

  Context = 0;
  fPending = 0;
  if ( __std_init_once_begin_initialize(&`uus::UUSTracing::Instance'::`2'::wrapper, 0, &fPending, &Context) && fPending )
  {
    qword_1800635D8 = 0;
    Context = &qword_1800635D0;
    qword_1800635D0 = &uus::UUSTracing::`vftable';
    byte_1800635E0 = 0;
    dword_1800635E4 = 0;
    qword_1800635E8 = (struct _tlgProvider_t *)&`uus::UUSTracing::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(_lambda_9d7d50b15fa394df4407dd6844a6c30a_::_lambda_invoker_cdecl_);
    wil::TraceLoggingProvider::Register((wil::TraceLoggingProvider *)&qword_1800635D0, qword_1800635E8, v0);
    InitOnceComplete(&`uus::UUSTracing::Instance'::`2'::wrapper, 0, &qword_1800635D0);
  }
  return (struct uus::UUSTracing *)Context;
}

```

## disassembly

```asm
0x18003c6b8  push    rbx
0x18003c6ba  sub     rsp, 40h
0x18003c6be  mov     rax, cs:__security_cookie
0x18003c6c5  xor     rax, rsp
0x18003c6c8  mov     [rsp+48h+var_18], rax
0x18003c6cd  lea     r9, [rsp+48h+Context]; lpContext
0x18003c6d2  mov     [rsp+48h+Context], 0
0x18003c6db  lea     r8, [rsp+48h+fPending]; fPending
0x18003c6e0  mov     [rsp+48h+fPending], 0
0x18003c6e8  xor     edx, edx; dwFlags
0x18003c6ea  lea     rcx, ?wrapper@?1??Instance@UUSTracing@uus@@KAPEAV23@XZ@4V?$static_lazy@VUUSTracing@uus@@@details@wil@@A; lpInitOnce
0x18003c6f1  call    cs:__imp___std_init_once_begin_initialize
0x18003c6f7  test    eax, eax
0x18003c6f9  jz      short loc_18003C773
0x18003c6fb  cmp     [rsp+48h+fPending], 0
0x18003c700  jz      short loc_18003C773
0x18003c702  lea     rbx, qword_1800635D0
0x18003c709  mov     cs:qword_1800635D8, 0
0x18003c714  lea     rax, ??_7UUSTracing@uus@@6B@; const uus::UUSTracing::`vftable'
0x18003c71b  mov     [rsp+48h+Context], rbx
0x18003c720  mov     cs:qword_1800635D0, rax
0x18003c727  mov     cs:byte_1800635E0, 0
0x18003c72e  mov     cs:dword_1800635E4, 0
0x18003c738  lea     rax, ?__hInner@?1???0StaticHandle@UUSTracing@uus@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `uus::UUSTracing::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x18003c73f  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_9d7d50b15fa394df4407dd6844a6c30a_@@CA@XZ; void (__cdecl *)()
0x18003c746  mov     cs:qword_1800635E8, rax
0x18003c74d  call    atexit
0x18003c752  mov     rdx, cs:qword_1800635E8; struct _tlgProvider_t *
0x18003c759  mov     rcx, rbx; this
0x18003c75c  call    ?Register@TraceLoggingProvider@wil@@IEAAXQEBU_tlgProvider_t@@P6AXPEBU_GUID@@KE_K2PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z@Z; wil::TraceLoggingProvider::Register(_tlgProvider_t const * const,void (*)(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *))
0x18003c761  mov     r8, rbx; lpContext
0x18003c764  lea     rcx, ?wrapper@?1??Instance@UUSTracing@uus@@KAPEAV23@XZ@4V?$static_lazy@VUUSTracing@uus@@@details@wil@@A; lpInitOnce
0x18003c76b  xor     edx, edx; dwFlags
0x18003c76d  call    cs:__imp_InitOnceComplete
0x18003c773  mov     rax, [rsp+48h+Context]
0x18003c778  mov     rcx, [rsp+48h+var_18]
0x18003c77d  xor     rcx, rsp; StackCookie
0x18003c780  call    __security_check_cookie
0x18003c785  add     rsp, 40h
0x18003c789  pop     rbx
0x18003c78a  retn
```
