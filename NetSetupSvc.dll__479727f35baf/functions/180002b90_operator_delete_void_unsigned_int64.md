# operator delete(void *,unsigned __int64)

- ea: `0x180002b90`
- end: `0x180002b95`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __fastcall(void *Block)`
- caller_count: `19`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1800042b0`
- `0x1800042f0`
- `0x180006e34`
- `0x1800072f8`
- `0x180007324`
- `0x180008db0`
- `0x1800095d4`
- `0x180009680`
- `0x1800096c0`
- `0x18000fc80`
- `0x18001345c`
- `0x180013490`
- `0x1800134d0`
- `0x180016ca0`
- `0x18001d568`
- `0x180025a78`
- `0x18002e690`
- `0x18002ed73`
- `0x18002f563`

## callees

- `0x180003110`

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
0x180002b90  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
