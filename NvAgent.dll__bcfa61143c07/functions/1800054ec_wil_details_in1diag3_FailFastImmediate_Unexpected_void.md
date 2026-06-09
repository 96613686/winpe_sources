# wil::details::in1diag3::_FailFastImmediate_Unexpected(void)

- ea: `0x1800054ec`
- end: `0x1800054f3`
- name: `?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ`
- size: `7`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this)`
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x1800024dc`
- `0x180002d18`
- `0x1800030bc`
- `0x180003f64`
- `0x180005824`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_FailFastImmediate_Unexpected(wil::details::in1diag3 *this)
{
  __fastfail(7u);
}

```

## disassembly

```asm
0x1800054ec  mov     ecx, 7
0x1800054f1  int     29h; Win8: RtlFailFast(ecx)
```
