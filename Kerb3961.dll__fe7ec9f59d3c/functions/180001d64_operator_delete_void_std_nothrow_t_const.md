# operator delete(void *,std::nothrow_t const &)

- ea: `0x180001d64`
- end: `0x180001d69`
- name: `??3@YAXPEAXAEBUnothrow_t@std@@@Z`
- size: `5`
- prototype: `void __fastcall(void *, const struct std::nothrow_t *)`
- caller_count: `94`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180002b10`
- `0x1800032f4`
- `0x180003410`
- `0x180003cc4`
- `0x180004b40`
- `0x180004cf4`
- `0x180004e74`
- `0x180004fac`
- `0x1800050e0`
- `0x180005480`
- `0x180005ed0`
- `0x180006270`
- `0x180006ac0`
- `0x18000712c`
- `0x1800071e0`
- `0x180007500`
- `0x180007650`
- `0x180007960`
- `0x180007a90`
- `0x180007d00`
- `0x1800082f0`
- `0x180008500`
- `0x1800085cc`
- `0x18000901c`
- `0x1800090b0`
- `0x1800092a4`
- `0x180009470`
- `0x1800095b0`
- `0x1800098c0`
- `0x1800099c0`
- `0x180009dc0`
- `0x18000a010`
- `0x18000a210`
- `0x18000afb0`
- `0x18000b3d0`
- `0x18000b840`
- `0x18000ba20`
- `0x18000c4c8`
- `0x18000ca80`
- `0x18000de8c`
- `0x18000e05c`
- `0x18000e320`
- `0x18000e6c4`
- `0x18000e804`
- `0x18000ec30`
- `0x18000f030`
- `0x18000f580`
- `0x18000f754`
- `0x180010980`
- `0x1800109c0`

## callees

- `0x1800029e8`

## pseudocode

```c
// attributes: thunk
void __fastcall operator delete(void *a1, const struct std::nothrow_t *a2)
{
  ??3@YAXPEAX@Z(a1);
}

```

## disassembly

```asm
0x180001d64  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
