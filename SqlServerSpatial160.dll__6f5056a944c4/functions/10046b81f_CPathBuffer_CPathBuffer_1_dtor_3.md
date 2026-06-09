# _CPathBuffer::_CPathBuffer_::_1_::dtor$3

- ea: `0x10046b81f`
- end: `0x10046b82b`
- name: `_CPathBuffer::_CPathBuffer_::_1_::dtor$3`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1004013d0`

## pseudocode

```c
void __fastcall CPathBuffer::_CPathBuffer_::_1_::dtor_3(__int64 a1, __int64 a2)
{
  IMglGeometrySink::~IMglGeometrySink(*(IMglGeometrySink **)(a2 + 72));
}

```

## disassembly

```asm
0x10046b81f  mov     rcx, [rdx+48h]; this
0x10046b826  jmp     ??1IMglGeometrySink@@UEAA@XZ
```
