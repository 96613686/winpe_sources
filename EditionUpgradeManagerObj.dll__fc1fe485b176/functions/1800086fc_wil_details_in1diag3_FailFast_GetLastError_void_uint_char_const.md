# wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)

- ea: `0x1800086fc`
- end: `0x180008710`
- name: `?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z`
- size: `20`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *this, void *, __int64, const char *)`
- caller_count: `12`
- callee_count: `1`
- tags: ``

## callers

- `0x1800033e8`
- `0x1800034b4`
- `0x180003bc4`
- `0x180003f94`
- `0x18000438c`
- `0x1800045d0`
- `0x180007160`
- `0x180007274`
- `0x180007e20`
- `0x18000f020`
- `0x180014ce0`
- `0x180017b1c`

## callees

- `0x180002ac4`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_FailFast_GetLastError(
        wil::details::in1diag3 *this,
        void *a2,
        __int64 a3,
        const char *a4)
{
  int v4; // [rsp+20h] [rbp-18h]
  char *retaddr; // [rsp+38h] [rbp+0h]

  wil::details::ReportFailure_GetLastError<3>(this, a2, a3, a4, v4, retaddr);
}

```

## disassembly

```asm
0x1800086fc  sub     rsp, 38h
0x180008700  mov     rax, [rsp+38h]
0x180008705  mov     [rsp+38h+var_10], rax
0x18000870a  call    ??$ReportFailure_GetLastError@$02@details@wil@@YAKPEAXIPEBD110@Z; wil::details::ReportFailure_GetLastError<3>(void *,uint,char const *,char const *,char const *,void *)
```
