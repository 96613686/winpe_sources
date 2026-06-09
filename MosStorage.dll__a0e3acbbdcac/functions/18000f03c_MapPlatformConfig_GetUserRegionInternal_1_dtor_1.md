# _MapPlatformConfig::GetUserRegionInternal_::_1_::dtor$1

- ea: `0x18000f03c`
- end: `0x18000f048`
- name: `_MapPlatformConfig::GetUserRegionInternal_::_1_::dtor$1`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180006e68`

## pseudocode

```c
void __fastcall MapPlatformConfig::GetUserRegionInternal_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  Microsoft::WRL::Wrappers::HString::~HString((HSTRING *)(a2 + 48));
}

```

## disassembly

```asm
0x18000f03c  lea     rcx, [rdx+30h]; this
0x18000f043  jmp     ??1HString@Wrappers@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Wrappers::HString::~HString(void)
```
