# operator delete(void *,unsigned __int64)

- ea: `0x180001420`
- end: `0x180001425`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __fastcall(void *, unsigned __int64)`
- caller_count: `27`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1800022cc`
- `0x18000279c`
- `0x1800028e0`
- `0x180002918`
- `0x180002e48`
- `0x180003cc0`
- `0x180004560`
- `0x180004750`
- `0x180004ffc`
- `0x180006020`
- `0x180007380`
- `0x180007800`
- `0x180008350`
- `0x1800090f0`
- `0x180009134`
- `0x180009ac8`
- `0x180009d10`
- `0x180012c30`
- `0x180012c74`
- `0x1800142a0`
- `0x18001e840`
- `0x18001e890`
- `0x18001ea6c`
- `0x18001efbc`
- `0x18001fbac`
- `0x18001fc44`
- `0x18001fd08`

## callees

- `0x180001478`

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
0x180001420  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
