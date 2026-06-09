# TraceLog::Providers::Reliability::Provider(void)

- ea: `0x180036d18`
- end: `0x180036e01`
- name: `?Provider@Reliability@Providers@TraceLog@@SAPEBU_tlgProvider_t@@XZ`
- size: `233`
- prototype: `const struct _tlgProvider_t *(void)`
- caller_count: `6`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180036664`
- `0x1800369d0`
- `0x180036e08`
- `0x180037188`
- `0x180037310`
- `0x180037450`

## callees

- `0x180001748`
- `0x1800064d8`
- `0x180036d18`
- `0x1800ae010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180036dec`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180036dec`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180036d40`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180036d40`

## pseudocode

```c
const struct _tlgProvider_t *TraceLog::Providers::Reliability::Provider(void)
{
  WINBOOL v1; // [rsp+30h] [rbp+8h] BYREF
  __int64 *v2; // [rsp+38h] [rbp+10h] BYREF

  v2 = 0;
  v1 = 0;
  if ( __std_init_once_begin_initialize(
         &`TraceLog::Providers::Reliability::Instance'::`2'::wrapper,
         0,
         &v1,
         (LPVOID *)&v2)
    && v1 )
  {
    qword_180109318 = 0;
    v2 = &qword_180109310;
    qword_180109310 = (__int64)&TraceLog::Providers::Reliability::`vftable';
    byte_180109320 = 0;
    dword_180109324 = 0;
    qword_180109328 = &`TraceLog::Providers::Reliability::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(_lambda_b3ba549a0478ed578a07f87a224ac94f_::_lambda_invoker_cdecl_);
    qword_180109318 = (__int64)qword_180109328;
    byte_180109320 = 1;
    TraceLoggingRegisterEx_EventRegister_EventSetInformation(qword_180109328);
    dword_180109324 = 1;
    (*(void (__fastcall **)(__int64 *))(qword_180109310 + 8))(&qword_180109310);
    InitOnceComplete(&`TraceLog::Providers::Reliability::Instance'::`2'::wrapper, 0, &qword_180109310);
  }
  return (const struct _tlgProvider_t *)v2[1];
}

```

## disassembly

```asm
0x180036d18  mov     rax, rsp
0x180036d1b  push    rbx
0x180036d1c  sub     rsp, 20h
0x180036d20  lea     r9, [rax+10h]; lpContext
0x180036d24  mov     qword ptr [rax+10h], 0
0x180036d2c  lea     r8, [rax+8]; fPending
0x180036d30  mov     dword ptr [rax+8], 0
0x180036d37  xor     edx, edx; dwFlags
0x180036d39  lea     rcx, ?wrapper@?1??Instance@Reliability@Providers@TraceLog@@KAPEAV234@XZ@4V?$static_lazy@VReliability@Providers@TraceLog@@@details@wil@@A; lpInitOnce
0x180036d40  call    cs:__imp___std_init_once_begin_initialize
0x180036d46  test    eax, eax
0x180036d48  jz      loc_180036DF2
0x180036d4e  cmp     [rsp+28h+arg_0], 0
0x180036d53  jz      loc_180036DF2
0x180036d59  lea     rbx, qword_180109310
0x180036d60  mov     cs:qword_180109318, 0
0x180036d6b  lea     rax, ??_7Reliability@Providers@TraceLog@@6B@; const TraceLog::Providers::Reliability::`vftable'
0x180036d72  mov     [rsp+28h+arg_8], rbx
0x180036d77  mov     cs:qword_180109310, rax
0x180036d7e  mov     cs:byte_180109320, 0
0x180036d85  mov     cs:dword_180109324, 0
0x180036d8f  lea     rax, ?__hInner@?1???0StaticHandle@Reliability@Providers@TraceLog@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `TraceLog::Providers::Reliability::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x180036d96  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_b3ba549a0478ed578a07f87a224ac94f_@@CA@XZ; void (__cdecl *)()
0x180036d9d  mov     cs:qword_180109328, rax
0x180036da4  call    atexit
0x180036da9  mov     rcx, cs:qword_180109328; CallbackContext
0x180036db0  mov     cs:qword_180109318, rcx
0x180036db7  mov     cs:byte_180109320, 1
0x180036dbe  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x180036dc3  mov     rax, cs:qword_180109310
0x180036dca  mov     rcx, rbx
0x180036dcd  mov     cs:dword_180109324, 1
0x180036dd7  mov     rax, [rax+8]
0x180036ddb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036de0  mov     r8, rbx; lpContext
0x180036de3  lea     rcx, ?wrapper@?1??Instance@Reliability@Providers@TraceLog@@KAPEAV234@XZ@4V?$static_lazy@VReliability@Providers@TraceLog@@@details@wil@@A; lpInitOnce
0x180036dea  xor     edx, edx; dwFlags
0x180036dec  call    cs:__imp_InitOnceComplete
0x180036df2  mov     rax, [rsp+28h+arg_8]
0x180036df7  mov     rax, [rax+8]
0x180036dfb  add     rsp, 20h
0x180036dff  pop     rbx
0x180036e00  retn
```
