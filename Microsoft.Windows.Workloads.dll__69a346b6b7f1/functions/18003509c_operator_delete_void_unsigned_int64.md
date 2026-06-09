# operator delete(void *,unsigned __int64)

- ea: `0x18003509c`
- end: `0x1800350a1`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __fastcall(void *Block)`
- caller_count: `166`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1800027d0`
- `0x180002940`
- `0x180004a60`
- `0x180004aa0`
- `0x180004c40`
- `0x1800052e0`
- `0x180006110`
- `0x180006b70`
- `0x180007a20`
- `0x1800086d0`
- `0x180009a40`
- `0x18000a2b0`
- `0x18000a350`
- `0x18000b2d0`
- `0x18000b4e0`
- `0x18000b690`
- `0x18000b6d0`
- `0x18000b780`
- `0x18000b7c0`
- `0x18000bb70`
- `0x18000c010`
- `0x18000c530`
- `0x18000c830`
- `0x18000cca0`
- `0x18000ce20`
- `0x18000ced0`
- `0x18000cf30`
- `0x18000d760`
- `0x18000de00`
- `0x18000df90`
- `0x18000dfd0`
- `0x18000e330`
- `0x18000e530`
- `0x18000f160`
- `0x18000f230`
- `0x180010320`
- `0x1800105a0`
- `0x180010e10`
- `0x180010e90`
- `0x180011130`
- `0x1800112f0`
- `0x180011560`
- `0x1800118f0`
- `0x180011dd0`
- `0x180012630`
- `0x180012900`
- `0x180012a60`
- `0x180012ed0`
- `0x180012fb0`
- `0x180013460`

## callees

- `0x180035428`

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
0x18003509c  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
