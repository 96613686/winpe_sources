# wil::details::in1diag3::_FailFastImmediate_Unexpected(void)

- ea: `0x180009aec`
- end: `0x180009af3`
- name: `?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ`
- size: `7`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this)`
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x180007b28`
- `0x180008aa0`
- `0x18000983c`
- `0x180009990`
- `0x18000a780`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_FailFastImmediate_Unexpected(wil::details::in1diag3 *this)
{
  __fastfail(7u);
}

```

## disassembly

```asm
0x180009aec  mov     ecx, 7
0x180009af1  int     29h; Win8: RtlFailFast(ecx)
```
