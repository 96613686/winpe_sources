# wil::details::in1diag4::_FailFastImmediate_Unexpected(void)

- ea: `0x140006008`
- end: `0x14000600f`
- name: `?_FailFastImmediate_Unexpected@in1diag4@details@wil@@YAXXZ`
- size: `7`
- prototype: `void __fastcall __noreturn(wil::details::in1diag4 *__hidden this)`
- caller_count: `6`
- callee_count: `0`
- tags: ``

## callers

- `0x140004e28`
- `0x14000835c`
- `0x140008f9c`
- `0x14000936c`
- `0x140009764`
- `0x14000b804`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag4::_FailFastImmediate_Unexpected(wil::details::in1diag4 *this)
{
  __fastfail(7u);
}

```

## disassembly

```asm
0x140006008  mov     ecx, 7
0x14000600d  int     29h; Win8: RtlFailFast(ecx)
```
