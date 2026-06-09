# LanguageComponentsInstallerTelemetry::UninstallationRequest::~UninstallationRequest(void)

- ea: `0x1800249e4`
- end: `0x180024a09`
- name: `??1UninstallationRequest@LanguageComponentsInstallerTelemetry@@QEAA@XZ`
- size: `37`
- prototype: `void __fastcall(LanguageComponentsInstallerTelemetry::UninstallationRequest *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180029701`

## callees

- `0x1800248c0`
- `0x180024a10`

## pseudocode

```c
void __fastcall LanguageComponentsInstallerTelemetry::UninstallationRequest::~UninstallationRequest(
        LanguageComponentsInstallerTelemetry::UninstallationRequest *this)
{
  *(_QWORD *)this = &LanguageComponentsInstallerTelemetry::UninstallationRequest::`vftable';
  wil::ActivityBase<LanguageComponentsInstallerTelemetryProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(this);
  wil::ActivityBase<LanguageComponentsInstallerTelemetryProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<LanguageComponentsInstallerTelemetryProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>((__int64)this);
}

```

## disassembly

```asm
0x1800249e4  push    rbx
0x1800249e6  sub     rsp, 20h
0x1800249ea  lea     rax, ??_7UninstallationRequest@LanguageComponentsInstallerTelemetry@@6B@; const LanguageComponentsInstallerTelemetry::UninstallationRequest::`vftable'
0x1800249f1  mov     rbx, rcx
0x1800249f4  mov     [rcx], rax
0x1800249f7  call    ?Destroy@?$ActivityBase@VLanguageComponentsInstallerTelemetryProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<LanguageComponentsInstallerTelemetryProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x1800249fc  mov     rcx, rbx
0x1800249ff  add     rsp, 20h
0x180024a03  pop     rbx
0x180024a04  jmp     ??1?$ActivityBase@VLanguageComponentsInstallerTelemetryProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<LanguageComponentsInstallerTelemetryProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<LanguageComponentsInstallerTelemetryProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(void)
```
