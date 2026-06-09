# wil::details::in1diag3::_FailFastImmediate_Unexpected(void)

- ea: `0x180006958`
- end: `0x18000695f`
- name: `?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ`
- size: `7`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this)`
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x180003f18`
- `0x1800059f0`
- `0x1800073b8`
- `0x180007790`
- `0x18000bccc`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_FailFastImmediate_Unexpected(wil::details::in1diag3 *this)
{
  __fastfail(7u);
}

```

## disassembly

```asm
0x180006958  mov     ecx, 7
0x18000695d  int     29h; Win8: RtlFailFast(ecx)
```
