# _DisableMdmDiagnosticsCleanupTask_::_1_::dtor$0

- ea: `0x140009895`
- end: `0x1400098a1`
- name: `_DisableMdmDiagnosticsCleanupTask_::_1_::dtor$0`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x140003470`

## pseudocode

```c
void __fastcall DisableMdmDiagnosticsCleanupTask_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  AutoCoInitialize::~AutoCoInitialize((AutoCoInitialize *)(a2 + 432));
}

```

## disassembly

```asm
0x140009895  lea     rcx, [rdx+1B0h]; this
0x14000989c  jmp     ??1AutoCoInitialize@@QEAA@XZ; AutoCoInitialize::~AutoCoInitialize(void)
```
