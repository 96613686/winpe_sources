# __scrt_fastfail

- ea: `0x180001b24`
- end: `0x180001b28`
- name: `__scrt_fastfail`
- size: `4`
- prototype: ``
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x180001318`
- `0x180001418`
- `0x180001810`
- `0x1800020c0`

## pseudocode

```c
void __fastcall __noreturn _scrt_fastfail(unsigned int a1)
{
  __fastfail(a1);
}

```

## disassembly

```asm
0x180001b24  mov     ecx, ecx
0x180001b26  int     29h; Win8: RtlFailFast(ecx)
```
