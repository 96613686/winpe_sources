# _dynamic_atexit_destructor_for__OSIntegration::DEH::Internal::SRStatics::s_customInstallWorkStatics__

- ea: `0x14000eeb0`
- end: `0x14000eebc`
- name: `_dynamic_atexit_destructor_for__OSIntegration::DEH::Internal::SRStatics::s_customInstallWorkStatics__`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1400098dc`

## pseudocode

```c
__int64 dynamic_atexit_destructor_for__OSIntegration::DEH::Internal::SRStatics::s_customInstallWorkStatics__()
{
  return Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackageLocationStatics>::InternalRelease(&OSIntegration::DEH::Internal::SRStatics::s_customInstallWorkStatics);
}

```

## disassembly

```asm
0x14000eeb0  lea     rcx, ?s_customInstallWorkStatics@SRStatics@Internal@DEH@OSIntegration@@1V?$ComPtr@UICustomInstallWorkStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@A; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::ICustomInstallWorkStatics> OSIntegration::DEH::Internal::SRStatics::s_customInstallWorkStatics
0x14000eeb7  jmp     ?InternalRelease@?$ComPtr@UIPackageLocationStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackageLocationStatics>::InternalRelease(void)
```
