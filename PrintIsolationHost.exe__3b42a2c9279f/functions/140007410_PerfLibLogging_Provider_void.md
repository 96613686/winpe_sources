# PerfLibLogging::Provider(void)

- ea: `0x140007410`
- end: `0x1400074c9`
- name: `?Provider@PerfLibLogging@@SAPEBU_tlgProvider_t@@XZ`
- size: `185`
- prototype: `const struct _tlgProvider_t *(void)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140007338`
- `0x1400074d0`

## callees

- `0x140001f44`
- `0x140004bcc`
- `0x140007410`

## import_xrefs

- `KERNEL32!InitOnceBeginInitialize` at `0x140007438`
- `KERNEL32!InitOnceBeginInitialize` at `0x140007438`
- `KERNEL32!InitOnceComplete` at `0x1400074b4`
- `KERNEL32!InitOnceComplete` at `0x1400074b4`

## pseudocode

```c
const struct _tlgProvider_t *PerfLibLogging::Provider(void)
{
  void (*v0)(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, void *); // r8
  WINBOOL v2; // [rsp+30h] [rbp+8h] BYREF
  _QWORD *v3; // [rsp+38h] [rbp+10h] BYREF

  v3 = 0;
  v2 = 0;
  if ( InitOnceBeginInitialize(&`PerfLibLogging::Instance'::`2'::wrapper, 0, &v2, (LPVOID *)&v3) && v2 )
  {
    qword_14000C4D0 = 0;
    v3 = &qword_14000C4C8;
    qword_14000C4C8 = &PerfLibLogging::`vftable';
    byte_14000C4D8 = 0;
    dword_14000C4DC = 0;
    qword_14000C4E0 = (struct _tlgProvider_t *)&`PerfLibLogging::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(_lambda_413cbca4d6bb2bbe5e98eab3b821cc31_::_lambda_invoker_cdecl_);
    wil::TraceLoggingProvider::Register((wil::TraceLoggingProvider *)&qword_14000C4C8, qword_14000C4E0, v0);
    InitOnceComplete(&`PerfLibLogging::Instance'::`2'::wrapper, 0, &qword_14000C4C8);
  }
  return (const struct _tlgProvider_t *)v3[1];
}

```

## disassembly

```asm
0x140007410  mov     rax, rsp
0x140007413  push    rbx
0x140007414  sub     rsp, 20h
0x140007418  lea     r9, [rax+10h]; lpContext
0x14000741c  mov     qword ptr [rax+10h], 0
0x140007424  lea     r8, [rax+8]; fPending
0x140007428  mov     dword ptr [rax+8], 0
0x14000742f  xor     edx, edx; dwFlags
0x140007431  lea     rcx, ?wrapper@?1??Instance@PerfLibLogging@@KAPEAV2@XZ@4V?$static_lazy@VPerfLibLogging@@@details@wil@@A; lpInitOnce
0x140007438  call    cs:__imp_InitOnceBeginInitialize
0x14000743e  test    eax, eax
0x140007440  jz      short loc_1400074BA
0x140007442  cmp     [rsp+28h+arg_0], 0
0x140007447  jz      short loc_1400074BA
0x140007449  lea     rbx, qword_14000C4C8
0x140007450  mov     cs:qword_14000C4D0, 0
0x14000745b  lea     rax, ??_7PerfLibLogging@@6B@; const PerfLibLogging::`vftable'
0x140007462  mov     [rsp+28h+arg_8], rbx
0x140007467  mov     cs:qword_14000C4C8, rax
0x14000746e  mov     cs:byte_14000C4D8, 0
0x140007475  mov     cs:dword_14000C4DC, 0
0x14000747f  lea     rax, ?__hInner@?1???0StaticHandle@PerfLibLogging@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `PerfLibLogging::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x140007486  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_413cbca4d6bb2bbe5e98eab3b821cc31_@@CA@XZ; void (__cdecl *)()
0x14000748d  mov     cs:qword_14000C4E0, rax
0x140007494  call    atexit
0x140007499  mov     rdx, cs:qword_14000C4E0; struct _tlgProvider_t *
0x1400074a0  mov     rcx, rbx; this
0x1400074a3  call    ?Register@TraceLoggingProvider@wil@@IEAAXQEBU_tlgProvider_t@@P6AXPEBU_GUID@@KE_K2PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z@Z; wil::TraceLoggingProvider::Register(_tlgProvider_t const * const,void (*)(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *))
0x1400074a8  mov     r8, rbx; lpContext
0x1400074ab  lea     rcx, ?wrapper@?1??Instance@PerfLibLogging@@KAPEAV2@XZ@4V?$static_lazy@VPerfLibLogging@@@details@wil@@A; lpInitOnce
0x1400074b2  xor     edx, edx; dwFlags
0x1400074b4  call    cs:__imp_InitOnceComplete
0x1400074ba  mov     rax, [rsp+28h+arg_8]
0x1400074bf  mov     rax, [rax+8]
0x1400074c3  add     rsp, 20h
0x1400074c7  pop     rbx
0x1400074c8  retn
```
