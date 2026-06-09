# wil::details::in1diag3::_FailFastImmediate_Unexpected(void)

- ea: `0x140006abc`
- end: `0x140006ac3`
- name: `?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ`
- size: `7`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x1400044c4`
- `0x1400049d0`
- `0x140004da0`
- `0x140005cd4`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_FailFastImmediate_Unexpected(wil::details::in1diag3 *this)
{
  __fastfail(7u);
}

```

## disassembly

```asm
0x140006abc  mov     ecx, 7
0x140006ac1  int     29h; Win8: RtlFailFast(ecx)
```
