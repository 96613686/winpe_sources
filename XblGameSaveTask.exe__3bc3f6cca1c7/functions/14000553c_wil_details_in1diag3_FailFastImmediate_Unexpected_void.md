# wil::details::in1diag3::_FailFastImmediate_Unexpected(void)

- ea: `0x14000553c`
- end: `0x140005543`
- name: `?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ`
- size: `7`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x140002524`
- `0x140002d58`
- `0x1400030fc`
- `0x140003fa8`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_FailFastImmediate_Unexpected(wil::details::in1diag3 *this)
{
  __fastfail(7u);
}

```

## disassembly

```asm
0x14000553c  mov     ecx, 7
0x140005541  int     29h; Win8: RtlFailFast(ecx)
```
