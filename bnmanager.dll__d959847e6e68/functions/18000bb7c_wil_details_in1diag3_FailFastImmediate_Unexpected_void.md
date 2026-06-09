# wil::details::in1diag3::_FailFastImmediate_Unexpected(void)

- ea: `0x18000bb7c`
- end: `0x18000bb83`
- name: `?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ`
- size: `7`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this)`
- caller_count: `6`
- callee_count: `0`
- tags: ``

## callers

- `0x180002cdc`
- `0x180005ad8`
- `0x180005e7c`
- `0x180006e6c`
- `0x1800088d8`
- `0x180009bfc`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_FailFastImmediate_Unexpected(wil::details::in1diag3 *this)
{
  __fastfail(7u);
}

```

## disassembly

```asm
0x18000bb7c  mov     ecx, 7
0x18000bb81  int     29h; Win8: RtlFailFast(ecx)
```
