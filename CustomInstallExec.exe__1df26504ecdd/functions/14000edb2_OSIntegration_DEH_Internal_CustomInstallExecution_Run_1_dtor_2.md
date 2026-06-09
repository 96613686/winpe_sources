# _OSIntegration::DEH::Internal::CustomInstallExecution::Run_::_1_::dtor$2

- ea: `0x14000edb2`
- end: `0x14000edbe`
- name: `_OSIntegration::DEH::Internal::CustomInstallExecution::Run_::_1_::dtor$2`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x140008524`

## pseudocode

```c
void __fastcall OSIntegration::DEH::Internal::CustomInstallExecution::Run_::_1_::dtor_2(__int64 a1, __int64 a2)
{
  OSIntegration::DEH::Internal::CustomInstallExecution::~CustomInstallExecution((OSIntegration::DEH::Internal::CustomInstallExecution *)(a2 + 64));
}

```

## disassembly

```asm
0x14000edb2  lea     rcx, [rdx+40h]; this
0x14000edb9  jmp     ??1CustomInstallExecution@Internal@DEH@OSIntegration@@QEAA@XZ; OSIntegration::DEH::Internal::CustomInstallExecution::~CustomInstallExecution(void)
```
