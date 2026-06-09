# __scrt_fastfail

- ea: `0x180001e84`
- end: `0x180001e88`
- name: `__scrt_fastfail`
- size: `4`
- prototype: ``
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x180001648`
- `0x180001748`
- `0x180001b40`
- `0x1800027c0`

## pseudocode

```c
void __fastcall __noreturn _scrt_fastfail(unsigned int a1)
{
  __fastfail(a1);
}

```

## disassembly

```asm
0x180001e84  mov     ecx, ecx
0x180001e86  int     29h; Win8: RtlFailFast(ecx)
```
