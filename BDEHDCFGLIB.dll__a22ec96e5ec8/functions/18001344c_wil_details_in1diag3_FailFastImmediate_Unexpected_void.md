# wil::details::in1diag3::_FailFastImmediate_Unexpected(void)

- ea: `0x18001344c`
- end: `0x180013453`
- name: `?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ`
- size: `7`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x180010ec8`
- `0x1800113dc`
- `0x180011780`
- `0x180012640`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_FailFastImmediate_Unexpected(wil::details::in1diag3 *this)
{
  __fastfail(7u);
}

```

## disassembly

```asm
0x18001344c  mov     ecx, 7
0x180013451  int     29h; Win8: RtlFailFast(ecx)
```
