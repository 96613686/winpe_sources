# _SettingsCopier::LockedDesktopCopy_::_1_::dtor$0

- ea: `0x1400160b1`
- end: `0x1400160bd`
- name: `_SettingsCopier::LockedDesktopCopy_::_1_::dtor$0`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x140003944`

## pseudocode

```c
void __fastcall SettingsCopier::LockedDesktopCopy_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  ATL::CRegKey::~CRegKey((HKEY *)(a2 + 32));
}

```

## disassembly

```asm
0x1400160b1  lea     rcx, [rdx+20h]; this
0x1400160b8  jmp     ??1CRegKey@ATL@@QEAA@XZ; ATL::CRegKey::~CRegKey(void)
```
