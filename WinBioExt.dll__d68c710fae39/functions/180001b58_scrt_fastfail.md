# __scrt_fastfail

- ea: `0x180001b58`
- end: `0x180001b5c`
- name: `__scrt_fastfail`
- size: `4`
- prototype: ``
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x1800012f8`
- `0x1800013f8`
- `0x1800017f0`
- `0x1800020f0`

## pseudocode

```c
void __fastcall __noreturn _scrt_fastfail(unsigned int a1)
{
  __fastfail(a1);
}

```

## disassembly

```asm
0x180001b58  mov     ecx, ecx
0x180001b5a  int     29h; Win8: RtlFailFast(ecx)
```
