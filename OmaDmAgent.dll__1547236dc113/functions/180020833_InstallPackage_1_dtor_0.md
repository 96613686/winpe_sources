# _InstallPackage_::_1_::dtor$0

- ea: `0x180020833`
- end: `0x18002083f`
- name: `_InstallPackage_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x18000bbf8`

## pseudocode

```c
void __fastcall InstallPackage_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  _DeployJob::~_DeployJob(*(_DeployJob **)(a2 + 136));
}

```

## disassembly

```asm
0x180020833  mov     rcx, [rdx+88h]; this
0x18002083a  jmp     ??1_DeployJob@@QEAA@XZ; _DeployJob::~_DeployJob(void)
```
