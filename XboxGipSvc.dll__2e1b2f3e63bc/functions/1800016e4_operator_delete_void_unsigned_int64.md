# operator delete[](void *,unsigned __int64)

- ea: `0x1800016e4`
- end: `0x1800016e9`
- name: `??_V@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __fastcall(void *, const struct std::nothrow_t *)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x18000c8fc`
- `0x18000dc70`

## callees

- `0x180001b6c`

## pseudocode

```c
// attributes: thunk
void __fastcall operator delete[](void *a1, const struct std::nothrow_t *a2)
{
  operator delete(a1, a2);
}

```

## disassembly

```asm
0x1800016e4  jmp     ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
```
