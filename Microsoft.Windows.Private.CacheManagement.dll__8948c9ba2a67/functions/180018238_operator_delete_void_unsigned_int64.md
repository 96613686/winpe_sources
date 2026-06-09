# operator delete(void *,unsigned __int64)

- ea: `0x180018238`
- end: `0x18001823d`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __fastcall(void *Block)`
- caller_count: `49`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180002370`
- `0x180002520`
- `0x1800050b0`
- `0x180005df0`
- `0x180007410`
- `0x1800091e0`
- `0x180009280`
- `0x180009aa0`
- `0x180009b70`
- `0x180009ed0`
- `0x180009f30`
- `0x180009f70`
- `0x18000a230`
- `0x18000a720`
- `0x18000acc0`
- `0x18000b320`
- `0x18000b700`
- `0x18000bdd0`
- `0x18000c050`
- `0x18000e3e0`
- `0x18000ec30`
- `0x180010fe0`
- `0x1800110c0`
- `0x180011500`
- `0x180011800`
- `0x180011ce0`
- `0x180012290`
- `0x180012640`
- `0x180012fc0`
- `0x180013150`
- `0x180013a20`
- `0x180016974`
- `0x180016d90`
- `0x180016ee0`
- `0x180016f10`
- `0x180017054`
- `0x1800175e0`
- `0x180017640`
- `0x180017694`
- `0x180017710`
- `0x180017740`
- `0x1800181d0`
- `0x18001c7a0`
- `0x18001ca20`
- `0x18001cca0`
- `0x18001da6c`
- `0x18001daa0`
- `0x18001db4c`
- `0x18001dc18`

## callees

- `0x180018ed8`

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
0x180018238  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
