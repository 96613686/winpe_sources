# LanguageComponentsInstallerTelemetry::UninstallationTaskRun::~UninstallationTaskRun(void)

- ea: `0x180013514`
- end: `0x180013539`
- name: `??1UninstallationTaskRun@LanguageComponentsInstallerTelemetry@@QEAA@XZ`
- size: `37`
- prototype: `void __fastcall(LanguageComponentsInstallerTelemetry::UninstallationTaskRun *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180028dd8`

## callees

- `0x180012160`
- `0x180015bb8`

## pseudocode

```c
void __fastcall LanguageComponentsInstallerTelemetry::UninstallationTaskRun::~UninstallationTaskRun(
        LanguageComponentsInstallerTelemetry::UninstallationTaskRun *this)
{
  *(_QWORD *)this = &LanguageComponentsInstallerTelemetry::UninstallationTaskRun::`vftable';
  wil::ActivityBase<LanguageComponentsInstallerTelemetryProvider,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::Destroy(this);
  wil::ActivityBase<LanguageComponentsInstallerTelemetryProvider,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<LanguageComponentsInstallerTelemetryProvider,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>((__int64)this);
}

```

## disassembly

```asm
0x180013514  push    rbx
0x180013516  sub     rsp, 20h
0x18001351a  lea     rax, ??_7UninstallationTaskRun@LanguageComponentsInstallerTelemetry@@6B@; const LanguageComponentsInstallerTelemetry::UninstallationTaskRun::`vftable'
0x180013521  mov     rbx, rcx
0x180013524  mov     [rcx], rax
0x180013527  call    ?Destroy@?$ActivityBase@VLanguageComponentsInstallerTelemetryProvider@@$00$0EAAAAAAAAAAA@$04$0DAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<LanguageComponentsInstallerTelemetryProvider,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x18001352c  mov     rcx, rbx
0x18001352f  add     rsp, 20h
0x180013533  pop     rbx
0x180013534  jmp     ??1?$ActivityBase@VLanguageComponentsInstallerTelemetryProvider@@$00$0EAAAAAAAAAAA@$04$0DAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<LanguageComponentsInstallerTelemetryProvider,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<LanguageComponentsInstallerTelemetryProvider,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>(void)
```
