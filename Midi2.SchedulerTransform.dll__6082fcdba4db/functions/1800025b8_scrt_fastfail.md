# __scrt_fastfail

- ea: `0x1800025b8`
- end: `0x1800025bc`
- name: `__scrt_fastfail`
- size: `4`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x180001cd8`
- `0x180001dd8`
- `0x180002250`

## pseudocode

```c
void __fastcall __noreturn _scrt_fastfail(unsigned int a1)
{
  __fastfail(a1);
}

```

## disassembly

```asm
0x1800025b8  mov     ecx, ecx
0x1800025ba  int     29h; Win8: RtlFailFast(ecx)
```
