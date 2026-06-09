# wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)

- ea: `0x1800082d4`
- end: `0x1800082e8`
- name: `?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z`
- size: `20`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this, void *, unsigned int, const char *)`
- caller_count: `9`
- callee_count: `1`
- tags: ``

## callers

- `0x180002fe8`
- `0x1800030b4`
- `0x1800038a8`
- `0x180003c4c`
- `0x180004044`
- `0x180004280`
- `0x180006fa0`
- `0x1800070b4`
- `0x1800079e0`

## callees

- `0x1800026c4`

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
0x1800082d4  sub     rsp, 38h
0x1800082d8  mov     rax, [rsp+38h]
0x1800082dd  mov     [rsp+38h+var_10], rax
0x1800082e2  call    ??$ReportFailure_GetLastError@$02@details@wil@@YAKPEAXIPEBD110@Z; wil::details::ReportFailure_GetLastError<3>(void *,uint,char const *,char const *,char const *,void *)
```
