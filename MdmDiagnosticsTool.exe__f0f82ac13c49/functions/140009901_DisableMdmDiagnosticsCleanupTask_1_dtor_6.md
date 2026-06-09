# _DisableMdmDiagnosticsCleanupTask_::_1_::dtor$6

- ea: `0x140009901`
- end: `0x14000990d`
- name: `_DisableMdmDiagnosticsCleanupTask_::_1_::dtor$6`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x140003198`

## pseudocode

```c
__int64 __fastcall DisableMdmDiagnosticsCleanupTask_::_1_::dtor_6(__int64 a1, __int64 a2)
{
  return Microsoft::WRL::ComPtr<IRegisteredTask>::~ComPtr<IRegisteredTask>(a2 + 48);
}

```

## disassembly

```asm
0x140009901  lea     rcx, [rdx+30h]
0x140009908  jmp     ??1?$ComPtr@UIRegisteredTask@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ComPtr<IRegisteredTask>::~ComPtr<IRegisteredTask>(void)
```
