# operator delete(void *)

- ea: `0x180001160`
- end: `0x180001165`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `15`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180001178`
- `0x1800016b0`
- `0x1800032b0`
- `0x180003860`
- `0x180003890`
- `0x180003bfc`
- `0x180003cb0`
- `0x180003d10`
- `0x180003d70`
- `0x180003ef0`
- `0x180004180`
- `0x180004730`
- `0x1800047f0`
- `0x180009480`
- `0x180009df0`

## callees

- `0x180001696`

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
0x180001160  jmp     free_0
```
