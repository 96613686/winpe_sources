# _CNgcNode::Create_::_1_::dtor$2

- ea: `0x18001f21f`
- end: `0x18001f22b`
- name: `_CNgcNode::Create_::_1_::dtor$2`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18000852c`

## pseudocode

```c
__int64 __fastcall CNgcNode::Create_::_1_::dtor_2(__int64 a1, __int64 a2)
{
  return std::wstring::~wstring(a2 + 144, a2);
}

```

## disassembly

```asm
0x18001f21f  lea     rcx, [rdx+90h]
0x18001f226  jmp     ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
