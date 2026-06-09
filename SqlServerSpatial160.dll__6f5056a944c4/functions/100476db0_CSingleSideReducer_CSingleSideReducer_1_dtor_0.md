# _CSingleSideReducer::_CSingleSideReducer_::_1_::dtor$0

- ea: `0x100476db0`
- end: `0x100476dbc`
- name: `_CSingleSideReducer::_CSingleSideReducer_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation`

## callees

- `0x100401480`

## pseudocode

```c
void __fastcall CSingleSideReducer::_CSingleSideReducer_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  CGeometrySinkD::~CGeometrySinkD(*(CGeometrySinkD **)(a2 + 96));
}

```

## disassembly

```asm
0x100476db0  mov     rcx, [rdx+60h]; this
0x100476db7  jmp     ??1CGeometrySinkD@@UEAA@XZ
```
