# _DisableMdmDiagnosticsCleanupTask_::_1_::dtor$8

- ea: `0x140009f5a`
- end: `0x140009f66`
- name: `_DisableMdmDiagnosticsCleanupTask_::_1_::dtor$8`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x140003244`

## pseudocode

```c
__int64 __fastcall DisableMdmDiagnosticsCleanupTask_::_1_::dtor_8(__int64 a1, __int64 a2)
{
  return Microsoft::WRL::ComPtr<IRegisteredTask>::~ComPtr<IRegisteredTask>(a2 + 456);
}

```

## disassembly

```asm
0x140009f5a  lea     rcx, [rdx+1C8h]
0x140009f61  jmp     ??1?$ComPtr@UIRegisteredTask@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ComPtr<IRegisteredTask>::~ComPtr<IRegisteredTask>(void)
```
