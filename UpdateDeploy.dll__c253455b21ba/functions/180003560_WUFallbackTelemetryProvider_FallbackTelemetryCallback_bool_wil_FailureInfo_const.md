# WUFallbackTelemetryProvider::FallbackTelemetryCallback(bool,wil::FailureInfo const &)

- ea: `0x180003560`
- end: `0x18000368a`
- name: `?FallbackTelemetryCallback@WUFallbackTelemetryProvider@@SAX_NAEBUFailureInfo@wil@@@Z`
- size: `298`
- prototype: `void __fastcall(bool, const struct wil::FailureInfo *)`
- caller_count: `0`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1800016fc`
- `0x180003560`
- `0x180061960`
- `0x180061d34`
- `0x180068ea0`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180003651`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180003651`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1800035a5`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1800035a5`

## pseudocode

```c
void __fastcall WUFallbackTelemetryProvider::FallbackTelemetryCallback(char a1, const struct wil::FailureInfo *a2)
{
  __int64 v4; // rdx
  __int64 *v5; // [rsp+20h] [rbp-28h] BYREF
  WINBOOL v6; // [rsp+28h] [rbp-20h] BYREF

  v5 = 0;
  v6 = 0;
  if ( InitOnceBeginInitialize(&`WUFallbackTelemetryProvider::Instance'::`2'::wrapper, 0, &v6, (LPVOID *)&v5) && v6 )
  {
    qword_1800A2690 = 0;
    v5 = &qword_1800A2688;
    qword_1800A2688 = (__int64)&DeploymentHelperPrivate::UpdateDeploymentTelemetry::`vftable';
    byte_1800A2698 = 0;
    dword_1800A269C = 0;
    CallbackContext = &`WUFallbackTelemetryProvider::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(_lambda_381b80c70d062aa1595caf08c84bdedd_::_lambda_invoker_cdecl_);
    qword_1800A2690 = (__int64)CallbackContext;
    byte_1800A2698 = 1;
    TraceLoggingRegisterEx_EventRegister_EventSetInformation(CallbackContext);
    dword_1800A269C = 1;
    (*(void (__fastcall **)(__int64 *))(qword_1800A2688 + 8))(&qword_1800A2688);
    InitOnceComplete(&`WUFallbackTelemetryProvider::Instance'::`2'::wrapper, 0, &qword_1800A2688);
  }
  LOBYTE(v4) = a1;
  (*(void (__fastcall **)(__int64 *, __int64, const struct wil::FailureInfo *))(*v5 + 16))(v5, v4, a2);
}

```

## disassembly

```asm
0x180003560  mov     r11, rsp
0x180003563  mov     [r11+18h], rbx
0x180003567  mov     [r11+20h], rsi
0x18000356b  push    rdi
0x18000356c  sub     rsp, 40h
0x180003570  mov     rax, cs:__security_cookie
0x180003577  xor     rax, rsp
0x18000357a  mov     [rsp+48h+var_18], rax
0x18000357f  mov     rdi, rdx
0x180003582  mov     qword ptr [r11-28h], 0
0x18000358a  mov     bl, cl
0x18000358c  mov     [rsp+48h+var_20], 0
0x180003594  xor     edx, edx; dwFlags
0x180003596  lea     rcx, ?wrapper@?1??Instance@WUFallbackTelemetryProvider@@KAPEAV2@XZ@4V?$static_lazy@VWUFallbackTelemetryProvider@@@details@wil@@A; lpInitOnce
0x18000359d  lea     r9, [r11-28h]; lpContext
0x1800035a1  lea     r8, [r11-20h]; fPending
0x1800035a5  call    cs:__imp_InitOnceBeginInitialize
0x1800035ab  test    eax, eax
0x1800035ad  jz      loc_180003657
0x1800035b3  cmp     [rsp+48h+var_20], 0
0x1800035b8  jz      loc_180003657
0x1800035be  lea     rsi, qword_1800A2688
0x1800035c5  mov     cs:qword_1800A2690, 0
0x1800035d0  lea     rax, ??_7UpdateDeploymentTelemetry@DeploymentHelperPrivate@@6B@; const DeploymentHelperPrivate::UpdateDeploymentTelemetry::`vftable'
0x1800035d7  mov     [rsp+48h+var_28], rsi
0x1800035dc  mov     cs:qword_1800A2688, rax
0x1800035e3  mov     cs:byte_1800A2698, 0
0x1800035ea  mov     cs:dword_1800A269C, 0
0x1800035f4  lea     rax, ?__hInner@?1???0StaticHandle@WUFallbackTelemetryProvider@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `WUFallbackTelemetryProvider::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x1800035fb  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_381b80c70d062aa1595caf08c84bdedd_@@CA@XZ; void (__cdecl *)()
0x180003602  mov     cs:CallbackContext, rax
0x180003609  call    atexit
0x18000360e  mov     rcx, cs:CallbackContext; CallbackContext
0x180003615  mov     cs:qword_1800A2690, rcx
0x18000361c  mov     cs:byte_1800A2698, 1
0x180003623  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x180003628  mov     rax, cs:qword_1800A2688
0x18000362f  mov     rcx, rsi
0x180003632  mov     cs:dword_1800A269C, 1
0x18000363c  mov     rax, [rax+8]
0x180003640  call    _guard_dispatch_icall
0x180003645  mov     r8, rsi; lpContext
0x180003648  lea     rcx, ?wrapper@?1??Instance@WUFallbackTelemetryProvider@@KAPEAV2@XZ@4V?$static_lazy@VWUFallbackTelemetryProvider@@@details@wil@@A; lpInitOnce
0x18000364f  xor     edx, edx; dwFlags
0x180003651  call    cs:__imp_InitOnceComplete
0x180003657  mov     rcx, [rsp+48h+var_28]
0x18000365c  mov     r8, rdi
0x18000365f  mov     dl, bl
0x180003661  mov     rax, [rcx]
0x180003664  mov     rax, [rax+10h]
0x180003668  call    _guard_dispatch_icall
0x18000366d  mov     rcx, [rsp+48h+var_18]
0x180003672  xor     rcx, rsp; StackCookie
0x180003675  call    __security_check_cookie
0x18000367a  mov     rbx, [rsp+48h+arg_10]
0x18000367f  mov     rsi, [rsp+48h+arg_18]
0x180003684  add     rsp, 40h
0x180003688  pop     rdi
0x180003689  retn
```
