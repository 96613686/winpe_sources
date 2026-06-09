# _CPathBuffer::_CPathBuffer_::_1_::dtor$1

- ea: `0x10046b800`
- end: `0x10046b813`
- name: `_CPathBuffer::_CPathBuffer_::_1_::dtor$1`
- size: `19`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x100403b50`

## pseudocode

```c
void __fastcall CPathBuffer::_CPathBuffer_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  COptimizedOutlineModule::~COptimizedOutlineModule((COptimizedOutlineModule *)(*(_QWORD *)(a2 + 64) + 384LL));
}

```

## disassembly

```asm
0x10046b800  mov     rcx, [rdx+40h]
0x10046b807  add     rcx, 180h; this
0x10046b80e  jmp     ??1COptimizedOutlineModule@@UEAA@XZ; COptimizedOutlineModule::~COptimizedOutlineModule(void)
```
