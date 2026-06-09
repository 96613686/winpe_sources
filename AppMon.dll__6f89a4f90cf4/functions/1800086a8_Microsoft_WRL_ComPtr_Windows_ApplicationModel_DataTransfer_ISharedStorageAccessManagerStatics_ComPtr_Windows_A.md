# Microsoft::WRL::ComPtr<Windows::ApplicationModel::DataTransfer::ISharedStorageAccessManagerStatics>::~ComPtr<Windows::ApplicationModel::DataTransfer::ISharedStorageAccessManagerStatics>(void)

- ea: `0x1800086a8`
- end: `0x1800086ad`
- name: `??1?$ComPtr@UISharedStorageAccessManagerStatics@DataTransfer@ApplicationModel@Windows@@@WRL@Microsoft@@QEAA@XZ`
- size: `5`
- prototype: ``
- caller_count: `7`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000f779`
- `0x18000f7c1`
- `0x18000f7d3`
- `0x18000f7e5`
- `0x18000fb6d`
- `0x18000fb7f`
- `0x18000fba3`

## callees

- `0x1800096e0`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall Microsoft::WRL::ComPtr<Windows::ApplicationModel::DataTransfer::ISharedStorageAccessManagerStatics>::~ComPtr<Windows::ApplicationModel::DataTransfer::ISharedStorageAccessManagerStatics>(
        __int64 a1)
{
  return Microsoft::WRL::ComPtr<IDesktopAppXActivator>::InternalRelease(a1);
}

```

## disassembly

```asm
0x1800086a8  jmp     ?InternalRelease@?$ComPtr@UIDesktopAppXActivator@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDesktopAppXActivator>::InternalRelease(void)
```
