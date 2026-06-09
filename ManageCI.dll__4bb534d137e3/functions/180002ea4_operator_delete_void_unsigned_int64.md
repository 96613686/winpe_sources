# operator delete(void *,unsigned __int64)

- ea: `0x180002ea4`
- end: `0x180002ea9`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __fastcall(void *Block)`
- caller_count: `45`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180004a98`
- `0x1800052e4`
- `0x180005308`
- `0x1800057a8`
- `0x1800057d8`
- `0x180005820`
- `0x180005860`
- `0x18000589c`
- `0x1800058e0`
- `0x180005920`
- `0x18000a308`
- `0x18000a6e4`
- `0x18000a720`
- `0x18000a760`
- `0x180011860`
- `0x180011890`
- `0x1800118c0`
- `0x1800118f0`
- `0x180011920`
- `0x180011950`
- `0x180011b74`
- `0x180011bc0`
- `0x180015d68`
- `0x180016f48`
- `0x180017ec0`
- `0x18001bf2c`
- `0x18001c4a0`
- `0x18001c4d0`
- `0x18001c510`
- `0x18001c560`
- `0x18001c5a0`
- `0x18001c5e0`
- `0x18001c620`
- `0x18001c660`
- `0x18001c6a0`
- `0x18001c6e0`
- `0x18002021c`
- `0x180029ff5`
- `0x18002a358`
- `0x18002a837`
- `0x18002ab7e`
- `0x18002adce`
- `0x18002ae93`
- `0x18002b619`
- `0x18002b6a8`

## callees

- `0x180003738`

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
0x180002ea4  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
