# wil::details::in1diag3::_FailFastImmediate_Unexpected(void)

- ea: `0x180006efc`
- end: `0x180006f03`
- name: `?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ`
- size: `7`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x1800035cc`
- `0x180003ff8`
- `0x18000439c`
- `0x18000525c`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_FailFastImmediate_Unexpected(wil::details::in1diag3 *this)
{
  __fastfail(7u);
}

```

## disassembly

```asm
0x180006efc  mov     ecx, 7
0x180006f01  int     29h; Win8: RtlFailFast(ecx)
```
