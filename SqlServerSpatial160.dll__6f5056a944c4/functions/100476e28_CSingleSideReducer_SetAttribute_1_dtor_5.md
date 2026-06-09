# _CSingleSideReducer::SetAttribute_::_1_::dtor$5

- ea: `0x100476e28`
- end: `0x100476e38`
- name: `_CSingleSideReducer::SetAttribute_::_1_::dtor$5`
- size: `16`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation`

## callees

- `0x100439420`

## pseudocode

```c
void __fastcall CSingleSideReducer::SetAttribute_::_1_::dtor_5(__int64 a1, __int64 a2)
{
  ArrayOverPages<CSingleSideReducer::ShapeData,Default_Allocator<CSingleSideReducer::ShapeData>>::~ArrayOverPages<CSingleSideReducer::ShapeData,Default_Allocator<CSingleSideReducer::ShapeData>>(a2 + 80);
}

```

## disassembly

```asm
0x100476e28  lea     rcx, [rdx+40h]
0x100476e2f  add     rcx, 10h
0x100476e33  jmp     ??1?$ArrayOverPages@UShapeData@CSingleSideReducer@@V?$Default_Allocator@UShapeData@CSingleSideReducer@@@@@@QEAA@XZ; ArrayOverPages<CSingleSideReducer::ShapeData,Default_Allocator<CSingleSideReducer::ShapeData>>::~ArrayOverPages<CSingleSideReducer::ShapeData,Default_Allocator<CSingleSideReducer::ShapeData>>(void)
```
