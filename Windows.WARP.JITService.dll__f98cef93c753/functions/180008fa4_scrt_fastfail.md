# __scrt_fastfail

- ea: `0x180008fa4`
- end: `0x180008fa8`
- name: `__scrt_fastfail`
- size: `4`
- prototype: `void __fastcall __noreturn(unsigned int)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x180008768`
- `0x180008868`
- `0x180008c60`

## pseudocode

```c
void __fastcall __noreturn _scrt_fastfail(unsigned int a1)
{
  __fastfail(a1);
}

```

## disassembly

```asm
0x180008fa4  mov     ecx, ecx
0x180008fa6  int     29h; Win8: RtlFailFast(ecx)
```
