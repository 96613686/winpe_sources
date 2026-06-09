# operator delete(void *,unsigned __int64)

- ea: `0x180002e94`
- end: `0x180002e99`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `35`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x18000467c`
- `0x1800049b0`
- `0x180004a20`
- `0x180004a90`
- `0x180004ad0`
- `0x180004b10`
- `0x180004f28`
- `0x180005a00`
- `0x180005f50`
- `0x1800086d0`
- `0x180009e0c`
- `0x180009fa0`
- `0x18000a000`
- `0x18000a080`
- `0x18000a0e0`
- `0x18000b344`
- `0x18000b4d4`
- `0x18000b5dc`
- `0x18000b770`
- `0x18000d0ac`
- `0x18000d268`
- `0x18000d2f0`
- `0x18000d7d0`
- `0x18000d800`
- `0x18000d860`
- `0x18000d8b0`
- `0x18000d900`
- `0x18000e950`
- `0x1800102f8`
- `0x180010390`
- `0x180010410`
- `0x1800104e0`
- `0x180010560`
- `0x180010e7c`
- `0x180011db8`

## callees

- `0x180002e54`

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
0x180002e94  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
