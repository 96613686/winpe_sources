# __scrt_fastfail

- ea: `0x140002604`
- end: `0x140002608`
- name: `__scrt_fastfail`
- size: `4`
- prototype: `void __fastcall __noreturn(unsigned int)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x140001e80`
- `0x140001f70`
- `0x1400021c4`

## pseudocode

```c
void __fastcall __noreturn _scrt_fastfail(unsigned int a1)
{
  __fastfail(a1);
}

```

## disassembly

```asm
0x140002604  mov     ecx, ecx
0x140002606  int     29h; Win8: RtlFailFast(ecx)
```
