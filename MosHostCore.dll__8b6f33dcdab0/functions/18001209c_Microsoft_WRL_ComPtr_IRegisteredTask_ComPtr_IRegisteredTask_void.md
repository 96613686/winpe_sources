# Microsoft::WRL::ComPtr<IRegisteredTask>::~ComPtr<IRegisteredTask>(void)

- ea: `0x18001209c`
- end: `0x1800120a1`
- name: `??1?$ComPtr@UIRegisteredTask@@@WRL@Microsoft@@QEAA@XZ`
- size: `5`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `9`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180023c26`
- `0x180023cbd`
- `0x180023d29`
- `0x180023d3b`
- `0x180023d4d`
- `0x180023e01`
- `0x180023e13`
- `0x180023e25`
- `0x180023f8d`

## callees

- `0x1800171d0`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall Microsoft::WRL::ComPtr<IRegisteredTask>::~ComPtr<IRegisteredTask>(__int64 a1)
{
  return Microsoft::WRL::ComPtr<IClientProxyResolver>::InternalRelease(a1);
}

```

## disassembly

```asm
0x18001209c  jmp     ?InternalRelease@?$ComPtr@UIClientProxyResolver@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IClientProxyResolver>::InternalRelease(void)
```
