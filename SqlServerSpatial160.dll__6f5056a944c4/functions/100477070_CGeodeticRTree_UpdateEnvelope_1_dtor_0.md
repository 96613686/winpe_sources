# _CGeodeticRTree::UpdateEnvelope_::_1_::dtor$0

- ea: `0x100477070`
- end: `0x10047707c`
- name: `_CGeodeticRTree::UpdateEnvelope_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x100408db0`

## pseudocode

```c
void __fastcall CGeodeticRTree::UpdateEnvelope_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  CCap::~CCap((CCap *)(a2 + 64));
}

```

## disassembly

```asm
0x100477070  lea     rcx, [rdx+40h]; this
0x100477077  jmp     ??1CCap@@UEAA@XZ; CCap::~CCap(void)
```
