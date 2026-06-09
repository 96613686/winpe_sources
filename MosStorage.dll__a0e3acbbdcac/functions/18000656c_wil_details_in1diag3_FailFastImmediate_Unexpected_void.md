# wil::details::in1diag3::_FailFastImmediate_Unexpected(void)

- ea: `0x18000656c`
- end: `0x180006573`
- name: `?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ`
- size: `7`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x1800033e4`
- `0x180003c14`
- `0x180003fb8`
- `0x180004e74`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_FailFastImmediate_Unexpected(wil::details::in1diag3 *this)
{
  __fastfail(7u);
}

```

## disassembly

```asm
0x18000656c  mov     ecx, 7
0x180006571  int     29h; Win8: RtlFailFast(ecx)
```
