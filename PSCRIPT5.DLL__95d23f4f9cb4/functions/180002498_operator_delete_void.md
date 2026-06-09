# operator delete(void *)

- ea: `0x180002498`
- end: `0x18000249d`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `16`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180001f30`
- `0x180030f80`
- `0x180033ffc`
- `0x1800340bc`
- `0x180034150`
- `0x180034190`
- `0x1800341c0`
- `0x180034220`
- `0x18003431c`
- `0x180034518`
- `0x180034e30`
- `0x180035e3c`
- `0x180035f4c`
- `0x180036118`
- `0x18003629c`
- `0x180036388`

## callees

- `0x18000286c`

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
0x180002498  jmp     free
```
