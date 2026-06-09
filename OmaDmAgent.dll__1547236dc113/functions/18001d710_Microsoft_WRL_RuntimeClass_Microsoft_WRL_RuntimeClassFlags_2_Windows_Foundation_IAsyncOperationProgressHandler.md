# Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationProgressHandler<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress>,Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress>>::`vector deleting destructor'(uint)

- ea: `0x18001d710`
- end: `0x18001d73b`
- name: `??_E?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationProgressHandler@PEAVDeploymentResult@Deployment@Management@Windows@@UDeploymentProgress@234@@Foundation@Windows@@U?$IAsyncOperationWithProgressCompletedHandler@PEAVDeploymentResult@Deployment@Management@Windows@@UDeploymentProgress@234@@56@@WRL@Microsoft@@UEAAPEAXI@Z`
- size: `43`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x18001d710`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18001d725`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001d725`

## pseudocode

```c
_DWORD *__fastcall Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationProgressHandler<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress>,Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress>>::`vector deleting destructor'(
        _DWORD *a1,
        char a2)
{
  a1[5] = -1073741823;
  if ( (a2 & 1) != 0 )
    operator delete(a1);
  return a1;
}

```

## disassembly

```asm
0x18001d710  push    rbx
0x18001d712  sub     rsp, 20h
0x18001d716  mov     dword ptr [rcx+14h], 0C0000001h
0x18001d71d  mov     rbx, rcx
0x18001d720  test    dl, 1
0x18001d723  jz      short loc_18001D731
0x18001d725  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001d72c  nop     dword ptr [rax+rax+00h]
0x18001d731  mov     rax, rbx
0x18001d734  add     rsp, 20h
0x18001d738  pop     rbx
0x18001d739  retn
```
