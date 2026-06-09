# wil::details::in1diag3::_FailFastImmediate_Unexpected(void)

- ea: `0x14000572c`
- end: `0x140005733`
- name: `?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ`
- size: `7`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this)`
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x1400024e0`
- `0x140002d28`
- `0x1400030f8`
- `0x140003fd8`
- `0x140005a64`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_FailFastImmediate_Unexpected(wil::details::in1diag3 *this)
{
  __fastfail(7u);
}

```

## disassembly

```asm
0x14000572c  mov     ecx, 7
0x140005731  int     29h; Win8: RtlFailFast(ecx)
```
