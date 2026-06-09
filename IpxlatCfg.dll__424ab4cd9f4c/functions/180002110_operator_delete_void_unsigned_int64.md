# operator delete(void *,unsigned __int64)

- ea: `0x180002110`
- end: `0x180002115`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __fastcall(void *Block)`
- caller_count: `28`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180004880`
- `0x1800048c0`
- `0x180004900`
- `0x180004940`
- `0x18000b590`
- `0x18000b620`
- `0x18000c190`
- `0x18000df7c`
- `0x18000e5a4`
- `0x18000e734`
- `0x18000e7a8`
- `0x18000f23c`
- `0x18000f260`
- `0x18000f2d8`
- `0x18000f34c`
- `0x18000f37c`
- `0x18000f3ac`
- `0x18000f480`
- `0x18000f4b0`
- `0x18000f4f8`
- `0x18000f668`
- `0x18000f9f0`
- `0x1800132f0`
- `0x180013350`
- `0x180018302`
- `0x18001865a`
- `0x180018735`
- `0x18001877c`

## callees

- `0x1800028bc`

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
0x180002110  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
