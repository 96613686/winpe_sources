# operator delete(void *,unsigned __int64)

- ea: `0x180002750`
- end: `0x180002755`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __fastcall(void *Block)`
- caller_count: `50`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180004b20`
- `0x180004b60`
- `0x180004ba0`
- `0x180004be0`
- `0x180004c60`
- `0x180004ce0`
- `0x180004d20`
- `0x180006880`
- `0x1800068c0`
- `0x18000cc6c`
- `0x180011300`
- `0x180011dc4`
- `0x1800128d0`
- `0x180012900`
- `0x180012940`
- `0x180012980`
- `0x1800129c0`
- `0x180012a10`
- `0x180012a50`
- `0x180012a90`
- `0x180012ad0`
- `0x180012b10`
- `0x180012b50`
- `0x180012b90`
- `0x180012bd0`
- `0x180012c10`
- `0x180012c50`
- `0x180012c90`
- `0x180012cd0`
- `0x180012d10`
- `0x180012d50`
- `0x180012d90`
- `0x180012dd0`
- `0x180012e10`
- `0x180012e4c`
- `0x180012e80`
- `0x180012ec0`
- `0x180012f00`
- `0x180012f40`
- `0x18001cd98`
- `0x18001e8d4`
- `0x18001eb74`
- `0x1800214c0`
- `0x180021500`
- `0x180022a60`
- `0x180022c80`
- `0x18002346f`
- `0x1800239e8`
- `0x180023feb`
- `0x180024159`

## callees

- `0x18000278c`

## pseudocode

```c
// attributes: thunk
void __fastcall operator delete(void *Block)
{
  ??3@YAXPEAX@Z(Block);
}

```

## disassembly

```asm
0x180002750  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
