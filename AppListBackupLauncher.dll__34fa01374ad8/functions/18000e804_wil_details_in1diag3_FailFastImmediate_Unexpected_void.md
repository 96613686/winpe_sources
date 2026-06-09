# wil::details::in1diag3::_FailFastImmediate_Unexpected(void)

- ea: `0x18000e804`
- end: `0x18000e80b`
- name: `?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ`
- size: `7`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this)`
- caller_count: `7`
- callee_count: `0`
- tags: ``

## callers

- `0x180003cbc`
- `0x180003f78`
- `0x1800068a8`
- `0x180006c4c`
- `0x180007084`
- `0x1800092b0`
- `0x18000afdc`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_FailFastImmediate_Unexpected(wil::details::in1diag3 *this)
{
  __fastfail(7u);
}

```

## disassembly

```asm
0x18000e804  mov     ecx, 7
0x18000e809  int     29h; Win8: RtlFailFast(ecx)
```
