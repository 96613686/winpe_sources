# __scrt_fastfail

- ea: `0x140002cf4`
- end: `0x140002cf8`
- name: `__scrt_fastfail`
- size: `4`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x140002670`
- `0x140002760`
- `0x1400029b4`

## pseudocode

```c
void __fastcall __noreturn _scrt_fastfail(unsigned int a1)
{
  __fastfail(a1);
}

```

## disassembly

```asm
0x140002cf4  mov     ecx, ecx
0x140002cf6  int     29h; Win8: RtlFailFast(ecx)
```
