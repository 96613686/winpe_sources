# _DisableMdmDiagnosticsCleanupTask_::_1_::dtor$6

- ea: `0x140009f36`
- end: `0x140009f42`
- name: `_DisableMdmDiagnosticsCleanupTask_::_1_::dtor$6`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x140003244`

## pseudocode

```c
__int64 __fastcall DisableMdmDiagnosticsCleanupTask_::_1_::dtor_6(__int64 a1, __int64 a2)
{
  return Microsoft::WRL::ComPtr<IRegisteredTask>::~ComPtr<IRegisteredTask>(a2 + 48);
}

```

## disassembly

```asm
0x140009f36  lea     rcx, [rdx+30h]
0x140009f3d  jmp     ??1?$ComPtr@UIRegisteredTask@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ComPtr<IRegisteredTask>::~ComPtr<IRegisteredTask>(void)
```
