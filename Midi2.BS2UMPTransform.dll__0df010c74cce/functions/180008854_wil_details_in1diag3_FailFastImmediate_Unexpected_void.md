# wil::details::in1diag3::_FailFastImmediate_Unexpected(void)

- ea: `0x180008854`
- end: `0x18000885b`
- name: `?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ`
- size: `7`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x180002e60`
- `0x1800038e8`
- `0x180004850`
- `0x180005cd0`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_FailFastImmediate_Unexpected(wil::details::in1diag3 *this)
{
  __fastfail(7u);
}

```

## disassembly

```asm
0x180008854  mov     ecx, 7
0x180008859  int     29h; Win8: RtlFailFast(ecx)
```
