# operator delete(void *,unsigned __int64)

- ea: `0x1800011c0`
- end: `0x1800011c5`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `189`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180002250`
- `0x18000228c`
- `0x1800036f0`
- `0x180004450`
- `0x180004490`
- `0x180004940`
- `0x180004980`
- `0x180006ff8`
- `0x180007490`
- `0x180007560`
- `0x1800079a0`
- `0x1800079dc`
- `0x180009cdc`
- `0x180009d60`
- `0x180009d9c`
- `0x18000a31c`
- `0x18000a3b0`
- `0x18000a5e4`
- `0x18000a8b8`
- `0x18000ac64`
- `0x18000bbc0`
- `0x18000be50`
- `0x18000c280`
- `0x18000c2bc`
- `0x18000c2f8`
- `0x18000c460`
- `0x18000c5d0`
- `0x18000cd00`
- `0x18000cfa0`
- `0x18000cfdc`
- `0x18000d018`
- `0x18000d100`
- `0x18000d5e0`
- `0x18000d6c0`
- `0x18000d9d0`
- `0x18000db60`
- `0x18000e250`
- `0x18000e510`
- `0x18000e54c`
- `0x18000e588`
- `0x18000e6d0`
- `0x18000ef80`
- `0x18000f1c0`
- `0x18000f1fc`
- `0x18000f2b0`
- `0x18000f480`
- `0x18000f890`
- `0x18000fa90`
- `0x18000fd20`
- `0x180010250`

## callees

- `0x1800011b4`

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
0x1800011c0  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
