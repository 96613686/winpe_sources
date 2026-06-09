# wil::details::in1diag3::_FailFastImmediate_Unexpected(void)

- ea: `0x14000492c`
- end: `0x140004933`
- name: `?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ`
- size: `7`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x140001fe0`
- `0x1400024f4`
- `0x140002898`
- `0x140003740`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_FailFastImmediate_Unexpected(wil::details::in1diag3 *this)
{
  __fastfail(7u);
}

```

## disassembly

```asm
0x14000492c  mov     ecx, 7
0x140004931  int     29h; Win8: RtlFailFast(ecx)
```
