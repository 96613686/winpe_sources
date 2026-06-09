# _GetPackageFamilyAndFullNameForExtension_::_1_::dtor$2

- ea: `0x140011a24`
- end: `0x140011a30`
- name: `_GetPackageFamilyAndFullNameForExtension_::_1_::dtor$2`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x14000a374`

## pseudocode

```c
void __fastcall GetPackageFamilyAndFullNameForExtension_::_1_::dtor_2(__int64 a1, __int64 a2)
{
  Microsoft::WRL::Wrappers::HString::~HString((HSTRING *)(a2 + 120));
}

```

## disassembly

```asm
0x140011a24  lea     rcx, [rdx+78h]; this
0x140011a2b  jmp     ??1HString@Wrappers@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Wrappers::HString::~HString(void)
```
