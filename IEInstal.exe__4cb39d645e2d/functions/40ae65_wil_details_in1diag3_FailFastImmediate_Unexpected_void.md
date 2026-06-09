# wil::details::in1diag3::_FailFastImmediate_Unexpected(void)

- ea: `0x40ae65`
- end: `0x40ae6a`
- name: `?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YGXXZ`
- size: `5`
- prototype: `void __noreturn(wil::details::in1diag3 *__hidden this)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x40aa18`
- `0x40aec9`
- `0x40c146`
- `0x40c61e`

## pseudocode

```c
void __stdcall __noreturn wil::details::in1diag3::_FailFastImmediate_Unexpected(wil::details::in1diag3 *this)
{
  __fastfail(7u);
}

```

## disassembly

```asm
0x40ae65  push    7
0x40ae67  pop     ecx
0x40ae68  int     29h; Win8: RtlFailFast(ecx)
```
