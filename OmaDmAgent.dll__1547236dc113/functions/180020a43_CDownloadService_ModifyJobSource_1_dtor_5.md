# _CDownloadService::ModifyJobSource_::_1_::dtor$5

- ea: `0x180020a43`
- end: `0x180020a4f`
- name: `_CDownloadService::ModifyJobSource_::_1_::dtor$5`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x180002cec`

## pseudocode

```c
__int64 __fastcall CDownloadService::ModifyJobSource_::_1_::dtor_5(__int64 a1, __int64 a2)
{
  return std::wstring::~wstring((void **)(a2 + 184));
}

```

## disassembly

```asm
0x180020a43  lea     rcx, [rdx+0B8h]
0x180020a4a  jmp     ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
