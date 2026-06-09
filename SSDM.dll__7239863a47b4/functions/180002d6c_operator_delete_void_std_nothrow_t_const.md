# operator delete(void *,std::nothrow_t const &)

- ea: `0x180002d6c`
- end: `0x180002d71`
- name: `??3@YAXPEAXAEBUnothrow_t@std@@@Z`
- size: `5`
- prototype: `void __fastcall(void *, const struct std::nothrow_t *)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x18000f2ae`

## callees

- `0x180002d0d`

## pseudocode

```c
// attributes: thunk
void __fastcall operator delete(void *a1, const struct std::nothrow_t *a2)
{
  ??3@YAXPEAX@Z_0(a1);
}

```

## disassembly

```asm
0x180002d6c  jmp     ??3@YAXPEAX@Z_0; operator delete(void *)
```
