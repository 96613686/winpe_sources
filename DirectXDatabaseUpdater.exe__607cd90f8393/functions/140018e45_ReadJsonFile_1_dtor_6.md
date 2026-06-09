# _ReadJsonFile_::_1_::dtor$6

- ea: `0x140018e45`
- end: `0x140018e51`
- name: `_ReadJsonFile_::_1_::dtor$6`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x140005c14`

## pseudocode

```c
__int64 __fastcall ReadJsonFile_::_1_::dtor_6(__int64 a1, __int64 a2)
{
  return std::wstring::~wstring(a2 + 400);
}

```

## disassembly

```asm
0x140018e45  lea     rcx, [rdx+190h]
0x140018e4c  jmp     ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
