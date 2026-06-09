# LanguageComponentsInstallerTelemetry::InstallationRequest::~InstallationRequest(void)

- ea: `0x1800249b8`
- end: `0x1800249dd`
- name: `??1InstallationRequest@LanguageComponentsInstallerTelemetry@@QEAA@XZ`
- size: `37`
- prototype: `void __fastcall(LanguageComponentsInstallerTelemetry::InstallationRequest *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18002969e`

## callees

- `0x1800248c0`
- `0x180024a10`

## pseudocode

```c
void __fastcall LanguageComponentsInstallerTelemetry::InstallationRequest::~InstallationRequest(
        LanguageComponentsInstallerTelemetry::InstallationRequest *this)
{
  *(_QWORD *)this = &LanguageComponentsInstallerTelemetry::InstallationRequest::`vftable';
  wil::ActivityBase<LanguageComponentsInstallerTelemetryProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(this);
  wil::ActivityBase<LanguageComponentsInstallerTelemetryProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<LanguageComponentsInstallerTelemetryProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>((__int64)this);
}

```

## disassembly

```asm
0x1800249b8  push    rbx
0x1800249ba  sub     rsp, 20h
0x1800249be  lea     rax, ??_7InstallationRequest@LanguageComponentsInstallerTelemetry@@6B@; const LanguageComponentsInstallerTelemetry::InstallationRequest::`vftable'
0x1800249c5  mov     rbx, rcx
0x1800249c8  mov     [rcx], rax
0x1800249cb  call    ?Destroy@?$ActivityBase@VLanguageComponentsInstallerTelemetryProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<LanguageComponentsInstallerTelemetryProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x1800249d0  mov     rcx, rbx
0x1800249d3  add     rsp, 20h
0x1800249d7  pop     rbx
0x1800249d8  jmp     ??1?$ActivityBase@VLanguageComponentsInstallerTelemetryProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<LanguageComponentsInstallerTelemetryProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<LanguageComponentsInstallerTelemetryProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(void)
```
