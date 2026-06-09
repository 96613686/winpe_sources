# operator delete(void *,unsigned __int64)

- ea: `0x14001382c`
- end: `0x140013831`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `93`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x140001388`
- `0x140001fac`
- `0x1400021a0`
- `0x140002208`
- `0x140002980`
- `0x140002b20`
- `0x140003010`
- `0x1400033b0`
- `0x1400043a0`
- `0x1400044b0`
- `0x140004958`
- `0x140004a30`
- `0x140004a8c`
- `0x140004b0c`
- `0x140004cf0`
- `0x140004d30`
- `0x140004e40`
- `0x140005074`
- `0x1400050ec`
- `0x140005400`
- `0x140005a10`
- `0x140005ae0`
- `0x140005b14`
- `0x140006b5c`
- `0x140006bac`
- `0x140006e5c`
- `0x140006eb4`
- `0x1400073b0`
- `0x140007468`
- `0x1400076f8`
- `0x14000778c`
- `0x140007854`
- `0x140008b1c`
- `0x140008ef4`
- `0x140009000`
- `0x1400090c8`
- `0x140009380`
- `0x140009480`
- `0x140009910`
- `0x140009c00`
- `0x140009ca0`
- `0x140009ce4`
- `0x14000a42c`
- `0x14000b7b4`
- `0x14000bdc0`
- `0x14000c890`
- `0x14000ca88`
- `0x14000cb7c`
- `0x14000cc10`
- `0x14000cc44`

## callees

- `0x1400137c4`

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
0x14001382c  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
