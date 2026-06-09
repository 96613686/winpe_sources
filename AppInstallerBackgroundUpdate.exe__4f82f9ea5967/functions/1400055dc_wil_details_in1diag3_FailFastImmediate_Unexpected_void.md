# wil::details::in1diag3::_FailFastImmediate_Unexpected(void)

- ea: `0x1400055dc`
- end: `0x1400055e3`
- name: `?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ`
- size: `7`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this)`
- caller_count: `6`
- callee_count: `0`
- tags: ``

## callers

- `0x1400024e4`
- `0x140002d18`
- `0x1400030e8`
- `0x140004068`
- `0x140006064`
- `0x140007530`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_FailFastImmediate_Unexpected(wil::details::in1diag3 *this)
{
  __fastfail(7u);
}

```

## disassembly

```asm
0x1400055dc  mov     ecx, 7
0x1400055e1  int     29h; Win8: RtlFailFast(ecx)
```
