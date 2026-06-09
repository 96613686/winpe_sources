# wil::details::in1diag3::_FailFastImmediate_Unexpected(void)

- ea: `0x1800088e4`
- end: `0x1800088eb`
- name: `?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ`
- size: `7`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x180002ef0`
- `0x180003978`
- `0x1800048e0`
- `0x180005d60`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_FailFastImmediate_Unexpected(wil::details::in1diag3 *this)
{
  __fastfail(7u);
}

```

## disassembly

```asm
0x1800088e4  mov     ecx, 7
0x1800088e9  int     29h; Win8: RtlFailFast(ecx)
```
