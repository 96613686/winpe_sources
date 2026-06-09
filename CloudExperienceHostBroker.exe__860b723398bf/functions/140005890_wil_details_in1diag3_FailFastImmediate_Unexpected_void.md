# wil::details::in1diag3::_FailFastImmediate_Unexpected(void)

- ea: `0x140005890`
- end: `0x140005897`
- name: `?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ`
- size: `7`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x140002b1c`
- `0x14000361c`
- `0x14000436c`
- `0x1400046d4`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_FailFastImmediate_Unexpected(wil::details::in1diag3 *this)
{
  __fastfail(7u);
}

```

## disassembly

```asm
0x140005890  mov     ecx, 7
0x140005895  int     29h; Win8: RtlFailFast(ecx)
```
