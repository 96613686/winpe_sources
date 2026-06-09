# __scrt_fastfail

- ea: `0x1800018f4`
- end: `0x1800018f8`
- name: `__scrt_fastfail`
- size: `4`
- prototype: `void __fastcall __noreturn(unsigned int)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x180001148`
- `0x180001248`
- `0x180001754`

## pseudocode

```c
void __fastcall __noreturn _scrt_fastfail(unsigned int a1)
{
  __fastfail(a1);
}

```

## disassembly

```asm
0x1800018f4  mov     ecx, ecx
0x1800018f6  int     29h; Win8: RtlFailFast(ecx)
```
