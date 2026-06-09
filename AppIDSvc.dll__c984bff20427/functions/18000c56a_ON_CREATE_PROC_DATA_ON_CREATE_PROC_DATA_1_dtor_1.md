# _ON_CREATE_PROC_DATA::ON_CREATE_PROC_DATA_::_1_::dtor$1

- ea: `0x18000c56a`
- end: `0x18000c57a`
- name: `_ON_CREATE_PROC_DATA::ON_CREATE_PROC_DATA_::_1_::dtor$1`
- size: `16`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1800060c4`

## pseudocode

```c
__int64 __fastcall ON_CREATE_PROC_DATA::ON_CREATE_PROC_DATA_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  return std::wstring::~wstring(*(_QWORD *)(a2 + 56) + 8LL);
}

```

## disassembly

```asm
0x18000c56a  mov     rcx, [rdx+38h]
0x18000c571  add     rcx, 8
0x18000c575  jmp     ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
