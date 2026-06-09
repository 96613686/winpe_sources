# wil::details::in1diag3::_FailFastImmediate_Unexpected(void)

- ea: `0x18000aafc`
- end: `0x18000ab03`
- name: `?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ`
- size: `7`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this)`
- caller_count: `6`
- callee_count: `0`
- tags: ``

## callers

- `0x180005298`
- `0x1800060bc`
- `0x180006460`
- `0x180006830`
- `0x180007bf4`
- `0x180008e0c`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_FailFastImmediate_Unexpected(wil::details::in1diag3 *this)
{
  __fastfail(7u);
}

```

## disassembly

```asm
0x18000aafc  mov     ecx, 7
0x18000ab01  int     29h; Win8: RtlFailFast(ecx)
```
