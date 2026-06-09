# __scrt_fastfail

- ea: `0x1800021ec`
- end: `0x1800021f0`
- name: `__scrt_fastfail`
- size: `4`
- prototype: `void __fastcall __noreturn(unsigned int)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x180001998`
- `0x180001a98`
- `0x180001fec`

## pseudocode

```c
void __fastcall __noreturn _scrt_fastfail(unsigned int a1)
{
  __fastfail(a1);
}

```

## disassembly

```asm
0x1800021ec  mov     ecx, ecx
0x1800021ee  int     29h; Win8: RtlFailFast(ecx)
```
