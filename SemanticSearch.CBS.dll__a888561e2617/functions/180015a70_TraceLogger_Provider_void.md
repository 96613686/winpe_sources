# TraceLogger::Provider(void)

- ea: `0x180015a70`
- end: `0x180015b4a`
- name: `?Provider@TraceLogger@@SAPEBU_tlgProvider_t@@XZ`
- size: `218`
- prototype: `const struct _tlgProvider_t *(void)`
- caller_count: `45`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180009bb0`
- `0x180009e70`
- `0x18000a710`
- `0x18000afa0`
- `0x18000b2a0`
- `0x180017600`
- `0x180017760`
- `0x180017960`
- `0x180018550`
- `0x180019470`
- `0x18001bcf0`
- `0x18001bfc0`
- `0x18001c120`
- `0x18001c320`
- `0x18001cc80`
- `0x18001d410`
- `0x180033f70`
- `0x180034400`
- `0x180034b20`
- `0x180034c70`
- `0x180034e70`
- `0x180034f70`
- `0x180035fa0`
- `0x18003f9f0`
- `0x18003fb50`
- `0x18003fd50`
- `0x1800406a0`
- `0x180040a80`
- `0x180052c90`
- `0x180053610`
- `0x1800583b0`
- `0x18005bc90`
- `0x180060020`
- `0x18006019c`
- `0x180060320`
- `0x180060760`
- `0x1800608dc`
- `0x180060a50`
- `0x180060bdc`
- `0x180060f6c`
- `0x180062600`
- `0x180062770`
- `0x1800628ec`
- `0x180062ef0`
- `0x180063060`

## callees

- `0x180015560`
- `0x180015a70`
- `0x18004c070`
- `0x18004c8ac`

## import_xrefs

- `KERNEL32!InitOnceBeginInitialize` at `0x180015a9f`
- `KERNEL32!InitOnceBeginInitialize` at `0x180015a9f`
- `KERNEL32!InitOnceComplete` at `0x180015b24`
- `KERNEL32!InitOnceComplete` at `0x180015b24`

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
    qword_180086710 = 0;
    Context = &qword_180086708;
    byte_180086718 = 0;
    dword_18008671C = 0;
    qword_180086708 = &TraceLogger::`vftable';
    qword_180086720 = (struct _tlgProvider_t *)&`TraceLogger::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(`TraceLogger::Instance'::`2'::_lambda_1_::_lambda_invoker_cdecl_);
    wil::TraceLoggingProvider::Register((wil::TraceLoggingProvider *)&qword_180086708, qword_180086720, v0);
    InitOnceComplete(&`TraceLogger::Instance'::`2'::wrapper, 0, &qword_180086708);
  }
  return (const struct _tlgProvider_t *)*((_QWORD *)Context + 1);
}

```

## disassembly

```asm
0x180015a70  sub     rsp, 48h
0x180015a74  mov     rax, cs:__security_cookie
0x180015a7b  xor     rax, rsp
0x180015a7e  mov     [rsp+48h+var_18], rax
0x180015a83  lea     r9, [rsp+48h+Context]; lpContext
0x180015a88  mov     [rsp+48h+Context], 0
0x180015a91  lea     r8, [rsp+48h+fPending]; fPending
0x180015a96  xor     edx, edx; dwFlags
0x180015a98  lea     rcx, ?wrapper@?1??Instance@TraceLogger@@KAPEAV2@XZ@4V?$static_lazy@VTraceLogger@@@details@wil@@A; lpInitOnce
0x180015a9f  call    cs:__imp_InitOnceBeginInitialize
0x180015aa5  test    eax, eax
0x180015aa7  jz      loc_180015B2F
0x180015aad  cmp     [rsp+48h+fPending], 0
0x180015ab2  jz      short loc_180015B2F
0x180015ab4  mov     [rsp+48h+var_8], rbx
0x180015ab9  lea     rax, ??_7TraceLogger@@6B@; const TraceLogger::`vftable'
0x180015ac0  lea     rbx, qword_180086708
0x180015ac7  mov     cs:qword_180086710, 0
0x180015ad2  mov     [rsp+48h+Context], rbx
0x180015ad7  mov     cs:byte_180086718, 0
0x180015ade  mov     cs:dword_18008671C, 0
0x180015ae8  mov     cs:qword_180086708, rax
0x180015aef  lea     rax, ?__hInner@?1???0StaticHandle@TraceLogger@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `TraceLogger::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x180015af6  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1_@?1??Instance@TraceLogger@@KAPEAV3@XZ@SA@XZ; void (__cdecl *)()
0x180015afd  mov     cs:qword_180086720, rax
0x180015b04  call    atexit
0x180015b09  mov     rdx, cs:qword_180086720; struct _tlgProvider_t *
0x180015b10  mov     rcx, rbx; this
0x180015b13  call    ?Register@TraceLoggingProvider@wil@@IEAAXQEBU_tlgProvider_t@@P6AXPEBU_GUID@@KE_K2PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z@Z; wil::TraceLoggingProvider::Register(_tlgProvider_t const * const,void (*)(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *))
0x180015b18  mov     r8, rbx; lpContext
0x180015b1b  lea     rcx, ?wrapper@?1??Instance@TraceLogger@@KAPEAV2@XZ@4V?$static_lazy@VTraceLogger@@@details@wil@@A; lpInitOnce
0x180015b22  xor     edx, edx; dwFlags
0x180015b24  call    cs:__imp_InitOnceComplete
0x180015b2a  mov     rbx, [rsp+48h+var_8]
0x180015b2f  mov     rax, [rsp+48h+Context]
0x180015b34  mov     rax, [rax+8]
0x180015b38  mov     rcx, [rsp+48h+var_18]
0x180015b3d  xor     rcx, rsp; StackCookie
0x180015b40  call    __security_check_cookie
0x180015b45  add     rsp, 48h
0x180015b49  retn
```
