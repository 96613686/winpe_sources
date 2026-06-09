# _CDownloadService::AddJob_::_1_::dtor$5

- ea: `0x18001f83f`
- end: `0x18001f84b`
- name: `_CDownloadService::AddJob_::_1_::dtor$5`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x180002cec`

## pseudocode

```c
__int64 __fastcall CDownloadService::AddJob_::_1_::dtor_5(__int64 a1, __int64 a2)
{
  return std::wstring::~wstring((void **)(a2 + 160));
}

```

## disassembly

```asm
0x18001f83f  lea     rcx, [rdx+0A0h]
0x18001f846  jmp     ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
