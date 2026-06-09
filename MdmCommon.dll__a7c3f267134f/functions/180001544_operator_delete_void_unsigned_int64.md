# operator delete(void *,unsigned __int64)

- ea: `0x180001544`
- end: `0x180001549`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __fastcall(void *, unsigned __int64)`
- caller_count: `41`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1800028e4`
- `0x180002a24`
- `0x180002de8`
- `0x180002e54`
- `0x180002f1c`
- `0x180002fc0`
- `0x1800036d0`
- `0x180003a30`
- `0x180004550`
- `0x180004ca0`
- `0x180006200`
- `0x18000685c`
- `0x180006b24`
- `0x1800074e4`
- `0x180007974`
- `0x180008154`
- `0x180008438`
- `0x180008be0`
- `0x180009d18`
- `0x18000a528`
- `0x18000adb0`
- `0x18000addc`
- `0x18000f3b8`
- `0x180010eb4`
- `0x18001134c`
- `0x180012414`
- `0x180017060`
- `0x180017090`
- `0x1800180a0`
- `0x18001a16c`
- `0x18001a194`
- `0x18001a8c0`
- `0x18001aac0`
- `0x18001ade0`
- `0x18001ae24`
- `0x18001b6c0`
- `0x18001b8e0`
- `0x18001b924`
- `0x18001be50`
- `0x18001c8d0`
- `0x18001d010`

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
