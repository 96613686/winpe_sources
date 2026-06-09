# wil::details::in1diag3::_FailFastImmediate_Unexpected(void)

- ea: `0x14000cd74`
- end: `0x14000cd7b`
- name: `?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ`
- size: `7`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this)`
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x140008668`
- `0x1400087cc`
- `0x14000a648`
- `0x14000b1a4`
- `0x14000bcfc`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_FailFastImmediate_Unexpected(wil::details::in1diag3 *this)
{
  __fastfail(7u);
}

```

## disassembly

```asm
0x14000cd74  mov     ecx, 7
0x14000cd79  int     29h; Win8: RtlFailFast(ecx)
```
