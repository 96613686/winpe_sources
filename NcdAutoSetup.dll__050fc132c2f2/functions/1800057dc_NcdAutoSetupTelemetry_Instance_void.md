# NcdAutoSetupTelemetry::Instance(void)

- ea: `0x1800057dc`
- end: `0x1800058ac`
- name: `?Instance@NcdAutoSetupTelemetry@@KAPEAV1@XZ`
- size: `208`
- prototype: `struct NcdAutoSetupTelemetry *(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800094c8`

## callees

- `0x180001e40`
- `0x1800057dc`
- `0x180005f94`
- `0x180014010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180005804`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180005804`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000589b`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000589b`

## pseudocode

```c
struct NcdAutoSetupTelemetry *NcdAutoSetupTelemetry::Instance(void)
{
  WINBOOL v1; // [rsp+30h] [rbp+8h] BYREF
  __int64 *v2; // [rsp+38h] [rbp+10h] BYREF

  v2 = 0;
  v1 = 0;
  if ( InitOnceBeginInitialize(&`NcdAutoSetupTelemetry::Instance'::`2'::wrapper, 0, &v1, (LPVOID *)&v2) && v1 )
  {
    qword_18001AE50 = 0;
    qword_18001AE48 = (__int64)&wil::TraceLoggingProvider::`vftable';
    v2 = &qword_18001AE48;
    byte_18001AE58 = 0;
    dword_18001AE5C = 0;
    atexit(_lambda_e242f0e0f0aaa7b23a4cb48cdf7e6943_::_lambda_invoker_cdecl_);
    qword_18001AE50 = (__int64)NcdAutoSetupLogging::Provider();
    byte_18001AE58 = 0;
    dword_18001AE5C = 1;
    (*(void (__fastcall **)(__int64 *))(qword_18001AE48 + 8))(&qword_18001AE48);
    InitOnceComplete(&`NcdAutoSetupTelemetry::Instance'::`2'::wrapper, 0, &qword_18001AE48);
  }
  return (struct NcdAutoSetupTelemetry *)v2;
}

```

## disassembly

```asm
0x1800057dc  mov     rax, rsp
0x1800057df  push    rbx
0x1800057e0  sub     rsp, 20h
0x1800057e4  lea     r9, [rax+10h]; lpContext
0x1800057e8  mov     qword ptr [rax+10h], 0
0x1800057f0  lea     r8, [rax+8]; fPending
0x1800057f4  mov     dword ptr [rax+8], 0
0x1800057fb  xor     edx, edx; dwFlags
0x1800057fd  lea     rcx, ?wrapper@?1??Instance@NcdAutoSetupTelemetry@@KAPEAV2@XZ@4V?$static_lazy@VNcdAutoSetupTelemetry@@@details@wil@@A; lpInitOnce
0x180005804  call    cs:__imp_InitOnceBeginInitialize
0x18000580a  test    eax, eax
0x18000580c  jz      loc_1800058A1
0x180005812  cmp     [rsp+28h+arg_0], 0
0x180005817  jz      loc_1800058A1
0x18000581d  lea     rax, ??_7TraceLoggingProvider@wil@@6B@; const wil::TraceLoggingProvider::`vftable'
0x180005824  mov     cs:qword_18001AE50, 0
0x18000582f  lea     rbx, qword_18001AE48
0x180005836  mov     cs:qword_18001AE48, rax
0x18000583d  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_e242f0e0f0aaa7b23a4cb48cdf7e6943_@@CA@XZ; void (__cdecl *)()
0x180005844  mov     [rsp+28h+arg_8], rbx
0x180005849  mov     cs:byte_18001AE58, 0
0x180005850  mov     cs:dword_18001AE5C, 0
0x18000585a  call    atexit
0x18000585f  call    ?Provider@NcdAutoSetupLogging@@SAPEBU_tlgProvider_t@@XZ; NcdAutoSetupLogging::Provider(void)
0x180005864  mov     cs:qword_18001AE50, rax
0x18000586b  mov     rcx, rbx
0x18000586e  mov     rax, cs:qword_18001AE48
0x180005875  mov     cs:byte_18001AE58, 0
0x18000587c  mov     cs:dword_18001AE5C, 1
0x180005886  mov     rax, [rax+8]
0x18000588a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000588f  mov     r8, rbx; lpContext
0x180005892  lea     rcx, ?wrapper@?1??Instance@NcdAutoSetupTelemetry@@KAPEAV2@XZ@4V?$static_lazy@VNcdAutoSetupTelemetry@@@details@wil@@A; lpInitOnce
0x180005899  xor     edx, edx; dwFlags
0x18000589b  call    cs:__imp_InitOnceComplete
0x1800058a1  mov     rax, [rsp+28h+arg_8]
0x1800058a6  add     rsp, 20h
0x1800058aa  pop     rbx
0x1800058ab  retn
```
