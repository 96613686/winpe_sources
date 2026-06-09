# _CGeodeticRTree::ComputeLeafEnvelope_::_1_::dtor$0

- ea: `0x100477050`
- end: `0x10047705c`
- name: `_CGeodeticRTree::ComputeLeafEnvelope_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x100408db0`

## pseudocode

```c
void __fastcall CGeodeticRTree::ComputeLeafEnvelope_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  CCap::~CCap((CCap *)(a2 + 48));
}

```

## disassembly

```asm
0x100477050  lea     rcx, [rdx+30h]; this
0x100477057  jmp     ??1CCap@@UEAA@XZ; CCap::~CCap(void)
```
