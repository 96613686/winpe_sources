# _MapPlatformConfig::GetUserRegionInternal_::_1_::dtor$0

- ea: `0x18000f072`
- end: `0x18000f07e`
- name: `_MapPlatformConfig::GetUserRegionInternal_::_1_::dtor$0`
- size: `12`
- prototype: `_QWORD *__fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180006c14`

## pseudocode

```c
_QWORD *__fastcall MapPlatformConfig::GetUserRegionInternal_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return Microsoft::WRL::ComPtr<ILocaleMapConfiguration>::~ComPtr<ILocaleMapConfiguration>((_QWORD *)(a2 + 32));
}

```

## disassembly

```asm
0x18000f072  lea     rcx, [rdx+20h]
0x18000f079  jmp     ??1?$ComPtr@UILocaleMapConfiguration@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ComPtr<ILocaleMapConfiguration>::~ComPtr<ILocaleMapConfiguration>(void)
```
