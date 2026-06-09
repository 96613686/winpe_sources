# RtlFailFast

- ea: `0x1800019d8`
- end: `0x1800019dc`
- name: `RtlFailFast`
- size: `4`
- prototype: `void __fastcall __noreturn(unsigned int)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x180001238`
- `0x180001338`
- `0x180001838`

## pseudocode

```c
void __fastcall __noreturn RtlFailFast(unsigned int a1)
{
  __fastfail(a1);
}

```

## disassembly

```asm
0x1800019d8  mov     ecx, ecx
0x1800019da  int     29h; Win8: RtlFailFast(ecx)
```
