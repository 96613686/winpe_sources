# __scrt_fastfail

- ea: `0x140001f84`
- end: `0x140001f88`
- name: `__scrt_fastfail`
- size: `4`
- prototype: `void __fastcall __noreturn(unsigned int)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x140001340`
- `0x140001430`
- `0x140001710`
- `0x140001930`

## pseudocode

```c
void __fastcall __noreturn _scrt_fastfail(unsigned int a1)
{
  __fastfail(a1);
}

```

## disassembly

```asm
0x140001f84  mov     ecx, ecx
0x140001f86  int     29h; Win8: RtlFailFast(ecx)
```
