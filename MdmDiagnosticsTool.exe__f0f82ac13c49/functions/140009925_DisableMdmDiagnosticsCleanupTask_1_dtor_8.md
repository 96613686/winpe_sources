# _DisableMdmDiagnosticsCleanupTask_::_1_::dtor$8

- ea: `0x140009925`
- end: `0x140009931`
- name: `_DisableMdmDiagnosticsCleanupTask_::_1_::dtor$8`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x140003198`

## pseudocode

```c
__int64 __fastcall DisableMdmDiagnosticsCleanupTask_::_1_::dtor_8(__int64 a1, __int64 a2)
{
  return Microsoft::WRL::ComPtr<IRegisteredTask>::~ComPtr<IRegisteredTask>(a2 + 456);
}

```

## disassembly

```asm
0x140009925  lea     rcx, [rdx+1C8h]
0x14000992c  jmp     ??1?$ComPtr@UIRegisteredTask@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ComPtr<IRegisteredTask>::~ComPtr<IRegisteredTask>(void)
```
