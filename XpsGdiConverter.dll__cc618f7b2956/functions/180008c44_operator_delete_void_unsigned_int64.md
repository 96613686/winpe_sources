# operator delete(void *,unsigned __int64)

- ea: `0x180008c44`
- end: `0x180008c49`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __fastcall(void *, unsigned __int64)`
- caller_count: `66`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x18000aba0`
- `0x18000abe0`
- `0x18000da2c`
- `0x18000ea00`
- `0x18000ea50`
- `0x18000ea80`
- `0x18000eab0`
- `0x18000eaf0`
- `0x18000eb30`
- `0x18000eb6c`
- `0x18000eb98`
- `0x18000ebd0`
- `0x18000ec0c`
- `0x18000ec40`
- `0x18000ec80`
- `0x1800122d0`
- `0x180015ef0`
- `0x180016910`
- `0x180016944`
- `0x180016970`
- `0x1800169ac`
- `0x180018530`
- `0x180019b50`
- `0x18001e274`
- `0x18001e2a0`
- `0x18001e2e0`
- `0x18001e314`
- `0x18001e340`
- `0x180027184`
- `0x180027208`
- `0x180027d70`
- `0x180027db0`
- `0x180028730`
- `0x18002a658`
- `0x18002b9c8`
- `0x1800317d0`
- `0x180033490`
- `0x180035370`
- `0x1800353a4`
- `0x1800353d0`
- `0x180037230`
- `0x18003cf8c`
- `0x18003cfc0`
- `0x18003d000`
- `0x18003d040`
- `0x18003dca8`
- `0x18003eda4`
- `0x1800426b0`
- `0x1800426f0`
- `0x180042730`

## callees

- `0x1800091f4`

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
0x180008c44  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
