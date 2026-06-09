# _GetPackageFamilyAndFullNameForExtension_::_1_::dtor$3

- ea: `0x140011915`
- end: `0x140011921`
- name: `_GetPackageFamilyAndFullNameForExtension_::_1_::dtor$3`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140009e48`

## pseudocode

```c
__int64 __fastcall GetPackageFamilyAndFullNameForExtension_::_1_::dtor_3(__int64 a1, __int64 a2)
{
  return Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackage>::~ComPtr<Windows::Internal::StateRepository::IPackage>(a2 + 40);
}

```

## disassembly

```asm
0x140011915  lea     rcx, [rdx+28h]
0x14001191c  jmp     ??1?$ComPtr@UIPackage@StateRepository@Internal@Windows@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackage>::~ComPtr<Windows::Internal::StateRepository::IPackage>(void)
```
