# _CDownloadService::ModifyJobSource_::_1_::dtor$2

- ea: `0x18001fd4b`
- end: `0x18001fd57`
- name: `_CDownloadService::ModifyJobSource_::_1_::dtor$2`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x180002cec`

## pseudocode

```c
__int64 __fastcall CDownloadService::ModifyJobSource_::_1_::dtor_2(__int64 a1, __int64 a2)
{
  return std::wstring::~wstring((void **)(a2 + 120));
}

```

## disassembly

```asm
0x18001fd4b  lea     rcx, [rdx+78h]
0x18001fd52  jmp     ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
