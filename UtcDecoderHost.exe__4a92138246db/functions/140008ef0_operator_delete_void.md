# operator delete(void *)

- ea: `0x140008ef0`
- end: `0x140008ef5`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1400088f4`
- `0x140008900`

## callees

- `0x1400090a4`

## pseudocode

```c
// attributes: thunk
void __cdecl operator delete(void *Block)
{
  free(Block);
}

```

## disassembly

```asm
0x140008ef0  jmp     free
```
