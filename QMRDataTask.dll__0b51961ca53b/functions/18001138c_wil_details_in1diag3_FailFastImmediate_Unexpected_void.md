# wil::details::in1diag3::_FailFastImmediate_Unexpected(void)

- ea: `0x18001138c`
- end: `0x180011393`
- name: `?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ`
- size: `7`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this)`
- caller_count: `6`
- callee_count: `0`
- tags: ``

## callers

- `0x180004d4c`
- `0x180006108`
- `0x1800064ac`
- `0x180007134`
- `0x18000bb60`
- `0x18000d5a0`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_FailFastImmediate_Unexpected(wil::details::in1diag3 *this)
{
  __fastfail(7u);
}

```

## disassembly

```asm
0x18001138c  mov     ecx, 7
0x180011391  int     29h; Win8: RtlFailFast(ecx)
```
