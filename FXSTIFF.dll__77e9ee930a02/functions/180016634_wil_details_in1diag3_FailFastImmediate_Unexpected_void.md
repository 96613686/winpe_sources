# wil::details::in1diag3::_FailFastImmediate_Unexpected(void)

- ea: `0x180016634`
- end: `0x18001663b`
- name: `?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ`
- size: `7`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x180010688`
- `0x180011df8`
- `0x180013298`
- `0x180014820`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_FailFastImmediate_Unexpected(wil::details::in1diag3 *this)
{
  __fastfail(7u);
}

```

## disassembly

```asm
0x180016634  mov     ecx, 7
0x180016639  int     29h; Win8: RtlFailFast(ecx)
```
