# _CInstallService::StartDeployments_::_1_::dtor$1

- ea: `0x18002075b`
- end: `0x180020767`
- name: `_CInstallService::StartDeployments_::_1_::dtor$1`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180015004`

## pseudocode

```c
_QWORD *__fastcall CInstallService::StartDeployments_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  return Microsoft::WRL::ComPtr<DeploymentProgressHandler>::~ComPtr<DeploymentProgressHandler>((_QWORD *)(a2 + 48));
}

```

## disassembly

```asm
0x18002075b  lea     rcx, [rdx+30h]
0x180020762  jmp     ??1?$ComPtr@VDeploymentProgressHandler@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ComPtr<DeploymentProgressHandler>::~ComPtr<DeploymentProgressHandler>(void)
```
