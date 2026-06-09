# __scrt_fastfail

- ea: `0x1800022b4`
- end: `0x1800022b8`
- name: `__scrt_fastfail`
- size: `4`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x180001a48`
- `0x180001b48`
- `0x180001f64`

## pseudocode

```c
void __fastcall __noreturn _scrt_fastfail(unsigned int a1)
{
  __fastfail(a1);
}

```

## disassembly

```asm
0x1800022b4  mov     ecx, ecx
0x1800022b6  int     29h; Win8: RtlFailFast(ecx)
```
