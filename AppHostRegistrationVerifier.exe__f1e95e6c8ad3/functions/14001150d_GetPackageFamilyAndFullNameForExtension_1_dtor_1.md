# _GetPackageFamilyAndFullNameForExtension_::_1_::dtor$1

- ea: `0x14001150d`
- end: `0x140011519`
- name: `_GetPackageFamilyAndFullNameForExtension_::_1_::dtor$1`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140009e48`

## pseudocode

```c
__int64 __fastcall GetPackageFamilyAndFullNameForExtension_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  return Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackage>::~ComPtr<Windows::Internal::StateRepository::IPackage>(a2 + 32);
}

```

## disassembly

```asm
0x14001150d  lea     rcx, [rdx+20h]
0x140011514  jmp     ??1?$ComPtr@UIPackage@StateRepository@Internal@Windows@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackage>::~ComPtr<Windows::Internal::StateRepository::IPackage>(void)
```
