# _DxDbFileCompression::DecompressDatabaseFileImpl_::_1_::dtor$3

- ea: `0x140019148`
- end: `0x140019154`
- name: `_DxDbFileCompression::DecompressDatabaseFileImpl_::_1_::dtor$3`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140005c14`

## pseudocode

```c
__int64 __fastcall DxDbFileCompression::DecompressDatabaseFileImpl_::_1_::dtor_3(__int64 a1, __int64 a2)
{
  return std::wstring::~wstring(a2 + 336);
}

```

## disassembly

```asm
0x140019148  lea     rcx, [rdx+150h]
0x14001914f  jmp     ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
