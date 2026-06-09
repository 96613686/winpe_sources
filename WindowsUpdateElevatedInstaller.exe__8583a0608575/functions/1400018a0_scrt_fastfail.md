# __scrt_fastfail

- ea: `0x1400018a0`
- end: `0x1400018a4`
- name: `__scrt_fastfail`
- size: `4`
- prototype: `void __fastcall __noreturn(unsigned int)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x1400011d0`
- `0x1400012c0`
- `0x140001524`

## pseudocode

```c
void __fastcall __noreturn _scrt_fastfail(unsigned int a1)
{
  __fastfail(a1);
}

```

## disassembly

```asm
0x1400018a0  mov     ecx, ecx
0x1400018a2  int     29h; Win8: RtlFailFast(ecx)
```
