# wil::details::in1diag3::_FailFastImmediate_Unexpected(void)

- ea: `0x1800115b4`
- end: `0x1800115bb`
- name: `?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ`
- size: `7`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x18000f5d0`
- `0x18000fe38`
- `0x1800107d0`
- `0x180010b38`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_FailFastImmediate_Unexpected(wil::details::in1diag3 *this)
{
  __fastfail(7u);
}

```

## disassembly

```asm
0x1800115b4  mov     ecx, 7
0x1800115b9  int     29h; Win8: RtlFailFast(ecx)
```
