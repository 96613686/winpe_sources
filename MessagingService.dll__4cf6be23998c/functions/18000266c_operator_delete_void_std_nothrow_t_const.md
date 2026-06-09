# operator delete(void *,std::nothrow_t const &)

- ea: `0x18000266c`
- end: `0x180002671`
- name: `??3@YAXPEAXAEBUnothrow_t@std@@@Z`
- size: `5`
- prototype: `void __fastcall(void *, const struct std::nothrow_t *)`
- caller_count: `13`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180003dc8`
- `0x180004984`
- `0x180004ea0`
- `0x180005720`
- `0x180005bd4`
- `0x180006fdc`
- `0x18000707c`
- `0x180007930`
- `0x180008168`
- `0x1800093e4`
- `0x180009524`
- `0x180009aec`
- `0x18000a0f4`

## callees

- `0x180002556`

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
0x18000266c  jmp     ??3@YAXPEAX@Z_0; operator delete(void *)
```
