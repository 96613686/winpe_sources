# BingFilterDSTelemetry::Instance(void)

- ea: `0x18000537c`
- end: `0x180005466`
- name: `?Instance@BingFilterDSTelemetry@@KAPEAV1@XZ`
- size: `234`
- prototype: `struct BingFilterDSTelemetry *(void)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180004570`
- `0x180007a18`

## callees

- `0x1800015b4`
- `0x18000265c`
- `0x18000537c`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1800053a4`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1800053a4`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180005455`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180005455`

## pseudocode

```c
struct BingFilterDSTelemetry *BingFilterDSTelemetry::Instance(void)
{
  BOOL v1; // [rsp+30h] [rbp+8h] BYREF
  __int64 *v2; // [rsp+38h] [rbp+10h] BYREF

  v2 = 0;
  v1 = 0;
  if ( InitOnceBeginInitialize(&`BingFilterDSTelemetry::Instance'::`2'::wrapper, 0, &v1, (LPVOID *)&v2) && v1 )
  {
    qword_180015B00 = 0;
    v2 = &qword_180015AF8;
    qword_180015AF8 = (__int64)&wil::TraceLoggingProvider::`vftable';
    byte_180015B08 = 0;
    dword_180015B0C = 0;
    CallbackContext = &`BingFilterDSTelemetry::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(_lambda_2af219bd64725203e8bf6583d6b84790_::_lambda_invoker_cdecl_);
    qword_180015B00 = (__int64)CallbackContext;
    byte_180015B08 = 1;
    TraceLoggingRegisterEx_EventRegister_EventSetInformation(CallbackContext);
    dword_180015B0C = 1;
    (*(void (__fastcall **)(__int64 *))(qword_180015AF8 + 8))(&qword_180015AF8);
    InitOnceComplete(&`BingFilterDSTelemetry::Instance'::`2'::wrapper, 0, &qword_180015AF8);
  }
  return (struct BingFilterDSTelemetry *)v2;
}

```

## disassembly

```asm
0x18000537c  mov     rax, rsp
0x18000537f  push    rbx
0x180005380  sub     rsp, 20h
0x180005384  lea     r9, [rax+10h]; lpContext
0x180005388  mov     qword ptr [rax+10h], 0
0x180005390  lea     r8, [rax+8]; fPending
0x180005394  mov     dword ptr [rax+8], 0
0x18000539b  xor     edx, edx; dwFlags
0x18000539d  lea     rcx, ?wrapper@?1??Instance@BingFilterDSTelemetry@@KAPEAV2@XZ@4V?$static_lazy@VBingFilterDSTelemetry@@@details@wil@@A; lpInitOnce
0x1800053a4  call    cs:__imp_InitOnceBeginInitialize
0x1800053aa  test    eax, eax
0x1800053ac  jz      loc_18000545B
0x1800053b2  cmp     [rsp+28h+arg_0], 0
0x1800053b7  jz      loc_18000545B
0x1800053bd  lea     rbx, qword_180015AF8
0x1800053c4  mov     cs:qword_180015B00, 0
0x1800053cf  lea     rax, ??_7TraceLoggingProvider@wil@@6B@; const wil::TraceLoggingProvider::`vftable'
0x1800053d6  mov     [rsp+28h+arg_8], rbx
0x1800053db  mov     cs:qword_180015AF8, rax
0x1800053e2  mov     cs:byte_180015B08, 0
0x1800053e9  mov     cs:dword_180015B0C, 0
0x1800053f3  lea     rax, ?__hInner@?1???0StaticHandle@BingFilterDSTelemetry@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `BingFilterDSTelemetry::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x1800053fa  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_2af219bd64725203e8bf6583d6b84790_@@CA@XZ; void (__cdecl *)()
0x180005401  mov     cs:CallbackContext, rax
0x180005408  call    atexit
0x18000540d  mov     rcx, cs:CallbackContext; CallbackContext
0x180005414  xor     r8d, r8d
0x180005417  xor     edx, edx
0x180005419  mov     cs:qword_180015B00, rcx
0x180005420  mov     cs:byte_180015B08, 1
0x180005427  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x18000542c  mov     rax, cs:qword_180015AF8
0x180005433  mov     rcx, rbx
0x180005436  mov     cs:dword_180015B0C, 1
0x180005440  mov     rax, [rax+8]
0x180005444  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005449  mov     r8, rbx; lpContext
0x18000544c  lea     rcx, ?wrapper@?1??Instance@BingFilterDSTelemetry@@KAPEAV2@XZ@4V?$static_lazy@VBingFilterDSTelemetry@@@details@wil@@A; lpInitOnce
0x180005453  xor     edx, edx; dwFlags
0x180005455  call    cs:__imp_InitOnceComplete
0x18000545b  mov     rax, [rsp+28h+arg_8]
0x180005460  add     rsp, 20h
0x180005464  pop     rbx
0x180005465  retn
```
