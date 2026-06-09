# wil::details::in1diag3::_FailFastImmediate_Unexpected(void)

- ea: `0x18000ab0c`
- end: `0x18000ab13`
- name: `?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ`
- size: `7`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this)`
- caller_count: `6`
- callee_count: `0`
- tags: ``

## callers

- `0x18000290c`
- `0x180003940`
- `0x180003ce4`
- `0x180004140`
- `0x1800069f0`
- `0x180007f30`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_FailFastImmediate_Unexpected(wil::details::in1diag3 *this)
{
  __fastfail(7u);
}

```

## disassembly

```asm
0x18000ab0c  mov     ecx, 7
0x18000ab11  int     29h; Win8: RtlFailFast(ecx)
```
