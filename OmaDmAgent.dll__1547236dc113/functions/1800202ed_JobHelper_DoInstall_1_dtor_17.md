# _JobHelper::DoInstall_::_1_::dtor$17

- ea: `0x1800202ed`
- end: `0x1800202f9`
- name: `_JobHelper::DoInstall_::_1_::dtor$17`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x18000bccc`

## pseudocode

```c
void __fastcall JobHelper::DoInstall_::_1_::dtor_17(__int64 a1, __int64 a2)
{
  _FrameworkDependency::~_FrameworkDependency((_FrameworkDependency *)(a2 + 480));
}

```

## disassembly

```asm
0x1800202ed  lea     rcx, [rdx+1E0h]; this
0x1800202f4  jmp     ??1_FrameworkDependency@@QEAA@XZ; _FrameworkDependency::~_FrameworkDependency(void)
```
