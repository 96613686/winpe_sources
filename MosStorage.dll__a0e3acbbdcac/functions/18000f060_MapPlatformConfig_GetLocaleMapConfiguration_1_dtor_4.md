# _MapPlatformConfig::GetLocaleMapConfiguration_::_1_::dtor$4

- ea: `0x18000f060`
- end: `0x18000f06c`
- name: `_MapPlatformConfig::GetLocaleMapConfiguration_::_1_::dtor$4`
- size: `12`
- prototype: `_QWORD *__fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180006c14`

## pseudocode

```c
_QWORD *__fastcall MapPlatformConfig::GetLocaleMapConfiguration_::_1_::dtor_4(__int64 a1, __int64 a2)
{
  return Microsoft::WRL::ComPtr<ILocaleMapConfiguration>::~ComPtr<ILocaleMapConfiguration>((_QWORD *)(a2 + 72));
}

```

## disassembly

```asm
0x18000f060  lea     rcx, [rdx+48h]
0x18000f067  jmp     ??1?$ComPtr@UILocaleMapConfiguration@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ComPtr<ILocaleMapConfiguration>::~ComPtr<ILocaleMapConfiguration>(void)
```
