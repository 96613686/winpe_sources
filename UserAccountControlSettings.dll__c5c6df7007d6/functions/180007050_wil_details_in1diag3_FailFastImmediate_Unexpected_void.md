# wil::details::in1diag3::_FailFastImmediate_Unexpected(void)

- ea: `0x180007050`
- end: `0x180007057`
- name: `?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ`
- size: `7`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x1800045d4`
- `0x180004fb0`
- `0x180005e30`
- `0x1800061a0`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_FailFastImmediate_Unexpected(wil::details::in1diag3 *this)
{
  __fastfail(7u);
}

```

## disassembly

```asm
0x180007050  mov     ecx, 7
0x180007055  int     29h; Win8: RtlFailFast(ecx)
```
