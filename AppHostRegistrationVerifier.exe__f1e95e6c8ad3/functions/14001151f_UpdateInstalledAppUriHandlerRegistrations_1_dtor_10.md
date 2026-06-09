# _UpdateInstalledAppUriHandlerRegistrations_::_1_::dtor$10

- ea: `0x14001151f`
- end: `0x14001152b`
- name: `_UpdateInstalledAppUriHandlerRegistrations_::_1_::dtor$10`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x140009e48`

## pseudocode

```c
__int64 __fastcall UpdateInstalledAppUriHandlerRegistrations_::_1_::dtor_10(__int64 a1, __int64 a2)
{
  return Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackage>::~ComPtr<Windows::Internal::StateRepository::IPackage>(a2 + 104);
}

```

## disassembly

```asm
0x14001151f  lea     rcx, [rdx+68h]
0x140011526  jmp     ??1?$ComPtr@UIPackage@StateRepository@Internal@Windows@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackage>::~ComPtr<Windows::Internal::StateRepository::IPackage>(void)
```
