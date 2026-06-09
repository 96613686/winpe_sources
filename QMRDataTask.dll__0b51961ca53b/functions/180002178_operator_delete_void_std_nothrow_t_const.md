# operator delete(void *,std::nothrow_t const &)

- ea: `0x180002178`
- end: `0x18000217d`
- name: `??3@YAXPEAXAEBUnothrow_t@std@@@Z`
- size: `5`
- prototype: `void __fastcall(void *, const struct std::nothrow_t *)`
- caller_count: `19`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180005280`
- `0x180005828`
- `0x18000592c`
- `0x18000687c`
- `0x180006c00`
- `0x180009494`
- `0x18000a1c0`
- `0x18000a7d0`
- `0x18000a8c0`
- `0x18000ace0`
- `0x18000c260`
- `0x18000c410`
- `0x18000c5b0`
- `0x18000ebf8`
- `0x18000ef08`
- `0x18000f418`
- `0x180011b60`
- `0x180011c80`
- `0x180011d54`

## callees

- `0x180001b56`

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
0x180002178  jmp     ??3@YAXPEAX@Z_0; operator delete(void *)
```
