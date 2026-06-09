# _CPathBuffer::_CPathBuffer_::_1_::dtor$2

- ea: `0x10046b813`
- end: `0x10046b81f`
- name: `_CPathBuffer::_CPathBuffer_::_1_::dtor$2`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x100401480`

## pseudocode

```c
void __fastcall CPathBuffer::_CPathBuffer_::_1_::dtor_2(__int64 a1, __int64 a2)
{
  CGeometrySinkD::~CGeometrySinkD(*(CGeometrySinkD **)(a2 + 72));
}

```

## disassembly

```asm
0x10046b813  mov     rcx, [rdx+48h]; this
0x10046b81a  jmp     ??1CGeometrySinkD@@UEAA@XZ
```
