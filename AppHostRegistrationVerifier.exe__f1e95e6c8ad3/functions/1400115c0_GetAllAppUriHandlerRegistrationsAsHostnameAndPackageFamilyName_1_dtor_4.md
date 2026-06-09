# _GetAllAppUriHandlerRegistrationsAsHostnameAndPackageFamilyName_::_1_::dtor$4

- ea: `0x1400115c0`
- end: `0x1400115cc`
- name: `_GetAllAppUriHandlerRegistrationsAsHostnameAndPackageFamilyName_::_1_::dtor$4`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140009e48`

## pseudocode

```c
__int64 __fastcall GetAllAppUriHandlerRegistrationsAsHostnameAndPackageFamilyName_::_1_::dtor_4(__int64 a1, __int64 a2)
{
  return Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackage>::~ComPtr<Windows::Internal::StateRepository::IPackage>(a2 + 128);
}

```

## disassembly

```asm
0x1400115c0  lea     rcx, [rdx+80h]
0x1400115c7  jmp     ??1?$ComPtr@UIPackage@StateRepository@Internal@Windows@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackage>::~ComPtr<Windows::Internal::StateRepository::IPackage>(void)
```
