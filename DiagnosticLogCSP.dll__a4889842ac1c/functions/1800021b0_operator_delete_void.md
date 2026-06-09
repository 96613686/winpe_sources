# operator delete(void *)

- ea: `0x1800021b0`
- end: `0x1800021b5`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `6`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180001bc8`
- `0x180002480`
- `0x1800141f0`
- `0x180014600`
- `0x180035460`
- `0x180035490`

## callees

- `0x1800025cc`

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
0x1800021b0  jmp     free
```
