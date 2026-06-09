# _JobHelper::DoInstall_::_1_::dtor$1

- ea: `0x1800202a5`
- end: `0x1800202b1`
- name: `_JobHelper::DoInstall_::_1_::dtor$1`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x180002cec`

## pseudocode

```c
__int64 __fastcall JobHelper::DoInstall_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  return std::wstring::~wstring((void **)(a2 + 136));
}

```

## disassembly

```asm
0x1800202a5  lea     rcx, [rdx+88h]
0x1800202ac  jmp     ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
