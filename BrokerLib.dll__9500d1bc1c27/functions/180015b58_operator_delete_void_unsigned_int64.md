# operator delete(void *,unsigned __int64)

- ea: `0x180015b58`
- end: `0x180015b5d`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __fastcall(void *, unsigned __int64)`
- caller_count: `38`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180002614`
- `0x180003cd0`
- `0x180004b34`
- `0x180004ca8`
- `0x180004d70`
- `0x180004e38`
- `0x180004e78`
- `0x180006540`
- `0x180007350`
- `0x180008340`
- `0x18000b954`
- `0x18000bef4`
- `0x18000ef90`
- `0x18000f7c0`
- `0x180011640`
- `0x180011dd0`
- `0x180011e9c`
- `0x180012200`
- `0x180013930`
- `0x180016820`
- `0x180017720`
- `0x180017760`
- `0x1800177a0`
- `0x1800177e0`
- `0x180017828`
- `0x180017854`
- `0x180017880`
- `0x1800178c8`
- `0x18001a330`
- `0x18001b880`
- `0x18001be9c`
- `0x18001c00e`
- `0x18001c2eb`
- `0x18001c5f4`
- `0x18001c9fb`
- `0x18001d71c`
- `0x18001d863`
- `0x18001d886`

## callees

- `0x180016490`

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
0x180015b58  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
