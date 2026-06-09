# DeploymentHelperPrivate::UpdateDeploymentTelemetry::Provider(void)

- ea: `0x18003bdfc`
- end: `0x18003bf03`
- name: `?Provider@UpdateDeploymentTelemetry@DeploymentHelperPrivate@@SAPEBU_tlgProvider_t@@XZ`
- size: `263`
- prototype: `const struct _tlgProvider_t *(void)`
- caller_count: `2`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18003c074`
- `0x18003c290`

## callees

- `0x1800016fc`
- `0x18003bdfc`
- `0x180061960`
- `0x180061d34`
- `0x180068ea0`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18003bee1`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18003bee1`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18003be35`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18003be35`

## pseudocode

```c
const struct _tlgProvider_t *DeploymentHelperPrivate::UpdateDeploymentTelemetry::Provider(void)
{
  LPVOID Context; // [rsp+20h] [rbp-28h] BYREF
  WINBOOL fPending; // [rsp+28h] [rbp-20h] BYREF

  Context = 0;
  fPending = 0;
  if ( InitOnceBeginInitialize(
         &`DeploymentHelperPrivate::UpdateDeploymentTelemetry::Instance'::`2'::wrapper,
         0,
         &fPending,
         &Context)
    && fPending )
  {
    qword_1800A29D8 = 0;
    Context = &qword_1800A29D0;
    qword_1800A29D0 = (__int64)&DeploymentHelperPrivate::UpdateDeploymentTelemetry::`vftable';
    byte_1800A29E0 = 0;
    dword_1800A29E4 = 0;
    qword_1800A29E8 = &`DeploymentHelperPrivate::UpdateDeploymentTelemetry::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(_lambda_0f3140eafb87bf272117671e6d7addf1_::_lambda_invoker_cdecl_);
    qword_1800A29D8 = (__int64)qword_1800A29E8;
    byte_1800A29E0 = 1;
    TraceLoggingRegisterEx_EventRegister_EventSetInformation(qword_1800A29E8);
    dword_1800A29E4 = 1;
    (*(void (__fastcall **)(__int64 *))(qword_1800A29D0 + 8))(&qword_1800A29D0);
    InitOnceComplete(&`DeploymentHelperPrivate::UpdateDeploymentTelemetry::Instance'::`2'::wrapper, 0, &qword_1800A29D0);
  }
  return (const struct _tlgProvider_t *)*((_QWORD *)Context + 1);
}

```

## disassembly

```asm
0x18003bdfc  push    rbx
0x18003bdfe  sub     rsp, 40h
0x18003be02  mov     rax, cs:__security_cookie
0x18003be09  xor     rax, rsp
0x18003be0c  mov     [rsp+48h+var_18], rax
0x18003be11  lea     r9, [rsp+48h+Context]; lpContext
0x18003be16  mov     [rsp+48h+Context], 0
0x18003be1f  lea     r8, [rsp+48h+fPending]; fPending
0x18003be24  mov     [rsp+48h+fPending], 0
0x18003be2c  xor     edx, edx; dwFlags
0x18003be2e  lea     rcx, ?wrapper@?1??Instance@UpdateDeploymentTelemetry@DeploymentHelperPrivate@@KAPEAV23@XZ@4V?$static_lazy@VUpdateDeploymentTelemetry@DeploymentHelperPrivate@@@details@wil@@A; lpInitOnce
0x18003be35  call    cs:__imp_InitOnceBeginInitialize
0x18003be3b  test    eax, eax
0x18003be3d  jz      loc_18003BEE7
0x18003be43  cmp     [rsp+48h+fPending], 0
0x18003be48  jz      loc_18003BEE7
0x18003be4e  lea     rbx, qword_1800A29D0
0x18003be55  mov     cs:qword_1800A29D8, 0
0x18003be60  lea     rax, ??_7UpdateDeploymentTelemetry@DeploymentHelperPrivate@@6B@; const DeploymentHelperPrivate::UpdateDeploymentTelemetry::`vftable'
0x18003be67  mov     [rsp+48h+Context], rbx
0x18003be6c  mov     cs:qword_1800A29D0, rax
0x18003be73  mov     cs:byte_1800A29E0, 0
0x18003be7a  mov     cs:dword_1800A29E4, 0
0x18003be84  lea     rax, ?__hInner@?1???0StaticHandle@UpdateDeploymentTelemetry@DeploymentHelperPrivate@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `DeploymentHelperPrivate::UpdateDeploymentTelemetry::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x18003be8b  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0f3140eafb87bf272117671e6d7addf1_@@CA@XZ; void (__cdecl *)()
0x18003be92  mov     cs:qword_1800A29E8, rax
0x18003be99  call    atexit
0x18003be9e  mov     rcx, cs:qword_1800A29E8; CallbackContext
0x18003bea5  mov     cs:qword_1800A29D8, rcx
0x18003beac  mov     cs:byte_1800A29E0, 1
0x18003beb3  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x18003beb8  mov     rax, cs:qword_1800A29D0
0x18003bebf  mov     rcx, rbx
0x18003bec2  mov     cs:dword_1800A29E4, 1
0x18003becc  mov     rax, [rax+8]
0x18003bed0  call    _guard_dispatch_icall
0x18003bed5  mov     r8, rbx; lpContext
0x18003bed8  lea     rcx, ?wrapper@?1??Instance@UpdateDeploymentTelemetry@DeploymentHelperPrivate@@KAPEAV23@XZ@4V?$static_lazy@VUpdateDeploymentTelemetry@DeploymentHelperPrivate@@@details@wil@@A; lpInitOnce
0x18003bedf  xor     edx, edx; dwFlags
0x18003bee1  call    cs:__imp_InitOnceComplete
0x18003bee7  mov     rax, [rsp+48h+Context]
0x18003beec  mov     rax, [rax+8]
0x18003bef0  mov     rcx, [rsp+48h+var_18]
0x18003bef5  xor     rcx, rsp; StackCookie
0x18003bef8  call    __security_check_cookie
0x18003befd  add     rsp, 40h
0x18003bf01  pop     rbx
0x18003bf02  retn
```
