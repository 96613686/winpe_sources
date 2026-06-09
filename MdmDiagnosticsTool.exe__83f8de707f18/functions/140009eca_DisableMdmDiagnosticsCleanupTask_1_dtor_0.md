# _DisableMdmDiagnosticsCleanupTask_::_1_::dtor$0

- ea: `0x140009eca`
- end: `0x140009ed6`
- name: `_DisableMdmDiagnosticsCleanupTask_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x1400034d8`

## pseudocode

```c
void __fastcall DisableMdmDiagnosticsCleanupTask_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  AutoCoInitialize::~AutoCoInitialize((AutoCoInitialize *)(a2 + 432));
}

```

## disassembly

```asm
0x140009eca  lea     rcx, [rdx+1B0h]; this
0x140009ed1  jmp     ??1AutoCoInitialize@@QEAA@XZ; AutoCoInitialize::~AutoCoInitialize(void)
```
