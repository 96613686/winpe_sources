# _CSession::_DoReadrmonNodeDiff_::_1_::dtor$1

- ea: `0x18001eddc`
- end: `0x18001ede8`
- name: `_CSession::_DoReadrmonNodeDiff_::_1_::dtor$1`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18000c954`

## pseudocode

```c
void __fastcall CSession::_DoReadrmonNodeDiff_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  std::list<std::unique_ptr<std::wstring>>::~list<std::unique_ptr<std::wstring>>(a2 + 56);
}

```

## disassembly

```asm
0x18001eddc  lea     rcx, [rdx+38h]
0x18001ede3  jmp     ??1?$list@V?$unique_ptr@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$default_delete@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@V?$allocator@V?$unique_ptr@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$default_delete@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@2@@std@@QEAA@XZ; std::list<std::unique_ptr<std::wstring>>::~list<std::unique_ptr<std::wstring>>(void)
```
