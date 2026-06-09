# Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationProgressHandler<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress>,Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress>>::~RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationProgressHandler<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress>,Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress>>(void)

- ea: `0x18001d690`
- end: `0x18001d698`
- name: `??1?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationProgressHandler@PEAVDeploymentResult@Deployment@Management@Windows@@UDeploymentProgress@234@@Foundation@Windows@@U?$IAsyncOperationWithProgressCompletedHandler@PEAVDeploymentResult@Deployment@Management@Windows@@UDeploymentProgress@234@@56@@WRL@Microsoft@@UEAA@XZ`
- size: `8`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180020bff`

## pseudocode

```c
void __fastcall Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationProgressHandler<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress>,Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress>>::~RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationProgressHandler<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress>,Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress>>(
        __int64 a1)
{
  *(_DWORD *)(a1 + 20) = -1073741823;
}

```

## disassembly

```asm
0x18001d690  mov     dword ptr [rcx+14h], 0C0000001h
0x18001d697  retn
```
