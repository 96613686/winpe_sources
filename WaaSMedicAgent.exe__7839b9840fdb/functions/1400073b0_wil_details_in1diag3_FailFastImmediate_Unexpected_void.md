# wil::details::in1diag3::_FailFastImmediate_Unexpected(void)

- ea: `0x1400073b0`
- end: `0x1400073b7`
- name: `?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ`
- size: `7`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this)`
- caller_count: `6`
- callee_count: `0`
- tags: ``

## callers

- `0x140003e3c`
- `0x1400048f8`
- `0x140004cc8`
- `0x140005d34`
- `0x14000c164`
- `0x14000dcc4`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_FailFastImmediate_Unexpected(wil::details::in1diag3 *this)
{
  __fastfail(7u);
}

```

## disassembly

```asm
0x1400073b0  mov     ecx, 7
0x1400073b5  int     29h; Win8: RtlFailFast(ecx)
```
