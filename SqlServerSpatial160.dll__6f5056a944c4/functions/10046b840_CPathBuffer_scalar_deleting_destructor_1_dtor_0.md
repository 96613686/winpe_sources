# _CPathBuffer::_scalar_deleting_destructor__::_1_::dtor$0

- ea: `0x10046b840`
- end: `0x10046b850`
- name: `_CPathBuffer::_scalar_deleting_destructor__::_1_::dtor$0`
- size: `16`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x100404d70`

## pseudocode

```c
void __fastcall CPathBuffer::_scalar_deleting_destructor__::_1_::dtor_0(__int64 a1, __int64 a2)
{
  CWidener::~CWidener((CWidener *)(*(_QWORD *)(a2 + 64) + 8LL));
}

```

## disassembly

```asm
0x10046b840  mov     rcx, [rdx+40h]
0x10046b847  add     rcx, 8; this
0x10046b84b  jmp     ??1CWidener@@UEAA@XZ
```
