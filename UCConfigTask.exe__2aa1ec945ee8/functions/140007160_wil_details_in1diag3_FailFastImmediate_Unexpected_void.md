# wil::details::in1diag3::_FailFastImmediate_Unexpected(void)

- ea: `0x140007160`
- end: `0x140007167`
- name: `?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ`
- size: `7`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this)`
- caller_count: `6`
- callee_count: `0`
- tags: ``

## callers

- `0x140002594`
- `0x1400037b0`
- `0x1400048cc`
- `0x140004a0c`
- `0x140004e38`
- `0x140004f68`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_FailFastImmediate_Unexpected(wil::details::in1diag3 *this)
{
  __fastfail(7u);
}

```

## disassembly

```asm
0x140007160  mov     ecx, 7
0x140007165  int     29h; Win8: RtlFailFast(ecx)
```
