# wil::details::in1diag3::_FailFastImmediate_Unexpected(void)

- ea: `0x18001b054`
- end: `0x18001b05b`
- name: `?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ`
- size: `7`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x1800183c8`
- `0x180018ca8`
- `0x1800199e0`
- `0x180019d60`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_FailFastImmediate_Unexpected(wil::details::in1diag3 *this)
{
  __fastfail(7u);
}

```

## disassembly

```asm
0x18001b054  mov     ecx, 7
0x18001b059  int     29h; Win8: RtlFailFast(ecx)
```
