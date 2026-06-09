# wil::details::in1diag3::_FailFastImmediate_Unexpected(void)

- ea: `0x180009ac4`
- end: `0x180009acb`
- name: `?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ`
- size: `7`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x1800040d8`
- `0x180004b58`
- `0x180005ac0`
- `0x180006f40`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_FailFastImmediate_Unexpected(wil::details::in1diag3 *this)
{
  __fastfail(7u);
}

```

## disassembly

```asm
0x180009ac4  mov     ecx, 7
0x180009ac9  int     29h; Win8: RtlFailFast(ecx)
```
