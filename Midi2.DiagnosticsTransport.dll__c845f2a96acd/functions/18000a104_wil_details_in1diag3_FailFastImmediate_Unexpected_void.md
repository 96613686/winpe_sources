# wil::details::in1diag3::_FailFastImmediate_Unexpected(void)

- ea: `0x18000a104`
- end: `0x18000a10b`
- name: `?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ`
- size: `7`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x180004714`
- `0x180005198`
- `0x180006100`
- `0x180007580`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_FailFastImmediate_Unexpected(wil::details::in1diag3 *this)
{
  __fastfail(7u);
}

```

## disassembly

```asm
0x18000a104  mov     ecx, 7
0x18000a109  int     29h; Win8: RtlFailFast(ecx)
```
