# operator delete(void *,unsigned __int64)

- ea: `0x18000282c`
- end: `0x180002831`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `93`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180002374`
- `0x180004d20`
- `0x180004d50`
- `0x180004d90`
- `0x180004dd0`
- `0x180004e10`
- `0x18000af00`
- `0x18000af60`
- `0x18000afc0`
- `0x18000deec`
- `0x18000df1c`
- `0x18000e070`
- `0x18000e0a0`
- `0x18000e110`
- `0x18000efec`
- `0x18000f15c`
- `0x18000f604`
- `0x1800102cc`
- `0x180011d58`
- `0x180011d7c`
- `0x180011dec`
- `0x180011e7c`
- `0x180011f28`
- `0x180011f88`
- `0x180012714`
- `0x18001282c`
- `0x180012a00`
- `0x180012a70`
- `0x180012ab0`
- `0x180012af0`
- `0x180012b70`
- `0x180012be0`
- `0x180012c20`
- `0x180012c90`
- `0x180012cd0`
- `0x180012d10`
- `0x180012d70`
- `0x180012db0`
- `0x180012df0`
- `0x180012e40`
- `0x180012ea0`
- `0x180012f00`
- `0x180012f40`
- `0x180012f80`
- `0x180012fc0`
- `0x180013000`
- `0x180013040`
- `0x180013080`
- `0x1800130c0`
- `0x180013100`

## callees

- `0x180002820`

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
0x18000282c  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
