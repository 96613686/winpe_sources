# wil::details::in1diag3::_FailFastImmediate_Unexpected(void)

- ea: `0x1800057d4`
- end: `0x1800057db`
- name: `?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ`
- size: `7`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this)`
- caller_count: `6`
- callee_count: `0`
- tags: ``

## callers

- `0x180002854`
- `0x1800030a0`
- `0x180003470`
- `0x180004338`
- `0x180009ed8`
- `0x18000d7f0`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_FailFastImmediate_Unexpected(wil::details::in1diag3 *this)
{
  __fastfail(7u);
}

```

## disassembly

```asm
0x1800057d4  mov     ecx, 7
0x1800057d9  int     29h; Win8: RtlFailFast(ecx)
```
