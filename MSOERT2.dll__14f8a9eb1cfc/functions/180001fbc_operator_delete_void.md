# operator delete(void *)

- ea: `0x180001fbc`
- end: `0x180001fc1`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `14`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180001fd4`
- `0x180004560`
- `0x180004f10`
- `0x180005cc4`
- `0x180006670`
- `0x180008fc0`
- `0x180009500`
- `0x180009540`
- `0x18000e450`
- `0x180010910`
- `0x180010ba0`
- `0x180010be0`
- `0x180010f04`
- `0x180011d00`

## callees

- `0x1800027dc`

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
0x180001fbc  jmp     free_0
```
