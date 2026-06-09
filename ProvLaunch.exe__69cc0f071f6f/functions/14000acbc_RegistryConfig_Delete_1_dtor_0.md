# _RegistryConfig::Delete_::_1_::dtor$0

- ea: `0x14000acbc`
- end: `0x14000acc8`
- name: `_RegistryConfig::Delete_::_1_::dtor$0`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x140007c34`

## pseudocode

```c
__int64 __fastcall RegistryConfig::Delete_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return std::wstring::~wstring(a2 + 176);
}

```

## disassembly

```asm
0x14000acbc  lea     rcx, [rdx+0B0h]
0x14000acc3  jmp     ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
