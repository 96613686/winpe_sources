# operator delete(void *,std::nothrow_t const &)

- ea: `0x18000ef40`
- end: `0x18000ef45`
- name: `??3@YAXPEAXAEBUnothrow_t@std@@@Z`
- size: `5`
- prototype: `HLOCAL __stdcall(HLOCAL hMem)`
- caller_count: `8`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1800060d0`
- `0x18000e49c`
- `0x1800106b0`
- `0x1800106f0`
- `0x180014da0`
- `0x180016e2c`
- `0x18001782c`
- `0x1800285f0`

## callees

- `0x18000e3cc`

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
0x18000ef40  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
