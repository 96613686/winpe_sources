# wil::details::in1diag5::_FailFastImmediate_Unexpected(void)

- ea: `0x1400076dc`
- end: `0x1400076e3`
- name: `?_FailFastImmediate_Unexpected@in1diag5@details@wil@@YAXXZ`
- size: `7`
- prototype: `void __fastcall __noreturn(wil::details::in1diag5 *__hidden this)`
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x140001fd0`
- `0x1400027a4`
- `0x140003c20`
- `0x1400040e4`
- `0x1400059e8`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag5::_FailFastImmediate_Unexpected(wil::details::in1diag5 *this)
{
  __fastfail(7u);
}

```

## disassembly

```asm
0x1400076dc  mov     ecx, 7
0x1400076e1  int     29h; Win8: RtlFailFast(ecx)
```
