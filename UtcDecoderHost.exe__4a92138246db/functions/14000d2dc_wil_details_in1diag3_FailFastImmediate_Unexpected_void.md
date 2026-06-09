# wil::details::in1diag3::_FailFastImmediate_Unexpected(void)

- ea: `0x14000d2dc`
- end: `0x14000d2e3`
- name: `?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ`
- size: `7`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this)`
- caller_count: `9`
- callee_count: `0`
- tags: ``

## callers

- `0x140009c40`
- `0x140009eec`
- `0x14000aac8`
- `0x14000aea4`
- `0x14000e318`
- `0x14000e5cc`
- `0x14000e864`
- `0x14001373c`
- `0x140015230`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_FailFastImmediate_Unexpected(wil::details::in1diag3 *this)
{
  __fastfail(7u);
}

```

## disassembly

```asm
0x14000d2dc  mov     ecx, 7
0x14000d2e1  int     29h; Win8: RtlFailFast(ecx)
```
