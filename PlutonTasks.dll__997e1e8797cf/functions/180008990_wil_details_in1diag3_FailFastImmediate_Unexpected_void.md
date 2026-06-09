# wil::details::in1diag3::_FailFastImmediate_Unexpected(void)

- ea: `0x180008990`
- end: `0x180008997`
- name: `?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ`
- size: `7`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x180004084`
- `0x180005940`
- `0x180005d50`
- `0x180005e74`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_FailFastImmediate_Unexpected(wil::details::in1diag3 *this)
{
  __fastfail(7u);
}

```

## disassembly

```asm
0x180008990  mov     ecx, 7
0x180008995  int     29h; Win8: RtlFailFast(ecx)
```
