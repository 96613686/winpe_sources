# wil::details::in1diag3::_FailFastImmediate_Unexpected(void)

- ea: `0x1800086ec`
- end: `0x1800086f3`
- name: `?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ`
- size: `7`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this)`
- caller_count: `6`
- callee_count: `0`
- tags: ``

## callers

- `0x180002f64`
- `0x180003bc4`
- `0x180003f94`
- `0x18000438c`
- `0x18000591c`
- `0x180006d88`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_FailFastImmediate_Unexpected(wil::details::in1diag3 *this)
{
  __fastfail(7u);
}

```

## disassembly

```asm
0x1800086ec  mov     ecx, 7
0x1800086f1  int     29h; Win8: RtlFailFast(ecx)
```
