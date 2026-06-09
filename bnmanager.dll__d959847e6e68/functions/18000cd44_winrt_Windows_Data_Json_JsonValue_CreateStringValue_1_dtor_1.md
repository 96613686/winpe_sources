# _winrt::Windows::Data::Json::JsonValue::CreateStringValue_::_1_::dtor$1

- ea: `0x18000cd44`
- end: `0x18000cd50`
- name: `_winrt::Windows::Data::Json::JsonValue::CreateStringValue_::_1_::dtor$1`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x1800057b4`

## pseudocode

```c
void __fastcall winrt::Windows::Data::Json::JsonValue::CreateStringValue_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  winrt::impl::factory_count_guard::~factory_count_guard((volatile signed __int64 **)(a2 + 96));
}

```

## disassembly

```asm
0x18000cd44  lea     rcx, [rdx+60h]; this
0x18000cd4b  jmp     ??1factory_count_guard@impl@winrt@@QEAA@XZ; winrt::impl::factory_count_guard::~factory_count_guard(void)
```
