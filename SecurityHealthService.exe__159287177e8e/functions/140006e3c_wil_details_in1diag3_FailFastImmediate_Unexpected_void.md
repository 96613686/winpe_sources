# wil::details::in1diag3::_FailFastImmediate_Unexpected(void)

- ea: `0x140006e3c`
- end: `0x140006e43`
- name: `?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ`
- size: `7`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this)`
- caller_count: `6`
- callee_count: `0`
- tags: ``

## callers

- `0x140005778`
- `0x140006320`
- `0x140008718`
- `0x140008ae8`
- `0x140008ee0`
- `0x14000ab00`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_FailFastImmediate_Unexpected(wil::details::in1diag3 *this)
{
  __fastfail(7u);
}

```

## disassembly

```asm
0x140006e3c  mov     ecx, 7
0x140006e41  int     29h; Win8: RtlFailFast(ecx)
```
