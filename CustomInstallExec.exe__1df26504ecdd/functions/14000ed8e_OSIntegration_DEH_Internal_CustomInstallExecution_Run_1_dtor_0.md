# _OSIntegration::DEH::Internal::CustomInstallExecution::Run_::_1_::dtor$0

- ea: `0x14000ed8e`
- end: `0x14000ed9a`
- name: `_OSIntegration::DEH::Internal::CustomInstallExecution::Run_::_1_::dtor$0`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x1400084f8`

## pseudocode

```c
void __fastcall OSIntegration::DEH::Internal::CustomInstallExecution::Run_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  CASTraceProvider::CustomInstallExecRun::~CustomInstallExecRun((CASTraceProvider::CustomInstallExecRun *)(a2 + 176));
}

```

## disassembly

```asm
0x14000ed8e  lea     rcx, [rdx+0B0h]; this
0x14000ed95  jmp     ??1CustomInstallExecRun@CASTraceProvider@@QEAA@XZ; CASTraceProvider::CustomInstallExecRun::~CustomInstallExecRun(void)
```
