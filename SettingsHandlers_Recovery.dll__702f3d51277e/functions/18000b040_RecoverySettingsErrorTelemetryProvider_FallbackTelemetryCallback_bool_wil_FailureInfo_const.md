# RecoverySettingsErrorTelemetryProvider::FallbackTelemetryCallback(bool,wil::FailureInfo const &)

- ea: `0x18000b040`
- end: `0x18000b14f`
- name: `?FallbackTelemetryCallback@RecoverySettingsErrorTelemetryProvider@@SAX_NAEBUFailureInfo@wil@@@Z`
- size: `271`
- prototype: `void __fastcall(bool, const struct wil::FailureInfo *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800015b4`
- `0x180002800`
- `0x18000b040`
- `0x18002b010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000b122`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000b122`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18000b076`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18000b076`

## pseudocode

```c
void __fastcall RecoverySettingsErrorTelemetryProvider::FallbackTelemetryCallback(
        char a1,
        const struct wil::FailureInfo *a2)
{
  __int64 v4; // rdx
  WINBOOL v5; // [rsp+40h] [rbp+18h] BYREF
  __int64 *v6; // [rsp+48h] [rbp+20h] BYREF

  v6 = 0;
  v5 = 0;
  if ( InitOnceBeginInitialize(&`RecoverySettingsErrorTelemetryProvider::Instance'::`2'::wrapper, 0, &v5, (LPVOID *)&v6)
    && v5 )
  {
    qword_18005A030 = 0;
    v6 = &qword_18005A028;
    qword_18005A028 = (__int64)&RecoverySettingsErrorTelemetryProvider::`vftable';
    byte_18005A038 = 0;
    dword_18005A03C = 0;
    CallbackContext = &`RecoverySettingsErrorTelemetryProvider::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(_lambda_bfe8e9a5a6d50dd2e02556d79c25ff78_::_lambda_invoker_cdecl_);
    qword_18005A030 = (__int64)CallbackContext;
    byte_18005A038 = 1;
    TraceLoggingRegisterEx_EventRegister_EventSetInformation(CallbackContext);
    dword_18005A03C = 1;
    (*(void (__fastcall **)(__int64 *))(qword_18005A028 + 8))(&qword_18005A028);
    InitOnceComplete(&`RecoverySettingsErrorTelemetryProvider::Instance'::`2'::wrapper, 0, &qword_18005A028);
  }
  LOBYTE(v4) = a1;
  (*(void (__fastcall **)(__int64 *, __int64, const struct wil::FailureInfo *))(*v6 + 16))(v6, v4, a2);
}

```

## disassembly

```asm
0x18000b040  mov     rax, rsp
0x18000b043  mov     [rax+8], rbx
0x18000b047  mov     [rax+10h], rsi
0x18000b04b  push    rdi
0x18000b04c  sub     rsp, 20h
0x18000b050  mov     rbx, rdx
0x18000b053  mov     qword ptr [rax+20h], 0
0x18000b05b  mov     dil, cl
0x18000b05e  mov     dword ptr [rax+18h], 0
0x18000b065  xor     edx, edx; dwFlags
0x18000b067  lea     rcx, ?wrapper@?1??Instance@RecoverySettingsErrorTelemetryProvider@@KAPEAV2@XZ@4V?$static_lazy@VRecoverySettingsErrorTelemetryProvider@@@details@wil@@A; lpInitOnce
0x18000b06e  lea     r9, [rax+20h]; lpContext
0x18000b072  lea     r8, [rax+18h]; fPending
0x18000b076  call    cs:__imp_InitOnceBeginInitialize
0x18000b07c  test    eax, eax
0x18000b07e  jz      loc_18000B128
0x18000b084  cmp     [rsp+28h+arg_10], 0
0x18000b089  jz      loc_18000B128
0x18000b08f  lea     rsi, qword_18005A028
0x18000b096  mov     cs:qword_18005A030, 0
0x18000b0a1  lea     rax, ??_7RecoverySettingsErrorTelemetryProvider@@6B@; const RecoverySettingsErrorTelemetryProvider::`vftable'
0x18000b0a8  mov     [rsp+28h+arg_18], rsi
0x18000b0ad  mov     cs:qword_18005A028, rax
0x18000b0b4  mov     cs:byte_18005A038, 0
0x18000b0bb  mov     cs:dword_18005A03C, 0
0x18000b0c5  lea     rax, ?__hInner@?1???0StaticHandle@RecoverySettingsErrorTelemetryProvider@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `RecoverySettingsErrorTelemetryProvider::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x18000b0cc  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_bfe8e9a5a6d50dd2e02556d79c25ff78_@@CA@XZ; void (__cdecl *)()
0x18000b0d3  mov     cs:CallbackContext, rax
0x18000b0da  call    atexit
0x18000b0df  mov     rcx, cs:CallbackContext; CallbackContext
0x18000b0e6  mov     cs:qword_18005A030, rcx
0x18000b0ed  mov     cs:byte_18005A038, 1
0x18000b0f4  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x18000b0f9  mov     rax, cs:qword_18005A028
0x18000b100  mov     rcx, rsi
0x18000b103  mov     cs:dword_18005A03C, 1
0x18000b10d  mov     rax, [rax+8]
0x18000b111  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b116  mov     r8, rsi; lpContext
0x18000b119  lea     rcx, ?wrapper@?1??Instance@RecoverySettingsErrorTelemetryProvider@@KAPEAV2@XZ@4V?$static_lazy@VRecoverySettingsErrorTelemetryProvider@@@details@wil@@A; lpInitOnce
0x18000b120  xor     edx, edx; dwFlags
0x18000b122  call    cs:__imp_InitOnceComplete
0x18000b128  mov     rcx, [rsp+28h+arg_18]
0x18000b12d  mov     r8, rbx
0x18000b130  mov     dl, dil
0x18000b133  mov     rax, [rcx]
0x18000b136  mov     rax, [rax+10h]
0x18000b13a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b13f  mov     rbx, [rsp+28h+arg_0]
0x18000b144  mov     rsi, [rsp+28h+arg_8]
0x18000b149  add     rsp, 20h
0x18000b14d  pop     rdi
0x18000b14e  retn
```
