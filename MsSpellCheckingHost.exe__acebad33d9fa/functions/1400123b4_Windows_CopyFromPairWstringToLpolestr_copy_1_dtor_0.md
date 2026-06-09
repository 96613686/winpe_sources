# _Windows::CopyFromPairWstringToLpolestr::copy_::_1_::dtor$0

- ea: `0x1400123b4`
- end: `0x1400123c0`
- name: `_Windows::CopyFromPairWstringToLpolestr::copy_::_1_::dtor$0`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1400087c4`

## pseudocode

```c
__int64 __fastcall Windows::CopyFromPairWstringToLpolestr::copy_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return std::wstring::~wstring(a2 + 40);
}

```

## disassembly

```asm
0x1400123b4  lea     rcx, [rdx+28h]
0x1400123bb  jmp     ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
