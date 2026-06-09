# __scrt_fastfail

- ea: `0x140002fe8`
- end: `0x140002fec`
- name: `__scrt_fastfail`
- size: `4`
- prototype: `void __fastcall __noreturn(unsigned int)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x140002780`
- `0x140002870`
- `0x140002be8`
- `0x1400037e0`

## pseudocode

```c
void __fastcall __noreturn _scrt_fastfail(unsigned int a1)
{
  __fastfail(a1);
}

```

## disassembly

```asm
0x140002fe8  mov     ecx, ecx
0x140002fea  int     29h; Win8: RtlFailFast(ecx)
```
