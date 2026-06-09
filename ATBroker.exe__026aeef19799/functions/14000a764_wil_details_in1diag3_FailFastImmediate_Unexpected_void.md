# wil::details::in1diag3::_FailFastImmediate_Unexpected(void)

- ea: `0x14000a764`
- end: `0x14000a76b`
- name: `?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ`
- size: `7`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this)`
- caller_count: `6`
- callee_count: `0`
- tags: ``

## callers

- `0x1400032a4`
- `0x1400040c8`
- `0x140004498`
- `0x140004974`
- `0x140006e5c`
- `0x1400086cc`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_FailFastImmediate_Unexpected(wil::details::in1diag3 *this)
{
  __fastfail(7u);
}

```

## disassembly

```asm
0x14000a764  mov     ecx, 7
0x14000a769  int     29h; Win8: RtlFailFast(ecx)
```
