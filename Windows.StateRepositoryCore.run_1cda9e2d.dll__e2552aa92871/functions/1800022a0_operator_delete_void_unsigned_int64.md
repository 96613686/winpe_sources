# operator delete(void *,unsigned __int64)

- ea: `0x1800022a0`
- end: `0x1800022a5`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __fastcall(void *, unsigned __int64)`
- caller_count: `20`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1800041f0`
- `0x180004230`
- `0x180004270`
- `0x1800042b0`
- `0x1800042f0`
- `0x180004330`
- `0x18000bf7c`
- `0x18000c52c`
- `0x18000c928`
- `0x18000d534`
- `0x18000dd30`
- `0x18000de80`
- `0x18000df20`
- `0x18000df50`
- `0x18000e45c`
- `0x18000e488`
- `0x18000e8b0`
- `0x18000e954`
- `0x18000f140`
- `0x18000f6a4`

## callees

- `0x18000274c`

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
0x1800022a0  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
