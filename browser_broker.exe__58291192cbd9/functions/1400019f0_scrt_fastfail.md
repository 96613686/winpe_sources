# __scrt_fastfail

- ea: `0x1400019f0`
- end: `0x1400019f4`
- name: `__scrt_fastfail`
- size: `4`
- prototype: `void __fastcall __noreturn(unsigned int)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x140001360`
- `0x140001450`
- `0x1400016a4`

## pseudocode

```c
void __fastcall __noreturn _scrt_fastfail(unsigned int a1)
{
  __fastfail(a1);
}

```

## disassembly

```asm
0x1400019f0  mov     ecx, ecx
0x1400019f2  int     29h; Win8: RtlFailFast(ecx)
```
