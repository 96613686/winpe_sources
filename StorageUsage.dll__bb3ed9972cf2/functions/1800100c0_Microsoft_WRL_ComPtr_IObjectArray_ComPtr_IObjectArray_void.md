# Microsoft::WRL::ComPtr<IObjectArray>::~ComPtr<IObjectArray>(void)

- ea: `0x1800100c0`
- end: `0x1800100c5`
- name: `??1?$ComPtr@UIObjectArray@@@WRL@Microsoft@@QEAA@XZ`
- size: `5`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `15`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18002b256`
- `0x18002b268`
- `0x18002b27a`
- `0x18002b2d4`
- `0x18002b2e6`
- `0x18002b32e`
- `0x18002b340`
- `0x18002b364`
- `0x18002b778`
- `0x18002b78a`
- `0x18002b79c`
- `0x18002b81a`
- `0x18002b83e`
- `0x18002b850`
- `0x18002b862`

## callees

- `0x180013ae4`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall Microsoft::WRL::ComPtr<IObjectArray>::~ComPtr<IObjectArray>(__int64 a1)
{
  return Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(a1);
}

```

## disassembly

```asm
0x1800100c0  jmp     ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
```
