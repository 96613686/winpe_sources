# __scrt_fastfail

- ea: `0x180002178`
- end: `0x18000217c`
- name: `__scrt_fastfail`
- size: `4`
- prototype: `void __fastcall __noreturn(unsigned int)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x1800018e8`
- `0x1800019e8`
- `0x180001e24`

## pseudocode

```c
void __fastcall __noreturn _scrt_fastfail(unsigned int a1)
{
  __fastfail(a1);
}

```

## disassembly

```asm
0x180002178  mov     ecx, ecx
0x18000217a  int     29h; Win8: RtlFailFast(ecx)
```
