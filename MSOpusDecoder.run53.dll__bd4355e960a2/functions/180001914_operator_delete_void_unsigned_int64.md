# operator delete(void *,unsigned __int64)

- ea: `0x180001914`
- end: `0x180001919`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `15`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x18001b258`
- `0x18001b570`
- `0x18001b5b0`
- `0x18001b600`
- `0x18001b640`
- `0x18001b6a0`
- `0x18001ef40`
- `0x18001efb0`
- `0x18001f030`
- `0x18001f080`
- `0x180020500`
- `0x180021d50`
- `0x180021e9c`
- `0x1800230c1`
- `0x1800230e4`

## callees

- `0x180001434`

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
0x180001914  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
