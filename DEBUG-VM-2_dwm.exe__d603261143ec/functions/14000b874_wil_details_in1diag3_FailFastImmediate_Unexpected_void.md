# wil::details::in1diag3::_FailFastImmediate_Unexpected(void)

- ea: `0x14000b874`
- end: `0x14000b87b`
- name: `?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ`
- size: `7`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this)`
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x1400047c8`
- `0x14000492c`
- `0x140006f40`
- `0x140007e14`
- `0x14000943c`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_FailFastImmediate_Unexpected(wil::details::in1diag3 *this)
{
  __fastfail(7u);
}

```

## disassembly

```asm
0x14000b874  mov     ecx, 7
0x14000b879  int     29h; Win8: RtlFailFast(ecx)
```
