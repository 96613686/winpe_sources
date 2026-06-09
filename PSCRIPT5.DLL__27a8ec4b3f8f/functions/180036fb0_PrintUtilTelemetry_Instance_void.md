# PrintUtilTelemetry::Instance(void)

- ea: `0x180036fb0`
- end: `0x18003708d`
- name: `?Instance@PrintUtilTelemetry@@KAPEAV1@XZ`
- size: `221`
- prototype: `struct PrintUtilTelemetry *(void)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180035fb4`
- `0x1800381f4`

## callees

- `0x180002308`
- `0x180036fb0`
- `0x180037ca4`
- `0x18005f010`

## import_xrefs

- `KERNEL32!InitOnceComplete` at `0x180037075`
- `KERNEL32!InitOnceComplete` at `0x180037075`
- `KERNEL32!InitOnceBeginInitialize` at `0x180036fd8`
- `KERNEL32!InitOnceBeginInitialize` at `0x180036fd8`

## pseudocode

```c
struct PrintUtilTelemetry *PrintUtilTelemetry::Instance(void)
{
  BOOL v1; // [rsp+30h] [rbp+8h] BYREF
  __int64 *v2; // [rsp+38h] [rbp+10h] BYREF

  v2 = 0;
  v1 = 0;
  if ( InitOnceBeginInitialize(&`PrintUtilTelemetry::Instance'::`2'::wrapper, 0, &v1, (LPVOID *)&v2) && v1 )
  {
    qword_180076640 = 0;
    qword_180076638 = (__int64)&wil::TraceLoggingProvider::`vftable';
    v2 = &qword_180076638;
    byte_180076648 = 0;
    dword_18007664C = 0;
    atexit(_lambda_b30891faa824e6a906932a07a6ec270c_::_lambda_invoker_cdecl_);
    qword_180076640 = (__int64)PrintUtilLogging::Provider();
    byte_180076648 = 0;
    dword_18007664C = 1;
    (*(void (__fastcall **)(__int64 *))(qword_180076638 + 8))(&qword_180076638);
    InitOnceComplete(&`PrintUtilTelemetry::Instance'::`2'::wrapper, 0, &qword_180076638);
  }
  return (struct PrintUtilTelemetry *)v2;
}

```

## disassembly

```asm
0x180036fb0  mov     rax, rsp
0x180036fb3  push    rbx
0x180036fb4  sub     rsp, 20h
0x180036fb8  lea     r9, [rax+10h]; lpContext
0x180036fbc  mov     qword ptr [rax+10h], 0
0x180036fc4  lea     r8, [rax+8]; fPending
0x180036fc8  mov     dword ptr [rax+8], 0
0x180036fcf  xor     edx, edx; dwFlags
0x180036fd1  lea     rcx, ?wrapper@?1??Instance@PrintUtilTelemetry@@KAPEAV2@XZ@4V?$static_lazy@VPrintUtilTelemetry@@@details@wil@@A; lpInitOnce
0x180036fd8  call    cs:__imp_InitOnceBeginInitialize
0x180036fdf  nop     dword ptr [rax+rax+00h]
0x180036fe4  test    eax, eax
0x180036fe6  jz      loc_180037081
0x180036fec  cmp     [rsp+28h+arg_0], 0
0x180036ff1  jz      loc_180037081
0x180036ff7  lea     rax, ??_7TraceLoggingProvider@wil@@6B@; const wil::TraceLoggingProvider::`vftable'
0x180036ffe  mov     cs:qword_180076640, 0
0x180037009  lea     rbx, qword_180076638
0x180037010  mov     cs:qword_180076638, rax
0x180037017  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_b30891faa824e6a906932a07a6ec270c_@@CA@XZ; void (__cdecl *)()
0x18003701e  mov     [rsp+28h+arg_8], rbx
0x180037023  mov     cs:byte_180076648, 0
0x18003702a  mov     cs:dword_18007664C, 0
0x180037034  call    atexit
0x180037039  call    ?Provider@PrintUtilLogging@@SAPEBU_tlgProvider_t@@XZ; PrintUtilLogging::Provider(void)
0x18003703e  mov     cs:qword_180076640, rax
0x180037045  mov     rcx, rbx
0x180037048  mov     rax, cs:qword_180076638
0x18003704f  mov     cs:byte_180076648, 0
0x180037056  mov     cs:dword_18007664C, 1
0x180037060  mov     rax, [rax+8]
0x180037064  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037069  mov     r8, rbx; lpContext
0x18003706c  lea     rcx, ?wrapper@?1??Instance@PrintUtilTelemetry@@KAPEAV2@XZ@4V?$static_lazy@VPrintUtilTelemetry@@@details@wil@@A; lpInitOnce
0x180037073  xor     edx, edx; dwFlags
0x180037075  call    cs:__imp_InitOnceComplete
0x18003707c  nop     dword ptr [rax+rax+00h]
0x180037081  mov     rax, [rsp+28h+arg_8]
0x180037086  add     rsp, 20h
0x18003708a  pop     rbx
0x18003708b  retn
```
