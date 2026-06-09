# _CILogStorage::OpenLogStream_::_1_::dtor$0

- ea: `0x1800130b4`
- end: `0x1800130c0`
- name: `_CILogStorage::OpenLogStream_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x180001300`

## pseudocode

```c
void __fastcall CILogStorage::OpenLogStream_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  operator delete(*(void **)(a2 + 32));
}

```

## disassembly

```asm
0x1800130b4  mov     rcx, [rdx+20h]; Block
0x1800130bb  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
