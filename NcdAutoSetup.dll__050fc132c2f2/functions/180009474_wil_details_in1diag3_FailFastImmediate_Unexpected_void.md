# wil::details::in1diag3::_FailFastImmediate_Unexpected(void)

- ea: `0x180009474`
- end: `0x18000947b`
- name: `?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ`
- size: `7`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this)`
- caller_count: `6`
- callee_count: `0`
- tags: ``

## callers

- `0x180002cec`
- `0x180003a78`
- `0x180003e1c`
- `0x180004350`
- `0x1800058b4`
- `0x180006b98`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_FailFastImmediate_Unexpected(wil::details::in1diag3 *this)
{
  __fastfail(7u);
}

```

## disassembly

```asm
0x180009474  mov     ecx, 7
0x180009479  int     29h; Win8: RtlFailFast(ecx)
```
