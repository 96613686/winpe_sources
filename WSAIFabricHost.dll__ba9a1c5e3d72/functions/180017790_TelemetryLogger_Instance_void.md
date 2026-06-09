# TelemetryLogger::Instance(void)

- ea: `0x180017790`
- end: `0x18001787a`
- name: `?Instance@TelemetryLogger@@KAPEAV1@XZ`
- size: `234`
- prototype: `struct TelemetryLogger *(void)`
- caller_count: `55`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800160c0`
- `0x1800275dc`
- `0x180056208`
- `0x1800562f8`
- `0x180056390`
- `0x18005654c`
- `0x180056614`
- `0x180056998`
- `0x180056a78`
- `0x180056b70`
- `0x180056c1c`
- `0x180056e7c`
- `0x180057100`
- `0x180057190`
- `0x180057220`
- `0x1800572dc`
- `0x180057398`
- `0x180057454`
- `0x180057be0`
- `0x180057c70`
- `0x180058290`
- `0x1800583ac`
- `0x1800584e4`
- `0x1800585fc`
- `0x180058764`
- `0x1800588d4`
- `0x180058a6c`
- `0x18005a660`
- `0x18005a6e0`
- `0x1800645b0`
- `0x180064930`
- `0x180066984`
- `0x180066b84`
- `0x180066cb0`
- `0x180066e7c`
- `0x180066f7c`
- `0x180067144`
- `0x180067270`
- `0x1800673a8`
- `0x1800674e4`
- `0x1800678a8`
- `0x180067c84`
- `0x180067fec`
- `0x180068350`
- `0x18006870c`
- `0x180068aa0`
- `0x180068d90`
- `0x180069020`
- `0x1800692b0`
- `0x180069540`

## callees

- `0x1800016ac`
- `0x180005120`
- `0x180017790`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1800177b8`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1800177b8`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180017869`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180017869`

## pseudocode

```c
struct TelemetryLogger *TelemetryLogger::Instance(void)
{
  WINBOOL v1; // [rsp+30h] [rbp+8h] BYREF
  __int64 *v2; // [rsp+38h] [rbp+10h] BYREF

  v2 = 0;
  v1 = 0;
  if ( __std_init_once_begin_initialize(&`TelemetryLogger::Instance'::`2'::wrapper, 0, &v1, (LPVOID *)&v2) && v1 )
  {
    qword_1800AF510 = 0;
    v2 = &qword_1800AF508;
    qword_1800AF508 = (__int64)&SearchIndexerTraceProvider::`vftable';
    byte_1800AF518 = 0;
    dword_1800AF51C = 0;
    qword_1800AF520 = &`TelemetryLogger::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(_lambda_d0de0aea0d9e121ad3b76698eff7e035_::_lambda_invoker_cdecl_);
    qword_1800AF510 = (__int64)qword_1800AF520;
    byte_1800AF518 = 1;
    TraceLoggingRegisterEx_EventRegister_EventSetInformation(qword_1800AF520);
    dword_1800AF51C = 1;
    (*(void (__fastcall **)(__int64 *))(qword_1800AF508 + 8))(&qword_1800AF508);
    InitOnceComplete(&`TelemetryLogger::Instance'::`2'::wrapper, 0, &qword_1800AF508);
  }
  return (struct TelemetryLogger *)v2;
}

```

## disassembly

```asm
0x180017790  mov     rax, rsp
0x180017793  push    rbx
0x180017794  sub     rsp, 20h
0x180017798  lea     r9, [rax+10h]; lpContext
0x18001779c  mov     qword ptr [rax+10h], 0
0x1800177a4  lea     r8, [rax+8]; fPending
0x1800177a8  mov     dword ptr [rax+8], 0
0x1800177af  xor     edx, edx; dwFlags
0x1800177b1  lea     rcx, ?wrapper@?1??Instance@TelemetryLogger@@KAPEAV2@XZ@4V?$static_lazy@VTelemetryLogger@@@details@wil@@A; lpInitOnce
0x1800177b8  call    cs:__imp___std_init_once_begin_initialize
0x1800177be  test    eax, eax
0x1800177c0  jz      loc_18001786F
0x1800177c6  cmp     [rsp+28h+arg_0], 0
0x1800177cb  jz      loc_18001786F
0x1800177d1  lea     rbx, qword_1800AF508
0x1800177d8  mov     cs:qword_1800AF510, 0
0x1800177e3  lea     rax, ??_7SearchIndexerTraceProvider@@6B@; const SearchIndexerTraceProvider::`vftable'
0x1800177ea  mov     [rsp+28h+arg_8], rbx
0x1800177ef  mov     cs:qword_1800AF508, rax
0x1800177f6  mov     cs:byte_1800AF518, 0
0x1800177fd  mov     cs:dword_1800AF51C, 0
0x180017807  lea     rax, ?__hInner@?1???0StaticHandle@TelemetryLogger@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `TelemetryLogger::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x18001780e  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d0de0aea0d9e121ad3b76698eff7e035_@@CA@XZ; void (__cdecl *)()
0x180017815  mov     cs:qword_1800AF520, rax
0x18001781c  call    atexit
0x180017821  mov     rcx, cs:qword_1800AF520; CallbackContext
0x180017828  xor     r8d, r8d
0x18001782b  xor     edx, edx
0x18001782d  mov     cs:qword_1800AF510, rcx
0x180017834  mov     cs:byte_1800AF518, 1
0x18001783b  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x180017840  mov     rax, cs:qword_1800AF508
0x180017847  mov     rcx, rbx
0x18001784a  mov     cs:dword_1800AF51C, 1
0x180017854  mov     rax, [rax+8]
0x180017858  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001785d  mov     r8, rbx; lpContext
0x180017860  lea     rcx, ?wrapper@?1??Instance@TelemetryLogger@@KAPEAV2@XZ@4V?$static_lazy@VTelemetryLogger@@@details@wil@@A; lpInitOnce
0x180017867  xor     edx, edx; dwFlags
0x180017869  call    cs:__imp_InitOnceComplete
0x18001786f  mov     rax, [rsp+28h+arg_8]
0x180017874  add     rsp, 20h
0x180017878  pop     rbx
0x180017879  retn
```
