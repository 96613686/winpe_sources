# Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo2>::~ComPtr<IAppxBundleManifestPackageInfo2>(void)

- ea: `0x180001244`
- end: `0x180001249`
- name: `??1?$ComPtr@UIAppxBundleManifestPackageInfo2@@@WRL@Microsoft@@QEAA@XZ`
- size: `5`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800229a0`
- `0x1800229c0`

## callees

- `0x180001250`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo2>::~ComPtr<IAppxBundleManifestPackageInfo2>(
        __int64 *a1)
{
  return Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo2>::InternalRelease(a1);
}

```

## disassembly

```asm
0x180001244  jmp     ?InternalRelease@?$ComPtr@UIAppxBundleManifestPackageInfo2@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo2>::InternalRelease(void)
```
