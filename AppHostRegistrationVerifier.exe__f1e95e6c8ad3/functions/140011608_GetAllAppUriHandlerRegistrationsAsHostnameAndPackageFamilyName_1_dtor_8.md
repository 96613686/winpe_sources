# _GetAllAppUriHandlerRegistrationsAsHostnameAndPackageFamilyName_::_1_::dtor$8

- ea: `0x140011608`
- end: `0x140011614`
- name: `_GetAllAppUriHandlerRegistrationsAsHostnameAndPackageFamilyName_::_1_::dtor$8`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x14000a374`

## pseudocode

```c
void __fastcall GetAllAppUriHandlerRegistrationsAsHostnameAndPackageFamilyName_::_1_::dtor_8(__int64 a1, __int64 a2)
{
  Microsoft::WRL::Wrappers::HString::~HString((HSTRING *)(a2 + 88));
}

```

## disassembly

```asm
0x140011608  lea     rcx, [rdx+58h]; this
0x14001160f  jmp     ??1HString@Wrappers@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Wrappers::HString::~HString(void)
```
