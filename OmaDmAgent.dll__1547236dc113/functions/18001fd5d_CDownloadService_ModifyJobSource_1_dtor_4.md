# _CDownloadService::ModifyJobSource_::_1_::dtor$4

- ea: `0x18001fd5d`
- end: `0x18001fd69`
- name: `_CDownloadService::ModifyJobSource_::_1_::dtor$4`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x180002cec`

## pseudocode

```c
__int64 __fastcall CDownloadService::ModifyJobSource_::_1_::dtor_4(__int64 a1, __int64 a2)
{
  return std::wstring::~wstring((void **)(a2 + 56));
}

```

## disassembly

```asm
0x18001fd5d  lea     rcx, [rdx+38h]
0x18001fd64  jmp     ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
