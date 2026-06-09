# PrintUtilTelemetry::Instance(void)

- ea: `0x180035824`
- end: `0x1800358f4`
- name: `?Instance@PrintUtilTelemetry@@KAPEAV1@XZ`
- size: `208`
- prototype: `struct PrintUtilTelemetry *(void)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18003488c`
- `0x180036984`

## callees

- `0x1800022c8`
- `0x180035824`
- `0x180036454`
- `0x18005d010`

## import_xrefs

- `KERNEL32!InitOnceComplete` at `0x1800358e3`
- `KERNEL32!InitOnceComplete` at `0x1800358e3`
- `KERNEL32!InitOnceBeginInitialize` at `0x18003584c`
- `KERNEL32!InitOnceBeginInitialize` at `0x18003584c`

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
    qword_180074650 = 0;
    qword_180074648 = (__int64)&wil::TraceLoggingProvider::`vftable';
    v2 = &qword_180074648;
    byte_180074658 = 0;
    dword_18007465C = 0;
    atexit(_lambda_b30891faa824e6a906932a07a6ec270c_::_lambda_invoker_cdecl_);
    qword_180074650 = (__int64)PrintUtilLogging::Provider();
    byte_180074658 = 0;
    dword_18007465C = 1;
    (*(void (__fastcall **)(__int64 *))(qword_180074648 + 8))(&qword_180074648);
    InitOnceComplete(&`PrintUtilTelemetry::Instance'::`2'::wrapper, 0, &qword_180074648);
  }
  return (struct PrintUtilTelemetry *)v2;
}

```

## disassembly

```asm
0x180035824  mov     rax, rsp
0x180035827  push    rbx
0x180035828  sub     rsp, 20h
0x18003582c  lea     r9, [rax+10h]; lpContext
0x180035830  mov     qword ptr [rax+10h], 0
0x180035838  lea     r8, [rax+8]; fPending
0x18003583c  mov     dword ptr [rax+8], 0
0x180035843  xor     edx, edx; dwFlags
0x180035845  lea     rcx, ?wrapper@?1??Instance@PrintUtilTelemetry@@KAPEAV2@XZ@4V?$static_lazy@VPrintUtilTelemetry@@@details@wil@@A; lpInitOnce
0x18003584c  call    cs:__imp_InitOnceBeginInitialize
0x180035852  test    eax, eax
0x180035854  jz      loc_1800358E9
0x18003585a  cmp     [rsp+28h+arg_0], 0
0x18003585f  jz      loc_1800358E9
0x180035865  lea     rax, ??_7TraceLoggingProvider@wil@@6B@; const wil::TraceLoggingProvider::`vftable'
0x18003586c  mov     cs:qword_180074650, 0
0x180035877  lea     rbx, qword_180074648
0x18003587e  mov     cs:qword_180074648, rax
0x180035885  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_b30891faa824e6a906932a07a6ec270c_@@CA@XZ; void (__cdecl *)()
0x18003588c  mov     [rsp+28h+arg_8], rbx
0x180035891  mov     cs:byte_180074658, 0
0x180035898  mov     cs:dword_18007465C, 0
0x1800358a2  call    atexit
0x1800358a7  call    ?Provider@PrintUtilLogging@@SAPEBU_tlgProvider_t@@XZ; PrintUtilLogging::Provider(void)
0x1800358ac  mov     cs:qword_180074650, rax
0x1800358b3  mov     rcx, rbx
0x1800358b6  mov     rax, cs:qword_180074648
0x1800358bd  mov     cs:byte_180074658, 0
0x1800358c4  mov     cs:dword_18007465C, 1
0x1800358ce  mov     rax, [rax+8]
0x1800358d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800358d7  mov     r8, rbx; lpContext
0x1800358da  lea     rcx, ?wrapper@?1??Instance@PrintUtilTelemetry@@KAPEAV2@XZ@4V?$static_lazy@VPrintUtilTelemetry@@@details@wil@@A; lpInitOnce
0x1800358e1  xor     edx, edx; dwFlags
0x1800358e3  call    cs:__imp_InitOnceComplete
0x1800358e9  mov     rax, [rsp+28h+arg_8]
0x1800358ee  add     rsp, 20h
0x1800358f2  pop     rbx
0x1800358f3  retn
```
