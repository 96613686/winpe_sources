# [thunk]:Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Foundation::IAsyncOperationProgressHandler<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress>,Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress>>::Release`adjustor{8}' (void)

- ea: `0x18001dfd0`
- end: `0x18001dfd9`
- name: `?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@U?$IAsyncOperationProgressHandler@PEAVDeploymentResult@Deployment@Management@Windows@@UDeploymentProgress@234@@Foundation@Windows@@U?$IAsyncOperationWithProgressCompletedHandler@PEAVDeploymentResult@Deployment@Management@Windows@@UDeploymentProgress@234@@56@@Details@WRL@Microsoft@@W7EAAKXZ`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18001df60`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Foundation::IAsyncOperationProgressHandler<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress>,Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress>>::Release(
        __int64 a1)
{
  return Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Foundation::IAsyncOperationProgressHandler<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress>,Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress>>::Release((volatile signed __int32 *)(a1 - 8));
}

```

## disassembly

```asm
0x18001dfd0  sub     rcx, 8
0x18001dfd4  jmp     ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@U?$IAsyncOperationProgressHandler@PEAVDeploymentResult@Deployment@Management@Windows@@UDeploymentProgress@234@@Foundation@Windows@@U?$IAsyncOperationWithProgressCompletedHandler@PEAVDeploymentResult@Deployment@Management@Windows@@UDeploymentProgress@234@@56@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Foundation::IAsyncOperationProgressHandler<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress>,Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress>>::Release(void)
```
