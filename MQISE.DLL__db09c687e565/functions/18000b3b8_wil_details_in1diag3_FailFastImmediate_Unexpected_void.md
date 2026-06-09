# wil::details::in1diag3::_FailFastImmediate_Unexpected(void)

- ea: `0x18000b3b8`
- end: `0x18000b3bf`
- name: `?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ`
- size: `7`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this)`
- caller_count: `6`
- callee_count: `0`
- tags: ``

## callers

- `0x1800027cc`
- `0x1800044a8`
- `0x18000487c`
- `0x180005310`
- `0x1800075e0`
- `0x180008ed8`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_FailFastImmediate_Unexpected(wil::details::in1diag3 *this)
{
  __fastfail(7u);
}

```

## disassembly

```asm
0x18000b3b8  mov     ecx, 7
0x18000b3bd  int     29h; Win8: RtlFailFast(ecx)
```
