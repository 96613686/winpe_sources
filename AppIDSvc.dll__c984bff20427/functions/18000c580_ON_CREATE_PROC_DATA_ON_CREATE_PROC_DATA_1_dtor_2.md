# _ON_CREATE_PROC_DATA::ON_CREATE_PROC_DATA_::_1_::dtor$2

- ea: `0x18000c580`
- end: `0x18000c590`
- name: `_ON_CREATE_PROC_DATA::ON_CREATE_PROC_DATA_::_1_::dtor$2`
- size: `16`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1800060c4`

## pseudocode

```c
__int64 __fastcall ON_CREATE_PROC_DATA::ON_CREATE_PROC_DATA_::_1_::dtor_2(__int64 a1, __int64 a2)
{
  return std::wstring::~wstring(*(_QWORD *)(a2 + 56) + 40LL);
}

```

## disassembly

```asm
0x18000c580  mov     rcx, [rdx+38h]
0x18000c587  add     rcx, 28h ; '('
0x18000c58b  jmp     ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
