# wil::details::in1diag3::_FailFastImmediate_Unexpected(void)

- ea: `0x180007198`
- end: `0x18000719f`
- name: `?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ`
- size: `7`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this)`
- caller_count: `7`
- callee_count: `0`
- tags: ``

## callers

- `0x180003d68`
- `0x1800045b8`
- `0x180004988`
- `0x1800059c4`
- `0x180007b9c`
- `0x18000896c`
- `0x18000b264`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_FailFastImmediate_Unexpected(wil::details::in1diag3 *this)
{
  __fastfail(7u);
}

```

## disassembly

```asm
0x180007198  mov     ecx, 7
0x18000719d  int     29h; Win8: RtlFailFast(ecx)
```
