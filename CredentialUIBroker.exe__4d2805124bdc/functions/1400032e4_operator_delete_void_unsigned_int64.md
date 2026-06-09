# operator delete(void *,unsigned __int64)

- ea: `0x1400032e4`
- end: `0x1400032e9`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __fastcall(void *Block)`
- caller_count: `32`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x140006140`
- `0x140006484`
- `0x14000a030`
- `0x14000a060`
- `0x14000a0a0`
- `0x14000a0e0`
- `0x14000a120`
- `0x14000a150`
- `0x14000a1a0`
- `0x14000a1e0`
- `0x14000a220`
- `0x14000a260`
- `0x14000a2a0`
- `0x14000a2e0`
- `0x14000a320`
- `0x14000a360`
- `0x14000a3a0`
- `0x14000a3e0`
- `0x14000a420`
- `0x14000a460`
- `0x14000a4a0`
- `0x14000a4e0`
- `0x14000a520`
- `0x14000a560`
- `0x14000a5c0`
- `0x14000a600`
- `0x14000a640`
- `0x1400172ac`
- `0x14001ada0`
- `0x14001adf8`
- `0x14001ae50`
- `0x14001aea8`

## callees

- `0x1400032f0`

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
0x1400032e4  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
