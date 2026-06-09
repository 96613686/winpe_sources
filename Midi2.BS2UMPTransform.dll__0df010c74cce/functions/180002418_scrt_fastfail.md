# __scrt_fastfail

- ea: `0x180002418`
- end: `0x18000241c`
- name: `__scrt_fastfail`
- size: `4`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x180001b38`
- `0x180001c38`
- `0x1800020b0`

## pseudocode

```c
void __fastcall __noreturn _scrt_fastfail(unsigned int a1)
{
  __fastfail(a1);
}

```

## disassembly

```asm
0x180002418  mov     ecx, ecx
0x18000241a  int     29h; Win8: RtlFailFast(ecx)
```
