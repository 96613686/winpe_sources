# wil::details::in1diag3::_FailFastImmediate_Unexpected(void)

- ea: `0x180009c9c`
- end: `0x180009ca3`
- name: `?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ`
- size: `7`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this)`
- caller_count: `6`
- callee_count: `0`
- tags: ``

## callers

- `0x180004e98`
- `0x18000596c`
- `0x180005d10`
- `0x1800060e0`
- `0x1800074a0`
- `0x180008648`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_FailFastImmediate_Unexpected(wil::details::in1diag3 *this)
{
  __fastfail(7u);
}

```

## disassembly

```asm
0x180009c9c  mov     ecx, 7
0x180009ca1  int     29h; Win8: RtlFailFast(ecx)
```
