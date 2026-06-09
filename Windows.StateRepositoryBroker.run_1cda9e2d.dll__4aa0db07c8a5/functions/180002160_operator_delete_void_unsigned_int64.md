# operator delete(void *,unsigned __int64)

- ea: `0x180002160`
- end: `0x180002165`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `10`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180004060`
- `0x1800040b0`
- `0x1800040e0`
- `0x180004120`
- `0x180004150`
- `0x180004190`
- `0x1800041d0`
- `0x180004210`
- `0x180004250`
- `0x180004290`

## callees

- `0x180002154`

## pseudocode

```c
// attributes: thunk
void __cdecl operator delete(void *Block)
{
  ??3@YAXPEAX@Z(Block);
}

```

## disassembly

```asm
0x180002160  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
