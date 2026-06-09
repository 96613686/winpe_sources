# std::multimap<uint,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<uint>,std::allocator<std::pair<uint const,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>>>::~multimap<uint,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<uint>,std::allocator<std::pair<uint const,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>>>(void)

- ea: `0x18000130c`
- end: `0x180001311`
- name: `??1?$multimap@IV?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@U?$less@I@std@@V?$allocator@U?$pair@$$CBIV?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@std@@@5@@std@@QEAA@XZ`
- size: `5`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180022cb2`
- `0x180022cc8`

## callees

- `0x180001f74`

## pseudocode

```c
// attributes: thunk
void __fastcall std::multimap<unsigned int,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>::~multimap<unsigned int,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>(
        __int64 a1)
{
  std::_Tree<std::_Tmap_traits<enum DX_FEATURE_LEVEL,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<enum DX_FEATURE_LEVEL>,std::allocator<std::pair<enum DX_FEATURE_LEVEL const,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>>,1>>::~_Tree<std::_Tmap_traits<enum DX_FEATURE_LEVEL,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<enum DX_FEATURE_LEVEL>,std::allocator<std::pair<enum DX_FEATURE_LEVEL const,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>>,1>>(a1);
}

```

## disassembly

```asm
0x18000130c  jmp     ??1?$_Tree@V?$_Tmap_traits@W4DX_FEATURE_LEVEL@@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@U?$less@W4DX_FEATURE_LEVEL@@@std@@V?$allocator@U?$pair@$$CBW4DX_FEATURE_LEVEL@@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@std@@@6@$00@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<DX_FEATURE_LEVEL,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<DX_FEATURE_LEVEL>,std::allocator<std::pair<DX_FEATURE_LEVEL const,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>>,1>>::~_Tree<std::_Tmap_traits<DX_FEATURE_LEVEL,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<DX_FEATURE_LEVEL>,std::allocator<std::pair<DX_FEATURE_LEVEL const,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>>,1>>(void)
```
