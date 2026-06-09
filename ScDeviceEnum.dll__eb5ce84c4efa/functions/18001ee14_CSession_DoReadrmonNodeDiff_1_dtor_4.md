# _CSession::_DoReadrmonNodeDiff_::_1_::dtor$4

- ea: `0x18001ee14`
- end: `0x18001ee20`
- name: `_CSession::_DoReadrmonNodeDiff_::_1_::dtor$4`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18000ca98`

## pseudocode

```c
__int64 __fastcall CSession::_DoReadrmonNodeDiff_::_1_::dtor_4(__int64 a1, __int64 a2)
{
  return std::unique_ptr<std::wstring>::~unique_ptr<std::wstring>(a2 + 48);
}

```

## disassembly

```asm
0x18001ee14  lea     rcx, [rdx+30h]
0x18001ee1b  jmp     ??1?$unique_ptr@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$default_delete@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ; std::unique_ptr<std::wstring>::~unique_ptr<std::wstring>(void)
```
