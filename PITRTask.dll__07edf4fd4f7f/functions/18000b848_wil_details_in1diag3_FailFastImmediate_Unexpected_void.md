# wil::details::in1diag3::_FailFastImmediate_Unexpected(void)

- ea: `0x18000b848`
- end: `0x18000b84f`
- name: `?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ`
- size: `7`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this)`
- caller_count: `6`
- callee_count: `0`
- tags: ``

## callers

- `0x180002b7c`
- `0x180003eb0`
- `0x180004254`
- `0x1800046b0`
- `0x180006ae0`
- `0x180008020`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_FailFastImmediate_Unexpected(wil::details::in1diag3 *this)
{
  __fastfail(7u);
}

```

## disassembly

```asm
0x18000b848  mov     ecx, 7
0x18000b84d  int     29h; Win8: RtlFailFast(ecx)
```
