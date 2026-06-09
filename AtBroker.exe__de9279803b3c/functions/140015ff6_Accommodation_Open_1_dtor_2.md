# _Accommodation::Open_::_1_::dtor$2

- ea: `0x140015ff6`
- end: `0x140016002`
- name: `_Accommodation::Open_::_1_::dtor$2`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, broker_com_uri`

## callees

- `0x140001e44`

## pseudocode

```c
void __fastcall Accommodation::Open_::_1_::dtor_2(__int64 a1, __int64 a2)
{
  operator delete(*(void **)(a2 + 144));
}

```

## disassembly

```asm
0x140015ff6  mov     rcx, [rdx+90h]; Block
0x140015ffd  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
