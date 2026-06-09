# __scrt_fastfail

- ea: `0x1800018fc`
- end: `0x180001900`
- name: `__scrt_fastfail`
- size: `4`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x1800010e8`
- `0x1800011e8`
- `0x18000175c`

## pseudocode

```c
void __fastcall __noreturn _scrt_fastfail(unsigned int a1)
{
  __fastfail(a1);
}

```

## disassembly

```asm
0x1800018fc  mov     ecx, ecx
0x1800018fe  int     29h; Win8: RtlFailFast(ecx)
```
