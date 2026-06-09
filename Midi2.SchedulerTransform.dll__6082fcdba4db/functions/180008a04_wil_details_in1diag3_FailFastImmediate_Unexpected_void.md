# wil::details::in1diag3::_FailFastImmediate_Unexpected(void)

- ea: `0x180008a04`
- end: `0x180008a0b`
- name: `?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ`
- size: `7`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x180003000`
- `0x180003a88`
- `0x1800049f0`
- `0x180005e70`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_FailFastImmediate_Unexpected(wil::details::in1diag3 *this)
{
  __fastfail(7u);
}

```

## disassembly

```asm
0x180008a04  mov     ecx, 7
0x180008a09  int     29h; Win8: RtlFailFast(ecx)
```
