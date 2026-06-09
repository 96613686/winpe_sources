# _CSingleSideReducer::SetAttribute_::_1_::dtor$0

- ea: `0x100476e1c`
- end: `0x100476e28`
- name: `_CSingleSideReducer::SetAttribute_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation`

## callees

- `0x100437700`

## pseudocode

```c
void __fastcall CSingleSideReducer::SetAttribute_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  CSingleSideReducer::ShapeData::~ShapeData((CSingleSideReducer::ShapeData *)(a2 + 64));
}

```

## disassembly

```asm
0x100476e1c  lea     rcx, [rdx+40h]; this
0x100476e23  jmp     ??1ShapeData@CSingleSideReducer@@QEAA@XZ; CSingleSideReducer::ShapeData::~ShapeData(void)
```
