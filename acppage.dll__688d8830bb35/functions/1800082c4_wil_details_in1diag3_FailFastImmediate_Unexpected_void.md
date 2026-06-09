# wil::details::in1diag3::_FailFastImmediate_Unexpected(void)

- ea: `0x1800082c4`
- end: `0x1800082cb`
- name: `?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ`
- size: `7`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this)`
- caller_count: `6`
- callee_count: `0`
- tags: ``

## callers

- `0x180002b5c`
- `0x1800038a8`
- `0x180003c4c`
- `0x180004044`
- `0x180005794`
- `0x180006bcc`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_FailFastImmediate_Unexpected(wil::details::in1diag3 *this)
{
  __fastfail(7u);
}

```

## disassembly

```asm
0x1800082c4  mov     ecx, 7
0x1800082c9  int     29h; Win8: RtlFailFast(ecx)
```
