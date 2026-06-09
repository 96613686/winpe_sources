# wil::details::in1diag3::_FailFastImmediate_Unexpected(void)

- ea: `0x18000716c`
- end: `0x180007173`
- name: `?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ`
- size: `7`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this)`
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x180003a08`
- `0x1800042e8`
- `0x180004694`
- `0x180005778`
- `0x180007e0c`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_FailFastImmediate_Unexpected(wil::details::in1diag3 *this)
{
  __fastfail(7u);
}

```

## disassembly

```asm
0x18000716c  mov     ecx, 7
0x180007171  int     29h; Win8: RtlFailFast(ecx)
```
