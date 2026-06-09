# NetSetupTraceLogging::Provider(void)

- ea: `0x180033720`
- end: `0x18003381f`
- name: `?Provider@NetSetupTraceLogging@@SAPEBU_tlgProvider_t@@XZ`
- size: `255`
- prototype: `const struct _tlgProvider_t *(void)`
- caller_count: `57`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18000d574`
- `0x18000d694`
- `0x18000d860`
- `0x18000dd40`
- `0x18000e4c8`
- `0x180010e80`
- `0x18001368c`
- `0x18001498c`
- `0x180019890`
- `0x1800199b4`
- `0x180019fa0`
- `0x18001b25c`
- `0x180028440`
- `0x18002d4cc`
- `0x18003e218`
- `0x18003f0f8`
- `0x18003f3f4`
- `0x180046990`
- `0x180046bf0`
- `0x180046efc`
- `0x180046fb0`
- `0x180047070`
- `0x1800472d0`
- `0x180047530`
- `0x180047790`
- `0x1800479f0`
- `0x180047c48`
- `0x180047d00`
- `0x1800488a0`
- `0x1800495f0`
- `0x180049850`
- `0x180053b80`
- `0x180053f38`
- `0x1800541a4`
- `0x180054484`
- `0x1800555a8`
- `0x1800580d4`
- `0x180058188`
- `0x18005823c`
- `0x1800682d0`
- `0x1800684c0`
- `0x180068a10`
- `0x180068c70`
- `0x180068ed0`
- `0x180071c00`
- `0x180071e60`
- `0x180073610`
- `0x180073cd0`
- `0x180075650`
- `0x1800774d8`

## callees

- `0x180001008`
- `0x180033720`
- `0x180064e14`
- `0x1800810d0`
- `0x18008b010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18003380f`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18003380f`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180033753`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180033753`

## pseudocode

```c
const struct _tlgProvider_t *NetSetupTraceLogging::Provider(void)
{
  LPVOID Context; // [rsp+20h] [rbp-28h] BYREF
  WINBOOL fPending; // [rsp+28h] [rbp-20h] BYREF

  Context = 0;
  fPending = 0;
  if ( InitOnceBeginInitialize(&`NetSetupTraceLogging::Instance'::`2'::wrapper, 0, &fPending, &Context) && fPending )
  {
    qword_1800D4E80 = 0;
    Context = &qword_1800D4E78;
    byte_1800D4E88 = 0;
    dword_1800D4E8C = 0;
    qword_1800D4E78 = (__int64)&NetSetupTraceLogging::`vftable';
    CallbackContext = &`NetSetupTraceLogging::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(_lambda_17d5a69de876e4b99dd4545a5408007a_::_lambda_invoker_cdecl_);
    qword_1800D4E80 = (__int64)CallbackContext;
    byte_1800D4E88 = 1;
    TraceLoggingRegisterEx_EventRegister_EventSetInformation(CallbackContext);
    dword_1800D4E8C = 1;
    (*(void (__fastcall **)(__int64 *))(qword_1800D4E78 + 8))(&qword_1800D4E78);
    InitOnceComplete(&`NetSetupTraceLogging::Instance'::`2'::wrapper, 0, &qword_1800D4E78);
  }
  return (const struct _tlgProvider_t *)*((_QWORD *)Context + 1);
}

```

## disassembly

```asm
0x180033720  push    rdi
0x180033722  sub     rsp, 40h
0x180033726  mov     rax, cs:__security_cookie
0x18003372d  xor     rax, rsp
0x180033730  mov     [rsp+48h+var_18], rax
0x180033735  xor     edi, edi
0x180033737  lea     r9, [rsp+48h+Context]; lpContext
0x18003373c  lea     r8, [rsp+48h+fPending]; fPending
0x180033741  mov     [rsp+48h+Context], rdi
0x180033746  xor     edx, edx; dwFlags
0x180033748  mov     [rsp+48h+fPending], edi
0x18003374c  lea     rcx, ?wrapper@?1??Instance@NetSetupTraceLogging@@KAPEAV2@XZ@4V?$static_lazy@VNetSetupTraceLogging@@@details@wil@@A; lpInitOnce
0x180033753  call    cs:__imp_InitOnceBeginInitialize
0x180033759  test    eax, eax
0x18003375b  jz      short loc_180033763
0x18003375d  cmp     [rsp+48h+fPending], edi
0x180033761  jnz     short loc_18003377F
0x180033763  mov     rax, [rsp+48h+Context]
0x180033768  mov     rax, [rax+8]
0x18003376c  mov     rcx, [rsp+48h+var_18]
0x180033771  xor     rcx, rsp; StackCookie
0x180033774  call    __security_check_cookie
0x180033779  add     rsp, 40h
0x18003377d  pop     rdi
0x18003377e  retn
0x18003377f  mov     [rsp+48h+arg_0], rbx
0x180033784  lea     rax, ??_7NetSetupTraceLogging@@6B@; const NetSetupTraceLogging::`vftable'
0x18003378b  lea     rbx, qword_1800D4E78
0x180033792  mov     cs:qword_1800D4E80, rdi
0x180033799  mov     [rsp+48h+Context], rbx
0x18003379e  mov     cs:byte_1800D4E88, dil
0x1800337a5  mov     cs:dword_1800D4E8C, edi
0x1800337ab  mov     cs:qword_1800D4E78, rax
0x1800337b2  lea     rax, ?__hInner@?1???0StaticHandle@NetSetupTraceLogging@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `NetSetupTraceLogging::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x1800337b9  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_17d5a69de876e4b99dd4545a5408007a_@@CA@XZ; void (__cdecl *)()
0x1800337c0  mov     cs:CallbackContext, rax
0x1800337c7  call    atexit
0x1800337cc  mov     rcx, cs:CallbackContext; CallbackContext
0x1800337d3  mov     cs:qword_1800D4E80, rcx
0x1800337da  mov     cs:byte_1800D4E88, 1
0x1800337e1  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x1800337e6  mov     rax, cs:qword_1800D4E78
0x1800337ed  mov     rcx, rbx
0x1800337f0  mov     cs:dword_1800D4E8C, 1
0x1800337fa  mov     rax, [rax+8]
0x1800337fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033803  mov     r8, rbx; lpContext
0x180033806  lea     rcx, ?wrapper@?1??Instance@NetSetupTraceLogging@@KAPEAV2@XZ@4V?$static_lazy@VNetSetupTraceLogging@@@details@wil@@A; lpInitOnce
0x18003380d  xor     edx, edx; dwFlags
0x18003380f  call    cs:__imp_InitOnceComplete
0x180033815  mov     rbx, [rsp+48h+arg_0]
0x18003381a  jmp     loc_180033763
```
