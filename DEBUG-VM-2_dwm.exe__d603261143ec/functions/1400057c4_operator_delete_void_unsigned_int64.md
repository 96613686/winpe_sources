# operator delete(void *,unsigned __int64)

- ea: `0x1400057c4`
- end: `0x1400057c9`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __fastcall(void *, unsigned __int64)`
- caller_count: `11`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1400079e0`
- `0x140007a20`
- `0x140007a60`
- `0x140007aa0`
- `0x14000c6f0`
- `0x14000c720`
- `0x14000c760`
- `0x14000c7a0`
- `0x14000da40`
- `0x14000dff4`
- `0x14000e1c0`

## callees

- `0x1400057f4`

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
0x1400057c4  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
