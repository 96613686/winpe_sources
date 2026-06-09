# _GetDllForwarder_::_1_::dtor$4

- ea: `0x18000c444`
- end: `0x18000c454`
- name: `_GetDllForwarder_::_1_::dtor$4`
- size: `16`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180008f20`

## pseudocode

```c
__int64 GetDllForwarder_::_1_::dtor_4()
{
  return std::wstring::~wstring((char **)&qword_1800130C8);
}

```

## disassembly

```asm
0x18000c444  lea     rcx, off_180013090
0x18000c44b  add     rcx, 38h ; '8'
0x18000c44f  jmp     ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
