# wil::details::in1diag3::_FailFastImmediate_Unexpected(void)

- ea: `0x1400068ec`
- end: `0x1400068f3`
- name: `?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ`
- size: `7`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this)`
- caller_count: `6`
- callee_count: `0`
- tags: ``

## callers

- `0x14000581c`
- `0x140006388`
- `0x1400078ec`
- `0x140007cbc`
- `0x1400080b4`
- `0x140009e24`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_FailFastImmediate_Unexpected(wil::details::in1diag3 *this)
{
  __fastfail(7u);
}

```

## disassembly

```asm
0x1400068ec  mov     ecx, 7
0x1400068f1  int     29h; Win8: RtlFailFast(ecx)
```
