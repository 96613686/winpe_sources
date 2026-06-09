# wil::details::in1diag3::_FailFastImmediate_Unexpected(void)

- ea: `0x140004a00`
- end: `0x140004a07`
- name: `?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ`
- size: `7`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x140002364`
- `0x140002bc0`
- `0x140003918`
- `0x140003c80`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_FailFastImmediate_Unexpected(wil::details::in1diag3 *this)
{
  __fastfail(7u);
}

```

## disassembly

```asm
0x140004a00  mov     ecx, 7
0x140004a05  int     29h; Win8: RtlFailFast(ecx)
```
