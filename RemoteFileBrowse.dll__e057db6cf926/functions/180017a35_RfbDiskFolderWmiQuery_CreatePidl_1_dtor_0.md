# _RfbDiskFolderWmiQuery::CreatePidl_::_1_::dtor$0

- ea: `0x180017a35`
- end: `0x180017a41`
- name: `_RfbDiskFolderWmiQuery::CreatePidl_::_1_::dtor$0`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18000591c`

## pseudocode

```c
__int64 __fastcall RfbDiskFolderWmiQuery::CreatePidl_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return std::wstring::~wstring((char **)(a2 + 120));
}

```

## disassembly

```asm
0x180017a35  lea     rcx, [rdx+78h]
0x180017a3c  jmp     ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
