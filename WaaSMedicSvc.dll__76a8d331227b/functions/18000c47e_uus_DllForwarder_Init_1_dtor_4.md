# _uus::DllForwarder::_Init_::_1_::dtor$4

- ea: `0x18000c47e`
- end: `0x18000c48a`
- name: `_uus::DllForwarder::_Init_::_1_::dtor$4`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180008f20`

## pseudocode

```c
__int64 __fastcall uus::DllForwarder::_Init_::_1_::dtor_4(__int64 a1, __int64 a2)
{
  return std::wstring::~wstring((char **)(a2 + 56));
}

```

## disassembly

```asm
0x18000c47e  lea     rcx, [rdx+38h]
0x18000c485  jmp     ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
