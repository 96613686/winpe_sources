# wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)

- ea: `0x180002e24`
- end: `0x180002e38`
- name: `?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z`
- size: `20`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *this, void *, __int64, const char *)`
- caller_count: `9`
- callee_count: `1`
- tags: ``

## callers

- `0x1800031dc`
- `0x180003280`
- `0x180003490`
- `0x180003924`
- `0x180005b00`
- `0x180007368`
- `0x1800075e8`
- `0x180007bf4`
- `0x180007c7c`

## callees

- `0x180002d60`

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
0x180002e24  sub     rsp, 38h
0x180002e28  mov     rax, [rsp+38h]
0x180002e2d  mov     [rsp+38h+var_10], rax; char *
0x180002e32  call    ??$ReportFailure_GetLastError@$02@details@wil@@YAKPEAXIPEBD110@Z; wil::details::ReportFailure_GetLastError<3>(void *,uint,char const *,char const *,char const *,void *)
```
