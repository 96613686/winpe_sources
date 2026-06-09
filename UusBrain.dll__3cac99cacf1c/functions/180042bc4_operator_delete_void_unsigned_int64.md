# operator delete(void *,unsigned __int64)

- ea: `0x180042bc4`
- end: `0x180042bc9`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __fastcall(void *, unsigned __int64)`
- caller_count: `158`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180004a60`
- `0x180005b40`
- `0x180008630`
- `0x1800088a0`
- `0x180008bf0`
- `0x18000a6a0`
- `0x18000a748`
- `0x18000bd00`
- `0x18000c1e0`
- `0x18000c220`
- `0x18000c260`
- `0x18000c2a0`
- `0x18000c3c0`
- `0x18000c400`
- `0x18000f39c`
- `0x18000f5a0`
- `0x18000f61c`
- `0x18000f6a0`
- `0x18000f724`
- `0x18000f84c`
- `0x180010370`
- `0x1800109f0`
- `0x180010be8`
- `0x18001104c`
- `0x180011c04`
- `0x180012290`
- `0x180012458`
- `0x1800129cc`
- `0x180012b10`
- `0x180012bf0`
- `0x180012c48`
- `0x180012cb0`
- `0x180012cec`
- `0x180012d50`
- `0x180012d8c`
- `0x180012e40`
- `0x180012ea8`
- `0x180012f10`
- `0x180012fa0`
- `0x180012fe4`
- `0x180013050`
- `0x18001308c`
- `0x1800130f0`
- `0x180013130`
- `0x180013838`
- `0x180014560`
- `0x180018520`
- `0x1800189d0`
- `0x180018a40`
- `0x180018a74`

## callees

- `0x180043770`

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
0x180042bc4  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
