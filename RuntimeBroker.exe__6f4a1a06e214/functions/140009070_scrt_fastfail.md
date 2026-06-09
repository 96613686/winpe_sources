# __scrt_fastfail

- ea: `0x140009070`
- end: `0x140009074`
- name: `__scrt_fastfail`
- size: `4`
- prototype: ``
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x1400089e0`
- `0x140008ad0`
- `0x140008d48`
- `0x140009df0`

## pseudocode

```c
void __fastcall __noreturn _scrt_fastfail(unsigned int a1)
{
  __fastfail(a1);
}

```

## disassembly

```asm
0x140009070  mov     ecx, ecx
0x140009072  int     29h; Win8: RtlFailFast(ecx)
```
