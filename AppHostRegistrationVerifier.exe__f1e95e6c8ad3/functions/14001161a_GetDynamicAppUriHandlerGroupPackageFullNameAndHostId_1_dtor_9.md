# _GetDynamicAppUriHandlerGroupPackageFullNameAndHostId_::_1_::dtor$9

- ea: `0x14001161a`
- end: `0x140011626`
- name: `_GetDynamicAppUriHandlerGroupPackageFullNameAndHostId_::_1_::dtor$9`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x14000a374`

## pseudocode

```c
void __fastcall GetDynamicAppUriHandlerGroupPackageFullNameAndHostId_::_1_::dtor_9(__int64 a1, __int64 a2)
{
  Microsoft::WRL::Wrappers::HString::~HString((HSTRING *)(a2 + 56));
}

```

## disassembly

```asm
0x14001161a  lea     rcx, [rdx+38h]; this
0x140011621  jmp     ??1HString@Wrappers@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Wrappers::HString::~HString(void)
```
