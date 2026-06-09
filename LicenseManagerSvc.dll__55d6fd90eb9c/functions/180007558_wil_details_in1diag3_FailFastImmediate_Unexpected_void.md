# wil::details::in1diag3::_FailFastImmediate_Unexpected(void)

- ea: `0x180007558`
- end: `0x18000755f`
- name: `?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ`
- size: `7`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this)`
- caller_count: `6`
- callee_count: `0`
- tags: ``

## callers

- `0x18000498c`
- `0x18000542c`
- `0x1800061e8`
- `0x180006538`
- `0x1800091dc`
- `0x1800093e0`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_FailFastImmediate_Unexpected(wil::details::in1diag3 *this)
{
  __fastfail(7u);
}

```

## disassembly

```asm
0x180007558  mov     ecx, 7
0x18000755d  int     29h; Win8: RtlFailFast(ecx)
```
