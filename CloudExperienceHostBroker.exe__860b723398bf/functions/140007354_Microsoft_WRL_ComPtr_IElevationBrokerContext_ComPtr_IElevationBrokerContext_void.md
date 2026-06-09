# Microsoft::WRL::ComPtr<IElevationBrokerContext>::~ComPtr<IElevationBrokerContext>(void)

- ea: `0x140007354`
- end: `0x140007359`
- name: `??1?$ComPtr@UIElevationBrokerContext@@@WRL@Microsoft@@QEAA@XZ`
- size: `5`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1400099c7`
- `0x1400099d9`
- `0x1400099fd`

## callees

- `0x140004340`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall Microsoft::WRL::ComPtr<IElevationBrokerContext>::~ComPtr<IElevationBrokerContext>(__int64 a1)
{
  return Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(a1);
}

```

## disassembly

```asm
0x140007354  jmp     ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
```
