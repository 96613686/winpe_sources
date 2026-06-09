# wil::details::in1diag3::_FailFastImmediate_Unexpected(void)

- ea: `0x18000916c`
- end: `0x180009173`
- name: `?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ`
- size: `7`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this)`
- caller_count: `6`
- callee_count: `0`
- tags: ``

## callers

- `0x180002aa0`
- `0x180003b08`
- `0x180003eac`
- `0x18000427c`
- `0x1800059ac`
- `0x18000701c`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_FailFastImmediate_Unexpected(wil::details::in1diag3 *this)
{
  __fastfail(7u);
}

```

## disassembly

```asm
0x18000916c  mov     ecx, 7
0x180009171  int     29h; Win8: RtlFailFast(ecx)
```
