# operator delete(void *,unsigned __int64)

- ea: `0x180001048`
- end: `0x18000104d`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __fastcall(void *, unsigned __int64)`
- caller_count: `26`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180006bf0`
- `0x180008c10`
- `0x180008db8`
- `0x180009650`
- `0x18000b5c0`
- `0x18000d49c`
- `0x18000dfb0`
- `0x180010320`
- `0x180010350`
- `0x1800103b0`
- `0x180010400`
- `0x180010440`
- `0x180010880`
- `0x180010cf0`
- `0x180010d60`
- `0x180011f9c`
- `0x1800120bc`
- `0x180012dc8`
- `0x180013d30`
- `0x180014580`
- `0x180014744`
- `0x1800148c4`
- `0x18001574c`
- `0x180015d30`
- `0x180016510`
- `0x1800166ec`

## callees

- `0x180001060`

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
0x180001048  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
