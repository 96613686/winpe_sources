# operator delete(void *)

- ea: `0x180001064`
- end: `0x180001069`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `16`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180001ca8`
- `0x180001e20`
- `0x180001e50`
- `0x180001ef0`
- `0x180001f80`
- `0x180002084`
- `0x1800021f0`
- `0x180003ed4`
- `0x1800048f0`
- `0x180005be0`
- `0x180005dc4`
- `0x180006120`
- `0x180007d34`
- `0x18000839c`
- `0x180008480`
- `0x180008538`

## callees

- `0x180001536`

## pseudocode

```c
// attributes: thunk
void __cdecl operator delete(void *Block)
{
  free_0(Block);
}

```

## disassembly

```asm
0x180001064  jmp     free_0
```
