# _ON_CREATE_PROC_DATA::ON_CREATE_PROC_DATA_::_1_::dtor$7

- ea: `0x18000c5e1`
- end: `0x18000c5ed`
- name: `_ON_CREATE_PROC_DATA::ON_CREATE_PROC_DATA_::_1_::dtor$7`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1800060c4`

## pseudocode

```c
__int64 __fastcall ON_CREATE_PROC_DATA::ON_CREATE_PROC_DATA_::_1_::dtor_7(__int64 a1, __int64 a2)
{
  return std::wstring::~wstring(a2 + 72);
}

```

## disassembly

```asm
0x18000c5e1  lea     rcx, [rdx+48h]
0x18000c5e8  jmp     ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
