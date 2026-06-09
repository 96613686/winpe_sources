# _DisableMdmDiagnosticsCleanupTask_::_1_::dtor$1

- ea: `0x1400098a7`
- end: `0x1400098b3`
- name: `_DisableMdmDiagnosticsCleanupTask_::_1_::dtor$1`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x140003198`

## pseudocode

```c
__int64 __fastcall DisableMdmDiagnosticsCleanupTask_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  return Microsoft::WRL::ComPtr<IRegisteredTask>::~ComPtr<IRegisteredTask>(a2 + 448);
}

```

## disassembly

```asm
0x1400098a7  lea     rcx, [rdx+1C0h]
0x1400098ae  jmp     ??1?$ComPtr@UIRegisteredTask@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ComPtr<IRegisteredTask>::~ComPtr<IRegisteredTask>(void)
```
