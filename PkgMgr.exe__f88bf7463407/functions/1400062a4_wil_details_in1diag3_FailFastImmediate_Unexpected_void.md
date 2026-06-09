# wil::details::in1diag3::_FailFastImmediate_Unexpected(void)

- ea: `0x1400062a4`
- end: `0x1400062ab`
- name: `?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ`
- size: `7`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this)`
- caller_count: `7`
- callee_count: `0`
- tags: ``

## callers

- `0x140003640`
- `0x140004190`
- `0x140004f0c`
- `0x140005280`
- `0x14000f180`
- `0x140024bfc`
- `0x140025fb0`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_FailFastImmediate_Unexpected(wil::details::in1diag3 *this)
{
  __fastfail(7u);
}

```

## disassembly

```asm
0x1400062a4  mov     ecx, 7
0x1400062a9  int     29h; Win8: RtlFailFast(ecx)
```
