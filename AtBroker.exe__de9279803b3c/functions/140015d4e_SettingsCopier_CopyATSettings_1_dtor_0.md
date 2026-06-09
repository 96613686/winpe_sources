# _SettingsCopier::CopyATSettings_::_1_::dtor$0

- ea: `0x140015d4e`
- end: `0x140015d5a`
- name: `_SettingsCopier::CopyATSettings_::_1_::dtor$0`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x140003944`

## pseudocode

```c
void __fastcall SettingsCopier::CopyATSettings_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  ATL::CRegKey::~CRegKey((HKEY *)(a2 + 80));
}

```

## disassembly

```asm
0x140015d4e  lea     rcx, [rdx+50h]; this
0x140015d55  jmp     ??1CRegKey@ATL@@QEAA@XZ; ATL::CRegKey::~CRegKey(void)
```
