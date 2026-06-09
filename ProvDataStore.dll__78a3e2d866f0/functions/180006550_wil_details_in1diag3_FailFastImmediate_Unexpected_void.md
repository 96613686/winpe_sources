# wil::details::in1diag3::_FailFastImmediate_Unexpected(void)

- ea: `0x180006550`
- end: `0x180006557`
- name: `?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ`
- size: `7`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this)`
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x180002cbc`
- `0x180003670`
- `0x180003a9c`
- `0x180004be8`
- `0x1800080b4`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_FailFastImmediate_Unexpected(wil::details::in1diag3 *this)
{
  __fastfail(7u);
}

```

## disassembly

```asm
0x180006550  mov     ecx, 7
0x180006555  int     29h; Win8: RtlFailFast(ecx)
```
