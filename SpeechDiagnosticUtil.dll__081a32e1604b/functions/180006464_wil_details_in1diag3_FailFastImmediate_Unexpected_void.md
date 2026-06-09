# wil::details::in1diag3::_FailFastImmediate_Unexpected(void)

- ea: `0x180006464`
- end: `0x18000646b`
- name: `?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ`
- size: `7`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x180003ae0`
- `0x1800050a0`
- `0x180005434`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_FailFastImmediate_Unexpected(wil::details::in1diag3 *this)
{
  __fastfail(7u);
}

```

## disassembly

```asm
0x180006464  mov     ecx, 7
0x180006469  int     29h; Win8: RtlFailFast(ecx)
```
