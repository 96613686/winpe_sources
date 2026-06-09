# __scrt_fastfail

- ea: `0x180001900`
- end: `0x180001904`
- name: `__scrt_fastfail`
- size: `4`
- prototype: `void __fastcall __noreturn(unsigned int)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x180001128`
- `0x180001228`
- `0x180001760`

## pseudocode

```c
void __fastcall __noreturn _scrt_fastfail(unsigned int a1)
{
  __fastfail(a1);
}

```

## disassembly

```asm
0x180001900  mov     ecx, ecx
0x180001902  int     29h; Win8: RtlFailFast(ecx)
```
