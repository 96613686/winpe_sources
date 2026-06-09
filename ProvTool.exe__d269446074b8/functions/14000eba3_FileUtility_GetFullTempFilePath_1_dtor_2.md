# _FileUtility::GetFullTempFilePath_::_1_::dtor$2

- ea: `0x14000eba3`
- end: `0x14000ebaf`
- name: `_FileUtility::GetFullTempFilePath_::_1_::dtor$2`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x14000ac50`

## pseudocode

```c
void __fastcall FileUtility::GetFullTempFilePath_::_1_::dtor_2(__int64 a1, __int64 a2)
{
  expanded_wstring::~expanded_wstring((expanded_wstring *)(a2 + 96));
}

```

## disassembly

```asm
0x14000eba3  lea     rcx, [rdx+60h]; this
0x14000ebaa  jmp     ??1expanded_wstring@@QEAA@XZ; expanded_wstring::~expanded_wstring(void)
```
