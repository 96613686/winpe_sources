# wil::details::in1diag3::_FailFastImmediate_Unexpected(void)

- ea: `0x14000ecd4`
- end: `0x14000ecdb`
- name: `?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ`
- size: `7`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this)`
- caller_count: `6`
- callee_count: `0`
- tags: ``

## callers

- `0x1400073ac`
- `0x140009088`
- `0x14000942c`
- `0x14000992c`
- `0x14000b5b4`
- `0x14000cb30`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_FailFastImmediate_Unexpected(wil::details::in1diag3 *this)
{
  __fastfail(7u);
}

```

## disassembly

```asm
0x14000ecd4  mov     ecx, 7
0x14000ecd9  int     29h; Win8: RtlFailFast(ecx)
```
