# LanguageComponentsInstallerTelemetry::InstallationTaskRun::~InstallationTaskRun(void)

- ea: `0x180013288`
- end: `0x1800132ad`
- name: `??1InstallationTaskRun@LanguageComponentsInstallerTelemetry@@QEAA@XZ`
- size: `37`
- prototype: `void __fastcall(LanguageComponentsInstallerTelemetry::InstallationTaskRun *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180028cba`

## callees

- `0x180012160`
- `0x180015bb8`

## pseudocode

```c
void __fastcall LanguageComponentsInstallerTelemetry::InstallationTaskRun::~InstallationTaskRun(
        LanguageComponentsInstallerTelemetry::InstallationTaskRun *this)
{
  *(_QWORD *)this = &LanguageComponentsInstallerTelemetry::InstallationTaskRun::`vftable';
  wil::ActivityBase<LanguageComponentsInstallerTelemetryProvider,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::Destroy(this);
  wil::ActivityBase<LanguageComponentsInstallerTelemetryProvider,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<LanguageComponentsInstallerTelemetryProvider,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>((__int64)this);
}

```

## disassembly

```asm
0x180013288  push    rbx
0x18001328a  sub     rsp, 20h
0x18001328e  lea     rax, ??_7InstallationTaskRun@LanguageComponentsInstallerTelemetry@@6B@; const LanguageComponentsInstallerTelemetry::InstallationTaskRun::`vftable'
0x180013295  mov     rbx, rcx
0x180013298  mov     [rcx], rax
0x18001329b  call    ?Destroy@?$ActivityBase@VLanguageComponentsInstallerTelemetryProvider@@$00$0EAAAAAAAAAAA@$04$0DAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<LanguageComponentsInstallerTelemetryProvider,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x1800132a0  mov     rcx, rbx
0x1800132a3  add     rsp, 20h
0x1800132a7  pop     rbx
0x1800132a8  jmp     ??1?$ActivityBase@VLanguageComponentsInstallerTelemetryProvider@@$00$0EAAAAAAAAAAA@$04$0DAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<LanguageComponentsInstallerTelemetryProvider,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<LanguageComponentsInstallerTelemetryProvider,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>(void)
```
