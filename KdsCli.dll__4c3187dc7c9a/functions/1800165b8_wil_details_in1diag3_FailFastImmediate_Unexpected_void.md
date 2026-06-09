# wil::details::in1diag3::_FailFastImmediate_Unexpected(void)

- ea: `0x1800165b8`
- end: `0x1800165bf`
- name: `?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ`
- size: `7`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this)`
- caller_count: `6`
- callee_count: `0`
- tags: ``

## callers

- `0x180011768`
- `0x18001223c`
- `0x1800125e0`
- `0x1800129b0`
- `0x180013e58`
- `0x180014f88`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_FailFastImmediate_Unexpected(wil::details::in1diag3 *this)
{
  __fastfail(7u);
}

```

## disassembly

```asm
0x1800165b8  mov     ecx, 7
0x1800165bd  int     29h; Win8: RtlFailFast(ecx)
```
