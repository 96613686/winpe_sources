# wil::details::in1diag3::_FailFastImmediate_Unexpected(void)

- ea: `0x18000870c`
- end: `0x180008713`
- name: `?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ`
- size: `7`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this)`
- caller_count: `7`
- callee_count: `0`
- tags: ``

## callers

- `0x180002a00`
- `0x180003ab8`
- `0x180003e5c`
- `0x18000422c`
- `0x1800055e4`
- `0x18000683c`
- `0x1800091c8`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_FailFastImmediate_Unexpected(wil::details::in1diag3 *this)
{
  __fastfail(7u);
}

```

## disassembly

```asm
0x18000870c  mov     ecx, 7
0x180008711  int     29h; Win8: RtlFailFast(ecx)
```
