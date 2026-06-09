# operator delete(void *,unsigned __int64)

- ea: `0x140008f38`
- end: `0x140008f3d`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __stdcall(LPVOID pv)`
- caller_count: `9`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x140004ef0`
- `0x1400068a0`
- `0x140006fb0`
- `0x14000ad80`
- `0x14000add0`
- `0x14000ae20`
- `0x14000ae60`
- `0x14000dbd0`
- `0x14000dc10`

## callees

- `0x1400076bc`

## pseudocode

```c
// attributes: thunk
void __stdcall operator delete(LPVOID pv)
{
  ??3@YAXPEAX@Z(pv);
}

```

## disassembly

```asm
0x140008f38  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
