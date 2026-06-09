# operator delete(void *,unsigned __int64)

- ea: `0x180015c0c`
- end: `0x180015c11`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `HLOCAL __stdcall(HLOCAL hMem)`
- caller_count: `28`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x18000c2a0`
- `0x18000cba4`
- `0x18000cbd0`
- `0x18000d520`
- `0x18000d6cc`
- `0x18000d82c`
- `0x18000d950`
- `0x18000d9a0`
- `0x18000e810`
- `0x18000fd10`
- `0x180017090`
- `0x1800175f0`
- `0x1800176f0`
- `0x180017730`
- `0x180017780`
- `0x180017860`
- `0x180018174`
- `0x180018788`
- `0x18001ccc0`
- `0x18001dec0`
- `0x18001fd18`
- `0x1800205e0`
- `0x180020810`
- `0x180020850`
- `0x180020890`
- `0x180022aa0`
- `0x180022ae0`
- `0x180026710`

## callees

- `0x18000f6a4`

## pseudocode

```c
// attributes: thunk
HLOCAL __stdcall operator delete(HLOCAL hMem)
{
  return ??3@YAXPEAX@Z(hMem);
}

```

## disassembly

```asm
0x180015c0c  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
