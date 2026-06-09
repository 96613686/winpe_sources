# _CSingleSideReducer::_CSingleSideReducer_::_1_::dtor$2

- ea: `0x100476dcc`
- end: `0x100476ddf`
- name: `_CSingleSideReducer::_CSingleSideReducer_::_1_::dtor$2`
- size: `19`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation`

## callees

- `0x100439420`

## pseudocode

```c
void __fastcall CSingleSideReducer::_CSingleSideReducer_::_1_::dtor_2(__int64 a1, __int64 a2)
{
  ArrayOverPages<CSingleSideReducer::ShapeData,Default_Allocator<CSingleSideReducer::ShapeData>>::~ArrayOverPages<CSingleSideReducer::ShapeData,Default_Allocator<CSingleSideReducer::ShapeData>>(*(_QWORD *)(a2 + 96) + 128LL);
}

```

## disassembly

```asm
0x100476dcc  mov     rcx, [rdx+60h]
0x100476dd3  add     rcx, 80h
0x100476dda  jmp     ??1?$ArrayOverPages@UShapeData@CSingleSideReducer@@V?$Default_Allocator@UShapeData@CSingleSideReducer@@@@@@QEAA@XZ; ArrayOverPages<CSingleSideReducer::ShapeData,Default_Allocator<CSingleSideReducer::ShapeData>>::~ArrayOverPages<CSingleSideReducer::ShapeData,Default_Allocator<CSingleSideReducer::ShapeData>>(void)
```
