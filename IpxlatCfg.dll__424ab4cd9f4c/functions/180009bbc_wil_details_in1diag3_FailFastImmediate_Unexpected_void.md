# wil::details::in1diag3::_FailFastImmediate_Unexpected(void)

- ea: `0x180009bbc`
- end: `0x180009bc3`
- name: `?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ`
- size: `7`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this)`
- caller_count: `6`
- callee_count: `0`
- tags: ``

## callers

- `0x18000398c`
- `0x180004988`
- `0x180004d38`
- `0x180005114`
- `0x18000667c`
- `0x180007b7c`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_FailFastImmediate_Unexpected(wil::details::in1diag3 *this)
{
  __fastfail(7u);
}

```

## disassembly

```asm
0x180009bbc  mov     ecx, 7
0x180009bc1  int     29h; Win8: RtlFailFast(ecx)
```
