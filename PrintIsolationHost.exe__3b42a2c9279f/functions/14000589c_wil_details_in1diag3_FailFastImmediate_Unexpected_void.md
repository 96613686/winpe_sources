# wil::details::in1diag3::_FailFastImmediate_Unexpected(void)

- ea: `0x14000589c`
- end: `0x1400058a3`
- name: `?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ`
- size: `7`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x140002c64`
- `0x14000323c`
- `0x1400035e0`
- `0x140004598`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_FailFastImmediate_Unexpected(wil::details::in1diag3 *this)
{
  __fastfail(7u);
}

```

## disassembly

```asm
0x14000589c  mov     ecx, 7
0x1400058a1  int     29h; Win8: RtlFailFast(ecx)
```
