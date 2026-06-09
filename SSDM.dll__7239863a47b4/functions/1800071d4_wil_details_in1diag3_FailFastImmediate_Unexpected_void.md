# wil::details::in1diag3::_FailFastImmediate_Unexpected(void)

- ea: `0x1800071d4`
- end: `0x1800071db`
- name: `?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ`
- size: `7`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this)`
- caller_count: `6`
- callee_count: `0`
- tags: ``

## callers

- `0x18000387c`
- `0x180003b30`
- `0x180006468`
- `0x180007a20`
- `0x180008080`
- `0x18000845c`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_FailFastImmediate_Unexpected(wil::details::in1diag3 *this)
{
  __fastfail(7u);
}

```

## disassembly

```asm
0x1800071d4  mov     ecx, 7
0x1800071d9  int     29h; Win8: RtlFailFast(ecx)
```
