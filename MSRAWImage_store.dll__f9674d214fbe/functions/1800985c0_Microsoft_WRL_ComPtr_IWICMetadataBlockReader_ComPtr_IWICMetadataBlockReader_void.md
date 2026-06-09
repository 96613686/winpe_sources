# Microsoft::WRL::ComPtr<IWICMetadataBlockReader>::~ComPtr<IWICMetadataBlockReader>(void)

- ea: `0x1800985c0`
- end: `0x1800985c5`
- name: `??1?$ComPtr@UIWICMetadataBlockReader@@@WRL@Microsoft@@QEAA@XZ`
- size: `5`
- prototype: `void(void *)`
- caller_count: `12`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800b25e4`
- `0x1800b26fc`
- `0x1800b270e`
- `0x1800b27cb`
- `0x1800b27dd`
- `0x1800b2fc8`
- `0x1800b310f`
- `0x1800b3121`
- `0x1800b3133`
- `0x1800b3157`
- `0x1800b318d`
- `0x1800b319f`

## callees

- `0x18009c44c`

## pseudocode

```c
// attributes: thunk
void __fastcall Microsoft::WRL::ComPtr<IWICMetadataBlockReader>::~ComPtr<IWICMetadataBlockReader>(__int64 *a1)
{
  Microsoft::WRL::ComPtr<IWICMetadataBlockReader>::InternalRelease(a1);
}

```

## disassembly

```asm
0x1800985c0  jmp     ?InternalRelease@?$ComPtr@UIWICMetadataBlockReader@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IWICMetadataBlockReader>::InternalRelease(void)
```
