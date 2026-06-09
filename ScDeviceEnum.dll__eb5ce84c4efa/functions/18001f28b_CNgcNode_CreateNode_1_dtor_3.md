# _CNgcNode::_CreateNode_::_1_::dtor$3

- ea: `0x18001f28b`
- end: `0x18001f297`
- name: `_CNgcNode::_CreateNode_::_1_::dtor$3`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180011a88`

## pseudocode

```c
void __fastcall CNgcNode::_CreateNode_::_1_::dtor_3(__int64 a1, __int64 a2)
{
  CNgcNode::CDeviceCreateContext::~CDeviceCreateContext((CNgcNode::CDeviceCreateContext *)(a2 + 240), a2);
}

```

## disassembly

```asm
0x18001f28b  lea     rcx, [rdx+0F0h]; this
0x18001f292  jmp     ??1CDeviceCreateContext@CNgcNode@@QEAA@XZ; CNgcNode::CDeviceCreateContext::~CDeviceCreateContext(void)
```
