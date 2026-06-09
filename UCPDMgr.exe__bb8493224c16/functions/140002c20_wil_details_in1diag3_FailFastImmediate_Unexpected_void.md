# wil::details::in1diag3::_FailFastImmediate_Unexpected(void)

- ea: `0x140002c20`
- end: `0x140002c27`
- name: `?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ`
- size: `7`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x1400026e0`
- `0x140004d94`
- `0x140005ba4`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_FailFastImmediate_Unexpected(wil::details::in1diag3 *this)
{
  __fastfail(7u);
}

```

## disassembly

```asm
0x140002c20  mov     ecx, 7
0x140002c25  int     29h; Win8: RtlFailFast(ecx)
```
