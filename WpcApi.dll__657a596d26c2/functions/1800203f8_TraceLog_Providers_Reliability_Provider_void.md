# TraceLog::Providers::Reliability::Provider(void)

- ea: `0x1800203f8`
- end: `0x1800204b1`
- name: `?Provider@Reliability@Providers@TraceLog@@SAPEBU_tlgProvider_t@@XZ`
- size: `185`
- prototype: `const struct _tlgProvider_t *(void)`
- caller_count: `6`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18001fdc4`
- `0x1800200b0`
- `0x1800204b8`
- `0x180020720`
- `0x1800208d8`
- `0x180020a70`

## callees

- `0x1800036b8`
- `0x180011f18`
- `0x1800203f8`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180020420`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180020420`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18002049c`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18002049c`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
const struct _tlgProvider_t *TraceLog::Providers::Reliability::Provider(void)
{
  void (*v0)(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, void *); // r8
  WINBOOL v2; // [rsp+30h] [rbp+8h] BYREF
  _QWORD *v3; // [rsp+38h] [rbp+10h] BYREF

  v3 = 0;
  v2 = 0;
  if ( InitOnceBeginInitialize(&`TraceLog::Providers::Reliability::Instance'::`2'::wrapper, 0, &v2, (LPVOID *)&v3) && v2 )
  {
    qword_18004ABE8 = 0;
    v3 = &qword_18004ABE0;
    qword_18004ABE0 = &TraceLog::Providers::Reliability::`vftable';
    byte_18004ABF0 = 0;
    dword_18004ABF4 = 0;
    qword_18004ABF8 = (struct _tlgProvider_t *)&`TraceLog::Providers::Reliability::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(_lambda_b3ba549a0478ed578a07f87a224ac94f_::_lambda_invoker_cdecl_);
    wil::TraceLoggingProvider::Register((wil::TraceLoggingProvider *)&qword_18004ABE0, qword_18004ABF8, v0);
    InitOnceComplete(&`TraceLog::Providers::Reliability::Instance'::`2'::wrapper, 0, &qword_18004ABE0);
  }
  return (const struct _tlgProvider_t *)v3[1];
}

```

## disassembly

```asm
0x1800203f8  mov     rax, rsp
0x1800203fb  push    rbx
0x1800203fc  sub     rsp, 20h
0x180020400  lea     r9, [rax+10h]; lpContext
0x180020404  mov     qword ptr [rax+10h], 0
0x18002040c  lea     r8, [rax+8]; fPending
0x180020410  mov     dword ptr [rax+8], 0
0x180020417  xor     edx, edx; dwFlags
0x180020419  lea     rcx, ?wrapper@?1??Instance@Reliability@Providers@TraceLog@@KAPEAV234@XZ@4V?$static_lazy@VReliability@Providers@TraceLog@@@details@wil@@A; lpInitOnce
0x180020420  call    cs:__imp_InitOnceBeginInitialize
0x180020426  test    eax, eax
0x180020428  jz      short loc_1800204A2
0x18002042a  cmp     [rsp+28h+arg_0], 0
0x18002042f  jz      short loc_1800204A2
0x180020431  lea     rbx, qword_18004ABE0
0x180020438  mov     cs:qword_18004ABE8, 0
0x180020443  lea     rax, ??_7Reliability@Providers@TraceLog@@6B@; const TraceLog::Providers::Reliability::`vftable'
0x18002044a  mov     [rsp+28h+arg_8], rbx
0x18002044f  mov     cs:qword_18004ABE0, rax
0x180020456  mov     cs:byte_18004ABF0, 0
0x18002045d  mov     cs:dword_18004ABF4, 0
0x180020467  lea     rax, ?__hInner@?1???0StaticHandle@Reliability@Providers@TraceLog@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `TraceLog::Providers::Reliability::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x18002046e  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_b3ba549a0478ed578a07f87a224ac94f_@@CA@XZ; void (__cdecl *)()
0x180020475  mov     cs:qword_18004ABF8, rax
0x18002047c  call    atexit
0x180020481  mov     rdx, cs:qword_18004ABF8; struct _tlgProvider_t *
0x180020488  mov     rcx, rbx; this
0x18002048b  call    ?Register@TraceLoggingProvider@wil@@IEAAXQEBU_tlgProvider_t@@P6AXPEBU_GUID@@KE_K2PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z@Z; wil::TraceLoggingProvider::Register(_tlgProvider_t const * const,void (*)(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *))
0x180020490  mov     r8, rbx; lpContext
0x180020493  lea     rcx, ?wrapper@?1??Instance@Reliability@Providers@TraceLog@@KAPEAV234@XZ@4V?$static_lazy@VReliability@Providers@TraceLog@@@details@wil@@A; lpInitOnce
0x18002049a  xor     edx, edx; dwFlags
0x18002049c  call    cs:__imp_InitOnceComplete
0x1800204a2  mov     rax, [rsp+28h+arg_8]
0x1800204a7  mov     rax, [rax+8]
0x1800204ab  add     rsp, 20h
0x1800204af  pop     rbx
0x1800204b0  retn
```
