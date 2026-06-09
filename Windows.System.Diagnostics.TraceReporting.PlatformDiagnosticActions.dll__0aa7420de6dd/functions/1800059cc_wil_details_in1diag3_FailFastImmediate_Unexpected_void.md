# wil::details::in1diag3::_FailFastImmediate_Unexpected(void)

- ea: `0x1800059cc`
- end: `0x1800059d3`
- name: `?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ`
- size: `7`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x1800027d4`
- `0x180003018`
- `0x1800033e8`
- `0x1800042b8`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_FailFastImmediate_Unexpected(wil::details::in1diag3 *this)
{
  __fastfail(7u);
}

```

## disassembly

```asm
0x1800059cc  mov     ecx, 7
0x1800059d1  int     29h; Win8: RtlFailFast(ecx)
```
