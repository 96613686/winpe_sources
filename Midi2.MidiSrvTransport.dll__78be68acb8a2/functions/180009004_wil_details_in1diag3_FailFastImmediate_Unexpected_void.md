# wil::details::in1diag3::_FailFastImmediate_Unexpected(void)

- ea: `0x180009004`
- end: `0x18000900b`
- name: `?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ`
- size: `7`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this)`
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x1800035b4`
- `0x180004038`
- `0x180004fa0`
- `0x180006430`
- `0x18000cdac`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_FailFastImmediate_Unexpected(wil::details::in1diag3 *this)
{
  __fastfail(7u);
}

```

## disassembly

```asm
0x180009004  mov     ecx, 7
0x180009009  int     29h; Win8: RtlFailFast(ecx)
```
