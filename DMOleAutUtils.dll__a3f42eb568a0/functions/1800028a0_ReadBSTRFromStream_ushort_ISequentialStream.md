# ReadBSTRFromStream(ushort * *,ISequentialStream *)

- ea: `0x1800028a0`
- end: `0x1800028a9`
- name: `?ReadBSTRFromStream@@YAJPEAPEAGPEAUISequentialStream@@@Z`
- size: `9`
- prototype: `__int64 __fastcall(unsigned __int16 **, struct ISequentialStream *)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1800028b0`

## pseudocode

```c
__int64 __fastcall ReadBSTRFromStream(unsigned __int16 **a1, struct ISequentialStream *a2)
{
  return ReadBSTRFromStreamEx(a1, a2, 0xFFFFFFFF);
}

```

## disassembly

```asm
0x1800028a0  or      r8d, 0FFFFFFFFh; unsigned int
0x1800028a4  jmp     ?ReadBSTRFromStreamEx@@YAJPEAPEAGPEAUISequentialStream@@K@Z; ReadBSTRFromStreamEx(ushort * *,ISequentialStream *,ulong)
```
