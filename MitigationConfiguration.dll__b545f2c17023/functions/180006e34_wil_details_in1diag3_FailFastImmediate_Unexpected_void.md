# wil::details::in1diag3::_FailFastImmediate_Unexpected(void)

- ea: `0x180006e34`
- end: `0x180006e3b`
- name: `?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ`
- size: `7`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x180002fa8`
- `0x1800038c8`
- `0x180003cd4`
- `0x1800054e0`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_FailFastImmediate_Unexpected(wil::details::in1diag3 *this)
{
  __fastfail(7u);
}

```

## disassembly

```asm
0x180006e34  mov     ecx, 7
0x180006e39  int     29h; Win8: RtlFailFast(ecx)
```
