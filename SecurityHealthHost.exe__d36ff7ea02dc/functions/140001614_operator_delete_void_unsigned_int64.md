# operator delete(void *,unsigned __int64)

- ea: `0x140001614`
- end: `0x140001619`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __fastcall(void *Block)`
- caller_count: `33`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x140002408`
- `0x140002744`
- `0x14000277c`
- `0x140002810`
- `0x14000285c`
- `0x140003188`
- `0x1400039c0`
- `0x1400039f0`
- `0x140003f18`
- `0x1400040bc`
- `0x140004130`
- `0x140004160`
- `0x140005bf0`
- `0x140005cc0`
- `0x140005fdc`
- `0x140007830`
- `0x140007870`
- `0x1400078b0`
- `0x14000c110`
- `0x14000c274`
- `0x14000c360`
- `0x14000c4a0`
- `0x14000ca30`
- `0x14000d12c`
- `0x14000d468`
- `0x14000d4c0`
- `0x14000d778`
- `0x14000d968`
- `0x14000dc20`
- `0x14000de68`
- `0x14000e47c`
- `0x14000fc66`
- `0x14000fd49`

## callees

- `0x140001900`

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
0x140001614  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
