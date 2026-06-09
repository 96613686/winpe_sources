# _CNgcNode::Uninstall_::_1_::dtor$3

- ea: `0x18001f267`
- end: `0x18001f273`
- name: `_CNgcNode::Uninstall_::_1_::dtor$3`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x18000852c`

## pseudocode

```c
__int64 __fastcall CNgcNode::Uninstall_::_1_::dtor_3(__int64 a1, __int64 a2)
{
  return std::wstring::~wstring(a2 + 160, a2);
}

```

## disassembly

```asm
0x18001f267  lea     rcx, [rdx+0A0h]
0x18001f26e  jmp     ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
