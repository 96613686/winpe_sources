# _GetDynamicAppUriHandlerGroupPackageFullNameAndHostId_::_1_::dtor$7

- ea: `0x1400119a5`
- end: `0x1400119b1`
- name: `_GetDynamicAppUriHandlerGroupPackageFullNameAndHostId_::_1_::dtor$7`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x14000a374`

## pseudocode

```c
void __fastcall GetDynamicAppUriHandlerGroupPackageFullNameAndHostId_::_1_::dtor_7(__int64 a1, __int64 a2)
{
  Microsoft::WRL::Wrappers::HString::~HString((HSTRING *)(a2 + 40));
}

```

## disassembly

```asm
0x1400119a5  lea     rcx, [rdx+28h]; this
0x1400119ac  jmp     ??1HString@Wrappers@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Wrappers::HString::~HString(void)
```
