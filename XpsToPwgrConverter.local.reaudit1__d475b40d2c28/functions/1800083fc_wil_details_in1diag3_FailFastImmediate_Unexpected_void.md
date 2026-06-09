# wil::details::in1diag3::_FailFastImmediate_Unexpected(void)

- ea: `0x1800083fc`
- end: `0x180008403`
- name: `?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ`
- size: `7`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this)`
- caller_count: `7`
- callee_count: `0`
- tags: ``

## callers

- `0x18000295c`
- `0x180003818`
- `0x180003bbc`
- `0x180003f8c`
- `0x180005344`
- `0x18000659c`
- `0x180008f08`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_FailFastImmediate_Unexpected(wil::details::in1diag3 *this)
{
  __fastfail(7u);
}

```

## disassembly

```asm
0x1800083fc  mov     ecx, 7
0x180008401  int     29h; Win8: RtlFailFast(ecx)
```
