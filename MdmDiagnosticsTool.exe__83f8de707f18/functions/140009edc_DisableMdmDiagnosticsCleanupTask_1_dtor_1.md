# _DisableMdmDiagnosticsCleanupTask_::_1_::dtor$1

- ea: `0x140009edc`
- end: `0x140009ee8`
- name: `_DisableMdmDiagnosticsCleanupTask_::_1_::dtor$1`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x140003244`

## pseudocode

```c
__int64 __fastcall DisableMdmDiagnosticsCleanupTask_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  return Microsoft::WRL::ComPtr<IRegisteredTask>::~ComPtr<IRegisteredTask>(a2 + 448);
}

```

## disassembly

```asm
0x140009edc  lea     rcx, [rdx+1C0h]
0x140009ee3  jmp     ??1?$ComPtr@UIRegisteredTask@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ComPtr<IRegisteredTask>::~ComPtr<IRegisteredTask>(void)
```
