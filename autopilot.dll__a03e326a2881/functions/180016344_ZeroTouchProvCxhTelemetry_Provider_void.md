# ZeroTouchProvCxhTelemetry::Provider(void)

- ea: `0x180016344`
- end: `0x180016418`
- name: `?Provider@ZeroTouchProvCxhTelemetry@@SAPEBU_tlgProvider_t@@XZ`
- size: `212`
- prototype: `const struct _tlgProvider_t *(void)`
- caller_count: `5`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180015af0`
- `0x180015d4c`
- `0x180015de0`
- `0x180016420`
- `0x18001b938`

## callees

- `0x1800049c8`
- `0x180016284`
- `0x180016344`
- `0x18002e010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18001636c`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18001636c`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180016403`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180016403`

## pseudocode

```c
const struct _tlgProvider_t *ZeroTouchProvCxhTelemetry::Provider(void)
{
  WINBOOL v1; // [rsp+30h] [rbp+8h] BYREF
  __int64 *v2; // [rsp+38h] [rbp+10h] BYREF

  v2 = 0;
  v1 = 0;
  if ( __std_init_once_begin_initialize(&`ZeroTouchProvCxhTelemetry::Instance'::`2'::wrapper, 0, &v1, (LPVOID *)&v2)
    && v1 )
  {
    qword_180043A88 = 0;
    qword_180043A80 = (__int64)&ZeroTouchProvCxhTelemetry::`vftable';
    v2 = &qword_180043A80;
    byte_180043A90 = 0;
    dword_180043A94 = 0;
    atexit(_lambda_83e41ce2d9c84e0531eaa5aafac1b80d_::_lambda_invoker_cdecl_);
    qword_180043A88 = (__int64)AutoPilotTelemProvider::Provider();
    byte_180043A90 = 0;
    dword_180043A94 = 1;
    (*(void (__fastcall **)(__int64 *))(qword_180043A80 + 8))(&qword_180043A80);
    InitOnceComplete(&`ZeroTouchProvCxhTelemetry::Instance'::`2'::wrapper, 0, &qword_180043A80);
  }
  return (const struct _tlgProvider_t *)v2[1];
}

```

## disassembly

```asm
0x180016344  mov     rax, rsp
0x180016347  push    rbx
0x180016348  sub     rsp, 20h
0x18001634c  lea     r9, [rax+10h]; lpContext
0x180016350  mov     qword ptr [rax+10h], 0
0x180016358  lea     r8, [rax+8]; fPending
0x18001635c  mov     dword ptr [rax+8], 0
0x180016363  xor     edx, edx; dwFlags
0x180016365  lea     rcx, ?wrapper@?1??Instance@ZeroTouchProvCxhTelemetry@@KAPEAV2@XZ@4V?$static_lazy@VZeroTouchProvCxhTelemetry@@@details@wil@@A; lpInitOnce
0x18001636c  call    cs:__imp___std_init_once_begin_initialize
0x180016372  test    eax, eax
0x180016374  jz      loc_180016409
0x18001637a  cmp     [rsp+28h+arg_0], 0
0x18001637f  jz      loc_180016409
0x180016385  lea     rax, ??_7ZeroTouchProvCxhTelemetry@@6B@; const ZeroTouchProvCxhTelemetry::`vftable'
0x18001638c  mov     cs:qword_180043A88, 0
0x180016397  lea     rbx, qword_180043A80
0x18001639e  mov     cs:qword_180043A80, rax
0x1800163a5  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_83e41ce2d9c84e0531eaa5aafac1b80d_@@CA@XZ; void (__cdecl *)()
0x1800163ac  mov     [rsp+28h+arg_8], rbx
0x1800163b1  mov     cs:byte_180043A90, 0
0x1800163b8  mov     cs:dword_180043A94, 0
0x1800163c2  call    atexit
0x1800163c7  call    ?Provider@AutoPilotTelemProvider@@SAPEBU_tlgProvider_t@@XZ; AutoPilotTelemProvider::Provider(void)
0x1800163cc  mov     cs:qword_180043A88, rax
0x1800163d3  mov     rcx, rbx
0x1800163d6  mov     rax, cs:qword_180043A80
0x1800163dd  mov     cs:byte_180043A90, 0
0x1800163e4  mov     cs:dword_180043A94, 1
0x1800163ee  mov     rax, [rax+8]
0x1800163f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800163f7  mov     r8, rbx; lpContext
0x1800163fa  lea     rcx, ?wrapper@?1??Instance@ZeroTouchProvCxhTelemetry@@KAPEAV2@XZ@4V?$static_lazy@VZeroTouchProvCxhTelemetry@@@details@wil@@A; lpInitOnce
0x180016401  xor     edx, edx; dwFlags
0x180016403  call    cs:__imp_InitOnceComplete
0x180016409  mov     rax, [rsp+28h+arg_8]
0x18001640e  mov     rax, [rax+8]
0x180016412  add     rsp, 20h
0x180016416  pop     rbx
0x180016417  retn
```
