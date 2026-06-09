# wil::details::in1diag3::_FailFastImmediate_Unexpected(void)

- ea: `0x18000c664`
- end: `0x18000c66b`
- name: `?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ`
- size: `7`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x1800082cc`
- `0x180009280`
- `0x18000a2a0`
- `0x18000a60c`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_FailFastImmediate_Unexpected(wil::details::in1diag3 *this)
{
  __fastfail(7u);
}

```

## disassembly

```asm
0x18000c664  mov     ecx, 7
0x18000c669  int     29h; Win8: RtlFailFast(ecx)
```
