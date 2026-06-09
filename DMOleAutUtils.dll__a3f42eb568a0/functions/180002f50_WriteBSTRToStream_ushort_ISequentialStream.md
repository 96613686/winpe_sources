# WriteBSTRToStream(ushort *,ISequentialStream *)

- ea: `0x180002f50`
- end: `0x180002f59`
- name: `?WriteBSTRToStream@@YAJPEAGPEAUISequentialStream@@@Z`
- size: `9`
- prototype: `__int64 __fastcall(unsigned __int16 *, struct ISequentialStream *)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180002f60`

## pseudocode

```c
__int64 __fastcall WriteBSTRToStream(unsigned __int16 *a1, struct ISequentialStream *a2)
{
  return WriteBSTRToStreamEx(a1, a2, 0xFFFFFFFF);
}

```

## disassembly

```asm
0x180002f50  or      r8d, 0FFFFFFFFh; unsigned int
0x180002f54  jmp     ?WriteBSTRToStreamEx@@YAJPEAGPEAUISequentialStream@@K@Z; WriteBSTRToStreamEx(ushort *,ISequentialStream *,ulong)
```
