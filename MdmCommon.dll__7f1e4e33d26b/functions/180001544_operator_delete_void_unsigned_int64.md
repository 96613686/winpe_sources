# operator delete(void *,unsigned __int64)

- ea: `0x180001544`
- end: `0x180001549`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __fastcall(void *Block)`
- caller_count: `41`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1800028e4`
- `0x180002a24`
- `0x180002de4`
- `0x180002e50`
- `0x180002f14`
- `0x180002fc0`
- `0x1800036c0`
- `0x180003a20`
- `0x180004520`
- `0x180004c70`
- `0x1800061a8`
- `0x1800067d8`
- `0x180006aa0`
- `0x18000745c`
- `0x1800078ec`
- `0x180008050`
- `0x180008328`
- `0x180008a6c`
- `0x180009b24`
- `0x18000a314`
- `0x18000ab88`
- `0x18000abb4`
- `0x18000ef34`
- `0x180010b0c`
- `0x180010f90`
- `0x180012038`
- `0x180016b60`
- `0x180016b90`
- `0x180017ad0`
- `0x180019c60`
- `0x180019c84`
- `0x18001a39c`
- `0x18001a588`
- `0x18001a890`
- `0x18001a8d4`
- `0x18001b13c`
- `0x18001b350`
- `0x18001b394`
- `0x18001b8b0`
- `0x18001c298`
- `0x18001c9ac`

## callees

- `0x180001b80`

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
0x180001544  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
