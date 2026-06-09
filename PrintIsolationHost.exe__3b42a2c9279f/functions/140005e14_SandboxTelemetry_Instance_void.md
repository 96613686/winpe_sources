# SandboxTelemetry::Instance(void)

- ea: `0x140005e14`
- end: `0x140005ee8`
- name: `?Instance@SandboxTelemetry@@KAPEAV1@XZ`
- size: `212`
- prototype: `struct SandboxTelemetry *(void)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14000634c`
- `0x140006454`

## callees

- `0x140001f44`
- `0x1400044dc`
- `0x140005e14`
- `0x140008010`

## import_xrefs

- `KERNEL32!InitOnceBeginInitialize` at `0x140005e3c`
- `KERNEL32!InitOnceBeginInitialize` at `0x140005e3c`
- `KERNEL32!InitOnceComplete` at `0x140005ed7`
- `KERNEL32!InitOnceComplete` at `0x140005ed7`

## pseudocode

```c
struct SandboxTelemetry *SandboxTelemetry::Instance(void)
{
  WINBOOL v1; // [rsp+30h] [rbp+8h] BYREF
  __int64 *v2; // [rsp+38h] [rbp+10h] BYREF

  v2 = 0;
  v1 = 0;
  if ( InitOnceBeginInitialize(&`SandboxTelemetry::Instance'::`2'::wrapper, 0, &v1, (LPVOID *)&v2) && v1 )
  {
    qword_14000C490 = 0;
    qword_14000C488 = (__int64)&wil::TraceLoggingProvider::`vftable';
    v2 = &qword_14000C488;
    byte_14000C498 = 0;
    dword_14000C49C = 0;
    atexit(_lambda_b349e8281252787553c8b1c24d2e5350_::_lambda_invoker_cdecl_);
    qword_14000C490 = *((_QWORD *)SandboxLogging::Instance() + 1);
    byte_14000C498 = 0;
    dword_14000C49C = 1;
    (*(void (__fastcall **)(__int64 *))(qword_14000C488 + 8))(&qword_14000C488);
    InitOnceComplete(&`SandboxTelemetry::Instance'::`2'::wrapper, 0, &qword_14000C488);
  }
  return (struct SandboxTelemetry *)v2;
}

```

## disassembly

```asm
0x140005e14  mov     rax, rsp
0x140005e17  push    rbx
0x140005e18  sub     rsp, 20h
0x140005e1c  lea     r9, [rax+10h]; lpContext
0x140005e20  mov     qword ptr [rax+10h], 0
0x140005e28  lea     r8, [rax+8]; fPending
0x140005e2c  mov     dword ptr [rax+8], 0
0x140005e33  xor     edx, edx; dwFlags
0x140005e35  lea     rcx, ?wrapper@?1??Instance@SandboxTelemetry@@KAPEAV2@XZ@4V?$static_lazy@VSandboxTelemetry@@@details@wil@@A; lpInitOnce
0x140005e3c  call    cs:__imp_InitOnceBeginInitialize
0x140005e42  test    eax, eax
0x140005e44  jz      loc_140005EDD
0x140005e4a  cmp     [rsp+28h+arg_0], 0
0x140005e4f  jz      loc_140005EDD
0x140005e55  lea     rax, ??_7TraceLoggingProvider@wil@@6B@; const wil::TraceLoggingProvider::`vftable'
0x140005e5c  mov     cs:qword_14000C490, 0
0x140005e67  lea     rbx, qword_14000C488
0x140005e6e  mov     cs:qword_14000C488, rax
0x140005e75  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_b349e8281252787553c8b1c24d2e5350_@@CA@XZ; void (__cdecl *)()
0x140005e7c  mov     [rsp+28h+arg_8], rbx
0x140005e81  mov     cs:byte_14000C498, 0
0x140005e88  mov     cs:dword_14000C49C, 0
0x140005e92  call    atexit
0x140005e97  call    ?Instance@SandboxLogging@@KAPEAV1@XZ; SandboxLogging::Instance(void)
0x140005e9c  mov     rcx, rbx
0x140005e9f  mov     rdx, [rax+8]
0x140005ea3  mov     rax, cs:qword_14000C488
0x140005eaa  mov     cs:qword_14000C490, rdx
0x140005eb1  mov     cs:byte_14000C498, 0
0x140005eb8  mov     cs:dword_14000C49C, 1
0x140005ec2  mov     rax, [rax+8]
0x140005ec6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005ecb  mov     r8, rbx; lpContext
0x140005ece  lea     rcx, ?wrapper@?1??Instance@SandboxTelemetry@@KAPEAV2@XZ@4V?$static_lazy@VSandboxTelemetry@@@details@wil@@A; lpInitOnce
0x140005ed5  xor     edx, edx; dwFlags
0x140005ed7  call    cs:__imp_InitOnceComplete
0x140005edd  mov     rax, [rsp+28h+arg_8]
0x140005ee2  add     rsp, 20h
0x140005ee6  pop     rbx
0x140005ee7  retn
```
