# wil::details::in1diag3::_FailFastImmediate_Unexpected(void)

- ea: `0x180015b5c`
- end: `0x180015b63`
- name: `?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ`
- size: `7`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this)`
- caller_count: `6`
- callee_count: `0`
- tags: ``

## callers

- `0x18000fecc`
- `0x180010f58`
- `0x180011324`
- `0x180011708`
- `0x180012b9c`
- `0x180013f90`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_FailFastImmediate_Unexpected(wil::details::in1diag3 *this)
{
  __fastfail(7u);
}

```

## disassembly

```asm
0x180015b5c  mov     ecx, 7
0x180015b61  int     29h; Win8: RtlFailFast(ecx)
```
