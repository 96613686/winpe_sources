# __scrt_fastfail

- ea: `0x180001c5c`
- end: `0x180001c60`
- name: `__scrt_fastfail`
- size: `4`
- prototype: `void __fastcall __noreturn(unsigned int)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x180001408`
- `0x180001508`
- `0x180001954`

## pseudocode

```c
void __fastcall __noreturn _scrt_fastfail(unsigned int a1)
{
  __fastfail(a1);
}

```

## disassembly

```asm
0x180001c5c  mov     ecx, ecx
0x180001c5e  int     29h; Win8: RtlFailFast(ecx)
```
