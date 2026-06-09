# wil::details::in1diag3::_FailFastImmediate_Unexpected(void)

- ea: `0x140008aec`
- end: `0x140008af3`
- name: `?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ`
- size: `7`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this)`
- caller_count: `6`
- callee_count: `0`
- tags: ``

## callers

- `0x140002a74`
- `0x140003a78`
- `0x140003e1c`
- `0x1400041ec`
- `0x14000575c`
- `0x140006c1c`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_FailFastImmediate_Unexpected(wil::details::in1diag3 *this)
{
  __fastfail(7u);
}

```

## disassembly

```asm
0x140008aec  mov     ecx, 7
0x140008af1  int     29h; Win8: RtlFailFast(ecx)
```
