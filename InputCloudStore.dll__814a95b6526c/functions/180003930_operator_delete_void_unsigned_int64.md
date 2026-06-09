# operator delete(void *,unsigned __int64)

- ea: `0x180003930`
- end: `0x180003935`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __fastcall(void *, unsigned __int64)`
- caller_count: `23`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1800050c0`
- `0x180005100`
- `0x180008490`
- `0x1800084c0`
- `0x180008500`
- `0x180008530`
- `0x18001213c`
- `0x18001eda0`
- `0x18001ede0`
- `0x18001ee20`
- `0x18001ee60`
- `0x18001eea0`
- `0x18001eee0`
- `0x18001ef20`
- `0x18001ef60`
- `0x18001efa0`
- `0x18001f000`
- `0x18001f040`
- `0x18001f080`
- `0x180024770`
- `0x180029040`
- `0x180029080`
- `0x18002f3c6`

## callees

- `0x180003990`

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
0x180003930  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
