# __scrt_fastfail

- ea: `0x180003048`
- end: `0x18000304c`
- name: `__scrt_fastfail`
- size: `4`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x180002338`
- `0x180002438`
- `0x180002900`

## pseudocode

```c
void __fastcall __noreturn _scrt_fastfail(unsigned int a1)
{
  __fastfail(a1);
}

```

## disassembly

```asm
0x180003048  mov     ecx, ecx
0x18000304a  int     29h; Win8: RtlFailFast(ecx)
```
