# wil::details::in1diag3::_FailFastImmediate_Unexpected(void)

- ea: `0x180007d0c`
- end: `0x180007d13`
- name: `?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ`
- size: `7`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this)`
- caller_count: `6`
- callee_count: `0`
- tags: ``

## callers

- `0x180003598`
- `0x1800046d8`
- `0x180004ae4`
- `0x180005db0`
- `0x180008278`
- `0x18000ad54`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_FailFastImmediate_Unexpected(wil::details::in1diag3 *this)
{
  __fastfail(7u);
}

```

## disassembly

```asm
0x180007d0c  mov     ecx, 7
0x180007d11  int     29h; Win8: RtlFailFast(ecx)
```
