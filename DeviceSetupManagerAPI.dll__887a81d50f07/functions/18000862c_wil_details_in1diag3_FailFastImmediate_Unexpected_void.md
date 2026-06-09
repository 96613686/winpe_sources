# wil::details::in1diag3::_FailFastImmediate_Unexpected(void)

- ea: `0x18000862c`
- end: `0x180008633`
- name: `?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ`
- size: `7`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this)`
- caller_count: `6`
- callee_count: `0`
- tags: ``

## callers

- `0x180002d44`
- `0x180003bf8`
- `0x180003f9c`
- `0x18000436c`
- `0x180005724`
- `0x18000693c`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_FailFastImmediate_Unexpected(wil::details::in1diag3 *this)
{
  __fastfail(7u);
}

```

## disassembly

```asm
0x18000862c  mov     ecx, 7
0x180008631  int     29h; Win8: RtlFailFast(ecx)
```
