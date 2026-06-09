# _SettingsCopier::LockedDesktopCopy_::_1_::dtor$1

- ea: `0x140015dcc`
- end: `0x140015dd8`
- name: `_SettingsCopier::LockedDesktopCopy_::_1_::dtor$1`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x140003944`

## pseudocode

```c
void __fastcall SettingsCopier::LockedDesktopCopy_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  ATL::CRegKey::~CRegKey((ATL::CRegKey *)(a2 + 56));
}

```

## disassembly

```asm
0x140015dcc  lea     rcx, [rdx+38h]; this
0x140015dd3  jmp     ??1CRegKey@ATL@@QEAA@XZ; ATL::CRegKey::~CRegKey(void)
```
