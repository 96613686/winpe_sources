# operator delete(void *,unsigned __int64)

- ea: `0x140001fcc`
- end: `0x140001fd1`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `23`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x140003f70`
- `0x140003fb0`
- `0x140006f58`
- `0x14000704c`
- `0x140007130`
- `0x140007170`
- `0x140007298`
- `0x1400072a8`
- `0x140009850`
- `0x1400098b8`
- `0x140009f08`
- `0x14000a1dc`
- `0x14000e880`
- `0x14000e8c0`
- `0x14000eae0`
- `0x140010b3c`
- `0x140012f60`
- `0x140015a08`
- `0x140016328`
- `0x1400170c0`
- `0x140023af0`
- `0x140023b30`
- `0x140024c68`

## callees

- `0x140001fc0`

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
0x140001fcc  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
