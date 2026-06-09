# __scrt_fastfail

- ea: `0x140001740`
- end: `0x140001744`
- name: `__scrt_fastfail`
- size: `4`
- prototype: `void __fastcall __noreturn(unsigned int)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x140001090`
- `0x140001180`
- `0x140001404`

## pseudocode

```c
void __fastcall __noreturn _scrt_fastfail(unsigned int a1)
{
  __fastfail(a1);
}

```

## disassembly

```asm
0x140001740  mov     ecx, ecx
0x140001742  int     29h; Win8: RtlFailFast(ecx)
```
