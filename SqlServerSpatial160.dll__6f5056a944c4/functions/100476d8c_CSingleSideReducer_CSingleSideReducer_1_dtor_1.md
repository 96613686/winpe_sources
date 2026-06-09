# _CSingleSideReducer::CSingleSideReducer_::_1_::dtor$1

- ea: `0x100476d8c`
- end: `0x100476d9c`
- name: `_CSingleSideReducer::CSingleSideReducer_::_1_::dtor$1`
- size: `16`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation`

## callees

- `0x100401590`

## pseudocode

```c
__int64 __fastcall CSingleSideReducer::CSingleSideReducer_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  return CDistanceTo<CDistanceFromPoint,CDistanceFromLineSegment,CDistanceFromArc>::~CDistanceTo<CDistanceFromPoint,CDistanceFromLineSegment,CDistanceFromArc>(*(_QWORD *)(a2 + 96) + 48LL);
}

```

## disassembly

```asm
0x100476d8c  mov     rcx, [rdx+60h]
0x100476d93  add     rcx, 30h ; '0'
0x100476d97  jmp     ??1?$CDistanceTo@VCDistanceFromPoint@@VCDistanceFromLineSegment@@VCDistanceFromArc@@@@UEAA@XZ
```
