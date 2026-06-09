# wil::details::in1diag3::_FailFastImmediate_Unexpected(void)

- ea: `0x1800060bc`
- end: `0x1800060c3`
- name: `?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ`
- size: `7`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this)`
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x180002f64`
- `0x1800037a8`
- `0x180003b10`
- `0x1800049c4`
- `0x1800067fc`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_FailFastImmediate_Unexpected(wil::details::in1diag3 *this)
{
  __fastfail(7u);
}

```

## disassembly

```asm
0x1800060bc  mov     ecx, 7
0x1800060c1  int     29h; Win8: RtlFailFast(ecx)
```
