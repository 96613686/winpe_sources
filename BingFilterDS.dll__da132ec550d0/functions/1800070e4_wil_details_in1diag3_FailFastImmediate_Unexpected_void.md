# wil::details::in1diag3::_FailFastImmediate_Unexpected(void)

- ea: `0x1800070e4`
- end: `0x1800070eb`
- name: `?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ`
- size: `7`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this)`
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x1800034a0`
- `0x180003df0`
- `0x18000421c`
- `0x1800054b8`
- `0x180007eec`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_FailFastImmediate_Unexpected(wil::details::in1diag3 *this)
{
  __fastfail(7u);
}

```

## disassembly

```asm
0x1800070e4  mov     ecx, 7
0x1800070e9  int     29h; Win8: RtlFailFast(ecx)
```
