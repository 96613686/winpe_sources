# wil::details::in1diag3::_FailFastImmediate_Unexpected(void)

- ea: `0x1400054ec`
- end: `0x1400054f3`
- name: `?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ`
- size: `7`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this)`
- caller_count: `6`
- callee_count: `0`
- tags: ``

## callers

- `0x140002b9c`
- `0x1400030b0`
- `0x140003474`
- `0x140004480`
- `0x1400063bc`
- `0x140010a9c`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_FailFastImmediate_Unexpected(wil::details::in1diag3 *this)
{
  __fastfail(7u);
}

```

## disassembly

```asm
0x1400054ec  mov     ecx, 7
0x1400054f1  int     29h; Win8: RtlFailFast(ecx)
```
