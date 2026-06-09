# operator delete(void *,std::nothrow_t const &)

- ea: `0x180002bac`
- end: `0x180002bb1`
- name: `??3@YAXPEAXAEBUnothrow_t@std@@@Z`
- size: `5`
- prototype: `void __fastcall(void *, const struct std::nothrow_t *)`
- caller_count: `10`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180006cb0`
- `0x18000c628`
- `0x18000c8f0`
- `0x18000f1c0`
- `0x18000f254`
- `0x180011748`
- `0x1800163ec`
- `0x18001669c`
- `0x180017518`
- `0x180017c90`

## callees

- `0x18000bcc8`

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
0x180002bac  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
