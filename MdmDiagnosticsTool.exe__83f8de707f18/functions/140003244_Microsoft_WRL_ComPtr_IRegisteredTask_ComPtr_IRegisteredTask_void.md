# Microsoft::WRL::ComPtr<IRegisteredTask>::~ComPtr<IRegisteredTask>(void)

- ea: `0x140003244`
- end: `0x140003249`
- name: `??1?$ComPtr@UIRegisteredTask@@@WRL@Microsoft@@QEAA@XZ`
- size: `5`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x140009edc`
- `0x140009f36`
- `0x140009f5a`

## callees

- `0x140005588`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall Microsoft::WRL::ComPtr<IRegisteredTask>::~ComPtr<IRegisteredTask>(__int64 a1)
{
  return Microsoft::WRL::ComPtr<IRegisteredTask>::InternalRelease(a1);
}

```

## disassembly

```asm
0x140003244  jmp     ?InternalRelease@?$ComPtr@UIRegisteredTask@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IRegisteredTask>::InternalRelease(void)
```
