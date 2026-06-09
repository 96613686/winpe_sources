# __scrt_fastfail

- ea: `0x180001908`
- end: `0x18000190c`
- name: `__scrt_fastfail`
- size: `4`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x180001168`
- `0x180001268`
- `0x180001768`

## pseudocode

```c
void __fastcall __noreturn _scrt_fastfail(unsigned int a1)
{
  __fastfail(a1);
}

```

## disassembly

```asm
0x180001908  mov     ecx, ecx
0x18000190a  int     29h; Win8: RtlFailFast(ecx)
```
