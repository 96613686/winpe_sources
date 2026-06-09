# _JobHelper::DoInstall_::_1_::dtor$16

- ea: `0x1800202db`
- end: `0x1800202e7`
- name: `_JobHelper::DoInstall_::_1_::dtor$16`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x18000bbf8`

## pseudocode

```c
void __fastcall JobHelper::DoInstall_::_1_::dtor_16(__int64 a1, __int64 a2)
{
  _DeployJob::~_DeployJob((_DeployJob *)(a2 + 352));
}

```

## disassembly

```asm
0x1800202db  lea     rcx, [rdx+160h]; this
0x1800202e2  jmp     ??1_DeployJob@@QEAA@XZ; _DeployJob::~_DeployJob(void)
```
