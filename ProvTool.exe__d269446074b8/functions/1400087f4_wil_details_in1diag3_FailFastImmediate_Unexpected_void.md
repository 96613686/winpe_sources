# wil::details::in1diag3::_FailFastImmediate_Unexpected(void)

- ea: `0x1400087f4`
- end: `0x1400087fb`
- name: `?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ`
- size: `7`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this)`
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x140002a34`
- `0x140002ce8`
- `0x140003de0`
- `0x140004d58`
- `0x140006df0`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_FailFastImmediate_Unexpected(wil::details::in1diag3 *this)
{
  __fastfail(7u);
}

```

## disassembly

```asm
0x1400087f4  mov     ecx, 7
0x1400087f9  int     29h; Win8: RtlFailFast(ecx)
```
