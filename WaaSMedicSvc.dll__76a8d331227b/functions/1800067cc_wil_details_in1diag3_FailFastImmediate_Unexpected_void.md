# wil::details::in1diag3::_FailFastImmediate_Unexpected(void)

- ea: `0x1800067cc`
- end: `0x1800067d3`
- name: `?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ`
- size: `7`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this)`
- caller_count: `6`
- callee_count: `0`
- tags: ``

## callers

- `0x18000357c`
- `0x180003dd8`
- `0x1800041a8`
- `0x180005080`
- `0x18000750c`
- `0x1800094c0`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_FailFastImmediate_Unexpected(wil::details::in1diag3 *this)
{
  __fastfail(7u);
}

```

## disassembly

```asm
0x1800067cc  mov     ecx, 7
0x1800067d1  int     29h; Win8: RtlFailFast(ecx)
```
