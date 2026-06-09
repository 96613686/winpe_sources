# _ON_CREATE_PROC_DATA::_ON_CREATE_PROC_DATA_::_1_::dtor$1

- ea: `0x18000c63d`
- end: `0x18000c64d`
- name: `_ON_CREATE_PROC_DATA::_ON_CREATE_PROC_DATA_::_1_::dtor$1`
- size: `16`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1800060c4`

## pseudocode

```c
__int64 __fastcall ON_CREATE_PROC_DATA::_ON_CREATE_PROC_DATA_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  return std::wstring::~wstring(*(_QWORD *)(a2 + 48) + 8LL);
}

```

## disassembly

```asm
0x18000c63d  mov     rcx, [rdx+30h]
0x18000c644  add     rcx, 8
0x18000c648  jmp     ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
