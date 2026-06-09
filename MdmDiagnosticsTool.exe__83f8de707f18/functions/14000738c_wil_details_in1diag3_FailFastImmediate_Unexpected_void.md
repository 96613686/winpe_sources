# wil::details::in1diag3::_FailFastImmediate_Unexpected(void)

- ea: `0x14000738c`
- end: `0x140007393`
- name: `?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ`
- size: `7`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x14000289c`
- `0x140003b00`
- `0x1400055b8`
- `0x140005934`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_FailFastImmediate_Unexpected(wil::details::in1diag3 *this)
{
  __fastfail(7u);
}

```

## disassembly

```asm
0x14000738c  mov     ecx, 7
0x140007391  int     29h; Win8: RtlFailFast(ecx)
```
