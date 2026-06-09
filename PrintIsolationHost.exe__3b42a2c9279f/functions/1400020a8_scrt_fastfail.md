# __scrt_fastfail

- ea: `0x1400020a8`
- end: `0x1400020ac`
- name: `__scrt_fastfail`
- size: `4`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x140001a30`
- `0x140001b20`
- `0x140001d74`

## pseudocode

```c
void __fastcall __noreturn _scrt_fastfail(unsigned int a1)
{
  __fastfail(a1);
}

```

## disassembly

```asm
0x1400020a8  mov     ecx, ecx
0x1400020aa  int     29h; Win8: RtlFailFast(ecx)
```
