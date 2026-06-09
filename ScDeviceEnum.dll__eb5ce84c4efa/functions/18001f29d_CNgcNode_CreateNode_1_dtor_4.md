# _CNgcNode::_CreateNode_::_1_::dtor$4

- ea: `0x18001f29d`
- end: `0x18001f2a9`
- name: `_CNgcNode::_CreateNode_::_1_::dtor$4`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18000852c`

## pseudocode

```c
__int64 __fastcall CNgcNode::_CreateNode_::_1_::dtor_4(__int64 a1, __int64 a2)
{
  return std::wstring::~wstring(a2 + 208, a2);
}

```

## disassembly

```asm
0x18001f29d  lea     rcx, [rdx+0D0h]
0x18001f2a4  jmp     ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
