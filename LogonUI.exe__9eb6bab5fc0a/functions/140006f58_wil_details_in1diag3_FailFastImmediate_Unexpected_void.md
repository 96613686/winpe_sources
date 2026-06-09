# wil::details::in1diag3::_FailFastImmediate_Unexpected(void)

- ea: `0x140006f58`
- end: `0x140006f5f`
- name: `?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ`
- size: `7`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x140004214`
- `0x1400050c4`
- `0x140005484`
- `0x1400055a8`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_FailFastImmediate_Unexpected(wil::details::in1diag3 *this)
{
  __fastfail(7u);
}

```

## disassembly

```asm
0x140006f58  mov     ecx, 7
0x140006f5d  int     29h; Win8: RtlFailFast(ecx)
```
