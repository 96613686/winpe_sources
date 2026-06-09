# _CSingleSideReducer::ShapeData::_ShapeData_::_1_::dtor$0

- ea: `0x100476e50`
- end: `0x100476e60`
- name: `_CSingleSideReducer::ShapeData::_ShapeData_::_1_::dtor$0`
- size: `16`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation`

## callees

- `0x100439420`

## pseudocode

```c
void __fastcall CSingleSideReducer::ShapeData::_ShapeData_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  ArrayOverPages<CSingleSideReducer::ShapeData,Default_Allocator<CSingleSideReducer::ShapeData>>::~ArrayOverPages<CSingleSideReducer::ShapeData,Default_Allocator<CSingleSideReducer::ShapeData>>(*(_QWORD *)(a2 + 64) + 16LL);
}

```

## disassembly

```asm
0x100476e50  mov     rcx, [rdx+40h]
0x100476e57  add     rcx, 10h
0x100476e5b  jmp     ??1?$ArrayOverPages@UShapeData@CSingleSideReducer@@V?$Default_Allocator@UShapeData@CSingleSideReducer@@@@@@QEAA@XZ; ArrayOverPages<CSingleSideReducer::ShapeData,Default_Allocator<CSingleSideReducer::ShapeData>>::~ArrayOverPages<CSingleSideReducer::ShapeData,Default_Allocator<CSingleSideReducer::ShapeData>>(void)
```
