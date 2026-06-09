# Microsoft::WRL::ComPtr<IRegisteredTask>::~ComPtr<IRegisteredTask>(void)

- ea: `0x140003198`
- end: `0x14000319d`
- name: `??1?$ComPtr@UIRegisteredTask@@@WRL@Microsoft@@QEAA@XZ`
- size: `5`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `3`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1400098a7`
- `0x140009901`
- `0x140009925`

## callees

- `0x1400052b4`

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
0x140003198  jmp     ?InternalRelease@?$ComPtr@UIRegisteredTask@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IRegisteredTask>::InternalRelease(void)
```
