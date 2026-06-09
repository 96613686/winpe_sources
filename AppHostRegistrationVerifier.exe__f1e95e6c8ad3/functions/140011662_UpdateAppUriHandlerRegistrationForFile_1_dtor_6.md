# _UpdateAppUriHandlerRegistrationForFile_::_1_::dtor$6

- ea: `0x140011662`
- end: `0x14001166e`
- name: `_UpdateAppUriHandlerRegistrationForFile_::_1_::dtor$6`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x140009e48`

## pseudocode

```c
__int64 __fastcall UpdateAppUriHandlerRegistrationForFile_::_1_::dtor_6(__int64 a1, __int64 a2)
{
  return Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackage>::~ComPtr<Windows::Internal::StateRepository::IPackage>(a2 + 80);
}

```

## disassembly

```asm
0x140011662  lea     rcx, [rdx+50h]
0x140011669  jmp     ??1?$ComPtr@UIPackage@StateRepository@Internal@Windows@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackage>::~ComPtr<Windows::Internal::StateRepository::IPackage>(void)
```
