# __scrt_fastfail

- ea: `0x180002034`
- end: `0x180002038`
- name: `__scrt_fastfail`
- size: `4`
- prototype: `void __fastcall __noreturn(unsigned int)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x1800017a8`
- `0x1800018a8`
- `0x180001ca0`
- `0x180002720`

## pseudocode

```c
void __fastcall __noreturn _scrt_fastfail(unsigned int a1)
{
  __fastfail(a1);
}

```

## disassembly

```asm
0x180002034  mov     ecx, ecx
0x180002036  int     29h; Win8: RtlFailFast(ecx)
```
