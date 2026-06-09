# operator delete(void *,unsigned __int64)

- ea: `0x18001662c`
- end: `0x180016631`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `HLOCAL __stdcall(HLOCAL hMem)`
- caller_count: `28`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x18000c850`
- `0x18000d1a8`
- `0x18000d1e0`
- `0x18000d2d0`
- `0x18000d500`
- `0x18000dec0`
- `0x18000dfc4`
- `0x18000e138`
- `0x18000ee80`
- `0x1800104f0`
- `0x180017b00`
- `0x1800180b0`
- `0x1800181b0`
- `0x1800181f0`
- `0x180018240`
- `0x18001832c`
- `0x180018bb4`
- `0x180019268`
- `0x18001da50`
- `0x18001ece0`
- `0x180020cd8`
- `0x180021630`
- `0x180021870`
- `0x1800218b0`
- `0x1800218f0`
- `0x180023bd0`
- `0x180023c10`
- `0x1800279c0`

## callees

- `0x18000fe1c`

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
0x18001662c  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
