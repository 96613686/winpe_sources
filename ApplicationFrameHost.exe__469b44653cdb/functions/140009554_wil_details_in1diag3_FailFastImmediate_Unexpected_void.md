# wil::details::in1diag3::_FailFastImmediate_Unexpected(void)

- ea: `0x140009554`
- end: `0x14000955b`
- name: `?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ`
- size: `7`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this)`
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x1400045e4`
- `0x140005630`
- `0x1400069e0`
- `0x140006e0c`
- `0x140006f70`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_FailFastImmediate_Unexpected(wil::details::in1diag3 *this)
{
  __fastfail(7u);
}

```

## disassembly

```asm
0x140009554  mov     ecx, 7
0x140009559  int     29h; Win8: RtlFailFast(ecx)
```
