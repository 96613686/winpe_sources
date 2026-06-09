# PerfLibTelemetry::Instance(void)

- ea: `0x140007338`
- end: `0x140007408`
- name: `?Instance@PerfLibTelemetry@@KAPEAV1@XZ`
- size: `208`
- prototype: `struct PerfLibTelemetry *(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1400074d0`

## callees

- `0x140001f44`
- `0x140007338`
- `0x140007410`
- `0x140008010`

## import_xrefs

- `KERNEL32!InitOnceBeginInitialize` at `0x140007360`
- `KERNEL32!InitOnceBeginInitialize` at `0x140007360`
- `KERNEL32!InitOnceComplete` at `0x1400073f7`
- `KERNEL32!InitOnceComplete` at `0x1400073f7`

## pseudocode

```c
struct PerfLibTelemetry *PerfLibTelemetry::Instance(void)
{
  WINBOOL v1; // [rsp+30h] [rbp+8h] BYREF
  __int64 *v2; // [rsp+38h] [rbp+10h] BYREF

  v2 = 0;
  v1 = 0;
  if ( InitOnceBeginInitialize(&`PerfLibTelemetry::Instance'::`2'::wrapper, 0, &v1, (LPVOID *)&v2) && v1 )
  {
    qword_14000C4F8 = 0;
    qword_14000C4F0 = (__int64)&PerfLibLogging::`vftable';
    v2 = &qword_14000C4F0;
    byte_14000C500 = 0;
    dword_14000C504 = 0;
    atexit(_lambda_afb3aedd42a937a6b0239593c828df1f_::_lambda_invoker_cdecl_);
    qword_14000C4F8 = (__int64)PerfLibLogging::Provider();
    byte_14000C500 = 0;
    dword_14000C504 = 1;
    (*(void (__fastcall **)(__int64 *))(qword_14000C4F0 + 8))(&qword_14000C4F0);
    InitOnceComplete(&`PerfLibTelemetry::Instance'::`2'::wrapper, 0, &qword_14000C4F0);
  }
  return (struct PerfLibTelemetry *)v2;
}

```

## disassembly

```asm
0x140007338  mov     rax, rsp
0x14000733b  push    rbx
0x14000733c  sub     rsp, 20h
0x140007340  lea     r9, [rax+10h]; lpContext
0x140007344  mov     qword ptr [rax+10h], 0
0x14000734c  lea     r8, [rax+8]; fPending
0x140007350  mov     dword ptr [rax+8], 0
0x140007357  xor     edx, edx; dwFlags
0x140007359  lea     rcx, ?wrapper@?1??Instance@PerfLibTelemetry@@KAPEAV2@XZ@4V?$static_lazy@VPerfLibTelemetry@@@details@wil@@A; lpInitOnce
0x140007360  call    cs:__imp_InitOnceBeginInitialize
0x140007366  test    eax, eax
0x140007368  jz      loc_1400073FD
0x14000736e  cmp     [rsp+28h+arg_0], 0
0x140007373  jz      loc_1400073FD
0x140007379  lea     rax, ??_7PerfLibLogging@@6B@; const PerfLibLogging::`vftable'
0x140007380  mov     cs:qword_14000C4F8, 0
0x14000738b  lea     rbx, qword_14000C4F0
0x140007392  mov     cs:qword_14000C4F0, rax
0x140007399  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_afb3aedd42a937a6b0239593c828df1f_@@CA@XZ; void (__cdecl *)()
0x1400073a0  mov     [rsp+28h+arg_8], rbx
0x1400073a5  mov     cs:byte_14000C500, 0
0x1400073ac  mov     cs:dword_14000C504, 0
0x1400073b6  call    atexit
0x1400073bb  call    ?Provider@PerfLibLogging@@SAPEBU_tlgProvider_t@@XZ; PerfLibLogging::Provider(void)
0x1400073c0  mov     cs:qword_14000C4F8, rax
0x1400073c7  mov     rcx, rbx
0x1400073ca  mov     rax, cs:qword_14000C4F0
0x1400073d1  mov     cs:byte_14000C500, 0
0x1400073d8  mov     cs:dword_14000C504, 1
0x1400073e2  mov     rax, [rax+8]
0x1400073e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400073eb  mov     r8, rbx; lpContext
0x1400073ee  lea     rcx, ?wrapper@?1??Instance@PerfLibTelemetry@@KAPEAV2@XZ@4V?$static_lazy@VPerfLibTelemetry@@@details@wil@@A; lpInitOnce
0x1400073f5  xor     edx, edx; dwFlags
0x1400073f7  call    cs:__imp_InitOnceComplete
0x1400073fd  mov     rax, [rsp+28h+arg_8]
0x140007402  add     rsp, 20h
0x140007406  pop     rbx
0x140007407  retn
```
