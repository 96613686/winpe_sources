# __report_gsfailure

- ea: `0x180001a80`
- end: `0x180001a87`
- name: `__report_gsfailure`
- size: `7`
- prototype: `void __cdecl __noreturn(uintptr_t StackCookie)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x180001550`

## pseudocode

```c
void __cdecl __noreturn _report_gsfailure(uintptr_t StackCookie)
{
  __fastfail(2u);
}

```

## disassembly

```asm
0x180001a80  mov     ecx, 2
0x180001a85  int     29h; Win8: RtlFailFast(ecx)
```
