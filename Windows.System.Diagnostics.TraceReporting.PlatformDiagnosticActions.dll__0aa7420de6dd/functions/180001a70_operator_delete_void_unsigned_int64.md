# operator delete(void *,unsigned __int64)

- ea: `0x180001a70`
- end: `0x180001a75`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __fastcall(void *Block)`
- caller_count: `20`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180002f90`
- `0x180002fd0`
- `0x180005cc0`
- `0x180006ca0`
- `0x180007040`
- `0x180007064`
- `0x1800070d4`
- `0x180007140`
- `0x1800071a0`
- `0x1800071d0`
- `0x180007220`
- `0x1800072a0`
- `0x1800072f0`
- `0x180007340`
- `0x180007390`
- `0x180007780`
- `0x180007de0`
- `0x180008370`
- `0x180008de0`
- `0x1800099e0`

## callees

- `0x180001f1c`

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
0x180001a70  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
