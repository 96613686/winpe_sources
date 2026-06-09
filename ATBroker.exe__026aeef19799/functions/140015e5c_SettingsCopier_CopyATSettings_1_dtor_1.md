# _SettingsCopier::CopyATSettings_::_1_::dtor$1

- ea: `0x140015e5c`
- end: `0x140015e68`
- name: `_SettingsCopier::CopyATSettings_::_1_::dtor$1`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x140003944`

## pseudocode

```c
void __fastcall SettingsCopier::CopyATSettings_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  ATL::CRegKey::~CRegKey((ATL::CRegKey *)(a2 + 104));
}

```

## disassembly

```asm
0x140015e5c  lea     rcx, [rdx+68h]; this
0x140015e63  jmp     ??1CRegKey@ATL@@QEAA@XZ; ATL::CRegKey::~CRegKey(void)
```
