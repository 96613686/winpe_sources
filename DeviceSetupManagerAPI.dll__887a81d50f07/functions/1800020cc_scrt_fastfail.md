# __scrt_fastfail

- ea: `0x1800020cc`
- end: `0x1800020d0`
- name: `__scrt_fastfail`
- size: `4`
- prototype: `void __fastcall __noreturn(unsigned int)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x1800014a8`
- `0x1800015a8`
- `0x180001a7c`
- `0x180001cb0`

## pseudocode

```c
void __fastcall __noreturn _scrt_fastfail(unsigned int a1)
{
  __fastfail(a1);
}

```

## disassembly

```asm
0x1800020cc  mov     ecx, ecx
0x1800020ce  int     29h; Win8: RtlFailFast(ecx)
```
