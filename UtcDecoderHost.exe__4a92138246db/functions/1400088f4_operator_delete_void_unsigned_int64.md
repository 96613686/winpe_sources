# operator delete(void *,unsigned __int64)

- ea: `0x1400088f4`
- end: `0x1400088f9`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __fastcall(void *Block)`
- caller_count: `38`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x14000a7cc`
- `0x14000a840`
- `0x14000aa40`
- `0x14000aa80`
- `0x14000ec68`
- `0x14000ef1c`
- `0x14000f014`
- `0x14000f194`
- `0x14000f6a8`
- `0x14000f6cc`
- `0x14000f758`
- `0x14000f7d0`
- `0x14000f918`
- `0x14000f9a8`
- `0x14000f9e0`
- `0x14000fa04`
- `0x14000fad4`
- `0x14000fc00`
- `0x14000fc3c`
- `0x14000fccc`
- `0x140010fd4`
- `0x1400110a4`
- `0x140011740`
- `0x140012414`
- `0x140012470`
- `0x140012ea4`
- `0x140012ec8`
- `0x140012f48`
- `0x140012fa0`
- `0x1400130a0`
- `0x140013600`
- `0x140013640`
- `0x140013680`
- `0x1400136e0`
- `0x1400166a0`
- `0x1400177ea`
- `0x140017b00`
- `0x140017c00`

## callees

- `0x140008ef0`

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
0x1400088f4  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
