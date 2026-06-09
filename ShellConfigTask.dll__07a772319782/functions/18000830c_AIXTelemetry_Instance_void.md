# AIXTelemetry::Instance(void)

- ea: `0x18000830c`
- end: `0x1800083dc`
- name: `?Instance@AIXTelemetry@@KAPEAV1@XZ`
- size: `208`
- prototype: `struct AIXTelemetry *(void)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180006ce0`
- `0x18002b864`

## callees

- `0x180002978`
- `0x18000830c`
- `0x18000896c`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800083cb`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800083cb`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180008334`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180008334`

## pseudocode

```c
struct AIXTelemetry *AIXTelemetry::Instance(void)
{
  WINBOOL v1; // [rsp+30h] [rbp+8h] BYREF
  __int64 *v2; // [rsp+38h] [rbp+10h] BYREF

  v2 = 0;
  v1 = 0;
  if ( InitOnceBeginInitialize(&`AIXTelemetry::Instance'::`2'::wrapper, 0, &v1, (LPVOID *)&v2) && v1 )
  {
    qword_180041960 = 0;
    qword_180041958 = (__int64)&AIXTelemetry::`vftable';
    v2 = &qword_180041958;
    byte_180041968 = 0;
    dword_18004196C = 0;
    atexit(_lambda_9beddb4148de818ebf02ec0fe0b0606b_::_lambda_invoker_cdecl_);
    qword_180041960 = (__int64)AIXTelemetryLogging::Provider();
    byte_180041968 = 0;
    dword_18004196C = 1;
    (*(void (__fastcall **)(__int64 *))(qword_180041958 + 8))(&qword_180041958);
    InitOnceComplete(&`AIXTelemetry::Instance'::`2'::wrapper, 0, &qword_180041958);
  }
  return (struct AIXTelemetry *)v2;
}

```

## disassembly

```asm
0x18000830c  mov     rax, rsp
0x18000830f  push    rbx
0x180008310  sub     rsp, 20h
0x180008314  lea     r9, [rax+10h]; lpContext
0x180008318  mov     qword ptr [rax+10h], 0
0x180008320  lea     r8, [rax+8]; fPending
0x180008324  mov     dword ptr [rax+8], 0
0x18000832b  xor     edx, edx; dwFlags
0x18000832d  lea     rcx, ?wrapper@?1??Instance@AIXTelemetry@@KAPEAV2@XZ@4V?$static_lazy@VAIXTelemetry@@@details@wil@@A; lpInitOnce
0x180008334  call    cs:__imp_InitOnceBeginInitialize
0x18000833a  test    eax, eax
0x18000833c  jz      loc_1800083D1
0x180008342  cmp     [rsp+28h+arg_0], 0
0x180008347  jz      loc_1800083D1
0x18000834d  lea     rax, ??_7AIXTelemetry@@6B@; const AIXTelemetry::`vftable'
0x180008354  mov     cs:qword_180041960, 0
0x18000835f  lea     rbx, qword_180041958
0x180008366  mov     cs:qword_180041958, rax
0x18000836d  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_9beddb4148de818ebf02ec0fe0b0606b_@@CA@XZ; void (__cdecl *)()
0x180008374  mov     [rsp+28h+arg_8], rbx
0x180008379  mov     cs:byte_180041968, 0
0x180008380  mov     cs:dword_18004196C, 0
0x18000838a  call    atexit
0x18000838f  call    ?Provider@AIXTelemetryLogging@@SAPEBU_tlgProvider_t@@XZ; AIXTelemetryLogging::Provider(void)
0x180008394  mov     cs:qword_180041960, rax
0x18000839b  mov     rcx, rbx
0x18000839e  mov     rax, cs:qword_180041958
0x1800083a5  mov     cs:byte_180041968, 0
0x1800083ac  mov     cs:dword_18004196C, 1
0x1800083b6  mov     rax, [rax+8]
0x1800083ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800083bf  mov     r8, rbx; lpContext
0x1800083c2  lea     rcx, ?wrapper@?1??Instance@AIXTelemetry@@KAPEAV2@XZ@4V?$static_lazy@VAIXTelemetry@@@details@wil@@A; lpInitOnce
0x1800083c9  xor     edx, edx; dwFlags
0x1800083cb  call    cs:__imp_InitOnceComplete
0x1800083d1  mov     rax, [rsp+28h+arg_8]
0x1800083d6  add     rsp, 20h
0x1800083da  pop     rbx
0x1800083db  retn
```
