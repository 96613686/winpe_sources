# _InstallPackage_::_1_::dtor$10

- ea: `0x18002037d`
- end: `0x180020389`
- name: `_InstallPackage_::_1_::dtor$10`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x180002cec`

## pseudocode

```c
__int64 __fastcall InstallPackage_::_1_::dtor_10(__int64 a1, __int64 a2)
{
  return std::wstring::~wstring((void **)(a2 + 176));
}

```

## disassembly

```asm
0x18002037d  lea     rcx, [rdx+0B0h]
0x180020384  jmp     ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
