# __scrt_fastfail

- ea: `0x1400018e0`
- end: `0x1400018e4`
- name: `__scrt_fastfail`
- size: `4`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x1400011c0`
- `0x1400012b0`
- `0x14000156c`

## pseudocode

```c
void __fastcall __noreturn _scrt_fastfail(unsigned int a1)
{
  __fastfail(a1);
}

```

## disassembly

```asm
0x1400018e0  mov     ecx, ecx
0x1400018e2  int     29h; Win8: RtlFailFast(ecx)
```
