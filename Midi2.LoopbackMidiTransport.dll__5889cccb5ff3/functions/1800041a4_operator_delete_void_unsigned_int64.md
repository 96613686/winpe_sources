# operator delete(void *,unsigned __int64)

- ea: `0x1800041a4`
- end: `0x1800041a9`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `86`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180005d1c`
- `0x180006050`
- `0x1800060e0`
- `0x180006170`
- `0x1800061b0`
- `0x1800061f0`
- `0x180006608`
- `0x1800070e0`
- `0x180007650`
- `0x180009dd0`
- `0x18000b478`
- `0x18000b6c4`
- `0x18000b740`
- `0x18000b7d0`
- `0x18000bc30`
- `0x18000bc60`
- `0x18000bca0`
- `0x18000bce0`
- `0x18000bd40`
- `0x18000c34c`
- `0x18000c4e0`
- `0x18000c540`
- `0x18000c5c0`
- `0x18000c620`
- `0x18000d650`
- `0x18000d680`
- `0x18000d6f0`
- `0x18000e22c`
- `0x18000e5a0`
- `0x18000e6e0`
- `0x18000faa8`
- `0x18000fbd0`
- `0x18000fc58`
- `0x18000fd2c`
- `0x18000feb0`
- `0x180010130`
- `0x180010180`
- `0x180012678`
- `0x180012710`
- `0x1800127f0`
- `0x180012870`
- `0x180013574`
- `0x180014920`
- `0x180014c84`
- `0x180014cec`
- `0x180014d48`
- `0x180015790`
- `0x1800158e8`
- `0x180015a48`
- `0x180015ba0`

## callees

- `0x180004164`

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
0x1800041a4  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
