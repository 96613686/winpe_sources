# Microsoft::WRL::ComPtr<IEnumNetworkSignaturePrivate>::~ComPtr<IEnumNetworkSignaturePrivate>(void)

- ea: `0x180011594`
- end: `0x180011599`
- name: `??1?$ComPtr@UIEnumNetworkSignaturePrivate@@@WRL@Microsoft@@QEAA@XZ`
- size: `5`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `11`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18003dd60`
- `0x18003dde0`
- `0x18003de00`
- `0x18003de20`
- `0x18003ecef`
- `0x18003f0ae`
- `0x18003f0c0`
- `0x18003f369`
- `0x18003fe9e`
- `0x18003fed4`
- `0x18003fef8`

## callees

- `0x180006b88`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
// attributes: thunk
__int64 __fastcall Microsoft::WRL::ComPtr<IEnumNetworkSignaturePrivate>::~ComPtr<IEnumNetworkSignaturePrivate>(
        __int64 a1)
{
  return Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(a1);
}

```

## disassembly

```asm
0x180011594  jmp     ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
```
