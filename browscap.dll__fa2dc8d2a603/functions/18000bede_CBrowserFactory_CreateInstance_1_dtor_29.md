# _CBrowserFactory::CreateInstance_::_1_::dtor$29

- ea: `0x18000bede`
- end: `0x18000beea`
- name: `_CBrowserFactory::CreateInstance_::_1_::dtor$29`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x180009a30`

## pseudocode

```c
void __fastcall CBrowserFactory::CreateInstance_::_1_::dtor_29(__int64 a1, __int64 a2)
{
  operator delete(*(void **)(a2 + 80));
}

```

## disassembly

```asm
0x18000bede  mov     rcx, [rdx+50h]; void *
0x18000bee5  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
