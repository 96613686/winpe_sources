# _CInstallService::StartDeployments_::_1_::dtor$0

- ea: `0x18002096d`
- end: `0x180020979`
- name: `_CInstallService::StartDeployments_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, installer_update`

## callees

- `0x18000bbf8`

## pseudocode

```c
void __fastcall CInstallService::StartDeployments_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  _DeployJob::~_DeployJob((_DeployJob *)(a2 + 272));
}

```

## disassembly

```asm
0x18002096d  lea     rcx, [rdx+110h]; this
0x180020974  jmp     ??1_DeployJob@@QEAA@XZ; _DeployJob::~_DeployJob(void)
```
