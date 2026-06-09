# wil::details::in1diag3::_FailFastImmediate_Unexpected(void)

- ea: `0x18000669c`
- end: `0x1800066a3`
- name: `?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ`
- size: `7`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this)`
- caller_count: `6`
- callee_count: `0`
- tags: ``

## callers

- `0x180003548`
- `0x180003f90`
- `0x180004334`
- `0x1800051d4`
- `0x180007dd8`
- `0x180009f90`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_FailFastImmediate_Unexpected(wil::details::in1diag3 *this)
{
  __fastfail(7u);
}

```

## disassembly

```asm
0x18000669c  mov     ecx, 7
0x1800066a1  int     29h; Win8: RtlFailFast(ecx)
```
