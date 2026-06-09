# __scrt_fastfail

- ea: `0x180003f34`
- end: `0x180003f38`
- name: `__scrt_fastfail`
- size: `4`
- prototype: ``
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x1800030a8`
- `0x1800031a8`
- `0x180003620`
- `0x180003870`

## pseudocode

```c
void __fastcall __noreturn _scrt_fastfail(unsigned int a1)
{
  __fastfail(a1);
}

```

## disassembly

```asm
0x180003f34  mov     ecx, ecx
0x180003f36  int     29h; Win8: RtlFailFast(ecx)
```
