# __scrt_fastfail

- ea: `0x1400019f8`
- end: `0x1400019fc`
- name: `__scrt_fastfail`
- size: `4`
- prototype: `void __fastcall __noreturn(unsigned int)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x140001320`
- `0x140001410`
- `0x1400016d0`
- `0x140002480`

## pseudocode

```c
void __fastcall __noreturn _scrt_fastfail(unsigned int a1)
{
  __fastfail(a1);
}

```

## disassembly

```asm
0x1400019f8  mov     ecx, ecx
0x1400019fa  int     29h; Win8: RtlFailFast(ecx)
```
