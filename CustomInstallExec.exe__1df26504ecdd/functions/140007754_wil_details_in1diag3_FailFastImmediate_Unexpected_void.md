# wil::details::in1diag3::_FailFastImmediate_Unexpected(void)

- ea: `0x140007754`
- end: `0x14000775b`
- name: `?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ`
- size: `7`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x140004be4`
- `0x1400056e8`
- `0x140006460`
- `0x1400067b0`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_FailFastImmediate_Unexpected(wil::details::in1diag3 *this)
{
  __fastfail(7u);
}

```

## disassembly

```asm
0x140007754  mov     ecx, 7
0x140007759  int     29h; Win8: RtlFailFast(ecx)
```
