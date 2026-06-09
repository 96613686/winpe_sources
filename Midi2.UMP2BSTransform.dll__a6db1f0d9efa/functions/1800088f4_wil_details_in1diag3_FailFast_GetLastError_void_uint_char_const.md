# wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)

- ea: `0x1800088f4`
- end: `0x180008908`
- name: `?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z`
- size: `20`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this, void *, unsigned int, const char *)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x1800034d8`
- `0x180003978`
- `0x1800048e0`
- `0x180007588`
- `0x18000823c`

## callees

- `0x180002a58`

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
0x1800088f4  sub     rsp, 38h
0x1800088f8  mov     rax, [rsp+38h]
0x1800088fd  mov     [rsp+38h+var_10], rax
0x180008902  call    ??$ReportFailure_GetLastError@$02@details@wil@@YAKPEAXIPEBD110@Z; wil::details::ReportFailure_GetLastError<3>(void *,uint,char const *,char const *,char const *,void *)
```
