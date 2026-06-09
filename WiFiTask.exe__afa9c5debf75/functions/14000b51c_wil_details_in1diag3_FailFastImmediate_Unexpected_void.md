# wil::details::in1diag3::_FailFastImmediate_Unexpected(void)

- ea: `0x14000b51c`
- end: `0x14000b523`
- name: `?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ`
- size: `7`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this)`
- caller_count: `6`
- callee_count: `0`
- tags: ``

## callers

- `0x1400029ac`
- `0x140003e78`
- `0x14000421c`
- `0x140004600`
- `0x14000771c`
- `0x140008e4c`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_FailFastImmediate_Unexpected(wil::details::in1diag3 *this)
{
  __fastfail(7u);
}

```

## disassembly

```asm
0x14000b51c  mov     ecx, 7
0x14000b521  int     29h; Win8: RtlFailFast(ecx)
```
