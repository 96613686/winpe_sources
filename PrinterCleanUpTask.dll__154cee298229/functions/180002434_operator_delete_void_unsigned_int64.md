# operator delete(void *,unsigned __int64)

- ea: `0x180002434`
- end: `0x180002439`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __fastcall(void *Block)`
- caller_count: `20`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180003910`
- `0x180003950`
- `0x180003990`
- `0x1800039d0`
- `0x180003a10`
- `0x180003a50`
- `0x180006b20`
- `0x180006b50`
- `0x180008008`
- `0x18000ac50`
- `0x18000ac90`
- `0x18000acd0`
- `0x18000ad10`
- `0x18000e210`
- `0x18000e310`
- `0x18000e390`
- `0x180011bb0`
- `0x180011bf0`
- `0x180013fd0`
- `0x180014020`

## callees

- `0x180002560`

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
0x180002434  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
