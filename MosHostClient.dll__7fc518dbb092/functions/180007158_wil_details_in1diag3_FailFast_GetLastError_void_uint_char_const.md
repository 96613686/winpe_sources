# wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)

- ea: `0x180007158`
- end: `0x18000716c`
- name: `?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z`
- size: `20`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *this, void *, __int64, const char *)`
- caller_count: `9`
- callee_count: `1`
- tags: ``

## callers

- `0x180003da4`
- `0x180003e70`
- `0x1800041d4`
- `0x1800045a8`
- `0x180005d7c`
- `0x180006cdc`
- `0x1800077bc`
- `0x180007948`
- `0x180007c10`

## callees

- `0x1800033a4`

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
0x180007158  sub     rsp, 38h
0x18000715c  mov     rax, [rsp+38h]
0x180007161  mov     [rsp+38h+var_10], rax
0x180007166  call    ??$ReportFailure_GetLastError@$02@details@wil@@YAKPEAXIPEBD110@Z; wil::details::ReportFailure_GetLastError<3>(void *,uint,char const *,char const *,char const *,void *)
```
