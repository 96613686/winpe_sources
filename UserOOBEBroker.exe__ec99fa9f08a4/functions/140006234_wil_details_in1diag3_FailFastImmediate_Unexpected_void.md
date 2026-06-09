# wil::details::in1diag3::_FailFastImmediate_Unexpected(void)

- ea: `0x140006234`
- end: `0x14000623b`
- name: `?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ`
- size: `7`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this)`
- caller_count: `7`
- callee_count: `0`
- tags: ``

## callers

- `0x1400030f4`
- `0x140003960`
- `0x140003d30`
- `0x140004be8`
- `0x14000783c`
- `0x140008710`
- `0x14000ba10`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_FailFastImmediate_Unexpected(wil::details::in1diag3 *this)
{
  __fastfail(7u);
}

```

## disassembly

```asm
0x140006234  mov     ecx, 7
0x140006239  int     29h; Win8: RtlFailFast(ecx)
```
