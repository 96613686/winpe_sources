# operator delete(void *,std::nothrow_t const &)

- ea: `0x140003a70`
- end: `0x140003a75`
- name: `??3@YAXPEAXAEBUnothrow_t@std@@@Z`
- size: `5`
- prototype: `void __fastcall(void *, const struct std::nothrow_t *)`
- caller_count: `6`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1400144f8`
- `0x14001abc8`
- `0x14001d4e0`
- `0x14001d520`
- `0x14001de80`
- `0x1400390e0`

## callees

- `0x1400039c2`

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
0x140003a70  jmp     ??3@YAXPEAX@Z_0; operator delete(void *)
```
