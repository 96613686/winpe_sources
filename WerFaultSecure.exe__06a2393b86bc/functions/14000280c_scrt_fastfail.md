# __scrt_fastfail

- ea: `0x14000280c`
- end: `0x140002810`
- name: `__scrt_fastfail`
- size: `4`
- prototype: `void __fastcall __noreturn(unsigned int)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x140002120`
- `0x140002210`
- `0x1400024e4`
- `0x140003290`

## pseudocode

```c
void __fastcall __noreturn _scrt_fastfail(unsigned int a1)
{
  __fastfail(a1);
}

```

## disassembly

```asm
0x14000280c  mov     ecx, ecx
0x14000280e  int     29h; Win8: RtlFailFast(ecx)
```
